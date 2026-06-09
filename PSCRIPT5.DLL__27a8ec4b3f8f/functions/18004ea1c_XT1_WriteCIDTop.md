# XT1_WriteCIDTop

- ea: `0x18004ea1c`
- end: `0x18004f0a6`
- name: `XT1_WriteCIDTop`
- size: `1674`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800477ac`

## callees

- `0x180001f20`
- `0x180001f60`
- `0x180049f64`
- `0x180049fe4`
- `0x18004b3a4`
- `0x18004b690`
- `0x18004b6d0`
- `0x18004cccc`
- `0x18004cd40`
- `0x18004ce4c`
- `0x18004dc18`
- `0x18004ea1c`
- `0x18005f010`

## string_xrefs

- `0x18004ed2d`: `Registry`

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
  unsigned __int16 v8; // dx
  const char *v9; // r9
  __int64 v10; // r9
  _WORD v12[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v13; // [rsp+54h] [rbp-ACh] BYREF
  int v14; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v15; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v16; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v17[128]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v18[1024]; // [rsp+F0h] [rbp-10h] BYREF

  *(_DWORD *)(a1 + 8024) = 0;
  PutString(a1, (__int64)"%!PS-Adobe-3.0 Resource-CIDFont");
  PutString(a1, (__int64)"\r\n");
  PutString(a1, (__int64)"%%DocumentNeededResources: ProcSet (CIDInit)");
  PutString(a1, (__int64)"\r\n");
  PutString(a1, (__int64)"%%IncludeResource: ProcSet (CIDInit)");
  PutString(a1, (__int64)"\r\n");
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
    XCF_LookUpTableEntry(a1, (_DWORD *)(a1 + 7860), *(_DWORD *)(a1 + 7840));
    if ( *(_WORD *)(a1 + 14172) < 0x7Fu )
      v2 = *(_WORD *)(a1 + 14172);
    (*(void (__fastcall **)(_BYTE *, _QWORD, _QWORD))(a1 + 344))(v17, *(_QWORD *)(a1 + 14144), v2);
    v3 = v2;
  }
  v17[v3] = 0;
  (*(void (**)(_BYTE *, __int64, const char *, ...))(a1 + 360))(v18, 1024, "%%%%BeginResource: CIDFont (%s)", v17);
  PutString(a1, (__int64)v18);
  PutString(a1, (__int64)"\r\n");
  PutString(a1, (__int64)"%%Title: (");
  PutStringID(a1, *(_WORD *)(a1 + 692));
  PutString(a1, (__int64)" ");
  PutStringID(a1, *(_WORD *)(a1 + 7796));
  PutString(a1, (__int64)" ");
  PutStringID(a1, *(_WORD *)(a1 + 7800));
  PutString(a1, (__int64)" ");
  PutLongNumber(a1, *(_DWORD *)(a1 + 7804));
  PutString(a1, (__int64)")");
  PutString(a1, (__int64)"\r\n");
  (*(void (**)(_BYTE *, __int64, const char *, ...))(a1 + 360))(v18, 1024, "%%%%Version: %s", a1 + 7752);
  PutString(a1, (__int64)v18);
  PutString(a1, (__int64)"\r\n");
  PutString(a1, (__int64)"\r\n/CIDInit /ProcSet findresource begin\r\n");
  PutString(a1, (__int64)"\r\n");
  PutString(a1, (__int64)"20 dict begin\r\n");
  PutString(a1, (__int64)"\r\n");
  (*(void (**)(_BYTE *, __int64, const char *, ...))(a1 + 360))(v18, 1024, "/CIDFontName /%s def", v17);
  PutString(a1, (__int64)v18);
  PutString(a1, (__int64)"\r\n");
  if ( *(int *)(a1 + 7748) > 0 )
  {
    (*(void (**)(_BYTE *, __int64, const char *, ...))(a1 + 360))(v18, 1024, "/CIDFontVersion %s def", a1 + 7752);
    PutString(a1, (__int64)v18);
    PutString(a1, (__int64)"\r\n");
  }
  WriteLongNumberLine(a1, (__int64)"CIDFontType", *(_DWORD *)(a1 + 7788), *(_DWORD *)(a1 + 7784));
  PutString(a1, (__int64)"\r\n/CIDSystemInfo 3 dict dup begin");
  PutString(a1, (__int64)"\r\n");
  WriteSIDLine(a1, (__int64)"Registry", *(_DWORD *)(a1 + 7796), *(_DWORD *)(a1 + 7792));
  WriteSIDLine(a1, (__int64)"Ordering", *(_DWORD *)(a1 + 7800), *(_DWORD *)(a1 + 7792));
  WriteLongNumberLine(a1, (__int64)"Supplement", *(_DWORD *)(a1 + 7804), *(_DWORD *)(a1 + 7792));
  PutString(a1, (__int64)"end def\r\n");
  PutString(a1, (__int64)"\r\n");
  WriteNumberListLine(a1, (__int64)"FontBBox", a1 + 1516, *(_DWORD *)(a1 + 1512));
  PutString(a1, (__int64)"\r\n");
  PutString(a1, (__int64)"/Metrics2 16 dict def\r\n");
  PutString(a1, (__int64)"\r\n");
  PutString(a1, (__int64)"/CDevProc {pop 4 index add} bind def\r\n");
  PutString(a1, (__int64)"\r\n");
  if ( *(_DWORD *)(a1 + 7964) != 1 )
  {
    WriteLongNumberLine(a1, (__int64)"UIDBase", *(_DWORD *)(a1 + 7812), *(_DWORD *)(a1 + 7808));
    WriteLongNumberListLine(a1, v5, a1 + 1144, *(_DWORD *)(a1 + 1140));
  }
  PutString(a1, (__int64)"\r\n/FontInfo 3 dict dup begin");
  PutString(a1, (__int64)"\r\n");
  WriteSIDLine(a1, (__int64)"Notice", *(_DWORD *)(a1 + 824), *(_DWORD *)(a1 + 820));
  WriteSIDLine(a1, (__int64)"FullName", *(_DWORD *)(a1 + 692), *(_DWORD *)(a1 + 688));
  v6 = *(void (__fastcall **)(__int64, unsigned int *, __int64))(a1 + 440);
  if ( v6 )
  {
    v7 = *(_QWORD *)(a1 + 448);
    v13 = 0;
    v6(a1, &v13, v7);
    if ( v13 != -1 )
      WriteLongNumberLine(a1, (__int64)"FSType", v13, 1);
  }
  if ( *(_QWORD *)(a1 + 456) )
  {
    v8 = *(_WORD *)(a1 + 7796);
    v14 = 0;
    LOWORD(v13) = 0;
    v15 = 0;
    v12[0] = 0;
    v16 = 0;
    XCF_LookUpString(a1, v8, &v16, &v13);
    XCF_LookUpString(a1, *(_WORD *)(a1 + 7800), &v15, v12);
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
      PutString(a1, (__int64)"/GlyphNames2Unicode 16 dict def");
      PutString(a1, (__int64)"\r\n");
      PutString(a1, (__int64)"/GlyphNames2HostCode 16 dict def");
      PutString(a1, (__int64)"\r\n");
    }
  }
  PutString(a1, (__int64)"end def\r\n\r\n/CIDMapOffset 0 def\r\n\r\n/GDBytes 4 def");
  PutString(a1, (__int64)"\r\n");
  v9 = "1";
  if ( *(_WORD *)(a1 + 14952) <= 1u )
    v9 = "0";
  (*(void (**)(_BYTE *, __int64, const char *, ...))(a1 + 360))(v18, 1024, "/FDBytes %s def", v9);
  PutString(a1, (__int64)v18);
  PutString(a1, (__int64)"\r\n");
  WriteLongNumberLine(a1, (__int64)"CIDCount", *(_DWORD *)(a1 + 7836), *(_DWORD *)(a1 + 7832));
  v10 = *(unsigned __int16 *)(a1 + 14952);
  *(_DWORD *)(a1 + 15004) = *(_DWORD *)(a1 + 7836);
  (*(void (**)(_BYTE *, __int64, const char *, ...))(a1 + 360))(v18, 1024, "\r\n/FDArray %d array", v10);
  PutString(a1, (__int64)v18);
  return PutString(a1, (__int64)"\r\n");
}

```

