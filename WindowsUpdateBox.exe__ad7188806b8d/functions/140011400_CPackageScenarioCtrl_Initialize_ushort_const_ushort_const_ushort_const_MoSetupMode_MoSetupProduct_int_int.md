# CPackageScenarioCtrl::Initialize(ushort const *,ushort const *,ushort const *,MoSetupMode,MoSetupProduct,int,int)

- ea: `0x140011400`
- end: `0x140011669`
- name: `?Initialize@CPackageScenarioCtrl@@UEAAJPEBG00W4MoSetupMode@@W4MoSetupProduct@@HH@Z`
- size: `617`
- prototype: `int __high(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, enum MoSetupMode, enum MoSetupProduct, int, int)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x140002116`
- `0x140002a98`
- `0x1400076c8`
- `0x140008434`
- `0x140009f00`
- `0x140011400`
- `0x1400135b8`
- `0x140016bb4`
- `0x140018a38`
- `0x140080d70`

## import_xrefs

- `KERNEL32!GetSystemWindowsDirectoryW` at `0x140011514`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x140011514`
- `KERNEL32!GetLastError` at `0x140011524`
- `KERNEL32!GetLastError` at `0x140011524`
- `USER32!CharUpperW` at `0x140011574`
- `USER32!CharUpperW` at `0x140011587`
- `USER32!CharUpperW` at `0x140011574`
- `USER32!CharUpperW` at `0x140011587`

## pseudocode

```c
__int64 __fastcall CPackageScenarioCtrl::Initialize(
        __int64 a1,
        unsigned __int16 *a2,
        __int64 a3,
        _WORD *a4,
        int a5,
        unsigned int a6)
{
  HANDLE v6; // rsi
  int v10; // ebx
  int v11; // edi
  signed int LastError; // eax
  WCHAR v13; // r13
  unsigned __int16 v14; // r15
  WCHAR *v15; // rbx
  int StringCch; // eax
  __int64 v18; // [rsp+20h] [rbp-E0h]
  unsigned int v19; // [rsp+30h] [rbp-D0h] BYREF
  _OWORD Src[3]; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t v21; // [rsp+68h] [rbp-98h]
  WCHAR Buffer[264]; // [rsp+70h] [rbp-90h] BYREF

  v6 = 0;
  v21 = aWindowsLsSourc[24];
  Src[0] = *(_OWORD *)L"?:\\$Windows.~LS\\Sources\\";
  Src[1] = *(_OWORD *)L"ows.~LS\\Sources\\";
  Src[2] = *(_OWORD *)L"Sources\\";
  if ( !a2 || !a4 || (unsigned int)(a5 - 1) > 2 && a5 != 11 || a6 > 4 )
  {
    v10 = -2147024809;
    v11 = -2147024809;
LABEL_23:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v10);
    LODWORD(v18) = v11;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v6 = g_shLogFile;
    OutputMsg(v6, g_shLogEvent, L"%s: Error = 0x%X", L"CPackageScenarioCtrl::Initialize", v18);
    goto LABEL_26;
  }
  v11 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::Create(a2);
  v10 = v11;
  if ( v11 < 0 )
    goto LABEL_23;
  v11 = CMiscHelpersT<CEmptyType>::ParseFileName(a2, 0, (unsigned __int16 **)(a1 + 24), 0, 0);
  v10 = v11;
  if ( v11 < 0 )
    goto LABEL_23;
  v11 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::Create(a4);
  v10 = v11;
  if ( v11 < 0 )
    goto LABEL_23;
  *(_DWORD *)(a1 + 40) = a5;
  v11 = 0;
  memset_0(Buffer, 0, 0x208u);
  if ( GetSystemWindowsDirectoryW(Buffer, 0x104u) )
  {
    v13 = Buffer[0];
  }
  else
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v11 = -2147467259;
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v11);
    v13 = 0;
  }
  v10 = v11;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v11);
  if ( v11 < 0 )
    goto LABEL_23;
  v14 = *a2;
  v15 = CharUpperW((LPWSTR)*a2);
  if ( CharUpperW((LPWSTR)v13) != v15 )
  {
    *(_DWORD *)(a1 + 44) = 1;
    LOWORD(Src[0]) = v14;
    v19 = 0;
    StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(Src, &v19, 0x7FFFFFFF);
    v11 = StringCch;
    if ( StringCch < 0
      || (StringCch = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(
                        Src,
                        v19,
                        (_QWORD *)(a1 + 48)),
          v11 = StringCch,
          StringCch < 0) )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(StringCch);
    }
    v10 = v11;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v11);
    if ( v11 < 0 )
      goto LABEL_23;
  }
