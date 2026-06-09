# wil::init_once_nothrow__lambda_b3e7cbd1ddeac58a7a05acaf7d857929___

- ea: `0x180055574`
- end: `0x18005561c`
- name: `wil::init_once_nothrow__lambda_b3e7cbd1ddeac58a7a05acaf7d857929___`
- size: `168`
- prototype: `__int64 __fastcall(LPINIT_ONCE lpInitOnce)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180060150`

## callees

- `0x180011e84`
- `0x180011ea4`
- `0x180055574`
- `0x18005ecd4`

## import_xrefs

- `KERNEL32!InitOnceComplete` at `0x1800555f7`
- `KERNEL32!InitOnceComplete` at `0x180055609`
- `KERNEL32!InitOnceComplete` at `0x1800555f7`
- `KERNEL32!InitOnceComplete` at `0x180055609`
- `KERNEL32!InitOnceBeginInitialize` at `0x18005559b`
- `KERNEL32!InitOnceBeginInitialize` at `0x18005559b`

## pseudocode

```c
__int64 __fastcall wil::init_once_nothrow__lambda_b3e7cbd1ddeac58a7a05acaf7d857929___(
        LPINIT_ONCE lpInitOnce,
        __int64 a2,
        __int64 a3)
{
  const char *v4; // r9
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v10; // [rsp+38h] [rbp+10h] BYREF
  WINBOOL v11; // [rsp+40h] [rbp+18h] BYREF
  int v12; // [rsp+44h] [rbp+1Ch]

  v12 = HIDWORD(a3);
  v10 = a2;
  v11 = 0;
  if ( !InitOnceBeginInitialize(lpInitOnce, 0, &v11, 0) )
    return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0x37A, (unsigned int)"wil", v4);
  if ( v11 )
  {
    v6 = lambda_b3e7cbd1ddeac58a7a05acaf7d857929_::operator()(&v10);
    v7 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x37F, (unsigned int)"wil", (const char *)(unsigned int)v6, v8);
      InitOnceComplete(lpInitOnce, 4u, 0);
      return v7;
    }
    InitOnceComplete(lpInitOnce, 0, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180055574  mov     rax, rsp
0x180055577  mov     [rax+8], rbx
0x18005557b  mov     [rax+18h], r8
0x18005557f  mov     [rax+10h], rdx
0x180055583  push    rdi; int
0x180055584  sub     rsp, 20h
0x180055588  mov     rdi, rcx
0x18005558b  mov     dword ptr [rax+18h], 0
0x180055592  xor     r9d, r9d; lpContext
0x180055595  lea     r8, [rax+18h]; fPending
0x180055599  xor     edx, edx; dwFlags
0x18005559b  call    cs:__imp_InitOnceBeginInitialize
0x1800555a1  test    eax, eax
0x1800555a3  jnz     short loc_1800555BD
0x1800555a5  mov     rcx, [rsp+28h]; this
0x1800555aa  lea     r8, aWil; "wil"
0x1800555b1  mov     edx, 37Ah; void *
0x1800555b6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800555bb  jmp     short loc_180055611
0x1800555bd  cmp     [rsp+28h+arg_10], 0
0x1800555c2  jz      short loc_18005560F
0x1800555c4  lea     rcx, [rsp+28h+arg_8]
0x1800555c9  call    _lambda_b3e7cbd1ddeac58a7a05acaf7d857929___operator__
0x1800555ce  mov     ebx, eax
0x1800555d0  test    eax, eax
0x1800555d2  jns     short loc_180055601
0x1800555d4  mov     rcx, [rsp+28h]; this
0x1800555d9  mov     r9d, eax; char *
0x1800555dc  lea     r8, aWil; "wil"
0x1800555e3  mov     edx, 37Fh; void *
0x1800555e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800555ed  xor     r8d, r8d; lpContext
0x1800555f0  lea     edx, [r8+4]; dwFlags
0x1800555f4  mov     rcx, rdi; lpInitOnce
0x1800555f7  call    cs:__imp_InitOnceComplete
0x1800555fd  mov     eax, ebx
0x1800555ff  jmp     short loc_180055611
0x180055601  xor     r8d, r8d; lpContext
0x180055604  xor     edx, edx; dwFlags
0x180055606  mov     rcx, rdi; lpInitOnce
0x180055609  call    cs:__imp_InitOnceComplete
0x18005560f  xor     eax, eax
0x180055611  mov     rbx, [rsp+28h+arg_0]
0x180055616  add     rsp, 20h
0x18005561a  pop     rdi
0x18005561b  retn
```
