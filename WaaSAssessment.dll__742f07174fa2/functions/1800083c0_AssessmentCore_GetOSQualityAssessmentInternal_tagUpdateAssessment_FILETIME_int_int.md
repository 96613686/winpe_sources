# AssessmentCore::GetOSQualityAssessmentInternal(tagUpdateAssessment *,_FILETIME *,int,int)

- ea: `0x1800083c0`
- end: `0x1800086ce`
- name: `?GetOSQualityAssessmentInternal@AssessmentCore@@MEAAJPEAUtagUpdateAssessment@@PEAU_FILETIME@@HH@Z`
- size: `782`
- prototype: `__int64 __fastcall(AssessmentCore *__hidden this, struct tagUpdateAssessment *, struct _FILETIME *, int, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800083c0`
- `0x18001752c`
- `0x180018948`
- `0x180019760`
- `0x18001b010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800086a6`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800086a6`
- `ntdll!RtlPublishWnfStateData` at `0x180008630`
- `ntdll!RtlPublishWnfStateData` at `0x180008630`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800085b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000865a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008668`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000867e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800085b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000865a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008668`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000867e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800085be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800085be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085ab`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180008615`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180008615`

## string_xrefs

- `0x180008580`: `Software\Microsoft\Windows\CurrentVersion\WaaSAssessment\Cache`
- `0x180008587`: `WaaSAssessmentCache`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AssessmentCore::GetOSQualityAssessmentInternal(
        AssessmentCore *this,
        struct tagUpdateAssessment *a2,
        struct _FILETIME *a3,
        int a4,
        int a5)
{
  _QWORD *v8; // rbx
  int v9; // esi
  int StateSeparationRegistryLocation; // ecx
  _QWORD *v11; // r12
  WCHAR *v12; // r13
  DWORD LastError; // edi
  int v14; // eax
  __int64 i; // rdi
  __int64 v16; // rcx
  int v18; // [rsp+40h] [rbp-71h] BYREF
  int v19; // [rsp+44h] [rbp-6Dh]
  LPCWSTR *Data; // [rsp+50h] [rbp-61h] BYREF
  unsigned __int16 *v21; // [rsp+58h] [rbp-59h] BYREF
  char v22; // [rsp+60h] [rbp-51h]
  _QWORD *v23; // [rsp+70h] [rbp-41h] BYREF
  LPCWSTR lpSubKey; // [rsp+78h] [rbp-39h] BYREF
  DWORD v25; // [rsp+80h] [rbp-31h]
  LPVOID pv[2]; // [rsp+88h] [rbp-29h] BYREF
  __int128 v27; // [rsp+98h] [rbp-19h]
  __int128 v28; // [rsp+A8h] [rbp-9h]

  *(_OWORD *)pv = 0;
  v27 = 0;
  v28 = 0;
  v23 = 0;
  v8 = 0;
  v18 = 0;
  *((_QWORD *)this + 290) = 0;
  if ( !a2 )
  {
    LogLevel(2u, L"Quality Assessment Result is null");
    v9 = -2147467261;
    goto LABEL_28;
  }
  *(_QWORD *)&a2->status = 0;
  a2->daysOutOfDate = 0;
  v9 = (*(__int64 (__fastcall **)(AssessmentCore *, _QWORD **, LPVOID *, __int64, int, int))(*(_QWORD *)this + 152LL))(
         this,
         &v23,
         pv,
         6,
         a4,
         a5);
  if ( v23 )
    v8 = v23;
  if ( v9 >= 0 && v9 != 1 )
  {
    if ( (*((_BYTE *)this + 96) & 1) != 0 )
    {
      LogLevel(4u, L"Determining End of Support");
      v9 = (*(__int64 (__fastcall **)(AssessmentCore *, int *))(*(_QWORD *)this + 168LL))(this, &v18);
      if ( v9 < 0 )
        goto LABEL_28;
      if ( !v18 )
        goto LABEL_12;
      LogLevel(4u, L"OS is in End of Support state");
      a2->status = UpdateAssessmentStatus_NotLatestEndOfSupport;
      a2->impact = UpdateImpactLevel_High;
      a2->daysOutOfDate = -1;
    }
    if ( v18 )
    {
LABEL_17:
      if ( v9 >= 0 )
      {
        lpSubKey = 0;
        Data = &lpSubKey;
        v21 = 0;
        v22 = 1;
        StateSeparationRegistryLocation = GetStateSeparationRegistryLocation(
                                            L"WaaSAssessmentCache",
                                            L"Software\\Microsoft\\Windows\\CurrentVersion\\WaaSAssessment\\Cache",
                                            &v21);
        v19 = StateSeparationRegistryLocation;
        if ( v22 )
        {
          v11 = Data;
          v12 = (WCHAR *)*Data;
          if ( *Data )
          {
            LastError = GetLastError();
            CoTaskMemFree(v12);
            SetLastError(LastError);
            StateSeparationRegistryLocation = v19;
          }
          *v11 = v21;
        }
        if ( StateSeparationRegistryLocation >= 0 )
        {
          Data = *(LPCWSTR **)&a2->status;
          LODWORD(v21) = a2->daysOutOfDate;
          RegSetKeyValueW(HKEY_LOCAL_MACHINE, lpSubKey, L"QualityAssessment", 3u, &Data, 0xCu);
        }
        v14 = RtlPublishWnfStateData(WNF_WAAS_QUALITY_IMPACT, 0, &a2->impact, 4, 0) | 0x10000000;
        if ( v14 < 0 )
          LogLevel(2u, L"Failed to publish WNF QUALITY IMPACT 0x%x", (unsigned int)v14);
        if ( lpSubKey )
          CoTaskMemFree((LPVOID)lpSubKey);
      }
      goto LABEL_28;
    }
LABEL_12:
    lpSubKey = 0;
    v25 = 0;
    LogLevel(4u, L"Determining quality assessment");
    v9 = (*(__int64 (__fastcall **)(AssessmentCore *, LPCWSTR *, _QWORD))(*(_QWORD *)this + 200LL))(
           this,
           &lpSubKey,
           v27);
    *(_QWORD *)&a2->status = lpSubKey;
    a2->daysOutOfDate = v25;
    if ( a3 )
    {
      *a3 = 0;
      *a3 = *(struct _FILETIME *)((char *)this + 148);
    }
    if ( (*((_BYTE *)this + 96) & 2) == 0 && a2->status )
    {
      v9 = -2147024894;
      goto LABEL_28;
    }
    goto LABEL_17;
  }
LABEL_28:
  for ( i = 0; i != 6; ++i )
    CoTaskMemFree(pv[i]);
  CoTaskMemFree(*((LPVOID *)this + 290));
  if ( v8 )
  {
    v16 = v8[1];
    if ( v16 )
    {
      v8[1] = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    operator delete(v8);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800083c0  push    rbp
0x1800083c2  push    rbx
0x1800083c3  push    rsi
0x1800083c4  push    rdi
0x1800083c5  push    r12
0x1800083c7  push    r13
0x1800083c9  push    r14
0x1800083cb  push    r15
0x1800083cd  lea     rbp, [rsp-17h]
0x1800083d2  sub     rsp, 0C8h
0x1800083d9  mov     rax, cs:__security_cookie
0x1800083e0  xor     rax, rsp
0x1800083e3  mov     [rbp+4Fh+var_48], rax
0x1800083e7  mov     rdi, r8
0x1800083ea  mov     r14, rdx
0x1800083ed  mov     r15, rcx
0x1800083f0  xorps   xmm0, xmm0
0x1800083f3  movups  xmmword ptr [rbp+4Fh+pv], xmm0
0x1800083f7  movups  [rbp+4Fh+var_68], xmm0
0x1800083fb  movups  [rbp+4Fh+var_58], xmm0
0x1800083ff  xor     r12d, r12d
0x180008402  mov     [rbp+4Fh+var_90], r12
0x180008406  mov     ebx, r12d
0x180008409  mov     [rbp+4Fh+var_C0], r12d
0x18000840d  mov     [rcx+910h], r12
0x180008414  test    rdx, rdx
0x180008417  jnz     short loc_180008433
0x180008419  lea     rdx, aQualityAssessm; "Quality Assessment Result is null"
0x180008420  lea     ecx, [r14+2]; unsigned __int8
0x180008424  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180008429  mov     esi, 80004003h
0x18000842e  jmp     loc_180008660
0x180008433  xor     eax, eax
0x180008435  mov     [rdx], rax
0x180008438  mov     [rdx+8], eax
0x18000843b  mov     rax, [rcx]
0x18000843e  mov     r10, [rax+98h]
0x180008445  mov     eax, [rbp+4Fh+arg_20]
0x180008448  mov     [rsp+100h+cbData], eax
0x18000844c  mov     dword ptr [rsp+100h+lpData], r9d
0x180008451  mov     r9d, 6
0x180008457  lea     r8, [rbp+4Fh+pv]
0x18000845b  lea     rdx, [rbp+4Fh+var_90]
0x18000845f  mov     rax, r10
0x180008462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008467  mov     esi, eax
0x180008469  mov     rax, [rbp+4Fh+var_90]
0x18000846d  test    rax, rax
0x180008470  jz      short loc_180008476
0x180008472  cmovnz  rbx, rax
0x180008476  test    esi, esi
0x180008478  js      loc_180008660
0x18000847e  cmp     esi, 1
0x180008481  jz      loc_180008660
0x180008487  mov     r13d, 4
0x18000848d  test    byte ptr [r15+60h], 1
0x180008492  jbe     short loc_1800084EB
0x180008494  lea     rdx, aDeterminingEnd; "Determining End of Support"
0x18000849b  mov     ecx, r13d; unsigned __int8
0x18000849e  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x1800084a3  mov     rax, [r15]
0x1800084a6  lea     rdx, [rbp+4Fh+var_C0]
0x1800084aa  mov     rcx, r15
0x1800084ad  mov     rax, [rax+0A8h]
0x1800084b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084b9  mov     esi, eax
0x1800084bb  test    eax, eax
0x1800084bd  js      loc_180008660
0x1800084c3  cmp     [rbp+4Fh+var_C0], r12d
0x1800084c7  jz      short loc_1800084F1
0x1800084c9  lea     rdx, aOsIsInEndOfSup; "OS is in End of Support state"
0x1800084d0  mov     ecx, r13d; unsigned __int8
0x1800084d3  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x1800084d8  lea     eax, [r13-1]
0x1800084dc  mov     [r14], eax
0x1800084df  mov     [r14+4], eax
0x1800084e3  mov     dword ptr [r14+8], 0FFFFFFFFh
0x1800084eb  cmp     [rbp+4Fh+var_C0], r12d
0x1800084ef  jnz     short loc_180008560
0x1800084f1  xor     eax, eax
0x1800084f3  mov     [rbp+4Fh+lpSubKey], rax
0x1800084f7  mov     [rbp+4Fh+var_80], eax
0x1800084fa  lea     rdx, aDeterminingQua; "Determining quality assessment"
0x180008501  mov     ecx, r13d; unsigned __int8
0x180008504  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180008509  mov     rax, [r15]
0x18000850c  mov     r8, qword ptr [rbp+4Fh+var_68]
0x180008510  lea     rdx, [rbp+4Fh+lpSubKey]
0x180008514  mov     rcx, r15
0x180008517  mov     rax, [rax+0C8h]
0x18000851e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008523  mov     esi, eax
0x180008525  movsd   xmm0, [rbp+4Fh+lpSubKey]
0x18000852a  movsd   qword ptr [r14], xmm0
0x18000852f  mov     eax, [rbp+4Fh+var_80]
0x180008532  mov     [r14+8], eax
0x180008536  test    rdi, rdi
0x180008539  jz      short loc_18000854A
0x18000853b  xor     eax, eax
0x18000853d  mov     [rdi], rax
0x180008540  mov     rax, [r15+94h]
0x180008547  mov     [rdi], rax
0x18000854a  test    byte ptr [r15+60h], 2
0x18000854f  ja      short loc_180008560
0x180008551  cmp     [r14], r12d
0x180008554  jz      short loc_180008560
0x180008556  mov     esi, 80070002h
0x18000855b  jmp     loc_180008660
0x180008560  test    esi, esi
0x180008562  js      loc_180008660
0x180008568  mov     [rbp+4Fh+lpSubKey], r12
0x18000856c  lea     rax, [rbp+4Fh+lpSubKey]
0x180008570  mov     [rbp+4Fh+Data], rax
0x180008574  mov     [rbp+4Fh+var_A8], r12
0x180008578  mov     [rbp+4Fh+var_A0], 1
0x18000857c  lea     r8, [rbp+4Fh+var_A8]; unsigned __int16 **
0x180008580  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180008587  lea     rcx, aWaasassessment_0; "WaaSAssessmentCache"
0x18000858e  call    ?GetStateSeparationRegistryLocation@@YAJPEBG0PEAPEAG@Z; GetStateSeparationRegistryLocation(ushort const *,ushort const *,ushort * *)
0x180008593  mov     ecx, eax
0x180008595  mov     [rbp+4Fh+var_BC], eax
0x180008598  cmp     [rbp+4Fh+var_A0], r12b
0x18000859c  jz      short loc_1800085D7
0x18000859e  mov     r12, [rbp+4Fh+Data]
0x1800085a2  mov     r13, [r12]
0x1800085a6  test    r13, r13
0x1800085a9  jz      short loc_1800085C7
0x1800085ab  call    cs:__imp_GetLastError
0x1800085b1  mov     edi, eax
0x1800085b3  mov     rcx, r13; pv
0x1800085b6  call    cs:__imp_CoTaskMemFree
0x1800085bc  mov     ecx, edi; dwErrCode
0x1800085be  call    cs:__imp_SetLastError
0x1800085c4  mov     ecx, [rbp+4Fh+var_BC]
0x1800085c7  mov     rax, [rbp+4Fh+var_A8]
0x1800085cb  mov     [r12], rax
0x1800085cf  xor     r12d, r12d
0x1800085d2  lea     r13d, [r12+4]
0x1800085d7  test    ecx, ecx
0x1800085d9  js      short loc_18000861B
0x1800085db  movsd   xmm0, qword ptr [r14]
0x1800085e0  movsd   [rbp+4Fh+Data], xmm0
0x1800085e5  mov     eax, [r14+8]
0x1800085e9  mov     dword ptr [rbp+4Fh+var_A8], eax
0x1800085ec  mov     [rsp+100h+cbData], 0Ch; cbData
0x1800085f4  lea     rax, [rbp+4Fh+Data]
0x1800085f8  mov     [rsp+100h+lpData], rax; lpData
0x1800085fd  mov     r9d, 3; dwType
0x180008603  lea     r8, aQualityassessm; "QualityAssessment"
0x18000860a  mov     rdx, [rbp+4Fh+lpSubKey]; lpSubKey
0x18000860e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180008615  call    cs:__imp_RegSetKeyValueW
0x18000861b  lea     r8, [r14+4]
0x18000861f  mov     [rsp+100h+lpData], r12
0x180008624  mov     r9d, r13d
0x180008627  xor     edx, edx
0x180008629  mov     rcx, cs:WNF_WAAS_QUALITY_IMPACT
0x180008630  call    cs:__imp_RtlPublishWnfStateData
0x180008636  or      eax, 10000000h
0x18000863b  jge     short loc_180008651
0x18000863d  mov     r8d, eax
0x180008640  lea     rdx, aFailedToPublis_0; "Failed to publish WNF QUALITY IMPACT 0x"...
0x180008647  mov     ecx, 2; unsigned __int8
0x18000864c  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180008651  mov     rcx, [rbp+4Fh+lpSubKey]; pv
0x180008655  test    rcx, rcx
0x180008658  jz      short loc_180008660
0x18000865a  call    cs:__imp_CoTaskMemFree
0x180008660  mov     rdi, r12
0x180008663  mov     rcx, [rbp+rdi*8+4Fh+pv]; pv
0x180008668  call    cs:__imp_CoTaskMemFree
0x18000866e  inc     rdi
0x180008671  cmp     rdi, 6
0x180008675  jnz     short loc_180008663
0x180008677  mov     rcx, [r15+910h]; pv
0x18000867e  call    cs:__imp_CoTaskMemFree
0x180008684  test    rbx, rbx
0x180008687  jz      short loc_1800086AC
0x180008689  mov     rcx, [rbx+8]
0x18000868d  test    rcx, rcx
0x180008690  jz      short loc_1800086A3
0x180008692  mov     [rbx+8], r12
0x180008696  mov     rax, [rcx]
0x180008699  mov     rax, [rax+10h]
0x18000869d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086a2  nop
0x1800086a3  mov     rcx, rbx
0x1800086a6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800086ac  mov     eax, esi
0x1800086ae  mov     rcx, [rbp+4Fh+var_48]
0x1800086b2  xor     rcx, rsp; StackCookie
0x1800086b5  call    __security_check_cookie
0x1800086ba  add     rsp, 0C8h
0x1800086c1  pop     r15
0x1800086c3  pop     r14
0x1800086c5  pop     r13
0x1800086c7  pop     r12
0x1800086c9  pop     rdi
0x1800086ca  pop     rsi
0x1800086cb  pop     rbx
0x1800086cc  pop     rbp
0x1800086cd  retn
```