LABEL_26:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v11);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140011400  mov     [rsp-8+arg_10], rbx
0x140011405  push    rbp
0x140011406  push    rsi
0x140011407  push    rdi
0x140011408  push    r12
0x14001140a  push    r13
0x14001140c  push    r14
0x14001140e  push    r15
0x140011410  lea     rbp, [rsp-190h]
0x140011418  sub     rsp, 290h
0x14001141f  mov     rax, cs:__security_cookie
0x140011426  xor     rax, rsp
0x140011429  mov     [rbp+1C0h+var_40], rax
0x140011430  movups  xmm0, xmmword ptr cs:aWindowsLsSourc; "?:\\$Windows.~LS\\Sources\\"
0x140011437  movzx   eax, word ptr cs:aWindowsLsSourc+30h; ""
0x14001143e  xor     esi, esi
0x140011440  mov     [rsp+2C0h+var_258], ax
0x140011445  mov     r13, r9
0x140011448  mov     r12, rdx
0x14001144b  mov     r14, rcx
0x14001144e  movups  xmm1, xmmword ptr cs:aWindowsLsSourc+10h; "ows.~LS\\Sources\\"
0x140011455  movups  [rsp+2C0h+Src], xmm0
0x14001145a  movups  xmm0, xmmword ptr cs:aWindowsLsSourc+20h; "Sources\\"
0x140011461  movups  [rsp+2C0h+var_278], xmm1
0x140011466  movups  [rsp+2C0h+var_268], xmm0
0x14001146b  test    rdx, rdx
0x14001146e  jnz     short loc_14001147C
0x140011470  mov     ebx, 80070057h
0x140011475  mov     edi, ebx
0x140011477  jmp     loc_1400115F5
0x14001147c  test    r13, r13
0x14001147f  jz      short loc_140011470
0x140011481  mov     r15d, [rbp+1C0h+arg_20]
0x140011488  lea     eax, [r15-1]
0x14001148c  cmp     eax, 2
0x14001148f  jbe     short loc_140011497
0x140011491  cmp     r15d, 0Bh
0x140011495  jnz     short loc_140011470
0x140011497  cmp     [rbp+1C0h+arg_28], 4
0x14001149e  ja      short loc_140011470
0x1400114a0  lea     rdx, [rcx+10h]
0x1400114a4  mov     rcx, r12; Src
0x1400114a7  call    ?Create@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@SAJPEBGPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::Create(ushort const *,ushort * *)
0x1400114ac  mov     edi, eax
0x1400114ae  mov     ebx, eax
0x1400114b0  test    eax, eax
0x1400114b2  js      loc_1400115F5
0x1400114b8  lea     r8, [r14+18h]
0x1400114bc  mov     [rsp+2C0h+var_2A0], rsi; __int64
0x1400114c1  xor     r9d, r9d
0x1400114c4  xor     edx, edx
0x1400114c6  mov     rcx, r12; Src
0x1400114c9  call    ?ParseFileName@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAHPEAPEAG22@Z; CMiscHelpersT<CEmptyType>::ParseFileName(ushort const *,int *,ushort * *,ushort * *,ushort * *)
0x1400114ce  mov     edi, eax
0x1400114d0  mov     ebx, eax
0x1400114d2  test    eax, eax
0x1400114d4  js      loc_1400115F5
0x1400114da  lea     rdx, [r14+20h]
0x1400114de  mov     rcx, r13; Src
0x1400114e1  call    ?Create@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@SAJPEBGPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::Create(ushort const *,ushort * *)
0x1400114e6  mov     edi, eax
0x1400114e8  mov     ebx, eax
0x1400114ea  test    eax, eax
0x1400114ec  js      loc_1400115F5
0x1400114f2  xor     edx, edx; Val
0x1400114f4  mov     [r14+28h], r15d
0x1400114f8  mov     r8d, 208h; Size
0x1400114fe  lea     rcx, [rsp+2C0h+Buffer]; void *
0x140011503  mov     edi, esi
0x140011505  call    memset_0
0x14001150a  mov     edx, 104h; uSize
0x14001150f  lea     rcx, [rsp+2C0h+Buffer]; lpBuffer
0x140011514  call    cs:__imp_GetSystemWindowsDirectoryW
0x14001151b  nop     dword ptr [rax+rax+00h]
0x140011520  test    eax, eax
0x140011522  jnz     short loc_140011555
0x140011524  call    cs:__imp_GetLastError
0x14001152b  nop     dword ptr [rax+rax+00h]
0x140011530  mov     edi, eax
0x140011532  test    eax, eax
0x140011534  jnz     short loc_14001153D
0x140011536  mov     edi, 80004005h
0x14001153b  jmp     short loc_140011548
0x14001153d  jle     short loc_140011548
0x14001153f  movzx   edi, ax
0x140011542  or      edi, 80070000h
0x140011548  mov     ecx, edi
0x14001154a  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14001154f  movzx   r13d, si
0x140011553  jmp     short loc_14001155B
0x140011555  movzx   r13d, [rsp+2C0h+Buffer]
0x14001155b  mov     ecx, edi
0x14001155d  mov     ebx, edi
0x14001155f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140011564  test    edi, edi
0x140011566  js      loc_1400115F5
0x14001156c  movzx   r15d, word ptr [r12]
0x140011571  mov     ecx, r15d; lpsz
0x140011574  call    cs:__imp_CharUpperW
0x14001157b  nop     dword ptr [rax+rax+00h]
0x140011580  movzx   ecx, r13w; lpsz
0x140011584  mov     rbx, rax
0x140011587  call    cs:__imp_CharUpperW
0x14001158e  nop     dword ptr [rax+rax+00h]
0x140011593  cmp     rax, rbx
0x140011596  jz      loc_140011635
0x14001159c  mov     r8d, 7FFFFFFFh
0x1400115a2  mov     dword ptr [r14+2Ch], 1
0x1400115aa  lea     rdx, [rsp+2C0h+var_290]
0x1400115af  mov     word ptr [rsp+2C0h+Src], r15w
0x1400115b5  lea     rcx, [rsp+2C0h+Src]
0x1400115ba  mov     [rsp+2C0h+var_290], esi
0x1400115be  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x1400115c3  mov     edi, eax
0x1400115c5  test    eax, eax
0x1400115c7  js      short loc_1400115E1
0x1400115c9  mov     edx, [rsp+2C0h+var_290]
0x1400115cd  lea     r8, [r14+30h]
0x1400115d1  lea     rcx, [rsp+2C0h+Src]; Src
0x1400115d6  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x1400115db  mov     edi, eax
0x1400115dd  test    eax, eax
0x1400115df  jns     short loc_1400115E8
0x1400115e1  mov     ecx, eax
0x1400115e3  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1400115e8  mov     ecx, edi
0x1400115ea  mov     ebx, edi
0x1400115ec  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1400115f1  test    edi, edi
0x1400115f3  jns     short loc_140011635
0x1400115f5  mov     ecx, ebx
0x1400115f7  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1400115fc  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x140011603  lea     r9, aCpackagescenar_0; "CPackageScenarioCtrl::Initialize"
0x14001160a  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x140011611  mov     dword ptr [rsp+2C0h+var_2A0], edi
0x140011615  lea     rax, [r8-1]
0x140011619  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001161d  setnbe  al
0x140011620  test    al, al
0x140011622  cmovz   rsi, r8
0x140011626  lea     r8, aSError0xX; "%s: Error = 0x%X"
0x14001162d  mov     rcx, rsi; hFile
0x140011630  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x140011635  mov     ecx, edi
0x140011637  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001163c  mov     eax, edi
0x14001163e  mov     rcx, [rbp+1C0h+var_40]
0x140011645  xor     rcx, rsp; StackCookie
0x140011648  call    __security_check_cookie
0x14001164d  mov     rbx, [rsp+2C0h+arg_10]
0x140011655  add     rsp, 290h
0x14001165c  pop     r15
0x14001165e  pop     r14
0x140011660  pop     r13
0x140011662  pop     r12
0x140011664  pop     rdi
0x140011665  pop     rsi
0x140011666  pop     rbp
0x140011667  retn
```
