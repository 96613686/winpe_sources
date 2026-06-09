# CWLIDCCHelper::GetSID(IWinApiLite *,ushort const *,ushort * *)

- ea: `0x180027724`
- end: `0x180027a4d`
- name: `?GetSID@CWLIDCCHelper@@SAJPEAVIWinApiLite@@PEBGPEAPEAG@Z`
- size: `809`
- prototype: `__int64 __fastcall(struct IWinApiLite *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x180010320`
- `0x180010e70`
- `0x180015468`
- `0x180017c20`

## callees

- `0x180003160`
- `0x180003b14`
- `0x180007484`
- `0x18000d91c`
- `0x18000def8`
- `0x180023b5c`
- `0x180023c04`
- `0x180024934`
- `0x180026c8c`
- `0x180027724`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027835`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800278d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027835`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800278d4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800278c2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800278c2`

## string_xrefs

- `0x1800277fb`: `CWLIDCCHelper::GetSID`
- `0x18002792f`: `hr = StringCchPrintf( spQualifiedUser, MAX_PATH, L"%ls\\%ls", machineName, pUserName )`

## pseudocode

```c
__int64 __fastcall CWLIDCCHelper::GetSID(struct IWinApiLite *a1, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  signed int LastError; // eax
  const char *v7; // rcx
  unsigned int v8; // r8d
  unsigned int v9; // ebx
  __int64 v10; // rsi
  unsigned __int16 *v11; // rbx
  bool v12; // sf
  int v13; // eax
  __int64 v14; // r9
  signed int v15; // eax
  unsigned __int16 *v16; // rax
  unsigned int v17; // ebx
  int v19; // [rsp+50h] [rbp-B0h] BYREF
  int v20; // [rsp+54h] [rbp-ACh] BYREF
  int v21; // [rsp+58h] [rbp-A8h] BYREF
  int v22; // [rsp+5Ch] [rbp-A4h] BYREF
  int v23; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v24; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v25; // [rsp+70h] [rbp-90h] BYREF
  __int64 v26; // [rsp+78h] [rbp-88h]
  __int64 v27; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v28; // [rsp+88h] [rbp-78h] BYREF
  __int64 v29; // [rsp+90h] [rbp-70h]
  __int64 v30; // [rsp+98h] [rbp-68h]
  int *v31[4]; // [rsp+A0h] [rbp-60h] BYREF
  _OWORD v32[2]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v33[80]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v34[528]; // [rsp+130h] [rbp+30h] BYREF

  v19 = 0;
  memset_0(v33, 0, 0x44u);
  v21 = 7;
  v23 = 68;
  memset_0(v34, 0, 0x208u);
  v22 = 260;
  v25 = 0;
  v27 = 0;
  v26 = 0;
  memset(v32, 0, sizeof(v32));
  v20 = 16;
  v28 = 0;
  v30 = 0;
  v29 = 0;
  v24 = 0;
  ErrorVerifier::ErrorVerifier((ErrorVerifier *)v31, "CWLIDCCHelper::GetSID", &v19, 11, &qword_180040A50);
  *a3 = 0;
  if ( (*(unsigned int (__fastcall **)(struct IWinApiLite *, _OWORD *, int *))(*(_QWORD *)a1 + 360LL))(a1, v32, &v20) )
    goto LABEL_7;
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  v19 = LastError;
  if ( LastError >= 0 )
  {
LABEL_7:
    LastError = StringCchLengthW(a2, 0x7FFFFFFEu, &v24);
    v19 = LastError;
    if ( LastError < 0 )
    {
      v7 = "hr = StringCchLengthW(pUserName, STRSAFE_MAX_LENGTH, &userNameLen)";
      v8 = 626;
      goto LABEL_6;
    }
    v9 = 2 * (v20 + v24) + 4;
    Auto<unsigned char *,LocalAllocFunctor<unsigned char *>,DummyContext>::Clear((__int64)&v28);
    v10 = v9;
    v11 = (unsigned __int16 *)LocalAlloc(0x40u, v9);
    v28 = v11;
    if ( v11 )
    {
      LastError = 0;
    }
    else
    {
      LastError = GetLastError();
      v12 = LastError < 0;
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v12 = LastError < 0;
      }
      if ( v12 )
      {
        v19 = LastError;
        v7 = "hr = spQualifiedUser.Allocate(qualifiedSize)";
        v8 = 631;
        goto LABEL_6;
      }
    }
    v29 = v10;
    v19 = LastError;
    LastError = StringCchPrintfW(v11, 0x104u, L"%ls\\%ls", v32, a2);
    v19 = LastError;
    if ( LastError < 0 )
    {
      v7 = "hr = StringCchPrintf( spQualifiedUser, MAX_PATH, L\"%ls\\\\%ls\", machineName, pUserName )";
      v8 = 639;
      goto LABEL_6;
    }
    v13 = (*(__int64 (__fastcall **)(struct IWinApiLite *, _QWORD, unsigned __int16 *, _BYTE *, int *, _BYTE *, int *, int *))(*(_QWORD *)a1 + 184LL))(
            a1,
            0,
            v11,
            v33,
            &v23,
            v34,
            &v22,
            &v21);
    v14 = *(_QWORD *)a1;
    if ( v13 )
    {
      if ( (*(unsigned int (__fastcall **)(struct IWinApiLite *, _BYTE *, unsigned __int16 **))(v14 + 192))(
             a1,
             v33,
             &v25) )
      {
        v16 = v25;
        v25 = 0;
        v26 = 0;
        *a3 = v16;
        goto LABEL_26;
      }
      v15 = (*(__int64 (__fastcall **)(struct IWinApiLite *))(*(_QWORD *)a1 + 120LL))(a1);
    }
    else
    {
      v15 = (*(__int64 (__fastcall **)(struct IWinApiLite *))(v14 + 120))(a1);
      if ( v15 == 1332 )
      {
        LOWORD(v15) = 1317;
        goto LABEL_21;
      }
    }
    if ( v15 <= 0 )
    {
LABEL_22:
      v19 = v15;
      goto LABEL_26;
    }
LABEL_21:
    v15 = (unsigned __int16)v15 | 0x80070000;
    goto LABEL_22;
  }
  v7 = "hr = HRESULT_FROM_WIN32(GetLastError())";
  v8 = 624;
