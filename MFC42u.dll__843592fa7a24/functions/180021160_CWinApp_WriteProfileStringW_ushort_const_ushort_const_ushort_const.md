# CWinApp::WriteProfileStringW(ushort const *,ushort const *,ushort const *)

- ea: `0x180021160`
- end: `0x180021238`
- name: `?WriteProfileStringW@CWinApp@@QEAAHPEBG00@Z`
- size: `216`
- prototype: `int(CWinApp *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18004ca90`
- `0x180071510`
- `0x180072400`

## callees

- `0x180021160`
- `0x180021460`
- `0x1800214f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18002119f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18002119f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800211ff`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800211ff`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800211c2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800211c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002120a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002120a`
- `KERNEL32!WritePrivateProfileStringW` at `0x180021229`
- `KERNEL32!WritePrivateProfileStringW` at `0x180021229`

## pseudocode

```c
BOOL __fastcall CWinApp::WriteProfileStringW(
        LPCWSTR *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const BYTE *a4)
{
  HKEY AppRegistryKey; // rax
  HKEY v8; // rdi
  LSTATUS v9; // eax
  HKEY v10; // rcx
  HKEY SectionKey; // rax
  HKEY v12; // rbx
  __int64 v14; // rax
  LSTATUS v15; // esi

  if ( this[30] )
  {
    if ( !a3 )
    {
      AppRegistryKey = CWinApp::GetAppRegistryKey((CWinApp *)this);
      v8 = AppRegistryKey;
      if ( AppRegistryKey )
      {
        v9 = RegDeleteKeyExW(AppRegistryKey, a2, 0, 0);
        v10 = v8;
LABEL_14:
        v15 = v9;
        RegCloseKey(v10);
        return v15 == 0;
      }
      return 0;
    }
    SectionKey = CWinApp::GetSectionKey((CWinApp *)this, a2);
    v12 = SectionKey;
    if ( a4 )
    {
      if ( !SectionKey )
        return 0;
      v14 = -1;
      do
        ++v14;
      while ( *(_WORD *)&a4[2 * v14] );
      v9 = RegSetValueExW(v12, a3, 0, 1u, a4, 2 * v14 + 2);
    }
    else
    {
      if ( !SectionKey )
        return 0;
      v9 = RegDeleteValueW(SectionKey, a3);
    }
    v10 = v12;
    goto LABEL_14;
  }
  return WritePrivateProfileStringW(a2, a3, (LPCWSTR)a4, this[35]);
}

```

## disassembly

```asm
0x180021160  push    rbx
0x180021162  push    rbp
0x180021163  push    rsi
0x180021164  push    rdi
0x180021165  sub     rsp, 38h
0x180021169  xor     ebp, ebp
0x18002116b  mov     rdi, r9
0x18002116e  mov     rsi, r8
0x180021171  mov     rbx, rdx
0x180021174  cmp     [rcx+0F0h], rbp
0x18002117b  jz      loc_180021219
0x180021181  test    r8, r8
0x180021184  jnz     short loc_1800211AA
0x180021186  call    ?GetAppRegistryKey@CWinApp@@QEAAPEAUHKEY__@@XZ; CWinApp::GetAppRegistryKey(void)
0x18002118b  mov     rdi, rax
0x18002118e  test    rax, rax
0x180021191  jz      short loc_1800211CF
0x180021193  xor     r9d, r9d; Reserved
0x180021196  xor     r8d, r8d; samDesired
0x180021199  mov     rdx, rbx; lpSubKey
0x18002119c  mov     rcx, rax; hKey
0x18002119f  call    cs:__imp_RegDeleteKeyExW
0x1800211a5  mov     rcx, rdi; this
0x1800211a8  jmp     short loc_180021208
0x1800211aa  call    ?GetSectionKey@CWinApp@@QEAAPEAUHKEY__@@PEBG@Z; CWinApp::GetSectionKey(ushort const *)
0x1800211af  mov     rbx, rax
0x1800211b2  test    rdi, rdi
0x1800211b5  jnz     short loc_1800211CA
0x1800211b7  test    rax, rax
0x1800211ba  jz      short loc_1800211CF
0x1800211bc  mov     rdx, rsi; lpValueName
0x1800211bf  mov     rcx, rax; hKey
0x1800211c2  call    cs:__imp_RegDeleteValueW
0x1800211c8  jmp     short loc_180021205
0x1800211ca  test    rax, rax
0x1800211cd  jnz     short loc_1800211D3
0x1800211cf  xor     eax, eax
0x1800211d1  jmp     short loc_18002122F
0x1800211d3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800211d7  inc     rax
0x1800211da  cmp     [rdi+rax*2], bp
0x1800211de  jnz     short loc_1800211D7
0x1800211e0  lea     eax, ds:2[rax*2]
0x1800211e7  mov     r9d, 1; dwType
0x1800211ed  mov     [rsp+58h+cbData], eax; cbData
0x1800211f1  xor     r8d, r8d; Reserved
0x1800211f4  mov     rdx, rsi; lpValueName
0x1800211f7  mov     [rsp+58h+lpData], rdi; lpData
0x1800211fc  mov     rcx, rbx; hKey
0x1800211ff  call    cs:__imp_RegSetValueExW
0x180021205  mov     rcx, rbx; hKey
0x180021208  mov     esi, eax
0x18002120a  call    cs:__imp_RegCloseKey
0x180021210  test    esi, esi
0x180021212  mov     eax, ebp
0x180021214  setz    al
0x180021217  jmp     short loc_18002122F
0x180021219  mov     r9, [rcx+118h]; lpFileName
0x180021220  mov     r8, rdi; lpString
0x180021223  mov     rcx, rbx; lpAppName
0x180021226  mov     rdx, rsi; lpKeyName
0x180021229  call    cs:__imp_WritePrivateProfileStringW
0x18002122f  add     rsp, 38h
0x180021233  pop     rdi
0x180021234  pop     rsi
0x180021235  pop     rbp
0x180021236  pop     rbx
0x180021237  retn
```
