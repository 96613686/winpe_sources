# CApplicationManager::OnScreenReaderStateChanged(CProcess *,int,int)

- ea: `0x18003c6c0`
- end: `0x18003c87a`
- name: `?OnScreenReaderStateChanged@CApplicationManager@@QEAAJPEAVCProcess@@HH@Z`
- size: `442`
- prototype: `int(CApplicationManager *__hidden this, struct CProcess *, int, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x180040720`

## callees

- `0x18000a384`
- `0x18000c878`
- `0x180015fe0`
- `0x18001c9f0`
- `0x18001d0b0`
- `0x180027f10`
- `0x18002f5c4`
- `0x180031960`
- `0x180038620`
- `0x18003c6c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c6fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c6fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c808`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c856`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c808`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c856`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CApplicationManager::OnScreenReaderStateChanged(
        CApplicationManager *this,
        struct CProcess *a2,
        int a3,
        int a4)
{
  CApplicationManager *v7; // r15
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  const struct _tlgProvider_t *v9; // rax
  __int64 v10; // r8
  __int64 v11; // r10
  int v12; // eax
  float v13; // xmm0_4
  int v14; // eax
  unsigned int v15; // esi
  int v17; // [rsp+20h] [rbp-79h]
  int v18; // [rsp+30h] [rbp-69h] BYREF
  int v19; // [rsp+34h] [rbp-65h] BYREF
  int v20; // [rsp+38h] [rbp-61h] BYREF
  int v21; // [rsp+3Ch] [rbp-5Dh] BYREF
  struct _RTL_CRITICAL_SECTION *v22; // [rsp+40h] [rbp-59h]
  struct _EVENT_DATA_DESCRIPTOR v23; // [rsp+50h] [rbp-49h] BYREF
  int *v24; // [rsp+70h] [rbp-29h]
  __int64 v25; // [rsp+78h] [rbp-21h]
  int *v26; // [rsp+80h] [rbp-19h]
  __int64 v27; // [rsp+88h] [rbp-11h]
  int *v28; // [rsp+90h] [rbp-9h]
  __int64 v29; // [rsp+98h] [rbp-1h]
  int *v30; // [rsp+A0h] [rbp+7h]
  __int64 v31; // [rsp+A8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v7 = g_ApplicationManager;
  v8 = (struct _RTL_CRITICAL_SECTION *)((char *)g_ApplicationManager + 32);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_ApplicationManager + 32));
  v22 = v8;
  v9 = AudioSrvPolicyManagerTelemetryProvider::Provider();
  if ( *(_DWORD *)v9 > 4u && (unsigned __int8)tlgKeywordOn(v9, 0x8000) )
  {
    v19 = a4;
    v18 = *((_DWORD *)a2 + 41);
    v20 = *((_DWORD *)a2 + 40);
    v21 = a3;
    v30 = &v19;
    v31 = v10;
    v28 = &v18;
    v29 = v10;
    v26 = &v20;
    v27 = v10;
    v24 = &v21;
    v25 = v10;
    tlgWriteTransfer_EventWriteTransfer(v11, (unsigned __int8 *)byte_180057AA9, 0, 0, 6u, &v23);
  }
  v12 = 0;
  if ( a4 <= 0 )
    v12 = a4;
  if ( v12 <= -24 )
    v12 = -24;
  v18 = 0;
  v13 = ConvertDbToEngineVolume((float)v12);
  v14 = TsSessionIdScreenReaderStateChanged(*((_DWORD *)a2 + 41), *((_DWORD *)a2 + 40), a3, v13, &v18);
  v15 = v14;
  if ( v14 >= 0 )
  {
    v19 = 0;
    CProcess::ApplyStreamClassPolicyGains(a2, a3 == 0, &v19);
    if ( v18 || v19 )
      CApplicationManager::UpdateVolumeForAllAppsInSession((__int64)v7, *((_DWORD *)a2 + 41), 3);
    if ( v8 )
      LeaveCriticalSection(v8);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAE3,
      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\applicationmanager.cpp",
      (const char *)(unsigned int)v14,
      v17);
    if ( v8 )
      LeaveCriticalSection(v8);
    return v15;
  }
}

```

