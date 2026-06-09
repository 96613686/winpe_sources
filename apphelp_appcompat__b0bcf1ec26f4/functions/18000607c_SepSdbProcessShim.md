# SepSdbProcessShim

- ea: `0x18000607c`
- end: `0x18000678c`
- name: `SepSdbProcessShim`
- size: `1808`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000a65c`

## callees

- `0x180005dfc`
- `0x18000607c`
- `0x180006ba0`
- `0x180006c20`
- `0x180007020`
- `0x180007424`
- `0x1800097f4`
- `0x180009a14`
- `0x18000aa08`
- `0x18000ae70`
- `0x18000ecc0`
- `0x18000f114`
- `0x18000f150`
- `0x180022b10`
- `0x180025c68`
- `0x180035dec`
- `0x1800363b8`
- `0x180057134`
- `0x180059235`
- `0x180059270`

## import_xrefs

- `ntdll!_wcsicmp` at `0x1800061cd`
- `ntdll!_wcsicmp` at `0x18000652c`
- `ntdll!_wcsicmp` at `0x180006540`
- `ntdll!_wcsicmp` at `0x1800066d5`
- `ntdll!_wcsicmp` at `0x1800061cd`
- `ntdll!_wcsicmp` at `0x18000652c`
- `ntdll!_wcsicmp` at `0x180006540`
- `ntdll!_wcsicmp` at `0x1800066d5`

## string_xrefs

- `0x18000635a`: `Failed to combine shim and global inex: %08lx`
- `0x1800063a7`: `Failed to read shim-level inex: %08lx`
- `0x1800065e5`: `Found already loaded shim: %S`
- `0x18000658b`: `Failed to read exe-level inex: %08lx`
- `0x1800066a3`: `Failed to read shim definition: %08lx`
- `0x1800066cb`: `__COMMAND_LINE_OVERRIDE__`
- `0x1800066e8`: `Failed to create inex: %08lx`
- `0x180006653`: `Failed to append the command line for shim name: %S %S`
- `0x180006732`: `Failed to create shim-level inex: %08lx`
- `0x1800066f7`: `Failed to create exe-level inex: %08lx`
- `0x18000675b`: `Failed to combine shim and exe inex: %08lx`

## pseudocode

```c
__int64 __fastcall SepSdbProcessShim(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6,
        wchar_t *a7)
{
  void *v10; // r12
  void *v11; // rsi
  unsigned int v12; // r14d
  unsigned int ItemFromItemRef; // eax
  unsigned int FirstTagRef; // eax
  int DWORDTagRef; // eax
  unsigned int FirstTag; // eax
  __int64 v17; // r14
  const wchar_t *StringTagPtr; // r13
  int DllName; // eax
  unsigned int updated; // ebx
  PWSTR Buffer; // rdx
  __int64 v22; // rcx
  wchar_t *v23; // rax
  wchar_t *v24; // rcx
  wchar_t *v25; // r14
  unsigned int v26; // eax
  unsigned __int64 *v27; // rbx
  unsigned __int64 i; // r15
  int DWORDTag; // ebx
  __int64 v30; // r15
  unsigned int v31; // eax
  int v32; // eax
  int v33; // eax
  const char *v34; // r9
  __int64 v35; // r8
  __int64 v37; // r15
  unsigned int v38; // eax
  int v39; // eax
  int v40; // eax
  const char *v41; // r9
  __int64 v42; // r8
  unsigned __int64 v43; // rax
  unsigned __int64 v44; // rcx
  unsigned __int64 v45; // rbx
  const wchar_t *FileNamePart; // rax
  const char *v47; // r9
  __int64 v48; // r8
  const char *v49; // r9
  __int64 v50; // r8
  const wchar_t *v51; // rax
  const char *v52; // r9
  __int64 v53; // r8
  __int64 v54; // [rsp+20h] [rbp-E0h]
  unsigned int v55; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v56; // [rsp+44h] [rbp-BCh]
  wchar_t *String2; // [rsp+48h] [rbp-B8h]
  void *v58; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 *v59; // [rsp+58h] [rbp-A8h]
  unsigned int v60; // [rsp+60h] [rbp-A0h]
  __int64 v61; // [rsp+68h] [rbp-98h]
  void *v62; // [rsp+70h] [rbp-90h] BYREF
  __int64 v63; // [rsp+78h] [rbp-88h]
  __int64 v64; // [rsp+80h] [rbp-80h]
  __int64 v65; // [rsp+88h] [rbp-78h]
  wchar_t String1[264]; // [rsp+A0h] [rbp-60h] BYREF

  v61 = a6;
  v64 = a3;
  v65 = a2;
  v63 = a1;
  String2 = a7;
  v60 = a4;
  memset_0(String1, 0, 0x208u);
  v62 = 0;
  v58 = 0;
  v55 = 0;
  v10 = 0;
  v11 = 0;
  if ( !(unsigned int)SdbTagIDToTagRef(a2, a3, a4, &v55) )
  {
    v49 = "Could not convert tagid to tagref: %08lx";
    v50 = 577;
LABEL_70:
    LODWORD(v54) = a4;
    AslLogCallPrintf(1, "SepSdbProcessShim", v50, v49, v54);
    return (unsigned int)-1073741480;
  }
  v12 = v55;
  ItemFromItemRef = SdbGetItemFromItemRef(a2, v55, 24577, 16388, 28676);
  v56 = ItemFromItemRef;
  if ( !ItemFromItemRef )
  {
    v47 = "Failed to read shim definition: %08lx";
    v48 = 589;
    goto LABEL_59;
  }
  FirstTagRef = SdbFindFirstTagRef(a2, ItemFromItemRef, 16417);
  if ( FirstTagRef )
    DWORDTagRef = SdbReadDWORDTagRef(a2, FirstTagRef, 255);
  else
    DWORDTagRef = 255;
  if ( (DWORDTagRef & *(_DWORD *)(a2 + 552)) == 0 )
  {
    v47 = "Shim definition does not apply to this architecture: %08lx";
    v48 = 616;
LABEL_59:
    LODWORD(v54) = v12;
    AslLogCallPrintf(3, "SepSdbProcessShim", v48, v47, v54);
    return (unsigned int)-1073741275;
  }
  FirstTag = SdbFindFirstTag(a3, a4, 24577);
  if ( !FirstTag )
  {
    v49 = "Failed to get shim name tag: %08lx";
    v50 = 627;
    goto LABEL_70;
  }
  v17 = 260;
  StringTagPtr = (const wchar_t *)SdbGetStringTagPtr(a3, FirstTag);
  DllName = SdbGetDllName(a2, v55, String1, 260);
  updated = DllName;
  if ( DllName < 0 )
  {
    AslLogCallPrintf(2, "SepSdbProcessShim", 637, "Shim not found: %S [%08lx]", StringTagPtr, DllName);
    return updated;
  }
  if ( !_wcsicmp(String1, L"INTERNAL") )
  {
    if ( !g_DataTableEntry )
    {
      AslLogCallPrintf(1, "SepSdbProcessShim", 649, "Failed to get loader entry for internal shim %S", StringTagPtr);
      return (unsigned int)-1073741595;
    }
    Buffer = g_DataTableEntry->FullDllName.Buffer;
    v22 = 2147483646;
    v23 = String1;
    do
    {
      if ( !v22 )
        break;
      if ( !*Buffer )
        break;
      *v23++ = *Buffer++;
      --v22;
      --v17;
    }
    while ( v17 );
    v24 = v23 - 1;
    if ( v17 )
      v24 = v23;
    *v24 = 0;
    if ( !v17 )
    {
      AslLogCallPrintf(3, "SepSdbProcessShim", 658, "Bad shim name: %S", StringTagPtr);
      return (unsigned int)-1073741595;
    }
  }
  v25 = 0;
  v26 = SdbFindFirstTag(a3, v60, 24584);
  if ( v26 )
  {
    v51 = (const wchar_t *)SdbGetStringTagPtr(a3, v26);
    v25 = (wchar_t *)v51;
    if ( v51 )
    {
      if ( !_wcsicmp(v51, L"__COMMAND_LINE_OVERRIDE__") )
        v25 = String2;
    }
  }
  v27 = *(unsigned __int64 **)(v63 + 16);
  v59 = v27;
  String2 = (wchar_t *)AslPathGetFileNamePart(String1);
  for ( i = 0; ; ++i )
  {
    if ( i >= v27[2] )
      goto LABEL_23;
    v43 = v27[1] * i;
    if ( !is_mul_ok(v27[1], i) || (v44 = v27[5], v45 = v44 + v43, v44 + v43 < v44) )
      v45 = 0;
    FileNamePart = (const wchar_t *)AslPathGetFileNamePart(*(_QWORD *)(v45 + 8));
    if ( !_wcsicmp(FileNamePart, String2) && !_wcsicmp(*(const wchar_t **)(v45 + 16), StringTagPtr) )
      break;
    v27 = v59;
  }
  if ( i == -1 )
  {
LABEL_23:
    DWORDTag = 0;
    LODWORD(String2) = 1;
    LODWORD(v59) = 0;
    if ( !v61 )
    {
      v37 = v64;
      v38 = SdbFindFirstTag(v64, v60, 16456);
      if ( v38 )
      {
        DWORDTag = SdbReadDWORDTag(v37, v38, 0);
        LODWORD(v59) = DWORDTag;
      }
    }
    v30 = v65;
    v31 = SdbFindFirstTagRef(v65, v56, 16452);
    if ( v31 )
      LODWORD(String2) = SdbReadDWORDTagRef(v30, v31, 1);
    if ( DWORDTag == 1 )
      goto LABEL_43;
    if ( v61 )
    {
      v39 = SeInExCreate(&v58);
      updated = v39;
      if ( v39 >= 0 )
      {
        v11 = v58;
        v40 = SeInExAppend(v58, L"*", 1);
        updated = v40;
        if ( v40 < 0 )
        {
          v41 = "Failed to change inex mode to EXCLUDE_ALL: %08lx";
          v42 = 732;
        }
        else
        {
          v40 = SeInExAppend(v11, v61, 0);
          updated = v40;
          if ( v40 >= 0 )
            goto LABEL_42;
          v41 = "Failed to append to inex: %08lx";
          v42 = 738;
        }
        goto LABEL_61;
      }
      v52 = "Failed to create inex: %08lx";
      v53 = 726;
    }
    else
    {
      v32 = SeInExCreate(&v62);
      updated = v32;
      if ( v32 < 0 )
      {
        AslLogCallPrintf(1, "SepSdbProcessShim", 750, "Failed to create shim-level inex: %08lx", v32);
        v10 = v62;
LABEL_33:
        if ( v10 )
          SeInExDelete(v10);
        return updated;
      }
      v10 = v62;
      v33 = SeSdbReadInEx(v62, v30, v56, 0);
      updated = v33;
      if ( v33 < 0 )
      {
        v34 = "Failed to read shim-level inex: %08lx";
        v35 = 756;
        goto LABEL_32;
      }
      v33 = SeInExCombine(v10, a5);
      updated = v33;
      if ( v33 < 0 )
      {
        v34 = "Failed to combine shim and global inex: %08lx";
        v35 = 762;
LABEL_32:
        LODWORD(v54) = v33;
        AslLogCallPrintf(1, "SepSdbProcessShim", v35, v34, v54);
        goto LABEL_33;
      }
      v39 = SeInExCreate(&v58);
      updated = v39;
      if ( v39 >= 0 )
      {
        v11 = v58;
        v40 = SeSdbReadInEx(v58, v30, v55, 0);
        updated = v40;
        if ( v40 < 0 )
        {
          v41 = "Failed to read exe-level inex: %08lx";
          v42 = 778;
        }
        else
        {
          v40 = SeInExCombine(v11, v10);
          updated = v40;
          if ( v40 >= 0 )
          {
LABEL_42:
            DWORDTag = (int)v59;
LABEL_43:
            v40 = SeShimManagerAddShim(
                    *(_QWORD *)(v63 + 16),
                    StringTagPtr,
                    String1,
                    (unsigned int)String2,
                    v25,
                    DWORDTag,
                    v11);
            updated = v40;
            if ( v40 >= 0 )
            {
              updated = 0;
              v11 = 0;
              v10 = 0;
              goto LABEL_45;
            }
            v41 = "SeEngineAddShim failed: %08lx";
            v42 = 802;
            goto LABEL_61;
          }
          v41 = "Failed to combine shim and exe inex: %08lx";
          v42 = 784;
        }
LABEL_61:
        LODWORD(v54) = v40;
        AslLogCallPrintf(1, "SepSdbProcessShim", v42, v41, v54);
        goto LABEL_45;
      }
      v52 = "Failed to create exe-level inex: %08lx";
      v53 = 772;
    }
    LODWORD(v54) = v39;
    AslLogCallPrintf(1, "SepSdbProcessShim", v53, v52, v54);
    v11 = v58;
LABEL_45:
    if ( v11 )
      SeInExDelete(v11);
    goto LABEL_33;
  }
  AslLogCallPrintf(3, "SepSdbProcessShim", 677, "Found already loaded shim: %S", StringTagPtr);
  updated = 0;
  if ( v25 )
  {
    if ( (unsigned int)SdbFindFirstTag(v64, v56, 4118) )
    {
      updated = SeShimManagerUpdateCommandLine(*(_QWORD *)(v63 + 16), i, v25);
      if ( (updated & 0x80000000) != 0 )
        AslLogCallPrintf(
          3,
          "SepSdbProcessShim",
          690,
          "Failed to append the command line for shim name: %S %S",
          StringTagPtr,
          v25);
    }
  }
  return updated;
}

