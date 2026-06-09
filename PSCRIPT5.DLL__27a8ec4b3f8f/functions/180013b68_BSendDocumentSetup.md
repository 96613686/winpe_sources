# BSendDocumentSetup

- ea: `0x180013b68`
- end: `0x180013f47`
- name: `BSendDocumentSetup`
- size: `991`
- prototype: `_BOOL8 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001502c`

## callees

- `0x180013b68`
- `0x180013f50`
- `0x180014434`
- `0x1800148c4`
- `0x180014c4c`
- `0x1800170a0`
- `0x180017340`
- `0x18001b388`

## string_xrefs

- `0x180013c17`: `Pscript_WinNT_Compat dup /initialize get exec\n`

## pseudocode

```c
_BOOL8 __fastcall BSendDocumentSetup(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rax
  __int64 v4; // rax
  int v5; // ecx
  int v6; // ebp
  __int64 v7; // rdi
  __int64 v8; // rsi

  v2 = *(_QWORD *)(a1 + 2144);
  v3 = *(unsigned int *)(v2 + 200);
  if ( (_DWORD)v3 )
    v4 = *(_QWORD *)(a1 + 2128) + v3;
  else
    v4 = 0;
  v5 = *(_DWORD *)(v2 + 196);
  if ( v5 )
  {
    while ( *(_DWORD *)(v4 + 4) != 64 )
    {
      v4 += 24;
      if ( !--v5 )
        goto LABEL_7;
    }
    v6 = 1;
  }
  else
  {
LABEL_7:
    v6 = 0;
  }
  DSCSend(a1, (const char *)0x10);
  v7 = a1 + 96;
  if ( *(int *)(a1 + 2152) >= 0 )
  {
    if ( *(_DWORD *)(*(_QWORD *)v7 + 124LL) != 2 )
      DSCSend(a1, "statusdict begin (%%%%[ ProductName: ) print product print ( ]%%%%)= flush end\r\n");
    if ( (*(_DWORD *)(*(_QWORD *)v7 + 124LL) & 0xFFFFFFFD) != 0 )
    {
      OPRawPortWrite(a1, "Pscript_WinNT_Compat dup /initialize get exec\r\n", 0x2Fu);
      *(_DWORD *)(a1 + 2152) |= 2u;
    }
    v8 = a1 + 88;
    BSendOrientationMatrix(
      a1,
      (*(__int16 *)(*(_QWORD *)(a1 + 88) + 84LL) << 8) / 100,
      (*(__int16 *)(*(_QWORD *)(a1 + 88) + 84LL) << 8) / 100);
    if ( (*(_DWORD *)(*(_QWORD *)v7 + 124LL) & 0xFFFFFFFD) != 0 )
      OPRawPortWrite(a1, "false /Pscript_WinNT_Full /ProcSet findresource dup /initialize get exec\r\n", 0x4Au);
    else
      OPRawPortWrite(a1, "false Pscript_WinNT_Incr dup /initialize get exec\r\n", 0x33u);
  }
  else
  {
    v8 = a1 + 88;
    OPRawPortWrite(a1, "Pscript_WinNT_Min dup /min_initialize get exec\r\n", 0x30u);
  }
  if ( (unsigned int)(*(_DWORD *)(*(_QWORD *)v7 + 124LL) - 2) > 1 )
  {
    OPRawPortWrite(a1, "featurebegin{\r\n", 0xFu);
    DSCSend(a1, "%%%%BeginNonPPDFeature: ");
    DSCSend(a1, "JobTimeout %d\r\n", *(_DWORD *)(a1 + 140));
    OPSendInt(a1, *(_DWORD *)(a1 + 140));
    OPRawPortWrite(
      a1,
      "/languagelevel where{pop languagelevel}{1}ifelse 2 ge{1 dict dup/JobTimeout  4 -1 roll put setuserparams}{statusdi"
      "ct/setjobtimeout get exec}ifelse\r\n",
      0x94u);
    DSCSend(a1, "%%%%EndNonPPDFeature\r\n");
    OPRawPortWrite(a1, "}featurecleanup\r\n", 0x11u);
    OPRawPortWrite(a1, "\r\n", 2u);
    OPRawPortWrite(a1, "featurebegin{\r\n", 0xFu);
    DSCSend(a1, "%%%%BeginNonPPDFeature: ");
    DSCSend(a1, "WaitTimeout %d\r\n", *(_DWORD *)(a1 + 144));
    OPSendInt(a1, *(_DWORD *)(a1 + 144));
    OPRawPortWrite(
      a1,
      "/languagelevel where{pop languagelevel}{1}ifelse 2 ge{1 dict dup/WaitTimeout 4 -1 roll put setuserparams}{statusdi"
      "ct/waittimeout 3 -1 roll put}ifelse\r\n",
      0x97u);
    DSCSend(a1, "%%%%EndNonPPDFeature\r\n");
    OPRawPortWrite(a1, "}featurecleanup\r\n", 0x11u);
    OPRawPortWrite(a1, "\r\n", 2u);
    if ( *(__int16 *)(*(_QWORD *)v8 + 86LL) > 1 )
    {
      OPRawPortWrite(a1, "featurebegin{\r\n", 0xFu);
      DSCSend(a1, "%%%%BeginNonPPDFeature: ");
      DSCSend(a1, "NumCopies %d\r\n", *(__int16 *)(*(_QWORD *)v8 + 86LL));
      OPSendInt(a1, *(__int16 *)(*(_QWORD *)v8 + 86LL));
      OPRawPortWrite(
        a1,
        " /languagelevel where {pop languagelevel}{1} ifelse\r\n"
        "2 ge { 1 dict dup /NumCopies 4 -1 roll put setpagedevice }{ userdict /#copies 3 -1 roll put } ifelse\r\n",
        0x9Bu);
      DSCSend(a1, "%%%%EndNonPPDFeature\r\n");
      OPRawPortWrite(a1, "}featurecleanup\r\n", 0x11u);
      OPRawPortWrite(a1, "\r\n", 2u);
    }
    BSendFeatures(a1, 32, 0);
    if ( *(int *)(a1 + 2152) < 0 && !*(_DWORD *)(a1 + 3668) )
    {
      if ( v6 )
        BSendFeatures(a1, 64, 0);
      goto LABEL_26;
    }
    if ( !v6 )
LABEL_26:
      BSendFeatures(a1, 8, 0);
  }
  OPRawPortWrite(a1, "1 setlinecap 1 setlinejoin\r\n", 0x1Cu);
  BSendMysetup(a1);
  if ( (unsigned int)(*(_DWORD *)(*(_QWORD *)v7 + 136LL) - 1) <= 4 && *(_DWORD *)(*(_QWORD *)v7 + 124LL) != 2 )
    BSendNupMatrix(a1);
  if ( *(int *)(a1 + 2152) < 0 && !*(_DWORD *)(a1 + 3668) )
    OPRawPortWrite(a1, "mysetup concat colspRefresh\r\n", 0x1Du);
  if ( (*(_BYTE *)(*(_QWORD *)v7 + 4LL) & 0x10) != 0 )
    OPRawPortWrite(a1, "userdict (OriginalTransferFunc) 1 currenttransfer exec put\r\n", 0x3Cu);
  DSCSend(a1, (const char *)0x11);
  return *(_DWORD *)(a1 + 3440) == 0;
}

```

