# ValidateLockAppHasExtension(ushort const *,ushort const *)

- ea: `0x180033ab0`
- end: `0x180033d15`
- name: `?ValidateLockAppHasExtension@@YAJPEBG0@Z`
- size: `613`
- prototype: `__int64 __fastcall(PCWSTR sourceString, PCWSTR)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180033480`

## callees

- `0x180017dec`
- `0x180033ab0`
- `0x180033f8c`
- `0x18005d488`
- `0x18006c000`
- `0x18009d010`

## import_xrefs

- `KERNEL32!RaiseException` at `0x180033b1a`
- `KERNEL32!RaiseException` at `0x180033bc3`
- `KERNEL32!RaiseException` at `0x180033c3a`
- `KERNEL32!RaiseException` at `0x180033c7c`
- `KERNEL32!RaiseException` at `0x180033b1a`
- `KERNEL32!RaiseException` at `0x180033bc3`
- `KERNEL32!RaiseException` at `0x180033c3a`
- `KERNEL32!RaiseException` at `0x180033c7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180033afa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180033bd7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180033c4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180033c8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180033afa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180033bd7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180033c4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180033c8f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180033b3b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180033b3b`

## string_xrefs

- `0x180033aef`: `lockframework.LockFrameworkBroker`

## pseudocode

