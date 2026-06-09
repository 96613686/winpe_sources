# OBJECT_EXTENSION::AddVerbTypeInformation(ulong,ushort const * * const,ulong (* const)[2],ulong,ushort const * * const,ulong (* const)[3],ulong,ushort const * * const,ulong (* const)[2])

- ea: `0x18000fc84`
- end: `0x1800101f7`
- name: `?AddVerbTypeInformation@OBJECT_EXTENSION@@IEAAJKQEAPEBGQEAY01KK0QEAY02KK01@Z`
- size: `1395`
- prototype: `__int64 __fastcall(OBJECT_EXTENSION *__hidden this, unsigned int, const unsigned __int16 **const, unsigned int (*const)[2], unsigned int, const unsigned __int16 **const, unsigned int (*const)[3], unsigned int, const unsigned __int16 **const, unsigned int (*const)[2])`
- caller_count: `11`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180011ea0`
- `0x180014f50`
- `0x180016c30`
- `0x180018400`
- `0x18001b0b0`
- `0x18001eb40`
- `0x18001fa00`
- `0x1800227e0`
- `0x180024e70`
- `0x180028bd0`
- `0x18002c900`

## callees

- `0x180001044`
- `0x180001fb0`
- `0x180002e90`
- `0x180005d74`
- `0x18000fc84`
- `0x1800131d8`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## pseudocode

```c
__int64 __fastcall OBJECT_EXTENSION::AddVerbTypeInformation(
        OBJECT_EXTENSION *this,
        unsigned int a2,
        const unsigned __int16 **const a3,
        unsigned int (*const a4)[2],
        unsigned int a5,
        const unsigned __int16 **const a6,
        unsigned int (*const a7)[3],
        unsigned int a8,
        const unsigned __int16 **const a9,
        unsigned int (*const a10)[2])
{
  const unsigned __int16 **v10; // r12
  unsigned int v11; // ebx
  unsigned int *v12; // rsi
  int v13; // r14d
  __int64 v14; // r13
  _DWORD *v15; // rax
  _DWORD *v16; // rbx
  __int64 i; // rsi
  unsigned int *v18; // r14
  _DWORD *v19; // rax
  _DWORD *v20; // rdi
  unsigned int v21; // r12d
  unsigned int *v22; // r15
  __int64 j; // r12
  _DWORD *v24; // rax
  _DWORD *v25; // rsi
  va_list Arguments; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v28; // [rsp+28h] [rbp-D8h]
  unsigned int *v29; // [rsp+30h] [rbp-D0h]
  unsigned int *v30; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 **v31; // [rsp+40h] [rbp-C0h]
  const unsigned __int16 **v32; // [rsp+48h] [rbp-B8h]
  OBJECT_EXTENSION *v33; // [rsp+58h] [rbp-A8h]
  unsigned int *v34; // [rsp+60h] [rbp-A0h]
  const unsigned __int16 **v35; // [rsp+68h] [rbp-98h]
  _BYTE v36[32]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v37; // [rsp+90h] [rbp-70h]
  int v38; // [rsp+98h] [rbp-68h]
  __int16 v39; // [rsp+9Ch] [rbp-64h]
  int v40; // [rsp+A0h] [rbp-60h]
  _BYTE v41[32]; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 *v42; // [rsp+C8h] [rbp-38h]
  int v43; // [rsp+D0h] [rbp-30h]
  __int16 v44; // [rsp+D4h] [rbp-2Ch]
  int v45; // [rsp+D8h] [rbp-28h]
  __int16 v46; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v47[1022]; // [rsp+E2h] [rbp-1Eh] BYREF
  __int16 v48; // [rsp+4E0h] [rbp+3E0h] BYREF
  _BYTE v49[1022]; // [rsp+4E2h] [rbp+3E2h] BYREF

  v10 = a3;
  v11 = a2;
  v31 = a6;
  v12 = (unsigned int *)a4;
  v13 = 0;
  v30 = (unsigned int *)a7;
  v35 = a3;
  v28 = a2;
  v33 = this;
  v29 = (unsigned int *)a10;
  v32 = a9;
  v34 = (unsigned int *)a4;
  memset_0(v47, 0, sizeof(v47));
  v39 = 256;
  v37 = (unsigned __int16 *)&v46;
  v38 = 1024;
  v46 = 0;
  v40 = 0;
  memset_0(v49, 0, sizeof(v49));
  v43 = 1024;
  v42 = (unsigned __int16 *)&v48;
  v48 = 0;
  v14 = 0;
  Arguments = 0;
  v44 = 256;
  v45 = 0;
  while ( (unsigned int)v14 < v11 )
  {
    v15 = operator new(0xE0u);
    v16 = v15;
    if ( !v15 )
    {
      v13 = -2147024888;
      break;
    }
    v15[4] = 1;
    *(_QWORD *)v15 = &VERB_TYPE::`vftable'{for `ICommandVerbType'};
    *((_QWORD *)v15 + 1) = &VERB_PARAMETER::`vftable'{for `IArrayListEntry'};
    v15[16] = 32;
    *((_QWORD *)v15 + 3) = 0;
    *((_QWORD *)v15 + 7) = v15 + 6;
    *((_WORD *)v15 + 34) = 256;
    v15[18] = 0;
    *((_QWORD *)v15 + 10) = 0;
    *((_QWORD *)v15 + 14) = v15 + 20;
    v15[30] = 32;
    *((_WORD *)v15 + 62) = 256;
    v15[32] = 0;
    *((_QWORD *)v15 + 17) = 0;
    *((_QWORD *)v15 + 21) = v15 + 34;
    v15[44] = 32;
    *((_WORD *)v15 + 90) = 256;
    v15[46] = 0;
    *((_QWORD *)v15 + 24) = 0;
    *((_QWORD *)v15 + 25) = 0;
    *((_QWORD *)v15 + 26) = 0;
    *((_QWORD *)v15 + 27) = 0;
    v13 = FormatCommandMessage(v12[2 * v14], &Arguments, (struct STRU *)v36);
    if ( v13 < 0
      || (v13 = FormatCommandMessage(v12[2 * v14 + 1], &Arguments, (struct STRU *)v41), v13 < 0)
      || (v13 = STRU::Copy((STRU *)(v16 + 6), v10[v14]), v13 < 0)
      || (v13 = STRU::Copy((STRU *)(v16 + 20), v37), v13 < 0)
      || (v13 = STRU::Copy((STRU *)(v16 + 34), v42), v13 < 0) )
    {
      v20 = 0;
LABEL_33:
      v25 = 0;
LABEL_34:
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v16 + 16LL))(v16);
      if ( v20 )
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v20 + 16LL))(v20);
      if ( v25 )
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v25 + 16LL))(v25);
      break;
    }
    for ( i = 0; (unsigned int)i < a5; i = (unsigned int)(i + 1) )
    {
      v18 = v30;
      if ( v30[3 * i] == (_DWORD)v14 )
      {
        v19 = operator new(0x90u);
        v20 = v19;
        if ( !v19 )
        {
          v25 = 0;
          v13 = -2147024888;
          v20 = 0;
          goto LABEL_34;
        }
        v19[4] = 1;
        *(_QWORD *)v19 = &VERB_PARAMETER::`vftable'{for `ICommandVerbParameter'};
        *((_QWORD *)v19 + 1) = &VERB_PARAMETER::`vftable'{for `IArrayListEntry'};
        *((_QWORD *)v19 + 3) = 0;
        *((_QWORD *)v19 + 7) = v19 + 6;
        v19[16] = 32;
        *((_WORD *)v19 + 34) = 256;
        v19[18] = 0;
        v19[30] = 32;
        *((_QWORD *)v19 + 10) = 0;
        *((_QWORD *)v19 + 14) = v19 + 20;
        *((_WORD *)v19 + 62) = 256;
        v19[32] = 0;
        v19[34] = 0;
        v13 = FormatCommandMessage(v18[3 * i + 1], &Arguments, (struct STRU *)v36);
        if ( v13 < 0 )
          goto LABEL_33;
        v21 = v30[3 * i + 2];
        v13 = STRU::Copy((STRU *)(v20 + 6), v31[i]);
        if ( v13 < 0 )
          goto LABEL_33;
        v13 = STRU::Copy((STRU *)(v20 + 20), v37);
        if ( v13 < 0 )
          goto LABEL_33;
        v20[34] = v21;
        v13 = ARRAY_LIST::AddEntry(
                (ARRAY_LIST *)(v16 + 48),
                (struct IArrayListEntry *)((unsigned __int64)(v20 + 2)
                                         & ((unsigned __int128)-(__int128)(unsigned __int64)v20 >> 64)),
                0xFFFFFFFF);
        if ( v13 < 0 )
          goto LABEL_33;
      }
    }
    v22 = v29;
    for ( j = 0; (unsigned int)j < a8; j = (unsigned int)(j + 1) )
    {
      if ( v22[2 * j] == (_DWORD)v14 )
      {
        v24 = operator new(0x88u);
        v25 = v24;
        if ( !v24 )
        {
          v13 = -2147024888;
          v20 = 0;
          v25 = 0;
          goto LABEL_34;
        }
        v24[4] = 1;
        *(_QWORD *)v24 = &VERB_EXAMPLE::`vftable'{for `ICommandVerbExample'};
        *((_QWORD *)v24 + 1) = &VERB_PARAMETER::`vftable'{for `IArrayListEntry'};
        *((_QWORD *)v24 + 3) = 0;
        *((_QWORD *)v24 + 7) = v24 + 6;
        v24[16] = 32;
        *((_WORD *)v24 + 34) = 256;
        v24[18] = 0;
        *((_QWORD *)v24 + 10) = 0;
        v24[30] = 32;
        *((_QWORD *)v24 + 14) = v24 + 20;
        *((_WORD *)v24 + 62) = 256;
        v24[32] = 0;
        v20 = 0;
        v13 = FormatCommandMessage(v29[2 * j + 1], &Arguments, (struct STRU *)v36);
        if ( v13 < 0 )
          goto LABEL_34;
        v13 = STRU::Copy((STRU *)(v25 + 6), v32[j]);
        if ( v13 < 0 )
          goto LABEL_34;
        v13 = STRU::Copy((STRU *)(v25 + 20), v37);
        if ( v13 < 0 )
          goto LABEL_34;
        v13 = ARRAY_LIST::AddEntry(
                (ARRAY_LIST *)(v16 + 52),
                (struct IArrayListEntry *)((unsigned __int64)(v25 + 2)
                                         & ((unsigned __int128)-(__int128)(unsigned __int64)v25 >> 64)),
                0xFFFFFFFF);
        if ( v13 < 0 )
          goto LABEL_34;
        v22 = v29;
      }
    }
    v13 = ARRAY_LIST::AddEntry(
            (OBJECT_EXTENSION *)((char *)v33 + 24),
            (struct IArrayListEntry *)((unsigned __int64)(v16 + 2)
                                     & ((unsigned __int128)-(__int128)(unsigned __int64)v16 >> 64)),
            0xFFFFFFFF);
    v20 = 0;
    v25 = 0;
    if ( v13 < 0 )
      goto LABEL_34;
    v12 = v34;
    v14 = (unsigned int)(v14 + 1);
    v11 = v28;
    v10 = v35;
  }
  BUFFER::~BUFFER((BUFFER *)v41);
  BUFFER::~BUFFER((BUFFER *)v36);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18000fc84  mov     [rsp-8+arg_8], rbx
