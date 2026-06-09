# ATL::CComAggObject<CMidi2UmpProtocolDownscalerTransform>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800077d0`
- end: `0x180007833`
- name: `?QueryInterface@?$CComAggObject@VCMidi2UmpProtocolDownscalerTransform@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006e00`
- `0x1800077d0`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CMidi2UmpProtocolDownscalerTransform>::QueryInterface(
        char *a1,
        __int64 a2,
        char **a3)
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
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CMidi2UmpProtocolDownscalerTransform::_GetEntries'::`2'::_entries,
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
0x1800077d0  push    rbx
0x1800077d2  sub     rsp, 20h
0x1800077d6  xor     ebx, ebx
0x1800077d8  test    r8, r8
0x1800077db  jnz     short loc_1800077E4
0x1800077dd  mov     eax, 80004003h
0x1800077e2  jmp     short loc_18000782D
0x1800077e4  mov     [r8], rbx
0x1800077e7  cmp     [rdx], ebx
0x1800077e9  jnz     short loc_180007813
0x1800077eb  cmp     [rdx+4], ebx
0x1800077ee  jnz     short loc_180007813
0x1800077f0  cmp     dword ptr [rdx+8], 0C0h
0x1800077f7  jnz     short loc_180007813
0x1800077f9  cmp     dword ptr [rdx+0Ch], 46000000h
0x180007800  jnz     short loc_180007813
0x180007802  mov     [r8], rcx
0x180007805  mov     rax, [rcx]
0x180007808  mov     rax, [rax+8]
0x18000780c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007811  jmp     short loc_18000782B
0x180007813  mov     r9, r8; void **
0x180007816  add     rcx, 18h; void *
0x18000781a  mov     r8, rdx; struct _GUID *
0x18000781d  lea     rdx, ?_entries@?1??_GetEntries@CMidi2UmpProtocolDownscalerTransform@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180007824  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180007829  mov     ebx, eax
0x18000782b  mov     eax, ebx
0x18000782d  add     rsp, 20h
0x180007831  pop     rbx
0x180007832  retn
```
