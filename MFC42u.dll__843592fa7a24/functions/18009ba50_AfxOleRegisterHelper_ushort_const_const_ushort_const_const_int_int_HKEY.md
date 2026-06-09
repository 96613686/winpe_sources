# AfxOleRegisterHelper(ushort const * const *,ushort const * const *,int,int,HKEY__ *)

- ea: `0x18009ba50`
- end: `0x18009bc10`
- name: `?AfxOleRegisterHelper@@YAHPEBQEBG0HHPEAUHKEY__@@@Z`
- size: `448`
- prototype: `int(const unsigned __int16 *const *, const unsigned __int16 *const *, int, int, HKEY)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18009bc20`
- `0x1800c4ce0`
- `0x1800c50c0`

## callees

- `0x180019290`
- `0x18002afd0`
- `0x18009ba50`
- `0x1800d1fe0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009bbc8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009bbc8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009bad3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009bad3`
- `ADVAPI32!RegQueryValueW` at `0x18009bb74`
- `ADVAPI32!RegQueryValueW` at `0x18009bb74`
- `ADVAPI32!RegSetValueW` at `0x18009bba9`
- `ADVAPI32!RegSetValueW` at `0x18009bba9`

## string_xrefs

- `0x18009bac9`: `CLSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AfxOleRegisterHelper(
        const unsigned __int16 **a1,
        const unsigned __int16 *const *a2,
        int a3,
        int a4,
        HKEY hKey)
{
  unsigned int v8; // esi
  const unsigned __int16 *v9; // rbx
  __int64 v10; // rdi
  const WCHAR *v11; // rbx
  LSTATUS v12; // eax
  __int64 v13; // rax
  LSTATUS v14; // eax
  int v16; // [rsp+30h] [rbp-D0h]
  LONG cbData; // [rsp+34h] [rbp-CCh] BYREF
  LPCWSTR lpData; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR lpSubKey; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Data[256]; // [rsp+50h] [rbp-B0h] BYREF

  v16 = a3;
  lpSubKey = _afxPchNil;
  lpData = _afxPchNil;
  phkResult = 0;
  if ( hKey == HKEY_CLASSES_ROOT )
  {
    RegOpenKeyExW(HKEY_CLASSES_ROOT, L"CLSID", 0, 0x2000000u, &phkResult);
    a3 = v16;
  }
  v8 = 1;
  while ( 1 )
  {
    v9 = *a1;
    if ( !*a1 )
      break;
    ++a1;
    if ( hKey != HKEY_CLASSES_ROOT || *v9 )
    {
      v10 = -1;
      do
        ++v10;
      while ( v9[v10] );
      AfxFormatStrings((struct CString *)&lpSubKey, v9, a2, a3);
      AfxFormatStrings((struct CString *)&lpData, &v9[v10 + 1], a2, v16);
      v11 = lpSubKey;
      if ( hKey != HKEY_CLASSES_ROOT || (a3 = v16, *((_DWORD *)lpSubKey - 2)) )
      {
        if ( a4 || (cbData = 512, v12 = RegQueryValueW(hKey, lpSubKey, Data, &cbData), a3 = v16, v12) )
        {
          v13 = -1;
          do
            ++v13;
          while ( lpData[v13] );
          v14 = RegSetValueW(hKey, v11, 1u, lpData, 2 * v13);
          a3 = v16;
          if ( v14 )
          {
            v8 = 0;
            break;
          }
        }
      }
    }
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  CString::~CString((CString *)&lpData);
  CString::~CString((CString *)&lpSubKey);
  return v8;
}

```

## disassembly

