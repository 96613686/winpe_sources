# BSendDocumentSetup

- ea: `0x180013500`
- end: `0x1800138de`
- name: `BSendDocumentSetup`
- size: `990`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180014988`

## callees

- `0x180013500`
- `0x1800138e4`
- `0x180013dbc`
- `0x180014238`
- `0x1800145ac`
- `0x180016940`
- `0x180016bdc`
- `0x18001aa48`

## string_xrefs

- `0x1800135af`: `Pscript_WinNT_Compat dup /initialize get exec\n`

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
  const char *v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rsi

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
      OPRawPortWrite(a1, "Pscript_WinNT_Compat dup /initialize get exec\r\n", 47);
      *(_DWORD *)(a1 + 2152) |= 2u;
    }
    v10 = a1 + 88;
    BSendOrientationMatrix(
      a1,
      (unsigned int)((*(__int16 *)(*(_QWORD *)(a1 + 88) + 84LL) << 8) / 100),
      (unsigned int)((*(__int16 *)(*(_QWORD *)(a1 + 88) + 84LL) << 8) / 100));
    if ( (*(_DWORD *)(*(_QWORD *)v7 + 124LL) & 0xFFFFFFFD) != 0 )
    {
      v8 = "false /Pscript_WinNT_Full /ProcSet findresource dup /initialize get exec\r\n";
      v9 = 74;
    }
    else
    {
      v8 = "false Pscript_WinNT_Incr dup /initialize get exec\r\n";
      v9 = 51;
    }
  }
  else
  {
    v8 = "Pscript_WinNT_Min dup /min_initialize get exec\r\n";
    v9 = 48;
    v10 = a1 + 88;
  }
  OPRawPortWrite(a1, v8, v9);
  if ( (unsigned int)(*(_DWORD *)(*(_QWORD *)v7 + 124LL) - 2) > 1 )
  {
    OPRawPortWrite(a1, "featurebegin{\r\n", 15);
    DSCSend(a1, "%%%%BeginNonPPDFeature: ");
    DSCSend(a1, "JobTimeout %d\r\n", *(_DWORD *)(a1 + 140));
    OPSendInt(a1, *(unsigned int *)(a1 + 140));
    OPRawPortWrite(
      a1,
      "/languagelevel where{pop languagelevel}{1}ifelse 2 ge{1 dict dup/JobTimeout  4 -1 roll put setuserparams}{statusdi"
      "ct/setjobtimeout get exec}ifelse\r\n",
      148);
    DSCSend(a1, "%%%%EndNonPPDFeature\r\n");
    OPRawPortWrite(a1, "}featurecleanup\r\n", 17);
    OPRawPortWrite(a1, "\r\n", 2);
    OPRawPortWrite(a1, "featurebegin{\r\n", 15);
    DSCSend(a1, "%%%%BeginNonPPDFeature: ");
    DSCSend(a1, "WaitTimeout %d\r\n", *(_DWORD *)(a1 + 144));
    OPSendInt(a1, *(unsigned int *)(a1 + 144));
    OPRawPortWrite(
      a1,
      "/languagelevel where{pop languagelevel}{1}ifelse 2 ge{1 dict dup/WaitTimeout 4 -1 roll put setuserparams}{statusdi"
      "ct/waittimeout 3 -1 roll put}ifelse\r\n",
      151);
    DSCSend(a1, "%%%%EndNonPPDFeature\r\n");
    OPRawPortWrite(a1, "}featurecleanup\r\n", 17);
    OPRawPortWrite(a1, "\r\n", 2);
    if ( *(__int16 *)(*(_QWORD *)v10 + 86LL) > 1 )
    {
      OPRawPortWrite(a1, "featurebegin{\r\n", 15);
      DSCSend(a1, "%%%%BeginNonPPDFeature: ");
      DSCSend(a1, "NumCopies %d\r\n", *(__int16 *)(*(_QWORD *)v10 + 86LL));
      OPSendInt(a1, (unsigned int)*(__int16 *)(*(_QWORD *)v10 + 86LL));
      OPRawPortWrite(
        a1,
        " /languagelevel where {pop languagelevel}{1} ifelse\r\n"
        "2 ge { 1 dict dup /NumCopies 4 -1 roll put setpagedevice }{ userdict /#copies 3 -1 roll put } ifelse\r\n",
        155);
      DSCSend(a1, "%%%%EndNonPPDFeature\r\n");
      OPRawPortWrite(a1, "}featurecleanup\r\n", 17);
      OPRawPortWrite(a1, "\r\n", 2);
    }
    BSendFeatures(a1, 32);
    if ( *(int *)(a1 + 2152) < 0 && !*(_DWORD *)(a1 + 3668) )
    {
      if ( v6 )
        BSendFeatures(a1, 64);
      goto LABEL_26;
    }
    if ( !v6 )
LABEL_26:
      BSendFeatures(a1, 8);
  }
  OPRawPortWrite(a1, "1 setlinecap 1 setlinejoin\r\n", 28);
  BSendMysetup(a1);
  if ( (unsigned int)(*(_DWORD *)(*(_QWORD *)v7 + 136LL) - 1) <= 4 && *(_DWORD *)(*(_QWORD *)v7 + 124LL) != 2 )
    BSendNupMatrix(a1);
  if ( *(int *)(a1 + 2152) < 0 && !*(_DWORD *)(a1 + 3668) )
    OPRawPortWrite(a1, "mysetup concat colspRefresh\r\n", 29);
  if ( (*(_BYTE *)(*(_QWORD *)v7 + 4LL) & 0x10) != 0 )
    OPRawPortWrite(a1, "userdict (OriginalTransferFunc) 1 currenttransfer exec put\r\n", 60);
  DSCSend(a1, (const char *)0x11);
  return *(_DWORD *)(a1 + 3440) == 0;
}

```

