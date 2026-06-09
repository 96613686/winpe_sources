# Microsoft::WRL::SimpleClassFactory<WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180003810`
- end: `0x1800038b6`
- name: `?CreateInstance@?$SimpleClassFactory@VServiceUiToastStatics@Calls@ApplicationModel@WindowsInternal@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `166`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800032d0`
- `0x180003810`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000383a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000383a`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics,0>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  int v6; // ebx
  __int64 v8; // rbx
  unsigned int v9; // edi
  _QWORD v10[3]; // [rsp+20h] [rbp-18h] BYREF

  *a4 = 0;
  if ( a2 )
  {
    v6 = -2147221232;
    RoOriginateError(2147746064LL);
    return (unsigned int)v6;
  }
  v10[0] = 0;
  v6 = Microsoft::WRL::Details::MakeAndInitialize<WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics,IUnknown,>(v10);
  if ( v6 < 0 )
  {
    if ( v10[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v10[0] + 16LL))(v10[0]);
    return (unsigned int)v6;
  }
  v8 = v10[0];
  v9 = (**(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *))v10[0])(v10[0], a3, a4);
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  return v9;
}

```

## disassembly

```asm
0x180003810  mov     [rsp+arg_0], rbx
0x180003815  mov     [rsp+arg_8], rsi
0x18000381a  push    rdi
0x18000381b  sub     rsp, 30h
0x18000381f  mov     qword ptr [r9], 0
0x180003826  mov     rdi, r9
0x180003829  mov     rsi, r8
0x18000382c  test    rdx, rdx
0x18000382f  jz      short loc_180003844
0x180003831  mov     ebx, 80040110h
0x180003836  xor     edx, edx
0x180003838  mov     ecx, ebx
0x18000383a  call    cs:__imp_RoOriginateError
0x180003840  mov     eax, ebx
0x180003842  jmp     short loc_1800038A6
0x180003844  lea     rcx, [rsp+38h+var_18]
0x180003849  mov     [rsp+38h+var_18], 0
0x180003852  call    ??$MakeAndInitialize@VServiceUiToastStatics@Calls@ApplicationModel@WindowsInternal@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::MakeAndInitialize<WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics,IUnknown,>(IUnknown * *)
0x180003857  mov     ebx, eax
0x180003859  test    eax, eax
0x18000385b  jns     short loc_180003875
0x18000385d  mov     rcx, [rsp+38h+var_18]
0x180003862  test    rcx, rcx
0x180003865  jz      short loc_180003840
0x180003867  mov     rdx, [rcx]
0x18000386a  mov     rax, [rdx+10h]
0x18000386e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003873  jmp     short loc_180003840
0x180003875  mov     rbx, [rsp+38h+var_18]
0x18000387a  mov     r8, rdi
0x18000387d  mov     rdx, rsi
0x180003880  mov     rcx, rbx
0x180003883  mov     rax, [rbx]
0x180003886  mov     rax, [rax]
0x180003889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000388e  mov     edi, eax
0x180003890  test    rbx, rbx
0x180003893  jz      short loc_1800038A4
0x180003895  mov     rdx, [rbx]
0x180003898  mov     rcx, rbx
0x18000389b  mov     rax, [rdx+10h]
0x18000389f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038a4  mov     eax, edi
0x1800038a6  mov     rbx, [rsp+38h+arg_0]
0x1800038ab  mov     rsi, [rsp+38h+arg_8]
0x1800038b0  add     rsp, 30h
0x1800038b4  pop     rdi
0x1800038b5  retn
```
