# ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties(void)

- ea: `0x18006b23c`
- end: `0x18006b4ae`
- name: `??1ComClassRegistrationEntryProperties@@QEAA@XZ`
- size: `626`
- prototype: `void __fastcall(ComClassRegistrationEntryProperties *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006abf0`
- `0x180097054`
- `0x18014bbfc`
- `0x18019fdce`
- `0x1801a1c28`
- `0x1801a5f08`

## callees

- `0x180006970`
- `0x180163550`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b250`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b278`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b29e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b2b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b2d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b2ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b306`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b320`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b33a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b354`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b36e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b388`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b3ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b3d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b3ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b408`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b422`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b439`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b456`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b46a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b47e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b492`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b250`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b278`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b29e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b2b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b2d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b2ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b306`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b320`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b33a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b354`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b36e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b388`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b3ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b3d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b3ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b408`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b422`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b439`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b456`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b46a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b47e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b492`

## pseudocode

```c
void __fastcall ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties(HSTRING *this)
{
  WindowsDeleteString(this[67]);
  this[67] = 0;
  SecurityDescriptor::Release((SecurityDescriptor *)(this + 63));
  WindowsDeleteString(this[57]);
  this[57] = 0;
  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(this + 52);
  WindowsDeleteString(this[50]);
  this[50] = 0;
  WindowsDeleteString(this[48]);
  this[48] = 0;
  WindowsDeleteString(this[46]);
  this[46] = 0;
  WindowsDeleteString(this[44]);
  this[44] = 0;
  WindowsDeleteString(this[41]);
  this[41] = 0;
  WindowsDeleteString(this[39]);
  this[39] = 0;
  WindowsDeleteString(this[37]);
  this[37] = 0;
  WindowsDeleteString(this[35]);
  this[35] = 0;
  WindowsDeleteString(this[31]);
  this[31] = 0;
  WindowsDeleteString(this[29]);
  this[29] = 0;
  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(this + 27);
  WindowsDeleteString(this[26]);
  this[26] = 0;
  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(this + 24);
  WindowsDeleteString(this[23]);
  this[23] = 0;
  WindowsDeleteString(this[21]);
  this[21] = 0;
  WindowsDeleteString(this[19]);
  this[19] = 0;
  WindowsDeleteString(this[17]);
  this[17] = 0;
  WindowsDeleteString(this[15]);
  this[15] = 0;
  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(this + 10);
  WindowsDeleteString(this[8]);
  this[8] = 0;
  WindowsDeleteString(this[6]);
  this[6] = 0;
  WindowsDeleteString(this[4]);
  this[4] = 0;
  WindowsDeleteString(this[2]);
  this[2] = 0;
}

```

## disassembly

