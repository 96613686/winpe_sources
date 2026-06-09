# ElevateCompatibilityTab(HWND__ *)

- ea: `0x18000b4d0`
- end: `0x18000b64e`
- name: `?ElevateCompatibilityTab@@YAHPEAUHWND__@@@Z`
- size: `382`
- prototype: `_BOOL8 __fastcall(HWND)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000cb60`

## callees

- `0x18000893c`
- `0x18000b4d0`
- `0x18000d6e8`
- `0x180010a70`
- `0x180016280`
- `0x180017010`

## import_xrefs

- `USER32!GetWindowLongPtrW` at `0x18000b4fd`
- `USER32!GetWindowLongPtrW` at `0x18000b4fd`
- `ole32!CoGetObject` at `0x18000b5a5`
- `ole32!CoGetObject` at `0x18000b5a5`
- `ole32!StringFromGUID2` at `0x18000b532`
- `ole32!StringFromGUID2` at `0x18000b532`

## pseudocode

```c
_BOOL8 __fastcall ElevateCompatibilityTab(HWND a1)
{
  CLayerUIPropPage *WindowLongPtrW; // rsi
  HRESULT Object; // ebx
  void *ppv; // [rsp+40h] [rbp-C0h] BYREF
  BIND_OPTS pBindOptions[3]; // [rsp+48h] [rbp-B8h] BYREF
  OLECHAR sz[56]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t pszDest[304]; // [rsp+F0h] [rbp-10h] BYREF

  ppv = 0;
  WindowLongPtrW = (CLayerUIPropPage *)GetWindowLongPtrW(a1, -21);
  memset(pBindOptions, 0, sizeof(pBindOptions));
  if ( StringFromGUID2(&CLSID_ShimLayerPropertyPage, sz, 50) )
  {
    Object = StringCchPrintfW(pszDest, 0x12Cu, L"Elevation:Administrator!new:%s", sz);
    if ( Object < 0
      || (pBindOptions[0].cbStruct = 48,
          *(_QWORD *)&pBindOptions[2].grfMode = a1,
          pBindOptions[1].grfFlags = 4,
          *(_OWORD *)&pBindOptions[0].grfFlags = 0,
          *(_OWORD *)&pBindOptions[1].grfMode = 0,
          Object = CoGetObject(pszDest, pBindOptions, &GUID_d3075f87_a7bd_4231_9f6a_60c5e07374a7, &ppv),
          Object < 0) )
    {
      if ( Object == -2147023636 )
        TaskDialog(a1, g_hInstance, 0, (PCWSTR)0x1776, (PCWSTR)0x7E5, 32, (PCWSTR)0xFFFE, 0);
    }
    else
    {
      Object = (*(__int64 (__fastcall **)(void *, HWND, _QWORD))(*(_QWORD *)ppv + 24LL))(
                 ppv,
                 a1,
                 *((_QWORD *)WindowLongPtrW + 4));
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
      CLayerUIPropPage::OnRefresh(WindowLongPtrW, a1);
    }
  }
  else
  {
    Object = -2147024882;
  }
  return Object >= 0;
}

```

## disassembly

