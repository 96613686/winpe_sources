# CMiscHelpersT<CEmptyType>::ExpandFileName(ushort const *,ushort * *)

- ea: `0x1800133e0`
- end: `0x180013565`
- name: `?ExpandFileName@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAPEAG@Z`
- size: `389`
- prototype: `__int64 __fastcall(__int64, LPWSTR *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800117b0`

## callees

- `0x180001ac0`
- `0x1800090dc`
- `0x180009480`
- `0x18000b448`
- `0x18000b57c`
- `0x18000b68c`
- `0x1800133e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013539`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013539`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001352a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001352a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800134f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800134f3`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001341d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800134e9`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001341d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800134e9`

## string_xrefs

- `0x180013402`: `%windir%\system32\Clipup.exe`
- `0x1800134dc`: `%windir%\system32\Clipup.exe`

## pseudocode

```c
__int64 __fastcall CMiscHelpersT<CEmptyType>::ExpandFileName(__int64 a1, LPWSTR *a2)
{
  LPWSTR v3; // rbx
  DWORD v4; // eax
  DWORD v5; // esi
  int StringCch; // eax
  unsigned int v7; // edi
  __int64 v8; // rcx
  int CchBufferN; // eax
  DWORD v10; // eax
  signed int LastError; // eax
  LPWSTR v12; // rax
  HANDLE ProcessHeap; // rax
  LPWSTR lpDst[2]; // [rsp+20h] [rbp-258h] BYREF
  WCHAR Dst[264]; // [rsp+30h] [rbp-248h] BYREF

  v3 = 0;
  lpDst[0] = 0;
  v4 = ExpandEnvironmentStringsW(L"%windir%\\system32\\Clipup.exe", Dst, 0x104u);
  v5 = v4;
  if ( !v4 )
    goto LABEL_17;
  if ( v4 <= 0x104 )
  {
    LODWORD(lpDst[0]) = 0;
    StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(Dst, lpDst);
    v7 = StringCch;
    if ( StringCch < 0
      || (StringCch = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(Dst),
          v7 = StringCch,
          StringCch < 0) )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)StringCch);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
    if ( (v7 & 0x80000000) != 0 )
      goto LABEL_11;
    goto LABEL_22;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  CchBufferN = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateCchBufferN(v8, v5, lpDst);
  v7 = CchBufferN;
  if ( CchBufferN < 0 )
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)CchBufferN);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  if ( (v7 & 0x80000000) != 0 )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
    v3 = lpDst[0];
    goto LABEL_22;
  }
  v3 = lpDst[0];
  v10 = ExpandEnvironmentStringsW(L"%windir%\\system32\\Clipup.exe", lpDst[0], v5);
  if ( !v10 )
  {
LABEL_17:
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v7 = -2147467259;
    }
    goto LABEL_11;
  }
  if ( v10 != v5 )
  {
    v7 = -2147024774;
LABEL_11:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
    goto LABEL_22;
  }
  v12 = v3;
  v3 = 0;
  *a2 = v12;
LABEL_22:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  if ( v3 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v3 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return v7;
}

```

## disassembly