0x18000fc89  push    rbp
0x18000fc8a  push    rsi
0x18000fc8b  push    rdi
0x18000fc8c  push    r12
0x18000fc8e  push    r13
0x18000fc90  push    r14
0x18000fc92  push    r15
0x18000fc94  lea     rbp, [rsp-7F0h]
0x18000fc9c  sub     rsp, 8F0h
0x18000fca3  mov     rax, cs:__security_cookie
0x18000fcaa  xor     rax, rsp
0x18000fcad  mov     [rbp+820h+var_40], rax
0x18000fcb4  mov     rax, [rbp+820h+arg_28]
0x18000fcbb  mov     r12, r8
0x18000fcbe  mov     r15, [rbp+820h+arg_48]
0x18000fcc5  mov     ebx, edx
0x18000fcc7  mov     [rsp+920h+var_8E0], rax
0x18000fccc  mov     rsi, r9
0x18000fccf  mov     rax, [rbp+820h+arg_30]
0x18000fcd6  xor     r14d, r14d
0x18000fcd9  mov     [rsp+920h+var_8E8], rax
0x18000fcde  mov     rax, [rbp+820h+arg_40]
0x18000fce5  mov     [rsp+920h+var_8B8], r8
0x18000fcea  mov     [rsp+920h+var_8F8], edx
0x18000fcee  xor     edx, edx; Val
0x18000fcf0  mov     [rsp+920h+var_8C8], rcx
0x18000fcf5  lea     rcx, [rbp+820h+var_83E]; void *
0x18000fcf9  mov     [rsp+920h+var_8F0], r15
0x18000fcfe  mov     r15d, 3FEh
0x18000fd04  mov     r8d, r15d; Size
0x18000fd07  mov     [rsp+920h+var_8D8], rax
0x18000fd0c  mov     [rsp+920h+var_8C0], r9
0x18000fd11  call    memset_0
0x18000fd16  lea     rax, [rbp+820h+var_840]
0x18000fd1a  mov     [rbp+820h+var_884], 100h
0x18000fd20  mov     [rbp+820h+var_890], rax
0x18000fd24  lea     edi, [r15+2]
0x18000fd28  xor     eax, eax
0x18000fd2a  mov     [rbp+820h+var_888], edi
0x18000fd2d  mov     r8d, r15d; Size
0x18000fd30  mov     [rbp+820h+var_840], ax
0x18000fd34  xor     edx, edx; Val
0x18000fd36  mov     [rbp+820h+var_880], r14d
0x18000fd3a  lea     rcx, [rbp+820h+var_43E]; void *
0x18000fd41  call    memset_0
0x18000fd46  lea     rax, [rbp+820h+var_440]
0x18000fd4d  mov     [rbp+820h+var_850], edi
0x18000fd50  mov     [rbp+820h+var_858], rax
0x18000fd54  xor     eax, eax
0x18000fd56  mov     [rbp+820h+var_440], ax
0x18000fd5d  xor     r13d, r13d
0x18000fd60  mov     [rsp+920h+Arguments], rax
0x18000fd65  mov     [rbp+820h+var_84C], 100h
0x18000fd6b  mov     [rbp+820h+var_848], r14d
0x18000fd6f  cmp     r13d, ebx
0x18000fd72  jnb     loc_1800101B7
0x18000fd78  mov     ecx, 0E0h; Size
0x18000fd7d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000fd82  mov     rbx, rax
0x18000fd85  test    rax, rax
0x18000fd88  jz      loc_1800101B1
0x18000fd8e  mov     dword ptr [rbx+10h], 1
0x18000fd95  lea     rax, ??_7VERB_TYPE@@6BICommandVerbType@@@; const VERB_TYPE::`vftable'{for `ICommandVerbType'}
0x18000fd9c  mov     [rbx], rax
0x18000fd9f  lea     r8, [rsp+920h+var_8B0]; this
0x18000fda4  lea     rax, ??_7VERB_PARAMETER@@6BIArrayListEntry@@@; const VERB_PARAMETER::`vftable'{for `IArrayListEntry'}
0x18000fdab  mov     [rbx+8], rax
0x18000fdaf  lea     rdx, [rsp+920h+Arguments]; Arguments
0x18000fdb4  mov     dword ptr [rbx+40h], 20h ; ' '
0x18000fdbb  lea     rax, [rbx+18h]
0x18000fdbf  mov     qword ptr [rax], 0
0x18000fdc6  mov     [rbx+38h], rax
0x18000fdca  lea     rax, [rbx+50h]
0x18000fdce  mov     word ptr [rbx+44h], 100h
0x18000fdd4  mov     dword ptr [rbx+48h], 0
0x18000fddb  mov     qword ptr [rax], 0
0x18000fde2  mov     [rbx+70h], rax
0x18000fde6  lea     rax, [rbx+88h]
0x18000fded  mov     dword ptr [rbx+78h], 20h ; ' '
0x18000fdf4  mov     word ptr [rbx+7Ch], 100h
0x18000fdfa  mov     dword ptr [rbx+80h], 0
0x18000fe04  mov     qword ptr [rax], 0
0x18000fe0b  mov     [rbx+0A8h], rax
0x18000fe12  mov     dword ptr [rbx+0B0h], 20h ; ' '
0x18000fe1c  mov     word ptr [rbx+0B4h], 100h
0x18000fe25  mov     dword ptr [rbx+0B8h], 0
0x18000fe2f  mov     qword ptr [rbx+0C0h], 0
0x18000fe3a  mov     qword ptr [rbx+0C8h], 0
0x18000fe45  mov     qword ptr [rbx+0D0h], 0
0x18000fe50  mov     qword ptr [rbx+0D8h], 0
0x18000fe5b  mov     ecx, [rsi+r13*8]; dwMessageId
0x18000fe5f  call    ?FormatCommandMessage@@YAJKQEAPEBGPEAVSTRU@@@Z; FormatCommandMessage(ulong,ushort const * * const,STRU *)
0x18000fe64  mov     r14d, eax
0x18000fe67  test    eax, eax
0x18000fe69  js      loc_180010174
0x18000fe6f  mov     ecx, [rsi+r13*8+4]; dwMessageId
0x18000fe74  lea     r8, [rbp+820h+var_878]; this
0x18000fe78  lea     rdx, [rsp+920h+Arguments]; Arguments
0x18000fe7d  call    ?FormatCommandMessage@@YAJKQEAPEBGPEAVSTRU@@@Z; FormatCommandMessage(ulong,ushort const * * const,STRU *)
0x18000fe82  mov     r14d, eax
0x18000fe85  test    eax, eax
0x18000fe87  js      loc_180010174
0x18000fe8d  mov     rdx, [r12+r13*8]; unsigned __int16 *
0x18000fe91  lea     rcx, [rbx+18h]; this
0x18000fe95  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000fe9a  mov     r14d, eax
0x18000fe9d  test    eax, eax
0x18000fe9f  js      loc_180010174
0x18000fea5  mov     rdx, [rbp+820h+var_890]; unsigned __int16 *
0x18000fea9  lea     rcx, [rbx+50h]; this
0x18000fead  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000feb2  mov     r14d, eax
0x18000feb5  test    eax, eax
0x18000feb7  js      loc_180010174
0x18000febd  mov     rdx, [rbp+820h+var_858]; unsigned __int16 *
0x18000fec1  lea     rcx, [rbx+88h]; this
0x18000fec8  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000fecd  mov     r14d, eax
0x18000fed0  test    eax, eax
0x18000fed2  js      loc_180010174
0x18000fed8  xor     esi, esi
0x18000feda  cmp     esi, [rbp+820h+arg_20]
0x18000fee0  jnb     loc_18000FFFE
0x18000fee6  mov     r14, [rsp+920h+var_8E8]
0x18000feeb  lea     r12, [rsi+rsi*2]
0x18000feef  cmp     [r14+r12*4], r13d
0x18000fef3  jnz     loc_18000FFF7
0x18000fef9  mov     ecx, 90h; Size
0x18000fefe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ff03  xor     ecx, ecx
0x18000ff05  mov     rdi, rax
0x18000ff08  test    rax, rax
0x18000ff0b  jz      loc_18001015A
0x18000ff11  mov     dword ptr [rdi+10h], 1
0x18000ff18  lea     edx, [rcx+20h]
0x18000ff1b  lea     rax, ??_7VERB_PARAMETER@@6BICommandVerbParameter@@@; const VERB_PARAMETER::`vftable'{for `ICommandVerbParameter'}
0x18000ff22  mov     [rdi], rax
0x18000ff25  lea     r8, [rsp+920h+var_8B0]; this
0x18000ff2a  lea     rax, ??_7VERB_PARAMETER@@6BIArrayListEntry@@@; const VERB_PARAMETER::`vftable'{for `IArrayListEntry'}
0x18000ff31  mov     [rdi+8], rax
0x18000ff35  lea     rax, [rdi+18h]
0x18000ff39  mov     [rax], rcx
0x18000ff3c  mov     [rdi+38h], rax
0x18000ff40  lea     rax, [rdi+50h]
0x18000ff44  mov     [rdi+40h], edx
0x18000ff47  mov     word ptr [rdi+44h], 100h
0x18000ff4d  mov     [rdi+48h], ecx
0x18000ff50  mov     [rdi+78h], edx
0x18000ff53  lea     rdx, [rsp+920h+Arguments]; Arguments
0x18000ff58  mov     [rax], rcx
0x18000ff5b  mov     [rdi+70h], rax
0x18000ff5f  mov     word ptr [rdi+7Ch], 100h
0x18000ff65  mov     [rdi+80h], ecx
0x18000ff6b  mov     [rdi+88h], ecx
0x18000ff71  mov     ecx, [r14+r12*4+4]; dwMessageId
0x18000ff76  call    ?FormatCommandMessage@@YAJKQEAPEBGPEAVSTRU@@@Z; FormatCommandMessage(ulong,ushort const * * const,STRU *)
0x18000ff7b  mov     r14d, eax
0x18000ff7e  test    eax, eax
0x18000ff80  js      loc_180010176
0x18000ff86  mov     rax, [rsp+920h+var_8E8]
0x18000ff8b  lea     rcx, [rdi+18h]; this
0x18000ff8f  mov     r12d, [rax+r12*4+8]
0x18000ff94  mov     rax, [rsp+920h+var_8E0]
0x18000ff99  mov     rdx, [rax+rsi*8]; unsigned __int16 *
0x18000ff9d  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000ffa2  mov     r14d, eax
0x18000ffa5  test    eax, eax
0x18000ffa7  js      loc_180010176
0x18000ffad  mov     rdx, [rbp+820h+var_890]; unsigned __int16 *
0x18000ffb1  lea     rcx, [rdi+50h]; this
0x18000ffb5  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000ffba  mov     r14d, eax
0x18000ffbd  test    eax, eax
0x18000ffbf  js      loc_180010176
0x18000ffc5  lea     rcx, [rdi+8]
0x18000ffc9  mov     [rdi+88h], r12d
0x18000ffd0  mov     rax, rdi
0x18000ffd3  neg     rax
0x18000ffd6  sbb     rdx, rdx
0x18000ffd9  or      r8d, 0FFFFFFFFh; unsigned int
0x18000ffdd  and     rdx, rcx; struct IArrayListEntry *
0x18000ffe0  lea     rcx, [rbx+0C0h]; this
0x18000ffe7  call    ?AddEntry@ARRAY_LIST@@QEAAJPEAVIArrayListEntry@@K@Z; ARRAY_LIST::AddEntry(IArrayListEntry *,ulong)
0x18000ffec  mov     r14d, eax
0x18000ffef  test    eax, eax
0x18000fff1  js      loc_180010176
0x18000fff7  inc     esi
0x18000fff9  jmp     loc_18000FEDA
0x18000fffe  mov     r15, [rsp+920h+var_8F0]
0x180010003  xor     r12d, r12d
0x180010006  cmp     r12d, [rbp+820h+arg_38]
0x18001000d  jnb     loc_180010117
0x180010013  cmp     [r15+r12*8], r13d
0x180010017  jnz     loc_18001010F
0x18001001d  mov     ecx, 88h; Size
0x180010022  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010027  xor     ecx, ecx
0x180010029  mov     rsi, rax
0x18001002c  test    rax, rax
0x18001002f  jz      loc_180010166
0x180010035  mov     dword ptr [rsi+10h], 1
0x18001003c  lea     edx, [rcx+20h]
0x18001003f  lea     rax, ??_7VERB_EXAMPLE@@6BICommandVerbExample@@@; const VERB_EXAMPLE::`vftable'{for `ICommandVerbExample'}
0x180010046  mov     [rsi], rax
0x180010049  lea     r8, [rsp+920h+var_8B0]; this
0x18001004e  lea     rax, ??_7VERB_PARAMETER@@6BIArrayListEntry@@@; const VERB_PARAMETER::`vftable'{for `IArrayListEntry'}
0x180010055  mov     [rsi+8], rax
0x180010059  lea     rax, [rsi+18h]
0x18001005d  mov     [rax], rcx
0x180010060  mov     [rsi+38h], rax
0x180010064  lea     rax, [rsi+50h]
0x180010068  mov     [rsi+40h], edx
0x18001006b  mov     word ptr [rsi+44h], 100h
0x180010071  mov     [rsi+48h], ecx
0x180010074  mov     [rax], rcx
0x180010077  mov     [rsi+78h], edx
0x18001007a  lea     rdx, [rsp+920h+Arguments]; Arguments
0x18001007f  mov     [rsi+70h], rax
0x180010083  mov     word ptr [rsi+7Ch], 100h
0x180010089  mov     [rsi+80h], ecx
0x18001008f  mov     rcx, [rsp+920h+var_8F0]
0x180010094  mov     ecx, [rcx+r12*8+4]; dwMessageId
0x180010099  call    ?FormatCommandMessage@@YAJKQEAPEBGPEAVSTRU@@@Z; FormatCommandMessage(ulong,ushort const * * const,STRU *)
0x18001009e  xor     edi, edi
0x1800100a0  mov     r14d, eax
0x1800100a3  test    eax, eax
0x1800100a5  js      loc_180010178
0x1800100ab  mov     rax, [rsp+920h+var_8D8]
0x1800100b0  lea     rcx, [rsi+18h]; this
0x1800100b4  mov     rdx, [rax+r12*8]; unsigned __int16 *
0x1800100b8  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800100bd  mov     r14d, eax
0x1800100c0  test    eax, eax
0x1800100c2  js      loc_180010178
0x1800100c8  mov     rdx, [rbp+820h+var_890]; unsigned __int16 *
0x1800100cc  lea     rcx, [rsi+50h]; this
0x1800100d0  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800100d5  mov     r14d, eax
0x1800100d8  test    eax, eax
0x1800100da  js      loc_180010178
0x1800100e0  lea     rcx, [rsi+8]
0x1800100e4  mov     rax, rsi
0x1800100e7  neg     rax
0x1800100ea  mov     r15, rbx
0x1800100ed  sbb     rdx, rdx
0x1800100f0  or      r8d, 0FFFFFFFFh; unsigned int
0x1800100f4  and     rdx, rcx; struct IArrayListEntry *
0x1800100f7  lea     rcx, [rbx+0D0h]; this
0x1800100fe  call    ?AddEntry@ARRAY_LIST@@QEAAJPEAVIArrayListEntry@@K@Z; ARRAY_LIST::AddEntry(IArrayListEntry *,ulong)
0x180010103  mov     r14d, eax
0x180010106  test    eax, eax
0x180010108  js      short loc_180010178
0x18001010a  mov     r15, [rsp+920h+var_8F0]
0x18001010f  inc     r12d
0x180010112  jmp     loc_180010006
0x180010117  lea     rcx, [rbx+8]
0x18001011b  mov     rax, rbx
0x18001011e  neg     rax
0x180010121  sbb     rdx, rdx
0x180010124  or      r8d, 0FFFFFFFFh; unsigned int
0x180010128  and     rdx, rcx; struct IArrayListEntry *
0x18001012b  mov     rcx, [rsp+920h+var_8C8]
0x180010130  add     rcx, 18h; this
0x180010134  call    ?AddEntry@ARRAY_LIST@@QEAAJPEAVIArrayListEntry@@K@Z; ARRAY_LIST::AddEntry(IArrayListEntry *,ulong)
0x180010139  mov     r14d, eax
0x18001013c  xor     edi, edi
0x18001013e  xor     esi, esi
0x180010140  test    eax, eax
0x180010142  js      short loc_180010178
0x180010144  mov     rsi, [rsp+920h+var_8C0]
0x180010149  inc     r13d
0x18001014c  mov     ebx, [rsp+920h+var_8F8]
0x180010150  mov     r12, [rsp+920h+var_8B8]
0x180010155  jmp     loc_18000FD6F
0x18001015a  xor     esi, esi
0x18001015c  mov     r14d, 80070008h
0x180010162  xor     edi, edi
0x180010164  jmp     short loc_180010178
0x180010166  mov     r14d, 80070008h
0x18001016c  mov     rdi, rcx
0x18001016f  mov     rsi, rcx
0x180010172  jmp     short loc_180010178
0x180010174  xor     edi, edi
0x180010176  xor     esi, esi
0x180010178  mov     rax, [rbx]
0x18001017b  mov     rcx, rbx
0x18001017e  mov     rax, [rax+10h]
0x180010182  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010187  test    rdi, rdi
0x18001018a  jz      short loc_18001019B
0x18001018c  mov     rax, [rdi]
0x18001018f  mov     rcx, rdi
0x180010192  mov     rax, [rax+10h]
0x180010196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001019b  test    rsi, rsi
0x18001019e  jz      short loc_1800101B7
0x1800101a0  mov     rax, [rsi]
0x1800101a3  mov     rcx, rsi
0x1800101a6  mov     rax, [rax+10h]
  ... truncated ...
```
