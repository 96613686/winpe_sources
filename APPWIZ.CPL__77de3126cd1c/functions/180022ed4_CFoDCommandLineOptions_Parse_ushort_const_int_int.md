# CFoDCommandLineOptions::Parse(ushort const *,int,int)

- ea: `0x180022ed4`
- end: `0x180023179`
- name: `?Parse@CFoDCommandLineOptions@@QEAAJPEBGHH@Z`
- size: `677`
- prototype: `__int64 __fastcall(CFoDCommandLineOptions *this, const unsigned __int16 *, int, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180029208`
- `0x1800298e4`

## callees

- `0x1800227c8`
- `0x1800228d0`
- `0x180022a70`
- `0x180022d34`
- `0x180022e20`
- `0x180022ed4`
- `0x180023180`
- `0x1800232c8`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180023004`
- `msvcrt!_wcsicmp` at `0x18002301e`
- `msvcrt!_wcsicmp` at `0x1800230db`
- `msvcrt!_wcsicmp` at `0x180023004`
- `msvcrt!_wcsicmp` at `0x18002301e`
- `msvcrt!_wcsicmp` at `0x1800230db`
- `SHCORE!CommandLineToArgvW` at `0x180022f27`
- `SHCORE!CommandLineToArgvW` at `0x180022f27`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023153`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023153`

## pseudocode

```c
__int64 __fastcall CFoDCommandLineOptions::Parse(
        CFoDCommandLineOptions *this,
        const unsigned __int16 *a2,
        int a3,
        int a4)
{
  unsigned int v4; // edi
  int v6; // r15d
  int v7; // ebx
  int v8; // r12d
  int v9; // r13d
  LPWSTR *v10; // rax
  CFoDCommandLineOptions *v11; // rcx
  int Command; // eax
  CFoDCommandLineOptions *v13; // rcx
  wchar_t *v14; // rbx
  int v15; // eax
  wchar_t *v16; // r14
  int Internal; // eax
  __int64 v18; // rcx
  wchar_t *v19; // r14
  int v20; // ebx
  __int64 v21; // rcx
  wchar_t *String2; // [rsp+20h] [rbp-28h] BYREF
  unsigned __int16 *v24; // [rsp+28h] [rbp-20h] BYREF
  LPWSTR *v25; // [rsp+30h] [rbp-18h]
  int v26; // [rsp+90h] [rbp+48h] BYREF
  int v27; // [rsp+98h] [rbp+50h]
  int v28; // [rsp+A0h] [rbp+58h]
  int pNumArgs; // [rsp+A8h] [rbp+60h] BYREF

  v28 = a3;
  v4 = 0;
  pNumArgs = 0;
  *((_DWORD *)this + 12) = 0;
  *((_DWORD *)this + 13) = a4;
  *((_DWORD *)this + 9) = 0;
  if ( !a2 )
    goto LABEL_46;
  v6 = 0;
  v7 = 0;
  v27 = 0;
  v8 = 0;
  v28 = 0;
  v9 = 0;
  v10 = CommandLineToArgvW(a2, &pNumArgs);
  v25 = v10;
  while ( v8 < pNumArgs )
  {
    v24 = 0;
    String2 = 0;
    v26 = 0;
    Command = CFoDCommandLineOptions::SplitArgs(v11, v10[v8], &v24, &String2);
    v4 = Command;
    if ( Command < 0
      || (Command = CFoDCommandLineOptions::GetCommand(v13, v24, (enum Command *)&v26), v4 = Command, Command < 0) )
    {
      v21 = (unsigned int)Command;
      goto LABEL_44;
    }
    switch ( v26 )
    {
      case 0:
        if ( v6 )
          goto LABEL_42;
        v19 = String2;
        if ( !String2 )
        {
LABEL_41:
          v21 = 2147942487LL;
          v4 = -2147024809;
          goto LABEL_44;
        }
        v6 = 1;
        v20 = 0;
        v27 = 1;
        while ( v20 < *((_DWORD *)this + 3) )
        {
          if ( !_wcsicmp(*(const wchar_t **)(*((_QWORD *)this + 2) + 8LL * v20), v19) )
            goto LABEL_38;
          ++v20;
        }
        CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Insert(
          (char *)this + 8,
          *((unsigned int *)this + 3),
          &String2);
        goto LABEL_38;
      case 1:
        if ( v7 )
          goto LABEL_42;
        v16 = String2;
        if ( !String2 )
          goto LABEL_41;
        v28 = 1;
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        Internal = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(v16);
        v18 = (unsigned int)Internal;
        if ( Internal < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)Internal);
        v7 = v28;
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v18);
        v6 = v27;
        break;
      case 2:
        if ( v9 || (v14 = String2) == 0 )
        {
LABEL_42:
          v4 = -2147024809;
          v21 = 2147942487LL;
          goto LABEL_44;
        }
        if ( !_wcsicmp(L"rebootrequest", String2) )
        {
          v15 = 1;
          goto LABEL_22;
        }
        if ( _wcsicmp(L"all", v14) )
        {
          v4 = -2147024809;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942487LL);
        }
        else
        {
          v15 = 2;
LABEL_22:
          v4 = 0;
          *((_DWORD *)this + 8) = v15;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
        if ( (v4 & 0x80000000) != 0 )
        {
          v21 = v4;
LABEL_44:
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v21);
          SH<unsigned short *,DH_SSTRING>::Reset(&String2);
          SH<unsigned short *,DH_SSTRING>::Reset(&v24);
          goto LABEL_47;
        }
        v9 = 1;
