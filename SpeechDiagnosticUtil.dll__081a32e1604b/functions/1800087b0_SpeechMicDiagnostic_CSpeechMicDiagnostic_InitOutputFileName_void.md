# SpeechMicDiagnostic::CSpeechMicDiagnostic::InitOutputFileName(void)

- ea: `0x1800087b0`
- end: `0x180008942`
- name: `?InitOutputFileName@CSpeechMicDiagnostic@SpeechMicDiagnostic@@AEAAJXZ`
- size: `402`
- prototype: `__int64 __fastcall(SpeechMicDiagnostic::CSpeechMicDiagnostic *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008a9c`

## callees

- `0x180002910`
- `0x180003290`
- `0x180005b08`
- `0x180005b28`
- `0x180005f08`
- `0x180007b44`
- `0x1800087b0`

## import_xrefs

- `KERNEL32!GetEnvironmentVariableW` at `0x1800087dd`
- `KERNEL32!GetEnvironmentVariableW` at `0x18000885e`
- `KERNEL32!GetEnvironmentVariableW` at `0x1800087dd`
- `KERNEL32!GetEnvironmentVariableW` at `0x18000885e`
- `KERNEL32!GetSystemTime` at `0x18000889c`
- `KERNEL32!GetSystemTime` at `0x18000889c`
- `ole32!CoTaskMemAlloc` at `0x180008815`
- `ole32!CoTaskMemAlloc` at `0x180008815`

## pseudocode

```c
__int64 __fastcall SpeechMicDiagnostic::CSpeechMicDiagnostic::InitOutputFileName(
        SpeechMicDiagnostic::CSpeechMicDiagnostic *this)
{
  DWORD EnvironmentVariableW; // eax
  const char *v3; // r9
  DWORD v4; // ebx
  WCHAR *v6; // rax
  WCHAR *v7; // rdi
  int appended; // ebx
  __int64 v9; // rdx
  __int64 v10; // r8
  int wMonth; // [rsp+20h] [rbp-E8h]
  _SYSTEMTIME SystemTime; // [rsp+40h] [rbp-C8h] BYREF
  unsigned __int16 v13[64]; // [rsp+50h] [rbp-B8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  EnvironmentVariableW = GetEnvironmentVariableW(L"TEMP", 0, 0);
  v4 = EnvironmentVariableW;
  if ( !EnvironmentVariableW )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x192,
             (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\speechmicdiagnostic.cpp",
             v3);
  v6 = (WCHAR *)CoTaskMemAlloc(2LL * EnvironmentVariableW);
  v7 = v6;
  if ( !v6 )
  {
    appended = -2147024882;
    v9 = 405;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\speechmicdiagnostic.cpp",
      (const char *)(unsigned int)appended,
      wMonth);
    return (unsigned int)appended;
  }
  if ( GetEnvironmentVariableW(L"TEMP", v6, v4) != v4 - 1 )
  {
    appended = -2147418113;
    v9 = 409;
    goto LABEL_5;
  }
  memset_0(v13, 0, sizeof(v13));
  SystemTime = 0;
  GetSystemTime(&SystemTime);
  wMonth = SystemTime.wMonth;
  appended = StringCchPrintfW(v13, 0x40u, L"\\SpeechMicDiagnostic_%u-%02u-%02u%02u.wav", SystemTime.wYear);
  if ( appended < 0 )
  {
    v9 = 418;
    goto LABEL_5;
  }
  v10 = -1;
  *((_QWORD *)this + 4) = v7;
  do
    ++v10;
  while ( v13[v10] );
  appended = CSpDynamicString::AppendHR((SpeechMicDiagnostic::CSpeechMicDiagnostic *)((char *)this + 32), v13, v10);
  if ( appended < 0 )
  {
    v9 = 421;
    goto LABEL_5;
  }
  return 0;
}

```

## disassembly

