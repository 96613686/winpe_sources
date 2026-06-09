# NfcNamedEventUtils::CreateNamedEvent(void *,ushort const *,_GUID *,void * *)

- ea: `0x18007a29c`
- end: `0x18007a441`
- name: `?CreateNamedEvent@NfcNamedEventUtils@@SAJPEAXPEBGPEAU_GUID@@PEAPEAX@Z`
- size: `421`
- prototype: `static int(void *, const unsigned __int16 *, struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180070440`
- `0x180083308`
- `0x1800835b8`

## callees

- `0x1800049a0`
- `0x18000a0f8`
- `0x18000c964`
- `0x180065a0c`
- `0x18007a23c`
- `0x18007a29c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18007a3be`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18007a3be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a3cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a3cc`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18007a387`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18007a3e8`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18007a437`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18007a387`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18007a3e8`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18007a437`
- `api-ms-win-security-accesshlpr-l1-1-0!BuildSecurityDescriptorForSharingAccess` at `0x18007a359`
- `api-ms-win-security-accesshlpr-l1-1-0!BuildSecurityDescriptorForSharingAccess` at `0x18007a359`
- `bcrypt!BCryptGenRandom` at `0x18007a2e2`
- `bcrypt!BCryptGenRandom` at `0x18007a2e2`

## string_xrefs

- `0x18007a2f0`: `onecoreuap\ds\nfc\shared\nfccommon\lib\nfcnamedeventutils.cpp`
- `0x18007a325`: `onecoreuap\ds\nfc\shared\nfccommon\lib\nfcnamedeventutils.cpp`
- `0x18007a367`: `onecoreuap\ds\nfc\shared\nfccommon\lib\nfcnamedeventutils.cpp`
- `0x18007a41b`: `onecoreuap\ds\nfc\shared\nfccommon\lib\nfcnamedeventutils.cpp`

## pseudocode

```c
int __fastcall NfcNamedEventUtils::CreateNamedEvent(void *a1, const unsigned __int16 *a2, struct _GUID *a3, void **a4)
{
  NTSTATUS v8; // eax
  bool v9; // cl
  int EventName; // eax
  int v12; // ebx
  int v13; // eax
  wil::details *v14; // rcx
  HANDLE v15; // rbx
  void *v16; // rcx
  int LastErrorFailHr; // eax
  int v18; // edi
  unsigned __int64 v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  void *v21; // [rsp+30h] [rbp-D0h] BYREF
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+38h] [rbp-C8h] BYREF
  UCHAR pbBuffer[16]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Name[96]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  *(_OWORD *)pbBuffer = 0;
  v8 = BCryptGenRandom(0, pbBuffer, 0x10u, 2u);
  if ( v8 < 0 )
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x24,
             (unsigned int)"onecoreuap\\ds\\nfc\\shared\\nfccommon\\lib\\nfcnamedeventutils.cpp",
             (const char *)(unsigned int)v8,
             v19);
  EventName = NfcNamedEventUtils::CreateEventName(v9, a2, (const struct _GUID *)pbBuffer, Name, v19);
  v12 = EventName;
  if ( EventName < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C,
      (unsigned int)"onecoreuap\\ds\\nfc\\shared\\nfccommon\\lib\\nfcnamedeventutils.cpp",
      (const char *)(unsigned int)EventName,
      v20);
    return v12;
  }
  v21 = 0;
  v13 = BuildSecurityDescriptorForSharingAccess(a1, 0, 0x100000, &v21);
  if ( v13 < 0 )
  {
    v12 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x37,
            (unsigned int)"onecoreuap\\ds\\nfc\\shared\\nfccommon\\lib\\nfcnamedeventutils.cpp",
            (const char *)(unsigned int)v13,
            v20);
    if ( v21 )
      FreeTransientObjectSecurityDescriptor(v21);
    return v12;
  }
  EventAttributes.lpSecurityDescriptor = v21;
  *(_QWORD *)&EventAttributes.nLength = 24;
  *(_QWORD *)&EventAttributes.bInheritHandle = 0;
  v15 = CreateEventExW(&EventAttributes, Name, 0, 0x1F0003u);
  if ( v15 )
  {
    GetLastError();
LABEL_11:
    v16 = v21;
    *a3 = *(struct _GUID *)pbBuffer;
    *a4 = v15;
    if ( v16 )
      FreeTransientObjectSecurityDescriptor(v16);
    return 0;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v14);
  v15 = 0;
  v18 = LastErrorFailHr;
  if ( LastErrorFailHr >= 0 )
    goto LABEL_11;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x40,
    (unsigned int)"onecoreuap\\ds\\nfc\\shared\\nfccommon\\lib\\nfcnamedeventutils.cpp",
    (const char *)(unsigned int)LastErrorFailHr,
    v20);
  if ( v21 )
    FreeTransientObjectSecurityDescriptor(v21);
  return v18;
}

