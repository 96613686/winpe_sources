# RegInstallA

- ea: `0x180003b50`
- end: `0x180003bce`
- name: `RegInstallA`
- size: `126`
- prototype: `HRESULT __stdcall(HMODULE hmod, LPCSTR pszSection, const STRTABLEA *pstTable)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x18000380c`
- `0x180003874`
- `0x180003b50`
- `0x180003be0`
- `0x1800173a0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180003bb5`
- `KERNEL32!LocalFree` at `0x180003bb5`

## pseudocode

```c
HRESULT __stdcall RegInstallA(HMODULE hmod, LPCSTR pszSection, const STRTABLEA *pstTable)
{
  STRTABLEW *v4; // rbx
  HRESULT v6; // edi
  int v7; // eax
  STRTABLEW *pstTablea; // [rsp+78h] [rbp+20h] BYREF

  v4 = 0;
  pstTablea = 0;
  v6 = -2147467259;
  if ( (int)ThunkToUnicode(pszSection) >= 0 )
  {
    v7 = ThunkSTRTABLEAToW(pstTable, &pstTablea);
    v4 = pstTablea;
    if ( v7 >= 0 )
      v6 = RegInstallW(hmod, 0, pstTablea);
  }
  LocalFree(0);
  ThunkFreeSTRTABLEW(v4);
  return v6;
}

```

## disassembly

```asm
0x180003b50  push    rbx; RegInstall
0x180003b52  push    rbp
0x180003b53  push    rsi
0x180003b54  push    rdi
0x180003b55  sub     rsp, 38h
0x180003b59  mov     rax, rdx
0x180003b5c  mov     [rsp+58h+pszSection], 0
0x180003b65  mov     rbp, rcx
0x180003b68  lea     rdx, [rsp+58h+pszSection]
0x180003b6d  xor     ebx, ebx
0x180003b6f  mov     rcx, rax; lpMultiByteStr
0x180003b72  mov     rsi, r8
0x180003b75  mov     [rsp+58h+pstTable], rbx
0x180003b7a  mov     edi, 80004005h
0x180003b7f  call    ThunkToUnicode
0x180003b84  test    eax, eax
0x180003b86  js      short loc_180003BB0
0x180003b88  lea     rdx, [rsp+58h+pstTable]; struct _StrTableW **
0x180003b8d  mov     rcx, rsi; struct _StrTableA *
0x180003b90  call    ?ThunkSTRTABLEAToW@@YAJPEBU_StrTableA@@PEAPEAU_StrTableW@@@Z; ThunkSTRTABLEAToW(_StrTableA const *,_StrTableW * *)
0x180003b95  mov     rbx, [rsp+58h+pstTable]
0x180003b9a  test    eax, eax
0x180003b9c  js      short loc_180003BB0
0x180003b9e  mov     rdx, [rsp+58h+pszSection]; pszSection
0x180003ba3  mov     r8, rbx; pstTable
0x180003ba6  mov     rcx, rbp; hmod
0x180003ba9  call    RegInstallW
0x180003bae  mov     edi, eax
0x180003bb0  mov     rcx, [rsp+58h+pszSection]; hMem
0x180003bb5  call    cs:__imp_LocalFree
0x180003bbb  mov     rcx, rbx; hMem
0x180003bbe  call    ?ThunkFreeSTRTABLEW@@YAJPEAU_StrTableW@@@Z; ThunkFreeSTRTABLEW(_StrTableW *)
0x180003bc3  mov     eax, edi
0x180003bc5  add     rsp, 38h
0x180003bc9  pop     rdi
0x180003bca  pop     rsi
0x180003bcb  pop     rbp
0x180003bcc  pop     rbx
0x180003bcd  retn
```
