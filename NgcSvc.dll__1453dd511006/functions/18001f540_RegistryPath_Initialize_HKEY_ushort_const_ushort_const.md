# RegistryPath::Initialize(HKEY__ *,ushort const *,ushort const *)

- ea: `0x18001f540`
- end: `0x18001f84b`
- name: `?Initialize@RegistryPath@@QEAAJPEAUHKEY__@@PEBG1@Z`
- size: `779`
- prototype: `__int64 __fastcall(RegistryPath *__hidden this, HKEY, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180033d48`
- `0x18004a470`

## callees

- `0x18001a100`
- `0x18001ea7c`
- `0x18001eb00`
- `0x18001f540`
- `0x180020c8c`
- `0x1800215e4`
- `0x18002fd54`
- `0x18003524c`
- `0x18004aa08`
- `0x18004d79c`
- `0x18005cee0`
- `0x18005dd44`
- `0x1800ac7d4`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18001f7a3`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18001f7a3`
- `ntdll!NtQueryKey` at `0x18001f691`
- `ntdll!NtQueryKey` at `0x18001f6f3`
- `ntdll!NtQueryKey` at `0x18001f691`
- `ntdll!NtQueryKey` at `0x18001f6f3`

## string_xrefs

- `0x18001f58b`: `RegistryPath::Initialize`
- `0x18001f625`: `RegistryPath::Initialize`
- `0x18001f7ca`: `RegistryPath::Append`
- `0x18001f601`: `Logger::WriteNullOrEmptyParameterFailureEvent`
- `0x18001f5fa`: `EventWriteNullOrEmptyParameterFailureEvent`
- `0x18001f63d`: `%s: Root path is empty. Retrieve path using the root key handle.`
- `0x18001f750`: `\Registry\User`
- `0x18001f730`: `\Registry\Machine`

## pseudocode

