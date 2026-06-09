# CDsmAccessCheck::IsUserAllowedToRemove(_GUID const &,void *,ulong,DSM_REMOVABLE_FLAGS *)

- ea: `0x18000a934`
- end: `0x18000abd8`
- name: `?IsUserAllowedToRemove@CDsmAccessCheck@@SAJAEBU_GUID@@PEAXKPEAW4DSM_REMOVABLE_FLAGS@@@Z`
- size: `676`
- prototype: `__int64 __fastcall(const struct _GUID *, void *, DWORD dwProcessId, enum DSM_REMOVABLE_FLAGS *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000abe0`

## callees

- `0x1800017c0`
- `0x180001dc0`
- `0x180001e28`
- `0x180002570`
- `0x18000a934`
- `0x18000b678`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000a9ea`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000a9ea`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000a991`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000a991`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18000ab0b`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18000ab0b`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x18000aa62`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x18000aa62`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x18000a9f0`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x18000a9f0`

## pseudocode

```c
__int64 __fastcall CDsmAccessCheck::IsUserAllowedToRemove(
        const struct _GUID *a1,
        void *a2,
        DWORD dwProcessId,
        enum DSM_REMOVABLE_FLAGS *a4)
{
  int v8; // ebx
  signed int ObjectProperties; // r14d
  bool v10; // si
  bool v11; // zf
  bool v12; // bl
  bool v13; // di
  bool v14; // r15
  __int64 v15; // r8
  __int64 v16; // rcx
  __int64 result; // rax
  bool v18; // [rsp+40h] [rbp-59h] BYREF
  bool v19; // [rsp+41h] [rbp-58h] BYREF
  DWORD pSessionId; // [rsp+44h] [rbp-55h] BYREF
  __int64 v21; // [rsp+48h] [rbp-51h]
  OLECHAR sz[40]; // [rsp+50h] [rbp-49h] BYREF

  *(_DWORD *)a4 = 0;
  v18 = 0;
  v19 = 0;
  memset_0(sz, 0, 0x4Eu);
  v8 = StringFromGUID2(a1, sz, 39);
  ObjectProperties = v8 == 0 ? 0x80004005 : 0;
  CDsmAccessCheck::_IsUserSIDAllowedToRemove(a1, a2, &v18, &v19);
  v10 = v19;
  v11 = v8 == 0;
  v12 = v18;
  if ( !v11 && !v18 && !v19 )
  {
    pSessionId = 0;
    ProcessIdToSessionId(dwProcessId, &pSessionId);
    if ( WTSGetActiveConsoleSessionId() == pSessionId )
    {
      v13 = 1;
      v14 = 0;
      if ( __TSS0__4__IsUserAllowedToRemove_CDsmAccessCheck__SAJAEBU_GUID__PEAXKPEAW4DSM_REMOVABLE_FLAGS___Z_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL) )
      {
        Init_thread_header(&__TSS0__4__IsUserAllowedToRemove_CDsmAccessCheck__SAJAEBU_GUID__PEAXKPEAW4DSM_REMOVABLE_FLAGS___Z_4HA);
        if ( __TSS0__4__IsUserAllowedToRemove_CDsmAccessCheck__SAJAEBU_GUID__PEAXKPEAW4DSM_REMOVABLE_FLAGS___Z_4HA == -1 )
        {
          *(DEVPROPKEY *)`CDsmAccessCheck::IsUserAllowedToRemove'::`5'::Keys = DEVPKEY_DeviceContainer_IsConnected;
          dword_1800179A4 = 0;
          qword_1800179A8 = 0;
          *(DEVPROPKEY *)byte_1800179B0 = DEVPKEY_DeviceContainer_IsPaired;
          dword_1800179C4 = 0;
          qword_1800179C8 = 0;
          Init_thread_footer(&__TSS0__4__IsUserAllowedToRemove_CDsmAccessCheck__SAJAEBU_GUID__PEAXKPEAW4DSM_REMOVABLE_FLAGS___Z_4HA);
        }
      }
      pSessionId = 0;
      v21 = 0;
      ObjectProperties = DevGetObjectProperties(2, sz, 0);
      if ( ObjectProperties >= 0 && pSessionId == 2 )
      {
        v15 = 0;
        v16 = 0;
        do
        {
          if ( *(_DWORD *)(v16 + v21 + 16) == 55 )
          {
            if ( *(_QWORD *)(v16 + v21) == *(_QWORD *)&DEVPKEY_DeviceContainer_IsConnected.fmtid.Data1
              && *(_QWORD *)(v16 + v21 + 8) == *(_QWORD *)DEVPKEY_DeviceContainer_IsConnected.fmtid.Data4
              && *(_DWORD *)(v16 + v21 + 32) == 17 )
            {
              v13 = **(_BYTE **)(v16 + v21 + 40) == 0xFF;
            }
          }
          else if ( *(_DWORD *)(v16 + v21 + 16) == 56
                 && *(_QWORD *)(v16 + v21) == *(_QWORD *)&DEVPKEY_DeviceContainer_IsPaired.fmtid.Data1
                 && *(_QWORD *)(v16 + v21 + 8) == *(_QWORD *)DEVPKEY_DeviceContainer_IsPaired.fmtid.Data4
                 && *(_DWORD *)(v16 + v21 + 32) == 17 )
          {
            v14 = **(_BYTE **)(v16 + v21 + 40) == 0xFF;
          }
          ++v15;
          v16 += 48;
        }
        while ( v15 != 2 );
      }
      if ( v21 )
        DevFreeObjectProperties(pSessionId, v21);
      if ( !v13 || v14 )
        v12 = 1;
    }
  }
  result = (unsigned int)ObjectProperties;
  *(_DWORD *)a4 |= (!v10 ? 2 : 0) | v12;
  return result;
}

