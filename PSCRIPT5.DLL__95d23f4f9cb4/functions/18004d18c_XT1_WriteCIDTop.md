# XT1_WriteCIDTop

- ea: `0x18004d18c`
- end: `0x18004d815`
- name: `XT1_WriteCIDTop`
- size: `1673`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180045e88`

## callees

- `0x180001ee0`
- `0x180001f20`
- `0x1800486f4`
- `0x180048774`
- `0x180049b2c`
- `0x180049e14`
- `0x180049e54`
- `0x18004b444`
- `0x18004b4b8`
- `0x18004b5c4`
- `0x18004c390`
- `0x18004d18c`
- `0x18005d010`

## string_xrefs

- `0x18004d49d`: `Registry`

## pseudocode

```c
__int64 __fastcall XT1_WriteCIDTop(__int64 a1)
{
  unsigned __int16 v2; // di
  __int64 v3; // rax
  unsigned __int16 v4; // si
  __int64 v5; // rdx
  void (__fastcall *v6)(__int64, unsigned int *, __int64); // rax
  __int64 v7; // r8
  __int64 v8; // rdx
  const char *v9; // r9
  __int64 v10; // r9
  _WORD v12[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v13; // [rsp+54h] [rbp-ACh] BYREF
  int v14; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v15; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v16; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v17[128]; // [rsp+70h] [rbp-90h] BYREF
  char v18[1024]; // [rsp+F0h] [rbp-10h] BYREF

  *(_DWORD *)(a1 + 8024) = 0;
  PutString(a1, "%!PS-Adobe-3.0 Resource-CIDFont");
  PutString(a1, "\r\n");
  PutString(a1, "%%DocumentNeededResources: ProcSet (CIDInit)");
  PutString(a1, "\r\n");
  PutString(a1, "%%IncludeResource: ProcSet (CIDInit)");
  PutString(a1, "\r\n");
  if ( *(_QWORD *)(a1 + 8008) )
  {
    v4 = (*(__int64 (**)(void))(a1 + 336))();
    if ( v4 > 0x7Fu )
      v4 = 127;
    (*(void (__fastcall **)(_BYTE *, _QWORD, _QWORD))(a1 + 344))(v17, *(_QWORD *)(a1 + 8008), v4);
    v3 = v4;
  }
  else
  {
    v2 = 127;
    XCF_LookUpTableEntry(a1, a1 + 7860, *(unsigned int *)(a1 + 7840));
    if ( *(_WORD *)(a1 + 14172) < 0x7Fu )
      v2 = *(_WORD *)(a1 + 14172);
    (*(void (__fastcall **)(_BYTE *, _QWORD, _QWORD))(a1 + 344))(v17, *(_QWORD *)(a1 + 14144), v2);
    v3 = v2;
  }
  v17[v3] = 0;
  (*(void (**)(char *, __int64, const char *, ...))(a1 + 360))(v18, 1024, "%%%%BeginResource: CIDFont (%s)", v17);
  PutString(a1, v18);
  PutString(a1, "\r\n");
  PutString(a1, "%%Title: (");
  PutStringID(a1, *(unsigned __int16 *)(a1 + 692));
  PutString(a1, " ");
  PutStringID(a1, *(unsigned __int16 *)(a1 + 7796));
  PutString(a1, " ");
  PutStringID(a1, *(unsigned __int16 *)(a1 + 7800));
  PutString(a1, " ");
  PutLongNumber(a1, *(unsigned int *)(a1 + 7804));
  PutString(a1, ")");
  PutString(a1, "\r\n");
  (*(void (**)(char *, __int64, const char *, ...))(a1 + 360))(v18, 1024, "%%%%Version: %s", a1 + 7752);
  PutString(a1, v18);
  PutString(a1, "\r\n");
  PutString(a1, "\r\n/CIDInit /ProcSet findresource begin\r\n");
  PutString(a1, "\r\n");
  PutString(a1, "20 dict begin\r\n");
  PutString(a1, "\r\n");
  (*(void (**)(char *, __int64, const char *, ...))(a1 + 360))(v18, 1024, "/CIDFontName /%s def", v17);
  PutString(a1, v18);
  PutString(a1, "\r\n");
  if ( *(int *)(a1 + 7748) > 0 )
  {
    (*(void (**)(char *, __int64, const char *, ...))(a1 + 360))(v18, 1024, "/CIDFontVersion %s def", a1 + 7752);
    PutString(a1, v18);
    PutString(a1, "\r\n");
  }
  WriteLongNumberLine(a1, "CIDFontType", *(unsigned int *)(a1 + 7788), *(unsigned int *)(a1 + 7784));
  PutString(a1, "\r\n/CIDSystemInfo 3 dict dup begin");
  PutString(a1, "\r\n");
  WriteSIDLine(a1, "Registry", *(unsigned int *)(a1 + 7796), *(unsigned int *)(a1 + 7792));
  WriteSIDLine(a1, "Ordering", *(unsigned int *)(a1 + 7800), *(unsigned int *)(a1 + 7792));
  WriteLongNumberLine(a1, "Supplement", *(unsigned int *)(a1 + 7804), *(unsigned int *)(a1 + 7792));
  PutString(a1, "end def\r\n");
  PutString(a1, "\r\n");
  WriteNumberListLine(a1, "FontBBox", a1 + 1516, *(unsigned int *)(a1 + 1512));
  PutString(a1, "\r\n");
  PutString(a1, "/Metrics2 16 dict def\r\n");
  PutString(a1, "\r\n");
  PutString(a1, "/CDevProc {pop 4 index add} bind def\r\n");
  PutString(a1, "\r\n");
  if ( *(_DWORD *)(a1 + 7964) != 1 )
  {
    WriteLongNumberLine(a1, "UIDBase", *(unsigned int *)(a1 + 7812), *(unsigned int *)(a1 + 7808));
    WriteLongNumberListLine(a1, v5, a1 + 1144);
  }
  PutString(a1, "\r\n/FontInfo 3 dict dup begin");
  PutString(a1, "\r\n");
  WriteSIDLine(a1, "Notice", *(unsigned int *)(a1 + 824), *(unsigned int *)(a1 + 820));
  WriteSIDLine(a1, "FullName", *(unsigned int *)(a1 + 692), *(unsigned int *)(a1 + 688));
  v6 = *(void (__fastcall **)(__int64, unsigned int *, __int64))(a1 + 440);
  if ( v6 )
  {
    v7 = *(_QWORD *)(a1 + 448);
    v13 = 0;
    v6(a1, &v13, v7);
    if ( v13 != -1 )
      WriteLongNumberLine(a1, "FSType", v13, 1);
  }
  if ( *(_QWORD *)(a1 + 456) )
  {
    v8 = *(unsigned __int16 *)(a1 + 7796);
    v14 = 0;
    LOWORD(v13) = 0;
    v15 = 0;
    v12[0] = 0;
    v16 = 0;
    XCF_LookUpString(a1, v8, &v16, &v13);
    XCF_LookUpString(a1, *(unsigned __int16 *)(a1 + 7800), &v15, v12);
    (*(void (__fastcall **)(__int64, int *, __int64, _QWORD, __int64, _WORD, _DWORD, _QWORD))(a1 + 456))(
      a1,
      &v14,
      v16,
      (unsigned __int16)v13,
      v15,
      v12[0],
      *(_DWORD *)(a1 + 7804),
      *(_QWORD *)(a1 + 464));
    if ( !v14 )
    {
      PutString(a1, "/GlyphNames2Unicode 16 dict def");
      PutString(a1, "\r\n");
      PutString(a1, "/GlyphNames2HostCode 16 dict def");
      PutString(a1, "\r\n");
    }
  }
  PutString(a1, "end def\r\n\r\n/CIDMapOffset 0 def\r\n\r\n/GDBytes 4 def");
  PutString(a1, "\r\n");
  v9 = "1";
  if ( *(_WORD *)(a1 + 14952) <= 1u )
    v9 = "0";
  (*(void (**)(char *, __int64, const char *, ...))(a1 + 360))(v18, 1024, "/FDBytes %s def", v9);
  PutString(a1, v18);
  PutString(a1, "\r\n");
  WriteLongNumberLine(a1, "CIDCount", *(unsigned int *)(a1 + 7836), *(unsigned int *)(a1 + 7832));
  v10 = *(unsigned __int16 *)(a1 + 14952);
  *(_DWORD *)(a1 + 15004) = *(_DWORD *)(a1 + 7836);
  (*(void (**)(char *, __int64, const char *, ...))(a1 + 360))(v18, 1024, "\r\n/FDArray %d array", v10);
  PutString(a1, v18);
  return PutString(a1, "\r\n");
}

```

## disassembly

```asm
0x18004d18c  mov     [rsp-8+arg_8], rbx
0x18004d191  mov     [rsp-8+arg_10], rsi
0x18004d196  push    rbp
0x18004d197  push    rdi
0x18004d198  push    r15
0x18004d19a  lea     rbp, [rsp-400h]
0x18004d1a2  sub     rsp, 500h
0x18004d1a9  mov     rax, cs:__security_cookie
0x18004d1b0  xor     rax, rsp
0x18004d1b3  mov     [rbp+410h+var_20], rax
0x18004d1ba  lea     rdx, aPsAdobe30Resou; "%!PS-Adobe-3.0 Resource-CIDFont"
0x18004d1c1  mov     dword ptr [rcx+1F58h], 0
0x18004d1cb  mov     rbx, rcx
0x18004d1ce  call    PutString
0x18004d1d3  lea     r15, asc_180062FDC; "\r\n"
0x18004d1da  mov     rcx, rbx
0x18004d1dd  mov     rdx, r15
0x18004d1e0  call    PutString
0x18004d1e5  lea     rdx, aDocumentneeded; "%%DocumentNeededResources: ProcSet (CID"...
0x18004d1ec  mov     rcx, rbx
0x18004d1ef  call    PutString
0x18004d1f4  mov     rdx, r15
0x18004d1f7  mov     rcx, rbx
0x18004d1fa  call    PutString
0x18004d1ff  lea     rdx, aIncluderesourc_1; "%%IncludeResource: ProcSet (CIDInit)"
0x18004d206  mov     rcx, rbx
0x18004d209  call    PutString
0x18004d20e  mov     rdx, r15
0x18004d211  mov     rcx, rbx
0x18004d214  call    PutString
0x18004d219  mov     rcx, [rbx+1F48h]
0x18004d220  test    rcx, rcx
0x18004d223  jnz     short loc_18004D27B
0x18004d225  mov     r8d, [rbx+1EA0h]
0x18004d22c  lea     edi, [rcx+7Fh]
0x18004d22f  mov     rcx, rbx
0x18004d232  lea     rdx, [rbx+1EB4h]
0x18004d239  call    XCF_LookUpTableEntry
0x18004d23e  movzx   eax, word ptr [rbx+375Ch]
0x18004d245  lea     rcx, [rsp+510h+var_4A0]
0x18004d24a  mov     rdx, [rbx+3740h]
0x18004d251  cmp     ax, di
0x18004d254  cmovb   di, ax
0x18004d258  mov     rax, [rbx+158h]
0x18004d25f  movzx   r8d, di
0x18004d263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d268  mov     eax, 80h
0x18004d26d  cmp     di, ax
0x18004d270  jnb     loc_18004D80F
0x18004d276  movzx   eax, di
0x18004d279  jmp     short loc_18004D2B5
0x18004d27b  mov     rax, [rbx+150h]
0x18004d282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d287  mov     edi, 7Fh
0x18004d28c  movzx   esi, ax
0x18004d28f  cmp     ax, di
0x18004d292  jbe     short loc_18004D296
0x18004d294  mov     esi, edi
0x18004d296  mov     rdx, [rbx+1F48h]
0x18004d29d  lea     rcx, [rsp+510h+var_4A0]
0x18004d2a2  mov     rax, [rbx+158h]
0x18004d2a9  movzx   r8d, si
0x18004d2ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d2b2  movzx   eax, si
0x18004d2b5  mov     [rsp+rax+510h+var_4A0], 0
0x18004d2ba  lea     r9, [rsp+510h+var_4A0]
0x18004d2bf  mov     rax, [rbx+168h]
0x18004d2c6  lea     r8, aBeginresourceC; "%%%%BeginResource: CIDFont (%s)"
0x18004d2cd  mov     esi, 400h
0x18004d2d2  lea     rcx, [rbp+410h+var_420]
0x18004d2d6  mov     edx, esi
0x18004d2d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d2dd  lea     rdx, [rbp+410h+var_420]
0x18004d2e1  mov     rcx, rbx
0x18004d2e4  call    PutString
0x18004d2e9  mov     rdx, r15
0x18004d2ec  mov     rcx, rbx
0x18004d2ef  call    PutString
0x18004d2f4  lea     rdx, aTitle; "%%Title: ("
0x18004d2fb  mov     rcx, rbx
0x18004d2fe  call    PutString
0x18004d303  movzx   edx, word ptr [rbx+2B4h]
0x18004d30a  mov     rcx, rbx
0x18004d30d  call    PutStringID
0x18004d312  lea     rdi, asc_180062A20; " "
0x18004d319  mov     rcx, rbx
0x18004d31c  mov     rdx, rdi
0x18004d31f  call    PutString
0x18004d324  movzx   edx, word ptr [rbx+1E74h]
0x18004d32b  mov     rcx, rbx
0x18004d32e  call    PutStringID
0x18004d333  mov     rdx, rdi
0x18004d336  mov     rcx, rbx
0x18004d339  call    PutString
0x18004d33e  movzx   edx, word ptr [rbx+1E78h]
0x18004d345  mov     rcx, rbx
0x18004d348  call    PutStringID
0x18004d34d  mov     rdx, rdi
0x18004d350  mov     rcx, rbx
0x18004d353  call    PutString
0x18004d358  mov     edx, [rbx+1E7Ch]
0x18004d35e  mov     rcx, rbx
0x18004d361  call    PutLongNumber
0x18004d366  lea     rdx, asc_180062948; ")"
0x18004d36d  mov     rcx, rbx
0x18004d370  call    PutString
0x18004d375  mov     rdx, r15
0x18004d378  mov     rcx, rbx
0x18004d37b  call    PutString
0x18004d380  mov     rax, [rbx+168h]
0x18004d387  lea     rdi, [rbx+1E48h]
0x18004d38e  mov     r9, rdi
0x18004d391  lea     r8, aVersionS; "%%%%Version: %s"
0x18004d398  mov     edx, esi
0x18004d39a  lea     rcx, [rbp+410h+var_420]
0x18004d39e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d3a3  lea     rdx, [rbp+410h+var_420]
0x18004d3a7  mov     rcx, rbx
0x18004d3aa  call    PutString
0x18004d3af  mov     rdx, r15
0x18004d3b2  mov     rcx, rbx
0x18004d3b5  call    PutString
0x18004d3ba  lea     rdx, aCidinitProcset_0; "\r\n/CIDInit /ProcSet findresource begi"...
0x18004d3c1  mov     rcx, rbx
0x18004d3c4  call    PutString
0x18004d3c9  mov     rdx, r15
0x18004d3cc  mov     rcx, rbx
0x18004d3cf  call    PutString
0x18004d3d4  lea     rdx, a20DictBegin; "20 dict begin\r\n"
0x18004d3db  mov     rcx, rbx
0x18004d3de  call    PutString
0x18004d3e3  mov     rdx, r15
0x18004d3e6  mov     rcx, rbx
0x18004d3e9  call    PutString
0x18004d3ee  mov     rax, [rbx+168h]
0x18004d3f5  lea     r9, [rsp+510h+var_4A0]
0x18004d3fa  lea     r8, aCidfontnameSDe; "/CIDFontName /%s def"
0x18004d401  mov     edx, esi
0x18004d403  lea     rcx, [rbp+410h+var_420]
0x18004d407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d40c  lea     rdx, [rbp+410h+var_420]
0x18004d410  mov     rcx, rbx
0x18004d413  call    PutString
0x18004d418  mov     rdx, r15
0x18004d41b  mov     rcx, rbx
0x18004d41e  call    PutString
0x18004d423  cmp     dword ptr [rbx+1E44h], 0
0x18004d42a  jle     short loc_18004D45F
0x18004d42c  mov     rax, [rbx+168h]
0x18004d433  lea     r8, aCidfontversion; "/CIDFontVersion %s def"
0x18004d43a  mov     r9, rdi
0x18004d43d  lea     rcx, [rbp+410h+var_420]
0x18004d441  mov     edx, esi
0x18004d443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d448  lea     rdx, [rbp+410h+var_420]
0x18004d44c  mov     rcx, rbx
0x18004d44f  call    PutString
0x18004d454  mov     rdx, r15
0x18004d457  mov     rcx, rbx
0x18004d45a  call    PutString
0x18004d45f  mov     r9d, [rbx+1E68h]
0x18004d466  lea     rdx, aCidfonttype; "CIDFontType"
0x18004d46d  mov     r8d, [rbx+1E6Ch]
0x18004d474  mov     rcx, rbx
0x18004d477  call    WriteLongNumberLine
0x18004d47c  lea     rdx, aCidsysteminfo3; "\r\n/CIDSystemInfo 3 dict dup begin"
0x18004d483  mov     rcx, rbx
0x18004d486  call    PutString
0x18004d48b  mov     rdx, r15
0x18004d48e  mov     rcx, rbx
0x18004d491  call    PutString
0x18004d496  mov     r9d, [rbx+1E70h]
0x18004d49d  lea     rdx, aRegistry; "Registry"
0x18004d4a4  mov     r8d, [rbx+1E74h]
0x18004d4ab  mov     rcx, rbx
0x18004d4ae  call    WriteSIDLine
0x18004d4b3  mov     r9d, [rbx+1E70h]
0x18004d4ba  lea     rdx, aOrdering; "Ordering"
0x18004d4c1  mov     r8d, [rbx+1E78h]
0x18004d4c8  mov     rcx, rbx
0x18004d4cb  call    WriteSIDLine
0x18004d4d0  mov     r9d, [rbx+1E70h]
0x18004d4d7  lea     rdx, aSupplement; "Supplement"
0x18004d4de  mov     r8d, [rbx+1E7Ch]
0x18004d4e5  mov     rcx, rbx
0x18004d4e8  call    WriteLongNumberLine
0x18004d4ed  lea     rdx, aEndDef; "end def\r\n"
0x18004d4f4  mov     rcx, rbx
0x18004d4f7  call    PutString
0x18004d4fc  mov     rdx, r15
0x18004d4ff  mov     rcx, rbx
0x18004d502  call    PutString
0x18004d507  mov     r9d, [rbx+5E8h]
0x18004d50e  lea     r8, [rbx+5ECh]
0x18004d515  lea     rdx, aFontbbox; "FontBBox"
0x18004d51c  mov     rcx, rbx
0x18004d51f  call    WriteNumberListLine
0x18004d524  mov     rdx, r15
0x18004d527  mov     rcx, rbx
0x18004d52a  call    PutString
0x18004d52f  lea     rdx, aMetrics216Dict; "/Metrics2 16 dict def\r\n"
0x18004d536  mov     rcx, rbx
0x18004d539  call    PutString
0x18004d53e  mov     rdx, r15
0x18004d541  mov     rcx, rbx
0x18004d544  call    PutString
0x18004d549  lea     rdx, aCdevprocPop4In; "/CDevProc {pop 4 index add} bind def\r"...
0x18004d550  mov     rcx, rbx
0x18004d553  call    PutString
0x18004d558  mov     rdx, r15
0x18004d55b  mov     rcx, rbx
0x18004d55e  call    PutString
0x18004d563  mov     edi, 1
0x18004d568  cmp     [rbx+1F1Ch], edi
0x18004d56e  jz      short loc_18004D5A3
0x18004d570  mov     r9d, [rbx+1E80h]
0x18004d577  lea     rdx, aUidbase; "UIDBase"
0x18004d57e  mov     r8d, [rbx+1E84h]
0x18004d585  mov     rcx, rbx
0x18004d588  call    WriteLongNumberLine
0x18004d58d  mov     r9d, [rbx+474h]
0x18004d594  lea     r8, [rbx+478h]
0x18004d59b  mov     rcx, rbx
0x18004d59e  call    WriteLongNumberListLine
0x18004d5a3  lea     rdx, aFontinfo3DictD; "\r\n/FontInfo 3 dict dup begin"
0x18004d5aa  mov     rcx, rbx
0x18004d5ad  call    PutString
0x18004d5b2  mov     rdx, r15
0x18004d5b5  mov     rcx, rbx
0x18004d5b8  call    PutString
0x18004d5bd  mov     r9d, [rbx+334h]
0x18004d5c4  lea     rdx, aNotice; "Notice"
0x18004d5cb  mov     r8d, [rbx+338h]
0x18004d5d2  mov     rcx, rbx
0x18004d5d5  call    WriteSIDLine
0x18004d5da  mov     r9d, [rbx+2B0h]
0x18004d5e1  lea     rdx, aFullname; "FullName"
0x18004d5e8  mov     r8d, [rbx+2B4h]
0x18004d5ef  mov     rcx, rbx
0x18004d5f2  call    WriteSIDLine
0x18004d5f7  mov     rax, [rbx+1B8h]
0x18004d5fe  test    rax, rax
0x18004d601  jz      short loc_18004D63C
0x18004d603  mov     r8, [rbx+1C0h]
0x18004d60a  lea     rdx, [rsp+510h+var_4BC]
0x18004d60f  mov     rcx, rbx
0x18004d612  mov     [rsp+510h+var_4BC], 0
0x18004d61a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d61f  mov     r8d, [rsp+510h+var_4BC]
0x18004d624  cmp     r8d, 0FFFFFFFFh
0x18004d628  jz      short loc_18004D63C
0x18004d62a  mov     r9d, edi
0x18004d62d  lea     rdx, aFstype; "FSType"
0x18004d634  mov     rcx, rbx
0x18004d637  call    WriteLongNumberLine
0x18004d63c  cmp     qword ptr [rbx+1C8h], 0
0x18004d644  jz      loc_18004D722
0x18004d64a  movzx   edx, word ptr [rbx+1E74h]
0x18004d651  lea     r9, [rsp+510h+var_4BC]
0x18004d656  xor     eax, eax
0x18004d658  mov     [rsp+510h+var_4B8], 0
0x18004d660  lea     r8, [rsp+510h+var_4A8]
0x18004d665  mov     word ptr [rsp+510h+var_4BC], ax
0x18004d66a  mov     rcx, rbx
0x18004d66d  mov     [rsp+510h+var_4B0], rax
0x18004d672  mov     [rsp+510h+var_4C0], ax
0x18004d677  mov     [rsp+510h+var_4A8], 0
0x18004d680  call    XCF_LookUpString
0x18004d685  movzx   edx, word ptr [rbx+1E78h]
0x18004d68c  lea     r9, [rsp+510h+var_4C0]
0x18004d691  lea     r8, [rsp+510h+var_4B0]
0x18004d696  mov     rcx, rbx
0x18004d699  call    XCF_LookUpString
0x18004d69e  mov     rcx, [rbx+1D0h]
0x18004d6a5  lea     rdx, [rsp+510h+var_4B8]
0x18004d6aa  movzx   r9d, word ptr [rsp+510h+var_4BC]
0x18004d6b0  mov     r8, [rsp+510h+var_4A8]
0x18004d6b5  mov     rax, [rbx+1C8h]
0x18004d6bc  mov     [rsp+510h+var_4D8], rcx
0x18004d6c1  mov     ecx, [rbx+1E7Ch]
0x18004d6c7  mov     [rsp+510h+var_4E0], ecx
0x18004d6cb  movzx   ecx, [rsp+510h+var_4C0]
0x18004d6d0  mov     [rsp+510h+var_4E8], cx
0x18004d6d5  mov     rcx, [rsp+510h+var_4B0]
0x18004d6da  mov     [rsp+510h+var_4F0], rcx
0x18004d6df  mov     rcx, rbx
0x18004d6e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d6e7  cmp     [rsp+510h+var_4B8], 0
0x18004d6ec  jnz     short loc_18004D722
0x18004d6ee  lea     rdx, aGlyphnames2uni; "/GlyphNames2Unicode 16 dict def"
0x18004d6f5  mov     rcx, rbx
0x18004d6f8  call    PutString
0x18004d6fd  mov     rdx, r15
0x18004d700  mov     rcx, rbx
0x18004d703  call    PutString
0x18004d708  lea     rdx, aGlyphnames2hos; "/GlyphNames2HostCode 16 dict def"
0x18004d70f  mov     rcx, rbx
0x18004d712  call    PutString
0x18004d717  mov     rdx, r15
0x18004d71a  mov     rcx, rbx
  ... truncated ...
```
