# ComputerAccountHelper::DeleteAccount(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180072a78`
- end: `0x180072b85`
- name: `?DeleteAccount@ComputerAccountHelper@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `269`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002a020`

## callees

- `0x18000b6b4`
- `0x18000cfe4`
- `0x18002001c`
- `0x180072a78`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180072ab6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180072ab6`

## string_xrefs

- `0x180072ac9`: `onecoreuap\base\embedded\sys\lockdown\utils\lib\computeraccounthelper.cpp`
- `0x180072b1f`: `onecoreuap\base\embedded\sys\lockdown\utils\lib\computeraccounthelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ComputerAccountHelper::DeleteAccount(__int64 a1, __int64 a2)
{
  HRESULT v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rax
  __int64 (__fastcall *v6)(__int64, __int64, __int64 *); // r9
  __int64 v7; // r10
  int v8; // eax
  __int64 v9; // rdx
  int v11; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+8h]
  __int64 v13; // [rsp+40h] [rbp+10h] BYREF
  LPVOID v14; // [rsp+50h] [rbp+20h] BYREF

  v13 = a1;
  v14 = 0;
  v3 = CoCreateInstance(&CLSID_LocalUserAccounts, 0, 3u, &GUID_3c708557_c99d_4fa3_9231_56518418b4e4, &v14);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v13 = 0;
    v5 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
    v8 = v6(v7, v5, &v13);
    v4 = v8;
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v14 + 64LL))(v14, v13);
      v4 = v8;
      if ( v8 >= 0 )
      {
        wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v13);
        v4 = 0;
        goto LABEL_9;
      }
      v9 = 72;
    }
    else
    {
      v9 = 71;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\utils\\lib\\computeraccounthelper.cpp",
      (const char *)(unsigned int)v8,
      v11);
    wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v13);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x44,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\utils\\lib\\computeraccounthelper.cpp",
      (const char *)(unsigned int)v3,
      v11);
  }
LABEL_9:
  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v14);
  return v4;
}

```

## disassembly

```asm
0x180072a78  mov     r11, rsp
0x180072a7b  mov     [r11+10h], rbx
0x180072a7f  mov     [r11+20h], rdi
0x180072a83  mov     [r11+8], rcx
0x180072a87  push    rbp
0x180072a88  mov     rbp, rsp
0x180072a8b  sub     rsp, 30h
0x180072a8f  mov     rdi, rdx
0x180072a92  mov     [rbp+arg_10], 0
0x180072a9a  lea     rax, [rbp+arg_10]
0x180072a9e  mov     [r11-18h], rax
0x180072aa2  lea     r9, _GUID_3c708557_c99d_4fa3_9231_56518418b4e4; riid
0x180072aa9  xor     edx, edx; pUnkOuter
0x180072aab  lea     r8d, [rdx+3]; dwClsContext
0x180072aaf  lea     rcx, CLSID_LocalUserAccounts; rclsid
0x180072ab6  call    cs:__imp_CoCreateInstance
0x180072abc  mov     ebx, eax
0x180072abe  test    eax, eax
0x180072ac0  jns     short loc_180072ADF
0x180072ac2  mov     rcx, [rbp+8]; this
0x180072ac6  mov     r9d, eax; char *
0x180072ac9  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180072ad0  mov     edx, 44h ; 'D'; void *
0x180072ad5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072ada  jmp     loc_180072B6A
0x180072adf  mov     [rbp+arg_0], 0
0x180072ae7  mov     r10, [rbp+arg_10]
0x180072aeb  mov     rax, [r10]
0x180072aee  mov     r9, [rax+48h]
0x180072af2  mov     [rbp+arg_0], 0
0x180072afa  mov     rcx, rdi
0x180072afd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180072b02  lea     r8, [rbp+arg_0]
0x180072b06  mov     rdx, rax
0x180072b09  mov     rcx, r10
0x180072b0c  mov     rax, r9
0x180072b0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072b14  mov     ebx, eax
0x180072b16  test    eax, eax
0x180072b18  jns     short loc_180072B3E
0x180072b1a  mov     edx, 47h ; 'G'; void *
0x180072b1f  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180072b26  mov     r9d, eax; char *
0x180072b29  mov     rcx, [rbp+8]; this
0x180072b2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072b32  nop
0x180072b33  lea     rcx, [rbp+arg_0]
0x180072b37  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180072b3c  jmp     short loc_180072B6A
0x180072b3e  mov     rcx, [rbp+arg_10]
0x180072b42  mov     rax, [rcx]
0x180072b45  mov     rdx, [rbp+arg_0]
0x180072b49  mov     rax, [rax+40h]
0x180072b4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072b52  mov     ebx, eax
0x180072b54  test    eax, eax
0x180072b56  jns     short loc_180072B5F
0x180072b58  mov     edx, 48h ; 'H'
0x180072b5d  jmp     short loc_180072B1F
0x180072b5f  lea     rcx, [rbp+arg_0]
0x180072b63  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180072b68  xor     ebx, ebx
0x180072b6a  lea     rcx, [rbp+arg_10]
0x180072b6e  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180072b73  mov     eax, ebx
0x180072b75  mov     rbx, [rsp+30h+arg_8]
0x180072b7a  mov     rdi, [rsp+30h+arg_18]
0x180072b7f  add     rsp, 30h
0x180072b83  pop     rbp
0x180072b84  retn
```
