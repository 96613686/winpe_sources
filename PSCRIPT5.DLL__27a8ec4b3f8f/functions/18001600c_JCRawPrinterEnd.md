# JCRawPrinterEnd

- ea: `0x18001600c`
- end: `0x1800160a7`
- name: `JCRawPrinterEnd`
- size: `155`
- prototype: `_BOOL8 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180012e18`

## callees

- `0x18001600c`
- `0x1800170a0`
- `0x18001b388`

## string_xrefs

- `0x180016045`: `Pscript_WinNT_Compat dup /suspend get exec\n`

## pseudocode

```c
_BOOL8 __fastcall JCRawPrinterEnd(__int64 a1)
{
  OPRawPortWrite(a1, "\r\n", 2u);
  DSCSend(a1, "%%%%EndDocument\r\n\r\n");
  if ( *(int *)(a1 + 2152) >= 0 )
  {
    OPRawPortWrite(a1, "Pscript_WinNT_Compat dup /suspend get exec\r\n", 0x2Cu);
    *(_DWORD *)(a1 + 2152) &= ~2u;
    if ( (*(_BYTE *)(a1 + 132) & 0x10) != 0 || (*(_DWORD *)(*(_QWORD *)(a1 + 96) + 124LL) & 0xFFFFFFFD) != 0 )
      OPRawPortWrite(a1, "/Pscript_WinNT_Full /ProcSet findresource dup /resume get exec\r\n", 0x40u);
    else
      OPRawPortWrite(a1, "Pscript_WinNT_Incr dup /resume get exec\r\n", 0x29u);
  }
  return *(_DWORD *)(a1 + 3440) == 0;
}

```

## disassembly

```asm
0x18001600c  push    rbx
0x18001600e  sub     rsp, 20h
0x180016012  mov     r8d, 2
0x180016018  lea     rdx, gstrCRLF; "\r\n"
0x18001601f  mov     rbx, rcx
0x180016022  call    OPRawPortWrite
0x180016027  lea     rdx, DSC_EndDocument; "%%%%EndDocument\r\n\r\n"
0x18001602e  mov     rcx, rbx
0x180016031  call    DSCSend
0x180016036  cmp     dword ptr [rbx+868h], 0
0x18001603d  jl      short loc_180016095
0x18001603f  mov     r8d, 2Ch ; ','
0x180016045  lea     rdx, PSFRAG_suspendcompatdict; "Pscript_WinNT_Compat dup /suspend get e"...
0x18001604c  mov     rcx, rbx
0x18001604f  call    OPRawPortWrite
0x180016054  mov     ecx, 0FFFFFFFDh
0x180016059  and     [rbx+868h], ecx
0x18001605f  test    byte ptr [rbx+84h], 10h
0x180016066  jnz     short loc_180016080
0x180016068  mov     rax, [rbx+60h]
0x18001606c  test    [rax+7Ch], ecx
0x18001606f  jnz     short loc_180016080
0x180016071  mov     r8d, 29h ; ')'
0x180016077  lea     rdx, PSFRAG_resumeincrdict; "Pscript_WinNT_Incr dup /resume get exec"...
0x18001607e  jmp     short loc_18001608D
0x180016080  mov     r8d, 40h ; '@'
0x180016086  lea     rdx, PSFRAG_resumefulldict; "/Pscript_WinNT_Full /ProcSet findresour"...
0x18001608d  mov     rcx, rbx
0x180016090  call    OPRawPortWrite
0x180016095  xor     eax, eax
0x180016097  cmp     [rbx+0D70h], eax
0x18001609d  setz    al
0x1800160a0  add     rsp, 20h
0x1800160a4  pop     rbx
0x1800160a5  retn
```
