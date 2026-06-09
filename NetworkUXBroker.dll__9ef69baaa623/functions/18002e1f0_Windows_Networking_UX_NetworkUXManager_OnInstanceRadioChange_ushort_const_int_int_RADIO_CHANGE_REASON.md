# Windows::Networking::UX::NetworkUXManager::OnInstanceRadioChange(ushort const *,int,int,_RADIO_CHANGE_REASON)

- ea: `0x18002e1f0`
- end: `0x18002e3af`
- name: `?OnInstanceRadioChange@NetworkUXManager@UX@Networking@Windows@@UEAAJPEBGHHW4_RADIO_CHANGE_REASON@@@Z`
- size: `447`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002e3c0`

## callees

- `0x180002520`
- `0x180007be0`
- `0x18000955c`
- `0x18000e768`
- `0x180015f50`
- `0x180024188`
- `0x180026ecc`
- `0x18002e1f0`
- `0x180032f60`
- `0x180037b34`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002e255`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002e255`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::NetworkUXManager::OnInstanceRadioChange(
        Windows::Networking::UX::NetworkUXManager *a1,
        const OLECHAR *a2,
        int a3,
        char a4)
{
  HRESULT v6; // eax
  unsigned int v7; // ebx
  int v8; // eax
  int WeakReference; // eax
  unsigned __int64 v10; // r9
  __int64 v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v16; // [rsp+20h] [rbp-60h]
  int v17; // [rsp+30h] [rbp-50h] BYREF
  struct Windows::Networking::UX::IUXCategory *v18; // [rsp+38h] [rbp-48h] BYREF
  struct _GUID v19; // [rsp+40h] [rbp-40h] BYREF
  GUID pclsid; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v21[24]; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_Sll(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)a2, a3, (_DWORD)a2, a3, a4);
  pclsid = 0;
  v6 = CLSIDFromString(a2, &pclsid);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v18 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
    v19 = pclsid;
    if ( Windows::Networking::UX::NetworkUXManager::_FindCategoryFromManagers(a1, &v19, &v18) )
    {
      v17 = 0;
      v8 = (*(__int64 (__fastcall **)(struct Windows::Networking::UX::IUXCategory *, int *))(*(_QWORD *)v18 + 72LL))(
             v18,
             &v17);
      v7 = v8;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1F4,
          (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\networkuxmanager.cpp",
          (const char *)(unsigned int)v8,
          v16);
LABEL_17:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
        return v7;
      }
      if ( v17 != 1 )
      {
        *(_QWORD *)&v19.Data1 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
        WeakReference = Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::IAdapterStatistics,Microsoft::WRL::FtmBase>::GetWeakReference(
                          (char *)a1 + 8,
                          &v19);
        v7 = WeakReference;
        if ( WeakReference < 0 )
        {
          v10 = (unsigned int)WeakReference;
          v11 = 505;
LABEL_12:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v11,
            (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\networkuxmanager.cpp",
            (const char *)v10,
            v16);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
          goto LABEL_17;
        }
        v12 = Windows::Networking::UX::NetworkUXManager::OnInstanceRadioChange_::_22_::_lambda_1_::_lambda_1_(
                v21,
                &v19,
                &pclsid);
        v7 = Windows::Internal::ComTaskPool::QueueTask__Windows::Networking::UX::NetworkUXManager::OnInstanceRadioChange_::_22_::_lambda_1___(
               v14,
               v13,
               dword_18007EB30,
               v12);
        Microsoft::WRL::ComPtr<IWbemServices>::~ComPtr<IWbemServices>(v21);
        if ( (v7 & 0x80000000) != 0 )
        {
          v10 = v7;
          v11 = 516;
          goto LABEL_12;
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
      }
    }
    v7 = 0;
    goto LABEL_17;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1EE,
    (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\networkuxmanager.cpp",
    (const char *)(unsigned int)v6,
    v16);
  return v7;
}

```

## disassembly

