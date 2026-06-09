# Windows::Networking::UX::Internal::StateAuthProxy::ProcessUserInput(Windows::Networking::UX::IUserInputType *)

- ea: `0x180070900`
- end: `0x180070bf7`
- name: `?ProcessUserInput@StateAuthProxy@Internal@UX@Networking@Windows@@UEAAJPEAUIUserInputType@345@@Z`
- size: `759`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::StateAuthProxy *__hidden this, struct Windows::Networking::UX::IUserInputType *)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x180008e30`
- `0x18000de4c`
- `0x180015348`
- `0x18001d4d4`
- `0x1800644b8`
- `0x18006476c`
- `0x18006b548`
- `0x18006d5e8`
- `0x180070900`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800709db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180070ba2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800709db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180070ba2`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Windows::Networking::UX::Internal::StateAuthProxy::ProcessUserInput(
        Windows::Networking::UX::Internal::StateAuthProxy *this,
        struct Windows::Networking::UX::IUserInputType *a2)
{
  __int64 (__fastcall *v4)(struct Windows::Networking::UX::IUserInputType *, GUID *, __int64 **); // rbx
  __int64 v5; // rdx
  __int64 v6; // r8
  int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 *v10; // rdi
  __int64 (__fastcall *v11)(__int64 *, HSTRING *); // rbx
  int v12; // eax
  __int64 v13; // rax
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  int v17; // eax
  int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // r8
  _BYTE *v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // r8
  char v25; // [rsp+30h] [rbp-40h] BYREF
  char v26[3]; // [rsp+31h] [rbp-3Fh] BYREF
  unsigned int v27; // [rsp+34h] [rbp-3Ch] BYREF
  __int64 *v28; // [rsp+38h] [rbp-38h] BYREF
  _BYTE *v29; // [rsp+40h] [rbp-30h] BYREF
  HSTRING string; // [rsp+48h] [rbp-28h] BYREF
  __int64 v31; // [rsp+50h] [rbp-20h] BYREF
  _QWORD *v32; // [rsp+58h] [rbp-18h] BYREF
  __int64 v33; // [rsp+60h] [rbp-10h] BYREF
  char v34; // [rsp+68h] [rbp-8h]
  struct Windows::Networking::UX::IUserInputType *v35; // [rsp+B8h] [rbp+48h] BYREF
  char v36; // [rsp+C0h] [rbp+50h] BYREF
  char v37; // [rsp+C8h] [rbp+58h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 126, &WPP_a797c7dc6893366bd5e69a838f894db7_Traceguids);
  v28 = 0;
  v35 = a2;
  Microsoft::WRL::ComPtr<Windows::Networking::UX::IUserInputType>::InternalAddRef(&v35);
  v4 = **(__int64 (__fastcall ***)(struct Windows::Networking::UX::IUserInputType *, GUID *, __int64 **))a2;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28, v5, v6);
  v7 = v4(a2, &GUID_ec52d38a_5340_4351_ac18_392d10a08217, &v28);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35, v8, v9);
  if ( v7 >= 0 )
  {
    string = 0;
    v10 = v28;
    v11 = *(__int64 (__fastcall **)(__int64 *, HSTRING *))(*v28 + 48);
    WindowsDeleteString(0);
    string = 0;
    v12 = v11(v10, &string);
    v7 = v12;
    if ( v12 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          128,
          &WPP_a797c7dc6893366bd5e69a838f894db7_Traceguids,
          (unsigned int)v12);
LABEL_29:
      WindowsDeleteString(string);
      goto LABEL_30;
    }
    v27 = 0;
    v29 = 0;
    v13 = *v28;
    v32 = &v29;
    v33 = 0;
    v34 = 1;
    v7 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *, __int64 *))(v13 + 56))(v28, &v27, &v33);
    wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::cotaskmem_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::cotaskmem_secure_deleter>>(&v32);
    if ( v7 >= 0 )
    {
      v17 = (*(__int64 (__fastcall **)(_QWORD, HSTRING, _QWORD, _BYTE *))(**((_QWORD **)this + 2) + 176LL))(
              *((_QWORD *)this + 2),
              string,
              v27,
              v29);
      v7 = v17;
      if ( v17 >= 0 )
      {
        v31 = 0;
        LOBYTE(v35) = 0;
        v36 = 0;
        v37 = 0;
        v25 = 1;
        v26[0] = 1;
        v18 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Networking::UX::Internal::CWiFiInProgressUIPrompt,Windows::Networking::UX::IUserInputType,bool,bool,bool,bool,bool>(
                (__int64)&v31,
                (__int64)v26,
                (__int64)&v25,
                (int)&v37,
                (__int64)&v36,
                (__int64)&v35);
        v7 = v18;
        if ( v18 >= 0 )
        {
          (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 2) + 16LL))(*((_QWORD *)this + 2), v31);
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            131,
            &WPP_a797c7dc6893366bd5e69a838f894db7_Traceguids,
            (unsigned int)v18);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31, v19, v20);
        goto LABEL_27;
      }
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v15 = 130;
        v16 = (unsigned int)v17;
        goto LABEL_20;
      }
    }
    else
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v15 = 129;
        v16 = (unsigned int)v7;