```asm
0x1800087b0  push    rbx
0x1800087b2  push    rbp
0x1800087b3  push    rsi
0x1800087b4  push    rdi
0x1800087b5  sub     rsp, 0E8h
0x1800087bc  mov     rax, cs:__security_cookie
0x1800087c3  xor     rax, rsp
0x1800087c6  mov     [rsp+108h+var_38], rax
0x1800087ce  mov     rsi, rcx
0x1800087d1  xor     r8d, r8d; nSize
0x1800087d4  lea     rcx, Name; "TEMP"
0x1800087db  xor     edx, edx; lpBuffer
0x1800087dd  call    cs:__imp_GetEnvironmentVariableW
0x1800087e4  nop     dword ptr [rax+rax+00h]
0x1800087e9  xor     ebp, ebp
0x1800087eb  mov     ebx, eax
0x1800087ed  test    eax, eax
0x1800087ef  jnz     short loc_18000880F
0x1800087f1  mov     rcx, [rsp+108h]; this
0x1800087f9  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x180008800  mov     edx, 192h; void *
0x180008805  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000880a  jmp     loc_180008925
0x18000880f  mov     rcx, rbx
0x180008812  add     rcx, rcx; cb
0x180008815  call    cs:__imp_CoTaskMemAlloc
0x18000881c  nop     dword ptr [rax+rax+00h]
0x180008821  mov     rdi, rax
0x180008824  test    rax, rax
0x180008827  jnz     short loc_180008851
0x180008829  mov     ebx, 8007000Eh
0x18000882e  mov     edx, 195h; void *
0x180008833  mov     rcx, [rsp+108h]; this
0x18000883b  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x180008842  mov     r9d, ebx; char *
0x180008845  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000884a  mov     eax, ebx
0x18000884c  jmp     loc_180008925
0x180008851  mov     r8d, ebx; nSize
0x180008854  lea     rcx, Name; "TEMP"
0x18000885b  mov     rdx, rdi; lpBuffer
0x18000885e  call    cs:__imp_GetEnvironmentVariableW
0x180008865  nop     dword ptr [rax+rax+00h]
0x18000886a  lea     ecx, [rbx-1]
0x18000886d  cmp     eax, ecx
0x18000886f  jz      short loc_18000887D
0x180008871  mov     ebx, 8000FFFFh
0x180008876  mov     edx, 199h
0x18000887b  jmp     short loc_180008833
0x18000887d  xor     edx, edx; Val
0x18000887f  lea     rcx, [rsp+108h+var_B8]; void *
0x180008884  mov     r8d, 80h; Size
0x18000888a  call    memset_0
0x18000888f  xorps   xmm0, xmm0
0x180008892  lea     rcx, [rsp+108h+SystemTime]; lpSystemTime
0x180008897  movups  xmmword ptr [rsp+108h+SystemTime.wYear], xmm0
0x18000889c  call    cs:__imp_GetSystemTime
0x1800088a3  nop     dword ptr [rax+rax+00h]
0x1800088a8  movzx   ecx, [rsp+108h+SystemTime.wHour]
0x1800088ad  lea     r8, aSpeechmicdiagn; "\\SpeechMicDiagnostic_%u-%02u-%02u%02u."...
0x1800088b4  movzx   edx, [rsp+108h+SystemTime.wMonth]
0x1800088b9  movzx   eax, [rsp+108h+SystemTime.wMinute]
0x1800088be  movzx   r9d, [rsp+108h+SystemTime.wYear]
0x1800088c4  mov     [rsp+108h+var_D8], eax
0x1800088c8  mov     [rsp+108h+var_E0], ecx
0x1800088cc  lea     rcx, [rsp+108h+var_B8]; unsigned __int16 *
0x1800088d1  mov     [rsp+108h+var_E8], edx
0x1800088d5  mov     edx, 40h ; '@'; unsigned __int64
0x1800088da  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800088df  mov     ebx, eax
0x1800088e1  test    eax, eax
0x1800088e3  jns     short loc_1800088EF
0x1800088e5  mov     edx, 1A2h
0x1800088ea  jmp     loc_180008833
0x1800088ef  lea     rcx, [rsi+20h]; this
0x1800088f3  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800088f7  mov     [rcx], rdi
0x1800088fa  lea     rax, [rsp+108h+var_B8]
0x1800088ff  inc     r8; unsigned int
0x180008902  cmp     [rax+r8*2], bp
0x180008907  jnz     short loc_1800088FF
0x180008909  lea     rdx, [rsp+108h+var_B8]; unsigned __int16 *
0x18000890e  call    ?AppendHR@CSpDynamicString@@QEAAJPEBGK@Z; CSpDynamicString::AppendHR(ushort const *,ulong)
0x180008913  mov     ebx, eax
0x180008915  test    eax, eax
0x180008917  jns     short loc_180008923
0x180008919  mov     edx, 1A5h
0x18000891e  jmp     loc_180008833
0x180008923  xor     eax, eax
0x180008925  mov     rcx, [rsp+108h+var_38]
0x18000892d  xor     rcx, rsp; StackCookie
0x180008930  call    __security_check_cookie
0x180008935  add     rsp, 0E8h
0x18000893c  pop     rdi
0x18000893d  pop     rsi
0x18000893e  pop     rbp
0x18000893f  pop     rbx
0x180008940  retn
```
