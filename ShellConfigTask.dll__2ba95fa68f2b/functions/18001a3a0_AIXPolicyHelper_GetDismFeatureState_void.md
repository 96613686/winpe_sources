# AIXPolicyHelper::GetDismFeatureState(void)

- ea: `0x18001a3a0`
- end: `0x18001a515`
- name: `?GetDismFeatureState@AIXPolicyHelper@@YAKXZ`
- size: `373`
- prototype: `unsigned int __fastcall(AIXPolicyHelper *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001fd50`
- `0x18002d050`

## callees

- `0x18000163c`
- `0x180002590`
- `0x18000896c`
- `0x18000ab14`
- `0x18001a3a0`

## import_xrefs

- `DismApi!DismCloseSession` at `0x18001a4c1`
- `DismApi!DismCloseSession` at `0x18001a4c1`
- `DismApi!DismDelete` at `0x18001a4b4`
- `DismApi!DismDelete` at `0x18001a4b4`
- `DismApi!DismInitialize` at `0x18001a3f8`
- `DismApi!DismInitialize` at `0x18001a3f8`
- `DismApi!DismOpenSession` at `0x18001a436`
- `DismApi!DismOpenSession` at `0x18001a436`
- `DismApi!DismGetFeatureInfo` at `0x18001a47b`
- `DismApi!DismGetFeatureInfo` at `0x18001a47b`

## string_xrefs

- `0x18001a406`: `shellcommon\internal\shell\inc\AIXPolicyHelper.h`
- `0x18001a444`: `shellcommon\internal\shell\inc\AIXPolicyHelper.h`
- `0x18001a489`: `shellcommon\internal\shell\inc\AIXPolicyHelper.h`

## pseudocode

```c
__int64 __fastcall AIXPolicyHelper::GetDismFeatureState(AIXPolicyHelper *this)
{
  unsigned int v1; // ebx
  const struct _tlgProvider_t *v2; // rcx
  int v3; // eax
  int v4; // eax
  int FeatureInfo; // eax
  const struct _tlgProvider_t *v6; // rcx
  int v8; // [rsp+20h] [rbp-50h]
  unsigned int v9; // [rsp+30h] [rbp-40h] BYREF
  int v10[2]; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v11[32]; // [rsp+40h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  v1 = -1;
  v2 = AIXTelemetryLogging::Provider();
  if ( *(_DWORD *)v2 > 5u )
    tlgWriteTransfer_EventWriteTransfer(v2, &dword_180039B44, 0, 0, 2, v11);
  v3 = DismInitialize(2, 0, 0);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA1,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\AIXPolicyHelper.h",
      (const char *)(unsigned int)v3,
      v8);
    goto LABEL_15;
  }
  v9 = 0;
  v4 = DismOpenSession(L"DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF845}", 0, 0, &v9);
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA4,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\AIXPolicyHelper.h",
      (const char *)(unsigned int)v4,
      v8);
    goto LABEL_13;
  }
  *(_QWORD *)v10 = 0;
  FeatureInfo = DismGetFeatureInfo(v9, L"Recall", 0, 0);
  if ( FeatureInfo >= 0 )
  {
    if ( !*(_QWORD *)v10 )
      goto LABEL_13;
    v1 = *(_DWORD *)(*(_QWORD *)v10 + 8LL);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA7,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\AIXPolicyHelper.h",
      (const char *)(unsigned int)FeatureInfo,
      (int)v10);
    if ( !*(_QWORD *)v10 )
      goto LABEL_13;
  }
  DismDelete();
LABEL_13:
  if ( v9 )
    DismCloseSession();
LABEL_15:
  v6 = AIXTelemetryLogging::Provider();
  if ( *(_DWORD *)v6 > 5u )
    tlgWriteTransfer_EventWriteTransfer(v6, byte_180039B6D, 0, 0, 2, v11);
  return v1;
}

```

## disassembly