## disassembly

```asm
0x180013b68  push    rbx
0x180013b6a  push    rbp
0x180013b6b  push    rsi
0x180013b6c  push    rdi
0x180013b6d  push    r12
0x180013b6f  push    r13
0x180013b71  sub     rsp, 28h
0x180013b75  mov     rbx, rcx
0x180013b78  mov     rcx, [rcx+860h]
0x180013b7f  mov     eax, [rcx+0C8h]
0x180013b85  test    eax, eax
0x180013b87  jz      short loc_180013B92
0x180013b89  add     rax, [rbx+850h]
0x180013b90  jmp     short loc_180013B94
0x180013b92  xor     eax, eax
0x180013b94  mov     ecx, [rcx+0C4h]
0x180013b9a  mov     r12d, 1
0x180013ba0  test    ecx, ecx
0x180013ba2  jz      short loc_180013BB3
0x180013ba4  cmp     dword ptr [rax+4], 40h ; '@'
0x180013ba8  jz      short loc_180013BE5
0x180013baa  add     rax, 18h
0x180013bae  add     ecx, 0FFFFFFFFh
0x180013bb1  jnz     short loc_180013BA4
0x180013bb3  xor     ebp, ebp
0x180013bb5  mov     edx, 10h
0x180013bba  mov     rcx, rbx
0x180013bbd  call    DSCSend
0x180013bc2  cmp     dword ptr [rbx+868h], 0
0x180013bc9  lea     rdi, [rbx+60h]
0x180013bcd  jge     short loc_180013BEA
0x180013bcf  lea     rdx, PSFRAG_initminhdrdict; "Pscript_WinNT_Min dup /min_initialize g"...
0x180013bd6  mov     r8d, 30h ; '0'
0x180013bdc  lea     rsi, [rbx+58h]
0x180013be0  jmp     loc_180013C7C
0x180013be5  mov     ebp, r12d
0x180013be8  jmp     short loc_180013BB5
0x180013bea  mov     rax, [rdi]
0x180013bed  cmp     dword ptr [rax+7Ch], 2
0x180013bf1  jz      short loc_180013C02
0x180013bf3  lea     rdx, DSC_ProductName; "statusdict begin (%%%%[ ProductName: ) "...
0x180013bfa  mov     rcx, rbx
0x180013bfd  call    DSCSend
0x180013c02  mov     rax, [rdi]
0x180013c05  mov     r13d, 0FFFFFFFDh
0x180013c0b  test    [rax+7Ch], r13d
0x180013c0f  jz      short loc_180013C2D
0x180013c11  mov     r8d, 2Fh ; '/'
0x180013c17  lea     rdx, PSFRAG_initcompatdict; "Pscript_WinNT_Compat dup /initialize ge"...
0x180013c1e  mov     rcx, rbx
0x180013c21  call    OPRawPortWrite
0x180013c26  or      dword ptr [rbx+868h], 2
0x180013c2d  lea     rsi, [rbx+58h]
0x180013c31  mov     rax, [rsi]
0x180013c34  movsx   ecx, word ptr [rax+54h]
0x180013c38  mov     eax, 51EB851Fh
0x180013c3d  shl     ecx, 8
0x180013c40  imul    ecx
0x180013c42  mov     rcx, rbx
0x180013c45  sar     edx, 5
0x180013c48  mov     eax, edx
0x180013c4a  shr     eax, 1Fh
0x180013c4d  add     edx, eax
0x180013c4f  mov     r8d, edx
0x180013c52  call    BSendOrientationMatrix
0x180013c57  mov     rax, [rdi]
0x180013c5a  test    [rax+7Ch], r13d
0x180013c5e  jz      short loc_180013C6F
0x180013c60  lea     rdx, PSFRAG_initfulldict; "false /Pscript_WinNT_Full /ProcSet find"...
0x180013c67  mov     r8d, 4Ah ; 'J'
0x180013c6d  jmp     short loc_180013C7C
0x180013c6f  lea     rdx, PSFRAG_initincrdict; "false Pscript_WinNT_Incr dup /initializ"...
0x180013c76  mov     r8d, 33h ; '3'
0x180013c7c  mov     rcx, rbx
0x180013c7f  call    OPRawPortWrite
0x180013c84  mov     rax, [rdi]
0x180013c87  mov     r13d, 11h
0x180013c8d  mov     ecx, [rax+7Ch]
0x180013c90  sub     ecx, 2
0x180013c93  cmp     ecx, r12d
0x180013c96  jbe     loc_180013EA2
0x180013c9c  lea     r8d, [r13-2]
0x180013ca0  mov     rcx, rbx
0x180013ca3  lea     rdx, PSFRAG_beginsafe; "featurebegin{\r\n"
0x180013caa  call    OPRawPortWrite
0x180013caf  lea     rdx, DSC_BeginNonPPDFeature; "%%%%BeginNonPPDFeature: "
0x180013cb6  mov     rcx, rbx
0x180013cb9  call    DSCSend
0x180013cbe  mov     r8d, [rbx+8Ch]
0x180013cc5  lea     rdx, DSC_JobTimeout; "JobTimeout %d\r\n"
0x180013ccc  mov     rcx, rbx
0x180013ccf  call    DSCSend
0x180013cd4  mov     edx, [rbx+8Ch]
0x180013cda  mov     rcx, rbx
0x180013cdd  call    OPSendInt
0x180013ce2  mov     r8d, 94h
0x180013ce8  lea     rdx, PSFRAG_jobtimeout; "/languagelevel where{pop languagelevel}"...
0x180013cef  mov     rcx, rbx
0x180013cf2  call    OPRawPortWrite
0x180013cf7  lea     rdx, DSC_EndNonPPDFeature; "%%%%EndNonPPDFeature\r\n"
0x180013cfe  mov     rcx, rbx
0x180013d01  call    DSCSend
0x180013d06  mov     r8d, r13d
0x180013d09  lea     rdx, PSFRAG_endsafe; "}featurecleanup\r\n"
0x180013d10  mov     rcx, rbx
0x180013d13  call    OPRawPortWrite
0x180013d18  lea     r8d, [r13-0Fh]
0x180013d1c  mov     rcx, rbx
0x180013d1f  lea     rdx, gstrCRLF; "\r\n"
0x180013d26  call    OPRawPortWrite
0x180013d2b  lea     r8d, [r13-2]
0x180013d2f  mov     rcx, rbx
0x180013d32  lea     rdx, PSFRAG_beginsafe; "featurebegin{\r\n"
0x180013d39  call    OPRawPortWrite
0x180013d3e  lea     rdx, DSC_BeginNonPPDFeature; "%%%%BeginNonPPDFeature: "
0x180013d45  mov     rcx, rbx
0x180013d48  call    DSCSend
0x180013d4d  mov     r8d, [rbx+90h]
0x180013d54  lea     rdx, DSC_WaitTimeout; "WaitTimeout %d\r\n"
0x180013d5b  mov     rcx, rbx
0x180013d5e  call    DSCSend
0x180013d63  mov     edx, [rbx+90h]
0x180013d69  mov     rcx, rbx
0x180013d6c  call    OPSendInt
0x180013d71  mov     r8d, 97h
0x180013d77  lea     rdx, PSFRAG_waittimeout; "/languagelevel where{pop languagelevel}"...
0x180013d7e  mov     rcx, rbx
0x180013d81  call    OPRawPortWrite
0x180013d86  lea     rdx, DSC_EndNonPPDFeature; "%%%%EndNonPPDFeature\r\n"
0x180013d8d  mov     rcx, rbx
0x180013d90  call    DSCSend
0x180013d95  mov     r8d, r13d
0x180013d98  lea     rdx, PSFRAG_endsafe; "}featurecleanup\r\n"
0x180013d9f  mov     rcx, rbx
0x180013da2  call    OPRawPortWrite
0x180013da7  lea     r8d, [r13-0Fh]
0x180013dab  mov     rcx, rbx
0x180013dae  lea     rdx, gstrCRLF; "\r\n"
0x180013db5  call    OPRawPortWrite
0x180013dba  mov     rax, [rsi]
0x180013dbd  cmp     [rax+56h], r12w
0x180013dc2  jle     loc_180013E59
0x180013dc8  lea     r8d, [r13-2]
0x180013dcc  mov     rcx, rbx
0x180013dcf  lea     rdx, PSFRAG_beginsafe; "featurebegin{\r\n"
0x180013dd6  call    OPRawPortWrite
0x180013ddb  lea     rdx, DSC_BeginNonPPDFeature; "%%%%BeginNonPPDFeature: "
0x180013de2  mov     rcx, rbx
0x180013de5  call    DSCSend
0x180013dea  mov     rax, [rsi]
0x180013ded  lea     rdx, DSC_NumCopies; "NumCopies %d\r\n"
0x180013df4  mov     rcx, rbx
0x180013df7  movsx   r8d, word ptr [rax+56h]
0x180013dfc  call    DSCSend
0x180013e01  mov     rax, [rsi]
0x180013e04  mov     rcx, rbx
0x180013e07  movsx   edx, word ptr [rax+56h]
0x180013e0b  call    OPSendInt
0x180013e10  mov     r8d, 9Bh
0x180013e16  lea     rdx, PSFRAG_copies; " /languagelevel where {pop languageleve"...
0x180013e1d  mov     rcx, rbx
0x180013e20  call    OPRawPortWrite
0x180013e25  lea     rdx, DSC_EndNonPPDFeature; "%%%%EndNonPPDFeature\r\n"
0x180013e2c  mov     rcx, rbx
0x180013e2f  call    DSCSend
0x180013e34  mov     r8d, r13d
0x180013e37  lea     rdx, PSFRAG_endsafe; "}featurecleanup\r\n"
0x180013e3e  mov     rcx, rbx
0x180013e41  call    OPRawPortWrite
0x180013e46  lea     r8d, [r13-0Fh]
0x180013e4a  mov     rcx, rbx
0x180013e4d  lea     rdx, gstrCRLF; "\r\n"
0x180013e54  call    OPRawPortWrite
0x180013e59  xor     r8d, r8d
0x180013e5c  mov     rcx, rbx
0x180013e5f  lea     edx, [r8+20h]
0x180013e63  call    BSendFeatures
0x180013e68  cmp     dword ptr [rbx+868h], 0
0x180013e6f  jge     short loc_180013E8F
0x180013e71  cmp     dword ptr [rbx+0E54h], 0
0x180013e78  jnz     short loc_180013E8F
0x180013e7a  test    ebp, ebp
0x180013e7c  jz      short loc_180013E93
0x180013e7e  xor     r8d, r8d
0x180013e81  mov     rcx, rbx
0x180013e84  lea     edx, [r8+40h]
0x180013e88  call    BSendFeatures
0x180013e8d  jmp     short loc_180013E93
0x180013e8f  test    ebp, ebp
0x180013e91  jnz     short loc_180013EA2
0x180013e93  xor     r8d, r8d
0x180013e96  mov     rcx, rbx
0x180013e99  lea     edx, [r8+8]
0x180013e9d  call    BSendFeatures
0x180013ea2  mov     r8d, 1Ch
0x180013ea8  lea     rdx, PSFRAG_linedefaults; "1 setlinecap 1 setlinejoin\r\n"
0x180013eaf  mov     rcx, rbx
0x180013eb2  call    OPRawPortWrite
0x180013eb7  mov     rcx, rbx
0x180013eba  call    BSendMysetup
0x180013ebf  mov     rcx, [rdi]
0x180013ec2  mov     eax, [rcx+88h]
0x180013ec8  sub     eax, r12d
0x180013ecb  cmp     eax, 4
0x180013ece  ja      short loc_180013EDE
0x180013ed0  cmp     dword ptr [rcx+7Ch], 2
0x180013ed4  jz      short loc_180013EDE
0x180013ed6  mov     rcx, rbx
0x180013ed9  call    BSendNupMatrix
0x180013ede  cmp     dword ptr [rbx+868h], 0
0x180013ee5  jge     short loc_180013F05
0x180013ee7  cmp     dword ptr [rbx+0E54h], 0
0x180013eee  jnz     short loc_180013F05
0x180013ef0  mov     r8d, 1Dh
0x180013ef6  lea     rdx, PSFRAG_setupmatrix; "mysetup concat colspRefresh\r\n"
0x180013efd  mov     rcx, rbx
0x180013f00  call    OPRawPortWrite
0x180013f05  mov     rax, [rdi]
0x180013f08  test    byte ptr [rax+4], 10h
0x180013f0c  jz      short loc_180013F23
0x180013f0e  mov     r8d, 3Ch ; '<'
0x180013f14  lea     rdx, PSFRAG_setupnegativeimage; "userdict (OriginalTransferFunc) 1 curre"...
0x180013f1b  mov     rcx, rbx
0x180013f1e  call    OPRawPortWrite
0x180013f23  mov     rdx, r13
0x180013f26  mov     rcx, rbx
0x180013f29  call    DSCSend
0x180013f2e  xor     eax, eax
0x180013f30  cmp     [rbx+0D70h], eax
0x180013f36  setz    al
0x180013f39  add     rsp, 28h
0x180013f3d  pop     r13
0x180013f3f  pop     r12
0x180013f41  pop     rdi
0x180013f42  pop     rsi
0x180013f43  pop     rbp
0x180013f44  pop     rbx
0x180013f45  retn
```
