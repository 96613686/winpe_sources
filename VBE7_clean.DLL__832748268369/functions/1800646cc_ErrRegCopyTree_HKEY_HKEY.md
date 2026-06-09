# _ErrRegCopyTree(HKEY__ *,HKEY__ *)

- ea: `0x1800646cc`
- end: `0x1800648fa`
- name: `?_ErrRegCopyTree@@YAIPEAUHKEY__@@0@Z`
- size: `558`
- prototype: `unsigned int __fastcall(HKEY, HKEY)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180062920`
- `0x1800646cc`
- `0x180064900`
- `0x180064db0`

## callees

- `0x180016790`
- `0x180059120`
- `0x1800646cc`
- `0x180379380`

## import_xrefs

- `MSVCR100!free` at `0x180064825`
- `MSVCR100!free` at `0x1800648e6`
- `MSVCR100!free` at `0x180064825`
- `MSVCR100!free` at `0x1800648e6`
- `MSVCR100!malloc` at `0x180064761`
- `MSVCR100!malloc` at `0x18006477d`
- `MSVCR100!malloc` at `0x180064761`
- `MSVCR100!malloc` at `0x18006477d`
- `ADVAPI32!RegQueryInfoKeyA` at `0x18006473a`
- `ADVAPI32!RegQueryInfoKeyA` at `0x18006473a`
- `ADVAPI32!RegEnumValueA` at `0x1800647d4`
- `ADVAPI32!RegEnumValueA` at `0x1800647d4`
- `ADVAPI32!RegEnumKeyA` at `0x180064847`
- `ADVAPI32!RegEnumKeyA` at `0x180064847`
- `ADVAPI32!RegSetValueExA` at `0x1800647fc`
- `ADVAPI32!RegSetValueExA` at `0x1800647fc`
- `ADVAPI32!RegOpenKeyA` at `0x18006488a`
- `ADVAPI32!RegOpenKeyA` at `0x18006488a`
- `ADVAPI32!RegCloseKey` at `0x1800648b4`
- `ADVAPI32!RegCloseKey` at `0x1800648be`
- `ADVAPI32!RegCloseKey` at `0x1800648b4`
- `ADVAPI32!RegCloseKey` at `0x1800648be`

## pseudocode

