# Microsoft::WRL::SimpleClassFactory<FilterDS,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180009640`
- end: `0x1800096f7`
- name: `?CreateInstance@?$SimpleClassFactory@VFilterDS@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `183`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000775c`
- `0x180009640`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000966a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000966a`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<FilterDS,0>::CreateInstance(
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
    v6 = Microsoft::WRL::Details::MakeAndInitialize<FilterDS,IUnknown,>(&v10);
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
0x180009640  mov     [rsp+arg_0], rbx
0x180009645  mov     [rsp+arg_10], rsi
0x18000964a  push    rdi
0x18000964b  sub     rsp, 20h
0x18000964f  mov     rdi, r9
0x180009652  mov     rsi, r8
0x180009655  mov     qword ptr [r9], 0
0x18000965c  test    rdx, rdx
0x18000965f  jz      short loc_180009672
0x180009661  xor     edx, edx
0x180009663  mov     ebx, 80040110h
0x180009668  mov     ecx, ebx
0x18000966a  call    cs:__imp_RoOriginateError
0x180009670  jmp     short loc_1800096E5
0x180009672  mov     [rsp+28h+arg_8], 0
0x18000967b  lea     rcx, [rsp+28h+arg_8]
0x180009680  call    ??$MakeAndInitialize@VFilterDS@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::MakeAndInitialize<FilterDS,IUnknown,>(IUnknown * *)
0x180009685  mov     ebx, eax
0x180009687  test    eax, eax
0x180009689  jns     short loc_1800096AD
0x18000968b  mov     rcx, [rsp+28h+arg_8]
0x180009690  test    rcx, rcx
0x180009693  jz      short loc_1800096AB
0x180009695  mov     [rsp+28h+arg_8], 0
0x18000969e  mov     rdx, [rcx]
0x1800096a1  mov     rax, [rdx+10h]
0x1800096a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096aa  nop
0x1800096ab  jmp     short loc_1800096E5
0x1800096ad  mov     rcx, [rsp+28h+arg_8]
0x1800096b2  mov     rax, [rcx]
0x1800096b5  mov     r8, rdi
0x1800096b8  mov     rdx, rsi
0x1800096bb  mov     rax, [rax]
0x1800096be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096c3  mov     ebx, eax
0x1800096c5  mov     rcx, [rsp+28h+arg_8]
0x1800096ca  test    rcx, rcx
0x1800096cd  jz      short loc_1800096E5
0x1800096cf  mov     [rsp+28h+arg_8], 0
0x1800096d8  mov     rdx, [rcx]
0x1800096db  mov     rax, [rdx+10h]
0x1800096df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096e4  nop
0x1800096e5  mov     eax, ebx
0x1800096e7  mov     rbx, [rsp+28h+arg_0]
0x1800096ec  mov     rsi, [rsp+28h+arg_10]
0x1800096f1  add     rsp, 20h
0x1800096f5  pop     rdi
0x1800096f6  retn
```
