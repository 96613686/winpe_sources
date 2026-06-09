# Siufp_IsCandidate_Telecommand(int *,ushort *,uint *,ITelecommandCache *,ushort const *,uint)

- ea: `0x1800a82f0`
- end: `0x1800a8639`
- name: `?Siufp_IsCandidate_Telecommand@@YAKPEAHPEAGPEAIPEAVITelecommandCache@@PEBGI@Z`
- size: `841`
- prototype: `__int64 __fastcall(int *, unsigned __int16 *, unsigned int *, struct ITelecommandCache *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800a7a60`

## callees

- `0x180005180`
- `0x18000b6f0`
- `0x18000dcc0`
- `0x18000f6c4`
- `0x180012920`
- `0x18001b320`
- `0x18001e688`
- `0x1800a82f0`
- `0x1800ee46c`
- `0x1800f1f10`
- `0x1800f7010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x1800a8368`
- `msvcrt!wcscpy_s` at `0x1800a85e8`
- `msvcrt!wcscpy_s` at `0x1800a8368`
- `msvcrt!wcscpy_s` at `0x1800a85e8`
- `msvcrt!swscanf_s` at `0x1800a8565`
- `msvcrt!swscanf_s` at `0x1800a8565`
- `msvcrt!_wcsicmp` at `0x1800a84dd`
- `msvcrt!_wcsicmp` at `0x1800a850f`
- `msvcrt!_wcsicmp` at `0x1800a84dd`
- `msvcrt!_wcsicmp` at `0x1800a850f`

## string_xrefs

- `0x1800a8437`: `Telecommand,Skipped,FileName not specified`
- `0x1800a8453`: `No FileName parameter for SIUF Telecommand`
- `0x1800a8399`: `Failed to load telecommand cache [%d]`
- `0x1800a83ab`: `Siufp_IsCandidate_Telecommand`
- `0x1800a840c`: `Siufp_IsCandidate_Telecommand`
- `0x1800a8460`: `Siufp_IsCandidate_Telecommand`
- `0x1800a8581`: `Siufp_IsCandidate_Telecommand`
- `0x1800a85ae`: `Siufp_IsCandidate_Telecommand`
- `0x1800a83ff`: `Failed to read telecommand parameters [%d]`
- `0x1800a84e7`: `Telecommand,Skipped,FileId mismatch`
- `0x1800a8519`: `Telecommand,Skipped,ProgramId mismatch`

## pseudocode

