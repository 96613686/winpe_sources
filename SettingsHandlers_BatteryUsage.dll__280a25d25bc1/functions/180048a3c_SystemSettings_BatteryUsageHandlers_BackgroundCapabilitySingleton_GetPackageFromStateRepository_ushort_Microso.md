# SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::GetPackageFromStateRepository(ushort *,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage> *)

- ea: `0x180048a3c`
- end: `0x180048af7`
- name: `?GetPackageFromStateRepository@BackgroundCapabilitySingleton@BatteryUsageHandlers@SystemSettings@@QEAAJPEAGPEAV?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Z`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800481b0`

## callees

- `0x1800028d0`
- `0x180010c8c`
- `0x180048a3c`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180048aaa`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180048aaa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180048ac1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180048ac1`

## pseudocode

```c
__int64 __fastcall SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::GetPackageFromStateRepository(
        __int64 a1,
        const WCHAR *a2,
        __int64 a3)
{
  __int64 *v3; // rbx
  __int64 v7; // rax
  unsigned __int64 v8; // rcx
  __int64 (__fastcall *v9)(__int64 *, HSTRING, __int64); // rsi
  const ULONG_PTR *v10; // r9
  UINT32 length; // [rsp+20h] [rbp-48h] BYREF
  HSTRING string; // [rsp+28h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-38h] BYREF

  v3 = *(__int64 **)(a1 + 288);
  if ( !v3 )
    return 2147500037LL;
  v7 = *v3;
  v8 = -1;
  length = 0;
  v9 = *(__int64 (__fastcall **)(__int64 *, HSTRING, __int64))(v7 + 176);
  do
    ++v8;
  while ( a2[v8] );
  if ( (int)ULongLongToUInt(v8, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, v10);
  WindowsCreateStringReference(a2, length, &hstringHeader, &string);
  return v9(v3, string, a3);
}

```

## disassembly

```asm
0x180048a3c  mov     [rsp+arg_18], rbx
0x180048a41  push    rbp
0x180048a42  push    rsi
0x180048a43  push    rdi
0x180048a44  sub     rsp, 50h
0x180048a48  mov     rax, cs:__security_cookie
0x180048a4f  xor     rax, rsp
0x180048a52  mov     [rsp+68h+var_20], rax
0x180048a57  mov     rbx, [rcx+120h]
0x180048a5e  xor     r9d, r9d
0x180048a61  mov     rbp, r8
0x180048a64  mov     rdi, rdx
0x180048a67  test    rbx, rbx
0x180048a6a  jnz     short loc_180048A73
0x180048a6c  mov     eax, 80004005h
0x180048a71  jmp     short loc_180048ADA
0x180048a73  mov     rax, [rbx]
0x180048a76  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180048a7a  mov     [rsp+68h+length], r9d
0x180048a7f  mov     rsi, [rax+0B0h]
0x180048a86  inc     rcx; unsigned __int64
0x180048a89  cmp     [rdx+rcx*2], r9w
0x180048a8e  jnz     short loc_180048A86
0x180048a90  lea     rdx, [rsp+68h+length]; unsigned int *
0x180048a95  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180048a9a  test    eax, eax
0x180048a9c  jns     short loc_180048AB0
0x180048a9e  xor     r8d, r8d; nNumberOfArguments
0x180048aa1  mov     ecx, 0C000000Dh; dwExceptionCode
0x180048aa6  lea     edx, [r8+1]; dwExceptionFlags
0x180048aaa  call    cs:__imp_RaiseException
0x180048ab0  mov     edx, [rsp+68h+length]; length
0x180048ab4  lea     r9, [rsp+68h+string]; string
0x180048ab9  lea     r8, [rsp+68h+hstringHeader]; hstringHeader
0x180048abe  mov     rcx, rdi; sourceString
0x180048ac1  call    cs:__imp_WindowsCreateStringReference
0x180048ac7  mov     rdx, [rsp+68h+string]
0x180048acc  mov     r8, rbp
0x180048acf  mov     rcx, rbx
0x180048ad2  mov     rax, rsi
0x180048ad5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048ada  mov     rcx, [rsp+68h+var_20]
0x180048adf  xor     rcx, rsp; StackCookie
0x180048ae2  call    __security_check_cookie
0x180048ae7  mov     rbx, [rsp+68h+arg_18]
0x180048aef  add     rsp, 50h
0x180048af3  pop     rdi
0x180048af4  pop     rsi
0x180048af5  pop     rbp
0x180048af6  retn
```
