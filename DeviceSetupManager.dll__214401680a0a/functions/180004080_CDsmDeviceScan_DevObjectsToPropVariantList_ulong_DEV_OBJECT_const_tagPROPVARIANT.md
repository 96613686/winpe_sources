# CDsmDeviceScan::_DevObjectsToPropVariantList(ulong,_DEV_OBJECT const *,tagPROPVARIANT *)

- ea: `0x180004080`
- end: `0x1800041bb`
- name: `?_DevObjectsToPropVariantList@CDsmDeviceScan@@CAJKPEBU_DEV_OBJECT@@PEAUtagPROPVARIANT@@@Z`
- size: `315`
- prototype: `__int64 __fastcall(unsigned int, const struct _DEV_OBJECT *, PROPVARIANT *)`
- caller_count: `5`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180002a24`
- `0x180002c90`
- `0x1800170f4`
- `0x18002ea48`
- `0x18002eb20`

## callees

- `0x180004080`
- `0x18001ba48`
- `0x180027678`
- `0x1800276d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000409d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800040d3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000409d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800040d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800040b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004127`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800040b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004127`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000417a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800041a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000417a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800041a9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDsmDeviceScan::_DevObjectsToPropVariantList(
        unsigned int a1,
        const struct _DEV_OBJECT *a2,
        PROPVARIANT *a3)
{
  BYTE *v6; // rax
  int v7; // edi
  const wchar_t *v9; // rbx
  __int64 v10; // rax
  SIZE_T v12; // rsi
  const wchar_t *v13; // rcx
  size_t v14; // r8
  _WORD *v15; // r11
  __int64 i; // rbp
  size_t v17; // rsi
  HRESULT v18; // eax
  size_t v19; // rdx
  size_t *v20; // r8
  size_t v21; // [rsp+20h] [rbp-58h]

  PropVariantClear(a3);
  *(_WORD *)a3 = 4127;
  *((_DWORD *)a3 + 2) = a1;
  v6 = (BYTE *)CoTaskMemAlloc(8LL * a1);
  a3[2] = v6;
  if ( v6 )
  {
    v7 = 0;
    memset_0(v6, 0, 8LL * a1);
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)i >= a1 )
        return (unsigned int)v7;
      v9 = (const wchar_t *)*((_QWORD *)a2 + 4 * (unsigned int)i + 1);
      if ( !v9 )
      {
        v15 = 0;
        v7 = 0;
        goto LABEL_12;
      }
      v10 = -1;
      while ( v9[++v10] != 0 )
        ;
      v12 = 2 * v10 + 2;
      v15 = CoTaskMemAlloc(v12);
      if ( !v15 )
      {
        v7 = -2147024882;
        goto LABEL_11;
      }
      v17 = v12 >> 1;
      v18 = StringValidateDestW(v13, v17, v14);
      v7 = v18;
      if ( v18 >= 0 )
        break;
      if ( !v17 )
        goto LABEL_15;
      *v15 = 0;
LABEL_22:
      CoTaskMemFree(v15);
      v15 = 0;
LABEL_11:
      if ( v7 < 0 )
      {
        if ( v15 )
          CoTaskMemFree(v15);
        goto LABEL_3;
      }
LABEL_12:
      *((_QWORD *)a3[2] + i) = v15;
    }
    v18 = StringCopyWorkerW_0(v15, v19, v20, v9, v21);
LABEL_15:
    v7 = v18;
    if ( !v18 )
      goto LABEL_11;
    goto LABEL_22;
  }
  v7 = -2147024882;
LABEL_3:
  PropVariantClear(a3);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180004080  push    rbx
