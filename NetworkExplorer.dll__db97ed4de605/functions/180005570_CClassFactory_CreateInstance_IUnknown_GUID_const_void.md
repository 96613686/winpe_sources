# CClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180005570`
- end: `0x18000567c`
- name: `?CreateInstance@CClassFactory@@EEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `268`
- prototype: `__int64 __fastcall(CClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180005570`
- `0x180005690`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800055b1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800055b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000559d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000559d`

## pseudocode

```c
__int64 __fastcall CClassFactory::CreateInstance(
        CClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  HANDLE ProcessHeap; // rax
  _OWORD *v7; // rdi
  int v8; // ebp
  __int64 v10; // [rsp+38h] [rbp+10h] BYREF

  *a4 = 0;
  if ( a2 )
    return 2147746064LL;
  v10 = 0;
  ProcessHeap = GetProcessHeap();
  v7 = HeapAlloc(ProcessHeap, 8u, 0x88u);
  if ( v7 )
  {
    *v7 = 0;
    v7[1] = 0;
    v7[2] = 0;
    v7[3] = 0;
    v7[4] = 0;
    v7[5] = 0;
    v7[6] = 0;
    v7[7] = 0;
    *((_QWORD *)v7 + 16) = 0;
    CNetworkExplorerFolder::CNetworkExplorerFolder((CNetworkExplorerFolder *)v7);
    v8 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))v7)(
           v7,
           &GUID_00000000_0000_0000_c000_000000000046,
           &v10);
    (*(void (__fastcall **)(_OWORD *))(*(_QWORD *)v7 + 16LL))(v7);
    if ( v8 >= 0 )
    {
      v8 = (**(__int64 (__fastcall ***)(__int64, const struct _GUID *, void **))v10)(v10, a3, a4);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180005570  mov     [rsp+arg_18], rbx
0x180005575  push    rsi
0x180005576  sub     rsp, 20h
0x18000557a  xor     eax, eax
0x18000557c  mov     rbx, r9
0x18000557f  mov     [r9], rax
0x180005582  mov     rsi, r8
0x180005585  test    rdx, rdx
0x180005588  jnz     loc_180005665
0x18000558e  mov     [rsp+28h+arg_0], rbp
0x180005593  mov     [rsp+28h+arg_10], rdi
0x180005598  mov     [rsp+28h+arg_8], rax
0x18000559d  call    cs:__imp_GetProcessHeap
0x1800055a3  mov     edx, 8; dwFlags
0x1800055a8  mov     r8d, 88h; dwBytes
0x1800055ae  mov     rcx, rax; hHeap
0x1800055b1  call    cs:__imp_HeapAlloc
0x1800055b7  mov     rdi, rax
0x1800055ba  test    rax, rax
0x1800055bd  jz      loc_180005675
0x1800055c3  xorps   xmm0, xmm0
0x1800055c6  xor     eax, eax
0x1800055c8  movups  xmmword ptr [rdi], xmm0
0x1800055cb  mov     rcx, rdi; this
0x1800055ce  movups  xmmword ptr [rdi+10h], xmm0
0x1800055d2  movups  xmmword ptr [rdi+20h], xmm0
0x1800055d6  movups  xmmword ptr [rdi+30h], xmm0
0x1800055da  movups  xmmword ptr [rdi+40h], xmm0
0x1800055de  movups  xmmword ptr [rdi+50h], xmm0
0x1800055e2  movups  xmmword ptr [rdi+60h], xmm0
0x1800055e6  movups  xmmword ptr [rdi+70h], xmm0
0x1800055ea  mov     [rdi+80h], rax
0x1800055f1  call    ??0CNetworkExplorerFolder@@QEAA@XZ; CNetworkExplorerFolder::CNetworkExplorerFolder(void)
0x1800055f6  mov     r9, [rdi]
0x1800055f9  lea     r8, [rsp+28h+arg_8]
0x1800055fe  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180005605  mov     rcx, rdi
0x180005608  mov     rax, [r9]
0x18000560b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005610  mov     ebp, eax
0x180005612  mov     rcx, rdi
0x180005615  mov     rax, [rdi]
0x180005618  mov     rax, [rax+10h]
0x18000561c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005621  test    ebp, ebp
0x180005623  js      short loc_18000564E
0x180005625  mov     rcx, [rsp+28h+arg_8]
0x18000562a  mov     r8, rbx
0x18000562d  mov     rdx, rsi
0x180005630  mov     rax, [rcx]
0x180005633  mov     rax, [rax]
0x180005636  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000563b  mov     rcx, [rsp+28h+arg_8]
0x180005640  mov     ebp, eax
0x180005642  mov     rdx, [rcx]
0x180005645  mov     rax, [rdx+10h]
0x180005649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000564e  mov     rdi, [rsp+28h+arg_10]
0x180005653  mov     eax, ebp
0x180005655  mov     rbp, [rsp+28h+arg_0]
0x18000565a  mov     rbx, [rsp+28h+arg_18]
0x18000565f  add     rsp, 20h
0x180005663  pop     rsi
0x180005664  retn
0x180005665  mov     rbx, [rsp+28h+arg_18]
0x18000566a  mov     eax, 80040110h
0x18000566f  add     rsp, 20h
0x180005673  pop     rsi
0x180005674  retn
0x180005675  mov     ebp, 8007000Eh
0x18000567a  jmp     short loc_18000564E
```
