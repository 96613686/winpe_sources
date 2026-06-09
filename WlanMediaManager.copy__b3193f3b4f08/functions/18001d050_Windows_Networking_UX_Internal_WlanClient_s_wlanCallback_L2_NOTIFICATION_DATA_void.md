# Windows::Networking::UX::Internal::WlanClient::s_wlanCallback(_L2_NOTIFICATION_DATA *,void *)

- ea: `0x18001d050`
- end: `0x18001d23c`
- name: `?s_wlanCallback@WlanClient@Internal@UX@Networking@Windows@@KAXPEAU_L2_NOTIFICATION_DATA@@PEAX@Z`
- size: `492`
- prototype: `void __stdcall(PWLAN_NOTIFICATION_DATA, PVOID)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003ed0`
- `0x180008e30`
- `0x18000a7d8`
- `0x18000de4c`
- `0x18000e1dc`
- `0x18000e314`
- `0x1800114f0`
- `0x180011c24`
- `0x18001be60`
- `0x18001be80`
- `0x18001cb10`
- `0x18001d050`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d11c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d11c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d1d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d1d6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Windows::Networking::UX::Internal::WlanClient::s_wlanCallback(
        PWLAN_NOTIFICATION_DATA a1,
        _QWORD *a2,
        __int64 a3)
{
  rsize_t v5; // r14
  void *v6; // rax
  const char *v7; // r9
  void *v8; // rdi
  __int64 v9; // rax
  unsigned int v10; // r11d
  __int64 v11; // rdx
  __int64 v12; // rcx
  int v13; // edi
  const char *v14; // r9
  int v15; // [rsp+20h] [rbp-B8h]
  struct IInspectable *v16; // [rsp+30h] [rbp-A8h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-A0h] BYREF
  _QWORD *v18; // [rsp+40h] [rbp-98h] BYREF
  __int128 Destination; // [rsp+48h] [rbp-90h] BYREF
  SIZE_T cb[2]; // [rsp+58h] [rbp-80h]
  void *v21; // [rsp+68h] [rbp-70h]
  _BYTE v22[64]; // [rsp+70h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, &WPP_21979ef79db039135e573b3136931b8d_Traceguids);
  try
  {
    v18 = a2;
    v16 = 0;
    if ( a2[73]
      && (int)Microsoft::WRL::WeakRef::As<Windows::Networking::UX::Internal::IMediaManager>(
                (Microsoft::WRL::WeakRef *)(a2 + 73),
                &v16) >= 0
      && v16
      && a1 )
    {
      Destination = 0;
      *(_OWORD *)cb = 0;
      v21 = 0;
      memcpy_s_0(&Destination, 0x28u, a1, 0x28u);
      v5 = LODWORD(cb[1]);
      v6 = CoTaskMemAlloc(LODWORD(cb[1]));
      v8 = v6;
      pv = v6;
      if ( !v6 )
        wil::details::in1diag3::_Throw_NullAlloc(
          retaddr,
          (void *)0x62E,
          (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlanclient.cpp",
          v7);
      memcpy_s_0(v6, v5, a1->pData, a1->dwDataSize);
      v21 = v8;
      std::_Atomic_storage<unsigned long,4>::load(&v16[7]);
      v9 = Windows::Networking::UX::Internal::WlanClient::s_wlanCallback_::_6_::_lambda_1_::_lambda_1_(
             (unsigned int)v22,
             (unsigned int)&v18,
             (unsigned int)&v16,
             (unsigned int)&Destination,
             (__int64)&pv);
      v13 = Windows::Internal::ComTaskPool::QueueTask__Windows::Networking::UX::Internal::WlanClient::s_wlanCallback_::_6_::_lambda_1___(
              v12,
              v11,
              v10,
              v9);
      Windows::Networking::UX::Internal::WlanClient::s_wlanCallback_::_6_::_lambda_1_::__lambda_1_(v22);
      if ( v13 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x644,
          (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlanclient.cpp",
          (const char *)(unsigned int)v13,
          v15);
      if ( pv )
        CoTaskMemFree(pv);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v16, a2, a3);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x647,
      (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlanclient.cpp",
      v14);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 110, &WPP_21979ef79db039135e573b3136931b8d_Traceguids);
}

```

## disassembly

```asm
0x18001d050  mov     [rsp+arg_10], rbx
0x18001d055  push    rsi
0x18001d056  push    rdi
0x18001d057  push    r14
0x18001d059  sub     rsp, 0C0h
0x18001d060  mov     rax, cs:__security_cookie
0x18001d067  xor     rax, rsp
0x18001d06a  mov     [rsp+0D8h+var_28], rax
0x18001d072  mov     rdi, rdx
0x18001d075  mov     rsi, rcx
0x18001d078  lea     rbx, WPP_GLOBAL_Control
0x18001d07f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d086  cmp     rcx, rbx
0x18001d089  jz      short loc_18001D0A7
0x18001d08b  test    byte ptr [rcx+1Ch], 40h
0x18001d08f  jz      short loc_18001D0A7
0x18001d091  mov     edx, 6Dh ; 'm'
0x18001d096  lea     r8, WPP_21979ef79db039135e573b3136931b8d_Traceguids
0x18001d09d  mov     rcx, [rcx+10h]
0x18001d0a1  call    WPP_SF_
0x18001d0a6  nop
0x18001d0a7  mov     [rsp+0D8h+var_98], rdi
0x18001d0ac  mov     [rsp+0D8h+var_A8], 0
0x18001d0b5  lea     rcx, [rdi+248h]; this
0x18001d0bc  cmp     qword ptr [rcx], 0
0x18001d0c0  jz      loc_18001D1DD
0x18001d0c6  lea     rdx, [rsp+0D8h+var_A8]; struct IInspectable **
0x18001d0cb  call    ??$As@UIMediaManager@Internal@UX@Networking@Windows@@@WeakRef@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIMediaManager@Internal@UX@Networking@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::WeakRef::As<Windows::Networking::UX::Internal::IMediaManager>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Networking::UX::Internal::IMediaManager>>)
0x18001d0d0  test    eax, eax
0x18001d0d2  js      loc_18001D1DD
0x18001d0d8  cmp     [rsp+0D8h+var_A8], 0
0x18001d0de  jz      loc_18001D1DD
0x18001d0e4  test    rsi, rsi
0x18001d0e7  jz      loc_18001D1DD
0x18001d0ed  xorps   xmm0, xmm0
0x18001d0f0  xor     eax, eax
0x18001d0f2  movups  [rsp+0D8h+Destination], xmm0
0x18001d0f7  movups  xmmword ptr [rsp+0D8h+cb], xmm0
0x18001d0fc  mov     [rsp+0D8h+var_70], rax
0x18001d101  lea     edx, [rax+28h]; DestinationSize
0x18001d104  mov     r9d, edx; SourceSize
0x18001d107  mov     r8, rsi; Source
0x18001d10a  lea     rcx, [rsp+0D8h+Destination]; Destination
0x18001d10f  call    memcpy_s_0
0x18001d114  mov     r14d, dword ptr [rsp+0D8h+cb+8]
0x18001d119  mov     ecx, r14d; cb
0x18001d11c  call    cs:__imp_CoTaskMemAlloc
0x18001d122  mov     rdi, rax
0x18001d125  mov     [rsp+0D8h+pv], rax
0x18001d12a  mov     rcx, [rsp+0D8h]; this
0x18001d132  test    rax, rax
0x18001d135  jnz     short loc_18001D148
0x18001d137  lea     r8, aOnecoreuapNetU_22; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18001d13e  mov     edx, 62Eh; void *
0x18001d143  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18001d148  mov     r9d, [rsi+18h]; SourceSize
0x18001d14c  mov     r8, [rsi+20h]; Source
0x18001d150  mov     rdx, r14; DestinationSize
0x18001d153  mov     rcx, rdi; Destination
0x18001d156  call    memcpy_s_0
0x18001d15b  mov     [rsp+0D8h+var_70], rdi
0x18001d160  mov     rcx, [rsp+0D8h+var_A8]
0x18001d165  add     rcx, 38h ; '8'
0x18001d169  call    ?load@?$_Atomic_storage@K$03@std@@QEBAKW4memory_order@2@@Z; std::_Atomic_storage<ulong,4>::load(std::memory_order)
0x18001d16e  mov     r11d, eax
0x18001d171  lea     rax, [rsp+0D8h+pv]
0x18001d176  mov     qword ptr [rsp+0D8h+var_B8], rax; int
0x18001d17b  lea     r9, [rsp+0D8h+Destination]
0x18001d180  lea     r8, [rsp+0D8h+var_A8]
0x18001d185  lea     rdx, [rsp+0D8h+var_98]
0x18001d18a  lea     rcx, [rsp+0D8h+var_68]
0x18001d18f  call    _Windows__Networking__UX__Internal__WlanClient__s_wlanCallback____6____lambda_1____lambda_1_
0x18001d194  mov     r9, rax
0x18001d197  mov     r8d, r11d
0x18001d19a  call    Windows__Internal__ComTaskPool__QueueTask__Windows__Networking__UX__Internal__WlanClient__s_wlanCallback____6____lambda_1___
0x18001d19f  mov     edi, eax
0x18001d1a1  lea     rcx, [rsp+0D8h+var_68]
0x18001d1a6  call    _Windows__Networking__UX__Internal__WlanClient__s_wlanCallback____6____lambda_1_____lambda_1_
0x18001d1ab  mov     rcx, [rsp+0D8h]; this
0x18001d1b3  test    edi, edi
0x18001d1b5  jns     short loc_18001D1CC
0x18001d1b7  mov     r9d, edi; char *
0x18001d1ba  lea     r8, aOnecoreuapNetU_22; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18001d1c1  mov     edx, 644h; void *
0x18001d1c6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001d1cc  mov     rcx, [rsp+0D8h+pv]; pv
0x18001d1d1  test    rcx, rcx
0x18001d1d4  jz      short loc_18001D1DD
0x18001d1d6  call    cs:__imp_CoTaskMemFree
0x18001d1dc  nop
0x18001d1dd  lea     rcx, [rsp+0D8h+var_A8]
0x18001d1e2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001d1e7  nop
0x18001d1e8  jmp     short loc_18001D1F1
0x18001d1ea  lea     rbx, WPP_GLOBAL_Control
0x18001d1f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d1f8  cmp     rcx, rbx
0x18001d1fb  jz      short loc_18001D218
0x18001d1fd  test    byte ptr [rcx+1Ch], 40h
0x18001d201  jz      short loc_18001D218
0x18001d203  mov     edx, 6Eh ; 'n'
0x18001d208  lea     r8, WPP_21979ef79db039135e573b3136931b8d_Traceguids
0x18001d20f  mov     rcx, [rcx+10h]
0x18001d213  call    WPP_SF_
0x18001d218  mov     rcx, [rsp+0D8h+var_28]
0x18001d220  xor     rcx, rsp; StackCookie
0x18001d223  call    __security_check_cookie
0x18001d228  mov     rbx, [rsp+0D8h+arg_10]
0x18001d230  add     rsp, 0C0h
0x18001d237  pop     r14
0x18001d239  pop     rdi
0x18001d23a  pop     rsi
0x18001d23b  retn
```
