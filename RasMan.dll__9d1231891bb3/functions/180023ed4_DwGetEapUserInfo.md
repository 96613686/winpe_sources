# DwGetEapUserInfo

- ea: `0x180023ed4`
- end: `0x180024137`
- name: `DwGetEapUserInfo`
- size: `611`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180018ea0`

## callees

- `0x180023d40`
- `0x180023ed4`
- `0x1800263b6`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180023f96`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180023f96`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024117`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024117`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800240e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024107`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800240e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024107`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023ff1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023ff1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024003`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024003`

## pseudocode

```c
__int64 __fastcall DwGetEapUserInfo(int a1, void *a2, _DWORD *a3, _QWORD *a4, int a5, int a6)
{
  _QWORD *v6; // r15
  void *v8; // rbp
  DWORD EapInfo; // ebx
  unsigned int v10; // edi
  unsigned int *v11; // rsi
  unsigned int v12; // r15d
  unsigned int *v13; // r12
  char *v14; // rbp
  char *i; // rcx
  unsigned int *v16; // rax
  unsigned int *v17; // r13
  unsigned int v18; // ecx
  unsigned int *v19; // rdx
  __int64 v20; // rax
  _DWORD *v21; // rdi
  unsigned int *v22; // rdi
  unsigned int *v23; // rsi
  __int64 v24; // rdx
  void *Src; // [rsp+30h] [rbp-48h] BYREF
  HKEY hKey[8]; // [rsp+38h] [rbp-40h] BYREF
  unsigned int v29; // [rsp+90h] [rbp+18h] BYREF
  _QWORD *v30; // [rsp+98h] [rbp+20h]

  v30 = a4;
  Src = 0;
  v6 = a4;
  v29 = 0;
  hKey[0] = 0;
  v8 = a2;
  if ( !a3 )
    return (DWORD)-2147024809;
  if ( !a4 )
  {
    EapInfo = 0;
    *a3 = 0;
    return EapInfo;
  }
  EapInfo = DwGetEapInfo(a1, a5, (unsigned int)&Src, (unsigned int)&v29, (__int64)hKey);
  if ( EapInfo || (v10 = v29) == 0 )
  {
    v11 = (unsigned int *)Src;
    goto LABEL_39;
  }
  v11 = (unsigned int *)Src;
  if ( v29 < 4 )
    goto LABEL_10;
  if ( *(_DWORD *)Src == 827343173 )
  {
    v12 = 0;
    v13 = (unsigned int *)((char *)Src + v29);
    v14 = (char *)Src;
    for ( i = (char *)Src; i < (char *)v13; i += (unsigned int)(*((_DWORD *)i + 6) + 32) )
    {
      if ( *((_DWORD *)i + 6) >= 0xFFFFFFE0 || v12 + ((*((_DWORD *)i + 6) + 39) & 0xFFFFFFF8) < v12 )
      {
        EapInfo = -2147024362;
        goto LABEL_39;
      }
      v12 += (*((_DWORD *)i + 6) + 39) & 0xFFFFFFF8;
    }
    v16 = (unsigned int *)LocalAlloc(0x40u, v12);
    v17 = v16;
    if ( v16 )
    {
      EapInfo = 0;
      v22 = v11;
      v23 = v16;
      if ( v14 < (char *)v13 )
      {
        do
        {
          memcpy_0(v23, v22, v22[6] + 32LL);
          *v23 = 844120389;
          v24 = v22[6];
          v22 = (unsigned int *)((char *)v22 + v24 + 32);
          v23 = (unsigned int *)((char *)v23 + ((v24 + 39) & 0xFFFFFFFFFFFFFFF8uLL));
        }
        while ( v22 < v13 );
      }
      v11 = v17;
      v10 = v12;
      if ( v14 )
      {
        LocalFree(v14);
LABEL_21:
        v8 = a2;
        v6 = v30;
        goto LABEL_22;
      }
    }
    else
    {
      EapInfo = GetLastError();
    }
    if ( EapInfo )
      goto LABEL_39;
    goto LABEL_21;
  }
  if ( *(_DWORD *)Src != 844120389 )
  {
LABEL_10:
    RegDeleteValueW(hKey[0], L"EapInfo");
LABEL_11:
    *a3 = 0;
    goto LABEL_39;
  }
LABEL_22:
  v18 = 0;
  v19 = v11;
  if ( !v10 )
    goto LABEL_11;
  do
  {
    v20 = *v6 - *((_QWORD *)v19 + 1);
    if ( *v6 == *((_QWORD *)v19 + 1) )
      v20 = v6[1] - *((_QWORD *)v19 + 2);
    if ( !v20 && a6 == v19[1] )
      break;
    v18 += (v19[6] + 39) & 0xFFFFFFF8;
    v19 = (unsigned int *)((char *)v11 + v18);
  }
  while ( v18 < v10 );
  if ( v18 >= v10 )
    goto LABEL_11;
  v21 = v19 + 6;
  if ( v8 && *a3 >= *v21 )
    memcpy_0(v8, v19 + 7, (unsigned int)*v21);
  else
    EapInfo = 603;
  *a3 = *v21;
LABEL_39:
  if ( v11 )
    LocalFree(v11);
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return EapInfo;
}

