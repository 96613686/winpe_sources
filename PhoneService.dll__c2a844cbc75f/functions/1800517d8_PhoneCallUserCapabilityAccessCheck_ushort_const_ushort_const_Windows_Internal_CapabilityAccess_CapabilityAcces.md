# PhoneCallUserCapabilityAccessCheck(ushort const *,ushort const *,Windows::Internal::CapabilityAccess::CapabilityAccessStatus *)

- ea: `0x1800517d8`
- end: `0x180051ac0`
- name: `?PhoneCallUserCapabilityAccessCheck@@YAJPEBG0PEAW4CapabilityAccessStatus@CapabilityAccess@Internal@Windows@@@Z`
- size: `744`
- prototype: `__int64 __fastcall(PCWSTR sourceString, PCWSTR, enum Windows::Internal::CapabilityAccess::CapabilityAccessStatus *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18001787c`

## callees

- `0x180006e94`
- `0x180051530`
- `0x1800517d8`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180051843`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800518f6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180051943`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180051988`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180051843`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800518f6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180051943`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180051988`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180051874`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180051874`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180051829`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180051909`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180051956`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005199b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180051829`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180051909`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180051956`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005199b`

## string_xrefs

- `0x180051822`: `Windows.Internal.CapabilityAccess.CapabilityAccess`

## pseudocode

```c
__int64 __fastcall PhoneCallUserCapabilityAccessCheck(
        PCWSTR sourceString,
        PCWSTR a2,
        enum Windows::Internal::CapabilityAccess::CapabilityAccessStatus *a3)
{
  __int64 v6; // rcx
  HSTRING v7; // rbx
  int ActivationFactory; // eax
  BackTraceCollection *v9; // rcx
  unsigned int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v15; // r14
  unsigned __int64 v16; // rdi
  unsigned __int64 v17; // rbx
  HSTRING v18; // r12
  unsigned __int64 v19; // rbx
  HSTRING v20; // rbx
  int v21; // eax
  __int64 v22; // rdx
  BackTraceCollection *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 v27; // rcx
  __int64 v28; // rcx
  int v29; // eax
  BackTraceCollection *v30; // rcx
  int v31; // eax
  BackTraceCollection *v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 (__fastcall *v35)(__int64, HSTRING, HSTRING, HSTRING, __int64 *); // [rsp+30h] [rbp-59h]
  HSTRING string; // [rsp+38h] [rbp-51h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-49h] BYREF
  HSTRING v38; // [rsp+58h] [rbp-31h] BYREF
  HSTRING_HEADER v39; // [rsp+60h] [rbp-29h] BYREF
  HSTRING v40; // [rsp+78h] [rbp-11h] BYREF
  HSTRING_HEADER v41; // [rsp+80h] [rbp-9h] BYREF
  __int64 v42; // [rsp+98h] [rbp+Fh] BYREF
  __int64 v43; // [rsp+A0h] [rbp+17h] BYREF

