# Microsoft::WRL::SimpleClassFactory<WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180003750`
- end: `0x180003800`
- name: `?CreateInstance@?$SimpleClassFactory@VIncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `176`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001dc0`
- `0x1800031ec`
- `0x180003750`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180003789`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180003789`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics,0>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned int v6; // ebx
  int v7; // eax
  __int64 (__fastcall ***v8)(_QWORD, _QWORD, _QWORD *); // rcx
  unsigned int v9; // eax
  __int64 (__fastcall ***v11)(_QWORD, __int64, _QWORD *); // [rsp+20h] [rbp-18h] BYREF

  *a4 = 0;
  if ( a2 )
  {
    v6 = -2147221232;
    RoOriginateError(2147746064LL);
  }
  else
  {
    v11 = 0;
    v7 = Microsoft::WRL::Details::MakeAndInitialize<WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics,IUnknown,>(&v11);
    v8 = v11;
    v6 = v7;
    if ( v7 >= 0 )
    {
      v9 = (**v11)(v11, a3, a4);
      v8 = v11;
      v6 = v9;
    }
    if ( v8 )
    {
      v11 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD *)))(*v8)[2])(v8);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180003750  mov     [rsp+arg_0], rbx
0x180003755  mov     [rsp+arg_8], rsi
0x18000375a  push    rdi
0x18000375b  sub     rsp, 30h
0x18000375f  mov     rax, cs:__security_cookie
0x180003766  xor     rax, rsp
0x180003769  mov     [rsp+38h+var_10], rax
0x18000376e  mov     qword ptr [r9], 0
0x180003775  mov     rdi, r9
0x180003778  mov     rsi, r8
0x18000377b  test    rdx, rdx
0x18000377e  jz      short loc_180003791
0x180003780  mov     ebx, 80040110h
0x180003785  xor     edx, edx
0x180003787  mov     ecx, ebx
0x180003789  call    cs:__imp_RoOriginateError
0x18000378f  jmp     short loc_1800037E1
0x180003791  lea     rcx, [rsp+38h+var_18]
0x180003796  mov     [rsp+38h+var_18], 0
0x18000379f  call    ??$MakeAndInitialize@VIncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::MakeAndInitialize<WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics,IUnknown,>(IUnknown * *)
0x1800037a4  mov     rcx, [rsp+38h+var_18]
0x1800037a9  mov     ebx, eax
0x1800037ab  test    eax, eax
0x1800037ad  js      short loc_1800037C7
0x1800037af  mov     rax, [rcx]
0x1800037b2  mov     r8, rdi
0x1800037b5  mov     rdx, rsi
0x1800037b8  mov     rax, [rax]
0x1800037bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037c0  mov     rcx, [rsp+38h+var_18]
0x1800037c5  mov     ebx, eax
0x1800037c7  test    rcx, rcx
0x1800037ca  jz      short loc_1800037E1
0x1800037cc  mov     [rsp+38h+var_18], 0
0x1800037d5  mov     rdx, [rcx]
0x1800037d8  mov     rax, [rdx+10h]
0x1800037dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037e1  mov     eax, ebx
0x1800037e3  mov     rcx, [rsp+38h+var_10]
0x1800037e8  xor     rcx, rsp; StackCookie
0x1800037eb  call    __security_check_cookie
0x1800037f0  mov     rbx, [rsp+38h+arg_0]
0x1800037f5  mov     rsi, [rsp+38h+arg_8]
0x1800037fa  add     rsp, 30h
0x1800037fe  pop     rdi
0x1800037ff  retn
```
