# Execution::ActivationManagerShim::RefreshExtensionArgsIfNeeded(ulong,ushort const *,ushort const *,ActivateByExtensionArgs *)

- ea: `0x18003d434`
- end: `0x18003d568`
- name: `?RefreshExtensionArgsIfNeeded@ActivationManagerShim@Execution@@CAJKPEBG0PEAUActivateByExtensionArgs@@@Z`
- size: `308`
- prototype: `static int(unsigned int, const unsigned __int16 *, const unsigned __int16 *, struct ActivateByExtensionArgs *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006b040`

## callees

- `0x18000b5c0`
- `0x180011328`
- `0x180011590`
- `0x18002a380`
- `0x18003d434`
- `0x18005ae90`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d51b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d51b`
- `combase!__imp_RoGetExtensionRegistration` at `0x18003d501`
- `combase!__imp_RoGetExtensionRegistration` at `0x18003d501`
- `combase!__imp_RoGetExtensionRegistrationByExtensionId` at `0x18003d49e`
- `combase!__imp_RoGetExtensionRegistrationByExtensionId` at `0x18003d49e`

## pseudocode

```c
__int64 __fastcall Execution::ActivationManagerShim::RefreshExtensionArgsIfNeeded(
        int a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct ActivateByExtensionArgs *a4)
{
  struct Windows::Foundation::IExtensionRegistration **v5; // rsi
  char *v6; // rcx
  __int64 v7; // rbx
  __int64 v8; // rax
  int ExtensionRegistrationByExtensionId; // ebx
  __int64 v10; // rdx
  __int64 v12; // rdi
  __int64 v13; // rbx
  __int64 v14; // rax
  int v15[2]; // [rsp+20h] [rbp-78h] BYREF
  const unsigned __int16 *v16; // [rsp+28h] [rbp-70h] BYREF
  _BYTE v17[32]; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v18[32]; // [rsp+50h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v16 = a2;
  *(_QWORD *)v15 = a3;
  v5 = (struct Windows::Foundation::IExtensionRegistration **)((char *)a4 + 16);
  if ( a1 || !*v5 )
  {
    v6 = (char *)a4 + 16;
    if ( *((_QWORD *)a4 + 1) )
    {
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v6);
      v7 = *((_QWORD *)a4 + 1);
      v8 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v17, v15);
      ExtensionRegistrationByExtensionId = RoGetExtensionRegistrationByExtensionId(*(_QWORD *)(v8 + 24), v7, v5);
      if ( ExtensionRegistrationByExtensionId < 0 )
      {
        v10 = 1697;
LABEL_6:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v10,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
          (const char *)(unsigned int)ExtensionRegistrationByExtensionId,
          v15[0]);
        return (unsigned int)ExtensionRegistrationByExtensionId;
      }
    }
    else
    {
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v6);
      v12 = *(_QWORD *)a4;
      v13 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(v17, &v16) + 24);
      v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v18, v15);
      ExtensionRegistrationByExtensionId = RoGetExtensionRegistration(*(_QWORD *)(v14 + 24), v13, v12, v5);
      if ( ExtensionRegistrationByExtensionId < 0 )
      {
        v10 = 1701;
        goto LABEL_6;
      }
    }
    WindowsDeleteString(*((HSTRING *)a4 + 3));
    *((_QWORD *)a4 + 3) = 0;
    ExtensionRegistrationByExtensionId = GetAppIdForExtensionRegistration(*v5, 0, (HSTRING *)a4 + 3);
    if ( ExtensionRegistrationByExtensionId < 0 )
    {
      v10 = 1704;
      goto LABEL_6;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18003d434  mov     [rsp+arg_0], rbx
0x18003d439  push    rsi
0x18003d43a  push    rdi
0x18003d43b  push    r14
0x18003d43d  sub     rsp, 80h
0x18003d444  mov     rax, cs:__security_cookie
0x18003d44b  xor     rax, rsp
0x18003d44e  mov     [rsp+98h+var_28], rax
0x18003d453  mov     [rsp+98h+var_70], rdx
0x18003d458  mov     r14, r9
0x18003d45b  mov     qword ptr [rsp+98h+var_78], r8; int
0x18003d460  lea     rsi, [r9+10h]
0x18003d464  test    ecx, ecx
0x18003d466  jnz     short loc_18003D472
0x18003d468  cmp     qword ptr [rsi], 0
0x18003d46c  jnz     loc_18003D545
0x18003d472  cmp     qword ptr [r9+8], 0
0x18003d477  mov     rcx, rsi
0x18003d47a  jz      short loc_18003D4CA
0x18003d47c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003d481  mov     rbx, [r14+8]
0x18003d485  lea     rdx, [rsp+98h+var_78]
0x18003d48a  lea     rcx, [rsp+98h+var_68]
0x18003d48f  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18003d494  mov     r8, rsi
0x18003d497  mov     rdx, rbx
0x18003d49a  mov     rcx, [rax+18h]
0x18003d49e  call    cs:__imp_RoGetExtensionRegistrationByExtensionId
0x18003d4a4  mov     ebx, eax
0x18003d4a6  test    eax, eax
0x18003d4a8  jns     short loc_18003D514
0x18003d4aa  mov     edx, 6A1h; void *
0x18003d4af  mov     rcx, [rsp+98h]; this
0x18003d4b7  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18003d4be  mov     r9d, ebx; char *
0x18003d4c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d4c6  mov     eax, ebx
0x18003d4c8  jmp     short loc_18003D547
0x18003d4ca  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003d4cf  mov     rdi, [r14]
0x18003d4d2  lea     rdx, [rsp+98h+var_70]
0x18003d4d7  lea     rcx, [rsp+98h+var_68]
0x18003d4dc  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18003d4e1  lea     rdx, [rsp+98h+var_78]
0x18003d4e6  lea     rcx, [rsp+98h+var_48]
0x18003d4eb  mov     rbx, [rax+18h]
0x18003d4ef  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18003d4f4  mov     r9, rsi
0x18003d4f7  mov     r8, rdi
0x18003d4fa  mov     rdx, rbx
0x18003d4fd  mov     rcx, [rax+18h]
0x18003d501  call    cs:__imp_RoGetExtensionRegistration
0x18003d507  mov     ebx, eax
0x18003d509  test    eax, eax
0x18003d50b  jns     short loc_18003D514
0x18003d50d  mov     edx, 6A5h
0x18003d512  jmp     short loc_18003D4AF
0x18003d514  lea     rbx, [r14+18h]
0x18003d518  mov     rcx, [rbx]; string
0x18003d51b  call    cs:__imp_WindowsDeleteString
0x18003d521  mov     qword ptr [rbx], 0
0x18003d528  mov     r8, rbx; HSTRING *
0x18003d52b  mov     rcx, [rsi]; struct Windows::Foundation::IExtensionRegistration *
0x18003d52e  xor     edx, edx; HSTRING *
0x18003d530  call    ?GetAppIdForExtensionRegistration@@YAJPEAUIExtensionRegistration@Foundation@Windows@@PEAPEAUHSTRING__@@1@Z; GetAppIdForExtensionRegistration(Windows::Foundation::IExtensionRegistration *,HSTRING__ * *,HSTRING__ * *)
0x18003d535  mov     ebx, eax
0x18003d537  test    eax, eax
0x18003d539  jns     short loc_18003D545
0x18003d53b  mov     edx, 6A8h
0x18003d540  jmp     loc_18003D4AF
0x18003d545  xor     eax, eax
0x18003d547  mov     rcx, [rsp+98h+var_28]
0x18003d54c  xor     rcx, rsp; StackCookie
0x18003d54f  call    __security_check_cookie
0x18003d554  mov     rbx, [rsp+98h+arg_0]
0x18003d55c  add     rsp, 80h
0x18003d563  pop     r14
0x18003d565  pop     rdi
0x18003d566  pop     rsi
0x18003d567  retn
```
