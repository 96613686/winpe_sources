# VBAddInManager::LoadAllFromReg(void)

- ea: `0x1800a7704`
- end: `0x1800a7a41`
- name: `?LoadAllFromReg@VBAddInManager@@AEAAJXZ`
- size: `829`
- prototype: `__int64 __fastcall(VBAddInManager *__hidden this)`
- caller_count: `5`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800a6d30`
- `0x1800a6e54`
- `0x1800a71e4`
- `0x1800a7440`
- `0x1800a8528`

## callees

- `0x180015ac0`
- `0x18001606c`
- `0x1800a7178`
- `0x1800a7704`
- `0x1800a7a48`
- `0x1800a8094`
- `0x1800a8204`
- `0x180379380`

## import_xrefs

- `MSVCR100!free` at `0x1800a78c5`
- `MSVCR100!free` at `0x1800a791d`
- `MSVCR100!free` at `0x1800a7953`
- `MSVCR100!free` at `0x1800a79d8`
- `MSVCR100!free` at `0x1800a7a04`
- `MSVCR100!free` at `0x1800a7a0d`
- `MSVCR100!free` at `0x1800a7a39`
- `MSVCR100!free` at `0x1800a78c5`
- `MSVCR100!free` at `0x1800a791d`
- `MSVCR100!free` at `0x1800a7953`
- `MSVCR100!free` at `0x1800a79d8`
- `MSVCR100!free` at `0x1800a7a04`
- `MSVCR100!free` at `0x1800a7a0d`
- `MSVCR100!free` at `0x1800a7a39`
- `MSVCR100!malloc` at `0x1800a7750`
- `MSVCR100!malloc` at `0x1800a7871`
- `MSVCR100!malloc` at `0x1800a7750`
- `MSVCR100!malloc` at `0x1800a7871`
- `KERNEL32!lstrlenA` at `0x1800a7858`
- `KERNEL32!lstrlenA` at `0x1800a7863`
- `KERNEL32!lstrlenA` at `0x1800a7858`
- `KERNEL32!lstrlenA` at `0x1800a7863`
- `USER32!wsprintfA` at `0x1800a7894`
- `USER32!wsprintfA` at `0x1800a7894`
- `ADVAPI32!RegOpenKeyExA` at `0x1800a78b6`
- `ADVAPI32!RegOpenKeyExA` at `0x1800a78b6`
- `ADVAPI32!RegQueryValueExA` at `0x1800a799d`
- `ADVAPI32!RegQueryValueExA` at `0x1800a799d`
- `ADVAPI32!RegOpenKeyA` at `0x1800a7792`
- `ADVAPI32!RegOpenKeyA` at `0x1800a77e5`
- `ADVAPI32!RegOpenKeyA` at `0x1800a7792`
- `ADVAPI32!RegOpenKeyA` at `0x1800a77e5`
- `ADVAPI32!RegCloseKey` at `0x1800a77ca`
- `ADVAPI32!RegCloseKey` at `0x1800a781b`
- `ADVAPI32!RegCloseKey` at `0x1800a79cf`
- `ADVAPI32!RegCloseKey` at `0x1800a77ca`
- `ADVAPI32!RegCloseKey` at `0x1800a781b`
- `ADVAPI32!RegCloseKey` at `0x1800a79cf`

## pseudocode

```c
__int64 __fastcall VBAddInManager::LoadAllFromReg(VBAddInManager *this)
{
  int v1; // ebx
  int SubKeyString; // esi
  void *v4; // rdi
  const CHAR *AddinRegLocation; // rax
  CHAR *v7; // r12
  HKEY v8; // rbx
  LSTATUS v9; // eax
  HKEY v10; // rcx
  __int64 i; // rdi
  HKEY v12; // rbx
  LSTATUS v13; // eax
  HKEY v14; // rcx
  __int64 v15; // rdi
  bool j; // zf
  int v17; // ebx
  int v18; // eax
  CHAR *v19; // rax
  CHAR *v20; // r15
  LSTATUS v21; // ebx
  __int64 v22; // rax
  __int64 v23; // rax
  char *v24; // rcx
  void *v25; // rcx
  void *v26; // rcx
  _DWORD *v27; // rbx
  HKEY hKey[3]; // [rsp+30h] [rbp-18h]
  DWORD cbData; // [rsp+90h] [rbp+48h] BYREF
  HKEY phkResult; // [rsp+98h] [rbp+50h] BYREF
  HKEY v31; // [rsp+A0h] [rbp+58h] BYREF
  void *v32; // [rsp+A8h] [rbp+60h]

  v1 = *((_DWORD *)this + 90);
  hKey[0] = HKEY_LOCAL_MACHINE;
  phkResult = 0;
  v31 = 0;
  SubKeyString = 0;
  hKey[1] = HKEY_CURRENT_USER;
  v4 = malloc(0x800u);
  v32 = v4;
  if ( !v4 )
    return 2147942414LL;
  AddinRegLocation = VBAddInManager::GetAddinRegLocation(this);
  v7 = (CHAR *)AddinRegLocation;
  if ( AddinRegLocation )
  {
    if ( !v1 )
    {
      for ( i = 0; i < 2; ++i )
      {
        v12 = phkResult;
        v13 = RegOpenKeyA(hKey[i], v7, &phkResult);
        v14 = phkResult;
        if ( v13 )
          v14 = v12;
        phkResult = v14;
        SubKeyString = HrFromRegError(v13);
        if ( SubKeyString >= 0 )
        {
          VBAddInManager::LoadAddinsFromReg(this, hKey[i], phkResult);
          RegCloseKey(phkResult);
        }
      }
      goto LABEL_15;
    }
    v8 = phkResult;
    v9 = RegOpenKeyA(HKEY_CURRENT_USER, AddinRegLocation, &phkResult);
    v10 = phkResult;
    if ( v9 )
      v10 = v8;
    phkResult = v10;
    SubKeyString = HrFromRegError(v9);
    if ( SubKeyString >= 0 )
    {
      VBAddInManager::LoadAddinsFromReg(this, HKEY_CURRENT_USER, phkResult);
      RegCloseKey(phkResult);
LABEL_15:
      v15 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 39) + 32LL))((char *)this + 312);
      for ( j = v15 == 0; ; j = v15 == 0 )
      {
        if ( j )
        {
LABEL_41:
          v4 = v32;
          goto LABEL_42;
        }
        if ( !*(_DWORD *)(v15 + 140) )
          goto LABEL_38;
        v17 = lstrlenA(*(LPCSTR *)(v15 + 72));
        v18 = lstrlenA(v7);
        v19 = (CHAR *)malloc(v17 + v18 + 2);
        v20 = v19;
        if ( !v19 )
          goto LABEL_38;
        wsprintfA(v19, "%s\\%s", v7, *(const char **)(v15 + 72));
        v21 = RegOpenKeyExA(*(HKEY *)(v15 + 152), v20, 0, 0x20019u, &v31);
        if ( !v21 )
          break;
        free(v20);
        if ( v21 != 2 )
          goto LABEL_40;
        VBAddInManager::RemoveName(this, *(char **)(v15 + 72));
        v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 80LL))(v15);
        if ( v22 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 64LL))(v22, 1);
        v23 = *((_QWORD *)this + 39);
        v24 = (char *)this + 312;
