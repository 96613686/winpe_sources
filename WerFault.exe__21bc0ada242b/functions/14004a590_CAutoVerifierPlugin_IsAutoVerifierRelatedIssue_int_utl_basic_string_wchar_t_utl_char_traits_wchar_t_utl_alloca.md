# CAutoVerifierPlugin::IsAutoVerifierRelatedIssue(int *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x14004a590`
- end: `0x14004a762`
- name: `?IsAutoVerifierRelatedIssue@CAutoVerifierPlugin@@AEAAJPEAHPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `466`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14004aed0`

## callees

- `0x14001444c`
- `0x140014474`
- `0x140015b40`
- `0x140049b98`
- `0x140049df4`
- `0x14004a590`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14004a74a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14004a74a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004a66f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004a66f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14004a620`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14004a620`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAutoVerifierPlugin::IsAutoVerifierRelatedIssue(CAutoVerifierPlugin *a1, _DWORD *a2, _QWORD *a3)
{
  _WORD *v6; // r8
  __int64 v7; // rcx
  unsigned int v8; // ebx
  HMODULE v9; // rdi
  const WCHAR *v10; // rbx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  int v13; // ebx
  LPCWSTR lpLibFileName; // [rsp+30h] [rbp-20h] BYREF
  HINSTANCE v16; // [rsp+38h] [rbp-18h] BYREF
  HMODULE v17; // [rsp+40h] [rbp-10h]
  char v18; // [rsp+98h] [rbp+48h] BYREF
  int v19; // [rsp+A0h] [rbp+50h] BYREF
  HINSTANCE v20; // [rsp+A8h] [rbp+58h] BYREF

  v20 = 0;
  v17 = 0;
  v16 = 0;
  v18 = 0;
  lpLibFileName = 0;
  v19 = 0;
  *a2 = 0;
  v6 = (_WORD *)*a3;
  a3[1] = v6;
  *v6 = 0;
  if ( (int)CAutoVerifierPlugin::FindVerifierAndWerDiagDlls(a1, &v20, &lpLibFileName, &v16, &v19) < 0 )
  {
    v8 = 0;
LABEL_3:
    v9 = 0;
    goto LABEL_28;
  }
  if ( !v20 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v7);
  v10 = lpLibFileName;
  if ( !lpLibFileName )
    MicrosoftTelemetryAssertTriggeredNoArgs(v7);
  Library = LoadLibraryExW(v10, 0, 0);
  v9 = Library;
  v17 = Library;
  if ( !Library )
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids);
    }
    v8 = -2147467259;
    goto LABEL_3;
  }
  ProcAddress = GetProcAddress(Library, "VerifierGetInfoForException");
  if ( ProcAddress )
  {
    v13 = ((__int64 (__fastcall *)(_QWORD, HINSTANCE, char *, char *, char *))ProcAddress)(
            *((_QWORD *)a1 + 98),
            v20,
            (char *)a1 + 800,
            &v18,
            (char *)a1 + 8);
    if ( v13 >= 0 )
    {
      if ( v18 )
      {
        if ( *((_QWORD *)a1 + 1) )
        {
          *a2 = 1;
          if ( v16 )
            CAutoVerifierPlugin::GetOriginalBucket((__int64)a1, (__int64)v16, (__int64)a3);
        }
      }
      v8 = 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids,
          (unsigned int)v13);
      }
      v8 = v13 | 0x10000000;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids);
    }
    v8 = -2147467259;
  }
LABEL_28:
  if ( ((unsigned __int64)v9 & -(__int64)(v19 != 0)) != 0 )
    FreeLibrary((HMODULE)((unsigned __int64)v9 & -(__int64)(v19 != 0)));
  return v8;
}

