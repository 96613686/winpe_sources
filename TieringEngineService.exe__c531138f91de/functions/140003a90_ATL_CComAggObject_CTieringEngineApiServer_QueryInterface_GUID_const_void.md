# ATL::CComAggObject<CTieringEngineApiServer>::QueryInterface(_GUID const &,void * *)

- ea: `0x140003a90`
- end: `0x140003af3`
- name: `?QueryInterface@?$CComAggObject@VCTieringEngineApiServer@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `99`
- prototype: `__int64 __fastcall(char *, __int64, char **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400035e4`
- `0x140003a90`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CTieringEngineApiServer>::QueryInterface(char *a1, __int64 a2, char **a3)
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
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CTieringEngineApiServer::_GetEntries'::`2'::_entries,
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
0x140003a90  push    rbx
0x140003a92  sub     rsp, 20h
0x140003a96  xor     ebx, ebx
0x140003a98  test    r8, r8
0x140003a9b  jnz     short loc_140003AA4
0x140003a9d  mov     eax, 80004003h
0x140003aa2  jmp     short loc_140003AED
0x140003aa4  mov     [r8], rbx
0x140003aa7  cmp     [rdx], ebx
0x140003aa9  jnz     short loc_140003AD3
0x140003aab  cmp     [rdx+4], ebx
0x140003aae  jnz     short loc_140003AD3
0x140003ab0  cmp     dword ptr [rdx+8], 0C0h
0x140003ab7  jnz     short loc_140003AD3
0x140003ab9  cmp     dword ptr [rdx+0Ch], 46000000h
0x140003ac0  jnz     short loc_140003AD3
0x140003ac2  mov     [r8], rcx
0x140003ac5  mov     rax, [rcx]
0x140003ac8  mov     rax, [rax+8]
0x140003acc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003ad1  jmp     short loc_140003AEB
0x140003ad3  mov     r9, r8; void **
0x140003ad6  add     rcx, 18h; void *
0x140003ada  mov     r8, rdx; struct _GUID *
0x140003add  lea     rdx, ?_entries@?1??_GetEntries@CTieringEngineApiServer@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x140003ae4  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x140003ae9  mov     ebx, eax
0x140003aeb  mov     eax, ebx
0x140003aed  add     rsp, 20h
0x140003af1  pop     rbx
0x140003af2  retn
```
