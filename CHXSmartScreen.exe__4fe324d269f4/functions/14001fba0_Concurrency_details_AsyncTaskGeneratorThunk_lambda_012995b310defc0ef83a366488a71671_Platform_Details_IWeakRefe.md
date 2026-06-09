# Concurrency::details::_AsyncTaskGeneratorThunk__lambda_012995b310defc0ef83a366488a71671___::[Platform::Details::IWeakReferenceSource]::__abi_Platform_Details_IWeakReferenceSource____abi_GetWeakReference

- ea: `0x14001fba0`
- end: `0x14001fc2b`
- name: `Concurrency::details::_AsyncTaskGeneratorThunk__lambda_012995b310defc0ef83a366488a71671___::[Platform::Details::IWeakReferenceSource]::__abi_Platform_Details_IWeakReferenceSource____abi_GetWeakReference`
- size: `139`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x14001fc40`
- `0x14001fc60`

## callees

- `0x14001fba0`
- `0x140035010`

## import_xrefs

- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x14001fbbb`
- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x14001fbbb`

## pseudocode

```c
__int64 __fastcall Concurrency::details::_AsyncTaskGeneratorThunk__lambda_012995b310defc0ef83a366488a71671___::_Platform::Details::IWeakReferenceSource_::__abi_Platform_Details_IWeakReferenceSource____abi_GetWeakReference(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v3; // rbx

  if ( *(_BYTE *)(a1 + 240) )
  {
    __abi_WinRTraiseObjectDisposedException();
    __debugbreak();
  }
  *a2 = 0;
  v3 = *(_QWORD *)(a1 + 176);
  if ( v3 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v3 + 8LL))(*(_QWORD *)(a1 + 176));
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  *a2 = v3;
  return 0;
}

```

## disassembly

```asm
0x14001fba0  mov     [rsp+arg_8], rbx
0x14001fba5  mov     [rsp+arg_10], rsi
0x14001fbaa  push    rdi
0x14001fbab  sub     rsp, 20h
0x14001fbaf  mov     rsi, rdx
0x14001fbb2  cmp     byte ptr [rcx+0F0h], 0
0x14001fbb9  jz      short loc_14001FBC2
0x14001fbbb  call    cs:__imp_?__abi_WinRTraiseObjectDisposedException@@YAXXZ; __abi_WinRTraiseObjectDisposedException(void)
0x14001fbc1  int     3; Trap to Debugger
0x14001fbc2  xor     edi, edi
0x14001fbc4  mov     [rdx], rdi
0x14001fbc7  mov     rbx, [rcx+0B0h]
0x14001fbce  test    rbx, rbx
0x14001fbd1  jz      short loc_14001FBE2
0x14001fbd3  mov     rax, [rbx]
0x14001fbd6  mov     rcx, rbx
0x14001fbd9  mov     rax, [rax+8]
0x14001fbdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001fbe2  mov     [rsp+28h+arg_0], rbx
0x14001fbe7  test    rbx, rbx
0x14001fbea  jz      short loc_14001FBFC
0x14001fbec  mov     rax, [rbx]
0x14001fbef  mov     rcx, rbx
0x14001fbf2  mov     rax, [rax+8]
0x14001fbf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001fbfb  nop
0x14001fbfc  test    rbx, rbx
0x14001fbff  jz      short loc_14001FC10
0x14001fc01  mov     rax, [rbx]
0x14001fc04  mov     rcx, rbx
0x14001fc07  mov     rax, [rax+10h]
0x14001fc0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001fc10  mov     [rsi], rbx
0x14001fc13  jmp     short loc_14001FC19
0x14001fc15  mov     edi, dword ptr [rsp+28h+arg_0]
0x14001fc19  mov     eax, edi
0x14001fc1b  mov     rbx, [rsp+28h+arg_8]
0x14001fc20  mov     rsi, [rsp+28h+arg_10]
0x14001fc25  add     rsp, 20h
0x14001fc29  pop     rdi
0x14001fc2a  retn
```
