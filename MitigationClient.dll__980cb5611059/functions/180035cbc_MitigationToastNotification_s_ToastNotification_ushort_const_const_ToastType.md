# MitigationToastNotification::s_ToastNotification(ushort const * const,ToastType)

- ea: `0x180035cbc`
- end: `0x180035ec5`
- name: `?s_ToastNotification@MitigationToastNotification@@KAJQEBGW4ToastType@@@Z`
- size: `521`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800358e8`

## callees

- `0x18001208c`
- `0x18002cf48`
- `0x180035cbc`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180035d6c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180035d6c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180035d42`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180035ea2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180035d42`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180035ea2`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180035cf7`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180035cf7`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180035dc6`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180035dc6`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MitigationToastNotification::s_ToastNotification(__int64 a1, int a2)
{
  int v3; // ebx
  HRESULT Instance; // edi
  __int64 v5; // rdx
  const wchar_t *v7; // rsi
  const wchar_t *v8; // rdi
  int ppv; // [rsp+20h] [rbp-79h]
  __int64 v10; // [rsp+98h] [rbp-1h] BYREF
  LPVOID v11[3]; // [rsp+A0h] [rbp+7h] BYREF
  int v12; // [rsp+B8h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]
  int v14; // [rsp+110h] [rbp+77h] BYREF
  int v15; // [rsp+118h] [rbp+7Fh]

  v3 = 0;
  v15 = 0;
  v11[0] = 0;
  v10 = 0;
  Instance = CoInitializeEx(0, 0);
  if ( Instance >= 0 )
  {
    v3 = 1;
    v15 = 1;
    Instance = 0;
  }
  if ( Instance < 0 )
  {
    v5 = 106;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\toastnotification\\mitigationtoastnotification.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
    wil::com_ptr_t<IBootTrigger,wil::err_exception_policy>::~com_ptr_t<IBootTrigger,wil::err_exception_policy>(&v10);
    wil::com_ptr_t<IBootTrigger,wil::err_exception_policy>::~com_ptr_t<IBootTrigger,wil::err_exception_policy>((__int64 *)v11);
    if ( v3 )
      CoUninitialize();
    return (unsigned int)Instance;
  }
  Instance = CoCreateInstance(
               &GUID_0c9281f9_6da1_4006_8729_de6e6b61581c,
               0,
               4u,
               &GUID_df8e9480_ca73_448e_b8f0_da000f581428,
               v11);
  if ( Instance < 0 )
  {
    v5 = 107;
    goto LABEL_5;
  }
  Instance = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v11[0] + 24LL))(v11[0], &v10);
  if ( Instance < 0 )
  {
    v5 = 108;
    goto LABEL_5;
  }
  v7 = L"TroubleshootRes";
  if ( a2 != 2 )
    v7 = L"Troubleshoot";
  v14 = 0;
  RtlGetDeviceFamilyInfoEnum(0, &v14, 0);
  v8 = L"BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy!App";
  if ( v14 != 16 )
    v8 = L"windows.immersivecontrolpanel_cw5n1h2txyewy!microsoft.windows.immersivecontrolpanel";
  (*(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *, _QWORD, _QWORD, const wchar_t *))(*(_QWORD *)v10 + 80LL))(
    v10,
    L"NonImmersivePackage",
    v8,
    0,
    0,
    v7);
  v11[2] = 0;
  v12 = 0;
  ppv = 1;
  Instance = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, _QWORD))(*(_QWORD *)v10 + 64LL))(
               v10,
               L"NonImmersivePackage",
               v8,
               0);
  if ( Instance < 0 )
  {
    v5 = 148;
    goto LABEL_5;
  }
  wil::com_ptr_t<IBootTrigger,wil::err_exception_policy>::~com_ptr_t<IBootTrigger,wil::err_exception_policy>(&v10);
  wil::com_ptr_t<IBootTrigger,wil::err_exception_policy>::~com_ptr_t<IBootTrigger,wil::err_exception_policy>((__int64 *)v11);
  if ( v3 )
    CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x180035cbc  mov     [rsp-8+arg_0], rbx