## disassembly

```asm
0x18003c6c0  push    rbp
0x18003c6c2  push    rbx
0x18003c6c3  push    rsi
0x18003c6c4  push    rdi
0x18003c6c5  push    r14
0x18003c6c7  push    r15
0x18003c6c9  lea     rbp, [rsp-2Fh]
0x18003c6ce  sub     rsp, 0C8h
0x18003c6d5  mov     rax, cs:__security_cookie
0x18003c6dc  xor     rax, rsp
0x18003c6df  mov     [rbp+57h+var_40], rax
0x18003c6e3  mov     esi, r9d
0x18003c6e6  mov     r14d, r8d
0x18003c6e9  mov     rdi, rdx
0x18003c6ec  mov     r15, cs:?g_ApplicationManager@@3PEAVCApplicationManager@@EA; CApplicationManager * g_ApplicationManager
0x18003c6f3  lea     rbx, [r15+20h]
0x18003c6f7  mov     rcx, rbx; lpCriticalSection
0x18003c6fa  call    cs:__imp_EnterCriticalSection
0x18003c700  mov     [rbp+57h+var_B0], rbx
0x18003c704  call    ?Provider@AudioSrvPolicyManagerTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioSrvPolicyManagerTelemetryProvider::Provider(void)
0x18003c709  mov     r10, rax
0x18003c70c  mov     ecx, [rax]
0x18003c70e  mov     r8d, 4
0x18003c714  cmp     ecx, r8d
0x18003c717  jbe     loc_18003C79D
0x18003c71d  mov     edx, 8000h
0x18003c722  mov     rcx, rax
0x18003c725  call    _tlgKeywordOn
0x18003c72a  test    al, al
0x18003c72c  jz      short loc_18003C79D
0x18003c72e  mov     [rbp+57h+var_BC], esi
0x18003c731  mov     eax, [rdi+0A4h]
0x18003c737  mov     [rbp+57h+var_C0], eax
0x18003c73a  mov     eax, [rdi+0A0h]
0x18003c740  mov     [rbp+57h+var_B8], eax
0x18003c743  mov     [rbp+57h+var_B4], r14d
0x18003c747  lea     rax, [rbp+57h+var_BC]
0x18003c74b  mov     [rbp+57h+var_50], rax
0x18003c74f  mov     [rbp+57h+var_48], r8
0x18003c753  lea     rax, [rbp+57h+var_C0]
0x18003c757  mov     [rbp+57h+var_60], rax
0x18003c75b  mov     [rbp+57h+var_58], r8
0x18003c75f  lea     rax, [rbp+57h+var_B8]
0x18003c763  mov     [rbp+57h+var_70], rax
0x18003c767  mov     [rbp+57h+var_68], r8
0x18003c76b  lea     rax, [rbp+57h+var_B4]
0x18003c76f  mov     [rbp+57h+var_80], rax
0x18003c773  mov     [rbp+57h+var_78], r8
0x18003c777  lea     rax, [rbp+57h+var_A0]
0x18003c77b  mov     [rsp+0F0h+var_C8], rax
0x18003c780  mov     dword ptr [rsp+0F0h+var_D0], 6
0x18003c788  xor     r9d, r9d
0x18003c78b  xor     r8d, r8d
0x18003c78e  lea     rdx, byte_180057AA9
0x18003c795  mov     rcx, r10
0x18003c798  call    _tlgWriteTransfer_EventWriteTransfer
0x18003c79d  xor     eax, eax
0x18003c79f  test    esi, esi
0x18003c7a1  cmovle  eax, esi
0x18003c7a4  mov     ecx, 0FFFFFFE8h
0x18003c7a9  cmp     eax, ecx
0x18003c7ab  cmovle  eax, ecx
0x18003c7ae  mov     [rbp+57h+var_C0], 0
0x18003c7b5  movd    xmm0, eax
0x18003c7b9  cvtdq2ps xmm0, xmm0; float
0x18003c7bc  call    ?ConvertDbToEngineVolume@@YAMM@Z; ConvertDbToEngineVolume(float)
0x18003c7c1  movaps  xmm3, xmm0; float
0x18003c7c4  lea     rax, [rbp+57h+var_C0]
0x18003c7c8  mov     [rsp+0F0h+var_D0], rax; int
0x18003c7cd  mov     r8d, r14d; int
0x18003c7d0  mov     edx, [rdi+0A0h]; unsigned int
0x18003c7d6  mov     ecx, [rdi+0A4h]; unsigned int
0x18003c7dc  call    ?TsSessionIdScreenReaderStateChanged@@YAJKKHMPEAH@Z; TsSessionIdScreenReaderStateChanged(ulong,ulong,int,float,int *)
0x18003c7e1  mov     esi, eax
0x18003c7e3  test    eax, eax
0x18003c7e5  jns     short loc_18003C812
0x18003c7e7  mov     rcx, [rbp+5Fh]; this
0x18003c7eb  mov     r9d, eax; char *
0x18003c7ee  lea     r8, aClientcoreMult_5; "clientcore\\multimedia\\audiocore\\serv"...
0x18003c7f5  mov     edx, 0AE3h; void *
0x18003c7fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c7ff  nop
0x18003c800  test    rbx, rbx
0x18003c803  jz      short loc_18003C80E
0x18003c805  mov     rcx, rbx; lpCriticalSection
0x18003c808  call    cs:__imp_LeaveCriticalSection
0x18003c80e  mov     eax, esi
0x18003c810  jmp     short loc_18003C85E
0x18003c812  mov     [rbp+57h+var_BC], 0
0x18003c819  xor     edx, edx
0x18003c81b  test    r14d, r14d
0x18003c81e  setz    dl; int
0x18003c821  lea     r8, [rbp+57h+var_BC]; int *
0x18003c825  mov     rcx, rdi; this
0x18003c828  call    ?ApplyStreamClassPolicyGains@CProcess@@UEAAXHPEAH@Z; CProcess::ApplyStreamClassPolicyGains(int,int *)
0x18003c82d  cmp     [rbp+57h+var_C0], 0
0x18003c831  jnz     short loc_18003C839
0x18003c833  cmp     [rbp+57h+var_BC], 0
0x18003c837  jz      short loc_18003C84E
0x18003c839  mov     r8d, 3
0x18003c83f  mov     edx, [rdi+0A4h]
0x18003c845  mov     rcx, r15
0x18003c848  call    ?UpdateVolumeForAllAppsInSession@CApplicationManager@@QEAAJKW4AudioVolumeChangeType@@@Z; CApplicationManager::UpdateVolumeForAllAppsInSession(ulong,AudioVolumeChangeType)
0x18003c84d  nop
0x18003c84e  test    rbx, rbx
0x18003c851  jz      short loc_18003C85C
0x18003c853  mov     rcx, rbx; lpCriticalSection
0x18003c856  call    cs:__imp_LeaveCriticalSection
0x18003c85c  xor     eax, eax
0x18003c85e  mov     rcx, [rbp+57h+var_40]
0x18003c862  xor     rcx, rsp; StackCookie
0x18003c865  call    __security_check_cookie
0x18003c86a  add     rsp, 0C8h
0x18003c871  pop     r15
0x18003c873  pop     r14
0x18003c875  pop     rdi
0x18003c876  pop     rsi
0x18003c877  pop     rbx
0x18003c878  pop     rbp
0x18003c879  retn
```
