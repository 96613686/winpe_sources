# BfeChangeSourceNotifySink

- ea: `0x18002a720`
- end: `0x18002a9f1`
- name: `BfeChangeSourceNotifySink`
- size: `721`
- prototype: ``
- caller_count: `7`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002a270`
- `0x18002a350`
- `0x18002a400`
- `0x180067e30`
- `0x18006b6e0`
- `0x180072780`
- `0x180072c00`

## callees

- `0x18000dab0`
- `0x18000f1a8`
- `0x180010ad0`
- `0x180012950`
- `0x18002a720`
- `0x180058b30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002a9d7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002a9d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a81e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a81e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a838`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a838`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a861`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a861`
- `AUTHZ!AuthzAccessCheck` at `0x18002a7e1`
- `AUTHZ!AuthzAccessCheck` at `0x18002a7e1`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18002a795`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18002a795`

## string_xrefs

- `0x18002a8a4`: `BfeAccessCheckFromContext`
- `0x18002a877`: `AuthzAccessCheck`

## pseudocode

```c
void __fastcall BfeChangeSourceNotifySink(__int64 a1, __int64 a2, void *a3)
{
  AUTHZ_CLIENT_CONTEXT_HANDLE v6; // rbx
  __int64 v7; // rbx
  DWORD LastError; // eax
  int v9; // r8d
  signed int v10; // ebx
  _QWORD *v11; // rcx
  bool v12; // zf
  signed int v13; // [rsp+50h] [rbp-69h] BYREF
  int v14; // [rsp+58h] [rbp-61h] BYREF
  struct _AUTHZ_ACCESS_REPLY pReply; // [rsp+60h] [rbp-59h] BYREF
  DWORD AccessMask; // [rsp+80h] [rbp-39h] BYREF
  int v17; // [rsp+88h] [rbp-31h] BYREF
  struct _AUTHZ_ACCESS_REQUEST pRequest; // [rsp+90h] [rbp-29h] BYREF
  _BYTE v19[16]; // [rsp+B8h] [rbp-1h] BYREF
  const char *v20; // [rsp+C8h] [rbp+Fh]
  __int64 v21; // [rsp+D0h] [rbp+17h]
  signed int *v22; // [rsp+D8h] [rbp+1Fh]
  __int64 v23; // [rsp+E0h] [rbp+27h]

  if ( !a3 )
  {
LABEL_4:
    if ( !a2 || (*(_QWORD *)(a2 + 8) = *(_QWORD *)(a1 + 48), BfeNotifyOneWay(*(LPCRITICAL_SECTION *)(a1 + 40))) )
    {
      v7 = *(_QWORD *)(a1 + 40);
      EnterCriticalSection((LPCRITICAL_SECTION)v7);
      v12 = *(_DWORD *)(v7 + 84) == 0;
      *(_DWORD *)(v7 + 80) = 1;
      if ( v12 )
      {
        if ( SetEvent(*(HANDLE *)(v7 + 216)) )
          *(_DWORD *)(v7 + 84) = 1;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)v7);
    }
    return;
  }
  v6 = *(AUTHZ_CLIENT_CONTEXT_HANDLE *)(a1 + 56);
  AccessMask = 128;
  v14 = 5;
  v17 = 0;
  memset(&pRequest, 0, sizeof(pRequest));
  *(&pReply.ResultListLength + 1) = 0;
  pReply.SaclEvaluationResults = 0;
  MapGenericMask(&AccessMask, (PGENERIC_MAPPING)&GenericMapping);
  pRequest.DesiredAccess = AccessMask;
  pReply.GrantedAccessMask = (PACCESS_MASK)&v17;
  pReply.ResultListLength = 1;
  pReply.Error = (PDWORD)&v14;
  if ( AuthzAccessCheck(0, v6, &pRequest, 0, a3, 0, 0, &pReply, 0) )
  {
    if ( v14 )
      return;
    goto LABEL_4;
  }
  LastError = GetLastError();
  v10 = LastError;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_SsD(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, v9, 0, (__int64)"AuthzAccessCheck", LastError);
    v11 = WPP_GLOBAL_Control;
  }
  if ( MEMORY[0x1800EF078] && (qword_1800F2668[337] & 0x10000000000LL) != 0 )
  {
    v13 = v10;
    v22 = &v13;
    v20 = "AuthzAccessCheck";
    v21 = 17;
    v23 = 4;
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
      (unsigned int)WFP_USERMODE_ERROR,
      v9,
      3,
      (__int64)v19);
    v11 = WPP_GLOBAL_Control;
  }
  v12 = v10 == 0;
  if ( v10 > 0 )
  {
    v10 = (unsigned __int16)v10 | 0x80070000;
    v12 = v10 == 0;
  }
  if ( !v12 )
  {
    if ( v11 != &WPP_GLOBAL_Control && *((_BYTE *)v11 + 25) >= 2u && (*((_BYTE *)v11 + 28) & 1) != 0 )
      WPP_SF_Ssd(v11[2], 26, v9, 0, (__int64)"BfeAccessCheckFromContext", v10);
    if ( MEMORY[0x1800EF078] && (qword_1800F2668[337] & 0x10000000000LL) != 0 )
    {
      v13 = v10;
      v22 = &v13;
      v20 = "BfeAccessCheckFromContext";
      v21 = 26;
      v23 = 4;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
        (unsigned int)WFP_USERMODE_ERROR,
        v9,
        3,
        (__int64)v19);
    }
  }
}

```