```

## disassembly

```asm
0x180023ed4  mov     rax, rsp
0x180023ed7  mov     [rax+8], rbx
0x180023edb  mov     [rax+20h], r9
0x180023edf  mov     [rax+10h], rdx
0x180023ee3  push    rbp
0x180023ee4  push    rsi
0x180023ee5  push    rdi
0x180023ee6  push    r12
0x180023ee8  push    r13
0x180023eea  push    r14
0x180023eec  push    r15
0x180023eee  sub     rsp, 40h
0x180023ef2  mov     qword ptr [rax-48h], 0
0x180023efa  mov     r15, r9
0x180023efd  mov     dword ptr [rax+18h], 0
0x180023f04  mov     r14, r8
0x180023f07  mov     qword ptr [rax-40h], 0
0x180023f0f  mov     rbp, rdx
0x180023f12  test    r8, r8
0x180023f15  jnz     short loc_180023F21
0x180023f17  mov     ebx, 80070057h
0x180023f1c  jmp     loc_18002411D
0x180023f21  test    r9, r9
0x180023f24  jnz     short loc_180023F30
0x180023f26  xor     ebx, ebx
0x180023f28  mov     [r8], ebx
0x180023f2b  jmp     loc_18002411D
0x180023f30  mov     edx, [rsp+78h+arg_20]
0x180023f37  lea     rax, [rsp+78h+hKey]
0x180023f3c  lea     r9, [rsp+78h+arg_10]
0x180023f44  mov     [rsp+78h+var_58], rax
0x180023f49  lea     r8, [rsp+78h+Src]
0x180023f4e  call    DwGetEapInfo
0x180023f53  mov     ebx, eax
0x180023f55  test    eax, eax
0x180023f57  jnz     loc_1800240FA
0x180023f5d  mov     edi, [rsp+78h+arg_10]
0x180023f64  test    edi, edi
0x180023f66  jz      loc_1800240FA
0x180023f6c  mov     rsi, [rsp+78h+Src]
0x180023f71  cmp     edi, 4
0x180023f74  jb      short loc_180023F8A
0x180023f76  cmp     dword ptr [rsi], 31504145h
0x180023f7c  jz      short loc_180023FA8
0x180023f7e  cmp     dword ptr [rsi], 32504145h
0x180023f84  jz      loc_180024023
0x180023f8a  mov     rcx, [rsp+78h+hKey]; hKey
0x180023f8f  lea     rdx, aEapinfo; "EapInfo"
0x180023f96  call    cs:__imp_RegDeleteValueW
0x180023f9c  mov     dword ptr [r14], 0
0x180023fa3  jmp     loc_1800240FF
0x180023fa8  xor     r15d, r15d
0x180023fab  lea     r12, [rsi+rdi]
0x180023faf  mov     rbp, rsi
0x180023fb2  mov     rcx, rsi
0x180023fb5  cmp     rcx, r12
0x180023fb8  jnb     short loc_180023FE9
0x180023fba  mov     edx, [rcx+18h]
0x180023fbd  add     edx, 20h ; ' '
0x180023fc0  cmp     edx, 20h ; ' '
0x180023fc3  jb      short loc_180023FDF
0x180023fc5  lea     r8d, [rdx+7]
0x180023fc9  and     r8d, 0FFFFFFF8h
0x180023fcd  add     r8d, r15d
0x180023fd0  cmp     r8d, r15d
0x180023fd3  jb      short loc_180023FDF
0x180023fd5  mov     eax, edx
0x180023fd7  mov     r15d, r8d
0x180023fda  add     rcx, rax
0x180023fdd  jmp     short loc_180023FB5
0x180023fdf  mov     ebx, 80070216h
0x180023fe4  jmp     loc_1800240FF
0x180023fe9  mov     edx, r15d; uBytes
0x180023fec  mov     ecx, 40h ; '@'; uFlags
0x180023ff1  call    cs:__imp_LocalAlloc
0x180023ff7  mov     r13, rax
0x180023ffa  test    rax, rax
0x180023ffd  jnz     loc_180024091
0x180024003  call    cs:__imp_GetLastError
0x180024009  mov     ebx, eax
0x18002400b  test    ebx, ebx
0x18002400d  jnz     loc_1800240FF
0x180024013  mov     rbp, [rsp+78h+arg_8]
0x18002401b  mov     r15, [rsp+78h+arg_18]
0x180024023  xor     ecx, ecx
0x180024025  mov     rdx, rsi
0x180024028  test    edi, edi
0x18002402a  jz      loc_180023F9C
0x180024030  mov     r8d, [rsp+78h+arg_28]
0x180024038  mov     rax, [r15]
0x18002403b  sub     rax, [rdx+8]
0x18002403f  jnz     short loc_180024049
0x180024041  mov     rax, [r15+8]
0x180024045  sub     rax, [rdx+10h]
0x180024049  test    rax, rax
0x18002404c  jnz     short loc_180024054
0x18002404e  cmp     r8d, [rdx+4]
0x180024052  jz      short loc_180024068
0x180024054  mov     eax, [rdx+18h]
0x180024057  add     eax, 27h ; '''
0x18002405a  and     eax, 0FFFFFFF8h
0x18002405d  add     ecx, eax
0x18002405f  mov     edx, ecx
0x180024061  add     rdx, rsi
0x180024064  cmp     ecx, edi
0x180024066  jb      short loc_180024038
0x180024068  cmp     ecx, edi
0x18002406a  jnb     loc_180023F9C
0x180024070  lea     rdi, [rdx+18h]
0x180024074  test    rbp, rbp
0x180024077  jz      short loc_1800240EE
0x180024079  mov     eax, [rdi]
0x18002407b  cmp     [r14], eax
0x18002407e  jb      short loc_1800240EE
0x180024080  mov     r8d, eax; Size
0x180024083  add     rdx, 1Ch; Src
0x180024087  mov     rcx, rbp; void *
0x18002408a  call    memcpy_0
0x18002408f  jmp     short loc_1800240F3
0x180024091  xor     ebx, ebx
0x180024093  mov     rdi, rbp
0x180024096  mov     rsi, r13
0x180024099  cmp     rbp, r12
0x18002409c  jnb     short loc_1800240D1
0x18002409e  mov     r8d, [rdi+18h]
0x1800240a2  mov     rdx, rdi; Src
0x1800240a5  add     r8, 20h ; ' '; Size
0x1800240a9  mov     rcx, rsi; void *
0x1800240ac  call    memcpy_0
0x1800240b1  mov     dword ptr [rsi], 32504145h
0x1800240b7  mov     edx, [rdi+18h]
0x1800240ba  add     rdi, 20h ; ' '
0x1800240be  add     rdi, rdx
0x1800240c1  lea     rax, [rdx+27h]
0x1800240c5  and     rax, 0FFFFFFFFFFFFFFF8h
0x1800240c9  add     rsi, rax
0x1800240cc  cmp     rdi, r12
0x1800240cf  jb      short loc_18002409E
0x1800240d1  mov     rsi, r13
0x1800240d4  mov     edi, r15d
0x1800240d7  test    rbp, rbp
0x1800240da  jz      loc_18002400B
0x1800240e0  mov     rcx, rbp; hMem
0x1800240e3  call    cs:__imp_LocalFree
0x1800240e9  jmp     loc_180024013
0x1800240ee  mov     ebx, 25Bh
0x1800240f3  mov     eax, [rdi]
0x1800240f5  mov     [r14], eax
0x1800240f8  jmp     short loc_1800240FF
0x1800240fa  mov     rsi, [rsp+78h+Src]
0x1800240ff  test    rsi, rsi
0x180024102  jz      short loc_18002410D
0x180024104  mov     rcx, rsi; hMem
0x180024107  call    cs:__imp_LocalFree
0x18002410d  mov     rcx, [rsp+78h+hKey]; hKey
0x180024112  test    rcx, rcx
0x180024115  jz      short loc_18002411D
0x180024117  call    cs:__imp_RegCloseKey
0x18002411d  mov     eax, ebx
0x18002411f  mov     rbx, [rsp+78h+arg_0]
0x180024127  add     rsp, 40h
0x18002412b  pop     r15
0x18002412d  pop     r14
0x18002412f  pop     r13
0x180024131  pop     r12
0x180024133  pop     rdi
0x180024134  pop     rsi
0x180024135  pop     rbp
0x180024136  retn
```
