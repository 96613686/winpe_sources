# OOBEOneDriveOptin::TryPinOfficeApps(ushort const *,uint *,ulong *)

- ea: `0x18001c0e0`
- end: `0x18001c376`
- name: `?TryPinOfficeApps@OOBEOneDriveOptin@@UEAAJPEBGPEAIPEAK@Z`
- size: `662`
- prototype: `__int64 __fastcall(OOBEOneDriveOptin *__hidden this, const unsigned __int16 *, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800032b0`
- `0x180007134`
- `0x18000e270`
- `0x18001136c`
- `0x180012328`
- `0x180019e60`
- `0x18001bd7c`
- `0x18001c0e0`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001c1c9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001c1c9`
- `api-ms-win-oobe-notification-l1-1-0!OOBEComplete` at `0x18001c207`
- `api-ms-win-oobe-notification-l1-1-0!OOBEComplete` at `0x18001c207`

## string_xrefs

- `0x18001c1aa`: `Windows.Internal.Taskbar.PinnedAuxiliaryItems`
- `0x18001c153`: `shell\oobe\user\dll\oobesyncengineapi.cpp`
- `0x18001c1dc`: `shell\oobe\user\dll\oobesyncengineapi.cpp`
- `0x18001c24c`: `shell\oobe\user\dll\oobesyncengineapi.cpp`
- `0x18001c28a`: `shell\oobe\user\dll\oobesyncengineapi.cpp`
- `0x18001c2e7`: `shell\oobe\user\dll\oobesyncengineapi.cpp`
- `0x18001c310`: `shell\oobe\user\dll\oobesyncengineapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall OOBEOneDriveOptin::TryPinOfficeApps(
        OOBEOneDriveOptin *this,
        const unsigned __int16 *a2,
        unsigned int *a3,
        unsigned int *a4)
{
  int v7; // eax
  __int64 v8; // rcx
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // rcx
  int ActivationFactory; // eax
  __int64 v13; // rdx
  int v14; // eax
  int v15; // eax
  unsigned int v16; // edi
  unsigned int i; // ebx
  int v18; // eax
  int v19; // esi
  int v21; // [rsp+20h] [rbp-60h]
  __int64 v22; // [rsp+30h] [rbp-50h] BYREF
  __int64 v23; // [rsp+38h] [rbp-48h] BYREF
  unsigned int v24; // [rsp+40h] [rbp-40h] BYREF
  int v25; // [rsp+44h] [rbp-3Ch] BYREF
  unsigned int v26; // [rsp+48h] [rbp-38h] BYREF
  _DWORD v27[3]; // [rsp+4Ch] [rbp-34h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF
  __int64 v29; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  *a3 = 0;
  *a4 = 0;
  *(_QWORD *)&v27[1] = 0;
  v7 = OOBEOneDriveOptin::TokenizeAumids(this, a2, &v27[1]);
  v9 = v7;
  if ( v7 >= 0 )
  {
    v24 = 0;
    v7 = OOBEOneDriveOptin::GetAndValidateNumRequests(v8, *(_QWORD *)&v27[1], &v24);
    v9 = v7;
    if ( v7 < 0 )
    {
      v10 = 355;
      goto LABEL_5;
    }
    if ( v24 )
    {
      *a3 = v24;
      v11 = *((_QWORD *)this + 5);
      v22 = v11;
      if ( v11 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
        v11 = v22;
      }
      if ( !v11 )
      {
        v22 = 0;
        v29 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.Internal.Taskbar.PinnedAuxiliaryItems",
          0x2Eu,
          0x2Du);
        ActivationFactory = RoGetActivationFactory(v29, &GUID_a58229bb_aa2f_4643_b94f_4f90309f1f2b, &v22);
        v9 = ActivationFactory;
        if ( ActivationFactory < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x16F,
            (unsigned int)"shell\\oobe\\user\\dll\\oobesyncengineapi.cpp",
            (const char *)(unsigned int)ActivationFactory,
            v21);
LABEL_12:
          wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v22);
          goto LABEL_31;
        }
      }
      v25 = 0;
      if ( !(unsigned int)OOBEComplete(&v25) || (v13 = 4, v25) )
        v13 = 5;
      v23 = 0;
      v14 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64 *))(*(_QWORD *)v22 + 48LL))(
              v22,
              v13,
              *(_QWORD *)&v27[1],
              &v23);
      if ( v14 >= 0 )
      {
        v26 = 0;
        v15 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v23 + 56LL))(v23, &v26);
        v9 = v15;
        if ( v15 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x17E,
            (unsigned int)"shell\\oobe\\user\\dll\\oobesyncengineapi.cpp",
            (const char *)(unsigned int)v15,
            v21);
          wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v23);
          goto LABEL_12;
        }
        v16 = 0;
        for ( i = 0; i < v26; ++i )
        {
          v27[0] = 0;
          v18 = (*(__int64 (__fastcall **)(__int64, _QWORD, _DWORD *))(*(_QWORD *)v23 + 48LL))(v23, i, v27);
          v19 = v18;
          if ( v18 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x183,
              (unsigned int)"shell\\oobe\\user\\dll\\oobesyncengineapi.cpp",
              (const char *)(unsigned int)v18,
              v21);
            wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v23);
            wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v22);
            v9 = v19;
            goto LABEL_31;
          }
          if ( v27[0] >= 0 )
            v16 |= 1 << i;
          else
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x184,
              (unsigned int)"shell\\oobe\\user\\dll\\oobesyncengineapi.cpp",
              (const char *)v27[0],
              v21);
        }
        *a4 = v16;
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x177,
          (unsigned int)"shell\\oobe\\user\\dll\\oobesyncengineapi.cpp",
          (const char *)(unsigned int)v14,
          v21);
      }
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v23);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v22);
    }
    v9 = 0;
    goto LABEL_31;
  }
  v10 = 351;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"shell\\oobe\\user\\dll\\oobesyncengineapi.cpp",
    (const char *)(unsigned int)v7,
    v21);