```asm
0x18001a3a0  mov     [rsp-8+arg_0], rbx
0x18001a3a5  push    rbp
0x18001a3a6  mov     rbp, rsp
0x18001a3a9  sub     rsp, 70h
0x18001a3ad  mov     rax, cs:__security_cookie
0x18001a3b4  xor     rax, rsp
0x18001a3b7  mov     [rbp+var_10], rax
0x18001a3bb  or      ebx, 0FFFFFFFFh
0x18001a3be  call    ?Provider@AIXTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; AIXTelemetryLogging::Provider(void)
0x18001a3c3  mov     rcx, rax
0x18001a3c6  mov     eax, [rax]
0x18001a3c8  cmp     eax, 5
0x18001a3cb  jbe     short loc_18001A3F0
0x18001a3cd  lea     rax, [rbp+var_30]
0x18001a3d1  xor     r9d, r9d
0x18001a3d4  mov     [rsp+70h+var_48], rax
0x18001a3d9  lea     rdx, dword_180039B44
0x18001a3e0  xor     r8d, r8d
0x18001a3e3  mov     [rsp+70h+var_50], 2; int
0x18001a3eb  call    _tlgWriteTransfer_EventWriteTransfer
0x18001a3f0  xor     edx, edx
0x18001a3f2  xor     r8d, r8d
0x18001a3f5  lea     ecx, [rdx+2]
0x18001a3f8  call    cs:__imp_DismInitialize
0x18001a3fe  test    eax, eax
0x18001a400  jns     short loc_18001A41F
0x18001a402  mov     rcx, [rbp+8]; this
0x18001a406  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\AIXP"...
0x18001a40d  mov     r9d, eax; char *
0x18001a410  mov     edx, 0A1h; void *
0x18001a415  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a41a  jmp     loc_18001A4C7
0x18001a41f  lea     r9, [rbp+var_40]
0x18001a423  mov     [rbp+var_40], 0
0x18001a42a  xor     r8d, r8d
0x18001a42d  lea     rcx, aDism53bfae52B1; "DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF"...
0x18001a434  xor     edx, edx
0x18001a436  call    cs:__imp_DismOpenSession
0x18001a43c  test    eax, eax
0x18001a43e  jns     short loc_18001A45A
0x18001a440  mov     rcx, [rbp+8]; this
0x18001a444  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\AIXP"...
0x18001a44b  mov     r9d, eax; char *
0x18001a44e  mov     edx, 0A4h; void *
0x18001a453  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a458  jmp     short loc_18001A4BA
0x18001a45a  mov     ecx, [rbp+var_40]
0x18001a45d  lea     rax, [rbp+var_38]
0x18001a461  xor     r9d, r9d
0x18001a464  mov     qword ptr [rsp+70h+var_50], rax; int
0x18001a469  xor     r8d, r8d
0x18001a46c  mov     qword ptr [rbp+var_38], 0
0x18001a474  lea     rdx, aRecall; "Recall"
0x18001a47b  call    cs:__imp_DismGetFeatureInfo
0x18001a481  test    eax, eax
0x18001a483  jns     short loc_18001A4A8
0x18001a485  mov     rcx, [rbp+8]; this
0x18001a489  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\AIXP"...
0x18001a490  mov     r9d, eax; char *
0x18001a493  mov     edx, 0A7h; void *
0x18001a498  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a49d  mov     rcx, qword ptr [rbp+var_38]
0x18001a4a1  test    rcx, rcx
0x18001a4a4  jz      short loc_18001A4BA
0x18001a4a6  jmp     short loc_18001A4B4
0x18001a4a8  mov     rcx, qword ptr [rbp+var_38]
0x18001a4ac  test    rcx, rcx
0x18001a4af  jz      short loc_18001A4BA
0x18001a4b1  mov     ebx, [rcx+8]
0x18001a4b4  call    cs:__imp_DismDelete
0x18001a4ba  mov     ecx, [rbp+var_40]
0x18001a4bd  test    ecx, ecx
0x18001a4bf  jz      short loc_18001A4C7
0x18001a4c1  call    cs:__imp_DismCloseSession
0x18001a4c7  call    ?Provider@AIXTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; AIXTelemetryLogging::Provider(void)
0x18001a4cc  mov     rcx, rax
0x18001a4cf  mov     eax, [rax]
0x18001a4d1  cmp     eax, 5
0x18001a4d4  jbe     short loc_18001A4F9
0x18001a4d6  lea     rax, [rbp+var_30]
0x18001a4da  xor     r9d, r9d
0x18001a4dd  mov     [rsp+70h+var_48], rax
0x18001a4e2  lea     rdx, byte_180039B6D
0x18001a4e9  xor     r8d, r8d
0x18001a4ec  mov     [rsp+70h+var_50], 2
0x18001a4f4  call    _tlgWriteTransfer_EventWriteTransfer
0x18001a4f9  mov     eax, ebx
0x18001a4fb  mov     rcx, [rbp+var_10]
0x18001a4ff  xor     rcx, rsp; StackCookie
0x18001a502  call    __security_check_cookie
0x18001a507  mov     rbx, [rsp+70h+arg_0]
0x18001a50f  add     rsp, 70h
0x18001a513  pop     rbp
0x18001a514  retn
```
