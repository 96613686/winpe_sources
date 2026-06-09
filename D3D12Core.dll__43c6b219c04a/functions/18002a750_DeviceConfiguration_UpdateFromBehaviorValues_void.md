# DeviceConfiguration::UpdateFromBehaviorValues(void)

- ea: `0x18002a750`
- end: `0x18002a8ef`
- name: `?UpdateFromBehaviorValues@DeviceConfiguration@@QEAAXXZ`
- size: `415`
- prototype: `void __fastcall(DeviceConfiguration *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18007703c`

## callees

- `0x18002a750`
- `0x18002a900`
- `0x18002ae44`
- `0x1801536c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180233174`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180233174`

## string_xrefs

- `0x18002a79c`: `DredMarkersOnlyBreadcrumbs`
- `0x18002a7fb`: `DredBreadcrumbContext`
- `0x18002a85e`: `DredAutoBreadcrumbs`
- `0x1802330db`: `EnableSyncCommandQueuesOr`
- `0x1802330b2`: `EnableSyncCommandQueuesAnd`

## pseudocode

```c
void __fastcall DeviceConfiguration::UpdateFromBehaviorValues(DeviceConfiguration *this)
{
  bool v2; // zf
  _DWORD *v3; // rax
  char *v4; // rcx
  int v5; // eax
  int v6; // eax
  int BehaviorValue; // eax
  int v8; // eax
  HKEY v9; // rax
  HKEY v10; // rdi
  __int64 v11; // [rsp+40h] [rbp+20h] BYREF
  __int64 v12; // [rsp+48h] [rbp+28h] BYREF

  v2 = *((_DWORD *)this + 54) == 3;
  v11 = 0;
  if ( v2 )
  {
    BehaviorValue = GetBehaviorValue("DredWatson", &v11);
    *((_DWORD *)this + 54) = BehaviorValue != 0 ? v11 : 0;
  }
  if ( *((_DWORD *)this + 55) == 3 )
  {
    v8 = GetBehaviorValue("DredAutoBreadcrumbs", &v11);
    *((_DWORD *)this + 55) = v8 != 0 ? v11 : 0;
  }
  if ( *((_DWORD *)this + 56) == 3 )
  {
    v6 = GetBehaviorValue("DredPageFault", &v11);
    *((_DWORD *)this + 56) = v6 != 0 ? v11 : 0;
  }
  if ( *((_DWORD *)this + 57) == 3 )
  {
    v5 = GetBehaviorValue("DredBreadcrumbContext", &v11);
    *((_DWORD *)this + 57) = v5 != 0 ? v11 : 0;
  }
  if ( (unsigned int)GetBehaviorValue("DredMarkersOnlyBreadcrumbs", &v11) && v11 )
    *((_BYTE *)this + 232) = v11 == 1;
  v3 = (_DWORD *)*((_QWORD *)this + 26);
  v11 = 0;
  if ( *v3 || (unsigned int)GetBehaviorValue("RequireSDKLayers", &v11) && v11 )
  {
    v11 = 1;
    v12 = 0;
    GetBehaviorValue("D3D12SDKLayerFlagsAnd", &v11);
    GetBehaviorValue("D3D12SDKLayerFlagsOr", &v12);
    v4 = (char *)*((_QWORD *)this + 26);
    *(_DWORD *)v4 = (v12 | v11 & *(int *)v4) != 0;
  }
  if ( **((_DWORD **)this + 26) )
  {
    v9 = OpenAppRegKey(v4);
    v10 = v9;
    if ( v9 )
    {
      LODWORD(v11) = 1;
      LODWORD(v12) = 0;
      RegDWORD(v9, "EnableGPUBasedValidationFlagsAnd", (unsigned int *)&v11);
      RegDWORD(v10, "EnableGPUBasedValidationFlagsOr", (unsigned int *)&v12);
      *((_DWORD *)this + 48) = v12 | v11 & *((_DWORD *)this + 48);
      LODWORD(v11) = 1;
      LODWORD(v12) = 0;
      RegDWORD(v10, "EnableSyncCommandQueuesAnd", (unsigned int *)&v11);
      RegDWORD(v10, "EnableSyncCommandQueuesOr", (unsigned int *)&v12);
      *((_DWORD *)this + 49) = v12 | v11 & *((_DWORD *)this + 49);
      LODWORD(v11) = 0;
      if ( RegDWORD(v10, "LegacyStateValidation", (unsigned int *)&v11) )
      {
        if ( (_DWORD)v11 == 1 )
        {
          *((_DWORD *)this + 51) = 1;
        }
        else if ( (_DWORD)v11 == 2 )
        {
          *((_DWORD *)this + 51) = 0;
        }
      }
      if ( *((_DWORD *)this + 48) )
      {
        LODWORD(v11) = 0;
        if ( RegDWORD(v10, "GbvStateTracking", (unsigned int *)&v11) )
        {
          if ( (_DWORD)v11 == 1 )
          {
            *((_DWORD *)this + 50) |= 1u;
          }
          else if ( (_DWORD)v11 == 2 )
          {
            *((_DWORD *)this + 50) &= ~1u;
          }
        }
      }
      RegCloseKey(v10);
    }
  }
}

