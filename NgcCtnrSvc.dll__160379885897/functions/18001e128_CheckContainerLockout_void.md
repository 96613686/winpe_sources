# CheckContainerLockout(void)

- ea: `0x18001e128`
- end: `0x18001e395`
- name: `?CheckContainerLockout@@YAJXZ`
- size: `621`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180022b70`

## callees

- `0x180018194`
- `0x180019c94`
- `0x18001ced8`
- `0x18001e128`
- `0x18003aa60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e277`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e277`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001e267`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001e267`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e17f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e17f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001e330`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001e330`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 CheckContainerLockout(void)
{
  int LastError; // ebx
  int v1; // eax
  int v2; // esi
  int *v3; // rdx
  void **v5; // [rsp+50h] [rbp+7h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+58h] [rbp+Fh] BYREF
  void **v7; // [rsp+60h] [rbp+17h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp+1Fh] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+70h] [rbp+27h] BYREF
  int v10; // [rsp+B0h] [rbp+67h] BYREF

  v7 = &Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable';
  phkResult = 0;
  Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v7);
  LastError = RegOpenKeyExW(
                HKEY_USERS,
                L"S-1-5-19\\SOFTWARE\\Microsoft\\Cryptography\\NGC\\SoftLockoutVolatileKey",
                0,
                0x20019u,
                &phkResult);
  if ( !LastError )
    goto LABEL_23;
  if ( LastError != 2 )
  {
    if ( (unsigned int)dword_1800BE0B8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800BE0B8, 0x400000000000LL) )
    {
      v10 = LastError;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800BE0B8,
        (unsigned int)&unk_1800A9490,
        0,
        0,
        (__int64)&v10);
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_23;
  }
  v1 = ResetContainerLockout();
  v2 = v1;
  if ( v1 < 0 )
  {
    if ( (unsigned int)dword_1800BE0B8 > 3 )
    {
      v10 = v1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800BE0B8,
        (unsigned int)byte_1800A945D,
        0,
        0,
        (__int64)&v10);
    }
    v2 = 0;
  }
  v5 = &Microsoft::WRL::Wrappers::HandleT<SecurityDescriptorTraits>::`vftable';
  SecurityDescriptor = 0;
  Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v5);
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:PAI(A;OICI;FA;;;SY)(A;OICI;FA;;;S-1-5-80-2381253463-2694003897-3435975801-3559003598-683041300)",
         1u,
         &SecurityDescriptor,
         0) )
  {
    *(_QWORD *)&SecurityAttributes.nLength = 24;
    *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
    SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
    Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v7);
    LastError = RegCreateKeyExW(
                  HKEY_USERS,
                  L"S-1-5-19\\SOFTWARE\\Microsoft\\Cryptography\\NGC\\SoftLockoutVolatileKey",
                  0,
                  0,
                  1u,
                  0x20006u,
                  &SecurityAttributes,
                  &phkResult,
                  0);
    if ( !LastError )
    {
      v5 = &Microsoft::WRL::Wrappers::HandleT<SecurityDescriptorTraits>::`vftable';
      Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v5);
      LastError = v2;
      goto LABEL_23;
    }
    if ( (unsigned int)dword_1800BE0B8 <= 2 )
      goto LABEL_16;
    v3 = &dword_1800A93DC;
    goto LABEL_15;
  }
  LastError = GetLastError();
  if ( (unsigned int)dword_1800BE0B8 > 2 )
  {
    v3 = (int *)byte_1800A9411;
LABEL_15:
    v10 = LastError;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_1800BE0B8,
      (_DWORD)v3,
      0,
      0,
      (__int64)&v10);
  }
LABEL_16:
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  v5 = &Microsoft::WRL::Wrappers::HandleT<SecurityDescriptorTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v5);
LABEL_23:
  v7 = &Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v7);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18001e128  mov     [rsp-8+arg_8], rbx
