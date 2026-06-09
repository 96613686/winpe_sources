# ProcessNameCache::ProcessNameCache(void)

- ea: `0x180127358`
- end: `0x1801273cf`
- name: `??0ProcessNameCache@@AEAA@XZ`
- size: `119`
- prototype: `ProcessNameCache *__fastcall(ProcessNameCache *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800a12f4`

## callees

- `0x1800320d4`
- `0x180120c94`
- `0x180127358`

## import_xrefs

- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1801273b3`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1801273b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180127375`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180127375`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180127385`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180127385`

## pseudocode

```c
ProcessNameCache *__fastcall ProcessNameCache::ProcessNameCache(ProcessNameCache *this)
{
  DWORD CurrentProcessId; // eax
  char *v2; // rax
  ProcessNameCache *dwSize; // [rsp+30h] [rbp+8h] BYREF
  char *v5; // [rsp+38h] [rbp+10h] BYREF

  dwSize = this;
  memset_0(&`ProcessNameCache::GetInstance'::`2'::s_processNameCache, 0, 0x208u);
  CurrentProcessId = GetCurrentProcessId();
  v2 = (char *)OpenProcess(0x1000u, 0, CurrentProcessId);
  v5 = v2;
  if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    LODWORD(dwSize) = 260;
    QueryFullProcessImageNameW(v2, 0, &`ProcessNameCache::GetInstance'::`2'::s_processNameCache, (PDWORD)&dwSize);
  }
  std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,bool>::~pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,bool>(&v5);
  return (ProcessNameCache *)&`ProcessNameCache::GetInstance'::`2'::s_processNameCache;
}

```

## disassembly

```asm
0x180127358  mov     [rsp+dwSize], rcx
0x18012735d  sub     rsp, 28h
0x180127361  xor     edx, edx; Val
0x180127363  lea     rcx, ?s_processNameCache@?1??GetInstance@ProcessNameCache@@SAAEBV2@XZ@4V2@A; void *
0x18012736a  mov     r8d, 208h; Size
0x180127370  call    memset_0
0x180127375  call    cs:__imp_GetCurrentProcessId
0x18012737b  xor     edx, edx; bInheritHandle
0x18012737d  mov     ecx, 1000h; dwDesiredAccess
0x180127382  mov     r8d, eax; dwProcessId
0x180127385  call    cs:__imp_OpenProcess
0x18012738b  mov     [rsp+28h+arg_8], rax
0x180127390  lea     rcx, [rax-1]
0x180127394  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180127398  ja      short loc_1801273B9
0x18012739a  lea     r9, [rsp+28h+dwSize]; lpdwSize
0x18012739f  mov     dword ptr [rsp+28h+dwSize], 104h
0x1801273a7  lea     r8, ?s_processNameCache@?1??GetInstance@ProcessNameCache@@SAAEBV2@XZ@4V2@A; lpExeName
0x1801273ae  xor     edx, edx; dwFlags
0x1801273b0  mov     rcx, rax; hProcess
0x1801273b3  call    cs:__imp_QueryFullProcessImageNameW
0x1801273b9  lea     rcx, [rsp+28h+arg_8]
0x1801273be  call    ??1?$pair@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@_N@std@@QEAA@XZ; std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,bool>::~pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,bool>(void)
0x1801273c3  lea     rax, ?s_processNameCache@?1??GetInstance@ProcessNameCache@@SAAEBV2@XZ@4V2@A; ProcessNameCache `ProcessNameCache::GetInstance(void)'::`2'::s_processNameCache
0x1801273ca  add     rsp, 28h
0x1801273ce  retn
```
