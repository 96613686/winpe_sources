# CLockScreenHistory::s_GetCallerDisplayString(ushort const *,ushort * *)

- ea: `0x1800bbec8`
- end: `0x1800bc0e2`
- name: `?s_GetCallerDisplayString@CLockScreenHistory@@SAJPEBGPEAPEAG@Z`
- size: `538`
- prototype: `__int64 __fastcall(LPCWCH lpString1, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800b0fa0`

## callees

- `0x18003217c`
- `0x18004d6c4`
- `0x1800bbec8`
- `0x1800d95c8`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800bbefb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800bbf1d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800bbf3f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800bbf64`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800bbfbb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800bc01f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800bbefb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800bbf1d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800bbf3f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800bbf64`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800bbfbb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800bc01f`
- `SHELL32!SHCreateItemInKnownFolder` at `0x1800bbff4`
- `SHELL32!SHCreateItemInKnownFolder` at `0x1800bbff4`
- `SHELL32!SHCreateItemFromParsingName` at `0x1800bc04d`
- `SHELL32!SHCreateItemFromParsingName` at `0x1800bc04d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bc09e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bc09e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLockScreenHistory::s_GetCallerDisplayString(LPCWCH lpString1, unsigned __int16 **a2)
{
  int v4; // edi
  __int64 v5; // rbx
  int v6; // r8d
  int v7; // edx
  LPCWCH v8; // rbx
  HRESULT v9; // eax
  void *bIgnoreCase; // [rsp+20h] [rbp-28h]
  void *ppv; // [rsp+58h] [rbp+10h] BYREF
  LPVOID pv; // [rsp+60h] [rbp+18h] BYREF

  *a2 = 0;
  v4 = 0;
  v5 = -1;
  if ( CompareStringOrdinal(lpString1, -1, L"IMMERSIVE_CPL", -1, 0) != 2
    && CompareStringOrdinal(lpString1, -1, L"CREATIVE", -1, 0) != 2 )
  {
    if ( CompareStringOrdinal(lpString1, -1, L"ROAMING", -1, 0) == 2 )
    {
      v7 = 38915;
      return (unsigned int)TResourceStringAllocCopyEx<unsigned short *>(
                             (int)&_ImageBase,
                             v7,
                             v6,
                             (int)&ResourceStringAllocCopyExCoAlloc,
                             bIgnoreCase,
                             a2);
    }
    if ( CompareStringOrdinal(lpString1, -1, L"POLICY", -1, 0) == 2 )
    {
      v7 = 38928;
      return (unsigned int)TResourceStringAllocCopyEx<unsigned short *>(
                             (int)&_ImageBase,
                             v7,
                             v6,
                             (int)&ResourceStringAllocCopyExCoAlloc,
                             bIgnoreCase,
                             a2);
    }
    do
      ++v5;
    while ( lpString1[v5] );
    ppv = 0;
    if ( (int)v5 > 6 && CompareStringOrdinal(lpString1, 6, L"APPID:", 6, 0) == 2 )
    {
      v8 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
      v9 = SHCreateItemInKnownFolder(
             &FOLDERID_AppsFolder,
             0x4000u,
             lpString1 + 6,
             &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
             &ppv);
    }
    else
    {
      v4 = -2147467259;
      if ( (int)v5 <= 10 || CompareStringOrdinal(lpString1, 10, L"IMAGENAME:", 10, 0) != 2 )
      {
LABEL_20:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
        return (unsigned int)v4;
      }
      v8 = lpString1 + 10;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
      v9 = SHCreateItemFromParsingName(lpString1 + 10, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
    }
    v4 = v9;
    if ( v9 < 0
      || (pv = 0, v4 = (*(__int64 (__fastcall **)(void *, _QWORD, LPVOID *))(*(_QWORD *)ppv + 40LL))(ppv, 0, &pv),
                  v4 < 0)
      || (v4 = ResourceStringCoAllocFormatMessage(&_ImageBase, 38916, a2, pv), CoTaskMemFree(pv), v4 < 0) )
    {
      if ( v8 )
        v4 = ResourceStringCoAllocFormatMessage(&_ImageBase, 38916, a2, v8);
    }
    goto LABEL_20;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800bbec8  mov     [rsp+arg_0], rbx
0x1800bbecd  mov     [rsp+arg_18], rbp
0x1800bbed2  push    rsi
0x1800bbed3  push    rdi
0x1800bbed4  push    r14
0x1800bbed6  sub     rsp, 30h
0x1800bbeda  mov     r14, rdx
0x1800bbedd  mov     rsi, rcx
0x1800bbee0  xor     ebp, ebp
0x1800bbee2  mov     [rdx], rbp
0x1800bbee5  mov     edi, ebp
0x1800bbee7  mov     [rsp+48h+bIgnoreCase], ebp; bIgnoreCase
0x1800bbeeb  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800bbeef  mov     r9d, ebx; cchCount2
0x1800bbef2  lea     r8, aImmersiveCpl; "IMMERSIVE_CPL"
0x1800bbef9  mov     edx, ebx; cchCount1
0x1800bbefb  call    cs:__imp_CompareStringOrdinal
0x1800bbf01  cmp     eax, 2
0x1800bbf04  jz      loc_1800BC0CD
0x1800bbf0a  mov     [rsp+48h+bIgnoreCase], ebp; bIgnoreCase
0x1800bbf0e  mov     r9d, ebx; cchCount2
0x1800bbf11  lea     r8, aCreative; "CREATIVE"
0x1800bbf18  mov     edx, ebx; cchCount1
0x1800bbf1a  mov     rcx, rsi; lpString1
0x1800bbf1d  call    cs:__imp_CompareStringOrdinal
0x1800bbf23  cmp     eax, 2
0x1800bbf26  jz      loc_1800BC0CD
0x1800bbf2c  mov     [rsp+48h+bIgnoreCase], ebp; bIgnoreCase
0x1800bbf30  mov     r9d, ebx; cchCount2
0x1800bbf33  lea     r8, aRoaming; "ROAMING"
0x1800bbf3a  mov     edx, ebx; cchCount1
0x1800bbf3c  mov     rcx, rsi; lpString1
0x1800bbf3f  call    cs:__imp_CompareStringOrdinal
0x1800bbf45  cmp     eax, 2
0x1800bbf48  jnz     short loc_1800BBF51
0x1800bbf4a  mov     edx, 9803h
0x1800bbf4f  jmp     short loc_1800BBF74
0x1800bbf51  mov     [rsp+48h+bIgnoreCase], ebp; Src
0x1800bbf55  mov     r9d, ebx; cchCount2
0x1800bbf58  lea     r8, aPolicy; "POLICY"
0x1800bbf5f  mov     edx, ebx; cchCount1
0x1800bbf61  mov     rcx, rsi; lpString1
0x1800bbf64  call    cs:__imp_CompareStringOrdinal
0x1800bbf6a  cmp     eax, 2
0x1800bbf6d  jnz     short loc_1800BBF93
0x1800bbf6f  mov     edx, 9810h; int
0x1800bbf74  lea     r9, _ResourceStringAllocCopyExCoAlloc; int
0x1800bbf7b  mov     [rsp+48h+var_20], r14; void *
0x1800bbf80  lea     rcx, __ImageBase; int
0x1800bbf87  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x1800bbf8c  mov     edi, eax
0x1800bbf8e  jmp     loc_1800BC0CD
0x1800bbf93  inc     rbx
0x1800bbf96  cmp     [rsi+rbx*2], bp
0x1800bbf9a  jnz     short loc_1800BBF93
0x1800bbf9c  mov     [rsp+48h+ppv], rbp
0x1800bbfa1  mov     edx, 6; cchCount1
0x1800bbfa6  cmp     ebx, edx
0x1800bbfa8  jle     short loc_1800BBFFC
0x1800bbfaa  mov     [rsp+48h+bIgnoreCase], ebp; bIgnoreCase
0x1800bbfae  mov     r9d, edx; cchCount2
0x1800bbfb1  lea     r8, aAppid; "APPID:"
0x1800bbfb8  mov     rcx, rsi; lpString1
0x1800bbfbb  call    cs:__imp_CompareStringOrdinal
0x1800bbfc1  cmp     eax, 2
0x1800bbfc4  jnz     short loc_1800BBFFC
0x1800bbfc6  mov     rbx, rbp
0x1800bbfc9  lea     rcx, [rsp+48h+ppv]
0x1800bbfce  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bbfd3  lea     r8, [rsi+0Ch]; pszItem
0x1800bbfd7  lea     rax, [rsp+48h+ppv]
0x1800bbfdc  mov     qword ptr [rsp+48h+bIgnoreCase], rax; ppv
0x1800bbfe1  lea     r9, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800bbfe8  mov     edx, 4000h; dwKFFlags
0x1800bbfed  lea     rcx, FOLDERID_AppsFolder; kfid
0x1800bbff4  call    cs:__imp_SHCreateItemInKnownFolder
0x1800bbffa  jmp     short loc_1800BC053
0x1800bbffc  mov     edi, 80004005h
0x1800bc001  mov     edx, 0Ah; cchCount1
0x1800bc006  cmp     ebx, edx
0x1800bc008  jle     loc_1800BC0C3
0x1800bc00e  mov     [rsp+48h+bIgnoreCase], ebp; bIgnoreCase
0x1800bc012  mov     r9d, edx; cchCount2
0x1800bc015  lea     r8, aImagename; "IMAGENAME:"
0x1800bc01c  mov     rcx, rsi; lpString1
0x1800bc01f  call    cs:__imp_CompareStringOrdinal
0x1800bc025  cmp     eax, 2
0x1800bc028  jnz     loc_1800BC0C3
0x1800bc02e  lea     rbx, [rsi+14h]
0x1800bc032  lea     rcx, [rsp+48h+ppv]
0x1800bc037  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bc03c  lea     r9, [rsp+48h+ppv]; ppv
0x1800bc041  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800bc048  xor     edx, edx; pbc
0x1800bc04a  mov     rcx, rbx; pszPath
0x1800bc04d  call    cs:__imp_SHCreateItemFromParsingName
0x1800bc053  mov     edi, eax
0x1800bc055  mov     esi, 9804h
0x1800bc05a  test    eax, eax
0x1800bc05c  js      short loc_1800BC0A8
0x1800bc05e  mov     [rsp+48h+pv], rbp
0x1800bc063  mov     rcx, [rsp+48h+ppv]
0x1800bc068  mov     rax, [rcx]
0x1800bc06b  lea     r8, [rsp+48h+pv]
0x1800bc070  xor     edx, edx
0x1800bc072  mov     rax, [rax+28h]
0x1800bc076  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc07b  mov     edi, eax
0x1800bc07d  test    eax, eax
0x1800bc07f  js      short loc_1800BC0A8
0x1800bc081  mov     r9, [rsp+48h+pv]
0x1800bc086  mov     r8, r14
0x1800bc089  mov     edx, esi
0x1800bc08b  lea     rcx, __ImageBase
0x1800bc092  call    ResourceStringCoAllocFormatMessage
0x1800bc097  mov     edi, eax
0x1800bc099  mov     rcx, [rsp+48h+pv]; pv
0x1800bc09e  call    cs:__imp_CoTaskMemFree
0x1800bc0a4  test    edi, edi
0x1800bc0a6  jns     short loc_1800BC0C3
0x1800bc0a8  test    rbx, rbx
0x1800bc0ab  jz      short loc_1800BC0C3
0x1800bc0ad  mov     r9, rbx
0x1800bc0b0  mov     r8, r14
0x1800bc0b3  mov     edx, esi
0x1800bc0b5  lea     rcx, __ImageBase
0x1800bc0bc  call    ResourceStringCoAllocFormatMessage
0x1800bc0c1  mov     edi, eax
0x1800bc0c3  lea     rcx, [rsp+48h+ppv]
0x1800bc0c8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bc0cd  mov     eax, edi
0x1800bc0cf  mov     rbx, [rsp+48h+arg_0]
0x1800bc0d4  mov     rbp, [rsp+48h+arg_18]
0x1800bc0d9  add     rsp, 30h
0x1800bc0dd  pop     r14
0x1800bc0df  pop     rdi
0x1800bc0e0  pop     rsi
0x1800bc0e1  retn
```
