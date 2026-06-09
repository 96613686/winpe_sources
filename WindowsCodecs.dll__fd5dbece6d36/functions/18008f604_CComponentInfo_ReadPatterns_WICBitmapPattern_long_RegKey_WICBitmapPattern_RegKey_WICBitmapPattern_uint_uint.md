# CComponentInfo::ReadPatterns<WICBitmapPattern>(long (*)(RegKey *,WICBitmapPattern *),RegKey *,WICBitmapPattern * *,uint *,uint *)

- ea: `0x18008f604`
- end: `0x18008f983`
- name: `??$ReadPatterns@UWICBitmapPattern@@@CComponentInfo@@IEAAJP6AJPEAVRegKey@@PEAUWICBitmapPattern@@@Z0PEAPEAU2@PEAI4@Z`
- size: `895`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008f258`

## callees

- `0x18002f820`
- `0x18008f604`
- `0x18008f98c`
- `0x1800bb784`
- `0x1800e2f90`
- `0x1800e3c04`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008f890`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008f890`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18008f8e5`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18008f8e5`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18008f6d1`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18008f6d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008f752`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008f7cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008f80a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008f752`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008f7cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008f80a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008f73e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008f73e`

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
0x18008f604  mov     [rsp-8+arg_0], rbx
0x18008f609  push    rbp
0x18008f60a  push    rsi
0x18008f60b  push    rdi
0x18008f60c  push    r12
0x18008f60e  push    r13
0x18008f610  push    r14
0x18008f612  push    r15
0x18008f614  lea     rbp, [rsp-17h]
0x18008f619  sub     rsp, 0E0h
0x18008f620  mov     rax, cs:__security_cookie
0x18008f627  xor     rax, rsp
0x18008f62a  mov     [rbp+47h+var_38], rax
0x18008f62e  mov     rax, [rbp+47h+arg_20]
0x18008f632  xor     r14d, r14d
0x18008f635  mov     [rbp+47h+var_90], rax
0x18008f639  xor     edi, edi
0x18008f63b  mov     rax, [rbp+47h+arg_28]
0x18008f63f  xor     r15d, r15d
0x18008f642  xor     r12d, r12d
0x18008f645  mov     [rbp+47h+var_88], rax
0x18008f649  xor     eax, eax
0x18008f64b  mov     [rbp+47h+var_98], r9
0x18008f64f  mov     [rsp+110h+var_D0], eax
0x18008f653  lea     r13d, [r14+1]
0x18008f657  mov     r10, r8
0x18008f65a  mov     [rbp+47h+var_B0], r8
0x18008f65e  mov     [rbp+47h+var_B8], r14
0x18008f662  xor     ebx, ebx
0x18008f664  mov     [rbp+47h+var_BC], eax
0x18008f667  cmp     eax, 2
0x18008f66a  jge     loc_18008F941
0x18008f670  xor     eax, eax
0x18008f672  mov     [rbp+47h+var_80], ebx
0x18008f675  xorps   xmm0, xmm0
0x18008f678  mov     [rbp+47h+var_5C], eax
0x18008f67b  test    r13d, r13d
0x18008f67e  mov     [rbp+47h+var_C0], eax
0x18008f681  lea     rsi, [rbp+47h+var_80]
0x18008f685  cmovz   rsi, r14
0x18008f689  movups  [rbp+47h+var_7C], xmm0
0x18008f68d  movups  [rbp+47h+var_6C], xmm0
0x18008f691  lea     rcx, [rbp+47h+ftLastWriteTime]
0x18008f695  mov     [rbp+47h+cchName], 10h
0x18008f69c  mov     [rsp+110h+lpftLastWriteTime], rcx; lpftLastWriteTime
0x18008f6a1  lea     r9, [rbp+47h+cchName]; lpcchName
0x18008f6a5  mov     rcx, [r10]; hKey
0x18008f6a8  lea     r8, [rbp+47h+Name]; lpName
0x18008f6ac  mov     [rsp+110h+lpcchClass], 0; lpcchClass
0x18008f6b5  mov     edx, eax; dwIndex
0x18008f6b7  mov     [rsp+110h+lpClass], 0; lpClass
0x18008f6c0  mov     [rsp+110h+lpReserved], 0; lpReserved
0x18008f6c9  mov     qword ptr [rbp+47h+ftLastWriteTime.dwLowDateTime], 0
0x18008f6d1  call    cs:__imp_RegEnumKeyExW
0x18008f6d7  mov     ebx, eax
0x18008f6d9  cmp     eax, 103h
0x18008f6de  jz      loc_18008F852
0x18008f6e4  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18008f6ea  xor     ecx, ecx
0x18008f6ec  test    ebx, ebx
0x18008f6ee  jnz     loc_18008F959
0x18008f6f4  mov     ebx, [rsp+110h+var_D0]
0x18008f6f8  test    r13d, r13d
0x18008f6fb  jz      loc_18008F843
0x18008f701  mov     rax, [rbp+47h+var_B8]
0x18008f705  lea     rdx, [rbp+47h+Name]; lpSubKey
0x18008f709  mov     [rsi], rcx
0x18008f70c  mov     r9d, 20019h; samDesired
0x18008f712  mov     [rsi+8], rcx
0x18008f716  xor     r8d, r8d; ulOptions
0x18008f719  mov     [rsi+18h], rcx
0x18008f71d  mov     [rsi+20h], rcx
0x18008f721  mov     [rsp+110h+hKey], rcx
0x18008f726  mov     qword ptr [rbp+47h+ftLastWriteTime.dwLowDateTime], rcx
0x18008f72a  mov     rcx, [rbp+47h+var_B0]
0x18008f72e  mov     [rsi+10h], rax
0x18008f732  lea     rax, [rbp+47h+ftLastWriteTime]
0x18008f736  mov     [rsp+110h+lpReserved], rax; phkResult
0x18008f73b  mov     rcx, [rcx]; hKey
0x18008f73e  call    cs:__imp_RegOpenKeyExW
0x18008f744  test    eax, eax
0x18008f746  jnz     short loc_18008F7B2
0x18008f748  mov     rcx, [rsp+110h+hKey]; hKey
0x18008f74d  test    rcx, rcx
0x18008f750  jz      short loc_18008F758
0x18008f752  call    cs:__imp_RegCloseKey
0x18008f758  mov     rcx, qword ptr [rbp+47h+ftLastWriteTime.dwLowDateTime]
0x18008f75c  mov     [rsp+110h+hKey], rcx
0x18008f761  test    eax, eax
0x18008f763  jnz     short loc_18008F7B2
0x18008f765  mov     eax, r12d
0x18008f768  lea     r8, [rsp+110h+hKey]
0x18008f76d  shr     eax, 1
0x18008f76f  mov     r9, rsi
0x18008f772  mov     [rsi+8], eax
0x18008f775  call    ??$ReadOnePattern@UWICBitmapPattern@@@CComponentInfo@@IEAAJP6AJPEAVRegKey@@PEAUWICBitmapPattern@@@Z01@Z; CComponentInfo::ReadOnePattern<WICBitmapPattern>(long (*)(RegKey *,WICBitmapPattern *),RegKey *,WICBitmapPattern *)
0x18008f77a  test    eax, eax
0x18008f77c  js      short loc_18008F7B2
0x18008f77e  mov     eax, [rsi+8]
0x18008f781  lea     ecx, [rax+rax]
0x18008f784  cmp     ecx, eax
0x18008f786  jb      short loc_18008F7E7
0x18008f788  test    r13d, r13d
0x18008f78b  jnz     loc_18008F812
0x18008f791  cmp     r12d, ecx
0x18008f794  jb      loc_18008F822
0x18008f79a  mov     eax, ecx
0x18008f79c  sub     r12d, ecx
0x18008f79f  add     [rbp+47h+var_B8], rax
0x18008f7a3  add     rsi, 28h ; '('
0x18008f7a7  mov     eax, 0FFFFFFFFh
0x18008f7ac  add     ebx, eax
0x18008f7ae  mov     [rsp+110h+var_D0], ebx
0x18008f7b2  mov     eax, [rbp+47h+var_C0]
0x18008f7b5  mov     rcx, [rsp+110h+hKey]; hKey
0x18008f7ba  inc     eax
0x18008f7bc  mov     r10, [rbp+47h+var_B0]
0x18008f7c0  mov     [rbp+47h+var_C0], eax
0x18008f7c3  test    rcx, rcx
0x18008f7c6  jz      loc_18008F691
0x18008f7cc  call    cs:__imp_RegCloseKey
0x18008f7d2  mov     eax, [rbp+47h+var_C0]
0x18008f7d5  mov     r10, [rbp+47h+var_B0]
0x18008f7d9  mov     [rsp+110h+hKey], 0
0x18008f7e2  jmp     loc_18008F691
0x18008f7e7  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18008f7ee  mov     ebx, 80070216h
0x18008f7f3  jz      short loc_18008F7FC
0x18008f7f5  mov     ecx, ebx; int
0x18008f7f7  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18008f7fc  mov     rcx, [rsp+110h+hKey]; hKey
0x18008f801  test    rcx, rcx
0x18008f804  jz      loc_18008F88D
0x18008f80a  call    cs:__imp_RegCloseKey
0x18008f810  jmp     short loc_18008F88D
0x18008f812  lea     eax, [rcx+r15]
0x18008f816  cmp     eax, r15d
0x18008f819  jb      short loc_18008F7E7
0x18008f81b  inc     edi
0x18008f81d  mov     r15d, eax
0x18008f820  jmp     short loc_18008F7B2
0x18008f822  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18008f829  mov     ebx, 80070216h
0x18008f82e  jz      short loc_18008F837
0x18008f830  mov     ecx, ebx; int
0x18008f832  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18008f837  lea     rcx, [rsp+110h+hKey]; this
0x18008f83c  call    ?Close@RegKey@@QEAAJXZ; RegKey::Close(void)
0x18008f841  jmp     short loc_18008F88D
0x18008f843  test    ebx, ebx
0x18008f845  jnz     loc_18008F701
0x18008f84b  test    eax, eax
0x18008f84d  jmp     loc_18008F937
0x18008f852  test    r13d, r13d
0x18008f855  jz      loc_18008F924
0x18008f85b  xor     ebx, ebx
0x18008f85d  test    edi, edi
0x18008f85f  jz      loc_18008F941
0x18008f865  lea     rcx, [rdi+rdi*4]
0x18008f869  mov     eax, 0FFFFFFFFh
0x18008f86e  lea     rbx, ds:0[rcx*8]
0x18008f876  cmp     rbx, rax
0x18008f879  jbe     short loc_18008F8D9
0x18008f87b  mov     ebx, 80070216h
0x18008f880  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18008f887  jnz     loc_18008F94D
0x18008f88d  mov     rcx, r14; Block
0x18008f890  call    cs:__imp_free
0x18008f896  xor     eax, eax
0x18008f898  xor     edi, edi
0x18008f89a  xor     r14d, r14d
0x18008f89d  mov     rcx, [rbp+47h+var_98]
0x18008f8a1  mov     [rcx], r14
0x18008f8a4  mov     rcx, [rbp+47h+var_90]
0x18008f8a8  mov     [rcx], edi
0x18008f8aa  mov     rcx, [rbp+47h+var_88]
0x18008f8ae  mov     [rcx], eax
0x18008f8b0  mov     eax, ebx
0x18008f8b2  mov     rcx, [rbp+47h+var_38]
0x18008f8b6  xor     rcx, rsp; StackCookie
0x18008f8b9  call    __security_check_cookie
0x18008f8be  mov     rbx, [rsp+110h+arg_0]
0x18008f8c6  add     rsp, 0E0h
0x18008f8cd  pop     r15
0x18008f8cf  pop     r14
0x18008f8d1  pop     r13
0x18008f8d3  pop     r12
0x18008f8d5  pop     rdi
0x18008f8d6  pop     rsi
0x18008f8d7  pop     rbp
0x18008f8d8  retn
0x18008f8d9  lea     eax, [rbx+r15]
0x18008f8dd  cmp     eax, ebx
0x18008f8df  jb      short loc_18008F87B
0x18008f8e1  mov     ecx, eax; Size
0x18008f8e3  mov     esi, eax
0x18008f8e5  call    cs:__imp_malloc
0x18008f8eb  mov     r14, rax
0x18008f8ee  test    rax, rax
0x18008f8f1  jz      loc_18008F979
0x18008f8f7  xor     r13d, r13d
0x18008f8fa  mov     [rsp+110h+var_D0], edi
0x18008f8fe  mov     r8d, esi; Size
0x18008f901  xor     edx, edx; Val
0x18008f903  mov     rcx, rax; void *
0x18008f906  mov     r12d, r15d
0x18008f909  call    memset_0
0x18008f90e  lea     rax, [rbx+r14]
0x18008f912  mov     [rbp+47h+var_B8], rax
0x18008f916  mov     eax, [rbp+47h+var_BC]
0x18008f919  mov     r10, [rbp+47h+var_B0]
0x18008f91d  inc     eax
0x18008f91f  jmp     loc_18008F662
0x18008f924  cmp     [rsp+110h+var_D0], 0
0x18008f929  jnz     short loc_18008F930
0x18008f92b  test    r12d, r12d
0x18008f92e  jz      short loc_18008F916
0x18008f930  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18008f937  mov     ebx, 80004005h
0x18008f93c  jmp     loc_18008F887
0x18008f941  lea     ecx, [rdi+rdi*4]
0x18008f944  lea     eax, [r15+rcx*8]
0x18008f948  jmp     loc_18008F89D
0x18008f94d  mov     ecx, ebx; int
0x18008f94f  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18008f954  jmp     loc_18008F88D
0x18008f959  jle     short loc_18008F966
0x18008f95b  movzx   ebx, bx
0x18008f95e  or      ebx, 80070000h
0x18008f964  test    ebx, ebx
0x18008f966  jns     short loc_18008F96C
0x18008f968  test    eax, eax
0x18008f96a  jnz     short loc_18008F94D
0x18008f96c  test    ebx, ebx
0x18008f96e  js      loc_18008F88D
0x18008f974  jmp     loc_18008F6F4
0x18008f979  mov     ebx, 8007000Eh
0x18008f97e  jmp     loc_18008F880
```
