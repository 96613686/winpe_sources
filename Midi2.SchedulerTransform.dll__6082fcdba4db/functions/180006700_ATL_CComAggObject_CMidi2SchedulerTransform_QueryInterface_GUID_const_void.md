# ATL::CComAggObject<CMidi2SchedulerTransform>::QueryInterface(_GUID const &,void * *)

- ea: `0x180006700`
- end: `0x180006763`
- name: `?QueryInterface@?$CComAggObject@VCMidi2SchedulerTransform@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180005d30`
- `0x180006700`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CMidi2SchedulerTransform>::QueryInterface(char *a1, __int64 a2, char **a3)
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
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CMidi2SchedulerTransform::_GetEntries'::`2'::_entries,
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
0x180006700  push    rbx
0x180006702  sub     rsp, 20h
0x180006706  xor     ebx, ebx
0x180006708  test    r8, r8
0x18000670b  jnz     short loc_180006714
0x18000670d  mov     eax, 80004003h
0x180006712  jmp     short loc_18000675D
0x180006714  mov     [r8], rbx
0x180006717  cmp     [rdx], ebx
0x180006719  jnz     short loc_180006743
0x18000671b  cmp     [rdx+4], ebx
0x18000671e  jnz     short loc_180006743
0x180006720  cmp     dword ptr [rdx+8], 0C0h
0x180006727  jnz     short loc_180006743
0x180006729  cmp     dword ptr [rdx+0Ch], 46000000h
0x180006730  jnz     short loc_180006743
0x180006732  mov     [r8], rcx
0x180006735  mov     rax, [rcx]
0x180006738  mov     rax, [rax+8]
0x18000673c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006741  jmp     short loc_18000675B
0x180006743  mov     r9, r8; void **
0x180006746  add     rcx, 18h; void *
0x18000674a  mov     r8, rdx; struct _GUID *
0x18000674d  lea     rdx, ?_entries@?1??_GetEntries@CMidi2SchedulerTransform@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180006754  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180006759  mov     ebx, eax
0x18000675b  mov     eax, ebx
0x18000675d  add     rsp, 20h
0x180006761  pop     rbx
0x180006762  retn
```