0x180004082  push    rbp
0x180004083  push    rsi
0x180004084  push    rdi
0x180004085  push    r12
0x180004087  push    r13
0x180004089  push    r14
0x18000408b  push    r15
0x18000408d  sub     rsp, 38h
0x180004091  mov     r15d, ecx
0x180004094  mov     r13, r8
0x180004097  mov     rcx, r8; pvar
0x18000409a  mov     r12, rdx
0x18000409d  call    cs:__imp_PropVariantClear
0x1800040a3  mov     ebx, r15d
0x1800040a6  mov     word ptr [r13+0], 101Fh
0x1800040ad  shl     rbx, 3
0x1800040b1  mov     rcx, rbx; cb
0x1800040b4  mov     [r13+8], r15d
0x1800040b8  call    cs:__imp_CoTaskMemAlloc
0x1800040be  mov     [r13+10h], rax
0x1800040c2  test    rax, rax
0x1800040c5  jnz     loc_180004185
0x1800040cb  mov     edi, 8007000Eh
0x1800040d0  mov     rcx, r13; pvar
0x1800040d3  call    cs:__imp_PropVariantClear
0x1800040d9  mov     eax, edi
0x1800040db  add     rsp, 38h
0x1800040df  pop     r15
0x1800040e1  pop     r14
0x1800040e3  pop     r13
0x1800040e5  pop     r12
0x1800040e7  pop     rdi
0x1800040e8  pop     rsi
0x1800040e9  pop     rbp
0x1800040ea  pop     rbx
0x1800040eb  retn
0x1800040f0  cmp     ebp, r15d
0x1800040f3  jnb     short loc_1800040D9
0x1800040f5  mov     eax, ebp
0x1800040f7  shl     rax, 5
0x1800040fb  mov     rbx, [rax+r12+8]
0x180004100  test    rbx, rbx
0x180004103  jz      loc_1800041B4
0x180004109  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180004110  cmp     word ptr [rbx+rax*2+2], 0
0x180004116  lea     rax, [rax+1]
0x18000411a  jnz     short loc_180004110
0x18000411c  lea     rsi, ds:2[rax*2]
0x180004124  mov     rcx, rsi; cb
0x180004127  call    cs:__imp_CoTaskMemAlloc
0x18000412d  mov     r11, rax
0x180004130  test    rax, rax
0x180004133  jnz     short loc_18000414A
0x180004135  mov     edi, 8007000Eh
0x18000413a  test    edi, edi
0x18000413c  js      short loc_18000416E
0x18000413e  mov     rax, [r13+10h]
0x180004142  mov     [rax+rbp*8], r11
0x180004146  inc     ebp
0x180004148  jmp     short loc_1800040F0
0x18000414a  shr     rsi, 1
0x18000414d  mov     rdx, rsi; cchDest
0x180004150  call    StringValidateDestW
0x180004155  mov     edi, eax
0x180004157  test    eax, eax
0x180004159  js      short loc_18000419B
0x18000415b  mov     r9, rbx; pszSrc
0x18000415e  mov     rcx, r11; pszDest
0x180004161  call    StringCopyWorkerW_0
0x180004166  mov     edi, eax
0x180004168  test    eax, eax
0x18000416a  jz      short loc_18000413A
0x18000416c  jmp     short loc_1800041A6
0x18000416e  test    r11, r11
0x180004171  jz      loc_1800040D0
0x180004177  mov     rcx, r11; pv
0x18000417a  call    cs:__imp_CoTaskMemFree
0x180004180  jmp     loc_1800040D0
0x180004185  mov     r8, rbx; Size
0x180004188  xor     edx, edx; Val
0x18000418a  mov     rcx, rax; void *
0x18000418d  xor     edi, edi
0x18000418f  call    memset_0
0x180004194  xor     ebp, ebp
0x180004196  jmp     loc_1800040F0
0x18000419b  test    rsi, rsi
0x18000419e  jz      short loc_180004166
0x1800041a0  xor     eax, eax
0x1800041a2  mov     [r11], ax
0x1800041a6  mov     rcx, r11; pv
0x1800041a9  call    cs:__imp_CoTaskMemFree
0x1800041af  xor     r11d, r11d
0x1800041b2  jmp     short loc_18000413A
0x1800041b4  xor     r11d, r11d
0x1800041b7  xor     edi, edi
0x1800041b9  jmp     short loc_18000413E
```