  *(_DWORD *)a3 = 0;
  v42 = 0;
  if ( WindowsCreateStringReference(
         L"Windows.Internal.CapabilityAccess.CapabilityAccess",
         0x32u,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v6 = v42;
  v7 = string;
  if ( v42 )
  {
    v42 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  ActivationFactory = RoGetActivationFactory(v7, &GUID_518f3880_4e5c_4524_ab03_cd01336b2178, &v42);
  v10 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    BackTraceCollection::Capture(v9, ActivationFactory);
    Log_HREvent_11(v10, v11, v12, 48);
    v13 = v42;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    return v10;
  }
  v15 = v42;
  v16 = -1;
  v43 = 0;
  v17 = -1;
  v35 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, HSTRING, __int64 *))(*(_QWORD *)v42 + 48LL);
  do
    ++v17;
  while ( a2[v17] );
  if ( v17 > 0xFFFFFFFF )
  {
    LODWORD(v17) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(a2, v17, &hstringHeader, &string);
  v18 = string;
  v19 = -1;
  do
    ++v19;
  while ( c_szCapabilityPhoneCall[v19] );
  if ( v19 > 0xFFFFFFFF )
  {
    LODWORD(v19) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(c_szCapabilityPhoneCall, v19, &v39, &v38);
  v20 = v38;
  do
    ++v16;
  while ( sourceString[v16] );
  if ( v16 > 0xFFFFFFFF )
  {
    LODWORD(v16) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(sourceString, v16, &v41, &v40);
  v21 = v35(v15, v40, v20, v18, &v43);
  v10 = v21;
  if ( v21 < 0 )
  {
    BackTraceCollection::Capture(v23, v21);
    v26 = 55;
LABEL_23:
    Log_HREvent_11(v10, v24, v25, v26);
    v27 = v43;
    if ( v43 )
    {
      v43 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    }
    v28 = v42;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    }
    return v10;
  }
  LOBYTE(v22) = 1;
  v29 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v43 + 88LL))(v43, v22);
  v10 = v29;
  if ( v29 < 0 )
  {
    BackTraceCollection::Capture(v30, v29);
    v26 = 58;
    goto LABEL_23;
  }
  v31 = (*(__int64 (__fastcall **)(__int64, enum Windows::Internal::CapabilityAccess::CapabilityAccessStatus *))(*(_QWORD *)v43 + 152LL))(
          v43,
          a3);
  v10 = v31;
  if ( v31 < 0 )
  {
    BackTraceCollection::Capture(v32, v31);
    v26 = 59;
    goto LABEL_23;
  }
  v33 = v43;
  if ( v43 )
  {
    v43 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  }
  v34 = v42;
  if ( v42 )
  {
    v42 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  }
  return 0;
}

