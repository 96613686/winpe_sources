# wil::init_once_nothrow__lambda_1cba0c56c11df3097c8f2ad02e3e4fb7___

- ea: `0x180041aa0`
- end: `0x180041b42`
- name: `wil::init_once_nothrow__lambda_1cba0c56c11df3097c8f2ad02e3e4fb7___`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002637c`

## callees

- `0x18000a384`
- `0x18002acfc`
- `0x180041aa0`
- `0x180041d00`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180041b1e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180041b34`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180041b1e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180041b34`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180041ac3`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180041ac3`

## pseudocode

```c
__int64 __fastcall wil::init_once_nothrow__lambda_1cba0c56c11df3097c8f2ad02e3e4fb7___(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  const char *v3; // r9
  int v5; // eax
  unsigned int v6; // ebx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  WINBOOL fPending; // [rsp+40h] [rbp+18h] BYREF
  int v10; // [rsp+44h] [rbp+1Ch]

  v10 = HIDWORD(a3);
  fPending = 0;
  if ( !InitOnceBeginInitialize(&InitOnce, 0, &fPending, 0) )
    return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0x37A, (unsigned int)"wil", v3);
  if ( fPending )
  {
    v5 = lambda_1cba0c56c11df3097c8f2ad02e3e4fb7_::operator()();
    v6 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x37F, (unsigned int)"wil", (const char *)(unsigned int)v5, v7);
      InitOnceComplete(&InitOnce, 4u, 0);
      return v6;
    }
    InitOnceComplete(&InitOnce, 0, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180041aa0  mov     qword ptr [rsp+fPending], r8
0x180041aa5  push    rbx; int
0x180041aa6  sub     rsp, 20h
0x180041aaa  xor     r9d, r9d; lpContext
0x180041aad  mov     [rsp+28h+fPending], 0
0x180041ab5  lea     r8, [rsp+28h+fPending]; fPending
0x180041aba  xor     edx, edx; dwFlags
0x180041abc  lea     rcx, InitOnce; lpInitOnce
0x180041ac3  call    cs:__imp_InitOnceBeginInitialize
0x180041ac9  test    eax, eax
0x180041acb  jnz     short loc_180041AE5
0x180041acd  mov     rcx, [rsp+28h]; this
0x180041ad2  lea     r8, aWil; "wil"
0x180041ad9  mov     edx, 37Ah; void *
0x180041ade  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180041ae3  jmp     short loc_180041B3C
0x180041ae5  cmp     [rsp+28h+fPending], 0
0x180041aea  jz      short loc_180041B3A
0x180041aec  call    _lambda_1cba0c56c11df3097c8f2ad02e3e4fb7___operator__
0x180041af1  mov     ebx, eax
0x180041af3  test    eax, eax
0x180041af5  jns     short loc_180041B28
0x180041af7  mov     rcx, [rsp+28h]; this
0x180041afc  lea     r8, aWil; "wil"
0x180041b03  mov     r9d, eax; char *
0x180041b06  mov     edx, 37Fh; void *
0x180041b0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041b10  xor     r8d, r8d; lpContext
0x180041b13  lea     rcx, InitOnce; lpInitOnce
0x180041b1a  lea     edx, [r8+4]; dwFlags
0x180041b1e  call    cs:__imp_InitOnceComplete
0x180041b24  mov     eax, ebx
0x180041b26  jmp     short loc_180041B3C
0x180041b28  xor     r8d, r8d; lpContext
0x180041b2b  lea     rcx, InitOnce; lpInitOnce
0x180041b32  xor     edx, edx; dwFlags
0x180041b34  call    cs:__imp_InitOnceComplete
0x180041b3a  xor     eax, eax
0x180041b3c  add     rsp, 20h
0x180041b40  pop     rbx
0x180041b41  retn
```