```

## disassembly

```asm
0x14004a590  push    rbp
0x14004a592  push    rbx
0x14004a593  push    rdi
0x14004a594  push    r12
0x14004a596  push    r13
0x14004a598  push    r14
0x14004a59a  push    r15
0x14004a59c  mov     rbp, rsp
0x14004a59f  sub     rsp, 50h
0x14004a5a3  mov     r12, r8
0x14004a5a6  mov     r13, rdx
0x14004a5a9  mov     r14, rcx
0x14004a5ac  xor     r15d, r15d
0x14004a5af  mov     [rbp+arg_18], r15
0x14004a5b3  mov     [rbp+var_10], r15
0x14004a5b7  mov     [rbp+var_18], r15
0x14004a5bb  mov     [rbp+arg_8], r15b
0x14004a5bf  mov     [rbp+lpLibFileName], r15
0x14004a5c3  mov     [rbp+arg_10], r15d
0x14004a5c7  mov     [rdx], r15d
0x14004a5ca  mov     r8, [r8]
0x14004a5cd  mov     [r12+8], r8
0x14004a5d2  mov     [r8], r15w
0x14004a5d6  lea     rax, [rbp+arg_10]
0x14004a5da  mov     [rsp+50h+var_30], rax; int *
0x14004a5df  lea     r9, [rbp+var_18]; HINSTANCE *
0x14004a5e3  lea     r8, [rbp+lpLibFileName]; wchar_t **
0x14004a5e7  lea     rdx, [rbp+arg_18]; HINSTANCE *
0x14004a5eb  call    ?FindVerifierAndWerDiagDlls@CAutoVerifierPlugin@@AEAAJPEAPEAUHINSTANCE__@@PEAPEB_W0PEAH@Z; CAutoVerifierPlugin::FindVerifierAndWerDiagDlls(HINSTANCE__ * *,wchar_t const * *,HINSTANCE__ * *,int *)
0x14004a5f0  test    eax, eax
0x14004a5f2  jns     short loc_14004A5FF
0x14004a5f4  mov     ebx, r15d
0x14004a5f7  mov     rdi, r15
0x14004a5fa  jmp     loc_14004A73D
0x14004a5ff  cmp     [rbp+arg_18], r15
0x14004a603  jnz     short loc_14004A60A
0x14004a605  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14004a60a  mov     rbx, [rbp+lpLibFileName]
0x14004a60e  test    rbx, rbx
0x14004a611  jnz     short loc_14004A618
0x14004a613  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14004a618  xor     r8d, r8d; dwFlags
0x14004a61b  xor     edx, edx; hFile
0x14004a61d  mov     rcx, rbx; lpLibFileName
0x14004a620  call    cs:__imp_LoadLibraryExW
0x14004a626  mov     rdi, rax
0x14004a629  mov     [rbp+var_10], rax
0x14004a62d  test    rax, rax
0x14004a630  jnz     short loc_14004A665
0x14004a632  lea     rax, WPP_GLOBAL_Control
0x14004a639  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a640  cmp     rcx, rax
0x14004a643  jz      short loc_14004A65E
0x14004a645  test    byte ptr [rcx+1Ch], 1
0x14004a649  jz      short loc_14004A65E
0x14004a64b  lea     edx, [rdi+0Fh]
0x14004a64e  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x14004a655  mov     rcx, [rcx+10h]
0x14004a659  call    WPP_SF_
0x14004a65e  mov     ebx, 80004005h
0x14004a663  jmp     short loc_14004A5F7
0x14004a665  lea     rdx, aVerifiergetinf; "VerifierGetInfoForException"
0x14004a66c  mov     rcx, rax; hModule
0x14004a66f  call    cs:__imp_GetProcAddress
0x14004a675  test    rax, rax
0x14004a678  jnz     short loc_14004A6B2
0x14004a67a  lea     rax, WPP_GLOBAL_Control
0x14004a681  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a688  cmp     rcx, rax
0x14004a68b  jz      short loc_14004A6A8
0x14004a68d  test    byte ptr [rcx+1Ch], 1
0x14004a691  jz      short loc_14004A6A8
0x14004a693  mov     edx, 10h
0x14004a698  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x14004a69f  mov     rcx, [rcx+10h]
0x14004a6a3  call    WPP_SF_
0x14004a6a8  mov     ebx, 80004005h
0x14004a6ad  jmp     loc_14004A73D
0x14004a6b2  lea     r15, [r14+8]
0x14004a6b6  lea     r8, [r14+320h]
0x14004a6bd  mov     [rsp+50h+var_30], r15
0x14004a6c2  lea     r9, [rbp+arg_8]
0x14004a6c6  mov     rdx, [rbp+arg_18]
0x14004a6ca  mov     rcx, [r14+310h]
0x14004a6d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004a6d6  mov     ebx, eax
0x14004a6d8  test    eax, eax
0x14004a6da  jns     short loc_14004A713
0x14004a6dc  lea     rax, WPP_GLOBAL_Control
0x14004a6e3  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a6ea  cmp     rcx, rax
0x14004a6ed  jz      short loc_14004A70D
0x14004a6ef  test    byte ptr [rcx+1Ch], 1
0x14004a6f3  jz      short loc_14004A70D
0x14004a6f5  mov     edx, 11h
0x14004a6fa  mov     r9d, ebx
0x14004a6fd  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x14004a704  mov     rcx, [rcx+10h]
0x14004a708  call    WPP_SF_d
0x14004a70d  bts     ebx, 1Ch
0x14004a711  jmp     short loc_14004A73D
0x14004a713  cmp     [rbp+arg_8], 0
0x14004a717  jz      short loc_14004A73B
0x14004a719  cmp     qword ptr [r15], 0
0x14004a71d  jz      short loc_14004A73B
0x14004a71f  mov     dword ptr [r13+0], 1
0x14004a727  mov     rdx, [rbp+var_18]
0x14004a72b  test    rdx, rdx
0x14004a72e  jz      short loc_14004A73B
0x14004a730  mov     r8, r12
0x14004a733  mov     rcx, r14
0x14004a736  call    ?GetOriginalBucket@CAutoVerifierPlugin@@AEAAJPEAUHINSTANCE__@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CAutoVerifierPlugin::GetOriginalBucket(HINSTANCE__ *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x14004a73b  xor     ebx, ebx
0x14004a73d  mov     ecx, [rbp+arg_10]
0x14004a740  neg     ecx
0x14004a742  sbb     rcx, rcx
0x14004a745  and     rcx, rdi; hLibModule
0x14004a748  jz      short loc_14004A750
0x14004a74a  call    cs:__imp_FreeLibrary
0x14004a750  mov     eax, ebx
0x14004a752  add     rsp, 50h
0x14004a756  pop     r15
0x14004a758  pop     r14
0x14004a75a  pop     r13
0x14004a75c  pop     r12
0x14004a75e  pop     rdi
0x14004a75f  pop     rbx
0x14004a760  pop     rbp
0x14004a761  retn
```
