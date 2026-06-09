# _SaveTempImage(IStream *,bool,ushort * *)

- ea: `0x1800c862c`
- end: `0x1800c87ac`
- name: `?_SaveTempImage@@YAJPEAUIStream@@_NPEAPEAG@Z`
- size: `384`
- prototype: `int(struct IStream *, bool, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x1800c80e0`

## callees

- `0x180019df0`
- `0x1800277f0`
- `0x18002be34`
- `0x18003217c`
- `0x180050ba0`
- `0x1800c7524`
- `0x1800c862c`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800c8750`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800c8750`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800c8766`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800c8766`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800c86be`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800c86be`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800c869e`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800c869e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall _SaveTempImage(struct IStream *a1, char a2, unsigned __int16 **a3)
{
  HRESULT TempFolder; // ebx
  const unsigned __int16 *v7; // r8
  struct IShellItem *v9; // [rsp+20h] [rbp-E0h] BYREF
  PCWSTR pszPathIn; // [rsp+28h] [rbp-D8h] BYREF
  GUID pguid; // [rsp+30h] [rbp-D0h] BYREF
  OLECHAR sz[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pszPathOut[264]; // [rsp+250h] [rbp+150h] BYREF

  *a3 = 0;
  v9 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v9);
  TempFolder = _GetTempFolder(&v9);
  if ( TempFolder >= 0 )
  {
    pguid = 0;
    TempFolder = CoCreateGuid(&pguid);
    if ( TempFolder >= 0 )
    {
      StringFromGUID2(&pguid, sz, 260);
      v7 = L".mp4";
      if ( !a2 )
        v7 = L".bmp";
      TempFolder = StringCchCatW(sz, 0x104u, v7);
      if ( TempFolder >= 0 )
      {
        TempFolder = SaveStreamToFolder(v9, a1, sz, 1);
        if ( TempFolder >= 0 )
        {
          pszPathIn = 0;
          TempFolder = ((__int64 (__fastcall *)(struct IShellItem *, __int64, PCWSTR *))v9->lpVtbl->GetDisplayName)(
                         v9,
                         2147844096LL,
                         &pszPathIn);
          if ( TempFolder >= 0 )
          {
            TempFolder = PathCchCombine(pszPathOut, 0x104u, pszPathIn, sz);
            if ( TempFolder >= 0 )
              TempFolder = SHStrDupW(pszPathOut, a3);
          }
          CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&pszPathIn);
        }
      }
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v9);
  return (unsigned int)TempFolder;
}

```

## disassembly

