# ATL::CComObject<CMigrationPlugin>::Release(void)

- ea: `0x180011f30`
- end: `0x180011fb1`
- name: `?Release@?$CComObject@VCMigrationPlugin@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011fc0`
- `0x180011fd0`
- `0x180011fe0`
- `0x180011ff0`
- `0x180012000`

## callees

- `0x180011f30`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMigrationPlugin>::Release(volatile signed __int32 *a1)
{
  signed __int32 i; // r8d
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)a1 + 12);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange(a1 + 12, i - 1, i);
        i = *((_DWORD *)a1 + 12) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 80LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180011f30  mov     [rsp+arg_0], rbx
0x180011f35  push    rdi
0x180011f36  sub     rsp, 20h
0x180011f3a  mov     r8d, [rcx+30h]
0x180011f3e  mov     rbx, rcx
0x180011f41  mov     ecx, 7FFFFFFFh
0x180011f46  jmp     short loc_180011F5A
0x180011f48  lea     edx, [r8-1]
0x180011f4c  mov     eax, r8d
0x180011f4f  lock cmpxchg [rbx+30h], edx
0x180011f54  jz      short loc_180011F5F
0x180011f56  mov     r8d, [rbx+30h]
0x180011f5a  cmp     r8d, ecx
0x180011f5d  jnz     short loc_180011F48
0x180011f5f  lea     edi, [r8-1]
0x180011f63  test    edi, edi
0x180011f65  jnz     short loc_180011FA4
0x180011f67  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180011f6e  mov     rax, [rcx]
0x180011f71  mov     rax, [rax+8]
0x180011f75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f7a  test    rbx, rbx
0x180011f7d  jz      short loc_180011F91
0x180011f7f  mov     rax, [rbx]
0x180011f82  lea     edx, [rdi+1]
0x180011f85  mov     rcx, rbx
0x180011f88  mov     rax, [rax+50h]
0x180011f8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f91  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180011f98  mov     rdx, [rcx]
0x180011f9b  mov     rax, [rdx+10h]
0x180011f9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011fa4  mov     rbx, [rsp+28h+arg_0]
0x180011fa9  mov     eax, edi
0x180011fab  add     rsp, 20h
0x180011faf  pop     rdi
0x180011fb0  retn
```
