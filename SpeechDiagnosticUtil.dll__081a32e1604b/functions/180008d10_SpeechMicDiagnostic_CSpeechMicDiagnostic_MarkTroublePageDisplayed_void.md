# SpeechMicDiagnostic::CSpeechMicDiagnostic::MarkTroublePageDisplayed(void)

- ea: `0x180008d10`
- end: `0x180008fd2`
- name: `?MarkTroublePageDisplayed@CSpeechMicDiagnostic@SpeechMicDiagnostic@@UEAAJXZ`
- size: `706`
- prototype: `__int64 __fastcall(SpeechMicDiagnostic::CSpeechMicDiagnostic *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002910`
- `0x180003290`
- `0x180005b28`
- `0x180005f08`
- `0x18000744c`
- `0x180007510`
- `0x180007f18`
- `0x180008d10`
- `0x18000989c`
- `0x18000a494`

## import_xrefs

- `KERNEL32!GetSystemTime` at `0x180008ddf`
- `KERNEL32!GetSystemTime` at `0x180008ddf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180008da4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180008da4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008f00`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008f00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008ecb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008f32`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008f82`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008ecb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008f32`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008f82`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SpeechMicDiagnostic::CSpeechMicDiagnostic::MarkTroublePageDisplayed(
        SpeechMicDiagnostic::CSpeechMicDiagnostic *this)
{
  unsigned int v2; // eax
  unsigned int v3; // r8d
  __int64 v4; // rdx
  int v5; // eax
  unsigned int v6; // ebx
  unsigned __int64 v7; // r9
  __int64 v8; // rdx
  __int64 v9; // rcx
  BYTE *v10; // rax
  const WCHAR *v11; // rdx
  unsigned int dwOptions; // [rsp+20h] [rbp-E0h]
  int dwOptionsa; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v17[42]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 Data[256]; // [rsp+1C0h] [rbp+C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3E8h] [rbp+2E8h]

  wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v17,
    "MarkTroublePageDisplayed");
  v17[0] = &SpeechMicDiagnostic::SmdTraceProvider::MarkTroublePageDisplayed::`vftable';
  SpeechMicDiagnostic::SmdTraceProvider::MarkTroublePageDisplayed::StartActivity((SpeechMicDiagnostic::SmdTraceProvider::MarkTroublePageDisplayed *)v17);
  hKey = 0;
  v2 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Speech_OneCore\\AudioInput\\MicWiz\\LastRun",
         0,
         0,
         0,
         0x20006u,
         0,
         &hKey,
         0);
  if ( v2 )
  {
    v4 = 157;
LABEL_15:
    v6 = wil::details::in1diag3::Return_Win32(retaddr, (void *)v4, v3, (const char *)v2, dwOptions);
    goto LABEL_21;
  }
  memset_0(Data, 0, sizeof(Data));
  SystemTime = 0;
  GetSystemTime(&SystemTime);
  dwOptionsa = SystemTime.wMonth;
  v5 = StringCchPrintfW(Data, 0x100u, L"%04d.%02d.%02d-%02d.%02d.%02d", SystemTime.wYear);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = (unsigned int)v5;
    v8 = 169;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\speechmicdiagnostic.cpp",
      (const char *)v7,
      dwOptionsa);
LABEL_21:
    if ( hKey )
      RegCloseKey(hKey);
LABEL_23:
    v17[0] = &SpeechMicDiagnostic::SmdTraceProvider::MarkTroublePageDisplayed::`vftable';
    wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v17);
    wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v17);
    return v6;
  }
  v9 = 128;
  v10 = (BYTE *)Data;
  do
  {
    if ( !*(_WORD *)v10 )
      break;
    v10 += 2;
    --v9;
  }
  while ( v9 );
  v6 = v9 == 0 ? 0x80070057 : 0;
  if ( !v9 )
  {
    v7 = v6;
    v8 = 172;
    goto LABEL_20;
  }
  v11 = *(const WCHAR **)(*((_QWORD *)this + 1) + 144LL);
  if ( !v11 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAF,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\speechmicdiagnostic.cpp",
      (const char *)0x80070057LL,
      dwOptionsa);
    if ( hKey )
      RegCloseKey(hKey);
    v6 = -2147024809;
    goto LABEL_23;
  }
  v2 = RegSetValueExW(hKey, v11, 0, 1u, (const BYTE *)Data, v9 != 0 ? 2 * (128 - v9) : 0);
  if ( v2 )
  {
    v4 = 178;
    goto LABEL_15;
  }
  if ( hKey )
    RegCloseKey(hKey);
  v17[0] = &SpeechMicDiagnostic::SmdTraceProvider::MarkTroublePageDisplayed::`vftable';
  wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v17);
  wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v17);
  return 0;
}

```

## disassembly