```asm
0x18000b4d0  push    rbp
0x18000b4d2  push    rbx
0x18000b4d3  push    rsi
0x18000b4d4  push    rdi
0x18000b4d5  lea     rbp, [rsp-268h]
0x18000b4dd  sub     rsp, 368h
0x18000b4e4  mov     rax, cs:__security_cookie
0x18000b4eb  xor     rax, rsp
0x18000b4ee  mov     [rbp+280h+var_30], rax
0x18000b4f5  mov     edx, 0FFFFFFEBh; nIndex
0x18000b4fa  mov     rdi, rcx
0x18000b4fd  call    cs:__imp_GetWindowLongPtrW
0x18000b503  xorps   xmm0, xmm0
0x18000b506  mov     [rsp+380h+ppv], 0
0x18000b50f  mov     r8d, 32h ; '2'; cchMax
0x18000b515  lea     rdx, [rbp+280h+sz]; lpsz
0x18000b519  lea     rcx, ?CLSID_ShimLayerPropertyPage@@3U_GUID@@B; rguid
0x18000b520  mov     rsi, rax
0x18000b523  movups  xmmword ptr [rsp+380h+pBindOptions.cbStruct], xmm0
0x18000b528  movups  [rsp+380h+var_328], xmm0
0x18000b52d  movups  [rsp+380h+var_318], xmm0
0x18000b532  call    cs:__imp_StringFromGUID2
0x18000b538  test    eax, eax
0x18000b53a  jnz     short loc_18000B546
0x18000b53c  mov     ebx, 8007000Eh
0x18000b541  jmp     loc_18000B62C
0x18000b546  lea     r9, [rbp+280h+sz]
0x18000b54a  mov     edx, 12Ch; cchDest
0x18000b54f  lea     r8, aElevationAdmin; "Elevation:Administrator!new:%s"
0x18000b556  lea     rcx, [rbp+280h+pszDest]; pszDest
0x18000b55a  call    StringCchPrintfW
0x18000b55f  mov     ebx, eax
0x18000b561  test    eax, eax
0x18000b563  js      loc_18000B5E9
0x18000b569  xorps   xmm0, xmm0
0x18000b56c  mov     [rsp+380h+pBindOptions.cbStruct], 30h ; '0'
0x18000b574  xorps   xmm1, xmm1
0x18000b577  mov     qword ptr [rsp+380h+var_318+8], rdi
0x18000b57c  lea     r9, [rsp+380h+ppv]; ppv
0x18000b581  mov     dword ptr [rsp+380h+var_328+4], 4
0x18000b589  lea     r8, _GUID_d3075f87_a7bd_4231_9f6a_60c5e07374a7; riid
0x18000b590  lea     rdx, [rsp+380h+pBindOptions]; pBindOptions
0x18000b595  lea     rcx, [rbp+280h+pszDest]; pszName
0x18000b599  movdqu  xmmword ptr [rsp+380h+pBindOptions.grfFlags], xmm0
0x18000b59f  movdqu  [rsp+380h+var_328+8], xmm1
0x18000b5a5  call    cs:__imp_CoGetObject
0x18000b5ab  mov     ebx, eax
0x18000b5ad  test    eax, eax
0x18000b5af  js      short loc_18000B5E9
0x18000b5b1  mov     rcx, [rsp+380h+ppv]
0x18000b5b6  mov     rdx, rdi
0x18000b5b9  mov     r8, [rsi+20h]
0x18000b5bd  mov     rax, [rcx]
0x18000b5c0  mov     rax, [rax+18h]
0x18000b5c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5c9  mov     rcx, [rsp+380h+ppv]
0x18000b5ce  mov     ebx, eax
0x18000b5d0  mov     r8, [rcx]
0x18000b5d3  mov     rax, [r8+10h]
0x18000b5d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5dc  mov     rdx, rdi; HWND
0x18000b5df  mov     rcx, rsi; this
0x18000b5e2  call    ?OnRefresh@CLayerUIPropPage@@QEAAXPEAUHWND__@@@Z; CLayerUIPropPage::OnRefresh(HWND__ *)
0x18000b5e7  jmp     short loc_18000B62C
0x18000b5e9  cmp     ebx, 800704ECh
0x18000b5ef  jnz     short loc_18000B62C
0x18000b5f1  mov     rdx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18000b5f8  mov     r9d, 1776h; pszMainInstruction
0x18000b5fe  mov     [rsp+380h+pnButton], 0; pnButton
0x18000b607  xor     r8d, r8d; pszWindowTitle
0x18000b60a  mov     [rsp+380h+pszIcon], 0FFFEh; pszIcon
0x18000b613  mov     rcx, rdi; hwndOwner
0x18000b616  mov     [rsp+380h+dwCommonButtons], 20h ; ' '; dwCommonButtons
0x18000b61e  mov     [rsp+380h+pszContent], 7E5h; pszContent
0x18000b627  call    TaskDialog
0x18000b62c  not     ebx
0x18000b62e  shr     ebx, 1Fh
0x18000b631  mov     eax, ebx
0x18000b633  mov     rcx, [rbp+280h+var_30]
0x18000b63a  xor     rcx, rsp; StackCookie
0x18000b63d  call    __security_check_cookie
0x18000b642  add     rsp, 368h
0x18000b649  pop     rdi
0x18000b64a  pop     rsi
0x18000b64b  pop     rbx
0x18000b64c  pop     rbp
0x18000b64d  retn
```
