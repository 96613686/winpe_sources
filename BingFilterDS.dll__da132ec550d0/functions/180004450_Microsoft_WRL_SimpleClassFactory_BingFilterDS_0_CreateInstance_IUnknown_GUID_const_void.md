# Microsoft::WRL::SimpleClassFactory<BingFilterDS,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180004450`
- end: `0x180004507`
- name: `?CreateInstance@?$SimpleClassFactory@VBingFilterDS@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `183`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180002e6c`
- `0x180004450`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000447a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000447a`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<BingFilterDS,0>::CreateInstance(
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
    v6 = Microsoft::WRL::Details::MakeAndInitialize<BingFilterDS,IUnknown,>(&v10);
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
0x180004450  mov     [rsp+arg_0], rbx
0x180004455  mov     [rsp+arg_10], rsi
0x18000445a  push    rdi
0x18000445b  sub     rsp, 20h
0x18000445f  mov     rdi, r9
0x180004462  mov     rsi, r8
0x180004465  mov     qword ptr [r9], 0
0x18000446c  test    rdx, rdx
0x18000446f  jz      short loc_180004482
0x180004471  xor     edx, edx
0x180004473  mov     ebx, 80040110h
0x180004478  mov     ecx, ebx
0x18000447a  call    cs:__imp_RoOriginateError
0x180004480  jmp     short loc_1800044F5
0x180004482  mov     [rsp+28h+arg_8], 0
0x18000448b  lea     rcx, [rsp+28h+arg_8]
0x180004490  call    ??$MakeAndInitialize@VBingFilterDS@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::MakeAndInitialize<BingFilterDS,IUnknown,>(IUnknown * *)
0x180004495  mov     ebx, eax
0x180004497  test    eax, eax
0x180004499  jns     short loc_1800044BD
0x18000449b  mov     rcx, [rsp+28h+arg_8]
0x1800044a0  test    rcx, rcx
0x1800044a3  jz      short loc_1800044BB
0x1800044a5  mov     [rsp+28h+arg_8], 0
0x1800044ae  mov     rdx, [rcx]
0x1800044b1  mov     rax, [rdx+10h]
0x1800044b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044ba  nop
0x1800044bb  jmp     short loc_1800044F5
0x1800044bd  mov     rcx, [rsp+28h+arg_8]
0x1800044c2  mov     rax, [rcx]
0x1800044c5  mov     r8, rdi
0x1800044c8  mov     rdx, rsi
0x1800044cb  mov     rax, [rax]
0x1800044ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044d3  mov     ebx, eax
0x1800044d5  mov     rcx, [rsp+28h+arg_8]
0x1800044da  test    rcx, rcx
0x1800044dd  jz      short loc_1800044F5
0x1800044df  mov     [rsp+28h+arg_8], 0
0x1800044e8  mov     rdx, [rcx]
0x1800044eb  mov     rax, [rdx+10h]
0x1800044ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044f4  nop
0x1800044f5  mov     eax, ebx
0x1800044f7  mov     rbx, [rsp+28h+arg_0]
0x1800044fc  mov     rsi, [rsp+28h+arg_10]
0x180004501  add     rsp, 20h
0x180004505  pop     rdi
0x180004506  retn
```
