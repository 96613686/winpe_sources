# VBAddInManager::LoadAddinsFromReg(HKEY__ *,HKEY__ *)

- ea: `0x1800a7a48`
- end: `0x1800a7f55`
- name: `?LoadAddinsFromReg@VBAddInManager@@AEAAJPEAUHKEY__@@0@Z`
- size: `1293`
- prototype: `__int64 __fastcall(VBAddInManager *__hidden this, HKEY, HKEY)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800a7704`

## callees

- `0x18001606c`
- `0x18005ab18`
- `0x1800a4b78`
- `0x1800a4d4c`
- `0x1800a73b0`
- `0x1800a7a48`
- `0x1800a7f5c`
- `0x1800a89b8`
- `0x180379380`
- `0x180379520`
- `0x180379546`

## import_xrefs

- `MSVCR100!strcpy_s` at `0x1800a7c18`
- `MSVCR100!strcpy_s` at `0x1800a7c18`
- `MSVCR100!free` at `0x1800a7ce7`
- `MSVCR100!free` at `0x1800a7d7a`
- `MSVCR100!free` at `0x1800a7dfb`
- `MSVCR100!free` at `0x1800a7e7c`
- `MSVCR100!free` at `0x1800a7f1f`
- `MSVCR100!free` at `0x1800a7ce7`
- `MSVCR100!free` at `0x1800a7d7a`
- `MSVCR100!free` at `0x1800a7dfb`
- `MSVCR100!free` at `0x1800a7e7c`
- `MSVCR100!free` at `0x1800a7f1f`
- `MSVCR100!malloc` at `0x1800a7a96`
- `MSVCR100!malloc` at `0x1800a7b52`
- `MSVCR100!malloc` at `0x1800a7c04`
- `MSVCR100!malloc` at `0x1800a7ca3`
- `MSVCR100!malloc` at `0x1800a7d3c`
- `MSVCR100!malloc` at `0x1800a7dbd`
- `MSVCR100!malloc` at `0x1800a7e3e`
- `MSVCR100!malloc` at `0x1800a7a96`
- `MSVCR100!malloc` at `0x1800a7b52`
- `MSVCR100!malloc` at `0x1800a7c04`
- `MSVCR100!malloc` at `0x1800a7ca3`
- `MSVCR100!malloc` at `0x1800a7d3c`
- `MSVCR100!malloc` at `0x1800a7dbd`
- `MSVCR100!malloc` at `0x1800a7e3e`
- `ADVAPI32!RegEnumKeyA` at `0x1800a7ab9`
- `ADVAPI32!RegEnumKeyA` at `0x1800a7f05`
- `ADVAPI32!RegEnumKeyA` at `0x1800a7ab9`
- `ADVAPI32!RegEnumKeyA` at `0x1800a7f05`
- `ADVAPI32!RegOpenKeyExA` at `0x1800a7bb7`
- `ADVAPI32!RegOpenKeyExA` at `0x1800a7bb7`
- `ADVAPI32!RegQueryValueExA` at `0x1800a7c48`
- `ADVAPI32!RegQueryValueExA` at `0x1800a7c89`
- `ADVAPI32!RegQueryValueExA` at `0x1800a7ccc`
- `ADVAPI32!RegQueryValueExA` at `0x1800a7d22`
- `ADVAPI32!RegQueryValueExA` at `0x1800a7d65`
- `ADVAPI32!RegQueryValueExA` at `0x1800a7da3`
- `ADVAPI32!RegQueryValueExA` at `0x1800a7de6`
- `ADVAPI32!RegQueryValueExA` at `0x1800a7e24`
- `ADVAPI32!RegQueryValueExA` at `0x1800a7e67`
- `ADVAPI32!RegQueryValueExA` at `0x1800a7eb0`
- `ADVAPI32!RegQueryValueExA` at `0x1800a7c48`
- `ADVAPI32!RegQueryValueExA` at `0x1800a7c89`
- `ADVAPI32!RegQueryValueExA` at `0x1800a7ccc`
- `ADVAPI32!RegQueryValueExA` at `0x1800a7d22`
- `ADVAPI32!RegQueryValueExA` at `0x1800a7d65`
- `ADVAPI32!RegQueryValueExA` at `0x1800a7da3`
- `ADVAPI32!RegQueryValueExA` at `0x1800a7de6`
- `ADVAPI32!RegQueryValueExA` at `0x1800a7e24`
- `ADVAPI32!RegQueryValueExA` at `0x1800a7e67`
- `ADVAPI32!RegQueryValueExA` at `0x1800a7eb0`

