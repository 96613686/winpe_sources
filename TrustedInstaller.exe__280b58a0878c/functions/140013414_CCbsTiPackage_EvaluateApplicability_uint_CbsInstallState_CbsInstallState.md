# CCbsTiPackage::EvaluateApplicability(uint,_CbsInstallState *,_CbsInstallState *)

- ea: `0x140013414`
- end: `0x1400136c5`
- name: `?EvaluateApplicability@CCbsTiPackage@@UEAAJIPEAW4_CbsInstallState@@0@Z`
- size: `689`
- prototype: `__int64 __fastcall(CCbsTiPackage *this, __int64, enum _CbsInstallState *, enum _CbsInstallState *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x140013400`

## callees

- `0x1400023e0`
- `0x140002674`
- `0x14000f020`
- `0x140013414`
- `0x140017658`
- `0x140017c30`
- `0x14001a16c`
- `0x14001c9a0`
- `0x1400214fc`
- `0x140023280`
- `0x14002b010`

## string_xrefs

- `0x14001352b`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Component Based Servicing\ApplicabilityEvaluationCache\`
- `0x140013593`: `Read out cached applicability from TiLight for package: %S, ApplicableState: %d, CurrentState:%d`
- `0x14001362b`: `Failed to create internal CBS Package`

## pseudocode

```c
__int64 __fastcall CCbsTiPackage::EvaluateApplicability(
        CCbsTiPackage *this,
        __int64 a2,
        enum _CbsInstallState *a3,
        enum _CbsInstallState *a4)
{
  __int64 v5; // rcx
  wchar_t *v8; // r14
  const wchar_t *v9; // r15
  unsigned int v10; // esi
  const char *v11; // r9
  size_t v12; // rdx
  int InternalCbsPackage; // eax
  int QuickIdentity; // eax
  int v15; // eax
  HKEY v16; // rcx
  HKEY v17; // rcx
  unsigned int v18; // edi
  unsigned int v19; // ebx
  __int64 v20; // r8
  CCbsTiSession *v21; // rcx
  int v23; // [rsp+20h] [rbp-49h]
  __int64 v24; // [rsp+30h] [rbp-39h]
  unsigned int v25; // [rsp+60h] [rbp-9h] BYREF
  unsigned int v26; // [rsp+64h] [rbp-5h] BYREF
  wchar_t *v27; // [rsp+68h] [rbp-1h] BYREF
  wchar_t *v28[2]; // [rsp+70h] [rbp+7h] BYREF
  __int64 v29; // [rsp+80h] [rbp+17h] BYREF

