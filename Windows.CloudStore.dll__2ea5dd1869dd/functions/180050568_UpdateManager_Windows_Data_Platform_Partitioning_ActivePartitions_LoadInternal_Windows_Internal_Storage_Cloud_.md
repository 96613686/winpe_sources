# UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::LoadInternal(Windows::Internal::Storage::Cloud::LoadOptions)

- ea: `0x180050568`
- end: `0x1800506e7`
- name: `?LoadInternal@?$UpdateManager@UActivePartitions@Partitioning@Platform@Data@Windows@@@@AEAA?AV?$unique_ptr@VSyncItem@?$UpdateManager@UActivePartitions@Partitioning@Platform@Data@Windows@@@@U?$default_delete@VSyncItem@?$UpdateManager@UActivePartitions@Partitioning@Platform@Data@Windows@@@@@std@@@std@@W4LoadOptions@Cloud@Storage@Internal@Windows@@@Z`
- size: `383`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800500b4`

## callees

- `0x18000e84c`
- `0x180016cf4`
- `0x18005050c`
- `0x180050568`
- `0x180050728`
- `0x180063ba0`
- `0x1801201a0`
- `0x180208010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180050610`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800506e0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180050610`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800506e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800505fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800505fa`

## string_xrefs

- `0x18005065a`: `onecoreuap\shell\cloudstore\store\api\src\updatehelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::LoadInternal(
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
  __int64 v14; // [rsp+50h] [rbp-19h] BYREF
  __int64 *v15; // [rsp+58h] [rbp-11h]
  __int64 v16; // [rsp+60h] [rbp-9h]
  char v17; // [rsp+68h] [rbp-1h]
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp+Fh] BYREF
  HSTRING string; // [rsp+90h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v14 = 0;
  v3 = *a1;
  v4 = **a1;
  v15 = &v14;
  v16 = 0;
  v17 = 1;
  TypeName = UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::GetTypeName(a1);
  v6 = (const WCHAR *)TypeName;
  string = 0;
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)(TypeName + 2 * v7) );
  if ( v7 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    JUMPOUT(0x1800506E6LL);
  }
  v8 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v7);
  v9 = v8 - 1;
  if ( (unsigned int)v7 < v8 )
    v9 = v7;
  v10 = WindowsCreateStringReference(v6, v9, &hstringHeader, &string);
  if ( v10 < 0 )
    RaiseException(v10, 1u, 0, 0);
  v11 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD))(v4 + 72))(v3, 0, 0, 0);
  v12 = retaddr;
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xED,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\updatehelper.h",
      (const char *)(unsigned int)v11,
      0);
  string = 0;
  if ( v17 )
    wil::com_ptr_t<Windows::Internal::Storage::Cloud::State::ICloudStoreStateManager,wil::err_exception_policy>::attach(
      v15,
      v16);
  UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::GetSyncItemFromCloudStoreData(v12, a2, v14);
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  return a2;
}

