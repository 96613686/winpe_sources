# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x180001ff8`
- end: `0x18000205e`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `102`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001fd4`

## callees

- `0x180001ff8`
- `0x18000b3b0`
- `0x18000c010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180002047`
- `KERNEL32!DeleteCriticalSection` at `0x180002047`

## pseudocode

```c
void __fastcall ATL::CAtlModule::~CAtlModule(ATL::CAtlModule *this)
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
0x180001ff8  mov     [rsp+arg_0], rbx
0x180001ffd  push    rdi
0x180001ffe  sub     rsp, 20h
0x180002002  mov     rbx, rcx
0x180002005  lea     rdi, [rcx+8]
0x180002009  cmp     dword ptr [rdi], 0
0x18000200c  jz      short loc_180002053
0x18000200e  cmp     qword ptr [rcx+10h], 0
0x180002013  jz      short loc_18000202E
0x180002015  mov     rax, rcx
0x180002018  neg     rax
0x18000201b  sbb     rcx, rcx
0x18000201e  and     rcx, rdi; struct ATL::_ATL_MODULE70 *
0x180002021  call    ?AtlCallTermFunc@ATL@@YAXPEAU_ATL_MODULE70@1@@Z; ATL::AtlCallTermFunc(ATL::_ATL_MODULE70 *)
0x180002026  mov     qword ptr [rbx+10h], 0
0x18000202e  mov     rcx, [rbx+40h]
0x180002032  test    rcx, rcx
0x180002035  jz      short loc_180002043
0x180002037  mov     rax, [rcx]
0x18000203a  mov     rax, [rax+10h]
0x18000203e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002043  lea     rcx, [rbx+18h]; lpCriticalSection
0x180002047  call    cs:__imp_DeleteCriticalSection
0x18000204d  mov     dword ptr [rdi], 0
0x180002053  mov     rbx, [rsp+28h+arg_0]
0x180002058  add     rsp, 20h
0x18000205c  pop     rdi
0x18000205d  retn
```
