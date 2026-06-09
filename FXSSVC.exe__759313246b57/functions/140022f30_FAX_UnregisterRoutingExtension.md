# FAX_UnregisterRoutingExtension

- ea: `0x140022f30`
- end: `0x140023112`
- name: `FAX_UnregisterRoutingExtension`
- size: `482`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x140004f64`
- `0x140022f30`
- `0x140047d20`
- `0x1400745e4`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1400230c5`
- `ADVAPI32!RegCloseKey` at `0x1400230c5`
- `ADVAPI32!RegOpenKeyExW` at `0x140023031`
- `ADVAPI32!RegOpenKeyExW` at `0x140023031`
- `KERNEL32!GetLastError` at `0x140023082`
- `KERNEL32!GetLastError` at `0x140023082`

## string_xrefs

- `0x140023023`: `Software\Microsoft\Fax\Routing Extensions`

## pseudocode

```c
__int64 __fastcall FAX_UnregisterRoutingExtension(__int64 a1, __int64 a2)
{
  unsigned int v3; // ebx
  CMapDeviceId *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r9
  DWORD LastError; // eax
  unsigned int v9; // eax
  int v10; // [rsp+60h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  v10 = 0;
  hKey = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 395, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
  }
  v3 = FaxSvcAccessCheck(0x40u, &v10, 0, 1);
  if ( v3 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v3;
    }
    v5 = 396;
    goto LABEL_10;
  }
  if ( v10 )
  {
    v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fax\\Routing Extensions", 0, 0x2001Fu, &hKey);
    if ( !v3 )
    {
      if ( !(unsigned int)DeleteRegistryKey(hKey, a2) )
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            399,
            (unsigned int)&WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
            a2,
            LastError);
        }
      }
      v9 = RegCloseKey(hKey);
      if ( !v9 )
        return v3;
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return v3;
      }
      v5 = 400;
      v6 = v9;
      goto LABEL_32;
    }
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v3;
    }
    v5 = 398;
LABEL_10:
    v6 = v3;
LABEL_32:
    WPP_SF_d(*((_QWORD *)v4 + 2), v5, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v6);
    return v3;
  }
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 397, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
  }
  return 5;
}

```

## disassembly

