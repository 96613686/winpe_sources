# JCRawPrinterStart

- ea: `0x180015994`
- end: `0x180015ad4`
- name: `JCRawPrinterStart`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001283c`

## callees

- `0x180011ae8`
- `0x18001247c`
- `0x180015994`
- `0x180015adc`
- `0x180015f84`
- `0x180016940`
- `0x18001a6fc`
- `0x18001a874`
- `0x18001aa48`

## string_xrefs

- `0x180015a3c`: `Pscript_WinNT_Compat begin /$x mysetup def end\n`
- `0x180015a94`: `Pscript_WinNT_Compat dup /initialize get exec\n`

## pseudocode

```c
_BOOL8 __fastcall JCRawPrinterStart(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // rax
  const char *v4; // rdx
  __int64 v5; // r8

  if ( *(int *)(a1 + 2152) >= 0 )
  {
    GSEndOptimization();
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
        OPRawPortWrite(a1, "mysetup concat colspRefresh\r\n", 29);
    }
    VMCheck(a1, 3);
    PSProcsetSend(a1, 23);
    OPRawPortWrite(a1, "Pscript_WinNT_Compat begin /$x mysetup def end\r\n", 48);
    if ( (*(_BYTE *)(a1 + 132) & 0x10) != 0 || (*(_DWORD *)(*(_QWORD *)(a1 + 96) + 124LL) & 0xFFFFFFFD) != 0 )
    {
      v4 = "/Pscript_WinNT_Full /ProcSet findresource dup /suspend get exec\r\n";
      v5 = 65;
    }
    else
    {
      v4 = "Pscript_WinNT_Incr dup /suspend get exec\r\n";
      v5 = 42;
    }
    OPRawPortWrite(a1, v4, v5);
    if ( (*(_BYTE *)(a1 + 2152) & 2) == 0 )
    {
      OPRawPortWrite(a1, "Pscript_WinNT_Compat dup /initialize get exec\r\n", 47);
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
0x180015994  push    rbx
0x180015996  sub     rsp, 20h
0x18001599a  cmp     dword ptr [rcx+868h], 0
0x1800159a1  mov     rbx, rcx
0x1800159a4  jl      loc_180015AB4
0x1800159aa  call    GSEndOptimization
0x1800159af  mov     rax, [rbx+60h]
0x1800159b3  cmp     dword ptr [rax+8Ch], 1
0x1800159ba  jnz     short loc_180015A1A
0x1800159bc  test    byte ptr [rbx+8BCh], 4
0x1800159c3  jnz     short loc_180015A1A
0x1800159c5  mov     rcx, rbx
0x1800159c8  call    VMRestoreLevel1
0x1800159cd  mov     rax, [rbx+60h]
0x1800159d1  cmp     dword ptr [rax+7Ch], 0
0x1800159d5  jnz     short loc_1800159F4
0x1800159d7  mov     eax, [rax+88h]
0x1800159dd  dec     eax
0x1800159df  cmp     eax, 4
0x1800159e2  ja      short loc_1800159F4
0x1800159e4  mov     rcx, rbx
0x1800159e7  call    JCSendNup
0x1800159ec  mov     rcx, rbx
0x1800159ef  call    GSSendGsave
0x1800159f4  mov     rax, [rbx+60h]
0x1800159f8  or      dword ptr [rbx+8BCh], 4
0x1800159ff  cmp     dword ptr [rax+7Ch], 0
0x180015a03  jnz     short loc_180015A1A
0x180015a05  mov     r8d, 1Dh
0x180015a0b  lea     rdx, PSFRAG_setupmatrix; "mysetup concat colspRefresh\r\n"
0x180015a12  mov     rcx, rbx
0x180015a15  call    OPRawPortWrite
0x180015a1a  xor     r8d, r8d
0x180015a1d  mov     rcx, rbx
0x180015a20  lea     edx, [r8+3]
0x180015a24  call    VMCheck
0x180015a29  mov     edx, 17h
0x180015a2e  mov     rcx, rbx
0x180015a31  call    PSProcsetSend
0x180015a36  mov     r8d, 30h ; '0'
0x180015a3c  lea     rdx, PSFRAG_setupcompatmatrix; "Pscript_WinNT_Compat begin /$x mysetup "...
0x180015a43  mov     rcx, rbx
0x180015a46  call    OPRawPortWrite
0x180015a4b  test    byte ptr [rbx+84h], 10h
0x180015a52  jnz     short loc_180015A70
0x180015a54  mov     rax, [rbx+60h]
0x180015a58  test    dword ptr [rax+7Ch], 0FFFFFFFDh
0x180015a5f  jnz     short loc_180015A70
0x180015a61  lea     rdx, PSFRAG_suspendincrdict; "Pscript_WinNT_Incr dup /suspend get exe"...
0x180015a68  mov     r8d, 2Ah ; '*'
0x180015a6e  jmp     short loc_180015A7D
0x180015a70  lea     rdx, PSFRAG_suspendfulldict; "/Pscript_WinNT_Full /ProcSet findresour"...
0x180015a77  mov     r8d, 41h ; 'A'
0x180015a7d  mov     rcx, rbx
0x180015a80  call    OPRawPortWrite
0x180015a85  test    byte ptr [rbx+868h], 2
0x180015a8c  jnz     short loc_180015AAA
0x180015a8e  mov     r8d, 2Fh ; '/'
0x180015a94  lea     rdx, PSFRAG_initcompatdict; "Pscript_WinNT_Compat dup /initialize ge"...
0x180015a9b  mov     rcx, rbx
0x180015a9e  call    OPRawPortWrite
0x180015aa3  or      dword ptr [rbx+868h], 2
0x180015aaa  mov     rax, [rbx+2F0h]
0x180015ab1  or      dword ptr [rax], 2
0x180015ab4  lea     rdx, DSC_BeginDocument; "%%%%BeginDocument: Pscript_Win_PassThro"...
0x180015abb  mov     rcx, rbx
0x180015abe  call    DSCSend
0x180015ac3  xor     eax, eax
0x180015ac5  cmp     [rbx+0D70h], eax
0x180015acb  setz    al
0x180015ace  add     rsp, 20h
0x180015ad2  pop     rbx
0x180015ad3  retn
```
