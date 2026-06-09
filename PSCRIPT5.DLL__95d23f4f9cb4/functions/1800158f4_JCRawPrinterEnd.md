# JCRawPrinterEnd

- ea: `0x1800158f4`
- end: `0x18001598e`
- name: `JCRawPrinterEnd`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001283c`

## callees

- `0x1800158f4`
- `0x180016940`
- `0x18001aa48`

## string_xrefs

- `0x18001592d`: `Pscript_WinNT_Compat dup /suspend get exec\n`

## pseudocode

```c
_BOOL8 __fastcall JCRawPrinterEnd(__int64 a1)
{
  unsigned int v2; // r8d
  char *v3; // rdx

  OPRawPortWrite(a1, "\r\n", 2u);
  DSCSend(a1, "%%%%EndDocument\r\n\r\n");
  if ( *(int *)(a1 + 2152) >= 0 )
  {
    OPRawPortWrite(a1, "Pscript_WinNT_Compat dup /suspend get exec\r\n", 0x2Cu);
    *(_DWORD *)(a1 + 2152) &= ~2u;
    if ( (*(_BYTE *)(a1 + 132) & 0x10) != 0 || (*(_DWORD *)(*(_QWORD *)(a1 + 96) + 124LL) & 0xFFFFFFFD) != 0 )
    {
      v2 = 64;
      v3 = "/Pscript_WinNT_Full /ProcSet findresource dup /resume get exec\r\n";
    }
    else
    {
      v2 = 41;
      v3 = "Pscript_WinNT_Incr dup /resume get exec\r\n";
    }
    OPRawPortWrite(a1, v3, v2);
  }
  return *(_DWORD *)(a1 + 3440) == 0;
}

```

## disassembly

```asm
0x1800158f4  push    rbx
0x1800158f6  sub     rsp, 20h
0x1800158fa  mov     r8d, 2
0x180015900  lea     rdx, gstrCRLF; "\r\n"
0x180015907  mov     rbx, rcx
0x18001590a  call    OPRawPortWrite
0x18001590f  lea     rdx, DSC_EndDocument; "%%%%EndDocument\r\n\r\n"
0x180015916  mov     rcx, rbx
0x180015919  call    DSCSend
0x18001591e  cmp     dword ptr [rbx+868h], 0
0x180015925  jl      short loc_18001597D
0x180015927  mov     r8d, 2Ch ; ','
0x18001592d  lea     rdx, PSFRAG_suspendcompatdict; "Pscript_WinNT_Compat dup /suspend get e"...
0x180015934  mov     rcx, rbx
0x180015937  call    OPRawPortWrite
0x18001593c  mov     ecx, 0FFFFFFFDh
0x180015941  and     [rbx+868h], ecx
0x180015947  test    byte ptr [rbx+84h], 10h
0x18001594e  jnz     short loc_180015968
0x180015950  mov     rax, [rbx+60h]
0x180015954  test    [rax+7Ch], ecx
0x180015957  jnz     short loc_180015968
0x180015959  mov     r8d, 29h ; ')'
0x18001595f  lea     rdx, PSFRAG_resumeincrdict; "Pscript_WinNT_Incr dup /resume get exec"...
0x180015966  jmp     short loc_180015975
0x180015968  mov     r8d, 40h ; '@'
0x18001596e  lea     rdx, PSFRAG_resumefulldict; "/Pscript_WinNT_Full /ProcSet findresour"...
0x180015975  mov     rcx, rbx
0x180015978  call    OPRawPortWrite
0x18001597d  xor     eax, eax
0x18001597f  cmp     [rbx+0D70h], eax
0x180015985  setz    al
0x180015988  add     rsp, 20h
0x18001598c  pop     rbx
0x18001598d  retn
```
