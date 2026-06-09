# CredUXParameters::~CredUXParameters(void)

- ea: `0x140009340`
- end: `0x1400094a4`
- name: `??1CredUXParameters@@UEAA@XZ`
- size: `356`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000a460`

## callees

- `0x140008b38`
- `0x140009340`
- `0x14000e920`
- `0x14001f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140009360`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140009376`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140009396`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400093aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000943f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140009450`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000945e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000946c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000947a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140009488`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140009360`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140009376`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140009396`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400093aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000943f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140009450`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000945e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000946c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000947a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140009488`

## pseudocode

```c
void __fastcall CredUXParameters::~CredUXParameters(HSTRING *this)
{
  HSTRING v2; // rcx
  HSTRING v3; // rcx
  HSTRING v4; // rcx

  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(this + 36);
  WindowsDeleteString(this[35]);
  this[35] = 0;
  WindowsDeleteString(this[34]);
  this[34] = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(this + 32);
  WindowsDeleteString(this[30]);
  this[30] = 0;
  WindowsDeleteString(this[29]);
  this[29] = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(this + 27);
  v2 = this[26];
  if ( v2 )
  {
    this[26] = 0;
    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v2 + 16LL))(v2);
  }
  v3 = this[25];
  if ( v3 )
  {
    this[25] = 0;
    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v3 + 16LL))(v3);
  }
  v4 = this[24];
  if ( v4 )
  {
    this[24] = 0;
    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v4 + 16LL))(v4);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(this + 23);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(this + 18);
  WindowsDeleteString(this[17]);
  this[17] = 0;
  WindowsDeleteString(this[14]);
  this[14] = 0;
  WindowsDeleteString(this[13]);
  this[13] = 0;
  WindowsDeleteString(this[12]);
  this[12] = 0;
  WindowsDeleteString(this[11]);
  this[11] = 0;
  WindowsDeleteString(this[10]);
  this[10] = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::UI::Credentials::Controller::ICredUXParameters,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::UI::Credentials::Controller::ICredUXParameters,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x140009340  mov     [rsp+arg_0], rbx
0x140009345  push    rdi
0x140009346  sub     rsp, 20h
0x14000934a  mov     rbx, rcx
0x14000934d  add     rcx, 120h
0x140009354  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140009359  mov     rcx, [rbx+118h]; string
0x140009360  call    cs:__imp_WindowsDeleteString
0x140009366  xor     edi, edi
0x140009368  mov     [rbx+118h], rdi
0x14000936f  mov     rcx, [rbx+110h]; string
0x140009376  call    cs:__imp_WindowsDeleteString
0x14000937c  lea     rcx, [rbx+100h]
0x140009383  mov     [rbx+110h], rdi
0x14000938a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14000938f  mov     rcx, [rbx+0F0h]; string
0x140009396  call    cs:__imp_WindowsDeleteString
0x14000939c  mov     [rbx+0F0h], rdi
0x1400093a3  mov     rcx, [rbx+0E8h]; string
0x1400093aa  call    cs:__imp_WindowsDeleteString
0x1400093b0  lea     rcx, [rbx+0D8h]
0x1400093b7  mov     [rbx+0E8h], rdi
0x1400093be  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400093c3  mov     rcx, [rbx+0D0h]
0x1400093ca  test    rcx, rcx
0x1400093cd  jz      short loc_1400093E2
0x1400093cf  mov     [rbx+0D0h], rdi
0x1400093d6  mov     rax, [rcx]
0x1400093d9  mov     rax, [rax+10h]
0x1400093dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400093e2  mov     rcx, [rbx+0C8h]
0x1400093e9  test    rcx, rcx
0x1400093ec  jz      short loc_140009401
0x1400093ee  mov     [rbx+0C8h], rdi
0x1400093f5  mov     rax, [rcx]
0x1400093f8  mov     rax, [rax+10h]
0x1400093fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009401  mov     rcx, [rbx+0C0h]
0x140009408  test    rcx, rcx
0x14000940b  jz      short loc_140009420
0x14000940d  mov     [rbx+0C0h], rdi
0x140009414  mov     rax, [rcx]
0x140009417  mov     rax, [rax+10h]
0x14000941b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009420  lea     rcx, [rbx+0B8h]
0x140009427  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14000942c  lea     rcx, [rbx+90h]
0x140009433  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140009438  mov     rcx, [rbx+88h]; string
0x14000943f  call    cs:__imp_WindowsDeleteString
0x140009445  mov     [rbx+88h], rdi
0x14000944c  mov     rcx, [rbx+70h]; string
0x140009450  call    cs:__imp_WindowsDeleteString
0x140009456  mov     [rbx+70h], rdi
0x14000945a  mov     rcx, [rbx+68h]; string
0x14000945e  call    cs:__imp_WindowsDeleteString
0x140009464  mov     [rbx+68h], rdi
0x140009468  mov     rcx, [rbx+60h]; string
0x14000946c  call    cs:__imp_WindowsDeleteString
0x140009472  mov     [rbx+60h], rdi
0x140009476  mov     rcx, [rbx+58h]; string
0x14000947a  call    cs:__imp_WindowsDeleteString
0x140009480  mov     [rbx+58h], rdi
0x140009484  mov     rcx, [rbx+50h]; string
0x140009488  call    cs:__imp_WindowsDeleteString
0x14000948e  mov     rcx, rbx
0x140009491  mov     [rbx+50h], rdi
0x140009495  mov     rbx, [rsp+28h+arg_0]
0x14000949a  add     rsp, 20h
0x14000949e  pop     rdi
0x14000949f  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UICredUXParameters@Controller@Credentials@UI@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::UI::Credentials::Controller::ICredUXParameters,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::UI::Credentials::Controller::ICredUXParameters,Microsoft::WRL::FtmBase>(void)
```
