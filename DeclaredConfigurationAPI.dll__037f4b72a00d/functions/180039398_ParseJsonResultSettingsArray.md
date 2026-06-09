# ParseJsonResultSettingsArray

- ea: `0x180039398`
- end: `0x180039962`
- name: `ParseJsonResultSettingsArray`
- size: `1482`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003821c`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x18001438c`
- `0x1800143c8`
- `0x180018ac0`
- `0x180019188`
- `0x1800192b4`
- `0x180019d38`
- `0x1800370d4`
- `0x18003821c`
- `0x180039398`
- `0x18004ba8c`
- `0x180139010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800396a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800396a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039573`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800395ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039667`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003978e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039812`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003989c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800398f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039573`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800395ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039667`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003978e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039812`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003989c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800398f1`

## string_xrefs

- `0x18003941b`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparse.cpp`
- `0x18003948c`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparse.cpp`
- `0x1800394e6`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparse.cpp`
- `0x1800395cc`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparse.cpp`
- `0x180039645`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparse.cpp`
- `0x180039761`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparse.cpp`
- `0x1800397e5`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparse.cpp`
- `0x18003986f`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparse.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall ParseJsonResultSettingsArray(
        __int64 (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        __int64 a2,
        __int64 a3,
        HSTRING ****a4)
{
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  __int64 result; // rax
  unsigned int v11; // esi
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, _QWORD, __int64 *); // rbx
  int v14; // eax
  unsigned int v15; // ebx
  const char *v16; // r9
  int v17; // eax
  unsigned int v18; // ebx
  __int64 v19; // rax
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, _QWORD, HSTRING *); // rbx
  _QWORD *v22; // rdx
  __int64 v23; // rax
  int v24; // eax
  unsigned int v25; // ebx
  PCWSTR StringRawBuffer; // rax
  __int64 v27; // r8
  HSTRING ***v28; // rbx
  HSTRING ***v29; // rdi
  HSTRING **v30; // rbx
  __int64 v31; // rdi
  __int64 (__fastcall *v32)(__int64, _QWORD, _QWORD **); // r14
  __int64 *v33; // rax
  __int64 v34; // rax
  int v35; // eax
  unsigned int v36; // edi
  int v37; // eax
  unsigned int v38; // ebx
  HSTRING string; // [rsp+20h] [rbp-D8h] BYREF
  __int64 v40; // [rsp+28h] [rbp-D0h] BYREF
  __int64 v41; // [rsp+30h] [rbp-C8h] BYREF
  __int64 v42; // [rsp+38h] [rbp-C0h] BYREF
  _QWORD *v43; // [rsp+40h] [rbp-B8h] BYREF
  unsigned int v44; // [rsp+48h] [rbp-B0h] BYREF
  __int64 *v45; // [rsp+50h] [rbp-A8h] BYREF
  _QWORD v46[4]; // [rsp+58h] [rbp-A0h] BYREF
  char *v47[4]; // [rsp+78h] [rbp-80h] BYREF
  _BYTE v48[32]; // [rsp+98h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v40 = 0;
  v7 = (**a1)(a1, &GUID_d44662bc_dce3_59a8_9272_4b210f33908b, &v40);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = 6843;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparse.cpp",
      (const char *)(unsigned int)v7,
      (int)string);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
    return v8;
  }
  v44 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v40 + 56LL))(v40, &v44);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = 6847;
    goto LABEL_5;
  }
  v11 = 0;
  try
  {
    while ( v11 < v44 )
    {
      v41 = 0;
      v12 = v40;
      v13 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v40 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
      v14 = v13(v12, v11, &v41);
      v15 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1AC7,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparse.cpp",
          (const char *)(unsigned int)v14,
          (int)string);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
        return v15;
      }
      v42 = 0;
      v17 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v41 + 96LL))(v41, &v42);
      v18 = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1ACB,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparse.cpp",
          (const char *)(unsigned int)v17,
          (int)string);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
        return v18;
      }
      v19 = std::wstring::wstring((__int64)v48, a3);
      std::operator+<unsigned short>(v46, v19, L"Id");
      std::wstring::_Tidy_deallocate(v48);
      string = 0;
      std::wstring::wstring((__int64)v47);
      v20 = v42;
      v21 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v42 + 80LL);
      WindowsDeleteString(string);
      string = 0;
      v22 = v46;
      if ( v46[3] > 7u )
        v22 = (_QWORD *)v46[0];
      v43 = v22;
      v23 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v48, &v43);
      v24 = v21(v20, *(_QWORD *)(v23 + 24), &string);
      v25 = v24;
      if ( v24 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1AD1,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparse.cpp",
          (const char *)(unsigned int)v24,
          (int)string);
        std::wstring::_Tidy_deallocate(v47);
        WindowsDeleteString(string);
        string = 0;
        std::wstring::_Tidy_deallocate(v46);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
        return v25;
      }
      if ( !string )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1AD5,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparse.cpp",
          (const char *)0x82F00003LL,
          0);
        std::wstring::_Tidy_deallocate(v47);
        WindowsDeleteString(string);
        string = 0;
        std::wstring::_Tidy_deallocate(v46);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
        return 2196766723LL;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v27 = -1;
      do
        ++v27;
      while ( StringRawBuffer[v27] );
      std::wstring::_Assign<unsigned short>(v47, StringRawBuffer, (char *)v27);
      v28 = *a4;
      v29 = a4[1];
      while ( v28 != v29 )
      {
        if ( !(unsigned int)std::wstring::compare(v47, *v28 + 39) )
        {
          v30 = *v28;
          if ( v30 )
          {
            v43 = 0;
            v31 = v42;
            v32 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD **))(*(_QWORD *)v42 + 64LL);
            if ( (unsigned __int64)v30[3] <= 7 )
              v33 = (__int64 *)v30;
            else
              v33 = (__int64 *)*v30;
            v45 = v33;
            v34 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v48, &v45);
            v35 = v32(v31, *(_QWORD *)(v34 + 24), &v43);
            v36 = v35;
            if ( v35 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1AE8,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparse.cpp",
                (const char *)(unsigned int)v35,
                (int)string);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
              std::wstring::_Tidy_deallocate(v47);
              WindowsDeleteString(string);
              string = 0;
              std::wstring::_Tidy_deallocate(v46);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
              return v36;
            }
            if ( !v43 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1AED,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparse.cpp",
                (const char *)0x82F00003LL,
                (int)string);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
              std::wstring::_Tidy_deallocate(v47);
              WindowsDeleteString(string);
              string = 0;
              std::wstring::_Tidy_deallocate(v46);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
              return 2196766723LL;
            }
            v37 = ParseJsonResultSettings((__int64)v43, a2, v30 + 36);
            v38 = v37;
            if ( v37 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1AF1,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparse.cpp",
                (const char *)(unsigned int)v37,
                (int)string);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
              std::wstring::_Tidy_deallocate(v47);
              WindowsDeleteString(string);
              string = 0;
              std::wstring::_Tidy_deallocate(v46);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
              return v38;
            }
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
          }
          break;
        }
        v28 += 2;
      }
      std::wstring::_Tidy_deallocate(v47);
      WindowsDeleteString(string);
      string = 0;
      std::wstring::_Tidy_deallocate(v46);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
      ++v11;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(string) = wil::details::in1diag3::Return_CaughtException(
                        retaddr,
                        (void *)0x1AF5,
                        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparse.cpp",
                        v16);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
    return (unsigned int)string;
  }
  return result;
}

```

