# CWin32Broker::CreateFile2(ushort const *,ulong,ulong,ulong,ulong,ulong,void * *)

- ea: `0x180017940`
- end: `0x180017b5f`
- name: `?CreateFile2@CWin32Broker@@UEAAJPEBGKKKKKPEAPEAX@Z`
- size: `543`
- prototype: `__int64 __fastcall(CWin32Broker *this, unsigned __int16 *, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, void **)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180002be0`
- `0x180005db8`
- `0x18000d4e0`
- `0x1800120c0`
- `0x180012b7c`
- `0x180015d50`
- `0x1800168e0`
- `0x1800170fc`
- `0x18001738c`
- `0x180017940`

## import_xrefs

- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180017a8a`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180017a8a`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CWin32Broker::CreateFile2(
        CWin32Broker *this,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        void **a8)
{
  unsigned int v11; // ecx
  const char *v12; // r9
  __int64 result; // rax
  wil::details *v14; // rcx
  void *File2; // rbx
  unsigned int LastErrorFailHr; // ebx
  bool v17; // [rsp+30h] [rbp-238h] BYREF
  _QWORD v18[2]; // [rsp+38h] [rbp-230h] BYREF
  _DWORD v19[4]; // [rsp+48h] [rbp-220h] BYREF
  __int64 v20; // [rsp+58h] [rbp-210h]
  __int64 v21; // [rsp+60h] [rbp-208h]
  _BYTE v22[96]; // [rsp+70h] [rbp-1F8h] BYREF
  _BYTE v23[352]; // [rsp+D0h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  start_scoped_activity<TraceProvider::CreateFile2BrokerActivity>(v23);
  try
  {
    *a8 = 0;
    WindowsStorage::Utilities::Identity::Identity((WindowsStorage::Utilities::Identity *)v22);
    v17 = 0;
    if ( !WindowsStorage::Win32BrokeredAPIs::FilePathAccess::IsAllowed(
            (WindowsStorage::Utilities::Identity *)v22,
            a2,
            &v17,
            0xFFFDu) )
      goto LABEL_6;
    if ( v17 )
    {
      v11 = a7;
    }
    else if ( (a6 & 0x400) != 0 || (v11 = a7, (a7 & 0x200000) != 0) )
    {
LABEL_6:
      WindowsStorage::Utilities::Identity::~Identity((WindowsStorage::Utilities::Identity *)v22);
      wil::details::lambda_call<_lambda_70b204013488a836da8c9e05ae18fd45_>::~lambda_call<_lambda_70b204013488a836da8c9e05ae18fd45_>((TraceProvider::CreateFile2BrokerActivity *)v23);
      return 2147942405LL;
    }
    v19[1] = a6;
    v19[2] = v11;
    v19[3] = 0;
    v19[0] = 32;
    v21 = 0;
    v20 = 0;
    File2 = (void *)CreateFile2(a2, a3, a4, a5, v19);
    v18[0] = File2;
    if ( (((unsigned __int64)File2 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      if ( !v17 && (a3 & 0x116) != 0 )
      {
        v18[1] = v22;
        WindowsStorage::Utilities::ModifyZoneIdentifierOnPath__lambda_582adc48acbb24e7e5f85ee00fe99bbe___(
          File2,
          (struct _GUID *)a2);
      }
      v18[0] = -1;
      *a8 = File2;
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v18);
      WindowsStorage::Utilities::Identity::~Identity((WindowsStorage::Utilities::Identity *)v22);
      wil::details::lambda_call<_lambda_70b204013488a836da8c9e05ae18fd45_>::~lambda_call<_lambda_70b204013488a836da8c9e05ae18fd45_>((TraceProvider::CreateFile2BrokerActivity *)v23);
      result = 0;
    }
    else
    {
      LastErrorFailHr = wil::details::GetLastErrorFailHr(v14);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v18);
      WindowsStorage::Utilities::Identity::~Identity((WindowsStorage::Utilities::Identity *)v22);
      wil::details::lambda_call<_lambda_70b204013488a836da8c9e05ae18fd45_>::~lambda_call<_lambda_70b204013488a836da8c9e05ae18fd45_>((TraceProvider::CreateFile2BrokerActivity *)v23);
      result = LastErrorFailHr;
    }
  }
  catch ( ... )
  {
    LODWORD(v18[0]) = wil::details::in1diag3::Return_CaughtException(
                        retaddr,
                        (void *)0xA9,
                        (unsigned int)"onecore\\base\\windows.storage\\src\\win32broker.cpp",
                        v12);
    wil::details::lambda_call<_lambda_70b204013488a836da8c9e05ae18fd45_>::~lambda_call<_lambda_70b204013488a836da8c9e05ae18fd45_>((TraceProvider::CreateFile2BrokerActivity *)v23);
    return LODWORD(v18[0]);
  }
  return result;
}

