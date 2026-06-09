# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x1800467c4`
- end: `0x180046834`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180046798`

## callees

- `0x1800467c4`
- `0x180056b28`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004681d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004681d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x1800467c4  push    rdi
0x1800467c6  sub     rsp, 30h
0x1800467ca  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800467d3  mov     [rsp+38h+arg_0], rbx
0x1800467d8  mov     rbx, rcx
0x1800467db  lea     rdi, [rcx+8]
0x1800467df  cmp     dword ptr [rdi], 0
0x1800467e2  jz      short loc_180046829
0x1800467e4  cmp     qword ptr [rcx+10h], 0
0x1800467e9  jz      short loc_180046804
0x1800467eb  mov     rax, rcx
0x1800467ee  neg     rax
0x1800467f1  sbb     rcx, rcx
0x1800467f4  and     rcx, rdi; struct ATL::_ATL_MODULE70 *
0x1800467f7  call    ?AtlCallTermFunc@ATL@@YAXPEAU_ATL_MODULE70@1@@Z; ATL::AtlCallTermFunc(ATL::_ATL_MODULE70 *)
0x1800467fc  mov     qword ptr [rbx+10h], 0
0x180046804  mov     rcx, [rbx+40h]
0x180046808  test    rcx, rcx
0x18004680b  jz      short loc_180046819
0x18004680d  mov     rax, [rcx]
0x180046810  mov     rax, [rax+10h]
0x180046814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046819  lea     rcx, [rbx+18h]; lpCriticalSection
0x18004681d  call    cs:__imp_DeleteCriticalSection
0x180046823  mov     dword ptr [rdi], 0
0x180046829  mov     rbx, [rsp+38h+arg_0]
0x18004682e  add     rsp, 30h
0x180046832  pop     rdi
0x180046833  retn
```