## string_xrefs

- `0x1800a7d8c`: `SatelliteDllName`
- `0x1800a7dc7`: `SatelliteDllName`
- `0x1800a7e0d`: `SatelliteDllPath`
- `0x1800a7e48`: `SatelliteDllPath`
- `0x1800a7e8e`: `CommandLineSafe`

## pseudocode

```c
__int64 __fastcall VBAddInManager::LoadAddinsFromReg(VBAddInManager *this, HKEY a2, HKEY a3)
{
  DWORD v4; // r12d
  CHAR *v6; // rax
  char *v7; // rsi
  LSTATUS v9; // eax
  int i; // ebx
  __int64 v11; // rax
  unsigned __int64 v12; // rax
  __int64 v13; // rcx
  unsigned __int64 v14; // rcx
  void *v15; // rsp
  void *v16; // rsp
  wchar_t *v17; // rax
  unsigned int v18; // eax
  void *v19; // rdi
  _QWORD *v20; // rax
  _QWORD *v21; // rbx
  VBAddIn *v22; // rdi
  LSTATUS v23; // eax
  HKEY v24; // rax
  __int64 v25; // rbx
  char *v26; // rax
  LSTATUS v27; // eax
  LSTATUS v28; // eax
  int v29; // ebx
  DWORD v30; // ecx
  BYTE *v31; // rax
  LSTATUS v32; // eax
  LSTATUS v33; // eax
  BYTE *v34; // rax
  LSTATUS v35; // eax
  LSTATUS v36; // eax
  BYTE *v37; // rax
  LSTATUS v38; // eax
  LSTATUS v39; // eax
  BYTE *v40; // rax
  LSTATUS v41; // eax
  LSTATUS v42; // eax
  LSTATUS v43; // eax
  DWORD cbData; // [rsp+30h] [rbp+0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp+8h] BYREF
  HKEY v46; // [rsp+40h] [rbp+10h]

  v4 = 0;
  hKey = 0;
  v46 = a2;
  v6 = (CHAR *)malloc(0x800u);
  v7 = v6;
  if ( !v6 )
    return 2147942414LL;
  v9 = RegEnumKeyA(a3, 0, v6, 0x800u);
  for ( i = HrFromRegError(v9); i >= 0; i = HrFromRegError(v43) )
  {
    ++v4;
    if ( (unsigned __int64)v7 >> 16 )
    {
      v11 = -1;
      do
        ++v11;
      while ( v7[v11] );
      v12 = 2 * v11 + 2;
      v13 = v12 + 15;
      if ( v12 + 15 < v12 )
        v13 = 0xFFFFFFFFFFFFFF0LL;
      v14 = v13 & 0xFFFFFFFFFFFFFFF0uLL;
      v15 = alloca(v14);
      v16 = alloca(v14);
      v17 = strcpyWfromA((wchar_t *)&cbData, v7);
    }
    else
    {
      v17 = (wchar_t *)v7;
    }
    v18 = HashName(v17);
    if ( !(unsigned int)VBAddInManager::AddName(this, v7, v18) )
      goto LABEL_48;
    v19 = g_hHeapPrimary;
    v20 = malloc(0xA8u);
    v21 = v20;
    if ( v20 )
      memset_0(v20, 0, 0xA8u);
    if ( !v21 || (*v21 = v19, v21 == (_QWORD *)-8LL) )
      v22 = 0;
    else
      v22 = VBAddIn::VBAddIn((VBAddIn *)(v21 + 1), this);
    if ( !v22 )
      return 2147942414LL;
    v23 = RegOpenKeyExA(a3, v7, 0, 0x20019u, &hKey);
    i = HrFromRegError(v23);
    if ( i < 0 )
      break;
    v24 = v46;
    *((_QWORD *)v22 + 19) = v46;
    if ( v24 == HKEY_LOCAL_MACHINE && !*((_DWORD *)this + 91) )
      VBAddInManager::CheckHKLMReadOnly(this);
    v25 = -1;
    do
      ++v25;
    while ( v7[v25] );
    v26 = (char *)malloc(v25 + 1);
    *((_QWORD *)v22 + 9) = v26;
    strcpy_s(v26, v25 + 1, v7);
    cbData = 4;
    v27 = RegQueryValueExA(hKey, "LoadBehavior", 0, 0, (LPBYTE)v22 + 40, &cbData);
    HrFromRegError(v27);
    *((_DWORD *)v22 + 10) &= ~2u;
    if ( *((_DWORD *)v22 + 10) == 2 || *((_DWORD *)v22 + 10) == 3 )
      *((_DWORD *)v22 + 30) = 1;
    v28 = RegQueryValueExA(hKey, "FriendlyName", 0, 0, 0, &cbData);
    v29 = HrFromRegError(v28);
    if ( v29 >= 0 )
    {
      v30 = cbData;
      if ( cbData )
      {
        v31 = (BYTE *)malloc(cbData);
        *((_QWORD *)v22 + 10) = v31;
        v32 = RegQueryValueExA(hKey, "FriendlyName", 0, 0, v31, &cbData);
        v29 = HrFromRegError(v32);
        if ( v29 >= 0 )
        {
          v30 = cbData;
LABEL_33:
          if ( v30 )
            goto LABEL_35;
          goto LABEL_34;
        }
        free(*((void **)v22 + 10));
        v30 = cbData;
      }
      if ( v29 >= 0 )
        goto LABEL_33;
    }
LABEL_34:
    *((_QWORD *)v22 + 10) = *((_QWORD *)v22 + 9);
LABEL_35:
    v33 = RegQueryValueExA(hKey, "Description", 0, 0, 0, &cbData);
    if ( (int)HrFromRegError(v33) >= 0 )
    {
      if ( cbData )
      {
        v34 = (BYTE *)malloc(cbData);
        *((_QWORD *)v22 + 11) = v34;
        v35 = RegQueryValueExA(hKey, "Description", 0, 0, v34, &cbData);
        if ( (int)HrFromRegError(v35) < 0 )
        {
          free(*((void **)v22 + 11));
          *((_QWORD *)v22 + 11) = 0;
        }
      }
    }
    v36 = RegQueryValueExA(hKey, "SatelliteDllName", 0, 0, 0, &cbData);
    if ( (int)HrFromRegError(v36) >= 0 )
    {
      if ( cbData )
      {
        v37 = (BYTE *)malloc(cbData);
        *((_QWORD *)v22 + 13) = v37;
        v38 = RegQueryValueExA(hKey, "SatelliteDllName", 0, 0, v37, &cbData);
        if ( (int)HrFromRegError(v38) < 0 )
        {
          free(*((void **)v22 + 13));
          *((_QWORD *)v22 + 13) = 0;
        }
      }
    }
    v39 = RegQueryValueExA(hKey, "SatelliteDllPath", 0, 0, 0, &cbData);
    if ( (int)HrFromRegError(v39) >= 0 && cbData )
    {
      v40 = (BYTE *)malloc(cbData);
      *((_QWORD *)v22 + 12) = v40;
      v41 = RegQueryValueExA(hKey, "SatelliteDllPath", 0, 0, v40, &cbData);
      if ( (int)HrFromRegError(v41) < 0 )
      {
        free(*((void **)v22 + 12));
        *((_QWORD *)v22 + 12) = 0;
      }
    }
    cbData = 4;
    v42 = RegQueryValueExA(hKey, "CommandLineSafe", 0, 0, (LPBYTE)v22 + 124, &cbData);
    HrFromRegError(v42);
    *((_DWORD *)v22 + 32) = 1;
    *((_DWORD *)v22 + 33) = 1;
    *((_DWORD *)v22 + 34) = 1;
    *((_DWORD *)v22 + 35) = 1;
    (*(void (__fastcall **)(char *, VBAddIn *))(*((_QWORD *)this + 39) + 8LL))((char *)this + 312, v22);
    CVBAddIn::Create(v22, (struct CVBAddIn **)v22 + 4);
LABEL_48:
    v43 = RegEnumKeyA(a3, v4, v7, 0x800u);
  }
  free(v7);
  return (unsigned int)i;
}

```