```asm
0x140022f30  mov     [rsp+arg_0], rbx
0x140022f35  push    rbp
0x140022f36  push    rdi
0x140022f37  push    r15
0x140022f39  sub     rsp, 30h
0x140022f3d  mov     rdi, rdx
0x140022f40  mov     [rsp+48h+arg_10], 0
0x140022f48  mov     [rsp+48h+hKey], 0
0x140022f51  mov     rcx, cs:WPP_GLOBAL_Control
0x140022f58  lea     rbp, WPP_GLOBAL_Control
0x140022f5f  lea     r15, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x140022f66  cmp     rcx, rbp
0x140022f69  jz      short loc_140022F88
0x140022f6b  test    byte ptr [rcx+1Ch], 4
0x140022f6f  jz      short loc_140022F88
0x140022f71  cmp     byte ptr [rcx+19h], 5
0x140022f75  jb      short loc_140022F88
0x140022f77  mov     rcx, [rcx+10h]
0x140022f7b  mov     edx, 18Bh
0x140022f80  mov     r8, r15
0x140022f83  call    WPP_SF_
0x140022f88  mov     r9d, 1; int
0x140022f8e  lea     rdx, [rsp+48h+arg_10]; int *
0x140022f93  xor     r8d, r8d; unsigned int *
0x140022f96  lea     ecx, [r9+3Fh]; unsigned int
0x140022f9a  call    ?FaxSvcAccessCheck@@YAKKPEAHPEAKH@Z; FaxSvcAccessCheck(ulong,int *,ulong *,int)
0x140022f9f  mov     ebx, eax
0x140022fa1  test    eax, eax
0x140022fa3  jz      short loc_140022FD6
0x140022fa5  mov     rcx, cs:WPP_GLOBAL_Control
0x140022fac  cmp     rcx, rbp
0x140022faf  jz      loc_140023101
0x140022fb5  test    byte ptr [rcx+1Ch], 4
0x140022fb9  jz      loc_140023101
0x140022fbf  cmp     byte ptr [rcx+19h], 2
0x140022fc3  jb      loc_140023101
0x140022fc9  mov     edx, 18Ch
0x140022fce  mov     r9d, ebx
0x140022fd1  jmp     loc_1400230F5
0x140022fd6  cmp     [rsp+48h+arg_10], 0
0x140022fdb  jnz     short loc_140023010
0x140022fdd  mov     rcx, cs:WPP_GLOBAL_Control
0x140022fe4  cmp     rcx, rbp
0x140022fe7  jz      short loc_140023006
0x140022fe9  test    byte ptr [rcx+1Ch], 4
0x140022fed  jz      short loc_140023006
0x140022fef  cmp     byte ptr [rcx+19h], 2
0x140022ff3  jb      short loc_140023006
0x140022ff5  mov     rcx, [rcx+10h]
0x140022ff9  mov     edx, 18Dh
0x140022ffe  mov     r8, r15
0x140023001  call    WPP_SF_
0x140023006  mov     eax, 5
0x14002300b  jmp     loc_140023103
0x140023010  lea     rax, [rsp+48h+hKey]
0x140023015  mov     r9d, 2001Fh; samDesired
0x14002301b  xor     r8d, r8d; ulOptions
0x14002301e  mov     [rsp+48h+phkResult], rax; phkResult
0x140023023  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Fax\\Routing Exten"...
0x14002302a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140023031  call    cs:__imp_RegOpenKeyExW
0x140023038  nop     dword ptr [rax+rax+00h]
0x14002303d  mov     ebx, eax
0x14002303f  test    eax, eax
0x140023041  jz      short loc_140023071
0x140023043  mov     rcx, cs:WPP_GLOBAL_Control
0x14002304a  cmp     rcx, rbp
0x14002304d  jz      loc_140023101
0x140023053  test    byte ptr [rcx+1Ch], 4
0x140023057  jz      loc_140023101
0x14002305d  cmp     byte ptr [rcx+19h], 2
0x140023061  jb      loc_140023101
0x140023067  mov     edx, 18Eh
0x14002306c  jmp     loc_140022FCE
0x140023071  mov     rcx, [rsp+48h+hKey]
0x140023076  mov     rdx, rdi
0x140023079  call    DeleteRegistryKey
0x14002307e  test    eax, eax
0x140023080  jnz     short loc_1400230C0
0x140023082  call    cs:__imp_GetLastError
0x140023089  nop     dword ptr [rax+rax+00h]
0x14002308e  mov     ebx, eax
0x140023090  mov     rcx, cs:WPP_GLOBAL_Control
0x140023097  cmp     rcx, rbp
0x14002309a  jz      short loc_1400230C0
0x14002309c  test    byte ptr [rcx+1Ch], 4
0x1400230a0  jz      short loc_1400230C0
0x1400230a2  cmp     byte ptr [rcx+19h], 2
0x1400230a6  jb      short loc_1400230C0
0x1400230a8  mov     rcx, [rcx+10h]
0x1400230ac  mov     edx, 18Fh
0x1400230b1  mov     r9, rdi
0x1400230b4  mov     dword ptr [rsp+48h+phkResult], eax
0x1400230b8  mov     r8, r15
0x1400230bb  call    WPP_SF_Sd
0x1400230c0  mov     rcx, [rsp+48h+hKey]; hKey
0x1400230c5  call    cs:__imp_RegCloseKey
0x1400230cc  nop     dword ptr [rax+rax+00h]
0x1400230d1  test    eax, eax
0x1400230d3  jz      short loc_140023101
0x1400230d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400230dc  cmp     rcx, rbp
0x1400230df  jz      short loc_140023101
0x1400230e1  test    byte ptr [rcx+1Ch], 4
0x1400230e5  jz      short loc_140023101
0x1400230e7  cmp     byte ptr [rcx+19h], 2
0x1400230eb  jb      short loc_140023101
0x1400230ed  mov     edx, 190h
0x1400230f2  mov     r9d, eax
0x1400230f5  mov     rcx, [rcx+10h]
0x1400230f9  mov     r8, r15
0x1400230fc  call    WPP_SF_d
0x140023101  mov     eax, ebx
0x140023103  mov     rbx, [rsp+48h+arg_0]
0x140023108  add     rsp, 30h
0x14002310c  pop     r15
0x14002310e  pop     rdi
0x14002310f  pop     rbp
0x140023110  retn
```
