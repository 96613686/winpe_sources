# CComponentInfo::ReadPatterns<WICBitmapPattern>(long (*)(RegKey *,WICBitmapPattern *),RegKey *,WICBitmapPattern * *,uint *,uint *)

- ea: `0x180063cf4`
- end: `0x18006409e`
- name: `??$ReadPatterns@UWICBitmapPattern@@@CComponentInfo@@IEAAJP6AJPEAVRegKey@@PEAUWICBitmapPattern@@@Z0PEAPEAU2@PEAI4@Z`
- size: `938`
- prototype: `__int64 __fastcall(__int64, __int64, HKEY *, int **, _DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800634f0`

## callees

- `0x18006168c`
- `0x180063cf4`
- `0x1800640a4`
- `0x1800bd9d4`
- `0x1800e5e60`
- `0x1800e6af4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180063f9e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180063f9e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180063ffa`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180063ffa`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180063dc1`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180063dc1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180063e4e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180063ece`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180063f12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180063e4e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180063ece`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180063f12`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180063e34`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180063e34`

## pseudocode

```c
__int64 __fastcall CComponentInfo::ReadPatterns<WICBitmapPattern>(
        __int64 a1,
        __int64 a2,
        HKEY *a3,
        int **a4,
        _DWORD *a5,
        _DWORD *a6)
{
  int *v6; // r14
  __int64 v7; // rdi
  unsigned int v8; // r15d
  unsigned int v9; // r12d
  int v10; // eax
  int v11; // r13d
  HKEY *v12; // r10
  int v13; // ebx
  DWORD v14; // eax
  int *v15; // rsi
  HKEY v16; // rcx
  bool v17; // sf
  char *v18; // rax
  HKEY *v19; // rcx
  LSTATUS v20; // eax
  __int64 v21; // rdx
  struct _FILETIME v22; // rcx
  unsigned int v23; // eax
  unsigned int v24; // ecx
  bool v25; // zf
  __int64 v26; // rbx
  int v27; // eax
  int *v29; // rax
  int v30; // [rsp+40h] [rbp-89h]
  HKEY hKey; // [rsp+48h] [rbp-81h] BYREF
  DWORD v32; // [rsp+50h] [rbp-79h]
  int v33; // [rsp+54h] [rbp-75h]
  char *v34; // [rsp+58h] [rbp-71h]
  HKEY *v35; // [rsp+60h] [rbp-69h]
  struct _FILETIME ftLastWriteTime; // [rsp+68h] [rbp-61h] BYREF
  DWORD cchName; // [rsp+70h] [rbp-59h] BYREF
  int **v38; // [rsp+78h] [rbp-51h]
  _DWORD *v39; // [rsp+80h] [rbp-49h]
  _DWORD *v40; // [rsp+88h] [rbp-41h]
  int v41; // [rsp+90h] [rbp-39h] BYREF
  __int128 v42; // [rsp+94h] [rbp-35h]
  __int128 v43; // [rsp+A4h] [rbp-25h]
  int v44; // [rsp+B4h] [rbp-15h]
  WCHAR Name[16]; // [rsp+B8h] [rbp-11h] BYREF

  v6 = 0;
  v39 = a5;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v40 = a6;
  v10 = 0;
  v38 = a4;
  v30 = 0;
  v11 = 1;
  v12 = a3;
  v35 = a3;
  v34 = 0;
  while ( 1 )
  {
    v13 = 0;
    v33 = v10;
    if ( v10 >= 2 )
      break;
    v14 = 0;
    v41 = 0;
    v44 = 0;
    v32 = 0;
    v15 = &v41;
    if ( !v11 )
      v15 = v6;
    v42 = 0;
    v43 = 0;
    while ( 1 )
    {
      cchName = 16;
      v16 = *v12;
      ftLastWriteTime = 0;
      v13 = RegEnumKeyExW(v16, v14, Name, &cchName, 0, 0, 0, &ftLastWriteTime);
      if ( v13 == 259 )
        break;
      v17 = v13 < 0;
      if ( v13 )
      {
        if ( v13 > 0 )
        {
          v13 = (unsigned __int16)v13 | 0x80070000;
          v17 = v13 < 0;
        }
        if ( !v17 || !(_DWORD)g_doStackCaptures )
          goto LABEL_37;
LABEL_48:
        DoStackCapture(v13);
LABEL_37:
        free(v6);
        v27 = 0;
        LODWORD(v7) = 0;
        v6 = 0;
        goto LABEL_38;
      }
      if ( !v11 && !v30 )
      {
        v25 = (_DWORD)g_doStackCaptures == 0;
        goto LABEL_46;
      }
      v18 = v34;
      *(_QWORD *)v15 = 0;
      *((_QWORD *)v15 + 1) = 0;
      *((_QWORD *)v15 + 3) = 0;
      *((_QWORD *)v15 + 4) = 0;
      hKey = 0;
      ftLastWriteTime = 0;
      v19 = v35;
      *((_QWORD *)v15 + 2) = v18;
      v20 = RegOpenKeyExW(*v19, Name, 0, 0x20019u, (PHKEY)&ftLastWriteTime);
      if ( !v20 )
      {
        if ( hKey )
          v20 = RegCloseKey(hKey);
        v22 = ftLastWriteTime;
        hKey = (HKEY)ftLastWriteTime;
        if ( !v20 )
        {
          v15[2] = v9 >> 1;
          if ( (int)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))CComponentInfo::ReadOnePattern<WICBitmapPattern>)(
                      v22,
                      v21,
                      &hKey,
                      v15) >= 0 )
          {
            v23 = v15[2];
            v24 = 2 * v23;
            if ( 2 * v23 < v23 )
              goto LABEL_20;
            if ( v11 )
            {
              if ( v24 + v8 < v8 )
              {
LABEL_20:
                v13 = -2147024362;
                if ( (_DWORD)g_doStackCaptures )
                  DoStackCapture(-2147024362);
                if ( hKey )
                  RegCloseKey(hKey);
                goto LABEL_37;
              }
              v7 = (unsigned int)(v7 + 1);
              v8 += v24;
            }
            else
            {
              if ( v9 < v24 )
              {
                v13 = -2147024362;
                if ( (_DWORD)g_doStackCaptures )
                  DoStackCapture(-2147024362);
                RegKey::Close((RegKey *)&hKey);
                goto LABEL_37;
              }
              v9 -= v24;
              v34 += v24;
              v15 += 10;
              --v30;
            }
          }
        }
      }
      v14 = v32 + 1;
      v12 = v35;
      ++v32;
      if ( hKey )
      {
        RegCloseKey(hKey);
        v14 = v32;
        v12 = v35;
        hKey = 0;
      }
    }
    if ( v11 )
    {
      v13 = 0;
      if ( !(_DWORD)v7 )
        break;
      v26 = 40 * v7;
      if ( (unsigned __int64)(40 * v7) > 0xFFFFFFFF || (unsigned int)v26 + v8 < (unsigned int)v26 )
      {
        v13 = -2147024362;
        goto LABEL_35;
      }
      v29 = (int *)malloc((unsigned int)v26 + v8);
      v6 = v29;
      if ( !v29 )
      {
        v13 = -2147024882;
LABEL_35:
        v25 = (_DWORD)g_doStackCaptures == 0;
LABEL_36:
        if ( !v25 )
          goto LABEL_48;
        goto LABEL_37;
      }
      v11 = 0;
      v30 = v7;
      v9 = v8;
      memset_0(v29, 0, (unsigned int)v26 + v8);
      v34 = (char *)&v6[(unsigned __int64)v26 / 4];
    }
    else if ( v30 || v9 )
    {
      v25 = (_DWORD)g_doStackCaptures == 0;
LABEL_46:
      v13 = -2147467259;
      goto LABEL_36;
    }
    v12 = v35;
    v10 = v33 + 1;
  }
  v27 = v8 + 40 * v7;