```asm
0x180008d10  mov     [rsp-8+arg_8], rbx
0x180008d15  mov     [rsp-8+arg_10], rsi
0x180008d1a  push    rbp
0x180008d1b  push    rdi
0x180008d1c  push    r15
0x180008d1e  lea     rbp, [rsp-2D0h]
0x180008d26  sub     rsp, 3D0h
0x180008d2d  mov     rax, cs:__security_cookie
0x180008d34  xor     rax, rsp
0x180008d37  mov     [rbp+2E0h+var_20], rax
0x180008d3e  mov     rdi, rcx
0x180008d41  lea     rdx, aMarktroublepag_0; "MarkTroublePageDisplayed"
0x180008d48  lea     rcx, [rsp+3E0h+var_370]
0x180008d4d  call    ??0?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180008d52  lea     r15, ??_7MarkTroublePageDisplayed@SmdTraceProvider@SpeechMicDiagnostic@@6B@; const SpeechMicDiagnostic::SmdTraceProvider::MarkTroublePageDisplayed::`vftable'
0x180008d59  mov     [rsp+3E0h+var_370], r15
0x180008d5e  lea     rcx, [rsp+3E0h+var_370]; this
0x180008d63  call    ?StartActivity@MarkTroublePageDisplayed@SmdTraceProvider@SpeechMicDiagnostic@@QEAAXXZ; SpeechMicDiagnostic::SmdTraceProvider::MarkTroublePageDisplayed::StartActivity(void)
0x180008d68  nop
0x180008d69  xor     esi, esi
0x180008d6b  mov     [rsp+3E0h+hKey], rsi
0x180008d70  mov     [rsp+3E0h+lpdwDisposition], rsi; lpdwDisposition
0x180008d75  lea     rax, [rsp+3E0h+hKey]
0x180008d7a  mov     [rsp+3E0h+phkResult], rax; phkResult
0x180008d7f  mov     [rsp+3E0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180008d84  mov     [rsp+3E0h+samDesired], 20006h; samDesired
0x180008d8c  mov     [rsp+3E0h+dwOptions], esi; dwOptions
0x180008d90  xor     r9d, r9d; lpClass
0x180008d93  xor     r8d, r8d; Reserved
0x180008d96  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Speech_OneCore\\Au"...
0x180008d9d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180008da4  call    cs:__imp_RegCreateKeyExW
0x180008dab  nop     dword ptr [rax+rax+00h]
0x180008db0  test    eax, eax
0x180008db2  jz      short loc_180008DBE
0x180008db4  mov     edx, 9Dh
0x180008db9  jmp     loc_180008F15
0x180008dbe  xor     edx, edx; Val
0x180008dc0  mov     r8d, 200h; Size
0x180008dc6  lea     rcx, [rbp+2E0h+Data]; void *
0x180008dcd  call    memset_0
0x180008dd2  xorps   xmm0, xmm0
0x180008dd5  movups  xmmword ptr [rsp+3E0h+SystemTime.wYear], xmm0
0x180008dda  lea     rcx, [rsp+3E0h+SystemTime]; lpSystemTime
0x180008ddf  call    cs:__imp_GetSystemTime
0x180008de6  nop     dword ptr [rax+rax+00h]
0x180008deb  movzx   eax, [rsp+3E0h+SystemTime.wSecond]
0x180008df0  movzx   ecx, [rsp+3E0h+SystemTime.wMinute]
0x180008df5  movzx   edx, [rsp+3E0h+SystemTime.wHour]
0x180008dfa  movzx   r8d, [rsp+3E0h+SystemTime.wDay]
0x180008e00  movzx   r10d, [rsp+3E0h+SystemTime.wMonth]
0x180008e06  movzx   r9d, [rsp+3E0h+SystemTime.wYear]
0x180008e0c  mov     dword ptr [rsp+3E0h+lpdwDisposition], eax
0x180008e10  mov     dword ptr [rsp+3E0h+phkResult], ecx
0x180008e14  mov     dword ptr [rsp+3E0h+lpSecurityAttributes], edx
0x180008e18  mov     [rsp+3E0h+samDesired], r8d
0x180008e1d  mov     [rsp+3E0h+dwOptions], r10d; int
0x180008e22  lea     r8, a04d02d02d02d02; "%04d.%02d.%02d-%02d.%02d.%02d"
0x180008e29  mov     edx, 100h; unsigned __int64
0x180008e2e  lea     rcx, [rbp+2E0h+Data]; unsigned __int16 *
0x180008e35  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008e3a  mov     ebx, eax
0x180008e3c  test    eax, eax
0x180008e3e  jns     short loc_180008E4D
0x180008e40  mov     r9d, eax
0x180008e43  mov     edx, 0A9h
0x180008e48  jmp     loc_180008F64
0x180008e4d  mov     edx, 80h
0x180008e52  mov     ecx, edx
0x180008e54  lea     rax, [rbp+2E0h+Data]
0x180008e5b  cmp     [rax], si
0x180008e5e  jz      short loc_180008E6A
0x180008e60  add     rax, 2
0x180008e64  sub     rcx, 1
0x180008e68  jnz     short loc_180008E5B
0x180008e6a  mov     rax, rcx
0x180008e6d  neg     rax
0x180008e70  sbb     ebx, ebx
0x180008e72  not     ebx
0x180008e74  and     ebx, 80070057h
0x180008e7a  test    rcx, rcx
0x180008e7d  jz      loc_180008F5C
0x180008e83  sub     rdx, rcx
0x180008e86  add     rdx, rdx
0x180008e89  neg     rcx
0x180008e8c  sbb     r8, r8
0x180008e8f  and     r8, rdx
0x180008e92  mov     rax, [rdi+8]
0x180008e96  mov     rdx, [rax+90h]; lpValueName
0x180008e9d  test    rdx, rdx
0x180008ea0  jnz     short loc_180008EE1
0x180008ea2  mov     rcx, [rbp+2E8h]; this
0x180008ea9  mov     r9d, 80070057h; char *
0x180008eaf  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x180008eb6  mov     edx, 0AFh; void *
0x180008ebb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008ec0  nop
0x180008ec1  mov     rcx, [rsp+3E0h+hKey]; hKey
0x180008ec6  test    rcx, rcx
0x180008ec9  jz      short loc_180008ED7
0x180008ecb  call    cs:__imp_RegCloseKey
0x180008ed2  nop     dword ptr [rax+rax+00h]
0x180008ed7  mov     ebx, 80070057h
0x180008edc  jmp     loc_180008F8F
0x180008ee1  mov     [rsp+3E0h+samDesired], r8d; cbData
0x180008ee6  lea     rax, [rbp+2E0h+Data]
0x180008eed  mov     qword ptr [rsp+3E0h+dwOptions], rax; unsigned int
0x180008ef2  mov     r9d, 1; dwType
0x180008ef8  xor     r8d, r8d; Reserved
0x180008efb  mov     rcx, [rsp+3E0h+hKey]; hKey
0x180008f00  call    cs:__imp_RegSetValueExW
0x180008f07  nop     dword ptr [rax+rax+00h]
0x180008f0c  test    eax, eax
0x180008f0e  jz      short loc_180008F28
0x180008f10  mov     edx, 0B2h; void *
0x180008f15  mov     r9d, eax; char *
0x180008f18  mov     rcx, [rbp+2E8h]; this
0x180008f1f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180008f24  mov     ebx, eax
0x180008f26  jmp     short loc_180008F78
0x180008f28  mov     rcx, [rsp+3E0h+hKey]; hKey
0x180008f2d  test    rcx, rcx
0x180008f30  jz      short loc_180008F3F
0x180008f32  call    cs:__imp_RegCloseKey
0x180008f39  nop     dword ptr [rax+rax+00h]
0x180008f3e  nop
0x180008f3f  mov     [rsp+3E0h+var_370], r15
0x180008f44  lea     rcx, [rsp+3E0h+var_370]
0x180008f49  call    ?Destroy@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180008f4e  lea     rcx, [rsp+3E0h+var_370]
0x180008f53  call    ??1?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180008f58  xor     eax, eax
0x180008f5a  jmp     short loc_180008FAA
0x180008f5c  mov     r9d, ebx; char *
0x180008f5f  mov     edx, 0ACh; void *
0x180008f64  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x180008f6b  mov     rcx, [rbp+2E8h]; this
0x180008f72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008f77  nop
0x180008f78  mov     rcx, [rsp+3E0h+hKey]; hKey
0x180008f7d  test    rcx, rcx
0x180008f80  jz      short loc_180008F8F
0x180008f82  call    cs:__imp_RegCloseKey
0x180008f89  nop     dword ptr [rax+rax+00h]
0x180008f8e  nop
0x180008f8f  mov     [rsp+3E0h+var_370], r15
0x180008f94  lea     rcx, [rsp+3E0h+var_370]
0x180008f99  call    ?Destroy@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180008f9e  lea     rcx, [rsp+3E0h+var_370]
0x180008fa3  call    ??1?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180008fa8  mov     eax, ebx
0x180008faa  mov     rcx, [rbp+2E0h+var_20]
0x180008fb1  xor     rcx, rsp; StackCookie
0x180008fb4  call    __security_check_cookie
0x180008fb9  lea     r11, [rsp+3E0h+var_10]
0x180008fc1  mov     rbx, [r11+28h]
0x180008fc5  mov     rsi, [r11+30h]
0x180008fc9  mov     rsp, r11
0x180008fcc  pop     r15
0x180008fce  pop     rdi
0x180008fcf  pop     rbp
0x180008fd0  retn
```
