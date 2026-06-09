# ATL::CComAggObject<CRemMdmObj>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800056e0`
- end: `0x180005743`
- name: `?QueryInterface@?$CComAggObject@VCRemMdmObj@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180005588`
- `0x1800056e0`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CRemMdmObj>::QueryInterface(char *a1, __int64 a2, char **a3)
{
  unsigned int v3; // ebx

  v3 = 0;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  if ( *(_DWORD *)a2 || *(_DWORD *)(a2 + 4) || *(_DWORD *)(a2 + 8) != 192 || *(_DWORD *)(a2 + 12) != 1174405120 )
  {
    return (unsigned int)ATL::CComObjectRootBase::InternalQueryInterface(
                           a1 + 16,
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CRemMdmObj::_GetEntries'::`2'::_entries,
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
0x1800056e0  push    rbx
0x1800056e2  sub     rsp, 20h
0x1800056e6  xor     ebx, ebx
0x1800056e8  test    r8, r8
0x1800056eb  jnz     short loc_1800056F4
0x1800056ed  mov     eax, 80004003h
0x1800056f2  jmp     short loc_18000573D
0x1800056f4  mov     [r8], rbx
0x1800056f7  cmp     [rdx], ebx
0x1800056f9  jnz     short loc_180005723
0x1800056fb  cmp     [rdx+4], ebx
0x1800056fe  jnz     short loc_180005723
0x180005700  cmp     dword ptr [rdx+8], 0C0h
0x180005707  jnz     short loc_180005723
0x180005709  cmp     dword ptr [rdx+0Ch], 46000000h
0x180005710  jnz     short loc_180005723
0x180005712  mov     [r8], rcx
0x180005715  mov     rax, [rcx]
0x180005718  mov     rax, [rax+8]
0x18000571c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005721  jmp     short loc_18000573B
0x180005723  mov     r9, r8; void **
0x180005726  add     rcx, 10h; void *
0x18000572a  mov     r8, rdx; struct _GUID *
0x18000572d  lea     rdx, ?_entries@?1??_GetEntries@CRemMdmObj@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180005734  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180005739  mov     ebx, eax
0x18000573b  mov     eax, ebx
0x18000573d  add     rsp, 20h
0x180005741  pop     rbx
0x180005742  retn
```
