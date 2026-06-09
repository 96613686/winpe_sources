# RegistryPath::Initialize(HKEY__ *,ushort const *,ushort const *)

- ea: `0x180091c18`
- end: `0x180091ed1`
- name: `?Initialize@RegistryPath@@QEAAJPEAUHKEY__@@PEBG1@Z`
- size: `697`
- prototype: `__int64 __fastcall(RegistryPath *__hidden this, HKEY, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, loader_planting`

## callers

- `0x180091ed8`
- `0x180091fa0`
- `0x180097184`

## callees

- `0x180004a24`
- `0x180087188`
- `0x1800871b4`
- `0x18008a9ec`
- `0x18008aa28`
- `0x18008aa9c`
- `0x18008aecc`
- `0x18009157c`
- `0x180091b50`
- `0x180091c18`
- `0x1800924b8`
- `0x180092694`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180091e28`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180091e28`
- `ntdll!NtQueryKey` at `0x180091d04`
- `ntdll!NtQueryKey` at `0x180091d76`
- `ntdll!NtQueryKey` at `0x180091d04`
- `ntdll!NtQueryKey` at `0x180091d76`

## string_xrefs

- `0x180091e53`: `RegistryPath::Append`
- `0x180091cab`: `%s: Root path is empty. Retrieve path using the root key handle.`
- `0x180091c4f`: `RegistryPath::Initialize`
- `0x180091c93`: `RegistryPath::Initialize`
- `0x180091dd3`: `\Registry\User`
- `0x180091db3`: `\Registry\Machine`

## pseudocode

