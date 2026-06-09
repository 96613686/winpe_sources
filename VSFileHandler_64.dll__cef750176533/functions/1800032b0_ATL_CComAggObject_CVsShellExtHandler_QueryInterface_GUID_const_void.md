# ATL::CComAggObject<CVsShellExtHandler>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800032b0`
- end: `0x18000330d`
- name: `?QueryInterface@?$CComAggObject@VCVsShellExtHandler@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `93`
- prototype: `__int64 __fastcall(char *, __int64, char **)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002f5c`

## callees

- `0x1800032b0`
- `0x18000372c`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CVsShellExtHandler>::QueryInterface(char *a1, __int64 a2, char **a3)
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
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CVsShellExtHandler::_GetEntries'::`2'::_entries,
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
0x1800032b0  push    rbx
0x1800032b2  sub     rsp, 20h
0x1800032b6  xor     ebx, ebx
0x1800032b8  test    r8, r8
0x1800032bb  jnz     short loc_1800032C4
0x1800032bd  mov     eax, 80004003h
0x1800032c2  jmp     short loc_180003307
0x1800032c4  mov     [r8], rbx
0x1800032c7  cmp     [rdx], ebx
0x1800032c9  jnz     short loc_1800032ED
0x1800032cb  cmp     [rdx+4], ebx
0x1800032ce  jnz     short loc_1800032ED
0x1800032d0  cmp     dword ptr [rdx+8], 0C0h
0x1800032d7  jnz     short loc_1800032ED
0x1800032d9  cmp     dword ptr [rdx+0Ch], 46000000h
0x1800032e0  jnz     short loc_1800032ED
0x1800032e2  mov     [r8], rcx
0x1800032e5  mov     rax, [rcx]
0x1800032e8  call    qword ptr [rax+8]
0x1800032eb  jmp     short loc_180003305
0x1800032ed  mov     r9, r8; void **
0x1800032f0  add     rcx, 10h; void *
0x1800032f4  mov     r8, rdx; struct _GUID *
0x1800032f7  lea     rdx, ?_entries@?1??_GetEntries@CVsShellExtHandler@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x1800032fe  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180003303  mov     ebx, eax
0x180003305  mov     eax, ebx
0x180003307  add     rsp, 20h
0x18000330b  pop     rbx
0x18000330c  retn
```
