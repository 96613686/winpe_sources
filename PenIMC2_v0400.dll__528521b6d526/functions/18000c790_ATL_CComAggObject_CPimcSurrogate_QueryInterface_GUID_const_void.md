# ATL::CComAggObject<CPimcSurrogate>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000c790`
- end: `0x18000c7f4`
- name: `?QueryInterface@?$CComAggObject@VCPimcSurrogate@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000c4f0`

## callees

- `0x18000323c`
- `0x18000c790`
- `0x18000e4a0`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CPimcSurrogate>::QueryInterface(char *a1, __int64 a2, char **a3)
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
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CPimcSurrogate::_GetEntries'::`2'::_entries,
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
0x18000c790  push    rbx
0x18000c792  sub     rsp, 20h
0x18000c796  xor     ebx, ebx
0x18000c798  test    r8, r8
0x18000c79b  jnz     short loc_18000C7A4
0x18000c79d  mov     eax, 80004003h
0x18000c7a2  jmp     short loc_18000C7EE
0x18000c7a4  mov     [r8], rbx
0x18000c7a7  cmp     [rdx], ebx
0x18000c7a9  jnz     short loc_18000C7D4
0x18000c7ab  cmp     [rdx+4], ebx
0x18000c7ae  jnz     short loc_18000C7D4
0x18000c7b0  cmp     dword ptr [rdx+8], 0C0h
0x18000c7b7  jnz     short loc_18000C7D4
0x18000c7b9  cmp     dword ptr [rdx+0Ch], 46000000h
0x18000c7c0  jnz     short loc_18000C7D4
0x18000c7c2  mov     [r8], rcx
0x18000c7c5  mov     rax, [rcx]
0x18000c7c8  mov     rax, [rax+8]
0x18000c7cc  call    cs:__guard_dispatch_icall_fptr
0x18000c7d2  jmp     short loc_18000C7EC
0x18000c7d4  mov     r9, r8; void **
0x18000c7d7  add     rcx, 10h; void *
0x18000c7db  mov     r8, rdx; struct _GUID *
0x18000c7de  lea     rdx, ?_entries@?1??_GetEntries@CPimcSurrogate@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000c7e5  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x18000c7ea  mov     ebx, eax
0x18000c7ec  mov     eax, ebx
0x18000c7ee  add     rsp, 20h
0x18000c7f2  pop     rbx
0x18000c7f3  retn
```
