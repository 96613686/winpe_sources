# _CopyCurrentHistoryItemToStream(IStream *)

- ea: `0x1800c65c4`
- end: `0x1800c6778`
- name: `?_CopyCurrentHistoryItemToStream@@YAJPEAUIStream@@@Z`
- size: `436`
- prototype: `__int64 __fastcall(struct IStream *pstmTo)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800c4ea0`

## callees

- `0x18000d2b8`
- `0x180013244`
- `0x18003217c`
- `0x180050ba0`
- `0x1800c65c4`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c662c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c662c`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Copy` at `0x1800c673e`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Copy` at `0x1800c673e`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x1800c6725`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x1800c6725`
- `SHELL32!SHCreateItemInKnownFolder` at `0x1800c66b8`
- `SHELL32!SHCreateItemInKnownFolder` at `0x1800c66b8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall _CopyCurrentHistoryItemToStream(struct IStream *pstmTo)
{
  int ValueW; // ebx
  bool v3; // sf
  void *v4; // rdi
  __int64 (__fastcall *v5)(void *, _QWORD, const GUID *, GUID *, DWORD *); // rbx
  DWORD pcbData[2]; // [rsp+40h] [rbp-C0h] BYREF
  void *ppv; // [rsp+48h] [rbp-B8h] BYREF
  ULARGE_INTEGER pui; // [rsp+50h] [rbp-B0h] BYREF
  _WORD pvData[20]; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR pszItem[264]; // [rsp+80h] [rbp-80h] BYREF

  pcbData[0] = 40;
  ValueW = RegGetValueW(
             HKEY_CURRENT_USER,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\AccountPicture",
             L"SourceId",
             2u,
             0,
             pvData,
             pcbData);
  if ( !ValueW )
    goto LABEL_4;
  pvData[0] = 0;
  v3 = ValueW < 0;
  if ( ValueW > 0 )
  {
    ValueW = (unsigned __int16)ValueW | 0x80070000;
LABEL_4:
    v3 = ValueW < 0;
  }
  if ( !v3 )
  {
    ValueW = StringCchPrintfW(pszItem, 0x104u, L"%s%s", pvData, L".accountpicture-ms");
    if ( ValueW >= 0 )
    {
      ppv = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
      ValueW = SHCreateItemInKnownFolder(
                 &FOLDERID_AccountPictures,
                 0x1000u,
                 pszItem,
                 &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                 &ppv);
      if ( ValueW >= 0 )
      {
        *(_QWORD *)pcbData = 0;
        v4 = ppv;
        v5 = *(__int64 (__fastcall **)(void *, _QWORD, const GUID *, GUID *, DWORD *))(*(_QWORD *)ppv + 24LL);
        Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(pcbData);
        ValueW = v5(v4, 0, &BHID_SFObject, &GUID_0000000c_0000_0000_c000_000000000046, pcbData);
        if ( ValueW >= 0 )
        {
          pui.QuadPart = 0;
          ValueW = IStream_Size(*(IStream **)pcbData, &pui);
          if ( ValueW >= 0 )
            ValueW = IStream_Copy(*(IStream **)pcbData, pstmTo, pui.LowPart);
        }
        Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(pcbData);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    }
  }
  return (unsigned int)ValueW;
}

```

## disassembly

```asm
0x1800c65c4  push    rbp
0x1800c65c6  push    rbx
0x1800c65c7  push    rsi
0x1800c65c8  push    rdi
0x1800c65c9  lea     rbp, [rsp-1A8h]
0x1800c65d1  sub     rsp, 2A8h
0x1800c65d8  mov     rax, cs:__security_cookie
0x1800c65df  xor     rax, rsp
0x1800c65e2  mov     [rbp+1C0h+var_30], rax
0x1800c65e9  mov     rsi, rcx
0x1800c65ec  mov     [rsp+2C0h+var_280], 28h ; '('
0x1800c65f4  lea     rax, [rsp+2C0h+var_280]
0x1800c65f9  mov     [rsp+2C0h+pcbData], rax; pcbData
0x1800c65fe  lea     rax, [rsp+2C0h+var_268]
0x1800c6603  mov     [rsp+2C0h+pvData], rax; pvData
0x1800c6608  mov     [rsp+2C0h+pdwType], 0; pdwType
0x1800c6611  mov     r9d, 2; dwFlags
0x1800c6617  lea     r8, aSourceid; "SourceId"
0x1800c661e  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800c6625  mov     rcx, 0FFFFFFFF80000001h; hkey
0x1800c662c  call    cs:__imp_RegGetValueW
0x1800c6632  mov     ebx, eax
0x1800c6634  test    eax, eax
0x1800c6636  jz      short loc_1800C664C
0x1800c6638  xor     eax, eax
0x1800c663a  mov     [rsp+2C0h+var_268], ax
0x1800c663f  test    ebx, ebx
0x1800c6641  jle     short loc_1800C664E
0x1800c6643  movzx   ebx, bx
0x1800c6646  or      ebx, 80070000h
0x1800c664c  test    ebx, ebx
0x1800c664e  js      loc_1800C675B
0x1800c6654  lea     rax, aAccountpicture; ".accountpicture-ms"
0x1800c665b  mov     [rsp+2C0h+pdwType], rax
0x1800c6660  lea     r9, [rsp+2C0h+var_268]
0x1800c6665  lea     r8, aSS_2; "%s%s"
0x1800c666c  mov     edx, 104h; unsigned __int64
0x1800c6671  lea     rcx, [rbp+1C0h+pszItem]; unsigned __int16 *
0x1800c6675  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800c667a  mov     ebx, eax
0x1800c667c  test    eax, eax
0x1800c667e  js      loc_1800C675B
0x1800c6684  mov     [rsp+2C0h+ppv], 0
0x1800c668d  lea     rcx, [rsp+2C0h+ppv]
0x1800c6692  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c6697  lea     rax, [rsp+2C0h+ppv]
0x1800c669c  mov     [rsp+2C0h+pdwType], rax; ppv
0x1800c66a1  lea     r9, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800c66a8  lea     r8, [rbp+1C0h+pszItem]; pszItem
0x1800c66ac  mov     edx, 1000h; dwKFFlags
0x1800c66b1  lea     rcx, FOLDERID_AccountPictures; kfid
0x1800c66b8  call    cs:__imp_SHCreateItemInKnownFolder
0x1800c66be  mov     ebx, eax
0x1800c66c0  test    eax, eax
0x1800c66c2  js      loc_1800C6751
0x1800c66c8  mov     qword ptr [rsp+2C0h+var_280], 0
0x1800c66d1  mov     rdi, [rsp+2C0h+ppv]
0x1800c66d6  mov     rax, [rdi]
0x1800c66d9  mov     rbx, [rax+18h]
0x1800c66dd  lea     rcx, [rsp+2C0h+var_280]
0x1800c66e2  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800c66e7  lea     rax, [rsp+2C0h+var_280]
0x1800c66ec  mov     [rsp+2C0h+pdwType], rax
0x1800c66f1  lea     r9, _GUID_0000000c_0000_0000_c000_000000000046
0x1800c66f8  lea     r8, BHID_SFObject
0x1800c66ff  xor     edx, edx
0x1800c6701  mov     rcx, rdi
0x1800c6704  mov     rax, rbx
0x1800c6707  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c670c  mov     ebx, eax
0x1800c670e  test    eax, eax
0x1800c6710  js      short loc_1800C6746
0x1800c6712  mov     qword ptr [rsp+2C0h+pui], 0
0x1800c671b  lea     rdx, [rsp+2C0h+pui]; pui
0x1800c6720  mov     rcx, qword ptr [rsp+2C0h+var_280]; pstm
0x1800c6725  call    cs:__imp_IStream_Size
0x1800c672b  mov     ebx, eax
0x1800c672d  test    eax, eax
0x1800c672f  js      short loc_1800C6746
0x1800c6731  mov     r8d, dword ptr [rsp+2C0h+pui]; cb
0x1800c6736  mov     rdx, rsi; pstmTo
0x1800c6739  mov     rcx, qword ptr [rsp+2C0h+var_280]; pstmFrom
0x1800c673e  call    cs:__imp_IStream_Copy
0x1800c6744  mov     ebx, eax
0x1800c6746  lea     rcx, [rsp+2C0h+var_280]
0x1800c674b  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800c6750  nop
0x1800c6751  lea     rcx, [rsp+2C0h+ppv]
0x1800c6756  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c675b  mov     eax, ebx
0x1800c675d  mov     rcx, [rbp+1C0h+var_30]
0x1800c6764  xor     rcx, rsp; StackCookie
0x1800c6767  call    __security_check_cookie
0x1800c676c  add     rsp, 2A8h
0x1800c6773  pop     rdi
0x1800c6774  pop     rsi
0x1800c6775  pop     rbx
0x1800c6776  pop     rbp
0x1800c6777  retn
```
