# wil::init_once_nothrow__lambda_07cfb4ee289b66859adc8332a269efc3___

- ea: `0x18007aca8`
- end: `0x18007ad4a`
- name: `wil::init_once_nothrow__lambda_07cfb4ee289b66859adc8332a269efc3___`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18007ae20`

## callees

- `0x18000b5c0`
- `0x180044408`
- `0x18007aca8`
- `0x18007ad50`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18007accb`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18007accb`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18007ad26`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18007ad3c`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18007ad26`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18007ad3c`

## pseudocode

```c
__int64 __fastcall wil::init_once_nothrow__lambda_07cfb4ee289b66859adc8332a269efc3___(
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
  if ( !__std_init_once_begin_initialize(&ActivatableApplicationRegistrar::s_activationStoreInitOnce, 0, &fPending, 0) )
    return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0x37A, (unsigned int)"wil", v3);
  if ( fPending )
  {
    v5 = lambda_07cfb4ee289b66859adc8332a269efc3_::operator()();
    v6 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x37F, (unsigned int)"wil", (const char *)(unsigned int)v5, v7);
      InitOnceComplete(&ActivatableApplicationRegistrar::s_activationStoreInitOnce, 4u, 0);
      return v6;
    }
    InitOnceComplete(&ActivatableApplicationRegistrar::s_activationStoreInitOnce, 0, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x18007aca8  mov     qword ptr [rsp+fPending], r8
0x18007acad  push    rbx; int
0x18007acae  sub     rsp, 20h
0x18007acb2  mov     [rsp+28h+fPending], 0
0x18007acba  xor     r9d, r9d; lpContext
0x18007acbd  lea     r8, [rsp+28h+fPending]; fPending
0x18007acc2  xor     edx, edx; dwFlags
0x18007acc4  lea     rcx, ?s_activationStoreInitOnce@ActivatableApplicationRegistrar@@0T_RTL_RUN_ONCE@@A; lpInitOnce
0x18007accb  call    cs:__imp___std_init_once_begin_initialize
0x18007acd1  test    eax, eax
0x18007acd3  jnz     short loc_18007ACED
0x18007acd5  mov     rcx, [rsp+28h]; this
0x18007acda  lea     r8, aWil; "wil"
0x18007ace1  mov     edx, 37Ah; void *
0x18007ace6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007aceb  jmp     short loc_18007AD44
0x18007aced  cmp     [rsp+28h+fPending], 0
0x18007acf2  jz      short loc_18007AD42
0x18007acf4  call    _lambda_07cfb4ee289b66859adc8332a269efc3___operator__
0x18007acf9  mov     ebx, eax
0x18007acfb  test    eax, eax
0x18007acfd  jns     short loc_18007AD30
0x18007acff  mov     rcx, [rsp+28h]; this
0x18007ad04  mov     r9d, eax; char *
0x18007ad07  lea     r8, aWil; "wil"
0x18007ad0e  mov     edx, 37Fh; void *
0x18007ad13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007ad18  xor     r8d, r8d; lpContext
0x18007ad1b  lea     edx, [r8+4]; dwFlags
0x18007ad1f  lea     rcx, ?s_activationStoreInitOnce@ActivatableApplicationRegistrar@@0T_RTL_RUN_ONCE@@A; lpInitOnce
0x18007ad26  call    cs:__imp_InitOnceComplete
0x18007ad2c  mov     eax, ebx
0x18007ad2e  jmp     short loc_18007AD44
0x18007ad30  xor     r8d, r8d; lpContext
0x18007ad33  xor     edx, edx; dwFlags
0x18007ad35  lea     rcx, ?s_activationStoreInitOnce@ActivatableApplicationRegistrar@@0T_RTL_RUN_ONCE@@A; lpInitOnce
0x18007ad3c  call    cs:__imp_InitOnceComplete
0x18007ad42  xor     eax, eax
0x18007ad44  add     rsp, 20h
0x18007ad48  pop     rbx
0x18007ad49  retn
```
