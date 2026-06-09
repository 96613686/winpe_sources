# UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::LoadInternal(Windows::Internal::Storage::Cloud::LoadOptions)

- ea: `0x180063a14`
- end: `0x180063b97`
- name: `?LoadInternal@?$UpdateManager@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@@AEAA?AV?$unique_ptr@VSyncItem@?$UpdateManager@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@@U?$default_delete@VSyncItem@?$UpdateManager@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@@@std@@@std@@W4LoadOptions@Cloud@Storage@Internal@Windows@@@Z`
- size: `387`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18006352c`

## callees

- `0x18000e84c`
- `0x180016cf4`
- `0x1800639a0`
- `0x180063a14`
- `0x180063ba0`
- `0x180063ca4`
- `0x1801201a0`
- `0x180208010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180063b68`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180063b90`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180063b68`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180063b90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180063aa6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180063aa6`

## string_xrefs

- `0x180063b72`: `onecoreuap\shell\cloudstore\store\api\src\updatehelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::LoadInternal(
        __int64 **a1,
        __int64 a2)
{
  __int64 *v3; // r14
  __int64 v4; // r15
  __int64 TypeName; // rax
  const WCHAR *v6; // rsi
  unsigned __int64 v7; // rbx
  unsigned int v8; // eax
  UINT32 v9; // edx
  HRESULT v10; // eax
  int v11; // eax
  wil::details::in1diag3 *v12; // rcx
  int v14; // [rsp+20h] [rbp-49h]
  __int64 v15; // [rsp+50h] [rbp-19h] BYREF
  __int64 *v16; // [rsp+58h] [rbp-11h]
  __int64 v17; // [rsp+60h] [rbp-9h]
  char v18; // [rsp+68h] [rbp-1h]
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp+Fh] BYREF
  HSTRING string; // [rsp+90h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v15 = 0;
  v3 = *a1;
  v4 = **a1;
  v16 = &v15;
  v17 = 0;
  v18 = 1;
  TypeName = UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::GetTypeName(a1);
  v6 = (const WCHAR *)TypeName;
  string = 0;
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)(TypeName + 2 * v7) );
  if ( v7 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    goto LABEL_14;
  }
  v8 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v7);
  v9 = v8 - 1;
  if ( (unsigned int)v7 < v8 )
    v9 = v7;
  v10 = WindowsCreateStringReference(v6, v9, &hstringHeader, &string);
  if ( v10 < 0 )
  {
    RaiseException(v10, 1u, 0, 0);
    JUMPOUT(0x180063B96LL);
  }
  v14 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD))(v4 + 72))(v3, 0, 0, 0);
  v12 = retaddr;
  if ( v11 < 0 )
LABEL_14:
    wil::details::in1diag3::Throw_Hr(
      v12,
      (void *)0xED,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\updatehelper.h",
      (const char *)(unsigned int)v11,
      v14);
  string = 0;
  if ( v18 )
    wil::com_ptr_t<Windows::Internal::Storage::Cloud::State::ICloudStoreStateManager,wil::err_exception_policy>::attach(
      v16,
      v17);
  UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::GetSyncItemFromCloudStoreData(
    v12,
    a2,
    v15);
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  return a2;
}

```

## disassembly

