# ?__abi_Platform_Details_IWeakReferenceSource____abi_GetWeakReference@?QIWeakReferenceSource@Details@Platform@@?$Array@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@3@UE$AAAJPEAPE$AAUIWeakReference@23@@Z

- ea: `0x14000e868`
- end: `0x14000e8f0`
- name: `?__abi_Platform_Details_IWeakReferenceSource____abi_GetWeakReference@?QIWeakReferenceSource@Details@Platform@@?$Array@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@3@UE$AAAJPEAPE$AAUIWeakReference@23@@Z`
- size: `136`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000e900`
- `0x14000e910`

## callees

- `0x14000e868`
- `0x140035010`

## import_xrefs

- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x14000e883`
- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x14000e883`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ___abi_Platform_Details_IWeakReferenceSource____abi_GetWeakReference__QIWeakReferenceSource_Details_Platform____Array_VXmlnsDefinition_Markup_Xaml_UI_Windows___00_3_UE_AAAJPEAPE_AAUIWeakReference_23__Z(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v3; // rbx

  if ( *(_BYTE *)(a1 + 128) )
  {
    __abi_WinRTraiseObjectDisposedException();
    __debugbreak();
  }
  try
  {
    *a2 = 0;
    v3 = *(_QWORD *)(a1 + 88);
    if ( v3 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v3 + 8LL))(*(_QWORD *)(a1 + 88));
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
0x14000e868  mov     [rsp+arg_8], rbx
0x14000e86d  mov     [rsp+arg_10], rsi
0x14000e872  push    rdi
0x14000e873  sub     rsp, 20h
0x14000e877  mov     rsi, rdx
0x14000e87a  cmp     byte ptr [rcx+80h], 0
0x14000e881  jz      short loc_14000E88A
0x14000e883  call    cs:__imp_?__abi_WinRTraiseObjectDisposedException@@YAXXZ; __abi_WinRTraiseObjectDisposedException(void)
0x14000e889  int     3; Trap to Debugger
0x14000e88a  xor     edi, edi
0x14000e88c  mov     [rdx], rdi
0x14000e88f  mov     rbx, [rcx+58h]
0x14000e893  test    rbx, rbx
0x14000e896  jz      short loc_14000E8A7
0x14000e898  mov     rax, [rbx]
0x14000e89b  mov     rcx, rbx
0x14000e89e  mov     rax, [rax+8]
0x14000e8a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e8a7  mov     [rsp+28h+arg_0], rbx
0x14000e8ac  test    rbx, rbx
0x14000e8af  jz      short loc_14000E8C1
0x14000e8b1  mov     rax, [rbx]
0x14000e8b4  mov     rcx, rbx
0x14000e8b7  mov     rax, [rax+8]
0x14000e8bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e8c0  nop
0x14000e8c1  test    rbx, rbx
0x14000e8c4  jz      short loc_14000E8D5
0x14000e8c6  mov     rax, [rbx]
0x14000e8c9  mov     rcx, rbx
0x14000e8cc  mov     rax, [rax+10h]
0x14000e8d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e8d5  mov     [rsi], rbx
0x14000e8d8  jmp     short loc_14000E8DE
0x14000e8da  mov     edi, dword ptr [rsp+28h+arg_0]
0x14000e8de  mov     eax, edi
0x14000e8e0  mov     rbx, [rsp+28h+arg_8]
0x14000e8e5  mov     rsi, [rsp+28h+arg_10]
0x14000e8ea  add     rsp, 20h
0x14000e8ee  pop     rdi
0x14000e8ef  retn
```