LABEL_20:
        WPP_SF_d(v14[2], v15, &WPP_a797c7dc6893366bd5e69a838f894db7_Traceguids, v16);
      }
    }
LABEL_27:
    v21 = v29;
    v29 = 0;
    if ( v21 )
      wil::cotaskmem_secure_deleter::operator()<unsigned short>((__int64)v14, v21);
    goto LABEL_29;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      127,
      &WPP_a797c7dc6893366bd5e69a838f894db7_Traceguids,
      (unsigned int)v7);
LABEL_30:
  Windows::Networking::UX::Internal::StateBase::LogProcessUserInputAction(this, a2, v7);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      132,
      &WPP_a797c7dc6893366bd5e69a838f894db7_Traceguids,
      (unsigned int)v7);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28, v22, v23);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180070900  push    rbp
0x180070902  push    rbx
0x180070903  push    rsi
0x180070904  push    rdi
0x180070905  push    r12
0x180070907  push    r13
0x180070909  push    r14
0x18007090b  mov     rbp, rsp
0x18007090e  sub     rsp, 70h
0x180070912  mov     rsi, rdx
0x180070915  mov     r14, rcx
0x180070918  lea     r12, WPP_GLOBAL_Control
0x18007091f  lea     r13, WPP_a797c7dc6893366bd5e69a838f894db7_Traceguids
0x180070926  mov     rcx, cs:WPP_GLOBAL_Control
0x18007092d  cmp     rcx, r12
0x180070930  jz      short loc_180070949
0x180070932  test    byte ptr [rcx+1Ch], 8
0x180070936  jz      short loc_180070949
0x180070938  mov     edx, 7Eh ; '~'
0x18007093d  mov     r8, r13
0x180070940  mov     rcx, [rcx+10h]
0x180070944  call    WPP_SF_
0x180070949  mov     [rbp+var_38], 0
0x180070951  mov     [rbp+arg_8], rsi
0x180070955  lea     rcx, [rbp+arg_8]
0x180070959  call    ?InternalAddRef@?$ComPtr@UIUserInputType@UX@Networking@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Networking::UX::IUserInputType>::InternalAddRef(void)
0x18007095e  nop
0x18007095f  mov     rax, [rsi]
0x180070962  mov     rbx, [rax]
0x180070965  lea     rcx, [rbp+var_38]
0x180070969  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007096e  lea     r8, [rbp+var_38]
0x180070972  lea     rdx, _GUID_ec52d38a_5340_4351_ac18_392d10a08217
0x180070979  mov     rcx, rsi
0x18007097c  mov     rax, rbx
0x18007097f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070984  mov     ebx, eax
0x180070986  lea     rcx, [rbp+arg_8]
0x18007098a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007098f  test    ebx, ebx
0x180070991  jns     short loc_1800709C6
0x180070993  mov     rcx, cs:WPP_GLOBAL_Control
0x18007099a  cmp     rcx, r12
0x18007099d  jz      loc_180070BA8
0x1800709a3  test    byte ptr [rcx+1Ch], 2
0x1800709a7  jz      loc_180070BA8
0x1800709ad  mov     edx, 7Fh
0x1800709b2  mov     r9d, ebx
0x1800709b5  mov     r8, r13
0x1800709b8  mov     rcx, [rcx+10h]
0x1800709bc  call    WPP_SF_d
0x1800709c1  jmp     loc_180070BA8
0x1800709c6  mov     [rbp+string], 0
0x1800709ce  mov     rdi, [rbp+var_38]
0x1800709d2  mov     rax, [rdi]
0x1800709d5  mov     rbx, [rax+30h]
0x1800709d9  xor     ecx, ecx; string
0x1800709db  call    cs:__imp_WindowsDeleteString
0x1800709e1  mov     [rbp+string], 0
0x1800709e9  lea     rdx, [rbp+string]
0x1800709ed  mov     rcx, rdi
0x1800709f0  mov     rax, rbx
0x1800709f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800709f8  mov     ebx, eax
0x1800709fa  test    eax, eax
0x1800709fc  jns     short loc_180070A31
0x1800709fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180070a05  cmp     rcx, r12
0x180070a08  jz      loc_180070B9E
0x180070a0e  test    byte ptr [rcx+1Ch], 2
0x180070a12  jz      loc_180070B9E
0x180070a18  mov     edx, 80h
0x180070a1d  mov     r9d, eax
0x180070a20  mov     r8, r13
0x180070a23  mov     rcx, [rcx+10h]
0x180070a27  call    WPP_SF_d
0x180070a2c  jmp     loc_180070B9E
0x180070a31  mov     [rbp+var_3C], 0
0x180070a38  mov     [rbp+var_30], 0
0x180070a40  mov     rcx, [rbp+var_38]
0x180070a44  mov     rax, [rcx]
0x180070a47  lea     rdx, [rbp+var_30]
0x180070a4b  mov     [rbp+var_18], rdx
0x180070a4f  mov     [rbp+var_10], 0
0x180070a57  mov     [rbp+var_8], 1
0x180070a5b  lea     r8, [rbp+var_10]
0x180070a5f  lea     rdx, [rbp+var_3C]
0x180070a63  mov     rax, [rax+38h]
0x180070a67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070a6c  mov     ebx, eax
0x180070a6e  lea     rcx, [rbp+var_18]
0x180070a72  call    ??1?$out_param_t@V?$unique_ptr@GUcotaskmem_secure_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::cotaskmem_secure_deleter>>::~out_param_t<wistd::unique_ptr<ushort,wil::cotaskmem_secure_deleter>>(void)
0x180070a77  test    ebx, ebx
0x180070a79  jns     short loc_180070A9F
0x180070a7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180070a82  cmp     rcx, r12
0x180070a85  jz      loc_180070B87
0x180070a8b  test    byte ptr [rcx+1Ch], 2
0x180070a8f  jz      loc_180070B87
0x180070a95  mov     edx, 81h
0x180070a9a  mov     r9d, ebx
0x180070a9d  jmp     short loc_180070AE6
0x180070a9f  mov     rcx, [r14+10h]
0x180070aa3  mov     rax, [rcx]
0x180070aa6  mov     r9, [rbp+var_30]
0x180070aaa  mov     r8d, [rbp+var_3C]
0x180070aae  mov     rdx, [rbp+string]
0x180070ab2  mov     rax, [rax+0B0h]
0x180070ab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070abe  mov     ebx, eax
0x180070ac0  test    eax, eax
0x180070ac2  jns     short loc_180070AF7
0x180070ac4  mov     rcx, cs:WPP_GLOBAL_Control
0x180070acb  cmp     rcx, r12
0x180070ace  jz      loc_180070B87
0x180070ad4  test    byte ptr [rcx+1Ch], 2
0x180070ad8  jz      loc_180070B87
0x180070ade  mov     edx, 82h
0x180070ae3  mov     r9d, eax
0x180070ae6  mov     r8, r13
0x180070ae9  mov     rcx, [rcx+10h]
0x180070aed  call    WPP_SF_d
0x180070af2  jmp     loc_180070B87
0x180070af7  mov     [rbp+var_20], 0
0x180070aff  mov     byte ptr [rbp+arg_8], 0
0x180070b03  mov     [rbp+arg_10], 0
0x180070b07  mov     [rbp+arg_18], 0
0x180070b0b  mov     [rbp+var_40], 1
0x180070b0f  mov     [rbp+var_3F], 1
0x180070b13  lea     rax, [rbp+arg_8]
0x180070b17  mov     [rsp+70h+var_48], rax
0x180070b1c  lea     rax, [rbp+arg_10]
0x180070b20  mov     [rsp+70h+var_50], rax
0x180070b25  lea     r9, [rbp+arg_18]
0x180070b29  lea     r8, [rbp+var_40]
0x180070b2d  lea     rdx, [rbp+var_3F]
0x180070b31  lea     rcx, [rbp+var_20]
0x180070b35  call    ??$MakeAndInitialize@VCWiFiInProgressUIPrompt@Internal@UX@Networking@Windows@@UIUserInputType@345@_N_N_N_N_N@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@UIUserInputType@UX@Networking@Windows@@@WRL@Microsoft@@@012@$$QEA_N1111@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Networking::UX::Internal::CWiFiInProgressUIPrompt,Windows::Networking::UX::IUserInputType,bool,bool,bool,bool,bool>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Networking::UX::IUserInputType>>,bool &&,bool &&,bool &&,bool &&,bool &&)
0x180070b3a  mov     ebx, eax
0x180070b3c  test    eax, eax
0x180070b3e  jns     short loc_180070B68
0x180070b40  mov     rcx, cs:WPP_GLOBAL_Control
0x180070b47  cmp     rcx, r12
0x180070b4a  jz      short loc_180070B7D
0x180070b4c  test    byte ptr [rcx+1Ch], 2
0x180070b50  jz      short loc_180070B7D
0x180070b52  mov     edx, 83h
0x180070b57  mov     r9d, eax
0x180070b5a  mov     r8, r13
0x180070b5d  mov     rcx, [rcx+10h]
0x180070b61  call    WPP_SF_d
0x180070b66  jmp     short loc_180070B7D
0x180070b68  mov     rcx, [r14+10h]
0x180070b6c  mov     rax, [rcx]
0x180070b6f  mov     rdx, [rbp+var_20]
0x180070b73  mov     rax, [rax+10h]
0x180070b77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070b7c  nop
0x180070b7d  lea     rcx, [rbp+var_20]
0x180070b81  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180070b86  nop
0x180070b87  mov     rdx, [rbp+var_30]
0x180070b8b  mov     [rbp+var_30], 0
0x180070b93  test    rdx, rdx
0x180070b96  jz      short loc_180070B9E
0x180070b98  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x180070b9d  nop
0x180070b9e  mov     rcx, [rbp+string]; string
0x180070ba2  call    cs:__imp_WindowsDeleteString
0x180070ba8  mov     r8d, ebx; int
0x180070bab  mov     rdx, rsi; struct Windows::Networking::UX::IUserInputType *
0x180070bae  mov     rcx, r14; this
0x180070bb1  call    ?LogProcessUserInputAction@StateBase@Internal@UX@Networking@Windows@@IEAAXPEAUIUserInputType@345@J@Z; Windows::Networking::UX::Internal::StateBase::LogProcessUserInputAction(Windows::Networking::UX::IUserInputType *,long)
0x180070bb6  mov     rcx, cs:WPP_GLOBAL_Control
0x180070bbd  cmp     rcx, r12
0x180070bc0  jz      short loc_180070BDD
0x180070bc2  test    byte ptr [rcx+1Ch], 8
0x180070bc6  jz      short loc_180070BDD
0x180070bc8  mov     edx, 84h
0x180070bcd  mov     r9d, ebx
0x180070bd0  mov     r8, r13
0x180070bd3  mov     rcx, [rcx+10h]
0x180070bd7  call    WPP_SF_d
0x180070bdc  nop
0x180070bdd  lea     rcx, [rbp+var_38]
0x180070be1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180070be6  mov     eax, ebx
0x180070be8  add     rsp, 70h
0x180070bec  pop     r14
0x180070bee  pop     r13
0x180070bf0  pop     r12
0x180070bf2  pop     rdi
0x180070bf3  pop     rsi
0x180070bf4  pop     rbx
0x180070bf5  pop     rbp
0x180070bf6  retn
```
