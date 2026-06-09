# ATL::CComAggObject<CMidi2MidiSrvTransport>::QueryInterface(_GUID const &,void * *)

- ea: `0x180006cc0`
- end: `0x180006d23`
- name: `?QueryInterface@?$CComAggObject@VCMidi2MidiSrvTransport@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800062e8`
- `0x180006cc0`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CMidi2MidiSrvTransport>::QueryInterface(char *a1, __int64 a2, char **a3)
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
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CMidi2MidiSrvTransport::_GetEntries'::`2'::_entries,
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
0x180006cc0  push    rbx
0x180006cc2  sub     rsp, 20h
0x180006cc6  xor     ebx, ebx
0x180006cc8  test    r8, r8
0x180006ccb  jnz     short loc_180006CD4
0x180006ccd  mov     eax, 80004003h
0x180006cd2  jmp     short loc_180006D1D
0x180006cd4  mov     [r8], rbx
0x180006cd7  cmp     [rdx], ebx
0x180006cd9  jnz     short loc_180006D03
0x180006cdb  cmp     [rdx+4], ebx
0x180006cde  jnz     short loc_180006D03
0x180006ce0  cmp     dword ptr [rdx+8], 0C0h
0x180006ce7  jnz     short loc_180006D03
0x180006ce9  cmp     dword ptr [rdx+0Ch], 46000000h
0x180006cf0  jnz     short loc_180006D03
0x180006cf2  mov     [r8], rcx
0x180006cf5  mov     rax, [rcx]
0x180006cf8  mov     rax, [rax+8]
0x180006cfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d01  jmp     short loc_180006D1B
0x180006d03  mov     r9, r8; void **
0x180006d06  add     rcx, 18h; void *
0x180006d0a  mov     r8, rdx; struct _GUID *
0x180006d0d  lea     rdx, ?_entries@?1??_GetEntries@CMidi2MidiSrvTransport@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180006d14  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180006d19  mov     ebx, eax
0x180006d1b  mov     eax, ebx
0x180006d1d  add     rsp, 20h
0x180006d21  pop     rbx
0x180006d22  retn
```
