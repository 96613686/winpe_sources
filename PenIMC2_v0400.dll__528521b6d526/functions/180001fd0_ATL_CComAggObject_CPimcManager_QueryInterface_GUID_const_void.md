# ATL::CComAggObject<CPimcManager>::QueryInterface(_GUID const &,void * *)

- ea: `0x180001fd0`
- end: `0x180002034`
- name: `?QueryInterface@?$CComAggObject@VCPimcManager@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001b50`

## callees

- `0x180001fd0`
- `0x18000323c`
- `0x18000e4a0`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CPimcManager>::QueryInterface(char *a1, __int64 a2, char **a3)
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
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CPimcManager::_GetEntries'::`2'::_entries,
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
0x180001fd0  push    rbx
0x180001fd2  sub     rsp, 20h
0x180001fd6  xor     ebx, ebx
0x180001fd8  test    r8, r8
0x180001fdb  jnz     short loc_180001FE4
0x180001fdd  mov     eax, 80004003h
0x180001fe2  jmp     short loc_18000202E
0x180001fe4  mov     [r8], rbx
0x180001fe7  cmp     [rdx], ebx
0x180001fe9  jnz     short loc_180002014
0x180001feb  cmp     [rdx+4], ebx
0x180001fee  jnz     short loc_180002014
0x180001ff0  cmp     dword ptr [rdx+8], 0C0h
0x180001ff7  jnz     short loc_180002014
0x180001ff9  cmp     dword ptr [rdx+0Ch], 46000000h
0x180002000  jnz     short loc_180002014
0x180002002  mov     [r8], rcx
0x180002005  mov     rax, [rcx]
0x180002008  mov     rax, [rax+8]
0x18000200c  call    cs:__guard_dispatch_icall_fptr
0x180002012  jmp     short loc_18000202C
0x180002014  mov     r9, r8; void **
0x180002017  add     rcx, 10h; void *
0x18000201b  mov     r8, rdx; struct _GUID *
0x18000201e  lea     rdx, ?_entries@?1??_GetEntries@CPimcManager@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180002025  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x18000202a  mov     ebx, eax
0x18000202c  mov     eax, ebx
0x18000202e  add     rsp, 20h
0x180002032  pop     rbx
0x180002033  retn
```
