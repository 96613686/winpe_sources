# RegistryJson::RuntimeClassInitialize(Windows::Data::Json::IJsonObject *,HKEY__ *,ushort const *)

- ea: `0x18006c3a8`
- end: `0x18006c82c`
- name: `?RuntimeClassInitialize@RegistryJson@@QEAAJPEAUIJsonObject@Json@Data@Windows@@PEAUHKEY__@@PEBG@Z`
- size: `1156`
- prototype: `__int64 __fastcall(RegistryJson *__hidden this, struct Windows::Data::Json::IJsonObject *, HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006bb4c`

## callees

- `0x180004b80`
- `0x18000cc8c`
- `0x18001146c`
- `0x1800168c8`
- `0x18001ce88`
- `0x18001e50c`
- `0x18006c3a8`
- `0x18006d090`
- `0x18006d0ac`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18006c53c`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18006c53c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006c3f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006c47c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006c4d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006c5a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006c5bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006c5d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006c62f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006c6c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006c71f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006c733`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006c803`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006c3f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006c47c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006c4d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006c5a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006c5bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006c5d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006c62f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006c6c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006c71f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006c733`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006c803`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006c442`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006c521`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006c680`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006c442`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006c521`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006c680`

## string_xrefs

- `0x18006c590`: `onecore\base\flighting\common\regvalet\registryjson.cpp`
- `0x18006c6a9`: `onecore\base\flighting\common\regvalet\registryjson.cpp`
- `0x18006c702`: `onecore\base\flighting\common\regvalet\registryjson.cpp`
- `0x18006c494`: `FullPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall RegistryJson::RuntimeClassInitialize(
        RegistryJson *this,
        struct Windows::Data::Json::IJsonObject *a2,
        HKEY a3,
        unsigned __int16 *a4)
{
  int (__fastcall *v8)(struct Windows::Data::Json::IJsonObject *, __int64, HSTRING *); // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  int v10; // ebx
  __int64 v11; // r9
  __int64 v12; // rdx
  int (__fastcall *v13)(struct Windows::Data::Json::IJsonObject *, __int64, char *); // rbx
  int (__fastcall *v14)(struct Windows::Data::Json::IJsonObject *, __int64, HSTRING *); // rbx
  PCWSTR v15; // rax
  unsigned __int64 v16; // rcx
  int (__fastcall *v17)(struct Windows::Data::Json::IJsonObject *, __int64, char *); // rdi
  bool v18; // al
  int (__fastcall *v19)(struct Windows::Data::Json::IJsonObject *, __int64, HSTRING *); // rbx
  const unsigned __int16 *v20; // rax
  int v21; // eax
  void (__fastcall *v22)(struct Windows::Data::Json::IJsonObject *, __int64, char *); // rdi
  int (__fastcall *v23)(struct Windows::Data::Json::IJsonObject *, __int64, char *); // rbx
  int (__fastcall *v24)(struct Windows::Data::Json::IJsonObject *, __int64, char *); // rbx
  int v26; // [rsp+20h] [rbp-E0h]
  HSTRING v27; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING v28; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING string; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v31; // [rsp+60h] [rbp-A0h]
  unsigned __int16 v32[520]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4C8h] [rbp+3C8h]

  v28 = (HSTRING)a4;
  string = 0;
  v8 = *(int (__fastcall **)(struct Windows::Data::Json::IJsonObject *, __int64, HSTRING *))(*(_QWORD *)a2 + 80LL);
  WindowsDeleteString(0);
  string = 0;
  v31 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"HKey", 5u, 4u);
  if ( v8(a2, v31, &string) < 0 )
  {
    *((_QWORD *)this + 2) = a3;
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    if ( !RegValet::StringType::ToRootHive((HKEY *)this + 2, StringRawBuffer) )
    {
      v10 = -2147467259;
      v11 = 2147500037LL;
      v12 = 89;
LABEL_22:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecore\\base\\flighting\\common\\regvalet\\registryjson.cpp",
        (const char *)v11,
        v26);
      goto LABEL_29;
    }
  }
  v13 = *(int (__fastcall **)(struct Windows::Data::Json::IJsonObject *, __int64, char *))(*(_QWORD *)a2 + 80LL);
  WindowsDeleteString(*((HSTRING *)this + 3));
  *((_QWORD *)this + 3) = 0;
  v31 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"FullPath", 9u, 8u);
  if ( v13(a2, v31, (char *)this + 24) < 0 )
  {
    if ( a4 )
    {
      if ( *a4 )
      {
        v21 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>((char *)this + 24, &v28);
        v10 = v21;
        if ( v21 < 0 )
        {
          v11 = (unsigned int)v21;
          v12 = 121;
          goto LABEL_22;
        }
      }
    }
  }
  else
  {
    v28 = 0;
    v14 = *(int (__fastcall **)(struct Windows::Data::Json::IJsonObject *, __int64, HSTRING *))(*(_QWORD *)a2 + 80LL);
    WindowsDeleteString(0);
    v28 = 0;
    v31 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"PersistedSourceId", 0x12u, 0x11u);
    if ( v14(a2, v31, &v28) >= 0 )
    {
      v15 = WindowsGetStringRawBuffer(v28, 0);
      v26 = 0;
      if ( !(unsigned int)GetPersistedRegistryLocationW(v15, 0, v32, 1040) )
      {
        LODWORD(v27) = 0;
        v16 = -1;
        do
          ++v16;
        while ( v32[v16] );
        v10 = ULongLongToUInt(v16, (unsigned int *)&v27);
        if ( v10 < 0
          || (v10 = Microsoft::WRL::Wrappers::HString::Set((RegistryJson *)((char *)this + 24), v32, (unsigned int)v27),
              v10 < 0) )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x6E,
            (unsigned int)"onecore\\base\\flighting\\common\\regvalet\\registryjson.cpp",
            (const char *)(unsigned int)v10,
            0);
          WindowsDeleteString(v28);
          v28 = 0;
          goto LABEL_29;
        }
      }
    }
    WindowsDeleteString(v28);
  }
  *((_DWORD *)this + 12) = 0;
  v17 = *(int (__fastcall **)(struct Windows::Data::Json::IJsonObject *, __int64, char *))(*(_QWORD *)a2 + 80LL);
  WindowsDeleteString(*((HSTRING *)this + 4));
  *((_QWORD *)this + 4) = 0;
  v31 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"ValueName", 0xAu, 9u);
  v18 = v17(a2, v31, (char *)this + 32) >= 0;
  *((_BYTE *)this + 52) = v18;
  if ( v18 )
  {
    v27 = 0;
    v19 = *(int (__fastcall **)(struct Windows::Data::Json::IJsonObject *, __int64, HSTRING *))(*(_QWORD *)a2 + 80LL);
    WindowsDeleteString(0);
    v27 = 0;
    v31 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"RegValueType", 0xDu, 0xCu);
    if ( v19(a2, v31, &v27) >= 0 )
    {
      v20 = WindowsGetStringRawBuffer(v27, 0);
      if ( !RegValet::StringType::ToValueType((unsigned int *)this + 12, v20) )
      {
        v10 = -2147467259;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x97,
          (unsigned int)"onecore\\base\\flighting\\common\\regvalet\\registryjson.cpp",
          (const char *)0x80004005LL,
          v26);
        WindowsDeleteString(v27);
        v27 = 0;
        goto LABEL_29;
      }
    }
    WindowsDeleteString(v27);
  }
  v22 = *(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *, __int64, char *))(*(_QWORD *)a2 + 80LL);
  WindowsDeleteString(*((HSTRING *)this + 5));
  *((_QWORD *)this + 5) = 0;
  v31 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"EncodingType", 0xDu, 0xCu);
  v22(a2, v31, (char *)this + 40);
  v23 = *(int (__fastcall **)(struct Windows::Data::Json::IJsonObject *, __int64, char *))(*(_QWORD *)a2 + 96LL);
  v31 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"IfExists", 9u, 8u);
  if ( v23(a2, v31, (char *)this + 53) < 0 )
    *((_BYTE *)this + 53) = 0;
  v24 = *(int (__fastcall **)(struct Windows::Data::Json::IJsonObject *, __int64, char *))(*(_QWORD *)a2 + 96LL);
  v31 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"IgnoreWild", 0xBu, 0xAu);
  if ( v24(a2, v31, (char *)this + 54) < 0 )
    *((_BYTE *)this + 54) = 0;
  v10 = 0;
