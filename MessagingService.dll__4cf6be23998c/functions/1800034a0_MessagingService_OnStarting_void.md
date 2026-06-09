# MessagingService::OnStarting(void)

- ea: `0x1800034a0`
- end: `0x1800034ec`
- name: `?OnStarting@MessagingService@@UEAAJXZ`
- size: `76`
- prototype: `__int64 __fastcall(MessagingService *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000307c`
- `0x1800034a0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800034d5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800034d5`
- `iertutil!__imp_?UseEdgeBrowserComponentsForProcess@@YAJXZ` at `0x1800034a6`
- `iertutil!__imp_?UseEdgeBrowserComponentsForProcess@@YAJXZ` at `0x1800034a6`

## string_xrefs

- `0x1800034ca`: `MessagingService.dll`
- `0x1800034b8`: `onecoreuap\net\messaging\desktoptransport\service\messagingservice.cpp`

## pseudocode

```c
__int64 __fastcall MessagingService::OnStarting(MessagingService *this)
{
  int v1; // eax
  __int64 v2; // rdx
  unsigned int v3; // ebx

  v1 = UseEdgeBrowserComponentsForProcess();
  v3 = v1;
  if ( v1 >= 0 )
  {
    g_dllResource = LoadLibraryExW(L"MessagingService.dll", 0, 2u);
    return 0;
  }
  else
  {
    Log_HREvent((unsigned int)v1, v2, "onecoreuap\\net\\messaging\\desktoptransport\\service\\messagingservice.cpp", 37);
  }
  return v3;
}

```

## disassembly

```asm
0x1800034a0  push    rbx
0x1800034a2  sub     rsp, 30h
0x1800034a6  call    cs:__imp_?UseEdgeBrowserComponentsForProcess@@YAJXZ; UseEdgeBrowserComponentsForProcess(void)
0x1800034ac  mov     ebx, eax
0x1800034ae  test    eax, eax
0x1800034b0  jns     short loc_1800034C8
0x1800034b2  mov     r9d, 25h ; '%'
0x1800034b8  lea     r8, aOnecoreuapNetM_7; "onecoreuap\\net\\messaging\\desktoptran"...
0x1800034bf  mov     ecx, eax
0x1800034c1  call    Log_HREvent
0x1800034c6  jmp     short loc_1800034E4
0x1800034c8  xor     edx, edx; hFile
0x1800034ca  lea     rcx, LibFileName; "MessagingService.dll"
0x1800034d1  lea     r8d, [rdx+2]; dwFlags
0x1800034d5  call    cs:__imp_LoadLibraryExW
0x1800034db  mov     cs:?g_dllResource@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_dllResource
0x1800034e2  xor     ebx, ebx
0x1800034e4  mov     eax, ebx
0x1800034e6  add     rsp, 30h
0x1800034ea  pop     rbx
0x1800034eb  retn
```