LABEL_38:
  *v38 = v6;
  *v39 = v7;
  *v40 = v27;
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180063cf4  mov     [rsp-8+arg_0], rbx
0x180063cf9  push    rbp
0x180063cfa  push    rsi
0x180063cfb  push    rdi
0x180063cfc  push    r12
0x180063cfe  push    r13
0x180063d00  push    r14
0x180063d02  push    r15
0x180063d04  lea     rbp, [rsp-17h]
0x180063d09  sub     rsp, 0E0h
0x180063d10  mov     rax, cs:__security_cookie
0x180063d17  xor     rax, rsp
0x180063d1a  mov     [rbp+47h+var_38], rax
0x180063d1e  mov     rax, [rbp+47h+arg_20]
0x180063d22  xor     r14d, r14d
0x180063d25  mov     [rbp+47h+var_90], rax
0x180063d29  xor     edi, edi
0x180063d2b  mov     rax, [rbp+47h+arg_28]
0x180063d2f  xor     r15d, r15d
0x180063d32  xor     r12d, r12d
0x180063d35  mov     [rbp+47h+var_88], rax
0x180063d39  xor     eax, eax
0x180063d3b  mov     [rbp+47h+var_98], r9
0x180063d3f  mov     [rsp+110h+var_D0], eax
0x180063d43  lea     r13d, [r14+1]
0x180063d47  mov     r10, r8
0x180063d4a  mov     [rbp+47h+var_B0], r8
0x180063d4e  mov     [rbp+47h+var_B8], r14
0x180063d52  xor     ebx, ebx
0x180063d54  mov     [rbp+47h+var_BC], eax
0x180063d57  cmp     eax, 2
0x180063d5a  jge     loc_18006405C
0x180063d60  xor     eax, eax
0x180063d62  mov     [rbp+47h+var_80], ebx
0x180063d65  xorps   xmm0, xmm0
0x180063d68  mov     [rbp+47h+var_5C], eax
0x180063d6b  test    r13d, r13d
0x180063d6e  mov     [rbp+47h+var_C0], eax
0x180063d71  lea     rsi, [rbp+47h+var_80]
0x180063d75  cmovz   rsi, r14
0x180063d79  movups  [rbp+47h+var_7C], xmm0
0x180063d7d  movups  [rbp+47h+var_6C], xmm0
0x180063d81  lea     rcx, [rbp+47h+ftLastWriteTime]
0x180063d85  mov     [rbp+47h+cchName], 10h
0x180063d8c  mov     [rsp+110h+lpftLastWriteTime], rcx; lpftLastWriteTime
0x180063d91  lea     r9, [rbp+47h+cchName]; lpcchName
0x180063d95  mov     rcx, [r10]; hKey
0x180063d98  lea     r8, [rbp+47h+Name]; lpName
0x180063d9c  mov     [rsp+110h+lpcchClass], 0; lpcchClass
0x180063da5  mov     edx, eax; dwIndex
0x180063da7  mov     [rsp+110h+lpClass], 0; lpClass
0x180063db0  mov     [rsp+110h+lpReserved], 0; lpReserved
0x180063db9  mov     qword ptr [rbp+47h+ftLastWriteTime.dwLowDateTime], 0
0x180063dc1  call    cs:__imp_RegEnumKeyExW
0x180063dc8  nop     dword ptr [rax+rax+00h]
0x180063dcd  mov     ebx, eax
0x180063dcf  cmp     eax, 103h
0x180063dd4  jz      loc_180063F60
0x180063dda  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180063de0  xor     ecx, ecx
0x180063de2  test    ebx, ebx
0x180063de4  jnz     loc_180064074
0x180063dea  mov     ebx, [rsp+110h+var_D0]
0x180063dee  test    r13d, r13d
0x180063df1  jz      loc_180063F51
0x180063df7  mov     rax, [rbp+47h+var_B8]
0x180063dfb  lea     rdx, [rbp+47h+Name]; lpSubKey
0x180063dff  mov     [rsi], rcx
0x180063e02  mov     r9d, 20019h; samDesired
0x180063e08  mov     [rsi+8], rcx
0x180063e0c  xor     r8d, r8d; ulOptions
0x180063e0f  mov     [rsi+18h], rcx
0x180063e13  mov     [rsi+20h], rcx
0x180063e17  mov     [rsp+110h+hKey], rcx
0x180063e1c  mov     qword ptr [rbp+47h+ftLastWriteTime.dwLowDateTime], rcx
0x180063e20  mov     rcx, [rbp+47h+var_B0]
0x180063e24  mov     [rsi+10h], rax
0x180063e28  lea     rax, [rbp+47h+ftLastWriteTime]
0x180063e2c  mov     [rsp+110h+lpReserved], rax; phkResult
0x180063e31  mov     rcx, [rcx]; hKey
0x180063e34  call    cs:__imp_RegOpenKeyExW
0x180063e3b  nop     dword ptr [rax+rax+00h]
0x180063e40  test    eax, eax
0x180063e42  jnz     short loc_180063EB4
0x180063e44  mov     rcx, [rsp+110h+hKey]; hKey
0x180063e49  test    rcx, rcx
0x180063e4c  jz      short loc_180063E5A
0x180063e4e  call    cs:__imp_RegCloseKey
0x180063e55  nop     dword ptr [rax+rax+00h]
0x180063e5a  mov     rcx, qword ptr [rbp+47h+ftLastWriteTime.dwLowDateTime]
0x180063e5e  mov     [rsp+110h+hKey], rcx
0x180063e63  test    eax, eax
0x180063e65  jnz     short loc_180063EB4
0x180063e67  mov     eax, r12d
0x180063e6a  lea     r8, [rsp+110h+hKey]
0x180063e6f  shr     eax, 1
0x180063e71  mov     r9, rsi
0x180063e74  mov     [rsi+8], eax
0x180063e77  call    ??$ReadOnePattern@UWICBitmapPattern@@@CComponentInfo@@IEAAJP6AJPEAVRegKey@@PEAUWICBitmapPattern@@@Z01@Z; CComponentInfo::ReadOnePattern<WICBitmapPattern>(long (*)(RegKey *,WICBitmapPattern *),RegKey *,WICBitmapPattern *)
0x180063e7c  test    eax, eax
0x180063e7e  js      short loc_180063EB4
0x180063e80  mov     eax, [rsi+8]
0x180063e83  lea     ecx, [rax+rax]
0x180063e86  cmp     ecx, eax
0x180063e88  jb      short loc_180063EEF
0x180063e8a  test    r13d, r13d
0x180063e8d  jnz     loc_180063F20
0x180063e93  cmp     r12d, ecx
0x180063e96  jb      loc_180063F30
0x180063e9c  mov     eax, ecx
0x180063e9e  sub     r12d, ecx
0x180063ea1  add     [rbp+47h+var_B8], rax
0x180063ea5  add     rsi, 28h ; '('
0x180063ea9  mov     eax, 0FFFFFFFFh
0x180063eae  add     ebx, eax
0x180063eb0  mov     [rsp+110h+var_D0], ebx
0x180063eb4  mov     eax, [rbp+47h+var_C0]
0x180063eb7  mov     rcx, [rsp+110h+hKey]; hKey
0x180063ebc  inc     eax
0x180063ebe  mov     r10, [rbp+47h+var_B0]
0x180063ec2  mov     [rbp+47h+var_C0], eax
0x180063ec5  test    rcx, rcx
0x180063ec8  jz      loc_180063D81
0x180063ece  call    cs:__imp_RegCloseKey
0x180063ed5  nop     dword ptr [rax+rax+00h]
0x180063eda  mov     eax, [rbp+47h+var_C0]
0x180063edd  mov     r10, [rbp+47h+var_B0]
0x180063ee1  mov     [rsp+110h+hKey], 0
0x180063eea  jmp     loc_180063D81
0x180063eef  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180063ef6  mov     ebx, 80070216h
0x180063efb  jz      short loc_180063F04
0x180063efd  mov     ecx, ebx; int
0x180063eff  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180063f04  mov     rcx, [rsp+110h+hKey]; hKey
0x180063f09  test    rcx, rcx
0x180063f0c  jz      loc_180063F9B
0x180063f12  call    cs:__imp_RegCloseKey
0x180063f19  nop     dword ptr [rax+rax+00h]
0x180063f1e  jmp     short loc_180063F9B
0x180063f20  lea     eax, [rcx+r15]
0x180063f24  cmp     eax, r15d
0x180063f27  jb      short loc_180063EEF
0x180063f29  inc     edi
0x180063f2b  mov     r15d, eax
0x180063f2e  jmp     short loc_180063EB4
0x180063f30  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180063f37  mov     ebx, 80070216h
0x180063f3c  jz      short loc_180063F45
0x180063f3e  mov     ecx, ebx; int
0x180063f40  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180063f45  lea     rcx, [rsp+110h+hKey]; this
0x180063f4a  call    ?Close@RegKey@@QEAAJXZ; RegKey::Close(void)
0x180063f4f  jmp     short loc_180063F9B
0x180063f51  test    ebx, ebx
0x180063f53  jnz     loc_180063DF7
0x180063f59  test    eax, eax
0x180063f5b  jmp     loc_180064052
0x180063f60  test    r13d, r13d
0x180063f63  jz      loc_18006403F
0x180063f69  xor     ebx, ebx
0x180063f6b  test    edi, edi
0x180063f6d  jz      loc_18006405C
0x180063f73  lea     rcx, [rdi+rdi*4]
0x180063f77  mov     eax, 0FFFFFFFFh
0x180063f7c  lea     rbx, ds:0[rcx*8]
0x180063f84  cmp     rbx, rax
0x180063f87  jbe     short loc_180063FEE
0x180063f89  mov     ebx, 80070216h
0x180063f8e  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180063f95  jnz     loc_180064068
0x180063f9b  mov     rcx, r14; Block
0x180063f9e  call    cs:__imp_free
0x180063fa5  nop     dword ptr [rax+rax+00h]
0x180063faa  xor     eax, eax
0x180063fac  xor     edi, edi
0x180063fae  xor     r14d, r14d
0x180063fb1  mov     rcx, [rbp+47h+var_98]
0x180063fb5  mov     [rcx], r14
0x180063fb8  mov     rcx, [rbp+47h+var_90]
0x180063fbc  mov     [rcx], edi
0x180063fbe  mov     rcx, [rbp+47h+var_88]
0x180063fc2  mov     [rcx], eax
0x180063fc4  mov     eax, ebx
0x180063fc6  mov     rcx, [rbp+47h+var_38]
0x180063fca  xor     rcx, rsp; StackCookie
0x180063fcd  call    __security_check_cookie
0x180063fd2  mov     rbx, [rsp+110h+arg_0]
0x180063fda  add     rsp, 0E0h
0x180063fe1  pop     r15
0x180063fe3  pop     r14
0x180063fe5  pop     r13
0x180063fe7  pop     r12
0x180063fe9  pop     rdi
0x180063fea  pop     rsi
0x180063feb  pop     rbp
0x180063fec  retn
0x180063fee  lea     eax, [rbx+r15]
0x180063ff2  cmp     eax, ebx
0x180063ff4  jb      short loc_180063F89
0x180063ff6  mov     ecx, eax; Size
0x180063ff8  mov     esi, eax
0x180063ffa  call    cs:__imp_malloc
0x180064001  nop     dword ptr [rax+rax+00h]
0x180064006  mov     r14, rax
0x180064009  test    rax, rax
0x18006400c  jz      loc_180064094
0x180064012  xor     r13d, r13d
0x180064015  mov     [rsp+110h+var_D0], edi
0x180064019  mov     r8d, esi; Size
0x18006401c  xor     edx, edx; Val
0x18006401e  mov     rcx, rax; void *
0x180064021  mov     r12d, r15d
0x180064024  call    memset_0
0x180064029  lea     rax, [rbx+r14]
0x18006402d  mov     [rbp+47h+var_B8], rax
0x180064031  mov     eax, [rbp+47h+var_BC]
0x180064034  mov     r10, [rbp+47h+var_B0]
0x180064038  inc     eax
0x18006403a  jmp     loc_180063D52
0x18006403f  cmp     [rsp+110h+var_D0], 0
0x180064044  jnz     short loc_18006404B
0x180064046  test    r12d, r12d
0x180064049  jz      short loc_180064031
0x18006404b  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180064052  mov     ebx, 80004005h
0x180064057  jmp     loc_180063F95
0x18006405c  lea     ecx, [rdi+rdi*4]
0x18006405f  lea     eax, [r15+rcx*8]
0x180064063  jmp     loc_180063FB1
0x180064068  mov     ecx, ebx; int
0x18006406a  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18006406f  jmp     loc_180063F9B
0x180064074  jle     short loc_180064081
0x180064076  movzx   ebx, bx
0x180064079  or      ebx, 80070000h
0x18006407f  test    ebx, ebx
0x180064081  jns     short loc_180064087
0x180064083  test    eax, eax
0x180064085  jnz     short loc_180064068
0x180064087  test    ebx, ebx
0x180064089  js      loc_180063F9B
0x18006408f  jmp     loc_180063DEA
0x180064094  mov     ebx, 8007000Eh
0x180064099  jmp     loc_180063F8E
```
