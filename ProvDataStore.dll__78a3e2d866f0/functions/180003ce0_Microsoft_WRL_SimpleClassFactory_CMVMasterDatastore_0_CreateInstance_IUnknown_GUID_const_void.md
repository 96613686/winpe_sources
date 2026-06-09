# Microsoft::WRL::SimpleClassFactory<CMVMasterDatastore,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180003ce0`
- end: `0x180003d97`
- name: `?CreateInstance@?$SimpleClassFactory@VCMVMasterDatastore@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `183`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000266c`
- `0x180003ce0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180003d0a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180003d0a`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<CMVMasterDatastore,0>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  int v6; // ebx
  __int64 (__fastcall ***v7)(_QWORD, _QWORD, _QWORD *); // rcx
  __int64 (__fastcall ***v8)(_QWORD, _QWORD, _QWORD *); // rcx
  __int64 (__fastcall ***v10)(_QWORD, __int64, _QWORD *); // [rsp+38h] [rbp+10h] BYREF

  *a4 = 0;
  if ( a2 )
  {
    v6 = -2147221232;
    RoOriginateError(2147746064LL, 0);
  }
  else
  {
    v10 = 0;
    v6 = Microsoft::WRL::Details::MakeAndInitialize<CMVMasterDatastore,IUnknown,>(&v10);
    if ( v6 >= 0 )
    {
      v6 = (**v10)(v10, a3, a4);
      v8 = v10;
      if ( v10 )
      {
        v10 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD *)))(*v8)[2])(v8);
      }
    }
    else
    {
      v7 = v10;
      if ( v10 )
      {
        v10 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD *)))(*v7)[2])(v7);
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180003ce0  mov     [rsp+arg_0], rbx
0x180003ce5  mov     [rsp+arg_10], rsi
0x180003cea  push    rdi
0x180003ceb  sub     rsp, 20h
0x180003cef  mov     rdi, r9
0x180003cf2  mov     rsi, r8
0x180003cf5  mov     qword ptr [r9], 0
0x180003cfc  test    rdx, rdx
0x180003cff  jz      short loc_180003D12
0x180003d01  xor     edx, edx
0x180003d03  mov     ebx, 80040110h
0x180003d08  mov     ecx, ebx
0x180003d0a  call    cs:__imp_RoOriginateError
0x180003d10  jmp     short loc_180003D85
0x180003d12  mov     [rsp+28h+arg_8], 0
0x180003d1b  lea     rcx, [rsp+28h+arg_8]
0x180003d20  call    ??$MakeAndInitialize@VCMVMasterDatastore@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CMVMasterDatastore,IUnknown,>(IUnknown * *)
0x180003d25  mov     ebx, eax
0x180003d27  test    eax, eax
0x180003d29  jns     short loc_180003D4D
0x180003d2b  mov     rcx, [rsp+28h+arg_8]
0x180003d30  test    rcx, rcx
0x180003d33  jz      short loc_180003D4B
0x180003d35  mov     [rsp+28h+arg_8], 0
0x180003d3e  mov     rdx, [rcx]
0x180003d41  mov     rax, [rdx+10h]
0x180003d45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d4a  nop
0x180003d4b  jmp     short loc_180003D85
0x180003d4d  mov     rcx, [rsp+28h+arg_8]
0x180003d52  mov     rax, [rcx]
0x180003d55  mov     r8, rdi
0x180003d58  mov     rdx, rsi
0x180003d5b  mov     rax, [rax]
0x180003d5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d63  mov     ebx, eax
0x180003d65  mov     rcx, [rsp+28h+arg_8]
0x180003d6a  test    rcx, rcx
0x180003d6d  jz      short loc_180003D85
0x180003d6f  mov     [rsp+28h+arg_8], 0
0x180003d78  mov     rdx, [rcx]
0x180003d7b  mov     rax, [rdx+10h]
0x180003d7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d84  nop
0x180003d85  mov     eax, ebx
0x180003d87  mov     rbx, [rsp+28h+arg_0]
0x180003d8c  mov     rsi, [rsp+28h+arg_10]
0x180003d91  add     rsp, 20h
0x180003d95  pop     rdi
0x180003d96  retn
```
