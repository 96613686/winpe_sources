# MpWatchDog::MpIsCoreSvcInDevMode(void)

- ea: `0x1400833d4`
- end: `0x140083456`
- name: `?MpIsCoreSvcInDevMode@MpWatchDog@@YA_NXZ`
- size: `130`
- prototype: `char __fastcall(MpWatchDog *this)`
- caller_count: `37`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14007d880`
- `0x140081fc8`
- `0x1400820b4`
- `0x14008236c`
- `0x140083458`
- `0x14008371c`
- `0x140088b60`
- `0x140089890`
- `0x14008a040`
- `0x14008a988`
- `0x14008fd14`
- `0x140091ad0`
- `0x140092b74`
- `0x140092cd8`
- `0x140097924`
- `0x14009a074`
- `0x14009d97c`
- `0x14009e52c`
- `0x1400a1500`
- `0x1400a1dec`
- `0x1400acfa0`
- `0x1400ae494`
- `0x1400b6564`
- `0x1400b6810`
- `0x1400b7000`
- `0x1400c2874`
- `0x1400c33ac`
- `0x1400c38c4`
- `0x1400c46d0`
- `0x1400c575c`
- `0x1400c5a4c`
- `0x1400c5d60`
- `0x1400d21c0`
- `0x1400d26f0`
- `0x1400d7390`
- `0x1400e4424`
- `0x1400ee2e8`

## callees

- `0x14001dd90`
- `0x14003a5c0`
- `0x14004f9a8`
- `0x1400814f4`
- `0x1400833d4`

## import_xrefs

- `KERNEL32!InitOnceComplete` at `0x140083428`
- `KERNEL32!InitOnceComplete` at `0x140083428`
- `KERNEL32!InitOnceBeginInitialize` at `0x140083400`
- `KERNEL32!InitOnceBeginInitialize` at `0x140083400`

## pseudocode

```c
char __fastcall MpWatchDog::MpIsCoreSvcInDevMode(MpWatchDog *this)
{
  WINBOOL fPending; // [rsp+30h] [rbp-18h] BYREF

  fPending = 0;
  if ( !__std_init_once_begin_initialize(&InitOnce, 0, &fPending, 0) )
    abort();
  if ( fPending )
  {
    byte_1401E72D8 = MpWatchDog::CheckCoreSvcDevMode();
    if ( !InitOnceComplete(&InitOnce, 0, 0) )
      _std_init_once_link_alternate_names_and_abort();
  }
  return byte_1401E72D8;
}

```

## disassembly

```asm
0x1400833d4  sub     rsp, 48h
0x1400833d8  mov     rax, cs:__security_cookie
0x1400833df  xor     rax, rsp
0x1400833e2  mov     [rsp+48h+var_10], rax
0x1400833e7  xor     r9d, r9d; lpContext
0x1400833ea  mov     [rsp+48h+fPending], 0
0x1400833f2  lea     r8, [rsp+48h+fPending]; fPending
0x1400833f7  xor     edx, edx; dwFlags
0x1400833f9  lea     rcx, InitOnce; lpInitOnce
0x140083400  call    cs:__imp___std_init_once_begin_initialize
0x140083406  test    eax, eax
0x140083408  jz      short loc_140083450
0x14008340a  cmp     [rsp+48h+fPending], 0
0x14008340f  jz      short loc_140083432
0x140083411  call    MpWatchDog__CheckCoreSvcDevMode
0x140083416  xor     r8d, r8d; lpContext
0x140083419  mov     cs:byte_1401E72D8, al
0x14008341f  xor     edx, edx; dwFlags
0x140083421  lea     rcx, InitOnce; lpInitOnce
0x140083428  call    cs:__imp_InitOnceComplete
0x14008342e  test    eax, eax
0x140083430  jz      short loc_14008344A
0x140083432  mov     al, cs:byte_1401E72D8
0x140083438  mov     rcx, [rsp+48h+var_10]
0x14008343d  xor     rcx, rsp; StackCookie
0x140083440  call    __security_check_cookie
0x140083445  add     rsp, 48h
0x140083449  retn
0x14008344a  call    __std_init_once_link_alternate_names_and_abort
0x140083450  call    abort
```
