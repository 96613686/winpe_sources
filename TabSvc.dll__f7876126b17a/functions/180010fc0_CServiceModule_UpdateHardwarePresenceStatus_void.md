# CServiceModule::UpdateHardwarePresenceStatus(void)

- ea: `0x180010fc0`
- end: `0x1800110d1`
- name: `?UpdateHardwarePresenceStatus@CServiceModule@@QEAAXXZ`
- size: `273`
- prototype: `void __fastcall(CServiceModule *__hidden this)`
- caller_count: `4`
- callee_count: `6`
- tags: `service_task, installer_update`

## callers

- `0x18000ed70`
- `0x18000f0fc`
- `0x18000fa00`
- `0x180025bbc`

## callees

- `0x180010fc0`
- `0x1800110e0`
- `0x18001477c`
- `0x18001cf00`
- `0x18001cf68`
- `0x18002efa4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800110c0`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800110c0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800110b8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800110b8`
- `USER32!GetSystemMetrics` at `0x180011062`
- `USER32!GetSystemMetrics` at `0x18001106f`
- `USER32!GetSystemMetrics` at `0x180011062`
- `USER32!GetSystemMetrics` at `0x18001106f`

## pseudocode

```c
void __fastcall CServiceModule::UpdateHardwarePresenceStatus(
        CServiceModule *this,
        __int64 a2,
        __int64 a3,
        unsigned int a4)
{
  __int64 TabletOrGamingHardware; // rax
  char v6; // r8
  int v7; // edx
  int v8; // ecx
  unsigned int v9; // eax
  int SystemMetrics; // edi
  void *v11; // rcx
  _BYTE v12[24]; // [rsp+20h] [rbp-18h] BYREF

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController>::__private_IsEnabled(
                          (wil::details *)`wil::Feature<__WilFeatureTraits_Feature_TabsvcMonitorsController>::GetImpl'::`2'::impl,
                          a2,
                          a3,
                          a4) )
  {
    TabletOrGamingHardware = QueryTabletOrGamingHardware(v12);
    v6 = *(_BYTE *)TabletOrGamingHardware;
    v7 = *(_DWORD *)(TabletOrGamingHardware + 4);
    v8 = *(_DWORD *)(TabletOrGamingHardware + 8);
    *((_BYTE *)this + 65) = *(_BYTE *)(TabletOrGamingHardware + 1);
    v9 = v7 | *((_DWORD *)this + 19) & 0xFFFFFEF0;
  }
  else
  {
    if ( dword_180042164 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                     + 4LL) )
    {
      Init_thread_header(&dword_180042164);
      if ( dword_180042164 == -1 )
      {
        byte_180042161 = IsTouchDisabled();
        Init_thread_footer(&dword_180042164);
      }
    }
    if ( byte_180042161 )
    {
      SystemMetrics = 0;
      v8 = 0;
    }
    else
    {
      SystemMetrics = GetSystemMetrics(94);
      v8 = GetSystemMetrics(95);
    }
    v9 = SystemMetrics | *((_DWORD *)this + 19) & 0xFFFFFEF0;
    v6 = SystemMetrics != 0;
  }
  *((_BYTE *)this + 64) = v6;
  *((_DWORD *)this + 20) = v8;
  v11 = (void *)*((_QWORD *)this + 19);
  *((_DWORD *)this + 19) = v9;
  if ( v11 )
  {
    if ( v6 )
      SetEvent(v11);
    else
      ResetEvent(v11);
  }
}

```

## disassembly

```asm
0x180010fc0  mov     [rsp+arg_0], rbx
0x180010fc5  push    rdi
0x180010fc6  sub     rsp, 30h
0x180010fca  mov     rbx, rcx
0x180010fcd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController> `wil::Feature<__WilFeatureTraits_Feature_TabsvcMonitorsController>::GetImpl(void)'::`2'::impl
0x180010fd4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController>::__private_IsEnabled(void)
0x180010fd9  test    al, al
0x180010fdb  jz      short loc_180011005
0x180010fdd  lea     rcx, [rsp+38h+var_18]
0x180010fe2  call    ?QueryTabletOrGamingHardware@@YA?AUHARDWARE_INFO@@XZ; QueryTabletOrGamingHardware(void)
0x180010fe7  mov     r8b, [rax]
0x180010fea  mov     edx, [rax+4]
0x180010fed  mov     ecx, [rax+8]
0x180010ff0  mov     al, [rax+1]
0x180010ff3  mov     [rbx+41h], al
0x180010ff6  mov     eax, [rbx+4Ch]
0x180010ff9  and     eax, 0FFFFFEF0h
0x180010ffe  or      eax, edx
0x180011000  jmp     loc_18001108D
0x180011005  mov     ecx, cs:_tls_index
0x18001100b  mov     rax, gs:58h
0x180011014  mov     edx, 4
0x180011019  mov     rax, [rax+rcx*8]
0x18001101d  mov     eax, [rdx+rax]
0x180011020  cmp     cs:dword_180042164, eax
0x180011026  jle     short loc_180011054
0x180011028  lea     rcx, dword_180042164
0x18001102f  call    _Init_thread_header
0x180011034  cmp     cs:dword_180042164, 0FFFFFFFFh
0x18001103b  jnz     short loc_180011054
0x18001103d  call    ?IsTouchDisabled@@YA_NXZ; IsTouchDisabled(void)
0x180011042  lea     rcx, dword_180042164
0x180011049  mov     cs:byte_180042161, al
0x18001104f  call    _Init_thread_footer
0x180011054  cmp     cs:byte_180042161, 0
0x18001105b  jnz     short loc_180011079
0x18001105d  mov     ecx, 5Eh ; '^'; nIndex
0x180011062  call    cs:__imp_GetSystemMetrics
0x180011068  mov     ecx, 5Fh ; '_'; nIndex
0x18001106d  mov     edi, eax
0x18001106f  call    cs:__imp_GetSystemMetrics
0x180011075  mov     ecx, eax
0x180011077  jmp     short loc_18001107D
0x180011079  xor     edi, edi
0x18001107b  xor     ecx, ecx
0x18001107d  mov     eax, [rbx+4Ch]
0x180011080  and     eax, 0FFFFFEF0h
0x180011085  or      eax, edi
0x180011087  test    edi, edi
0x180011089  setnz   r8b
0x18001108d  mov     r9d, 40h ; '@'
0x180011093  mov     r11, rbx
0x180011096  mov     r10, rbx
0x180011099  mov     [r9+rbx], r8b
0x18001109d  lea     edx, [r9+10h]
0x1800110a1  mov     [rdx+rbx], ecx
0x1800110a4  mov     rcx, [rbx+98h]; hEvent
0x1800110ab  mov     [rbx+4Ch], eax
0x1800110ae  test    rcx, rcx
0x1800110b1  jz      short loc_1800110C6
0x1800110b3  test    r8b, r8b
0x1800110b6  jz      short loc_1800110C0
0x1800110b8  call    cs:__imp_SetEvent
0x1800110be  jmp     short loc_1800110C6
0x1800110c0  call    cs:__imp_ResetEvent
0x1800110c6  mov     rbx, [rsp+38h+arg_0]
0x1800110cb  add     rsp, 30h
0x1800110cf  pop     rdi
0x1800110d0  retn
```
