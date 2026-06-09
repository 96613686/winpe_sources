# KerbConvertStringToSid

- ea: `0x18007d950`
- end: `0x18007da2b`
- name: `KerbConvertStringToSid`
- size: `219`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180053900`

## callees

- `0x180002ad0`
- `0x180003210`
- `0x1800038f0`
- `0x18007d950`
- `0x18007f4d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d9e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d9e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007d9de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007d9de`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18007d9c0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18007d9c0`

## pseudocode

```c
__int64 __fastcall KerbConvertStringToSid(const void **a1, _QWORD *a2)
{
  __int64 v3; // rbx
  unsigned __int64 v4; // rbx
  unsigned int v5; // ebx
  PSID Sid; // [rsp+20h] [rbp-228h] BYREF
  WCHAR StringSid[256]; // [rsp+30h] [rbp-218h] BYREF

  *a2 = 0;
  v3 = *(unsigned __int16 *)a1;
  Sid = 0;
  if ( (unsigned __int64)(v3 + 2) > 0x200 )
    return 3221225485LL;
  memcpy_0(StringSid, a1[1], (unsigned int)v3);
  v4 = v3 & 0xFFFFFFFFFFFFFFFEuLL;
  if ( v4 >= 0x200 )
    _report_rangecheckfailure();
  *(WCHAR *)((char *)StringSid + v4) = 0;
  if ( ConvertStringSidToSidW(StringSid, &Sid) )
  {
    v5 = KerbDuplicateSid(a2, Sid);
    LocalFree(Sid);
  }
  else
  {
    v5 = -1073741811;
    if ( GetLastError() == 8 )
      return (unsigned int)-1073741670;
  }
  return v5;
}

```

## disassembly

```asm
0x18007d950  mov     [rsp+arg_10], rbx
0x18007d955  push    rdi
0x18007d956  sub     rsp, 240h
0x18007d95d  mov     rax, cs:__security_cookie
0x18007d964  xor     rax, rsp
0x18007d967  mov     [rsp+248h+var_18], rax
0x18007d96f  mov     qword ptr [rdx], 0
0x18007d976  mov     rdi, rdx
0x18007d979  movzx   ebx, word ptr [rcx]
0x18007d97c  mov     [rsp+248h+Sid], 0
0x18007d985  lea     rax, [rbx+2]
0x18007d989  cmp     rax, 200h
0x18007d98f  ja      short loc_18007D9FF
0x18007d991  mov     rdx, [rcx+8]; Src
0x18007d995  mov     r8d, ebx; Size
0x18007d998  lea     rcx, [rsp+248h+StringSid]; void *
0x18007d99d  call    memcpy_0
0x18007d9a2  and     rbx, 0FFFFFFFFFFFFFFFEh
0x18007d9a6  cmp     rbx, 200h
0x18007d9ad  jnb     short loc_18007DA25
0x18007d9af  xor     eax, eax
0x18007d9b1  lea     rdx, [rsp+248h+Sid]; Sid
0x18007d9b6  lea     rcx, [rsp+248h+StringSid]; StringSid
0x18007d9bb  mov     [rsp+rbx+248h+StringSid], ax
0x18007d9c0  call    cs:__imp_ConvertStringSidToSidW
0x18007d9c6  test    eax, eax
0x18007d9c8  jz      short loc_18007D9E6
0x18007d9ca  mov     rdx, [rsp+248h+Sid]
0x18007d9cf  mov     rcx, rdi
0x18007d9d2  call    KerbDuplicateSid
0x18007d9d7  mov     rcx, [rsp+248h+Sid]; hMem
0x18007d9dc  mov     ebx, eax
0x18007d9de  call    cs:__imp_LocalFree
0x18007d9e4  jmp     short loc_18007D9FB
0x18007d9e6  call    cs:__imp_GetLastError
0x18007d9ec  mov     ebx, 0C000000Dh
0x18007d9f1  cmp     eax, 8
0x18007d9f4  jnz     short loc_18007D9FB
0x18007d9f6  mov     ebx, 0C000009Ah
0x18007d9fb  mov     eax, ebx
0x18007d9fd  jmp     short loc_18007DA04
0x18007d9ff  mov     eax, 0C000000Dh
0x18007da04  mov     rcx, [rsp+248h+var_18]
0x18007da0c  xor     rcx, rsp; StackCookie
0x18007da0f  call    __security_check_cookie
0x18007da14  mov     rbx, [rsp+248h+arg_10]
0x18007da1c  add     rsp, 240h
0x18007da23  pop     rdi
0x18007da24  retn
0x18007da25  call    __report_rangecheckfailure
```
