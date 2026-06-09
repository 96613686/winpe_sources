# WMDSPPropClear

- ea: `0x180044d20`
- end: `0x180044d64`
- name: `WMDSPPropClear`
- size: `68`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800447ac`
- `0x180044830`

## callees

- `0x180044d20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044d3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044d3e`
- `OLEAUT32!__imp_SysFreeString` at `0x180044d51`
- `OLEAUT32!__imp_SysFreeString` at `0x180044d51`

## pseudocode

```c
void __fastcall WMDSPPropClear(__int16 a1, __int64 a2)
{
  void *v3; // rcx

  if ( a1 == 8 )
  {
    SysFreeString(*(BSTR *)a2);
    *(_QWORD *)a2 = 0;
  }
  else if ( a1 == 65 )
  {
    v3 = *(void **)(a2 + 8);
    if ( v3 )
      CoTaskMemFree(v3);
    *(_QWORD *)(a2 + 8) = 0;
  }
}

```

## disassembly

```asm
0x180044d20  push    rbx
0x180044d22  sub     rsp, 20h
0x180044d26  mov     rbx, rdx
0x180044d29  cmp     cx, 8
0x180044d2d  jz      short loc_180044D4E
0x180044d2f  cmp     cx, 41h ; 'A'
0x180044d33  jnz     short loc_180044D5E
0x180044d35  mov     rcx, [rdx+8]; pv
0x180044d39  test    rcx, rcx
0x180044d3c  jz      short loc_180044D44
0x180044d3e  call    cs:__imp_CoTaskMemFree
0x180044d44  mov     qword ptr [rbx+8], 0
0x180044d4c  jmp     short loc_180044D5E
0x180044d4e  mov     rcx, [rdx]; bstrString
0x180044d51  call    cs:__imp_SysFreeString
0x180044d57  mov     qword ptr [rbx], 0
0x180044d5e  add     rsp, 20h
0x180044d62  pop     rbx
0x180044d63  retn
```
