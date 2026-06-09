# ATL::CComAggObject<CRemoveDeviceContextHandler>::QueryInterface(_GUID const &,void * *)

- ea: `0x180009230`
- end: `0x180009293`
- name: `?QueryInterface@?$CComAggObject@VCRemoveDeviceContextHandler@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008498`
- `0x180009230`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CRemoveDeviceContextHandler>::QueryInterface(char *a1, __int64 a2, char **a3)
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
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CRemoveDeviceContextHandler::_GetEntries'::`2'::_entries,
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
0x180009230  push    rbx
0x180009232  sub     rsp, 20h
0x180009236  xor     ebx, ebx
0x180009238  test    r8, r8
0x18000923b  jnz     short loc_180009244
0x18000923d  mov     eax, 80004003h
0x180009242  jmp     short loc_18000928D
0x180009244  mov     [r8], rbx
0x180009247  cmp     [rdx], ebx
0x180009249  jnz     short loc_180009273
0x18000924b  cmp     [rdx+4], ebx
0x18000924e  jnz     short loc_180009273
0x180009250  cmp     dword ptr [rdx+8], 0C0h
0x180009257  jnz     short loc_180009273
0x180009259  cmp     dword ptr [rdx+0Ch], 46000000h
0x180009260  jnz     short loc_180009273
0x180009262  mov     [r8], rcx
0x180009265  mov     rax, [rcx]
0x180009268  mov     rax, [rax+8]
0x18000926c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009271  jmp     short loc_18000928B
0x180009273  mov     r9, r8; void **
0x180009276  add     rcx, 10h; void *
0x18000927a  mov     r8, rdx; struct _GUID *
0x18000927d  lea     rdx, ?_entries@?1??_GetEntries@CRemoveDeviceContextHandler@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180009284  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180009289  mov     ebx, eax
0x18000928b  mov     eax, ebx
0x18000928d  add     rsp, 20h
0x180009291  pop     rbx
0x180009292  retn
```
