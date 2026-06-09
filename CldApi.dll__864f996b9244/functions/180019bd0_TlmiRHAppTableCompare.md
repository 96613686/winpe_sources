# TlmiRHAppTableCompare

- ea: `0x180019bd0`
- end: `0x180019c14`
- name: `TlmiRHAppTableCompare`
- size: `68`
- prototype: `RTL_AVL_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180019bd0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180019bef`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180019bef`

## pseudocode

```c
char __fastcall TlmiRHAppTableCompare(struct _RTL_AVL_TABLE *Table, _QWORD *FirstStruct, _QWORD *SecondStruct)
{
  int v3; // ecx

  if ( *(_DWORD *)FirstStruct != *(_DWORD *)SecondStruct )
    return *(_DWORD *)FirstStruct > *(_DWORD *)SecondStruct;
  v3 = _o__wcsnicmp(FirstStruct[2], SecondStruct[2], 0x7FFF);
  if ( v3 )
    return v3 >= 0;
  else
    return 2;
}

```

## disassembly

```asm
0x180019bd0  sub     rsp, 28h
0x180019bd4  mov     ecx, [rdx]
0x180019bd6  mov     r9, r8
0x180019bd9  mov     rax, rdx
0x180019bdc  cmp     ecx, [r8]
0x180019bdf  jnz     short loc_180019C07
0x180019be1  mov     rdx, [r9+10h]
0x180019be5  mov     r8d, 7FFFh
0x180019beb  mov     rcx, [rax+10h]
0x180019bef  call    cs:__imp__o__wcsnicmp
0x180019bf5  mov     ecx, eax
0x180019bf7  xor     eax, eax
0x180019bf9  test    ecx, ecx
0x180019bfb  jnz     short loc_180019C02
0x180019bfd  lea     eax, [rcx+2]
0x180019c00  jmp     short loc_180019C0F
0x180019c02  setns   al
0x180019c05  jmp     short loc_180019C0F
0x180019c07  xor     eax, eax
0x180019c09  cmp     ecx, [r8]
0x180019c0c  setnbe  al
0x180019c0f  add     rsp, 28h
0x180019c13  retn
```
