# ATL::CAtlModule::Term(void)

- ea: `0x18000f408`
- end: `0x18000f479`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `113`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f378`
- `0x1800181f0`
- `0x1800284d0`

## callees

- `0x18000f408`
- `0x180018bb4`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f432`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f432`

## pseudocode

```c
void __fastcall ATL::CAtlModule::Term(ATL::CAtlModule *this)
{
  unsigned __int64 v2; // rdi
  __int64 v3; // rcx

  v2 = (unsigned __int64)this + 8;
  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 2) )
    {
      ATL::AtlCallTermFunc((struct ATL::_ATL_MODULE70 *)(v2 & -(__int64)(this != 0)));
      *((_QWORD *)this + 2) = 0;
    }
    v3 = *((_QWORD *)this + 8);
    if ( v3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    *(_DWORD *)v2 = 0;
  }
}

```

## disassembly

```asm
0x18000f408  mov     [rsp+arg_0], rbx
0x18000f40d  push    rdi
0x18000f40e  sub     rsp, 20h
0x18000f412  mov     rbx, rcx
0x18000f415  lea     rdi, [rcx+8]
0x18000f419  cmp     dword ptr [rdi], 0
0x18000f41c  jz      short loc_18000F444
0x18000f41e  cmp     qword ptr [rcx+10h], 0
0x18000f423  jnz     short loc_18000F450
0x18000f425  mov     rcx, [rbx+40h]
0x18000f429  test    rcx, rcx
0x18000f42c  jnz     short loc_18000F46B
0x18000f42e  lea     rcx, [rbx+18h]; lpCriticalSection
0x18000f432  call    cs:__imp_DeleteCriticalSection
0x18000f439  nop     dword ptr [rax+rax+00h]
0x18000f43e  mov     dword ptr [rdi], 0
0x18000f444  mov     rbx, [rsp+28h+arg_0]
0x18000f449  add     rsp, 20h
0x18000f44d  pop     rdi
0x18000f44e  retn
0x18000f450  mov     rax, rbx
0x18000f453  neg     rax
0x18000f456  sbb     rcx, rcx
0x18000f459  and     rcx, rdi; struct ATL::_ATL_MODULE70 *
0x18000f45c  call    ?AtlCallTermFunc@ATL@@YAXPEAU_ATL_MODULE70@1@@Z; ATL::AtlCallTermFunc(ATL::_ATL_MODULE70 *)
0x18000f461  mov     qword ptr [rbx+10h], 0
0x18000f469  jmp     short loc_18000F425
0x18000f46b  mov     rax, [rcx]
0x18000f46e  mov     rax, [rax+10h]
0x18000f472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f477  jmp     short loc_18000F42E
```