LABEL_38:
        v7 = v28;
        break;
      case 3:
        if ( String2 )
          goto LABEL_42;
        *((_DWORD *)this + 9) = 1;
        break;
      case 4:
        *((_DWORD *)this + 10) = 1;
        break;
      case 5:
        *((_DWORD *)this + 11) = 1;
        break;
      default:
        goto LABEL_42;
    }
    ++v8;
    SH<unsigned short *,DH_SSTRING>::Reset(&String2);
    SH<unsigned short *,DH_SSTRING>::Reset(&v24);
    v10 = v25;
  }
  LocalFree(v10);
LABEL_46:
  *(_DWORD *)this = 1;
LABEL_47:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  return v4;
}

```

## disassembly

```asm
0x180022ed4  mov     [rsp-40h+arg_10], r8d
0x180022ed9  push    rbp
0x180022eda  push    rbx
0x180022edb  push    rsi
0x180022edc  push    rdi
0x180022edd  push    r12
0x180022edf  push    r13
0x180022ee1  push    r14
0x180022ee3  push    r15
0x180022ee5  mov     rbp, rsp
0x180022ee8  sub     rsp, 48h
0x180022eec  xor     edi, edi
0x180022eee  mov     [rbp+pNumArgs], 0
0x180022ef5  mov     [rcx+30h], edi
0x180022ef8  mov     rax, rdx
0x180022efb  mov     [rcx+34h], r9d
0x180022eff  mov     rsi, rcx
0x180022f02  mov     [rcx+24h], edi
0x180022f05  test    rdx, rdx
0x180022f08  jz      loc_180023159
0x180022f0e  xor     r15d, r15d
0x180022f11  lea     rdx, [rbp+pNumArgs]; pNumArgs
0x180022f15  xor     ebx, ebx
0x180022f17  mov     [rbp+arg_8], r15d
0x180022f1b  xor     r12d, r12d
0x180022f1e  mov     [rbp+arg_10], ebx
0x180022f21  xor     r13d, r13d
0x180022f24  mov     rcx, rax; lpCmdLine
0x180022f27  call    cs:__imp_CommandLineToArgvW
0x180022f2d  mov     [rbp+var_18], rax
0x180022f31  mov     r14d, 80070057h
0x180022f37  cmp     r12d, [rbp+pNumArgs]
0x180022f3b  jge     loc_180023150
0x180022f41  movsxd  rdx, r12d
0x180022f44  lea     r9, [rbp+String2]; unsigned __int16 **
0x180022f48  lea     r8, [rbp+var_20]; unsigned __int16 **
0x180022f4c  mov     [rbp+var_20], 0
0x180022f54  mov     [rbp+String2], 0
0x180022f5c  mov     [rbp+arg_0], 0
0x180022f63  mov     rdx, [rax+rdx*8]; unsigned __int16 *
0x180022f67  call    ?SplitArgs@CFoDCommandLineOptions@@AEAAJPEAGPEAPEAG1@Z; CFoDCommandLineOptions::SplitArgs(ushort *,ushort * *,ushort * *)
0x180022f6c  mov     edi, eax
0x180022f6e  test    eax, eax
0x180022f70  js      loc_180023135
0x180022f76  mov     rdx, [rbp+var_20]; unsigned __int16 *
0x180022f7a  lea     r8, [rbp+arg_0]; enum Command *
0x180022f7e  call    ?GetCommand@CFoDCommandLineOptions@@AEAAJPEAGPEAW4Command@1@@Z; CFoDCommandLineOptions::GetCommand(ushort *,CFoDCommandLineOptions::Command *)
0x180022f83  mov     edi, eax
0x180022f85  test    eax, eax
0x180022f87  js      loc_180023135
0x180022f8d  mov     ecx, [rbp+arg_0]
0x180022f90  test    ecx, ecx
0x180022f92  jz      loc_1800230AE
0x180022f98  sub     ecx, 1
0x180022f9b  jz      loc_180023059
0x180022fa1  sub     ecx, 1
0x180022fa4  jz      short loc_180022FE4
0x180022fa6  sub     ecx, 1
0x180022fa9  jz      short loc_180022FCD
0x180022fab  sub     ecx, 1
0x180022fae  jz      short loc_180022FC1
0x180022fb0  cmp     ecx, 1
0x180022fb3  jnz     loc_18002312D
0x180022fb9  mov     [rsi+2Ch], ecx
0x180022fbc  jmp     loc_180023102
0x180022fc1  mov     dword ptr [rsi+28h], 1
0x180022fc8  jmp     loc_180023102
0x180022fcd  cmp     [rbp+String2], 0
0x180022fd2  jnz     loc_18002312D
0x180022fd8  mov     dword ptr [rsi+24h], 1
0x180022fdf  jmp     loc_180023102
0x180022fe4  test    r13d, r13d
0x180022fe7  jnz     loc_18002312D
0x180022fed  mov     rbx, [rbp+String2]
0x180022ff1  test    rbx, rbx
0x180022ff4  jz      loc_18002312D
0x180022ffa  mov     rdx, rbx; String2
0x180022ffd  lea     rcx, aRebootrequest; "rebootrequest"
0x180023004  call    cs:__imp__wcsicmp
0x18002300a  test    eax, eax
0x18002300c  jnz     short loc_180023014
0x18002300e  lea     eax, [r13+1]
0x180023012  jmp     short loc_18002302D
0x180023014  mov     rdx, rbx; String2
0x180023017  lea     rcx, aAll; "all"
0x18002301e  call    cs:__imp__wcsicmp
0x180023024  test    eax, eax
0x180023026  jnz     short loc_180023034
0x180023028  mov     eax, 2
0x18002302d  xor     edi, edi
0x18002302f  mov     [rsi+20h], eax
0x180023032  jmp     short loc_18002303F
0x180023034  mov     ecx, r14d
0x180023037  mov     edi, r14d
0x18002303a  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002303f  mov     ecx, edi
0x180023041  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180023046  test    edi, edi
0x180023048  js      loc_180023120
0x18002304e  mov     r13d, 1
0x180023054  jmp     loc_1800230FF
0x180023059  test    ebx, ebx
0x18002305b  jnz     loc_18002312D
0x180023061  mov     r14, [rbp+String2]
0x180023065  test    r14, r14
0x180023068  jz      loc_180023124
0x18002306e  mov     ebx, 1
0x180023073  xor     ecx, ecx
0x180023075  mov     [rbp+arg_10], ebx
0x180023078  mov     ebx, [r14-4]
0x18002307c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180023081  lea     r8, [rsi+18h]
0x180023085  mov     edx, ebx
0x180023087  mov     rcx, r14; Src
0x18002308a  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x18002308f  mov     ecx, eax
0x180023091  test    eax, eax
0x180023093  jns     short loc_18002309A
0x180023095  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002309a  mov     ebx, [rbp+arg_10]
0x18002309d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800230a2  mov     r15d, [rbp+arg_8]
0x1800230a6  mov     r14d, 80070057h
0x1800230ac  jmp     short loc_180023102
0x1800230ae  test    r15d, r15d
0x1800230b1  jnz     short loc_18002312D
0x1800230b3  mov     r14, [rbp+String2]
0x1800230b7  test    r14, r14
0x1800230ba  jz      short loc_180023124
0x1800230bc  mov     r15d, 1
0x1800230c2  xor     ebx, ebx
0x1800230c4  mov     [rbp+arg_8], r15d
0x1800230c8  cmp     ebx, [rsi+0Ch]
0x1800230cb  jge     short loc_1800230E9
0x1800230cd  mov     rcx, [rsi+10h]
0x1800230d1  mov     rdx, r14; String2
0x1800230d4  movsxd  rax, ebx
0x1800230d7  mov     rcx, [rcx+rax*8]; String1
0x1800230db  call    cs:__imp__wcsicmp
0x1800230e1  test    eax, eax
0x1800230e3  jz      short loc_1800230F9
0x1800230e5  inc     ebx
0x1800230e7  jmp     short loc_1800230C8
0x1800230e9  lea     rcx, [rsi+8]
0x1800230ed  mov     edx, [rcx+4]
0x1800230f0  lea     r8, [rbp+String2]
0x1800230f4  call    ?Insert@?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJHAEBVDH_SSTRING@@@Z; CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Insert(int,DH_SSTRING const &)
0x1800230f9  mov     r14d, 80070057h
0x1800230ff  mov     ebx, [rbp+arg_10]
0x180023102  lea     rcx, [rbp+String2]
0x180023106  inc     r12d
0x180023109  call    ?Reset@?$SH@PEAGVDH_SSTRING@@@@QEAAXXZ; SH<ushort *,DH_SSTRING>::Reset(void)
0x18002310e  lea     rcx, [rbp+var_20]
0x180023112  call    ?Reset@?$SH@PEAGVDH_SSTRING@@@@QEAAXXZ; SH<ushort *,DH_SSTRING>::Reset(void)
0x180023117  mov     rax, [rbp+var_18]
0x18002311b  jmp     loc_180022F37
0x180023120  mov     ecx, edi
0x180023122  jmp     short loc_180023137
0x180023124  mov     ecx, 80070057h
0x180023129  mov     edi, ecx
0x18002312b  jmp     short loc_180023137
0x18002312d  mov     edi, r14d
0x180023130  mov     ecx, r14d
0x180023133  jmp     short loc_180023137
0x180023135  mov     ecx, eax
0x180023137  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002313c  lea     rcx, [rbp+String2]
0x180023140  call    ?Reset@?$SH@PEAGVDH_SSTRING@@@@QEAAXXZ; SH<ushort *,DH_SSTRING>::Reset(void)
0x180023145  lea     rcx, [rbp+var_20]
0x180023149  call    ?Reset@?$SH@PEAGVDH_SSTRING@@@@QEAAXXZ; SH<ushort *,DH_SSTRING>::Reset(void)
0x18002314e  jmp     short loc_18002315F
0x180023150  mov     rcx, rax; hMem
0x180023153  call    cs:__imp_LocalFree
0x180023159  mov     dword ptr [rsi], 1
0x18002315f  mov     ecx, edi
0x180023161  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180023166  mov     eax, edi
0x180023168  add     rsp, 48h
0x18002316c  pop     r15
0x18002316e  pop     r14
0x180023170  pop     r13
0x180023172  pop     r12
0x180023174  pop     rdi
0x180023175  pop     rsi
0x180023176  pop     rbx
0x180023177  pop     rbp
0x180023178  retn
```