```asm
0x18006b23c  mov     [rsp+arg_0], rbx
0x18006b241  push    rdi
0x18006b242  sub     rsp, 20h
0x18006b246  mov     rbx, rcx
0x18006b249  mov     rcx, [rcx+218h]; string
0x18006b250  call    cs:__imp_WindowsDeleteString
0x18006b257  nop     dword ptr [rax+rax+00h]
0x18006b25c  xor     edi, edi
0x18006b25e  lea     rcx, [rbx+1F8h]; this
0x18006b265  mov     [rbx+218h], rdi
0x18006b26c  call    ?Release@SecurityDescriptor@@QEAAXXZ; SecurityDescriptor::Release(void)
0x18006b271  mov     rcx, [rbx+1C8h]; string
0x18006b278  call    cs:__imp_WindowsDeleteString
0x18006b27f  nop     dword ptr [rax+rax+00h]
0x18006b284  lea     rcx, [rbx+1A0h]
0x18006b28b  mov     [rbx+1C8h], rdi
0x18006b292  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x18006b297  mov     rcx, [rbx+190h]; string
0x18006b29e  call    cs:__imp_WindowsDeleteString
0x18006b2a5  nop     dword ptr [rax+rax+00h]
0x18006b2aa  mov     [rbx+190h], rdi
0x18006b2b1  mov     rcx, [rbx+180h]; string
0x18006b2b8  call    cs:__imp_WindowsDeleteString
0x18006b2bf  nop     dword ptr [rax+rax+00h]
0x18006b2c4  mov     [rbx+180h], rdi
0x18006b2cb  mov     rcx, [rbx+170h]; string
0x18006b2d2  call    cs:__imp_WindowsDeleteString
0x18006b2d9  nop     dword ptr [rax+rax+00h]
0x18006b2de  mov     [rbx+170h], rdi
0x18006b2e5  mov     rcx, [rbx+160h]; string
0x18006b2ec  call    cs:__imp_WindowsDeleteString
0x18006b2f3  nop     dword ptr [rax+rax+00h]
0x18006b2f8  mov     [rbx+160h], rdi
0x18006b2ff  mov     rcx, [rbx+148h]; string
0x18006b306  call    cs:__imp_WindowsDeleteString
0x18006b30d  nop     dword ptr [rax+rax+00h]
0x18006b312  mov     [rbx+148h], rdi
0x18006b319  mov     rcx, [rbx+138h]; string
0x18006b320  call    cs:__imp_WindowsDeleteString
0x18006b327  nop     dword ptr [rax+rax+00h]
0x18006b32c  mov     [rbx+138h], rdi
0x18006b333  mov     rcx, [rbx+128h]; string
0x18006b33a  call    cs:__imp_WindowsDeleteString
0x18006b341  nop     dword ptr [rax+rax+00h]
0x18006b346  mov     [rbx+128h], rdi
0x18006b34d  mov     rcx, [rbx+118h]; string
0x18006b354  call    cs:__imp_WindowsDeleteString
0x18006b35b  nop     dword ptr [rax+rax+00h]
0x18006b360  mov     [rbx+118h], rdi
0x18006b367  mov     rcx, [rbx+0F8h]; string
0x18006b36e  call    cs:__imp_WindowsDeleteString
0x18006b375  nop     dword ptr [rax+rax+00h]
0x18006b37a  mov     [rbx+0F8h], rdi
0x18006b381  mov     rcx, [rbx+0E8h]; string
0x18006b388  call    cs:__imp_WindowsDeleteString
0x18006b38f  nop     dword ptr [rax+rax+00h]
0x18006b394  lea     rcx, [rbx+0D8h]
0x18006b39b  mov     [rbx+0E8h], rdi
0x18006b3a2  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x18006b3a7  mov     rcx, [rbx+0D0h]; string
0x18006b3ae  call    cs:__imp_WindowsDeleteString
0x18006b3b5  nop     dword ptr [rax+rax+00h]
0x18006b3ba  lea     rcx, [rbx+0C0h]
0x18006b3c1  mov     [rbx+0D0h], rdi
0x18006b3c8  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x18006b3cd  mov     rcx, [rbx+0B8h]; string
0x18006b3d4  call    cs:__imp_WindowsDeleteString
0x18006b3db  nop     dword ptr [rax+rax+00h]
0x18006b3e0  mov     [rbx+0B8h], rdi
0x18006b3e7  mov     rcx, [rbx+0A8h]; string
0x18006b3ee  call    cs:__imp_WindowsDeleteString
0x18006b3f5  nop     dword ptr [rax+rax+00h]
0x18006b3fa  mov     [rbx+0A8h], rdi
0x18006b401  mov     rcx, [rbx+98h]; string
0x18006b408  call    cs:__imp_WindowsDeleteString
0x18006b40f  nop     dword ptr [rax+rax+00h]
0x18006b414  mov     [rbx+98h], rdi
0x18006b41b  mov     rcx, [rbx+88h]; string
0x18006b422  call    cs:__imp_WindowsDeleteString
0x18006b429  nop     dword ptr [rax+rax+00h]
0x18006b42e  mov     [rbx+88h], rdi
0x18006b435  mov     rcx, [rbx+78h]; string
0x18006b439  call    cs:__imp_WindowsDeleteString
0x18006b440  nop     dword ptr [rax+rax+00h]
0x18006b445  lea     rcx, [rbx+50h]
0x18006b449  mov     [rbx+78h], rdi
0x18006b44d  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x18006b452  mov     rcx, [rbx+40h]; string
0x18006b456  call    cs:__imp_WindowsDeleteString
0x18006b45d  nop     dword ptr [rax+rax+00h]
0x18006b462  mov     [rbx+40h], rdi
0x18006b466  mov     rcx, [rbx+30h]; string
0x18006b46a  call    cs:__imp_WindowsDeleteString
0x18006b471  nop     dword ptr [rax+rax+00h]
0x18006b476  mov     [rbx+30h], rdi
0x18006b47a  mov     rcx, [rbx+20h]; string
0x18006b47e  call    cs:__imp_WindowsDeleteString
0x18006b485  nop     dword ptr [rax+rax+00h]
0x18006b48a  mov     [rbx+20h], rdi
0x18006b48e  mov     rcx, [rbx+10h]; string
0x18006b492  call    cs:__imp_WindowsDeleteString
0x18006b499  nop     dword ptr [rax+rax+00h]
0x18006b49e  mov     [rbx+10h], rdi
0x18006b4a2  mov     rbx, [rsp+28h+arg_0]
0x18006b4a7  add     rsp, 20h
0x18006b4ab  pop     rdi
0x18006b4ac  retn
```
