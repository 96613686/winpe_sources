# CMetadataAPEReaderWriter::SetValue(uint,tagPROPVARIANT const *)

- ea: `0x1800c7450`
- end: `0x1800c75d7`
- name: `?SetValue@CMetadataAPEReaderWriter@@MEAAJIPEBUtagPROPVARIANT@@@Z`
- size: `391`
- prototype: `int(CMetadataAPEReaderWriter *__hidden this, unsigned int, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800bd9d4`
- `0x1800c7450`
- `0x1800c75e0`
- `0x18017e438`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800c74ce`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800c74ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c752f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c752f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800c74b6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800c74ea`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800c74b6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800c74ea`

## pseudocode

```c
__int64 __fastcall CMetadataAPEReaderWriter::SetValue(CMetadataAPEReaderWriter *this, int a2, const PROPVARIANT *a3)
{
  int v5; // edx
  LONG v6; // r8d
  unsigned __int8 *v7; // rdx
  HRESULT v8; // eax
  unsigned int v9; // ebx
  int v10; // ecx
  PROPVARIANT *v11; // rcx
  LONG v12; // ebp
  SIZE_T v13; // rcx
  size_t v14; // rbp
  void *v15; // rax
  BYTE *v16; // rdx
  int v18; // [rsp+68h] [rbp+10h] BYREF

  v5 = a2 - 1;
  if ( !v5 )
  {
    v9 = 0;
    if ( !*(_WORD *)a3 )
    {
      *((_QWORD *)this + 19) = 0;
      *((_WORD *)this + 80) = 0;
      *((_BYTE *)this + 162) = 0;
      *((_DWORD *)this + 41) = 0;
      return v9;
    }
    v16 = (BYTE *)*((_QWORD *)a3 + 2);
    if ( v16 && *((_DWORD *)a3 + 2) == 11 )
    {
      memcpy_0((char *)this + 152, v16, *((unsigned int *)a3 + 2));
      *((_DWORD *)this + 41) = 1;
      return v9;
    }
    goto LABEL_23;
  }
  if ( v5 != 1 )
  {
LABEL_23:
    v9 = -2147024809;
    goto LABEL_24;
  }
  v6 = *((_DWORD *)a3 + 2);
  v7 = (unsigned __int8 *)*((_QWORD *)a3 + 2);
  v18 = 0;
  v8 = CMetadataAPEReaderWriter::HrCheckApplicationData(this, v7, v6, &v18);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v11 = (PROPVARIANT *)((char *)this + 168);
    if ( !v18 )
    {
      v8 = PropVariantClear(v11);
      v9 = v8;
      if ( v8 >= 0 )
      {
        v8 = PropVariantCopy((PROPVARIANT *)this + 21, a3);
        v9 = v8;
        if ( v8 >= 0 )
          return v9;
      }
      goto LABEL_4;
    }
    v12 = *((_DWORD *)a3 + 2);
    v8 = PropVariantClear(v11);
    v9 = v8;
    if ( v8 < 0 )
    {
      if ( !(_DWORD)g_doStackCaptures )
        return v9;
      goto LABEL_5;
    }
    v13 = (unsigned int)(v12 - 1);
    *((_WORD *)this + 84) = *(_WORD *)a3;
    *((_DWORD *)this + 44) = v13;
    if ( v12 == 1 )
    {
      *((_QWORD *)this + 23) = 0;
      return v9;
    }
    v14 = (unsigned int)v13;
    v15 = CoTaskMemAlloc(v13);
    *((_QWORD *)this + 23) = v15;
    if ( v15 )
    {
      memcpy_0(v15, *((const void **)a3 + 2), v14);
      return v9;
    }
    v9 = -2147024882;
LABEL_24:
    if ( (_DWORD)g_doStackCaptures )
    {
      v10 = v9;
      goto LABEL_26;
    }
    return v9;
  }
LABEL_4:
  if ( (_DWORD)g_doStackCaptures )
  {
LABEL_5:
    v10 = v8;
LABEL_26:
    DoStackCapture(v10);
  }
  return v9;
}

