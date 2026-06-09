# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)

- ea: `0x1800206e8`
- end: `0x180020912`
- name: `?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ`
- size: `554`
- prototype: ``
- caller_count: `7`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001feb0`
- `0x18006b3f8`
- `0x18006b984`
- `0x18006ba70`
- `0x18006bd5c`
- `0x18006bfec`
- `0x18006c268`

## callees

- `0x18001e260`
- `0x1800206e8`
- `0x18002e020`
- `0x180044708`
- `0x1800532a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__get_errno` at `0x180020897`
- `api-ms-win-crt-private-l1-1-0!_o__get_errno` at `0x180020897`
- `api-ms-win-crt-private-l1-1-0!_o__set_errno` at `0x1800207b7`
- `api-ms-win-crt-private-l1-1-0!_o__set_errno` at `0x1800207b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180020865`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180020865`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020784`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020784`

## pseudocode

```c
__int64 Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
        __int64 a1,
        const wchar_t *a2,
        ...)
{
  unsigned __int64 v3; // rcx
  unsigned __int64 v5; // rsi
  unsigned __int64 v6; // r9
  int v7; // ebx
  _WORD *v9; // rax
  unsigned __int64 v10; // rsi
  wchar_t *v11; // r14
  size_t v12; // rsi
  int v13; // eax
  __int64 v14; // r9
  unsigned __int64 v15; // rbx
  LPVOID v16; // rax
  unsigned __int64 v17; // rax
  unsigned __int64 v18[7]; // [rsp+20h] [rbp-38h] BYREF
  va_list Args; // [rsp+70h] [rbp+18h] BYREF

  va_start(Args, a2);
  v18[0] = 0;
  v3 = 32;
  while ( 1 )
  {
    v5 = v3 + 1;
    if ( v3 + 1 < v3 )
    {
LABEL_6:
      v7 = -2147024362;
      goto LABEL_8;
    }
    v6 = *(_QWORD *)(a1 + 16);
    if ( v6 == -1 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(a1);
      if ( *(_QWORD *)a1 )
        v6 = *(_QWORD *)(a1 + 8) + 1LL;
      else
        v6 = 0;
      *(_QWORD *)(a1 + 16) = v6;
    }
    if ( v6 )
      break;
    v18[0] = 0;
    if ( !is_mul_ok(v5, 2u) )
      goto LABEL_6;
    v9 = CoTaskMemAlloc(2 * v5);
    if ( v9 )
    {
      v7 = 0;
      *(_QWORD *)(a1 + 16) = v5;
      *(_QWORD *)a1 = v9;
      *v9 = 0;
    }
    else
    {
      v7 = -2147024882;
    }
    if ( v7 < 0 )
      goto LABEL_33;
LABEL_14:
    v10 = *(_QWORD *)(a1 + 16);
    v11 = *(wchar_t **)a1;
    _o__set_errno(0);
    if ( v10 )
    {
      if ( v10 > 0x7FFFFFFF )
      {
        *v11 = 0;
LABEL_40:
        v7 = -2147024809;
        goto LABEL_8;
      }
      v12 = v10 - 1;
      v13 = vsnwprintf(v11, v12, a2, Args);
      if ( v13 < 0 || v13 > v12 )
      {
        v7 = -2147024774;
        v11[v12] = 0;
      }
      else
      {
        v7 = 0;
        if ( v13 == v12 )
          v11[v12] = 0;
      }
    }
    else
    {
      v7 = -2147024809;
    }
    if ( v7 != -2147024774 )
      goto LABEL_8;
    LODWORD(v18[0]) = 0;
    _o__get_errno(v18);
    if ( LODWORD(v18[0]) == 22 )
      goto LABEL_40;
    v17 = *(_QWORD *)(a1 + 16);
    v3 = v17 + 32;
    if ( v17 + 32 < v17 )
    {
      v7 = -2147024362;
      goto LABEL_33;
    }
  }
  if ( v5 <= v6 )
    goto LABEL_14;
  v18[0] = 0;
  v7 = ULongLongMult(v6, 2u, v18);
  if ( v7 < 0 )
    goto LABEL_8;
  v15 = v18[0];
  if ( v18[0] - v14 > 0x800 )
    v15 = v14 + 2048;
  if ( v5 > v15 )
    v15 = v5;
  v16 = CoTaskMemRealloc(*(LPVOID *)a1, 2 * v15);
  if ( v16 )
  {
    *(_QWORD *)(a1 + 16) = v15;
    *(_QWORD *)a1 = v16;
    goto LABEL_14;
  }
  v7 = -2147024882;
LABEL_8:
  if ( v7 >= 0 )
  {
    *(_QWORD *)(a1 + 8) = -1;
    return (unsigned int)v7;
  }
LABEL_33:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(a1);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800206e8  mov     rax, rsp
0x1800206eb  mov     [rax+10h], rdx
0x1800206ef  mov     [rax+18h], r8
0x1800206f3  mov     [rax+20h], r9
0x1800206f7  push    rbx
0x1800206f8  push    rbp
0x1800206f9  push    rsi
0x1800206fa  push    rdi
0x1800206fb  push    r14
0x1800206fd  sub     rsp, 30h
0x180020701  mov     rdi, rcx
0x180020704  mov     qword ptr [rax-38h], 0
0x18002070c  mov     ecx, 20h ; ' '
0x180020711  mov     rbp, rdx
0x180020714  lea     rsi, [rcx+1]
0x180020718  lea     rbx, [rsp+58h+Args]
0x18002071d  cmp     rsi, rcx
0x180020720  jb      short loc_18002074A
0x180020722  mov     r9, [rdi+10h]
0x180020726  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x18002072a  jz      loc_1800208C7
0x180020730  test    r9, r9
0x180020733  jnz     loc_180020813
0x180020739  lea     eax, [r9+2]
0x18002073d  mov     [rsp+58h+var_38], r9
0x180020742  mul     rsi
0x180020745  test    rdx, rdx
0x180020748  jz      short loc_180020781
0x18002074a  mov     ebx, 80070216h
0x18002074f  jmp     short loc_180020764
0x180020751  xor     eax, eax
0x180020753  mov     [r14+rsi*2], ax
0x180020758  cmp     ebx, 8007007Ah
0x18002075e  jz      loc_18002088A
0x180020764  test    ebx, ebx
0x180020766  js      loc_1800208BA
0x18002076c  mov     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFFh
0x180020774  mov     eax, ebx
0x180020776  add     rsp, 30h
0x18002077a  pop     r14
0x18002077c  pop     rdi
0x18002077d  pop     rsi
0x18002077e  pop     rbp
0x18002077f  pop     rbx
0x180020780  retn
0x180020781  mov     rcx, rax; cb
0x180020784  call    cs:__imp_CoTaskMemAlloc
0x18002078a  test    rax, rax
0x18002078d  jz      loc_180020880
0x180020793  xor     ebx, ebx
0x180020795  mov     [rdi+10h], rsi
0x180020799  xor     ecx, ecx
0x18002079b  mov     [rdi], rax
0x18002079e  mov     [rax], cx
0x1800207a1  test    ebx, ebx
0x1800207a3  js      loc_1800208BA
0x1800207a9  lea     rbx, [rsp+58h+Args]
0x1800207ae  mov     rsi, [rdi+10h]
0x1800207b2  xor     ecx, ecx
0x1800207b4  mov     r14, [rdi]
0x1800207b7  call    cs:__imp__o__set_errno
0x1800207bd  test    rsi, rsi
0x1800207c0  jz      loc_1800208EA
0x1800207c6  cmp     rsi, 7FFFFFFFh
0x1800207cd  ja      loc_1800208F8
0x1800207d3  dec     rsi
0x1800207d6  mov     r9, rbx; Args
0x1800207d9  mov     rdx, rsi; BufferCount
0x1800207dc  mov     r8, rbp; Format
0x1800207df  mov     rcx, r14; Buffer
0x1800207e2  call    _vsnwprintf
0x1800207e7  test    eax, eax
0x1800207e9  js      short loc_180020802
0x1800207eb  cdqe
0x1800207ed  cmp     rax, rsi
0x1800207f0  ja      short loc_180020802
0x1800207f2  xor     ebx, ebx
0x1800207f4  cmp     rax, rsi
0x1800207f7  jnz     loc_180020758
0x1800207fd  jmp     loc_180020751
0x180020802  xor     eax, eax
0x180020804  mov     ebx, 8007007Ah
0x180020809  mov     [r14+rsi*2], ax
0x18002080e  jmp     loc_180020758
0x180020813  cmp     rsi, r9
0x180020816  jbe     short loc_1800207AE
0x180020818  lea     r8, [rsp+58h+var_38]; unsigned __int64 *
0x18002081d  mov     [rsp+58h+var_38], 0
0x180020826  mov     edx, 2; unsigned __int64
0x18002082b  mov     rcx, r9; unsigned __int64
0x18002082e  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180020833  mov     ebx, eax
0x180020835  test    eax, eax
0x180020837  js      loc_180020764
0x18002083d  mov     rbx, [rsp+58h+var_38]
0x180020842  mov     rax, rbx
0x180020845  sub     rax, r9
0x180020848  cmp     rax, 800h
0x18002084e  jbe     short loc_180020857
0x180020850  lea     rbx, [r9+800h]
0x180020857  mov     rcx, [rdi]; pv
0x18002085a  cmp     rsi, rbx
0x18002085d  cmova   rbx, rsi
0x180020861  lea     rdx, [rbx+rbx]; cb
0x180020865  call    cs:__imp_CoTaskMemRealloc
0x18002086b  test    rax, rax
0x18002086e  jz      loc_180020908
0x180020874  mov     [rdi+10h], rbx
0x180020878  mov     [rdi], rax
0x18002087b  jmp     loc_1800207A9
0x180020880  mov     ebx, 8007000Eh
0x180020885  jmp     loc_1800207A1
0x18002088a  lea     rcx, [rsp+58h+var_38]
0x18002088f  mov     dword ptr [rsp+58h+var_38], 0
0x180020897  call    cs:__imp__o__get_errno
0x18002089d  cmp     dword ptr [rsp+58h+var_38], 16h
0x1800208a2  jz      short loc_1800208FE
0x1800208a4  mov     rax, [rdi+10h]
0x1800208a8  lea     rcx, [rax+20h]
0x1800208ac  cmp     rcx, rax
0x1800208af  jnb     loc_180020714
0x1800208b5  mov     ebx, 80070216h
0x1800208ba  mov     rcx, rdi
0x1800208bd  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800208c2  jmp     loc_180020774
0x1800208c7  mov     rcx, rdi
0x1800208ca  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x1800208cf  cmp     qword ptr [rdi], 0
0x1800208d3  jz      short loc_1800208DE
0x1800208d5  mov     r9, [rdi+8]
0x1800208d9  inc     r9
0x1800208dc  jmp     short loc_1800208E1
0x1800208de  xor     r9d, r9d
0x1800208e1  mov     [rdi+10h], r9
0x1800208e5  jmp     loc_180020730
0x1800208ea  mov     ebx, 80070057h
0x1800208ef  test    rsi, rsi
0x1800208f2  jz      loc_180020758
0x1800208f8  xor     eax, eax
0x1800208fa  mov     [r14], ax
0x1800208fe  mov     ebx, 80070057h
0x180020903  jmp     loc_180020764
0x180020908  mov     ebx, 8007000Eh
0x18002090d  jmp     loc_180020764
```