```asm
0x1800133e0  push    rbx
0x1800133e2  push    rsi
0x1800133e3  push    rdi
0x1800133e4  push    r14
0x1800133e6  sub     rsp, 258h
0x1800133ed  mov     rax, cs:__security_cookie
0x1800133f4  xor     rax, rsp
0x1800133f7  mov     [rsp+278h+var_38], rax
0x1800133ff  mov     r14, rdx
0x180013402  lea     rcx, aWindirSystem32; "%windir%\\system32\\Clipup.exe"
0x180013409  mov     edi, 104h
0x18001340e  lea     rdx, [rsp+278h+Dst]; lpDst
0x180013413  xor     ebx, ebx
0x180013415  mov     r8d, edi; nSize
0x180013418  mov     [rsp+278h+lpDst], rbx
0x18001341d  call    cs:__imp_ExpandEnvironmentStringsW
0x180013423  mov     esi, eax
0x180013425  test    eax, eax
0x180013427  jz      loc_1800134F3
0x18001342d  cmp     eax, edi
0x18001342f  ja      short loc_180013497
0x180013431  lea     rdx, [rsp+278h+lpDst]
0x180013436  mov     dword ptr [rsp+278h+lpDst], ebx
0x18001343a  lea     rcx, [rsp+278h+Dst]
0x18001343f  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x180013444  mov     edi, eax
0x180013446  test    eax, eax
0x180013448  js      short loc_180013461
0x18001344a  mov     edx, dword ptr [rsp+278h+lpDst]
0x18001344e  lea     rcx, [rsp+278h+Dst]; Src
0x180013453  mov     r8, r14
0x180013456  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x18001345b  mov     edi, eax
0x18001345d  test    eax, eax
0x18001345f  jns     short loc_180013468
0x180013461  mov     ecx, eax
0x180013463  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180013468  mov     ecx, edi
0x18001346a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001346f  test    edi, edi
0x180013471  jns     loc_18001351E
0x180013477  jmp     short loc_18001348B
0x180013479  mov     edi, 80004005h
0x18001347e  jmp     short loc_18001348B
0x180013480  jle     short loc_18001348B
0x180013482  movzx   edi, ax
0x180013485  or      edi, 80070000h
0x18001348b  mov     ecx, edi
0x18001348d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180013492  jmp     loc_18001351E
0x180013497  xor     ecx, ecx
0x180013499  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001349e  xor     ecx, ecx
0x1800134a0  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800134a5  lea     r8, [rsp+278h+lpDst]
0x1800134aa  mov     edx, esi
0x1800134ac  call    ?CreateCchBufferN@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@SAJGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateCchBufferN(ushort,ulong,ushort * *)
0x1800134b1  mov     edi, eax
0x1800134b3  test    eax, eax
0x1800134b5  jns     short loc_1800134BE
0x1800134b7  mov     ecx, eax
0x1800134b9  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800134be  mov     ecx, edi
0x1800134c0  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800134c5  test    edi, edi
0x1800134c7  jns     short loc_1800134D7
0x1800134c9  mov     ecx, edi
0x1800134cb  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800134d0  mov     rbx, [rsp+278h+lpDst]
0x1800134d5  jmp     short loc_18001351E
0x1800134d7  mov     rbx, [rsp+278h+lpDst]
0x1800134dc  lea     rcx, aWindirSystem32; "%windir%\\system32\\Clipup.exe"
0x1800134e3  mov     rdx, rbx; lpDst
0x1800134e6  mov     r8d, esi; nSize
0x1800134e9  call    cs:__imp_ExpandEnvironmentStringsW
0x1800134ef  test    eax, eax
0x1800134f1  jnz     short loc_180013508
0x1800134f3  call    cs:__imp_GetLastError
0x1800134f9  mov     edi, eax
0x1800134fb  test    eax, eax
0x1800134fd  jz      loc_180013479
0x180013503  jmp     loc_180013480
0x180013508  cmp     eax, esi
0x18001350a  jz      short loc_180013516
0x18001350c  mov     edi, 8007007Ah
0x180013511  jmp     loc_18001348B
0x180013516  mov     rax, rbx
0x180013519  xor     ebx, ebx
0x18001351b  mov     [r14], rax
0x18001351e  mov     ecx, edi
0x180013520  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180013525  test    rbx, rbx
0x180013528  jz      short loc_180013546
0x18001352a  call    cs:__imp_GetProcessHeap
0x180013530  lea     r8, [rbx-4]; lpMem
0x180013534  xor     edx, edx; dwFlags
0x180013536  mov     rcx, rax; hHeap
0x180013539  call    cs:__imp_HeapFree
0x18001353f  xor     ecx, ecx
0x180013541  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180013546  mov     eax, edi
0x180013548  mov     rcx, [rsp+278h+var_38]
0x180013550  xor     rcx, rsp; StackCookie
0x180013553  call    __security_check_cookie
0x180013558  add     rsp, 258h
0x18001355f  pop     r14
0x180013561  pop     rdi
0x180013562  pop     rsi
0x180013563  pop     rbx
0x180013564  retn
```