LABEL_39:
        v15 = (*(__int64 (__fastcall **)(char *))(v23 + 32))(v24);
      }
      v25 = *(void **)(v15 + 80);
      if ( v25 && v25 != *(void **)(v15 + 72) )
        free(v25);
      *(_QWORD *)(v15 + 80) = 0;
      SubKeyString = VBAddInManager::GetSubKeyString(this, v31, "FriendlyName", (char **)(v15 + 80));
      if ( SubKeyString < 0 )
        goto LABEL_41;
      v26 = *(void **)(v15 + 88);
      if ( v26 )
      {
        free(v26);
        *(_QWORD *)(v15 + 88) = 0;
      }
      VBAddInManager::GetSubKeyString(this, v31, "Description", (char **)(v15 + 88));
      v27 = (_DWORD *)(v15 + 40);
      cbData = 4;
      if ( RegQueryValueExA(v31, "LoadBehavior", 0, 0, (LPBYTE)(v15 + 40), &cbData) )
      {
        free(v20);
LABEL_40:
        SubKeyString = -2147467259;
        goto LABEL_41;
      }
      if ( *(_QWORD *)(v15 + 48) )
        *v27 |= 2u;
      else
        *v27 &= ~2u;
      if ( *v27 == 2 || *v27 == 3 )
        *(_DWORD *)(v15 + 120) = 1;
      RegCloseKey(v31);
      free(v20);
LABEL_38:
      v23 = *(_QWORD *)v15;
      v24 = (char *)v15;
      goto LABEL_39;
    }