```asm
0x18002e1f0  mov     r11, rsp
0x18002e1f3  mov     [r11+18h], rbx
0x18002e1f7  mov     [r11+20h], rdi
0x18002e1fb  push    rbp
0x18002e1fc  mov     rbp, rsp
0x18002e1ff  sub     rsp, 80h
0x18002e206  mov     rax, cs:__security_cookie
0x18002e20d  xor     rax, rsp
0x18002e210  mov     [rbp+var_8], rax
0x18002e214  mov     rbx, rdx
0x18002e217  mov     rdi, rcx
0x18002e21a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e221  lea     rax, WPP_GLOBAL_Control
0x18002e228  cmp     rcx, rax
0x18002e22b  jz      short loc_18002E247
0x18002e22d  test    byte ptr [rcx+1Ch], 8
0x18002e231  jz      short loc_18002E247
0x18002e233  mov     rcx, [rcx+10h]
0x18002e237  mov     [r11-60h], r9d
0x18002e23b  mov     r9, rdx
0x18002e23e  mov     [r11-68h], r8d
0x18002e242  call    WPP_SF_Sll
0x18002e247  xorps   xmm0, xmm0
0x18002e24a  lea     rdx, [rbp+pclsid]; pclsid
0x18002e24e  mov     rcx, rbx; lpsz
0x18002e251  movups  xmmword ptr [rbp+pclsid.Data1], xmm0
0x18002e255  call    cs:__imp_CLSIDFromString
0x18002e25b  mov     ebx, eax
0x18002e25d  test    eax, eax
0x18002e25f  jns     short loc_18002E27E
0x18002e261  mov     rcx, [rbp+8]; this
0x18002e265  lea     r8, aOnecoreuapNetU_5; "onecoreuap\\net\\ux\\uxmanager\\lib\\ne"...
0x18002e26c  mov     r9d, eax; char *
0x18002e26f  mov     edx, 1EEh; void *
0x18002e274  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e279  jmp     loc_18002E38C
0x18002e27e  lea     rcx, [rbp+var_48]
0x18002e282  mov     [rbp+var_48], 0
0x18002e28a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002e28f  movaps  xmm0, xmmword ptr [rbp+pclsid.Data1]
0x18002e293  lea     r8, [rbp+var_48]; struct Windows::Networking::UX::IUXCategory **
0x18002e297  lea     rdx, [rbp+var_40]; struct _GUID
0x18002e29b  movdqa  xmmword ptr [rbp+var_40.Data1], xmm0
0x18002e2a0  mov     rcx, rdi; this
0x18002e2a3  call    ?_FindCategoryFromManagers@NetworkUXManager@UX@Networking@Windows@@AEAA_NU_GUID@@PEAPEAUIUXCategory@234@@Z; Windows::Networking::UX::NetworkUXManager::_FindCategoryFromManagers(_GUID,Windows::Networking::UX::IUXCategory * *)
0x18002e2a8  test    al, al
0x18002e2aa  jz      loc_18002E381
0x18002e2b0  mov     rcx, [rbp+var_48]
0x18002e2b4  lea     rdx, [rbp+var_50]
0x18002e2b8  mov     [rbp+var_50], 0
0x18002e2bf  mov     rax, [rcx]
0x18002e2c2  mov     rax, [rax+48h]
0x18002e2c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e2cb  mov     ebx, eax
0x18002e2cd  test    eax, eax
0x18002e2cf  jns     short loc_18002E2EE
0x18002e2d1  mov     rcx, [rbp+8]; this
0x18002e2d5  lea     r8, aOnecoreuapNetU_5; "onecoreuap\\net\\ux\\uxmanager\\lib\\ne"...
0x18002e2dc  mov     r9d, eax; char *
0x18002e2df  mov     edx, 1F4h; void *
0x18002e2e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e2e9  jmp     loc_18002E383
0x18002e2ee  cmp     [rbp+var_50], 1
0x18002e2f2  jz      loc_18002E381
0x18002e2f8  lea     rcx, [rbp+var_40]
0x18002e2fc  mov     qword ptr [rbp+var_40.Data1], 0
0x18002e304  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002e309  lea     rcx, [rdi+8]
0x18002e30d  lea     rdx, [rbp+var_40]
0x18002e311  call    ?GetWeakReference@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIAdapterStatistics@UX@Networking@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAPEAUIWeakReference@@@Z; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::IAdapterStatistics,Microsoft::WRL::FtmBase>::GetWeakReference(IWeakReference * *)
0x18002e316  mov     ebx, eax
0x18002e318  test    eax, eax
0x18002e31a  jns     short loc_18002E33F
0x18002e31c  mov     r9d, eax; char *
0x18002e31f  mov     edx, 1F9h; void *
0x18002e324  mov     rcx, [rbp+8]; this
0x18002e328  lea     r8, aOnecoreuapNetU_5; "onecoreuap\\net\\ux\\uxmanager\\lib\\ne"...
0x18002e32f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e334  lea     rcx, [rbp+var_40]
0x18002e338  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002e33d  jmp     short loc_18002E383
0x18002e33f  lea     r8, [rbp+pclsid]
0x18002e343  lea     rdx, [rbp+var_40]
0x18002e347  lea     rcx, [rbp+var_20]
0x18002e34b  call    _Windows__Networking__UX__NetworkUXManager__OnInstanceRadioChange____22____lambda_1____lambda_1_
0x18002e350  mov     r8d, cs:dword_18007EB30
0x18002e357  mov     r9, rax
0x18002e35a  call    Windows__Internal__ComTaskPool__QueueTask__Windows__Networking__UX__NetworkUXManager__OnInstanceRadioChange____22____lambda_1___
0x18002e35f  lea     rcx, [rbp+var_20]; void *
0x18002e363  mov     ebx, eax
0x18002e365  call    ??1?$ComPtr@UIWbemServices@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IWbemServices>::~ComPtr<IWbemServices>(void)
0x18002e36a  test    ebx, ebx
0x18002e36c  jns     short loc_18002E378
0x18002e36e  mov     r9d, ebx
0x18002e371  mov     edx, 204h
0x18002e376  jmp     short loc_18002E324
0x18002e378  lea     rcx, [rbp+var_40]
0x18002e37c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002e381  xor     ebx, ebx
0x18002e383  lea     rcx, [rbp+var_48]
0x18002e387  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002e38c  mov     eax, ebx
0x18002e38e  mov     rcx, [rbp+var_8]
0x18002e392  xor     rcx, rsp; StackCookie
0x18002e395  call    __security_check_cookie
0x18002e39a  lea     r11, [rsp+80h+var_s0]
0x18002e3a2  mov     rbx, [r11+20h]
0x18002e3a6  mov     rdi, [r11+28h]
0x18002e3aa  mov     rsp, r11
0x18002e3ad  pop     rbp
0x18002e3ae  retn
```
