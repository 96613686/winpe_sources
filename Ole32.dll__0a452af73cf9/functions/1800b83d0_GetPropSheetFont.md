# GetPropSheetFont

- ea: `0x1800b83d0`
- end: `0x1800b85b5`
- name: `GetPropSheetFont`
- size: `485`
- prototype: `HFONT__ *__fastcall()`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800b8dc0`

## callees

- `0x180052390`
- `0x180053014`
- `0x1800b83d0`
- `0x1800c4651`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800b8455`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800b8455`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800b8498`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800b8498`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800b8425`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800b8441`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800b8425`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800b8441`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x1800b84a1`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x1800b84a1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b846c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b846c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800b854e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800b854e`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x1800b848c`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x1800b848c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800b8577`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800b8577`
- `GDI32!CreateFontIndirectW` at `0x1800b8593`
- `GDI32!CreateFontIndirectW` at `0x1800b8593`
- `GDI32!GetDeviceCaps` at `0x1800b8567`
- `GDI32!GetDeviceCaps` at `0x1800b8567`
- `USER32!ReleaseDC` at `0x1800b8588`
- `USER32!ReleaseDC` at `0x1800b8588`
- `USER32!GetDC` at `0x1800b8556`
- `USER32!GetDC` at `0x1800b8556`

## pseudocode

```c
HFONT __fastcall GetPropSheetFont()
{
  int v0; // esi
  int v1; // edi
  HMODULE Library; // rax
  HMODULE v3; // rbx
  HRSRC ResourceW; // rax
  HGLOBAL Resource; // rax
  _DWORD *v6; // rax
  __int64 v7; // rcx
  unsigned int v8; // r8d
  unsigned __int16 *v9; // rdx
  __int64 v10; // rcx
  unsigned __int16 *v14; // rdx
  __int64 v15; // rax
  unsigned __int64 v16; // rax
  HDC DC; // rbx
  int DeviceCaps; // eax
  tagLOGFONTW logfontW; // [rsp+20h] [rbp-B8h] BYREF
  wchar_t wszlfHeight[16]; // [rsp+80h] [rbp-58h] BYREF

  memset_0(&logfontW, 0, sizeof(logfontW));
  v0 = 8;
  logfontW.lfWeight = 400;
  logfontW.lfCharSet = 1;
  v1 = 32;
  LoadStringW(g_hinstDLL, 0x64u, logfontW.lfFaceName, 32);
  if ( LoadStringW(g_hinstDLL, 0x65u, wszlfHeight, 16) )
    v0 = _o__wtoi(wszlfHeight);
  Library = LoadLibraryExW(wszCOMCTL32, 0, 0x800u);
  v3 = Library;
  if ( Library )
  {
    ResourceW = FindResourceW(Library, (LPCWSTR)0x3EE, (LPCWSTR)5);
    Resource = LoadResource(v3, ResourceW);
    v6 = LockResource(Resource);
    if ( v6 )
    {
      v7 = 18;
      v8 = *v6 & 0xFFFF0000;
      if ( v8 == -65536 )
        v7 = 26;
      v9 = (unsigned __int16 *)((char *)v6 + v7);
      v10 = 1;
      if ( *v9 == 0xFFFF )
      {
        v9 += 2;
      }
      else
      {
        while ( *v9++ )
          ;
      }
      if ( *v9 == 0xFFFF )
      {
        v9 += 2;
      }
      else
      {
        while ( *v9++ )
          ;
      }
      while ( *v9++ )
        ;
      v0 = *v9;
      if ( v8 == -65536 )
        v10 = 3;
      v14 = &v9[v10];
      v15 = -1;
      do
        ++v15;
      while ( v14[v15] );
      v16 = v15 + 1;
      if ( v16 <= 0x20 )
        v1 = v16;
      memcpy_0(logfontW.lfFaceName, v14, 2LL * v1);
    }
    FreeLibrary(v3);
  }
  DC = GetDC(0);
  DeviceCaps = GetDeviceCaps(DC, 90);
  logfontW.lfHeight = -MulDiv(v0, DeviceCaps, 72);
  ReleaseDC(0, DC);
  return CreateFontIndirectW(&logfontW);
}

```

## disassembly

