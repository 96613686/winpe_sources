# CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)

- ea: `0x180008428`
- end: `0x180008517`
- name: `?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z`
- size: `239`
- prototype: `int(HWND, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008d48`
- `0x180009388`

## callees

- `0x180007b10`
- `0x180008428`
- `0x18000a9d0`

## import_xrefs

- `ole32!CoGetObject` at `0x1800084ed`
- `ole32!CoGetObject` at `0x1800084ed`
- `ole32!StringFromGUID2` at `0x180008484`
- `ole32!StringFromGUID2` at `0x180008484`

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
  if ( !StringFromGUID2(&CLSID_DfsShellAdmin, sz, 50) )
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
    return CoGetObject(pszName, pBindOptions, &IID_IDfsShellAdmin, a4);
  }
  return result;
}

```

## disassembly

```asm
0x180008428  mov     [rsp-8+arg_8], rbx
0x18000842d  mov     [rsp-8+arg_10], rdi
0x180008432  push    rbp
0x180008433  lea     rbp, [rsp-230h]
0x18000843b  sub     rsp, 330h
0x180008442  mov     rax, cs:__security_cookie
0x180008449  xor     rax, rsp
0x18000844c  mov     [rbp+230h+var_10], rax
0x180008453  xorps   xmm0, xmm0
0x180008456  mov     qword ptr [r9], 0
0x18000845d  mov     rdi, rcx
0x180008460  lea     rdx, [rsp+330h+sz]; lpsz
0x180008465  lea     rcx, CLSID_DfsShellAdmin; rguid
0x18000846c  mov     r8d, 32h ; '2'; cchMax
0x180008472  movups  xmmword ptr [rsp+330h+pBindOptions.cbStruct], xmm0
0x180008477  mov     rbx, r9
0x18000847a  movups  [rsp+330h+var_300], xmm0
0x18000847f  movups  [rsp+330h+var_2F0], xmm0
0x180008484  call    cs:__imp_StringFromGUID2
0x18000848a  test    eax, eax
0x18000848c  jnz     short loc_180008495
0x18000848e  mov     eax, 8007000Eh
0x180008493  jmp     short loc_1800084F3
0x180008495  lea     r9, [rsp+330h+sz]
0x18000849a  mov     edx, 12Ch; unsigned __int64
0x18000849f  lea     r8, aElevationAdmin; "Elevation:Administrator!new:%s"
0x1800084a6  lea     rcx, [rbp+230h+pszName]; unsigned __int16 *
0x1800084aa  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800084af  test    eax, eax
0x1800084b1  js      short loc_1800084F3
0x1800084b3  xorps   xmm0, xmm0
0x1800084b6  mov     [rsp+330h+pBindOptions.cbStruct], 30h ; '0'
0x1800084be  xorps   xmm1, xmm1
0x1800084c1  mov     qword ptr [rsp+330h+var_2F0+8], rdi
0x1800084c6  mov     r9, rbx; ppv
0x1800084c9  mov     dword ptr [rsp+330h+var_300+4], 4
0x1800084d1  lea     r8, IID_IDfsShellAdmin; riid
0x1800084d8  lea     rdx, [rsp+330h+pBindOptions]; pBindOptions
0x1800084dd  lea     rcx, [rbp+230h+pszName]; pszName
0x1800084e1  movdqu  xmmword ptr [rsp+330h+pBindOptions.grfFlags], xmm0
0x1800084e7  movdqu  [rsp+330h+var_300+8], xmm1
0x1800084ed  call    cs:__imp_CoGetObject
0x1800084f3  mov     rcx, [rbp+230h+var_10]
0x1800084fa  xor     rcx, rsp; StackCookie
0x1800084fd  call    __security_check_cookie
0x180008502  lea     r11, [rsp+330h+var_s0]
0x18000850a  mov     rbx, [r11+18h]
0x18000850e  mov     rdi, [r11+20h]
0x180008512  mov     rsp, r11
0x180008515  pop     rbp
0x180008516  retn
```
