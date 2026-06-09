# Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::IXamlMetadataProvider *,1>::AllocateAndCopyElements(Windows::UI::Xaml::Markup::IXamlMetadataProvider * const *,uint)

- ea: `0x140029a28`
- end: `0x140029acf`
- name: `?AllocateAndCopyElements@?$WriteOnlyArray@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@$00@Platform@@KAPEAPE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@PEBQE$AAU34567@I@Z`
- size: `167`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140029170`
- `0x14002ddb0`

## callees

- `0x14000342d`
- `0x1400039f2`
- `0x140029a28`
- `0x140035010`

## import_xrefs

- `wincorlib!?__abi_WinRTraiseInvalidCastException@@YAXXZ` at `0x140029a4a`
- `wincorlib!?__abi_WinRTraiseInvalidCastException@@YAXXZ` at `0x140029a4a`
- `wincorlib!?__abi_WinRTraiseOutOfMemoryException@@YAXXZ` at `0x140029a68`
- `wincorlib!?__abi_WinRTraiseOutOfMemoryException@@YAXXZ` at `0x140029a68`

## pseudocode

```c
_QWORD *__fastcall Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::IXamlMetadataProvider __gc *,1>::AllocateAndCopyElements(
        __int64 a1,
        unsigned int a2)
{
  __int64 v2; // rdi
  _QWORD *v4; // rbx
  _QWORD *v5; // rax
  __int64 i; // rbp
  __int64 v7; // rsi
  __int64 v8; // rcx

  v2 = a2;
  if ( !a2 )
    return 0;
  if ( a2 > 0x1FFFFFFF )
  {
    __abi_WinRTraiseInvalidCastException();
    __debugbreak();
  }
  v5 = _Platform_CoTaskMemAlloc(8LL * a2);
  v4 = v5;
  if ( !v5 )
  {
    __abi_WinRTraiseOutOfMemoryException();
    __debugbreak();
  }
  memset_0(v5, 0, 8 * v2);
  for ( i = 0; (unsigned int)i < (unsigned int)v2; i = (unsigned int)(i + 1) )
  {
    v7 = *(_QWORD *)(a1 + 8 * i);
    if ( v7 != v4[i] )
    {
      if ( v7 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v7 + 8LL))(*(_QWORD *)(a1 + 8 * i));
      v8 = v4[i];
      if ( v8 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      v4[i] = v7;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x140029a28  push    rbx
0x140029a2a  push    rbp
0x140029a2b  push    rsi
0x140029a2c  push    rdi
0x140029a2d  push    r14
0x140029a2f  push    r15
0x140029a31  sub     rsp, 28h
0x140029a35  mov     edi, edx
0x140029a37  mov     r15, rcx
0x140029a3a  test    edx, edx
0x140029a3c  jnz     short loc_140029A42
0x140029a3e  xor     ebx, ebx
0x140029a40  jmp     short loc_140029ABF
0x140029a42  cmp     edi, 1FFFFFFFh
0x140029a48  jbe     short loc_140029A51
0x140029a4a  call    cs:__imp_?__abi_WinRTraiseInvalidCastException@@YAXXZ; __abi_WinRTraiseInvalidCastException(void)
0x140029a50  int     3; Trap to Debugger
0x140029a51  mov     rsi, rdi
0x140029a54  shl     rsi, 3
0x140029a58  mov     rcx, rsi; cb
0x140029a5b  call    __Platform_CoTaskMemAlloc
0x140029a60  mov     rbx, rax
0x140029a63  test    rax, rax
0x140029a66  jnz     short loc_140029A6F
0x140029a68  call    cs:__imp_?__abi_WinRTraiseOutOfMemoryException@@YAXXZ; __abi_WinRTraiseOutOfMemoryException(void)
0x140029a6e  int     3; Trap to Debugger
0x140029a6f  mov     r8, rsi; Size
0x140029a72  xor     edx, edx; Val
0x140029a74  mov     rcx, rbx; void *
0x140029a77  call    memset_0
0x140029a7c  xor     ebp, ebp
0x140029a7e  test    edi, edi
0x140029a80  jz      short loc_140029ABF
0x140029a82  mov     rsi, [r15+rbp*8]
0x140029a86  cmp     rsi, [rbx+rbp*8]
0x140029a8a  jz      short loc_140029AB9
0x140029a8c  test    rsi, rsi
0x140029a8f  jz      short loc_140029AA0
0x140029a91  mov     rax, [rsi]
0x140029a94  mov     rcx, rsi
0x140029a97  mov     rax, [rax+8]
0x140029a9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029aa0  mov     rcx, [rbx+rbp*8]
0x140029aa4  test    rcx, rcx
0x140029aa7  jz      short loc_140029AB5
0x140029aa9  mov     rax, [rcx]
0x140029aac  mov     rax, [rax+10h]
0x140029ab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029ab5  mov     [rbx+rbp*8], rsi
0x140029ab9  inc     ebp
0x140029abb  cmp     ebp, edi
0x140029abd  jb      short loc_140029A82
0x140029abf  mov     rax, rbx
0x140029ac2  add     rsp, 28h
0x140029ac6  pop     r15
0x140029ac8  pop     r14
0x140029aca  pop     rdi
0x140029acb  pop     rsi
0x140029acc  pop     rbp
0x140029acd  pop     rbx
0x140029ace  retn
```
