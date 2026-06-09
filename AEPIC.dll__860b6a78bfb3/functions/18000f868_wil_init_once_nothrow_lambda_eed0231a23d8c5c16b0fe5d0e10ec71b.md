# wil::init_once_nothrow__lambda_eed0231a23d8c5c16b0fe5d0e10ec71b___

- ea: `0x18000f868`
- end: `0x18000f90a`
- name: `wil::init_once_nothrow__lambda_eed0231a23d8c5c16b0fe5d0e10ec71b___`
- size: `162`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180017fe0`

## callees

- `0x18000c35c`
- `0x18000c37c`
- `0x18000f868`
- `0x1800108f8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000f88b`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000f88b`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000f8e6`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000f8fc`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000f8e6`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000f8fc`

## pseudocode

```c
__int64 __fastcall wil::init_once_nothrow__lambda_eed0231a23d8c5c16b0fe5d0e10ec71b___(
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
  if ( !InitOnceBeginInitialize(&stru_180121580, 0, &fPending, 0) )
    return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0x37A, (unsigned int)"wil", v3);
  if ( fPending )
  {
    v5 = lambda_eed0231a23d8c5c16b0fe5d0e10ec71b_::operator()();
    v6 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x37F, (unsigned int)"wil", (const char *)(unsigned int)v5, v7);
      InitOnceComplete(&stru_180121580, 4u, 0);
      return v6;
    }
    InitOnceComplete(&stru_180121580, 0, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x18000f868  mov     qword ptr [rsp+fPending], r8
0x18000f86d  push    rbx; int
0x18000f86e  sub     rsp, 20h
0x18000f872  mov     [rsp+28h+fPending], 0
0x18000f87a  xor     r9d, r9d; lpContext
0x18000f87d  lea     r8, [rsp+28h+fPending]; fPending
0x18000f882  xor     edx, edx; dwFlags
0x18000f884  lea     rcx, stru_180121580; lpInitOnce
0x18000f88b  call    cs:__imp_InitOnceBeginInitialize
0x18000f891  test    eax, eax
0x18000f893  jnz     short loc_18000F8AD
0x18000f895  mov     rcx, [rsp+28h]; this
0x18000f89a  lea     r8, aWil; "wil"
0x18000f8a1  mov     edx, 37Ah; void *
0x18000f8a6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000f8ab  jmp     short loc_18000F904
0x18000f8ad  cmp     [rsp+28h+fPending], 0
0x18000f8b2  jz      short loc_18000F902
0x18000f8b4  call    _lambda_eed0231a23d8c5c16b0fe5d0e10ec71b___operator__
0x18000f8b9  mov     ebx, eax
0x18000f8bb  test    eax, eax
0x18000f8bd  jns     short loc_18000F8F0
0x18000f8bf  mov     rcx, [rsp+28h]; this
0x18000f8c4  mov     r9d, eax; char *
0x18000f8c7  lea     r8, aWil; "wil"
0x18000f8ce  mov     edx, 37Fh; void *
0x18000f8d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f8d8  xor     r8d, r8d; lpContext
0x18000f8db  lea     edx, [r8+4]; dwFlags
0x18000f8df  lea     rcx, stru_180121580; lpInitOnce
0x18000f8e6  call    cs:__imp_InitOnceComplete
0x18000f8ec  mov     eax, ebx
0x18000f8ee  jmp     short loc_18000F904
0x18000f8f0  xor     r8d, r8d; lpContext
0x18000f8f3  xor     edx, edx; dwFlags
0x18000f8f5  lea     rcx, stru_180121580; lpInitOnce
0x18000f8fc  call    cs:__imp_InitOnceComplete
0x18000f902  xor     eax, eax
0x18000f904  add     rsp, 20h
0x18000f908  pop     rbx
0x18000f909  retn
```
