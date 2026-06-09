# WMDSPPropClear

- ea: `0x180007c64`
- end: `0x180007caa`
- name: `WMDSPPropClear`
- size: `70`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007be4`
- `0x1800833d0`

## callees

- `0x180007c64`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180007c9b`
- `OLEAUT32!__imp_SysFreeString` at `0x180007c9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007c88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007c88`

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
0x180007c64  push    rbx
0x180007c66  sub     rsp, 20h
0x180007c6a  mov     rbx, rdx
0x180007c6d  cmp     cx, 8
0x180007c71  jz      short loc_180007C98
0x180007c73  cmp     cx, 41h ; 'A'
0x180007c77  jz      short loc_180007C7F
0x180007c79  add     rsp, 20h
0x180007c7d  pop     rbx
0x180007c7e  retn
0x180007c7f  mov     rcx, [rdx+8]; pv
0x180007c83  test    rcx, rcx
0x180007c86  jz      short loc_180007C8E
0x180007c88  call    cs:__imp_CoTaskMemFree
0x180007c8e  mov     qword ptr [rbx+8], 0
0x180007c96  jmp     short loc_180007C79
0x180007c98  mov     rcx, [rdx]; bstrString
0x180007c9b  call    cs:__imp_SysFreeString
0x180007ca1  mov     qword ptr [rbx], 0
0x180007ca8  jmp     short loc_180007C79
```
