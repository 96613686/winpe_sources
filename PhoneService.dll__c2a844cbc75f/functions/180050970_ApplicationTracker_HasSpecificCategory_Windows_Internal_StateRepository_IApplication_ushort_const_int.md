# ApplicationTracker::HasSpecificCategory(Windows::Internal::StateRepository::IApplication *,ushort const *,int *)

- ea: `0x180050970`
- end: `0x180050b30`
- name: `?HasSpecificCategory@ApplicationTracker@@KAJPEAUIApplication@StateRepository@Internal@Windows@@PEBGPEAH@Z`
- size: `448`
- prototype: `static int(struct Windows::Internal::StateRepository::IApplication *, const unsigned __int16 *, int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180079d60`
- `0x18007b7e0`

## callees

- `0x180006e94`
- `0x180050970`
- `0x180050fd8`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800509d6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180050a81`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800509d6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180050a81`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180050a07`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180050a07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800509bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180050a94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800509bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180050a94`

## string_xrefs

- `0x1800509b4`: `Windows.Internal.StateRepository.ApplicationExtension`

## pseudocode

```c
__int64 __fastcall ApplicationTracker::HasSpecificCategory(
        struct Windows::Internal::StateRepository::IApplication *a1,
        const unsigned __int16 *a2,
        int *a3)
{
  __int64 v6; // rcx
  HSTRING v7; // rbx
  int ActivationFactory; // eax
  BackTraceCollection *v9; // rcx
  unsigned int v10; // ebx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rcx
  __int64 v15; // rdi
  unsigned __int64 v16; // rbx
  __int64 (__fastcall *v17)(__int64, struct Windows::Internal::StateRepository::IApplication *, HSTRING, _BYTE *); // r15
  int v18; // eax
  BackTraceCollection *v19; // rcx
  __int64 v20; // r8
  __int64 v21; // rcx
  HSTRING string; // [rsp+30h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v24[8]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v25; // [rsp+58h] [rbp-18h] BYREF

  *a3 = 0;
  v25 = 0;
  if ( WindowsCreateStringReference(
         L"Windows.Internal.StateRepository.ApplicationExtension",
         0x35u,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v6 = v25;
  v7 = string;
  if ( v25 )
  {
    v25 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  ActivationFactory = RoGetActivationFactory(v7, &GUID_b94b62a2_4012_4b7e_a395_f21cc665fd12, &v25);
  v10 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    BackTraceCollection::Capture(v9, ActivationFactory);
    v12 = 218;
LABEL_7:
    Log_HREvent_10(v10, 1, v11, v12);
    v13 = v25;
    if ( v25 )
    {
      v25 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    return v10;
  }
  v15 = v25;
  v16 = -1;
  v24[0] = 0;
  v17 = *(__int64 (__fastcall **)(__int64, struct Windows::Internal::StateRepository::IApplication *, HSTRING, _BYTE *))(*(_QWORD *)v25 + 64LL);
  do
    ++v16;
  while ( a2[v16] );
  if ( v16 > 0xFFFFFFFF )
  {
    LODWORD(v16) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(a2, v16, &hstringHeader, &string);
  v18 = v17(v15, a1, string, v24);
  v10 = v18;
  if ( v18 < 0 )
  {
    BackTraceCollection::Capture(v19, v18);
    v12 = 221;
    goto LABEL_7;
  }
  if ( v24[0] )
  {
    *a3 = 1;
  }
  else
  {
    BackTraceCollection::Capture(v19, 0);
    Log_HREvent_10(0, 0, v20, 222);
  }
  v21 = v25;
  if ( v25 )
  {
    v25 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  }
  return 0;
}

```

## disassembly

