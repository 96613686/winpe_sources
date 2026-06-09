# ATL::CComAggObject<CLayerUIPropPage>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000dd90`
- end: `0x18000ddf3`
- name: `?QueryInterface@?$CComAggObject@VCLayerUIPropPage@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000953c`
- `0x18000dd90`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CLayerUIPropPage>::QueryInterface(char *a1, __int64 a2, char **a3)
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
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CLayerUIPropPage::_GetEntries'::`2'::_entries,
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
0x18000dd90  push    rbx
0x18000dd92  sub     rsp, 20h
0x18000dd96  xor     ebx, ebx
0x18000dd98  test    r8, r8
0x18000dd9b  jnz     short loc_18000DDA4
0x18000dd9d  mov     eax, 80004003h
0x18000dda2  jmp     short loc_18000DDED
0x18000dda4  mov     [r8], rbx
0x18000dda7  cmp     [rdx], ebx
0x18000dda9  jnz     short loc_18000DDD3
0x18000ddab  cmp     [rdx+4], ebx
0x18000ddae  jnz     short loc_18000DDD3
0x18000ddb0  cmp     dword ptr [rdx+8], 0C0h
0x18000ddb7  jnz     short loc_18000DDD3
0x18000ddb9  cmp     dword ptr [rdx+0Ch], 46000000h
0x18000ddc0  jnz     short loc_18000DDD3
0x18000ddc2  mov     [r8], rcx
0x18000ddc5  mov     rax, [rcx]
0x18000ddc8  mov     rax, [rax+8]
0x18000ddcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ddd1  jmp     short loc_18000DDEB
0x18000ddd3  mov     r9, r8; void **
0x18000ddd6  add     rcx, 10h; void *
0x18000ddda  mov     r8, rdx; struct _GUID *
0x18000dddd  lea     rdx, ?_entries@?1??_GetEntries@CLayerUIPropPage@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000dde4  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x18000dde9  mov     ebx, eax
0x18000ddeb  mov     eax, ebx
0x18000dded  add     rsp, 20h
0x18000ddf1  pop     rbx
0x18000ddf2  retn
```
