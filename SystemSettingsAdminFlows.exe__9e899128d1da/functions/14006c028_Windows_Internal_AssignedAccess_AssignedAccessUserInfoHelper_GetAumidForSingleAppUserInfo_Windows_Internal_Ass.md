# Windows::Internal::AssignedAccess::AssignedAccessUserInfoHelper::GetAumidForSingleAppUserInfo(Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *,ushort * *)

- ea: `0x14006c028`
- end: `0x14006c291`
- name: `?GetAumidForSingleAppUserInfo@AssignedAccessUserInfoHelper@AssignedAccess@Internal@Windows@@SAJPEAUIAssignedAccessUserInfo@234@PEAPEAG@Z`
- size: `617`
- prototype: `__int64 __fastcall(struct Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14006c3b8`

## callees

- `0x14000e428`
- `0x14000f164`
- `0x14000f384`
- `0x14001f3d4`
- `0x140059d0c`
- `0x1400694d0`
- `0x1400695a4`
- `0x14006c028`
- `0x14007d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14006c22e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14006c22e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14006c1d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14006c1d3`

## string_xrefs

- `0x14006c04a`: `shellcommondesktopbase\base\embedded\sys\lockdown\inc\assignedaccessconfigurationhelper.h`
- `0x14006c0b6`: `shellcommondesktopbase\base\embedded\sys\lockdown\inc\assignedaccessconfigurationhelper.h`
- `0x14006c10a`: `shellcommondesktopbase\base\embedded\sys\lockdown\inc\assignedaccessconfigurationhelper.h`
- `0x14006c18c`: `shellcommondesktopbase\base\embedded\sys\lockdown\inc\assignedaccessconfigurationhelper.h`
- `0x14006c207`: `shellcommondesktopbase\base\embedded\sys\lockdown\inc\assignedaccessconfigurationhelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::AssignedAccess::AssignedAccessUserInfoHelper::GetAumidForSingleAppUserInfo(
        struct Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *a1,
        unsigned __int16 **a2)
{
  unsigned int v3; // ebx
  int v4; // eax
  __int64 v5; // rdx
  __int64 v6; // r9
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r9
  int v10; // eax
  __int64 (__fastcall *v11)(__int64, HSTRING *); // rsi
  int v12; // eax
  char *StringRawBuffer; // rax
  const char *v14; // r9
  unsigned __int16 *v15; // rax
  HSTRING string; // [rsp+20h] [rbp-20h] BYREF
  __int64 v18; // [rsp+28h] [rbp-18h] BYREF
  __int64 v19; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int16 *v20; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  char v22; // [rsp+70h] [rbp+30h] BYREF
  int v23; // [rsp+80h] [rbp+40h] BYREF
  __int64 v24; // [rsp+88h] [rbp+48h] BYREF

  if ( a1 )
  {
    *a2 = 0;
    v19 = 0;
    v4 = (*(__int64 (__fastcall **)(struct Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *, __int64 *))(*(_QWORD *)a1 + 64LL))(
           a1,
           &v19);
    v3 = v4;
    if ( v4 < 0 )
    {
      v5 = 89;
LABEL_7:
      v6 = (unsigned int)v4;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v5,
        (unsigned int)"shellcommondesktopbase\\base\\embedded\\sys\\lockdown\\inc\\assignedaccessconfigurationhelper.h",
        (const char *)v6,
        (int)string);
LABEL_26:
      ATL::CComPtrBase<ICbsSession>::~CComPtrBase<ICbsSession>(&v19);
      return v3;
    }
    v22 = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v19 + 72LL))(v19, &v22);
    v3 = v4;
    if ( v4 < 0 )
    {
      v5 = 92;
      goto LABEL_7;
    }
    if ( !v22 )
    {
      v3 = -2147024809;
      v6 = 2147942487LL;
      v5 = 94;
      goto LABEL_8;
    }
    v24 = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v19 + 120LL))(v19, &v24);
    v3 = v7;
    if ( v7 >= 0 )
    {
      v23 = 0;
      v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v24 + 56LL))(v24, &v23);
      v3 = v7;
      if ( v7 >= 0 )
      {
        if ( v23 == 1 )
        {
          v18 = 0;
          v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v24 + 48LL))(v24, 0, &v18);
          v3 = v10;
          if ( v10 >= 0 )
          {
            string = 0;
            v11 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v18 + 48LL);
            string = 0;
            v12 = v11(v18, &string);
            v3 = v12;
            if ( v12 >= 0 )
            {
              StringRawBuffer = (char *)WindowsGetStringRawBuffer(string, 0);
              wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                &v20,
                StringRawBuffer,
                0xFFFFFFFFFFFFFFFFuLL,
                v14);
              v15 = v20;
              v20 = 0;
              *a2 = v15;
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v20);
              Windows::Internal::String::~String((Windows::Internal::String *)&string);
              ATL::CComPtrBase<ICbsSession>::~CComPtrBase<ICbsSession>(&v18);
              ATL::CComPtrBase<ICbsSession>::~CComPtrBase<ICbsSession>(&v24);
              v3 = 0;
              goto LABEL_26;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x6A,
              (unsigned int)"shellcommondesktopbase\\base\\embedded\\sys\\lockdown\\inc\\assignedaccessconfigurationhelper.h",
              (const char *)(unsigned int)v12,
              (int)string);
            Windows::Internal::String::~String((Windows::Internal::String *)&string);
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x68,
              (unsigned int)"shellcommondesktopbase\\base\\embedded\\sys\\lockdown\\inc\\assignedaccessconfigurationhelper.h",
              (const char *)(unsigned int)v10,
              (int)string);
          }
          ATL::CComPtrBase<ICbsSession>::~CComPtrBase<ICbsSession>(&v18);
          goto LABEL_15;
        }
        v3 = -2147418113;
        v9 = 2147549183LL;
        v8 = 101;
LABEL_14:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v8,
          (unsigned int)"shellcommondesktopbase\\base\\embedded\\sys\\lockdown\\inc\\assignedaccessconfigurationhelper.h",
          (const char *)v9,
          (int)string);
LABEL_15:
        ATL::CComPtrBase<ICbsSession>::~CComPtrBase<ICbsSession>(&v24);
        goto LABEL_26;
      }
      v8 = 99;
    }
    else
    {
      v8 = 97;
    }
    v9 = (unsigned int)v7;
    goto LABEL_14;
  }
  v3 = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x56,
    (unsigned int)"shellcommondesktopbase\\base\\embedded\\sys\\lockdown\\inc\\assignedaccessconfigurationhelper.h",
    (const char *)0x80004003LL,
    (int)string);
  return v3;
}

```