```c
unsigned int __fastcall _ErrRegCopyTree(HKEY a1, HKEY a2)
{
  DWORD v2; // esi
  unsigned int v3; // edi
  LSTATUS v4; // eax
  DWORD v6; // ebx
  DWORD v7; // ebx
  BYTE *v8; // rax
  const CHAR *v9; // rbx
  LSTATUS v10; // eax
  DWORD v11; // ebx
  LSTATUS v12; // esi
  HKEY v13; // rbx
  HKEY v14; // rax
  HKEY v15; // rbx
  LSTATUS v16; // eax
  HKEY v17; // rcx
  unsigned int v18; // eax
  DWORD cSubKeys; // [rsp+60h] [rbp-9h] BYREF
  DWORD cbMaxValueLen; // [rsp+64h] [rbp-5h] BYREF
  LPSTR lpValueName; // [rsp+68h] [rbp-1h]
  DWORD cbMaxSubKeyLen; // [rsp+70h] [rbp+7h] BYREF
  DWORD cValues; // [rsp+74h] [rbp+Bh] BYREF
  HKEY v24; // [rsp+78h] [rbp+Fh] BYREF
  HKEY phkResult; // [rsp+80h] [rbp+17h] BYREF
  DWORD cchValueName; // [rsp+88h] [rbp+1Fh] BYREF
  DWORD Type; // [rsp+8Ch] [rbp+23h] BYREF
  BYTE *lpData; // [rsp+90h] [rbp+27h]
  DWORD cbMaxValueNameLen; // [rsp+E0h] [rbp+77h] BYREF
  DWORD cbData; // [rsp+E8h] [rbp+7Fh] BYREF

  v2 = 0;
  v3 = 0;
  v4 = RegQueryInfoKeyA(a1, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
  if ( v4 )
    return ErrFromRegError(v4);
  v6 = cbMaxValueNameLen;
  if ( cbMaxSubKeyLen > cbMaxValueNameLen )
    v6 = cbMaxSubKeyLen;
  v7 = v6 + 1;
  cbMaxValueNameLen = v7;
  lpValueName = (LPSTR)malloc(v7);
  if ( !lpValueName )
    return 7;
  v8 = (BYTE *)malloc(cbMaxValueLen);
  lpData = v8;
  if ( v8 )
  {
    if ( cValues )
    {
      while ( 1 )
      {
        cchValueName = v7;
        v9 = lpValueName;
        cbData = cbMaxValueLen;
        v10 = RegEnumValueA(a1, v2, lpValueName, &cchValueName, 0, &Type, v8, &cbData);
        if ( !v10 )
          v10 = RegSetValueExA(a2, v9, 0, Type, lpData, cbData);
        if ( !v3 )
          v3 = ErrFromRegError(v10);
        v8 = lpData;
        if ( ++v2 >= cValues )
          break;
        v7 = cbMaxValueNameLen;
      }
    }
    free(v8);
    v11 = 0;
    for ( cbData = 0; v11 < cSubKeys; cbData = v11 )
    {
      v12 = RegEnumKeyA(a1, v11, lpValueName, cbMaxValueNameLen);
      if ( !v12 )
      {
        v13 = v24;
        v12 = FastRegCreateKey(a2, lpValueName, &v24);
        v14 = v24;
        if ( v12 )
          v14 = v13;
        v24 = v14;
        if ( !v12 )
        {
          v15 = phkResult;
          v16 = RegOpenKeyA(a1, lpValueName, &phkResult);
          v17 = phkResult;
          v12 = v16;
          if ( v16 )
            v17 = v15;
          phkResult = v17;
          if ( !v16 )
          {
            v18 = _ErrRegCopyTree(v17, v24);
            if ( !v3 )
              v3 = v18;
            RegCloseKey(phkResult);
          }
          RegCloseKey(v24);
        }
        v11 = cbData;
      }
      if ( !v3 )
        v3 = ErrFromRegError(v12);
      ++v11;
    }
  }
  else
  {
    v3 = 7;
  }
  free(lpValueName);
  return v3;
}

```

## disassembly