```asm
0x180063a14  mov     [rsp-8+arg_10], rbx
0x180063a19  mov     [rsp-8+arg_18], rsi
0x180063a1e  push    rbp
0x180063a1f  push    rdi
0x180063a20  push    r12
0x180063a22  push    r14
0x180063a24  push    r15
0x180063a26  lea     rbp, [rsp-37h]
0x180063a2b  sub     rsp, 0A0h
0x180063a32  mov     rax, cs:__security_cookie
0x180063a39  xor     rax, rsp
0x180063a3c  mov     [rbp+57h+var_28], rax
0x180063a40  mov     rdi, rdx
0x180063a43  mov     [rbp+57h+var_70], rdx
0x180063a47  xor     r12d, r12d
0x180063a4a  mov     [rbp+57h+var_70], r12
0x180063a4e  mov     r14, [rcx]
0x180063a51  mov     r15, [r14]
0x180063a54  lea     rax, [rbp+57h+var_70]
0x180063a58  mov     [rbp+57h+var_68], rax
0x180063a5c  mov     [rbp+57h+var_60], r12
0x180063a60  mov     [rbp+57h+var_58], 1
0x180063a64  call    ?GetTypeName@?$UpdateManager@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@@AEAAPEBGXZ; UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::GetTypeName(void)
0x180063a69  mov     rsi, rax
0x180063a6c  mov     [rbp+57h+string], r12
0x180063a70  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180063a74  inc     rbx
0x180063a77  cmp     [rax+rbx*2], r12w
0x180063a7c  jnz     short loc_180063A74
0x180063a7e  mov     eax, 0FFFFFFFFh
0x180063a83  cmp     rbx, rax
0x180063a86  ja      loc_180063B59
0x180063a8c  mov     ecx, ebx; unsigned int
0x180063a8e  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180063a93  lea     edx, [rax-1]
0x180063a96  cmp     ebx, eax
0x180063a98  cmovb   edx, ebx; length
0x180063a9b  lea     r9, [rbp+57h+string]; string
0x180063a9f  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180063aa3  mov     rcx, rsi; sourceString
0x180063aa6  call    cs:__imp_WindowsCreateStringReference
0x180063aac  test    eax, eax
0x180063aae  js      loc_180063B84
0x180063ab4  lea     rax, [rbp+57h+var_60]
0x180063ab8  mov     [rsp+0C0h+var_80], rax
0x180063abd  mov     [rsp+0C0h+var_88], r12
0x180063ac2  mov     [rsp+0C0h+var_90], 2
0x180063aca  mov     rax, [rbp+57h+string]
0x180063ace  mov     [rsp+0C0h+var_98], rax
0x180063ad3  mov     [rsp+0C0h+var_A0], r12
0x180063ad8  xor     r9d, r9d
0x180063adb  xor     r8d, r8d
0x180063ade  xor     edx, edx
0x180063ae0  mov     rcx, r14
0x180063ae3  mov     rax, [r15+48h]
0x180063ae7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063aec  mov     rcx, [rbp+5Fh]
0x180063af0  test    eax, eax
0x180063af2  js      short loc_180063B6F
0x180063af4  mov     [rbp+57h+string], r12
0x180063af8  cmp     [rbp+57h+var_58], r12b
0x180063afc  jz      short loc_180063B0B
0x180063afe  mov     rdx, [rbp+57h+var_60]
0x180063b02  mov     rcx, [rbp+57h+var_68]
0x180063b06  call    ?attach@?$com_ptr_t@VICloudStoreStateManager@State@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAXPEAVICloudStoreStateManager@State@Cloud@Storage@Internal@Windows@@@Z; wil::com_ptr_t<Windows::Internal::Storage::Cloud::State::ICloudStoreStateManager,wil::err_exception_policy>::attach(Windows::Internal::Storage::Cloud::State::ICloudStoreStateManager *)
0x180063b0b  mov     r8, [rbp+57h+var_70]
0x180063b0f  mov     rdx, rdi
0x180063b12  call    ?GetSyncItemFromCloudStoreData@?$UpdateManager@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@@AEAA?AV?$unique_ptr@VSyncItem@?$UpdateManager@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@@U?$default_delete@VSyncItem@?$UpdateManager@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@@@std@@@std@@PEAUICloudStoreData@Cloud@Storage@Internal@Windows@@@Z; UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::GetSyncItemFromCloudStoreData(Windows::Internal::Storage::Cloud::ICloudStoreData *)
0x180063b17  nop
0x180063b18  mov     rcx, [rbp+57h+var_70]
0x180063b1c  test    rcx, rcx
0x180063b1f  jz      short loc_180063B2E
0x180063b21  mov     rdx, [rcx]
0x180063b24  mov     rax, [rdx+10h]
0x180063b28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063b2d  nop
0x180063b2e  mov     rax, rdi
0x180063b31  mov     rcx, [rbp+57h+var_28]
0x180063b35  xor     rcx, rsp; StackCookie
0x180063b38  call    __security_check_cookie
0x180063b3d  lea     r11, [rsp+0C0h+var_20]
0x180063b45  mov     rbx, [r11+40h]
0x180063b49  mov     rsi, [r11+48h]
0x180063b4d  mov     rsp, r11
0x180063b50  pop     r15
0x180063b52  pop     r14
0x180063b54  pop     r12
0x180063b56  pop     rdi
0x180063b57  pop     rbp
0x180063b58  retn
0x180063b59  xor     r9d, r9d; lpArguments
0x180063b5c  xor     r8d, r8d; nNumberOfArguments
0x180063b5f  lea     edx, [r9+1]; dwExceptionFlags
0x180063b63  mov     ecx, 80070216h; dwExceptionCode
0x180063b68  call    cs:__imp_RaiseException
0x180063b6e  nop
0x180063b6f  mov     r9d, eax; char *
0x180063b72  lea     r8, aOnecoreuapShel_37; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x180063b79  mov     edx, 0EDh; void *
0x180063b7e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180063b84  xor     r9d, r9d; lpArguments
0x180063b87  xor     r8d, r8d; nNumberOfArguments
0x180063b8a  lea     edx, [r9+1]; dwExceptionFlags
0x180063b8e  mov     ecx, eax; dwExceptionCode
0x180063b90  call    cs:__imp_RaiseException
```