```c
__int64 __fastcall RegistryPath::Initialize(
        size_t *this,
        HKEY a2,
        const unsigned __int16 *PredefinedRegistryHandlePath,
        unsigned __int16 *a4)
{
  HANDLE *v4; // rbx
  NTSTATUS v8; // r13d
  unsigned __int16 *v9; // rbp
  unsigned int v10; // r14d
  HANDLE v11; // rcx
  __int64 v12; // rdi
  void *v13; // rax
  const unsigned __int16 *v14; // rbp
  const unsigned __int16 *v15; // rdx
  const unsigned __int16 *v16; // rax
  int v17; // edi
  size_t v18; // rax
  unsigned __int16 *v19; // rdx
  int v20; // edi
  void *v22; // [rsp+30h] [rbp-48h]
  ULONG ResultLength; // [rsp+88h] [rbp+10h] BYREF
  unsigned __int16 *v24; // [rsp+98h] [rbp+20h]

  v24 = a4;
  v4 = (HANDLE *)(this + 4);
  v22 = 0;
  v8 = 0;
  v9 = 0;
  if ( !a2 )
  {
    v10 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"RegistryPath::Initialize", L"rootKey");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"RegistryPath::Initialize", L"rootKey");
    goto LABEL_28;
  }
  v10 = 0;
  RegistryPath::Reset((RegistryPath *)this);
  *v4 = a2;
  if ( !PredefinedRegistryHandlePath || !*PredefinedRegistryHandlePath )
  {
    Logger::TraceVerbose(
      L"%s: Root path is empty. Retrieve path using the root key handle.",
      L"RegistryPath::Initialize");
    if ( (unsigned __int64)(a2 + 0x20000000) <= 7 || a2 == HKEY_PERFORMANCE_TEXT || a2 == HKEY_PERFORMANCE_NLSTEXT )
    {
      PredefinedRegistryHandlePath = RegistryPath::GetPredefinedRegistryHandlePath(a2);
    }
    else
    {
      v11 = *v4;
      ResultLength = 0;
      v8 = NtQueryKey(v11, KeyNameInformation, 0, 0, &ResultLength);
      if ( v8 == -1073741789 )
      {
        v12 = ResultLength + 2LL;
        v13 = SafeAlloc(v12);
        v22 = v13;
        v9 = (unsigned __int16 *)v13;
        if ( !v13 )
        {
          v10 = -2147024882;
          Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"RegistryPath::Initialize");
          goto LABEL_28;
        }
        memset_0(v13, 0, v12);
        v8 = NtQueryKey(*v4, KeyNameInformation, v9, v12, &ResultLength);
      }
      if ( v8 < 0 )
      {
        Logger::TraceError(
          L"%s: %s failed with NTSTATUS: 0x%08x.",
          L"RegistryPath::Initialize",
          L"NtQueryKey",
          (unsigned int)v8);
        goto LABEL_28;
      }
      PredefinedRegistryHandlePath = v9 + 2;
    }
  }
  v14 = SplitPath(PredefinedRegistryHandlePath, L"\\Registry\\Machine");
  if ( v14 )
  {
    v15 = L"HKEY_LOCAL_MACHINE";
  }
  else
  {
    v16 = SplitPath(PredefinedRegistryHandlePath, L"\\Registry\\User");
    v15 = L"HKEY_USERS";
    v14 = v16;
    if ( !v16 )
      v15 = PredefinedRegistryHandlePath;
  }
  v17 = RegistryPath::Append((const wchar_t **)this, v15);
  if ( v17
    || v14 && *v14 && (v17 = RegistryPath::Append((const wchar_t **)this, v14)) != 0
    || (v18 = wcsnlen((const wchar_t *)*this, this[1]),
        v19 = v24,
        this[3] = v18,
        (v17 = RegistryPath::Append((const wchar_t **)this, v19)) != 0) )
  {
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"RegistryPath::Initialize",
      L"RegistryPath::Append",
      (unsigned int)v17);
    if ( v17 > 0 )
      v10 = (unsigned __int16)v17 | 0x80070000;
    else
      v10 = v17;
  }
LABEL_28:
  v20 = v8 | 0x10000000;
  if ( !v8 )
    v20 = v10;
  if ( v20 < 0 )
  {
    if ( *v4 == a2 )
      *v4 = 0;
    RegistryPath::Reset((RegistryPath *)this);
  }
  SafeFree(v22);
  Logger::TraceVerbose(L"%s - hr: 0x%08x", L"RegistryPath::Initialize", (unsigned int)v20);
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x180091c18  mov     [rsp+arg_0], rbx
0x180091c1d  mov     [rsp+arg_18], r9
0x180091c22  push    rbp
0x180091c23  push    rsi
0x180091c24  push    rdi
0x180091c25  push    r12
0x180091c27  push    r13
0x180091c29  push    r14
0x180091c2b  push    r15
0x180091c2d  sub     rsp, 40h
0x180091c31  xor     eax, eax
0x180091c33  lea     rbx, [rcx+20h]
0x180091c37  mov     [rsp+78h+var_48], rax
0x180091c3c  mov     rdi, r8
0x180091c3f  mov     r15, rdx
0x180091c42  mov     r12, rcx
0x180091c45  mov     r13d, eax
0x180091c48  mov     ebp, eax
0x180091c4a  test    rdx, rdx
0x180091c4d  jnz     short loc_180091C86
0x180091c4f  lea     rsi, aRegistrypathIn_0; "RegistryPath::Initialize"
0x180091c56  mov     r14d, 80070057h
0x180091c5c  mov     rdx, rsi
0x180091c5f  lea     r8, aRootkey; "rootKey"
0x180091c66  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180091c6d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180091c72  lea     rdx, aRootkey; "rootKey"
0x180091c79  mov     rcx, rsi; unsigned __int16 *
0x180091c7c  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180091c81  jmp     loc_180091E76
0x180091c86  mov     r14d, eax
0x180091c89  call    ?Reset@RegistryPath@@AEAAXXZ; RegistryPath::Reset(void)
0x180091c8e  xor     eax, eax
0x180091c90  mov     [rbx], r15
0x180091c93  lea     rsi, aRegistrypathIn_0; "RegistryPath::Initialize"
0x180091c9a  test    rdi, rdi
0x180091c9d  jz      short loc_180091CA8
0x180091c9f  cmp     [rdi], ax
0x180091ca2  jnz     loc_180091DB3
0x180091ca8  mov     rdx, rsi
0x180091cab  lea     rcx, aSRootPathIsEmp; "%s: Root path is empty. Retrieve path u"...
0x180091cb2  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180091cb7  mov     eax, 80000000h
0x180091cbc  add     rax, r15
0x180091cbf  cmp     rax, 7
0x180091cc3  jbe     loc_180091DA8
0x180091cc9  cmp     r15, 0FFFFFFFF80000050h
0x180091cd0  jz      loc_180091DA8
0x180091cd6  cmp     r15, 0FFFFFFFF80000060h
0x180091cdd  jz      loc_180091DA8
0x180091ce3  mov     rcx, [rbx]; KeyHandle
0x180091ce6  lea     rax, [rsp+78h+arg_8]
0x180091cee  xor     r9d, r9d; Length
0x180091cf1  mov     [rsp+78h+arg_8], ebp
0x180091cf8  xor     r8d, r8d; KeyInformation
0x180091cfb  mov     [rsp+78h+ResultLength], rax; ResultLength
0x180091d00  lea     edx, [r9+3]; KeyInformationClass
0x180091d04  call    cs:__imp_NtQueryKey
0x180091d0a  mov     r13d, eax
0x180091d0d  cmp     eax, 0C0000023h
0x180091d12  jnz     short loc_180091D7F
0x180091d14  mov     edi, [rsp+78h+arg_8]
0x180091d1b  add     rdi, 2
0x180091d1f  mov     rcx, rdi; unsigned __int64
0x180091d22  call    ?SafeAlloc@@YAPEAX_K@Z; SafeAlloc(unsigned __int64)
0x180091d27  mov     [rsp+78h+var_48], rax
0x180091d2c  mov     rbp, rax
0x180091d2f  test    rax, rax
0x180091d32  jnz     short loc_180091D4E
0x180091d34  mov     rdx, rsi
0x180091d37  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x180091d3e  mov     r14d, 8007000Eh
0x180091d44  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x180091d49  jmp     loc_180091E76
0x180091d4e  mov     r8, rdi; Size
0x180091d51  xor     edx, edx; Val
0x180091d53  mov     rcx, rbp; void *
0x180091d56  call    memset_0
0x180091d5b  mov     rcx, [rbx]; KeyHandle
0x180091d5e  lea     rax, [rsp+78h+arg_8]
0x180091d66  mov     r9d, edi; Length
0x180091d69  mov     [rsp+78h+ResultLength], rax; ResultLength
0x180091d6e  mov     r8, rbp; KeyInformation
0x180091d71  mov     edx, 3; KeyInformationClass
0x180091d76  call    cs:__imp_NtQueryKey
0x180091d7c  mov     r13d, eax
0x180091d7f  test    r13d, r13d
0x180091d82  jns     short loc_180091DA2
0x180091d84  mov     r9d, r13d
0x180091d87  lea     r8, aNtquerykey; "NtQueryKey"
0x180091d8e  mov     rdx, rsi
0x180091d91  lea     rcx, aSSFailedWithNt; "%s: %s failed with NTSTATUS: 0x%08x."
0x180091d98  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180091d9d  jmp     loc_180091E76
0x180091da2  lea     rdi, [rbp+4]
0x180091da6  jmp     short loc_180091DB3
0x180091da8  mov     rcx, r15; HKEY
0x180091dab  call    ?GetPredefinedRegistryHandlePath@RegistryPath@@CAPEBGPEAUHKEY__@@@Z; RegistryPath::GetPredefinedRegistryHandlePath(HKEY__ *)
0x180091db0  mov     rdi, rax
0x180091db3  lea     rdx, aRegistryMachin; "\\Registry\\Machine"
0x180091dba  mov     rcx, rdi; unsigned __int16 *
0x180091dbd  call    ?SplitPath@@YAPEBGPEBG0@Z; SplitPath(ushort const *,ushort const *)
0x180091dc2  mov     rbp, rax
0x180091dc5  test    rax, rax
0x180091dc8  jz      short loc_180091DD3
0x180091dca  lea     rdx, aHkeyLocalMachi_0; "HKEY_LOCAL_MACHINE"
0x180091dd1  jmp     short loc_180091DF3
0x180091dd3  lea     rdx, aRegistryUser; "\\Registry\\User"
0x180091dda  mov     rcx, rdi; unsigned __int16 *
0x180091ddd  call    ?SplitPath@@YAPEBGPEBG0@Z; SplitPath(ushort const *,ushort const *)
0x180091de2  test    rax, rax
0x180091de5  lea     rdx, aHkeyUsers; "HKEY_USERS"
0x180091dec  mov     rbp, rax
0x180091def  cmovz   rdx, rdi; unsigned __int16 *
0x180091df3  mov     rcx, r12; this
0x180091df6  call    ?Append@RegistryPath@@QEAAKPEBG@Z; RegistryPath::Append(ushort const *)
0x180091dfb  mov     edi, eax
0x180091dfd  xor     eax, eax
0x180091dff  test    edi, edi
0x180091e01  jnz     short loc_180091E49
0x180091e03  test    rbp, rbp
0x180091e06  jz      short loc_180091E1F
0x180091e08  cmp     [rbp+0], ax
0x180091e0c  jz      short loc_180091E1F
0x180091e0e  mov     rdx, rbp; unsigned __int16 *
0x180091e11  mov     rcx, r12; this
0x180091e14  call    ?Append@RegistryPath@@QEAAKPEBG@Z; RegistryPath::Append(ushort const *)
0x180091e19  mov     edi, eax
0x180091e1b  test    eax, eax
0x180091e1d  jnz     short loc_180091E49
0x180091e1f  mov     rdx, [r12+8]; MaxCount
0x180091e24  mov     rcx, [r12]; Source
0x180091e28  call    cs:__imp_wcsnlen
0x180091e2e  mov     rdx, [rsp+78h+arg_18]; unsigned __int16 *
0x180091e36  mov     rcx, r12; this
0x180091e39  mov     [r12+18h], rax
0x180091e3e  call    ?Append@RegistryPath@@QEAAKPEBG@Z; RegistryPath::Append(ushort const *)
0x180091e43  mov     edi, eax
0x180091e45  test    eax, eax
0x180091e47  jz      short loc_180091E76
0x180091e49  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x180091e50  mov     rdx, rsi
0x180091e53  lea     r8, aRegistrypathAp; "RegistryPath::Append"
0x180091e5a  mov     r9d, edi
0x180091e5d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180091e62  test    edi, edi
0x180091e64  jg      short loc_180091E6B
0x180091e66  mov     r14d, edi
0x180091e69  jmp     short loc_180091E76
0x180091e6b  movzx   r14d, di
0x180091e6f  or      r14d, 80070000h
0x180091e76  mov     edi, r13d
0x180091e79  bts     edi, 1Ch
0x180091e7d  test    r13d, r13d
0x180091e80  cmovz   edi, r14d
0x180091e84  xor     r14d, r14d
0x180091e87  test    edi, edi
0x180091e89  jns     short loc_180091E9B
0x180091e8b  cmp     [rbx], r15
0x180091e8e  jnz     short loc_180091E93
0x180091e90  mov     [rbx], r14
0x180091e93  mov     rcx, r12; this
0x180091e96  call    ?Reset@RegistryPath@@AEAAXXZ; RegistryPath::Reset(void)
0x180091e9b  mov     rcx, [rsp+78h+var_48]; void *
0x180091ea0  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180091ea5  mov     r8d, edi
0x180091ea8  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x180091eaf  mov     rdx, rsi
0x180091eb2  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180091eb7  mov     rbx, [rsp+78h+arg_0]
0x180091ebf  mov     eax, edi
0x180091ec1  add     rsp, 40h
0x180091ec5  pop     r15
0x180091ec7  pop     r14
0x180091ec9  pop     r13
0x180091ecb  pop     r12
0x180091ecd  pop     rdi
0x180091ece  pop     rsi
0x180091ecf  pop     rbp
0x180091ed0  retn
```
