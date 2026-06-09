# CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)

- ea: `0x180006ee0`
- end: `0x180006fcf`
- name: `?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z`
- size: `239`
- prototype: `HRESULT __fastcall(HWND, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180007a10`

## callees

- `0x18000518c`
- `0x180006ee0`
- `0x18000c990`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180006f3c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180006f3c`
- `ole32!CoGetObject` at `0x180006fa5`
- `ole32!CoGetObject` at `0x180006fa5`

## pseudocode

```c
HRESULT __fastcall CoCreateInstanceAsAdmin(HWND a1, const struct _GUID *a2, const struct _GUID *a3, void **a4)
{
  HRESULT result; // eax
  BIND_OPTS pBindOptions[3]; // [rsp+20h] [rbp-E0h] BYREF
  OLECHAR sz[56]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszName[304]; // [rsp+C0h] [rbp-40h] BYREF

  *a4 = 0;
  memset(pBindOptions, 0, sizeof(pBindOptions));
  if ( !StringFromGUID2(&CLSID_RemoveDeviceElevatedHandler, sz, 50) )
    return -2147024882;
  result = StringCchPrintfW(
             pszName,
             0x12Cu,
             L"Elevation:Administrator!new:%s",
             sz,
             *(_QWORD *)&pBindOptions[0].cbStruct,
             *(_QWORD *)&pBindOptions[0].grfMode,
             *(_OWORD *)&pBindOptions[1],
             *(_OWORD *)&pBindOptions[2]);
  if ( result >= 0 )
  {
    pBindOptions[0].cbStruct = 48;
    *(_QWORD *)&pBindOptions[2].grfMode = a1;
    pBindOptions[1].grfFlags = 4;
    *(_OWORD *)&pBindOptions[0].grfFlags = 0;
    *(_OWORD *)&pBindOptions[1].grfMode = 0;
    return CoGetObject(pszName, pBindOptions, &GUID_304fc8ab_6643_4daa_9027_4b21389dcb2d, a4);
  }
  return result;
}

```

## disassembly

```asm
0x180006ee0  mov     [rsp-8+arg_8], rbx
0x180006ee5  mov     [rsp-8+arg_10], rdi
0x180006eea  push    rbp
0x180006eeb  lea     rbp, [rsp-230h]
0x180006ef3  sub     rsp, 330h
0x180006efa  mov     rax, cs:__security_cookie
0x180006f01  xor     rax, rsp
0x180006f04  mov     [rbp+230h+var_10], rax
0x180006f0b  xorps   xmm0, xmm0
0x180006f0e  mov     qword ptr [r9], 0
0x180006f15  mov     rdi, rcx
0x180006f18  lea     rdx, [rsp+330h+sz]; lpsz
0x180006f1d  lea     rcx, CLSID_RemoveDeviceElevatedHandler; rguid
0x180006f24  mov     r8d, 32h ; '2'; cchMax
0x180006f2a  movups  xmmword ptr [rsp+330h+pBindOptions.cbStruct], xmm0
0x180006f2f  mov     rbx, r9
0x180006f32  movups  [rsp+330h+var_300], xmm0
0x180006f37  movups  [rsp+330h+var_2F0], xmm0
0x180006f3c  call    cs:__imp_StringFromGUID2
0x180006f42  test    eax, eax
0x180006f44  jnz     short loc_180006F4D
0x180006f46  mov     eax, 8007000Eh
0x180006f4b  jmp     short loc_180006FAB
0x180006f4d  lea     r9, [rsp+330h+sz]
0x180006f52  mov     edx, 12Ch; unsigned __int64
0x180006f57  lea     r8, aElevationAdmin; "Elevation:Administrator!new:%s"
0x180006f5e  lea     rcx, [rbp+230h+pszName]; unsigned __int16 *
0x180006f62  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006f67  test    eax, eax
0x180006f69  js      short loc_180006FAB
0x180006f6b  xorps   xmm0, xmm0
0x180006f6e  mov     [rsp+330h+pBindOptions.cbStruct], 30h ; '0'
0x180006f76  xorps   xmm1, xmm1
0x180006f79  mov     qword ptr [rsp+330h+var_2F0+8], rdi
0x180006f7e  mov     r9, rbx; ppv
0x180006f81  mov     dword ptr [rsp+330h+var_300+4], 4
0x180006f89  lea     r8, _GUID_304fc8ab_6643_4daa_9027_4b21389dcb2d; riid
0x180006f90  lea     rdx, [rsp+330h+pBindOptions]; pBindOptions
0x180006f95  lea     rcx, [rbp+230h+pszName]; pszName
0x180006f99  movdqu  xmmword ptr [rsp+330h+pBindOptions.grfFlags], xmm0
0x180006f9f  movdqu  [rsp+330h+var_300+8], xmm1
0x180006fa5  call    cs:__imp_CoGetObject
0x180006fab  mov     rcx, [rbp+230h+var_10]
0x180006fb2  xor     rcx, rsp; StackCookie
0x180006fb5  call    __security_check_cookie
0x180006fba  lea     r11, [rsp+330h+var_s0]
0x180006fc2  mov     rbx, [r11+18h]
0x180006fc6  mov     rdi, [r11+20h]
0x180006fca  mov     rsp, r11
0x180006fcd  pop     rbp
0x180006fce  retn
```
