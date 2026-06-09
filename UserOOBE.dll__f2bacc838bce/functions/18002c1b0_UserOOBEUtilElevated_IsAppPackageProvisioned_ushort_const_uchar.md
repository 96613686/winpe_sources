# UserOOBEUtilElevated::IsAppPackageProvisioned(ushort const *,uchar *)

- ea: `0x18002c1b0`
- end: `0x18002c3b7`
- name: `?IsAppPackageProvisioned@UserOOBEUtilElevated@@UEAAJPEBGPEAE@Z`
- size: `519`
- prototype: `__int64 __fastcall(UserOOBEUtilElevated *__hidden this, const unsigned __int16 *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800032b0`
- `0x1800041dc`
- `0x180007134`
- `0x18000ee5c`
- `0x18001136c`
- `0x180012328`
- `0x18002c1b0`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18002c21e`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18002c21e`

## string_xrefs

- `0x18002c285`: `shell\oobe\user\dll\useroobeutilelevated.cpp`
- `0x18002c2ea`: `shell\oobe\user\dll\useroobeutilelevated.cpp`
- `0x18002c339`: `shell\oobe\user\dll\useroobeutilelevated.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UserOOBEUtilElevated::IsAppPackageProvisioned(
        UserOOBEUtilElevated *this,
        const unsigned __int16 *a2,
        unsigned __int8 *a3)
{
  int v4; // ebx
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, _QWORD, __int64, __int64 **); // rbx
  __int64 v7; // rax
  int v8; // eax
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // rdx
  int v13; // [rsp+20h] [rbp-60h]
  __int64 *v14; // [rsp+30h] [rbp-50h] BYREF
  __int64 v15; // [rsp+38h] [rbp-48h] BYREF
  __int64 v16; // [rsp+40h] [rbp-40h] BYREF
  __int64 v17; // [rsp+48h] [rbp-38h] BYREF
  const unsigned __int16 *v18; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF
  __int64 v20; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v18 = a2;
  *a3 = 0;
  v20 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Management.Deployment.PackageManager",
    0x2Du,
    0x2Cu);
  v16 = 0;
  v17 = 0;
  v4 = RoActivateInstance(v20, &v17);
  if ( v4 >= 0 )
  {
    if ( !memcmp_0(&GUID_f7aad08d_0840_46f2_b5d8_cad47693a095, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      v16 = v17;
    }
    else
    {
      v4 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v17)(
             v17,
             &GUID_f7aad08d_0840_46f2_b5d8_cad47693a095,
             &v16);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
  }
  if ( v4 >= 0 )
  {
    v14 = 0;
    v5 = v16;
    v6 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 **))(*(_QWORD *)v16 + 104LL);
    v14 = 0;
    v7 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v18);
    v8 = v6(v5, *(_QWORD *)(v7 + 24), 41, &v14);
    v4 = v8;
    if ( v8 >= 0 )
    {
      v15 = 0;
      v9 = *v14;
      v15 = 0;
      v10 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v9 + 48))(v14, &v15);
      v4 = v10;
      if ( v10 >= 0 )
      {
        v10 = (*(__int64 (__fastcall **)(__int64, unsigned __int8 *))(*(_QWORD *)v15 + 56LL))(v15, a3);
        v4 = v10;
        if ( v10 >= 0 )
        {
          wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v15);
          wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v14);
          v4 = 0;
          goto LABEL_16;
        }
        v11 = 36;
      }
      else
      {
        v11 = 35;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"shell\\oobe\\user\\dll\\useroobeutilelevated.cpp",
        (const char *)(unsigned int)v10,
        v13);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v15);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x21,
        (unsigned int)"shell\\oobe\\user\\dll\\useroobeutilelevated.cpp",
        (const char *)(unsigned int)v8,
        v13);
    }
    wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v14);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobeutilelevated.cpp",
      (const char *)(unsigned int)v4,
      v13);
  }
LABEL_16:
  wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v16);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002c1b0  mov     [rsp-18h+arg_0], rbx
0x18002c1b5  push    rbp
0x18002c1b6  push    rsi
0x18002c1b7  push    rdi
0x18002c1b8  mov     rbp, rsp
0x18002c1bb  sub     rsp, 80h
0x18002c1c2  mov     rax, cs:__security_cookie
0x18002c1c9  xor     rax, rsp
0x18002c1cc  mov     [rbp+var_8], rax
0x18002c1d0  mov     rsi, r8
0x18002c1d3  mov     [rbp+var_30], rdx
0x18002c1d7  mov     byte ptr [r8], 0
0x18002c1db  mov     [rbp+var_40], 0
0x18002c1e3  mov     [rbp+var_10], 0
0x18002c1eb  mov     r9d, 2Ch ; ','; unsigned int
0x18002c1f1  lea     r8d, [r9+1]; unsigned int
0x18002c1f5  lea     rdx, ?RuntimeClass_Windows_Management_Deployment_PackageManager@@3QBGB; "Windows.Management.Deployment.PackageMa"...
0x18002c1fc  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18002c200  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002c205  nop
0x18002c206  mov     [rbp+var_40], 0
0x18002c20e  mov     [rbp+var_38], 0
0x18002c216  lea     rdx, [rbp+var_38]
0x18002c21a  mov     rcx, [rbp+var_10]
0x18002c21e  call    cs:__imp_RoActivateInstance
0x18002c224  mov     ebx, eax
0x18002c226  test    eax, eax
0x18002c228  js      short loc_18002C27A
0x18002c22a  mov     r8d, 10h; Size
0x18002c230  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x18002c237  lea     rcx, _GUID_f7aad08d_0840_46f2_b5d8_cad47693a095; Buf1
0x18002c23e  call    memcmp_0
0x18002c243  mov     rcx, [rbp+var_38]
0x18002c247  test    eax, eax
0x18002c249  jnz     short loc_18002C251
0x18002c24b  mov     [rbp+var_40], rcx
0x18002c24f  jmp     short loc_18002C27A
0x18002c251  mov     rax, [rcx]
0x18002c254  lea     r8, [rbp+var_40]
0x18002c258  lea     rdx, _GUID_f7aad08d_0840_46f2_b5d8_cad47693a095
0x18002c25f  mov     rax, [rax]
0x18002c262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c267  mov     ebx, eax
0x18002c269  mov     rcx, [rbp+var_38]
0x18002c26d  mov     rax, [rcx]
0x18002c270  mov     rax, [rax+10h]
0x18002c274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c279  nop
0x18002c27a  test    ebx, ebx
0x18002c27c  jns     short loc_18002C29B
0x18002c27e  mov     rcx, [rbp+18h]; this
0x18002c282  mov     r9d, ebx; char *
0x18002c285  lea     r8, aShellOobeUserD_3; "shell\\oobe\\user\\dll\\useroobeutilele"...
0x18002c28c  mov     edx, 1Fh; void *
0x18002c291  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c296  jmp     loc_18002C38D
0x18002c29b  mov     [rbp+var_50], 0
0x18002c2a3  mov     rdi, [rbp+var_40]
0x18002c2a7  mov     rax, [rdi]
0x18002c2aa  mov     rbx, [rax+68h]
0x18002c2ae  mov     [rbp+var_50], 0
0x18002c2b6  lea     rdx, [rbp+var_30]
0x18002c2ba  lea     rcx, [rbp+hstringHeader]
0x18002c2be  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002c2c3  nop
0x18002c2c4  lea     r9, [rbp+var_50]
0x18002c2c8  mov     r8d, 29h ; ')'
0x18002c2ce  mov     rdx, [rax+18h]
0x18002c2d2  mov     rcx, rdi
0x18002c2d5  mov     rax, rbx
0x18002c2d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c2dd  mov     ebx, eax
0x18002c2df  test    eax, eax
0x18002c2e1  jns     short loc_18002C30A
0x18002c2e3  mov     rcx, [rbp+18h]; this
0x18002c2e7  mov     r9d, eax; char *
0x18002c2ea  lea     r8, aShellOobeUserD_3; "shell\\oobe\\user\\dll\\useroobeutilele"...
0x18002c2f1  mov     edx, 21h ; '!'; void *
0x18002c2f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c2fb  nop
0x18002c2fc  lea     rcx, [rbp+var_50]
0x18002c300  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x18002c305  jmp     loc_18002C38D
0x18002c30a  mov     [rbp+var_48], 0
0x18002c312  mov     rcx, [rbp+var_50]
0x18002c316  mov     rax, [rcx]
0x18002c319  mov     [rbp+var_48], 0
0x18002c321  lea     rdx, [rbp+var_48]
0x18002c325  mov     rax, [rax+30h]
0x18002c329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c32e  mov     ebx, eax
0x18002c330  test    eax, eax
0x18002c332  jns     short loc_18002C358
0x18002c334  mov     edx, 23h ; '#'; void *
0x18002c339  lea     r8, aShellOobeUserD_3; "shell\\oobe\\user\\dll\\useroobeutilele"...
0x18002c340  mov     r9d, eax; char *
0x18002c343  mov     rcx, [rbp+18h]; this
0x18002c347  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c34c  nop
0x18002c34d  lea     rcx, [rbp+var_48]
0x18002c351  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x18002c356  jmp     short loc_18002C2FC
0x18002c358  mov     rcx, [rbp+var_48]
0x18002c35c  mov     rax, [rcx]
0x18002c35f  mov     rdx, rsi
0x18002c362  mov     rax, [rax+38h]
0x18002c366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c36b  mov     ebx, eax
0x18002c36d  test    eax, eax
0x18002c36f  jns     short loc_18002C378
0x18002c371  mov     edx, 24h ; '$'
0x18002c376  jmp     short loc_18002C339
0x18002c378  lea     rcx, [rbp+var_48]
0x18002c37c  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x18002c381  nop
0x18002c382  lea     rcx, [rbp+var_50]
0x18002c386  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x18002c38b  xor     ebx, ebx
0x18002c38d  lea     rcx, [rbp+var_40]
0x18002c391  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x18002c396  mov     eax, ebx
0x18002c398  mov     rcx, [rbp+var_8]
0x18002c39c  xor     rcx, rsp; StackCookie
0x18002c39f  call    __security_check_cookie
0x18002c3a4  mov     rbx, [rsp+80h+arg_0]
0x18002c3ac  add     rsp, 80h
0x18002c3b3  pop     rdi
0x18002c3b4  pop     rsi
0x18002c3b5  pop     rbp
0x18002c3b6  retn
```