```

## disassembly

```asm
0x1800517d8  mov     [rsp-8+arg_18], rbx
0x1800517dd  push    rbp
0x1800517de  push    rsi
0x1800517df  push    rdi
0x1800517e0  push    r12
0x1800517e2  push    r13
0x1800517e4  push    r14
0x1800517e6  push    r15
0x1800517e8  lea     rbp, [rsp-27h]
0x1800517ed  sub     rsp, 0B0h
0x1800517f4  mov     rax, cs:__security_cookie
0x1800517fb  xor     rax, rsp
0x1800517fe  mov     [rbp+57h+var_38], rax
0x180051802  xor     r12d, r12d
0x180051805  lea     r9, [rbp+57h+string]; string
0x180051809  mov     r15, r8
0x18005180c  mov     [r8], r12d
0x18005180f  mov     rsi, rdx
0x180051812  mov     [rbp+57h+var_48], r12
0x180051816  mov     r13, rcx
0x180051819  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18005181d  lea     edx, [r12+32h]; length
0x180051822  lea     rcx, ?RuntimeClass_Windows_Internal_CapabilityAccess_CapabilityAccess@@3QBGB; "Windows.Internal.CapabilityAccess.Capab"...
0x180051829  call    cs:__imp_WindowsCreateStringReference
0x18005182f  test    eax, eax
0x180051831  jns     short loc_180051849
0x180051833  xor     r9d, r9d; lpArguments
0x180051836  lea     edx, [r12+1]; dwExceptionFlags
0x18005183b  xor     r8d, r8d; nNumberOfArguments
0x18005183e  mov     ecx, 0C000000Dh; dwExceptionCode
0x180051843  call    cs:__imp_RaiseException
0x180051849  mov     rcx, [rbp+57h+var_48]
0x18005184d  mov     rbx, [rbp+57h+string]
0x180051851  test    rcx, rcx
0x180051854  jz      short loc_180051866
0x180051856  mov     [rbp+57h+var_48], r12
0x18005185a  mov     rax, [rcx]
0x18005185d  mov     rax, [rax+10h]
0x180051861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051866  lea     r8, [rbp+57h+var_48]
0x18005186a  mov     rcx, rbx
0x18005186d  lea     rdx, _GUID_518f3880_4e5c_4524_ab03_cd01336b2178
0x180051874  call    cs:__imp_RoGetActivationFactory
0x18005187a  mov     ebx, eax
0x18005187c  test    eax, eax
0x18005187e  jns     short loc_1800518B7
0x180051880  mov     edx, eax; int
0x180051882  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180051887  mov     r9d, 30h ; '0'
0x18005188d  mov     ecx, ebx
0x18005188f  call    Log_HREvent_11
0x180051894  mov     rdx, [rbp+57h+var_48]
0x180051898  test    rdx, rdx
0x18005189b  jz      short loc_1800518B0
0x18005189d  mov     [rbp+57h+var_48], r12
0x1800518a1  mov     rcx, [rdx]
0x1800518a4  mov     rax, [rcx+10h]
0x1800518a8  mov     rcx, rdx
0x1800518ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800518b0  mov     eax, ebx
0x1800518b2  jmp     loc_180051A99
0x1800518b7  mov     r14, [rbp+57h+var_48]
0x1800518bb  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800518bf  mov     [rbp+57h+var_40], r12
0x1800518c3  mov     rbx, rdi
0x1800518c6  mov     rax, [r14]
0x1800518c9  mov     rax, [rax+30h]
0x1800518cd  mov     [rbp+57h+var_B0], rax
0x1800518d1  inc     rbx
0x1800518d4  cmp     [rsi+rbx*2], r12w
0x1800518d9  jnz     short loc_1800518D1
0x1800518db  mov     eax, 0FFFFFFFFh
0x1800518e0  cmp     rbx, rax
0x1800518e3  jbe     short loc_1800518FC
0x1800518e5  xor     r9d, r9d; lpArguments
0x1800518e8  xor     r8d, r8d; nNumberOfArguments
0x1800518eb  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800518f0  mov     ebx, eax
0x1800518f2  lea     edx, [r9+1]; dwExceptionFlags
0x1800518f6  call    cs:__imp_RaiseException
0x1800518fc  lea     r9, [rbp+57h+string]; string
0x180051900  mov     edx, ebx; length
0x180051902  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180051906  mov     rcx, rsi; sourceString
0x180051909  call    cs:__imp_WindowsCreateStringReference
0x18005190f  mov     r12, [rbp+57h+string]
0x180051913  xor     eax, eax
0x180051915  mov     rsi, cs:?c_szCapabilityPhoneCall@@3QEBGEB; ushort const * const c_szCapabilityPhoneCall
0x18005191c  mov     rbx, rdi
0x18005191f  inc     rbx
0x180051922  cmp     [rsi+rbx*2], ax
0x180051926  jnz     short loc_18005191F
0x180051928  mov     eax, 0FFFFFFFFh
0x18005192d  cmp     rbx, rax
0x180051930  jbe     short loc_180051949
0x180051932  xor     r9d, r9d; lpArguments
0x180051935  xor     r8d, r8d; nNumberOfArguments
0x180051938  mov     ecx, 0C000000Dh; dwExceptionCode
0x18005193d  mov     ebx, eax
0x18005193f  lea     edx, [r9+1]; dwExceptionFlags
0x180051943  call    cs:__imp_RaiseException
0x180051949  lea     r9, [rbp+57h+var_88]; string
0x18005194d  mov     edx, ebx; length
0x18005194f  lea     r8, [rbp+57h+var_80]; hstringHeader
0x180051953  mov     rcx, rsi; sourceString
0x180051956  call    cs:__imp_WindowsCreateStringReference
0x18005195c  mov     rbx, [rbp+57h+var_88]
0x180051960  xor     esi, esi
0x180051962  inc     rdi
0x180051965  cmp     [r13+rdi*2+0], si
0x18005196b  jnz     short loc_180051962
0x18005196d  mov     eax, 0FFFFFFFFh
0x180051972  cmp     rdi, rax
0x180051975  jbe     short loc_18005198E
0x180051977  xor     r9d, r9d; lpArguments
0x18005197a  xor     r8d, r8d; nNumberOfArguments
0x18005197d  mov     ecx, 0C000000Dh; dwExceptionCode
0x180051982  mov     edi, eax
0x180051984  lea     edx, [r9+1]; dwExceptionFlags
0x180051988  call    cs:__imp_RaiseException
0x18005198e  lea     r9, [rbp+57h+var_68]; string
0x180051992  mov     edx, edi; length
0x180051994  lea     r8, [rbp+57h+var_60]; hstringHeader
0x180051998  mov     rcx, r13; sourceString
0x18005199b  call    cs:__imp_WindowsCreateStringReference
0x1800519a1  mov     rdx, [rbp+57h+var_68]
0x1800519a5  lea     rax, [rbp+57h+var_40]
0x1800519a9  mov     [rsp+0E0h+var_C0], rax
0x1800519ae  mov     r9, r12
0x1800519b1  mov     rax, [rbp+57h+var_B0]
0x1800519b5  mov     r8, rbx
0x1800519b8  mov     rcx, r14
0x1800519bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800519c0  mov     ebx, eax
0x1800519c2  test    eax, eax
0x1800519c4  jns     short loc_180051A10
0x1800519c6  mov     edx, eax; int
0x1800519c8  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800519cd  mov     r9d, 37h ; '7'
0x1800519d3  mov     ecx, ebx
0x1800519d5  call    Log_HREvent_11
0x1800519da  mov     rcx, [rbp+57h+var_40]
0x1800519de  test    rcx, rcx
0x1800519e1  jz      short loc_1800519F3
0x1800519e3  mov     [rbp+57h+var_40], rsi
0x1800519e7  mov     rdx, [rcx]
0x1800519ea  mov     rax, [rdx+10h]
0x1800519ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800519f3  mov     rcx, [rbp+57h+var_48]
0x1800519f7  test    rcx, rcx
0x1800519fa  jz      loc_1800518B0
0x180051a00  mov     [rbp+57h+var_48], rsi
0x180051a04  mov     rax, [rcx]
0x180051a07  mov     rax, [rax+10h]
0x180051a0b  jmp     loc_1800518AB
0x180051a10  mov     rcx, [rbp+57h+var_40]
0x180051a14  mov     dl, 1
0x180051a16  mov     rax, [rcx]
0x180051a19  mov     rax, [rax+58h]
0x180051a1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051a22  mov     ebx, eax
0x180051a24  test    eax, eax
0x180051a26  jns     short loc_180051A37
0x180051a28  mov     edx, eax; int
0x180051a2a  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180051a2f  mov     r9d, 3Ah ; ':'
0x180051a35  jmp     short loc_1800519D3
0x180051a37  mov     rcx, [rbp+57h+var_40]
0x180051a3b  mov     rdx, r15
0x180051a3e  mov     rax, [rcx]
0x180051a41  mov     rax, [rax+98h]
0x180051a48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051a4d  mov     ebx, eax
0x180051a4f  test    eax, eax
0x180051a51  jns     short loc_180051A65
0x180051a53  mov     edx, eax; int
0x180051a55  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180051a5a  mov     r9d, 3Bh ; ';'
0x180051a60  jmp     loc_1800519D3
0x180051a65  mov     rcx, [rbp+57h+var_40]
0x180051a69  test    rcx, rcx
0x180051a6c  jz      short loc_180051A7E
0x180051a6e  mov     [rbp+57h+var_40], rsi
0x180051a72  mov     rax, [rcx]
0x180051a75  mov     rax, [rax+10h]
0x180051a79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051a7e  mov     rcx, [rbp+57h+var_48]
0x180051a82  test    rcx, rcx
0x180051a85  jz      short loc_180051A97
0x180051a87  mov     [rbp+57h+var_48], rsi
0x180051a8b  mov     rax, [rcx]
0x180051a8e  mov     rax, [rax+10h]
0x180051a92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051a97  xor     eax, eax
0x180051a99  mov     rcx, [rbp+57h+var_38]
0x180051a9d  xor     rcx, rsp; StackCookie
0x180051aa0  call    __security_check_cookie
0x180051aa5  mov     rbx, [rsp+0E0h+arg_18]
0x180051aad  add     rsp, 0B0h
0x180051ab4  pop     r15
0x180051ab6  pop     r14
0x180051ab8  pop     r13
0x180051aba  pop     r12
0x180051abc  pop     rdi
0x180051abd  pop     rsi
0x180051abe  pop     rbp
0x180051abf  retn
```