LABEL_6:
  Telemetry::IfFailExit(
    "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\wlidcchelper.cpp",
    "CWLIDCCHelper::GetSID",
    v8,
    LastError,
    v7);
LABEL_26:
  v17 = v19;
  ErrorVerifier::CheckAgainstList((PPTraceStatus *)v31[3], *v31[2], (unsigned __int64)v31[1], v31[0]);
  Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>((__int64)&v28);
  Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>((__int64)&v25);
  return v17;
}

```

## disassembly

```asm
0x180027724  push    rbp
0x180027726  push    rbx
0x180027727  push    rsi
0x180027728  push    rdi
0x180027729  push    r13
0x18002772b  push    r14
0x18002772d  push    r15
0x18002772f  lea     rbp, [rsp-250h]
0x180027737  sub     rsp, 350h
0x18002773e  mov     rax, cs:__security_cookie
0x180027745  xor     rax, rsp
0x180027748  mov     [rbp+280h+var_40], rax
0x18002774f  mov     r15, r8
0x180027752  mov     r14, rdx
0x180027755  mov     rdi, rcx
0x180027758  mov     [rsp+380h+var_330], 0
0x180027760  mov     ebx, 44h ; 'D'
0x180027765  mov     r8d, ebx; Size
0x180027768  xor     edx, edx; Val
0x18002776a  lea     rcx, [rbp+280h+var_2A0]; void *
0x18002776e  call    memset_0
0x180027773  mov     [rsp+380h+var_328], 7
0x18002777b  mov     [rsp+380h+var_320], ebx
0x18002777f  xor     edx, edx; Val
0x180027781  mov     r8d, 208h; Size
0x180027787  lea     rcx, [rbp+280h+var_250]; void *
0x18002778b  call    memset_0
0x180027790  mov     [rsp+380h+var_324], 104h
0x180027798  mov     [rsp+380h+var_310], 0
0x1800277a1  mov     [rbp+280h+var_300], 0
0x1800277a9  mov     [rsp+380h+var_308], 0
0x1800277b2  xorps   xmm0, xmm0
0x1800277b5  movups  [rbp+280h+var_2C0], xmm0
0x1800277b9  movups  [rbp+280h+var_2B0], xmm0
0x1800277bd  mov     [rsp+380h+var_32C], 10h
0x1800277c5  mov     [rbp+280h+var_2F8], 0
0x1800277cd  mov     [rbp+280h+var_2E8], 0
0x1800277d5  mov     [rbp+280h+var_2F0], 0
0x1800277dd  mov     [rsp+380h+var_318], 0
0x1800277e6  lea     rax, qword_180040A50
0x1800277ed  mov     [rsp+380h+var_360], rax; int *
0x1800277f2  lea     r9d, [rbx-39h]; unsigned __int64
0x1800277f6  lea     r8, [rsp+380h+var_330]; int *
0x1800277fb  lea     r13, aCwlidcchelperG_0; "CWLIDCCHelper::GetSID"
0x180027802  mov     rdx, r13; char *
0x180027805  lea     rcx, [rbp+280h+var_2E0]; this
0x180027809  call    ??0ErrorVerifier@@QEAA@PEBDPEAJ_KPEBJ@Z; ErrorVerifier::ErrorVerifier(char const *,long *,unsigned __int64,long const *)
0x18002780e  nop
0x18002780f  mov     qword ptr [r15], 0
0x180027816  mov     rax, [rdi]
0x180027819  lea     r8, [rsp+380h+var_32C]
0x18002781e  lea     rdx, [rbp+280h+var_2C0]
0x180027822  mov     rcx, rdi
0x180027825  mov     rax, [rax+168h]
0x18002782c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027831  test    eax, eax
0x180027833  jnz     short loc_180027878
0x180027835  call    cs:__imp_GetLastError
0x18002783b  test    eax, eax
0x18002783d  jle     short loc_180027847
0x18002783f  movzx   eax, ax
0x180027842  or      eax, 80070000h
0x180027847  mov     [rsp+380h+var_330], eax
0x18002784b  test    eax, eax
0x18002784d  jns     short loc_180027878
0x18002784f  lea     rcx, aHrHresultFromW_1; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x180027856  mov     r8d, 270h; unsigned int
0x18002785c  mov     r9d, eax; int
0x18002785f  mov     [rsp+380h+var_360], rcx; char *
0x180027864  mov     rdx, r13; char *
0x180027867  lea     rcx, aOnecoreuapDsEx_7; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18002786e  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180027873  jmp     loc_1800279FA
0x180027878  lea     r8, [rsp+380h+var_318]; unsigned __int64 *
0x18002787d  mov     edx, 7FFFFFFEh; unsigned __int64
0x180027882  mov     rcx, r14; unsigned __int16 *
0x180027885  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18002788a  mov     [rsp+380h+var_330], eax
0x18002788e  test    eax, eax
0x180027890  jns     short loc_1800278A1
0x180027892  lea     rcx, aHrStringcchlen_2; "hr = StringCchLengthW(pUserName, STRSAF"...
0x180027899  mov     r8d, 272h
0x18002789f  jmp     short loc_18002785C
0x1800278a1  mov     ecx, dword ptr [rsp+380h+var_318]
0x1800278a5  add     ecx, [rsp+380h+var_32C]
0x1800278a9  lea     ebx, ds:4[rcx*2]
0x1800278b0  lea     rcx, [rbp+280h+var_2F8]
0x1800278b4  call    ?Clear@?$Auto@PEAEV?$LocalAllocFunctor@PEAE@@VDummyContext@@@@QEAAXXZ; Auto<uchar *,LocalAllocFunctor<uchar *>,DummyContext>::Clear(void)
0x1800278b9  mov     esi, ebx
0x1800278bb  mov     edx, ebx; uBytes
0x1800278bd  mov     ecx, 40h ; '@'; uFlags
0x1800278c2  call    cs:__imp_LocalAlloc
0x1800278c8  mov     rbx, rax
0x1800278cb  mov     [rbp+280h+var_2F8], rax
0x1800278cf  test    rax, rax
0x1800278d2  jnz     short loc_180027900
0x1800278d4  call    cs:__imp_GetLastError
0x1800278da  test    eax, eax
0x1800278dc  jle     short loc_1800278E8
0x1800278de  movzx   eax, ax
0x1800278e1  or      eax, 80070000h
0x1800278e6  test    eax, eax
0x1800278e8  jns     short loc_180027902
0x1800278ea  mov     [rsp+380h+var_330], eax
0x1800278ee  lea     rcx, aHrSpqualifiedu; "hr = spQualifiedUser.Allocate(qualified"...
0x1800278f5  mov     r8d, 277h
0x1800278fb  jmp     loc_18002785C
0x180027900  xor     eax, eax
0x180027902  mov     [rbp+280h+var_2F0], rsi
0x180027906  mov     [rsp+380h+var_330], eax
0x18002790a  mov     [rsp+380h+var_360], r14
0x18002790f  lea     r9, [rbp+280h+var_2C0]
0x180027913  lea     r8, aLsLs; "%ls\\%ls"
0x18002791a  mov     edx, 104h; unsigned __int64
0x18002791f  mov     rcx, rbx; unsigned __int16 *
0x180027922  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180027927  mov     [rsp+380h+var_330], eax
0x18002792b  test    eax, eax
0x18002792d  jns     short loc_180027941
0x18002792f  lea     rcx, aHrStringcchpri_1; "hr = StringCchPrintf( spQualifiedUser, "...
0x180027936  mov     r8d, 27Fh
0x18002793c  jmp     loc_18002785C
0x180027941  mov     rax, [rdi]
0x180027944  lea     rcx, [rsp+380h+var_328]
0x180027949  mov     [rsp+380h+var_348], rcx
0x18002794e  lea     rcx, [rsp+380h+var_324]
0x180027953  mov     [rsp+380h+var_350], rcx
0x180027958  lea     rcx, [rbp+280h+var_250]
0x18002795c  mov     [rsp+380h+var_358], rcx
0x180027961  lea     rcx, [rsp+380h+var_320]
0x180027966  mov     [rsp+380h+var_360], rcx
0x18002796b  lea     r9, [rbp+280h+var_2A0]
0x18002796f  mov     r8, rbx
0x180027972  xor     edx, edx
0x180027974  mov     rcx, rdi
0x180027977  mov     rax, [rax+0B8h]
0x18002797e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027983  mov     r9, [rdi]
0x180027986  mov     rcx, rdi
0x180027989  test    eax, eax
0x18002798b  jnz     short loc_1800279B6
0x18002798d  mov     rax, [r9+78h]
0x180027991  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027996  cmp     eax, 534h
0x18002799b  jnz     short loc_1800279A4
0x18002799d  mov     eax, 525h
0x1800279a2  jmp     short loc_1800279A8
0x1800279a4  test    eax, eax
0x1800279a6  jle     short loc_1800279B0
0x1800279a8  movzx   eax, ax
0x1800279ab  or      eax, 80070000h
0x1800279b0  mov     [rsp+380h+var_330], eax
0x1800279b4  jmp     short loc_1800279FA
0x1800279b6  lea     r8, [rsp+380h+var_310]
0x1800279bb  lea     rdx, [rbp+280h+var_2A0]
0x1800279bf  mov     rax, [r9+0C0h]
0x1800279c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800279cb  test    eax, eax
0x1800279cd  jnz     short loc_1800279E0
0x1800279cf  mov     rax, [rdi]
0x1800279d2  mov     rcx, rdi
0x1800279d5  mov     rax, [rax+78h]
0x1800279d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800279de  jmp     short loc_1800279A4
0x1800279e0  mov     rax, [rsp+380h+var_310]
0x1800279e5  mov     [rsp+380h+var_310], 0
0x1800279ee  mov     [rsp+380h+var_308], 0
0x1800279f7  mov     [r15], rax
0x1800279fa  mov     ebx, [rsp+380h+var_330]
0x1800279fe  mov     r9, [rbp+280h+var_2E0]; int *
0x180027a02  mov     r8, [rbp+280h+var_2D8]; unsigned __int64
0x180027a06  mov     rdx, [rbp+280h+var_2D0]
0x180027a0a  mov     edx, [rdx]; int
0x180027a0c  mov     rcx, [rbp+280h+var_2C8]; char *
0x180027a10  call    ?CheckAgainstList@ErrorVerifier@@SAXPEBDJ_KPEBJ@Z; ErrorVerifier::CheckAgainstList(char const *,long,unsigned __int64,long const *)
0x180027a15  nop
0x180027a16  lea     rcx, [rbp+280h+var_2F8]
0x180027a1a  call    ??1?$Auto@PEAPEAXV?$LocalAllocFunctor@PEAPEAX@@VDummyContext@@@@QEAA@XZ; Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>(void)
0x180027a1f  nop
0x180027a20  lea     rcx, [rsp+380h+var_310]
0x180027a25  call    ??1?$Auto@PEAPEAXV?$LocalAllocFunctor@PEAPEAX@@VDummyContext@@@@QEAA@XZ; Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>(void)
0x180027a2a  mov     eax, ebx
0x180027a2c  mov     rcx, [rbp+280h+var_40]
0x180027a33  xor     rcx, rsp; StackCookie
0x180027a36  call    __security_check_cookie
0x180027a3b  add     rsp, 350h
0x180027a42  pop     r15
0x180027a44  pop     r14
0x180027a46  pop     r13
0x180027a48  pop     rdi
0x180027a49  pop     rsi
0x180027a4a  pop     rbx
0x180027a4b  pop     rbp
0x180027a4c  retn
```
