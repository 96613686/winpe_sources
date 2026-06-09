# CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)

- ea: `0x1400097c0`
- end: `0x1400098a7`
- name: `?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z`
- size: `231`
- prototype: `HRESULT __fastcall(HWND, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400098b0`

## callees

- `0x1400016a0`
- `0x140005740`
- `0x1400097c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140009814`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140009814`
- `ole32!CoGetObject` at `0x140009881`
- `ole32!CoGetObject` at `0x140009881`

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
  if ( !StringFromGUID2(&CLSID_TpmVirtualSmartCardManager, sz, 50) )
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
    pBindOptions[1].grfFlags = 4;
    *(_OWORD *)&pBindOptions[0].grfFlags = 0;
    memset(&pBindOptions[1].grfMode, 0, 24);
    return CoGetObject(pszName, pBindOptions, &IID_ITpmVirtualSmartCardManager3, a4);
  }
  return result;
}

```

## disassembly

```asm
0x1400097c0  mov     [rsp-8+arg_0], rbx
0x1400097c5  push    rbp
0x1400097c6  lea     rbp, [rsp-230h]
0x1400097ce  sub     rsp, 330h
0x1400097d5  mov     rax, cs:__security_cookie
0x1400097dc  xor     rax, rsp
0x1400097df  mov     [rbp+230h+var_10], rax
0x1400097e6  xorps   xmm0, xmm0
0x1400097e9  mov     qword ptr [r9], 0
0x1400097f0  mov     r8d, 32h ; '2'; cchMax
0x1400097f6  lea     rdx, [rsp+330h+sz]; lpsz
0x1400097fb  lea     rcx, CLSID_TpmVirtualSmartCardManager; rguid
0x140009802  mov     rbx, r9
0x140009805  movups  xmmword ptr [rsp+330h+pBindOptions.cbStruct], xmm0
0x14000980a  movups  [rsp+330h+var_300], xmm0
0x14000980f  movups  [rsp+330h+var_2F0], xmm0
0x140009814  call    cs:__imp_StringFromGUID2
0x14000981a  test    eax, eax
0x14000981c  jnz     short loc_140009825
0x14000981e  mov     eax, 8007000Eh
0x140009823  jmp     short loc_140009887
0x140009825  lea     r9, [rsp+330h+sz]
0x14000982a  mov     edx, 12Ch; unsigned __int64
0x14000982f  lea     r8, aElevationAdmin; "Elevation:Administrator!new:%s"
0x140009836  lea     rcx, [rbp+230h+pszName]; unsigned __int16 *
0x14000983a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000983f  test    eax, eax
0x140009841  js      short loc_140009887
0x140009843  xorps   xmm0, xmm0
0x140009846  mov     [rsp+330h+pBindOptions.cbStruct], 30h ; '0'
0x14000984e  xorps   xmm1, xmm1
0x140009851  mov     qword ptr [rsp+330h+var_2F0+8], 0
0x14000985a  mov     r9, rbx; ppv
0x14000985d  mov     dword ptr [rsp+330h+var_300+4], 4
0x140009865  lea     r8, IID_ITpmVirtualSmartCardManager3; riid
0x14000986c  lea     rdx, [rsp+330h+pBindOptions]; pBindOptions
0x140009871  lea     rcx, [rbp+230h+pszName]; pszName
0x140009875  movdqu  xmmword ptr [rsp+330h+pBindOptions.grfFlags], xmm0
0x14000987b  movdqu  [rsp+330h+var_300+8], xmm1
0x140009881  call    cs:__imp_CoGetObject
0x140009887  mov     rcx, [rbp+230h+var_10]
0x14000988e  xor     rcx, rsp; StackCookie
0x140009891  call    __security_check_cookie
0x140009896  mov     rbx, [rsp+330h+arg_0]
0x14000989e  add     rsp, 330h
0x1400098a5  pop     rbp
0x1400098a6  retn
```
