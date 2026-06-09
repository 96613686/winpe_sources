# ATL::_dynamic_atexit_destructor_for___AtlComModule__

- ea: `0x18000e420`
- end: `0x18000e4a5`
- name: `ATL::_dynamic_atexit_destructor_for___AtlComModule__`
- size: `133`
- prototype: `void()`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000e420`
- `0x18000e4b0`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e47f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e47f`

## pseudocode

```c
void ATL::_dynamic_atexit_destructor_for___AtlComModule__()
{
  __int64 *v0; // rbx
  unsigned __int64 v1; // rax
  __int64 v2; // rdi
  __int64 v3; // rcx

  if ( ATL::_AtlComModule )
  {
    v0 = (__int64 *)qword_180026AD0;
    v1 = qword_180026AD8;
    while ( (unsigned __int64)v0 < v1 )
    {
      v2 = *v0;
      if ( *v0 )
      {
        v3 = *(_QWORD *)(v2 + 32);
        if ( v3 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
        *(_QWORD *)(v2 + 32) = 0;
        v1 = qword_180026AD8;
      }
      ++v0;
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)&CriticalSection);
    ATL::_AtlComModule = 0;
  }
}

```

## disassembly

```asm
0x18000e420  mov     [rsp+arg_0], rbx
0x18000e425  push    rdi
0x18000e426  sub     rsp, 20h
0x18000e42a  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x18000e431  jz      short loc_18000E48F
0x18000e433  mov     rbx, cs:qword_180026AD0
0x18000e43a  mov     rax, cs:qword_180026AD8
0x18000e441  cmp     rbx, rax
0x18000e444  jnb     short loc_18000E478
0x18000e446  mov     rdi, [rbx]
0x18000e449  test    rdi, rdi
0x18000e44c  jz      short loc_18000E472
0x18000e44e  mov     rcx, [rdi+20h]
0x18000e452  test    rcx, rcx
0x18000e455  jz      short loc_18000E463
0x18000e457  mov     rax, [rcx]
0x18000e45a  mov     rax, [rax+10h]
0x18000e45e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e463  mov     qword ptr [rdi+20h], 0
0x18000e46b  mov     rax, cs:qword_180026AD8
0x18000e472  add     rbx, 8
0x18000e476  jmp     short loc_18000E441
0x18000e478  lea     rcx, CriticalSection; lpCriticalSection
0x18000e47f  call    cs:__imp_DeleteCriticalSection
0x18000e485  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x18000e48f  lea     rcx, ?_AtlComModule@ATL@@3VCAtlComModule@1@A; ATL::CAtlComModule ATL::_AtlComModule
0x18000e496  mov     rbx, [rsp+28h+arg_0]
0x18000e49b  add     rsp, 20h
0x18000e49f  pop     rdi
0x18000e4a0  jmp     _guard_check_icall_nop
```
