# wil::init_once_nothrow__lambda_3c850af1cf56a0cec55244ba14e13cf1___

- ea: `0x180076a80`
- end: `0x180076b22`
- name: `wil::init_once_nothrow__lambda_3c850af1cf56a0cec55244ba14e13cf1___`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180077440`

## callees

- `0x18000b5c0`
- `0x180044408`
- `0x180076a80`
- `0x180076f8c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180076aa3`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180076aa3`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180076afe`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180076b14`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180076afe`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180076b14`

## pseudocode

```c
__int64 __fastcall wil::init_once_nothrow__lambda_3c850af1cf56a0cec55244ba14e13cf1___(
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
  if ( !__std_init_once_begin_initialize(&ApplicationActivationImpl::s_activationBrokerInitOnce, 0, &fPending, 0) )
    return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0x37A, (unsigned int)"wil", v3);
  if ( fPending )
  {
    v5 = lambda_3c850af1cf56a0cec55244ba14e13cf1_::operator()();
    v6 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x37F, (unsigned int)"wil", (const char *)(unsigned int)v5, v7);
      InitOnceComplete(&ApplicationActivationImpl::s_activationBrokerInitOnce, 4u, 0);
      return v6;
    }
    InitOnceComplete(&ApplicationActivationImpl::s_activationBrokerInitOnce, 0, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180076a80  mov     qword ptr [rsp+fPending], r8
0x180076a85  push    rbx; int
0x180076a86  sub     rsp, 20h
0x180076a8a  mov     [rsp+28h+fPending], 0
0x180076a92  xor     r9d, r9d; lpContext
0x180076a95  lea     r8, [rsp+28h+fPending]; fPending
0x180076a9a  xor     edx, edx; dwFlags
0x180076a9c  lea     rcx, ?s_activationBrokerInitOnce@ApplicationActivationImpl@@0T_RTL_RUN_ONCE@@A; lpInitOnce
0x180076aa3  call    cs:__imp___std_init_once_begin_initialize
0x180076aa9  test    eax, eax
0x180076aab  jnz     short loc_180076AC5
0x180076aad  mov     rcx, [rsp+28h]; this
0x180076ab2  lea     r8, aWil; "wil"
0x180076ab9  mov     edx, 37Ah; void *
0x180076abe  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180076ac3  jmp     short loc_180076B1C
0x180076ac5  cmp     [rsp+28h+fPending], 0
0x180076aca  jz      short loc_180076B1A
0x180076acc  call    _lambda_3c850af1cf56a0cec55244ba14e13cf1___operator__
0x180076ad1  mov     ebx, eax
0x180076ad3  test    eax, eax
0x180076ad5  jns     short loc_180076B08
0x180076ad7  mov     rcx, [rsp+28h]; this
0x180076adc  mov     r9d, eax; char *
0x180076adf  lea     r8, aWil; "wil"
0x180076ae6  mov     edx, 37Fh; void *
0x180076aeb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076af0  xor     r8d, r8d; lpContext
0x180076af3  lea     edx, [r8+4]; dwFlags
0x180076af7  lea     rcx, ?s_activationBrokerInitOnce@ApplicationActivationImpl@@0T_RTL_RUN_ONCE@@A; lpInitOnce
0x180076afe  call    cs:__imp_InitOnceComplete
0x180076b04  mov     eax, ebx
0x180076b06  jmp     short loc_180076B1C
0x180076b08  xor     r8d, r8d; lpContext
0x180076b0b  xor     edx, edx; dwFlags
0x180076b0d  lea     rcx, ?s_activationBrokerInitOnce@ApplicationActivationImpl@@0T_RTL_RUN_ONCE@@A; lpInitOnce
0x180076b14  call    cs:__imp_InitOnceComplete
0x180076b1a  xor     eax, eax
0x180076b1c  add     rsp, 20h
0x180076b20  pop     rbx
0x180076b21  retn
```