```asm
0x1800c862c  mov     [rsp-8+arg_8], rbx
0x1800c8631  mov     [rsp-8+arg_18], rsi
0x1800c8636  push    rbp
0x1800c8637  push    rdi
0x1800c8638  push    r14
0x1800c863a  lea     rbp, [rsp-370h]
0x1800c8642  sub     rsp, 470h
0x1800c8649  mov     rax, cs:__security_cookie
0x1800c8650  xor     rax, rsp
0x1800c8653  mov     [rbp+380h+var_20], rax
0x1800c865a  mov     rdi, r8
0x1800c865d  mov     r14b, dl
0x1800c8660  mov     rsi, rcx
0x1800c8663  mov     qword ptr [r8], 0
0x1800c866a  mov     [rsp+480h+var_460], 0
0x1800c8673  lea     rcx, [rsp+480h+var_460]
0x1800c8678  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c867d  lea     rcx, [rsp+480h+var_460]; struct IShellItem **
0x1800c8682  call    ?_GetTempFolder@@YAJPEAPEAUIShellItem@@@Z; _GetTempFolder(IShellItem * *)
0x1800c8687  mov     ebx, eax
0x1800c8689  test    eax, eax
0x1800c868b  js      loc_1800C8779
0x1800c8691  xorps   xmm0, xmm0
0x1800c8694  movups  xmmword ptr [rsp+480h+pguid.Data1], xmm0
0x1800c8699  lea     rcx, [rsp+480h+pguid]; pguid
0x1800c869e  call    cs:__imp_CoCreateGuid
0x1800c86a4  mov     ebx, eax
0x1800c86a6  test    eax, eax
0x1800c86a8  js      loc_1800C8779
0x1800c86ae  mov     r8d, 104h; cchMax
0x1800c86b4  lea     rdx, [rsp+480h+sz]; lpsz
0x1800c86b9  lea     rcx, [rsp+480h+pguid]; rguid
0x1800c86be  call    cs:__imp_StringFromGUID2
0x1800c86c4  lea     rax, aBmp; ".bmp"
0x1800c86cb  lea     r8, aMp4; ".mp4"
0x1800c86d2  test    r14b, r14b
0x1800c86d5  cmovz   r8, rax; unsigned __int16 *
0x1800c86d9  mov     edx, 104h; unsigned __int64
0x1800c86de  lea     rcx, [rsp+480h+sz]; unsigned __int16 *
0x1800c86e3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800c86e8  mov     ebx, eax
0x1800c86ea  test    eax, eax
0x1800c86ec  js      loc_1800C8779
0x1800c86f2  mov     r9d, 1
0x1800c86f8  lea     r8, [rsp+480h+sz]
0x1800c86fd  mov     rdx, rsi
0x1800c8700  mov     rcx, [rsp+480h+var_460]
0x1800c8705  call    ?SaveStreamToFolder@@YAJPEAUIShellItem@@PEAUIStream@@PEBGW4SAVE_STREAM_MODE@@@Z; SaveStreamToFolder(IShellItem *,IStream *,ushort const *,SAVE_STREAM_MODE)
0x1800c870a  mov     ebx, eax
0x1800c870c  test    eax, eax
0x1800c870e  js      short loc_1800C8779
0x1800c8710  mov     [rsp+480h+pszPathIn], 0
0x1800c8719  mov     rcx, [rsp+480h+var_460]
0x1800c871e  mov     rax, [rcx]
0x1800c8721  lea     r8, [rsp+480h+pszPathIn]
0x1800c8726  mov     edx, 80058000h
0x1800c872b  mov     rax, [rax+28h]
0x1800c872f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8734  mov     ebx, eax
0x1800c8736  test    eax, eax
0x1800c8738  js      short loc_1800C876E
0x1800c873a  lea     r9, [rsp+480h+sz]; pszMore
0x1800c873f  mov     r8, [rsp+480h+pszPathIn]; pszPathIn
0x1800c8744  mov     edx, 104h; cchPathOut
0x1800c8749  lea     rcx, [rbp+380h+pszPathOut]; pszPathOut
0x1800c8750  call    cs:__imp_PathCchCombine
0x1800c8756  mov     ebx, eax
0x1800c8758  test    eax, eax
0x1800c875a  js      short loc_1800C876E
0x1800c875c  mov     rdx, rdi; ppwsz
0x1800c875f  lea     rcx, [rbp+380h+pszPathOut]; psz
0x1800c8766  call    cs:__imp_SHStrDupW
0x1800c876c  mov     ebx, eax
0x1800c876e  lea     rcx, [rsp+480h+pszPathIn]
0x1800c8773  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800c8778  nop
0x1800c8779  lea     rcx, [rsp+480h+var_460]
0x1800c877e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c8783  mov     eax, ebx
0x1800c8785  mov     rcx, [rbp+380h+var_20]
0x1800c878c  xor     rcx, rsp; StackCookie
0x1800c878f  call    __security_check_cookie
0x1800c8794  lea     r11, [rsp+480h+var_10]
0x1800c879c  mov     rbx, [r11+28h]
0x1800c87a0  mov     rsi, [r11+38h]
0x1800c87a4  mov     rsp, r11
0x1800c87a7  pop     r14
0x1800c87a9  pop     rdi
0x1800c87aa  pop     rbp
0x1800c87ab  retn
```
