# RegistryPath::Initialize(HKEY__ *,ushort const *,ushort const *)

- ea: `0x18008168c`
- end: `0x180081945`
- name: `?Initialize@RegistryPath@@QEAAJPEAUHKEY__@@PEBG1@Z`
- size: `697`
- prototype: `__int64 __fastcall(RegistryPath *__hidden this, HKEY, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting`

## callers

- `0x18008194c`
- `0x180081a14`

## callees

- `0x1800084c8`
- `0x18006b2c0`
- `0x180079de0`
- `0x18007d17c`
- `0x18007d1b8`
- `0x18007d22c`
- `0x18007d2a4`
- `0x1800812c0`
- `0x1800815c4`
- `0x18008168c`
- `0x180081e1c`
- `0x180081eb8`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18008189c`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18008189c`
- `ntdll!NtQueryKey` at `0x180081778`
- `ntdll!NtQueryKey` at `0x1800817ea`
- `ntdll!NtQueryKey` at `0x180081778`
- `ntdll!NtQueryKey` at `0x1800817ea`

## string_xrefs

- `0x1800818c7`: `RegistryPath::Append`
- `0x1800816c3`: `RegistryPath::Initialize`
- `0x180081707`: `RegistryPath::Initialize`
- `0x18008171f`: `%s: Root path is empty. Retrieve path using the root key handle.`
- `0x180081827`: `\Registry\Machine`
- `0x180081847`: `\Registry\User`

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
        v13 = MIDL_user_allocate(v12);
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
0x18008168c  mov     [rsp+arg_0], rbx
0x180081691  mov     [rsp+arg_18], r9
0x180081696  push    rbp
0x180081697  push    rsi
0x180081698  push    rdi
0x180081699  push    r12
0x18008169b  push    r13
0x18008169d  push    r14
0x18008169f  push    r15
0x1800816a1  sub     rsp, 40h
0x1800816a5  xor     eax, eax
0x1800816a7  lea     rbx, [rcx+20h]
0x1800816ab  mov     [rsp+78h+var_48], rax
0x1800816b0  mov     rdi, r8
0x1800816b3  mov     r15, rdx
0x1800816b6  mov     r12, rcx
0x1800816b9  mov     r13d, eax
0x1800816bc  mov     ebp, eax
0x1800816be  test    rdx, rdx
0x1800816c1  jnz     short loc_1800816FA
0x1800816c3  lea     rsi, aRegistrypathIn_0; "RegistryPath::Initialize"
0x1800816ca  mov     r14d, 80070057h
0x1800816d0  mov     rdx, rsi
0x1800816d3  lea     r8, aRootkey; "rootKey"
0x1800816da  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x1800816e1  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800816e6  lea     rdx, aRootkey; "rootKey"
0x1800816ed  mov     rcx, rsi; unsigned __int16 *
0x1800816f0  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x1800816f5  jmp     loc_1800818EA
0x1800816fa  mov     r14d, eax
0x1800816fd  call    ?Reset@RegistryPath@@AEAAXXZ; RegistryPath::Reset(void)
0x180081702  xor     eax, eax
0x180081704  mov     [rbx], r15
0x180081707  lea     rsi, aRegistrypathIn_0; "RegistryPath::Initialize"
0x18008170e  test    rdi, rdi
0x180081711  jz      short loc_18008171C
0x180081713  cmp     [rdi], ax
0x180081716  jnz     loc_180081827
0x18008171c  mov     rdx, rsi
0x18008171f  lea     rcx, aSRootPathIsEmp; "%s: Root path is empty. Retrieve path u"...
0x180081726  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18008172b  mov     eax, 80000000h
0x180081730  add     rax, r15
0x180081733  cmp     rax, 7
0x180081737  jbe     loc_18008181C
0x18008173d  cmp     r15, 0FFFFFFFF80000050h
0x180081744  jz      loc_18008181C
0x18008174a  cmp     r15, 0FFFFFFFF80000060h
0x180081751  jz      loc_18008181C
0x180081757  mov     rcx, [rbx]; KeyHandle
0x18008175a  lea     rax, [rsp+78h+arg_8]
0x180081762  xor     r9d, r9d; Length
0x180081765  mov     [rsp+78h+arg_8], ebp
0x18008176c  xor     r8d, r8d; KeyInformation
0x18008176f  mov     [rsp+78h+ResultLength], rax; ResultLength
0x180081774  lea     edx, [r9+3]; KeyInformationClass
0x180081778  call    cs:__imp_NtQueryKey
0x18008177e  mov     r13d, eax
0x180081781  cmp     eax, 0C0000023h
0x180081786  jnz     short loc_1800817F3
0x180081788  mov     edi, [rsp+78h+arg_8]
0x18008178f  add     rdi, 2
0x180081793  mov     rcx, rdi; size
0x180081796  call    MIDL_user_allocate
0x18008179b  mov     [rsp+78h+var_48], rax
0x1800817a0  mov     rbp, rax
0x1800817a3  test    rax, rax
0x1800817a6  jnz     short loc_1800817C2
0x1800817a8  mov     rdx, rsi
0x1800817ab  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x1800817b2  mov     r14d, 8007000Eh
0x1800817b8  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x1800817bd  jmp     loc_1800818EA
0x1800817c2  mov     r8, rdi; Size
0x1800817c5  xor     edx, edx; Val
0x1800817c7  mov     rcx, rbp; void *
0x1800817ca  call    memset_0
0x1800817cf  mov     rcx, [rbx]; KeyHandle
0x1800817d2  lea     rax, [rsp+78h+arg_8]
0x1800817da  mov     r9d, edi; Length
0x1800817dd  mov     [rsp+78h+ResultLength], rax; ResultLength
0x1800817e2  mov     r8, rbp; KeyInformation
0x1800817e5  mov     edx, 3; KeyInformationClass
0x1800817ea  call    cs:__imp_NtQueryKey
0x1800817f0  mov     r13d, eax
0x1800817f3  test    r13d, r13d
0x1800817f6  jns     short loc_180081816
0x1800817f8  mov     r9d, r13d
0x1800817fb  lea     r8, aNtquerykey; "NtQueryKey"
0x180081802  mov     rdx, rsi
0x180081805  lea     rcx, aSSFailedWithNt; "%s: %s failed with NTSTATUS: 0x%08x."
0x18008180c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180081811  jmp     loc_1800818EA
0x180081816  lea     rdi, [rbp+4]
0x18008181a  jmp     short loc_180081827
0x18008181c  mov     rcx, r15; HKEY
0x18008181f  call    ?GetPredefinedRegistryHandlePath@RegistryPath@@CAPEBGPEAUHKEY__@@@Z; RegistryPath::GetPredefinedRegistryHandlePath(HKEY__ *)
0x180081824  mov     rdi, rax
0x180081827  lea     rdx, aRegistryMachin; "\\Registry\\Machine"
0x18008182e  mov     rcx, rdi; unsigned __int16 *
0x180081831  call    ?SplitPath@@YAPEBGPEBG0@Z; SplitPath(ushort const *,ushort const *)
0x180081836  mov     rbp, rax
0x180081839  test    rax, rax
0x18008183c  jz      short loc_180081847
0x18008183e  lea     rdx, aHkeyLocalMachi_0; "HKEY_LOCAL_MACHINE"
0x180081845  jmp     short loc_180081867
0x180081847  lea     rdx, aRegistryUser; "\\Registry\\User"
0x18008184e  mov     rcx, rdi; unsigned __int16 *
0x180081851  call    ?SplitPath@@YAPEBGPEBG0@Z; SplitPath(ushort const *,ushort const *)
0x180081856  test    rax, rax
0x180081859  lea     rdx, aHkeyUsers; "HKEY_USERS"
0x180081860  mov     rbp, rax
0x180081863  cmovz   rdx, rdi; unsigned __int16 *
0x180081867  mov     rcx, r12; this
0x18008186a  call    ?Append@RegistryPath@@QEAAKPEBG@Z; RegistryPath::Append(ushort const *)
0x18008186f  mov     edi, eax
0x180081871  xor     eax, eax
0x180081873  test    edi, edi
0x180081875  jnz     short loc_1800818BD
0x180081877  test    rbp, rbp
0x18008187a  jz      short loc_180081893
0x18008187c  cmp     [rbp+0], ax
0x180081880  jz      short loc_180081893
0x180081882  mov     rdx, rbp; unsigned __int16 *
0x180081885  mov     rcx, r12; this
0x180081888  call    ?Append@RegistryPath@@QEAAKPEBG@Z; RegistryPath::Append(ushort const *)
0x18008188d  mov     edi, eax
0x18008188f  test    eax, eax
0x180081891  jnz     short loc_1800818BD
0x180081893  mov     rdx, [r12+8]; MaxCount
0x180081898  mov     rcx, [r12]; Source
0x18008189c  call    cs:__imp_wcsnlen
0x1800818a2  mov     rdx, [rsp+78h+arg_18]; unsigned __int16 *
0x1800818aa  mov     rcx, r12; this
0x1800818ad  mov     [r12+18h], rax
0x1800818b2  call    ?Append@RegistryPath@@QEAAKPEBG@Z; RegistryPath::Append(ushort const *)
0x1800818b7  mov     edi, eax
0x1800818b9  test    eax, eax
0x1800818bb  jz      short loc_1800818EA
0x1800818bd  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x1800818c4  mov     rdx, rsi
0x1800818c7  lea     r8, aRegistrypathAp; "RegistryPath::Append"
0x1800818ce  mov     r9d, edi
0x1800818d1  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800818d6  test    edi, edi
0x1800818d8  jg      short loc_1800818DF
0x1800818da  mov     r14d, edi
0x1800818dd  jmp     short loc_1800818EA
0x1800818df  movzx   r14d, di
0x1800818e3  or      r14d, 80070000h
0x1800818ea  mov     edi, r13d
0x1800818ed  bts     edi, 1Ch
0x1800818f1  test    r13d, r13d
0x1800818f4  cmovz   edi, r14d
0x1800818f8  xor     r14d, r14d
0x1800818fb  test    edi, edi
0x1800818fd  jns     short loc_18008190F
0x1800818ff  cmp     [rbx], r15
0x180081902  jnz     short loc_180081907
0x180081904  mov     [rbx], r14
0x180081907  mov     rcx, r12; this
0x18008190a  call    ?Reset@RegistryPath@@AEAAXXZ; RegistryPath::Reset(void)
0x18008190f  mov     rcx, [rsp+78h+var_48]; void *
0x180081914  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180081919  mov     r8d, edi
0x18008191c  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x180081923  mov     rdx, rsi
0x180081926  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18008192b  mov     rbx, [rsp+78h+arg_0]
0x180081933  mov     eax, edi
0x180081935  add     rsp, 40h
0x180081939  pop     r15
0x18008193b  pop     r14
0x18008193d  pop     r13
0x18008193f  pop     r12
0x180081941  pop     rdi
0x180081942  pop     rsi
0x180081943  pop     rbp
0x180081944  retn
```
