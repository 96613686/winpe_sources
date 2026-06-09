# DllMain

- ea: `0x18007a2bc`
- end: `0x18007a3f4`
- name: `DllMain`
- size: `312`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18004d774`
- `0x18007a2bc`

## callees

- `0x1800012e4`
- `0x180023560`
- `0x180023634`
- `0x1800239bc`
- `0x180030b44`
- `0x180037c20`
- `0x180049270`
- `0x18007a2bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18007a351`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18007a351`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18007a2e9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18007a3b0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18007a2e9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18007a3b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18007a30e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18007a30e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18007a330`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18007a330`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18007a3e1`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18007a3e1`
- `ext-ms-win-ole32-oleautomation-l1-1-0!SetOleautModule` at `0x18007a31c`
- `ext-ms-win-ole32-oleautomation-l1-1-0!SetOleautModule` at `0x18007a31c`

## string_xrefs

- `0x18007a307`: `ext-ms-win-ole32-oleautomation-l1-1-0.dll`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  BOOL v4; // ebx
  __int64 v5; // rdx
  UINT SystemDirectoryW; // eax
  REGHANDLE v8; // rcx
  void *v9; // [rsp+48h] [rbp+20h] BYREF

  v4 = 1;
  if ( fdwReason )
  {
    v5 = fdwReason - 1;
    if ( (_DWORD)v5 )
    {
      if ( (_DWORD)v5 == 2 )
      {
        if ( TlsGetValue(g_itlsAppData) )
          ReleaseAppData();
      }
    }
    else
    {
      TraceLoggingRegisterEx_EventRegister_EventSetInformation(hinstDLL, v5, lpvReserved);
      if ( GetModuleHandleW(L"ext-ms-win-ole32-oleautomation-l1-1-0.dll") )
        SetOleautModule(hinstDLL);
      SystemDirectoryW = GetSystemDirectoryW(&g_rcSystemDirectory, 0x104u);
      if ( !SystemDirectoryW || SystemDirectoryW + 2 > 0x104 )
        return 0;
      _o_wcscat_s(&g_rcSystemDirectory, 260, L"\\");
      InitMbString();
      v4 = InitProcessData() >= 0;
      GetWrapperPSFactory_Imp();
      CStubRecordInfoCF::QueryInterface((CStubRecordInfoCF *)off_1800C26D0, &IID_IUnknown, &v9);
      if ( !v4 )
        DllMain(hinstDLL, 0, 0);
    }
  }
  else
  {
    g_bProcessShutdown = lpvReserved != 0;
    if ( TlsGetValue(g_itlsAppData) )
      ReleaseAppData();
    ReleaseProcessData();
    v8 = RegHandle;
    dword_1800C2698 = 0;
    RegHandle = 0;
    EventUnregister(v8);
  }
  return v4;
}

```

## disassembly

```asm
0x18007a2bc  mov     [rsp+arg_0], rbx
0x18007a2c1  push    rdi
0x18007a2c2  sub     rsp, 20h
0x18007a2c6  mov     rdi, rcx
0x18007a2c9  mov     ebx, 1
0x18007a2ce  test    edx, edx
0x18007a2d0  jz      loc_18007A39C
0x18007a2d6  sub     edx, ebx
0x18007a2d8  jz      short loc_18007A302
0x18007a2da  cmp     edx, 2
0x18007a2dd  jnz     loc_18007A3E7
0x18007a2e3  mov     ecx, cs:?g_itlsAppData@@3KA; dwTlsIndex
0x18007a2e9  call    cs:__imp_TlsGetValue
0x18007a2ef  test    rax, rax
0x18007a2f2  jz      loc_18007A3E7
0x18007a2f8  call    ?ReleaseAppData@@YAXXZ; ReleaseAppData(void)
0x18007a2fd  jmp     loc_18007A3E7
0x18007a302  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18007a307  lea     rcx, aExtMsWinOle32O_0; "ext-ms-win-ole32-oleautomation-l1-1-0.d"...
0x18007a30e  call    cs:__imp_GetModuleHandleW
0x18007a314  test    rax, rax
0x18007a317  jz      short loc_18007A322
0x18007a319  mov     rcx, rdi
0x18007a31c  call    cs:__imp_SetOleautModule
0x18007a322  mov     ebx, 104h
0x18007a327  lea     rcx, g_rcSystemDirectory; lpBuffer
0x18007a32e  mov     edx, ebx; uSize
0x18007a330  call    cs:__imp_GetSystemDirectoryW
0x18007a336  test    eax, eax
0x18007a338  jz      short loc_18007A398
0x18007a33a  add     eax, 2
0x18007a33d  cmp     eax, ebx
0x18007a33f  ja      short loc_18007A398
0x18007a341  lea     r8, asc_1800B2C30; "\\"
0x18007a348  mov     edx, ebx
0x18007a34a  lea     rcx, g_rcSystemDirectory
0x18007a351  call    cs:__imp__o_wcscat_s
0x18007a357  call    InitMbString
0x18007a35c  call    ?InitProcessData@@YAJXZ; InitProcessData(void)
0x18007a361  mov     ebx, eax
0x18007a363  not     ebx
0x18007a365  shr     ebx, 1Fh
0x18007a368  call    GetWrapperPSFactory_Imp
0x18007a36d  lea     r8, [rsp+28h+arg_18]; void **
0x18007a372  lea     rdx, IID_IUnknown; struct _GUID *
0x18007a379  lea     rcx, off_1800C26D0; this
0x18007a380  call    ?QueryInterface@CStubRecordInfoCF@@UEAAJAEBU_GUID@@PEAPEAX@Z; CStubRecordInfoCF::QueryInterface(_GUID const &,void * *)
0x18007a385  test    ebx, ebx
0x18007a387  jnz     short loc_18007A3E7
0x18007a389  xor     r8d, r8d; lpvReserved
0x18007a38c  xor     edx, edx; fdwReason
0x18007a38e  mov     rcx, rdi; hinstDLL
0x18007a391  call    DllMain
0x18007a396  jmp     short loc_18007A3E7
0x18007a398  xor     eax, eax
0x18007a39a  jmp     short loc_18007A3E9
0x18007a39c  mov     ecx, cs:?g_itlsAppData@@3KA; dwTlsIndex
0x18007a3a2  xor     eax, eax
0x18007a3a4  test    r8, r8
0x18007a3a7  setnz   al
0x18007a3aa  mov     cs:?g_bProcessShutdown@@3HA, eax; int g_bProcessShutdown
0x18007a3b0  call    cs:__imp_TlsGetValue
0x18007a3b6  test    rax, rax
0x18007a3b9  jz      short loc_18007A3C0
0x18007a3bb  call    ?ReleaseAppData@@YAXXZ; ReleaseAppData(void)
0x18007a3c0  call    ?ReleaseProcessData@@YAXXZ; ReleaseProcessData(void)
0x18007a3c5  mov     rcx, cs:RegHandle; RegHandle
0x18007a3cc  mov     cs:dword_1800C2698, 0
0x18007a3d6  mov     cs:RegHandle, 0
0x18007a3e1  call    cs:__imp_EventUnregister
0x18007a3e7  mov     eax, ebx
0x18007a3e9  mov     rbx, [rsp+28h+arg_0]
0x18007a3ee  add     rsp, 20h
0x18007a3f2  pop     rdi
0x18007a3f3  retn
```
