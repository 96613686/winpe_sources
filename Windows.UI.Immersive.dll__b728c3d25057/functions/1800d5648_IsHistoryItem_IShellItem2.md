# _IsHistoryItem(IShellItem2 *)

- ea: `0x1800d5648`
- end: `0x1800d57d0`
- name: `?_IsHistoryItem@@YA_NPEAUIShellItem2@@@Z`
- size: `392`
- prototype: `bool __fastcall(struct IShellItem2 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800d5444`

## callees

- `0x18000a910`
- `0x180019df0`
- `0x180050ba0`
- `0x1800d5648`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800d56e8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800d5797`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800d56e8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800d5797`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800d5734`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800d5734`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1800d56ca`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1800d56ca`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800d577f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800d577f`

## pseudocode

```c
bool __fastcall _IsHistoryItem(struct IShellItem2 *a1)
{
  struct IShellItem2Vtbl *lpVtbl; // rax
  bool v3; // si
  HRESULT (__stdcall *GetDisplayName)(IShellItem2 *, SIGDN, LPWSTR *); // rbx
  const WCHAR *ExtensionW; // rax
  int ValueW; // eax
  bool v7; // sf
  WCHAR v8; // cx
  const WCHAR *FileNameW; // rax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR pszPath; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v13; // [rsp+50h] [rbp-B0h]
  __int64 v14; // [rsp+58h] [rbp-A8h]
  WCHAR String2[264]; // [rsp+60h] [rbp-A0h] BYREF

  lpVtbl = a1->lpVtbl;
  pszPath = 0;
  v13 = 0;
  v3 = 0;
  v14 = 0;
  GetDisplayName = lpVtbl->GetDisplayName;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pszPath);
  v13 = -1;
  v14 = -1;
  if ( ((int (__fastcall *)(struct IShellItem2 *, __int64, LPCWSTR *))GetDisplayName)(a1, 2147844096LL, &pszPath) < 0 )
    goto LABEL_12;
  ExtensionW = PathFindExtensionW(pszPath);
  if ( CompareStringOrdinal(ExtensionW, -1, L".accountpicture-ms", -1, 1) != 2 )
    goto LABEL_12;
  pcbData = 520;
  v3 = 1;
  ValueW = RegGetValueW(
             HKEY_CURRENT_USER,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\AccountPicture",
             L"SourceId",
             2u,
             0,
             String2,
             &pcbData);
  v7 = ValueW < 0;
  if ( !ValueW )
  {
    v8 = String2[0];
    goto LABEL_7;
  }
  v8 = 0;
  String2[0] = 0;
  if ( ValueW > 0 )
  {
    ValueW = (unsigned __int16)ValueW | 0x80070000;
LABEL_7:
    v7 = ValueW < 0;
  }
  if ( !v7 && v8 && (int)StringCchCatW(String2, 0x104u, L".accountpicture-ms") >= 0 )
  {
    FileNameW = PathFindFileNameW(pszPath);
    v3 = CompareStringOrdinal(FileNameW, -1, String2, -1, 1) != 2;
  }
LABEL_12:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pszPath);
  return v3;
}

