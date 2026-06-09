# ApplicationVersionMatchingPlugin(int *,void *,_DB *,ulong,ulong,ushort const *,void *)

- ea: `0x18000b790`
- end: `0x18000bb8e`
- name: `?ApplicationVersionMatchingPlugin@@YAHPEAHPEAXPEAU_DB@@KKPEBG1@Z`
- size: `1022`
- prototype: `__int64 __fastcall(int *, void *, struct _DB *, unsigned int, unsigned int, const unsigned __int16 *, void *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting`

## callees

- `0x180001cf0`
- `0x1800020c0`
- `0x180002120`
- `0x180002874`
- `0x180002bb8`
- `0x18000b5fc`
- `0x18000b720`
- `0x18000b790`
- `0x18000be58`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000b8b4`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000b96a`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000b8b4`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000b96a`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000b83d`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000b8d0`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000b907`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000b83d`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000b8d0`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000b907`
- `ADVAPI32!RegEnumKeyW` at `0x18000b9d1`
- `ADVAPI32!RegEnumKeyW` at `0x18000baae`
- `ADVAPI32!RegEnumKeyW` at `0x18000b9d1`
- `ADVAPI32!RegEnumKeyW` at `0x18000baae`
- `ADVAPI32!RegQueryValueExW` at `0x18000ba5d`
- `ADVAPI32!RegQueryValueExW` at `0x18000bb3d`
- `ADVAPI32!RegQueryValueExW` at `0x18000ba5d`
- `ADVAPI32!RegQueryValueExW` at `0x18000bb3d`
- `ADVAPI32!RegCloseKey` at `0x18000ba97`
- `ADVAPI32!RegCloseKey` at `0x18000bac7`
- `ADVAPI32!RegCloseKey` at `0x18000ba97`
- `ADVAPI32!RegCloseKey` at `0x18000bac7`
- `ADVAPI32!RegOpenKeyExW` at `0x18000b9aa`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ba1e`
- `ADVAPI32!RegOpenKeyExW` at `0x18000b9aa`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ba1e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ApplicationVersionMatchingPlugin(
        int *a1,
        void *a2,
        struct _DB *a3,
        __int64 a4,
        unsigned int a5,
        const unsigned __int16 *a6)
{
  void *v6; // r14
  __int64 v7; // r8
  wchar_t **v8; // rbx
  const wchar_t *v9; // rcx
  wchar_t *v10; // rax
  int v11; // r13d
  unsigned __int64 v12; // r12
  unsigned int v13; // r15d
  unsigned __int64 v14; // rsi
  void *v15; // rax
  const wchar_t *v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rsi
  void *v19; // rax
  _WORD *v20; // rax
  DWORD i; // ebx
  BYTE *v22; // rax
  int v23; // ecx
  int v24; // edx
  __int64 j; // rbx
  HKEY phkResult; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbData; // [rsp+3Ch] [rbp-C4h] BYREF
  DWORD lpcbData[2]; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  int *v32; // [rsp+50h] [rbp-B0h]
  __int64 v33; // [rsp+58h] [rbp-A8h]
  wchar_t *Str[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v35; // [rsp+70h] [rbp-90h]
  unsigned __int64 v36; // [rsp+78h] [rbp-88h]
  BYTE Data[528]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Name[264]; // [rsp+290h] [rbp+190h] BYREF
  BYTE v39[2]; // [rsp+4A0h] [rbp+3A0h] BYREF

  v33 = -2;
  v32 = a1;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  *a1 = 0;
  v6 = operator new[](0x38u);
  *(_OWORD *)Str = 0;
  v35 = 0;
  v36 = 0;
  v7 = -1;
  do
    ++v7;
  while ( a6[v7] );
  std::wstring::_Construct<1,unsigned short const *>(Str, a6, v7);
  v8 = Str;
  if ( v36 > 7 )
    v8 = (wchar_t **)Str[0];
  phkResult = (HKEY)v8;
  v9 = (const wchar_t *)Str;
  if ( v36 > 7 )
    v9 = Str[0];
  v10 = wcschr(v9, 0x2Cu);
  v11 = 0;
  v12 = 20;
  v13 = 1;
  while ( 1 )
  {
    *(_QWORD *)lpcbData = v10;
    if ( !v10 || v11 >= 6 )
      break;
    *((_QWORD *)v6 + v11) = 0;
    v14 = (int)(((char *)v10 - (char *)v8) >> 1);
    v15 = operator new[](saturated_mul(v14 + 1, 2u));
    *((_QWORD *)v6 + v11) = v15;
    memset_0(v15, 0, 2 * v14 + 2);
    _o_wcsncpy_s(*((_QWORD *)v6 + v11), v14 + 1, phkResult, v14);
    v8 = (wchar_t **)(*(_QWORD *)lpcbData + 2LL);
    phkResult = (HKEY)(*(_QWORD *)lpcbData + 2LL);
    v10 = wcschr((const wchar_t *)(*(_QWORD *)lpcbData + 2LL), 0x2Cu);
    if ( v11 != 5 )
      v14 = v12;
    v12 = v14;
    ++v11;
  }
  v16 = (const wchar_t *)Str;
  if ( v36 > 7 )
    v16 = Str[0];
  v17 = ((char *)wcschr(v16, 0) - (char *)v8) >> 1;
  v18 = (int)v17;
  if ( v11 == 6 && (int)v17 > v12 )
    v12 = (int)v17;
  v19 = operator new[](saturated_mul((int)v17 + 1LL, 2u));
  *((_QWORD *)v6 + v11) = v19;
  memset_0(v19, 0, 2 * v18 + 2);
  _o_wcsncpy_s(*((_QWORD *)v6 + v11), v18 + 1, phkResult, v18);
  if ( v11 < 6 )
  {
    v20 = operator new(2u);
    *((_QWORD *)v6 + 6) = v20;
    *v20 = 0;
  }
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, *(LPCWSTR *)v6, 0, 8u, &hKey) )
  {
    for ( i = 0; !RegEnumKeyW(hKey, i, Name, 0x104u); ++i )
    {
      cbData = 0;
      lpcbData[0] = 0;
      Type = 0;
      phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
      *(_WORD *)Data = 0;
      *(_WORD *)v39 = 0;
      if ( RegOpenKeyExW(hKey, Name, 0, 0x20019u, &phkResult) )
        break;
      cbData = 520;
      lpcbData[0] = 520;
      RegQueryValueExW(phkResult, *((LPCWSTR *)v6 + 1), 0, &Type, Data, &cbData);
      v22 = Data;
      do
      {
        v23 = *(unsigned __int16 *)&v22[*((_QWORD *)v6 + 3) - (_QWORD)Data];
        v24 = *(unsigned __int16 *)v22 - v23;
        if ( v24 )
          break;
        v22 += 2;
      }
      while ( v23 );
      if ( !v24 )
      {
        if ( !RegQueryValueExW(phkResult, *((LPCWSTR *)v6 + 2), 0, &Type, v39, lpcbData)
          && Type == 1
          && versioncheck(
               v32,
               (unsigned __int16 *)v39,
               *((unsigned __int16 **)v6 + 4),
               *((unsigned __int16 **)v6 + 5),
               *((unsigned __int16 **)v6 + 6),
               v12) )
        {
          v13 = 0;
          goto LABEL_35;
        }
        break;
      }
      if ( phkResult != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
        RegCloseKey(phkResult);
    }
  }
  if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    RegCloseKey(hKey);
  for ( j = 0; j != 7; ++j )
    operator delete(*((void **)v6 + j));
  operator delete(v6);
LABEL_35:
  std::wstring::~wstring(Str);
  return v13;
}

```

