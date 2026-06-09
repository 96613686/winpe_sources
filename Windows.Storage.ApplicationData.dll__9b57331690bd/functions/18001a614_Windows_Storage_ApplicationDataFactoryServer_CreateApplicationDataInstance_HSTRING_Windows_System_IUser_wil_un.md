# Windows::Storage::ApplicationDataFactoryServer::CreateApplicationDataInstance(HSTRING__ *,Windows::System::IUser *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&,Windows::Storage::IApplicationData * *)

- ea: `0x18001a614`
- end: `0x18001a74b`
- name: `?CreateApplicationDataInstance@ApplicationDataFactoryServer@Storage@Windows@@CAJPEAUHSTRING__@@PEAUIUser@System@3@$$QEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAPEAUIApplicationData@23@@Z`
- size: `311`
- prototype: `__int64 __fastcall(HSTRING userSid, Windows::System::IUser *userParam, wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (__cdecl*)(void *),&CloseHandle> > > *token, Windows::Storage::IApplicationData **value)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001e9b4`
- `0x18003f264`

## callees

- `0x180009778`
- `0x18001a614`
- `0x18001ed7c`
- `0x180021efc`
- `0x180041620`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001a71a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001a71a`

## pseudocode

```c

```
