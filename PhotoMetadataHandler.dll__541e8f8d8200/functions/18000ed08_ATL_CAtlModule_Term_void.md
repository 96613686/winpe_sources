# ATL::CAtlModule::Term(void)

- ea: `0x18000ed08`
- end: `0x18000ed72`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `106`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ec78`
- `0x180017730`
- `0x180027200`

## callees

- `0x18000ed08`
- `0x180018174`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ed32`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ed32`

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
0x18000ed08  mov     [rsp+arg_0], rbx
0x18000ed0d  push    rdi
0x18000ed0e  sub     rsp, 20h
0x18000ed12  mov     rbx, rcx
0x18000ed15  lea     rdi, [rcx+8]
0x18000ed19  cmp     dword ptr [rdi], 0
0x18000ed1c  jz      short loc_18000ED3E
0x18000ed1e  cmp     qword ptr [rcx+10h], 0
0x18000ed23  jnz     short loc_18000ED49
0x18000ed25  mov     rcx, [rbx+40h]
0x18000ed29  test    rcx, rcx
0x18000ed2c  jnz     short loc_18000ED64
0x18000ed2e  lea     rcx, [rbx+18h]; lpCriticalSection
0x18000ed32  call    cs:__imp_DeleteCriticalSection
0x18000ed38  mov     dword ptr [rdi], 0
0x18000ed3e  mov     rbx, [rsp+28h+arg_0]
0x18000ed43  add     rsp, 20h
0x18000ed47  pop     rdi
0x18000ed48  retn
0x18000ed49  mov     rax, rbx
0x18000ed4c  neg     rax
0x18000ed4f  sbb     rcx, rcx
0x18000ed52  and     rcx, rdi; struct ATL::_ATL_MODULE70 *
0x18000ed55  call    ?AtlCallTermFunc@ATL@@YAXPEAU_ATL_MODULE70@1@@Z; ATL::AtlCallTermFunc(ATL::_ATL_MODULE70 *)
0x18000ed5a  mov     qword ptr [rbx+10h], 0
0x18000ed62  jmp     short loc_18000ED25
0x18000ed64  mov     rax, [rcx]
0x18000ed67  mov     rax, [rax+10h]
0x18000ed6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed70  jmp     short loc_18000ED2E
```