LABEL_29:
  WindowsDeleteString(string);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18006c3a8  push    rbp
0x18006c3aa  push    rbx
0x18006c3ab  push    rsi
0x18006c3ac  push    rdi
0x18006c3ad  push    r12
0x18006c3af  push    r14
0x18006c3b1  push    r15
0x18006c3b3  lea     rbp, [rsp-390h]
0x18006c3bb  sub     rsp, 490h
0x18006c3c2  mov     rax, cs:__security_cookie
0x18006c3c9  xor     rax, rsp
0x18006c3cc  mov     [rbp+3C0h+var_40], rax
0x18006c3d3  mov     r14, r9
0x18006c3d6  mov     rdi, r8
0x18006c3d9  mov     rsi, rdx
0x18006c3dc  mov     r15, rcx
0x18006c3df  mov     [rsp+4C0h+var_488], r9
0x18006c3e4  xor     r12d, r12d
0x18006c3e7  mov     [rsp+4C0h+string], r12
0x18006c3ec  mov     rax, [rdx]
0x18006c3ef  mov     rbx, [rax+50h]
0x18006c3f3  xor     ecx, ecx; string
0x18006c3f5  call    cs:__imp_WindowsDeleteString
0x18006c3fb  mov     [rsp+4C0h+string], r12
0x18006c400  mov     [rsp+4C0h+var_460], r12
0x18006c405  lea     r9d, [r12+4]; unsigned int
0x18006c40a  lea     r8d, [r12+5]; unsigned int
0x18006c40f  lea     rdx, ?c_jsonRegHKey@RegistryJson@@0QBGB; "HKey"
0x18006c416  lea     rcx, [rsp+4C0h+hstringHeader]; hstringHeader
0x18006c41b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18006c420  nop
0x18006c421  lea     r8, [rsp+4C0h+string]
0x18006c426  mov     rdx, [rsp+4C0h+var_460]
0x18006c42b  mov     rcx, rsi
0x18006c42e  mov     rax, rbx
0x18006c431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c436  nop
0x18006c437  test    eax, eax
0x18006c439  js      short loc_18006C46A
0x18006c43b  xor     edx, edx; length
0x18006c43d  mov     rcx, [rsp+4C0h+string]; string
0x18006c442  call    cs:__imp_WindowsGetStringRawBuffer
0x18006c448  mov     rdx, rax; unsigned __int16 *
0x18006c44b  lea     rcx, [r15+10h]; HKEY *
0x18006c44f  call    ?ToRootHive@StringType@RegValet@@SA_NPEAPEAUHKEY__@@PEBG@Z; RegValet::StringType::ToRootHive(HKEY__ * *,ushort const *)
0x18006c454  cmp     al, 1
0x18006c456  jz      short loc_18006C46E
0x18006c458  mov     ebx, 80004005h
0x18006c45d  mov     r9d, ebx
0x18006c460  lea     edx, [r12+59h]
0x18006c465  jmp     loc_18006C702
0x18006c46a  mov     [r15+10h], rdi
0x18006c46e  mov     rax, [rsi]
0x18006c471  mov     rbx, [rax+50h]
0x18006c475  lea     rdi, [r15+18h]
0x18006c479  mov     rcx, [rdi]; string
0x18006c47c  call    cs:__imp_WindowsDeleteString
0x18006c482  mov     [rdi], r12
0x18006c485  mov     [rsp+4C0h+var_460], r12
0x18006c48a  mov     r9d, 8; unsigned int
0x18006c490  lea     r8d, [r9+1]; unsigned int
0x18006c494  lea     rdx, ?c_jsonRegFullPath@RegistryJson@@0QBGB; "FullPath"
0x18006c49b  lea     rcx, [rsp+4C0h+hstringHeader]; hstringHeader
0x18006c4a0  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18006c4a5  nop
0x18006c4a6  mov     r8, rdi
0x18006c4a9  mov     rdx, [rsp+4C0h+var_460]
0x18006c4ae  mov     rcx, rsi
0x18006c4b1  mov     rax, rbx
0x18006c4b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c4b9  nop
0x18006c4ba  test    eax, eax
0x18006c4bc  js      loc_18006C6D0
0x18006c4c2  mov     [rsp+4C0h+var_488], r12
0x18006c4c7  mov     rax, [rsi]
0x18006c4ca  mov     rbx, [rax+50h]
0x18006c4ce  xor     ecx, ecx; string
0x18006c4d0  call    cs:__imp_WindowsDeleteString
0x18006c4d6  mov     [rsp+4C0h+var_488], r12
0x18006c4db  mov     [rsp+4C0h+var_460], r12
0x18006c4e0  mov     r9d, 11h; unsigned int
0x18006c4e6  lea     r8d, [r9+1]; unsigned int
0x18006c4ea  lea     rdx, ?c_jsonPersistedSourceId@RegistryJson@@0QBGB; "PersistedSourceId"
0x18006c4f1  lea     rcx, [rsp+4C0h+hstringHeader]; hstringHeader
0x18006c4f6  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18006c4fb  nop
0x18006c4fc  lea     r8, [rsp+4C0h+var_488]
0x18006c501  mov     rdx, [rsp+4C0h+var_460]
0x18006c506  mov     rcx, rsi
0x18006c509  mov     rax, rbx
0x18006c50c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c511  nop
0x18006c512  test    eax, eax
0x18006c514  js      loc_18006C5B7
0x18006c51a  xor     edx, edx; length
0x18006c51c  mov     rcx, [rsp+4C0h+var_488]; string
0x18006c521  call    cs:__imp_WindowsGetStringRawBuffer
0x18006c527  mov     qword ptr [rsp+4C0h+var_4A0], r12; int
0x18006c52c  mov     r9d, 410h
0x18006c532  lea     r8, [rsp+4C0h+var_450]
0x18006c537  xor     edx, edx
0x18006c539  mov     rcx, rax
0x18006c53c  call    cs:__imp_GetPersistedRegistryLocationW
0x18006c542  test    eax, eax
0x18006c544  jnz     short loc_18006C5B7
0x18006c546  mov     dword ptr [rsp+4C0h+var_490], r12d
0x18006c54b  lea     rax, [rsp+4C0h+var_450]
0x18006c550  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18006c554  inc     rcx; unsigned __int64
0x18006c557  cmp     [rax+rcx*2], r12w
0x18006c55c  jnz     short loc_18006C554
0x18006c55e  lea     rdx, [rsp+4C0h+var_490]; unsigned int *
0x18006c563  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18006c568  mov     ebx, eax
0x18006c56a  test    eax, eax
0x18006c56c  js      short loc_18006C586
0x18006c56e  mov     r8d, dword ptr [rsp+4C0h+var_490]; unsigned int
0x18006c573  lea     rdx, [rsp+4C0h+var_450]; unsigned __int16 *
0x18006c578  mov     rcx, rdi; this
0x18006c57b  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18006c580  mov     ebx, eax
0x18006c582  test    eax, eax
0x18006c584  jns     short loc_18006C5B7
0x18006c586  mov     rcx, [rbp+3C8h]; this
0x18006c58d  mov     r9d, ebx; char *
0x18006c590  lea     r8, aOnecoreBaseFli_17; "onecore\\base\\flighting\\common\\regva"...
0x18006c597  mov     edx, 6Eh ; 'n'; void *
0x18006c59c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c5a1  nop
0x18006c5a2  mov     rcx, [rsp+4C0h+var_488]; string
0x18006c5a7  call    cs:__imp_WindowsDeleteString
0x18006c5ad  mov     [rsp+4C0h+var_488], r12
0x18006c5b2  jmp     loc_18006C7FE
0x18006c5b7  mov     rcx, [rsp+4C0h+var_488]; string
0x18006c5bc  call    cs:__imp_WindowsDeleteString
0x18006c5c2  mov     [r15+30h], r12d
0x18006c5c6  mov     rax, [rsi]
0x18006c5c9  mov     rdi, [rax+50h]
0x18006c5cd  lea     rbx, [r15+20h]
0x18006c5d1  mov     rcx, [rbx]; string
0x18006c5d4  call    cs:__imp_WindowsDeleteString
0x18006c5da  mov     [rbx], r12
0x18006c5dd  mov     [rsp+4C0h+var_460], r12
0x18006c5e2  mov     r9d, 9; unsigned int
0x18006c5e8  lea     r8d, [r9+1]; unsigned int
0x18006c5ec  lea     rdx, ?c_jsonRegValueName@RegistryJson@@0QBGB; "ValueName"
0x18006c5f3  lea     rcx, [rsp+4C0h+hstringHeader]; hstringHeader
0x18006c5f8  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18006c5fd  nop
0x18006c5fe  mov     r8, rbx
0x18006c601  mov     rdx, [rsp+4C0h+var_460]
0x18006c606  mov     rcx, rsi
0x18006c609  mov     rax, rdi
0x18006c60c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c611  nop
0x18006c612  shr     eax, 1Fh
0x18006c615  xor     al, 1
0x18006c617  mov     [r15+34h], al
0x18006c61b  jz      loc_18006C725
0x18006c621  mov     [rsp+4C0h+var_490], r12
0x18006c626  mov     rax, [rsi]
0x18006c629  mov     rbx, [rax+50h]
0x18006c62d  xor     ecx, ecx; string
0x18006c62f  call    cs:__imp_WindowsDeleteString
0x18006c635  mov     [rsp+4C0h+var_490], r12
0x18006c63a  mov     [rsp+4C0h+var_460], r12
0x18006c63f  mov     r9d, 0Ch; unsigned int
0x18006c645  lea     r8d, [r9+1]; unsigned int
0x18006c649  lea     rdx, ?c_jsonRegValueType@RegistryJson@@0QBGB; "RegValueType"
0x18006c650  lea     rcx, [rsp+4C0h+hstringHeader]; hstringHeader
0x18006c655  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18006c65a  nop
0x18006c65b  lea     r8, [rsp+4C0h+var_490]
0x18006c660  mov     rdx, [rsp+4C0h+var_460]
0x18006c665  mov     rcx, rsi
0x18006c668  mov     rax, rbx
0x18006c66b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c670  nop
0x18006c671  test    eax, eax
0x18006c673  js      loc_18006C71A
0x18006c679  xor     edx, edx; length
0x18006c67b  mov     rcx, [rsp+4C0h+var_490]; string
0x18006c680  call    cs:__imp_WindowsGetStringRawBuffer
0x18006c686  mov     rdx, rax; unsigned __int16 *
0x18006c689  lea     rcx, [r15+30h]; unsigned int *
0x18006c68d  call    ?ToValueType@StringType@RegValet@@SA_NPEAKPEBG@Z; RegValet::StringType::ToValueType(ulong *,ushort const *)
0x18006c692  test    al, al
0x18006c694  jnz     loc_18006C71A
0x18006c69a  mov     rcx, [rbp+3C8h]; this
0x18006c6a1  mov     ebx, 80004005h
0x18006c6a6  mov     r9d, ebx; char *
0x18006c6a9  lea     r8, aOnecoreBaseFli_17; "onecore\\base\\flighting\\common\\regva"...
0x18006c6b0  mov     edx, 97h; void *
0x18006c6b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c6ba  nop
0x18006c6bb  mov     rcx, [rsp+4C0h+var_490]; string
0x18006c6c0  call    cs:__imp_WindowsDeleteString
0x18006c6c6  mov     [rsp+4C0h+var_490], r12
0x18006c6cb  jmp     loc_18006C7FE
0x18006c6d0  test    r14, r14
0x18006c6d3  jz      loc_18006C5C2
0x18006c6d9  cmp     [r14], r12w
0x18006c6dd  jz      loc_18006C5C2
0x18006c6e3  lea     rdx, [rsp+4C0h+var_488]
0x18006c6e8  mov     rcx, rdi
0x18006c6eb  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18006c6f0  mov     ebx, eax
0x18006c6f2  test    eax, eax
0x18006c6f4  jns     loc_18006C5C2
0x18006c6fa  mov     r9d, eax; char *
0x18006c6fd  mov     edx, 79h ; 'y'; void *
0x18006c702  lea     r8, aOnecoreBaseFli_17; "onecore\\base\\flighting\\common\\regva"...
0x18006c709  mov     rcx, [rbp+3C8h]; this
0x18006c710  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c715  jmp     loc_18006C7FE
0x18006c71a  mov     rcx, [rsp+4C0h+var_490]; string
0x18006c71f  call    cs:__imp_WindowsDeleteString
0x18006c725  mov     rax, [rsi]
0x18006c728  mov     rdi, [rax+50h]
0x18006c72c  lea     rbx, [r15+28h]
0x18006c730  mov     rcx, [rbx]; string
0x18006c733  call    cs:__imp_WindowsDeleteString
0x18006c739  mov     [rbx], r12
0x18006c73c  mov     [rsp+4C0h+var_460], r12
0x18006c741  mov     r9d, 0Ch; unsigned int
0x18006c747  lea     r8d, [r9+1]; unsigned int
0x18006c74b  lea     rdx, ?c_jsonEncodingType@RegistryJson@@0QBGB; "EncodingType"
0x18006c752  lea     rcx, [rsp+4C0h+hstringHeader]; hstringHeader
0x18006c757  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18006c75c  nop
0x18006c75d  mov     r8, rbx
0x18006c760  mov     rdx, [rsp+4C0h+var_460]
0x18006c765  mov     rcx, rsi
0x18006c768  mov     rax, rdi
0x18006c76b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c770  nop
0x18006c771  mov     rax, [rsi]
0x18006c774  mov     rbx, [rax+60h]
0x18006c778  mov     [rsp+4C0h+var_460], r12
0x18006c77d  mov     r9d, 8; unsigned int
0x18006c783  lea     r8d, [r9+1]; unsigned int
0x18006c787  lea     rdx, ?c_jsonRegExists@RegistryJson@@0QBGB; "IfExists"
0x18006c78e  lea     rcx, [rsp+4C0h+hstringHeader]; hstringHeader
0x18006c793  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18006c798  nop
0x18006c799  lea     r8, [r15+35h]
0x18006c79d  mov     rdx, [rsp+4C0h+var_460]
0x18006c7a2  mov     rcx, rsi
0x18006c7a5  mov     rax, rbx
0x18006c7a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c7ad  nop
0x18006c7ae  test    eax, eax
0x18006c7b0  jns     short loc_18006C7B6
0x18006c7b2  mov     [r15+35h], r12b
0x18006c7b6  mov     rax, [rsi]
0x18006c7b9  mov     rbx, [rax+60h]
0x18006c7bd  mov     [rsp+4C0h+var_460], r12
0x18006c7c2  mov     r9d, 0Ah; unsigned int
0x18006c7c8  lea     r8d, [r9+1]; unsigned int
0x18006c7cc  lea     rdx, ?c_jsonIgnoreWild@RegistryJson@@0QBGB; "IgnoreWild"
0x18006c7d3  lea     rcx, [rsp+4C0h+hstringHeader]; hstringHeader
0x18006c7d8  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18006c7dd  nop
0x18006c7de  lea     r8, [r15+36h]
0x18006c7e2  mov     rdx, [rsp+4C0h+var_460]
0x18006c7e7  mov     rcx, rsi
0x18006c7ea  mov     rax, rbx
0x18006c7ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c7f2  nop
0x18006c7f3  test    eax, eax
0x18006c7f5  jns     short loc_18006C7FB
0x18006c7f7  mov     [r15+36h], r12b
0x18006c7fb  mov     ebx, r12d
0x18006c7fe  mov     rcx, [rsp+4C0h+string]; string
0x18006c803  call    cs:__imp_WindowsDeleteString
0x18006c809  mov     eax, ebx
0x18006c80b  mov     rcx, [rbp+3C0h+var_40]
0x18006c812  xor     rcx, rsp; StackCookie
0x18006c815  call    __security_check_cookie
0x18006c81a  add     rsp, 490h
0x18006c821  pop     r15
0x18006c823  pop     r14
0x18006c825  pop     r12
0x18006c827  pop     rdi
0x18006c828  pop     rsi
0x18006c829  pop     rbx
0x18006c82a  pop     rbp
0x18006c82b  retn
```
