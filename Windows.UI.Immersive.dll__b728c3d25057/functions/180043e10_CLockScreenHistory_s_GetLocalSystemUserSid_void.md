# CLockScreenHistory::s_GetLocalSystemUserSid(void * *)

- ea: `0x180043e10`
- end: `0x180043eba`
- name: `?s_GetLocalSystemUserSid@CLockScreenHistory@@SAJPEAPEAX@Z`
- size: `170`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18000bf20`

## callees

- `0x18003aa84`
- `0x180043e10`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180043ea2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180043ea2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180043e5f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180043e5f`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180043e3d`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180043e81`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180043e3d`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180043e81`

## pseudocode

```c
__int64 __fastcall CLockScreenHistory::s_GetLocalSystemUserSid(void **a1)
{
  int Error; // ebx
  HLOCAL v3; // rax
  void *v4; // rdi
  SIZE_T uBytes; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  LODWORD(uBytes) = 0;
  if ( CreateWellKnownSid(WinLocalSystemSid, 0, 0, (DWORD *)&uBytes) )
  {
    return 0;
  }
  else
  {
    Error = ResultFromKnownLastError();
    if ( Error == -2147024774 )
    {
      v3 = LocalAlloc(0, (unsigned int)uBytes);
      v4 = v3;
      if ( v3 )
      {
        if ( CreateWellKnownSid(WinLocalSystemSid, 0, v3, (DWORD *)&uBytes) )
        {
          Error = 0;
        }
        else
        {
          Error = ResultFromKnownLastError();
          if ( Error < 0 )
          {
            LocalFree(v4);
            return (unsigned int)Error;
          }
        }
        *a1 = v4;
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180043e10  mov     rax, rsp
0x180043e13  mov     [rax+10h], rbx
0x180043e17  mov     [rax+18h], rsi
0x180043e1b  push    rdi
0x180043e1c  sub     rsp, 20h
0x180043e20  xor     edx, edx; DomainSid
0x180043e22  mov     qword ptr [rcx], 0
0x180043e29  mov     rsi, rcx
0x180043e2c  mov     dword ptr [rax+8], 0
0x180043e33  lea     r9, [rax+8]; cbSid
0x180043e37  xor     r8d, r8d; pSid
0x180043e3a  lea     ecx, [rdx+16h]; WellKnownSidType
0x180043e3d  call    cs:__imp_CreateWellKnownSid
0x180043e43  test    eax, eax
0x180043e45  jz      short loc_180043E4B
0x180043e47  xor     ebx, ebx
0x180043e49  jmp     short loc_180043EA8
0x180043e4b  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180043e50  mov     ebx, eax
0x180043e52  cmp     eax, 8007007Ah
0x180043e57  jnz     short loc_180043EA8
0x180043e59  mov     edx, dword ptr [rsp+28h+uBytes]; uBytes
0x180043e5d  xor     ecx, ecx; uFlags
0x180043e5f  call    cs:__imp_LocalAlloc
0x180043e65  mov     rdi, rax
0x180043e68  test    rax, rax
0x180043e6b  jnz     short loc_180043E74
0x180043e6d  mov     ebx, 8007000Eh
0x180043e72  jmp     short loc_180043EA8
0x180043e74  xor     edx, edx; DomainSid
0x180043e76  lea     r9, [rsp+28h+uBytes]; cbSid
0x180043e7b  mov     r8, rdi; pSid
0x180043e7e  lea     ecx, [rdx+16h]; WellKnownSidType
0x180043e81  call    cs:__imp_CreateWellKnownSid
0x180043e87  test    eax, eax
0x180043e89  jz      short loc_180043E8F
0x180043e8b  xor     ebx, ebx
0x180043e8d  jmp     short loc_180043E9A
0x180043e8f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180043e94  mov     ebx, eax
0x180043e96  test    eax, eax
0x180043e98  js      short loc_180043E9F
0x180043e9a  mov     [rsi], rdi
0x180043e9d  jmp     short loc_180043EA8
0x180043e9f  mov     rcx, rdi; hMem
0x180043ea2  call    cs:__imp_LocalFree
0x180043ea8  mov     rsi, [rsp+28h+arg_10]
0x180043ead  mov     eax, ebx
0x180043eaf  mov     rbx, [rsp+28h+arg_8]
0x180043eb4  add     rsp, 20h
0x180043eb8  pop     rdi
0x180043eb9  retn
```
