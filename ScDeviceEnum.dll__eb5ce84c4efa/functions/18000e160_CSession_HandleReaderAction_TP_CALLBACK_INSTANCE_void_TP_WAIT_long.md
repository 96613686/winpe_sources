# CSession::_HandleReaderAction(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x18000e160`
- end: `0x18000e220`
- name: `?_HandleReaderAction@CSession@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `192`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, CSession *Context, PTP_WAIT Wait, __int64 WaitResult)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18000c7b0`
- `0x18000cc78`
- `0x18000d4bc`
- `0x18000da20`
- `0x18000db7c`
- `0x18000e160`
- `0x18001e020`

## string_xrefs

- `0x18000e18a`: `CSession::_HandleReaderAction`

## pseudocode

```c
void __fastcall CSession::_HandleReaderAction(
        PTP_CALLBACK_INSTANCE Instance,
        CSession *Context,
        PTP_WAIT Wait,
        __int64 WaitResult)
{
  int v5; // [rsp+20h] [rbp-19h] BYREF
  CSession *v6; // [rsp+28h] [rbp-11h] BYREF
  _QWORD *v7; // [rsp+38h] [rbp-1h] BYREF
  _QWORD v8[2]; // [rsp+40h] [rbp+7h] BYREF
  CSession **v9; // [rsp+50h] [rbp+17h] BYREF
  __int16 v10; // [rsp+58h] [rbp+1Fh]
  char v11[32]; // [rsp+60h] [rbp+27h] BYREF

  strcpy(v11, "CSession::_HandleReaderAction");
  v8[0] = v11;
  v8[1] = &v5;
  lambda_1684c019d9c653e113c18e280f091e04_::operator()(v8, Context, Wait, WaitResult, 0);
  v5 = 1;
  v7 = v8;
  v6 = Context;
  v9 = &v6;
  v10 = 258;
  if ( (int)CSession::_CreateReaderActionWait((char *)Context) >= 0 )
    CSession::_DoReadrmonNodeDiff(v6);
  wil::details::ScopeExitFnGuard__lambda_1f25a61b5ace30e9fc9ecb8c3af71889___::operator()(&v9);
  WppTraceUnwinder__lambda_1684c019d9c653e113c18e280f091e04____::_WppTraceUnwinder__lambda_1684c019d9c653e113c18e280f091e04____(&v7);
}

```

## disassembly

```asm
0x18000e160  mov     [rsp-8+arg_0], rbx
0x18000e165  push    rbp
0x18000e166  lea     rbp, [rsp-57h]
0x18000e16b  sub     rsp, 90h
0x18000e172  mov     rax, cs:__security_cookie
0x18000e179  xor     rax, rsp
0x18000e17c  mov     [rbp+57h+var_10], rax
0x18000e180  mov     rbx, rdx
0x18000e183  mov     [rbp+57h+var_70], 0
0x18000e18a  movups  xmm0, xmmword ptr cs:aCsessionHandle; "CSession::_HandleReaderAction"
0x18000e191  movups  xmmword ptr [rbp+57h+var_30], xmm0
0x18000e195  movups  xmm1, xmmword ptr cs:aCsessionHandle+0Eh; "dleReaderAction"
0x18000e19c  movups  xmmword ptr [rbp+57h+var_30+0Eh], xmm1
0x18000e1a0  lea     rax, [rbp+57h+var_30]
0x18000e1a4  mov     [rbp+57h+var_50], rax
0x18000e1a8  lea     rax, [rbp+57h+var_70]
0x18000e1ac  mov     [rbp+57h+var_48], rax
0x18000e1b0  lea     rcx, [rbp+57h+var_50]
0x18000e1b4  call    _lambda_1684c019d9c653e113c18e280f091e04___operator__
0x18000e1b9  mov     [rbp+57h+var_70], 1
0x18000e1c0  lea     rax, [rbp+57h+var_50]
0x18000e1c4  mov     [rbp+57h+var_58], rax
0x18000e1c8  mov     [rbp+57h+var_68], rbx
0x18000e1cc  lea     rax, [rbp+57h+var_68]
0x18000e1d0  mov     [rbp+57h+var_40], rax
0x18000e1d4  mov     [rbp+57h+var_38], 102h
0x18000e1da  mov     rcx, rbx; pv
0x18000e1dd  call    ?_CreateReaderActionWait@CSession@@AEAAJXZ; CSession::_CreateReaderActionWait(void)
0x18000e1e2  test    eax, eax
0x18000e1e4  js      short loc_18000E1F0
0x18000e1e6  mov     rcx, [rbp+57h+var_68]; this
0x18000e1ea  call    ?_DoReadrmonNodeDiff@CSession@@AEAAJXZ; CSession::_DoReadrmonNodeDiff(void)
0x18000e1ef  nop
0x18000e1f0  lea     rcx, [rbp+57h+var_40]
0x18000e1f4  call    wil__details__ScopeExitFnGuard__lambda_1f25a61b5ace30e9fc9ecb8c3af71889_____operator__
0x18000e1f9  nop
0x18000e1fa  lea     rcx, [rbp+57h+var_58]
0x18000e1fe  call    WppTraceUnwinder__lambda_1684c019d9c653e113c18e280f091e04_______WppTraceUnwinder__lambda_1684c019d9c653e113c18e280f091e04____
0x18000e203  mov     rcx, [rbp+57h+var_10]
0x18000e207  xor     rcx, rsp; StackCookie
0x18000e20a  call    __security_check_cookie
0x18000e20f  mov     rbx, [rsp+90h+arg_0]
0x18000e217  add     rsp, 90h
0x18000e21e  pop     rbp
0x18000e21f  retn
```
