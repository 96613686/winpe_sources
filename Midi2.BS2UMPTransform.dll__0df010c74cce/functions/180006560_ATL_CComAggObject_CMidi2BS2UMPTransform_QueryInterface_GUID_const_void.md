# ATL::CComAggObject<CMidi2BS2UMPTransform>::QueryInterface(_GUID const &,void * *)

- ea: `0x180006560`
- end: `0x1800065c3`
- name: `?QueryInterface@?$CComAggObject@VCMidi2BS2UMPTransform@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180005b90`
- `0x180006560`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CMidi2BS2UMPTransform>::QueryInterface(char *a1, __int64 a2, char **a3)
{
  unsigned int v3; // ebx

  v3 = 0;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  if ( *(_DWORD *)a2 || *(_DWORD *)(a2 + 4) || *(_DWORD *)(a2 + 8) != 192 || *(_DWORD *)(a2 + 12) != 1174405120 )
  {
    return (unsigned int)ATL::CComObjectRootBase::InternalQueryInterface(
                           a1 + 24,
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CMidi2BS2UMPTransform::_GetEntries'::`2'::_entries,
                           (const struct _GUID *)a2,
                           a3);
  }
  else
  {
    *a3 = a1;
    (*(void (__fastcall **)(char *))(*(_QWORD *)a1 + 8LL))(a1);
  }
  return v3;
}

```

## disassembly

```asm
0x180006560  push    rbx
0x180006562  sub     rsp, 20h
0x180006566  xor     ebx, ebx
0x180006568  test    r8, r8
0x18000656b  jnz     short loc_180006574
0x18000656d  mov     eax, 80004003h
0x180006572  jmp     short loc_1800065BD
0x180006574  mov     [r8], rbx
0x180006577  cmp     [rdx], ebx
0x180006579  jnz     short loc_1800065A3
0x18000657b  cmp     [rdx+4], ebx
0x18000657e  jnz     short loc_1800065A3
0x180006580  cmp     dword ptr [rdx+8], 0C0h
0x180006587  jnz     short loc_1800065A3
0x180006589  cmp     dword ptr [rdx+0Ch], 46000000h
0x180006590  jnz     short loc_1800065A3
0x180006592  mov     [r8], rcx
0x180006595  mov     rax, [rcx]
0x180006598  mov     rax, [rax+8]
0x18000659c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065a1  jmp     short loc_1800065BB
0x1800065a3  mov     r9, r8; void **
0x1800065a6  add     rcx, 18h; void *
0x1800065aa  mov     r8, rdx; struct _GUID *
0x1800065ad  lea     rdx, ?_entries@?1??_GetEntries@CMidi2BS2UMPTransform@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x1800065b4  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x1800065b9  mov     ebx, eax
0x1800065bb  mov     eax, ebx
0x1800065bd  add     rsp, 20h
0x1800065c1  pop     rbx
0x1800065c2  retn
```
