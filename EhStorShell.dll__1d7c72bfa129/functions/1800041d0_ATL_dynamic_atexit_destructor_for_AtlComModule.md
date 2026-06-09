# ATL::_dynamic_atexit_destructor_for___AtlComModule__

- ea: `0x1800041d0`
- end: `0x180004255`
- name: `ATL::_dynamic_atexit_destructor_for___AtlComModule__`
- size: `133`
- prototype: `void()`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180002380`
- `0x1800041d0`
- `0x18000c010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000422f`
- `KERNEL32!DeleteCriticalSection` at `0x18000422f`

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
    v0 = (__int64 *)qword_180012950;
    v1 = qword_180012958;
    while ( (unsigned __int64)v0 < v1 )
    {
      v2 = *v0;
      if ( *v0 )
      {
        v3 = *(_QWORD *)(v2 + 32);
        if ( v3 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
        *(_QWORD *)(v2 + 32) = 0;
        v1 = qword_180012958;
      }
      ++v0;
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)&stru_180012960);
    ATL::_AtlComModule = 0;
  }
}

```

## disassembly

```asm
0x1800041d0  mov     [rsp+arg_0], rbx
0x1800041d5  push    rdi
0x1800041d6  sub     rsp, 20h
0x1800041da  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x1800041e1  jz      short loc_18000423F
0x1800041e3  mov     rbx, cs:qword_180012950
0x1800041ea  mov     rax, cs:qword_180012958
0x1800041f1  jmp     short loc_180004223
0x1800041f3  mov     rdi, [rbx]
0x1800041f6  test    rdi, rdi
0x1800041f9  jz      short loc_18000421F
0x1800041fb  mov     rcx, [rdi+20h]
0x1800041ff  test    rcx, rcx
0x180004202  jz      short loc_180004210
0x180004204  mov     rax, [rcx]
0x180004207  mov     rax, [rax+10h]
0x18000420b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004210  mov     qword ptr [rdi+20h], 0
0x180004218  mov     rax, cs:qword_180012958
0x18000421f  add     rbx, 8
0x180004223  cmp     rbx, rax
0x180004226  jb      short loc_1800041F3
0x180004228  lea     rcx, stru_180012960; lpCriticalSection
0x18000422f  call    cs:__imp_DeleteCriticalSection
0x180004235  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x18000423f  lea     rcx, ?_AtlComModule@ATL@@3VCAtlComModule@1@A; ATL::CAtlComModule ATL::_AtlComModule
0x180004246  mov     rbx, [rsp+28h+arg_0]
0x18000424b  add     rsp, 20h
0x18000424f  pop     rdi
0x180004250  jmp     _guard_check_icall_nop
```