```asm
0x180050970  mov     [rsp-38h+arg_18], rbx
0x180050975  push    rbp
0x180050976  push    rsi
0x180050977  push    rdi
0x180050978  push    r12
0x18005097a  push    r13
0x18005097c  push    r14
0x18005097e  push    r15
0x180050980  mov     rbp, rsp
0x180050983  sub     rsp, 70h
0x180050987  mov     rax, cs:__security_cookie
0x18005098e  xor     rax, rsp
0x180050991  mov     [rbp+var_10], rax
0x180050995  xor     r13d, r13d
0x180050998  lea     r9, [rbp+string]; string
0x18005099c  mov     rsi, r8
0x18005099f  mov     [r8], r13d
0x1800509a2  mov     r14, rdx
0x1800509a5  mov     [rbp+var_18], r13
0x1800509a9  mov     r12, rcx
0x1800509ac  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800509b0  lea     edx, [r13+35h]; length
0x1800509b4  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_ApplicationExtension@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x1800509bb  call    cs:__imp_WindowsCreateStringReference
0x1800509c1  lea     edi, [r13+1]
0x1800509c5  test    eax, eax
0x1800509c7  jns     short loc_1800509DC
0x1800509c9  xor     r9d, r9d; lpArguments
0x1800509cc  xor     r8d, r8d; nNumberOfArguments
0x1800509cf  mov     edx, edi; dwExceptionFlags
0x1800509d1  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800509d6  call    cs:__imp_RaiseException
0x1800509dc  mov     rcx, [rbp+var_18]
0x1800509e0  mov     rbx, [rbp+string]
0x1800509e4  test    rcx, rcx
0x1800509e7  jz      short loc_1800509F9
0x1800509e9  mov     [rbp+var_18], r13
0x1800509ed  mov     rax, [rcx]
0x1800509f0  mov     rax, [rax+10h]
0x1800509f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800509f9  lea     r8, [rbp+var_18]
0x1800509fd  mov     rcx, rbx
0x180050a00  lea     rdx, _GUID_b94b62a2_4012_4b7e_a395_f21cc665fd12
0x180050a07  call    cs:__imp_RoGetActivationFactory
0x180050a0d  mov     ebx, eax
0x180050a0f  test    eax, eax
0x180050a11  jns     short loc_180050A49
0x180050a13  mov     edx, eax; int
0x180050a15  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180050a1a  mov     r9d, 0DAh
0x180050a20  mov     edx, edi
0x180050a22  mov     ecx, ebx
0x180050a24  call    Log_HREvent_10
0x180050a29  mov     rcx, [rbp+var_18]
0x180050a2d  test    rcx, rcx
0x180050a30  jz      short loc_180050A42
0x180050a32  mov     [rbp+var_18], r13
0x180050a36  mov     rax, [rcx]
0x180050a39  mov     rax, [rax+10h]
0x180050a3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050a42  mov     eax, ebx
0x180050a44  jmp     loc_180050B0C
0x180050a49  mov     rdi, [rbp+var_18]
0x180050a4d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180050a51  mov     [rbp+var_20], r13b
0x180050a55  mov     rax, [rdi]
0x180050a58  mov     r15, [rax+40h]
0x180050a5c  inc     rbx
0x180050a5f  cmp     [r14+rbx*2], r13w
0x180050a64  jnz     short loc_180050A5C
0x180050a66  mov     eax, 0FFFFFFFFh
0x180050a6b  cmp     rbx, rax
0x180050a6e  jbe     short loc_180050A87
0x180050a70  xor     r9d, r9d; lpArguments
0x180050a73  xor     r8d, r8d; nNumberOfArguments
0x180050a76  mov     ecx, 0C000000Dh; dwExceptionCode
0x180050a7b  mov     ebx, eax
0x180050a7d  lea     edx, [r9+1]; dwExceptionFlags
0x180050a81  call    cs:__imp_RaiseException
0x180050a87  lea     r9, [rbp+string]; string
0x180050a8b  mov     edx, ebx; length
0x180050a8d  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180050a91  mov     rcx, r14; sourceString
0x180050a94  call    cs:__imp_WindowsCreateStringReference
0x180050a9a  mov     r8, [rbp+string]
0x180050a9e  lea     r9, [rbp+var_20]
0x180050aa2  mov     rdx, r12
0x180050aa5  mov     rcx, rdi
0x180050aa8  mov     rax, r15
0x180050aab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050ab0  mov     ebx, eax
0x180050ab2  test    eax, eax
0x180050ab4  jns     short loc_180050ACD
0x180050ab6  mov     edx, eax; int
0x180050ab8  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180050abd  mov     edx, 1
0x180050ac2  mov     r9d, 0DDh
0x180050ac8  jmp     loc_180050A22
0x180050acd  cmp     [rbp+var_20], r13b
0x180050ad1  jnz     short loc_180050AEB
0x180050ad3  xor     edx, edx; int
0x180050ad5  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180050ada  xor     edx, edx
0x180050adc  xor     ecx, ecx
0x180050ade  mov     r9d, 0DEh
0x180050ae4  call    Log_HREvent_10
0x180050ae9  jmp     short loc_180050AF1
0x180050aeb  mov     dword ptr [rsi], 1
0x180050af1  mov     rcx, [rbp+var_18]
0x180050af5  test    rcx, rcx
0x180050af8  jz      short loc_180050B0A
0x180050afa  mov     [rbp+var_18], r13
0x180050afe  mov     rax, [rcx]
0x180050b01  mov     rax, [rax+10h]
0x180050b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050b0a  xor     eax, eax
0x180050b0c  mov     rcx, [rbp+var_10]
0x180050b10  xor     rcx, rsp; StackCookie
0x180050b13  call    __security_check_cookie
0x180050b18  mov     rbx, [rsp+70h+arg_18]
0x180050b20  add     rsp, 70h
0x180050b24  pop     r15
0x180050b26  pop     r14
0x180050b28  pop     r13
0x180050b2a  pop     r12
0x180050b2c  pop     rdi
0x180050b2d  pop     rsi
0x180050b2e  pop     rbp
0x180050b2f  retn
```
