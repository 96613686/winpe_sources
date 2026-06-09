# ?__abi_Platform_Details_IWeakReferenceSource____abi_GetWeakReference@?QIWeakReferenceSource@Details@Platform@@CssTemplateInfo@CHXSmartScreen@@UE$AAAJPEAPE$AAUIWeakReference@23@@Z

- ea: `0x1400080fc`
- end: `0x140008181`
- name: `?__abi_Platform_Details_IWeakReferenceSource____abi_GetWeakReference@?QIWeakReferenceSource@Details@Platform@@CssTemplateInfo@CHXSmartScreen@@UE$AAAJPEAPE$AAUIWeakReference@23@@Z`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140008190`

## callees

- `0x1400080fc`
- `0x140035010`

## import_xrefs

- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x140008114`
- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x140008114`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ___abi_Platform_Details_IWeakReferenceSource____abi_GetWeakReference__QIWeakReferenceSource_Details_Platform__CssTemplateInfo_CHXSmartScreen__UE_AAAJPEAPE_AAUIWeakReference_23__Z(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v3; // rbx

  if ( *(_BYTE *)(a1 + 112) )
  {
    __abi_WinRTraiseObjectDisposedException();
    __debugbreak();
  }
  try
  {
    *a2 = 0;
    v3 = *(_QWORD *)(a1 + 96);
    if ( v3 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v3 + 8LL))(*(_QWORD *)(a1 + 96));
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    }
    *a2 = v3;
  }
  catch ( ... )
  {
    __abi_translateCurrentException(0);
  }
  return 0;
}

```

## disassembly

```asm
0x1400080fc  mov     [rsp+arg_8], rbx
0x140008101  mov     [rsp+arg_10], rsi
0x140008106  push    rdi
0x140008107  sub     rsp, 20h
0x14000810b  mov     rsi, rdx
0x14000810e  cmp     byte ptr [rcx+70h], 0
0x140008112  jz      short loc_14000811B
0x140008114  call    cs:__imp_?__abi_WinRTraiseObjectDisposedException@@YAXXZ; __abi_WinRTraiseObjectDisposedException(void)
0x14000811a  int     3; Trap to Debugger
0x14000811b  xor     edi, edi
0x14000811d  mov     [rdx], rdi
0x140008120  mov     rbx, [rcx+60h]
0x140008124  test    rbx, rbx
0x140008127  jz      short loc_140008138
0x140008129  mov     rax, [rbx]
0x14000812c  mov     rcx, rbx
0x14000812f  mov     rax, [rax+8]
0x140008133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008138  mov     [rsp+28h+arg_0], rbx
0x14000813d  test    rbx, rbx
0x140008140  jz      short loc_140008152
0x140008142  mov     rax, [rbx]
0x140008145  mov     rcx, rbx
0x140008148  mov     rax, [rax+8]
0x14000814c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008151  nop
0x140008152  test    rbx, rbx
0x140008155  jz      short loc_140008166
0x140008157  mov     rax, [rbx]
0x14000815a  mov     rcx, rbx
0x14000815d  mov     rax, [rax+10h]
0x140008161  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008166  mov     [rsi], rbx
0x140008169  jmp     short loc_14000816F
0x14000816b  mov     edi, dword ptr [rsp+28h+arg_0]
0x14000816f  mov     eax, edi
0x140008171  mov     rbx, [rsp+28h+arg_8]
0x140008176  mov     rsi, [rsp+28h+arg_10]
0x14000817b  add     rsp, 20h
0x14000817f  pop     rdi
0x140008180  retn
```