```c
__int64 __fastcall Siufp_IsCandidate_Telecommand(
        int *a1,
        unsigned __int16 *a2,
        unsigned int *a3,
        struct ITelecommandCache *a4,
        unsigned __int16 *a5,
        unsigned int a6)
{
  unsigned __int16 v10; // ax
  unsigned int v11; // ebx
  unsigned int i; // r15d
  int v13; // eax
  const unsigned __int16 *Value; // rax
  unsigned __int16 *v15; // rbx
  unsigned int ProgramInfo; // eax
  const wchar_t *v17; // rax
  const wchar_t *v18; // rax
  const wchar_t *v19; // rax
  const wchar_t *v20; // rbx
  const wchar_t *v21; // rax
  unsigned __int16 *v23; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v24; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v25; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v26; // [rsp+50h] [rbp-B0h]
  wchar_t *Destination; // [rsp+58h] [rbp-A8h]
  int *v28; // [rsp+60h] [rbp-A0h]
  _BYTE v29[56]; // [rsp+68h] [rbp-98h] BYREF
  wchar_t String2[48]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t v31[48]; // [rsp+100h] [rbp+0h] BYREF

  Destination = a2;
  v28 = a1;
  v26 = a5;
  v25 = 0;
  v24 = 0;
  RtlNameValueArray::RtlNameValueArray((RtlNameValueArray *)v29);
  *a1 = 0;
  wcscpy_s(a2, 0x104u, &sourceString);
  *a3 = 0;
  if ( a4 )
  {
    v10 = (*(__int64 (__fastcall **)(struct ITelecommandCache *))(*(_QWORD *)a4 + 8LL))(a4);
    v11 = v10;
    if ( v10 )
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"Siufp_IsCandidate_Telecommand",
        612,
        (unsigned int)"Failed to load telecommand cache [%d]",
        v10);
      goto LABEL_29;
    }
    for ( i = 0;
          (*(unsigned int (__fastcall **)(struct ITelecommandCache *, _QWORD, __int64 *, unsigned __int16 **))(*(_QWORD *)a4 + 16LL))(
            a4,
            i,
            &v25,
            &v24);
          ++i )
    {
      v13 = PcaUtilityNameValueArrayLoadFromString((struct RtlNameValueArray *)v29, v24);
      if ( v13 )
      {
        LODWORD(v23) = v13;
        AslLogCallPrintf(
          1,
          (unsigned int)"Siufp_IsCandidate_Telecommand",
          631,
          (unsigned int)"Failed to read telecommand parameters [%d]",
          v23);
      }
      else
      {
        Value = RtlNameValueArray::GetValue((RtlNameValueArray *)v29, 0, (wchar_t *)L"FileName");
        if ( Value )
        {
          v15 = v26;
          if ( (unsigned int)AslStringPatternMatchExW(Value, v26) )
          {
            ProgramInfo = PcaUtilityGetProgramInfo(v31, String2, 0, 0, 0, 0, 0, v15);
            v11 = ProgramInfo;
            if ( ProgramInfo )
            {
              LODWORD(v23) = ProgramInfo;
              AslLogCallPrintf(
                1,
                (unsigned int)"Siufp_IsCandidate_Telecommand",
                656,
                (unsigned int)"Failed to retrieve program attributes [%d]",
                v23);
              goto LABEL_29;
            }
            v17 = RtlNameValueArray::GetValue((RtlNameValueArray *)v29, 0, (wchar_t *)L"FileId");
            if ( v17 && _wcsicmp(v17, String2) )
            {
              PcaTracePrintf("Siuf", a6, 0, "Telecommand,Skipped,FileId mismatch");
            }
            else
            {
              v18 = RtlNameValueArray::GetValue((RtlNameValueArray *)v29, 0, (wchar_t *)L"ProgramId");
              if ( !v18 || !_wcsicmp(v18, v31) )
              {
                v19 = RtlNameValueArray::GetValue((RtlNameValueArray *)v29, 0, (wchar_t *)L"EventIndex");
                v20 = v19;
                if ( v19 )
                {
                  if ( swscanf_s(v19, L"%u", a3) != 1 )
                  {
                    AslLogCallPrintf(
                      1,
                      (unsigned int)"Siufp_IsCandidate_Telecommand",
                      679,
                      (unsigned int)"Bad event index: %S",
                      v20);
                    *a3 = 0;
                  }
                  if ( *a3 > 0xA )
                  {
                    AslLogCallPrintf(
                      1,
                      (unsigned int)"Siufp_IsCandidate_Telecommand",
                      684,
                      (unsigned int)"Event index too large: %S",
                      v20);
                    *a3 = 0;
                  }
                }
                v21 = RtlNameValueArray::GetValue((RtlNameValueArray *)v29, 0, (wchar_t *)L"StudyId");
                if ( v21 )
                  wcscpy_s(Destination, 0x104u, v21);
                *v28 = 1;
                break;
              }
              PcaTracePrintf("Siuf", a6, 0, "Telecommand,Skipped,ProgramId mismatch");
            }
          }
        }
        else
        {
          PcaTracePrintf("Siuf", a6, 0, "Telecommand,Skipped,FileName not specified");
          AslLogCallPrintf(
            1,
            (unsigned int)"Siufp_IsCandidate_Telecommand",
            642,
            (unsigned int)"No FileName parameter for SIUF Telecommand");
        }
      }
    }
  }
  v11 = 0;
LABEL_29:
  RtlStringArray::~RtlStringArray((RtlStringArray *)v29);
  return v11;
}

```

## disassembly