  v5 = *((_QWORD *)this - 2);
  v27 = 0;
  v28[0] = 0;
  v8 = 0;
  v29 = 0;
  v9 = 0;
  if ( !v5 && !*((_QWORD *)this - 7) )
  {
    v10 = -2147418113;
    CBSWdsLogLight(
      0x4000000u,
      0x8000FFFF,
      (size_t *)1,
      "The package is neither a regular package nor a normal package.");
    goto LABEL_26;
  }
  if ( a3 )
  {
    if ( !a4 )
    {
      v11 = "No current state result specified";
      goto LABEL_6;
    }
    if ( v5 )
    {
      InternalCbsPackage = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v5 + 80LL))(v5, 0);
      v10 = InternalCbsPackage;
      if ( InternalCbsPackage >= 0 )
        goto LABEL_26;
    }
    else
    {
      if ( (unsigned int)GetCbsOperationInitiator(*((_QWORD *)this - 6)) > 3 )
      {
        QuickIdentity = GetQuickIdentity(*((const wchar_t **)this - 7), &v27);
        if ( QuickIdentity >= 0 )
        {
          v8 = v27;
          if ( !QuickIdentity )
          {
            v26 = 4096;
            v25 = 4096;
            v15 = SczAllocConcat2Sz(
                    v28,
                    L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Component Based Servicing\\ApplicabilityEvaluationCache\\",
                    v27);
            v9 = v28[0];
            if ( !v15 && !(unsigned int)CbsRegQueryDWORDValue(v16, v28[0], 1, L"ApplicabilityState", &v26) )
            {
              v10 = CbsRegQueryDWORDValue(v17, v9, 1, L"CurrentState", &v25);
              if ( !v10 )
              {
                v18 = v25;
                v19 = v26;
                CBSWdsLogLight(
                  0x4000000u,
                  0,
                  0,
                  "Read out cached applicability from TiLight for package: %S, ApplicableState: %d, CurrentState:%d",
                  v8,
                  v26,
                  v25);
                *(_DWORD *)a3 = ConvertInternalStateToPublicState(v19);
                *(_DWORD *)a4 = ConvertInternalStateToPublicState(v18);
                goto LABEL_26;
              }
            }
          }
        }
        else
        {
          CBSWdsLogLight(0x4000000u, (unsigned int)QuickIdentity, (size_t *)1, "Unable to process package string");
          v8 = v27;
        }
      }
      v20 = *((_QWORD *)this - 6);
      v21 = (CCbsTiSession *)*((_QWORD *)this - 8);
      v24 = *((_QWORD *)this - 7);
      v23 = *((_DWORD *)this - 6);
      *(_OWORD *)v28 = *(_OWORD *)((char *)this - 40);
      InternalCbsPackage = CCbsTiSession::CreateInternalCbsPackage(
                             v21,
                             0,
                             v20,
                             (__int128 *)v28,
                             v23,
                             3,
                             v24,
                             0,
                             0,
                             0,
                             0,
                             (__int64)&v29);
      v10 = InternalCbsPackage;
      if ( InternalCbsPackage < 0 )
      {
        v11 = "Failed to create internal CBS Package";
LABEL_24:
        v12 = (unsigned int)InternalCbsPackage;
        goto LABEL_25;
      }
      InternalCbsPackage = (*(__int64 (__fastcall **)(__int64, _QWORD, enum _CbsInstallState *, enum _CbsInstallState *))(*(_QWORD *)v29 + 80LL))(
                             v29,
                             0,
                             a3,
                             a4);
      v10 = InternalCbsPackage;
      if ( InternalCbsPackage >= 0 )
        goto LABEL_26;
    }
    v11 = "Failed to call EvaluateApplicability on internal CBS package.";
    goto LABEL_24;
  }
  v11 = "No applicable state result specified";
LABEL_6:
  v12 = 2147500035LL;
  v10 = -2147467261;
LABEL_25:
  CBSWdsLogLight(0x4000000u, v12, (size_t *)1, v11);
LABEL_26:
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  if ( v8 )
    operator delete(v8 - 4);
  if ( v9 )
    operator delete((void *)(v9 - 4));
  return v10;
}