```asm
0x18009ba50  mov     [rsp-8+arg_18], rbx
0x18009ba55  push    rbp
0x18009ba56  push    rsi
0x18009ba57  push    rdi
0x18009ba58  push    r12
0x18009ba5a  push    r13
0x18009ba5c  push    r14
0x18009ba5e  push    r15
0x18009ba60  lea     rbp, [rsp-160h]
0x18009ba68  sub     rsp, 260h
0x18009ba6f  mov     rax, cs:__security_cookie
0x18009ba76  xor     rax, rsp
0x18009ba79  mov     [rbp+190h+var_40], rax
0x18009ba80  mov     r12d, r9d
0x18009ba83  mov     [rsp+290h+var_260], r8d
0x18009ba88  mov     r13, rdx
0x18009ba8b  mov     r15, rcx
0x18009ba8e  mov     r14, [rbp+190h+hKey]
0x18009ba95  mov     rax, cs:?_afxPchNil@@3PEBGEB; ushort const * const _afxPchNil
0x18009ba9c  mov     [rsp+290h+lpSubKey], rax
0x18009baa1  mov     [rsp+290h+lpData], rax
0x18009baa6  xor     edi, edi
0x18009baa8  mov     [rsp+290h+var_248], rdi
0x18009baad  cmp     r14, 0FFFFFFFF80000000h
0x18009bab4  jnz     short loc_18009BADE
0x18009bab6  lea     rax, [rsp+290h+var_248]
0x18009babb  mov     [rsp+290h+phkResult], rax; phkResult
0x18009bac0  mov     r9d, 2000000h; samDesired
0x18009bac6  xor     r8d, r8d; ulOptions
0x18009bac9  lea     rdx, aClsid_1; "CLSID"
0x18009bad0  mov     rcx, r14; hKey
0x18009bad3  call    cs:__imp_RegOpenKeyExW
0x18009bad9  mov     r8d, [rsp+290h+var_260]
0x18009bade  mov     esi, 1
0x18009bae3  mov     rbx, [r15]
0x18009bae6  test    rbx, rbx
0x18009bae9  jz      loc_18009BBBE
0x18009baef  add     r15, 8
0x18009baf3  cmp     r14, 0FFFFFFFF80000000h
0x18009bafa  jnz     short loc_18009BB01
0x18009bafc  cmp     [rbx], di
0x18009baff  jz      short loc_18009BAE3
0x18009bb01  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18009bb05  xor     eax, eax
0x18009bb07  inc     rdi
0x18009bb0a  cmp     [rbx+rdi*2], ax
0x18009bb0e  jnz     short loc_18009BB07
0x18009bb10  mov     r9d, r8d; int
0x18009bb13  mov     r8, r13; unsigned __int16 **
0x18009bb16  mov     rdx, rbx; unsigned __int16 *
0x18009bb19  lea     rcx, [rsp+290h+lpSubKey]; this
0x18009bb1e  call    ?AfxFormatStrings@@YAXAEAVCString@@PEBGPEBQEBGH@Z; AfxFormatStrings(CString &,ushort const *,ushort const * const *,int)
0x18009bb23  lea     rdx, [rbx+2]
0x18009bb27  lea     rdx, [rdx+rdi*2]; unsigned __int16 *
0x18009bb2b  mov     r9d, [rsp+290h+var_260]; int
0x18009bb30  mov     r8, r13; unsigned __int16 **
0x18009bb33  lea     rcx, [rsp+290h+lpData]; this
0x18009bb38  call    ?AfxFormatStrings@@YAXAEAVCString@@PEBGPEBQEBGH@Z; AfxFormatStrings(CString &,ushort const *,ushort const * const *,int)
0x18009bb3d  mov     rbx, [rsp+290h+lpSubKey]
0x18009bb42  xor     edi, edi
0x18009bb44  cmp     r14, 0FFFFFFFF80000000h
0x18009bb4b  jnz     short loc_18009BB57
0x18009bb4d  cmp     [rbx-8], edi
0x18009bb50  mov     r8d, [rsp+290h+var_260]
0x18009bb55  jz      short loc_18009BAE3
0x18009bb57  test    r12d, r12d
0x18009bb5a  jnz     short loc_18009BB87
0x18009bb5c  mov     [rsp+290h+cbData], 200h
0x18009bb64  lea     r9, [rsp+290h+cbData]; lpcbData
0x18009bb69  lea     r8, [rsp+290h+Data]; lpData
0x18009bb6e  mov     rdx, rbx; lpSubKey
0x18009bb71  mov     rcx, r14; hKey
0x18009bb74  call    cs:__imp_RegQueryValueW
0x18009bb7a  test    eax, eax
0x18009bb7c  mov     r8d, [rsp+290h+var_260]
0x18009bb81  jz      loc_18009BAE3
0x18009bb87  mov     r9, [rsp+290h+lpData]; lpData
0x18009bb8c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009bb90  inc     rax
0x18009bb93  cmp     [r9+rax*2], di
0x18009bb98  jnz     short loc_18009BB90
0x18009bb9a  add     eax, eax
0x18009bb9c  mov     dword ptr [rsp+290h+phkResult], eax; cbData
0x18009bba0  mov     r8d, esi; dwType
0x18009bba3  mov     rdx, rbx; lpSubKey
0x18009bba6  mov     rcx, r14; hKey
0x18009bba9  call    cs:__imp_RegSetValueW
0x18009bbaf  test    eax, eax
0x18009bbb1  mov     r8d, [rsp+290h+var_260]
0x18009bbb6  jz      loc_18009BAE3
0x18009bbbc  mov     esi, edi
0x18009bbbe  mov     rcx, [rsp+290h+var_248]; hKey
0x18009bbc3  test    rcx, rcx
0x18009bbc6  jz      short loc_18009BBCF
0x18009bbc8  call    cs:__imp_RegCloseKey
0x18009bbce  nop
0x18009bbcf  lea     rcx, [rsp+290h+lpData]; this
0x18009bbd4  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x18009bbd9  nop
0x18009bbda  lea     rcx, [rsp+290h+lpSubKey]; this
0x18009bbdf  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x18009bbe4  mov     eax, esi
0x18009bbe6  mov     rcx, [rbp+190h+var_40]
0x18009bbed  xor     rcx, rsp; StackCookie
0x18009bbf0  call    __security_check_cookie
0x18009bbf5  mov     rbx, [rsp+290h+arg_18]
0x18009bbfd  add     rsp, 260h
0x18009bc04  pop     r15
0x18009bc06  pop     r14
0x18009bc08  pop     r13
0x18009bc0a  pop     r12
0x18009bc0c  pop     rdi
0x18009bc0d  pop     rsi
0x18009bc0e  pop     rbp
0x18009bc0f  retn
```