```

## disassembly

```asm
0x1800c7450  push    rbx
0x1800c7452  push    rbp
0x1800c7453  push    rsi
0x1800c7454  push    rdi
0x1800c7455  push    r14
0x1800c7457  push    r15
0x1800c7459  sub     rsp, 28h
0x1800c745d  mov     r14, r8
0x1800c7460  mov     rsi, rcx
0x1800c7463  sub     edx, 1
0x1800c7466  jz      loc_1800C755F
0x1800c746c  xor     edi, edi
0x1800c746e  cmp     edx, 1
0x1800c7471  jnz     loc_1800C75B3
0x1800c7477  mov     r8d, [r8+8]; unsigned int
0x1800c747b  lea     r9, [rsp+58h+arg_8]; int *
0x1800c7480  mov     rdx, [r14+10h]; unsigned __int8 *
0x1800c7484  mov     [rsp+58h+arg_8], edi
0x1800c7488  call    ?HrCheckApplicationData@CMetadataAPEReaderWriter@@MEAAJPEAEIPEAH@Z; CMetadataAPEReaderWriter::HrCheckApplicationData(uchar *,uint,int *)
0x1800c748d  mov     ebx, eax
0x1800c748f  test    eax, eax
0x1800c7491  jns     short loc_1800C74A6
0x1800c7493  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x1800c7499  jz      loc_1800C75C7
0x1800c749f  mov     ecx, eax
0x1800c74a1  jmp     loc_1800C75C2
0x1800c74a6  lea     r15, [rsi+0A8h]
0x1800c74ad  mov     rcx, r15; pvar
0x1800c74b0  cmp     [rsp+58h+arg_8], edi
0x1800c74b4  jnz     short loc_1800C74E6
0x1800c74b6  call    cs:__imp_PropVariantClear
0x1800c74bd  nop     dword ptr [rax+rax+00h]
0x1800c74c2  mov     ebx, eax
0x1800c74c4  test    eax, eax
0x1800c74c6  js      short loc_1800C7493
0x1800c74c8  mov     rdx, r14; pvarSrc
0x1800c74cb  mov     rcx, r15; pvarDest
0x1800c74ce  call    cs:__imp_PropVariantCopy
0x1800c74d5  nop     dword ptr [rax+rax+00h]
0x1800c74da  mov     ebx, eax
0x1800c74dc  test    eax, eax
0x1800c74de  jns     loc_1800C75C7
0x1800c74e4  jmp     short loc_1800C7493
0x1800c74e6  mov     ebp, [r14+8]
0x1800c74ea  call    cs:__imp_PropVariantClear
0x1800c74f1  nop     dword ptr [rax+rax+00h]
0x1800c74f6  mov     ebx, eax
0x1800c74f8  test    eax, eax
0x1800c74fa  jns     short loc_1800C750C
0x1800c74fc  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x1800c7502  jnz     short loc_1800C749F
0x1800c7504  test    eax, eax
0x1800c7506  js      loc_1800C75C7
0x1800c750c  movzx   eax, word ptr [r14]
0x1800c7510  lea     ecx, [rbp-1]; cb
0x1800c7513  mov     [r15], ax
0x1800c7517  mov     [rsi+0B0h], ecx
0x1800c751d  test    ecx, ecx
0x1800c751f  jnz     short loc_1800C752D
0x1800c7521  mov     [rsi+0B8h], rdi
0x1800c7528  jmp     loc_1800C75C7
0x1800c752d  mov     ebp, ecx
0x1800c752f  call    cs:__imp_CoTaskMemAlloc
0x1800c7536  nop     dword ptr [rax+rax+00h]
0x1800c753b  mov     [rsi+0B8h], rax
0x1800c7542  test    rax, rax
0x1800c7545  jnz     short loc_1800C754E
0x1800c7547  mov     ebx, 8007000Eh
0x1800c754c  jmp     short loc_1800C75B8
0x1800c754e  mov     rdx, [r14+10h]; Src
0x1800c7552  mov     r8, rbp; Size
0x1800c7555  mov     rcx, rax; void *
0x1800c7558  call    memcpy_0
0x1800c755d  jmp     short loc_1800C75C7
0x1800c755f  xor     edi, edi
0x1800c7561  mov     ebx, edi
0x1800c7563  cmp     [r8], di
0x1800c7567  jnz     short loc_1800C7587
0x1800c7569  xor     eax, eax
0x1800c756b  mov     [rcx+98h], rax
0x1800c7572  mov     [rcx+0A0h], ax
0x1800c7579  mov     [rcx+0A2h], al
0x1800c757f  mov     [rcx+0A4h], edi
0x1800c7585  jmp     short loc_1800C75C7
0x1800c7587  mov     rdx, [r8+10h]; Src
0x1800c758b  test    rdx, rdx
0x1800c758e  jz      short loc_1800C75B3
0x1800c7590  cmp     dword ptr [r8+8], 0Bh
0x1800c7595  jnz     short loc_1800C75B3
0x1800c7597  mov     r8d, [r8+8]; Size
0x1800c759b  add     rcx, 98h; void *
0x1800c75a2  call    memcpy_0
0x1800c75a7  mov     dword ptr [rsi+0A4h], 1
0x1800c75b1  jmp     short loc_1800C75C7
0x1800c75b3  mov     ebx, 80070057h
0x1800c75b8  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x1800c75be  jz      short loc_1800C75C7
0x1800c75c0  mov     ecx, ebx; int
0x1800c75c2  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800c75c7  mov     eax, ebx
0x1800c75c9  add     rsp, 28h
0x1800c75cd  pop     r15
0x1800c75cf  pop     r14
0x1800c75d1  pop     rdi
0x1800c75d2  pop     rsi
0x1800c75d3  pop     rbp
0x1800c75d4  pop     rbx
0x1800c75d5  retn
```