```

## disassembly

```asm
0x18000a934  push    rbp
0x18000a936  push    rbx
0x18000a937  push    rsi
0x18000a938  push    rdi
0x18000a939  push    r12
0x18000a93b  push    r13
0x18000a93d  push    r14
0x18000a93f  push    r15
0x18000a941  lea     rbp, [rsp-1Fh]
0x18000a946  sub     rsp, 0B8h
0x18000a94d  mov     rax, cs:__security_cookie
0x18000a954  xor     rax, rsp
0x18000a957  mov     [rbp+57h+var_50], rax
0x18000a95b  xor     r12d, r12d
0x18000a95e  mov     r15d, r8d
0x18000a961  mov     rsi, rdx
0x18000a964  mov     [r9], r12d
0x18000a967  mov     rdi, rcx
0x18000a96a  mov     [rbp+57h+var_B0], r12b
0x18000a96e  xor     edx, edx; Val
0x18000a970  mov     [rbp+57h+var_AF], r12b
0x18000a974  lea     r8d, [r12+4Eh]; Size
0x18000a979  mov     r13, r9
0x18000a97c  lea     rcx, [rbp+57h+sz]; void *
0x18000a980  call    memset_0
0x18000a985  lea     r8d, [r12+27h]; cchMax
0x18000a98a  mov     rcx, rdi; rguid
0x18000a98d  lea     rdx, [rbp+57h+sz]; lpsz
0x18000a991  call    cs:__imp_StringFromGUID2
0x18000a997  lea     r9, [rbp+57h+var_AF]; bool *
0x18000a99b  mov     rdx, rsi; void *
0x18000a99e  mov     r8d, eax
0x18000a9a1  mov     rcx, rdi; struct _GUID *
0x18000a9a4  neg     r8d
0x18000a9a7  mov     ebx, eax
0x18000a9a9  lea     r8, [rbp+57h+var_B0]; bool *
0x18000a9ad  sbb     r14d, r14d
0x18000a9b0  not     r14d
0x18000a9b3  and     r14d, 80004005h
0x18000a9ba  call    ?_IsUserSIDAllowedToRemove@CDsmAccessCheck@@CAXAEBU_GUID@@PEAXPEA_N2@Z; CDsmAccessCheck::_IsUserSIDAllowedToRemove(_GUID const &,void *,bool *,bool *)
0x18000a9bf  mov     sil, [rbp+57h+var_AF]
0x18000a9c3  test    ebx, ebx
0x18000a9c5  mov     bl, [rbp+57h+var_B0]
0x18000a9c8  jz      loc_18000AB1D
0x18000a9ce  test    bl, bl
0x18000a9d0  jnz     loc_18000AB1D
0x18000a9d6  test    sil, sil
0x18000a9d9  jnz     loc_18000AB1D
0x18000a9df  lea     rdx, [rbp+57h+pSessionId]; pSessionId
0x18000a9e3  mov     [rbp+57h+pSessionId], r12d
0x18000a9e7  mov     ecx, r15d; dwProcessId
0x18000a9ea  call    cs:__imp_ProcessIdToSessionId
0x18000a9f0  call    cs:__imp_WTSGetActiveConsoleSessionId
0x18000a9f6  cmp     eax, [rbp+57h+pSessionId]
0x18000a9f9  jnz     loc_18000AB1D
0x18000a9ff  mov     ecx, cs:_tls_index
0x18000aa05  mov     dil, 1
0x18000aa08  mov     rax, gs:58h
0x18000aa11  mov     r15b, r12b
0x18000aa14  mov     edx, 4
0x18000aa19  mov     rax, [rax+rcx*8]
0x18000aa1d  mov     eax, [rdx+rax]
0x18000aa20  cmp     cs:?$TSS0@?4??IsUserAllowedToRemove@CDsmAccessCheck@@SAJAEBU_GUID@@PEAXKPEAW4DSM_REMOVABLE_FLAGS@@@Z@4HA, eax
0x18000aa26  jg      loc_18000AB5E
0x18000aa2c  lea     rax, [rbp+57h+var_A8]
0x18000aa30  mov     [rbp+57h+pSessionId], r12d
0x18000aa34  mov     [rsp+0F0h+var_C0], rax
0x18000aa39  lea     rdx, [rbp+57h+sz]
0x18000aa3d  lea     rax, [rbp+57h+pSessionId]
0x18000aa41  mov     [rbp+57h+var_A8], r12
0x18000aa45  mov     [rsp+0F0h+var_C8], rax
0x18000aa4a  mov     r9d, 2
0x18000aa50  lea     rax, ?Keys@?4??IsUserAllowedToRemove@CDsmAccessCheck@@SAJAEBU_GUID@@PEAXKPEAW4DSM_REMOVABLE_FLAGS@@@Z@4QBU_DEVPROPCOMPKEY@@B; _DEVPROPCOMPKEY const near * const `CDsmAccessCheck::IsUserAllowedToRemove(_GUID const &,void *,ulong,DSM_REMOVABLE_FLAGS *)'::`5'::Keys
0x18000aa57  xor     r8d, r8d
0x18000aa5a  mov     ecx, r9d
0x18000aa5d  mov     [rsp+0F0h+var_D0], rax
0x18000aa62  call    cs:__imp_DevGetObjectProperties
0x18000aa68  mov     rdx, [rbp+57h+var_A8]
0x18000aa6c  mov     r14d, eax
0x18000aa6f  test    eax, eax
0x18000aa71  js      loc_18000AB03
0x18000aa77  cmp     [rbp+57h+pSessionId], 2
0x18000aa7b  jnz     loc_18000AB03
0x18000aa81  mov     r9, qword ptr cs:DEVPKEY_DeviceContainer_IsConnected.fmtid.Data4
0x18000aa88  mov     r8, r12
0x18000aa8b  mov     r10, qword ptr cs:DEVPKEY_DeviceContainer_IsConnected.fmtid.Data1
0x18000aa92  mov     rcx, r12
0x18000aa95  mov     r12, qword ptr cs:DEVPKEY_DeviceContainer_IsPaired.fmtid.Data1
0x18000aa9c  mov     r11, qword ptr cs:DEVPKEY_DeviceContainer_IsPaired.fmtid.Data4
0x18000aaa3  cmp     dword ptr [rcx+rdx+10h], 37h ; '7'
0x18000aaa8  jnz     short loc_18000AACC
0x18000aaaa  cmp     [rcx+rdx], r10
0x18000aaae  jnz     short loc_18000AAF3
0x18000aab0  cmp     [rcx+rdx+8], r9
0x18000aab5  jnz     short loc_18000AAF3
0x18000aab7  cmp     dword ptr [rcx+rdx+20h], 11h
0x18000aabc  jnz     short loc_18000AAF3
0x18000aabe  mov     rax, [rcx+rdx+28h]
0x18000aac3  cmp     byte ptr [rax], 0FFh
0x18000aac6  setz    dil
0x18000aaca  jmp     short loc_18000AAF3
0x18000aacc  cmp     dword ptr [rcx+rdx+10h], 38h ; '8'
0x18000aad1  jnz     short loc_18000AAF3
0x18000aad3  cmp     [rcx+rdx], r12
0x18000aad7  jnz     short loc_18000AAF3
0x18000aad9  cmp     [rcx+rdx+8], r11
0x18000aade  jnz     short loc_18000AAF3
0x18000aae0  cmp     dword ptr [rcx+rdx+20h], 11h
0x18000aae5  jnz     short loc_18000AAF3
0x18000aae7  mov     rax, [rcx+rdx+28h]
0x18000aaec  cmp     byte ptr [rax], 0FFh
0x18000aaef  setz    r15b
0x18000aaf3  inc     r8
0x18000aaf6  add     rcx, 30h ; '0'
0x18000aafa  cmp     r8, 2
0x18000aafe  jnz     short loc_18000AAA3
0x18000ab00  xor     r12d, r12d
0x18000ab03  test    rdx, rdx
0x18000ab06  jz      short loc_18000AB11
0x18000ab08  mov     ecx, [rbp+57h+pSessionId]
0x18000ab0b  call    cs:__imp_DevFreeObjectProperties
0x18000ab11  test    dil, dil
0x18000ab14  jz      short loc_18000AB1B
0x18000ab16  test    r15b, r15b
0x18000ab19  jz      short loc_18000AB1D
0x18000ab1b  mov     bl, 1
0x18000ab1d  mov     ecx, [r13+0]
0x18000ab21  test    bl, bl
0x18000ab23  mov     eax, r12d
0x18000ab26  setnz   al
0x18000ab29  or      ecx, eax
0x18000ab2b  neg     sil
0x18000ab2e  sbb     eax, eax
0x18000ab30  not     eax
0x18000ab32  and     eax, 2
0x18000ab35  or      ecx, eax
0x18000ab37  mov     eax, r14d
0x18000ab3a  mov     [r13+0], ecx
0x18000ab3e  mov     rcx, [rbp+57h+var_50]
0x18000ab42  xor     rcx, rsp; StackCookie
0x18000ab45  call    __security_check_cookie
0x18000ab4a  add     rsp, 0B8h
0x18000ab51  pop     r15
0x18000ab53  pop     r14
0x18000ab55  pop     r13
0x18000ab57  pop     r12
0x18000ab59  pop     rdi
0x18000ab5a  pop     rsi
0x18000ab5b  pop     rbx
0x18000ab5c  pop     rbp
0x18000ab5d  retn
0x18000ab5e  lea     rcx, ?$TSS0@?4??IsUserAllowedToRemove@CDsmAccessCheck@@SAJAEBU_GUID@@PEAXKPEAW4DSM_REMOVABLE_FLAGS@@@Z@4HA
0x18000ab65  call    _Init_thread_header
0x18000ab6a  cmp     cs:?$TSS0@?4??IsUserAllowedToRemove@CDsmAccessCheck@@SAJAEBU_GUID@@PEAXKPEAW4DSM_REMOVABLE_FLAGS@@@Z@4HA, 0FFFFFFFFh
0x18000ab71  jnz     loc_18000AA2C
0x18000ab77  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceContainer_IsConnected.fmtid.Data1
0x18000ab7e  mov     eax, cs:DEVPKEY_DeviceContainer_IsConnected.pid
0x18000ab84  lea     rcx, ?$TSS0@?4??IsUserAllowedToRemove@CDsmAccessCheck@@SAJAEBU_GUID@@PEAXKPEAW4DSM_REMOVABLE_FLAGS@@@Z@4HA
0x18000ab8b  mov     dword ptr cs:?Keys@?4??IsUserAllowedToRemove@CDsmAccessCheck@@SAJAEBU_GUID@@PEAXKPEAW4DSM_REMOVABLE_FLAGS@@@Z@4QBU_DEVPROPCOMPKEY@@B+10h, eax; _DEVPROPCOMPKEY const near * const `CDsmAccessCheck::IsUserAllowedToRemove(_GUID const &,void *,ulong,DSM_REMOVABLE_FLAGS *)'::`5'::Keys
0x18000ab91  mov     eax, cs:DEVPKEY_DeviceContainer_IsPaired.pid
0x18000ab97  movaps  xmmword ptr cs:?Keys@?4??IsUserAllowedToRemove@CDsmAccessCheck@@SAJAEBU_GUID@@PEAXKPEAW4DSM_REMOVABLE_FLAGS@@@Z@4QBU_DEVPROPCOMPKEY@@B, xmm0; _DEVPROPCOMPKEY const near * const `CDsmAccessCheck::IsUserAllowedToRemove(_GUID const &,void *,ulong,DSM_REMOVABLE_FLAGS *)'::`5'::Keys
0x18000ab9e  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceContainer_IsPaired.fmtid.Data1
0x18000aba5  mov     cs:dword_1800179A4, r12d
0x18000abac  mov     cs:qword_1800179A8, r12
0x18000abb3  movaps  xmmword ptr cs:byte_1800179B0, xmm0
0x18000abba  mov     dword ptr cs:byte_1800179B0+10h, eax
0x18000abc0  mov     cs:dword_1800179C4, r12d
0x18000abc7  mov     cs:qword_1800179C8, r12
0x18000abce  call    _Init_thread_footer
0x18000abd3  jmp     loc_18000AA2C
```