```asm
0x1800646cc  mov     [rsp-8+arg_8], rdx
0x1800646d1  mov     [rsp-8+hKey], rcx
0x1800646d6  push    rbp
0x1800646d7  push    rbx
0x1800646d8  push    rsi
0x1800646d9  push    rdi
0x1800646da  lea     rbp, [rsp-3Fh]
0x1800646df  mov     eax, 0A8h
0x1800646e4  call    _alloca_probe
0x1800646e9  sub     rsp, rax
0x1800646ec  mov     rax, rcx
0x1800646ef  xor     esi, esi
0x1800646f1  lea     rcx, [rbp+57h+cbMaxValueLen]
0x1800646f5  mov     [rsp+0C0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x1800646fa  mov     [rsp+0C0h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x1800646ff  mov     [rsp+0C0h+lpcbMaxValueLen], rcx; lpcbMaxValueLen
0x180064704  lea     rcx, [rbp+57h+cbMaxValueNameLen]
0x180064708  xor     r9d, r9d; lpReserved
0x18006470b  xor     r8d, r8d; lpcchClass
0x18006470e  mov     [rsp+0C0h+lpcbMaxValueNameLen], rcx; lpcbMaxValueNameLen
0x180064713  lea     rcx, [rbp+57h+cValues]
0x180064717  xor     edx, edx; lpClass
0x180064719  mov     [rsp+0C0h+lpcValues], rcx; lpcValues
0x18006471e  lea     rcx, [rbp+57h+cbMaxSubKeyLen]
0x180064722  mov     [rsp+0C0h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x180064727  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rcx; lpcbMaxSubKeyLen
0x18006472c  lea     rcx, [rbp+57h+cSubKeys]
0x180064730  mov     edi, esi
0x180064732  mov     [rsp+0C0h+lpcSubKeys], rcx; lpReserved
0x180064737  mov     rcx, rax; hKey
0x18006473a  call    cs:__imp_RegQueryInfoKeyA
0x180064740  test    eax, eax
0x180064742  jz      short loc_180064750
0x180064744  mov     ecx, eax; int
0x180064746  call    ?ErrFromRegError@@YAIJ@Z; ErrFromRegError(long)
0x18006474b  jmp     loc_1800648EE
0x180064750  mov     ebx, [rbp+57h+cbMaxValueNameLen]
0x180064753  cmp     [rbp+57h+cbMaxSubKeyLen], ebx
0x180064756  cmova   ebx, [rbp+57h+cbMaxSubKeyLen]
0x18006475a  inc     ebx
0x18006475c  mov     ecx, ebx; Size
0x18006475e  mov     [rbp+57h+cbMaxValueNameLen], ebx
0x180064761  call    cs:__imp_malloc
0x180064767  mov     [rbp+57h+lpValueName], rax
0x18006476b  test    rax, rax
0x18006476e  jnz     short loc_18006477A
0x180064770  mov     eax, 7
0x180064775  jmp     loc_1800648EE
0x18006477a  mov     ecx, [rbp+57h+cbMaxValueLen]; Size
0x18006477d  call    cs:__imp_malloc
0x180064783  mov     [rbp+57h+lpData], rax
0x180064787  test    rax, rax
0x18006478a  jnz     short loc_180064794
0x18006478c  lea     edi, [rax+7]
0x18006478f  jmp     loc_1800648E2
0x180064794  cmp     [rbp+57h+cValues], esi
0x180064797  jbe     loc_180064822
0x18006479d  mov     ecx, [rbp+57h+cbMaxValueLen]
0x1800647a0  mov     [rbp+57h+cchValueName], ebx
0x1800647a3  mov     rbx, [rbp+57h+lpValueName]
0x1800647a7  mov     [rbp+57h+cbData], ecx
0x1800647aa  lea     rcx, [rbp+57h+cbData]
0x1800647ae  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x1800647b2  mov     [rsp+0C0h+lpcValues], rcx; lpcbData
0x1800647b7  mov     rcx, [rbp+57h+hKey]; hKey
0x1800647bb  mov     [rsp+0C0h+lpcbMaxClassLen], rax; lpData
0x1800647c0  lea     rax, [rbp+57h+Type]
0x1800647c4  mov     r8, rbx; lpValueName
0x1800647c7  mov     edx, esi; dwIndex
0x1800647c9  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax; lpType
0x1800647ce  and     [rsp+0C0h+lpcSubKeys], 0
0x1800647d4  call    cs:__imp_RegEnumValueA
0x1800647da  test    eax, eax
0x1800647dc  jnz     short loc_180064802
0x1800647de  mov     eax, [rbp+57h+cbData]
0x1800647e1  mov     r9d, [rbp+57h+Type]; dwType
0x1800647e5  mov     rcx, [rbp+57h+arg_8]; hKey
0x1800647e9  mov     dword ptr [rsp+0C0h+lpcbMaxSubKeyLen], eax; cbData
0x1800647ed  mov     rax, [rbp+57h+lpData]
0x1800647f1  xor     r8d, r8d; Reserved
0x1800647f4  mov     rdx, rbx; lpValueName
0x1800647f7  mov     [rsp+0C0h+lpcSubKeys], rax; lpData
0x1800647fc  call    cs:__imp_RegSetValueExA
0x180064802  test    edi, edi
0x180064804  jnz     short loc_18006480F
0x180064806  mov     ecx, eax; int
0x180064808  call    ?ErrFromRegError@@YAIJ@Z; ErrFromRegError(long)
0x18006480d  mov     edi, eax
0x18006480f  mov     rax, [rbp+57h+lpData]
0x180064813  inc     esi
0x180064815  cmp     esi, [rbp+57h+cValues]
0x180064818  jnb     short loc_180064822
0x18006481a  mov     ebx, [rbp+57h+cbMaxValueNameLen]
0x18006481d  jmp     loc_18006479D
0x180064822  mov     rcx, rax; Block
0x180064825  call    cs:__imp_free
0x18006482b  xor     ebx, ebx
0x18006482d  mov     [rbp+57h+cbData], ebx
0x180064830  cmp     [rbp+57h+cSubKeys], ebx
0x180064833  jbe     loc_1800648E2
0x180064839  mov     r9d, [rbp+57h+cbMaxValueNameLen]; cchName
0x18006483d  mov     r8, [rbp+57h+lpValueName]; lpName
0x180064841  mov     rcx, [rbp+57h+hKey]; hKey
0x180064845  mov     edx, ebx; dwIndex
0x180064847  call    cs:__imp_RegEnumKeyA
0x18006484d  mov     esi, eax
0x18006484f  test    eax, eax
0x180064851  jnz     short loc_1800648C7
0x180064853  mov     rdx, [rbp+57h+lpValueName]; char *
0x180064857  mov     rcx, [rbp+57h+arg_8]; HKEY
0x18006485b  mov     rbx, [rbp+57h+var_48]
0x18006485f  lea     r8, [rbp+57h+var_48]; HKEY *
0x180064863  call    ?FastRegCreateKey@@YAJPEAUHKEY__@@PEBDPEAPEAU1@@Z; FastRegCreateKey(HKEY__ *,char const *,HKEY__ * *)
0x180064868  mov     esi, eax
0x18006486a  mov     rax, [rbp+57h+var_48]
0x18006486e  test    esi, esi
0x180064870  cmovnz  rax, rbx
0x180064874  mov     [rbp+57h+var_48], rax
0x180064878  jnz     short loc_1800648C4
0x18006487a  mov     rdx, [rbp+57h+lpValueName]; lpSubKey
0x18006487e  mov     rcx, [rbp+57h+hKey]; hKey
0x180064882  mov     rbx, [rbp+57h+phkResult]
0x180064886  lea     r8, [rbp+57h+phkResult]; phkResult
0x18006488a  call    cs:__imp_RegOpenKeyA
0x180064890  mov     rcx, [rbp+57h+phkResult]
0x180064894  test    eax, eax
0x180064896  mov     esi, eax
0x180064898  cmovnz  rcx, rbx; HKEY
0x18006489c  mov     [rbp+57h+phkResult], rcx
0x1800648a0  jnz     short loc_1800648BA
0x1800648a2  mov     rdx, [rbp+57h+var_48]; HKEY
0x1800648a6  call    ?_ErrRegCopyTree@@YAIPEAUHKEY__@@0@Z; _ErrRegCopyTree(HKEY__ *,HKEY__ *)
0x1800648ab  mov     rcx, [rbp+57h+phkResult]; hKey
0x1800648af  test    edi, edi
0x1800648b1  cmovz   edi, eax
0x1800648b4  call    cs:__imp_RegCloseKey
0x1800648ba  mov     rcx, [rbp+57h+var_48]; hKey
0x1800648be  call    cs:__imp_RegCloseKey
0x1800648c4  mov     ebx, [rbp+57h+cbData]
0x1800648c7  test    edi, edi
0x1800648c9  jnz     short loc_1800648D4
0x1800648cb  mov     ecx, esi; int
0x1800648cd  call    ?ErrFromRegError@@YAIJ@Z; ErrFromRegError(long)
0x1800648d2  mov     edi, eax
0x1800648d4  inc     ebx
0x1800648d6  mov     [rbp+57h+cbData], ebx
0x1800648d9  cmp     ebx, [rbp+57h+cSubKeys]
0x1800648dc  jb      loc_180064839
0x1800648e2  mov     rcx, [rbp+57h+lpValueName]; Block
0x1800648e6  call    cs:__imp_free
0x1800648ec  mov     eax, edi
0x1800648ee  add     rsp, 0A8h
0x1800648f5  pop     rdi
0x1800648f6  pop     rsi
0x1800648f7  pop     rbx
0x1800648f8  pop     rbp
0x1800648f9  retn
```
