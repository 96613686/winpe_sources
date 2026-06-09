# ATL::CComAggObject<CMsMpComFactoryHome>::QueryInterface(_GUID const &,void * *)

- ea: `0x180004870`
- end: `0x1800048d3`
- name: `?QueryInterface@?$CComAggObject@VCMsMpComFactoryHome@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000420c`
- `0x180004870`
- `0x18000a010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CMsMpComFactoryHome>::QueryInterface(char *a1, __int64 a2, char **a3)
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
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CMsMpComFactory::_GetEntries'::`2'::_entries,
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
0x180004870  push    rbx
0x180004872  sub     rsp, 20h
0x180004876  xor     ebx, ebx
0x180004878  test    r8, r8
0x18000487b  jnz     short loc_180004884
0x18000487d  mov     eax, 80004003h
0x180004882  jmp     short loc_1800048CD
0x180004884  mov     [r8], rbx
0x180004887  cmp     [rdx], ebx
0x180004889  jnz     short loc_1800048B3
0x18000488b  cmp     [rdx+4], ebx
0x18000488e  jnz     short loc_1800048B3
0x180004890  cmp     dword ptr [rdx+8], 0C0h
0x180004897  jnz     short loc_1800048B3
0x180004899  cmp     dword ptr [rdx+0Ch], 46000000h
0x1800048a0  jnz     short loc_1800048B3
0x1800048a2  mov     [r8], rcx
0x1800048a5  mov     rax, [rcx]
0x1800048a8  mov     rax, [rax+8]
0x1800048ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048b1  jmp     short loc_1800048CB
0x1800048b3  mov     r9, r8; void **
0x1800048b6  add     rcx, 18h; void *
0x1800048ba  mov     r8, rdx; struct _GUID *
0x1800048bd  lea     rdx, ?_entries@?1??_GetEntries@CMsMpComFactory@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x1800048c4  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x1800048c9  mov     ebx, eax
0x1800048cb  mov     eax, ebx
0x1800048cd  add     rsp, 20h
0x1800048d1  pop     rbx
0x1800048d2  retn
```