```

## disassembly

```asm
0x18007a29c  push    rbp
0x18007a29e  push    rbx
0x18007a29f  push    rsi
0x18007a2a0  push    rdi
0x18007a2a1  push    r14
0x18007a2a3  lea     rbp, [rsp-30h]
0x18007a2a8  sub     rsp, 130h
0x18007a2af  mov     rax, cs:__security_cookie
0x18007a2b6  xor     rax, rsp
0x18007a2b9  mov     [rbp+50h+var_30], rax
0x18007a2bd  mov     r14, r9
0x18007a2c0  mov     rsi, r8
0x18007a2c3  mov     r9d, 2; dwFlags
0x18007a2c9  mov     rbx, rdx
0x18007a2cc  mov     rdi, rcx
0x18007a2cf  lea     rdx, [rsp+150h+pbBuffer]; pbBuffer
0x18007a2d4  xorps   xmm0, xmm0
0x18007a2d7  xor     ecx, ecx; hAlgorithm
0x18007a2d9  movups  xmmword ptr [rsp+150h+pbBuffer], xmm0
0x18007a2de  lea     r8d, [r9+0Eh]; cbBuffer
0x18007a2e2  call    cs:__imp_BCryptGenRandom
0x18007a2e8  test    eax, eax
0x18007a2ea  jns     short loc_18007A309
0x18007a2ec  mov     rcx, [rbp+58h]; this
0x18007a2f0  lea     r8, aOnecoreuapDsNf_20; "onecoreuap\\ds\\nfc\\shared\\nfccommon"...
0x18007a2f7  mov     r9d, eax; char *
0x18007a2fa  mov     edx, 24h ; '$'; void *
0x18007a2ff  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18007a304  jmp     loc_18007A3F0
0x18007a309  lea     r9, [rsp+150h+Name]; unsigned __int16 *
0x18007a30e  mov     rdx, rbx; unsigned __int16 *
0x18007a311  lea     r8, [rsp+150h+pbBuffer]; struct _GUID *
0x18007a316  call    ?CreateEventName@NfcNamedEventUtils@@CAJ_NPEBGAEBU_GUID@@PEAG_K@Z; NfcNamedEventUtils::CreateEventName(bool,ushort const *,_GUID const &,ushort *,unsigned __int64)
0x18007a31b  mov     ebx, eax
0x18007a31d  test    eax, eax
0x18007a31f  jns     short loc_18007A340
0x18007a321  mov     rcx, [rbp+58h]; this
0x18007a325  lea     r8, aOnecoreuapDsNf_20; "onecoreuap\\ds\\nfc\\shared\\nfccommon"...
0x18007a32c  mov     r9d, eax; char *
0x18007a32f  mov     edx, 2Ch ; ','; void *
0x18007a334  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a339  mov     eax, ebx
0x18007a33b  jmp     loc_18007A3F0
0x18007a340  lea     r9, [rsp+150h+var_120]
0x18007a345  mov     [rsp+150h+var_120], 0
0x18007a34e  xor     edx, edx
0x18007a350  mov     r8d, 100000h
0x18007a356  mov     rcx, rdi
0x18007a359  call    cs:__imp_BuildSecurityDescriptorForSharingAccess
0x18007a35f  test    eax, eax
0x18007a361  jns     short loc_18007A38F
0x18007a363  mov     rcx, [rbp+58h]; this
0x18007a367  lea     r8, aOnecoreuapDsNf_20; "onecoreuap\\ds\\nfc\\shared\\nfccommon"...
0x18007a36e  mov     r9d, eax; char *
0x18007a371  mov     edx, 37h ; '7'; void *
0x18007a376  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18007a37b  mov     rcx, [rsp+150h+var_120]
0x18007a380  mov     ebx, eax
0x18007a382  test    rcx, rcx
0x18007a385  jz      short loc_18007A339
0x18007a387  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18007a38d  jmp     short loc_18007A339
0x18007a38f  mov     rax, [rsp+150h+var_120]
0x18007a394  lea     rdx, [rsp+150h+Name]; lpName
0x18007a399  mov     r9d, 1F0003h; dwDesiredAccess
0x18007a39f  mov     [rsp+150h+EventAttributes.lpSecurityDescriptor], rax
0x18007a3a4  xor     r8d, r8d; dwFlags
0x18007a3a7  mov     qword ptr [rsp+150h+EventAttributes.nLength], 18h
0x18007a3b0  lea     rcx, [rsp+150h+EventAttributes]; lpEventAttributes
0x18007a3b5  mov     qword ptr [rsp+150h+EventAttributes.bInheritHandle], 0
0x18007a3be  call    cs:__imp_CreateEventExW
0x18007a3c4  mov     rbx, rax
0x18007a3c7  test    rax, rax
0x18007a3ca  jz      short loc_18007A40A
0x18007a3cc  call    cs:__imp_GetLastError
0x18007a3d2  movups  xmm0, xmmword ptr [rsp+150h+pbBuffer]
0x18007a3d7  mov     rcx, [rsp+150h+var_120]
0x18007a3dc  movdqu  xmmword ptr [rsi], xmm0
0x18007a3e0  mov     [r14], rbx
0x18007a3e3  test    rcx, rcx
0x18007a3e6  jz      short loc_18007A3EE
0x18007a3e8  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18007a3ee  xor     eax, eax
0x18007a3f0  mov     rcx, [rbp+50h+var_30]
0x18007a3f4  xor     rcx, rsp; StackCookie
0x18007a3f7  call    __security_check_cookie
0x18007a3fc  add     rsp, 130h
0x18007a403  pop     r14
0x18007a405  pop     rdi
0x18007a406  pop     rsi
0x18007a407  pop     rbx
0x18007a408  pop     rbp
0x18007a409  retn
0x18007a40a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18007a40f  xor     ebx, ebx
0x18007a411  mov     edi, eax
0x18007a413  test    eax, eax
0x18007a415  jns     short loc_18007A3D2
0x18007a417  mov     rcx, [rbp+58h]; this
0x18007a41b  lea     r8, aOnecoreuapDsNf_20; "onecoreuap\\ds\\nfc\\shared\\nfccommon"...
0x18007a422  mov     r9d, eax; char *
0x18007a425  lea     edx, [rbx+40h]; void *
0x18007a428  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a42d  mov     rcx, [rsp+150h+var_120]
0x18007a432  test    rcx, rcx
0x18007a435  jz      short loc_18007A43D
0x18007a437  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18007a43d  mov     eax, edi
0x18007a43f  jmp     short loc_18007A3F0
```
