# zip_read_data_deflate

- ea: `0x1800eab88`
- end: `0x1800eae7d`
- name: `zip_read_data_deflate`
- size: `757`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800e7f40`
- `0x1800e81f0`
- `0x1800eb920`

## callees

- `0x180005914`
- `0x180005c7c`
- `0x180006c00`
- `0x180012634`
- `0x1800b079c`
- `0x1800e88b8`
- `0x1800ea8b0`
- `0x1800eaa88`
- `0x1800eab88`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800eabd4`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800eabd4`
- `bcrypt!BCryptHashData` at `0x1800eae0f`
- `bcrypt!BCryptHashData` at `0x1800eae0f`

## string_xrefs

- `0x1800eabe6`: `No memory for ZIP decompression`
- `0x1800eae4d`: `Out of memory for ZIP decompression`
- `0x1800ead82`: `ZIP decompression failed (%d)`

## pseudocode

```c
__int64 __fastcall zip_read_data_deflate(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  __int64 *v4; // rax
  __int64 v7; // rbx
  void *v8; // rax
  const char *v9; // r8
  __int64 result; // rax
  __int64 v11; // rax
  UCHAR *v12; // rbp
  __int16 v13; // r10
  __int64 v14; // rdx
  char v15; // r8
  __int64 *v16; // r14
  __int64 v17; // rcx
  unsigned __int64 v18; // rdi
  __int64 v19; // rdx
  int v20; // r9d
  int v21; // eax
  __int64 v22; // rdi
  bool v23; // zf
  signed __int64 v24; // [rsp+78h] [rbp+20h] BYREF

  v24 = 0;
  v4 = *(__int64 **)(a1 + 2072);
  v7 = *v4;
  if ( !*(_QWORD *)(*v4 + 168) )
  {
    *(_QWORD *)(v7 + 176) = 0x40000;
    v8 = malloc(0x40000u);
    *(_QWORD *)(v7 + 168) = v8;
    if ( !v8 )
    {
      v9 = "No memory for ZIP decompression";
LABEL_45:
      archive_set_error(a1, 12, v9);
      return 4294967266LL;
    }
  }
  result = zip_deflate_init(a1, v7);
  if ( (_DWORD)result )
    return result;
  v11 = _archive_read_filter_ahead(*(_QWORD *)(a1 + 632), 1, &v24);
  v12 = (UCHAR *)v11;
  v13 = *(_WORD *)(*(_QWORD *)(v7 + 112) + 126LL) & 8;
  v14 = v24;
  if ( !v13 && v24 > *(_QWORD *)(v7 + 120) )
    v14 = *(_QWORD *)(v7 + 120);
  if ( v14 < 0 )
  {
    archive_set_error(a1, 42, "Truncated ZIP file body");
    return 4294967266LL;
  }
  v15 = *(_BYTE *)(v7 + 8044);
  if ( !v15 && !*(_BYTE *)(v7 + 8112) )
  {
    v16 = (__int64 *)(v7 + 8000);
    goto LABEL_28;
  }
  v17 = *(_QWORD *)(v7 + 8016);
  v16 = (__int64 *)(v7 + 8000);
  if ( v17 >= (unsigned __int64)v14 )
    goto LABEL_26;
  v18 = *(_QWORD *)(v7 + 7992) + *(_QWORD *)(v7 + 8008) - *v16 - v17;
  if ( v18 > v14 )
    v18 = v14;
  if ( !v13 )
  {
    v19 = *(_QWORD *)(v7 + 120);
    if ( v19 > 0 && (__int64)(v17 + v18) > v19 )
    {
      if ( v19 < v17 )
        goto LABEL_26;
      v18 = v19 - v17;
    }
  }
  if ( v18 )
  {
    v20 = v17 + *v16;
    if ( v15 )
    {
      trad_enc_decrypt_update(v7 + 8032, v11, v18, v20, v18);
    }
    else
    {
      v24 = v18;
      aes_ctr_update(v7 + 8048, v11, v18, v20, (__int64)&v24);
    }
    *(_QWORD *)(v7 + 8016) += v18;
    v14 = *(_QWORD *)(v7 + 8016);
    goto LABEL_27;
  }
LABEL_26:
  v14 = *(_QWORD *)(v7 + 8016);
LABEL_27:
  v11 = *v16;
LABEL_28:
  *(_DWORD *)(v7 + 192) = v14;
  *(_QWORD *)(v7 + 184) = v11;
  *(_QWORD *)(v7 + 200) = *(_QWORD *)(v7 + 168);
  *(_DWORD *)(v7 + 208) = *(_DWORD *)(v7 + 176);
  *(_DWORD *)(v7 + 196) = 0;
  *(_DWORD *)(v7 + 212) = 0;
  v21 = inflate(v7 + 184, 0);
  if ( v21 == -4 )
  {
    v9 = "Out of memory for ZIP decompression";
    goto LABEL_45;
  }
  if ( v21 )
  {
    if ( v21 != 1 )
    {
      archive_set_error(a1, 0xFFFFFFFFLL, "ZIP decompression failed (%d)", v21);
      return 4294967266LL;
    }
    *(_BYTE *)(v7 + 162) = 1;
  }
  v22 = *(unsigned int *)(v7 + 196);
  _archive_read_filter_consume(*(_QWORD *)(a1 + 632), v22);
  *(_QWORD *)(v7 + 136) += *(unsigned int *)(v7 + 212);
  *(_QWORD *)(v7 + 120) -= v22;
  *(_QWORD *)(v7 + 128) += v22;
  if ( *(_BYTE *)(v7 + 8044) || *(_BYTE *)(v7 + 8112) )
  {
    v23 = *(_QWORD *)(v7 + 8016) == v22;
    *(_QWORD *)(v7 + 8016) -= v22;
    if ( v23 )
      *v16 = *(_QWORD *)(v7 + 7992);
    else
      *v16 += v22;
  }
  if ( *(_BYTE *)(v7 + 8152) )
    BCryptHashData(*(BCRYPT_HASH_HANDLE *)(v7 + 8128), v12, v22, 0);
  if ( !*(_BYTE *)(v7 + 162) || !*(_BYTE *)(v7 + 8152) || (result = check_authentication_code(a1, 0), !(_DWORD)result) )
  {
    *a3 = *(unsigned int *)(v7 + 212);
    *a2 = *(_QWORD *)(v7 + 168);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800eab88  mov     rax, rsp
0x1800eab8b  mov     [rax+8], rbx
0x1800eab8f  mov     [rax+10h], rbp
0x1800eab93  mov     [rax+20h], r9
0x1800eab97  push    rsi
0x1800eab98  push    rdi
0x1800eab99  push    r12
0x1800eab9b  push    r14
0x1800eab9d  push    r15
0x1800eab9f  sub     rsp, 30h
0x1800eaba3  mov     qword ptr [rax+20h], 0
0x1800eabab  mov     r15, r8
0x1800eabae  mov     rax, [rcx+818h]
0x1800eabb5  mov     r12, rdx
0x1800eabb8  mov     rsi, rcx
0x1800eabbb  mov     rbx, [rax]
0x1800eabbe  cmp     qword ptr [rbx+0A8h], 0
0x1800eabc6  jnz     short loc_1800EABF2
0x1800eabc8  mov     ecx, 40000h; Size
0x1800eabcd  mov     [rbx+0B0h], rcx
0x1800eabd4  call    cs:__imp_malloc
0x1800eabda  mov     [rbx+0A8h], rax
0x1800eabe1  test    rax, rax
0x1800eabe4  jnz     short loc_1800EABF2
0x1800eabe6  lea     r8, aNoMemoryForZip_0; "No memory for ZIP decompression"
0x1800eabed  jmp     loc_1800EAE54
0x1800eabf2  mov     rdx, rbx
0x1800eabf5  mov     rcx, rsi
0x1800eabf8  call    zip_deflate_init
0x1800eabfd  test    eax, eax
0x1800eabff  jnz     loc_1800EAE66
0x1800eac05  mov     rcx, [rsi+278h]
0x1800eac0c  lea     r8, [rsp+58h+arg_18]
0x1800eac11  lea     edx, [rax+1]
0x1800eac14  call    __archive_read_filter_ahead
0x1800eac19  mov     rcx, [rbx+70h]
0x1800eac1d  mov     rbp, rax
0x1800eac20  movzx   edx, word ptr [rcx+7Eh]
0x1800eac24  xor     ecx, ecx
0x1800eac26  and     dx, 8
0x1800eac2a  movzx   r10d, dx
0x1800eac2e  cmp     cx, dx
0x1800eac31  mov     rdx, [rsp+58h+arg_18]
0x1800eac36  jnz     short loc_1800EAC41
0x1800eac38  cmp     rdx, [rbx+78h]
0x1800eac3c  cmovg   rdx, [rbx+78h]
0x1800eac41  test    rdx, rdx
0x1800eac44  jns     short loc_1800EAC57
0x1800eac46  lea     r8, aTruncatedZipFi_0; "Truncated ZIP file body"
0x1800eac4d  mov     edx, 2Ah ; '*'
0x1800eac52  jmp     loc_1800EAE59
0x1800eac57  mov     r8b, [rbx+1F6Ch]
0x1800eac5e  test    r8b, r8b
0x1800eac61  jnz     short loc_1800EAC77
0x1800eac63  cmp     [rbx+1FB0h], cl
0x1800eac69  jnz     short loc_1800EAC77
0x1800eac6b  lea     r14, [rbx+1F40h]
0x1800eac72  jmp     loc_1800EAD28
0x1800eac77  mov     rcx, [rbx+1F50h]
0x1800eac7e  lea     r14, [rbx+1F40h]
0x1800eac85  cmp     rcx, rdx
0x1800eac88  jnb     loc_1800EAD22
0x1800eac8e  mov     rdi, [rbx+1F48h]
0x1800eac95  add     rdi, [rbx+1F38h]
0x1800eac9c  mov     r9, [r14]
0x1800eac9f  sub     rdi, r9
0x1800eaca2  sub     rdi, rcx
0x1800eaca5  cmp     rdi, rdx
0x1800eaca8  cmova   rdi, rdx
0x1800eacac  xor     eax, eax
0x1800eacae  cmp     ax, r10w
0x1800eacb2  jnz     short loc_1800EACD1
0x1800eacb4  mov     rdx, [rbx+78h]
0x1800eacb8  test    rdx, rdx
0x1800eacbb  jle     short loc_1800EACD1
0x1800eacbd  lea     rax, [rcx+rdi]
0x1800eacc1  cmp     rax, rdx
0x1800eacc4  jle     short loc_1800EACD1
0x1800eacc6  cmp     rdx, rcx
0x1800eacc9  jl      short loc_1800EAD22
0x1800eaccb  mov     rdi, rdx
0x1800eacce  sub     rdi, rcx
0x1800eacd1  test    rdi, rdi
0x1800eacd4  jz      short loc_1800EAD22
0x1800eacd6  add     r9, rcx
0x1800eacd9  mov     rdx, rbp
0x1800eacdc  test    r8b, r8b
0x1800eacdf  mov     r8, rdi
0x1800eace2  jz      short loc_1800EACF7
0x1800eace4  lea     rcx, [rbx+1F60h]
0x1800eaceb  mov     [rsp+58h+var_38], rdi
0x1800eacf0  call    trad_enc_decrypt_update
0x1800eacf5  jmp     short loc_1800EAD12
0x1800eacf7  lea     rax, [rsp+58h+arg_18]
0x1800eacfc  mov     [rsp+58h+arg_18], rdi
0x1800ead01  lea     rcx, [rbx+1F70h]
0x1800ead08  mov     [rsp+58h+var_38], rax
0x1800ead0d  call    aes_ctr_update
0x1800ead12  add     [rbx+1F50h], rdi
0x1800ead19  mov     rdx, [rbx+1F50h]
0x1800ead20  jmp     short loc_1800EAD25
0x1800ead22  mov     rdx, rcx
0x1800ead25  mov     rax, [r14]
0x1800ead28  lea     rcx, [rbx+0B8h]
0x1800ead2f  mov     [rbx+0C0h], edx
0x1800ead35  mov     [rcx], rax
0x1800ead38  xor     edx, edx
0x1800ead3a  mov     rax, [rbx+0A8h]
0x1800ead41  mov     [rbx+0C8h], rax
0x1800ead48  mov     eax, [rbx+0B0h]
0x1800ead4e  mov     [rbx+0D0h], eax
0x1800ead54  mov     dword ptr [rbx+0C4h], 0
0x1800ead5e  mov     dword ptr [rbx+0D4h], 0
0x1800ead68  call    inflate
0x1800ead6d  cmp     eax, 0FFFFFFFCh
0x1800ead70  jz      loc_1800EAE4D
0x1800ead76  test    eax, eax
0x1800ead78  jz      short loc_1800EADA0
0x1800ead7a  cmp     eax, 1
0x1800ead7d  jz      short loc_1800EAD99
0x1800ead7f  mov     r9d, eax
0x1800ead82  lea     r8, aZipDecompressi; "ZIP decompression failed (%d)"
0x1800ead89  or      edx, 0FFFFFFFFh
0x1800ead8c  mov     rcx, rsi
0x1800ead8f  call    archive_set_error
0x1800ead94  jmp     loc_1800EAE61
0x1800ead99  mov     byte ptr [rbx+0A2h], 1
0x1800eada0  mov     edi, [rbx+0C4h]
0x1800eada6  mov     rcx, [rsi+278h]
0x1800eadad  mov     edx, edi
0x1800eadaf  call    __archive_read_filter_consume
0x1800eadb4  mov     eax, [rbx+0D4h]
0x1800eadba  add     [rbx+88h], rax
0x1800eadc1  sub     [rbx+78h], rdi
0x1800eadc5  add     [rbx+80h], rdi
0x1800eadcc  cmp     byte ptr [rbx+1F6Ch], 0
0x1800eadd3  jnz     short loc_1800EADDE
0x1800eadd5  cmp     byte ptr [rbx+1FB0h], 0
0x1800eaddc  jz      short loc_1800EADF6
0x1800eadde  sub     [rbx+1F50h], rdi
0x1800eade5  jnz     short loc_1800EADF3
0x1800eade7  mov     rax, [rbx+1F38h]
0x1800eadee  mov     [r14], rax
0x1800eadf1  jmp     short loc_1800EADF6
0x1800eadf3  add     [r14], rdi
0x1800eadf6  cmp     byte ptr [rbx+1FD8h], 0
0x1800eadfd  jz      short loc_1800EAE15
0x1800eadff  mov     rcx, [rbx+1FC0h]; hHash
0x1800eae06  xor     r9d, r9d; dwFlags
0x1800eae09  mov     r8d, edi; cbInput
0x1800eae0c  mov     rdx, rbp; pbInput
0x1800eae0f  call    cs:__imp_BCryptHashData
0x1800eae15  cmp     byte ptr [rbx+0A2h], 0
0x1800eae1c  jz      short loc_1800EAE35
0x1800eae1e  cmp     byte ptr [rbx+1FD8h], 0
0x1800eae25  jz      short loc_1800EAE35
0x1800eae27  xor     edx, edx
0x1800eae29  mov     rcx, rsi
0x1800eae2c  call    check_authentication_code
0x1800eae31  test    eax, eax
0x1800eae33  jnz     short loc_1800EAE66
0x1800eae35  mov     eax, [rbx+0D4h]
0x1800eae3b  mov     [r15], rax
0x1800eae3e  mov     rax, [rbx+0A8h]
0x1800eae45  mov     [r12], rax
0x1800eae49  xor     eax, eax
0x1800eae4b  jmp     short loc_1800EAE66
0x1800eae4d  lea     r8, aOutOfMemoryFor_0; "Out of memory for ZIP decompression"
0x1800eae54  mov     edx, 0Ch
0x1800eae59  mov     rcx, rsi
0x1800eae5c  call    archive_set_error
0x1800eae61  mov     eax, 0FFFFFFE2h
0x1800eae66  mov     rbx, [rsp+58h+arg_0]
0x1800eae6b  mov     rbp, [rsp+58h+arg_8]
0x1800eae70  add     rsp, 30h
0x1800eae74  pop     r15
0x1800eae76  pop     r14
0x1800eae78  pop     r12
0x1800eae7a  pop     rdi
0x1800eae7b  pop     rsi
0x1800eae7c  retn
```