## disassembly

```asm
0x180013500  push    rbx
0x180013502  push    rbp
0x180013503  push    rsi
0x180013504  push    rdi
0x180013505  push    r12
0x180013507  push    r13
0x180013509  sub     rsp, 28h
0x18001350d  mov     rbx, rcx
0x180013510  mov     rcx, [rcx+860h]
0x180013517  mov     eax, [rcx+0C8h]
0x18001351d  test    eax, eax
0x18001351f  jz      short loc_18001352A
0x180013521  add     rax, [rbx+850h]
0x180013528  jmp     short loc_18001352C
0x18001352a  xor     eax, eax
0x18001352c  mov     ecx, [rcx+0C4h]
0x180013532  mov     r12d, 1
0x180013538  test    ecx, ecx
0x18001353a  jz      short loc_18001354B
0x18001353c  cmp     dword ptr [rax+4], 40h ; '@'
0x180013540  jz      short loc_18001357D
0x180013542  add     rax, 18h
0x180013546  add     ecx, 0FFFFFFFFh
0x180013549  jnz     short loc_18001353C
0x18001354b  xor     ebp, ebp
0x18001354d  mov     edx, 10h
0x180013552  mov     rcx, rbx
0x180013555  call    DSCSend
0x18001355a  cmp     dword ptr [rbx+868h], 0
0x180013561  lea     rdi, [rbx+60h]
0x180013565  jge     short loc_180013582
0x180013567  lea     rdx, PSFRAG_initminhdrdict; "Pscript_WinNT_Min dup /min_initialize g"...
0x18001356e  mov     r8d, 30h ; '0'
0x180013574  lea     rsi, [rbx+58h]
0x180013578  jmp     loc_180013614
0x18001357d  mov     ebp, r12d
0x180013580  jmp     short loc_18001354D
0x180013582  mov     rax, [rdi]
0x180013585  cmp     dword ptr [rax+7Ch], 2
0x180013589  jz      short loc_18001359A
0x18001358b  lea     rdx, DSC_ProductName; "statusdict begin (%%%%[ ProductName: ) "...
0x180013592  mov     rcx, rbx
0x180013595  call    DSCSend
0x18001359a  mov     rax, [rdi]
0x18001359d  mov     r13d, 0FFFFFFFDh
0x1800135a3  test    [rax+7Ch], r13d
0x1800135a7  jz      short loc_1800135C5
0x1800135a9  mov     r8d, 2Fh ; '/'
0x1800135af  lea     rdx, PSFRAG_initcompatdict; "Pscript_WinNT_Compat dup /initialize ge"...
0x1800135b6  mov     rcx, rbx
0x1800135b9  call    OPRawPortWrite
0x1800135be  or      dword ptr [rbx+868h], 2
0x1800135c5  lea     rsi, [rbx+58h]
0x1800135c9  mov     rax, [rsi]
0x1800135cc  movsx   ecx, word ptr [rax+54h]
0x1800135d0  mov     eax, 51EB851Fh
0x1800135d5  shl     ecx, 8
0x1800135d8  imul    ecx
0x1800135da  mov     rcx, rbx
0x1800135dd  sar     edx, 5
0x1800135e0  mov     eax, edx
0x1800135e2  shr     eax, 1Fh
0x1800135e5  add     edx, eax
0x1800135e7  mov     r8d, edx
0x1800135ea  call    BSendOrientationMatrix
0x1800135ef  mov     rax, [rdi]
0x1800135f2  test    [rax+7Ch], r13d
0x1800135f6  jz      short loc_180013607
0x1800135f8  lea     rdx, PSFRAG_initfulldict; "false /Pscript_WinNT_Full /ProcSet find"...
0x1800135ff  mov     r8d, 4Ah ; 'J'
0x180013605  jmp     short loc_180013614
0x180013607  lea     rdx, PSFRAG_initincrdict; "false Pscript_WinNT_Incr dup /initializ"...
0x18001360e  mov     r8d, 33h ; '3'
0x180013614  mov     rcx, rbx
0x180013617  call    OPRawPortWrite
0x18001361c  mov     rax, [rdi]
0x18001361f  mov     r13d, 11h
0x180013625  mov     ecx, [rax+7Ch]
0x180013628  sub     ecx, 2
0x18001362b  cmp     ecx, r12d
0x18001362e  jbe     loc_18001383A
0x180013634  lea     r8d, [r13-2]
0x180013638  mov     rcx, rbx
0x18001363b  lea     rdx, PSFRAG_beginsafe; "featurebegin{\r\n"
0x180013642  call    OPRawPortWrite
0x180013647  lea     rdx, DSC_BeginNonPPDFeature; "%%%%BeginNonPPDFeature: "
0x18001364e  mov     rcx, rbx
0x180013651  call    DSCSend
0x180013656  mov     r8d, [rbx+8Ch]
0x18001365d  lea     rdx, DSC_JobTimeout; "JobTimeout %d\r\n"
0x180013664  mov     rcx, rbx
0x180013667  call    DSCSend
0x18001366c  mov     edx, [rbx+8Ch]
0x180013672  mov     rcx, rbx
0x180013675  call    OPSendInt
0x18001367a  mov     r8d, 94h
0x180013680  lea     rdx, PSFRAG_jobtimeout; "/languagelevel where{pop languagelevel}"...
0x180013687  mov     rcx, rbx
0x18001368a  call    OPRawPortWrite
0x18001368f  lea     rdx, DSC_EndNonPPDFeature; "%%%%EndNonPPDFeature\r\n"
0x180013696  mov     rcx, rbx
0x180013699  call    DSCSend
0x18001369e  mov     r8d, r13d
0x1800136a1  lea     rdx, PSFRAG_endsafe; "}featurecleanup\r\n"
0x1800136a8  mov     rcx, rbx
0x1800136ab  call    OPRawPortWrite
0x1800136b0  lea     r8d, [r13-0Fh]
0x1800136b4  mov     rcx, rbx
0x1800136b7  lea     rdx, gstrCRLF; "\r\n"
0x1800136be  call    OPRawPortWrite
0x1800136c3  lea     r8d, [r13-2]
0x1800136c7  mov     rcx, rbx
0x1800136ca  lea     rdx, PSFRAG_beginsafe; "featurebegin{\r\n"
0x1800136d1  call    OPRawPortWrite
0x1800136d6  lea     rdx, DSC_BeginNonPPDFeature; "%%%%BeginNonPPDFeature: "
0x1800136dd  mov     rcx, rbx
0x1800136e0  call    DSCSend
0x1800136e5  mov     r8d, [rbx+90h]
0x1800136ec  lea     rdx, DSC_WaitTimeout; "WaitTimeout %d\r\n"
0x1800136f3  mov     rcx, rbx
0x1800136f6  call    DSCSend
0x1800136fb  mov     edx, [rbx+90h]
0x180013701  mov     rcx, rbx
0x180013704  call    OPSendInt
0x180013709  mov     r8d, 97h
0x18001370f  lea     rdx, PSFRAG_waittimeout; "/languagelevel where{pop languagelevel}"...
0x180013716  mov     rcx, rbx
0x180013719  call    OPRawPortWrite
0x18001371e  lea     rdx, DSC_EndNonPPDFeature; "%%%%EndNonPPDFeature\r\n"
0x180013725  mov     rcx, rbx
0x180013728  call    DSCSend
0x18001372d  mov     r8d, r13d
0x180013730  lea     rdx, PSFRAG_endsafe; "}featurecleanup\r\n"
0x180013737  mov     rcx, rbx
0x18001373a  call    OPRawPortWrite
0x18001373f  lea     r8d, [r13-0Fh]
0x180013743  mov     rcx, rbx
0x180013746  lea     rdx, gstrCRLF; "\r\n"
0x18001374d  call    OPRawPortWrite
0x180013752  mov     rax, [rsi]
0x180013755  cmp     [rax+56h], r12w
0x18001375a  jle     loc_1800137F1
0x180013760  lea     r8d, [r13-2]
0x180013764  mov     rcx, rbx
0x180013767  lea     rdx, PSFRAG_beginsafe; "featurebegin{\r\n"
0x18001376e  call    OPRawPortWrite
0x180013773  lea     rdx, DSC_BeginNonPPDFeature; "%%%%BeginNonPPDFeature: "
0x18001377a  mov     rcx, rbx
0x18001377d  call    DSCSend
0x180013782  mov     rax, [rsi]
0x180013785  lea     rdx, DSC_NumCopies; "NumCopies %d\r\n"
0x18001378c  mov     rcx, rbx
0x18001378f  movsx   r8d, word ptr [rax+56h]
0x180013794  call    DSCSend
0x180013799  mov     rax, [rsi]
0x18001379c  mov     rcx, rbx
0x18001379f  movsx   edx, word ptr [rax+56h]
0x1800137a3  call    OPSendInt
0x1800137a8  mov     r8d, 9Bh
0x1800137ae  lea     rdx, PSFRAG_copies; " /languagelevel where {pop languageleve"...
0x1800137b5  mov     rcx, rbx
0x1800137b8  call    OPRawPortWrite
0x1800137bd  lea     rdx, DSC_EndNonPPDFeature; "%%%%EndNonPPDFeature\r\n"
0x1800137c4  mov     rcx, rbx
0x1800137c7  call    DSCSend
0x1800137cc  mov     r8d, r13d
0x1800137cf  lea     rdx, PSFRAG_endsafe; "}featurecleanup\r\n"
0x1800137d6  mov     rcx, rbx
0x1800137d9  call    OPRawPortWrite
0x1800137de  lea     r8d, [r13-0Fh]
0x1800137e2  mov     rcx, rbx
0x1800137e5  lea     rdx, gstrCRLF; "\r\n"
0x1800137ec  call    OPRawPortWrite
0x1800137f1  xor     r8d, r8d
0x1800137f4  mov     rcx, rbx
0x1800137f7  lea     edx, [r8+20h]
0x1800137fb  call    BSendFeatures
0x180013800  cmp     dword ptr [rbx+868h], 0
0x180013807  jge     short loc_180013827
0x180013809  cmp     dword ptr [rbx+0E54h], 0
0x180013810  jnz     short loc_180013827
0x180013812  test    ebp, ebp
0x180013814  jz      short loc_18001382B
0x180013816  xor     r8d, r8d
0x180013819  mov     rcx, rbx
0x18001381c  lea     edx, [r8+40h]
0x180013820  call    BSendFeatures
0x180013825  jmp     short loc_18001382B
0x180013827  test    ebp, ebp
0x180013829  jnz     short loc_18001383A
0x18001382b  xor     r8d, r8d
0x18001382e  mov     rcx, rbx
0x180013831  lea     edx, [r8+8]
0x180013835  call    BSendFeatures
0x18001383a  mov     r8d, 1Ch
0x180013840  lea     rdx, PSFRAG_linedefaults; "1 setlinecap 1 setlinejoin\r\n"
0x180013847  mov     rcx, rbx
0x18001384a  call    OPRawPortWrite
0x18001384f  mov     rcx, rbx
0x180013852  call    BSendMysetup
0x180013857  mov     rcx, [rdi]
0x18001385a  mov     eax, [rcx+88h]
0x180013860  sub     eax, r12d
0x180013863  cmp     eax, 4
0x180013866  ja      short loc_180013876
0x180013868  cmp     dword ptr [rcx+7Ch], 2
0x18001386c  jz      short loc_180013876
0x18001386e  mov     rcx, rbx
0x180013871  call    BSendNupMatrix
0x180013876  cmp     dword ptr [rbx+868h], 0
0x18001387d  jge     short loc_18001389D
0x18001387f  cmp     dword ptr [rbx+0E54h], 0
0x180013886  jnz     short loc_18001389D
0x180013888  mov     r8d, 1Dh
0x18001388e  lea     rdx, PSFRAG_setupmatrix; "mysetup concat colspRefresh\r\n"
0x180013895  mov     rcx, rbx
0x180013898  call    OPRawPortWrite
0x18001389d  mov     rax, [rdi]
0x1800138a0  test    byte ptr [rax+4], 10h
0x1800138a4  jz      short loc_1800138BB
0x1800138a6  mov     r8d, 3Ch ; '<'
0x1800138ac  lea     rdx, PSFRAG_setupnegativeimage; "userdict (OriginalTransferFunc) 1 curre"...
0x1800138b3  mov     rcx, rbx
0x1800138b6  call    OPRawPortWrite
0x1800138bb  mov     rdx, r13
0x1800138be  mov     rcx, rbx
0x1800138c1  call    DSCSend
0x1800138c6  xor     eax, eax
0x1800138c8  cmp     [rbx+0D70h], eax
0x1800138ce  setz    al
0x1800138d1  add     rsp, 28h
0x1800138d5  pop     r13
0x1800138d7  pop     r12
0x1800138d9  pop     rdi
0x1800138da  pop     rsi
0x1800138db  pop     rbp
0x1800138dc  pop     rbx
0x1800138dd  retn
```
