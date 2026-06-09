# Wallet::Utils::IsAppInstalled(ushort const *,uchar &)

- ea: `0x18003932c`
- end: `0x180039434`
- name: `?IsAppInstalled@Utils@Wallet@@YAJPEBGAEAE@Z`
- size: `264`
- prototype: `__int64 __fastcall(Wallet::Utils *__hidden this, const unsigned __int16 *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180026770`

## callees

- `0x1800265a4`
- `0x18003932c`
- `0x180039e10`
- `0x180043090`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003940a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003940a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003938c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003938c`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Wallet::Utils::IsAppInstalled(Wallet::Utils *this, const unsigned __int16 *a2, unsigned __int8 *a3)
{
  int ActivationFactory; // edi
  unsigned __int64 v6; // r8
  const WCHAR *v7; // rdx
  int v8; // eax
  __int64 v9; // rcx
  __int64 v11; // [rsp+20h] [rbp-40h] BYREF
  HSTRING string; // [rsp+28h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-30h] BYREF
  __int64 v14; // [rsp+48h] [rbp-18h]

  string = 0;
  v11 = 0;
  v14 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.StateRepository.Application",
    0x2Du,
    0x2Cu);
  ActivationFactory = RoGetActivationFactory(v14, &GUID_07adcc9a_e505_48c2_b471_45af8561f6af, &v11);
  if ( ActivationFactory < 0 )
    goto LABEL_11;
  if ( !this )
  {
    LODWORD(v6) = 0;
    v7 = &sourceString;
    goto LABEL_8;
  }
  v6 = -1;
  do
    ++v6;
  while ( *((_WORD *)this + v6) );
  if ( v6 <= 0xFFFFFFFF )
  {
    v7 = (const WCHAR *)this;
LABEL_8:
    Microsoft::WRL::Wrappers::HString::Set(&string, v7, v6);
  }
  v8 = (*(__int64 (__fastcall **)(__int64, HSTRING, const unsigned __int16 *))(*(_QWORD *)v11 + 56LL))(v11, string, a2);
  ActivationFactory = 0;
  if ( v8 < 0 )
    ActivationFactory = v8;
LABEL_11:
  v9 = v11;
  if ( v11 )
  {
    v11 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  WindowsDeleteString(string);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18003932c  mov     [rsp-18h+arg_10], rbx
0x180039331  mov     [rsp-18h+arg_18], rsi
0x180039336  push    rbp
0x180039337  push    rdi
0x180039338  push    r14
0x18003933a  mov     rbp, rsp
0x18003933d  sub     rsp, 60h
0x180039341  mov     rax, cs:__security_cookie
0x180039348  xor     rax, rsp
0x18003934b  mov     [rbp+var_10], rax
0x18003934f  mov     rsi, rdx
0x180039352  mov     rbx, rcx
0x180039355  xor     r14d, r14d
0x180039358  mov     [rbp+string], r14
0x18003935c  mov     [rbp+var_40], r14
0x180039360  mov     [rbp+var_18], r14
0x180039364  lea     r9d, [r14+2Ch]; unsigned int
0x180039368  lea     r8d, [r14+2Dh]; unsigned int
0x18003936c  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_Application@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x180039373  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180039377  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003937c  nop
0x18003937d  lea     r8, [rbp+var_40]
0x180039381  lea     rdx, _GUID_07adcc9a_e505_48c2_b471_45af8561f6af
0x180039388  mov     rcx, [rbp+var_18]
0x18003938c  call    cs:__imp_RoGetActivationFactory
0x180039392  mov     edi, eax
0x180039394  test    eax, eax
0x180039396  js      short loc_1800393EC
0x180039398  test    rbx, rbx
0x18003939b  jz      short loc_1800393BA
0x18003939d  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800393a1  inc     r8
0x1800393a4  cmp     [rbx+r8*2], r14w
0x1800393a9  jnz     short loc_1800393A1
0x1800393ab  mov     eax, 0FFFFFFFFh
0x1800393b0  cmp     r8, rax
0x1800393b3  ja      short loc_1800393CD
0x1800393b5  mov     rdx, rbx
0x1800393b8  jmp     short loc_1800393C4
0x1800393ba  xor     r8d, r8d; length
0x1800393bd  lea     rdx, sourceString; sourceString
0x1800393c4  lea     rcx, [rbp+string]; string
0x1800393c8  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x1800393cd  mov     rcx, [rbp+var_40]
0x1800393d1  mov     rax, [rcx]
0x1800393d4  mov     r8, rsi
0x1800393d7  mov     rdx, [rbp+string]
0x1800393db  mov     rax, [rax+38h]
0x1800393df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800393e4  mov     edi, r14d
0x1800393e7  test    eax, eax
0x1800393e9  cmovs   edi, eax
0x1800393ec  mov     rcx, [rbp+var_40]
0x1800393f0  test    rcx, rcx
0x1800393f3  jz      short loc_180039406
0x1800393f5  mov     [rbp+var_40], r14
0x1800393f9  mov     rdx, [rcx]
0x1800393fc  mov     rax, [rdx+10h]
0x180039400  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039405  nop
0x180039406  mov     rcx, [rbp+string]; string
0x18003940a  call    cs:__imp_WindowsDeleteString
0x180039410  nop
0x180039411  mov     eax, edi
0x180039413  mov     rcx, [rbp+var_10]
0x180039417  xor     rcx, rsp; StackCookie
0x18003941a  call    __security_check_cookie
0x18003941f  lea     r11, [rsp+60h+var_s0]
0x180039424  mov     rbx, [r11+30h]
0x180039428  mov     rsi, [r11+38h]
0x18003942c  mov     rsp, r11
0x18003942f  pop     r14
0x180039431  pop     rdi
0x180039432  pop     rbp
0x180039433  retn
```