```c
__int64 __fastcall RegistryPath::Initialize(
        RegistryPath *this,
        HKEY a2,
        const unsigned __int16 *PredefinedRegistryHandlePath,
        unsigned __int16 *a4)
{
  unsigned __int16 *v7; // r13
  int v8; // ebx
  __int64 v9; // r8
  unsigned int v10; // eax
  NTSTATUS v11; // r15d
  void *v12; // rcx
  __int64 v13; // rbx
  unsigned __int16 *v14; // rax
  const unsigned __int16 *v15; // r14
  const unsigned __int16 *v16; // rdx
  const unsigned __int16 *v17; // rax
  int v18; // ebp
  size_t v19; // rax
  unsigned __int16 *v20; // rdx
  ULONG ResultLength; // [rsp+30h] [rbp-98h] BYREF
  unsigned __int16 *v23; // [rsp+38h] [rbp-90h]
  _BYTE v24[16]; // [rsp+40h] [rbp-88h] BYREF
  const wchar_t *v25; // [rsp+50h] [rbp-78h]
  __int64 v26; // [rsp+58h] [rbp-70h]
  const wchar_t *v27; // [rsp+60h] [rbp-68h]
  __int64 v28; // [rsp+68h] [rbp-60h]

  v23 = a4;
  v7 = 0;
  if ( a2 )
  {
    v11 = 0;
    RegistryPath::Reset(this);
    *((_QWORD *)this + 4) = a2;
    if ( !PredefinedRegistryHandlePath || !*PredefinedRegistryHandlePath )
    {
      Logger::TraceVerbose(
        L"%s: Root path is empty. Retrieve path using the root key handle.",
        L"RegistryPath::Initialize");
      if ( a2 == HKEY_PERFORMANCE_TEXT || (unsigned __int64)(a2 + 0x20000000) <= 7 || a2 == HKEY_PERFORMANCE_NLSTEXT )
      {
        PredefinedRegistryHandlePath = RegistryPath::GetPredefinedRegistryHandlePath(a2);
      }
      else
      {
        v12 = (void *)*((_QWORD *)this + 4);
        ResultLength = 0;
        v11 = NtQueryKey(v12, KeyNameInformation, 0, 0, &ResultLength);
        if ( v11 == -1073741789 )
        {
          v13 = ResultLength + 2LL;
          v14 = (unsigned __int16 *)MIDL_user_allocate(v13);
          v7 = v14;
          if ( !v14 )
          {
            Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"RegistryPath::Initialize");
            goto LABEL_31;
          }
          memset_0(v14, 0, v13);
          v11 = NtQueryKey(*((HANDLE *)this + 4), KeyNameInformation, v7, v13, &ResultLength);
        }
        if ( v11 < 0 )
        {
          Logger::TraceError(
            L"%s: %s failed with NTSTATUS: 0x%08x.",
            L"RegistryPath::Initialize",
            L"NtQueryKey",
            (unsigned int)v11);
          goto LABEL_31;
        }
        PredefinedRegistryHandlePath = v7 + 2;
      }
    }
    v15 = SplitPath(PredefinedRegistryHandlePath, L"\\Registry\\Machine");
    if ( v15 )
    {
      v16 = L"HKEY_LOCAL_MACHINE";
    }
    else
    {
      v17 = SplitPath(PredefinedRegistryHandlePath, L"\\Registry\\User");
      v16 = L"HKEY_USERS";
      v15 = v17;
      if ( !v17 )
        v16 = PredefinedRegistryHandlePath;
    }
    v8 = 0;
    v18 = RegistryPath::Append(this, v16);
    if ( v18
      || v15 && *v15 && (v18 = RegistryPath::Append(this, v15)) != 0
      || (v19 = wcsnlen(*(const wchar_t **)this, *((_QWORD *)this + 1)),
          v20 = v23,
          *((_QWORD *)this + 3) = v19,
          (v18 = RegistryPath::Append(this, v20)) != 0) )
    {
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"RegistryPath::Initialize",
        L"RegistryPath::Append",
        (unsigned int)v18);
      if ( v18 > 0 )
        v8 = (unsigned __int16)v18 | 0x80070000;
      else
        v8 = v18;
    }
    if ( !v11 )
    {
LABEL_32:
      if ( v8 >= 0 )
        goto LABEL_36;
      goto LABEL_33;
    }
LABEL_31:
    v8 = v11 | 0x10000000;
    goto LABEL_32;
  }
  v8 = -2147024809;
  Logger::TraceError(L"%s: \"%s\" should not be null.", L"RegistryPath::Initialize", L"rootKey");
  if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
  {
    v25 = L"RegistryPath::Initialize";
    v26 = 50;
    v27 = L"rootKey";
    v28 = 16;
    v10 = McGenEventWrite_EventWriteTransfer(
            &UserDeviceRegistrationEventProvider_Context,
            NullOrEmptyParameterFailureEvent,
            v9,
            3,
            v24);
    if ( v10 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"Logger::WriteNullOrEmptyParameterFailureEvent",
        L"EventWriteNullOrEmptyParameterFailureEvent",
        v10);
  }
LABEL_33:
  if ( *((HKEY *)this + 4) == a2 )
    *((_QWORD *)this + 4) = 0;
  RegistryPath::Reset(this);
LABEL_36:
  SafeFree(v7);
  Logger::TraceVerbose(L"%s - hr: 0x%08x", L"RegistryPath::Initialize", (unsigned int)v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001f540  push    rbx
0x18001f542  push    rbp
0x18001f543  push    rsi
0x18001f544  push    rdi
0x18001f545  push    r12
0x18001f547  push    r13
0x18001f549  push    r14
0x18001f54b  push    r15
0x18001f54d  sub     rsp, 88h
0x18001f554  mov     rax, cs:__security_cookie
0x18001f55b  xor     rax, rsp
0x18001f55e  mov     [rsp+0C8h+var_58], rax
0x18001f563  xor     ebp, ebp
0x18001f565  mov     [rsp+0C8h+var_90], r9
0x18001f56a  mov     rbx, r8
0x18001f56d  mov     r12, rdx
0x18001f570  mov     rdi, rcx
0x18001f573  mov     r13d, ebp
0x18001f576  test    rdx, rdx
0x18001f579  jnz     loc_18001F619
0x18001f57f  lea     r14, aRootkey; "rootKey"
0x18001f586  mov     ebx, 80070057h
0x18001f58b  lea     rsi, aRegistrypathIn_0; "RegistryPath::Initialize"
0x18001f592  mov     r8, r14
0x18001f595  mov     rdx, rsi
0x18001f598  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18001f59f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001f5a4  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x18001f5ab  jz      loc_18001F7FC
0x18001f5b1  lea     rax, [rsp+0C8h+var_88]
0x18001f5b6  mov     [rsp+0C8h+var_78], rsi
0x18001f5bb  lea     r9d, [r12+3]
0x18001f5c0  mov     [rsp+0C8h+ResultLength], rax
0x18001f5c5  lea     rdx, NullOrEmptyParameterFailureEvent
0x18001f5cc  mov     [rsp+0C8h+var_70], 32h ; '2'
0x18001f5d5  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x18001f5dc  mov     [rsp+0C8h+var_68], r14
0x18001f5e1  mov     [rsp+0C8h+var_60], 10h
0x18001f5ea  call    McGenEventWrite_EventWriteTransfer
0x18001f5ef  test    eax, eax
0x18001f5f1  jz      loc_18001F7FC
0x18001f5f7  mov     r9d, eax
0x18001f5fa  lea     r8, aEventwritenull; "EventWriteNullOrEmptyParameterFailureEv"...
0x18001f601  lea     rdx, aLoggerWritenul; "Logger::WriteNullOrEmptyParameterFailur"...
0x18001f608  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x18001f60f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001f614  jmp     loc_18001F7FC
0x18001f619  mov     r15d, ebp
0x18001f61c  call    ?Reset@RegistryPath@@AEAAXXZ; RegistryPath::Reset(void)
0x18001f621  mov     [rdi+20h], r12
0x18001f625  lea     rsi, aRegistrypathIn_0; "RegistryPath::Initialize"
0x18001f62c  test    rbx, rbx
0x18001f62f  jz      short loc_18001F63A
0x18001f631  cmp     [rbx], bp
0x18001f634  jnz     loc_18001F730
0x18001f63a  mov     rdx, rsi
0x18001f63d  lea     rcx, aSRootPathIsEmp; "%s: Root path is empty. Retrieve path u"...
0x18001f644  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18001f649  cmp     r12, 0FFFFFFFF80000050h
0x18001f650  jz      loc_18001F725
0x18001f656  mov     eax, 80000000h
0x18001f65b  add     rax, r12
0x18001f65e  cmp     rax, 7
0x18001f662  jbe     loc_18001F725
0x18001f668  cmp     r12, 0FFFFFFFF80000060h
0x18001f66f  jz      loc_18001F725
0x18001f675  mov     rcx, [rdi+20h]; KeyHandle
0x18001f679  lea     rax, [rsp+0C8h+var_98]
0x18001f67e  xor     r9d, r9d; Length
0x18001f681  mov     [rsp+0C8h+var_98], ebp
0x18001f685  xor     r8d, r8d; KeyInformation
0x18001f688  mov     [rsp+0C8h+ResultLength], rax; ResultLength
0x18001f68d  lea     edx, [r9+3]; KeyInformationClass
0x18001f691  call    cs:__imp_NtQueryKey
0x18001f697  mov     r15d, eax
0x18001f69a  cmp     eax, 0C0000023h
0x18001f69f  jnz     short loc_18001F6FC
0x18001f6a1  mov     ebx, [rsp+0C8h+var_98]
0x18001f6a5  add     rbx, 2
0x18001f6a9  mov     rcx, rbx; size
0x18001f6ac  call    MIDL_user_allocate
0x18001f6b1  mov     r13, rax
0x18001f6b4  test    rax, rax
0x18001f6b7  jnz     short loc_18001F6CD
0x18001f6b9  mov     rdx, rsi
0x18001f6bc  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x18001f6c3  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x18001f6c8  jmp     loc_18001F7F1
0x18001f6cd  mov     r8, rbx; Size
0x18001f6d0  xor     edx, edx; Val
0x18001f6d2  mov     rcx, r13; void *
0x18001f6d5  call    memset_0
0x18001f6da  mov     rcx, [rdi+20h]; KeyHandle
0x18001f6de  lea     rax, [rsp+0C8h+var_98]
0x18001f6e3  mov     r9d, ebx; Length
0x18001f6e6  mov     [rsp+0C8h+ResultLength], rax; ResultLength
0x18001f6eb  mov     r8, r13; KeyInformation
0x18001f6ee  mov     edx, 3; KeyInformationClass
0x18001f6f3  call    cs:__imp_NtQueryKey
0x18001f6f9  mov     r15d, eax
0x18001f6fc  test    r15d, r15d
0x18001f6ff  jns     short loc_18001F71F
0x18001f701  mov     r9d, r15d
0x18001f704  lea     r8, aNtquerykey; "NtQueryKey"
0x18001f70b  mov     rdx, rsi
0x18001f70e  lea     rcx, aSSFailedWithNt; "%s: %s failed with NTSTATUS: 0x%08x."
0x18001f715  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001f71a  jmp     loc_18001F7F1
0x18001f71f  lea     rbx, [r13+4]
0x18001f723  jmp     short loc_18001F730
0x18001f725  mov     rcx, r12; HKEY
0x18001f728  call    ?GetPredefinedRegistryHandlePath@RegistryPath@@CAPEBGPEAUHKEY__@@@Z; RegistryPath::GetPredefinedRegistryHandlePath(HKEY__ *)
0x18001f72d  mov     rbx, rax
0x18001f730  lea     rdx, aRegistryMachin; "\\Registry\\Machine"
0x18001f737  mov     rcx, rbx; unsigned __int16 *
0x18001f73a  call    ?SplitPath@@YAPEBGPEBG0@Z; SplitPath(ushort const *,ushort const *)
0x18001f73f  mov     r14, rax
0x18001f742  test    rax, rax
0x18001f745  jz      short loc_18001F750
0x18001f747  lea     rdx, aHkeyLocalMachi_0; "HKEY_LOCAL_MACHINE"
0x18001f74e  jmp     short loc_18001F770
0x18001f750  lea     rdx, aRegistryUser; "\\Registry\\User"
0x18001f757  mov     rcx, rbx; unsigned __int16 *
0x18001f75a  call    ?SplitPath@@YAPEBGPEBG0@Z; SplitPath(ushort const *,ushort const *)
0x18001f75f  test    rax, rax
0x18001f762  lea     rdx, aHkeyUsers; "HKEY_USERS"
0x18001f769  mov     r14, rax
0x18001f76c  cmovz   rdx, rbx; unsigned __int16 *
0x18001f770  mov     rcx, rdi; this
0x18001f773  call    ?Append@RegistryPath@@QEAAKPEBG@Z; RegistryPath::Append(ushort const *)
0x18001f778  xor     ebx, ebx
0x18001f77a  mov     ebp, eax
0x18001f77c  test    eax, eax
0x18001f77e  jnz     short loc_18001F7C0
0x18001f780  test    r14, r14
0x18001f783  jz      short loc_18001F79C
0x18001f785  cmp     [r14], bx
0x18001f789  jz      short loc_18001F79C
0x18001f78b  mov     rdx, r14; unsigned __int16 *
0x18001f78e  mov     rcx, rdi; this
0x18001f791  call    ?Append@RegistryPath@@QEAAKPEBG@Z; RegistryPath::Append(ushort const *)
0x18001f796  mov     ebp, eax
0x18001f798  test    eax, eax
0x18001f79a  jnz     short loc_18001F7C0
0x18001f79c  mov     rdx, [rdi+8]; MaxCount
0x18001f7a0  mov     rcx, [rdi]; Source
0x18001f7a3  call    cs:__imp_wcsnlen
0x18001f7a9  mov     rdx, [rsp+0C8h+var_90]; unsigned __int16 *
0x18001f7ae  mov     rcx, rdi; this
0x18001f7b1  mov     [rdi+18h], rax
0x18001f7b5  call    ?Append@RegistryPath@@QEAAKPEBG@Z; RegistryPath::Append(ushort const *)
0x18001f7ba  mov     ebp, eax
0x18001f7bc  test    eax, eax
0x18001f7be  jz      short loc_18001F7EA
0x18001f7c0  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x18001f7c7  mov     rdx, rsi
0x18001f7ca  lea     r8, aRegistrypathAp; "RegistryPath::Append"
0x18001f7d1  mov     r9d, ebp
0x18001f7d4  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001f7d9  test    ebp, ebp
0x18001f7db  jg      short loc_18001F7E1
0x18001f7dd  mov     ebx, ebp
0x18001f7df  jmp     short loc_18001F7EA
0x18001f7e1  movzx   ebx, bp
0x18001f7e4  or      ebx, 80070000h
0x18001f7ea  xor     ebp, ebp
0x18001f7ec  test    r15d, r15d
0x18001f7ef  jz      short loc_18001F7F8
0x18001f7f1  mov     ebx, r15d
0x18001f7f4  bts     ebx, 1Ch
0x18001f7f8  test    ebx, ebx
0x18001f7fa  jns     short loc_18001F80E
0x18001f7fc  cmp     [rdi+20h], r12
0x18001f800  jnz     short loc_18001F806
0x18001f802  mov     [rdi+20h], rbp
0x18001f806  mov     rcx, rdi; this
0x18001f809  call    ?Reset@RegistryPath@@AEAAXXZ; RegistryPath::Reset(void)
0x18001f80e  mov     rcx, r13; void *
0x18001f811  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18001f816  mov     r8d, ebx
0x18001f819  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x18001f820  mov     rdx, rsi
0x18001f823  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18001f828  mov     eax, ebx
0x18001f82a  mov     rcx, [rsp+0C8h+var_58]
0x18001f82f  xor     rcx, rsp; StackCookie
0x18001f832  call    __security_check_cookie
0x18001f837  add     rsp, 88h
0x18001f83e  pop     r15
0x18001f840  pop     r14
0x18001f842  pop     r13
0x18001f844  pop     r12
0x18001f846  pop     rdi
0x18001f847  pop     rsi
0x18001f848  pop     rbp
0x18001f849  pop     rbx
0x18001f84a  retn
```