## disassembly

```asm
0x14006c028  push    rbp
0x14006c02a  push    rbx
0x14006c02b  push    rsi
0x14006c02c  push    rdi
0x14006c02d  push    r14
0x14006c02f  mov     rbp, rsp
0x14006c032  sub     rsp, 40h
0x14006c036  mov     r14, rdx
0x14006c039  test    rcx, rcx
0x14006c03c  jnz     short loc_14006C060
0x14006c03e  mov     rcx, [rbp+28h]; this
0x14006c042  mov     ebx, 80004003h
0x14006c047  mov     r9d, ebx; char *
0x14006c04a  lea     r8, aShellcommondes_1; "shellcommondesktopbase\\base\\embedded"...
0x14006c051  mov     edx, 56h ; 'V'; void *
0x14006c056  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006c05b  jmp     loc_14006C284
0x14006c060  mov     qword ptr [rdx], 0
0x14006c067  mov     [rbp+var_10], 0
0x14006c06f  mov     rax, [rcx]
0x14006c072  lea     rdx, [rbp+var_10]
0x14006c076  mov     rax, [rax+40h]
0x14006c07a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006c07f  mov     ebx, eax
0x14006c081  test    eax, eax
0x14006c083  jns     short loc_14006C08C
0x14006c085  mov     edx, 59h ; 'Y'
0x14006c08a  jmp     short loc_14006C0AF
0x14006c08c  mov     [rbp+arg_0], 0
0x14006c090  mov     rcx, [rbp+var_10]
0x14006c094  mov     rax, [rcx]
0x14006c097  lea     rdx, [rbp+arg_0]
0x14006c09b  mov     rax, [rax+48h]
0x14006c09f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006c0a4  mov     ebx, eax
0x14006c0a6  test    eax, eax
0x14006c0a8  jns     short loc_14006C0C7
0x14006c0aa  mov     edx, 5Ch ; '\'; void *
0x14006c0af  mov     r9d, eax; char *
0x14006c0b2  mov     rcx, [rbp+28h]; this
0x14006c0b6  lea     r8, aShellcommondes_1; "shellcommondesktopbase\\base\\embedded"...
0x14006c0bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006c0c2  jmp     loc_14006C27B
0x14006c0c7  cmp     [rbp+arg_0], 0
0x14006c0cb  jnz     short loc_14006C0DC
0x14006c0cd  mov     ebx, 80070057h
0x14006c0d2  mov     r9d, ebx
0x14006c0d5  mov     edx, 5Eh ; '^'
0x14006c0da  jmp     short loc_14006C0B2
0x14006c0dc  mov     [rbp+arg_18], 0
0x14006c0e4  mov     rcx, [rbp+var_10]
0x14006c0e8  mov     rax, [rcx]
0x14006c0eb  lea     rdx, [rbp+arg_18]
0x14006c0ef  mov     rax, [rax+78h]
0x14006c0f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006c0f8  mov     ebx, eax
0x14006c0fa  test    eax, eax
0x14006c0fc  jns     short loc_14006C124
0x14006c0fe  mov     edx, 61h ; 'a'; void *
0x14006c103  mov     r9d, eax; char *
0x14006c106  mov     rcx, [rbp+28h]; this
0x14006c10a  lea     r8, aShellcommondes_1; "shellcommondesktopbase\\base\\embedded"...
0x14006c111  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006c116  lea     rcx, [rbp+arg_18]
0x14006c11a  call    ??1?$CComPtrBase@UICbsSession@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICbsSession>::~CComPtrBase<ICbsSession>(void)
0x14006c11f  jmp     loc_14006C27B
0x14006c124  mov     [rbp+arg_10], 0
0x14006c12b  mov     rcx, [rbp+arg_18]
0x14006c12f  mov     rax, [rcx]
0x14006c132  lea     rdx, [rbp+arg_10]
0x14006c136  mov     rax, [rax+38h]
0x14006c13a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006c13f  mov     ebx, eax
0x14006c141  test    eax, eax
0x14006c143  jns     short loc_14006C14C
0x14006c145  mov     edx, 63h ; 'c'
0x14006c14a  jmp     short loc_14006C103
0x14006c14c  cmp     [rbp+arg_10], 1
0x14006c150  jz      short loc_14006C161
0x14006c152  mov     ebx, 8000FFFFh
0x14006c157  mov     r9d, ebx
0x14006c15a  mov     edx, 65h ; 'e'
0x14006c15f  jmp     short loc_14006C106
0x14006c161  mov     [rbp+var_18], 0
0x14006c169  mov     rcx, [rbp+arg_18]
0x14006c16d  mov     rax, [rcx]
0x14006c170  lea     r8, [rbp+var_18]
0x14006c174  xor     edx, edx
0x14006c176  mov     rax, [rax+30h]
0x14006c17a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006c17f  mov     ebx, eax
0x14006c181  test    eax, eax
0x14006c183  jns     short loc_14006C1AB
0x14006c185  mov     rcx, [rbp+28h]; this
0x14006c189  mov     r9d, eax; char *
0x14006c18c  lea     r8, aShellcommondes_1; "shellcommondesktopbase\\base\\embedded"...
0x14006c193  mov     edx, 68h ; 'h'; void *
0x14006c198  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006c19d  lea     rcx, [rbp+var_18]
0x14006c1a1  call    ??1?$CComPtrBase@UICbsSession@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICbsSession>::~CComPtrBase<ICbsSession>(void)
0x14006c1a6  jmp     loc_14006C116
0x14006c1ab  mov     [rbp+string], 0
0x14006c1b3  mov     rdi, [rbp+var_18]
0x14006c1b7  mov     rax, [rdi]
0x14006c1ba  mov     rsi, [rax+30h]
0x14006c1be  mov     rbx, [rbp+string]
0x14006c1c2  test    rbx, rbx
0x14006c1c5  jz      short loc_14006C1E3
0x14006c1c7  lea     rcx, [rbp+var_8]; this
0x14006c1cb  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14006c1d0  mov     rcx, rbx; string
0x14006c1d3  call    cs:__imp_WindowsDeleteString
0x14006c1d9  lea     rcx, [rbp+var_8]; this
0x14006c1dd  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14006c1e2  nop
0x14006c1e3  mov     [rbp+string], 0
0x14006c1eb  lea     rdx, [rbp+string]
0x14006c1ef  mov     rcx, rdi
0x14006c1f2  mov     rax, rsi
0x14006c1f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006c1fa  mov     ebx, eax
0x14006c1fc  test    eax, eax
0x14006c1fe  jns     short loc_14006C228
0x14006c200  mov     rcx, [rbp+28h]; this
0x14006c204  mov     r9d, eax; char *
0x14006c207  lea     r8, aShellcommondes_1; "shellcommondesktopbase\\base\\embedded"...
0x14006c20e  mov     edx, 6Ah ; 'j'; void *
0x14006c213  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006c218  nop
0x14006c219  lea     rcx, [rbp+string]; this
0x14006c21d  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x14006c222  nop
0x14006c223  jmp     loc_14006C19D
0x14006c228  xor     edx, edx; length
0x14006c22a  mov     rcx, [rbp+string]; string
0x14006c22e  call    cs:__imp_WindowsGetStringRawBuffer
0x14006c234  or      r8, 0FFFFFFFFFFFFFFFFh
0x14006c238  mov     rdx, rax
0x14006c23b  lea     rcx, [rbp+var_8]
0x14006c23f  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x14006c244  mov     rax, [rbp+var_8]
0x14006c248  mov     [rbp+var_8], 0
0x14006c250  mov     [r14], rax
0x14006c253  lea     rcx, [rbp+var_8]
0x14006c257  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14006c25c  nop
0x14006c25d  lea     rcx, [rbp+string]; this
0x14006c261  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x14006c266  nop
0x14006c267  lea     rcx, [rbp+var_18]
0x14006c26b  call    ??1?$CComPtrBase@UICbsSession@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICbsSession>::~CComPtrBase<ICbsSession>(void)
0x14006c270  lea     rcx, [rbp+arg_18]
0x14006c274  call    ??1?$CComPtrBase@UICbsSession@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICbsSession>::~CComPtrBase<ICbsSession>(void)
0x14006c279  xor     ebx, ebx
0x14006c27b  lea     rcx, [rbp+var_10]
0x14006c27f  call    ??1?$CComPtrBase@UICbsSession@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICbsSession>::~CComPtrBase<ICbsSession>(void)
0x14006c284  mov     eax, ebx
0x14006c286  add     rsp, 40h
0x14006c28a  pop     r14
0x14006c28c  pop     rdi
0x14006c28d  pop     rsi
0x14006c28e  pop     rbx
0x14006c28f  pop     rbp
0x14006c290  retn
```
