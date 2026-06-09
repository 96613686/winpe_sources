# InstalledClassicAppInfoServer::~InstalledClassicAppInfoServer(void)

- ea: `0x180040640`
- end: `0x18004067a`
- name: `??1InstalledClassicAppInfoServer@@UEAA@XZ`
- size: `58`
- prototype: `void __fastcall(InstalledClassicAppInfoServer *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180040770`

## callees

- `0x180040594`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004064d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004065f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004064d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004065f`

## pseudocode

```c
void __fastcall InstalledClassicAppInfoServer::~InstalledClassicAppInfoServer(HSTRING *this)
{
  WindowsDeleteString(this[9]);
  this[9] = 0;
  WindowsDeleteString(this[8]);
  this[8] = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Management::Deployment::Preview::IInstalledClassicAppInfo,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Management::Deployment::Preview::IInstalledClassicAppInfo,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x180040640  push    rbx
0x180040642  sub     rsp, 20h
0x180040646  mov     rbx, rcx
0x180040649  mov     rcx, [rcx+48h]; string
0x18004064d  call    cs:__imp_WindowsDeleteString
0x180040653  mov     qword ptr [rbx+48h], 0
0x18004065b  mov     rcx, [rbx+40h]; string
0x18004065f  call    cs:__imp_WindowsDeleteString
0x180040665  mov     rcx, rbx
0x180040668  mov     qword ptr [rbx+40h], 0
0x180040670  add     rsp, 20h
0x180040674  pop     rbx
0x180040675  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIInstalledClassicAppInfo@Preview@Deployment@Management@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Management::Deployment::Preview::IInstalledClassicAppInfo,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Management::Deployment::Preview::IInstalledClassicAppInfo,Microsoft::WRL::FtmBase>(void)
```
