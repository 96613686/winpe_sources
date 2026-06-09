# CachedShellState::SaveAdvancedSettings(void)

- ea: `0x1805a0ae4`
- end: `0x1805a0e75`
- name: `?SaveAdvancedSettings@CachedShellState@@QEAAXXZ`
- size: `913`
- prototype: `void __fastcall(CachedShellState *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180098bb0`
- `0x1805a0aa0`

## callees

- `0x1803a4cb0`
- `0x1805a0ae4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805a0b74`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805a0ba7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805a0bdb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805a0c11`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805a0c47`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805a0c7d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805a0cb3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805a0ce9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805a0d1f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805a0d55`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805a0d85`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805a0db8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805a0deb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805a0e1e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805a0e51`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805a0b74`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805a0ba7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805a0bdb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805a0c11`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805a0c47`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805a0c7d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805a0cb3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805a0ce9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805a0d1f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805a0d55`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805a0d85`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805a0db8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805a0deb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805a0e1e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805a0e51`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1805a0e5a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1805a0e5a`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHGetShellKeyEx` at `0x1805a0b25`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHGetShellKeyEx` at `0x1805a0b25`

## string_xrefs

- `0x1805a0b7e`: `ShowCompColor`
- `0x1805a0be5`: `DontPrettyPath`

## pseudocode

```c
void __fastcall CachedShellState::SaveAdvancedSettings(CachedShellState *this)
{
  HKEY v2; // rdi
  __int64 v3; // rcx
  BYTE Data[8]; // [rsp+30h] [rbp-18h] BYREF

  if ( this != (CachedShellState *)&CachedShellState::s_cssDefault )
  {
    v2 = (HKEY)SHGetShellKeyEx(1, L"Advanced");
    if ( v2 )
    {
      v3 = *((_QWORD *)this + 1);
      *(_DWORD *)Data = 0;
      *(_DWORD *)Data = 2 - ((*(_BYTE *)(v3 + 4) & 1) != 0);
      RegSetValueExW(v2, L"Hidden", 0, 4u, Data, 4u);
      *(_DWORD *)Data = (*(_DWORD *)(*((_QWORD *)this + 1) + 4LL) & 0x10u) >> 4;
      RegSetValueExW(v2, L"ShowCompColor", 0, 4u, Data, 4u);
      *(_DWORD *)Data = (unsigned __int8)(~(unsigned __int8)*(_DWORD *)(*((_QWORD *)this + 1) + 4LL) & 2) >> 1;
      RegSetValueExW(v2, L"HideFileExt", 0, 4u, Data, 4u);
      *(_DWORD *)Data = (*(_DWORD *)(*((_QWORD *)this + 1) + 4LL) & 0x100u) >> 8;
      RegSetValueExW(v2, L"DontPrettyPath", 0, 4u, Data, 4u);
      *(_DWORD *)Data = (*(_DWORD *)(*((_QWORD *)this + 1) + 4LL) & 0x800u) >> 11;
      RegSetValueExW(v2, L"ShowInfoTip", 0, 4u, Data, 4u);
      *(_DWORD *)Data = (*(_DWORD *)(*((_QWORD *)this + 1) + 4LL) & 0x1000u) >> 12;
      RegSetValueExW(v2, L"HideIcons", 0, 4u, Data, 4u);
      *(_DWORD *)Data = (*(_DWORD *)(*((_QWORD *)this + 1) + 4LL) & 0x400u) >> 10;
      RegSetValueExW(v2, L"MapNetDrvBtn", 0, 4u, Data, 4u);
      *(_DWORD *)Data = (*(_DWORD *)(*((_QWORD *)this + 1) + 4LL) & 0x2000u) >> 13;
      RegSetValueExW(v2, L"WebView", 0, 4u, Data, 4u);
      *(_DWORD *)Data = (*(_DWORD *)(*((_QWORD *)this + 1) + 4LL) & 0x4000u) >> 14;
      RegSetValueExW(v2, L"Filter", 0, 4u, Data, 4u);
      *(_DWORD *)Data = (*(_DWORD *)(*((_QWORD *)this + 1) + 4LL) & 0x8000u) >> 15;
      RegSetValueExW(v2, L"ShowSuperHidden", 0, 4u, Data, 4u);
      *(_DWORD *)Data = *(_DWORD *)(*((_QWORD *)this + 1) + 32LL) & 1;
      RegSetValueExW(v2, L"SeparateProcess", 0, 4u, Data, 4u);
      *(_DWORD *)Data = (*(_DWORD *)(*((_QWORD *)this + 1) + 32LL) & 8u) >> 3;
      RegSetValueExW(v2, L"AutoCheckSelect", 0, 4u, Data, 4u);
      *(_DWORD *)Data = (*(_DWORD *)(*((_QWORD *)this + 1) + 32LL) & 0x10u) >> 4;
      RegSetValueExW(v2, L"IconsOnly", 0, 4u, Data, 4u);
      *(_DWORD *)Data = (*(_DWORD *)(*((_QWORD *)this + 1) + 32LL) & 0x20u) >> 5;
      RegSetValueExW(v2, L"ShowTypeOverlay", 0, 4u, Data, 4u);
      *(_DWORD *)Data = (*(_DWORD *)(*((_QWORD *)this + 1) + 32LL) & 0x40u) >> 6;
      RegSetValueExW(v2, L"ShowStatusBar", 0, 4u, Data, 4u);
      RegCloseKey(v2);
    }
  }
}

```