```

## disassembly

```asm
0x18002a750  mov     [rsp-18h+arg_10], rbx
0x18002a755  push    rbp
0x18002a756  push    rsi
0x18002a757  push    rdi
0x18002a758  mov     rbp, rsp
0x18002a75b  sub     rsp, 20h
0x18002a75f  xor     esi, esi
0x18002a761  mov     rbx, rcx
0x18002a764  cmp     dword ptr [rcx+0D8h], 3
0x18002a76b  mov     [rbp+arg_0], rsi
0x18002a76f  jz      loc_18002A838
0x18002a775  cmp     dword ptr [rbx+0DCh], 3
0x18002a77c  jz      loc_18002A85A
0x18002a782  cmp     dword ptr [rbx+0E0h], 3
0x18002a789  jz      loc_18002A816
0x18002a78f  cmp     dword ptr [rbx+0E4h], 3
0x18002a796  jz      short loc_18002A7F7
0x18002a798  lea     rdx, [rbp+arg_0]
0x18002a79c  lea     rcx, aDredmarkersonl; "DredMarkersOnlyBreadcrumbs"
0x18002a7a3  call    GetBehaviorValue
0x18002a7a8  test    eax, eax
0x18002a7aa  jnz     loc_18002A87C
0x18002a7b0  mov     rax, [rbx+0D0h]
0x18002a7b7  mov     [rbp+arg_0], rsi
0x18002a7bb  cmp     [rax], esi
0x18002a7bd  jnz     loc_18002A8A5
0x18002a7c3  lea     rdx, [rbp+arg_0]
0x18002a7c7  lea     rcx, aRequiresdklaye; "RequireSDKLayers"
0x18002a7ce  call    GetBehaviorValue
0x18002a7d3  test    eax, eax
0x18002a7d5  jnz     loc_18002A89B
0x18002a7db  mov     rax, [rbx+0D0h]
0x18002a7e2  cmp     [rax], esi
0x18002a7e4  jnz     loc_180233064
0x18002a7ea  mov     rbx, [rsp+20h+arg_10]
0x18002a7ef  add     rsp, 20h
0x18002a7f3  pop     rdi
0x18002a7f4  pop     rsi
0x18002a7f5  pop     rbp
0x18002a7f6  retn
0x18002a7f7  lea     rdx, [rbp+arg_0]
0x18002a7fb  lea     rcx, aDredbreadcrumb; "DredBreadcrumbContext"
0x18002a802  call    GetBehaviorValue
0x18002a807  neg     eax
0x18002a809  sbb     ecx, ecx
0x18002a80b  and     ecx, dword ptr [rbp+arg_0]
0x18002a80e  mov     [rbx+0E4h], ecx
0x18002a814  jmp     short loc_18002A798
0x18002a816  lea     rdx, [rbp+arg_0]
0x18002a81a  lea     rcx, aDredpagefault; "DredPageFault"
0x18002a821  call    GetBehaviorValue
0x18002a826  neg     eax
0x18002a828  sbb     ecx, ecx
0x18002a82a  and     ecx, dword ptr [rbp+arg_0]
0x18002a82d  mov     [rbx+0E0h], ecx
0x18002a833  jmp     loc_18002A78F
0x18002a838  lea     rdx, [rbp+arg_0]
0x18002a83c  lea     rcx, aDredwatson; "DredWatson"
0x18002a843  call    GetBehaviorValue
0x18002a848  neg     eax
0x18002a84a  sbb     ecx, ecx
0x18002a84c  and     ecx, dword ptr [rbp+arg_0]
0x18002a84f  mov     [rbx+0D8h], ecx
0x18002a855  jmp     loc_18002A775
0x18002a85a  lea     rdx, [rbp+arg_0]
0x18002a85e  lea     rcx, aDredautobreadc; "DredAutoBreadcrumbs"
0x18002a865  call    GetBehaviorValue
0x18002a86a  neg     eax
0x18002a86c  sbb     ecx, ecx
0x18002a86e  and     ecx, dword ptr [rbp+arg_0]
0x18002a871  mov     [rbx+0DCh], ecx
0x18002a877  jmp     loc_18002A782
0x18002a87c  mov     rax, [rbp+arg_0]
0x18002a880  test    rax, rax
0x18002a883  jz      loc_18002A7B0
0x18002a889  cmp     rax, 1
0x18002a88d  setz    al
0x18002a890  mov     [rbx+0E8h], al
0x18002a896  jmp     loc_18002A7B0
0x18002a89b  cmp     [rbp+arg_0], rsi
0x18002a89f  jz      loc_18002A7DB
0x18002a8a5  lea     rdx, [rbp+arg_0]
0x18002a8a9  mov     [rbp+arg_0], 1
0x18002a8b1  lea     rcx, aD3d12sdklayerf; "D3D12SDKLayerFlagsAnd"
0x18002a8b8  mov     [rbp+arg_8], rsi
0x18002a8bc  call    GetBehaviorValue
0x18002a8c1  lea     rdx, [rbp+arg_8]
0x18002a8c5  lea     rcx, aD3d12sdklayerf_0; "D3D12SDKLayerFlagsOr"
0x18002a8cc  call    GetBehaviorValue
0x18002a8d1  mov     rcx, [rbx+0D0h]
0x18002a8d8  movsxd  rax, dword ptr [rcx]
0x18002a8db  and     rax, [rbp+arg_0]
0x18002a8df  or      rax, [rbp+arg_8]
0x18002a8e3  mov     eax, esi
0x18002a8e5  setnz   al
0x18002a8e8  mov     [rcx], eax
0x18002a8ea  jmp     loc_18002A7DB
0x180233064  call    ?OpenAppRegKey@@YAPEAUHKEY__@@PEBD@Z; OpenAppRegKey(char const *)
0x180233069  mov     rdi, rax
0x18023306c  test    rax, rax
0x18023306f  jz      loc_18002A7EA
0x180233075  lea     r8, [rbp+arg_0]; unsigned int *
0x180233079  mov     dword ptr [rbp+arg_0], 1
0x180233080  lea     rdx, aEnablegpubased; "EnableGPUBasedValidationFlagsAnd"
0x180233087  mov     dword ptr [rbp+arg_8], esi
0x18023308a  mov     rcx, rax; HKEY
0x18023308d  call    ?RegDWORD@@YA_NPEAUHKEY__@@PEBDPEAK@Z; RegDWORD(HKEY__ *,char const *,ulong *)
0x180233092  lea     r8, [rbp+arg_8]; unsigned int *
0x180233096  mov     rcx, rdi; HKEY
0x180233099  lea     rdx, aEnablegpubased_0; "EnableGPUBasedValidationFlagsOr"
0x1802330a0  call    ?RegDWORD@@YA_NPEAUHKEY__@@PEBDPEAK@Z; RegDWORD(HKEY__ *,char const *,ulong *)
0x1802330a5  mov     eax, [rbx+0C0h]
0x1802330ab  lea     r8, [rbp+arg_0]; unsigned int *
0x1802330af  and     eax, dword ptr [rbp+arg_0]
0x1802330b2  lea     rdx, aEnablesynccomm; "EnableSyncCommandQueuesAnd"
0x1802330b9  or      eax, dword ptr [rbp+arg_8]
0x1802330bc  mov     rcx, rdi; HKEY
0x1802330bf  mov     [rbx+0C0h], eax
0x1802330c5  mov     dword ptr [rbp+arg_0], 1
0x1802330cc  mov     dword ptr [rbp+arg_8], esi
0x1802330cf  call    ?RegDWORD@@YA_NPEAUHKEY__@@PEBDPEAK@Z; RegDWORD(HKEY__ *,char const *,ulong *)
0x1802330d4  lea     r8, [rbp+arg_8]; unsigned int *
0x1802330d8  mov     rcx, rdi; HKEY
0x1802330db  lea     rdx, aEnablesynccomm_0; "EnableSyncCommandQueuesOr"
0x1802330e2  call    ?RegDWORD@@YA_NPEAUHKEY__@@PEBDPEAK@Z; RegDWORD(HKEY__ *,char const *,ulong *)
0x1802330e7  mov     eax, [rbx+0C4h]
0x1802330ed  lea     r8, [rbp+arg_0]; unsigned int *
0x1802330f1  and     eax, dword ptr [rbp+arg_0]
0x1802330f4  lea     rdx, aLegacystateval; "LegacyStateValidation"
0x1802330fb  or      eax, dword ptr [rbp+arg_8]
0x1802330fe  mov     rcx, rdi; HKEY
0x180233101  mov     [rbx+0C4h], eax
0x180233107  mov     dword ptr [rbp+arg_0], esi
0x18023310a  call    ?RegDWORD@@YA_NPEAUHKEY__@@PEBDPEAK@Z; RegDWORD(HKEY__ *,char const *,ulong *)
0x18023310f  test    al, al
0x180233111  jz      short loc_180233132
0x180233113  mov     eax, dword ptr [rbp+arg_0]
0x180233116  sub     eax, 1
0x180233119  jz      short loc_180233128
0x18023311b  cmp     eax, 1
0x18023311e  jnz     short loc_180233132
0x180233120  mov     [rbx+0CCh], esi
0x180233126  jmp     short loc_180233132
0x180233128  mov     dword ptr [rbx+0CCh], 1
0x180233132  cmp     [rbx+0C0h], esi
0x180233138  jz      short loc_180233171
0x18023313a  lea     r8, [rbp+arg_0]; unsigned int *
0x18023313e  mov     dword ptr [rbp+arg_0], esi
0x180233141  lea     rdx, aGbvstatetracki; "GbvStateTracking"
0x180233148  mov     rcx, rdi; HKEY
0x18023314b  call    ?RegDWORD@@YA_NPEAUHKEY__@@PEBDPEAK@Z; RegDWORD(HKEY__ *,char const *,ulong *)
0x180233150  test    al, al
0x180233152  jz      short loc_180233171
0x180233154  mov     eax, dword ptr [rbp+arg_0]
0x180233157  sub     eax, 1
0x18023315a  jz      short loc_18023316A
0x18023315c  cmp     eax, 1
0x18023315f  jnz     short loc_180233171
0x180233161  and     dword ptr [rbx+0C8h], 0FFFFFFFEh
0x180233168  jmp     short loc_180233171
0x18023316a  or      dword ptr [rbx+0C8h], 1
0x180233171  mov     rcx, rdi; hKey
0x180233174  call    cs:__imp_RegCloseKey
0x18023317a  nop
0x18023317b  jmp     loc_18002A7EA
```