LABEL_31:
  wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v27[1]);
  return v9;
}

```

## disassembly

```asm
0x18001c0e0  push    rbp
0x18001c0e2  push    rbx
0x18001c0e3  push    rsi
0x18001c0e4  push    rdi
0x18001c0e5  push    r14
0x18001c0e7  mov     rbp, rsp
0x18001c0ea  sub     rsp, 80h
0x18001c0f1  mov     rax, cs:__security_cookie
0x18001c0f8  xor     rax, rsp
0x18001c0fb  mov     [rbp+var_8], rax
0x18001c0ff  mov     r14, r9
0x18001c102  mov     rdi, r8
0x18001c105  mov     rsi, rcx
0x18001c108  mov     dword ptr [r8], 0
0x18001c10f  mov     dword ptr [r9], 0
0x18001c116  mov     qword ptr [rbp+var_34+4], 0
0x18001c11e  lea     r8, [rbp+var_34+4]
0x18001c122  call    ?TokenizeAumids@OOBEOneDriveOptin@@AEAAJPEBGPEAPEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@Internal@Collections@Foundation@Windows@@@Z; OOBEOneDriveOptin::TokenizeAumids(ushort const *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> * *)
0x18001c127  mov     ebx, eax
0x18001c129  test    eax, eax
0x18001c12b  jns     short loc_18001C134
0x18001c12d  mov     edx, 15Fh
0x18001c132  jmp     short loc_18001C153
0x18001c134  mov     [rbp+var_40], 0
0x18001c13b  lea     r8, [rbp+var_40]
0x18001c13f  mov     rdx, qword ptr [rbp+var_34+4]
0x18001c143  call    ?GetAndValidateNumRequests@OOBEOneDriveOptin@@AEAAJPEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@Internal@Collections@Foundation@Windows@@PEAI@Z; OOBEOneDriveOptin::GetAndValidateNumRequests(Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> *,uint *)
0x18001c148  mov     ebx, eax
0x18001c14a  test    eax, eax
0x18001c14c  jns     short loc_18001C16B
0x18001c14e  mov     edx, 163h; void *
0x18001c153  lea     r8, aShellOobeUserD_8; "shell\\oobe\\user\\dll\\oobesyncenginea"...
0x18001c15a  mov     r9d, eax; char *
0x18001c15d  mov     rcx, [rbp+28h]; this
0x18001c161  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c166  jmp     loc_18001C351
0x18001c16b  mov     eax, [rbp+var_40]
0x18001c16e  test    eax, eax
0x18001c170  jz      loc_18001C34F
0x18001c176  mov     [rdi], eax
0x18001c178  mov     rcx, [rsi+28h]
0x18001c17c  mov     [rbp+var_50], rcx
0x18001c180  test    rcx, rcx
0x18001c183  jz      short loc_18001C195
0x18001c185  mov     rax, [rcx]
0x18001c188  mov     rax, [rax+8]
0x18001c18c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c191  mov     rcx, [rbp+var_50]
0x18001c195  test    rcx, rcx
0x18001c198  jnz     short loc_18001C1FC
0x18001c19a  mov     [rbp+var_50], rcx
0x18001c19e  mov     [rbp+var_10], rcx
0x18001c1a2  lea     r9d, [rcx+2Dh]; unsigned int
0x18001c1a6  lea     r8d, [rcx+2Eh]; unsigned int
0x18001c1aa  lea     rdx, ?RuntimeClass_Windows_Internal_Taskbar_PinnedAuxiliaryItems@@3QBGB; "Windows.Internal.Taskbar.PinnedAuxiliar"...
0x18001c1b1  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18001c1b5  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001c1ba  lea     r8, [rbp+var_50]
0x18001c1be  lea     rdx, _GUID_a58229bb_aa2f_4643_b94f_4f90309f1f2b
0x18001c1c5  mov     rcx, [rbp+var_10]
0x18001c1c9  call    cs:__imp_RoGetActivationFactory
0x18001c1cf  mov     ebx, eax
0x18001c1d1  test    eax, eax
0x18001c1d3  jns     short loc_18001C1FC
0x18001c1d5  mov     rcx, [rbp+28h]; this
0x18001c1d9  mov     r9d, eax; char *
0x18001c1dc  lea     r8, aShellOobeUserD_8; "shell\\oobe\\user\\dll\\oobesyncenginea"...
0x18001c1e3  mov     edx, 16Fh; void *
0x18001c1e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c1ed  nop
0x18001c1ee  lea     rcx, [rbp+var_50]
0x18001c1f2  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x18001c1f7  jmp     loc_18001C351
0x18001c1fc  mov     [rbp+var_3C], 0
0x18001c203  lea     rcx, [rbp+var_3C]
0x18001c207  call    cs:__imp_OOBEComplete
0x18001c20d  test    eax, eax
0x18001c20f  jz      short loc_18001C21C
0x18001c211  cmp     [rbp+var_3C], 0
0x18001c215  mov     edx, 4
0x18001c21a  jz      short loc_18001C221
0x18001c21c  mov     edx, 5
0x18001c221  mov     [rbp+var_48], 0
0x18001c229  mov     rcx, [rbp+var_50]
0x18001c22d  mov     rax, [rcx]
0x18001c230  lea     r9, [rbp+var_48]
0x18001c234  mov     r8, qword ptr [rbp+var_34+4]
0x18001c238  mov     rax, [rax+30h]
0x18001c23c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c241  mov     rcx, [rbp+28h]; this
0x18001c245  test    eax, eax
0x18001c247  jns     short loc_18001C262
0x18001c249  mov     r9d, eax; char *
0x18001c24c  lea     r8, aShellOobeUserD_8; "shell\\oobe\\user\\dll\\oobesyncenginea"...
0x18001c253  mov     edx, 177h; void *
0x18001c258  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001c25d  jmp     loc_18001C33C
0x18001c262  mov     [rbp+var_38], 0
0x18001c269  mov     rcx, [rbp+var_48]
0x18001c26d  mov     rax, [rcx]
0x18001c270  lea     rdx, [rbp+var_38]
0x18001c274  mov     rax, [rax+38h]
0x18001c278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c27d  mov     ebx, eax
0x18001c27f  test    eax, eax
0x18001c281  jns     short loc_18001C2AA
0x18001c283  mov     rcx, [rbp+28h]; this
0x18001c287  mov     r9d, eax; char *
0x18001c28a  lea     r8, aShellOobeUserD_8; "shell\\oobe\\user\\dll\\oobesyncenginea"...
0x18001c291  mov     edx, 17Eh; void *
0x18001c296  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c29b  nop
0x18001c29c  lea     rcx, [rbp+var_48]
0x18001c2a0  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x18001c2a5  jmp     loc_18001C1EE
0x18001c2aa  xor     edi, edi
0x18001c2ac  xor     ebx, ebx
0x18001c2ae  cmp     ebx, [rbp+var_38]
0x18001c2b1  jnb     loc_18001C339
0x18001c2b7  mov     dword ptr [rbp+var_34], 0
0x18001c2be  mov     rcx, [rbp+var_48]
0x18001c2c2  mov     rax, [rcx]
0x18001c2c5  lea     r8, [rbp+var_34]
0x18001c2c9  mov     edx, ebx
0x18001c2cb  mov     rax, [rax+30h]
0x18001c2cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c2d4  mov     esi, eax
0x18001c2d6  test    eax, eax
0x18001c2d8  js      short loc_18001C309
0x18001c2da  mov     r9d, dword ptr [rbp+var_34]; char *
0x18001c2de  test    r9d, r9d
0x18001c2e1  jns     short loc_18001C2FA
0x18001c2e3  mov     rcx, [rbp+28h]; this
0x18001c2e7  lea     r8, aShellOobeUserD_8; "shell\\oobe\\user\\dll\\oobesyncenginea"...
0x18001c2ee  mov     edx, 184h; void *
0x18001c2f3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001c2f8  jmp     short loc_18001C305
0x18001c2fa  mov     ecx, ebx
0x18001c2fc  mov     eax, 1
0x18001c301  shl     eax, cl
0x18001c303  or      edi, eax
0x18001c305  inc     ebx
0x18001c307  jmp     short loc_18001C2AE
0x18001c309  mov     rcx, [rbp+28h]; this
0x18001c30d  mov     r9d, esi; char *
0x18001c310  lea     r8, aShellOobeUserD_8; "shell\\oobe\\user\\dll\\oobesyncenginea"...
0x18001c317  mov     edx, 183h; void *
0x18001c31c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c321  nop
0x18001c322  lea     rcx, [rbp+var_48]
0x18001c326  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x18001c32b  nop
0x18001c32c  lea     rcx, [rbp+var_50]
0x18001c330  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x18001c335  mov     ebx, esi
0x18001c337  jmp     short loc_18001C351
0x18001c339  mov     [r14], edi
0x18001c33c  lea     rcx, [rbp+var_48]
0x18001c340  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x18001c345  nop
0x18001c346  lea     rcx, [rbp+var_50]
0x18001c34a  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x18001c34f  xor     ebx, ebx
0x18001c351  lea     rcx, [rbp+var_34+4]
0x18001c355  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x18001c35a  mov     eax, ebx
0x18001c35c  mov     rcx, [rbp+var_8]
0x18001c360  xor     rcx, rsp; StackCookie
0x18001c363  call    __security_check_cookie
0x18001c368  add     rsp, 80h
0x18001c36f  pop     r14
0x18001c371  pop     rdi
0x18001c372  pop     rsi
0x18001c373  pop     rbx
0x18001c374  pop     rbp
0x18001c375  retn
```