## disassembly

```asm
0x1800a7a48  push    rbp
0x1800a7a4a  push    r12
0x1800a7a4c  push    r13
0x1800a7a4e  push    r14
0x1800a7a50  push    r15
0x1800a7a52  mov     eax, 50h
0x1800a7a57  call    _alloca_probe
0x1800a7a5c  sub     rsp, rax
0x1800a7a5f  lea     rbp, [rsp+30h]
0x1800a7a64  mov     [rbp+40h+arg_0], rbx
0x1800a7a68  mov     [rbp+40h+arg_8], rsi
0x1800a7a6c  mov     [rbp+40h+arg_10], rdi
0x1800a7a70  mov     rax, cs:__security_cookie
0x1800a7a77  xor     rax, rbp
0x1800a7a7a  mov     [rbp+40h+var_28], rax
0x1800a7a7e  mov     r14, rcx
0x1800a7a81  mov     ebx, 800h
0x1800a7a86  xor     r12d, r12d
0x1800a7a89  and     [rbp+40h+hKey], r12
0x1800a7a8d  mov     ecx, ebx; Size
0x1800a7a8f  mov     r13, r8
0x1800a7a92  mov     [rbp+40h+var_30], rdx
0x1800a7a96  call    cs:__imp_malloc
0x1800a7a9c  mov     rsi, rax
0x1800a7a9f  test    rax, rax
0x1800a7aa2  jnz     short loc_1800A7AAE
0x1800a7aa4  mov     eax, 8007000Eh
0x1800a7aa9  jmp     loc_1800A7F27
0x1800a7aae  mov     r9d, ebx; cchName
0x1800a7ab1  mov     r8, rax; lpName
0x1800a7ab4  xor     edx, edx; dwIndex
0x1800a7ab6  mov     rcx, r13; hKey
0x1800a7ab9  call    cs:__imp_RegEnumKeyA
0x1800a7abf  mov     ecx, eax; int
0x1800a7ac1  call    ?HrFromRegError@@YAJJ@Z; HrFromRegError(long)
0x1800a7ac6  mov     ebx, eax
0x1800a7ac8  test    eax, eax
0x1800a7aca  js      loc_1800A7F1C
0x1800a7ad0  mov     r15, rsi
0x1800a7ad3  shr     r15, 10h
0x1800a7ad7  inc     r12d
0x1800a7ada  test    r15, r15
0x1800a7add  jz      short loc_1800A7B25
0x1800a7adf  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a7ae3  inc     rax
0x1800a7ae6  cmp     byte ptr [rsi+rax], 0
0x1800a7aea  jnz     short loc_1800A7AE3
0x1800a7aec  lea     rax, ds:2[rax*2]
0x1800a7af4  lea     rcx, [rax+0Fh]
0x1800a7af8  cmp     rcx, rax
0x1800a7afb  ja      short loc_1800A7B07
0x1800a7afd  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800a7b07  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800a7b0b  mov     rax, rcx
0x1800a7b0e  call    _alloca_probe
0x1800a7b13  sub     rsp, rcx
0x1800a7b16  mov     rdx, rsi; char *
0x1800a7b19  lea     rcx, [rsp+70h+cbData]; wchar_t *
0x1800a7b1e  call    ?strcpyWfromA@@YAPEA_WPEA_WPEBD@Z; strcpyWfromA(wchar_t *,char const *)
0x1800a7b23  jmp     short loc_1800A7B28
0x1800a7b25  mov     rax, rsi
0x1800a7b28  mov     rcx, rax; wchar_t *
0x1800a7b2b  call    ?HashName@@YAKPEA_W@Z; HashName(wchar_t *)
0x1800a7b30  mov     rdx, rsi; char *
0x1800a7b33  mov     rcx, r14; this
0x1800a7b36  mov     r8d, eax; unsigned int
0x1800a7b39  call    ?AddName@VBAddInManager@@AEAAHPEADK@Z; VBAddInManager::AddName(char *,ulong)
0x1800a7b3e  test    eax, eax
0x1800a7b40  jz      loc_1800A7EF6
0x1800a7b46  mov     rdi, cs:?g_hHeapPrimary@@3PEAXEA; void * g_hHeapPrimary
0x1800a7b4d  mov     ecx, 0A8h; Size
0x1800a7b52  call    cs:__imp_malloc
0x1800a7b58  mov     rbx, rax
0x1800a7b5b  test    rax, rax
0x1800a7b5e  jz      short loc_1800A7B70
0x1800a7b60  xor     edx, edx; Val
0x1800a7b62  mov     r8d, 0A8h; Size
0x1800a7b68  mov     rcx, rax; void *
0x1800a7b6b  call    memset_0
0x1800a7b70  test    rbx, rbx
0x1800a7b73  jz      short loc_1800A7B94
0x1800a7b75  lea     rcx, [rbx+8]; this
0x1800a7b79  mov     [rbx], rdi
0x1800a7b7c  test    rcx, rcx
0x1800a7b7f  jz      short loc_1800A7B94
0x1800a7b81  mov     r8d, 1
0x1800a7b87  mov     rdx, r14; struct VBAddInManager *
0x1800a7b8a  call    ??0VBAddIn@@QEAA@PEAVVBAddInManager@@@Z; VBAddIn::VBAddIn(VBAddInManager *)
0x1800a7b8f  mov     rdi, rax
0x1800a7b92  jmp     short loc_1800A7B96
0x1800a7b94  xor     edi, edi
0x1800a7b96  test    rdi, rdi
0x1800a7b99  jz      loc_1800A7AA4
0x1800a7b9f  lea     rax, [rbp+40h+hKey]
0x1800a7ba3  mov     r9d, 20019h; samDesired
0x1800a7ba9  xor     r8d, r8d; ulOptions
0x1800a7bac  mov     rdx, rsi; lpSubKey
0x1800a7baf  mov     rcx, r13; hKey
0x1800a7bb2  mov     [rsp+70h+phkResult], rax; phkResult
0x1800a7bb7  call    cs:__imp_RegOpenKeyExA
0x1800a7bbd  mov     ecx, eax; int
0x1800a7bbf  call    ?HrFromRegError@@YAJJ@Z; HrFromRegError(long)
0x1800a7bc4  mov     ebx, eax
0x1800a7bc6  test    eax, eax
0x1800a7bc8  js      loc_1800A7F1C
0x1800a7bce  mov     rax, [rbp+40h+var_30]
0x1800a7bd2  mov     [rdi+98h], rax
0x1800a7bd9  cmp     rax, 0FFFFFFFF80000002h
0x1800a7bdf  jnz     short loc_1800A7BF3
0x1800a7be1  cmp     dword ptr [r14+16Ch], 0
0x1800a7be9  jnz     short loc_1800A7BF3
0x1800a7beb  mov     rcx, r14; this
0x1800a7bee  call    ?CheckHKLMReadOnly@VBAddInManager@@QEAAXXZ; VBAddInManager::CheckHKLMReadOnly(void)
0x1800a7bf3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800a7bf7  inc     rbx
0x1800a7bfa  cmp     byte ptr [rsi+rbx], 0
0x1800a7bfe  jnz     short loc_1800A7BF7
0x1800a7c00  lea     rcx, [rbx+1]; Size
0x1800a7c04  call    cs:__imp_malloc
0x1800a7c0a  lea     rdx, [rbx+1]; SizeInBytes
0x1800a7c0e  mov     r8, rsi; Source
0x1800a7c11  mov     rcx, rax; Destination
0x1800a7c14  mov     [rdi+48h], rax
0x1800a7c18  call    cs:__imp_strcpy_s
0x1800a7c1e  mov     rcx, [rbp+40h+hKey]; hKey
0x1800a7c22  lea     rax, [rbp+40h+cbData]
0x1800a7c26  mov     [rsp+70h+lpcbData], rax; lpcbData
0x1800a7c2b  lea     rbx, [rdi+28h]
0x1800a7c2f  lea     rdx, aLoadbehavior; "LoadBehavior"
0x1800a7c36  xor     r9d, r9d; lpType
0x1800a7c39  xor     r8d, r8d; lpReserved
0x1800a7c3c  mov     [rbp+40h+cbData], 4
0x1800a7c43  mov     [rsp+70h+phkResult], rbx; lpData
0x1800a7c48  call    cs:__imp_RegQueryValueExA
0x1800a7c4e  mov     ecx, eax; int
0x1800a7c50  call    ?HrFromRegError@@YAJJ@Z; HrFromRegError(long)
0x1800a7c55  and     dword ptr [rbx], 0FFFFFFFDh
0x1800a7c58  cmp     dword ptr [rbx], 2
0x1800a7c5b  jz      short loc_1800A7C62
0x1800a7c5d  cmp     dword ptr [rbx], 3
0x1800a7c60  jnz     short loc_1800A7C69
0x1800a7c62  mov     dword ptr [rdi+78h], 1
0x1800a7c69  mov     rcx, [rbp+40h+hKey]; hKey
0x1800a7c6d  lea     rax, [rbp+40h+cbData]
0x1800a7c71  lea     rdx, aFriendlyname; "FriendlyName"
0x1800a7c78  mov     [rsp+70h+lpcbData], rax; lpcbData
0x1800a7c7d  and     [rsp+70h+phkResult], 0
0x1800a7c83  xor     r9d, r9d; lpType
0x1800a7c86  xor     r8d, r8d; lpReserved
0x1800a7c89  call    cs:__imp_RegQueryValueExA
0x1800a7c8f  mov     ecx, eax; int
0x1800a7c91  call    ?HrFromRegError@@YAJJ@Z; HrFromRegError(long)
0x1800a7c96  mov     ebx, eax
0x1800a7c98  test    eax, eax
0x1800a7c9a  js      short loc_1800A7CF9
0x1800a7c9c  mov     ecx, [rbp+40h+cbData]; Size
0x1800a7c9f  test    ecx, ecx
0x1800a7ca1  jz      short loc_1800A7CF0
0x1800a7ca3  call    cs:__imp_malloc
0x1800a7ca9  lea     rcx, [rbp+40h+cbData]
0x1800a7cad  lea     rdx, aFriendlyname; "FriendlyName"
0x1800a7cb4  mov     [rsp+70h+lpcbData], rcx; lpcbData
0x1800a7cb9  mov     [rdi+50h], rax
0x1800a7cbd  mov     rcx, [rbp+40h+hKey]; hKey
0x1800a7cc1  xor     r9d, r9d; lpType
0x1800a7cc4  xor     r8d, r8d; lpReserved
0x1800a7cc7  mov     [rsp+70h+phkResult], rax; lpData
0x1800a7ccc  call    cs:__imp_RegQueryValueExA
0x1800a7cd2  mov     ecx, eax; int
0x1800a7cd4  call    ?HrFromRegError@@YAJJ@Z; HrFromRegError(long)
0x1800a7cd9  mov     ebx, eax
0x1800a7cdb  test    eax, eax
0x1800a7cdd  jns     loc_1800A7F4D
0x1800a7ce3  mov     rcx, [rdi+50h]; Block
0x1800a7ce7  call    cs:__imp_free
0x1800a7ced  mov     ecx, [rbp+40h+cbData]
0x1800a7cf0  test    ebx, ebx
0x1800a7cf2  js      short loc_1800A7CF9
0x1800a7cf4  cmp     ecx, 1
0x1800a7cf7  jnb     short loc_1800A7D01
0x1800a7cf9  mov     rax, [rdi+48h]
0x1800a7cfd  mov     [rdi+50h], rax
0x1800a7d01  mov     rcx, [rbp+40h+hKey]; hKey
0x1800a7d05  lea     rax, [rbp+40h+cbData]
0x1800a7d09  lea     rdx, aDescription; "Description"
0x1800a7d10  mov     [rsp+70h+lpcbData], rax; lpcbData
0x1800a7d15  xor     ebx, ebx
0x1800a7d17  xor     r9d, r9d; lpType
0x1800a7d1a  xor     r8d, r8d; lpReserved
0x1800a7d1d  mov     [rsp+70h+phkResult], rbx; lpData
0x1800a7d22  call    cs:__imp_RegQueryValueExA
0x1800a7d28  mov     ecx, eax; int
0x1800a7d2a  call    ?HrFromRegError@@YAJJ@Z; HrFromRegError(long)
0x1800a7d2f  test    eax, eax
0x1800a7d31  js      short loc_1800A7D84
0x1800a7d33  mov     eax, [rbp+40h+cbData]
0x1800a7d36  test    eax, eax
0x1800a7d38  jz      short loc_1800A7D84
0x1800a7d3a  mov     ecx, eax; Size
0x1800a7d3c  call    cs:__imp_malloc
0x1800a7d42  lea     rcx, [rbp+40h+cbData]
0x1800a7d46  lea     rdx, aDescription; "Description"
0x1800a7d4d  mov     [rsp+70h+lpcbData], rcx; lpcbData
0x1800a7d52  mov     [rdi+58h], rax
0x1800a7d56  mov     rcx, [rbp+40h+hKey]; hKey
0x1800a7d5a  xor     r9d, r9d; lpType
0x1800a7d5d  xor     r8d, r8d; lpReserved
0x1800a7d60  mov     [rsp+70h+phkResult], rax; lpData
0x1800a7d65  call    cs:__imp_RegQueryValueExA
0x1800a7d6b  mov     ecx, eax; int
0x1800a7d6d  call    ?HrFromRegError@@YAJJ@Z; HrFromRegError(long)
0x1800a7d72  test    eax, eax
0x1800a7d74  jns     short loc_1800A7D84
0x1800a7d76  mov     rcx, [rdi+58h]; Block
0x1800a7d7a  call    cs:__imp_free
0x1800a7d80  mov     [rdi+58h], rbx
0x1800a7d84  mov     rcx, [rbp+40h+hKey]; hKey
0x1800a7d88  lea     rax, [rbp+40h+cbData]
0x1800a7d8c  lea     rdx, aSatellitedllna; "SatelliteDllName"
0x1800a7d93  mov     [rsp+70h+lpcbData], rax; lpcbData
0x1800a7d98  xor     r9d, r9d; lpType
0x1800a7d9b  xor     r8d, r8d; lpReserved
0x1800a7d9e  mov     [rsp+70h+phkResult], rbx; lpData
0x1800a7da3  call    cs:__imp_RegQueryValueExA
0x1800a7da9  mov     ecx, eax; int
0x1800a7dab  call    ?HrFromRegError@@YAJJ@Z; HrFromRegError(long)
0x1800a7db0  test    eax, eax
0x1800a7db2  js      short loc_1800A7E05
0x1800a7db4  mov     eax, [rbp+40h+cbData]
0x1800a7db7  test    eax, eax
0x1800a7db9  jz      short loc_1800A7E05
0x1800a7dbb  mov     ecx, eax; Size
0x1800a7dbd  call    cs:__imp_malloc
0x1800a7dc3  lea     rcx, [rbp+40h+cbData]
0x1800a7dc7  lea     rdx, aSatellitedllna; "SatelliteDllName"
0x1800a7dce  mov     [rsp+70h+lpcbData], rcx; lpcbData
0x1800a7dd3  mov     [rdi+68h], rax
0x1800a7dd7  mov     rcx, [rbp+40h+hKey]; hKey
0x1800a7ddb  xor     r9d, r9d; lpType
0x1800a7dde  xor     r8d, r8d; lpReserved
0x1800a7de1  mov     [rsp+70h+phkResult], rax; lpData
0x1800a7de6  call    cs:__imp_RegQueryValueExA
0x1800a7dec  mov     ecx, eax; int
0x1800a7dee  call    ?HrFromRegError@@YAJJ@Z; HrFromRegError(long)
0x1800a7df3  test    eax, eax
0x1800a7df5  jns     short loc_1800A7E05
0x1800a7df7  mov     rcx, [rdi+68h]; Block
0x1800a7dfb  call    cs:__imp_free
0x1800a7e01  mov     [rdi+68h], rbx
0x1800a7e05  mov     rcx, [rbp+40h+hKey]; hKey
0x1800a7e09  lea     rax, [rbp+40h+cbData]
0x1800a7e0d  lea     rdx, aSatellitedllpa; "SatelliteDllPath"
0x1800a7e14  mov     [rsp+70h+lpcbData], rax; lpcbData
0x1800a7e19  xor     r9d, r9d; lpType
0x1800a7e1c  xor     r8d, r8d; lpReserved
0x1800a7e1f  mov     [rsp+70h+phkResult], rbx; lpData
0x1800a7e24  call    cs:__imp_RegQueryValueExA
0x1800a7e2a  mov     ecx, eax; int
0x1800a7e2c  call    ?HrFromRegError@@YAJJ@Z; HrFromRegError(long)
0x1800a7e31  test    eax, eax
0x1800a7e33  js      short loc_1800A7E86
0x1800a7e35  mov     eax, [rbp+40h+cbData]
0x1800a7e38  test    eax, eax
0x1800a7e3a  jz      short loc_1800A7E86
0x1800a7e3c  mov     ecx, eax; Size
0x1800a7e3e  call    cs:__imp_malloc
0x1800a7e44  lea     rcx, [rbp+40h+cbData]
0x1800a7e48  lea     rdx, aSatellitedllpa; "SatelliteDllPath"
0x1800a7e4f  mov     [rsp+70h+lpcbData], rcx; lpcbData
0x1800a7e54  mov     [rdi+60h], rax
0x1800a7e58  mov     rcx, [rbp+40h+hKey]; hKey
0x1800a7e5c  xor     r9d, r9d; lpType
0x1800a7e5f  xor     r8d, r8d; lpReserved
0x1800a7e62  mov     [rsp+70h+phkResult], rax; lpData
0x1800a7e67  call    cs:__imp_RegQueryValueExA
0x1800a7e6d  mov     ecx, eax; int
0x1800a7e6f  call    ?HrFromRegError@@YAJJ@Z; HrFromRegError(long)
0x1800a7e74  test    eax, eax
0x1800a7e76  jns     short loc_1800A7E86
0x1800a7e78  mov     rcx, [rdi+60h]; Block
0x1800a7e7c  call    cs:__imp_free
0x1800a7e82  mov     [rdi+60h], rbx
0x1800a7e86  lea     rcx, [rbp+40h+cbData]
0x1800a7e8a  lea     rax, [rdi+7Ch]
0x1800a7e8e  lea     rdx, aCommandlinesaf; "CommandLineSafe"
0x1800a7e95  mov     [rsp+70h+lpcbData], rcx; lpcbData
0x1800a7e9a  mov     rcx, [rbp+40h+hKey]; hKey
0x1800a7e9e  xor     r9d, r9d; lpType
0x1800a7ea1  xor     r8d, r8d; lpReserved
0x1800a7ea4  mov     [rbp+40h+cbData], 4
0x1800a7eab  mov     [rsp+70h+phkResult], rax; lpData
0x1800a7eb0  call    cs:__imp_RegQueryValueExA
0x1800a7eb6  mov     ecx, eax; int
0x1800a7eb8  call    ?HrFromRegError@@YAJJ@Z; HrFromRegError(long)
0x1800a7ebd  mov     eax, 1
0x1800a7ec2  lea     rcx, [r14+138h]
0x1800a7ec9  mov     [rdi+80h], eax
0x1800a7ecf  mov     [rdi+84h], eax
0x1800a7ed5  mov     [rdi+88h], eax
0x1800a7edb  mov     [rdi+8Ch], eax
  ... truncated ...
```