## disassembly

```asm
0x18004ea1c  mov     [rsp-8+arg_8], rbx
0x18004ea21  mov     [rsp-8+arg_10], rsi
0x18004ea26  push    rbp
0x18004ea27  push    rdi
0x18004ea28  push    r15
0x18004ea2a  lea     rbp, [rsp-400h]
0x18004ea32  sub     rsp, 500h
0x18004ea39  mov     rax, cs:__security_cookie
0x18004ea40  xor     rax, rsp
0x18004ea43  mov     [rbp+410h+var_20], rax
0x18004ea4a  lea     rdx, aPsAdobe30Resou; "%!PS-Adobe-3.0 Resource-CIDFont"
0x18004ea51  mov     dword ptr [rcx+1F58h], 0
0x18004ea5b  mov     rbx, rcx
0x18004ea5e  call    PutString
0x18004ea63  lea     r15, asc_180064FCC; "\r\n"
0x18004ea6a  mov     rcx, rbx
0x18004ea6d  mov     rdx, r15
0x18004ea70  call    PutString
0x18004ea75  lea     rdx, aDocumentneeded; "%%DocumentNeededResources: ProcSet (CID"...
0x18004ea7c  mov     rcx, rbx
0x18004ea7f  call    PutString
0x18004ea84  mov     rdx, r15
0x18004ea87  mov     rcx, rbx
0x18004ea8a  call    PutString
0x18004ea8f  lea     rdx, aIncluderesourc_1; "%%IncludeResource: ProcSet (CIDInit)"
0x18004ea96  mov     rcx, rbx
0x18004ea99  call    PutString
0x18004ea9e  mov     rdx, r15
0x18004eaa1  mov     rcx, rbx
0x18004eaa4  call    PutString
0x18004eaa9  mov     rcx, [rbx+1F48h]
0x18004eab0  test    rcx, rcx
0x18004eab3  jnz     short loc_18004EB0B
0x18004eab5  mov     r8d, [rbx+1EA0h]
0x18004eabc  lea     edi, [rcx+7Fh]
0x18004eabf  mov     rcx, rbx
0x18004eac2  lea     rdx, [rbx+1EB4h]
0x18004eac9  call    XCF_LookUpTableEntry
0x18004eace  movzx   eax, word ptr [rbx+375Ch]
0x18004ead5  lea     rcx, [rsp+510h+var_4A0]
0x18004eada  mov     rdx, [rbx+3740h]
0x18004eae1  cmp     ax, di
0x18004eae4  cmovb   di, ax
0x18004eae8  mov     rax, [rbx+158h]
0x18004eaef  movzx   r8d, di
0x18004eaf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eaf8  mov     eax, 80h
0x18004eafd  cmp     di, ax
0x18004eb00  jnb     loc_18004F0A0
0x18004eb06  movzx   eax, di
0x18004eb09  jmp     short loc_18004EB45
0x18004eb0b  mov     rax, [rbx+150h]
0x18004eb12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eb17  mov     edi, 7Fh
0x18004eb1c  movzx   esi, ax
0x18004eb1f  cmp     ax, di
0x18004eb22  jbe     short loc_18004EB26
0x18004eb24  mov     esi, edi
0x18004eb26  mov     rdx, [rbx+1F48h]
0x18004eb2d  lea     rcx, [rsp+510h+var_4A0]
0x18004eb32  mov     rax, [rbx+158h]
0x18004eb39  movzx   r8d, si
0x18004eb3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eb42  movzx   eax, si
0x18004eb45  mov     [rsp+rax+510h+var_4A0], 0
0x18004eb4a  lea     r9, [rsp+510h+var_4A0]
0x18004eb4f  mov     rax, [rbx+168h]
0x18004eb56  lea     r8, aBeginresourceC; "%%%%BeginResource: CIDFont (%s)"
0x18004eb5d  mov     esi, 400h
0x18004eb62  lea     rcx, [rbp+410h+var_420]
0x18004eb66  mov     edx, esi
0x18004eb68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eb6d  lea     rdx, [rbp+410h+var_420]
0x18004eb71  mov     rcx, rbx
0x18004eb74  call    PutString
0x18004eb79  mov     rdx, r15
0x18004eb7c  mov     rcx, rbx
0x18004eb7f  call    PutString
0x18004eb84  lea     rdx, aTitle; "%%Title: ("
0x18004eb8b  mov     rcx, rbx
0x18004eb8e  call    PutString
0x18004eb93  movzx   edx, word ptr [rbx+2B4h]
0x18004eb9a  mov     rcx, rbx
0x18004eb9d  call    PutStringID
0x18004eba2  lea     rdi, asc_180064A10; " "
0x18004eba9  mov     rcx, rbx
0x18004ebac  mov     rdx, rdi
0x18004ebaf  call    PutString
0x18004ebb4  movzx   edx, word ptr [rbx+1E74h]
0x18004ebbb  mov     rcx, rbx
0x18004ebbe  call    PutStringID
0x18004ebc3  mov     rdx, rdi
0x18004ebc6  mov     rcx, rbx
0x18004ebc9  call    PutString
0x18004ebce  movzx   edx, word ptr [rbx+1E78h]
0x18004ebd5  mov     rcx, rbx
0x18004ebd8  call    PutStringID
0x18004ebdd  mov     rdx, rdi
0x18004ebe0  mov     rcx, rbx
0x18004ebe3  call    PutString
0x18004ebe8  mov     edx, [rbx+1E7Ch]
0x18004ebee  mov     rcx, rbx
0x18004ebf1  call    PutLongNumber
0x18004ebf6  lea     rdx, asc_180064938; ")"
0x18004ebfd  mov     rcx, rbx
0x18004ec00  call    PutString
0x18004ec05  mov     rdx, r15
0x18004ec08  mov     rcx, rbx
0x18004ec0b  call    PutString
0x18004ec10  mov     rax, [rbx+168h]
0x18004ec17  lea     rdi, [rbx+1E48h]
0x18004ec1e  mov     r9, rdi
0x18004ec21  lea     r8, aVersionS; "%%%%Version: %s"
0x18004ec28  mov     edx, esi
0x18004ec2a  lea     rcx, [rbp+410h+var_420]
0x18004ec2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ec33  lea     rdx, [rbp+410h+var_420]
0x18004ec37  mov     rcx, rbx
0x18004ec3a  call    PutString
0x18004ec3f  mov     rdx, r15
0x18004ec42  mov     rcx, rbx
0x18004ec45  call    PutString
0x18004ec4a  lea     rdx, aCidinitProcset_0; "\r\n/CIDInit /ProcSet findresource begi"...
0x18004ec51  mov     rcx, rbx
0x18004ec54  call    PutString
0x18004ec59  mov     rdx, r15
0x18004ec5c  mov     rcx, rbx
0x18004ec5f  call    PutString
0x18004ec64  lea     rdx, a20DictBegin; "20 dict begin\r\n"
0x18004ec6b  mov     rcx, rbx
0x18004ec6e  call    PutString
0x18004ec73  mov     rdx, r15
0x18004ec76  mov     rcx, rbx
0x18004ec79  call    PutString
0x18004ec7e  mov     rax, [rbx+168h]
0x18004ec85  lea     r9, [rsp+510h+var_4A0]
0x18004ec8a  lea     r8, aCidfontnameSDe; "/CIDFontName /%s def"
0x18004ec91  mov     edx, esi
0x18004ec93  lea     rcx, [rbp+410h+var_420]
0x18004ec97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ec9c  lea     rdx, [rbp+410h+var_420]
0x18004eca0  mov     rcx, rbx
0x18004eca3  call    PutString
0x18004eca8  mov     rdx, r15
0x18004ecab  mov     rcx, rbx
0x18004ecae  call    PutString
0x18004ecb3  cmp     dword ptr [rbx+1E44h], 0
0x18004ecba  jle     short loc_18004ECEF
0x18004ecbc  mov     rax, [rbx+168h]
0x18004ecc3  lea     r8, aCidfontversion; "/CIDFontVersion %s def"
0x18004ecca  mov     r9, rdi
0x18004eccd  lea     rcx, [rbp+410h+var_420]
0x18004ecd1  mov     edx, esi
0x18004ecd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ecd8  lea     rdx, [rbp+410h+var_420]
0x18004ecdc  mov     rcx, rbx
0x18004ecdf  call    PutString
0x18004ece4  mov     rdx, r15
0x18004ece7  mov     rcx, rbx
0x18004ecea  call    PutString
0x18004ecef  mov     r9d, [rbx+1E68h]
0x18004ecf6  lea     rdx, aCidfonttype; "CIDFontType"
0x18004ecfd  mov     r8d, [rbx+1E6Ch]
0x18004ed04  mov     rcx, rbx
0x18004ed07  call    WriteLongNumberLine
0x18004ed0c  lea     rdx, aCidsysteminfo3; "\r\n/CIDSystemInfo 3 dict dup begin"
0x18004ed13  mov     rcx, rbx
0x18004ed16  call    PutString
0x18004ed1b  mov     rdx, r15
0x18004ed1e  mov     rcx, rbx
0x18004ed21  call    PutString
0x18004ed26  mov     r9d, [rbx+1E70h]
0x18004ed2d  lea     rdx, aRegistry; "Registry"
0x18004ed34  mov     r8d, [rbx+1E74h]
0x18004ed3b  mov     rcx, rbx
0x18004ed3e  call    WriteSIDLine
0x18004ed43  mov     r9d, [rbx+1E70h]
0x18004ed4a  lea     rdx, aOrdering; "Ordering"
0x18004ed51  mov     r8d, [rbx+1E78h]
0x18004ed58  mov     rcx, rbx
0x18004ed5b  call    WriteSIDLine
0x18004ed60  mov     r9d, [rbx+1E70h]
0x18004ed67  lea     rdx, aSupplement; "Supplement"
0x18004ed6e  mov     r8d, [rbx+1E7Ch]
0x18004ed75  mov     rcx, rbx
0x18004ed78  call    WriteLongNumberLine
0x18004ed7d  lea     rdx, aEndDef; "end def\r\n"
0x18004ed84  mov     rcx, rbx
0x18004ed87  call    PutString
0x18004ed8c  mov     rdx, r15
0x18004ed8f  mov     rcx, rbx
0x18004ed92  call    PutString
0x18004ed97  mov     r9d, [rbx+5E8h]
0x18004ed9e  lea     r8, [rbx+5ECh]
0x18004eda5  lea     rdx, aFontbbox; "FontBBox"
0x18004edac  mov     rcx, rbx
0x18004edaf  call    WriteNumberListLine
0x18004edb4  mov     rdx, r15
0x18004edb7  mov     rcx, rbx
0x18004edba  call    PutString
0x18004edbf  lea     rdx, aMetrics216Dict; "/Metrics2 16 dict def\r\n"
0x18004edc6  mov     rcx, rbx
0x18004edc9  call    PutString
0x18004edce  mov     rdx, r15
0x18004edd1  mov     rcx, rbx
0x18004edd4  call    PutString
0x18004edd9  lea     rdx, aCdevprocPop4In; "/CDevProc {pop 4 index add} bind def\r"...
0x18004ede0  mov     rcx, rbx
0x18004ede3  call    PutString
0x18004ede8  mov     rdx, r15
0x18004edeb  mov     rcx, rbx
0x18004edee  call    PutString
0x18004edf3  mov     edi, 1
0x18004edf8  cmp     [rbx+1F1Ch], edi
0x18004edfe  jz      short loc_18004EE33
0x18004ee00  mov     r9d, [rbx+1E80h]
0x18004ee07  lea     rdx, aUidbase; "UIDBase"
0x18004ee0e  mov     r8d, [rbx+1E84h]
0x18004ee15  mov     rcx, rbx
0x18004ee18  call    WriteLongNumberLine
0x18004ee1d  mov     r9d, [rbx+474h]
0x18004ee24  lea     r8, [rbx+478h]
0x18004ee2b  mov     rcx, rbx
0x18004ee2e  call    WriteLongNumberListLine
0x18004ee33  lea     rdx, aFontinfo3DictD; "\r\n/FontInfo 3 dict dup begin"
0x18004ee3a  mov     rcx, rbx
0x18004ee3d  call    PutString
0x18004ee42  mov     rdx, r15
0x18004ee45  mov     rcx, rbx
0x18004ee48  call    PutString
0x18004ee4d  mov     r9d, [rbx+334h]
0x18004ee54  lea     rdx, aNotice; "Notice"
0x18004ee5b  mov     r8d, [rbx+338h]
0x18004ee62  mov     rcx, rbx
0x18004ee65  call    WriteSIDLine
0x18004ee6a  mov     r9d, [rbx+2B0h]
0x18004ee71  lea     rdx, aFullname; "FullName"
0x18004ee78  mov     r8d, [rbx+2B4h]
0x18004ee7f  mov     rcx, rbx
0x18004ee82  call    WriteSIDLine
0x18004ee87  mov     rax, [rbx+1B8h]
0x18004ee8e  test    rax, rax
0x18004ee91  jz      short loc_18004EECC
0x18004ee93  mov     r8, [rbx+1C0h]
0x18004ee9a  lea     rdx, [rsp+510h+var_4BC]
0x18004ee9f  mov     rcx, rbx
0x18004eea2  mov     [rsp+510h+var_4BC], 0
0x18004eeaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eeaf  mov     r8d, [rsp+510h+var_4BC]
0x18004eeb4  cmp     r8d, 0FFFFFFFFh
0x18004eeb8  jz      short loc_18004EECC
0x18004eeba  mov     r9d, edi
0x18004eebd  lea     rdx, aFstype; "FSType"
0x18004eec4  mov     rcx, rbx
0x18004eec7  call    WriteLongNumberLine
0x18004eecc  cmp     qword ptr [rbx+1C8h], 0
0x18004eed4  jz      loc_18004EFB2
0x18004eeda  movzx   edx, word ptr [rbx+1E74h]
0x18004eee1  lea     r9, [rsp+510h+var_4BC]
0x18004eee6  xor     eax, eax
0x18004eee8  mov     [rsp+510h+var_4B8], 0
0x18004eef0  lea     r8, [rsp+510h+var_4A8]
0x18004eef5  mov     word ptr [rsp+510h+var_4BC], ax
0x18004eefa  mov     rcx, rbx
0x18004eefd  mov     [rsp+510h+var_4B0], rax
0x18004ef02  mov     [rsp+510h+var_4C0], ax
0x18004ef07  mov     [rsp+510h+var_4A8], 0
0x18004ef10  call    XCF_LookUpString
0x18004ef15  movzx   edx, word ptr [rbx+1E78h]
0x18004ef1c  lea     r9, [rsp+510h+var_4C0]
0x18004ef21  lea     r8, [rsp+510h+var_4B0]
0x18004ef26  mov     rcx, rbx
0x18004ef29  call    XCF_LookUpString
0x18004ef2e  mov     rcx, [rbx+1D0h]
0x18004ef35  lea     rdx, [rsp+510h+var_4B8]
0x18004ef3a  movzx   r9d, word ptr [rsp+510h+var_4BC]
0x18004ef40  mov     r8, [rsp+510h+var_4A8]
0x18004ef45  mov     rax, [rbx+1C8h]
0x18004ef4c  mov     [rsp+510h+var_4D8], rcx
0x18004ef51  mov     ecx, [rbx+1E7Ch]
0x18004ef57  mov     [rsp+510h+var_4E0], ecx
0x18004ef5b  movzx   ecx, [rsp+510h+var_4C0]
0x18004ef60  mov     [rsp+510h+var_4E8], cx
0x18004ef65  mov     rcx, [rsp+510h+var_4B0]
0x18004ef6a  mov     [rsp+510h+var_4F0], rcx
0x18004ef6f  mov     rcx, rbx
0x18004ef72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ef77  cmp     [rsp+510h+var_4B8], 0
0x18004ef7c  jnz     short loc_18004EFB2
0x18004ef7e  lea     rdx, aGlyphnames2uni; "/GlyphNames2Unicode 16 dict def"
0x18004ef85  mov     rcx, rbx
0x18004ef88  call    PutString
0x18004ef8d  mov     rdx, r15
0x18004ef90  mov     rcx, rbx
0x18004ef93  call    PutString
0x18004ef98  lea     rdx, aGlyphnames2hos; "/GlyphNames2HostCode 16 dict def"
0x18004ef9f  mov     rcx, rbx
0x18004efa2  call    PutString
0x18004efa7  mov     rdx, r15
0x18004efaa  mov     rcx, rbx
  ... truncated ...
```
