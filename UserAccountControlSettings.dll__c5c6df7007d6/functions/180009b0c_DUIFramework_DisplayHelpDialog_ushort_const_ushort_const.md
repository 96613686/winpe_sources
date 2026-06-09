# DUIFramework_DisplayHelpDialog(ushort const *,ushort const *)

- ea: `0x180009b0c`
- end: `0x180009c3a`
- name: `?DUIFramework_DisplayHelpDialog@@YAJPEBG0@Z`
- size: `302`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180003400`

## callees

- `0x180006a9c`
- `0x180006af0`
- `0x180009b0c`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009b8d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009b8d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009ba4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009ba4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009c01`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009c01`
- `ntdll!WinSqmAddToStream` at `0x180009b61`
- `ntdll!WinSqmAddToStream` at `0x180009b61`
- `USER32!LoadCursorW` at `0x180009b27`
- `USER32!LoadCursorW` at `0x180009b27`
- `USER32!SetCursor` at `0x180009b30`
- `USER32!SetCursor` at `0x180009c22`
- `USER32!SetCursor` at `0x180009b30`
- `USER32!SetCursor` at `0x180009c22`

## pseudocode

```c
__int64 __fastcall DUIFramework_DisplayHelpDialog(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  HCURSOR CursorW; // rax
  HCURSOR v3; // rsi
  HRESULT v4; // ebx
  unsigned __int16 *v5; // rax
  unsigned __int16 *v6; // rdi
  unsigned int v7; // r11d
  int v9; // [rsp+30h] [rbp-18h] BYREF
  const wchar_t *v10; // [rsp+38h] [rbp-10h]
  LPVOID ppv; // [rsp+58h] [rbp+10h] BYREF

  ppv = a2;
  CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
  v9 = 2;
  v3 = SetCursor(CursorW);
  v10 = L"UAC_WHC_SETTINGS_WHAT_UAC_SETTINGS";
  WinSqmAddToStream(0, 911, 1, &v9);
  ppv = 0;
  v4 = CoCreateInstance(
         &GUID_8cec58e7_07a1_11d9_b15e_000d56bfe6ee,
         0,
         1u,
         &GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee,
         &ppv);
  if ( v4 >= 0 )
  {
    v5 = (unsigned __int16 *)LocalAlloc(0, 0x74u);
    v6 = v5;
    if ( v5 )
    {
      v4 = StringCchCopyW(v5, 0x3Au, L"mshelp://windows/?id=");
      if ( v4 >= 0 )
      {
        v4 = StringCchCatW(v6, v7, L"78540f6d-4505-497c-84cd-c37e1d9930aa");
        if ( v4 >= 0 )
          v4 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *))(*(_QWORD *)ppv + 24LL))(ppv, v6);
      }
      LocalFree(v6);
    }
    else
    {
      v4 = -2147024882;
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  SetCursor(v3);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180009b0c  mov     [rsp+arg_0], rbx
0x180009b11  mov     [rsp+arg_10], rsi
0x180009b16  mov     [rsp+arg_8], rdx
0x180009b1b  push    rdi
0x180009b1c  sub     rsp, 40h
0x180009b20  mov     edx, 7F02h; lpCursorName
0x180009b25  xor     ecx, ecx; hInstance
0x180009b27  call    cs:__imp_LoadCursorW
0x180009b2d  mov     rcx, rax; hCursor
0x180009b30  call    cs:__imp_SetCursor
0x180009b36  mov     ebx, 1
0x180009b3b  mov     [rsp+48h+var_18], 2
0x180009b43  mov     rsi, rax
0x180009b46  lea     r9, [rsp+48h+var_18]
0x180009b4b  lea     rax, aUacWhcSettings; "UAC_WHC_SETTINGS_WHAT_UAC_SETTINGS"
0x180009b52  mov     r8d, ebx
0x180009b55  mov     edx, 38Fh
0x180009b5a  mov     [rsp+48h+var_10], rax
0x180009b5f  xor     ecx, ecx
0x180009b61  call    cs:__imp_WinSqmAddToStream
0x180009b67  lea     rax, [rsp+48h+arg_8]
0x180009b6c  mov     [rsp+48h+arg_8], 0
0x180009b75  lea     r9, _GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee; riid
0x180009b7c  mov     [rsp+48h+ppv], rax; ppv
0x180009b81  mov     r8d, ebx; dwClsContext
0x180009b84  lea     rcx, _GUID_8cec58e7_07a1_11d9_b15e_000d56bfe6ee; rclsid
0x180009b8b  xor     edx, edx; pUnkOuter
0x180009b8d  call    cs:__imp_CoCreateInstance
0x180009b93  mov     ebx, eax
0x180009b95  test    eax, eax
0x180009b97  js      loc_180009C1F
0x180009b9d  mov     edx, 74h ; 't'; uBytes
0x180009ba2  xor     ecx, ecx; uFlags
0x180009ba4  call    cs:__imp_LocalAlloc
0x180009baa  mov     rdi, rax
0x180009bad  test    rax, rax
0x180009bb0  jz      short loc_180009C09
0x180009bb2  mov     r11d, 3Ah ; ':'
0x180009bb8  lea     r8, aMshelpWindowsI; "mshelp://windows/?id="
0x180009bbf  mov     edx, r11d; unsigned __int64
0x180009bc2  mov     rcx, rax; unsigned __int16 *
0x180009bc5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180009bca  mov     ebx, eax
0x180009bcc  test    eax, eax
0x180009bce  js      short loc_180009BFE
0x180009bd0  lea     r8, a78540f6d450549; "78540f6d-4505-497c-84cd-c37e1d9930aa"
0x180009bd7  mov     edx, r11d; unsigned __int64
0x180009bda  mov     rcx, rdi; unsigned __int16 *
0x180009bdd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009be2  mov     ebx, eax
0x180009be4  test    eax, eax
0x180009be6  js      short loc_180009BFE
0x180009be8  mov     rcx, [rsp+48h+arg_8]
0x180009bed  mov     rdx, rdi
0x180009bf0  mov     rax, [rcx]
0x180009bf3  mov     rax, [rax+18h]
0x180009bf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bfc  mov     ebx, eax
0x180009bfe  mov     rcx, rdi; hMem
0x180009c01  call    cs:__imp_LocalFree
0x180009c07  jmp     short loc_180009C0E
0x180009c09  mov     ebx, 8007000Eh
0x180009c0e  mov     rcx, [rsp+48h+arg_8]
0x180009c13  mov     rax, [rcx]
0x180009c16  mov     rax, [rax+10h]
0x180009c1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c1f  mov     rcx, rsi; hCursor
0x180009c22  call    cs:__imp_SetCursor
0x180009c28  mov     rsi, [rsp+48h+arg_10]
0x180009c2d  mov     eax, ebx
0x180009c2f  mov     rbx, [rsp+48h+arg_0]
0x180009c34  add     rsp, 40h
0x180009c38  pop     rdi
0x180009c39  retn
```
