# CAutoVerifierPlugin::IsAutoVerifierRelatedIssue(int *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x14004d9bc`
- end: `0x14004dba1`
- name: `?IsAutoVerifierRelatedIssue@CAutoVerifierPlugin@@AEAAJPEAHPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `485`
- prototype: `__int64 __fastcall(CAutoVerifierPlugin *, _DWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14004e350`

## callees

- `0x140014ee4`
- `0x140014f14`
- `0x1400166ec`
- `0x14004cf6c`
- `0x14004d1e8`
- `0x14004d9bc`
- `0x140061010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14004db82`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14004db82`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004daa1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004daa1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14004da4c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14004da4c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CAutoVerifierPlugin::IsAutoVerifierRelatedIssue(CAutoVerifierPlugin *a1, _DWORD *a2, _QWORD *a3)
{
  _WORD *v6; // r8
  unsigned int v7; // ebx
  HMODULE v8; // rdi
  const WCHAR *v9; // rbx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  int v12; // ebx
  LPCWSTR lpLibFileName; // [rsp+30h] [rbp-20h] BYREF
  HINSTANCE v15; // [rsp+38h] [rbp-18h] BYREF
  HMODULE v16; // [rsp+40h] [rbp-10h]
  char v17; // [rsp+98h] [rbp+48h] BYREF
  int v18; // [rsp+A0h] [rbp+50h] BYREF
  HINSTANCE v19; // [rsp+A8h] [rbp+58h] BYREF

  v19 = 0;
  v16 = 0;
  v15 = 0;
  v17 = 0;
  lpLibFileName = 0;
  v18 = 0;
  *a2 = 0;
  v6 = (_WORD *)*a3;
  a3[1] = v6;
  *v6 = 0;
  if ( (int)CAutoVerifierPlugin::FindVerifierAndWerDiagDlls(a1, &v19, &lpLibFileName, &v15, &v18) < 0 )
  {
    v7 = 0;
LABEL_3:
    v8 = 0;
    goto LABEL_28;
  }
  if ( !v19 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v9 = lpLibFileName;
  if ( !lpLibFileName )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  Library = LoadLibraryExW(v9, 0, 0);
  v8 = Library;
  v16 = Library;
  if ( !Library )
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids);
    }
    v7 = -2147467259;
    goto LABEL_3;
  }
  ProcAddress = GetProcAddress(Library, "VerifierGetInfoForException");
  if ( ProcAddress )
  {
    v12 = ((__int64 (__fastcall *)(_QWORD, HINSTANCE, char *, char *, char *))ProcAddress)(
            *((_QWORD *)a1 + 98),
            v19,
            (char *)a1 + 800,
            &v17,
            (char *)a1 + 8);
    if ( v12 >= 0 )
    {
      if ( v17 )
      {
        if ( *((_QWORD *)a1 + 1) )
        {
          *a2 = 1;
          if ( v15 )
            CAutoVerifierPlugin::GetOriginalBucket((__int64)a1, (__int64)v15, (__int64)a3);
        }
      }
      v7 = 0;
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
          (unsigned int)v12);
      }
      v7 = v12 | 0x10000000;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids);
    }
    v7 = -2147467259;
  }
LABEL_28:
  if ( ((unsigned __int64)v8 & -(__int64)(v18 != 0)) != 0 )
    FreeLibrary((HMODULE)((unsigned __int64)v8 & -(__int64)(v18 != 0)));
  return v7;
}

