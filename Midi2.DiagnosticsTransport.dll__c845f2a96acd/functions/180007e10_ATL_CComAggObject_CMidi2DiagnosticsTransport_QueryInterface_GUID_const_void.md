# ATL::CComAggObject<CMidi2DiagnosticsTransport>::QueryInterface(_GUID const &,void * *)

- ea: `0x180007e10`
- end: `0x180007e73`
- name: `?QueryInterface@?$CComAggObject@VCMidi2DiagnosticsTransport@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180007440`
- `0x180007e10`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CMidi2DiagnosticsTransport>::QueryInterface(char *a1, __int64 a2, char **a3)
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
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CMidi2DiagnosticsTransport::_GetEntries'::`2'::_entries,
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
0x180007e10  push    rbx
0x180007e12  sub     rsp, 20h
0x180007e16  xor     ebx, ebx
0x180007e18  test    r8, r8
0x180007e1b  jnz     short loc_180007E24
0x180007e1d  mov     eax, 80004003h
0x180007e22  jmp     short loc_180007E6D
0x180007e24  mov     [r8], rbx
0x180007e27  cmp     [rdx], ebx
0x180007e29  jnz     short loc_180007E53
0x180007e2b  cmp     [rdx+4], ebx
0x180007e2e  jnz     short loc_180007E53
0x180007e30  cmp     dword ptr [rdx+8], 0C0h
0x180007e37  jnz     short loc_180007E53
0x180007e39  cmp     dword ptr [rdx+0Ch], 46000000h
0x180007e40  jnz     short loc_180007E53
0x180007e42  mov     [r8], rcx
0x180007e45  mov     rax, [rcx]
0x180007e48  mov     rax, [rax+8]
0x180007e4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e51  jmp     short loc_180007E6B
0x180007e53  mov     r9, r8; void **
0x180007e56  add     rcx, 18h; void *
0x180007e5a  mov     r8, rdx; struct _GUID *
0x180007e5d  lea     rdx, ?_entries@?1??_GetEntries@CMidi2DiagnosticsTransport@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180007e64  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180007e69  mov     ebx, eax
0x180007e6b  mov     eax, ebx
0x180007e6d  add     rsp, 20h
0x180007e71  pop     rbx
0x180007e72  retn
```
