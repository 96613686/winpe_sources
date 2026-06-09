# _anonymous_namespace_::RecolorSvgSubtree

- ea: `0x18002bbf8`
- end: `0x18002bd28`
- name: `_anonymous_namespace_::RecolorSvgSubtree`
- size: `304`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002bb80`
- `0x18002bbf8`

## callees

- `0x18000a6e0`
- `0x18000cf94`
- `0x18002b9dc`
- `0x18002bbf8`
- `0x180035010`

## string_xrefs

- `0x18002bd00`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\cursorutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall anonymous_namespace_::RecolorSvgSubtree(__int64 a1, __int128 *a2)
{
  void (__fastcall *v4)(__int64, __int64 *); // rbx
  __int64 (__fastcall *v5)(__int64, __int64, __int64 *); // rbx
  int v6; // eax
  __int64 v7; // rax
  __int64 v8; // rbx
  __int128 v10; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  __int64 v12; // [rsp+50h] [rbp+20h] BYREF
  __int64 v13; // [rsp+58h] [rbp+28h] BYREF
  __int64 v14; // [rsp+60h] [rbp+30h] BYREF

  v10 = *a2;
  anonymous_namespace_::RecolorSvgAttribute(a1, (__int64)L"fill", &v10);
  v10 = *a2;
  anonymous_namespace_::RecolorSvgAttribute(a1, (__int64)L"stroke", &v10);
  v12 = 0;
  v4 = *(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a1 + 80LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
  v4(a1, &v12);
  while ( v12 )
  {
    v10 = *a2;
    anonymous_namespace_::RecolorSvgSubtree(v12, &v10);
    v13 = 0;
    v5 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)a1 + 104LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
    v6 = v5(a1, v12, &v13);
    if ( v6 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xD4,
        (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\cursorutils.cpp",
        (const char *)(unsigned int)v6,
        v10);
    v7 = v12;
    v8 = v13;
    if ( v12 != v13 )
    {
      if ( v13 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
        v7 = v12;
      }
      v14 = v7;
      v12 = v8;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
  }
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
}

```

## disassembly

```asm
0x18002bbf8  mov     [rsp-18h+arg_18], rbx
0x18002bbfd  push    rbp
0x18002bbfe  push    rsi
0x18002bbff  push    rdi
0x18002bc00  mov     rbp, rsp
0x18002bc03  sub     rsp, 30h
0x18002bc07  mov     rsi, rdx
0x18002bc0a  mov     rdi, rcx
0x18002bc0d  movups  xmm0, xmmword ptr [rdx]
0x18002bc10  movdqu  [rbp+var_10], xmm0
0x18002bc15  lea     r8, [rbp+var_10]
0x18002bc19  lea     rdx, aFill; "fill"
0x18002bc20  call    _anonymous_namespace___RecolorSvgAttribute
0x18002bc25  movups  xmm0, xmmword ptr [rsi]
0x18002bc28  movdqu  [rbp+var_10], xmm0
0x18002bc2d  lea     r8, [rbp+var_10]
0x18002bc31  lea     rdx, aStroke; "stroke"
0x18002bc38  mov     rcx, rdi
0x18002bc3b  call    _anonymous_namespace___RecolorSvgAttribute
0x18002bc40  mov     [rbp+arg_0], 0
0x18002bc48  mov     rax, [rdi]
0x18002bc4b  mov     rbx, [rax+50h]
0x18002bc4f  lea     rcx, [rbp+arg_0]
0x18002bc53  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002bc58  lea     rdx, [rbp+arg_0]
0x18002bc5c  mov     rcx, rdi
0x18002bc5f  mov     rax, rbx
0x18002bc62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc67  mov     rcx, [rbp+arg_0]
0x18002bc6b  test    rcx, rcx
0x18002bc6e  jz      loc_18002BD12
0x18002bc74  movups  xmm0, xmmword ptr [rsi]
0x18002bc77  movdqu  [rbp+var_10], xmm0
0x18002bc7c  lea     rdx, [rbp+var_10]
0x18002bc80  call    _anonymous_namespace___RecolorSvgSubtree
0x18002bc85  mov     [rbp+arg_8], 0
0x18002bc8d  mov     rax, [rdi]
0x18002bc90  mov     rbx, [rax+68h]
0x18002bc94  lea     rcx, [rbp+arg_8]
0x18002bc98  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002bc9d  lea     r8, [rbp+arg_8]
0x18002bca1  mov     rdx, [rbp+arg_0]
0x18002bca5  mov     rcx, rdi
0x18002bca8  mov     rax, rbx
0x18002bcab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bcb0  mov     rcx, [rbp+18h]; this
0x18002bcb4  test    eax, eax
0x18002bcb6  js      short loc_18002BCFD
0x18002bcb8  mov     rax, [rbp+arg_0]
0x18002bcbc  mov     rbx, [rbp+arg_8]
0x18002bcc0  cmp     rax, rbx
0x18002bcc3  jz      short loc_18002BCEF
0x18002bcc5  test    rbx, rbx
0x18002bcc8  jz      short loc_18002BCDD
0x18002bcca  mov     rax, [rbx]
0x18002bccd  mov     rcx, rbx
0x18002bcd0  mov     rax, [rax+8]
0x18002bcd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bcd9  mov     rax, [rbp+arg_0]
0x18002bcdd  mov     [rbp+arg_10], rax
0x18002bce1  mov     [rbp+arg_0], rbx
0x18002bce5  lea     rcx, [rbp+arg_10]
0x18002bce9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002bcee  nop
0x18002bcef  lea     rcx, [rbp+arg_8]
0x18002bcf3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002bcf8  jmp     loc_18002BC67
0x18002bcfd  mov     r9d, eax; char *
0x18002bd00  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\accessibletech\\ex"...
0x18002bd07  mov     edx, 0D4h; void *
0x18002bd0c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002bd12  lea     rcx, [rbp+arg_0]
0x18002bd16  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002bd1b  mov     rbx, [rsp+30h+arg_18]
0x18002bd20  add     rsp, 30h
0x18002bd24  pop     rdi
0x18002bd25  pop     rsi
0x18002bd26  pop     rbp
0x18002bd27  retn
```