0x18001e12d  mov     [rsp-8+arg_10], rsi
0x18001e132  push    rbp
0x18001e133  push    r13
0x18001e135  push    r15
0x18001e137  lea     rbp, [rsp-47h]
0x18001e13c  sub     rsp, 90h
0x18001e143  lea     r13, ??_7?$HandleT@URegKeyHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable'
0x18001e14a  mov     [rbp+57h+var_40], r13
0x18001e14e  mov     [rbp+57h+var_38], 0
0x18001e156  lea     rcx, [rbp+57h+var_40]
0x18001e15a  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x18001e15f  lea     rax, [rbp+57h+var_38]
0x18001e163  mov     [rsp+0A0h+phkResult], rax; phkResult
0x18001e168  mov     r9d, 20019h; samDesired
0x18001e16e  xor     r8d, r8d; ulOptions
0x18001e171  lea     rdx, aS1519SoftwareM; "S-1-5-19\\SOFTWARE\\Microsoft\\Cryptogr"...
0x18001e178  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18001e17f  call    cs:__imp_RegOpenKeyExW
0x18001e186  nop     dword ptr [rax+rax+00h]
0x18001e18b  mov     ebx, eax
0x18001e18d  test    eax, eax
0x18001e18f  jz      loc_18001E36C
0x18001e195  cmp     ebx, 2
0x18001e198  jz      short loc_18001E1FA
0x18001e19a  mov     eax, cs:dword_1800BE0B8
0x18001e1a0  cmp     eax, 5
0x18001e1a3  jbe     short loc_18001E1E4
0x18001e1a5  mov     rdx, 400000000000h
0x18001e1af  lea     rcx, dword_1800BE0B8
0x18001e1b6  call    _tlgKeywordOn
0x18001e1bb  test    al, al
0x18001e1bd  jz      short loc_18001E1E4
0x18001e1bf  mov     [rbp+57h+arg_0], ebx
0x18001e1c2  lea     rax, [rbp+57h+arg_0]
0x18001e1c6  mov     [rsp+0A0h+phkResult], rax
0x18001e1cb  xor     r9d, r9d
0x18001e1ce  xor     r8d, r8d
0x18001e1d1  lea     rdx, unk_1800A9490
0x18001e1d8  lea     rcx, dword_1800BE0B8
0x18001e1df  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001e1e4  test    ebx, ebx
0x18001e1e6  jle     loc_18001E36C
0x18001e1ec  movzx   ebx, bx
0x18001e1ef  or      ebx, 80070000h
0x18001e1f5  jmp     loc_18001E36C
0x18001e1fa  call    ?ResetContainerLockout@@YAJXZ; ResetContainerLockout(void)
0x18001e1ff  mov     esi, eax
0x18001e201  test    eax, eax
0x18001e203  jns     short loc_18001E237
0x18001e205  mov     ecx, cs:dword_1800BE0B8
0x18001e20b  cmp     ecx, 3
0x18001e20e  jbe     short loc_18001E235
0x18001e210  mov     [rbp+57h+arg_0], eax
0x18001e213  lea     rax, [rbp+57h+arg_0]
0x18001e217  mov     [rsp+0A0h+phkResult], rax
0x18001e21c  xor     r9d, r9d
0x18001e21f  xor     r8d, r8d
0x18001e222  lea     rdx, byte_1800A945D
0x18001e229  lea     rcx, dword_1800BE0B8
0x18001e230  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001e235  xor     esi, esi
0x18001e237  lea     r15, ??_7?$HandleT@USecurityDescriptorTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<SecurityDescriptorTraits>::`vftable'
0x18001e23e  mov     [rbp+57h+var_50], r15
0x18001e242  mov     [rbp+57h+SecurityDescriptor], 0
0x18001e24a  lea     rcx, [rbp+57h+var_50]
0x18001e24e  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x18001e253  xor     r9d, r9d; SecurityDescriptorSize
0x18001e256  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18001e25a  lea     ebx, [r9+1]
0x18001e25e  mov     edx, ebx; StringSDRevision
0x18001e260  lea     rcx, StringSecurityDescriptor; "D:PAI(A;OICI;FA;;;SY)(A;OICI;FA;;;S-1-5"...
0x18001e267  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001e26e  nop     dword ptr [rax+rax+00h]
0x18001e273  test    eax, eax
0x18001e275  jnz     short loc_18001E2D4
0x18001e277  call    cs:__imp_GetLastError
0x18001e27e  nop     dword ptr [rax+rax+00h]
0x18001e283  mov     ebx, eax
0x18001e285  mov     eax, cs:dword_1800BE0B8
0x18001e28b  cmp     eax, 2
0x18001e28e  jbe     short loc_18001E2B5
0x18001e290  lea     rdx, byte_1800A9411
0x18001e297  lea     rax, [rbp+57h+arg_0]
0x18001e29b  mov     [rsp+0A0h+phkResult], rax
0x18001e2a0  mov     [rbp+57h+arg_0], ebx
0x18001e2a3  xor     r9d, r9d
0x18001e2a6  xor     r8d, r8d
0x18001e2a9  lea     rcx, dword_1800BE0B8
0x18001e2b0  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001e2b5  test    ebx, ebx
0x18001e2b7  jle     short loc_18001E2C2
0x18001e2b9  movzx   ebx, bx
0x18001e2bc  or      ebx, 80070000h
0x18001e2c2  mov     [rbp+57h+var_50], r15
0x18001e2c6  lea     rcx, [rbp+57h+var_50]
0x18001e2ca  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x18001e2cf  jmp     loc_18001E36C
0x18001e2d4  mov     qword ptr [rbp+57h+SecurityAttributes.nLength], 18h
0x18001e2dc  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], 0
0x18001e2e4  mov     rax, [rbp+57h+SecurityDescriptor]
0x18001e2e8  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], rax
0x18001e2ec  lea     rcx, [rbp+57h+var_40]
0x18001e2f0  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x18001e2f5  mov     [rsp+0A0h+lpdwDisposition], 0; lpdwDisposition
0x18001e2fe  lea     rax, [rbp+57h+var_38]
0x18001e302  mov     [rsp+0A0h+var_68], rax; phkResult
0x18001e307  lea     rax, [rbp+57h+SecurityAttributes]
0x18001e30b  mov     [rsp+0A0h+lpSecurityAttributes], rax; lpSecurityAttributes
0x18001e310  mov     [rsp+0A0h+samDesired], 20006h; samDesired
0x18001e318  mov     dword ptr [rsp+0A0h+phkResult], ebx; dwOptions
0x18001e31c  xor     r9d, r9d; lpClass
0x18001e31f  xor     r8d, r8d; Reserved
0x18001e322  lea     rdx, aS1519SoftwareM; "S-1-5-19\\SOFTWARE\\Microsoft\\Cryptogr"...
0x18001e329  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18001e330  call    cs:__imp_RegCreateKeyExW
0x18001e337  nop     dword ptr [rax+rax+00h]
0x18001e33c  mov     ebx, eax
0x18001e33e  test    eax, eax
0x18001e340  jz      short loc_18001E35D
0x18001e342  mov     eax, cs:dword_1800BE0B8
0x18001e348  cmp     eax, 2
0x18001e34b  jbe     loc_18001E2B5
0x18001e351  lea     rdx, dword_1800A93DC
0x18001e358  jmp     loc_18001E297
0x18001e35d  mov     [rbp+57h+var_50], r15
0x18001e361  lea     rcx, [rbp+57h+var_50]
0x18001e365  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x18001e36a  mov     ebx, esi
0x18001e36c  mov     [rbp+57h+var_40], r13
0x18001e370  lea     rcx, [rbp+57h+var_40]
0x18001e374  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x18001e379  mov     eax, ebx
0x18001e37b  lea     r11, [rsp+0A0h+var_10]
0x18001e383  mov     rbx, [r11+28h]
0x18001e387  mov     rsi, [r11+30h]
0x18001e38b  mov     rsp, r11
0x18001e38e  pop     r15
0x18001e390  pop     r13
0x18001e392  pop     rbp
0x18001e393  retn
```