```

## disassembly

```asm
0x1800d5648  push    rbp
0x1800d564a  push    rbx
0x1800d564b  push    rsi
0x1800d564c  push    rdi
0x1800d564d  push    r14
0x1800d564f  push    r15
0x1800d5651  lea     rbp, [rsp-188h]
0x1800d5659  sub     rsp, 288h
0x1800d5660  mov     rax, cs:__security_cookie
0x1800d5667  xor     rax, rsp
0x1800d566a  mov     [rbp+1B0h+var_40], rax
0x1800d5671  mov     rax, [rcx]
0x1800d5674  xor     r14d, r14d
0x1800d5677  mov     rdi, rcx
0x1800d567a  mov     [rsp+2B0h+pszPath], r14
0x1800d567f  lea     rcx, [rsp+2B0h+pszPath]
0x1800d5684  mov     [rsp+2B0h+var_260], r14
0x1800d5689  mov     sil, r14b
0x1800d568c  mov     [rsp+2B0h+var_258], r14
0x1800d5691  mov     rbx, [rax+28h]
0x1800d5695  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800d569a  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800d569e  lea     r8, [rsp+2B0h+pszPath]
0x1800d56a3  mov     edx, 80058000h
0x1800d56a8  mov     [rsp+2B0h+var_260], r15
0x1800d56ad  mov     rcx, rdi
0x1800d56b0  mov     [rsp+2B0h+var_258], r15
0x1800d56b5  mov     rax, rbx
0x1800d56b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d56bd  test    eax, eax
0x1800d56bf  js      loc_1800D57A4
0x1800d56c5  mov     rcx, [rsp+2B0h+pszPath]; pszPath
0x1800d56ca  call    cs:__imp_PathFindExtensionW
0x1800d56d0  lea     ebx, [r14+1]
0x1800d56d4  mov     r9d, r15d; cchCount2
0x1800d56d7  mov     rcx, rax; lpString1
0x1800d56da  mov     [rsp+2B0h+bIgnoreCase], ebx; bIgnoreCase
0x1800d56de  lea     r8, aAccountpicture; ".accountpicture-ms"
0x1800d56e5  mov     edx, r15d; cchCount1
0x1800d56e8  call    cs:__imp_CompareStringOrdinal
0x1800d56ee  cmp     eax, 2
0x1800d56f1  jnz     loc_1800D57A4
0x1800d56f7  lea     rax, [rsp+2B0h+var_270]
0x1800d56fc  mov     [rsp+2B0h+var_270], 208h
0x1800d5704  mov     [rsp+2B0h+pcbData], rax; pcbData
0x1800d5709  lea     r9d, [r14+2]; dwFlags
0x1800d570d  lea     rax, [rsp+2B0h+String2]
0x1800d5712  mov     rcx, 0FFFFFFFF80000001h; hkey
0x1800d5719  mov     [rsp+2B0h+pvData], rax; pvData
0x1800d571e  lea     r8, aSourceid; "SourceId"
0x1800d5725  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800d572c  mov     qword ptr [rsp+2B0h+bIgnoreCase], r14; pdwType
0x1800d5731  mov     sil, bl
0x1800d5734  call    cs:__imp_RegGetValueW
0x1800d573a  test    eax, eax
0x1800d573c  jz      short loc_1800D5752
0x1800d573e  mov     ecx, r14d
0x1800d5741  mov     [rsp+2B0h+String2], cx
0x1800d5746  jle     short loc_1800D5759
0x1800d5748  movzx   eax, ax
0x1800d574b  or      eax, 80070000h
0x1800d5750  jmp     short loc_1800D5757
0x1800d5752  movzx   ecx, [rsp+2B0h+String2]
0x1800d5757  test    eax, eax
0x1800d5759  js      short loc_1800D57A4
0x1800d575b  test    cx, cx
0x1800d575e  jz      short loc_1800D57A4
0x1800d5760  lea     r8, aAccountpicture; ".accountpicture-ms"
0x1800d5767  mov     edx, 104h; unsigned __int64
0x1800d576c  lea     rcx, [rsp+2B0h+String2]; unsigned __int16 *
0x1800d5771  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800d5776  test    eax, eax
0x1800d5778  js      short loc_1800D57A4
0x1800d577a  mov     rcx, [rsp+2B0h+pszPath]; pszPath
0x1800d577f  call    cs:__imp_PathFindFileNameW
0x1800d5785  mov     r9d, r15d; cchCount2
0x1800d5788  mov     [rsp+2B0h+bIgnoreCase], ebx; bIgnoreCase
0x1800d578c  mov     rcx, rax; lpString1
0x1800d578f  lea     r8, [rsp+2B0h+String2]; lpString2
0x1800d5794  mov     edx, r15d; cchCount1
0x1800d5797  call    cs:__imp_CompareStringOrdinal
0x1800d579d  cmp     eax, 2
0x1800d57a0  setnz   sil
0x1800d57a4  lea     rcx, [rsp+2B0h+pszPath]
0x1800d57a9  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800d57ae  mov     al, sil
0x1800d57b1  mov     rcx, [rbp+1B0h+var_40]
0x1800d57b8  xor     rcx, rsp; StackCookie
0x1800d57bb  call    __security_check_cookie
0x1800d57c0  add     rsp, 288h
0x1800d57c7  pop     r15
0x1800d57c9  pop     r14
0x1800d57cb  pop     rdi
0x1800d57cc  pop     rsi
0x1800d57cd  pop     rbx
0x1800d57ce  pop     rbp
0x1800d57cf  retn
```