```c
__int64 __fastcall ValidateLockAppHasExtension(PCWSTR sourceString, PCWSTR a2)
{
  HSTRING v4; // rbx
  int ActivationFactory; // ebx
  __int64 v6; // rdx
  __int64 v7; // rcx
  unsigned __int64 v8; // rbx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, HSTRING, _BYTE *); // r14
  int v11; // eax
  __int64 v12; // r9
  __int64 v13; // rdx
  __int64 v14; // r15
  unsigned __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, HSTRING, HSTRING, _BYTE *); // r12
  HSTRING v17; // rdi
  int v19; // [rsp+20h] [rbp-49h]
  _BYTE v20[8]; // [rsp+30h] [rbp-39h] BYREF
  __int64 v21; // [rsp+38h] [rbp-31h] BYREF
  UINT32 length; // [rsp+40h] [rbp-29h] BYREF
  HSTRING string; // [rsp+48h] [rbp-21h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-19h] BYREF
  HSTRING v25; // [rsp+68h] [rbp-1h] BYREF
  HSTRING_HEADER v26; // [rsp+70h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v21 = 0;
  if ( WindowsCreateStringReference(L"lockframework.LockFrameworkBroker", 0x21u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v4 = string;
  Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v21);
  ActivationFactory = RoGetActivationFactory(v4, &GUID_28fe486d_6853_4c62_81ab_4bdc6b9c1a9d, &v21);
  if ( ActivationFactory < 0 )
  {
    v6 = 29;
    goto LABEL_5;
  }
  v8 = -1;
  v20[0] = 0;
  if ( !sourceString )
  {
    v9 = v21;
    length = 0;
    v10 = *(__int64 (__fastcall **)(__int64, HSTRING, _BYTE *))(*(_QWORD *)v21 + 64LL);
    do
      ++v8;
    while ( a2[v8] );
    if ( (int)ULongLongToULong(v8, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(a2, length, &hstringHeader, &string);
    v11 = v10(v9, string, v20);
    ActivationFactory = v11;
    if ( v11 < 0 )
    {
      v12 = (unsigned int)v11;
      v13 = 35;
      goto LABEL_26;
    }
LABEL_24:
    if ( v20[0] )
    {
      ActivationFactory = 0;
      goto LABEL_28;
    }
    ActivationFactory = -2147418113;
    v13 = 43;
    v12 = 2147549183LL;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"shell\\lib\\lockapphostdata\\lockapptype.cpp",
      (const char *)v12,
      v19);
LABEL_28:
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v21);
    return (unsigned int)ActivationFactory;
  }
  v14 = v21;
  v15 = -1;
  v16 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, _BYTE *))(*(_QWORD *)v21 + 88LL);
  do
    ++v15;
  while ( a2[v15] );
  if ( v15 > 0xFFFFFFFF )
  {
    LODWORD(v15) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(a2, v15, &hstringHeader, &string);
  v17 = string;
  do
    ++v8;
  while ( sourceString[v8] );
  if ( v8 > 0xFFFFFFFF )
  {
    LODWORD(v8) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(sourceString, v8, &v26, &v25);
  ActivationFactory = v16(v14, v25, v17, v20);
  if ( ActivationFactory >= 0 )
    goto LABEL_24;
  v6 = 39;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"shell\\lib\\lockapphostdata\\lockapptype.cpp",
    (const char *)(unsigned int)ActivationFactory,
    v19);
  v7 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180033ab0  mov     [rsp-8+arg_10], rbx
0x180033ab5  push    rbp
0x180033ab6  push    rsi
0x180033ab7  push    rdi
0x180033ab8  push    r12
0x180033aba  push    r13
0x180033abc  push    r14
0x180033abe  push    r15
0x180033ac0  lea     rbp, [rsp-27h]
0x180033ac5  sub     rsp, 90h
0x180033acc  mov     rax, cs:__security_cookie
0x180033ad3  xor     rax, rsp
0x180033ad6  mov     [rbp+57h+var_38], rax
0x180033ada  xor     r13d, r13d
0x180033add  lea     r9, [rbp+57h+string]; string
0x180033ae1  mov     rsi, rdx
0x180033ae4  mov     [rbp+57h+var_88], r13
0x180033ae8  mov     r14, rcx
0x180033aeb  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180033aef  lea     rcx, ?RuntimeClass_lockframework_LockFrameworkBroker@@3QBGB; "lockframework.LockFrameworkBroker"
0x180033af6  lea     edx, [r13+21h]; length
0x180033afa  call    cs:__imp_WindowsCreateStringReference
0x180033b00  lea     r15d, [r13+1]
0x180033b04  mov     r12d, 0C000000Dh
0x180033b0a  test    eax, eax
0x180033b0c  jns     short loc_180033B20
0x180033b0e  xor     r9d, r9d; lpArguments
0x180033b11  xor     r8d, r8d; nNumberOfArguments
0x180033b14  mov     edx, r15d; dwExceptionFlags
0x180033b17  mov     ecx, r12d; dwExceptionCode
0x180033b1a  call    cs:__imp_RaiseException
0x180033b20  mov     rbx, [rbp+57h+string]
0x180033b24  lea     rcx, [rbp+57h+var_88]
0x180033b28  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x180033b2d  lea     r8, [rbp+57h+var_88]
0x180033b31  mov     rcx, rbx
0x180033b34  lea     rdx, _GUID_28fe486d_6853_4c62_81ab_4bdc6b9c1a9d
0x180033b3b  call    cs:__imp_RoGetActivationFactory
0x180033b41  mov     ebx, eax
0x180033b43  test    eax, eax
0x180033b45  jns     short loc_180033B81
0x180033b47  mov     edx, 1Dh; void *
0x180033b4c  mov     rcx, [rbp+5Fh]; this
0x180033b50  lea     r8, aShellLibLockap; "shell\\lib\\lockapphostdata\\lockapptyp"...
0x180033b57  mov     r9d, ebx; char *
0x180033b5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033b5f  mov     rcx, [rbp+57h+var_88]
0x180033b63  test    rcx, rcx
0x180033b66  jz      loc_180033CEC
0x180033b6c  mov     [rbp+57h+var_88], r13
0x180033b70  mov     rax, [rcx]
0x180033b73  mov     rax, [rax+10h]
0x180033b77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033b7c  jmp     loc_180033CEC
0x180033b81  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180033b85  mov     [rbp+57h+var_90], r13b
0x180033b89  test    r14, r14
0x180033b8c  jnz     short loc_180033C07
0x180033b8e  mov     rdi, [rbp+57h+var_88]
0x180033b92  mov     [rbp+57h+length], r13d
0x180033b96  mov     rax, [rdi]
0x180033b99  mov     r14, [rax+40h]
0x180033b9d  inc     rbx
0x180033ba0  cmp     [rsi+rbx*2], r13w
0x180033ba5  jnz     short loc_180033B9D
0x180033ba7  lea     rdx, [rbp+57h+length]; unsigned int *
0x180033bab  mov     rcx, rbx; unsigned __int64
0x180033bae  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180033bb3  test    eax, eax
0x180033bb5  jns     short loc_180033BC9
0x180033bb7  xor     r9d, r9d; lpArguments
0x180033bba  xor     r8d, r8d; nNumberOfArguments
0x180033bbd  mov     edx, r15d; dwExceptionFlags
0x180033bc0  mov     ecx, r12d; dwExceptionCode
0x180033bc3  call    cs:__imp_RaiseException
0x180033bc9  mov     edx, [rbp+57h+length]; length
0x180033bcc  lea     r9, [rbp+57h+string]; string
0x180033bd0  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180033bd4  mov     rcx, rsi; sourceString
0x180033bd7  call    cs:__imp_WindowsCreateStringReference
0x180033bdd  mov     rdx, [rbp+57h+string]
0x180033be1  lea     r8, [rbp+57h+var_90]
0x180033be5  mov     rcx, rdi
0x180033be8  mov     rax, r14
0x180033beb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033bf0  mov     ebx, eax
0x180033bf2  test    eax, eax
0x180033bf4  jns     loc_180033CBB
0x180033bfa  mov     r9d, eax
0x180033bfd  mov     edx, 23h ; '#'
0x180033c02  jmp     loc_180033CCE
0x180033c07  mov     r15, [rbp+57h+var_88]
0x180033c0b  mov     rdi, rbx
0x180033c0e  mov     rax, [r15]
0x180033c11  mov     r12, [rax+58h]
0x180033c15  inc     rdi
0x180033c18  cmp     [rsi+rdi*2], r13w
0x180033c1d  jnz     short loc_180033C15
0x180033c1f  mov     eax, 0FFFFFFFFh
0x180033c24  cmp     rdi, rax
0x180033c27  jbe     short loc_180033C40
0x180033c29  xor     r9d, r9d; lpArguments
0x180033c2c  xor     r8d, r8d; nNumberOfArguments
0x180033c2f  mov     ecx, 0C000000Dh; dwExceptionCode
0x180033c34  mov     edi, eax
0x180033c36  lea     edx, [r9+1]; dwExceptionFlags
0x180033c3a  call    cs:__imp_RaiseException
0x180033c40  lea     r9, [rbp+57h+string]; string
0x180033c44  mov     edx, edi; length
0x180033c46  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180033c4a  mov     rcx, rsi; sourceString
0x180033c4d  call    cs:__imp_WindowsCreateStringReference
0x180033c53  mov     rdi, [rbp+57h+string]
0x180033c57  inc     rbx
0x180033c5a  cmp     [r14+rbx*2], r13w
0x180033c5f  jnz     short loc_180033C57
0x180033c61  mov     eax, 0FFFFFFFFh
0x180033c66  cmp     rbx, rax
0x180033c69  jbe     short loc_180033C82
0x180033c6b  xor     r9d, r9d; lpArguments
0x180033c6e  xor     r8d, r8d; nNumberOfArguments
0x180033c71  mov     ecx, 0C000000Dh; dwExceptionCode
0x180033c76  mov     ebx, eax
0x180033c78  lea     edx, [r9+1]; dwExceptionFlags
0x180033c7c  call    cs:__imp_RaiseException
0x180033c82  lea     r9, [rbp+57h+var_58]; string
0x180033c86  mov     edx, ebx; length
0x180033c88  lea     r8, [rbp+57h+var_50]; hstringHeader
0x180033c8c  mov     rcx, r14; sourceString
0x180033c8f  call    cs:__imp_WindowsCreateStringReference
0x180033c95  mov     rdx, [rbp+57h+var_58]
0x180033c99  lea     r9, [rbp+57h+var_90]
0x180033c9d  mov     r8, rdi
0x180033ca0  mov     rcx, r15
0x180033ca3  mov     rax, r12
0x180033ca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033cab  mov     ebx, eax
0x180033cad  test    eax, eax
0x180033caf  jns     short loc_180033CBB
0x180033cb1  mov     edx, 27h ; '''
0x180033cb6  jmp     loc_180033B4C
0x180033cbb  cmp     [rbp+57h+var_90], r13b
0x180033cbf  jnz     short loc_180033CE0
0x180033cc1  mov     ebx, 8000FFFFh
0x180033cc6  mov     edx, 2Bh ; '+'; void *
0x180033ccb  mov     r9d, ebx; char *
0x180033cce  mov     rcx, [rbp+5Fh]; this
0x180033cd2  lea     r8, aShellLibLockap; "shell\\lib\\lockapphostdata\\lockapptyp"...
0x180033cd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033cde  jmp     short loc_180033CE3
0x180033ce0  mov     ebx, r13d
0x180033ce3  lea     rcx, [rbp+57h+var_88]
0x180033ce7  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x180033cec  mov     eax, ebx
0x180033cee  mov     rcx, [rbp+57h+var_38]
0x180033cf2  xor     rcx, rsp; StackCookie
0x180033cf5  call    __security_check_cookie
0x180033cfa  mov     rbx, [rsp+0C0h+arg_10]
0x180033d02  add     rsp, 90h
0x180033d09  pop     r15
0x180033d0b  pop     r14
0x180033d0d  pop     r13
0x180033d0f  pop     r12
0x180033d11  pop     rdi
0x180033d12  pop     rsi
0x180033d13  pop     rbp
0x180033d14  retn
```
