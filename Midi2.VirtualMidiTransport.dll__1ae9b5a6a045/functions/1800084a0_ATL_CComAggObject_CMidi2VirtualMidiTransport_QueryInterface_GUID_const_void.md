# ATL::CComAggObject<CMidi2VirtualMidiTransport>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800084a0`
- end: `0x180008503`
- name: `?QueryInterface@?$CComAggObject@VCMidi2VirtualMidiTransport@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180007ad0`
- `0x1800084a0`
- `0x180021010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CMidi2VirtualMidiTransport>::QueryInterface(char *a1, __int64 a2, char **a3)
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
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CMidi2VirtualMidiTransport::_GetEntries'::`2'::_entries,
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
0x1800084a0  push    rbx
0x1800084a2  sub     rsp, 20h
0x1800084a6  xor     ebx, ebx
0x1800084a8  test    r8, r8
0x1800084ab  jnz     short loc_1800084B4
0x1800084ad  mov     eax, 80004003h
0x1800084b2  jmp     short loc_1800084FD
0x1800084b4  mov     [r8], rbx
0x1800084b7  cmp     [rdx], ebx
0x1800084b9  jnz     short loc_1800084E3
0x1800084bb  cmp     [rdx+4], ebx
0x1800084be  jnz     short loc_1800084E3
0x1800084c0  cmp     dword ptr [rdx+8], 0C0h
0x1800084c7  jnz     short loc_1800084E3
0x1800084c9  cmp     dword ptr [rdx+0Ch], 46000000h
0x1800084d0  jnz     short loc_1800084E3
0x1800084d2  mov     [r8], rcx
0x1800084d5  mov     rax, [rcx]
0x1800084d8  mov     rax, [rax+8]
0x1800084dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084e1  jmp     short loc_1800084FB
0x1800084e3  mov     r9, r8; void **
0x1800084e6  add     rcx, 18h; void *
0x1800084ea  mov     r8, rdx; struct _GUID *
0x1800084ed  lea     rdx, ?_entries@?1??_GetEntries@CMidi2VirtualMidiTransport@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x1800084f4  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x1800084f9  mov     ebx, eax
0x1800084fb  mov     eax, ebx
0x1800084fd  add     rsp, 20h
0x180008501  pop     rbx
0x180008502  retn
```
