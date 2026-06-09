# wil::init_once_nothrow__lambda_942f6dc8610eaee085bddeebfbc46684___

- ea: `0x180024e84`
- end: `0x180024f2f`
- name: `wil::init_once_nothrow__lambda_942f6dc8610eaee085bddeebfbc46684___`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180005b08`

## callees

- `0x180006edc`
- `0x180024e84`
- `0x180024f38`
- `0x18008072c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180024f0b`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180024f21`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180024f0b`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180024f21`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180024eab`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180024eab`

## pseudocode

```c
__int64 __fastcall wil::init_once_nothrow__lambda_942f6dc8610eaee085bddeebfbc46684___(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  const char *v3; // r9
  int v5; // eax
  unsigned int v6; // ebx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  _QWORD *v9; // [rsp+38h] [rbp+10h] BYREF
  WINBOOL v10; // [rsp+40h] [rbp+18h] BYREF
  int v11; // [rsp+44h] [rbp+1Ch]

  v11 = HIDWORD(a3);
  v9 = a2;
  v10 = 0;
  if ( !__std_init_once_begin_initialize(&BasicUtils::s_initOnceIsInRailSession, 0, &v10, 0) )
    return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0x37A, (unsigned int)"wil", v3);
  if ( v10 )
  {
    v5 = lambda_942f6dc8610eaee085bddeebfbc46684_::operator()(&v9);
    v6 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x37F, (unsigned int)"wil", (const char *)(unsigned int)v5, v7);
      InitOnceComplete(&BasicUtils::s_initOnceIsInRailSession, 4u, 0);
      return v6;
    }
    InitOnceComplete(&BasicUtils::s_initOnceIsInRailSession, 0, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180024e84  mov     rax, rsp
0x180024e87  mov     [rax+18h], r8
0x180024e8b  mov     [rax+10h], rdx
0x180024e8f  push    rbx; int
0x180024e90  sub     rsp, 20h
0x180024e94  xor     r9d, r9d; lpContext
0x180024e97  mov     dword ptr [rax+18h], 0
0x180024e9e  lea     r8, [rax+18h]; fPending
0x180024ea2  xor     edx, edx; dwFlags
0x180024ea4  lea     rcx, ?s_initOnceIsInRailSession@BasicUtils@@0T_RTL_RUN_ONCE@@A; lpInitOnce
0x180024eab  call    cs:__imp___std_init_once_begin_initialize
0x180024eb1  test    eax, eax
0x180024eb3  jnz     short loc_180024ECD
0x180024eb5  mov     rcx, [rsp+28h]; this
0x180024eba  lea     r8, aWil; "wil"
0x180024ec1  mov     edx, 37Ah; void *
0x180024ec6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180024ecb  jmp     short loc_180024F29
0x180024ecd  cmp     [rsp+28h+arg_10], 0
0x180024ed2  jz      short loc_180024F27
0x180024ed4  lea     rcx, [rsp+28h+arg_8]
0x180024ed9  call    _lambda_942f6dc8610eaee085bddeebfbc46684___operator__
0x180024ede  mov     ebx, eax
0x180024ee0  test    eax, eax
0x180024ee2  jns     short loc_180024F15
0x180024ee4  mov     rcx, [rsp+28h]; this
0x180024ee9  lea     r8, aWil; "wil"
0x180024ef0  mov     r9d, eax; char *
0x180024ef3  mov     edx, 37Fh; void *
0x180024ef8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024efd  xor     r8d, r8d; lpContext
0x180024f00  lea     rcx, ?s_initOnceIsInRailSession@BasicUtils@@0T_RTL_RUN_ONCE@@A; lpInitOnce
0x180024f07  lea     edx, [r8+4]; dwFlags
0x180024f0b  call    cs:__imp_InitOnceComplete
0x180024f11  mov     eax, ebx
0x180024f13  jmp     short loc_180024F29
0x180024f15  xor     r8d, r8d; lpContext
0x180024f18  lea     rcx, ?s_initOnceIsInRailSession@BasicUtils@@0T_RTL_RUN_ONCE@@A; lpInitOnce
0x180024f1f  xor     edx, edx; dwFlags
0x180024f21  call    cs:__imp_InitOnceComplete
0x180024f27  xor     eax, eax
0x180024f29  add     rsp, 20h
0x180024f2d  pop     rbx
0x180024f2e  retn
```
