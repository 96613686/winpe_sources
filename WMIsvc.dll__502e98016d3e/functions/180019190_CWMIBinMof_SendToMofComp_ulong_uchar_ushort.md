# CWMIBinMof::SendToMofComp(ulong,uchar *,ushort *)

- ea: `0x180019190`
- end: `0x180019354`
- name: `?SendToMofComp@CWMIBinMof@@AEAAJKPEAEPEAG@Z`
- size: `452`
- prototype: `int(CWMIBinMof *__hidden this, unsigned int, unsigned __int8 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000226c`
- `0x180002a5c`

## callees

- `0x180003e10`
- `0x180019190`
- `0x18001d3a0`
- `0x180020010`

## import_xrefs

- `wbemcomn!DebugTrace` at `0x1800192fa`
- `wbemcomn!DebugTrace` at `0x180019309`
- `wbemcomn!DebugTrace` at `0x180019321`
- `wbemcomn!DebugTrace` at `0x1800192fa`
- `wbemcomn!DebugTrace` at `0x180019309`
- `wbemcomn!DebugTrace` at `0x180019321`
- `wbemcomn!ErrorTrace` at `0x18001925d`
- `wbemcomn!ErrorTrace` at `0x18001926c`
- `wbemcomn!ErrorTrace` at `0x180019288`
- `wbemcomn!ErrorTrace` at `0x180019293`
- `wbemcomn!ErrorTrace` at `0x1800192a2`
- `wbemcomn!ErrorTrace` at `0x1800192b6`
- `wbemcomn!ErrorTrace` at `0x1800192ca`
- `wbemcomn!ErrorTrace` at `0x1800192d5`
- `wbemcomn!ErrorTrace` at `0x1800192e7`
- `wbemcomn!ErrorTrace` at `0x1800192f2`
- `wbemcomn!ErrorTrace` at `0x18001925d`
- `wbemcomn!ErrorTrace` at `0x18001926c`
- `wbemcomn!ErrorTrace` at `0x180019288`
- `wbemcomn!ErrorTrace` at `0x180019293`
- `wbemcomn!ErrorTrace` at `0x1800192a2`
- `wbemcomn!ErrorTrace` at `0x1800192b6`
- `wbemcomn!ErrorTrace` at `0x1800192ca`
- `wbemcomn!ErrorTrace` at `0x1800192d5`
- `wbemcomn!ErrorTrace` at `0x1800192e7`
- `wbemcomn!ErrorTrace` at `0x1800192f2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800191db`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800191db`

## string_xrefs

- `0x180019263`: `Mofcomp of binary mof failed for:\n`
- `0x18001927f`: `WinmgmtCompileBuffer return value: %ld\n`
- `0x180019299`: `WBEM_COMPILE_STATUS_INFO:\n`

## pseudocode

```c
__int64 __fastcall CWMIBinMof::SendToMofComp(
        CWMIBinMof *this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned __int16 *a4)
{
  __int64 *v4; // rbx
  unsigned int Instance; // edi
  __int64 v10; // r8
  __int64 v11; // rcx
  __int128 v13; // [rsp+50h] [rbp-58h] BYREF
  __int64 v14; // [rsp+60h] [rbp-48h]

  v4 = (__int64 *)((char *)this + 32);
  if ( *((_QWORD *)this + 4)
    || (Instance = CoCreateInstance(&CLSID_WinmgmtMofCompiler, 0, 1u, &IID_IWinmgmtMofCompiler, (LPVOID *)this + 4)) == 0 )
  {
    v10 = *((_QWORD *)this + 3);
    v11 = *v4;
    v14 = 0;
    v13 = 0;
    Instance = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int8 *, __int64, int, int, _QWORD, _QWORD, __int128 *))(*(_QWORD *)v11 + 32LL))(
                 v11,
                 a2,
                 a3,
                 256,
                 0x10000,
                 0x10000,
                 *(_QWORD *)(v10 + 8),
                 *(_QWORD *)(v10 + 24),
                 &v13);
    if ( Instance )
    {
      ErrorTrace(10, "***************************************\n");
      ErrorTrace(10, "Mofcomp of binary mof failed for:\n");
      TranslateAndLog(a4, 0);
      ErrorTrace(10, "WinmgmtCompileBuffer return value: %ld\n", Instance);
      ErrorTrace(10, "***************************************\n");
      ErrorTrace(10, "WBEM_COMPILE_STATUS_INFO:\n");
      ErrorTrace(10, "\tphase:\t%d\n", (_DWORD)v13);
      ErrorTrace(10, "\thresult:\t0x%x\n", DWORD1(v13));
      ErrorTrace(10, "***************************************\n");
      ErrorTrace(10, "Size of Mof: %ld\n", a2);
      ErrorTrace(10, "***************************************\n");
    }
    else
    {
      DebugTrace(10, "***************************************\n");
      DebugTrace(10, "Binary mof succeeded for:\n");
      TranslateAndLog(a4, 1);
      DebugTrace(10, "***************************************\n");
    }
    if ( DWORD1(v13) == -2147217357 )
      *((_DWORD *)this + 10) = 1;
  }
  return Instance;
}

