# Windows::Networking::UX::Internal::WlanInterface::UpdateProfileSecurity(Windows::Networking::UX::IAvailableNetwork *,ushort *)

- ea: `0x180047f90`
- end: `0x18004811e`
- name: `?UpdateProfileSecurity@WlanInterface@Internal@UX@Networking@Windows@@UEAAJPEAUIAvailableNetwork@345@PEAG@Z`
- size: `398`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::WlanInterface *__hidden this, struct Windows::Networking::UX::IAvailableNetwork *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180003ed0`
- `0x180008e30`
- `0x18000de4c`
- `0x180016f70`
- `0x18001d4d4`
- `0x180047f90`
- `0x18004a558`
- `0x18004c324`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048031`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800480ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048031`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800480ea`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Networking::UX::Internal::WlanInterface::UpdateProfileSecurity(
        Windows::Networking::UX::Internal::WlanClient **this,
        __int64 (__fastcall ***a2)(struct Windows::Networking::UX::IAvailableNetwork *, GUID *, __int64 *),
        unsigned __int16 *a3)
{
  __int64 (__fastcall *v6)(struct Windows::Networking::UX::IAvailableNetwork *, GUID *, __int64 *); // rbx
  int updated; // ebx
  __int64 (__fastcall *v8)(struct Windows::Networking::UX::IAvailableNetwork *, HSTRING *); // rbx
  Windows::Networking::UX::Internal::WlanClient *v9; // rdi
  enum _DOT11_CIPHER_ALGORITHM v10; // ebx
  enum _DOT11_AUTH_ALGORITHM v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  HSTRING string; // [rsp+30h] [rbp-30h] BYREF
  __int64 v16; // [rsp+38h] [rbp-28h] BYREF
  struct _GUID v17; // [rsp+40h] [rbp-20h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 190, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids);
  v16 = 0;
  string = 0;
  v6 = **a2;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v16, a2, a3);
  updated = v6(
              (struct Windows::Networking::UX::IAvailableNetwork *)a2,
              &GUID_ac2798f8_4bd2_4d64_be61_7002641cd494,
              &v16);
  if ( updated >= 0 )
  {
    v8 = (__int64 (__fastcall *)(struct Windows::Networking::UX::IAvailableNetwork *, HSTRING *))(*a2)[7];
    WindowsDeleteString(string);
    string = 0;
    updated = v8((struct Windows::Networking::UX::IAvailableNetwork *)a2, &string);
    if ( updated >= 0 )
    {
      Windows::Networking::UX::Internal::WlanInterface::_GetNetworkInterfaceGuid(
        (Windows::Networking::UX::Internal::WlanInterface *)this,
        &v17,
        (struct Windows::Networking::UX::IAvailableNetwork *)a2);
      v9 = this[3];
      v10 = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v16 + 96LL))(v16);
      v11 = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v16 + 88LL))(v16);
      updated = Windows::Networking::UX::Internal::WlanClient::UpdateProfileSecurity(v9, &v17, string, v11, v10, a3);
      if ( updated >= 0 )
        updated = Windows::Networking::UX::Internal::WlanInterface::_SetupConnectionFlow(
                    (Windows::Networking::UX::Internal::WlanInterface *)this,
                    (struct Windows::Networking::UX::IAvailableNetwork *)a2);
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      191,
      &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids,
      (unsigned int)updated);
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v16, v12, v13);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180047f90  push    rbp
0x180047f92  push    rbx
0x180047f93  push    rsi
0x180047f94  push    rdi
0x180047f95  push    r13
0x180047f97  push    r14
0x180047f99  push    r15
0x180047f9b  mov     rbp, rsp
0x180047f9e  sub     rsp, 60h
0x180047fa2  mov     rax, cs:__security_cookie
0x180047fa9  xor     rax, rsp
0x180047fac  mov     [rbp+var_10], rax
0x180047fb0  mov     r15, r8
0x180047fb3  mov     rsi, rdx
0x180047fb6  mov     r14, rcx
0x180047fb9  lea     r13, WPP_GLOBAL_Control
0x180047fc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180047fc7  cmp     rcx, r13
0x180047fca  jz      short loc_180047FE7
0x180047fcc  test    byte ptr [rcx+1Ch], 8
0x180047fd0  jz      short loc_180047FE7
0x180047fd2  mov     edx, 0BEh
0x180047fd7  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x180047fde  mov     rcx, [rcx+10h]
0x180047fe2  call    WPP_SF_
0x180047fe7  mov     [rbp+var_28], 0
0x180047fef  mov     [rbp+string], 0
0x180047ff7  mov     rax, [rsi]
0x180047ffa  mov     rbx, [rax]
0x180047ffd  lea     rcx, [rbp+var_28]
0x180048001  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180048006  lea     r8, [rbp+var_28]
0x18004800a  lea     rdx, _GUID_ac2798f8_4bd2_4d64_be61_7002641cd494
0x180048011  mov     rcx, rsi
0x180048014  mov     rax, rbx
0x180048017  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004801c  mov     ebx, eax
0x18004801e  test    eax, eax
0x180048020  js      loc_1800480BB
0x180048026  mov     rax, [rsi]
0x180048029  mov     rbx, [rax+38h]
0x18004802d  mov     rcx, [rbp+string]; string
0x180048031  call    cs:__imp_WindowsDeleteString
0x180048037  mov     [rbp+string], 0
0x18004803f  lea     rdx, [rbp+string]
0x180048043  mov     rcx, rsi
0x180048046  mov     rax, rbx
0x180048049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004804e  mov     ebx, eax
0x180048050  test    eax, eax
0x180048052  js      short loc_1800480BB
0x180048054  mov     r8, rsi; struct Windows::Networking::UX::IAvailableNetwork *
0x180048057  lea     rdx, [rbp+var_20]; retstr
0x18004805b  mov     rcx, r14; this
0x18004805e  call    ?_GetNetworkInterfaceGuid@WlanInterface@Internal@UX@Networking@Windows@@IEAA?AU_GUID@@PEAUIAvailableNetwork@345@@Z; Windows::Networking::UX::Internal::WlanInterface::_GetNetworkInterfaceGuid(Windows::Networking::UX::IAvailableNetwork *)
0x180048063  mov     rdi, [r14+18h]
0x180048067  mov     rcx, [rbp+var_28]
0x18004806b  mov     rax, [rcx]
0x18004806e  mov     rax, [rax+60h]
0x180048072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048077  mov     ebx, eax
0x180048079  mov     rdx, [rbp+var_28]
0x18004807d  mov     rcx, [rdx]
0x180048080  mov     rax, [rcx+58h]
0x180048084  mov     rcx, rdx
0x180048087  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004808c  mov     [rsp+60h+var_38], r15; unsigned __int16 *
0x180048091  mov     [rsp+60h+var_40], ebx; enum _DOT11_CIPHER_ALGORITHM
0x180048095  mov     r9d, eax; enum _DOT11_AUTH_ALGORITHM
0x180048098  mov     r8, [rbp+string]; HSTRING
0x18004809c  lea     rdx, [rbp+var_20]; struct _GUID *
0x1800480a0  mov     rcx, rdi; this
0x1800480a3  call    ?UpdateProfileSecurity@WlanClient@Internal@UX@Networking@Windows@@QEAAJAEBU_GUID@@PEAUHSTRING__@@W4_DOT11_AUTH_ALGORITHM@@W4_DOT11_CIPHER_ALGORITHM@@PEAG@Z; Windows::Networking::UX::Internal::WlanClient::UpdateProfileSecurity(_GUID const &,HSTRING__ *,_DOT11_AUTH_ALGORITHM,_DOT11_CIPHER_ALGORITHM,ushort *)
0x1800480a8  mov     ebx, eax
0x1800480aa  test    eax, eax
0x1800480ac  js      short loc_1800480BB
0x1800480ae  mov     rdx, rsi; struct Windows::Networking::UX::IAvailableNetwork *
0x1800480b1  mov     rcx, r14; this
0x1800480b4  call    ?_SetupConnectionFlow@WlanInterface@Internal@UX@Networking@Windows@@IEAAJPEAUIAvailableNetwork@345@@Z; Windows::Networking::UX::Internal::WlanInterface::_SetupConnectionFlow(Windows::Networking::UX::IAvailableNetwork *)
0x1800480b9  mov     ebx, eax
0x1800480bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800480c2  cmp     rcx, r13
0x1800480c5  jz      short loc_1800480E6
0x1800480c7  test    byte ptr [rcx+1Ch], 8
0x1800480cb  jz      short loc_1800480E6
0x1800480cd  mov     edx, 0BFh
0x1800480d2  mov     r9d, ebx
0x1800480d5  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x1800480dc  mov     rcx, [rcx+10h]
0x1800480e0  call    WPP_SF_d
0x1800480e5  nop
0x1800480e6  mov     rcx, [rbp+string]; string
0x1800480ea  call    cs:__imp_WindowsDeleteString
0x1800480f0  mov     [rbp+string], 0
0x1800480f8  lea     rcx, [rbp+var_28]
0x1800480fc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180048101  mov     eax, ebx
0x180048103  mov     rcx, [rbp+var_10]
0x180048107  xor     rcx, rsp; StackCookie
0x18004810a  call    __security_check_cookie
0x18004810f  add     rsp, 60h
0x180048113  pop     r15
0x180048115  pop     r14
0x180048117  pop     r13
0x180048119  pop     rdi
0x18004811a  pop     rsi
0x18004811b  pop     rbx
0x18004811c  pop     rbp
0x18004811d  retn
```
