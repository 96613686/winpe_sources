# UtilAssembleStringsWithAlloc(ushort * *,uint,ushort const *,ushort const *,uchar,ulong)

- ea: `0x180006560`
- end: `0x180006722`
- name: `?UtilAssembleStringsWithAlloc@@YAJPEAPEAGIPEBG1EK@Z`
- size: `450`
- prototype: `__int64 __fastcall(unsigned __int16 **, __int64, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800049d0`

## callees

- `0x180005dc0`
- `0x180006560`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000658d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006609`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006683`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000658d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006609`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006683`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800065dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006654`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006666`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006699`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800066a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800066de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800066ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000671a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800065dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006654`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006666`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006699`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800066a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800066de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800066ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000671a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000663c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000663c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800065bb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180006632`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800065bb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180006632`

## pseudocode

```c
__int64 __fastcall UtilAssembleStringsWithAlloc(
        unsigned __int16 **a1,
        __int64 a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  unsigned __int16 *v4; // rbx
  const unsigned __int16 *v6; // r15
  WCHAR *v8; // rax
  signed int LastError; // eax
  signed int v11; // edi
  unsigned __int16 *v12; // rdi
  WCHAR *v13; // rax
  unsigned __int16 *v14; // rsi
  signed int v15; // edi
  signed int v16; // eax
  unsigned __int16 *v17; // rax
  unsigned __int16 *v18; // rbp
  int v19; // esi

  v4 = 0;
  v6 = a3;
  if ( (unsigned __int64)a3 < 0x10000 )
  {
    v8 = (WCHAR *)CoTaskMemAlloc(0x800u);
    v4 = v8;
    if ( !v8 )
      return 2147942414LL;
    if ( LoadStringW(hInstance, (unsigned __int16)v6, v8, 1024) )
    {
      v6 = v4;
    }
    else
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      CoTaskMemFree(v4);
      v4 = (unsigned __int16 *)v6;
      if ( v11 < 0 )
        return (unsigned int)v11;
    }
  }
  v12 = 0;
  if ( (unsigned __int64)a4 < 0x10000 )
  {
    v13 = (WCHAR *)CoTaskMemAlloc(0x800u);
    v14 = v13;
    if ( !v13 )
    {
      v15 = -2147024882;
LABEL_17:
      if ( v4 )
        CoTaskMemFree(v4);
      return (unsigned int)v15;
    }
    if ( LoadStringW(hInstance, (unsigned __int16)a4, v13, 1024) )
    {
      a4 = v14;
    }
    else
    {
      v16 = GetLastError();
      v15 = v16;
      if ( v16 > 0 )
        v15 = (unsigned __int16)v16 | 0x80070000;
      CoTaskMemFree(v14);
      if ( v15 < 0 )
        goto LABEL_17;
    }
    v12 = a4;
  }
  v17 = (unsigned __int16 *)CoTaskMemAlloc(0x800u);
  v18 = v17;
  if ( !v17 )
  {
    if ( v12 )
      CoTaskMemFree(v12);
    if ( v4 )
      CoTaskMemFree(v4);
    return 2147942414LL;
  }
  v19 = StringCchPrintfW(v17, 0x400u, v6, a4);
  if ( v19 == -2147024774 )
  {
    v19 = 0;
  }
  else if ( v19 < 0 )
  {
    CoTaskMemFree(v18);
    goto LABEL_31;
  }
  *a1 = v18;
LABEL_31:
  if ( v12 )
    CoTaskMemFree(v12);
  if ( v4 )
    CoTaskMemFree(v4);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x180006560  mov     [rsp+arg_10], rbx
0x180006565  mov     [rsp+arg_18], rdi
0x18000656a  push    r12
0x18000656c  push    r14
0x18000656e  push    r15
0x180006570  sub     rsp, 20h
0x180006574  xor     ebx, ebx
0x180006576  mov     r14, r9
0x180006579  mov     r15, r8
0x18000657c  mov     r12, rcx
0x18000657f  cmp     r8, 10000h
0x180006586  jnb     short loc_1800065F4
0x180006588  mov     ecx, 800h; cb
0x18000658d  call    cs:__imp_CoTaskMemAlloc
0x180006593  mov     rbx, rax
0x180006596  test    rax, rax
0x180006599  jnz     short loc_1800065A7
0x18000659b  mov     edi, 8007000Eh
0x1800065a0  mov     eax, edi
0x1800065a2  jmp     loc_1800066FE
0x1800065a7  mov     rcx, cs:hInstance; hInstance
0x1800065ae  mov     r9d, 400h; cchBufferMax
0x1800065b4  movzx   edx, r15w; uID
0x1800065b8  mov     r8, rbx; lpBuffer
0x1800065bb  call    cs:__imp_LoadStringW
0x1800065c1  test    eax, eax
0x1800065c3  jnz     short loc_1800065F1
0x1800065c5  call    cs:__imp_GetLastError
0x1800065cb  mov     edi, eax
0x1800065cd  test    eax, eax
0x1800065cf  jle     short loc_1800065DA
0x1800065d1  movzx   edi, ax
0x1800065d4  or      edi, 80070000h
0x1800065da  mov     rcx, rbx; pv
0x1800065dd  call    cs:__imp_CoTaskMemFree
0x1800065e3  mov     rbx, r15
0x1800065e6  test    edi, edi
0x1800065e8  jns     short loc_1800065F4
0x1800065ea  mov     eax, edi
0x1800065ec  jmp     loc_1800066FE
0x1800065f1  mov     r15, rbx
0x1800065f4  xor     edi, edi
0x1800065f6  mov     [rsp+38h+arg_8], rsi
0x1800065fb  cmp     r14, 10000h
0x180006602  jnb     short loc_180006679
0x180006604  mov     ecx, 800h; cb
0x180006609  call    cs:__imp_CoTaskMemAlloc
0x18000660f  mov     rsi, rax
0x180006612  test    rax, rax
0x180006615  jnz     short loc_18000661E
0x180006617  mov     edi, 8007000Eh
0x18000661c  jmp     short loc_18000665E
0x18000661e  mov     rcx, cs:hInstance; hInstance
0x180006625  mov     r9d, 400h; cchBufferMax
0x18000662b  movzx   edx, r14w; uID
0x18000662f  mov     r8, rsi; lpBuffer
0x180006632  call    cs:__imp_LoadStringW
0x180006638  test    eax, eax
0x18000663a  jnz     short loc_180006673
0x18000663c  call    cs:__imp_GetLastError
0x180006642  mov     edi, eax
0x180006644  test    eax, eax
0x180006646  jle     short loc_180006651
0x180006648  movzx   edi, ax
0x18000664b  or      edi, 80070000h
0x180006651  mov     rcx, rsi; pv
0x180006654  call    cs:__imp_CoTaskMemFree
0x18000665a  test    edi, edi
0x18000665c  jns     short loc_180006676
0x18000665e  test    rbx, rbx
0x180006661  jz      short loc_18000666C
0x180006663  mov     rcx, rbx; pv
0x180006666  call    cs:__imp_CoTaskMemFree
0x18000666c  mov     eax, edi
0x18000666e  jmp     loc_1800066F9
0x180006673  mov     r14, rsi
0x180006676  mov     rdi, r14
0x180006679  mov     ecx, 800h; cb
0x18000667e  mov     [rsp+38h+arg_0], rbp
0x180006683  call    cs:__imp_CoTaskMemAlloc
0x180006689  mov     rbp, rax
0x18000668c  test    rax, rax
0x18000668f  jnz     short loc_1800066B4
0x180006691  test    rdi, rdi
0x180006694  jz      short loc_18000669F
0x180006696  mov     rcx, rdi; pv
0x180006699  call    cs:__imp_CoTaskMemFree
0x18000669f  test    rbx, rbx
0x1800066a2  jz      short loc_1800066AD
0x1800066a4  mov     rcx, rbx; pv
0x1800066a7  call    cs:__imp_CoTaskMemFree
0x1800066ad  mov     eax, 8007000Eh
0x1800066b2  jmp     short loc_1800066F4
0x1800066b4  mov     r9, r14
0x1800066b7  mov     r8, r15; unsigned __int16 *
0x1800066ba  mov     edx, 400h; unsigned __int64
0x1800066bf  mov     rcx, rbp; unsigned __int16 *
0x1800066c2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800066c7  mov     esi, eax
0x1800066c9  cmp     eax, 8007007Ah
0x1800066ce  jnz     short loc_180006713
0x1800066d0  xor     esi, esi
0x1800066d2  mov     [r12], rbp
0x1800066d6  test    rdi, rdi
0x1800066d9  jz      short loc_1800066E4
0x1800066db  mov     rcx, rdi; pv
0x1800066de  call    cs:__imp_CoTaskMemFree
0x1800066e4  test    rbx, rbx
0x1800066e7  jz      short loc_1800066F2
0x1800066e9  mov     rcx, rbx; pv
0x1800066ec  call    cs:__imp_CoTaskMemFree
0x1800066f2  mov     eax, esi
0x1800066f4  mov     rbp, [rsp+38h+arg_0]
0x1800066f9  mov     rsi, [rsp+38h+arg_8]
0x1800066fe  mov     rbx, [rsp+38h+arg_10]
0x180006703  mov     rdi, [rsp+38h+arg_18]
0x180006708  add     rsp, 20h
0x18000670c  pop     r15
0x18000670e  pop     r14
0x180006710  pop     r12
0x180006712  retn
0x180006713  test    esi, esi
0x180006715  jns     short loc_1800066D2
0x180006717  mov     rcx, rbp; pv
0x18000671a  call    cs:__imp_CoTaskMemFree
0x180006720  jmp     short loc_1800066D6
```
