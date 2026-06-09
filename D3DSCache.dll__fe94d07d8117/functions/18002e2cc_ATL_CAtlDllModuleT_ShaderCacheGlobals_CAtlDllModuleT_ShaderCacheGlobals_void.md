# ATL::CAtlDllModuleT<ShaderCacheGlobals>::~CAtlDllModuleT<ShaderCacheGlobals>(void)

- ea: `0x18002e2cc`
- end: `0x18002e365`
- name: `??1?$CAtlDllModuleT@VShaderCacheGlobals@@@ATL@@UEAA@XZ`
- size: `153`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180041b08`

## callees

- `0x18002e2cc`
- `0x180046c00`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002e34e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002e34e`

## pseudocode

```c
void __fastcall ATL::CAtlDllModuleT<ShaderCacheGlobals>::~CAtlDllModuleT<ShaderCacheGlobals>(__int64 a1)
{
  struct ATL::_ATL_OBJMAP_ENTRY30 **v2; // rdi
  __int64 *v3; // rax
  unsigned __int64 v4; // rdi
  __int64 v5; // rcx

  v2 = off_1800C66B0;
  v3 = off_1800C66B8;
  while ( v2 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v3 )
  {
    if ( *v2 )
    {
      (*((void (__fastcall **)(_QWORD))*v2 + 8))(0);
      v3 = off_1800C66B8;
    }
    ++v2;
  }
  v4 = a1 + 8;
  if ( *(_DWORD *)(a1 + 8) )
  {
    if ( *(_QWORD *)(a1 + 16) )
    {
      ATL::AtlCallTermFunc((struct ATL::_ATL_MODULE70 *)(v4 & -(__int64)(a1 != 0)));
      *(_QWORD *)(a1 + 16) = 0;
    }
    v5 = *(_QWORD *)(a1 + 64);
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
    *(_DWORD *)v4 = 0;
  }
}

```

## disassembly

```asm
0x18002e2cc  mov     [rsp+arg_0], rbx
0x18002e2d1  push    rdi
0x18002e2d2  sub     rsp, 20h
0x18002e2d6  mov     rbx, rcx
0x18002e2d9  mov     rdi, cs:off_1800C66B0
0x18002e2e0  mov     rax, cs:off_1800C66B8
0x18002e2e7  jmp     short loc_18002E307
0x18002e2e9  mov     rdx, [rdi]
0x18002e2ec  test    rdx, rdx
0x18002e2ef  jz      short loc_18002E303
0x18002e2f1  xor     ecx, ecx
0x18002e2f3  mov     rax, [rdx+40h]
0x18002e2f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e2fc  mov     rax, cs:off_1800C66B8
0x18002e303  add     rdi, 8
0x18002e307  cmp     rdi, rax
0x18002e30a  jb      short loc_18002E2E9
0x18002e30c  lea     rdi, [rbx+8]
0x18002e310  cmp     dword ptr [rdi], 0
0x18002e313  jz      short loc_18002E35A
0x18002e315  cmp     qword ptr [rbx+10h], 0
0x18002e31a  jz      short loc_18002E335
0x18002e31c  mov     rax, rbx
0x18002e31f  neg     rax
0x18002e322  sbb     rcx, rcx
0x18002e325  and     rcx, rdi; struct ATL::_ATL_MODULE70 *
0x18002e328  call    ?AtlCallTermFunc@ATL@@YAXPEAU_ATL_MODULE70@1@@Z; ATL::AtlCallTermFunc(ATL::_ATL_MODULE70 *)
0x18002e32d  mov     qword ptr [rbx+10h], 0
0x18002e335  mov     rcx, [rbx+40h]
0x18002e339  test    rcx, rcx
0x18002e33c  jz      short loc_18002E34A
0x18002e33e  mov     rax, [rcx]
0x18002e341  mov     rax, [rax+10h]
0x18002e345  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e34a  lea     rcx, [rbx+18h]; lpCriticalSection
0x18002e34e  call    cs:__imp_DeleteCriticalSection
0x18002e354  mov     dword ptr [rdi], 0
0x18002e35a  mov     rbx, [rsp+28h+arg_0]
0x18002e35f  add     rsp, 20h
0x18002e363  pop     rdi
0x18002e364  retn
```
