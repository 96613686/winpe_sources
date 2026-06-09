# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x1800080a4`
- end: `0x18000810f`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `107`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180008010`
- `0x180008080`

## callees

- `0x1800080a4`
- `0x180010cb0`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800080ce`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800080ce`

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
0x1800080a4  mov     [rsp+arg_0], rbx
0x1800080a9  push    rdi
0x1800080aa  sub     rsp, 20h
0x1800080ae  mov     rbx, rcx
0x1800080b1  lea     rdi, [rcx+8]
0x1800080b5  cmp     dword ptr [rdi], 0
0x1800080b8  jz      short loc_1800080DA
0x1800080ba  cmp     qword ptr [rcx+10h], 0
0x1800080bf  jnz     short loc_1800080E5
0x1800080c1  mov     rcx, [rbx+40h]
0x1800080c5  test    rcx, rcx
0x1800080c8  jnz     short loc_180008100
0x1800080ca  lea     rcx, [rbx+18h]; lpCriticalSection
0x1800080ce  call    cs:__imp_DeleteCriticalSection
0x1800080d4  mov     dword ptr [rdi], 0
0x1800080da  mov     rbx, [rsp+28h+arg_0]
0x1800080df  add     rsp, 20h
0x1800080e3  pop     rdi
0x1800080e4  retn
0x1800080e5  mov     rax, rbx
0x1800080e8  neg     rax
0x1800080eb  sbb     rcx, rcx
0x1800080ee  and     rcx, rdi; struct ATL::_ATL_MODULE70 *
0x1800080f1  call    ?AtlCallTermFunc@ATL@@YAXPEAU_ATL_MODULE70@1@@Z; ATL::AtlCallTermFunc(ATL::_ATL_MODULE70 *)
0x1800080f6  mov     qword ptr [rbx+10h], 0
0x1800080fe  jmp     short loc_1800080C1
0x180008100  mov     rax, [rcx]
0x180008103  mov     rax, [rax+10h]
0x180008107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000810c  jmp     short loc_1800080CA
```