```asm
0x1800b83d0  push    rbx
0x1800b83d2  push    rbp
0x1800b83d3  push    rsi
0x1800b83d4  push    rdi
0x1800b83d5  sub     rsp, 0B8h
0x1800b83dc  mov     rax, cs:__security_cookie
0x1800b83e3  xor     rax, rsp
0x1800b83e6  mov     [rsp+0D8h+var_38], rax
0x1800b83ee  xor     edx, edx; Val
0x1800b83f0  lea     rcx, [rsp+0D8h+logfontW]; void *
0x1800b83f5  lea     r8d, [rdx+5Ch]; Size
0x1800b83f9  call    memset_0
0x1800b83fe  mov     rcx, cs:g_hinstDLL; hInstance
0x1800b8405  lea     r8, [rsp+0D8h+logfontW.lfFaceName]; lpBuffer
0x1800b840a  mov     esi, 8
0x1800b840f  mov     [rsp+0D8h+logfontW.lfWeight], 190h
0x1800b8417  mov     [rsp+0D8h+logfontW.lfCharSet], 1
0x1800b841c  lea     edi, [rsi+18h]
0x1800b841f  mov     r9d, edi; cchBufferMax
0x1800b8422  lea     edx, [rsi+5Ch]; uID
0x1800b8425  call    cs:__imp_LoadStringW
0x1800b842b  mov     rcx, cs:g_hinstDLL; hInstance
0x1800b8432  lea     r9d, [rsi+8]; cchBufferMax
0x1800b8436  lea     r8, [rsp+0D8h+wszlfHeight]; lpBuffer
0x1800b843e  lea     edx, [rsi+5Dh]; uID
0x1800b8441  call    cs:__imp_LoadStringW
0x1800b8447  xor     ebp, ebp
0x1800b8449  test    eax, eax
0x1800b844b  jz      short loc_1800B845D
0x1800b844d  lea     rcx, [rsp+0D8h+wszlfHeight]
0x1800b8455  call    cs:__imp__o__wtoi
0x1800b845b  mov     esi, eax
0x1800b845d  xor     edx, edx; hFile
0x1800b845f  lea     rcx, wszCOMCTL32; lpLibFileName
0x1800b8466  mov     r8d, 800h; dwFlags
0x1800b846c  call    cs:__imp_LoadLibraryExW
0x1800b8472  mov     rbx, rax
0x1800b8475  test    rax, rax
0x1800b8478  jz      loc_1800B8554
0x1800b847e  mov     edx, 3EEh; lpName
0x1800b8483  mov     r8d, 5; lpType
0x1800b8489  mov     rcx, rax; hModule
0x1800b848c  call    cs:__imp_FindResourceW
0x1800b8492  mov     rdx, rax; hResInfo
0x1800b8495  mov     rcx, rbx; hModule
0x1800b8498  call    cs:__imp_LoadResource
0x1800b849e  mov     rcx, rax; hResData
0x1800b84a1  call    cs:__imp_LockResource
0x1800b84a7  test    rax, rax
0x1800b84aa  jz      loc_1800B854B
0x1800b84b0  mov     r8d, [rax]
0x1800b84b3  mov     r10d, 0FFFF0000h
0x1800b84b9  mov     ecx, 12h
0x1800b84be  and     r8d, r10d
0x1800b84c1  cmp     r8d, r10d
0x1800b84c4  mov     r9d, 0FFFFh
0x1800b84ca  lea     edx, [rcx+8]
0x1800b84cd  cmovz   ecx, edx
0x1800b84d0  lea     rdx, [rcx+rax]
0x1800b84d4  mov     ecx, 2
0x1800b84d9  cmp     [rdx], r9w
0x1800b84dd  jnz     short loc_1800B84E5
0x1800b84df  add     rdx, 4
0x1800b84e3  jmp     short loc_1800B84F0
0x1800b84e5  movzx   eax, word ptr [rdx]
0x1800b84e8  add     rdx, rcx
0x1800b84eb  test    ax, ax
0x1800b84ee  jnz     short loc_1800B84E5
0x1800b84f0  cmp     [rdx], r9w
0x1800b84f4  jnz     short loc_1800B84FC
0x1800b84f6  add     rdx, 4
0x1800b84fa  jmp     short loc_1800B8507
0x1800b84fc  movzx   eax, word ptr [rdx]
0x1800b84ff  add     rdx, rcx
0x1800b8502  test    ax, ax
0x1800b8505  jnz     short loc_1800B84FC
0x1800b8507  movzx   eax, word ptr [rdx]
0x1800b850a  add     rdx, rcx
0x1800b850d  test    ax, ax
0x1800b8510  jnz     short loc_1800B8507
0x1800b8512  movzx   esi, word ptr [rdx]
0x1800b8515  cmp     r8d, r10d
0x1800b8518  mov     eax, 6
0x1800b851d  cmovz   rcx, rax
0x1800b8521  add     rdx, rcx; Src
0x1800b8524  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800b8528  inc     rax
0x1800b852b  cmp     [rdx+rax*2], bp
0x1800b852f  jnz     short loc_1800B8528
0x1800b8531  inc     rax
0x1800b8534  cmp     rax, rdi
0x1800b8537  ja      short loc_1800B853B
0x1800b8539  mov     edi, eax
0x1800b853b  movsxd  r8, edi
0x1800b853e  lea     rcx, [rsp+0D8h+logfontW.lfFaceName]; void *
0x1800b8543  add     r8, r8; Size
0x1800b8546  call    memcpy_0
0x1800b854b  mov     rcx, rbx; hLibModule
0x1800b854e  call    cs:__imp_FreeLibrary
0x1800b8554  xor     ecx, ecx; hWnd
0x1800b8556  call    cs:__imp_GetDC
0x1800b855c  mov     rcx, rax; hdc
0x1800b855f  mov     edx, 5Ah ; 'Z'; index
0x1800b8564  mov     rbx, rax
0x1800b8567  call    cs:__imp_GetDeviceCaps
0x1800b856d  mov     r8d, 48h ; 'H'; nDenominator
0x1800b8573  mov     ecx, esi; nNumber
0x1800b8575  mov     edx, eax; nNumerator
0x1800b8577  call    cs:__imp_MulDiv
0x1800b857d  mov     rdx, rbx; hDC
0x1800b8580  xor     ecx, ecx; hWnd
0x1800b8582  neg     eax
0x1800b8584  mov     [rsp+0D8h+logfontW.lfHeight], eax
0x1800b8588  call    cs:__imp_ReleaseDC
0x1800b858e  lea     rcx, [rsp+0D8h+logfontW]; lplf
0x1800b8593  call    cs:__imp_CreateFontIndirectW
0x1800b8599  mov     rcx, [rsp+0D8h+var_38]
0x1800b85a1  xor     rcx, rsp; StackCookie
0x1800b85a4  call    __security_check_cookie
0x1800b85a9  add     rsp, 0B8h
0x1800b85b0  pop     rdi
0x1800b85b1  pop     rsi
0x1800b85b2  pop     rbp
0x1800b85b3  pop     rbx
0x1800b85b4  retn
```