```

## disassembly

```asm
0x140013414  mov     [rsp-8+arg_8], rbx
0x140013419  push    rbp
0x14001341a  push    rsi
0x14001341b  push    rdi
0x14001341c  push    r12
0x14001341e  push    r13
0x140013420  push    r14
0x140013422  push    r15
0x140013424  lea     rbp, [rsp-27h]
0x140013429  sub     rsp, 90h
0x140013430  mov     rax, cs:__security_cookie
0x140013437  xor     rax, rsp
0x14001343a  mov     [rbp+57h+var_38], rax
0x14001343e  xor     esi, esi
0x140013440  mov     rdi, rcx
0x140013443  mov     rcx, [rcx-10h]
0x140013447  mov     r13, r9
0x14001344a  mov     [rbp+57h+var_58], rsi
0x14001344e  mov     r12, r8
0x140013451  mov     [rbp+57h+var_50], rsi
0x140013455  mov     r14d, esi
0x140013458  mov     [rbp+57h+var_40], rsi
0x14001345c  mov     r15d, esi
0x14001345f  test    rcx, rcx
0x140013462  jnz     short loc_140013481
0x140013464  cmp     [rdi-38h], rsi
0x140013468  jnz     short loc_140013481
0x14001346a  mov     esi, 8000FFFFh
0x14001346f  lea     r9, aThePackageIsNe; "The package is neither a regular packag"...
0x140013476  mov     edx, esi
0x140013478  lea     r8d, [r15+1]
0x14001347c  jmp     loc_140013661
0x140013481  test    r12, r12
0x140013484  jnz     short loc_14001349F
0x140013486  lea     r9, aNoApplicableSt; "No applicable state result specified"
0x14001348d  mov     edx, 80004003h
0x140013492  mov     r8d, 1
0x140013498  mov     esi, edx
0x14001349a  jmp     loc_140013661
0x14001349f  test    r13, r13
0x1400134a2  jnz     short loc_1400134AD
0x1400134a4  lea     r9, aNoCurrentState; "No current state result specified"
0x1400134ab  jmp     short loc_14001348D
0x1400134ad  test    rcx, rcx
0x1400134b0  jz      short loc_1400134D5
0x1400134b2  mov     rax, [rcx]
0x1400134b5  xor     edx, edx
0x1400134b7  mov     rax, [rax+50h]
0x1400134bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400134c0  mov     esi, eax
0x1400134c2  test    eax, eax
0x1400134c4  jns     loc_14001366B
0x1400134ca  mov     r8d, 1
0x1400134d0  jmp     loc_140013658
0x1400134d5  mov     rcx, [rdi-30h]
0x1400134d9  call    ?GetCbsOperationInitiator@@YA?AW4CbsOperationInitiator@@PEB_W@Z; GetCbsOperationInitiator(wchar_t const *)
0x1400134de  mov     ebx, 1
0x1400134e3  cmp     eax, 3
0x1400134e6  jbe     loc_1400135D6
0x1400134ec  mov     rcx, [rdi-38h]; Str
0x1400134f0  lea     rdx, [rbp+57h+var_58]; wchar_t **
0x1400134f4  call    ?GetQuickIdentity@@YAJPEB_WPEAPEA_W@Z; GetQuickIdentity(wchar_t const *,wchar_t * *)
0x1400134f9  test    eax, eax
0x1400134fb  jns     short loc_14001351C
0x1400134fd  lea     r9, aUnableToProces; "Unable to process package string"
0x140013504  mov     r8d, ebx
0x140013507  mov     edx, eax
0x140013509  mov     ecx, 4000000h
0x14001350e  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140013513  mov     r14, [rbp+57h+var_58]
0x140013517  jmp     loc_1400135D6
0x14001351c  mov     r14, [rbp+57h+var_58]
0x140013520  jnz     loc_1400135D6
0x140013526  mov     eax, 1000h
0x14001352b  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x140013532  mov     r8, r14
0x140013535  mov     [rbp+57h+var_5C], eax
0x140013538  lea     rcx, [rbp+57h+var_50]
0x14001353c  mov     [rbp+57h+var_60], eax
0x14001353f  call    SczAllocConcat2Sz
0x140013544  mov     r15, [rbp+57h+var_50]
0x140013548  test    eax, eax
0x14001354a  jnz     loc_1400135D6
0x140013550  lea     rax, [rbp+57h+var_5C]
0x140013554  mov     r8d, ebx; unsigned int
0x140013557  lea     r9, aApplicabilitys; "ApplicabilityState"
0x14001355e  mov     [rsp+0C0h+var_A0], rax; unsigned int *
0x140013563  mov     rdx, r15; wchar_t *
0x140013566  call    ?CbsRegQueryDWORDValue@@YAJPEAUHKEY__@@PEB_WK1PEAK@Z; CbsRegQueryDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong *)
0x14001356b  test    eax, eax
0x14001356d  jnz     short loc_1400135D6
0x14001356f  lea     rax, [rbp+57h+var_60]
0x140013573  mov     r8d, ebx; unsigned int
0x140013576  lea     r9, aCurrentstate; "CurrentState"
0x14001357d  mov     [rsp+0C0h+var_A0], rax; unsigned int *
0x140013582  mov     rdx, r15; wchar_t *
0x140013585  call    ?CbsRegQueryDWORDValue@@YAJPEAUHKEY__@@PEB_WK1PEAK@Z; CbsRegQueryDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong *)
0x14001358a  mov     esi, eax
0x14001358c  test    eax, eax
0x14001358e  jnz     short loc_1400135D4
0x140013590  mov     edi, [rbp+57h+var_60]
0x140013593  lea     r9, aReadOutCachedA; "Read out cached applicability from TiLi"...
0x14001359a  mov     ebx, [rbp+57h+var_5C]
0x14001359d  xor     r8d, r8d
0x1400135a0  mov     dword ptr [rsp+0C0h+var_90], edi
0x1400135a4  xor     edx, edx
0x1400135a6  mov     [rsp+0C0h+var_98], ebx
0x1400135aa  mov     ecx, 4000000h
0x1400135af  mov     [rsp+0C0h+var_A0], r14
0x1400135b4  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400135b9  mov     ecx, ebx
0x1400135bb  call    ?ConvertInternalStateToPublicState@@YA?AW4_CbsInstallState@@W4CbsState@@@Z; ConvertInternalStateToPublicState(CbsState)
0x1400135c0  mov     ecx, edi
0x1400135c2  mov     [r12], eax
0x1400135c6  call    ?ConvertInternalStateToPublicState@@YA?AW4_CbsInstallState@@W4CbsState@@@Z; ConvertInternalStateToPublicState(CbsState)
0x1400135cb  mov     [r13+0], eax
0x1400135cf  jmp     loc_14001366B
0x1400135d4  xor     esi, esi
0x1400135d6  movups  xmm0, xmmword ptr [rdi-28h]
0x1400135da  mov     r8, [rdi-30h]
0x1400135de  lea     rax, [rbp+57h+var_40]
0x1400135e2  mov     rcx, [rdi-40h]
0x1400135e6  lea     r9, [rbp+57h+var_50]
0x1400135ea  mov     [rsp+0C0h+var_68], rax
0x1400135ef  xor     edx, edx
0x1400135f1  mov     rax, [rdi-38h]
0x1400135f5  mov     [rsp+0C0h+var_70], esi
0x1400135f9  mov     [rsp+0C0h+var_78], rsi
0x1400135fe  mov     [rsp+0C0h+var_80], esi
0x140013602  mov     [rsp+0C0h+var_88], rsi
0x140013607  mov     [rsp+0C0h+var_90], rax
0x14001360c  mov     eax, [rdi-18h]
0x14001360f  mov     [rsp+0C0h+var_98], 3
0x140013617  mov     dword ptr [rsp+0C0h+var_A0], eax
0x14001361b  movdqu  xmmword ptr [rbp+57h+var_50], xmm0
0x140013620  call    ?CreateInternalCbsPackage@CCbsTiSession@@QEAAJIPEB_WU_GUID@@IW4_CbsPackageType@@00IQEAUtagCbsPackageDecryptionData@@W4tagCBS_PACKAGE_ENCRYPTION_ENUM@@PEAPEAUICbsPackage@@@Z; CCbsTiSession::CreateInternalCbsPackage(uint,wchar_t const *,_GUID,uint,_CbsPackageType,wchar_t const *,wchar_t const *,uint,tagCbsPackageDecryptionData * const,tagCBS_PACKAGE_ENCRYPTION_ENUM,ICbsPackage * *)
0x140013625  mov     esi, eax
0x140013627  test    eax, eax
0x140013629  jns     short loc_140013637
0x14001362b  lea     r9, aFailedToCreate_23; "Failed to create internal CBS Package"
0x140013632  mov     r8d, ebx
0x140013635  jmp     short loc_14001365F
0x140013637  mov     rcx, [rbp+57h+var_40]
0x14001363b  mov     r9, r13
0x14001363e  mov     r8, r12
0x140013641  xor     edx, edx
0x140013643  mov     rax, [rcx]
0x140013646  mov     rax, [rax+50h]
0x14001364a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001364f  mov     esi, eax
0x140013651  test    eax, eax
0x140013653  jns     short loc_14001366B
0x140013655  mov     r8d, ebx
0x140013658  lea     r9, aFailedToCallEv; "Failed to call EvaluateApplicability on"...
0x14001365f  mov     edx, eax
0x140013661  mov     ecx, 4000000h
0x140013666  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14001366b  mov     rcx, [rbp+57h+var_40]
0x14001366f  test    rcx, rcx
0x140013672  jz      short loc_140013680
0x140013674  mov     rax, [rcx]
0x140013677  mov     rax, [rax+10h]
0x14001367b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013680  test    r14, r14
0x140013683  jz      short loc_14001368E
0x140013685  lea     rcx, [r14-8]; void *
0x140013689  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14001368e  test    r15, r15
0x140013691  jz      short loc_14001369C
0x140013693  lea     rcx, [r15-8]; void *
0x140013697  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14001369c  mov     eax, esi
0x14001369e  mov     rcx, [rbp+57h+var_38]
0x1400136a2  xor     rcx, rsp; StackCookie
0x1400136a5  call    __security_check_cookie
0x1400136aa  mov     rbx, [rsp+0C0h+arg_8]
0x1400136b2  add     rsp, 90h
0x1400136b9  pop     r15
0x1400136bb  pop     r14
0x1400136bd  pop     r13
0x1400136bf  pop     r12
0x1400136c1  pop     rdi
0x1400136c2  pop     rsi
0x1400136c3  pop     rbp
0x1400136c4  retn
```
