# Windows::Internal::FamilySafety::AppLimits::ParentalControlsAppInfo::ParentalControlsAppInfo(ushort const *,ushort const *)

- ea: `0x18000eb48`
- end: `0x18000ec85`
- name: `??0ParentalControlsAppInfo@AppLimits@FamilySafety@Internal@Windows@@QEAA@PEBG0@Z`
- size: `317`
- prototype: `Windows::Internal::FamilySafety::AppLimits::ParentalControlsAppInfo *__fastcall(Windows::Internal::FamilySafety::AppLimits::ParentalControlsAppInfo *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000f638`

## callees

- `0x180005b38`
- `0x18000eb48`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ec00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ec0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ec46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ec56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ec00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ec0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ec46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ec56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000ec24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000ec6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000ec24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000ec6b`

## pseudocode

```c
Windows::Internal::FamilySafety::AppLimits::ParentalControlsAppInfo *__fastcall Windows::Internal::FamilySafety::AppLimits::ParentalControlsAppInfo::ParentalControlsAppInfo(
        Windows::Internal::FamilySafety::AppLimits::ParentalControlsAppInfo *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  _QWORD *v6; // rbx
  HSTRING *v7; // rbx
  unsigned __int64 v8; // rdi
  unsigned __int64 v9; // rbp
  UINT32 v10; // edx
  const WCHAR *v11; // rcx
  UINT32 v12; // edx
  const WCHAR *v13; // rcx

  v6 = (_QWORD *)((char *)this + 16);
  Microsoft::WRL::FtmBase::FtmBase((Windows::Internal::FamilySafety::AppLimits::ParentalControlsAppInfo *)((char *)this + 16));
  *((_QWORD *)this + 7) = 1;
  *(_QWORD *)this = &Microsoft::WRL::RuntimeClass<Windows::Internal::FamilySafety::AppLimits::IParentalControlsAppInfo,Microsoft::WRL::FtmBase>::`vftable';
  *((_QWORD *)this + 1) = &Microsoft::WRL::RuntimeClass<Windows::Internal::FamilySafety::AppLimits::IParentalControlsAppInfo,Microsoft::WRL::FtmBase>::`vftable'{for `IWeakReferenceSource'};
  *v6 = &Microsoft::WRL::RuntimeClass<Windows::Internal::FamilySafety::AppLimits::IParentalControlsAppInfo,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)this = &Windows::Internal::FamilySafety::AppLimits::ParentalControlsAppInfo::`vftable';
  *((_QWORD *)this + 1) = &Windows::Internal::FamilySafety::AppLimits::ParentalControlsAppInfo::`vftable'{for `IWeakReferenceSource'};
  *v6 = &Windows::Internal::FamilySafety::AppLimits::ParentalControlsAppInfo::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *((_QWORD *)this + 8) = 0;
  v7 = (HSTRING *)((char *)this + 72);
  *((_QWORD *)this + 9) = 0;
  v8 = -1;
  if ( !a2 )
  {
    WindowsDeleteString(0);
    v10 = 0;
    v11 = &SubKey;
    goto LABEL_9;
  }
  v9 = -1;
  do
    ++v9;
  while ( a2[v9] );
  if ( v9 <= 0xFFFFFFFF )
  {
    WindowsDeleteString(0);
    v10 = v9;
    v11 = a2;
LABEL_9:
    *((_QWORD *)this + 8) = 0;
    WindowsCreateString(v11, v10, (HSTRING *)this + 8);
  }
  if ( !a3 )
  {
    WindowsDeleteString(*v7);
    v12 = 0;
    v13 = &SubKey;
    goto LABEL_15;
  }
  do
    ++v8;
  while ( a3[v8] );
  if ( v8 <= 0xFFFFFFFF )
  {
    WindowsDeleteString(*v7);
    v12 = v8;
    v13 = a3;
LABEL_15:
    *v7 = 0;
    WindowsCreateString(v13, v12, (HSTRING *)this + 9);
  }
  return this;
}