```

## disassembly

```asm
0x14004d9bc  push    rbp
0x14004d9be  push    rbx
0x14004d9bf  push    rdi
0x14004d9c0  push    r12
0x14004d9c2  push    r13
0x14004d9c4  push    r14
0x14004d9c6  push    r15
0x14004d9c8  mov     rbp, rsp
0x14004d9cb  sub     rsp, 50h
0x14004d9cf  mov     r12, r8
0x14004d9d2  mov     r13, rdx
0x14004d9d5  mov     r14, rcx
0x14004d9d8  xor     r15d, r15d
0x14004d9db  mov     [rbp+arg_18], r15
0x14004d9df  mov     [rbp+var_10], r15
0x14004d9e3  mov     [rbp+var_18], r15
0x14004d9e7  mov     [rbp+arg_8], r15b
0x14004d9eb  mov     [rbp+lpLibFileName], r15
0x14004d9ef  mov     [rbp+arg_10], r15d
0x14004d9f3  mov     [rdx], r15d
0x14004d9f6  mov     r8, [r8]
0x14004d9f9  mov     [r12+8], r8
0x14004d9fe  mov     [r8], r15w
0x14004da02  lea     rax, [rbp+arg_10]
0x14004da06  mov     [rsp+50h+var_30], rax; int *
0x14004da0b  lea     r9, [rbp+var_18]; HINSTANCE *
0x14004da0f  lea     r8, [rbp+lpLibFileName]; wchar_t **
0x14004da13  lea     rdx, [rbp+arg_18]; HINSTANCE *
0x14004da17  call    ?FindVerifierAndWerDiagDlls@CAutoVerifierPlugin@@AEAAJPEAPEAUHINSTANCE__@@PEAPEB_W0PEAH@Z; CAutoVerifierPlugin::FindVerifierAndWerDiagDlls(HINSTANCE__ * *,wchar_t const * *,HINSTANCE__ * *,int *)
0x14004da1c  test    eax, eax
0x14004da1e  jns     short loc_14004DA2B
0x14004da20  mov     ebx, r15d
0x14004da23  mov     rdi, r15
0x14004da26  jmp     loc_14004DB75
0x14004da2b  cmp     [rbp+arg_18], r15
0x14004da2f  jnz     short loc_14004DA36
0x14004da31  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14004da36  mov     rbx, [rbp+lpLibFileName]
0x14004da3a  test    rbx, rbx
0x14004da3d  jnz     short loc_14004DA44
0x14004da3f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14004da44  xor     r8d, r8d; dwFlags
0x14004da47  xor     edx, edx; hFile
0x14004da49  mov     rcx, rbx; lpLibFileName
0x14004da4c  call    cs:__imp_LoadLibraryExW
0x14004da53  nop     dword ptr [rax+rax+00h]
0x14004da58  mov     rdi, rax
0x14004da5b  mov     [rbp+var_10], rax
0x14004da5f  test    rax, rax
0x14004da62  jnz     short loc_14004DA97
0x14004da64  lea     rax, WPP_GLOBAL_Control
0x14004da6b  mov     rcx, cs:WPP_GLOBAL_Control
0x14004da72  cmp     rcx, rax
0x14004da75  jz      short loc_14004DA90
0x14004da77  test    byte ptr [rcx+1Ch], 1
0x14004da7b  jz      short loc_14004DA90
0x14004da7d  lea     edx, [rdi+0Fh]
0x14004da80  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x14004da87  mov     rcx, [rcx+10h]
0x14004da8b  call    WPP_SF_
0x14004da90  mov     ebx, 80004005h
0x14004da95  jmp     short loc_14004DA23
0x14004da97  lea     rdx, aVerifiergetinf; "VerifierGetInfoForException"
0x14004da9e  mov     rcx, rax; hModule
0x14004daa1  call    cs:__imp_GetProcAddress
0x14004daa8  nop     dword ptr [rax+rax+00h]
0x14004daad  test    rax, rax
0x14004dab0  jnz     short loc_14004DAEA
0x14004dab2  lea     rax, WPP_GLOBAL_Control
0x14004dab9  mov     rcx, cs:WPP_GLOBAL_Control
0x14004dac0  cmp     rcx, rax
0x14004dac3  jz      short loc_14004DAE0
0x14004dac5  test    byte ptr [rcx+1Ch], 1
0x14004dac9  jz      short loc_14004DAE0
0x14004dacb  mov     edx, 10h
0x14004dad0  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x14004dad7  mov     rcx, [rcx+10h]
0x14004dadb  call    WPP_SF_
0x14004dae0  mov     ebx, 80004005h
0x14004dae5  jmp     loc_14004DB75
0x14004daea  lea     r15, [r14+8]
0x14004daee  lea     r8, [r14+320h]
0x14004daf5  mov     [rsp+50h+var_30], r15
0x14004dafa  lea     r9, [rbp+arg_8]
0x14004dafe  mov     rdx, [rbp+arg_18]
0x14004db02  mov     rcx, [r14+310h]
0x14004db09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004db0e  mov     ebx, eax
0x14004db10  test    eax, eax
0x14004db12  jns     short loc_14004DB4B
0x14004db14  lea     rax, WPP_GLOBAL_Control
0x14004db1b  mov     rcx, cs:WPP_GLOBAL_Control
0x14004db22  cmp     rcx, rax
0x14004db25  jz      short loc_14004DB45
0x14004db27  test    byte ptr [rcx+1Ch], 1
0x14004db2b  jz      short loc_14004DB45
0x14004db2d  mov     edx, 11h
0x14004db32  mov     r9d, ebx
0x14004db35  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x14004db3c  mov     rcx, [rcx+10h]
0x14004db40  call    WPP_SF_d
0x14004db45  bts     ebx, 1Ch
0x14004db49  jmp     short loc_14004DB75
0x14004db4b  cmp     [rbp+arg_8], 0
0x14004db4f  jz      short loc_14004DB73
0x14004db51  cmp     qword ptr [r15], 0
0x14004db55  jz      short loc_14004DB73
0x14004db57  mov     dword ptr [r13+0], 1
0x14004db5f  mov     rdx, [rbp+var_18]
0x14004db63  test    rdx, rdx
0x14004db66  jz      short loc_14004DB73
0x14004db68  mov     r8, r12
0x14004db6b  mov     rcx, r14
0x14004db6e  call    ?GetOriginalBucket@CAutoVerifierPlugin@@AEAAJPEAUHINSTANCE__@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CAutoVerifierPlugin::GetOriginalBucket(HINSTANCE__ *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x14004db73  xor     ebx, ebx
0x14004db75  mov     ecx, [rbp+arg_10]
0x14004db78  neg     ecx
0x14004db7a  sbb     rcx, rcx
0x14004db7d  and     rcx, rdi; hLibModule
0x14004db80  jz      short loc_14004DB8E
0x14004db82  call    cs:__imp_FreeLibrary
0x14004db89  nop     dword ptr [rax+rax+00h]
0x14004db8e  mov     eax, ebx
0x14004db90  add     rsp, 50h
0x14004db94  pop     r15
0x14004db96  pop     r14
0x14004db98  pop     r13
0x14004db9a  pop     r12
0x14004db9c  pop     rdi
0x14004db9d  pop     rbx
0x14004db9e  pop     rbp
0x14004db9f  retn
```