```

## disassembly

```asm
0x180017940  push    rbx
0x180017942  push    rsi
0x180017943  push    r12
0x180017945  push    r14
0x180017947  push    r15
0x180017949  sub     rsp, 240h
0x180017950  mov     rax, cs:__security_cookie
0x180017957  xor     rax, rsp
0x18001795a  mov     [rsp+268h+var_38], rax
0x180017962  mov     ebx, r9d
0x180017965  mov     r15d, r8d
0x180017968  mov     r14, rdx
0x18001796b  mov     r12d, [rsp+268h+arg_20]
0x180017973  mov     rsi, [rsp+268h+arg_38]
0x18001797b  lea     rcx, [rsp+268h+var_198]
0x180017983  call    ??$start_scoped_activity@VCreateFile2BrokerActivity@TraceProvider@@@@YA?A_PXZ
0x180017988  nop
0x180017989  mov     qword ptr [rsi], 0
0x180017990  lea     rcx, [rsp+268h+var_1F8]; this
0x180017995  call    ??0Identity@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::Identity::Identity(void)
0x18001799a  nop
0x18001799b  mov     [rsp+268h+var_238], 0
0x1800179a0  mov     r9d, 0FFFDh
0x1800179a6  lea     r8, [rsp+268h+var_238]
0x1800179ab  mov     rdx, r14
0x1800179ae  lea     rcx, [rsp+268h+var_1F8]
0x1800179b3  call    ?IsAllowed@FilePathAccess@Win32BrokeredAPIs@WindowsStorage@@SA_NAEAVIdentity@Utilities@3@PEBGPEA_NW4PathAccessChecks@Storage@Internal@Windows@ABI@@@Z; WindowsStorage::Win32BrokeredAPIs::FilePathAccess::IsAllowed(WindowsStorage::Utilities::Identity &,ushort const *,bool *,ABI::Windows::Internal::Storage::PathAccessChecks)
0x1800179b8  test    al, al
0x1800179ba  jnz     short loc_1800179DE
0x1800179bc  lea     rcx, [rsp+268h+var_1F8]; this
0x1800179c1  call    ??1Identity@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::Identity::~Identity(void)
0x1800179c6  nop
0x1800179c7  lea     rcx, [rsp+268h+var_198]; this
0x1800179cf  call    ??1?$lambda_call@V_lambda_70b204013488a836da8c9e05ae18fd45_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_70b204013488a836da8c9e05ae18fd45_>::~lambda_call<_lambda_70b204013488a836da8c9e05ae18fd45_>(void)
0x1800179d4  mov     eax, 80070005h
0x1800179d9  jmp     loc_180017B3F
0x1800179de  mov     eax, [rsp+268h+arg_28]
0x1800179e5  cmp     [rsp+268h+var_238], 0
0x1800179ea  jnz     short loc_180017A43
0x1800179ec  bt      eax, 0Ah
0x1800179f0  jnb     short loc_180017A14
0x1800179f2  lea     rcx, [rsp+268h+var_1F8]; this
0x1800179f7  call    ??1Identity@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::Identity::~Identity(void)
0x1800179fc  nop
0x1800179fd  lea     rcx, [rsp+268h+var_198]; this
0x180017a05  call    ??1?$lambda_call@V_lambda_70b204013488a836da8c9e05ae18fd45_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_70b204013488a836da8c9e05ae18fd45_>::~lambda_call<_lambda_70b204013488a836da8c9e05ae18fd45_>(void)
0x180017a0a  mov     eax, 80070005h
0x180017a0f  jmp     loc_180017B3F
0x180017a14  mov     ecx, [rsp+268h+arg_30]
0x180017a1b  bt      ecx, 15h
0x180017a1f  jnb     short loc_180017A4A
0x180017a21  lea     rcx, [rsp+268h+var_1F8]; this
0x180017a26  call    ??1Identity@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::Identity::~Identity(void)
0x180017a2b  nop
0x180017a2c  lea     rcx, [rsp+268h+var_198]; this
0x180017a34  call    ??1?$lambda_call@V_lambda_70b204013488a836da8c9e05ae18fd45_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_70b204013488a836da8c9e05ae18fd45_>::~lambda_call<_lambda_70b204013488a836da8c9e05ae18fd45_>(void)
0x180017a39  mov     eax, 80070005h
0x180017a3e  jmp     loc_180017B3F
0x180017a43  mov     ecx, [rsp+268h+arg_30]
0x180017a4a  mov     [rsp+268h+var_21C], eax
0x180017a4e  mov     [rsp+268h+var_218], ecx
0x180017a52  mov     [rsp+268h+var_214], 0
0x180017a5a  mov     [rsp+268h+var_220], 20h ; ' '
0x180017a62  mov     [rsp+268h+var_208], 0
0x180017a6b  mov     [rsp+268h+var_210], 0
0x180017a74  lea     rax, [rsp+268h+var_220]
0x180017a79  mov     [rsp+268h+var_248], rax
0x180017a7e  mov     r9d, r12d
0x180017a81  mov     r8d, ebx
0x180017a84  mov     edx, r15d
0x180017a87  mov     rcx, r14
0x180017a8a  call    cs:__imp_CreateFile2
0x180017a90  mov     rbx, rax
0x180017a93  mov     [rsp+268h+var_230], rax
0x180017a98  inc     rax
0x180017a9b  test    rax, 0FFFFFFFFFFFFFFFEh
0x180017aa1  jnz     short loc_180017AD1
0x180017aa3  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180017aa8  mov     ebx, eax
0x180017aaa  lea     rcx, [rsp+268h+var_230]
0x180017aaf  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180017ab4  nop
0x180017ab5  lea     rcx, [rsp+268h+var_1F8]; this
0x180017aba  call    ??1Identity@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::Identity::~Identity(void)
0x180017abf  nop
0x180017ac0  lea     rcx, [rsp+268h+var_198]; this
0x180017ac8  call    ??1?$lambda_call@V_lambda_70b204013488a836da8c9e05ae18fd45_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_70b204013488a836da8c9e05ae18fd45_>::~lambda_call<_lambda_70b204013488a836da8c9e05ae18fd45_>(void)
0x180017acd  mov     eax, ebx
0x180017acf  jmp     short loc_180017B3F
0x180017ad1  cmp     [rsp+268h+var_238], 0
0x180017ad6  jnz     short loc_180017AFB
0x180017ad8  test    r15d, 116h
0x180017adf  jz      short loc_180017AFB
0x180017ae1  lea     rax, [rsp+268h+var_1F8]
0x180017ae6  mov     [rsp+268h+var_228], rax
0x180017aeb  lea     r9, [rsp+268h+var_228]
0x180017af0  mov     rdx, r14; struct _GUID *
0x180017af3  mov     rcx, rbx; hFile
0x180017af6  call    WindowsStorage__Utilities__ModifyZoneIdentifierOnPath__lambda_582adc48acbb24e7e5f85ee00fe99bbe___
0x180017afb  mov     [rsp+268h+var_230], 0FFFFFFFFFFFFFFFFh
0x180017b04  mov     [rsi], rbx
0x180017b07  lea     rcx, [rsp+268h+var_230]
0x180017b0c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180017b11  nop
0x180017b12  lea     rcx, [rsp+268h+var_1F8]; this
0x180017b17  call    ??1Identity@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::Identity::~Identity(void)
0x180017b1c  nop
0x180017b1d  lea     rcx, [rsp+268h+var_198]; this
0x180017b25  call    ??1?$lambda_call@V_lambda_70b204013488a836da8c9e05ae18fd45_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_70b204013488a836da8c9e05ae18fd45_>::~lambda_call<_lambda_70b204013488a836da8c9e05ae18fd45_>(void)
0x180017b2a  xor     eax, eax
0x180017b2c  jmp     short loc_180017B3F
0x180017b2e  lea     rcx, [rsp+268h+var_198]; this
0x180017b36  call    ??1?$lambda_call@V_lambda_70b204013488a836da8c9e05ae18fd45_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_70b204013488a836da8c9e05ae18fd45_>::~lambda_call<_lambda_70b204013488a836da8c9e05ae18fd45_>(void)
0x180017b3b  mov     eax, dword ptr [rsp+268h+var_230]
0x180017b3f  mov     rcx, [rsp+268h+var_38]
0x180017b47  xor     rcx, rsp; StackCookie
0x180017b4a  call    __security_check_cookie
0x180017b4f  add     rsp, 240h
0x180017b56  pop     r15
0x180017b58  pop     r14
0x180017b5a  pop     r12
0x180017b5c  pop     rsi
0x180017b5d  pop     rbx
0x180017b5e  retn
```
