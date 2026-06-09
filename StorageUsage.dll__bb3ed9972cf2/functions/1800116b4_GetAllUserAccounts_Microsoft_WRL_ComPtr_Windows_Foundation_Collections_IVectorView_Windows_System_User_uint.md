# GetAllUserAccounts(Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::System::User *>> &,uint &)

- ea: `0x1800116b4`
- end: `0x18001183c`
- name: `?GetAllUserAccounts@@YAJAEAV?$ComPtr@U?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@AEAI@Z`
- size: `392`
- prototype: `__int64 __fastcall(_QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012340`

## callees

- `0x1800050f0`
- `0x18000e840`
- `0x180011438`
- `0x1800116b4`
- `0x180013ae4`
- `0x1800152d4`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180011728`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180011728`

## pseudocode

```c
__int64 __fastcall GetAllUserAccounts(_QWORD *a1, _DWORD *a2)
{
  __int64 v4; // rbx
  int ActivationFactory; // eax
  int v6; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, int (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  int v9; // eax
  unsigned __int64 v10; // r9
  __int64 v11; // rdx
  int (__fastcall ***v12)(_QWORD, GUID *, __int64 *); // rdi
  HRESULT v13; // edx
  __int64 v14; // r8
  int v15; // eax
  int (__fastcall ***v17)(_QWORD, GUID *, __int64 *); // [rsp+20h] [rbp-40h] BYREF
  __int64 v18; // [rsp+28h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-30h] BYREF
  __int64 v20; // [rsp+48h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  *a2 = 0;
  v18 = 0;
  v20 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Windows.System.User", 0x14u, 0x13u);
  v4 = v20;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v18);
  ActivationFactory = RoGetActivationFactory(v4, &GUID_155eb23b_242a_45e0_a2e9_3171fc6a7fdd, &v18);
  v6 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v17 = 0;
    v7 = v18;
    v8 = *(__int64 (__fastcall **)(__int64, int (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v18 + 56LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v17);
    v9 = v8(v7, &v17);
    v6 = v9;
    if ( v9 >= 0 )
    {
      v12 = v17;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(a1);
      v6 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>>(
             v12,
             v13,
             v14);
      if ( v6 < 0
        || (v6 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), _QWORD *))(*v12)[8])(v12, a1),
            v6 < 0) )
      {
        v10 = (unsigned int)v6;
        v11 = 1308;
      }
      else
      {
        v15 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *))(*(_QWORD *)*a1 + 56LL))(*a1, a2);
        v6 = v15;
        if ( v15 >= 0 )
        {
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v17);
          v6 = 0;
          goto LABEL_12;
        }
        v10 = (unsigned int)v15;
        v11 = 1309;
      }
    }
    else
    {
      v10 = (unsigned int)v9;
      v11 = 1307;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\storagegrovelertelemetry.cpp",
      (const char *)v10,
      (int)v17);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v17);
    goto LABEL_12;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x518,
    (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\storagegrovelertelemetry.cpp",
    (const char *)(unsigned int)ActivationFactory,
    (int)v17);
LABEL_12:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v18);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800116b4  mov     [rsp-18h+arg_10], rbx
0x1800116b9  mov     [rsp-18h+arg_18], rsi
0x1800116be  push    rbp
0x1800116bf  push    rdi
0x1800116c0  push    r14
0x1800116c2  mov     rbp, rsp
0x1800116c5  sub     rsp, 60h
0x1800116c9  mov     rax, cs:__security_cookie
0x1800116d0  xor     rax, rsp
0x1800116d3  mov     [rbp+var_10], rax
0x1800116d7  mov     r14, rdx
0x1800116da  mov     rsi, rcx
0x1800116dd  mov     dword ptr [rdx], 0
0x1800116e3  mov     [rbp+var_38], 0
0x1800116eb  mov     [rbp+var_18], 0
0x1800116f3  mov     r9d, 13h; unsigned int
0x1800116f9  lea     r8d, [r9+1]; unsigned int
0x1800116fd  lea     rdx, ?RuntimeClass_Windows_System_User@@3QBGB; "Windows.System.User"
0x180011704  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180011708  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001170d  mov     rbx, [rbp+var_18]
0x180011711  lea     rcx, [rbp+var_38]
0x180011715  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001171a  lea     r8, [rbp+var_38]
0x18001171e  lea     rdx, _GUID_155eb23b_242a_45e0_a2e9_3171fc6a7fdd
0x180011725  mov     rcx, rbx
0x180011728  call    cs:__imp_RoGetActivationFactory
0x18001172e  mov     ebx, eax
0x180011730  test    eax, eax
0x180011732  jns     short loc_180011751
0x180011734  mov     rcx, [rbp+18h]; this
0x180011738  mov     r9d, eax; char *
0x18001173b  lea     r8, aOnecoreDrivers_1; "onecore\\drivers\\storage\\storsvc\\sto"...
0x180011742  mov     edx, 518h; void *
0x180011747  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001174c  jmp     loc_180011810
0x180011751  mov     [rbp+var_40], 0
0x180011759  mov     rdi, [rbp+var_38]
0x18001175d  mov     rax, [rdi]
0x180011760  mov     rbx, [rax+38h]
0x180011764  lea     rcx, [rbp+var_40]
0x180011768  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001176d  lea     rdx, [rbp+var_40]
0x180011771  mov     rcx, rdi
0x180011774  mov     rax, rbx
0x180011777  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001177c  mov     ebx, eax
0x18001177e  test    eax, eax
0x180011780  jns     short loc_18001178C
0x180011782  mov     r9d, eax
0x180011785  mov     edx, 51Bh
0x18001178a  jmp     short loc_1800117F5
0x18001178c  mov     rdi, [rbp+var_40]
0x180011790  mov     rcx, rsi
0x180011793  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180011798  mov     rcx, rdi
0x18001179b  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *,tagCOWAIT_FLAGS,void *)
0x1800117a0  mov     ebx, eax
0x1800117a2  test    eax, eax
0x1800117a4  js      short loc_1800117ED
0x1800117a6  mov     rax, [rdi]
0x1800117a9  mov     rdx, rsi
0x1800117ac  mov     rcx, rdi
0x1800117af  mov     rax, [rax+40h]
0x1800117b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800117b8  mov     ebx, eax
0x1800117ba  test    eax, eax
0x1800117bc  js      short loc_1800117ED
0x1800117be  mov     rcx, [rsi]
0x1800117c1  mov     rax, [rcx]
0x1800117c4  mov     rdx, r14
0x1800117c7  mov     rax, [rax+38h]
0x1800117cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800117d0  mov     ebx, eax
0x1800117d2  test    eax, eax
0x1800117d4  jns     short loc_1800117E0
0x1800117d6  mov     r9d, eax
0x1800117d9  mov     edx, 51Dh
0x1800117de  jmp     short loc_1800117F5
0x1800117e0  lea     rcx, [rbp+var_40]
0x1800117e4  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800117e9  xor     ebx, ebx
0x1800117eb  jmp     short loc_180011810
0x1800117ed  mov     r9d, ebx; char *
0x1800117f0  mov     edx, 51Ch; void *
0x1800117f5  lea     r8, aOnecoreDrivers_1; "onecore\\drivers\\storage\\storsvc\\sto"...
0x1800117fc  mov     rcx, [rbp+18h]; this
0x180011800  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011805  nop
0x180011806  lea     rcx, [rbp+var_40]
0x18001180a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001180f  nop
0x180011810  lea     rcx, [rbp+var_38]
0x180011814  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180011819  mov     eax, ebx
0x18001181b  mov     rcx, [rbp+var_10]
0x18001181f  xor     rcx, rsp; StackCookie
0x180011822  call    __security_check_cookie
0x180011827  lea     r11, [rsp+60h+var_s0]
0x18001182c  mov     rbx, [r11+30h]
0x180011830  mov     rsi, [r11+38h]
0x180011834  mov     rsp, r11
0x180011837  pop     r14
0x180011839  pop     rdi
0x18001183a  pop     rbp
0x18001183b  retn
```
