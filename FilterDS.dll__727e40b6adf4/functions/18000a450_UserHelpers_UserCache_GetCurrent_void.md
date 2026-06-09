# UserHelpers::UserCache::GetCurrent(void)

- ea: `0x18000a450`
- end: `0x18000a528`
- name: `?GetCurrent@UserCache@UserHelpers@@SAAEAV12@XZ`
- size: `216`
- prototype: `struct UserHelpers::UserCache *(void)`
- caller_count: `7`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000775c`
- `0x180008ea0`
- `0x180013d40`
- `0x1800140b0`
- `0x180015054`
- `0x180015c0c`
- `0x18001619c`

## callees

- `0x180002234`
- `0x18000297c`
- `0x1800029ec`
- `0x18000a450`

## pseudocode

```c
struct UserHelpers::UserCache *UserHelpers::UserCache::GetCurrent(void)
{
  if ( __TSS0__1__GetCurrent_UserCache_UserHelpers__SAAEAV23_XZ_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                  + (unsigned int)tls_index)
                                                                                + 4LL) )
  {
    Init_thread_header(&__TSS0__1__GetCurrent_UserCache_UserHelpers__SAAEAV23_XZ_4HA);
    if ( __TSS0__1__GetCurrent_UserCache_UserHelpers__SAAEAV23_XZ_4HA == -1 )
    {
      qword_180030B88 = 7;
      byte_180030B50 = 0;
      `UserHelpers::UserCache::GetCurrent'::`2'::userCache = 0;
      dword_180030B54 = 0;
      qword_180030B58 = 0;
      xmmword_180030B60 = 0;
      qword_180030B80 = 0;
      word_180030B70 = 0;
      xmmword_180030B90 = 0;
      xmmword_180030BA0 = 0;
      xmmword_180030BB0 = 0;
      qword_180030BC0 = 0;
      qword_180030BC8 = 0;
      qword_180030BD0 = 0;
      atexit(`UserHelpers::UserCache::GetCurrent'::`2'::`dynamic atexit destructor for 'userCache'');
      Init_thread_footer(&__TSS0__1__GetCurrent_UserCache_UserHelpers__SAAEAV23_XZ_4HA);
    }
  }
  return (struct UserHelpers::UserCache *)&`UserHelpers::UserCache::GetCurrent'::`2'::userCache;
}

```

## disassembly

```asm
0x18000a450  sub     rsp, 28h
0x18000a454  mov     ecx, cs:_tls_index
0x18000a45a  mov     rax, gs:58h
0x18000a463  mov     edx, 4
0x18000a468  mov     rax, [rax+rcx*8]
0x18000a46c  mov     eax, [rdx+rax]
0x18000a46f  cmp     cs:?$TSS0@?1??GetCurrent@UserCache@UserHelpers@@SAAEAV23@XZ@4HA, eax
0x18000a475  jg      short loc_18000A483
0x18000a477  lea     rax, ?userCache@?1??GetCurrent@UserCache@UserHelpers@@SAAEAV23@XZ@4V23@A; UserHelpers::UserCache `UserHelpers::UserCache::GetCurrent(void)'::`2'::userCache
0x18000a47e  add     rsp, 28h
0x18000a482  retn
0x18000a483  lea     rcx, ?$TSS0@?1??GetCurrent@UserCache@UserHelpers@@SAAEAV23@XZ@4HA
0x18000a48a  call    _Init_thread_header
0x18000a48f  cmp     cs:?$TSS0@?1??GetCurrent@UserCache@UserHelpers@@SAAEAV23@XZ@4HA, 0FFFFFFFFh
0x18000a496  jnz     short loc_18000A477
0x18000a498  xor     edx, edx
0x18000a49a  mov     cs:qword_180030B88, 7
0x18000a4a5  xorps   xmm0, xmm0
0x18000a4a8  mov     cs:byte_180030B50, dl
0x18000a4ae  xor     eax, eax
0x18000a4b0  movdqa  cs:?userCache@?1??GetCurrent@UserCache@UserHelpers@@SAAEAV23@XZ@4V23@A, xmm0; UserHelpers::UserCache `UserHelpers::UserCache::GetCurrent(void)'::`2'::userCache
0x18000a4b8  xorps   xmm1, xmm1
0x18000a4bb  mov     cs:dword_180030B54, edx
0x18000a4c1  lea     rcx, ??__FuserCache@?1??GetCurrent@UserCache@UserHelpers@@SAAEAV12@XZ@YAXXZ; void (__cdecl *)()
0x18000a4c8  mov     cs:qword_180030B58, rax
0x18000a4cf  movdqa  cs:xmmword_180030B60, xmm0
0x18000a4d7  mov     cs:qword_180030B80, rdx
0x18000a4de  mov     cs:word_180030B70, dx
0x18000a4e5  movdqa  cs:xmmword_180030B90, xmm0
0x18000a4ed  movdqa  cs:xmmword_180030BA0, xmm0
0x18000a4f5  movdqa  cs:xmmword_180030BB0, xmm1
0x18000a4fd  mov     cs:qword_180030BC0, rax
0x18000a504  mov     cs:qword_180030BC8, rdx
0x18000a50b  mov     cs:qword_180030BD0, rdx
0x18000a512  call    atexit
0x18000a517  lea     rcx, ?$TSS0@?1??GetCurrent@UserCache@UserHelpers@@SAAEAV23@XZ@4HA
0x18000a51e  call    _Init_thread_footer
0x18000a523  jmp     loc_18000A477
```
