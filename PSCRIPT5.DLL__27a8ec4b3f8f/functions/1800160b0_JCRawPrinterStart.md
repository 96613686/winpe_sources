# JCRawPrinterStart

- ea: `0x1800160b0`
- end: `0x1800161f1`
- name: `JCRawPrinterStart`
- size: `321`
- prototype: `_BOOL8 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180012e18`

## callees

- `0x18001208c`
- `0x180012a50`
- `0x1800160b0`
- `0x1800161f8`
- `0x1800166c0`
- `0x1800170a0`
- `0x18001b034`
- `0x18001b1b4`
- `0x18001b388`

## string_xrefs

- `0x180016158`: `Pscript_WinNT_Compat begin /$x mysetup def end\n`
- `0x1800161b0`: `Pscript_WinNT_Compat dup /initialize get exec\n`

## pseudocode

```c
_BOOL8 __fastcall JCRawPrinterStart(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // rax

  if ( *(int *)(a1 + 2152) >= 0 )
  {
    GSEndOptimization(a1);
    if ( *(_DWORD *)(*(_QWORD *)(a1 + 96) + 140LL) == 1 && (*(_BYTE *)(a1 + 2236) & 4) == 0 )
    {
      VMRestoreLevel1(a1);
      v2 = *(_QWORD *)(a1 + 96);
      if ( !*(_DWORD *)(v2 + 124) && (unsigned int)(*(_DWORD *)(v2 + 136) - 1) <= 4 )
      {
        JCSendNup(a1);
        GSSendGsave(a1);
      }
      v3 = *(_QWORD *)(a1 + 96);
      *(_DWORD *)(a1 + 2236) |= 4u;
      if ( !*(_DWORD *)(v3 + 124) )
        OPRawPortWrite(a1, "mysetup concat colspRefresh\r\n", 0x1Du);
    }
    VMCheck(a1, 3u, 0);
    PSProcsetSend((_DWORD *)a1, 23);
    OPRawPortWrite(a1, "Pscript_WinNT_Compat begin /$x mysetup def end\r\n", 0x30u);
    if ( (*(_BYTE *)(a1 + 132) & 0x10) != 0 || (*(_DWORD *)(*(_QWORD *)(a1 + 96) + 124LL) & 0xFFFFFFFD) != 0 )
      OPRawPortWrite(a1, "/Pscript_WinNT_Full /ProcSet findresource dup /suspend get exec\r\n", 0x41u);
    else
      OPRawPortWrite(a1, "Pscript_WinNT_Incr dup /suspend get exec\r\n", 0x2Au);
    if ( (*(_BYTE *)(a1 + 2152) & 2) == 0 )
    {
      OPRawPortWrite(a1, "Pscript_WinNT_Compat dup /initialize get exec\r\n", 0x2Fu);
      *(_DWORD *)(a1 + 2152) |= 2u;
    }
    **(_DWORD **)(a1 + 752) |= 2u;
  }
  DSCSend(a1, "%%%%BeginDocument: Pscript_Win_PassThrough\r\n");
  return *(_DWORD *)(a1 + 3440) == 0;
}

```

## disassembly

```asm
0x1800160b0  push    rbx
0x1800160b2  sub     rsp, 20h
0x1800160b6  cmp     dword ptr [rcx+868h], 0
0x1800160bd  mov     rbx, rcx
0x1800160c0  jl      loc_1800161D0
0x1800160c6  call    GSEndOptimization
0x1800160cb  mov     rax, [rbx+60h]
0x1800160cf  cmp     dword ptr [rax+8Ch], 1
0x1800160d6  jnz     short loc_180016136
0x1800160d8  test    byte ptr [rbx+8BCh], 4
0x1800160df  jnz     short loc_180016136
0x1800160e1  mov     rcx, rbx
0x1800160e4  call    VMRestoreLevel1
0x1800160e9  mov     rax, [rbx+60h]
0x1800160ed  cmp     dword ptr [rax+7Ch], 0
0x1800160f1  jnz     short loc_180016110
0x1800160f3  mov     eax, [rax+88h]
0x1800160f9  dec     eax
0x1800160fb  cmp     eax, 4
0x1800160fe  ja      short loc_180016110
0x180016100  mov     rcx, rbx
0x180016103  call    JCSendNup
0x180016108  mov     rcx, rbx
0x18001610b  call    GSSendGsave
0x180016110  mov     rax, [rbx+60h]
0x180016114  or      dword ptr [rbx+8BCh], 4
0x18001611b  cmp     dword ptr [rax+7Ch], 0
0x18001611f  jnz     short loc_180016136
0x180016121  mov     r8d, 1Dh
0x180016127  lea     rdx, PSFRAG_setupmatrix; "mysetup concat colspRefresh\r\n"
0x18001612e  mov     rcx, rbx
0x180016131  call    OPRawPortWrite
0x180016136  xor     r8d, r8d
0x180016139  mov     rcx, rbx
0x18001613c  lea     edx, [r8+3]
0x180016140  call    VMCheck
0x180016145  mov     edx, 17h
0x18001614a  mov     rcx, rbx
0x18001614d  call    PSProcsetSend
0x180016152  mov     r8d, 30h ; '0'
0x180016158  lea     rdx, PSFRAG_setupcompatmatrix; "Pscript_WinNT_Compat begin /$x mysetup "...
0x18001615f  mov     rcx, rbx
0x180016162  call    OPRawPortWrite
0x180016167  test    byte ptr [rbx+84h], 10h
0x18001616e  jnz     short loc_18001618C
0x180016170  mov     rax, [rbx+60h]
0x180016174  test    dword ptr [rax+7Ch], 0FFFFFFFDh
0x18001617b  jnz     short loc_18001618C
0x18001617d  lea     rdx, PSFRAG_suspendincrdict; "Pscript_WinNT_Incr dup /suspend get exe"...
0x180016184  mov     r8d, 2Ah ; '*'
0x18001618a  jmp     short loc_180016199
0x18001618c  lea     rdx, PSFRAG_suspendfulldict; "/Pscript_WinNT_Full /ProcSet findresour"...
0x180016193  mov     r8d, 41h ; 'A'
0x180016199  mov     rcx, rbx
0x18001619c  call    OPRawPortWrite
0x1800161a1  test    byte ptr [rbx+868h], 2
0x1800161a8  jnz     short loc_1800161C6
0x1800161aa  mov     r8d, 2Fh ; '/'
0x1800161b0  lea     rdx, PSFRAG_initcompatdict; "Pscript_WinNT_Compat dup /initialize ge"...
0x1800161b7  mov     rcx, rbx
0x1800161ba  call    OPRawPortWrite
0x1800161bf  or      dword ptr [rbx+868h], 2
0x1800161c6  mov     rax, [rbx+2F0h]
0x1800161cd  or      dword ptr [rax], 2
0x1800161d0  lea     rdx, DSC_BeginDocument; "%%%%BeginDocument: Pscript_Win_PassThro"...
0x1800161d7  mov     rcx, rbx
0x1800161da  call    DSCSend
0x1800161df  xor     eax, eax
0x1800161e1  cmp     [rbx+0D70h], eax
0x1800161e7  setz    al
0x1800161ea  add     rsp, 20h
0x1800161ee  pop     rbx
0x1800161ef  retn
```
