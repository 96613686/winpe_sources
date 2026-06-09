# ATL::CComAggObject<CTieringEngineTaskHandler>::QueryInterface(_GUID const &,void * *)

- ea: `0x140003b00`
- end: `0x140003b63`
- name: `?QueryInterface@?$CComAggObject@VCTieringEngineTaskHandler@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `99`
- prototype: `__int64 __fastcall(char *, __int64, char **)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1400035e4`
- `0x140003b00`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CTieringEngineTaskHandler>::QueryInterface(char *a1, __int64 a2, char **a3)
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
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CTieringEngineTaskHandler::_GetEntries'::`2'::_entries,
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
0x140003b00  push    rbx
0x140003b02  sub     rsp, 20h
0x140003b06  xor     ebx, ebx
0x140003b08  test    r8, r8
0x140003b0b  jnz     short loc_140003B14
0x140003b0d  mov     eax, 80004003h
0x140003b12  jmp     short loc_140003B5D
0x140003b14  mov     [r8], rbx
0x140003b17  cmp     [rdx], ebx
0x140003b19  jnz     short loc_140003B43
0x140003b1b  cmp     [rdx+4], ebx
0x140003b1e  jnz     short loc_140003B43
0x140003b20  cmp     dword ptr [rdx+8], 0C0h
0x140003b27  jnz     short loc_140003B43
0x140003b29  cmp     dword ptr [rdx+0Ch], 46000000h
0x140003b30  jnz     short loc_140003B43
0x140003b32  mov     [r8], rcx
0x140003b35  mov     rax, [rcx]
0x140003b38  mov     rax, [rax+8]
0x140003b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003b41  jmp     short loc_140003B5B
0x140003b43  mov     r9, r8; void **
0x140003b46  add     rcx, 18h; void *
0x140003b4a  mov     r8, rdx; struct _GUID *
0x140003b4d  lea     rdx, ?_entries@?1??_GetEntries@CTieringEngineTaskHandler@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x140003b54  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x140003b59  mov     ebx, eax
0x140003b5b  mov     eax, ebx
0x140003b5d  add     rsp, 20h
0x140003b61  pop     rbx
0x140003b62  retn
```
