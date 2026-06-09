# ATL::CComAggObject<CServiceProvider>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800075e0`
- end: `0x180007643`
- name: `?QueryInterface@?$CComAggObject@VCServiceProvider@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006f94`
- `0x1800075e0`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CServiceProvider>::QueryInterface(char *a1, __int64 a2, char **a3)
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
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CServiceProvider::_GetEntries'::`2'::_entries,
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
0x1800075e0  push    rbx
0x1800075e2  sub     rsp, 20h
0x1800075e6  xor     ebx, ebx
0x1800075e8  test    r8, r8
0x1800075eb  jnz     short loc_1800075F4
0x1800075ed  mov     eax, 80004003h
0x1800075f2  jmp     short loc_18000763D
0x1800075f4  mov     [r8], rbx
0x1800075f7  cmp     [rdx], ebx
0x1800075f9  jnz     short loc_180007623
0x1800075fb  cmp     [rdx+4], ebx
0x1800075fe  jnz     short loc_180007623
0x180007600  cmp     dword ptr [rdx+8], 0C0h
0x180007607  jnz     short loc_180007623
0x180007609  cmp     dword ptr [rdx+0Ch], 46000000h
0x180007610  jnz     short loc_180007623
0x180007612  mov     [r8], rcx
0x180007615  mov     rax, [rcx]
0x180007618  mov     rax, [rax+8]
0x18000761c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007621  jmp     short loc_18000763B
0x180007623  mov     r9, r8; void **
0x180007626  add     rcx, 18h; void *
0x18000762a  mov     r8, rdx; struct _GUID *
0x18000762d  lea     rdx, ?_entries@?1??_GetEntries@CServiceProvider@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180007634  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180007639  mov     ebx, eax
0x18000763b  mov     eax, ebx
0x18000763d  add     rsp, 20h
0x180007641  pop     rbx
0x180007642  retn
```
