# ApplicationTracker::IsAppInstalled(_ApplicationPackageInfo const &,int *)

- ea: `0x180050bd8`
- end: `0x180050d67`
- name: `?IsAppInstalled@ApplicationTracker@@IEAAJAEBU_ApplicationPackageInfo@@PEAH@Z`
- size: `399`
- prototype: `int(ApplicationTracker *__hidden this, const struct _ApplicationPackageInfo *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18004fbc0`

## callees

- `0x180006e94`
- `0x180050bd8`
- `0x180050fd8`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180050c36`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180050cec`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180050c36`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180050cec`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180050c6b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180050c6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180050c1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180050cd3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180050c1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180050cd3`

## pseudocode

```c
__int64 __fastcall ApplicationTracker::IsAppInstalled(ApplicationTracker *this, const WCHAR *a2, int *a3)
{
  __int64 v5; // rcx
  HSTRING v6; // rbx
  int ActivationFactory; // eax
  BackTraceCollection *v8; // rcx
  unsigned int v9; // ebx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rcx
  __int64 v14; // rbx
  __int64 (__fastcall *v15)(__int64, HSTRING, _BYTE *); // rdi
  int v16; // eax
  BackTraceCollection *v17; // rcx
  __int64 v18; // rcx
  HSTRING string; // [rsp+30h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v21[8]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v22; // [rsp+58h] [rbp-18h] BYREF

  v22 = 0;
  if ( WindowsCreateStringReference(L"Windows.Internal.StateRepository.Application", 0x2Cu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v5 = v22;
  v6 = string;
  if ( v22 )
  {
    v22 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  ActivationFactory = RoGetActivationFactory(v6, &GUID_07adcc9a_e505_48c2_b471_45af8561f6af, &v22);
  v9 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    BackTraceCollection::Capture(v8, ActivationFactory);
    v11 = 90;
LABEL_7:
    Log_HREvent_10(v9, 1, v10, v11);
    v12 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    return v9;
  }
  v14 = v22;
  v21[0] = 0;
  v15 = *(__int64 (__fastcall **)(__int64, HSTRING, _BYTE *))(*(_QWORD *)v22 + 56LL);
  if ( WindowsCreateStringReference(a2, 0x82u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v16 = v15(v14, string, v21);
  v9 = v16;
  if ( v16 < 0 )
  {
    BackTraceCollection::Capture(v17, v16);
    v11 = 93;
    goto LABEL_7;
  }
  v18 = v22;
  *a3 = v21[0] != 0;
  if ( v18 )
  {
    v22 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  return 0;
}

```

## disassembly

```asm
0x180050bd8  mov     [rsp-18h+arg_0], rbx
0x180050bdd  mov     [rsp-18h+arg_18], rsi
0x180050be2  push    rbp
0x180050be3  push    rdi
0x180050be4  push    r14
0x180050be6  mov     rbp, rsp
0x180050be9  sub     rsp, 70h
0x180050bed  mov     rax, cs:__security_cookie
0x180050bf4  xor     rax, rsp
0x180050bf7  mov     [rbp+var_10], rax
0x180050bfb  mov     rsi, r8
0x180050bfe  mov     [rbp+var_18], 0
0x180050c06  mov     r14, rdx
0x180050c09  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180050c0d  mov     edx, 2Ch ; ','; length
0x180050c12  lea     r9, [rbp+string]; string
0x180050c16  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Application@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x180050c1d  call    cs:__imp_WindowsCreateStringReference
0x180050c23  test    eax, eax
0x180050c25  jns     short loc_180050C3C
0x180050c27  xor     r9d, r9d; lpArguments
0x180050c2a  xor     r8d, r8d; nNumberOfArguments
0x180050c2d  mov     ecx, 0C000000Dh; dwExceptionCode
0x180050c32  lea     edx, [r9+1]; dwExceptionFlags
0x180050c36  call    cs:__imp_RaiseException
0x180050c3c  mov     rcx, [rbp+var_18]
0x180050c40  mov     rbx, [rbp+string]
0x180050c44  test    rcx, rcx
0x180050c47  jz      short loc_180050C5D
0x180050c49  mov     [rbp+var_18], 0
0x180050c51  mov     rax, [rcx]
0x180050c54  mov     rax, [rax+10h]
0x180050c58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050c5d  lea     r8, [rbp+var_18]
0x180050c61  mov     rcx, rbx
0x180050c64  lea     rdx, _GUID_07adcc9a_e505_48c2_b471_45af8561f6af
0x180050c6b  call    cs:__imp_RoGetActivationFactory
0x180050c71  mov     ebx, eax
0x180050c73  test    eax, eax
0x180050c75  jns     short loc_180050CB4
0x180050c77  mov     edx, eax; int
0x180050c79  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180050c7e  mov     r9d, 5Ah ; 'Z'
0x180050c84  mov     edx, 1
0x180050c89  mov     ecx, ebx
0x180050c8b  call    Log_HREvent_10
0x180050c90  mov     rcx, [rbp+var_18]
0x180050c94  test    rcx, rcx
0x180050c97  jz      short loc_180050CAD
0x180050c99  mov     [rbp+var_18], 0
0x180050ca1  mov     rax, [rcx]
0x180050ca4  mov     rax, [rax+10h]
0x180050ca8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050cad  mov     eax, ebx
0x180050caf  jmp     loc_180050D46
0x180050cb4  mov     rbx, [rbp+var_18]
0x180050cb8  lea     r9, [rbp+string]; string
0x180050cbc  mov     [rbp+var_20], 0
0x180050cc0  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180050cc4  mov     edx, 82h; length
0x180050cc9  mov     rcx, r14; sourceString
0x180050ccc  mov     rax, [rbx]
0x180050ccf  mov     rdi, [rax+38h]
0x180050cd3  call    cs:__imp_WindowsCreateStringReference
0x180050cd9  test    eax, eax
0x180050cdb  jns     short loc_180050CF2
0x180050cdd  xor     r9d, r9d; lpArguments
0x180050ce0  xor     r8d, r8d; nNumberOfArguments
0x180050ce3  mov     ecx, 0C000000Dh; dwExceptionCode
0x180050ce8  lea     edx, [r9+1]; dwExceptionFlags
0x180050cec  call    cs:__imp_RaiseException
0x180050cf2  mov     rdx, [rbp+string]
0x180050cf6  lea     r8, [rbp+var_20]
0x180050cfa  mov     rcx, rbx
0x180050cfd  mov     rax, rdi
0x180050d00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050d05  mov     ebx, eax
0x180050d07  test    eax, eax
0x180050d09  jns     short loc_180050D1D
0x180050d0b  mov     edx, eax; int
0x180050d0d  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180050d12  mov     r9d, 5Dh ; ']'
0x180050d18  jmp     loc_180050C84
0x180050d1d  mov     rcx, [rbp+var_18]
0x180050d21  xor     eax, eax
0x180050d23  cmp     [rbp+var_20], al
0x180050d26  setnz   al
0x180050d29  mov     [rsi], eax
0x180050d2b  test    rcx, rcx
0x180050d2e  jz      short loc_180050D44
0x180050d30  mov     [rbp+var_18], 0
0x180050d38  mov     rax, [rcx]
0x180050d3b  mov     rax, [rax+10h]
0x180050d3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050d44  xor     eax, eax
0x180050d46  mov     rcx, [rbp+var_10]
0x180050d4a  xor     rcx, rsp; StackCookie
0x180050d4d  call    __security_check_cookie
0x180050d52  lea     r11, [rsp+70h+var_s0]
0x180050d57  mov     rbx, [r11+20h]
0x180050d5b  mov     rsi, [r11+38h]
0x180050d5f  mov     rsp, r11
0x180050d62  pop     r14
0x180050d64  pop     rdi
0x180050d65  pop     rbp
0x180050d66  retn
```
