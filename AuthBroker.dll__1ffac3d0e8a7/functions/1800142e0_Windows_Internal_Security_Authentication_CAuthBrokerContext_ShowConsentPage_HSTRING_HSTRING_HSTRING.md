# Windows::Internal::Security::Authentication::CAuthBrokerContext::ShowConsentPage(HSTRING__ *,HSTRING__ *,HSTRING__ *)

- ea: `0x1800142e0`
- end: `0x180014496`
- name: `?ShowConsentPage@CAuthBrokerContext@Authentication@Security@Internal@Windows@@UEAAJPEAUHSTRING__@@00@Z`
- size: `438`
- prototype: `HRESULT __fastcall(Windows::Internal::Security::Authentication::CAuthBrokerContext *this, HSTRING__ *url, HSTRING__ *userName, HSTRING__ *password)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180012b88`
- `0x180013d9c`
- `0x1800142e0`
- `0x1800204ee`
- `0x180020520`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180014420`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180014420`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800143d6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800143d6`

## string_xrefs

- `0x1800143b9`: `SYSTEM\CurrentControlSet\Control\WebAuthBrokerTest`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Security::Authentication::CAuthBrokerContext::ShowConsentPage(
        Windows::Internal::Security::Authentication::CAuthBrokerContext *this,
        HSTRING__ *url,
        HSTRING__ *userName,
        HSTRING__ *password)
{
  _BOOL8 v8; // rdx
  int pvData; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int pcbData; // [rsp+44h] [rbp-BCh] BYREF
  HSTRING__ *other[5]; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t title[264]; // [rsp+70h] [rbp-90h] BYREF

  if ( this->m_wndMgmt && this->m_pWebAuthDialog )
  {
    title[0] = 0;
    memset_0(&title[1], 0, 0x206u);
    other[0] = url;
    Windows::Internal::String::Initialize(&this->m_urlString, other);
    other[0] = userName;
    Windows::Internal::String::Initialize(&this->m_UserName, other);
    other[0] = password;
    Windows::Internal::String::Initialize(&this->m_Password, other);
    pvData = 0;
    pcbData = 4;
    if ( RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"SYSTEM\\CurrentControlSet\\Control\\WebAuthBrokerTest",
           L"ButtonClicked",
           0x10u,
           0,
           &pvData,
           &pcbData) )
    {
      LOBYTE(v8) = 1;
      this->m_wndMgmt->ShowConsentBar(this->m_wndMgmt, v8);
      LoadStringW(g_hInstance, 0x3EBu, title, 260);
      this->m_pWebAuthDialog->SetTitle(this->m_pWebAuthDialog, title);
      this->m_pWebAuthDialog->SetHeaderColor(this->m_pWebAuthDialog, this->m_headerColor);
      this->m_wndMgmt->SetConsentButtonColor(this->m_wndMgmt, this->m_headerColor);
    }
    else if ( pvData )
    {
      Windows::Internal::Security::Authentication::CAuthBrokerContext::SaveCreds(this);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800142e0  mov     [rsp-8+arg_8], rbx
0x1800142e5  mov     [rsp-8+arg_10], rsi
0x1800142ea  push    rbp
0x1800142eb  push    rdi
0x1800142ec  push    r14
0x1800142ee  lea     rbp, [rsp-190h]
0x1800142f6  sub     rsp, 290h
0x1800142fd  mov     rax, cs:__security_cookie
0x180014304  xor     rax, rsp
0x180014307  mov     [rbp+1A0h+var_20], rax
0x18001430e  cmp     qword ptr [this+0F0h], 0
0x180014316  mov     rdi, password
0x180014319  mov     rsi, userName
0x18001431c  mov     r14, url
0x18001431f  mov     rbx, this
0x180014322  jz      loc_18001446D
0x180014328  cmp     qword ptr [this+58h], 0
0x18001432d  jz      loc_18001446D
0x180014333  xor     eax, eax
0x180014335  lea     this, [rsp+2A0h+title+2]; void *
0x18001433a  xor     edx, edx; Val
0x18001433c  mov     [rsp+2A0h+title], ax
0x180014341  mov     r8d, 206h; Size
0x180014347  call    memset_0
0x18001434c  lea     this, [rbx+0F8h]; this
0x180014353  mov     [rsp+2A0h+other], r14
0x180014358  lea     url, [rsp+2A0h+other]; other
0x18001435d  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x180014362  lea     this, [rbx+100h]; this
0x180014369  mov     [rsp+2A0h+other], rsi
0x18001436e  lea     url, [rsp+2A0h+other]; other
0x180014373  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x180014378  lea     this, [rbx+108h]; this
0x18001437f  mov     [rsp+2A0h+other], rdi
0x180014384  lea     url, [rsp+2A0h+other]; other
0x180014389  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x18001438e  lea     rax, [rsp+2A0h+var_25C]
0x180014393  mov     [rsp+2A0h+var_260], 0
0x18001439b  mov     [rsp+2A0h+pcbData], rax; pcbData
0x1800143a0  lea     userName, aButtonclicked; "ButtonClicked"
0x1800143a7  lea     rax, [rsp+2A0h+var_260]
0x1800143ac  mov     [rsp+2A0h+var_25C], 4
0x1800143b4  mov     [rsp+2A0h+pvData], rax; pvData
0x1800143b9  lea     url, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Web"...
0x1800143c0  mov     r9d, 10h; dwFlags
0x1800143c6  mov     [rsp+2A0h+pdwType], 0; pdwType
0x1800143cf  mov     this, 0FFFFFFFF80000002h; hkey
0x1800143d6  call    cs:__imp_RegGetValueW
0x1800143dc  test    eax, eax
0x1800143de  jnz     short loc_1800143F4
0x1800143e0  cmp     [rsp+2A0h+var_260], eax
0x1800143e4  jz      loc_18001446D
0x1800143ea  mov     this, rbx; this
0x1800143ed  call    ?SaveCreds@CAuthBrokerContext@Authentication@Security@Internal@Windows@@QEAAXXZ; Windows::Internal::Security::Authentication::CAuthBrokerContext::SaveCreds(void)
0x1800143f2  jmp     short loc_18001446D
0x1800143f4  mov     this, [rbx+0F0h]
0x1800143fb  mov     dl, 1
0x1800143fd  mov     rax, [this]
0x180014400  mov     rax, [rax+50h]
0x180014404  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014409  mov     this, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180014410  lea     userName, [rsp+2A0h+title]; lpBuffer
0x180014415  mov     r9d, 104h; cchBufferMax
0x18001441b  mov     edx, 3EBh; uID
0x180014420  call    cs:__imp_LoadStringW
0x180014426  mov     this, [rbx+58h]
0x18001442a  lea     url, [rsp+2A0h+title]
0x18001442f  mov     rax, [this]
0x180014432  mov     rax, [rax+20h]
0x180014436  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001443b  mov     this, [rbx+58h]
0x18001443f  mov     edx, [rbx+110h]
0x180014445  mov     rax, [this]
0x180014448  mov     rax, [rax+28h]
0x18001444c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014451  mov     this, [rbx+0F0h]
0x180014458  mov     edx, [rbx+110h]
0x18001445e  mov     rax, [this]
0x180014461  mov     rax, [rax+80h]
0x180014468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001446d  xor     eax, eax
0x18001446f  mov     this, [rbp+1A0h+var_20]
0x180014476  xor     this, rsp; StackCookie
0x180014479  call    __security_check_cookie
0x18001447e  lea     r11, [rsp+2A0h+var_10]
0x180014486  mov     rbx, [r11+28h]
0x18001448a  mov     rsi, [r11+30h]
0x18001448e  mov     rsp, r11
0x180014491  pop     r14
0x180014493  pop     rdi
0x180014494  pop     rbp
0x180014495  retn
```
