# Microsoft::WRL::SimpleClassFactory<WindowsInternal::ApplicationModel::Calls::AppLauncherStatics,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1800036a0`
- end: `0x180003746`
- name: `?CreateInstance@?$SimpleClassFactory@VAppLauncherStatics@Calls@ApplicationModel@WindowsInternal@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `166`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003130`
- `0x1800036a0`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800036ca`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800036ca`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<WindowsInternal::ApplicationModel::Calls::AppLauncherStatics,0>::CreateInstance(
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
  v6 = Microsoft::WRL::Details::MakeAndInitialize<WindowsInternal::ApplicationModel::Calls::AppLauncherStatics,IUnknown,>(v10);
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
0x1800036a0  mov     [rsp+arg_0], rbx
0x1800036a5  mov     [rsp+arg_8], rsi
0x1800036aa  push    rdi
0x1800036ab  sub     rsp, 30h
0x1800036af  mov     qword ptr [r9], 0
0x1800036b6  mov     rdi, r9
0x1800036b9  mov     rsi, r8
0x1800036bc  test    rdx, rdx
0x1800036bf  jz      short loc_1800036D4
0x1800036c1  mov     ebx, 80040110h
0x1800036c6  xor     edx, edx
0x1800036c8  mov     ecx, ebx
0x1800036ca  call    cs:__imp_RoOriginateError
0x1800036d0  mov     eax, ebx
0x1800036d2  jmp     short loc_180003736
0x1800036d4  lea     rcx, [rsp+38h+var_18]
0x1800036d9  mov     [rsp+38h+var_18], 0
0x1800036e2  call    ??$MakeAndInitialize@VAppLauncherStatics@Calls@ApplicationModel@WindowsInternal@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::MakeAndInitialize<WindowsInternal::ApplicationModel::Calls::AppLauncherStatics,IUnknown,>(IUnknown * *)
0x1800036e7  mov     ebx, eax
0x1800036e9  test    eax, eax
0x1800036eb  jns     short loc_180003705
0x1800036ed  mov     rcx, [rsp+38h+var_18]
0x1800036f2  test    rcx, rcx
0x1800036f5  jz      short loc_1800036D0
0x1800036f7  mov     rdx, [rcx]
0x1800036fa  mov     rax, [rdx+10h]
0x1800036fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003703  jmp     short loc_1800036D0
0x180003705  mov     rbx, [rsp+38h+var_18]
0x18000370a  mov     r8, rdi
0x18000370d  mov     rdx, rsi
0x180003710  mov     rcx, rbx
0x180003713  mov     rax, [rbx]
0x180003716  mov     rax, [rax]
0x180003719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000371e  mov     edi, eax
0x180003720  test    rbx, rbx
0x180003723  jz      short loc_180003734
0x180003725  mov     rdx, [rbx]
0x180003728  mov     rcx, rbx
0x18000372b  mov     rax, [rdx+10h]
0x18000372f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003734  mov     eax, edi
0x180003736  mov     rbx, [rsp+38h+arg_0]
0x18000373b  mov     rsi, [rsp+38h+arg_8]
0x180003740  add     rsp, 30h
0x180003744  pop     rdi
0x180003745  retn
```
