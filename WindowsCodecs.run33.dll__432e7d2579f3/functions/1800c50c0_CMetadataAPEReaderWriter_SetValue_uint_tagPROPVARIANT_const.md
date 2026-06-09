# CMetadataAPEReaderWriter::SetValue(uint,tagPROPVARIANT const *)

- ea: `0x1800c50c0`
- end: `0x1800c522e`
- name: `?SetValue@CMetadataAPEReaderWriter@@MEAAJIPEBUtagPROPVARIANT@@@Z`
- size: `366`
- prototype: `int(CMetadataAPEReaderWriter *__hidden this, unsigned int, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800bb784`
- `0x1800c50c0`
- `0x1800c5240`
- `0x18017b528`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800c5138`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800c5138`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c518d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c518d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800c5126`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800c514e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800c5126`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800c514e`

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
0x1800c50c0  push    rbx
0x1800c50c2  push    rbp
0x1800c50c3  push    rsi
0x1800c50c4  push    rdi
0x1800c50c5  push    r14
0x1800c50c7  push    r15
0x1800c50c9  sub     rsp, 28h
0x1800c50cd  mov     r14, r8
0x1800c50d0  mov     rsi, rcx
0x1800c50d3  sub     edx, 1
0x1800c50d6  jz      loc_1800C51B7
0x1800c50dc  xor     edi, edi
0x1800c50de  cmp     edx, 1
0x1800c50e1  jnz     loc_1800C520B
0x1800c50e7  mov     r8d, [r8+8]; unsigned int
0x1800c50eb  lea     r9, [rsp+58h+arg_8]; int *
0x1800c50f0  mov     rdx, [r14+10h]; unsigned __int8 *
0x1800c50f4  mov     [rsp+58h+arg_8], edi
0x1800c50f8  call    ?HrCheckApplicationData@CMetadataAPEReaderWriter@@MEAAJPEAEIPEAH@Z; CMetadataAPEReaderWriter::HrCheckApplicationData(uchar *,uint,int *)
0x1800c50fd  mov     ebx, eax
0x1800c50ff  test    eax, eax
0x1800c5101  jns     short loc_1800C5116
0x1800c5103  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x1800c5109  jz      loc_1800C521F
0x1800c510f  mov     ecx, eax
0x1800c5111  jmp     loc_1800C521A
0x1800c5116  lea     r15, [rsi+0A8h]
0x1800c511d  mov     rcx, r15; pvar
0x1800c5120  cmp     [rsp+58h+arg_8], edi
0x1800c5124  jnz     short loc_1800C514A
0x1800c5126  call    cs:__imp_PropVariantClear
0x1800c512c  mov     ebx, eax
0x1800c512e  test    eax, eax
0x1800c5130  js      short loc_1800C5103
0x1800c5132  mov     rdx, r14; pvarSrc
0x1800c5135  mov     rcx, r15; pvarDest
0x1800c5138  call    cs:__imp_PropVariantCopy
0x1800c513e  mov     ebx, eax
0x1800c5140  test    eax, eax
0x1800c5142  jns     loc_1800C521F
0x1800c5148  jmp     short loc_1800C5103
0x1800c514a  mov     ebp, [r14+8]
0x1800c514e  call    cs:__imp_PropVariantClear
0x1800c5154  mov     ebx, eax
0x1800c5156  test    eax, eax
0x1800c5158  jns     short loc_1800C516A
0x1800c515a  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x1800c5160  jnz     short loc_1800C510F
0x1800c5162  test    eax, eax
0x1800c5164  js      loc_1800C521F
0x1800c516a  movzx   eax, word ptr [r14]
0x1800c516e  lea     ecx, [rbp-1]; cb
0x1800c5171  mov     [r15], ax
0x1800c5175  mov     [rsi+0B0h], ecx
0x1800c517b  test    ecx, ecx
0x1800c517d  jnz     short loc_1800C518B
0x1800c517f  mov     [rsi+0B8h], rdi
0x1800c5186  jmp     loc_1800C521F
0x1800c518b  mov     ebp, ecx
0x1800c518d  call    cs:__imp_CoTaskMemAlloc
0x1800c5193  mov     [rsi+0B8h], rax
0x1800c519a  test    rax, rax
0x1800c519d  jnz     short loc_1800C51A6
0x1800c519f  mov     ebx, 8007000Eh
0x1800c51a4  jmp     short loc_1800C5210
0x1800c51a6  mov     rdx, [r14+10h]; Src
0x1800c51aa  mov     r8, rbp; Size
0x1800c51ad  mov     rcx, rax; void *
0x1800c51b0  call    memcpy_0
0x1800c51b5  jmp     short loc_1800C521F
0x1800c51b7  xor     edi, edi
0x1800c51b9  mov     ebx, edi
0x1800c51bb  cmp     [r8], di
0x1800c51bf  jnz     short loc_1800C51DF
0x1800c51c1  xor     eax, eax
0x1800c51c3  mov     [rcx+98h], rax
0x1800c51ca  mov     [rcx+0A0h], ax
0x1800c51d1  mov     [rcx+0A2h], al
0x1800c51d7  mov     [rcx+0A4h], edi
0x1800c51dd  jmp     short loc_1800C521F
0x1800c51df  mov     rdx, [r8+10h]; Src
0x1800c51e3  test    rdx, rdx
0x1800c51e6  jz      short loc_1800C520B
0x1800c51e8  cmp     dword ptr [r8+8], 0Bh
0x1800c51ed  jnz     short loc_1800C520B
0x1800c51ef  mov     r8d, [r8+8]; Size
0x1800c51f3  add     rcx, 98h; void *
0x1800c51fa  call    memcpy_0
0x1800c51ff  mov     dword ptr [rsi+0A4h], 1
0x1800c5209  jmp     short loc_1800C521F
0x1800c520b  mov     ebx, 80070057h
0x1800c5210  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x1800c5216  jz      short loc_1800C521F
0x1800c5218  mov     ecx, ebx; int
0x1800c521a  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800c521f  mov     eax, ebx
0x1800c5221  add     rsp, 28h
0x1800c5225  pop     r15
0x1800c5227  pop     r14
0x1800c5229  pop     rdi
0x1800c522a  pop     rsi
0x1800c522b  pop     rbp
0x1800c522c  pop     rbx
0x1800c522d  retn
```
