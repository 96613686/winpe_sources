# CodeIntegrity::Management::LoadExtensionRegistry

- ea: `0x18000b540`
- end: `0x18000b871`
- name: `CodeIntegrity::Management::LoadExtensionRegistry`
- size: `817`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000ad4c`

## callees

- `0x180002a90`
- `0x180003888`
- `0x18000a278`
- `0x18000a35c`
- `0x18000ad20`
- `0x18000b540`
- `0x18000b878`
- `0x18000c860`
- `0x18000d688`

## import_xrefs

- `ntdll!NtClose` at `0x18000b83f`
- `ntdll!NtClose` at `0x18000b83f`
- `ntdll!RtlGetPersistedStateLocation` at `0x18000b5f4`
- `ntdll!RtlGetPersistedStateLocation` at `0x18000b5f4`
- `ntdll!NtOpenKey` at `0x18000b6a6`
- `ntdll!NtOpenKey` at `0x18000b6a6`
- `ntdll!NtEnumerateKey` at `0x18000b7c6`
- `ntdll!NtEnumerateKey` at `0x18000b7c6`

## string_xrefs

- `0x18000b5e4`: `\REGISTRY\Machine\SYSTEM\CurrentControlSet\Control\CI\ExtensionPolicy`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CodeIntegrity::Management::LoadExtensionRegistry(__int64 a1)
{
  int PersistedStateLocation; // eax
  int v3; // ebx
  __int64 v4; // rdx
  _WORD *v5; // rax
  HLOCAL v6; // rcx
  _QWORD *v7; // rax
  ULONG v8; // esi
  ULONG i; // edx
  int v10; // eax
  int v11; // ebx
  HLOCAL *v12; // rcx
  HLOCAL **v13; // rax
  _QWORD *v14; // rax
  __int64 v15; // rcx
  _QWORD *v16; // rcx
  HLOCAL hMem; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL *p_hMem; // [rsp+48h] [rbp-B8h]
  HLOCAL **v20; // [rsp+50h] [rbp-B0h] BYREF
  ULONG ResultLength; // [rsp+58h] [rbp-A8h] BYREF
  void *KeyHandle; // [rsp+60h] [rbp-A0h] BYREF
  int v23; // [rsp+68h] [rbp-98h]
  struct _UNICODE_STRING v24; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING v25; // [rsp+80h] [rbp-80h] BYREF
  HLOCAL ***v26; // [rsp+90h] [rbp-70h] BYREF
  __int64 v27; // [rsp+98h] [rbp-68h] BYREF
  char v28; // [rsp+A0h] [rbp-60h]
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE KeyInformation[12]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int v31; // [rsp+ECh] [rbp-14h]
  char v32; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v33[528]; // [rsp+300h] [rbp+200h] BYREF

  v23 = 0;
  ResultLength = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  KeyHandle = 0;
  v25 = 0;
  v24 = 0;
  v20 = 0;
  memset_0(KeyInformation, 0, 0x220u);
  p_hMem = &hMem;
  hMem = &hMem;
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"CIExtPolicy",
                             0,
                             L"\\REGISTRY\\Machine\\SYSTEM\\CurrentControlSet\\Control\\CI\\ExtensionPolicy",
                             0);
  v3 = PersistedStateLocation | 0x10000000;
  if ( PersistedStateLocation >= 0 )
  {
    v24 = 0;
    v4 = 0x7FFF;
    v5 = v33;
    while ( *v5 )
    {
      ++v5;
      if ( !--v4 )
        goto LABEL_7;
    }
    v24.Length = -2 - 2 * v4;
    v24.MaximumLength = -2 * v4;
    v24.Buffer = (PWSTR)v33;
LABEL_7:
    v3 = v4 != 0 ? 0x10000000 : -805306355;
    if ( !v4 )
      goto LABEL_10;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.ObjectName = &v24;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) < 0 )
    {
      v3 = 0;
      goto LABEL_10;
    }
    v8 = 0;
    wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_EXT_REGISTRY___void____cdecl___SIPOLICY_EXT_REGISTRY_____CodeIntegrity::Management::FreeExtRegistry_wistd::integral_constant_unsigned___int64_0__SIPOLICY_EXT_REGISTRY___SIPOLICY_EXT_REGISTRY___0_std::nullptr_t___::reset(
      &v20,
      0);
    for ( i = 0; ; i = v8 )
    {
      v3 = NtEnumerateKey(KeyHandle, i, KeyBasicInformation, KeyInformation, 0x220u, &ResultLength) | 0x10000000;
      if ( v3 == -1879048166 )
        break;
      if ( v3 < 0 )
        goto LABEL_10;
      v10 = RtlULongToUShort(v31, &v25.Length);
      v3 = v10 | 0x10000000;
      if ( v10 < 0 )
        goto LABEL_10;
      v25.Buffer = (PWSTR)&v32;
      v25.MaximumLength = v25.Length;
      v26 = &v20;
      v27 = 0;
      v28 = 1;
      v11 = CodeIntegrity::Management::LoadOneExtensionConfig(&v24, &v25, &v27);
      wil::details::out_param_t_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_EXT_REGISTRY___void____cdecl___SIPOLICY_EXT_REGISTRY_____CodeIntegrity::Management::FreeExtRegistry_wistd::integral_constant_unsigned___int64_0__SIPOLICY_EXT_REGISTRY___SIPOLICY_EXT_REGISTRY___0_std::nullptr_t_______::_out_param_t_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_EXT_REGISTRY___void____cdecl___SIPOLICY_EXT_REGISTRY_____CodeIntegrity::Management::FreeExtRegistry_wistd::integral_constant_unsigned___int64_0__SIPOLICY_EXT_REGISTRY___SIPOLICY_EXT_REGISTRY___0_std::nullptr_t_______(&v26);
      if ( v11 >= 0 )
      {
        v12 = p_hMem;
        if ( *p_hMem != &hMem )
          goto LABEL_28;
        v13 = v20;
        *v20 = &hMem;
        v13[1] = v12;
        *v12 = v13;
        p_hMem = (HLOCAL *)v13;
        v20 = 0;
      }
      ++v8;
      wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_EXT_REGISTRY___void____cdecl___SIPOLICY_EXT_REGISTRY_____CodeIntegrity::Management::FreeExtRegistry_wistd::integral_constant_unsigned___int64_0__SIPOLICY_EXT_REGISTRY___SIPOLICY_EXT_REGISTRY___0_std::nullptr_t___::reset(
        &v20,
        0);
    }
    v3 = 0;
    while ( 1 )
    {
      v14 = hMem;
      if ( hMem == &hMem )
        goto LABEL_10;
      if ( *((HLOCAL **)hMem + 1) != &hMem )
        break;
      v15 = *(_QWORD *)hMem;
      if ( *(HLOCAL *)(*(_QWORD *)hMem + 8LL) != hMem )
        break;
      hMem = *(HLOCAL *)hMem;
      *(_QWORD *)(v15 + 8) = &hMem;
      v16 = *(_QWORD **)(a1 + 8);
      if ( *v16 != a1 )
        break;
      *v14 = a1;
      v14[1] = v16;
      *v16 = v14;
      *(_QWORD *)(a1 + 8) = v14;
    }
LABEL_28:
    __fastfail(3u);
  }
LABEL_10:
  while ( 1 )
  {
    v6 = hMem;
    if ( hMem == &hMem )
      break;
    if ( *((HLOCAL **)hMem + 1) != &hMem )
      goto LABEL_28;
    v7 = *(_QWORD **)hMem;
    if ( *(HLOCAL *)(*(_QWORD *)hMem + 8LL) != hMem )
      goto LABEL_28;
    hMem = *(HLOCAL *)hMem;
    v7[1] = &hMem;
    CodeIntegrity::Management::FreeExtRegistry(v6);
  }
  if ( KeyHandle )
    NtClose(KeyHandle);
  wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_EXT_REGISTRY___void____cdecl___SIPOLICY_EXT_REGISTRY_____CodeIntegrity::Management::FreeExtRegistry_wistd::integral_constant_unsigned___int64_0__SIPOLICY_EXT_REGISTRY___SIPOLICY_EXT_REGISTRY___0_std::nullptr_t___::_unique_storage_wil::details::resource_policy_SIPOLICY_EXT_REGISTRY___void____cdecl___SIPOLICY_EXT_REGISTRY_____CodeIntegrity::Management::FreeExtRegistry_wistd::integral_constant_unsigned___int64_0__SIPOLICY_EXT_REGISTRY___SIPOLICY_EXT_REGISTRY___0_std::nullptr_t___(&v20);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000b540  push    rbp
0x18000b542  push    rbx
0x18000b543  push    rsi
0x18000b544  push    rdi
0x18000b545  push    r14
0x18000b547  push    r15
0x18000b549  lea     rbp, [rsp-428h]
0x18000b551  sub     rsp, 528h
0x18000b558  mov     rax, cs:__security_cookie
0x18000b55f  xor     rax, rsp
0x18000b562  mov     [rbp+450h+var_40], rax
0x18000b569  mov     rdi, rcx
0x18000b56c  xor     r14d, r14d
0x18000b56f  mov     [rsp+550h+var_4E8], r14d
0x18000b574  mov     [rsp+550h+var_4F8], r14d
0x18000b579  xorps   xmm0, xmm0
0x18000b57c  movups  xmmword ptr [rbp+450h+ObjectAttributes.Length], xmm0
0x18000b580  movups  xmmword ptr [rbp+450h+ObjectAttributes.ObjectName], xmm0
0x18000b584  movups  xmmword ptr [rbp+450h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000b588  mov     [rsp+550h+KeyHandle], r14
0x18000b58d  movups  xmmword ptr [rbp+450h+var_4D0.Length], xmm0
0x18000b591  xorps   xmm1, xmm1
0x18000b594  movups  xmmword ptr [rsp+550h+var_4E0.Length], xmm1
0x18000b599  mov     [rsp+550h+var_500], r14
0x18000b59e  xor     edx, edx; Val
0x18000b5a0  mov     r8d, 220h; Size
0x18000b5a6  lea     rcx, [rbp+450h+KeyInformation]; void *
0x18000b5aa  call    memset_0
0x18000b5af  lea     rax, [rsp+550h+hMem]
0x18000b5b4  mov     [rsp+550h+var_508], rax
0x18000b5b9  lea     rax, [rsp+550h+hMem]
0x18000b5be  mov     [rsp+550h+hMem], rax
0x18000b5c3  lea     rax, [rsp+550h+var_4E8]
0x18000b5c8  mov     [rsp+550h+var_520], rax
0x18000b5cd  mov     dword ptr [rsp+550h+ResultLength], 20Ah
0x18000b5d5  lea     rax, [rbp+450h+var_250]
0x18000b5dc  mov     qword ptr [rsp+550h+Length], rax
0x18000b5e1  xor     r9d, r9d
0x18000b5e4  lea     r8, aRegistryMachin; "\\REGISTRY\\Machine\\SYSTEM\\CurrentCon"...
0x18000b5eb  xor     edx, edx
0x18000b5ed  lea     rcx, aCiextpolicy; "CIExtPolicy"
0x18000b5f4  call    cs:__imp_RtlGetPersistedStateLocation
0x18000b5fa  mov     ebx, eax
0x18000b5fc  mov     r15d, 10000000h
0x18000b602  or      ebx, r15d
0x18000b605  jl      loc_18000B6B4
0x18000b60b  xorps   xmm0, xmm0
0x18000b60e  movups  xmmword ptr [rsp+550h+var_4E0.Length], xmm0
0x18000b613  mov     edx, 7FFFh
0x18000b618  lea     rax, [rbp+450h+var_250]
0x18000b61f  lea     r8d, [r14+2]
0x18000b623  cmp     [rax], r14w
0x18000b627  jz      short loc_18000B634
0x18000b629  add     rax, r8
0x18000b62c  sub     rdx, 1
0x18000b630  jnz     short loc_18000B623
0x18000b632  jmp     short loc_18000B65C
0x18000b634  movzx   eax, dx
0x18000b637  add     ax, ax
0x18000b63a  mov     ecx, 0FFFEh
0x18000b63f  sub     cx, ax
0x18000b642  mov     [rsp+550h+var_4E0.Length], cx
0x18000b647  add     cx, r8w
0x18000b64b  mov     [rsp+550h+var_4E0.MaximumLength], cx
0x18000b650  lea     rax, [rbp+450h+var_250]
0x18000b657  mov     [rsp+550h+var_4E0.Buffer], rax
0x18000b65c  mov     rax, rdx
0x18000b65f  neg     rax
0x18000b662  sbb     ebx, ebx
0x18000b664  and     ebx, 3FFFFFF3h
0x18000b66a  add     ebx, 0D000000Dh
0x18000b670  test    rdx, rdx
0x18000b673  jz      short loc_18000B6B4
0x18000b675  mov     [rbp+450h+ObjectAttributes.Length], 30h ; '0'
0x18000b67c  mov     [rbp+450h+ObjectAttributes.RootDirectory], r14
0x18000b680  mov     [rbp+450h+ObjectAttributes.Attributes], 40h ; '@'
0x18000b687  lea     rax, [rsp+550h+var_4E0]
0x18000b68c  mov     [rbp+450h+ObjectAttributes.ObjectName], rax
0x18000b690  xorps   xmm0, xmm0
0x18000b693  movdqu  xmmword ptr [rbp+450h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000b698  lea     r8, [rbp+450h+ObjectAttributes]; ObjectAttributes
0x18000b69c  mov     edx, 20019h; DesiredAccess
0x18000b6a1  lea     rcx, [rsp+550h+KeyHandle]; KeyHandle
0x18000b6a6  call    cs:__imp_NtOpenKey
0x18000b6ac  or      eax, r15d
0x18000b6af  jge     short loc_18000B6F8
0x18000b6b1  mov     ebx, r14d
0x18000b6b4  mov     rcx, [rsp+550h+hMem]; hMem
0x18000b6b9  lea     rax, [rsp+550h+hMem]
0x18000b6be  cmp     rcx, rax
0x18000b6c1  jz      loc_18000B835
0x18000b6c7  lea     rax, [rsp+550h+hMem]
0x18000b6cc  cmp     [rcx+8], rax
0x18000b6d0  jnz     loc_18000B82E
0x18000b6d6  mov     rax, [rcx]
0x18000b6d9  cmp     [rax+8], rcx
0x18000b6dd  jnz     loc_18000B82E
0x18000b6e3  mov     [rsp+550h+hMem], rax
0x18000b6e8  lea     rdx, [rsp+550h+hMem]
0x18000b6ed  mov     [rax+8], rdx
0x18000b6f1  call    CodeIntegrity__Management__FreeExtRegistry
0x18000b6f6  jmp     short loc_18000B6B4
0x18000b6f8  mov     esi, r14d
0x18000b6fb  xor     edx, edx
0x18000b6fd  lea     rcx, [rsp+550h+var_500]
0x18000b702  call    wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_EXT_REGISTRY___void____cdecl___SIPOLICY_EXT_REGISTRY_____CodeIntegrity__Management__FreeExtRegistry_wistd__integral_constant_unsigned___int64_0__SIPOLICY_EXT_REGISTRY___SIPOLICY_EXT_REGISTRY___0_std__nullptr_t_____reset
0x18000b707  xor     edx, edx
0x18000b709  jmp     loc_18000B7A8
0x18000b70e  test    ebx, ebx
0x18000b710  js      short loc_18000B6B4
0x18000b712  lea     rdx, [rbp+450h+var_4D0]; unsigned __int16 *
0x18000b716  mov     ecx, [rbp+450h+var_464]; unsigned int
0x18000b719  call    ?RtlULongToUShort@@YAJKPEAG@Z; RtlULongToUShort(ulong,ushort *)
0x18000b71e  mov     ebx, eax
0x18000b720  or      ebx, r15d
0x18000b723  jl      short loc_18000B6B4
0x18000b725  lea     rax, [rbp+450h+var_460]
0x18000b729  mov     [rbp+450h+var_4D0.Buffer], rax
0x18000b72d  movzx   eax, [rbp+450h+var_4D0.Length]
0x18000b731  mov     [rbp+450h+var_4D0.MaximumLength], ax
0x18000b735  lea     rax, [rsp+550h+var_500]
0x18000b73a  mov     [rbp+450h+var_4C0], rax
0x18000b73e  mov     [rbp+450h+var_4B8], r14
0x18000b742  mov     [rbp+450h+var_4B0], 1
0x18000b746  lea     r8, [rbp+450h+var_4B8]
0x18000b74a  lea     rdx, [rbp+450h+var_4D0]; struct _UNICODE_STRING *
0x18000b74e  lea     rcx, [rsp+550h+var_4E0]; struct _UNICODE_STRING *
0x18000b753  call    CodeIntegrity__Management__LoadOneExtensionConfig
0x18000b758  mov     ebx, eax
0x18000b75a  lea     rcx, [rbp+450h+var_4C0]
0x18000b75e  call    wil__details__out_param_t_wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_EXT_REGISTRY___void____cdecl___SIPOLICY_EXT_REGISTRY_____CodeIntegrity__Management__FreeExtRegistry_wistd__integral_constant_unsigned___int64_0__SIPOLICY_EXT_REGISTRY___SIPOLICY_EXT_REGISTRY___0_std__nullptr_t__________out_param_t_wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_EXT_REGISTRY___void____cdecl___SIPOLICY_EXT_REGISTRY_____CodeIntegrity__Management__FreeExtRegistry_wistd__integral_constant_unsigned___int64_0__SIPOLICY_EXT_REGISTRY___SIPOLICY_EXT_REGISTRY___0_std__nullptr_t_______
0x18000b763  test    ebx, ebx
0x18000b765  js      short loc_18000B798
0x18000b767  mov     rcx, [rsp+550h+var_508]
0x18000b76c  lea     rax, [rsp+550h+hMem]
0x18000b771  cmp     [rcx], rax
0x18000b774  jnz     loc_18000B82E
0x18000b77a  mov     rax, [rsp+550h+var_500]
0x18000b77f  lea     rdx, [rsp+550h+hMem]
0x18000b784  mov     [rax], rdx
0x18000b787  mov     [rax+8], rcx
0x18000b78b  mov     [rcx], rax
0x18000b78e  mov     [rsp+550h+var_508], rax
0x18000b793  mov     [rsp+550h+var_500], r14
0x18000b798  inc     esi
0x18000b79a  xor     edx, edx
0x18000b79c  lea     rcx, [rsp+550h+var_500]
0x18000b7a1  call    wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_EXT_REGISTRY___void____cdecl___SIPOLICY_EXT_REGISTRY_____CodeIntegrity__Management__FreeExtRegistry_wistd__integral_constant_unsigned___int64_0__SIPOLICY_EXT_REGISTRY___SIPOLICY_EXT_REGISTRY___0_std__nullptr_t_____reset
0x18000b7a6  mov     edx, esi; Index
0x18000b7a8  lea     rax, [rsp+550h+var_4F8]
0x18000b7ad  mov     [rsp+550h+ResultLength], rax; ResultLength
0x18000b7b2  mov     [rsp+550h+Length], 220h; Length
0x18000b7ba  lea     r9, [rbp+450h+KeyInformation]; KeyInformation
0x18000b7be  xor     r8d, r8d; KeyInformationClass
0x18000b7c1  mov     rcx, [rsp+550h+KeyHandle]; KeyHandle
0x18000b7c6  call    cs:__imp_NtEnumerateKey
0x18000b7cc  mov     ebx, eax
0x18000b7ce  or      ebx, r15d
0x18000b7d1  cmp     ebx, 9000001Ah
0x18000b7d7  jnz     loc_18000B70E
0x18000b7dd  mov     ebx, r14d
0x18000b7e0  mov     rax, [rsp+550h+hMem]
0x18000b7e5  lea     rcx, [rsp+550h+hMem]
0x18000b7ea  cmp     rax, rcx
0x18000b7ed  jz      loc_18000B6B4
0x18000b7f3  lea     rcx, [rsp+550h+hMem]
0x18000b7f8  cmp     [rax+8], rcx
0x18000b7fc  jnz     short loc_18000B82E
0x18000b7fe  mov     rcx, [rax]
0x18000b801  cmp     [rcx+8], rax
0x18000b805  jnz     short loc_18000B82E
0x18000b807  mov     [rsp+550h+hMem], rcx
0x18000b80c  lea     rdx, [rsp+550h+hMem]
0x18000b811  mov     [rcx+8], rdx
0x18000b815  mov     rcx, [rdi+8]
0x18000b819  cmp     [rcx], rdi
0x18000b81c  jnz     short loc_18000B82E
0x18000b81e  mov     [rax], rdi
0x18000b821  mov     [rax+8], rcx
0x18000b825  mov     [rcx], rax
0x18000b828  mov     [rdi+8], rax
0x18000b82c  jmp     short loc_18000B7E0
0x18000b82e  mov     ecx, 3
0x18000b833  int     29h; Win8: RtlFailFast(ecx)
0x18000b835  mov     rcx, [rsp+550h+KeyHandle]; Handle
0x18000b83a  test    rcx, rcx
0x18000b83d  jz      short loc_18000B846
0x18000b83f  call    cs:__imp_NtClose
0x18000b845  nop
0x18000b846  lea     rcx, [rsp+550h+var_500]
0x18000b84b  call    wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_EXT_REGISTRY___void____cdecl___SIPOLICY_EXT_REGISTRY_____CodeIntegrity__Management__FreeExtRegistry_wistd__integral_constant_unsigned___int64_0__SIPOLICY_EXT_REGISTRY___SIPOLICY_EXT_REGISTRY___0_std__nullptr_t______unique_storage_wil__details__resource_policy_SIPOLICY_EXT_REGISTRY___void____cdecl___SIPOLICY_EXT_REGISTRY_____CodeIntegrity__Management__FreeExtRegistry_wistd__integral_constant_unsigned___int64_0__SIPOLICY_EXT_REGISTRY___SIPOLICY_EXT_REGISTRY___0_std__nullptr_t___
0x18000b850  mov     eax, ebx
0x18000b852  mov     rcx, [rbp+450h+var_40]
0x18000b859  xor     rcx, rsp; StackCookie
0x18000b85c  call    __security_check_cookie
0x18000b861  add     rsp, 528h
0x18000b868  pop     r15
0x18000b86a  pop     r14
0x18000b86c  pop     rdi
0x18000b86d  pop     rsi
0x18000b86e  pop     rbx
0x18000b86f  pop     rbp
0x18000b870  retn
```