```asm
0x1800a82f0  push    rbp
0x1800a82f2  push    rbx
0x1800a82f3  push    rdi
0x1800a82f4  push    r13
0x1800a82f6  push    r14
0x1800a82f8  push    r15
0x1800a82fa  lea     rbp, [rsp-78h]
0x1800a82ff  sub     rsp, 178h
0x1800a8306  mov     rax, cs:__security_cookie
0x1800a830d  xor     rax, rsp
0x1800a8310  mov     [rbp+0A0h+var_40], rax
0x1800a8314  mov     r13, r9
0x1800a8317  mov     r14, r8
0x1800a831a  mov     rdi, rdx
0x1800a831d  mov     [rsp+1A0h+Destination], rdx
0x1800a8322  mov     rbx, rcx
0x1800a8325  mov     [rsp+1A0h+var_140], rcx
0x1800a832a  mov     rax, [rbp+0A0h+arg_20]
0x1800a8331  mov     [rsp+1A0h+var_150], rax
0x1800a8336  mov     [rsp+1A0h+var_158], 0
0x1800a833f  mov     [rsp+1A0h+var_160], 0
0x1800a8348  lea     rcx, [rsp+1A0h+var_138]; this
0x1800a834d  call    ??0RtlNameValueArray@@QEAA@XZ; RtlNameValueArray::RtlNameValueArray(void)
0x1800a8352  nop
0x1800a8353  mov     dword ptr [rbx], 0
0x1800a8359  lea     r8, sourceString; Source
0x1800a8360  mov     edx, 104h; SizeInWords
0x1800a8365  mov     rcx, rdi; Destination
0x1800a8368  call    cs:__imp_wcscpy_s
0x1800a836e  mov     dword ptr [r14], 0
0x1800a8375  test    r13, r13
0x1800a8378  jz      loc_1800A85F5
0x1800a837e  mov     rax, [r13+0]
0x1800a8382  mov     rcx, r13
0x1800a8385  mov     rax, [rax+8]
0x1800a8389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a838e  movzx   ebx, ax
0x1800a8391  test    ebx, ebx
0x1800a8393  jz      short loc_1800A83BC
0x1800a8395  mov     dword ptr [rsp+1A0h+var_180], ebx
0x1800a8399  lea     r9, aFailedToLoadTe; "Failed to load telecommand cache [%d]"
0x1800a83a0  mov     r8d, 264h
0x1800a83a6  mov     ecx, 1
0x1800a83ab  lea     rdx, aSiufpIscandida_0; "Siufp_IsCandidate_Telecommand"
0x1800a83b2  call    AslLogCallPrintf
0x1800a83b7  jmp     loc_1800A85F7
0x1800a83bc  xor     r15d, r15d
0x1800a83bf  lea     edi, [r15+1]
0x1800a83c3  mov     rax, [r13+0]
0x1800a83c7  lea     r9, [rsp+1A0h+var_160]
0x1800a83cc  lea     r8, [rsp+1A0h+var_158]
0x1800a83d1  mov     edx, r15d
0x1800a83d4  mov     rcx, r13
0x1800a83d7  mov     rax, [rax+10h]
0x1800a83db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a83e0  test    eax, eax
0x1800a83e2  jz      loc_1800A85F5
0x1800a83e8  mov     rdx, [rsp+1A0h+var_160]; unsigned __int16 *
0x1800a83ed  lea     rcx, [rsp+1A0h+var_138]; struct RtlNameValueArray *
0x1800a83f2  call    ?PcaUtilityNameValueArrayLoadFromString@@YAKAEAVRtlNameValueArray@@PEBG@Z; PcaUtilityNameValueArrayLoadFromString(RtlNameValueArray &,ushort const *)
0x1800a83f7  test    eax, eax
0x1800a83f9  jz      short loc_1800A841F
0x1800a83fb  mov     dword ptr [rsp+1A0h+var_180], eax
0x1800a83ff  lea     r9, aFailedToReadTe_0; "Failed to read telecommand parameters ["...
0x1800a8406  mov     r8d, 277h
0x1800a840c  lea     rdx, aSiufpIscandida_0; "Siufp_IsCandidate_Telecommand"
0x1800a8413  mov     ecx, edi
0x1800a8415  call    AslLogCallPrintf
0x1800a841a  jmp     loc_1800A8535
0x1800a841f  lea     r8, aFilename; "FileName"
0x1800a8426  xor     edx, edx; String2
0x1800a8428  lea     rcx, [rsp+1A0h+var_138]; this
0x1800a842d  call    ?GetValue@RtlNameValueArray@@QEBAPEBGPEBG0@Z; RtlNameValueArray::GetValue(ushort const *,ushort const *)
0x1800a8432  test    rax, rax
0x1800a8435  jnz     short loc_1800A8473
0x1800a8437  lea     r9, aTelecommandSki_0; "Telecommand,Skipped,FileName not specif"...
0x1800a843e  xor     r8d, r8d; unsigned int
0x1800a8441  mov     edx, [rbp+0A0h+arg_28]; unsigned int
0x1800a8447  lea     rcx, aSiuf; "Siuf"
0x1800a844e  call    ?PcaTracePrintf@@YAXPEBDIK0ZZ; PcaTracePrintf(char const *,uint,ulong,char const *,...)
0x1800a8453  lea     r9, aNoFilenamePara_0; "No FileName parameter for SIUF Telecomm"...
0x1800a845a  mov     r8d, 282h
0x1800a8460  lea     rdx, aSiufpIscandida_0; "Siufp_IsCandidate_Telecommand"
0x1800a8467  mov     ecx, edi
0x1800a8469  call    AslLogCallPrintf
0x1800a846e  jmp     loc_1800A8535
0x1800a8473  mov     rbx, [rsp+1A0h+var_150]
0x1800a8478  mov     rdx, rbx
0x1800a847b  mov     rcx, rax
0x1800a847e  call    AslStringPatternMatchExW
0x1800a8483  xor     ecx, ecx
0x1800a8485  test    eax, eax
0x1800a8487  jz      loc_1800A8535
0x1800a848d  mov     [rsp+1A0h+var_168], rbx; unsigned __int16 *
0x1800a8492  mov     [rsp+1A0h+var_170], rcx; int *
0x1800a8497  mov     [rsp+1A0h+var_178], rcx; unsigned int *
0x1800a849c  mov     [rsp+1A0h+var_180], rcx; unsigned __int16 *
0x1800a84a1  xor     r9d, r9d; unsigned __int16 *
0x1800a84a4  xor     r8d, r8d; unsigned __int16 *
0x1800a84a7  lea     rdx, [rbp+0A0h+String2]; unsigned __int16 *
0x1800a84ab  lea     rcx, [rbp+0A0h+var_A0]; unsigned __int16 *
0x1800a84af  call    ?PcaUtilityGetProgramInfo@@YAKPEAG0000PEAIPEAHPEBG@Z; PcaUtilityGetProgramInfo(ushort *,ushort *,ushort *,ushort *,ushort *,uint *,int *,ushort const *)
0x1800a84b4  mov     ebx, eax
0x1800a84b6  test    eax, eax
0x1800a84b8  jnz     loc_1800A8620
0x1800a84be  lea     r8, aFileid; "FileId"
0x1800a84c5  xor     edx, edx; String2
0x1800a84c7  lea     rcx, [rsp+1A0h+var_138]; this
0x1800a84cc  call    ?GetValue@RtlNameValueArray@@QEBAPEBGPEBG0@Z; RtlNameValueArray::GetValue(ushort const *,ushort const *)
0x1800a84d1  test    rax, rax
0x1800a84d4  jz      short loc_1800A84F0
0x1800a84d6  lea     rdx, [rbp+0A0h+String2]; String2
0x1800a84da  mov     rcx, rax; String1
0x1800a84dd  call    cs:__imp__wcsicmp
0x1800a84e3  test    eax, eax
0x1800a84e5  jz      short loc_1800A84F0
0x1800a84e7  lea     r9, aTelecommandSki_1; "Telecommand,Skipped,FileId mismatch"
0x1800a84ee  jmp     short loc_1800A8520
0x1800a84f0  lea     r8, aProgramid; "ProgramId"
0x1800a84f7  xor     edx, edx; String2
0x1800a84f9  lea     rcx, [rsp+1A0h+var_138]; this
0x1800a84fe  call    ?GetValue@RtlNameValueArray@@QEBAPEBGPEBG0@Z; RtlNameValueArray::GetValue(ushort const *,ushort const *)
0x1800a8503  test    rax, rax
0x1800a8506  jz      short loc_1800A853D
0x1800a8508  lea     rdx, [rbp+0A0h+var_A0]; String2
0x1800a850c  mov     rcx, rax; String1
0x1800a850f  call    cs:__imp__wcsicmp
0x1800a8515  test    eax, eax
0x1800a8517  jz      short loc_1800A853D
0x1800a8519  lea     r9, aTelecommandSki; "Telecommand,Skipped,ProgramId mismatch"
0x1800a8520  xor     r8d, r8d; unsigned int
0x1800a8523  mov     edx, [rbp+0A0h+arg_28]; unsigned int
0x1800a8529  lea     rcx, aSiuf; "Siuf"
0x1800a8530  call    ?PcaTracePrintf@@YAXPEBDIK0ZZ; PcaTracePrintf(char const *,uint,ulong,char const *,...)
0x1800a8535  add     r15d, edi
0x1800a8538  jmp     loc_1800A83C3
0x1800a853d  lea     r8, aEventindex; "EventIndex"
0x1800a8544  xor     edx, edx; String2
0x1800a8546  lea     rcx, [rsp+1A0h+var_138]; this
0x1800a854b  call    ?GetValue@RtlNameValueArray@@QEBAPEBGPEBG0@Z; RtlNameValueArray::GetValue(ushort const *,ushort const *)
0x1800a8550  mov     rbx, rax
0x1800a8553  test    rax, rax
0x1800a8556  jz      short loc_1800A85C3
0x1800a8558  mov     r8, r14
0x1800a855b  lea     rdx, aU_0; "%u"
0x1800a8562  mov     rcx, rax; Buffer
0x1800a8565  call    cs:__imp_swscanf_s
0x1800a856b  cmp     eax, edi
0x1800a856d  jz      short loc_1800A8596
0x1800a856f  mov     [rsp+1A0h+var_180], rbx
0x1800a8574  lea     r9, aBadEventIndexS; "Bad event index: %S"
0x1800a857b  mov     r8d, 2A7h
0x1800a8581  lea     rdx, aSiufpIscandida_0; "Siufp_IsCandidate_Telecommand"
0x1800a8588  mov     ecx, edi
0x1800a858a  call    AslLogCallPrintf
0x1800a858f  mov     dword ptr [r14], 0
0x1800a8596  cmp     dword ptr [r14], 0Ah
0x1800a859a  jbe     short loc_1800A85C3
0x1800a859c  mov     [rsp+1A0h+var_180], rbx
0x1800a85a1  lea     r9, aEventIndexTooL; "Event index too large: %S"
0x1800a85a8  mov     r8d, 2ACh
0x1800a85ae  lea     rdx, aSiufpIscandida_0; "Siufp_IsCandidate_Telecommand"
0x1800a85b5  mov     ecx, edi
0x1800a85b7  call    AslLogCallPrintf
0x1800a85bc  mov     dword ptr [r14], 0
0x1800a85c3  lea     r8, aStudyid; "StudyId"
0x1800a85ca  xor     edx, edx; String2
0x1800a85cc  lea     rcx, [rsp+1A0h+var_138]; this
0x1800a85d1  call    ?GetValue@RtlNameValueArray@@QEBAPEBGPEBG0@Z; RtlNameValueArray::GetValue(ushort const *,ushort const *)
0x1800a85d6  test    rax, rax
0x1800a85d9  jz      short loc_1800A85EE
0x1800a85db  mov     r8, rax; Source
0x1800a85de  mov     edx, 104h; SizeInWords
0x1800a85e3  mov     rcx, [rsp+1A0h+Destination]; Destination
0x1800a85e8  call    cs:__imp_wcscpy_s
0x1800a85ee  mov     rax, [rsp+1A0h+var_140]
0x1800a85f3  mov     [rax], edi
0x1800a85f5  xor     ebx, ebx
0x1800a85f7  lea     rcx, [rsp+1A0h+var_138]; this
0x1800a85fc  call    ??1RtlStringArray@@QEAA@XZ; RtlStringArray::~RtlStringArray(void)
0x1800a8601  mov     eax, ebx
0x1800a8603  mov     rcx, [rbp+0A0h+var_40]
0x1800a8607  xor     rcx, rsp; StackCookie
0x1800a860a  call    __security_check_cookie
0x1800a860f  add     rsp, 178h
0x1800a8616  pop     r15
0x1800a8618  pop     r14
0x1800a861a  pop     r13
0x1800a861c  pop     rdi
0x1800a861d  pop     rbx
0x1800a861e  pop     rbp
0x1800a861f  retn
0x1800a8620  mov     dword ptr [rsp+1A0h+var_180], eax
0x1800a8624  lea     r9, aFailedToRetrie_19; "Failed to retrieve program attributes ["...
0x1800a862b  mov     r8d, 290h
0x1800a8631  mov     ecx, edi
0x1800a8633  jmp     loc_1800A83AB
```