## disassembly

```asm
0x1805a0ae4  push    rbp
0x1805a0ae6  push    rbx
0x1805a0ae7  push    rsi
0x1805a0ae8  push    rdi
0x1805a0ae9  mov     rbp, rsp
0x1805a0aec  sub     rsp, 48h
0x1805a0af0  mov     rax, cs:__security_cookie
0x1805a0af7  xor     rax, rsp
0x1805a0afa  mov     [rbp+var_10], rax
0x1805a0afe  lea     rax, ?s_cssDefault@CachedShellState@@0V1@A; CachedShellState CachedShellState::s_cssDefault
0x1805a0b05  mov     rbx, rcx
0x1805a0b08  cmp     rcx, rax
0x1805a0b0b  jz      loc_1805A0E60
0x1805a0b11  mov     r9d, 2
0x1805a0b17  lea     rdx, aAdvanced; "Advanced"
0x1805a0b1e  lea     r8d, [r9-1]
0x1805a0b22  mov     ecx, r8d
0x1805a0b25  call    cs:__imp_SHGetShellKeyEx
0x1805a0b2b  mov     rdi, rax
0x1805a0b2e  test    rax, rax
0x1805a0b31  jz      loc_1805A0E60
0x1805a0b37  mov     rcx, [rbx+8]
0x1805a0b3b  lea     rax, [rbp+Data]
0x1805a0b3f  mov     dword ptr [rbp+Data], 0
0x1805a0b46  mov     esi, 4
0x1805a0b4b  mov     [rsp+48h+cbData], esi; cbData
0x1805a0b4f  mov     r9d, esi; dwType
0x1805a0b52  mov     [rsp+48h+lpData], rax; lpData
0x1805a0b57  mov     dl, [rcx+4]
0x1805a0b5a  and     dl, 1
0x1805a0b5d  neg     dl
0x1805a0b5f  lea     rdx, aHidden; "Hidden"
0x1805a0b66  sbb     ecx, ecx
0x1805a0b68  xor     r8d, r8d; Reserved
0x1805a0b6b  add     ecx, 2
0x1805a0b6e  mov     dword ptr [rbp+Data], ecx
0x1805a0b71  mov     rcx, rdi; hKey
0x1805a0b74  call    cs:__imp_RegSetValueExW
0x1805a0b7a  mov     rax, [rbx+8]
0x1805a0b7e  lea     rdx, aShowcompcolor; "ShowCompColor"
0x1805a0b85  mov     [rsp+48h+cbData], esi; cbData
0x1805a0b89  mov     r9d, esi; dwType
0x1805a0b8c  xor     r8d, r8d; Reserved
0x1805a0b8f  mov     ecx, [rax+4]
0x1805a0b92  lea     rax, [rbp+Data]
0x1805a0b96  and     ecx, 10h
0x1805a0b99  mov     [rsp+48h+lpData], rax; lpData
0x1805a0b9e  shr     ecx, 4
0x1805a0ba1  mov     dword ptr [rbp+Data], ecx
0x1805a0ba4  mov     rcx, rdi; hKey
0x1805a0ba7  call    cs:__imp_RegSetValueExW
0x1805a0bad  mov     rax, [rbx+8]
0x1805a0bb1  lea     rdx, aHidefileext; "HideFileExt"
0x1805a0bb8  mov     [rsp+48h+cbData], esi; cbData
0x1805a0bbc  mov     r9d, esi; dwType
0x1805a0bbf  xor     r8d, r8d; Reserved
0x1805a0bc2  mov     ecx, [rax+4]
0x1805a0bc5  lea     rax, [rbp+Data]
0x1805a0bc9  not     ecx
0x1805a0bcb  mov     [rsp+48h+lpData], rax; lpData
0x1805a0bd0  and     ecx, 2
0x1805a0bd3  shr     ecx, 1
0x1805a0bd5  mov     dword ptr [rbp+Data], ecx
0x1805a0bd8  mov     rcx, rdi; hKey
0x1805a0bdb  call    cs:__imp_RegSetValueExW
0x1805a0be1  mov     rax, [rbx+8]
0x1805a0be5  lea     rdx, aDontprettypath; "DontPrettyPath"
0x1805a0bec  mov     [rsp+48h+cbData], esi; cbData
0x1805a0bf0  mov     r9d, esi; dwType
0x1805a0bf3  xor     r8d, r8d; Reserved
0x1805a0bf6  mov     ecx, [rax+4]
0x1805a0bf9  lea     rax, [rbp+Data]
0x1805a0bfd  and     ecx, 100h
0x1805a0c03  mov     [rsp+48h+lpData], rax; lpData
0x1805a0c08  shr     ecx, 8
0x1805a0c0b  mov     dword ptr [rbp+Data], ecx
0x1805a0c0e  mov     rcx, rdi; hKey
0x1805a0c11  call    cs:__imp_RegSetValueExW
0x1805a0c17  mov     rax, [rbx+8]
0x1805a0c1b  lea     rdx, aShowinfotip; "ShowInfoTip"
0x1805a0c22  mov     [rsp+48h+cbData], esi; cbData
0x1805a0c26  mov     r9d, esi; dwType
0x1805a0c29  xor     r8d, r8d; Reserved
0x1805a0c2c  mov     ecx, [rax+4]
0x1805a0c2f  lea     rax, [rbp+Data]
0x1805a0c33  and     ecx, 800h
0x1805a0c39  mov     [rsp+48h+lpData], rax; lpData
0x1805a0c3e  shr     ecx, 0Bh
0x1805a0c41  mov     dword ptr [rbp+Data], ecx
0x1805a0c44  mov     rcx, rdi; hKey
0x1805a0c47  call    cs:__imp_RegSetValueExW
0x1805a0c4d  mov     rax, [rbx+8]
0x1805a0c51  lea     rdx, aHideicons; "HideIcons"
0x1805a0c58  mov     [rsp+48h+cbData], esi; cbData
0x1805a0c5c  mov     r9d, esi; dwType
0x1805a0c5f  mov     ecx, [rax+4]
0x1805a0c62  lea     rax, [rbp+Data]
0x1805a0c66  and     ecx, 1000h
0x1805a0c6c  mov     [rsp+48h+lpData], rax; lpData
0x1805a0c71  shr     ecx, 0Ch
0x1805a0c74  mov     dword ptr [rbp+Data], ecx
0x1805a0c77  xor     r8d, r8d; Reserved
0x1805a0c7a  mov     rcx, rdi; hKey
0x1805a0c7d  call    cs:__imp_RegSetValueExW
0x1805a0c83  mov     rax, [rbx+8]
0x1805a0c87  lea     rdx, aMapnetdrvbtn; "MapNetDrvBtn"
0x1805a0c8e  mov     [rsp+48h+cbData], esi; cbData
0x1805a0c92  mov     r9d, esi; dwType
0x1805a0c95  xor     r8d, r8d; Reserved
0x1805a0c98  mov     ecx, [rax+4]
0x1805a0c9b  lea     rax, [rbp+Data]
0x1805a0c9f  and     ecx, 400h
0x1805a0ca5  mov     [rsp+48h+lpData], rax; lpData
0x1805a0caa  shr     ecx, 0Ah
0x1805a0cad  mov     dword ptr [rbp+Data], ecx
0x1805a0cb0  mov     rcx, rdi; hKey
0x1805a0cb3  call    cs:__imp_RegSetValueExW
0x1805a0cb9  mov     rax, [rbx+8]
0x1805a0cbd  lea     rdx, aWebview; "WebView"
0x1805a0cc4  mov     [rsp+48h+cbData], esi; cbData
0x1805a0cc8  mov     r9d, esi; dwType
0x1805a0ccb  xor     r8d, r8d; Reserved
0x1805a0cce  mov     ecx, [rax+4]
0x1805a0cd1  lea     rax, [rbp+Data]
0x1805a0cd5  and     ecx, 2000h
0x1805a0cdb  mov     [rsp+48h+lpData], rax; lpData
0x1805a0ce0  shr     ecx, 0Dh
0x1805a0ce3  mov     dword ptr [rbp+Data], ecx
0x1805a0ce6  mov     rcx, rdi; hKey
0x1805a0ce9  call    cs:__imp_RegSetValueExW
0x1805a0cef  mov     rax, [rbx+8]
0x1805a0cf3  lea     rdx, aFilter; "Filter"
0x1805a0cfa  mov     [rsp+48h+cbData], esi; cbData
0x1805a0cfe  mov     r9d, esi; dwType
0x1805a0d01  xor     r8d, r8d; Reserved
0x1805a0d04  mov     ecx, [rax+4]
0x1805a0d07  lea     rax, [rbp+Data]
0x1805a0d0b  and     ecx, 4000h
0x1805a0d11  mov     [rsp+48h+lpData], rax; lpData
0x1805a0d16  shr     ecx, 0Eh
0x1805a0d19  mov     dword ptr [rbp+Data], ecx
0x1805a0d1c  mov     rcx, rdi; hKey
0x1805a0d1f  call    cs:__imp_RegSetValueExW
0x1805a0d25  mov     rax, [rbx+8]
0x1805a0d29  lea     rdx, aShowsuperhidde_0; "ShowSuperHidden"
0x1805a0d30  mov     [rsp+48h+cbData], esi; cbData
0x1805a0d34  mov     r9d, esi; dwType
0x1805a0d37  xor     r8d, r8d; Reserved
0x1805a0d3a  mov     ecx, [rax+4]
0x1805a0d3d  lea     rax, [rbp+Data]
0x1805a0d41  and     ecx, 8000h
0x1805a0d47  mov     [rsp+48h+lpData], rax; lpData
0x1805a0d4c  shr     ecx, 0Fh
0x1805a0d4f  mov     dword ptr [rbp+Data], ecx
0x1805a0d52  mov     rcx, rdi; hKey
0x1805a0d55  call    cs:__imp_RegSetValueExW
0x1805a0d5b  mov     rax, [rbx+8]
0x1805a0d5f  lea     rdx, aSeparateproces; "SeparateProcess"
0x1805a0d66  mov     [rsp+48h+cbData], esi; cbData
0x1805a0d6a  mov     r9d, esi; dwType
0x1805a0d6d  xor     r8d, r8d; Reserved
0x1805a0d70  mov     ecx, [rax+20h]
0x1805a0d73  lea     rax, [rbp+Data]
0x1805a0d77  and     ecx, 1
0x1805a0d7a  mov     [rsp+48h+lpData], rax; lpData
0x1805a0d7f  mov     dword ptr [rbp+Data], ecx
0x1805a0d82  mov     rcx, rdi; hKey
0x1805a0d85  call    cs:__imp_RegSetValueExW
0x1805a0d8b  mov     rax, [rbx+8]
0x1805a0d8f  lea     rdx, aAutocheckselec; "AutoCheckSelect"
0x1805a0d96  mov     [rsp+48h+cbData], esi; cbData
0x1805a0d9a  mov     r9d, esi; dwType
0x1805a0d9d  xor     r8d, r8d; Reserved
0x1805a0da0  mov     ecx, [rax+20h]
0x1805a0da3  lea     rax, [rbp+Data]
0x1805a0da7  and     ecx, 8
0x1805a0daa  mov     [rsp+48h+lpData], rax; lpData
0x1805a0daf  shr     ecx, 3
0x1805a0db2  mov     dword ptr [rbp+Data], ecx
0x1805a0db5  mov     rcx, rdi; hKey
0x1805a0db8  call    cs:__imp_RegSetValueExW
0x1805a0dbe  mov     rax, [rbx+8]
0x1805a0dc2  mov     ecx, [rax+20h]
0x1805a0dc5  and     ecx, 10h
0x1805a0dc8  mov     [rsp+48h+cbData], esi; cbData
0x1805a0dcc  shr     ecx, 4
0x1805a0dcf  lea     rax, [rbp+Data]
0x1805a0dd3  mov     dword ptr [rbp+Data], ecx
0x1805a0dd6  lea     rdx, aIconsonly; "IconsOnly"
0x1805a0ddd  mov     rcx, rdi; hKey
0x1805a0de0  mov     [rsp+48h+lpData], rax; lpData
0x1805a0de5  mov     r9d, esi; dwType
0x1805a0de8  xor     r8d, r8d; Reserved
0x1805a0deb  call    cs:__imp_RegSetValueExW
0x1805a0df1  mov     rax, [rbx+8]
0x1805a0df5  lea     rdx, aShowtypeoverla; "ShowTypeOverlay"
0x1805a0dfc  mov     [rsp+48h+cbData], esi; cbData
0x1805a0e00  mov     r9d, esi; dwType
0x1805a0e03  xor     r8d, r8d; Reserved
0x1805a0e06  mov     ecx, [rax+20h]
0x1805a0e09  lea     rax, [rbp+Data]
0x1805a0e0d  and     ecx, 20h
0x1805a0e10  mov     [rsp+48h+lpData], rax; lpData
0x1805a0e15  shr     ecx, 5
0x1805a0e18  mov     dword ptr [rbp+Data], ecx
0x1805a0e1b  mov     rcx, rdi; hKey
0x1805a0e1e  call    cs:__imp_RegSetValueExW
0x1805a0e24  mov     rax, [rbx+8]
0x1805a0e28  lea     rdx, aShowstatusbar; "ShowStatusBar"
0x1805a0e2f  mov     [rsp+48h+cbData], esi; cbData
0x1805a0e33  mov     r9d, esi; dwType
0x1805a0e36  xor     r8d, r8d; Reserved
0x1805a0e39  mov     ecx, [rax+20h]
0x1805a0e3c  lea     rax, [rbp+Data]
0x1805a0e40  and     ecx, 40h
0x1805a0e43  mov     [rsp+48h+lpData], rax; lpData
0x1805a0e48  shr     ecx, 6
0x1805a0e4b  mov     dword ptr [rbp+Data], ecx
0x1805a0e4e  mov     rcx, rdi; hKey
0x1805a0e51  call    cs:__imp_RegSetValueExW
0x1805a0e57  mov     rcx, rdi; hKey
0x1805a0e5a  call    cs:__imp_RegCloseKey
0x1805a0e60  mov     rcx, [rbp+var_10]
0x1805a0e64  xor     rcx, rsp; StackCookie
0x1805a0e67  call    __security_check_cookie
0x1805a0e6c  add     rsp, 48h
0x1805a0e70  pop     rdi
0x1805a0e71  pop     rsi
0x1805a0e72  pop     rbx
0x1805a0e73  pop     rbp
0x1805a0e74  retn
```