```

## disassembly

```asm
0x18000eb48  push    rbx
0x18000eb4a  push    rbp
0x18000eb4b  push    rsi
0x18000eb4c  push    rdi
0x18000eb4d  push    r12
0x18000eb4f  push    r13
0x18000eb51  push    r14
0x18000eb53  push    r15
0x18000eb55  sub     rsp, 28h
0x18000eb59  mov     r15, r8
0x18000eb5c  mov     r12, rdx
0x18000eb5f  mov     rsi, rcx
0x18000eb62  lea     rbx, [rcx+10h]
0x18000eb66  mov     rcx, rbx; this
0x18000eb69  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18000eb6e  mov     qword ptr [rsi+38h], 1
0x18000eb76  lea     rax, ??_7?$RuntimeClass@UIParentalControlsAppInfo@AppLimits@FamilySafety@Internal@Windows@@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Windows::Internal::FamilySafety::AppLimits::IParentalControlsAppInfo,Microsoft::WRL::FtmBase>::`vftable'
0x18000eb7d  mov     [rsi], rax
0x18000eb80  lea     rax, ??_7?$RuntimeClass@UIParentalControlsAppInfo@AppLimits@FamilySafety@Internal@Windows@@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6BIWeakReferenceSource@@@; const Microsoft::WRL::RuntimeClass<Windows::Internal::FamilySafety::AppLimits::IParentalControlsAppInfo,Microsoft::WRL::FtmBase>::`vftable'{for `IWeakReferenceSource'}
0x18000eb87  mov     [rsi+8], rax
0x18000eb8b  lea     rax, ??_7?$RuntimeClass@UIParentalControlsAppInfo@AppLimits@FamilySafety@Internal@Windows@@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Windows::Internal::FamilySafety::AppLimits::IParentalControlsAppInfo,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000eb92  mov     [rbx], rax
0x18000eb95  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000eb9c  xor     r13d, r13d
0x18000eb9f  test    rcx, rcx
0x18000eba2  jz      short loc_18000EBB1
0x18000eba4  mov     rax, [rcx]
0x18000eba7  mov     rax, [rax+8]
0x18000ebab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebb0  nop
0x18000ebb1  lea     rax, ??_7ParentalControlsAppInfo@AppLimits@FamilySafety@Internal@Windows@@6B@; const Windows::Internal::FamilySafety::AppLimits::ParentalControlsAppInfo::`vftable'
0x18000ebb8  mov     [rsi], rax
0x18000ebbb  lea     rax, ??_7ParentalControlsAppInfo@AppLimits@FamilySafety@Internal@Windows@@6BIWeakReferenceSource@@@; const Windows::Internal::FamilySafety::AppLimits::ParentalControlsAppInfo::`vftable'{for `IWeakReferenceSource'}
0x18000ebc2  mov     [rsi+8], rax
0x18000ebc6  lea     rax, ??_7ParentalControlsAppInfo@AppLimits@FamilySafety@Internal@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const Windows::Internal::FamilySafety::AppLimits::ParentalControlsAppInfo::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000ebcd  mov     [rbx], rax
0x18000ebd0  lea     r14, [rsi+40h]
0x18000ebd4  mov     [r14], r13
0x18000ebd7  lea     rbx, [rsi+48h]
0x18000ebdb  mov     [rbx], r13
0x18000ebde  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000ebe2  mov     eax, 0FFFFFFFFh
0x18000ebe7  test    r12, r12
0x18000ebea  jz      short loc_18000EC0D
0x18000ebec  mov     rbp, rdi
0x18000ebef  inc     rbp
0x18000ebf2  cmp     [r12+rbp*2], r13w
0x18000ebf7  jnz     short loc_18000EBEF
0x18000ebf9  cmp     rbp, rax
0x18000ebfc  ja      short loc_18000EC2F
0x18000ebfe  xor     ecx, ecx; string
0x18000ec00  call    cs:__imp_WindowsDeleteString
0x18000ec06  mov     edx, ebp
0x18000ec08  mov     rcx, r12
0x18000ec0b  jmp     short loc_18000EC1E
0x18000ec0d  xor     ecx, ecx; string
0x18000ec0f  call    cs:__imp_WindowsDeleteString
0x18000ec15  xor     edx, edx; length
0x18000ec17  lea     rcx, SubKey; sourceString
0x18000ec1e  mov     [r14], r13
0x18000ec21  mov     r8, r14; string
0x18000ec24  call    cs:__imp_WindowsCreateString
0x18000ec2a  mov     eax, 0FFFFFFFFh
0x18000ec2f  test    r15, r15
0x18000ec32  jz      short loc_18000EC53
0x18000ec34  inc     rdi
0x18000ec37  cmp     [r15+rdi*2], r13w
0x18000ec3c  jnz     short loc_18000EC34
0x18000ec3e  cmp     rdi, rax
0x18000ec41  ja      short loc_18000EC71
0x18000ec43  mov     rcx, [rbx]; string
0x18000ec46  call    cs:__imp_WindowsDeleteString
0x18000ec4c  mov     edx, edi
0x18000ec4e  mov     rcx, r15
0x18000ec51  jmp     short loc_18000EC65
0x18000ec53  mov     rcx, [rbx]; string
0x18000ec56  call    cs:__imp_WindowsDeleteString
0x18000ec5c  xor     edx, edx; length
0x18000ec5e  lea     rcx, SubKey; sourceString
0x18000ec65  mov     [rbx], r13
0x18000ec68  mov     r8, rbx; string
0x18000ec6b  call    cs:__imp_WindowsCreateString
0x18000ec71  mov     rax, rsi
0x18000ec74  add     rsp, 28h
0x18000ec78  pop     r15
0x18000ec7a  pop     r14
0x18000ec7c  pop     r13
0x18000ec7e  pop     r12
0x18000ec80  pop     rdi
0x18000ec81  pop     rsi
0x18000ec82  pop     rbp
0x18000ec83  pop     rbx
0x18000ec84  retn
```
