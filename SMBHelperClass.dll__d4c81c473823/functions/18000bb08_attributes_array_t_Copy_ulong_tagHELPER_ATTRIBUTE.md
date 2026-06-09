# _attributes_array_t::Copy(ulong,tagHELPER_ATTRIBUTE *)

- ea: `0x18000bb08`
- end: `0x18000beac`
- name: `?Copy@_attributes_array_t@@QEAAJKPEAUtagHELPER_ATTRIBUTE@@@Z`
- size: `932`
- prototype: `__int64 __fastcall(_attributes_array_t *__hidden this, unsigned int, struct tagHELPER_ATTRIBUTE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180005910`

## callees

- `0x180002596`
- `0x180005050`
- `0x18000b8ac`
- `0x18000bb08`
- `0x18000c244`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bc0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bc27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bc3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bc73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bc8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bcde`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bcf7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bdb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bdec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000be05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000be1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000be58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000be62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bc0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bc27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bc3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bc73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bc8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bcde`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bcf7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bdb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bdec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000be05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000be1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000be58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000be62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bb62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bd1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bb62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bd1d`

## pseudocode

```c
__int64 __fastcall _attributes_array_t::Copy(
        _attributes_array_t *this,
        unsigned int a2,
        struct tagHELPER_ATTRIBUTE *a3)
{
  __int64 v3; // rdi
  struct tagHELPER_ATTRIBUTE *v4; // rsi
  __int64 v7; // rbx
  _BYTE *v8; // rax
  __int64 v10; // r13
  __int64 v11; // rbx
  void *v12; // rcx
  const unsigned __int16 *v13; // rsi
  __int64 v14; // rbx
  int v15; // r14d
  LPVOID *v16; // rdi
  _BYTE *v17; // rax
  __int64 v18; // rcx
  int v19; // esi
  void *v20; // rax
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int64 v29; // rax
  unsigned __int16 *pv; // [rsp+20h] [rbp-79h]
  SIZE_T v31; // [rsp+28h] [rbp-71h]
  unsigned __int16 *v32[2]; // [rsp+30h] [rbp-69h] BYREF
  SIZE_T cb[2]; // [rsp+40h] [rbp-59h]
  __int128 v34; // [rsp+50h] [rbp-49h]
  __int128 v35; // [rsp+60h] [rbp-39h]
  __int128 v36; // [rsp+70h] [rbp-29h]
  __int128 v37; // [rsp+80h] [rbp-19h]
  __int128 v38; // [rsp+90h] [rbp-9h]
  __int128 v39; // [rsp+A0h] [rbp+7h]
  __int128 v40; // [rsp+B0h] [rbp+17h]
  int v41; // [rsp+108h] [rbp+6Fh]
  void *Src; // [rsp+118h] [rbp+7Fh]