## disassembly

```asm
0x18002a720  mov     [rsp-8+arg_18], rbx
0x18002a725  push    rbp
0x18002a726  push    rsi
0x18002a727  push    rdi
0x18002a728  push    r14
0x18002a72a  push    r15
0x18002a72c  lea     rbp, [rsp-37h]
0x18002a731  sub     rsp, 0F0h
0x18002a738  mov     rax, cs:__security_cookie
0x18002a73f  xor     rax, rsp
0x18002a742  mov     [rbp+57h+var_28], rax
0x18002a746  mov     rsi, r8
0x18002a749  mov     r14, rdx
0x18002a74c  mov     rdi, rcx
0x18002a74f  test    r8, r8
0x18002a752  jz      loc_18002A7F9
0x18002a758  mov     rbx, [rcx+38h]
0x18002a75c  lea     rdx, GenericMapping; GenericMapping
0x18002a763  xorps   xmm0, xmm0
0x18002a766  mov     [rbp+57h+AccessMask], 80h
0x18002a76d  xor     eax, eax
0x18002a76f  mov     [rbp+57h+var_B8], 5
0x18002a776  xor     r15d, r15d
0x18002a779  mov     [rbp+57h+pRequest.OptionalArguments], rax
0x18002a77d  lea     rcx, [rbp+57h+AccessMask]; AccessMask
0x18002a781  mov     [rbp+57h+var_88], r15d
0x18002a785  movups  xmmword ptr [rbp+57h+pRequest.DesiredAccess], xmm0
0x18002a789  movups  xmmword ptr [rbp+57h+pRequest.ObjectTypeList], xmm0
0x18002a78d  movups  xmmword ptr [rbp+57h+var_B0.ResultListLength], xmm0
0x18002a791  movups  xmmword ptr [rbp+57h+var_B0.SaclEvaluationResults], xmm0
0x18002a795  call    cs:__imp_MapGenericMask
0x18002a79b  mov     eax, [rbp+57h+AccessMask]
0x18002a79e  lea     r8, [rbp+57h+pRequest]; pRequest
0x18002a7a2  mov     [rbp+57h+pRequest.DesiredAccess], eax
0x18002a7a5  xor     r9d, r9d; hAuditEvent
0x18002a7a8  mov     [rsp+110h+phAccessCheckResults], r15; phAccessCheckResults
0x18002a7ad  lea     rax, [rbp+57h+var_88]
0x18002a7b1  mov     [rbp+57h+var_B0.GrantedAccessMask], rax
0x18002a7b5  mov     rdx, rbx; hAuthzClientContext
0x18002a7b8  lea     rax, [rbp+57h+var_B8]
0x18002a7bc  mov     [rbp+57h+var_B0.ResultListLength], 1
0x18002a7c3  mov     [rbp+57h+var_B0.Error], rax
0x18002a7c7  xor     ecx, ecx; Flags
0x18002a7c9  lea     rax, [rbp+57h+var_B0]
0x18002a7cd  mov     [rsp+110h+pReply], rax; pReply
0x18002a7d2  mov     [rsp+110h+OptionalSecurityDescriptorCount], r15d; OptionalSecurityDescriptorCount
0x18002a7d7  mov     [rsp+110h+OptionalSecurityDescriptorArray], r15; OptionalSecurityDescriptorArray
0x18002a7dc  mov     [rsp+110h+pSecurityDescriptor], rsi; pSecurityDescriptor
0x18002a7e1  call    cs:__imp_AuthzAccessCheck
0x18002a7e7  test    eax, eax
0x18002a7e9  jz      short loc_18002A861
0x18002a7eb  cmp     [rbp+57h+var_B8], r15d
0x18002a7ef  mov     eax, r15d
0x18002a7f2  setz    al
0x18002a7f5  test    eax, eax
0x18002a7f7  jz      short loc_18002A83E
0x18002a7f9  test    r14, r14
0x18002a7fc  jz      short loc_18002A817
0x18002a7fe  mov     rax, [rdi+30h]
0x18002a802  mov     rdx, r14
0x18002a805  mov     [r14+8], rax
0x18002a809  mov     rcx, [rdi+28h]; lpCriticalSection
0x18002a80d  call    BfeNotifyOneWay
0x18002a812  test    rax, rax
0x18002a815  jz      short loc_18002A83E
0x18002a817  mov     rbx, [rdi+28h]
0x18002a81b  mov     rcx, rbx; lpCriticalSection
0x18002a81e  call    cs:__imp_EnterCriticalSection
0x18002a824  cmp     dword ptr [rbx+54h], 0
0x18002a828  mov     dword ptr [rbx+50h], 1
0x18002a82f  jz      loc_18002A9D0
0x18002a835  mov     rcx, rbx; lpCriticalSection
0x18002a838  call    cs:__imp_LeaveCriticalSection
0x18002a83e  mov     rcx, [rbp+57h+var_28]
0x18002a842  xor     rcx, rsp; StackCookie
0x18002a845  call    __security_check_cookie
0x18002a84a  mov     rbx, [rsp+110h+arg_18]
0x18002a852  add     rsp, 0F0h
0x18002a859  pop     r15
0x18002a85b  pop     r14
0x18002a85d  pop     rdi
0x18002a85e  pop     rsi
0x18002a85f  pop     rbp
0x18002a860  retn
0x18002a861  call    cs:__imp_GetLastError
0x18002a867  mov     ebx, eax
0x18002a869  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a870  lea     rdi, WPP_GLOBAL_Control
0x18002a877  lea     rsi, aAuthzaccessche; "AuthzAccessCheck"
0x18002a87e  cmp     rcx, rdi
0x18002a881  jz      short loc_18002A88D
0x18002a883  cmp     byte ptr [rcx+19h], 2
0x18002a887  jnb     loc_18002A936
0x18002a88d  cmp     cs:1800EF078h, r15d
0x18002a894  jnz     loc_18002A966
0x18002a89a  test    ebx, ebx
0x18002a89c  jg      loc_18002A9C0
0x18002a8a2  jz      short loc_18002A83E
0x18002a8a4  lea     rsi, aBfeaccesscheck_0; "BfeAccessCheckFromContext"
0x18002a8ab  cmp     rcx, rdi
0x18002a8ae  jz      short loc_18002A8D6
0x18002a8b0  cmp     byte ptr [rcx+19h], 2
0x18002a8b4  jb      short loc_18002A8D6
0x18002a8b6  test    byte ptr [rcx+1Ch], 1
0x18002a8ba  jz      short loc_18002A8D6
0x18002a8bc  mov     rcx, [rcx+10h]
0x18002a8c0  mov     edx, 1Ah
0x18002a8c5  mov     dword ptr [rsp+110h+OptionalSecurityDescriptorArray], ebx
0x18002a8c9  xor     r9d, r9d
0x18002a8cc  mov     [rsp+110h+pSecurityDescriptor], rsi
0x18002a8d1  call    WPP_SF_Ssd
0x18002a8d6  cmp     cs:1800EF078h, r15d
0x18002a8dd  jz      loc_18002A83E
0x18002a8e3  test    byte ptr cs:qword_1800F2668+0A8Dh, 1
0x18002a8ea  jz      loc_18002A83E
0x18002a8f0  lea     rax, [rbp+57h+var_C0]
0x18002a8f4  mov     [rbp+57h+var_C0], ebx
0x18002a8f7  mov     [rbp+57h+var_38], rax
0x18002a8fb  lea     rdx, WFP_USERMODE_ERROR
0x18002a902  lea     rax, [rbp+57h+var_58]
0x18002a906  mov     [rbp+57h+var_48], rsi
0x18002a90a  mov     r9d, 3
0x18002a910  mov     [rsp+110h+pSecurityDescriptor], rax
0x18002a915  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x18002a91c  mov     [rbp+57h+var_40], 1Ah
0x18002a924  mov     [rbp+57h+var_30], 4
0x18002a92c  call    McGenEventWrite_EtwEventWriteTransfer
0x18002a931  jmp     loc_18002A83E
0x18002a936  test    byte ptr [rcx+1Ch], 1
0x18002a93a  jz      loc_18002A88D
0x18002a940  mov     rcx, [rcx+10h]
0x18002a944  mov     edx, 17h
0x18002a949  mov     dword ptr [rsp+110h+OptionalSecurityDescriptorArray], ebx
0x18002a94d  xor     r9d, r9d
0x18002a950  mov     [rsp+110h+pSecurityDescriptor], rsi
0x18002a955  call    WPP_SF_SsD
0x18002a95a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a961  jmp     loc_18002A88D
0x18002a966  test    byte ptr cs:qword_1800F2668+0A8Dh, 1
0x18002a96d  jz      loc_18002A89A
0x18002a973  lea     rax, [rbp+57h+var_C0]
0x18002a977  mov     [rbp+57h+var_C0], ebx
0x18002a97a  mov     [rbp+57h+var_38], rax
0x18002a97e  lea     rdx, WFP_USERMODE_ERROR
0x18002a985  lea     rax, [rbp+57h+var_58]
0x18002a989  mov     [rbp+57h+var_48], rsi
0x18002a98d  mov     r9d, 3
0x18002a993  mov     [rsp+110h+pSecurityDescriptor], rax
0x18002a998  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x18002a99f  mov     [rbp+57h+var_40], 11h
0x18002a9a7  mov     [rbp+57h+var_30], 4
0x18002a9af  call    McGenEventWrite_EtwEventWriteTransfer
0x18002a9b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a9bb  jmp     loc_18002A89A
0x18002a9c0  movzx   ebx, bx
0x18002a9c3  or      ebx, 80070000h
0x18002a9c9  test    ebx, ebx
0x18002a9cb  jmp     loc_18002A8A2
0x18002a9d0  mov     rcx, [rbx+0D8h]; hEvent
0x18002a9d7  call    cs:__imp_SetEvent
0x18002a9dd  test    eax, eax
0x18002a9df  jz      loc_18002A835
0x18002a9e5  mov     dword ptr [rbx+54h], 1
0x18002a9ec  jmp     loc_18002A835
```
