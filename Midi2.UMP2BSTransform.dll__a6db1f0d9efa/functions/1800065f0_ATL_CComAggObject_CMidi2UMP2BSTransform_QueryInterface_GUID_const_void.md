# ATL::CComAggObject<CMidi2UMP2BSTransform>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800065f0`
- end: `0x180006653`
- name: `?QueryInterface@?$CComAggObject@VCMidi2UMP2BSTransform@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180005c20`
- `0x1800065f0`
- `0x18000f010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CMidi2UMP2BSTransform>::QueryInterface(char *a1, __int64 a2, char **a3)
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
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CMidi2UMP2BSTransform::_GetEntries'::`2'::_entries,
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
0x1800065f0  push    rbx
0x1800065f2  sub     rsp, 20h
0x1800065f6  xor     ebx, ebx
0x1800065f8  test    r8, r8
0x1800065fb  jnz     short loc_180006604
0x1800065fd  mov     eax, 80004003h
0x180006602  jmp     short loc_18000664D
0x180006604  mov     [r8], rbx
0x180006607  cmp     [rdx], ebx
0x180006609  jnz     short loc_180006633
0x18000660b  cmp     [rdx+4], ebx
0x18000660e  jnz     short loc_180006633
0x180006610  cmp     dword ptr [rdx+8], 0C0h
0x180006617  jnz     short loc_180006633
0x180006619  cmp     dword ptr [rdx+0Ch], 46000000h
0x180006620  jnz     short loc_180006633
0x180006622  mov     [r8], rcx
0x180006625  mov     rax, [rcx]
0x180006628  mov     rax, [rax+8]
0x18000662c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006631  jmp     short loc_18000664B
0x180006633  mov     r9, r8; void **
0x180006636  add     rcx, 18h; void *
0x18000663a  mov     r8, rdx; struct _GUID *
0x18000663d  lea     rdx, ?_entries@?1??_GetEntries@CMidi2UMP2BSTransform@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180006644  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180006649  mov     ebx, eax
0x18000664b  mov     eax, ebx
0x18000664d  add     rsp, 20h
0x180006651  pop     rbx
0x180006652  retn
```
