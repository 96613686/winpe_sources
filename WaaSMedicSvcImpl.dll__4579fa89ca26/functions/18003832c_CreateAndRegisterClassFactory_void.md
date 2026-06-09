# CreateAndRegisterClassFactory(void)

- ea: `0x18003832c`
- end: `0x1800383ef`
- name: `?CreateAndRegisterClassFactory@@YAJXZ`
- size: `195`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180038ce0`

## callees

- `0x18002e81c`
- `0x18003832c`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800383c4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800383c4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180038352`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180038352`

## string_xrefs

- `0x18003835e`: `Failed to create instance of Context Switcher. hr = 0x%08x`
- `0x1800383d1`: `Failed to get COM registration callback within the given timeout`

## pseudocode

```c
__int64 CreateAndRegisterClassFactory(void)
{
  HRESULT Instance; // eax
  unsigned int v1; // ebx
  int v2; // eax

  Instance = CoCreateInstance(
               &CLSID_ContextSwitcher,
               0,
               1u,
               &GUID_000001da_0000_0000_c000_000000000046,
               &g_contextCallback);
  v1 = Instance;
  if ( Instance >= 0 )
  {
    v2 = (*(__int64 (__fastcall **)(LPVOID, __int64 (__fastcall *)(struct tagComCallData *), _QWORD, GUID *, int, _QWORD))(*(_QWORD *)g_contextCallback + 24LL))(
           g_contextCallback,
           ConnectCallback,
           0,
           &GUID_000001da_0000_0000_c000_000000000046,
           5,
           0);
    v1 = v2;
    if ( v2 >= 0 )
    {
      if ( WaitForSingleObject(hEvent, 0x1388u) == 258 )
      {
        v1 = -2147418113;
        LogLevelW(2u, L"Failed to get COM registration callback within the given timeout");
      }
    }
    else
    {
      LogLevelW(2u, L"Failed to invoke ContextCallback on the context interface. hr = 0x%08x", (unsigned int)v2);
    }
  }
  else
  {
    LogLevelW(2u, L"Failed to create instance of Context Switcher. hr = 0x%08x", (unsigned int)Instance);
  }
  return v1;
}

```

## disassembly

```asm
0x18003832c  push    rbx
0x18003832e  sub     rsp, 40h
0x180038332  xor     edx, edx; pUnkOuter
0x180038334  lea     rax, ?g_contextCallback@@3PEAUIContextCallback@@EA; IContextCallback * g_contextCallback
0x18003833b  lea     r9, _GUID_000001da_0000_0000_c000_000000000046; riid
0x180038342  mov     [rsp+48h+ppv], rax; ppv
0x180038347  lea     rcx, CLSID_ContextSwitcher; rclsid
0x18003834e  lea     r8d, [rdx+1]; dwClsContext
0x180038352  call    cs:__imp_CoCreateInstance
0x180038358  mov     ebx, eax
0x18003835a  test    eax, eax
0x18003835c  jns     short loc_180038374
0x18003835e  lea     rdx, aFailedToCreate_19; "Failed to create instance of Context Sw"...
0x180038365  mov     r8d, eax
0x180038368  mov     ecx, 2; unsigned __int8
0x18003836d  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180038372  jmp     short loc_1800383E7
0x180038374  mov     rcx, cs:?g_contextCallback@@3PEAUIContextCallback@@EA; IContextCallback * g_contextCallback
0x18003837b  lea     r9, _GUID_000001da_0000_0000_c000_000000000046
0x180038382  mov     [rsp+48h+var_20], 0
0x18003838b  lea     rdx, ?ConnectCallback@@YAJPEAUtagComCallData@@@Z; ConnectCallback(tagComCallData *)
0x180038392  xor     r8d, r8d
0x180038395  mov     dword ptr [rsp+48h+ppv], 5
0x18003839d  mov     rax, [rcx]
0x1800383a0  mov     rax, [rax+18h]
0x1800383a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800383a9  mov     ebx, eax
0x1800383ab  test    eax, eax
0x1800383ad  jns     short loc_1800383B8
0x1800383af  lea     rdx, aFailedToInvoke; "Failed to invoke ContextCallback on the"...
0x1800383b6  jmp     short loc_180038365
0x1800383b8  mov     rcx, cs:hEvent; hHandle
0x1800383bf  mov     edx, 1388h; dwMilliseconds
0x1800383c4  call    cs:__imp_WaitForSingleObject
0x1800383ca  cmp     eax, 102h
0x1800383cf  jnz     short loc_1800383E7
0x1800383d1  lea     rdx, aFailedToGetCom; "Failed to get COM registration callback"...
0x1800383d8  mov     ecx, 2; unsigned __int8
0x1800383dd  mov     ebx, 8000FFFFh
0x1800383e2  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800383e7  mov     eax, ebx
0x1800383e9  add     rsp, 40h
0x1800383ed  pop     rbx
0x1800383ee  retn
```
