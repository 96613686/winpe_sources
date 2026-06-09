# DevPlat::Shared::IsAllowedByEdpPolicy(void *,EDP_ENTERPRISE_CONTEXT *,bool *)

- ea: `0x180094314`
- end: `0x1800944d7`
- name: `?IsAllowedByEdpPolicy@Shared@DevPlat@@YAJPEAXPEAUEDP_ENTERPRISE_CONTEXT@@PEA_N@Z`
- size: `451`
- prototype: `__int64 __fastcall(PSID Sid, void *, struct EDP_ENTERPRISE_CONTEXT *, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800302b4`

## callees

- `0x18001a1f0`
- `0x180020ca0`
- `0x18006de78`
- `0x180094314`

## import_xrefs

- `msvcrt!wcstok_s` at `0x18009445e`
- `msvcrt!wcstok_s` at `0x18009445e`
- `ntdll!RtlFreeUnicodeString` at `0x18009448c`
- `ntdll!RtlFreeUnicodeString` at `0x1800944bb`
- `ntdll!RtlFreeUnicodeString` at `0x18009448c`
- `ntdll!RtlFreeUnicodeString` at `0x1800944bb`
- `ntdll!RtlConvertSidToUnicodeString` at `0x180094344`
- `ntdll!RtlConvertSidToUnicodeString` at `0x180094344`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180094382`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180094382`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009439c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009439c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800943ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800943ab`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009443a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009443a`
- `FeClient!EdpQueryDplEnforcedPolicyOwnerIds` at `0x1800943b8`
- `FeClient!EdpQueryDplEnforcedPolicyOwnerIds` at `0x1800943b8`
- `FeClient!EdpFree` at `0x1800943e9`
- `FeClient!EdpFree` at `0x180094475`
- `FeClient!EdpFree` at `0x1800943e9`
- `FeClient!EdpFree` at `0x180094475`

## pseudocode

```c
__int64 __fastcall DevPlat::Shared::IsAllowedByEdpPolicy(
        PSID Sid,
        void *a2,
        struct EDP_ENTERPRISE_CONTEXT *a3,
        bool *a4)
{
  NTSTATUS v6; // eax
  unsigned int v7; // ebx
  HRESULT v8; // eax
  HSTRING v9; // rbx
  PCWSTR StringRawBuffer; // rax
  int v11; // eax
  wchar_t *v12; // rcx
  unsigned int i; // ebx
  wchar_t *v14; // rdi
  BOOL bIgnoreCase; // [rsp+20h] [rbp-30h]
  HSTRING string; // [rsp+30h] [rbp-20h] BYREF
  wchar_t *Context; // [rsp+38h] [rbp-18h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  wchar_t *v21; // [rsp+90h] [rbp+40h] BYREF
  HSTRING v22; // [rsp+98h] [rbp+48h] BYREF

  *(_BYTE *)a3 = 0;
  UnicodeString = 0;
  v6 = RtlConvertSidToUnicodeString(&UnicodeString, Sid, 1u);
  if ( v6 < 0 )
  {
    v7 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x27,
           (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\shared\\utility\\edppolicyutil.cpp",
           (const char *)(unsigned int)v6,
           bIgnoreCase);
LABEL_24:
    RtlFreeUnicodeString(&UnicodeString);
    return v7;
  }
  v22 = 0;
  string = 0;
  v8 = WindowsCreateString(UnicodeString.Buffer, UnicodeString.Length >> 1, &string);
  v7 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\shared\\utility\\edppolicyutil.cpp",
      (const char *)(unsigned int)v8,
      bIgnoreCase);
LABEL_23:
    Windows::Internal::String::~String(&v22);
    goto LABEL_24;
  }
  v9 = string;
  v22 = string;
  WindowsDeleteString(0);
  v21 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(v9, 0);
  v11 = EdpQueryDplEnforcedPolicyOwnerIds(StringRawBuffer, &v21);
  v7 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x37,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\shared\\utility\\edppolicyutil.cpp",
      (const char *)(unsigned int)v11,
      bIgnoreCase);
    if ( v21 )
    {
      EdpFree();
      v21 = 0;
    }
    goto LABEL_23;
  }
  v12 = v21;
  if ( v21 )
  {
    if ( *v21 )
    {
      Context = 0;
      while ( 1 )
      {
        v14 = wcstok_s(v12, L"|", &Context);
        if ( !v14 )
          break;
        for ( i = 0; i < *(_DWORD *)(*(_QWORD *)a2 + 4LL); ++i )
        {
          if ( CompareStringOrdinal(
                 v14,
                 -1,
                 *(LPCWCH *)(*(_QWORD *)a2 + 16LL * i + 24),
                 *(unsigned __int16 *)(*(_QWORD *)a2 + 16LL * i + 16) >> 1,
                 1) == 2 )
          {
            *(_BYTE *)a3 = 1;
            break;
          }
        }
        if ( *(_BYTE *)a3 )
          break;
        v12 = 0;
      }
      v12 = v21;
    }
    if ( v12 )
    {
      EdpFree();
      v21 = 0;
    }
  }
  Windows::Internal::String::~String(&v22);
  RtlFreeUnicodeString(&UnicodeString);
  return 0;
}

```

## disassembly

