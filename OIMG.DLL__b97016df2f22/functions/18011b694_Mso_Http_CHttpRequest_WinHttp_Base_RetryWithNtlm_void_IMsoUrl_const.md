# Mso::Http::CHttpRequest_WinHttp_Base::RetryWithNtlm(void *,IMsoUrl const &)

- ea: `0x18011b694`
- end: `0x18011bcf3`
- name: `?RetryWithNtlm@CHttpRequest_WinHttp_Base@Http@Mso@@IEAAXPEAXAEBUIMsoUrl@@@Z`
- size: `1631`
- prototype: `void(Mso::Http::CHttpRequest_WinHttp_Base *__hidden this, void *, const struct IMsoUrl *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18011e724`

## callees

- `0x180012ccc`
- `0x180016ee8`
- `0x1800a17ec`
- `0x18011b694`
- `0x180124e64`
- `0x18015c2ac`
- `0x18015c6cc`
- `0x18056bd00`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18011b9cc`
- `KERNEL32!GetLastError` at `0x18011baa6`
- `KERNEL32!GetLastError` at `0x18011bb8e`
- `KERNEL32!GetLastError` at `0x18011b9cc`
- `KERNEL32!GetLastError` at `0x18011baa6`
- `KERNEL32!GetLastError` at `0x18011bb8e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18011b8ab`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18011b8fa`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18011b940`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18011b99c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18011bc5d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18011bcbe`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18011b8ab`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18011b8fa`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18011b940`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18011b99c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18011bc5d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18011bcbe`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18011b995`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18011ba6d`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18011bb47`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18011bcb7`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18011b995`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18011ba6d`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18011bb47`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18011bcb7`
- `WINHTTP!WinHttpSetCredentials` at `0x18011ba8c`
- `WINHTTP!WinHttpSetCredentials` at `0x18011ba8c`
- `WINHTTP!WinHttpQueryAuthSchemes` at `0x18011b6fd`
- `WINHTTP!WinHttpQueryAuthSchemes` at `0x18011b6fd`
- `WINHTTP!WinHttpSetOption` at `0x18011b9b2`
- `WINHTTP!WinHttpSetOption` at `0x18011b9b2`

## string_xrefs

- `0x18011bbf6`: `Failed to perform WinHttpQueryAuthSchemes on the request. Skipping retry attempt`
- `0x18011bb4e`: `NTLM is not supported. Skipping retry attempt`

## pseudocode

```c

```
