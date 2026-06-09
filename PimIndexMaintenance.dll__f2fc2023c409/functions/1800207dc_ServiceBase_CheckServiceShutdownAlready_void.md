# ServiceBase::_CheckServiceShutdownAlready(void)

- ea: `0x1800207dc`
- end: `0x1800208a3`
- name: `?_CheckServiceShutdownAlready@ServiceBase@@AEAAJXZ`
- size: `199`
- prototype: `__int64 __fastcall(ServiceBase *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180020ab8`

## callees

- `0x180003edc`
- `0x1800207dc`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020872`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020883`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020892`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020872`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020883`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020892`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002084b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002084b`

## pseudocode

```c
__int64 __fastcall ServiceBase::_CheckServiceShutdownAlready(ServiceBase *this)
{
  const WCHAR *v1; // rbx
  HKEY *phkResult; // rax
  LSTATUS v4; // eax
  signed int v5; // ebx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  hKey = (HKEY)this;
  v1 = (const WCHAR *)(*(__int64 (__fastcall **)(void *))(myService + 88LL))(&myService);
  if ( !v1 )
  {
    (*(void (__fastcall **)(void *))(myService + 64LL))(&myService);
    return 0;
  }
  hKey = 0;
  phkResult = tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>(&hKey);
  v4 = RegOpenKeyExW(HKEY_CURRENT_USER, v1, 0, 0x20019u, phkResult);
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  if ( v5 == -2147024894 )
  {
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  if ( v5 >= 0 )
  {
    if ( hKey )
      RegCloseKey(hKey);
    return 2147943515LL;
  }
  else
  {
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v5;
  }
}

```

## disassembly

```asm
0x1800207dc  mov     [rsp+hKey], rcx
0x1800207e1  push    rbx
0x1800207e2  sub     rsp, 30h
0x1800207e6  mov     rax, cs:?myService@@3VPimIMService@@A; PimIMService myService
0x1800207ed  lea     rcx, ?myService@@3VPimIMService@@A; PimIMService myService
0x1800207f4  mov     rax, [rax+58h]
0x1800207f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800207fd  mov     rbx, rax
0x180020800  test    rax, rax
0x180020803  jnz     short loc_180020820
0x180020805  mov     rax, cs:?myService@@3VPimIMService@@A; PimIMService myService
0x18002080c  lea     rcx, ?myService@@3VPimIMService@@A; PimIMService myService
0x180020813  mov     rax, [rax+40h]
0x180020817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002081c  xor     eax, eax
0x18002081e  jmp     short loc_18002089D
0x180020820  lea     rcx, [rsp+38h+hKey]
0x180020825  mov     [rsp+38h+hKey], 0
0x18002082e  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x180020833  mov     r9d, 20019h; samDesired
0x180020839  mov     [rsp+38h+phkResult], rax; phkResult
0x18002083e  xor     r8d, r8d; ulOptions
0x180020841  mov     rdx, rbx; lpSubKey
0x180020844  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002084b  call    cs:__imp_RegOpenKeyExW
0x180020851  mov     ebx, eax
0x180020853  test    eax, eax
0x180020855  jle     short loc_180020860
0x180020857  movzx   ebx, ax
0x18002085a  or      ebx, 80070000h
0x180020860  mov     rcx, [rsp+38h+hKey]; hKey
0x180020865  cmp     ebx, 80070002h
0x18002086b  jnz     short loc_18002087A
0x18002086d  test    rcx, rcx
0x180020870  jz      short loc_18002081C
0x180020872  call    cs:__imp_RegCloseKey
0x180020878  jmp     short loc_18002081C
0x18002087a  test    ebx, ebx
0x18002087c  jns     short loc_18002088D
0x18002087e  test    rcx, rcx
0x180020881  jz      short loc_180020889
0x180020883  call    cs:__imp_RegCloseKey
0x180020889  mov     eax, ebx
0x18002088b  jmp     short loc_18002089D
0x18002088d  test    rcx, rcx
0x180020890  jz      short loc_180020898
0x180020892  call    cs:__imp_RegCloseKey
0x180020898  mov     eax, 8007045Bh
0x18002089d  add     rsp, 30h
0x1800208a1  pop     rbx
0x1800208a2  retn
```