```

## disassembly

```asm
0x180050568  mov     [rsp-8+arg_10], rbx
0x18005056d  mov     [rsp-8+arg_18], rsi
0x180050572  push    rbp
0x180050573  push    rdi
0x180050574  push    r12
0x180050576  push    r14
0x180050578  push    r15
0x18005057a  lea     rbp, [rsp-37h]
0x18005057f  sub     rsp, 0A0h
0x180050586  mov     rax, cs:__security_cookie
0x18005058d  xor     rax, rsp
0x180050590  mov     [rbp+57h+var_28], rax
0x180050594  mov     rdi, rdx
0x180050597  mov     [rbp+57h+var_70], rdx
0x18005059b  xor     r12d, r12d
0x18005059e  mov     [rbp+57h+var_70], r12
0x1800505a2  mov     r14, [rcx]
0x1800505a5  mov     r15, [r14]
0x1800505a8  lea     rax, [rbp+57h+var_70]
0x1800505ac  mov     [rbp+57h+var_68], rax
0x1800505b0  mov     [rbp+57h+var_60], r12
0x1800505b4  mov     [rbp+57h+var_58], 1
0x1800505b8  call    ?GetTypeName@?$UpdateManager@UActivePartitions@Partitioning@Platform@Data@Windows@@@@AEAAPEBGXZ; UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::GetTypeName(void)
0x1800505bd  mov     rsi, rax
0x1800505c0  mov     [rbp+57h+string], r12
0x1800505c4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800505c8  inc     rbx
0x1800505cb  cmp     [rax+rbx*2], r12w
0x1800505d0  jnz     short loc_1800505C8
0x1800505d2  mov     eax, 0FFFFFFFFh
0x1800505d7  cmp     rbx, rax
0x1800505da  ja      loc_1800506D1
0x1800505e0  mov     ecx, ebx; unsigned int
0x1800505e2  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800505e7  lea     edx, [rax-1]
0x1800505ea  cmp     ebx, eax
0x1800505ec  cmovb   edx, ebx; length
0x1800505ef  lea     r9, [rbp+57h+string]; string
0x1800505f3  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800505f7  mov     rcx, rsi; sourceString
0x1800505fa  call    cs:__imp_WindowsCreateStringReference
0x180050600  test    eax, eax
0x180050602  jns     short loc_180050617
0x180050604  xor     r9d, r9d; lpArguments
0x180050607  xor     r8d, r8d; nNumberOfArguments
0x18005060a  lea     edx, [r9+1]; dwExceptionFlags
0x18005060e  mov     ecx, eax; dwExceptionCode
0x180050610  call    cs:__imp_RaiseException
0x180050616  nop
0x180050617  lea     rax, [rbp+57h+var_60]
0x18005061b  mov     [rsp+0C0h+var_80], rax
0x180050620  mov     [rsp+0C0h+var_88], r12
0x180050625  mov     [rsp+0C0h+var_90], 2
0x18005062d  mov     rax, [rbp+57h+string]
0x180050631  mov     [rsp+0C0h+var_98], rax
0x180050636  mov     qword ptr [rsp+0C0h+var_A0], r12; int
0x18005063b  xor     r9d, r9d
0x18005063e  xor     r8d, r8d
0x180050641  xor     edx, edx
0x180050643  mov     rcx, r14
0x180050646  mov     rax, [r15+48h]
0x18005064a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005064f  mov     rcx, [rbp+5Fh]; this
0x180050653  test    eax, eax
0x180050655  jns     short loc_18005066C
0x180050657  mov     r9d, eax; char *
0x18005065a  lea     r8, aOnecoreuapShel_37; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x180050661  mov     edx, 0EDh; void *
0x180050666  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005066c  mov     [rbp+57h+string], r12
0x180050670  cmp     [rbp+57h+var_58], r12b
0x180050674  jz      short loc_180050683
0x180050676  mov     rdx, [rbp+57h+var_60]
0x18005067a  mov     rcx, [rbp+57h+var_68]
0x18005067e  call    ?attach@?$com_ptr_t@VICloudStoreStateManager@State@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAXPEAVICloudStoreStateManager@State@Cloud@Storage@Internal@Windows@@@Z; wil::com_ptr_t<Windows::Internal::Storage::Cloud::State::ICloudStoreStateManager,wil::err_exception_policy>::attach(Windows::Internal::Storage::Cloud::State::ICloudStoreStateManager *)
0x180050683  mov     r8, [rbp+57h+var_70]
0x180050687  mov     rdx, rdi
0x18005068a  call    ?GetSyncItemFromCloudStoreData@?$UpdateManager@UActivePartitions@Partitioning@Platform@Data@Windows@@@@AEAA?AV?$unique_ptr@VSyncItem@?$UpdateManager@UActivePartitions@Partitioning@Platform@Data@Windows@@@@U?$default_delete@VSyncItem@?$UpdateManager@UActivePartitions@Partitioning@Platform@Data@Windows@@@@@std@@@std@@PEAUICloudStoreData@Cloud@Storage@Internal@Windows@@@Z; UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::GetSyncItemFromCloudStoreData(Windows::Internal::Storage::Cloud::ICloudStoreData *)
0x18005068f  nop
0x180050690  mov     rcx, [rbp+57h+var_70]
0x180050694  test    rcx, rcx
0x180050697  jz      short loc_1800506A6
0x180050699  mov     rdx, [rcx]
0x18005069c  mov     rax, [rdx+10h]
0x1800506a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800506a5  nop
0x1800506a6  mov     rax, rdi
0x1800506a9  mov     rcx, [rbp+57h+var_28]
0x1800506ad  xor     rcx, rsp; StackCookie
0x1800506b0  call    __security_check_cookie
0x1800506b5  lea     r11, [rsp+0C0h+var_20]
0x1800506bd  mov     rbx, [r11+40h]
0x1800506c1  mov     rsi, [r11+48h]
0x1800506c5  mov     rsp, r11
0x1800506c8  pop     r15
0x1800506ca  pop     r14
0x1800506cc  pop     r12
0x1800506ce  pop     rdi
0x1800506cf  pop     rbp
0x1800506d0  retn
0x1800506d1  xor     r9d, r9d; lpArguments
0x1800506d4  xor     r8d, r8d; nNumberOfArguments
0x1800506d7  lea     edx, [r9+1]; dwExceptionFlags
0x1800506db  mov     ecx, 80070216h; dwExceptionCode
0x1800506e0  call    cs:__imp_RaiseException
```