```asm
0x180094314  mov     [rsp-28h+arg_0], rbx
0x180094319  push    rbp
0x18009431a  push    rsi
0x18009431b  push    rdi
0x18009431c  push    r14
0x18009431e  push    r15
0x180094320  mov     rbp, rsp
0x180094323  sub     rsp, 50h
0x180094327  mov     r14, rdx
0x18009432a  mov     rsi, r8
0x18009432d  xorps   xmm0, xmm0
0x180094330  mov     rdx, rcx; Sid
0x180094333  xor     r15d, r15d
0x180094336  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x18009433a  mov     [r8], r15b
0x18009433d  mov     r8b, 1; AllocateDestinationString
0x180094340  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x180094344  call    cs:__imp_RtlConvertSidToUnicodeString
0x18009434a  test    eax, eax
0x18009434c  jns     short loc_18009436C
0x18009434e  mov     rcx, [rbp+28h]; this
0x180094352  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180094359  mov     r9d, eax; char *
0x18009435c  lea     edx, [r15+27h]; void *
0x180094360  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180094365  mov     ebx, eax
0x180094367  jmp     loc_1800944B7
0x18009436c  movzx   edx, [rbp+UnicodeString.Length]
0x180094370  lea     r8, [rbp+string]; string
0x180094374  mov     rcx, [rbp+UnicodeString.Buffer]; sourceString
0x180094378  shr     edx, 1; length
0x18009437a  mov     [rbp+arg_18], r15
0x18009437e  mov     [rbp+string], r15
0x180094382  call    cs:__imp_WindowsCreateString
0x180094388  mov     ebx, eax
0x18009438a  test    eax, eax
0x18009438c  js      loc_180094496
0x180094392  mov     rbx, [rbp+string]
0x180094396  xor     ecx, ecx; string
0x180094398  mov     [rbp+arg_18], rbx
0x18009439c  call    cs:__imp_WindowsDeleteString
0x1800943a2  xor     edx, edx; length
0x1800943a4  mov     [rbp+arg_10], r15
0x1800943a8  mov     rcx, rbx; string
0x1800943ab  call    cs:__imp_WindowsGetStringRawBuffer
0x1800943b1  mov     rcx, rax
0x1800943b4  lea     rdx, [rbp+arg_10]
0x1800943b8  call    cs:__imp_EdpQueryDplEnforcedPolicyOwnerIds
0x1800943be  mov     ebx, eax
0x1800943c0  test    eax, eax
0x1800943c2  jns     short loc_1800943F8
0x1800943c4  mov     rcx, [rbp+28h]; this
0x1800943c8  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800943cf  mov     r9d, eax; char *
0x1800943d2  mov     edx, 37h ; '7'; void *
0x1800943d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800943dc  mov     rcx, [rbp+arg_10]
0x1800943e0  test    rcx, rcx
0x1800943e3  jz      loc_1800944AE
0x1800943e9  call    cs:__imp_EdpFree
0x1800943ef  mov     [rbp+arg_10], r15
0x1800943f3  jmp     loc_1800944AE
0x1800943f8  mov     rcx, [rbp+arg_10]
0x1800943fc  test    rcx, rcx
0x1800943ff  jz      short loc_18009447F
0x180094401  cmp     [rcx], r15w
0x180094405  jz      short loc_180094470
0x180094407  mov     [rbp+Context], r15
0x18009440b  jmp     short loc_180094453
0x18009440d  mov     ebx, r15d
0x180094410  mov     rax, [r14]
0x180094413  cmp     ebx, [rax+4]
0x180094416  jnb     short loc_18009444C
0x180094418  mov     r8d, ebx
0x18009441b  or      edx, 0FFFFFFFFh; cchCount1
0x18009441e  add     r8, r8
0x180094421  mov     [rsp+50h+bIgnoreCase], 1; bIgnoreCase
0x180094429  mov     rcx, rdi; lpString1
0x18009442c  movzx   r9d, word ptr [rax+r8*8+10h]
0x180094432  mov     r8, [rax+r8*8+18h]; lpString2
0x180094437  shr     r9d, 1; cchCount2
0x18009443a  call    cs:__imp_CompareStringOrdinal
0x180094440  cmp     eax, 2
0x180094443  jz      short loc_180094449
0x180094445  inc     ebx
0x180094447  jmp     short loc_180094410
0x180094449  mov     byte ptr [rsi], 1
0x18009444c  cmp     [rsi], r15b
0x18009444f  jnz     short loc_18009446C
0x180094451  xor     ecx, ecx; String
0x180094453  lea     r8, [rbp+Context]; Context
0x180094457  lea     rdx, Delimiter; "|"
0x18009445e  call    cs:__imp_wcstok_s
0x180094464  mov     rdi, rax
0x180094467  test    rax, rax
0x18009446a  jnz     short loc_18009440D
0x18009446c  mov     rcx, [rbp+arg_10]
0x180094470  test    rcx, rcx
0x180094473  jz      short loc_18009447F
0x180094475  call    cs:__imp_EdpFree
0x18009447b  mov     [rbp+arg_10], r15
0x18009447f  lea     rcx, [rbp+arg_18]; this
0x180094483  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180094488  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x18009448c  call    cs:__imp_RtlFreeUnicodeString
0x180094492  xor     eax, eax
0x180094494  jmp     short loc_1800944C3
0x180094496  mov     rcx, [rbp+28h]; this
0x18009449a  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800944a1  mov     r9d, ebx; char *
0x1800944a4  mov     edx, 2Ah ; '*'; void *
0x1800944a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800944ae  lea     rcx, [rbp+arg_18]; this
0x1800944b2  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800944b7  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x1800944bb  call    cs:__imp_RtlFreeUnicodeString
0x1800944c1  mov     eax, ebx
0x1800944c3  mov     rbx, [rsp+50h+arg_0]
0x1800944cb  add     rsp, 50h
0x1800944cf  pop     r15
0x1800944d1  pop     r14
0x1800944d3  pop     rdi
0x1800944d4  pop     rsi
0x1800944d5  pop     rbp
0x1800944d6  retn
```