LABEL_42:
    free(v7);
  }
  free(v4);
  if ( SubKeyString == (unsigned int)_HrFromErr(0x150u) )
    return 0;
  return (unsigned int)SubKeyString;
}

```

## disassembly

```asm
0x1800a7704  push    rbp
0x1800a7706  push    rbx
0x1800a7707  push    rsi
0x1800a7708  push    rdi
0x1800a7709  push    r12
0x1800a770b  push    r13
0x1800a770d  push    r14
0x1800a770f  push    r15
0x1800a7711  mov     rbp, rsp
0x1800a7714  mov     eax, 48h
0x1800a7719  call    _alloca_probe
0x1800a771e  sub     rsp, rax
0x1800a7721  mov     ebx, [rcx+168h]
0x1800a7727  xor     r15d, r15d
0x1800a772a  mov     r14, rcx
0x1800a772d  mov     r13, 0FFFFFFFF80000001h
0x1800a7734  mov     ecx, 800h; Size
0x1800a7739  mov     [rbp+hKey], 0FFFFFFFF80000002h
0x1800a7741  mov     [rbp+phkResult], r15
0x1800a7745  mov     [rbp+arg_10], r15
0x1800a7749  mov     esi, r15d
0x1800a774c  mov     [rbp+var_10], r13
0x1800a7750  call    cs:__imp_malloc
0x1800a7756  mov     rdi, rax
0x1800a7759  mov     [rbp+arg_18], rax
0x1800a775d  test    rax, rax
0x1800a7760  jnz     short loc_1800A776C
0x1800a7762  mov     eax, 8007000Eh
0x1800a7767  jmp     loc_1800A7A25
0x1800a776c  mov     rcx, r14; this
0x1800a776f  call    ?GetAddinRegLocation@VBAddInManager@@QEAAPEADXZ; VBAddInManager::GetAddinRegLocation(void)
0x1800a7774  mov     r12, rax
0x1800a7777  test    rax, rax
0x1800a777a  jz      loc_1800A7A0A
0x1800a7780  test    ebx, ebx
0x1800a7782  jz      short loc_1800A77D2
0x1800a7784  mov     rbx, [rbp+phkResult]
0x1800a7788  lea     r8, [rbp+phkResult]; phkResult
0x1800a778c  mov     rdx, rax; lpSubKey
0x1800a778f  mov     rcx, r13; hKey
0x1800a7792  call    cs:__imp_RegOpenKeyA
0x1800a7798  mov     rcx, [rbp+phkResult]
0x1800a779c  test    eax, eax
0x1800a779e  cmovnz  rcx, rbx
0x1800a77a2  mov     [rbp+phkResult], rcx
0x1800a77a6  mov     ecx, eax; int
0x1800a77a8  call    ?HrFromRegError@@YAJJ@Z; HrFromRegError(long)
0x1800a77ad  mov     esi, eax
0x1800a77af  test    eax, eax
0x1800a77b1  js      loc_1800A7A01
0x1800a77b7  mov     r8, [rbp+phkResult]; HKEY
0x1800a77bb  mov     rdx, r13; HKEY
0x1800a77be  mov     rcx, r14; this
0x1800a77c1  call    ?LoadAddinsFromReg@VBAddInManager@@AEAAJPEAUHKEY__@@0@Z; VBAddInManager::LoadAddinsFromReg(HKEY__ *,HKEY__ *)
0x1800a77c6  mov     rcx, [rbp+phkResult]; hKey
0x1800a77ca  call    cs:__imp_RegCloseKey
0x1800a77d0  jmp     short loc_1800A782A
0x1800a77d2  mov     rdi, r15
0x1800a77d5  mov     rcx, [rbp+rdi*8+hKey]; hKey
0x1800a77da  mov     rbx, [rbp+phkResult]
0x1800a77de  lea     r8, [rbp+phkResult]; phkResult
0x1800a77e2  mov     rdx, r12; lpSubKey
0x1800a77e5  call    cs:__imp_RegOpenKeyA
0x1800a77eb  mov     rcx, [rbp+phkResult]
0x1800a77ef  test    eax, eax
0x1800a77f1  cmovnz  rcx, rbx
0x1800a77f5  mov     [rbp+phkResult], rcx
0x1800a77f9  mov     ecx, eax; int
0x1800a77fb  call    ?HrFromRegError@@YAJJ@Z; HrFromRegError(long)
0x1800a7800  mov     esi, eax
0x1800a7802  test    eax, eax
0x1800a7804  js      short loc_1800A7821
0x1800a7806  mov     r8, [rbp+phkResult]; HKEY
0x1800a780a  mov     rdx, [rbp+rdi*8+hKey]; HKEY
0x1800a780f  mov     rcx, r14; this
0x1800a7812  call    ?LoadAddinsFromReg@VBAddInManager@@AEAAJPEAUHKEY__@@0@Z; VBAddInManager::LoadAddinsFromReg(HKEY__ *,HKEY__ *)
0x1800a7817  mov     rcx, [rbp+phkResult]; hKey
0x1800a781b  call    cs:__imp_RegCloseKey
0x1800a7821  inc     rdi
0x1800a7824  cmp     rdi, 2
0x1800a7828  jl      short loc_1800A77D5
0x1800a782a  lea     r13, [r14+138h]
0x1800a7831  mov     rcx, r13
0x1800a7834  mov     rax, [r13+0]
0x1800a7838  call    qword ptr [rax+20h]
0x1800a783b  mov     rdi, rax
0x1800a783e  test    rax, rax
0x1800a7841  jz      loc_1800A79FD
0x1800a7847  cmp     [rdi+8Ch], r15d
0x1800a784e  jz      loc_1800A79E1
0x1800a7854  mov     rcx, [rdi+48h]; lpString
0x1800a7858  call    cs:__imp_lstrlenA
0x1800a785e  mov     rcx, r12; lpString
0x1800a7861  mov     ebx, eax
0x1800a7863  call    cs:__imp_lstrlenA
0x1800a7869  lea     ecx, [rax+2]
0x1800a786c  add     ecx, ebx
0x1800a786e  movsxd  rcx, ecx; Size
0x1800a7871  call    cs:__imp_malloc
0x1800a7877  mov     r15, rax
0x1800a787a  test    rax, rax
0x1800a787d  jz      loc_1800A79DE
0x1800a7883  mov     r9, [rdi+48h]
0x1800a7887  lea     rdx, aSS_1; "%s\\%s"
0x1800a788e  mov     r8, r12
0x1800a7891  mov     rcx, rax; LPSTR
0x1800a7894  call    cs:__imp_wsprintfA
0x1800a789a  mov     rcx, [rdi+98h]; hKey
0x1800a78a1  lea     r11, [rbp+arg_10]
0x1800a78a5  mov     r9d, 20019h; samDesired
0x1800a78ab  xor     r8d, r8d; ulOptions
0x1800a78ae  mov     rdx, r15; lpSubKey
0x1800a78b1  mov     [rsp+48h+var_28], r11; phkResult
0x1800a78b6  call    cs:__imp_RegOpenKeyExA
0x1800a78bc  mov     ebx, eax
0x1800a78be  test    eax, eax
0x1800a78c0  jz      short loc_1800A790B
0x1800a78c2  mov     rcx, r15; Block
0x1800a78c5  call    cs:__imp_free
0x1800a78cb  cmp     ebx, 2
0x1800a78ce  jnz     loc_1800A79F5
0x1800a78d4  mov     rdx, [rdi+48h]; char *
0x1800a78d8  mov     rcx, r14; this
0x1800a78db  call    ?RemoveName@VBAddInManager@@AEAAHPEAD@Z; VBAddInManager::RemoveName(char *)
0x1800a78e0  mov     r11, [rdi]
0x1800a78e3  mov     rcx, rdi
0x1800a78e6  call    qword ptr [r11+50h]
0x1800a78ea  xor     r15d, r15d
0x1800a78ed  test    rax, rax
0x1800a78f0  jz      short loc_1800A78FF
0x1800a78f2  mov     r8, [rax]
0x1800a78f5  lea     edx, [rbx-1]
0x1800a78f8  mov     rcx, rax
0x1800a78fb  call    qword ptr [r8+40h]
0x1800a78ff  mov     rax, [r13+0]
0x1800a7903  mov     rcx, r13
0x1800a7906  jmp     loc_1800A79E7
0x1800a790b  lea     rbx, [rdi+50h]
0x1800a790f  mov     rcx, [rbx]; Block
0x1800a7912  test    rcx, rcx
0x1800a7915  jz      short loc_1800A7923
0x1800a7917  cmp     rcx, [rdi+48h]
0x1800a791b  jz      short loc_1800A7923
0x1800a791d  call    cs:__imp_free
0x1800a7923  and     qword ptr [rbx], 0
0x1800a7927  mov     rdx, [rbp+arg_10]; HKEY
0x1800a792b  lea     r8, aFriendlyname; "FriendlyName"
0x1800a7932  mov     r9, rbx; char **
0x1800a7935  mov     rcx, r14; this
0x1800a7938  call    ?GetSubKeyString@VBAddInManager@@AEAAJPEAUHKEY__@@PEADAEAPEAD@Z; VBAddInManager::GetSubKeyString(HKEY__ *,char *,char * &)
0x1800a793d  mov     esi, eax
0x1800a793f  test    eax, eax
0x1800a7941  js      loc_1800A79FA
0x1800a7947  lea     rbx, [rdi+58h]
0x1800a794b  mov     rcx, [rbx]; Block
0x1800a794e  test    rcx, rcx
0x1800a7951  jz      short loc_1800A795D
0x1800a7953  call    cs:__imp_free
0x1800a7959  and     qword ptr [rbx], 0
0x1800a795d  mov     rdx, [rbp+arg_10]; HKEY
0x1800a7961  lea     r8, aDescription; "Description"
0x1800a7968  mov     r9, rbx; char **
0x1800a796b  mov     rcx, r14; this
0x1800a796e  call    ?GetSubKeyString@VBAddInManager@@AEAAJPEAUHKEY__@@PEADAEAPEAD@Z; VBAddInManager::GetSubKeyString(HKEY__ *,char *,char * &)
0x1800a7973  mov     rcx, [rbp+arg_10]; hKey
0x1800a7977  lea     rax, [rbp+cbData]
0x1800a797b  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800a7980  lea     rbx, [rdi+28h]
0x1800a7984  lea     rdx, aLoadbehavior; "LoadBehavior"
0x1800a798b  xor     r9d, r9d; lpType
0x1800a798e  xor     r8d, r8d; lpReserved
0x1800a7991  mov     [rbp+cbData], 4
0x1800a7998  mov     [rsp+48h+var_28], rbx; lpData
0x1800a799d  call    cs:__imp_RegQueryValueExA
0x1800a79a3  test    eax, eax
0x1800a79a5  jnz     loc_1800A7A36
0x1800a79ab  cmp     qword ptr [rdi+30h], 0
0x1800a79b0  jz      short loc_1800A79B7
0x1800a79b2  or      dword ptr [rbx], 2
0x1800a79b5  jmp     short loc_1800A79BA
0x1800a79b7  and     dword ptr [rbx], 0FFFFFFFDh
0x1800a79ba  cmp     dword ptr [rbx], 2
0x1800a79bd  jz      short loc_1800A79C4
0x1800a79bf  cmp     dword ptr [rbx], 3
0x1800a79c2  jnz     short loc_1800A79CB
0x1800a79c4  mov     dword ptr [rdi+78h], 1
0x1800a79cb  mov     rcx, [rbp+arg_10]; hKey
0x1800a79cf  call    cs:__imp_RegCloseKey
0x1800a79d5  mov     rcx, r15; Block
0x1800a79d8  call    cs:__imp_free
0x1800a79de  xor     r15d, r15d
0x1800a79e1  mov     rax, [rdi]
0x1800a79e4  mov     rcx, rdi
0x1800a79e7  call    qword ptr [rax+20h]
0x1800a79ea  mov     rdi, rax
0x1800a79ed  test    rax, rax
0x1800a79f0  jmp     loc_1800A7841
0x1800a79f5  mov     esi, 80004005h
0x1800a79fa  xor     r15d, r15d
0x1800a79fd  mov     rdi, [rbp+arg_18]
0x1800a7a01  mov     rcx, r12; Block
0x1800a7a04  call    cs:__imp_free
0x1800a7a0a  mov     rcx, rdi; Block
0x1800a7a0d  call    cs:__imp_free
0x1800a7a13  mov     ecx, 150h; unsigned int
0x1800a7a18  call    ?_HrFromErr@@YAJI@Z; _HrFromErr(uint)
0x1800a7a1d  cmp     esi, eax
0x1800a7a1f  cmovz   esi, r15d
0x1800a7a23  mov     eax, esi
0x1800a7a25  add     rsp, 48h
0x1800a7a29  pop     r15
0x1800a7a2b  pop     r14
0x1800a7a2d  pop     r13
0x1800a7a2f  pop     r12
0x1800a7a31  pop     rdi
0x1800a7a32  pop     rsi
0x1800a7a33  pop     rbx
0x1800a7a34  pop     rbp
0x1800a7a35  retn
0x1800a7a36  mov     rcx, r15; Block
0x1800a7a39  call    cs:__imp_free
0x1800a7a3f  jmp     short loc_1800A79F5
```
