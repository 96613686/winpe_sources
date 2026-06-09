# AssessmentCore::GetOSUpdateAssessmentInternal(tagOSUpdateAssessment *,_FILETIME *,_FILETIME *,int)

- ea: `0x1800089d0`
- end: `0x180008c33`
- name: `?GetOSUpdateAssessmentInternal@AssessmentCore@@MEAAJPEAUtagOSUpdateAssessment@@PEAU_FILETIME@@1H@Z`
- size: `611`
- prototype: `int(AssessmentCore *__hidden this, struct tagOSUpdateAssessment *, struct _FILETIME *, struct _FILETIME *, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800089d0`
- `0x18000f728`
- `0x18001752c`
- `0x180018948`
- `0x18001972e`
- `0x180019760`
- `0x18001b010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180008c0b`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008c0b`
- `ntdll!RtlPublishWnfStateData` at `0x180008b95`
- `ntdll!RtlPublishWnfStateData` at `0x180008b95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008b43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008bbf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008bcd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008be3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008b43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008bbf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008bcd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008be3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008b4b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008b4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b38`

## string_xrefs

- `0x180008b0e`: `Software\Microsoft\Windows\CurrentVersion\WaaSAssessment\Cache`
- `0x180008b15`: `WaaSAssessmentCache`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AssessmentCore::GetOSUpdateAssessmentInternal(
        AssessmentCore *this,
        struct tagOSUpdateAssessment *a2,
        struct _FILETIME *a3,
        struct _FILETIME *a4,
        int a5)
{
  _QWORD *v9; // rbx
  int v10; // esi
  int StateSeparationRegistryLocation; // ecx
  _QWORD *v12; // r15
  void *v13; // r12
  DWORD LastError; // edi
  HKEY v15; // rcx
  int v16; // eax
  __int64 i; // rdi
  __int64 v18; // rcx
  int v20; // [rsp+40h] [rbp-61h]
  LPVOID pv; // [rsp+48h] [rbp-59h] BYREF
  _QWORD *v22; // [rsp+50h] [rbp-51h] BYREF
  LPVOID *p_pv; // [rsp+58h] [rbp-49h]
  unsigned __int16 *v24; // [rsp+60h] [rbp-41h] BYREF
  char v25; // [rsp+68h] [rbp-39h]
  LPVOID v26[2]; // [rsp+70h] [rbp-31h] BYREF
  __int128 v27; // [rsp+80h] [rbp-21h]
  __int128 v28; // [rsp+90h] [rbp-11h]

  *(_OWORD *)v26 = 0;
  v27 = 0;
  v28 = 0;
  v22 = 0;
  v9 = 0;
  *((_QWORD *)this + 290) = 0;
  if ( a2 )
  {
    memset_0(a2, 0, sizeof(struct tagOSUpdateAssessment));
    v10 = (*(__int64 (__fastcall **)(AssessmentCore *, _QWORD **, LPVOID *, __int64, int, _DWORD))(*(_QWORD *)this
                                                                                                 + 152LL))(
            this,
            &v22,
            v26,
            6,
            a5,
            0);
    if ( v22 )
      v9 = v22;
    if ( v10 >= 0 && v10 != 1 )
    {
      LogLevel(4u, L"Performing Asessment");
      v10 = (*(__int64 (__fastcall **)(AssessmentCore *, struct tagOSUpdateAssessment *, LPVOID *))(*(_QWORD *)this
                                                                                                  + 160LL))(
              this,
              a2,
              v26);
      if ( a3 && a4 )
      {
        *a3 = 0;
        *a4 = 0;
        *a4 = *(struct _FILETIME *)((char *)this + 124);
        *a3 = *(struct _FILETIME *)((char *)this + 132);
      }
      if ( v10 >= 0 )
      {
        pv = 0;
        p_pv = &pv;
        v24 = 0;
        v25 = 1;
        StateSeparationRegistryLocation = GetStateSeparationRegistryLocation(
                                            L"WaaSAssessmentCache",
                                            L"Software\\Microsoft\\Windows\\CurrentVersion\\WaaSAssessment\\Cache",
                                            &v24);
        v20 = StateSeparationRegistryLocation;
        if ( v25 )
        {
          v12 = p_pv;
          v13 = *p_pv;
          if ( *p_pv )
          {
            LastError = GetLastError();
            CoTaskMemFree(v13);
            SetLastError(LastError);
            StateSeparationRegistryLocation = v20;
          }
          *v12 = v24;
        }
        if ( StateSeparationRegistryLocation >= 0 )
        {
          LogLevel(4u, L"Caching Up-to-date assessment");
          Cache::StoreAssessment(v15, (const unsigned __int16 *)pv, a2);
        }
        v16 = RtlPublishWnfStateData(WNF_WAAS_QUALITY_IMPACT, 0, &a2->assessmentForUpToDate.impact, 4, 0) | 0x10000000;
        if ( v16 < 0 )
          LogLevel(2u, L"Failed to publish WNF QUALITY IMPACT 0x%x", (unsigned int)v16);
        if ( pv )
          CoTaskMemFree(pv);
      }
    }
  }
  else
  {
    LogLevel(2u, L"AssessmentResult is null");
    v10 = -2147467261;
  }
  for ( i = 0; i != 6; ++i )
    CoTaskMemFree(v26[i]);
  CoTaskMemFree(*((LPVOID *)this + 290));
  if ( v9 )
  {
    v18 = v9[1];
    if ( v18 )
    {
      v9[1] = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    operator delete(v9);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800089d0  push    rbp
0x1800089d2  push    rbx
0x1800089d3  push    rsi
0x1800089d4  push    rdi
0x1800089d5  push    r12
0x1800089d7  push    r13
0x1800089d9  push    r14
0x1800089db  push    r15
0x1800089dd  lea     rbp, [rsp-17h]
0x1800089e2  sub     rsp, 0B8h
0x1800089e9  mov     rax, cs:__security_cookie
0x1800089f0  xor     rax, rsp
0x1800089f3  mov     [rbp+4Fh+var_50], rax
0x1800089f7  mov     rdi, r9
0x1800089fa  mov     r15, r8
0x1800089fd  mov     r13, rdx
0x180008a00  mov     r14, rcx
0x180008a03  xorps   xmm0, xmm0
0x180008a06  movups  xmmword ptr [rbp+4Fh+var_80], xmm0
0x180008a0a  movups  [rbp+4Fh+var_70], xmm0
0x180008a0e  movups  [rbp+4Fh+var_60], xmm0
0x180008a12  xor     r12d, r12d
0x180008a15  mov     [rbp+4Fh+var_A0], r12
0x180008a19  mov     ebx, r12d
0x180008a1c  mov     [rcx+910h], r12
0x180008a23  test    rdx, rdx
0x180008a26  jnz     short loc_180008A42
0x180008a28  lea     rdx, aAssessmentresu_0; "AssessmentResult is null"
0x180008a2f  lea     ecx, [r13+2]; unsigned __int8
0x180008a33  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180008a38  mov     esi, 80004003h
0x180008a3d  jmp     loc_180008BC5
0x180008a42  xor     edx, edx; Val
0x180008a44  lea     r8d, [rdx+50h]; Size
0x180008a48  mov     rcx, r13; void *
0x180008a4b  call    memset_0
0x180008a50  mov     rax, [r14]
0x180008a53  mov     r10, [rax+98h]
0x180008a5a  mov     [rsp+0F0h+var_C8], r12d
0x180008a5f  mov     eax, [rbp+4Fh+arg_20]
0x180008a62  mov     dword ptr [rsp+0F0h+var_D0], eax
0x180008a66  mov     r9d, 6
0x180008a6c  lea     r8, [rbp+4Fh+var_80]
0x180008a70  lea     rdx, [rbp+4Fh+var_A0]
0x180008a74  mov     rcx, r14
0x180008a77  mov     rax, r10
0x180008a7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a7f  mov     esi, eax
0x180008a81  mov     rax, [rbp+4Fh+var_A0]
0x180008a85  test    rax, rax
0x180008a88  jz      short loc_180008A8E
0x180008a8a  cmovnz  rbx, rax
0x180008a8e  test    esi, esi
0x180008a90  js      loc_180008BC5
0x180008a96  cmp     esi, 1
0x180008a99  jz      loc_180008BC5
0x180008a9f  lea     rdx, aPerformingAses; "Performing Asessment"
0x180008aa6  mov     ecx, 4; unsigned __int8
0x180008aab  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180008ab0  mov     rax, [r14]
0x180008ab3  lea     r8, [rbp+4Fh+var_80]
0x180008ab7  mov     rdx, r13
0x180008aba  mov     rcx, r14
0x180008abd  mov     rax, [rax+0A0h]
0x180008ac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ac9  mov     esi, eax
0x180008acb  test    r15, r15
0x180008ace  jz      short loc_180008AEE
0x180008ad0  test    rdi, rdi
0x180008ad3  jz      short loc_180008AEE
0x180008ad5  xor     eax, eax
0x180008ad7  mov     [r15], rax
0x180008ada  mov     [rdi], rax
0x180008add  mov     rax, [r14+7Ch]
0x180008ae1  mov     [rdi], rax
0x180008ae4  mov     rax, [r14+84h]
0x180008aeb  mov     [r15], rax
0x180008aee  test    esi, esi
0x180008af0  js      loc_180008BC5
0x180008af6  mov     [rbp+4Fh+pv], r12
0x180008afa  lea     rax, [rbp+4Fh+pv]
0x180008afe  mov     [rbp+4Fh+var_98], rax
0x180008b02  mov     [rbp+4Fh+var_90], r12
0x180008b06  mov     [rbp+4Fh+var_88], 1
0x180008b0a  lea     r8, [rbp+4Fh+var_90]; unsigned __int16 **
0x180008b0e  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180008b15  lea     rcx, aWaasassessment_0; "WaaSAssessmentCache"
0x180008b1c  call    ?GetStateSeparationRegistryLocation@@YAJPEBG0PEAPEAG@Z; GetStateSeparationRegistryLocation(ushort const *,ushort const *,ushort * *)
0x180008b21  mov     ecx, eax
0x180008b23  mov     [rbp+4Fh+var_B0], eax
0x180008b26  cmp     [rbp+4Fh+var_88], r12b
0x180008b2a  jz      short loc_180008B5E
0x180008b2c  mov     r15, [rbp+4Fh+var_98]
0x180008b30  mov     r12, [r15]
0x180008b33  test    r12, r12
0x180008b36  jz      short loc_180008B54
0x180008b38  call    cs:__imp_GetLastError
0x180008b3e  mov     edi, eax
0x180008b40  mov     rcx, r12; pv
0x180008b43  call    cs:__imp_CoTaskMemFree
0x180008b49  mov     ecx, edi; dwErrCode
0x180008b4b  call    cs:__imp_SetLastError
0x180008b51  mov     ecx, [rbp+4Fh+var_B0]
0x180008b54  mov     rax, [rbp+4Fh+var_90]
0x180008b58  mov     [r15], rax
0x180008b5b  xor     r12d, r12d
0x180008b5e  test    ecx, ecx
0x180008b60  js      short loc_180008B7F
0x180008b62  lea     rdx, aCachingUpToDat; "Caching Up-to-date assessment"
0x180008b69  mov     ecx, 4; unsigned __int8
0x180008b6e  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180008b73  mov     r8, r13; struct tagOSUpdateAssessment *
0x180008b76  mov     rdx, [rbp+4Fh+pv]; unsigned __int16 *
0x180008b7a  call    ?StoreAssessment@Cache@@SAJPEAUHKEY__@@PEBGAEAUtagOSUpdateAssessment@@@Z; Cache::StoreAssessment(HKEY__ *,ushort const *,tagOSUpdateAssessment &)
0x180008b7f  lea     r8, [r13+14h]
0x180008b83  mov     [rsp+0F0h+var_D0], r12
0x180008b88  xor     edx, edx
0x180008b8a  lea     r9d, [rdx+4]
0x180008b8e  mov     rcx, cs:WNF_WAAS_QUALITY_IMPACT
0x180008b95  call    cs:__imp_RtlPublishWnfStateData
0x180008b9b  or      eax, 10000000h
0x180008ba0  jge     short loc_180008BB6
0x180008ba2  mov     r8d, eax
0x180008ba5  lea     rdx, aFailedToPublis_0; "Failed to publish WNF QUALITY IMPACT 0x"...
0x180008bac  mov     ecx, 2; unsigned __int8
0x180008bb1  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180008bb6  mov     rcx, [rbp+4Fh+pv]; pv
0x180008bba  test    rcx, rcx
0x180008bbd  jz      short loc_180008BC5
0x180008bbf  call    cs:__imp_CoTaskMemFree
0x180008bc5  mov     rdi, r12
0x180008bc8  mov     rcx, [rbp+rdi*8+4Fh+var_80]; pv
0x180008bcd  call    cs:__imp_CoTaskMemFree
0x180008bd3  inc     rdi
0x180008bd6  cmp     rdi, 6
0x180008bda  jnz     short loc_180008BC8
0x180008bdc  mov     rcx, [r14+910h]; pv
0x180008be3  call    cs:__imp_CoTaskMemFree
0x180008be9  test    rbx, rbx
0x180008bec  jz      short loc_180008C11
0x180008bee  mov     rcx, [rbx+8]
0x180008bf2  test    rcx, rcx
0x180008bf5  jz      short loc_180008C08
0x180008bf7  mov     [rbx+8], r12
0x180008bfb  mov     rax, [rcx]
0x180008bfe  mov     rax, [rax+10h]
0x180008c02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c07  nop
0x180008c08  mov     rcx, rbx
0x180008c0b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008c11  mov     eax, esi
0x180008c13  mov     rcx, [rbp+4Fh+var_50]
0x180008c17  xor     rcx, rsp; StackCookie
0x180008c1a  call    __security_check_cookie
0x180008c1f  add     rsp, 0B8h
0x180008c26  pop     r15
0x180008c28  pop     r14
0x180008c2a  pop     r13
0x180008c2c  pop     r12
0x180008c2e  pop     rdi
0x180008c2f  pop     rsi
0x180008c30  pop     rbx
0x180008c31  pop     rbp
0x180008c32  retn
```
