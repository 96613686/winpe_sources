# ATL::CComAggObject<CDsmControl>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000af50`
- end: `0x18000afb3`
- name: `?QueryInterface@?$CComAggObject@VCDsmControl@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `99`
- prototype: `__int64 __fastcall(char *, __int64, char **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800098f0`
- `0x18000af50`
- `0x18000f010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CDsmControl>::QueryInterface(char *a1, __int64 a2, char **a3)
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
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CDsmControl::_GetEntries'::`2'::_entries,
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
0x18000af50  push    rbx
0x18000af52  sub     rsp, 20h
0x18000af56  xor     ebx, ebx
0x18000af58  test    r8, r8
0x18000af5b  jnz     short loc_18000AF64
0x18000af5d  mov     eax, 80004003h
0x18000af62  jmp     short loc_18000AFAD
0x18000af64  mov     [r8], rbx
0x18000af67  cmp     [rdx], ebx
0x18000af69  jnz     short loc_18000AF93
0x18000af6b  cmp     [rdx+4], ebx
0x18000af6e  jnz     short loc_18000AF93
0x18000af70  cmp     dword ptr [rdx+8], 0C0h
0x18000af77  jnz     short loc_18000AF93
0x18000af79  cmp     dword ptr [rdx+0Ch], 46000000h
0x18000af80  jnz     short loc_18000AF93
0x18000af82  mov     [r8], rcx
0x18000af85  mov     rax, [rcx]
0x18000af88  mov     rax, [rax+8]
0x18000af8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af91  jmp     short loc_18000AFAB
0x18000af93  mov     r9, r8; void **
0x18000af96  add     rcx, 10h; void *
0x18000af9a  mov     r8, rdx; struct _GUID *
0x18000af9d  lea     rdx, ?_entries@?1??_GetEntries@CDsmControl@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000afa4  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x18000afa9  mov     ebx, eax
0x18000afab  mov     eax, ebx
0x18000afad  add     rsp, 20h
0x18000afb1  pop     rbx
0x18000afb2  retn
```