```

## disassembly

```asm
0x18000607c  push    rbp
0x18000607e  push    rbx
0x18000607f  push    rsi
0x180006080  push    rdi
0x180006081  push    r12
0x180006083  push    r13
0x180006085  push    r14
0x180006087  push    r15
0x180006089  lea     rbp, [rsp-1C8h]
0x180006091  sub     rsp, 2C8h
0x180006098  mov     rax, cs:__security_cookie
0x18000609f  xor     rax, rsp
0x1800060a2  mov     [rbp+200h+var_50], rax
0x1800060a9  mov     rax, [rbp+200h+arg_28]
0x1800060b0  mov     r15, r8
0x1800060b3  mov     [rsp+300h+var_298], rax
0x1800060b8  mov     rbx, rdx
0x1800060bb  mov     rax, [rbp+200h+arg_30]
0x1800060c2  mov     edi, r9d
0x1800060c5  mov     [rbp+200h+var_280], r8
0x1800060c9  mov     r8d, 208h; Size
0x1800060cf  mov     [rbp+200h+var_278], rdx
0x1800060d3  xor     edx, edx; Val
0x1800060d5  mov     [rsp+300h+var_288], rcx
0x1800060da  lea     rcx, [rbp+200h+String1]; void *
0x1800060de  mov     [rsp+300h+String2], rax
0x1800060e3  mov     [rsp+300h+var_2A0], r9d
0x1800060e8  call    memset_0
0x1800060ed  xor     r13d, r13d
0x1800060f0  lea     r9, [rsp+300h+var_2C0]
0x1800060f5  mov     r8d, edi
0x1800060f8  mov     [rsp+300h+var_290], r13
0x1800060fd  mov     rdx, r15
0x180006100  mov     [rsp+300h+var_2B0], r13
0x180006105  mov     rcx, rbx
0x180006108  mov     [rsp+300h+var_2C0], r13d
0x18000610d  mov     r12d, r13d
0x180006110  mov     esi, r13d
0x180006113  call    SdbTagIDToTagRef
0x180006118  test    eax, eax
0x18000611a  jz      loc_180006668
0x180006120  mov     r14d, [rsp+300h+var_2C0]
0x180006125  mov     r9d, 4004h
0x18000612b  mov     edx, r14d
0x18000612e  mov     word ptr [rsp+300h+var_2E0], 7004h
0x180006135  mov     r8d, 6001h
0x18000613b  mov     rcx, rbx
0x18000613e  call    SdbGetItemFromItemRef
0x180006143  mov     [rsp+300h+var_2BC], eax
0x180006147  test    eax, eax
0x180006149  jz      loc_1800066A3
0x18000614f  mov     r8d, 4021h
0x180006155  mov     edx, eax
0x180006157  mov     rcx, rbx
0x18000615a  call    SdbFindFirstTagRef
0x18000615f  mov     edx, eax
0x180006161  test    eax, eax
0x180006163  jnz     loc_18000625F
0x180006169  mov     eax, 0FFh
0x18000616e  test    [rbx+228h], eax
0x180006174  jz      loc_18000655E
0x18000617a  mov     r8d, 6001h
0x180006180  mov     edx, edi
0x180006182  mov     rcx, r15
0x180006185  call    SdbFindFirstTag
0x18000618a  test    eax, eax
0x18000618c  jz      loc_180006677
0x180006192  mov     edx, eax
0x180006194  mov     rcx, r15
0x180006197  call    SdbGetStringTagPtr
0x18000619c  mov     edx, [rsp+300h+var_2C0]
0x1800061a0  lea     r8, [rbp+200h+String1]
0x1800061a4  mov     r14d, 104h
0x1800061aa  mov     rcx, rbx
0x1800061ad  mov     r9d, r14d
0x1800061b0  mov     r13, rax
0x1800061b3  call    SdbGetDllName
0x1800061b8  mov     ebx, eax
0x1800061ba  test    eax, eax
0x1800061bc  js      loc_1800065AF
0x1800061c2  lea     rdx, aInternal; "INTERNAL"
0x1800061c9  lea     rcx, [rbp+200h+String1]; String1
0x1800061cd  call    cs:__imp__wcsicmp
0x1800061d3  xor     ebx, ebx
0x1800061d5  mov     edi, 1
0x1800061da  test    eax, eax
0x1800061dc  jnz     loc_180006272
0x1800061e2  mov     rax, cs:g_DataTableEntry
0x1800061e9  test    rax, rax
0x1800061ec  jz      loc_18000648A
0x1800061f2  mov     rdx, [rax+50h]
0x1800061f6  mov     ecx, 7FFFFFFEh
0x1800061fb  lea     rax, [rbp+200h+String1]
0x1800061ff  test    rcx, rcx
0x180006202  jz      short loc_180006222
0x180006204  movzx   r8d, word ptr [rdx]
0x180006208  test    r8w, r8w
0x18000620c  jz      short loc_180006222
0x18000620e  mov     [rax], r8w
0x180006212  add     rdx, 2
0x180006216  add     rax, 2
0x18000621a  sub     rcx, rdi
0x18000621d  sub     r14, rdi
0x180006220  jnz     short loc_1800061FF
0x180006222  test    r14, r14
0x180006225  lea     rcx, [rax-2]
0x180006229  cmovnz  rcx, rax
0x18000622d  mov     [rcx], bx
0x180006230  jnz     short loc_180006272
0x180006232  lea     r9, aBadShimNameS; "Bad shim name: %S"
0x180006239  mov     r8d, 292h
0x18000623f  mov     ecx, 3
0x180006244  lea     rdx, aSepsdbprocesss; "SepSdbProcessShim"
0x18000624b  mov     [rsp+300h+var_2E0], r13
0x180006250  call    AslLogCallPrintf
0x180006255  mov     ebx, 0C00000E5h
0x18000625a  jmp     loc_180006382
0x18000625f  mov     r8d, 0FFh
0x180006265  mov     rcx, rbx
0x180006268  call    SdbReadDWORDTagRef
0x18000626d  jmp     loc_18000616E
0x180006272  mov     edx, [rsp+300h+var_2A0]
0x180006276  mov     r8d, 6008h
0x18000627c  mov     rcx, r15
0x18000627f  mov     r14, rbx
0x180006282  call    SdbFindFirstTag
0x180006287  test    eax, eax
0x180006289  jnz     loc_1800066B5
0x18000628f  mov     rbx, [rsp+300h+var_288]
0x180006294  lea     rcx, [rbp+200h+String1]
0x180006298  mov     rbx, [rbx+10h]
0x18000629c  mov     [rsp+300h+var_2A8], rbx
0x1800062a1  call    AslPathGetFileNamePart
0x1800062a6  xor     r8d, r8d
0x1800062a9  mov     [rsp+300h+String2], rax
0x1800062ae  mov     r15d, r8d
0x1800062b1  cmp     r15, [rbx+10h]
0x1800062b5  jb      loc_1800064FF
0x1800062bb  mov     ebx, r8d
0x1800062be  mov     dword ptr [rsp+300h+String2], edi
0x1800062c2  mov     dword ptr [rsp+300h+var_2A8], ebx
0x1800062c6  cmp     [rsp+300h+var_298], r8
0x1800062cb  jz      loc_1800063B6
0x1800062d1  mov     r15, [rbp+200h+var_278]
0x1800062d5  mov     r8d, 4044h
0x1800062db  mov     edx, [rsp+300h+var_2BC]
0x1800062df  mov     rcx, r15
0x1800062e2  call    SdbFindFirstTagRef
0x1800062e7  test    eax, eax
0x1800062e9  jz      short loc_1800062FC
0x1800062eb  mov     r8d, edi
0x1800062ee  mov     edx, eax
0x1800062f0  mov     rcx, r15
0x1800062f3  call    SdbReadDWORDTagRef
0x1800062f8  mov     dword ptr [rsp+300h+String2], eax
0x1800062fc  cmp     ebx, edi
0x1800062fe  jz      loc_18000643B
0x180006304  cmp     [rsp+300h+var_298], rsi
0x180006309  jnz     loc_18000649E
0x18000630f  lea     rcx, [rsp+300h+var_290]
0x180006314  call    SeInExCreate
0x180006319  mov     ebx, eax
0x18000631b  test    eax, eax
0x18000631d  js      loc_180006732
0x180006323  mov     r12, [rsp+300h+var_290]
0x180006328  xor     r9d, r9d
0x18000632b  mov     r8d, [rsp+300h+var_2BC]
0x180006330  mov     rcx, r12
0x180006333  mov     rdx, r15
0x180006336  call    SeSdbReadInEx
0x18000633b  mov     ebx, eax
0x18000633d  test    eax, eax
0x18000633f  js      short loc_1800063A7
0x180006341  mov     rdx, [rbp+200h+arg_20]
0x180006348  mov     rcx, r12
0x18000634b  call    SeInExCombine
0x180006350  mov     ebx, eax
0x180006352  test    eax, eax
0x180006354  jns     loc_1800063EC
0x18000635a  lea     r9, aFailedToCombin; "Failed to combine shim and global inex:"...
0x180006361  mov     r8d, 2FAh
0x180006367  lea     rdx, aSepsdbprocesss; "SepSdbProcessShim"
0x18000636e  mov     dword ptr [rsp+300h+var_2E0], eax
0x180006372  mov     ecx, edi
0x180006374  call    AslLogCallPrintf
0x180006379  test    r12, r12
0x18000637c  jnz     loc_18000677F
0x180006382  mov     eax, ebx
0x180006384  mov     rcx, [rbp+200h+var_50]
0x18000638b  xor     rcx, rsp; StackCookie
0x18000638e  call    __security_check_cookie
0x180006393  add     rsp, 2C8h
0x18000639a  pop     r15
0x18000639c  pop     r14
0x18000639e  pop     r13
0x1800063a0  pop     r12
0x1800063a2  pop     rdi
0x1800063a3  pop     rsi
0x1800063a4  pop     rbx
0x1800063a5  pop     rbp
0x1800063a6  retn
0x1800063a7  lea     r9, aFailedToReadSh; "Failed to read shim-level inex: %08lx"
0x1800063ae  mov     r8d, 2F4h
0x1800063b4  jmp     short loc_180006367
0x1800063b6  mov     r15, [rbp+200h+var_280]
0x1800063ba  mov     r8d, 4048h
0x1800063c0  mov     edx, [rsp+300h+var_2A0]
0x1800063c4  mov     rcx, r15
0x1800063c7  call    SdbFindFirstTag
0x1800063cc  test    eax, eax
0x1800063ce  jz      loc_1800062D1
0x1800063d4  xor     r8d, r8d
0x1800063d7  mov     edx, eax
0x1800063d9  mov     rcx, r15
0x1800063dc  call    SdbReadDWORDTag
0x1800063e1  mov     ebx, eax
0x1800063e3  mov     dword ptr [rsp+300h+var_2A8], eax
0x1800063e7  jmp     loc_1800062D1
0x1800063ec  lea     rcx, [rsp+300h+var_2B0]
0x1800063f1  call    SeInExCreate
0x1800063f6  mov     ebx, eax
0x1800063f8  test    eax, eax
0x1800063fa  js      loc_1800066F7
0x180006400  mov     rsi, [rsp+300h+var_2B0]
0x180006405  xor     r9d, r9d
0x180006408  mov     r8d, [rsp+300h+var_2C0]
0x18000640d  mov     rcx, rsi
0x180006410  mov     rdx, r15
0x180006413  call    SeSdbReadInEx
0x180006418  mov     ebx, eax
0x18000641a  test    eax, eax
0x18000641c  js      loc_18000658B
0x180006422  mov     rdx, r12
0x180006425  mov     rcx, rsi
0x180006428  call    SeInExCombine
0x18000642d  mov     ebx, eax
0x18000642f  test    eax, eax
0x180006431  js      loc_18000675B
0x180006437  mov     ebx, dword ptr [rsp+300h+var_2A8]
0x18000643b  mov     rax, [rsp+300h+var_288]
0x180006440  lea     r8, [rbp+200h+String1]
0x180006444  mov     r9d, dword ptr [rsp+300h+String2]
0x180006449  mov     rdx, r13
0x18000644c  mov     [rsp+300h+var_2D0], rsi
0x180006451  mov     dword ptr [rsp+300h+var_2D8], ebx
0x180006455  mov     rcx, [rax+10h]
0x180006459  mov     [rsp+300h+var_2E0], r14
0x18000645e  call    SeShimManagerAddShim
0x180006463  mov     ebx, eax
0x180006465  test    eax, eax
0x180006467  js      loc_18000676D
0x18000646d  xor     ebx, ebx
0x18000646f  mov     esi, ebx
0x180006471  mov     r12d, ebx
0x180006474  test    rsi, rsi
0x180006477  jz      loc_180006379
0x18000647d  mov     rcx, rsi; void *
0x180006480  call    SeInExDelete
0x180006485  jmp     loc_180006379
0x18000648a  lea     r9, aFailedToGetLoa; "Failed to get loader entry for internal"...
0x180006491  mov     r8d, 289h
0x180006497  mov     ecx, edi
0x180006499  jmp     loc_180006244
0x18000649e  lea     rcx, [rsp+300h+var_2B0]
0x1800064a3  call    SeInExCreate
0x1800064a8  mov     ebx, eax
0x1800064aa  test    eax, eax
0x1800064ac  js      loc_1800066E8
0x1800064b2  mov     rsi, [rsp+300h+var_2B0]
0x1800064b7  lea     rdx, asc_18005E958; "*"
0x1800064be  mov     rcx, rsi
0x1800064c1  mov     r8d, edi
0x1800064c4  call    SeInExAppend
0x1800064c9  mov     ebx, eax
0x1800064cb  test    eax, eax
0x1800064cd  js      loc_180006720
0x1800064d3  mov     rdx, [rsp+300h+var_298]
0x1800064d8  xor     r8d, r8d
0x1800064db  mov     rcx, rsi
0x1800064de  call    SeInExAppend
0x1800064e3  mov     ebx, eax
0x1800064e5  test    eax, eax
0x1800064e7  jns     loc_180006437
0x1800064ed  lea     r9, aFailedToAppend_3; "Failed to append to inex: %08lx"
0x1800064f4  mov     r8d, 2E2h
0x1800064fa  jmp     loc_180006598
0x1800064ff  mov     rax, r15
0x180006502  mul     qword ptr [rbx+8]
0x180006506  test    rdx, rdx
0x180006509  jnz     short loc_180006518
0x18000650b  mov     rcx, [rbx+28h]
0x18000650f  lea     rbx, [rcx+rax]
0x180006513  cmp     rbx, rcx
0x180006516  jnb     short loc_18000651B
0x180006518  mov     rbx, r8
0x18000651b  mov     rcx, [rbx+8]
0x18000651f  call    AslPathGetFileNamePart
0x180006524  mov     rdx, [rsp+300h+String2]; String2
0x180006529  mov     rcx, rax; String1
0x18000652c  call    cs:__imp__wcsicmp
  ... truncated ...
```
