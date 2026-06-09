# WaasMedic::CreateSid(void * *,uchar,ulong,ulong)

- ea: `0x180028150`
- end: `0x18002822a`
- name: `?CreateSid@WaasMedic@@YAJPEAPEAXEKK@Z`
- size: `218`
- prototype: `__int64 __fastcall(WaasMedic *__hidden this, void **, unsigned __int8, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18002805c`

## callees

- `0x1800050a0`
- `0x180028150`
- `0x18002e81c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800281c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800281c0`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180028200`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180028200`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800281b6`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800281b6`

## string_xrefs

- `0x1800281d8`: `Failed to allocate and initialize SID! hr = 0x%08x`

## pseudocode

```c
__int64 __fastcall WaasMedic::CreateSid(WaasMedic *this, void **a2)
{
  signed int LastError; // eax
  unsigned int v4; // ebx
  PSID pSid; // [rsp+60h] [rbp-28h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v7; // [rsp+68h] [rbp-20h] BYREF

  *(_WORD *)&v7.Value[4] = 1280;
  *(_DWORD *)v7.Value = 0;
  pSid = 0;
  if ( AllocateAndInitializeSid(&v7, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    v4 = 0;
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)this, (signed __int64)pSid, 0) )
      FreeSid(pSid);
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    LogLevelW(2u, L"Failed to allocate and initialize SID! hr = 0x%08x", v4);
  }
  return v4;
}

```

## disassembly

```asm
0x180028150  mov     r11, rsp
0x180028153  mov     [r11+10h], rbx
0x180028157  mov     [r11+18h], rsi
0x18002815b  push    rdi
0x18002815c  sub     rsp, 80h
0x180028163  mov     rax, cs:__security_cookie
0x18002816a  xor     rax, rsp
0x18002816d  mov     [rsp+88h+var_18], rax
0x180028172  xor     esi, esi
0x180028174  mov     [rsp+88h+var_1C], 500h
0x18002817b  lea     rax, [r11-28h]
0x18002817f  mov     [rsp+88h+var_20], esi
0x180028183  mov     [r11-38h], rax
0x180028187  mov     rdi, rcx
0x18002818a  mov     [rsp+88h+nSubAuthority7], esi; nSubAuthority7
0x18002818e  lea     rcx, [r11-20h]; pIdentifierAuthority
0x180028192  mov     [rsp+88h+nSubAuthority6], esi; nSubAuthority6
0x180028196  lea     r8d, [rsi+20h]; nSubAuthority0
0x18002819a  mov     [rsp+88h+nSubAuthority5], esi; nSubAuthority5
0x18002819e  mov     r9d, 220h; nSubAuthority1
0x1800281a4  mov     [rsp+88h+nSubAuthority4], esi; nSubAuthority4
0x1800281a8  mov     dl, 2; nSubAuthorityCount
0x1800281aa  mov     [rsp+88h+nSubAuthority3], esi; nSubAuthority3
0x1800281ae  mov     [rsp+88h+nSubAuthority2], esi; nSubAuthority2
0x1800281b2  mov     [r11-28h], rsi
0x1800281b6  call    cs:__imp_AllocateAndInitializeSid
0x1800281bc  test    eax, eax
0x1800281be  jnz     short loc_1800281EB
0x1800281c0  call    cs:__imp_GetLastError
0x1800281c6  mov     ebx, eax
0x1800281c8  test    eax, eax
0x1800281ca  jle     short loc_1800281D5
0x1800281cc  movzx   ebx, ax
0x1800281cf  or      ebx, 80070000h
0x1800281d5  mov     r8d, ebx
0x1800281d8  lea     rdx, aFailedToAlloca_11; "Failed to allocate and initialize SID! "...
0x1800281df  mov     ecx, 2; unsigned __int8
0x1800281e4  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800281e9  jmp     short loc_180028206
0x1800281eb  mov     rcx, [rsp+88h+pSid]
0x1800281f0  mov     ebx, esi
0x1800281f2  xor     eax, eax
0x1800281f4  lock cmpxchg [rdi], rcx
0x1800281f9  jz      short loc_180028206
0x1800281fb  mov     rcx, [rsp+88h+pSid]; pSid
0x180028200  call    cs:__imp_FreeSid
0x180028206  mov     eax, ebx
0x180028208  mov     rcx, [rsp+88h+var_18]
0x18002820d  xor     rcx, rsp; StackCookie
0x180028210  call    __security_check_cookie
0x180028215  lea     r11, [rsp+88h+var_8]
0x18002821d  mov     rbx, [r11+18h]
0x180028221  mov     rsi, [r11+20h]
0x180028225  mov     rsp, r11
0x180028228  pop     rdi
0x180028229  retn
```
