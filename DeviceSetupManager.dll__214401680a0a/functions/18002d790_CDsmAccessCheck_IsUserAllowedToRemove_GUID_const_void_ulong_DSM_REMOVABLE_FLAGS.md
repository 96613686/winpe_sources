# CDsmAccessCheck::IsUserAllowedToRemove(_GUID const &,void *,ulong,DSM_REMOVABLE_FLAGS *)

- ea: `0x18002d790`
- end: `0x18002da3d`
- name: `?IsUserAllowedToRemove@CDsmAccessCheck@@SAJAEBU_GUID@@PEAXKPEAW4DSM_REMOVABLE_FLAGS@@@Z`
- size: `685`
- prototype: `__int64 __fastcall(const struct _GUID *, void *, DWORD dwProcessId, enum DSM_REMOVABLE_FLAGS *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002e220`
- `0x18002e5e0`

## callees

- `0x18001af70`
- `0x18001ba48`
- `0x18001bc4c`
- `0x18001bcb4`
- `0x18002d790`
- `0x18002da44`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18002d848`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18002d848`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002d7ec`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002d7ec`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x18002d84e`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x18002d84e`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x18002d942`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x18002d942`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18002d9ed`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18002d9ed`

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
  bool v13; // r15
  bool v14; // di
  __int64 v15; // r8
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 result; // rax
  bool v20; // [rsp+40h] [rbp-49h] BYREF
  bool v21; // [rsp+41h] [rbp-48h] BYREF
  DWORD pSessionId; // [rsp+44h] [rbp-45h] BYREF
  __int64 v23; // [rsp+48h] [rbp-41h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-39h] BYREF

  *(_DWORD *)a4 = 0;
  v20 = 0;
  v21 = 0;
  memset_0(sz, 0, 0x4Eu);
  v8 = StringFromGUID2(a1, sz, 39);
  ObjectProperties = v8 == 0 ? 0x80004005 : 0;
  CDsmAccessCheck::_IsUserSIDAllowedToRemove(a1, a2, &v20, &v21);
  v10 = v21;
  v11 = v8 == 0;
  v12 = v20;
  if ( !v11 && !v20 && !v21 )
  {
    pSessionId = 0;
    ProcessIdToSessionId(dwProcessId, &pSessionId);
    if ( WTSGetActiveConsoleSessionId() == pSessionId )
    {
      v13 = 0;
      v14 = 1;
      if ( __TSS0__4__IsUserAllowedToRemove_CDsmAccessCheck__SAJAEBU_GUID__PEAXKPEAW4DSM_REMOVABLE_FLAGS___Z_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL) )
      {
        Init_thread_header(&__TSS0__4__IsUserAllowedToRemove_CDsmAccessCheck__SAJAEBU_GUID__PEAXKPEAW4DSM_REMOVABLE_FLAGS___Z_4HA);
        if ( __TSS0__4__IsUserAllowedToRemove_CDsmAccessCheck__SAJAEBU_GUID__PEAXKPEAW4DSM_REMOVABLE_FLAGS___Z_4HA == -1 )
        {
          *(DEVPROPKEY *)`CDsmAccessCheck::IsUserAllowedToRemove'::`5'::Keys = DEVPKEY_DeviceContainer_IsConnected;
          dword_18005A1A4 = 0;
          qword_18005A1A8 = 0;
          *(DEVPROPKEY *)byte_18005A1B0 = DEVPKEY_DeviceContainer_IsPaired;
          dword_18005A1C4 = 0;
          qword_18005A1C8 = 0;
          Init_thread_footer(&__TSS0__4__IsUserAllowedToRemove_CDsmAccessCheck__SAJAEBU_GUID__PEAXKPEAW4DSM_REMOVABLE_FLAGS___Z_4HA);
        }
      }
      pSessionId = 0;
      v23 = 0;
      ObjectProperties = DevGetObjectProperties(
                           2,
                           sz,
                           0,
                           2,
                           `CDsmAccessCheck::IsUserAllowedToRemove'::`5'::Keys,
                           &pSessionId,
                           &v23);
      if ( ObjectProperties >= 0 && pSessionId == 2 )
      {
        v15 = 0;
        v16 = 0;
        do
        {
          if ( *(_DWORD *)(v16 + v23 + 16) == 55 )
          {
            v17 = *(_QWORD *)(v16 + v23) - *(_QWORD *)&DEVPKEY_DeviceContainer_IsConnected.fmtid.Data1;
            if ( !v17 )
              v17 = *(_QWORD *)(v16 + v23 + 8) - *(_QWORD *)DEVPKEY_DeviceContainer_IsConnected.fmtid.Data4;
            if ( !v17 && *(_DWORD *)(v16 + v23 + 32) == 17 )
              v14 = **(_BYTE **)(v16 + v23 + 40) == 0xFF;
          }
          else if ( *(_DWORD *)(v16 + v23 + 16) == 56 )
          {
            v18 = *(_QWORD *)(v16 + v23) - *(_QWORD *)&DEVPKEY_DeviceContainer_IsPaired.fmtid.Data1;
            if ( !v18 )
              v18 = *(_QWORD *)(v16 + v23 + 8) - *(_QWORD *)DEVPKEY_DeviceContainer_IsPaired.fmtid.Data4;
            if ( !v18 && *(_DWORD *)(v16 + v23 + 32) == 17 )
              v13 = **(_BYTE **)(v16 + v23 + 40) == 0xFF;
          }
          ++v15;
          v16 += 48;
        }
        while ( v15 != 2 );
      }
      if ( v23 )
        DevFreeObjectProperties(pSessionId, v23);
      if ( !v14 || v13 )
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
0x18002d790  push    rbp
0x18002d792  push    rbx
0x18002d793  push    rsi
0x18002d794  push    rdi
0x18002d795  push    r12
0x18002d797  push    r14
0x18002d799  push    r15
0x18002d79b  lea     rbp, [rsp-27h]
0x18002d7a0  sub     rsp, 0B0h
0x18002d7a7  mov     rax, cs:__security_cookie
0x18002d7ae  xor     rax, rsp
0x18002d7b1  mov     [rbp+57h+var_40], rax
0x18002d7b5  mov     rsi, rdx
0x18002d7b8  mov     dword ptr [r9], 0
0x18002d7bf  xor     edx, edx; Val
0x18002d7c1  mov     [rbp+57h+var_A0], 0
0x18002d7c5  mov     r15d, r8d
0x18002d7c8  mov     [rbp+57h+var_9F], 0
0x18002d7cc  mov     rdi, rcx
0x18002d7cf  mov     r12, r9
0x18002d7d2  lea     rcx, [rbp+57h+sz]; void *
0x18002d7d6  lea     r8d, [rdx+4Eh]; Size
0x18002d7da  call    memset_0
0x18002d7df  mov     r8d, 27h ; '''; cchMax
0x18002d7e5  lea     rdx, [rbp+57h+sz]; lpsz
0x18002d7e9  mov     rcx, rdi; rguid
0x18002d7ec  call    cs:__imp_StringFromGUID2
0x18002d7f2  lea     r9, [rbp+57h+var_9F]; bool *
0x18002d7f6  mov     rdx, rsi; void *
0x18002d7f9  mov     r8d, eax
0x18002d7fc  mov     rcx, rdi; struct _GUID *
0x18002d7ff  neg     r8d
0x18002d802  mov     ebx, eax
0x18002d804  lea     r8, [rbp+57h+var_A0]; bool *
0x18002d808  sbb     r14d, r14d
0x18002d80b  not     r14d
0x18002d80e  and     r14d, 80004005h
0x18002d815  call    ?_IsUserSIDAllowedToRemove@CDsmAccessCheck@@CAXAEBU_GUID@@PEAXPEA_N2@Z; CDsmAccessCheck::_IsUserSIDAllowedToRemove(_GUID const &,void *,bool *,bool *)
0x18002d81a  mov     sil, [rbp+57h+var_9F]
0x18002d81e  test    ebx, ebx
0x18002d820  mov     bl, [rbp+57h+var_A0]
0x18002d823  jz      loc_18002D9FF
0x18002d829  test    bl, bl
0x18002d82b  jnz     loc_18002D9FF
0x18002d831  test    sil, sil
0x18002d834  jnz     loc_18002D9FF
0x18002d83a  lea     rdx, [rbp+57h+pSessionId]; pSessionId
0x18002d83e  mov     [rbp+57h+pSessionId], 0
0x18002d845  mov     ecx, r15d; dwProcessId
0x18002d848  call    cs:__imp_ProcessIdToSessionId
0x18002d84e  call    cs:__imp_WTSGetActiveConsoleSessionId
0x18002d854  cmp     eax, [rbp+57h+pSessionId]
0x18002d857  jnz     loc_18002D9FF
0x18002d85d  mov     ecx, cs:_tls_index
0x18002d863  xor     r15b, r15b
0x18002d866  mov     rax, gs:58h
0x18002d86f  mov     dil, 1
0x18002d872  mov     edx, 4
0x18002d877  mov     rax, [rax+rcx*8]
0x18002d87b  mov     eax, [rdx+rax]
0x18002d87e  cmp     cs:?$TSS0@?4??IsUserAllowedToRemove@CDsmAccessCheck@@SAJAEBU_GUID@@PEAXKPEAW4DSM_REMOVABLE_FLAGS@@@Z@4HA, eax
0x18002d884  jle     short loc_18002D905
0x18002d886  lea     rcx, ?$TSS0@?4??IsUserAllowedToRemove@CDsmAccessCheck@@SAJAEBU_GUID@@PEAXKPEAW4DSM_REMOVABLE_FLAGS@@@Z@4HA
0x18002d88d  call    _Init_thread_header
0x18002d892  cmp     cs:?$TSS0@?4??IsUserAllowedToRemove@CDsmAccessCheck@@SAJAEBU_GUID@@PEAXKPEAW4DSM_REMOVABLE_FLAGS@@@Z@4HA, 0FFFFFFFFh
0x18002d899  jnz     short loc_18002D905
0x18002d89b  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceContainer_IsConnected.fmtid.Data1
0x18002d8a2  mov     eax, cs:DEVPKEY_DeviceContainer_IsConnected.pid
0x18002d8a8  lea     rcx, ?$TSS0@?4??IsUserAllowedToRemove@CDsmAccessCheck@@SAJAEBU_GUID@@PEAXKPEAW4DSM_REMOVABLE_FLAGS@@@Z@4HA
0x18002d8af  mov     dword ptr cs:?Keys@?4??IsUserAllowedToRemove@CDsmAccessCheck@@SAJAEBU_GUID@@PEAXKPEAW4DSM_REMOVABLE_FLAGS@@@Z@4QBU_DEVPROPCOMPKEY@@B+10h, eax; _DEVPROPCOMPKEY const near * const `CDsmAccessCheck::IsUserAllowedToRemove(_GUID const &,void *,ulong,DSM_REMOVABLE_FLAGS *)'::`5'::Keys
0x18002d8b5  mov     eax, cs:DEVPKEY_DeviceContainer_IsPaired.pid
0x18002d8bb  movaps  xmmword ptr cs:?Keys@?4??IsUserAllowedToRemove@CDsmAccessCheck@@SAJAEBU_GUID@@PEAXKPEAW4DSM_REMOVABLE_FLAGS@@@Z@4QBU_DEVPROPCOMPKEY@@B, xmm0; _DEVPROPCOMPKEY const near * const `CDsmAccessCheck::IsUserAllowedToRemove(_GUID const &,void *,ulong,DSM_REMOVABLE_FLAGS *)'::`5'::Keys
0x18002d8c2  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceContainer_IsPaired.fmtid.Data1
0x18002d8c9  mov     cs:dword_18005A1A4, 0
0x18002d8d3  mov     cs:qword_18005A1A8, 0
0x18002d8de  movaps  xmmword ptr cs:byte_18005A1B0, xmm0
0x18002d8e5  mov     dword ptr cs:byte_18005A1B0+10h, eax
0x18002d8eb  mov     cs:dword_18005A1C4, 0
0x18002d8f5  mov     cs:qword_18005A1C8, 0
0x18002d900  call    _Init_thread_footer
0x18002d905  lea     rax, [rbp+57h+var_98]
0x18002d909  mov     [rbp+57h+pSessionId], 0
0x18002d910  mov     [rsp+0E0h+var_B0], rax
0x18002d915  lea     rdx, [rbp+57h+sz]
0x18002d919  lea     rax, [rbp+57h+pSessionId]
0x18002d91d  mov     [rbp+57h+var_98], 0
0x18002d925  mov     [rsp+0E0h+var_B8], rax
0x18002d92a  mov     r9d, 2
0x18002d930  lea     rax, ?Keys@?4??IsUserAllowedToRemove@CDsmAccessCheck@@SAJAEBU_GUID@@PEAXKPEAW4DSM_REMOVABLE_FLAGS@@@Z@4QBU_DEVPROPCOMPKEY@@B; _DEVPROPCOMPKEY const near * const `CDsmAccessCheck::IsUserAllowedToRemove(_GUID const &,void *,ulong,DSM_REMOVABLE_FLAGS *)'::`5'::Keys
0x18002d937  xor     r8d, r8d
0x18002d93a  mov     ecx, r9d
0x18002d93d  mov     [rsp+0E0h+var_C0], rax
0x18002d942  call    cs:__imp_DevGetObjectProperties
0x18002d948  mov     rdx, [rbp+57h+var_98]
0x18002d94c  mov     r14d, eax
0x18002d94f  test    eax, eax
0x18002d951  js      loc_18002D9E5
0x18002d957  cmp     [rbp+57h+pSessionId], 2
0x18002d95b  jnz     loc_18002D9E5
0x18002d961  xor     r8d, r8d
0x18002d964  xor     ecx, ecx
0x18002d966  cmp     dword ptr [rcx+rdx+10h], 37h ; '7'
0x18002d96b  jnz     short loc_18002D9A0
0x18002d96d  mov     rax, [rcx+rdx]
0x18002d971  sub     rax, qword ptr cs:DEVPKEY_DeviceContainer_IsConnected.fmtid.Data1
0x18002d978  jnz     short loc_18002D986
0x18002d97a  mov     rax, [rcx+rdx+8]
0x18002d97f  sub     rax, qword ptr cs:DEVPKEY_DeviceContainer_IsConnected.fmtid.Data4
0x18002d986  test    rax, rax
0x18002d989  jnz     short loc_18002D9D8
0x18002d98b  cmp     dword ptr [rcx+rdx+20h], 11h
0x18002d990  jnz     short loc_18002D9D8
0x18002d992  mov     rax, [rcx+rdx+28h]
0x18002d997  cmp     byte ptr [rax], 0FFh
0x18002d99a  setz    dil
0x18002d99e  jmp     short loc_18002D9D8
0x18002d9a0  cmp     dword ptr [rcx+rdx+10h], 38h ; '8'
0x18002d9a5  jnz     short loc_18002D9D8
0x18002d9a7  mov     rax, [rcx+rdx]
0x18002d9ab  sub     rax, qword ptr cs:DEVPKEY_DeviceContainer_IsPaired.fmtid.Data1
0x18002d9b2  jnz     short loc_18002D9C0
0x18002d9b4  mov     rax, [rcx+rdx+8]
0x18002d9b9  sub     rax, qword ptr cs:DEVPKEY_DeviceContainer_IsPaired.fmtid.Data4
0x18002d9c0  test    rax, rax
0x18002d9c3  jnz     short loc_18002D9D8
0x18002d9c5  cmp     dword ptr [rcx+rdx+20h], 11h
0x18002d9ca  jnz     short loc_18002D9D8
0x18002d9cc  mov     rax, [rcx+rdx+28h]
0x18002d9d1  cmp     byte ptr [rax], 0FFh
0x18002d9d4  setz    r15b
0x18002d9d8  inc     r8
0x18002d9db  add     rcx, 30h ; '0'
0x18002d9df  cmp     r8, 2
0x18002d9e3  jnz     short loc_18002D966
0x18002d9e5  test    rdx, rdx
0x18002d9e8  jz      short loc_18002D9F3
0x18002d9ea  mov     ecx, [rbp+57h+pSessionId]
0x18002d9ed  call    cs:__imp_DevFreeObjectProperties
0x18002d9f3  test    dil, dil
0x18002d9f6  jz      short loc_18002D9FD
0x18002d9f8  test    r15b, r15b
0x18002d9fb  jz      short loc_18002D9FF
0x18002d9fd  mov     bl, 1
0x18002d9ff  mov     ecx, [r12]
0x18002da03  xor     eax, eax
0x18002da05  test    bl, bl
0x18002da07  setnz   al
0x18002da0a  or      ecx, eax
0x18002da0c  neg     sil
0x18002da0f  sbb     eax, eax
0x18002da11  not     eax
0x18002da13  and     eax, 2
0x18002da16  or      ecx, eax
0x18002da18  mov     eax, r14d
0x18002da1b  mov     [r12], ecx
0x18002da1f  mov     rcx, [rbp+57h+var_40]
0x18002da23  xor     rcx, rsp; StackCookie
0x18002da26  call    __security_check_cookie
0x18002da2b  add     rsp, 0B0h
0x18002da32  pop     r15
0x18002da34  pop     r14
0x18002da36  pop     r12
0x18002da38  pop     rdi
0x18002da39  pop     rsi
0x18002da3a  pop     rbx
0x18002da3b  pop     rbp
0x18002da3c  retn
```