  v3 = a2;
  v4 = a3;
  if ( a2 && a3 )
  {
    if ( a2 > 0x1C71C71 )
      return (unsigned int)-2147024362;
    _attributes_array_t::FreeAll(this);
    v7 = 144 * v3;
    v8 = CoTaskMemAlloc(144 * v3);
    *((_QWORD *)this + 1) = v8;
    if ( !v8 )
      return (unsigned int)-2147024882;
    for ( ; v7; --v7 )
      *v8++ = 0;
    v10 = 0;
    *(_DWORD *)this = v3;
    if ( !(_DWORD)v3 )
      return 0;
    while ( 1 )
    {
      v11 = *((_QWORD *)this + 1);
      v32[0] = 0;
      LODWORD(v32[1]) = 0;
      _attribute_t::Copy(v32, &v4[v10]);
      v12 = (void *)cb[1];
      v13 = (const unsigned __int16 *)cb[0];
      v14 = 144 * v10 + v11;
      v15 = (int)v32[1];
      Src = (void *)cb[1];
      v31 = cb[0];
      v41 = (int)v32[1];
      pv = v32[0];
      if ( (unsigned __int16 **)v14 == v32 )
        goto LABEL_49;
      if ( *(_DWORD *)(v14 + 8) == 10 )
      {
        CoTaskMemFree(*(LPVOID *)(v14 + 16));
        *(_QWORD *)(v14 + 16) = 0;
      }
      else if ( *(_DWORD *)(v14 + 8) == 14 )
      {
        CoTaskMemFree(*(LPVOID *)(v14 + 24));
        *(_QWORD *)(v14 + 24) = 0;
        *(_DWORD *)(v14 + 16) = 0;
      }
      CoTaskMemFree(*(LPVOID *)v14);
      v16 = (LPVOID *)(v14 + 16);
      *(_QWORD *)v14 = 0;
      v17 = (_BYTE *)(v14 + 16);
      v18 = 128;
      do
      {
        *v17++ = 0;
        --v18;
      }
      while ( v18 );
      if ( v15 == 10 )
      {
        if ( *(_DWORD *)(v14 + 8) == 10 )
        {
          CoTaskMemFree(*v16);
          *v16 = 0;
        }
        else if ( *(_DWORD *)(v14 + 8) == 14 )
        {
          CoTaskMemFree(*(LPVOID *)(v14 + 24));
          *(_QWORD *)(v14 + 24) = 0;
          *(_DWORD *)v16 = 0;
        }
        if ( v13 )
        {
          v19 = StringCchCopyWithAlloc((unsigned __int16 **)(v14 + 16), 0xFFFFu, v13);
          if ( v19 < 0 )
            goto LABEL_35;
          *(_DWORD *)(v14 + 8) = 10;
        }
      }
      else if ( v15 == 14 )
      {
        if ( *(_DWORD *)(v14 + 8) == 10 )
        {
          CoTaskMemFree(*v16);
          *v16 = 0;
        }
        else if ( *(_DWORD *)(v14 + 8) == 14 )
        {
          CoTaskMemFree(*(LPVOID *)(v14 + 24));
          *(_QWORD *)(v14 + 24) = 0;
          *(_DWORD *)v16 = 0;
        }
        if ( v14 == -16 || (unsigned int)v13 >= 0xFFFF )
        {
          v19 = -2147024809;
          goto LABEL_35;
        }
        v20 = CoTaskMemAlloc((unsigned int)v13);
        *(_QWORD *)(v14 + 24) = v20;
        if ( !v20 )
        {
          v15 = v41;
          v19 = -2147024882;
LABEL_35:
          *(_DWORD *)(v14 + 8) = 0;
          goto LABEL_41;
        }
        memcpy_0(v20, Src, (unsigned int)v13);
        v15 = v41;
        *(_DWORD *)v16 = (_DWORD)v13;
        *(_DWORD *)(v14 + 8) = 14;
      }
      else
      {
        v21 = *(_OWORD *)cb;
        *(_OWORD *)v14 = *(_OWORD *)v32;
        v22 = v34;
        *(_OWORD *)(v14 + 16) = v21;
        v23 = v35;
        *(_OWORD *)(v14 + 32) = v22;
        v24 = v36;
        *(_OWORD *)(v14 + 48) = v23;
        v25 = v37;
        *(_OWORD *)(v14 + 64) = v24;
        v26 = v38;
        *(_OWORD *)(v14 + 80) = v25;
        v27 = v39;
        *(_OWORD *)(v14 + 96) = v26;
        v28 = v40;
        *(_OWORD *)(v14 + 112) = v27;
        *(_OWORD *)(v14 + 128) = v28;
      }
      *(_QWORD *)v14 = 0;
      CoTaskMemFree(0);
      *(_QWORD *)v14 = 0;
      if ( !pv || (v19 = StringCchCopyWithAlloc((unsigned __int16 **)v14, 0xFFFFu, pv), v19 >= 0) )
      {
        v12 = Src;
LABEL_49:
        v19 = 0;
        goto LABEL_50;
      }
LABEL_41:
      if ( *(_DWORD *)(v14 + 8) == 10 )
      {
        CoTaskMemFree(*v16);
        *v16 = 0;
      }
      else if ( *(_DWORD *)(v14 + 8) == 14 )
      {
        CoTaskMemFree(*(LPVOID *)(v14 + 24));
        *(_QWORD *)(v14 + 24) = 0;
        *(_DWORD *)v16 = 0;
      }
      CoTaskMemFree(*(LPVOID *)v14);
      v29 = 128;
      *(_QWORD *)v14 = 0;
      do
      {
        *(_BYTE *)v16 = 0;
        v16 = (LPVOID *)((char *)v16 + 1);
        --v29;
      }
      while ( v29 );
      v12 = Src;
LABEL_50:
      if ( v15 == 10 )
      {
        v12 = (void *)v31;
      }
      else if ( v15 != 14 )
      {
        goto LABEL_54;
      }
      CoTaskMemFree(v12);
LABEL_54:
      CoTaskMemFree(pv);
      if ( v19 < 0 )
      {
        _attributes_array_t::FreeAll(this);
        return (unsigned int)v19;
      }
      v4 = a3;
      v10 = (unsigned int)(v10 + 1);
      if ( (unsigned int)v10 >= *(_DWORD *)this )
        return 0;
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000bb08  mov     [rsp-8+arg_0], rbx
0x18000bb0d  mov     [rsp-8+arg_10], r8
0x18000bb12  push    rbp
0x18000bb13  push    rsi
0x18000bb14  push    rdi
0x18000bb15  push    r12
0x18000bb17  push    r13
0x18000bb19  push    r14
0x18000bb1b  push    r15
0x18000bb1d  lea     rbp, [rsp-27h]
0x18000bb22  sub     rsp, 0C0h
0x18000bb29  mov     edi, edx
0x18000bb2b  mov     rsi, r8
0x18000bb2e  mov     r15, rcx
0x18000bb31  test    edx, edx
0x18000bb33  jz      loc_18000BE8C
0x18000bb39  test    r8, r8
0x18000bb3c  jz      loc_18000BE8C
0x18000bb42  cmp     edi, 1C71C71h
0x18000bb48  jbe     short loc_18000BB52
0x18000bb4a  mov     r12d, 80070216h
0x18000bb50  jmp     short loc_18000BB77
0x18000bb52  call    ?FreeAll@_attributes_array_t@@QEAAXXZ; _attributes_array_t::FreeAll(void)
0x18000bb57  lea     rbx, [rdi+rdi*8]
0x18000bb5b  shl     rbx, 4
0x18000bb5f  mov     rcx, rbx; cb
0x18000bb62  call    cs:__imp_CoTaskMemAlloc
0x18000bb68  mov     [r15+8], rax
0x18000bb6c  test    rax, rax
0x18000bb6f  jnz     short loc_18000BB7F
0x18000bb71  mov     r12d, 8007000Eh
0x18000bb77  mov     eax, r12d
0x18000bb7a  jmp     loc_18000BE91
0x18000bb7f  test    rbx, rbx
0x18000bb82  jz      short loc_18000BB90
0x18000bb84  mov     byte ptr [rax], 0
0x18000bb87  inc     rax
0x18000bb8a  sub     rbx, 1
0x18000bb8e  jnz     short loc_18000BB84
0x18000bb90  xor     r13d, r13d
0x18000bb93  mov     [r15], edi
0x18000bb96  test    edi, edi
0x18000bb98  jz      loc_18000BE7C
0x18000bb9e  mov     r12d, 8007000Eh
0x18000bba4  mov     rbx, [r15+8]
0x18000bba8  lea     rdi, ds:0[r13*8]
0x18000bbb0  add     rdi, r13
0x18000bbb3  mov     [rbp+57h+var_C0], 0
0x18000bbbb  shl     rdi, 4
0x18000bbbf  lea     rcx, [rbp+57h+var_C0]; this
0x18000bbc3  mov     dword ptr [rbp+57h+var_C0+8], 0
0x18000bbca  lea     rdx, [rdi+rsi]; struct tagHELPER_ATTRIBUTE *
0x18000bbce  call    ?Copy@_attribute_t@@QEAAJPEBUtagHELPER_ATTRIBUTE@@@Z; _attribute_t::Copy(tagHELPER_ATTRIBUTE const *)
0x18000bbd3  mov     rcx, [rbp+57h+cb+8]
0x18000bbd7  lea     rdx, [rbp+57h+var_C0]
0x18000bbdb  mov     rsi, [rbp+57h+cb]
0x18000bbdf  add     rbx, rdi
0x18000bbe2  mov     rax, [rbp+57h+var_C0]
0x18000bbe6  mov     r14d, dword ptr [rbp+57h+var_C0+8]
0x18000bbea  mov     [rbp+57h+Src], rcx
0x18000bbee  mov     [rbp+57h+var_C8], rsi
0x18000bbf2  mov     [rbp+57h+arg_8], r14d
0x18000bbf6  mov     [rbp+57h+pv], rax
0x18000bbfa  cmp     rbx, rdx
0x18000bbfd  jz      loc_18000BE44
0x18000bc03  cmp     dword ptr [rbx+8], 0Ah
0x18000bc07  jnz     short loc_18000BC1D
0x18000bc09  mov     rcx, [rbx+10h]; pv
0x18000bc0d  call    cs:__imp_CoTaskMemFree
0x18000bc13  mov     qword ptr [rbx+10h], 0
0x18000bc1b  jmp     short loc_18000BC3C
0x18000bc1d  cmp     dword ptr [rbx+8], 0Eh
0x18000bc21  jnz     short loc_18000BC3C
0x18000bc23  mov     rcx, [rbx+18h]; pv
0x18000bc27  call    cs:__imp_CoTaskMemFree
0x18000bc2d  mov     qword ptr [rbx+18h], 0
0x18000bc35  mov     dword ptr [rbx+10h], 0
0x18000bc3c  mov     rcx, [rbx]; pv
0x18000bc3f  call    cs:__imp_CoTaskMemFree
0x18000bc45  lea     rdi, [rbx+10h]
0x18000bc49  mov     qword ptr [rbx], 0
0x18000bc50  mov     rax, rdi
0x18000bc53  mov     ecx, 80h
0x18000bc58  mov     byte ptr [rax], 0
0x18000bc5b  inc     rax
0x18000bc5e  sub     rcx, 1
0x18000bc62  jnz     short loc_18000BC58
0x18000bc64  cmp     r14d, 0Ah
0x18000bc68  jnz     short loc_18000BCCB
0x18000bc6a  cmp     [rbx+8], r14d
0x18000bc6e  jnz     short loc_18000BC82
0x18000bc70  mov     rcx, [rdi]; pv
0x18000bc73  call    cs:__imp_CoTaskMemFree
0x18000bc79  mov     qword ptr [rdi], 0
0x18000bc80  jmp     short loc_18000BCA0
0x18000bc82  cmp     dword ptr [rbx+8], 0Eh
0x18000bc86  jnz     short loc_18000BCA0
0x18000bc88  mov     rcx, [rbx+18h]; pv
0x18000bc8c  call    cs:__imp_CoTaskMemFree
0x18000bc92  mov     qword ptr [rbx+18h], 0
0x18000bc9a  mov     dword ptr [rdi], 0
0x18000bca0  test    rsi, rsi
0x18000bca3  jz      loc_18000BDAE
0x18000bca9  mov     r8, rsi; unsigned __int16 *
0x18000bcac  mov     edx, 0FFFFh; unsigned __int64
0x18000bcb1  mov     rcx, rdi; unsigned __int16 **
0x18000bcb4  call    ?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z; StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)
0x18000bcb9  mov     esi, eax
0x18000bcbb  test    eax, eax
0x18000bcbd  js      short loc_18000BD33
0x18000bcbf  mov     dword ptr [rbx+8], 0Ah
0x18000bcc6  jmp     loc_18000BDAE
0x18000bccb  cmp     r14d, 0Eh
0x18000bccf  jnz     loc_18000BD64
0x18000bcd5  cmp     dword ptr [rbx+8], 0Ah
0x18000bcd9  jnz     short loc_18000BCED
0x18000bcdb  mov     rcx, [rdi]; pv
0x18000bcde  call    cs:__imp_CoTaskMemFree
0x18000bce4  mov     qword ptr [rdi], 0
0x18000bceb  jmp     short loc_18000BD0B
0x18000bced  cmp     dword ptr [rbx+8], 0Eh
0x18000bcf1  jnz     short loc_18000BD0B
0x18000bcf3  mov     rcx, [rbx+18h]; pv
0x18000bcf7  call    cs:__imp_CoTaskMemFree
0x18000bcfd  mov     qword ptr [rbx+18h], 0
0x18000bd05  mov     dword ptr [rdi], 0
0x18000bd0b  test    rdi, rdi
0x18000bd0e  jz      short loc_18000BD5D
0x18000bd10  cmp     esi, 0FFFFh
0x18000bd16  jnb     short loc_18000BD5D
0x18000bd18  mov     ecx, esi; cb
0x18000bd1a  mov     r14d, esi
0x18000bd1d  call    cs:__imp_CoTaskMemAlloc
0x18000bd23  mov     [rdi+8], rax
0x18000bd27  test    rax, rax
0x18000bd2a  jnz     short loc_18000BD3F
0x18000bd2c  mov     r14d, [rbp+57h+arg_8]
0x18000bd30  mov     esi, r12d
0x18000bd33  mov     dword ptr [rbx+8], 0
0x18000bd3a  jmp     loc_18000BDE3
0x18000bd3f  mov     rdx, [rbp+57h+Src]; Src
0x18000bd43  mov     r8, r14; Size
0x18000bd46  mov     rcx, rax; void *
0x18000bd49  call    memcpy_0
0x18000bd4e  mov     r14d, [rbp+57h+arg_8]
0x18000bd52  mov     [rdi], esi
0x18000bd54  mov     dword ptr [rbx+8], 0Eh
0x18000bd5b  jmp     short loc_18000BDAE
0x18000bd5d  mov     esi, 80070057h
0x18000bd62  jmp     short loc_18000BD33
0x18000bd64  movups  xmm0, xmmword ptr [rbp+57h+var_C0]
0x18000bd68  movups  xmm1, xmmword ptr [rbp+57h+cb]
0x18000bd6c  movups  xmmword ptr [rbx], xmm0
0x18000bd6f  movups  xmm0, [rbp+57h+var_A0]
0x18000bd73  movups  xmmword ptr [rbx+10h], xmm1
0x18000bd77  movups  xmm1, [rbp+57h+var_90]
0x18000bd7b  movups  xmmword ptr [rbx+20h], xmm0
0x18000bd7f  movups  xmm0, [rbp+57h+var_80]
0x18000bd83  movups  xmmword ptr [rbx+30h], xmm1
0x18000bd87  movups  xmm1, [rbp+57h+var_70]
0x18000bd8b  movups  xmmword ptr [rbx+40h], xmm0
0x18000bd8f  movups  xmm0, [rbp+57h+var_60]
0x18000bd93  movups  xmmword ptr [rbx+50h], xmm1
0x18000bd97  movups  xmm1, [rbp+57h+var_50]
0x18000bd9b  movups  xmmword ptr [rbx+60h], xmm0
0x18000bd9f  movups  xmm0, [rbp+57h+var_40]
0x18000bda3  movups  xmmword ptr [rbx+70h], xmm1
0x18000bda7  movups  xmmword ptr [rbx+80h], xmm0
0x18000bdae  xor     ecx, ecx; pv
0x18000bdb0  mov     qword ptr [rbx], 0
0x18000bdb7  call    cs:__imp_CoTaskMemFree
0x18000bdbd  mov     rax, [rbp+57h+pv]
0x18000bdc1  mov     qword ptr [rbx], 0
0x18000bdc8  test    rax, rax
0x18000bdcb  jz      short loc_18000BE40
0x18000bdcd  mov     r8, rax; unsigned __int16 *
0x18000bdd0  mov     edx, 0FFFFh; unsigned __int64
0x18000bdd5  mov     rcx, rbx; unsigned __int16 **
0x18000bdd8  call    ?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z; StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)
0x18000bddd  mov     esi, eax
0x18000bddf  test    eax, eax
0x18000bde1  jns     short loc_18000BE40
0x18000bde3  cmp     dword ptr [rbx+8], 0Ah
0x18000bde7  jnz     short loc_18000BDFB
0x18000bde9  mov     rcx, [rdi]; pv
0x18000bdec  call    cs:__imp_CoTaskMemFree
0x18000bdf2  mov     qword ptr [rdi], 0
0x18000bdf9  jmp     short loc_18000BE19
0x18000bdfb  cmp     dword ptr [rbx+8], 0Eh
0x18000bdff  jnz     short loc_18000BE19
0x18000be01  mov     rcx, [rbx+18h]; pv
0x18000be05  call    cs:__imp_CoTaskMemFree
0x18000be0b  mov     qword ptr [rbx+18h], 0
0x18000be13  mov     dword ptr [rdi], 0
0x18000be19  mov     rcx, [rbx]; pv
0x18000be1c  call    cs:__imp_CoTaskMemFree
0x18000be22  mov     eax, 80h
0x18000be27  mov     qword ptr [rbx], 0
0x18000be2e  mov     byte ptr [rdi], 0
0x18000be31  inc     rdi
0x18000be34  sub     rax, 1
0x18000be38  jnz     short loc_18000BE2E
0x18000be3a  mov     rcx, [rbp+57h+Src]
0x18000be3e  jmp     short loc_18000BE46
0x18000be40  mov     rcx, [rbp+57h+Src]; pv
0x18000be44  xor     esi, esi
0x18000be46  cmp     r14d, 0Ah
0x18000be4a  jnz     short loc_18000BE52
0x18000be4c  mov     rcx, [rbp+57h+var_C8]
0x18000be50  jmp     short loc_18000BE58
0x18000be52  cmp     r14d, 0Eh
0x18000be56  jnz     short loc_18000BE5E
0x18000be58  call    cs:__imp_CoTaskMemFree
0x18000be5e  mov     rcx, [rbp+57h+pv]; pv
0x18000be62  call    cs:__imp_CoTaskMemFree
0x18000be68  test    esi, esi
0x18000be6a  js      short loc_18000BE80
0x18000be6c  mov     rsi, [rbp+57h+arg_10]
0x18000be70  inc     r13d
0x18000be73  cmp     r13d, [r15]
0x18000be76  jb      loc_18000BBA4
0x18000be7c  xor     eax, eax
0x18000be7e  jmp     short loc_18000BE91
0x18000be80  mov     rcx, r15; this
0x18000be83  call    ?FreeAll@_attributes_array_t@@QEAAXXZ; _attributes_array_t::FreeAll(void)
0x18000be88  mov     eax, esi
0x18000be8a  jmp     short loc_18000BE91
0x18000be8c  mov     eax, 80070057h
0x18000be91  mov     rbx, [rsp+0F0h+arg_0]
0x18000be99  add     rsp, 0C0h
0x18000bea0  pop     r15
0x18000bea2  pop     r14
0x18000bea4  pop     r13
0x18000bea6  pop     r12
0x18000bea8  pop     rdi
0x18000bea9  pop     rsi
0x18000beaa  pop     rbp
0x18000beab  retn
```
