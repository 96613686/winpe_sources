# CWinApp::WriteProfileInt(ushort const *,ushort const *,int)

- ea: `0x1800213a0`
- end: `0x18002145a`
- name: `?WriteProfileInt@CWinApp@@QEAAHPEBG0H@Z`
- size: `186`
- prototype: `int(CWinApp *__hidden this, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180005290`
- `0x18004ca90`
- `0x18004cd70`

## callees

- `0x1800213a0`
- `0x180021460`
- `0x1800d1fe0`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180021438`
- `msvcrt!swprintf_s` at `0x180021438`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800213fa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800213fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021405`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021405`
- `KERNEL32!WritePrivateProfileStringW` at `0x180021450`
- `KERNEL32!WritePrivateProfileStringW` at `0x180021450`

## pseudocode

```c
int __fastcall CWinApp::WriteProfileInt(CWinApp *this, const unsigned __int16 *a2, const unsigned __int16 *a3, int a4)
{
  bool v4; // zf
  HKEY SectionKey; // rax
  HKEY v9; // rdi
  LSTATUS v10; // ebx
  BYTE Data[8]; // [rsp+30h] [rbp-48h] BYREF
  wchar_t Buffer[16]; // [rsp+38h] [rbp-40h] BYREF

  v4 = *((_QWORD *)this + 30) == 0;
  *(_DWORD *)Data = a4;
  if ( v4 )
  {
    swprintf_s(Buffer, 0x10u, L"%d");
    LODWORD(SectionKey) = WritePrivateProfileStringW(a2, a3, Buffer, *((LPCWSTR *)this + 35));
  }
  else
  {
    SectionKey = CWinApp::GetSectionKey(this, a2);
    v9 = SectionKey;
    if ( SectionKey )
    {
      v10 = RegSetValueExW(SectionKey, a3, 0, 4u, Data, 4u);
      RegCloseKey(v9);
      LODWORD(SectionKey) = v10 == 0;
    }
  }
  return (int)SectionKey;
}

```

## disassembly

```asm
0x1800213a0  push    rbx
0x1800213a2  push    rsi
0x1800213a3  push    rdi
0x1800213a4  sub     rsp, 60h
0x1800213a8  mov     rax, cs:__security_cookie
0x1800213af  xor     rax, rsp
0x1800213b2  mov     [rsp+78h+var_20], rax
0x1800213b7  cmp     qword ptr [rcx+0F0h], 0
0x1800213bf  mov     rsi, r8
0x1800213c2  mov     rdi, rdx
0x1800213c5  mov     dword ptr [rsp+78h+Data], r9d
0x1800213ca  mov     rbx, rcx
0x1800213cd  jz      short loc_180021427
0x1800213cf  call    ?GetSectionKey@CWinApp@@QEAAPEAUHKEY__@@PEBG@Z; CWinApp::GetSectionKey(ushort const *)
0x1800213d4  mov     rdi, rax
0x1800213d7  test    rax, rax
0x1800213da  jz      short loc_180021458
0x1800213dc  mov     r9d, 4; dwType
0x1800213e2  lea     rax, [rsp+78h+Data]
0x1800213e7  mov     [rsp+78h+cbData], r9d; cbData
0x1800213ec  xor     r8d, r8d; Reserved
0x1800213ef  mov     rdx, rsi; lpValueName
0x1800213f2  mov     [rsp+78h+lpData], rax; lpData
0x1800213f7  mov     rcx, rdi; hKey
0x1800213fa  call    cs:__imp_RegSetValueExW
0x180021400  mov     rcx, rdi; hKey
0x180021403  mov     ebx, eax
0x180021405  call    cs:__imp_RegCloseKey
0x18002140b  xor     eax, eax
0x18002140d  test    ebx, ebx
0x18002140f  setz    al
0x180021412  mov     rcx, [rsp+78h+var_20]
0x180021417  xor     rcx, rsp; StackCookie
0x18002141a  call    __security_check_cookie
0x18002141f  add     rsp, 60h
0x180021423  pop     rdi
0x180021424  pop     rsi
0x180021425  pop     rbx
0x180021426  retn
0x180021427  lea     r8, aD; "%d"
0x18002142e  mov     edx, 10h; BufferCount
0x180021433  lea     rcx, [rsp+78h+Buffer]; Buffer
0x180021438  call    cs:__imp_swprintf_s
0x18002143e  mov     r9, [rbx+118h]; lpFileName
0x180021445  lea     r8, [rsp+78h+Buffer]; lpString
0x18002144a  mov     rdx, rsi; lpKeyName
0x18002144d  mov     rcx, rdi; lpAppName
0x180021450  call    cs:__imp_WritePrivateProfileStringW
0x180021456  jmp     short loc_180021412
0x180021458  jmp     short loc_180021412
```