## disassembly

```asm
0x180039398  push    rbx
0x18003939a  push    rsi
0x18003939b  push    rdi
0x18003939c  push    r12
0x18003939e  push    r13
0x1800393a0  push    r14
0x1800393a2  push    r15
0x1800393a4  sub     rsp, 0C0h
0x1800393ab  mov     rax, cs:__security_cookie
0x1800393b2  xor     rax, rsp
0x1800393b5  mov     [rsp+0F8h+var_40], rax
0x1800393bd  mov     r15, r9
0x1800393c0  mov     r12, r8
0x1800393c3  mov     r13, rdx
0x1800393c6  xor     r14d, r14d
0x1800393c9  mov     [rsp+0F8h+var_D0], r14
0x1800393ce  mov     rax, [rcx]
0x1800393d1  lea     r8, [rsp+0F8h+var_D0]
0x1800393d6  lea     rdx, _GUID_d44662bc_dce3_59a8_9272_4b210f33908b
0x1800393dd  mov     rax, [rax]
0x1800393e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800393e5  mov     ebx, eax
0x1800393e7  test    eax, eax
0x1800393e9  jns     short loc_1800393F2
0x1800393eb  mov     edx, 1ABBh
0x1800393f0  jmp     short loc_180039418
0x1800393f2  mov     [rsp+0F8h+var_B0], r14d
0x1800393f7  mov     rcx, [rsp+0F8h+var_D0]
0x1800393fc  mov     rax, [rcx]
0x1800393ff  lea     rdx, [rsp+0F8h+var_B0]
0x180039404  mov     rax, [rax+38h]
0x180039408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003940d  mov     ebx, eax
0x18003940f  test    eax, eax
0x180039411  jns     short loc_180039441
0x180039413  mov     edx, 1ABFh; void *
0x180039418  mov     r9d, eax; char *
0x18003941b  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180039422  mov     rcx, [rsp+0F8h]; this
0x18003942a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003942f  nop
0x180039430  lea     rcx, [rsp+0F8h+var_D0]
0x180039435  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003943a  mov     eax, ebx
0x18003943c  jmp     loc_18003993F
0x180039441  mov     esi, r14d
0x180039444  cmp     esi, [rsp+0F8h+var_B0]
0x180039448  jnb     loc_180039923
0x18003944e  mov     [rsp+0F8h+var_C8], r14
0x180039453  mov     rdi, [rsp+0F8h+var_D0]
0x180039458  mov     rax, [rdi]
0x18003945b  mov     rbx, [rax+30h]
0x18003945f  lea     rcx, [rsp+0F8h+var_C8]
0x180039464  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180039469  lea     r8, [rsp+0F8h+var_C8]
0x18003946e  mov     edx, esi
0x180039470  mov     rcx, rdi
0x180039473  mov     rax, rbx
0x180039476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003947b  mov     ebx, eax
0x18003947d  test    eax, eax
0x18003947f  jns     short loc_1800394BA
0x180039481  mov     rcx, [rsp+0F8h]; this
0x180039489  mov     r9d, eax; char *
0x18003948c  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180039493  mov     edx, 1AC7h; void *
0x180039498  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003949d  nop
0x18003949e  lea     rcx, [rsp+0F8h+var_C8]
0x1800394a3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800394a8  nop
0x1800394a9  lea     rcx, [rsp+0F8h+var_D0]
0x1800394ae  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800394b3  mov     eax, ebx
0x1800394b5  jmp     loc_18003993F
0x1800394ba  mov     [rsp+0F8h+var_C0], r14
0x1800394bf  mov     rcx, [rsp+0F8h+var_C8]
0x1800394c4  mov     rax, [rcx]
0x1800394c7  lea     rdx, [rsp+0F8h+var_C0]
0x1800394cc  mov     rax, [rax+60h]
0x1800394d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800394d5  mov     ebx, eax
0x1800394d7  test    eax, eax
0x1800394d9  jns     short loc_18003951F
0x1800394db  mov     rcx, [rsp+0F8h]; this
0x1800394e3  mov     r9d, eax; char *
0x1800394e6  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800394ed  mov     edx, 1ACBh; void *
0x1800394f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800394f7  nop
0x1800394f8  lea     rcx, [rsp+0F8h+var_C0]
0x1800394fd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180039502  nop
0x180039503  lea     rcx, [rsp+0F8h+var_C8]
0x180039508  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003950d  nop
0x18003950e  lea     rcx, [rsp+0F8h+var_D0]
0x180039513  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180039518  mov     eax, ebx
0x18003951a  jmp     loc_18003993F
0x18003951f  mov     rdx, r12
0x180039522  lea     rcx, [rsp+0F8h+var_60]
0x18003952a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003952f  nop
0x180039530  lea     r8, aId; "Id"
0x180039537  mov     rdx, rax
0x18003953a  lea     rcx, [rsp+0F8h+var_A0]
0x18003953f  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180039544  nop
0x180039545  lea     rcx, [rsp+0F8h+var_60]
0x18003954d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180039552  mov     [rsp+0F8h+string], r14
0x180039557  lea     rcx, [rsp+0F8h+var_80]
0x18003955c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180039561  nop
0x180039562  mov     rdi, [rsp+0F8h+var_C0]
0x180039567  mov     rax, [rdi]
0x18003956a  mov     rbx, [rax+50h]
0x18003956e  mov     rcx, [rsp+0F8h+string]; string
0x180039573  call    cs:__imp_WindowsDeleteString
0x180039579  mov     [rsp+0F8h+string], r14; int
0x18003957e  lea     rdx, [rsp+0F8h+var_A0]
0x180039583  cmp     [rsp+0F8h+var_88], 7
0x180039589  cmova   rdx, [rsp+0F8h+var_A0]
0x18003958f  mov     [rsp+0F8h+var_B8], rdx
0x180039594  lea     rdx, [rsp+0F8h+var_B8]
0x180039599  lea     rcx, [rsp+0F8h+var_60]
0x1800395a1  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800395a6  nop
0x1800395a7  lea     r8, [rsp+0F8h+string]
0x1800395ac  mov     rdx, [rax+18h]
0x1800395b0  mov     rcx, rdi
0x1800395b3  mov     rax, rbx
0x1800395b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800395bb  mov     ebx, eax
0x1800395bd  test    eax, eax
0x1800395bf  jns     short loc_18003962B
0x1800395c1  mov     rcx, [rsp+0F8h]; this
0x1800395c9  mov     r9d, eax; char *
0x1800395cc  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800395d3  mov     edx, 1AD1h; void *
0x1800395d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800395dd  nop
0x1800395de  lea     rcx, [rsp+0F8h+var_80]
0x1800395e3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800395e8  nop
0x1800395e9  mov     rcx, [rsp+0F8h+string]; string
0x1800395ee  call    cs:__imp_WindowsDeleteString
0x1800395f4  mov     [rsp+0F8h+string], r14
0x1800395f9  lea     rcx, [rsp+0F8h+var_A0]
0x1800395fe  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180039603  nop
0x180039604  lea     rcx, [rsp+0F8h+var_C0]
0x180039609  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003960e  nop
0x18003960f  lea     rcx, [rsp+0F8h+var_C8]
0x180039614  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180039619  nop
0x18003961a  lea     rcx, [rsp+0F8h+var_D0]
0x18003961f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180039624  mov     eax, ebx
0x180039626  jmp     loc_18003993F
0x18003962b  mov     rcx, [rsp+0F8h+string]; string
0x180039630  test    rcx, rcx
0x180039633  jnz     short loc_1800396A4
0x180039635  mov     rcx, [rsp+0F8h]; this
0x18003963d  mov     ebx, 82F00003h
0x180039642  mov     r9d, ebx; char *
0x180039645  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18003964c  mov     edx, 1AD5h; void *
0x180039651  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039656  nop
0x180039657  lea     rcx, [rsp+0F8h+var_80]
0x18003965c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180039661  nop
0x180039662  mov     rcx, [rsp+0F8h+string]; string
0x180039667  call    cs:__imp_WindowsDeleteString
0x18003966d  mov     [rsp+0F8h+string], r14
0x180039672  lea     rcx, [rsp+0F8h+var_A0]
0x180039677  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003967c  nop
0x18003967d  lea     rcx, [rsp+0F8h+var_C0]
0x180039682  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180039687  nop
0x180039688  lea     rcx, [rsp+0F8h+var_C8]
0x18003968d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180039692  nop
0x180039693  lea     rcx, [rsp+0F8h+var_D0]
0x180039698  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003969d  mov     eax, ebx
0x18003969f  jmp     loc_18003993F
0x1800396a4  xor     edx, edx; length
0x1800396a6  call    cs:__imp_WindowsGetStringRawBuffer
0x1800396ac  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800396b0  inc     r8
0x1800396b3  cmp     [rax+r8*2], r14w
0x1800396b8  jnz     short loc_1800396B0
0x1800396ba  mov     rdx, rax
0x1800396bd  lea     rcx, [rsp+0F8h+var_80]
0x1800396c2  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800396c7  mov     rbx, [r15]
0x1800396ca  mov     rdi, [r15+8]
0x1800396ce  cmp     rbx, rdi
0x1800396d1  jz      loc_1800398E1
0x1800396d7  mov     rdx, [rbx]
0x1800396da  add     rdx, 138h
0x1800396e1  lea     rcx, [rsp+0F8h+var_80]
0x1800396e6  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHAEBV12@@Z; std::wstring::compare(std::wstring const &)
0x1800396eb  test    eax, eax
0x1800396ed  jz      short loc_1800396F5
0x1800396ef  add     rbx, 10h
0x1800396f3  jmp     short loc_1800396CE
0x1800396f5  mov     rbx, [rbx]
0x1800396f8  test    rbx, rbx
0x1800396fb  jz      loc_1800398E1
0x180039701  mov     [rsp+0F8h+var_B8], r14
0x180039706  mov     rdi, [rsp+0F8h+var_C0]
0x18003970b  mov     rax, [rdi]
0x18003970e  mov     r14, [rax+40h]
0x180039712  cmp     qword ptr [rbx+18h], 7
0x180039717  jbe     short loc_18003971E
0x180039719  mov     rax, [rbx]
0x18003971c  jmp     short loc_180039721
0x18003971e  mov     rax, rbx
0x180039721  mov     [rsp+0F8h+var_A8], rax
0x180039726  lea     rdx, [rsp+0F8h+var_A8]
0x18003972b  lea     rcx, [rsp+0F8h+var_60]
0x180039733  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180039738  nop
0x180039739  lea     r8, [rsp+0F8h+var_B8]
0x18003973e  mov     rdx, [rax+18h]
0x180039742  mov     rcx, rdi
0x180039745  mov     rax, r14
0x180039748  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003974d  mov     edi, eax
0x18003974f  xor     r14d, r14d
0x180039752  test    eax, eax
0x180039754  jns     short loc_1800397CB
0x180039756  mov     rcx, [rsp+0F8h]; this
0x18003975e  mov     r9d, eax; char *
0x180039761  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180039768  mov     edx, 1AE8h; void *
0x18003976d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039772  nop
0x180039773  lea     rcx, [rsp+0F8h+var_B8]
0x180039778  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003977d  nop
0x18003977e  lea     rcx, [rsp+0F8h+var_80]
0x180039783  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180039788  nop
0x180039789  mov     rcx, [rsp+0F8h+string]; string
0x18003978e  call    cs:__imp_WindowsDeleteString
0x180039794  mov     [rsp+0F8h+string], r14
0x180039799  lea     rcx, [rsp+0F8h+var_A0]
0x18003979e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800397a3  nop
0x1800397a4  lea     rcx, [rsp+0F8h+var_C0]
0x1800397a9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800397ae  nop
0x1800397af  lea     rcx, [rsp+0F8h+var_C8]
0x1800397b4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800397b9  nop
0x1800397ba  lea     rcx, [rsp+0F8h+var_D0]
0x1800397bf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800397c4  mov     eax, edi
0x1800397c6  jmp     loc_18003993F
0x1800397cb  mov     rcx, [rsp+0F8h+var_B8]
0x1800397d0  test    rcx, rcx
0x1800397d3  jnz     short loc_18003984F
0x1800397d5  mov     rcx, [rsp+0F8h]; this
0x1800397dd  mov     ebx, 82F00003h
0x1800397e2  mov     r9d, ebx; char *
0x1800397e5  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800397ec  mov     edx, 1AEDh; void *
0x1800397f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800397f6  nop
0x1800397f7  lea     rcx, [rsp+0F8h+var_B8]
0x1800397fc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180039801  nop
0x180039802  lea     rcx, [rsp+0F8h+var_80]
0x180039807  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003980c  nop
0x18003980d  mov     rcx, [rsp+0F8h+string]; string
0x180039812  call    cs:__imp_WindowsDeleteString
0x180039818  mov     [rsp+0F8h+string], r14
0x18003981d  lea     rcx, [rsp+0F8h+var_A0]
0x180039822  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180039827  nop
0x180039828  lea     rcx, [rsp+0F8h+var_C0]
0x18003982d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180039832  nop
0x180039833  lea     rcx, [rsp+0F8h+var_C8]
0x180039838  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003983d  nop
0x18003983e  lea     rcx, [rsp+0F8h+var_D0]
0x180039843  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180039848  mov     eax, ebx
0x18003984a  jmp     loc_18003993F
0x18003984f  lea     r8, [rbx+120h]
0x180039856  mov     rdx, r13
  ... truncated ...
```