0x180035cc1  push    rbp
0x180035cc2  push    rsi
0x180035cc3  push    rdi
0x180035cc4  push    r12
0x180035cc6  push    r13
0x180035cc8  push    r14
0x180035cca  push    r15
0x180035ccc  lea     rbp, [rsp-27h]
0x180035cd1  sub     rsp, 0C0h
0x180035cd8  mov     r14d, edx
0x180035cdb  mov     r15, rcx
0x180035cde  xor     r13d, r13d
0x180035ce1  mov     [rbp+57h+var_60], r13d
0x180035ce5  mov     ebx, r13d
0x180035ce8  mov     [rbp+57h+arg_18], ebx
0x180035ceb  mov     [rbp+57h+var_50], r13
0x180035cef  mov     [rbp+57h+var_58], r13
0x180035cf3  xor     edx, edx; dwCoInit
0x180035cf5  xor     ecx, ecx; pvReserved
0x180035cf7  call    cs:__imp_CoInitializeEx
0x180035cfd  mov     edi, eax
0x180035cff  test    eax, eax
0x180035d01  js      short loc_180035D0D
0x180035d03  lea     ebx, [r13+1]
0x180035d07  mov     [rbp+57h+arg_18], ebx
0x180035d0a  mov     edi, r13d
0x180035d0d  test    edi, edi
0x180035d0f  jns     short loc_180035D4F
0x180035d11  mov     edx, 6Ah ; 'j'; void *
0x180035d16  lea     r8, aOnecoreBaseDia_32; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180035d1d  mov     r9d, edi; char *
0x180035d20  mov     rcx, [rbp+5Fh]; this
0x180035d24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035d29  nop
0x180035d2a  lea     rcx, [rbp+57h+var_58]
0x180035d2e  call    ??1?$com_ptr_t@UIBootTrigger@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IBootTrigger,wil::err_exception_policy>::~com_ptr_t<IBootTrigger,wil::err_exception_policy>(void)
0x180035d33  nop
0x180035d34  lea     rcx, [rbp+57h+var_50]
0x180035d38  call    ??1?$com_ptr_t@UIBootTrigger@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IBootTrigger,wil::err_exception_policy>::~com_ptr_t<IBootTrigger,wil::err_exception_policy>(void)
0x180035d3d  nop
0x180035d3e  test    ebx, ebx
0x180035d40  jz      short loc_180035D48
0x180035d42  call    cs:__imp_CoUninitialize
0x180035d48  mov     eax, edi
0x180035d4a  jmp     loc_180035EAA
0x180035d4f  lea     rax, [rbp+57h+var_50]
0x180035d53  mov     [rsp+0F0h+ppv], rax; ppv
0x180035d58  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428; riid
0x180035d5f  xor     edx, edx; pUnkOuter
0x180035d61  lea     r8d, [rdx+4]; dwClsContext
0x180035d65  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c; rclsid
0x180035d6c  call    cs:__imp_CoCreateInstance
0x180035d72  mov     edi, eax
0x180035d74  test    eax, eax
0x180035d76  jns     short loc_180035D7F
0x180035d78  mov     edx, 6Bh ; 'k'
0x180035d7d  jmp     short loc_180035D16
0x180035d7f  mov     rcx, [rbp+57h+var_50]
0x180035d83  mov     rax, [rcx]
0x180035d86  lea     rdx, [rbp+57h+var_58]
0x180035d8a  mov     rax, [rax+18h]
0x180035d8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035d93  mov     edi, eax
0x180035d95  test    eax, eax
0x180035d97  jns     short loc_180035DA3
0x180035d99  mov     edx, 6Ch ; 'l'
0x180035d9e  jmp     loc_180035D16
0x180035da3  lea     r12, aTroubleshoot; "Troubleshoot"
0x180035daa  lea     rsi, aTroubleshootre; "TroubleshootRes"
0x180035db1  cmp     r14d, 2
0x180035db5  cmovnz  rsi, r12
0x180035db9  mov     [rbp+57h+arg_10], r13d
0x180035dbd  xor     r8d, r8d
0x180035dc0  lea     rdx, [rbp+57h+arg_10]
0x180035dc4  xor     ecx, ecx
0x180035dc6  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x180035dcc  cmp     [rbp+57h+arg_10], 10h
0x180035dd0  setz    al
0x180035dd3  lea     rcx, ?c_szPCSettingsAppID@@3QBGB; "windows.immersivecontrolpanel_cw5n1h2tx"...
0x180035dda  lea     rdi, aBaeaef159bab47; "BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw"...
0x180035de1  test    al, al
0x180035de3  cmovz   rdi, rcx
0x180035de7  mov     rcx, [rbp+57h+var_58]
0x180035deb  mov     rax, [rcx]
0x180035dee  mov     [rsp+0F0h+var_C8], rsi
0x180035df3  mov     [rsp+0F0h+ppv], r13
0x180035df8  xor     r9d, r9d
0x180035dfb  mov     r8, rdi
0x180035dfe  lea     rdx, aNonimmersivepa; "NonImmersivePackage"
0x180035e05  mov     rax, [rax+50h]
0x180035e09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035e0e  mov     rcx, [rbp+57h+var_58]
0x180035e12  mov     [rbp+57h+var_40], r13
0x180035e16  mov     [rbp+57h+var_38], r13d
0x180035e1a  mov     rax, [rcx]
0x180035e1d  lea     rdx, [rbp+57h+var_60]
0x180035e21  mov     [rsp+0F0h+var_78], rdx
0x180035e26  mov     [rsp+0F0h+var_80], r13d
0x180035e2b  mov     [rsp+0F0h+var_88], r13
0x180035e30  mov     [rsp+0F0h+var_90], r13
0x180035e35  mov     [rsp+0F0h+var_98], r13
0x180035e3a  mov     [rsp+0F0h+var_A0], r13d
0x180035e3f  mov     [rsp+0F0h+var_A8], r13d
0x180035e44  lea     r8, [rbp+57h+var_40]
0x180035e48  mov     [rsp+0F0h+var_B0], r8
0x180035e4d  mov     [rsp+0F0h+var_B8], rsi
0x180035e52  mov     [rsp+0F0h+var_C0], r12
0x180035e57  mov     [rsp+0F0h+var_C8], r15
0x180035e5c  mov     dword ptr [rsp+0F0h+ppv], 1
0x180035e64  xor     r9d, r9d
0x180035e67  mov     r8, rdi
0x180035e6a  lea     rdx, aNonimmersivepa; "NonImmersivePackage"
0x180035e71  mov     rax, [rax+40h]
0x180035e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035e7a  mov     edi, eax
0x180035e7c  test    eax, eax
0x180035e7e  jns     short loc_180035E8A
0x180035e80  mov     edx, 94h
0x180035e85  jmp     loc_180035D16
0x180035e8a  lea     rcx, [rbp+57h+var_58]
0x180035e8e  call    ??1?$com_ptr_t@UIBootTrigger@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IBootTrigger,wil::err_exception_policy>::~com_ptr_t<IBootTrigger,wil::err_exception_policy>(void)
0x180035e93  nop
0x180035e94  lea     rcx, [rbp+57h+var_50]
0x180035e98  call    ??1?$com_ptr_t@UIBootTrigger@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IBootTrigger,wil::err_exception_policy>::~com_ptr_t<IBootTrigger,wil::err_exception_policy>(void)
0x180035e9d  nop
0x180035e9e  test    ebx, ebx
0x180035ea0  jz      short loc_180035EA8
0x180035ea2  call    cs:__imp_CoUninitialize
0x180035ea8  xor     eax, eax
0x180035eaa  mov     rbx, [rsp+0F0h+arg_0]
0x180035eb2  add     rsp, 0C0h
0x180035eb9  pop     r15
0x180035ebb  pop     r14
0x180035ebd  pop     r13
0x180035ebf  pop     r12
0x180035ec1  pop     rdi
0x180035ec2  pop     rsi
0x180035ec3  pop     rbp
0x180035ec4  retn
```
