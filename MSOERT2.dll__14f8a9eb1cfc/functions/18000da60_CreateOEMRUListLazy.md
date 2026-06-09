# CreateOEMRUListLazy

- ea: `0x18000da60`
- end: `0x18000de43`
- name: `CreateOEMRUListLazy`
- size: `995`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000da40`

## callees

- `0x18000d5e4`
- `0x18000da60`
- `0x180011968`
- `0x180014010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000de29`
- `ADVAPI32!RegCloseKey` at `0x18000de29`
- `ADVAPI32!RegCreateKeyExW` at `0x18000db04`
- `ADVAPI32!RegCreateKeyExW` at `0x18000db04`
- `ADVAPI32!RegQueryValueExW` at `0x18000db50`
- `ADVAPI32!RegQueryValueExW` at `0x18000dc2b`
- `ADVAPI32!RegQueryValueExW` at `0x18000dc7c`
- `ADVAPI32!RegQueryValueExW` at `0x18000dd51`
- `ADVAPI32!RegQueryValueExW` at `0x18000dd94`
- `ADVAPI32!RegQueryValueExW` at `0x18000db50`
- `ADVAPI32!RegQueryValueExW` at `0x18000dc2b`
- `ADVAPI32!RegQueryValueExW` at `0x18000dc7c`
- `ADVAPI32!RegQueryValueExW` at `0x18000dd51`
- `ADVAPI32!RegQueryValueExW` at `0x18000dd94`
- `KERNEL32!lstrcmpiW` at `0x18000dab7`
- `USER32!CharLowerW` at `0x18000db61`
- `USER32!CharLowerW` at `0x18000db61`

## pseudocode

```c
_QWORD *__fastcall CreateOEMRUListLazy(__int64 a1, void *a2, unsigned int a3, _DWORD *a4)
{
  void *v4; // rdi
  unsigned int v5; // r12d
  _QWORD *v7; // rbx
  const WCHAR *v8; // rdx
  HKEY v9; // rcx
  BYTE *v10; // r15
  void *v11; // rax
  int v12; // eax
  BYTE *v13; // rsi
  _WORD *v14; // rdi
  unsigned int v15; // eax
  __int64 v16; // rcx
  unsigned int v17; // eax
  unsigned __int8 *v18; // rax
  unsigned __int8 *v19; // r14
  _DWORD *v20; // r14
  __int16 *v21; // rsi
  __int16 v22; // ax
  BYTE *v23; // r14
  bool v24; // zf
  WCHAR ValueName[2]; // [rsp+50h] [rbp-28h] BYREF
  DWORD Type; // [rsp+54h] [rbp-24h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+C0h] [rbp+48h] BYREF
  void *v31; // [rsp+C8h] [rbp+50h]
  unsigned int v32; // [rsp+D0h] [rbp+58h]
  _DWORD *v33; // [rsp+D8h] [rbp+60h]

  v33 = a4;
  v32 = a3;
  v31 = a2;
  v4 = *(void **)(a1 + 32);
  v5 = *(_DWORD *)(a1 + 4);
  cbData = 0;
  v7 = 0;
  dwDisposition = 0;
  Type = 0;
  hKey = 0;
  *(_DWORD *)ValueName = 0;
  if ( !v4 )
  {
    v4 = lstrcmpiW;
    if ( (*(_BYTE *)(a1 + 8) & 1) != 0 )
      v4 = _mymemcmp;
  }
  v8 = *(const WCHAR **)(a1 + 24);
  v9 = *(HKEY *)(a1 + 16);
  if ( v5 > 0x1D )
    v5 = 29;
  if ( RegCreateKeyExW(v9, v8, 0, (LPWSTR)L"Shell", 0, 0x2001Fu, 0, &hKey, &dwDisposition) )
    goto LABEL_44;
  v10 = (BYTE *)ZeroAllocate(2 * v5 + 2);
  if ( !v10 )
    goto LABEL_44;
  cbData = 2 * v5 + 2;
  if ( RegQueryValueExW(hKey, L"MRUList", 0, &Type, v10, &cbData) )
    *(_WORD *)v10 = 0;
  CharLowerW((LPWSTR)v10);
  v7 = ZeroAllocate(8 * v5 + 32);
  if ( !v7 )
    goto LABEL_43;
  v11 = ZeroAllocate(2 * v5 + 2);
  v7[3] = v11;
  if ( !v11 )
  {
    ((void (__fastcall *)(LPMALLOC, _QWORD *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v7);
    v7 = 0;
    goto LABEL_43;
  }
  v12 = *(_DWORD *)(a1 + 8);
  v13 = v10;
  v7[1] = v4;
  *(_DWORD *)v7 = v12;
  *((_DWORD *)v7 + 1) = v5;
  v7[2] = hKey;
  ValueName[1] = 0;
  v14 = (_WORD *)v7[3];
  while ( 1 )
  {
    v15 = *(unsigned __int16 *)v13;
    ValueName[0] = v15;
    if ( !(_WORD)v15 )
    {
      v20 = v33;
      goto LABEL_39;
    }
    v16 = v15;
    v17 = v15 - 97;
    if ( (*(_BYTE *)(a1 + 8) & 1) != 0 )
      break;
    if ( v17 < v5 && !v7[v16 - 93] )
    {
      cbData = 0;
      if ( !RegQueryValueExW(hKey, ValueName, 0, &Type, 0, &cbData) && Type == 1 )
      {
        cbData *= 2;
        v23 = (BYTE *)ZeroAllocate(cbData);
        if ( v23 )
        {
          if ( !RegQueryValueExW(hKey, ValueName, 0, &Type, v23, &cbData) )
          {
            if ( *(_WORD *)v23 )
            {
              v7[ValueName[0] - 93] = v23;
              *v14++ = ValueName[0];
            }
            else
            {
              ((void (__fastcall *)(LPMALLOC, BYTE *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v23);
            }
          }
        }
      }
    }
LABEL_37:
    v13 += 2;
  }
  if ( v17 >= v5 )
    goto LABEL_37;
  if ( v7[(int)v16 - 93] )
    goto LABEL_37;
  cbData = 0;
  if ( RegQueryValueExW(hKey, ValueName, 0, &Type, 0, &cbData) )
    goto LABEL_37;
  if ( Type != 3 )
    goto LABEL_37;
  v18 = (unsigned __int8 *)ZeroAllocate(cbData + 4);
  v19 = v18;
  if ( !v18 )
    goto LABEL_37;
  *(_DWORD *)v18 = cbData;
  if ( RegQueryValueExW(hKey, ValueName, 0, &Type, v18 + 4, (LPDWORD)v18) )
    goto LABEL_37;
  v7[ValueName[0] - 93] = v19;
  *v14++ = ValueName[0];
  if ( !v31 || !v33 || !(unsigned int)OEMRUIsSameData((struct tagOEMRUDATA *)v7, v19, v31, v32) )
    goto LABEL_37;
  v20 = v33;
  v21 = (__int16 *)(v13 + 2);
  *v33 = ((__int64)v14 - v7[3]) >> 1;
  *(_DWORD *)v7 |= 0x8000u;
  v22 = *v21;
  if ( *v21 )
  {
    do
    {
      *v14 = v22;
      v22 = *++v21;
      ++v14;
    }
    while ( *v21 );
    *v14 = 0;
    goto LABEL_41;
  }
LABEL_39:
  v24 = v31 == 0;
  *v14 = 0;
  if ( v24 || !v20 )
    goto LABEL_43;
LABEL_41:
  if ( (*(_DWORD *)v7 & 0x8000) == 0 )
    *v20 = -1;
LABEL_43:
  ((void (__fastcall *)(LPMALLOC, BYTE *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v10);
  if ( !v7 )
  {
LABEL_44:
    if ( hKey )
      RegCloseKey(hKey);
  }
  return v7;
}

```

## disassembly

```asm
0x18000da60  mov     [rsp-40h+arg_18], r9
0x18000da65  mov     [rsp-40h+arg_10], r8d
0x18000da6a  mov     [rsp-40h+arg_8], rdx
0x18000da6f  push    rbp
0x18000da70  push    rbx
0x18000da71  push    rsi
0x18000da72  push    rdi
0x18000da73  push    r12
0x18000da75  push    r13
0x18000da77  push    r14
0x18000da79  push    r15
0x18000da7b  mov     rbp, rsp
0x18000da7e  sub     rsp, 78h
0x18000da82  mov     rdi, [rcx+20h]
0x18000da86  xor     r14d, r14d
0x18000da89  mov     r12d, [rcx+4]
0x18000da8d  mov     r13, rcx
0x18000da90  mov     [rbp+cbData], r14d
0x18000da94  mov     ebx, r14d
0x18000da97  mov     [rbp+dwDisposition], r14d
0x18000da9b  mov     [rbp+Type], r14d
0x18000da9f  mov     [rbp+hKey], r14
0x18000daa3  mov     dword ptr [rbp+ValueName], r14d
0x18000daa7  test    rdi, rdi
0x18000daaa  jnz     short loc_18000DAC2
0x18000daac  test    byte ptr [rcx+8], 1
0x18000dab0  lea     rax, ?_mymemcmp@@YAHPEBX0_K@Z; _mymemcmp(void const *,void const *,unsigned __int64)
0x18000dab7  mov     rdi, cs:__imp_lstrcmpiW
0x18000dabe  cmovnz  rdi, rax
0x18000dac2  mov     rdx, [rcx+18h]; lpSubKey
0x18000dac6  lea     r9, Class; "Shell"
0x18000dacd  mov     rcx, [rcx+10h]; hKey
0x18000dad1  mov     eax, 1Dh
0x18000dad6  cmp     r12d, eax
0x18000dad9  cmova   r12d, eax
0x18000dadd  lea     rax, [rbp+dwDisposition]
0x18000dae1  mov     [rsp+78h+lpdwDisposition], rax; lpdwDisposition
0x18000dae6  xor     r8d, r8d; Reserved
0x18000dae9  lea     rax, [rbp+hKey]
0x18000daed  mov     [rsp+78h+phkResult], rax; phkResult
0x18000daf2  mov     [rsp+78h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18000daf7  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x18000daff  mov     [rsp+78h+dwOptions], r14d; dwOptions
0x18000db04  call    cs:__imp_RegCreateKeyExW
0x18000db0a  test    eax, eax
0x18000db0c  jnz     loc_18000DE20
0x18000db12  lea     esi, ds:2[r12*2]
0x18000db1a  mov     ecx, esi; Size
0x18000db1c  call    ?ZeroAllocate@@YAPEAXK@Z; ZeroAllocate(ulong)
0x18000db21  mov     r15, rax
0x18000db24  test    rax, rax
0x18000db27  jz      loc_18000DE20
0x18000db2d  mov     rcx, [rbp+hKey]; hKey
0x18000db31  lea     rax, [rbp+cbData]
0x18000db35  mov     qword ptr [rsp+78h+samDesired], rax; lpcbData
0x18000db3a  lea     r9, [rbp+Type]; lpType
0x18000db3e  xor     r8d, r8d; lpReserved
0x18000db41  mov     qword ptr [rsp+78h+dwOptions], r15; lpData
0x18000db46  lea     rdx, aMrulist; "MRUList"
0x18000db4d  mov     [rbp+cbData], esi
0x18000db50  call    cs:__imp_RegQueryValueExW
0x18000db56  test    eax, eax
0x18000db58  jz      short loc_18000DB5E
0x18000db5a  mov     [r15], r14w
0x18000db5e  mov     rcx, r15; lpsz
0x18000db61  call    cs:__imp_CharLowerW
0x18000db67  lea     ecx, ds:20h[r12*8]; Size
0x18000db6f  call    ?ZeroAllocate@@YAPEAXK@Z; ZeroAllocate(ulong)
0x18000db74  mov     rbx, rax
0x18000db77  test    rax, rax
0x18000db7a  jz      loc_18000DE05
0x18000db80  mov     ecx, esi; Size
0x18000db82  call    ?ZeroAllocate@@YAPEAXK@Z; ZeroAllocate(ulong)
0x18000db87  mov     [rbx+18h], rax
0x18000db8b  test    rax, rax
0x18000db8e  jnz     short loc_18000DBAE
0x18000db90  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18000db97  mov     rdx, rbx
0x18000db9a  mov     rax, [rcx]
0x18000db9d  mov     rax, [rax+28h]
0x18000dba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dba6  mov     rbx, r14
0x18000dba9  jmp     loc_18000DE05
0x18000dbae  mov     eax, [r13+8]
0x18000dbb2  mov     rsi, r15
0x18000dbb5  mov     [rbx+8], rdi
0x18000dbb9  mov     [rbx], eax
0x18000dbbb  mov     [rbx+4], r12d
0x18000dbbf  mov     rax, [rbp+hKey]
0x18000dbc3  mov     [rbx+10h], rax
0x18000dbc7  mov     [rbp+ValueName+2], r14w
0x18000dbcc  mov     rdi, [rbx+18h]
0x18000dbd0  movzx   eax, word ptr [rsi]
0x18000dbd3  mov     [rbp+ValueName], ax
0x18000dbd7  test    ax, ax
0x18000dbda  jz      loc_18000DDE1
0x18000dbe0  mov     ecx, eax
0x18000dbe2  add     eax, 0FFFFFF9Fh
0x18000dbe5  test    byte ptr [r13+8], 1
0x18000dbea  jz      loc_18000DD19
0x18000dbf0  cmp     eax, r12d
0x18000dbf3  jnb     loc_18000DDD8
0x18000dbf9  movsxd  rax, ecx
0x18000dbfc  cmp     [rbx+rax*8-2E8h], r14
0x18000dc04  jnz     loc_18000DDD8
0x18000dc0a  mov     rcx, [rbp+hKey]; hKey
0x18000dc0e  lea     rax, [rbp+cbData]
0x18000dc12  mov     qword ptr [rsp+78h+samDesired], rax; lpcbData
0x18000dc17  lea     r9, [rbp+Type]; lpType
0x18000dc1b  xor     r8d, r8d; lpReserved
0x18000dc1e  mov     qword ptr [rsp+78h+dwOptions], r14; lpData
0x18000dc23  lea     rdx, [rbp+ValueName]; lpValueName
0x18000dc27  mov     [rbp+cbData], r14d
0x18000dc2b  call    cs:__imp_RegQueryValueExW
0x18000dc31  test    eax, eax
0x18000dc33  jnz     loc_18000DDD8
0x18000dc39  cmp     [rbp+Type], 3
0x18000dc3d  jnz     loc_18000DDD8
0x18000dc43  mov     ecx, [rbp+cbData]
0x18000dc46  add     ecx, 4; Size
0x18000dc49  call    ?ZeroAllocate@@YAPEAXK@Z; ZeroAllocate(ulong)
0x18000dc4e  mov     r14, rax
0x18000dc51  test    rax, rax
0x18000dc54  jz      loc_18000DDD5
0x18000dc5a  mov     ecx, [rbp+cbData]
0x18000dc5d  lea     r9, [rbp+Type]; lpType
0x18000dc61  mov     [rax], ecx
0x18000dc63  lea     rdx, [rbp+ValueName]; lpValueName
0x18000dc67  lea     rcx, [rax+4]
0x18000dc6b  mov     qword ptr [rsp+78h+samDesired], rax; lpcbData
0x18000dc70  mov     qword ptr [rsp+78h+dwOptions], rcx; lpData
0x18000dc75  xor     r8d, r8d; lpReserved
0x18000dc78  mov     rcx, [rbp+hKey]; hKey
0x18000dc7c  call    cs:__imp_RegQueryValueExW
0x18000dc82  xor     ecx, ecx
0x18000dc84  test    eax, eax
0x18000dc86  jnz     loc_18000DDD5
0x18000dc8c  movzx   eax, [rbp+ValueName]
0x18000dc90  mov     [rbx+rax*8-2E8h], r14
0x18000dc98  movzx   eax, [rbp+ValueName]
0x18000dc9c  mov     [rdi], ax
0x18000dc9f  add     rdi, 2
0x18000dca3  mov     rax, [rbp+arg_8]
0x18000dca7  test    rax, rax
0x18000dcaa  jz      loc_18000DDD5
0x18000dcb0  cmp     [rbp+arg_18], rcx
0x18000dcb4  jz      loc_18000DDD5
0x18000dcba  mov     r9d, [rbp+arg_10]; unsigned int
0x18000dcbe  mov     r8, rax; void *
0x18000dcc1  mov     rdx, r14; unsigned __int8 *
0x18000dcc4  mov     rcx, rbx; struct tagOEMRUDATA *
0x18000dcc7  call    ?OEMRUIsSameData@@YAHPEAUtagOEMRUDATA@@PEAEPEBXI@Z; OEMRUIsSameData(tagOEMRUDATA *,uchar *,void const *,uint)
0x18000dccc  xor     r14d, r14d
0x18000dccf  test    eax, eax
0x18000dcd1  jz      loc_18000DDD8
0x18000dcd7  mov     r14, [rbp+arg_18]
0x18000dcdb  add     rsi, 2
0x18000dcdf  mov     rax, rdi
0x18000dce2  xor     ecx, ecx
0x18000dce4  sub     rax, [rbx+18h]
0x18000dce8  sar     rax, 1
0x18000dceb  mov     [r14], eax
0x18000dcee  bts     dword ptr [rbx], 0Fh
0x18000dcf2  movzx   eax, word ptr [rsi]
0x18000dcf5  test    ax, ax
0x18000dcf8  jz      loc_18000DDE7
0x18000dcfe  mov     [rdi], ax
0x18000dd01  lea     rsi, [rsi+2]
0x18000dd05  movzx   eax, word ptr [rsi]
0x18000dd08  lea     rdi, [rdi+2]
0x18000dd0c  test    ax, ax
0x18000dd0f  jnz     short loc_18000DCFE
0x18000dd11  mov     [rdi], cx
0x18000dd14  jmp     loc_18000DDF6
0x18000dd19  cmp     eax, r12d
0x18000dd1c  jnb     loc_18000DDD8
0x18000dd22  cmp     [rbx+rcx*8-2E8h], r14
0x18000dd2a  jnz     loc_18000DDD8
0x18000dd30  mov     rcx, [rbp+hKey]; hKey
0x18000dd34  lea     rax, [rbp+cbData]
0x18000dd38  mov     qword ptr [rsp+78h+samDesired], rax; lpcbData
0x18000dd3d  lea     r9, [rbp+Type]; lpType
0x18000dd41  xor     r8d, r8d; lpReserved
0x18000dd44  mov     qword ptr [rsp+78h+dwOptions], r14; lpData
0x18000dd49  lea     rdx, [rbp+ValueName]; lpValueName
0x18000dd4d  mov     [rbp+cbData], r14d
0x18000dd51  call    cs:__imp_RegQueryValueExW
0x18000dd57  test    eax, eax
0x18000dd59  jnz     short loc_18000DDD8
0x18000dd5b  cmp     [rbp+Type], 1
0x18000dd5f  jnz     short loc_18000DDD8
0x18000dd61  mov     eax, [rbp+cbData]
0x18000dd64  lea     ecx, [rax+rax]; Size
0x18000dd67  mov     [rbp+cbData], ecx
0x18000dd6a  call    ?ZeroAllocate@@YAPEAXK@Z; ZeroAllocate(ulong)
0x18000dd6f  mov     r14, rax
0x18000dd72  test    rax, rax
0x18000dd75  jz      short loc_18000DDD5
0x18000dd77  mov     rcx, [rbp+hKey]; hKey
0x18000dd7b  lea     rax, [rbp+cbData]
0x18000dd7f  mov     qword ptr [rsp+78h+samDesired], rax; lpcbData
0x18000dd84  lea     r9, [rbp+Type]; lpType
0x18000dd88  xor     r8d, r8d; lpReserved
0x18000dd8b  mov     qword ptr [rsp+78h+dwOptions], r14; lpData
0x18000dd90  lea     rdx, [rbp+ValueName]; lpValueName
0x18000dd94  call    cs:__imp_RegQueryValueExW
0x18000dd9a  xor     ecx, ecx
0x18000dd9c  test    eax, eax
0x18000dd9e  jnz     short loc_18000DDD5
0x18000dda0  cmp     [r14], cx
0x18000dda4  jz      short loc_18000DDBF
0x18000dda6  movzx   eax, [rbp+ValueName]
0x18000ddaa  mov     [rbx+rax*8-2E8h], r14
0x18000ddb2  movzx   eax, [rbp+ValueName]
0x18000ddb6  mov     [rdi], ax
0x18000ddb9  add     rdi, 2
0x18000ddbd  jmp     short loc_18000DDD5
0x18000ddbf  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18000ddc6  mov     rdx, r14
0x18000ddc9  mov     rax, [rcx]
0x18000ddcc  mov     rax, [rax+28h]
0x18000ddd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ddd5  xor     r14d, r14d
0x18000ddd8  add     rsi, 2
0x18000dddc  jmp     loc_18000DBD0
0x18000dde1  mov     r14, [rbp+arg_18]
0x18000dde5  xor     ecx, ecx
0x18000dde7  cmp     [rbp+arg_8], 0
0x18000ddec  mov     [rdi], cx
0x18000ddef  jz      short loc_18000DE05
0x18000ddf1  test    r14, r14
0x18000ddf4  jz      short loc_18000DE05
0x18000ddf6  test    dword ptr [rbx], 8000h
0x18000ddfc  jnz     short loc_18000DE05
0x18000ddfe  mov     dword ptr [r14], 0FFFFFFFFh
0x18000de05  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18000de0c  mov     rdx, r15
0x18000de0f  mov     rax, [rcx]
0x18000de12  mov     rax, [rax+28h]
0x18000de16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de1b  test    rbx, rbx
0x18000de1e  jnz     short loc_18000DE2F
0x18000de20  mov     rcx, [rbp+hKey]; hKey
0x18000de24  test    rcx, rcx
0x18000de27  jz      short loc_18000DE2F
0x18000de29  call    cs:__imp_RegCloseKey
0x18000de2f  mov     rax, rbx
0x18000de32  add     rsp, 78h
0x18000de36  pop     r15
0x18000de38  pop     r14
0x18000de3a  pop     r13
0x18000de3c  pop     r12
0x18000de3e  pop     rdi
0x18000de3f  pop     rsi
0x18000de40  pop     rbx
0x18000de41  pop     rbp
0x18000de42  retn
```