```

## disassembly

```asm
0x180019190  push    rbx
0x180019192  push    rbp
0x180019193  push    rsi
0x180019194  push    rdi
0x180019195  push    r14
0x180019197  push    r15
0x180019199  sub     rsp, 78h
0x18001919d  mov     rax, cs:__security_cookie
0x1800191a4  xor     rax, rsp
0x1800191a7  mov     [rsp+0A8h+var_40], rax
0x1800191ac  lea     rbx, [rcx+20h]
0x1800191b0  mov     r14, r9
0x1800191b3  cmp     qword ptr [rbx], 0
0x1800191b7  mov     rsi, r8
0x1800191ba  mov     r15d, edx
0x1800191bd  mov     rbp, rcx
0x1800191c0  jnz     short loc_1800191EB
0x1800191c2  xor     edx, edx; pUnkOuter
0x1800191c4  mov     [rsp+0A8h+ppv], rbx; ppv
0x1800191c9  lea     r9, IID_IWinmgmtMofCompiler; riid
0x1800191d0  lea     rcx, CLSID_WinmgmtMofCompiler; rclsid
0x1800191d7  lea     r8d, [rdx+1]; dwClsContext
0x1800191db  call    cs:__imp_CoCreateInstance
0x1800191e1  mov     edi, eax
0x1800191e3  test    eax, eax
0x1800191e5  jnz     loc_180019338
0x1800191eb  mov     r8, [rbp+18h]
0x1800191ef  lea     rdx, [rsp+0A8h+var_58]
0x1800191f4  mov     rcx, [rbx]
0x1800191f7  xor     eax, eax
0x1800191f9  mov     [rsp+0A8h+var_68], rdx
0x1800191fe  xorps   xmm0, xmm0
0x180019201  mov     [rsp+0A8h+var_48], rax
0x180019206  mov     r9d, 100h
0x18001920c  movups  [rsp+0A8h+var_58], xmm0
0x180019211  mov     rdx, [r8+18h]
0x180019215  mov     rax, [rcx]
0x180019218  mov     [rsp+0A8h+var_70], rdx
0x18001921d  mov     rdx, [r8+8]
0x180019221  mov     r8, rsi
0x180019224  mov     [rsp+0A8h+var_78], rdx
0x180019229  mov     edx, 10000h
0x18001922e  mov     rax, [rax+20h]
0x180019232  mov     [rsp+0A8h+var_80], edx
0x180019236  mov     dword ptr [rsp+0A8h+ppv], edx
0x18001923a  mov     edx, r15d
0x18001923d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019242  lea     rsi, asc_180023540; "***************************************"...
0x180019249  mov     ebx, 0Ah
0x18001924e  mov     rdx, rsi
0x180019251  mov     ecx, ebx
0x180019253  mov     edi, eax
0x180019255  test    eax, eax
0x180019257  jz      loc_1800192FA
0x18001925d  call    cs:__imp_?ErrorTrace@@YAHDPEBDZZ; ErrorTrace(char,char const *,...)
0x180019263  lea     rdx, aMofcompOfBinar; "Mofcomp of binary mof failed for:\n"
0x18001926a  mov     ecx, ebx
0x18001926c  call    cs:__imp_?ErrorTrace@@YAHDPEBDZZ; ErrorTrace(char,char const *,...)
0x180019272  xor     edx, edx; int
0x180019274  mov     rcx, r14; lpWideCharStr
0x180019277  call    ?TranslateAndLog@@YAXPEAGH@Z; TranslateAndLog(ushort *,int)
0x18001927c  mov     r8d, edi
0x18001927f  lea     rdx, aWinmgmtcompile; "WinmgmtCompileBuffer return value: %ld"...
0x180019286  mov     ecx, ebx
0x180019288  call    cs:__imp_?ErrorTrace@@YAHDPEBDZZ; ErrorTrace(char,char const *,...)
0x18001928e  mov     rdx, rsi
0x180019291  mov     ecx, ebx
0x180019293  call    cs:__imp_?ErrorTrace@@YAHDPEBDZZ; ErrorTrace(char,char const *,...)
0x180019299  lea     rdx, aWbemCompileSta; "WBEM_COMPILE_STATUS_INFO:\n"
0x1800192a0  mov     ecx, ebx
0x1800192a2  call    cs:__imp_?ErrorTrace@@YAHDPEBDZZ; ErrorTrace(char,char const *,...)
0x1800192a8  mov     r8d, dword ptr [rsp+0A8h+var_58]
0x1800192ad  lea     rdx, aPhaseD; "\tphase:\t%d\n"
0x1800192b4  mov     ecx, ebx
0x1800192b6  call    cs:__imp_?ErrorTrace@@YAHDPEBDZZ; ErrorTrace(char,char const *,...)
0x1800192bc  mov     r8d, dword ptr [rsp+0A8h+var_58+4]
0x1800192c1  lea     rdx, aHresult0xX; "\thresult:\t0x%x\n"
0x1800192c8  mov     ecx, ebx
0x1800192ca  call    cs:__imp_?ErrorTrace@@YAHDPEBDZZ; ErrorTrace(char,char const *,...)
0x1800192d0  mov     rdx, rsi
0x1800192d3  mov     ecx, ebx
0x1800192d5  call    cs:__imp_?ErrorTrace@@YAHDPEBDZZ; ErrorTrace(char,char const *,...)
0x1800192db  mov     r8d, r15d
0x1800192de  lea     rdx, aSizeOfMofLd; "Size of Mof: %ld\n"
0x1800192e5  mov     ecx, ebx
0x1800192e7  call    cs:__imp_?ErrorTrace@@YAHDPEBDZZ; ErrorTrace(char,char const *,...)
0x1800192ed  mov     rdx, rsi
0x1800192f0  mov     ecx, ebx
0x1800192f2  call    cs:__imp_?ErrorTrace@@YAHDPEBDZZ; ErrorTrace(char,char const *,...)
0x1800192f8  jmp     short loc_180019327
0x1800192fa  call    cs:__imp_?DebugTrace@@YAHDPEBDZZ; DebugTrace(char,char const *,...)
0x180019300  lea     rdx, aBinaryMofSucce; "Binary mof succeeded for:\n"
0x180019307  mov     ecx, ebx
0x180019309  call    cs:__imp_?DebugTrace@@YAHDPEBDZZ; DebugTrace(char,char const *,...)
0x18001930f  mov     edx, 1; int
0x180019314  mov     rcx, r14; lpWideCharStr
0x180019317  call    ?TranslateAndLog@@YAXPEAGH@Z; TranslateAndLog(ushort *,int)
0x18001931c  mov     rdx, rsi
0x18001931f  mov     ecx, ebx
0x180019321  call    cs:__imp_?DebugTrace@@YAHDPEBDZZ; DebugTrace(char,char const *,...)
0x180019327  cmp     dword ptr [rsp+0A8h+var_58+4], 80041033h
0x18001932f  jnz     short loc_180019338
0x180019331  mov     dword ptr [rbp+28h], 1
0x180019338  mov     eax, edi
0x18001933a  mov     rcx, [rsp+0A8h+var_40]
0x18001933f  xor     rcx, rsp; StackCookie
0x180019342  call    __security_check_cookie
0x180019347  add     rsp, 78h
0x18001934b  pop     r15
0x18001934d  pop     r14
0x18001934f  pop     rdi
0x180019350  pop     rsi
0x180019351  pop     rbp
0x180019352  pop     rbx
0x180019353  retn
```