## disassembly

```asm
0x18000b790  push    rbp
0x18000b792  push    rbx
0x18000b793  push    rsi
0x18000b794  push    rdi
0x18000b795  push    r12
0x18000b797  push    r13
0x18000b799  push    r14
0x18000b79b  push    r15
0x18000b79d  lea     rbp, [rsp-5C8h]
0x18000b7a5  sub     rsp, 6C8h
0x18000b7ac  mov     [rsp+700h+var_6A8], 0FFFFFFFFFFFFFFFEh
0x18000b7b5  mov     rax, cs:__security_cookie
0x18000b7bc  xor     rax, rsp
0x18000b7bf  mov     [rbp+600h+var_50], rax
0x18000b7c6  mov     [rsp+700h+var_6B0], rcx
0x18000b7cb  mov     rbx, [rbp+600h+arg_28]
0x18000b7d2  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000b7d6  mov     [rsp+700h+hKey], rdi
0x18000b7db  xor     esi, esi
0x18000b7dd  mov     [rcx], esi
0x18000b7df  lea     ecx, [rdi+39h]; unsigned __int64
0x18000b7e2  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000b7e7  mov     r14, rax
0x18000b7ea  xorps   xmm0, xmm0
0x18000b7ed  movups  xmmword ptr [rsp+700h+Str], xmm0
0x18000b7f2  mov     [rsp+700h+var_690], rsi
0x18000b7f7  mov     [rsp+700h+var_688], rsi
0x18000b7fc  mov     r8, rdi
0x18000b7ff  inc     r8
0x18000b802  cmp     [rbx+r8*2], si
0x18000b807  jnz     short loc_18000B7FF
0x18000b809  mov     rdx, rbx
0x18000b80c  lea     rcx, [rsp+700h+Str]
0x18000b811  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000b816  nop
0x18000b817  lea     rbx, [rsp+700h+Str]
0x18000b81c  cmp     [rsp+700h+var_688], 7
0x18000b822  cmova   rbx, [rsp+700h+Str]
0x18000b828  mov     [rsp+700h+var_6D0], rbx
0x18000b82d  lea     rcx, [rsp+700h+Str]
0x18000b832  cmova   rcx, [rsp+700h+Str]; Str
0x18000b838  mov     edx, 2Ch ; ','; Ch
0x18000b83d  call    cs:__imp_wcschr
0x18000b843  mov     r13d, esi
0x18000b846  mov     r12d, 14h
0x18000b84c  lea     r15d, [r12-13h]
0x18000b851  jmp     loc_18000B8E6
0x18000b856  cmp     r13d, 6
0x18000b85a  jge     loc_18000B8F4
0x18000b860  movsxd  rdi, r13d
0x18000b863  mov     [r14+rdi*8], rsi
0x18000b867  sub     rax, rbx
0x18000b86a  sar     rax, 1
0x18000b86d  movsxd  rsi, eax
0x18000b870  lea     rbx, [rsi+1]
0x18000b874  mov     eax, 2
0x18000b879  mul     rbx
0x18000b87c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000b883  cmovb   rax, rcx
0x18000b887  mov     rcx, rax; unsigned __int64
0x18000b88a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000b88f  mov     [r14+rdi*8], rax
0x18000b893  lea     r8, ds:2[rsi*2]; Size
0x18000b89b  xor     edx, edx; Val
0x18000b89d  mov     rcx, rax; void *
0x18000b8a0  call    memset_0
0x18000b8a5  mov     r9, rsi
0x18000b8a8  mov     r8, [rsp+700h+var_6D0]
0x18000b8ad  mov     rdx, rbx
0x18000b8b0  mov     rcx, [r14+rdi*8]
0x18000b8b4  call    cs:__imp__o_wcsncpy_s
0x18000b8ba  mov     rbx, qword ptr [rsp+700h+var_6C0]
0x18000b8bf  add     rbx, 2
0x18000b8c3  mov     [rsp+700h+var_6D0], rbx
0x18000b8c8  mov     edx, 2Ch ; ','; Ch
0x18000b8cd  mov     rcx, rbx; Str
0x18000b8d0  call    cs:__imp_wcschr
0x18000b8d6  cmp     r13d, 5
0x18000b8da  cmovnz  rsi, r12
0x18000b8de  mov     r12, rsi
0x18000b8e1  add     r13d, r15d
0x18000b8e4  xor     esi, esi
0x18000b8e6  test    rax, rax
0x18000b8e9  mov     qword ptr [rsp+700h+var_6C0], rax
0x18000b8ee  jnz     loc_18000B856
0x18000b8f4  lea     rcx, [rsp+700h+Str]
0x18000b8f9  cmp     [rsp+700h+var_688], 7
0x18000b8ff  cmova   rcx, [rsp+700h+Str]; Str
0x18000b905  xor     edx, edx; Ch
0x18000b907  call    cs:__imp_wcschr
0x18000b90d  sub     rax, rbx
0x18000b910  sar     rax, 1
0x18000b913  movsxd  rsi, eax
0x18000b916  cmp     r13d, 6
0x18000b91a  jnz     short loc_18000B923
0x18000b91c  cmp     rsi, r12
0x18000b91f  cmova   r12, rsi
0x18000b923  lea     rdi, [rsi+1]
0x18000b927  mov     eax, 2
0x18000b92c  mul     rdi
0x18000b92f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000b936  cmovb   rax, rcx
0x18000b93a  mov     rcx, rax; unsigned __int64
0x18000b93d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000b942  movsxd  rbx, r13d
0x18000b945  mov     [r14+rbx*8], rax
0x18000b949  lea     r8, ds:2[rsi*2]; Size
0x18000b951  xor     edx, edx; Val
0x18000b953  mov     rcx, rax; void *
0x18000b956  call    memset_0
0x18000b95b  mov     r9, rsi
0x18000b95e  mov     r8, [rsp+700h+var_6D0]
0x18000b963  mov     rdx, rdi
0x18000b966  mov     rcx, [r14+rbx*8]
0x18000b96a  call    cs:__imp__o_wcsncpy_s
0x18000b970  cmp     r13d, 6
0x18000b974  jge     short loc_18000B98B
0x18000b976  mov     ecx, 2; Size
0x18000b97b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b980  mov     [r14+30h], rax
0x18000b984  xor     edi, edi
0x18000b986  mov     [rax], di
0x18000b989  jmp     short loc_18000B98D
0x18000b98b  xor     edi, edi
0x18000b98d  lea     rax, [rsp+700h+hKey]
0x18000b992  mov     [rsp+700h+phkResult], rax; phkResult
0x18000b997  mov     r9d, 8; samDesired
0x18000b99d  xor     r8d, r8d; ulOptions
0x18000b9a0  mov     rdx, [r14]; lpSubKey
0x18000b9a3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000b9aa  call    cs:__imp_RegOpenKeyExW
0x18000b9b0  test    eax, eax
0x18000b9b2  jnz     loc_18000BABC
0x18000b9b8  mov     ebx, edi
0x18000b9ba  mov     r13d, 104h
0x18000b9c0  mov     r9d, r13d; cchName
0x18000b9c3  lea     r8, [rbp+600h+Name]; lpName
0x18000b9ca  xor     edx, edx; dwIndex
0x18000b9cc  mov     rcx, [rsp+700h+hKey]; hKey
0x18000b9d1  call    cs:__imp_RegEnumKeyW
0x18000b9d7  test    eax, eax
0x18000b9d9  jnz     loc_18000BABC
0x18000b9df  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000b9e3  mov     [rsp+700h+cbData], edi
0x18000b9e7  mov     [rsp+700h+var_6C0], edi
0x18000b9eb  mov     [rsp+700h+Type], edi
0x18000b9ef  mov     [rsp+700h+var_6D0], rsi
0x18000b9f4  mov     word ptr [rbp+600h+Data], di
0x18000b9f8  mov     word ptr [rbp+600h+var_260], di
0x18000b9ff  lea     rax, [rsp+700h+var_6D0]
0x18000ba04  mov     [rsp+700h+phkResult], rax; phkResult
0x18000ba09  mov     r9d, 20019h; samDesired
0x18000ba0f  xor     r8d, r8d; ulOptions
0x18000ba12  lea     rdx, [rbp+600h+Name]; lpSubKey
0x18000ba19  mov     rcx, [rsp+700h+hKey]; hKey
0x18000ba1e  call    cs:__imp_RegOpenKeyExW
0x18000ba24  test    eax, eax
0x18000ba26  jnz     loc_18000BABC
0x18000ba2c  mov     eax, 208h
0x18000ba31  mov     [rsp+700h+cbData], eax
0x18000ba35  mov     [rsp+700h+var_6C0], eax
0x18000ba39  lea     rax, [rsp+700h+cbData]
0x18000ba3e  mov     [rsp+700h+lpcbData], rax; lpcbData
0x18000ba43  lea     rax, [rbp+600h+Data]
0x18000ba47  mov     [rsp+700h+phkResult], rax; lpData
0x18000ba4c  lea     r9, [rsp+700h+Type]; lpType
0x18000ba51  xor     r8d, r8d; lpReserved
0x18000ba54  mov     rdx, [r14+8]; lpValueName
0x18000ba58  mov     rcx, [rsp+700h+var_6D0]; hKey
0x18000ba5d  call    cs:__imp_RegQueryValueExW
0x18000ba63  lea     rax, [rbp+600h+Data]
0x18000ba67  mov     r8, [r14+18h]
0x18000ba6b  sub     r8, rax
0x18000ba6e  movzx   edx, word ptr [rax]
0x18000ba71  movzx   ecx, word ptr [rax+r8]
0x18000ba76  sub     edx, ecx
0x18000ba78  jnz     short loc_18000BA82
0x18000ba7a  add     rax, 2
0x18000ba7e  test    ecx, ecx
0x18000ba80  jnz     short loc_18000BA6E
0x18000ba82  mov     rcx, [rsp+700h+var_6D0]; hKey
0x18000ba87  test    edx, edx
0x18000ba89  jz      loc_18000BB1B
0x18000ba8f  add     ebx, r15d
0x18000ba92  cmp     rcx, rsi
0x18000ba95  jz      short loc_18000BA9D
0x18000ba97  call    cs:__imp_RegCloseKey
0x18000ba9d  mov     r9d, r13d; cchName
0x18000baa0  lea     r8, [rbp+600h+Name]; lpName
0x18000baa7  mov     edx, ebx; dwIndex
0x18000baa9  mov     rcx, [rsp+700h+hKey]; hKey
0x18000baae  call    cs:__imp_RegEnumKeyW
0x18000bab4  test    eax, eax
0x18000bab6  jz      loc_18000B9E3
0x18000babc  mov     rcx, [rsp+700h+hKey]; hKey
0x18000bac1  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000bac5  jz      short loc_18000BACD
0x18000bac7  call    cs:__imp_RegCloseKey
0x18000bacd  mov     rbx, rdi
0x18000bad0  mov     rcx, [r14+rbx*8]; Block
0x18000bad4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000bad9  add     rbx, r15
0x18000badc  cmp     rbx, 7
0x18000bae0  jnz     short loc_18000BAD0
0x18000bae2  mov     rcx, r14; Block
0x18000bae5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000baea  nop
0x18000baeb  lea     rcx, [rsp+700h+Str]; void *
0x18000baf0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000baf5  mov     eax, r15d
0x18000baf8  mov     rcx, [rbp+600h+var_50]
0x18000baff  xor     rcx, rsp; StackCookie
0x18000bb02  call    __security_check_cookie
0x18000bb07  add     rsp, 6C8h
0x18000bb0e  pop     r15
0x18000bb10  pop     r14
0x18000bb12  pop     r13
0x18000bb14  pop     r12
0x18000bb16  pop     rdi
0x18000bb17  pop     rsi
0x18000bb18  pop     rbx
0x18000bb19  pop     rbp
0x18000bb1a  retn
0x18000bb1b  lea     rax, [rsp+700h+var_6C0]
0x18000bb20  mov     [rsp+700h+lpcbData], rax; lpcbData
0x18000bb25  lea     rax, [rbp+600h+var_260]
0x18000bb2c  mov     [rsp+700h+phkResult], rax; lpData
0x18000bb31  lea     r9, [rsp+700h+Type]; lpType
0x18000bb36  xor     r8d, r8d; lpReserved
0x18000bb39  mov     rdx, [r14+10h]; lpValueName
0x18000bb3d  call    cs:__imp_RegQueryValueExW
0x18000bb43  test    eax, eax
0x18000bb45  jnz     loc_18000BABC
0x18000bb4b  cmp     [rsp+700h+Type], r15d
0x18000bb50  jnz     loc_18000BABC
0x18000bb56  mov     [rsp+700h+lpcbData], r12; unsigned __int64
0x18000bb5b  mov     rax, [r14+30h]
0x18000bb5f  mov     [rsp+700h+phkResult], rax; unsigned __int16 *
0x18000bb64  mov     r9, [r14+28h]; unsigned __int16 *
0x18000bb68  mov     r8, [r14+20h]; unsigned __int16 *
0x18000bb6c  lea     rdx, [rbp+600h+var_260]; unsigned __int16 *
0x18000bb73  mov     rcx, [rsp+700h+var_6B0]; int *
0x18000bb78  call    ?versioncheck@@YAJPEAHPEAG111_K@Z; versioncheck(int *,ushort *,ushort *,ushort *,ushort *,unsigned __int64)
0x18000bb7d  test    eax, eax
0x18000bb7f  jz      loc_18000BABC
0x18000bb85  mov     r15d, edi
0x18000bb88  jmp     loc_18000BAEB
```
