# GenADTG::SaveColumnData(ushort,ADTGTOKENTYPEENUM,unsigned __int64 *,uchar *)

- ea: `0x1800076d4`
- end: `0x180007962`
- name: `?SaveColumnData@GenADTG@@AEAAXGW4ADTGTOKENTYPEENUM@@PEA_KPEAE@Z`
- size: `654`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800089a8`

## callees

- `0x180003abc`
- `0x1800041f8`
- `0x180006c94`
- `0x1800076d4`
- `0x180009490`
- `0x18001a6c8`
- `0x18002cd54`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x180007855`
- `KERNEL32!MultiByteToWideChar` at `0x180007855`

## pseudocode

```c
void __fastcall GenADTG::SaveColumnData(_QWORD *a1, unsigned __int16 a2, int a3, _QWORD *a4, __int64 a5)
{
  __int64 v5; // r10
  __int64 v7; // r14
  __int64 v9; // rbx
  unsigned int v10; // ecx
  int v11; // eax
  const CHAR *v12; // rdi
  unsigned __int16 v13; // dx
  __int64 v14; // r10
  int v15; // r11d
  int v16; // r8d
  unsigned int v17; // ecx
  int *p_cbMultiByte; // rdx
  unsigned int v19; // r8d
  __int16 v20; // cx
  WCHAR *lpWideCharStr; // rbx
  unsigned __int16 v22; // ax
  unsigned __int16 v23; // ax
  bool v24; // zf
  char v25; // [rsp+78h] [rbp+48h] BYREF
  int cbMultiByte; // [rsp+80h] [rbp+50h] BYREF

  cbMultiByte = a3;
  v5 = a1[7];
  v7 = a5;
  v9 = 88LL * a2;
  v25 = 0;
  cbMultiByte = 0;
  v10 = *(_DWORD *)(*(unsigned int *)(v9 + v5 + 24) + a5);
  if ( v10 <= 0xD )
  {
    v11 = 8209;
    if ( _bittest(&v11, v10) )
    {
      v12 = (const CHAR *)(a5 + *(unsigned int *)(v9 + v5 + 8));
      if ( (*(_WORD *)(v9 + v5 + 84) & 0x4000) != 0 )
        v12 = *(const CHAR **)v12;
      if ( (CMetaData::mdGetFlags((CMetaData *)(a1 + 16), *(_WORD *)(v9 + v5) - 1) & 0x2000) == 0
        && CMetaData::mdGetType((CMetaData *)(a1 + 16), v13) != 136 )
      {
        if ( (*(_BYTE *)(v9 + v14 + 56) & 2) != 0 )
        {
          v17 = *(_DWORD *)(v7 + *(_QWORD *)(v9 + v14 + 16));
          cbMultiByte = v17;
          if ( (*(_WORD *)(v9 + v14 + 84) & 0x4000) != 0 )
          {
            v19 = 4;
            p_cbMultiByte = &cbMultiByte;
          }
          else
          {
            if ( v17 > 0xFF )
            {
              p_cbMultiByte = &cbMultiByte;
              v15 = 4;
            }
            else
            {
              v25 = v17;
              p_cbMultiByte = (int *)&v25;
            }
            v19 = v15;
          }
          GenADTG::SaveToBuffer((GenADTG *)a1, (const unsigned __int8 *)p_cbMultiByte, v19);
          v16 = cbMultiByte;
        }
        else
        {
          v16 = *(_DWORD *)(v9 + v14 + 72);
          cbMultiByte = v16;
          if ( *(_WORD *)(v9 + v14 + 84) == 129 )
          {
            --v16;
LABEL_12:
            cbMultiByte = v16;
            goto LABEL_20;
          }
          if ( *(_WORD *)(v9 + v14 + 84) == 130 )
          {
            v16 -= 2;
            goto LABEL_12;
          }
        }
LABEL_20:
        v20 = *(_WORD *)(v9 + a1[7] + 84) & 0xBFFF;
        if ( g_fUnicode && v20 == 129 )
        {
          lpWideCharStr = GenADTG::GetUnicodeBuffer((GenADTG *)a1, v16);
          v22 = MultiByteToWideChar(0, 0, v12, cbMultiByte, lpWideCharStr, cbMultiByte);
          v12 = (const CHAR *)lpWideCharStr;
          v16 = 2 * v22;
          cbMultiByte = v16;
        }
        else if ( v20 == 12 )
        {
          if ( (*(_WORD *)v12 & 0xF000) != 0 )
            v23 = -1;
          else
            v23 = *(_WORD *)v12;
          if ( v23 > 0xBu )
          {
            if ( v23 == 14 || v23 == 16 || v23 == 17 || v23 == 18 || v23 == 19 || v23 == 20 || v23 == 21 || v23 == 22 )
              goto LABEL_23;
            v24 = v23 == 23;
          }
          else
          {
            if ( v23 == 11 || !v23 || v23 == 1 || v23 == 2 || v23 == 3 || v23 == 4 || v23 == 5 || v23 == 6 || v23 == 7 )
              goto LABEL_23;
            v24 = v23 == 10;
          }
          if ( !v24 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              if ( off_1800484D8[0] )
                bidTraceW(off_1800481C0[0], 2302976, off_1800484D8[0], 2147749405LL, 2249);
            }
            ThrowHR(-2147217891);
          }
        }
LABEL_23:
        GenADTG::SaveToBuffer((GenADTG *)a1, (const unsigned __int8 *)v12, v16);
        return;
      }
      *a4 = *(_QWORD *)v12;
    }
  }
}

```

## disassembly

```asm
0x1800076d4  mov     [rsp-38h+arg_0], rbx
0x1800076d9  mov     [rsp-38h+cbMultiByte], r8d
0x1800076de  push    rbp
0x1800076df  push    rsi
0x1800076e0  push    rdi
0x1800076e1  push    r12
0x1800076e3  push    r13
0x1800076e5  push    r14
0x1800076e7  push    r15
0x1800076e9  mov     rbp, rsp
0x1800076ec  sub     rsp, 30h
0x1800076f0  mov     r10, [rcx+38h]
0x1800076f4  mov     rsi, rcx
0x1800076f7  mov     r14, [rbp+arg_20]
0x1800076fb  mov     r15, r9
0x1800076fe  movzx   eax, dx
0x180007701  imul    rbx, rax, 58h ; 'X'
0x180007705  mov     [rbp+arg_8], 0
0x180007709  mov     [rbp+cbMultiByte], 0
0x180007710  mov     eax, [rbx+r10+18h]
0x180007715  mov     ecx, [rax+r14]
0x180007719  cmp     ecx, 0Dh
0x18000771c  ja      loc_18000794D
0x180007722  mov     eax, 2011h
0x180007727  bt      eax, ecx
0x18000772a  jnb     loc_18000794D
0x180007730  mov     edi, [rbx+r10+8]
0x180007735  mov     eax, 4000h
0x18000773a  add     rdi, r14
0x18000773d  test    [rbx+r10+54h], ax
0x180007743  jz      short loc_180007748
0x180007745  mov     rdi, [rdi]
0x180007748  movzx   eax, word ptr [rbx+r10]
0x18000774d  lea     r13, [rsi+80h]
0x180007754  mov     r11d, 1
0x18000775a  mov     rcx, r13; this
0x18000775d  sub     ax, r11w
0x180007761  movzx   edx, ax; unsigned __int16
0x180007764  movzx   r12d, ax
0x180007768  call    ?mdGetFlags@CMetaData@@QEAAKG@Z; CMetaData::mdGetFlags(ushort)
0x18000776d  bt      eax, 0Dh
0x180007771  jb      loc_180007947
0x180007777  mov     rcx, r13; this
0x18000777a  call    ?mdGetType@CMetaData@@QEAAGG@Z; CMetaData::mdGetType(ushort)
0x18000777f  mov     ecx, 88h
0x180007784  cmp     ax, cx
0x180007787  jz      loc_180007947
0x18000778d  test    byte ptr [rbx+r10+38h], 2
0x180007793  lea     r15d, [rcx-7]
0x180007797  jnz     short loc_1800077C6
0x180007799  mov     r8d, [rbx+r10+48h]
0x18000779e  mov     [rbp+cbMultiByte], r8d
0x1800077a2  cmp     [rbx+r10+54h], r15w
0x1800077a8  jnz     short loc_1800077AF
0x1800077aa  dec     r8d
0x1800077ad  jmp     short loc_1800077C0
0x1800077af  mov     eax, 82h
0x1800077b4  cmp     [rbx+r10+54h], ax
0x1800077ba  jnz     short loc_180007815
0x1800077bc  add     r8d, 0FFFFFFFEh
0x1800077c0  mov     [rbp+cbMultiByte], r8d
0x1800077c4  jmp     short loc_180007815
0x1800077c6  mov     rax, [rbx+r10+10h]
0x1800077cb  mov     ecx, [r14+rax]
0x1800077cf  mov     eax, 4000h
0x1800077d4  mov     [rbp+cbMultiByte], ecx
0x1800077d7  test    [rbx+r10+54h], ax
0x1800077dd  jnz     short loc_1800077FF
0x1800077df  cmp     ecx, 0FFh
0x1800077e5  ja      short loc_1800077F0
0x1800077e7  mov     [rbp+arg_8], cl
0x1800077ea  lea     rdx, [rbp+arg_8]
0x1800077ee  jmp     short loc_1800077FA
0x1800077f0  lea     rdx, [rbp+cbMultiByte]
0x1800077f4  mov     r11d, 4
0x1800077fa  mov     r8d, r11d
0x1800077fd  jmp     short loc_180007809
0x1800077ff  mov     r8d, 4; unsigned int
0x180007805  lea     rdx, [rbp+cbMultiByte]; unsigned __int8 *
0x180007809  mov     rcx, rsi; this
0x18000780c  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180007811  mov     r8d, [rbp+cbMultiByte]
0x180007815  mov     rax, [rsi+38h]
0x180007819  mov     ecx, 0BFFFh
0x18000781e  and     cx, [rbx+rax+54h]
0x180007823  cmp     cs:?g_fUnicode@@3HA, 0; int g_fUnicode
0x18000782a  jz      short loc_180007879
0x18000782c  cmp     cx, r15w
0x180007830  jnz     short loc_180007879
0x180007832  mov     edx, r8d; unsigned int
0x180007835  mov     rcx, rsi; this
0x180007838  call    ?GetUnicodeBuffer@GenADTG@@AEAAPEAGK@Z; GenADTG::GetUnicodeBuffer(ulong)
0x18000783d  mov     r9d, [rbp+cbMultiByte]; cbMultiByte
0x180007841  mov     r8, rdi; lpMultiByteStr
0x180007844  mov     [rsp+30h+cchWideChar], r9d; cchWideChar
0x180007849  xor     edx, edx; dwFlags
0x18000784b  xor     ecx, ecx; CodePage
0x18000784d  mov     [rsp+30h+lpWideCharStr], rax; lpWideCharStr
0x180007852  mov     rbx, rax
0x180007855  call    cs:__imp_MultiByteToWideChar
0x18000785b  movzx   r8d, ax
0x18000785f  mov     rdi, rbx
0x180007862  add     r8d, r8d; unsigned int
0x180007865  mov     [rbp+cbMultiByte], r8d
0x180007869  mov     rdx, rdi; unsigned __int8 *
0x18000786c  mov     rcx, rsi; this
0x18000786f  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180007874  jmp     loc_18000794D
0x180007879  cmp     cx, 0Ch
0x18000787d  jnz     short loc_180007869
0x18000787f  mov     eax, 0F000h
0x180007884  test    [rdi], ax
0x180007887  jz      short loc_180007890
0x180007889  mov     eax, 0FFFFh
0x18000788e  jmp     short loc_180007893
0x180007890  movzx   eax, word ptr [rdi]
0x180007893  movzx   ecx, ax
0x180007896  cmp     ecx, 0Bh
0x180007899  ja      short loc_1800078C9
0x18000789b  jz      short loc_180007869
0x18000789d  test    ecx, ecx
0x18000789f  jz      short loc_180007869
0x1800078a1  sub     ecx, 1
0x1800078a4  jz      short loc_180007869
0x1800078a6  sub     ecx, 1
0x1800078a9  jz      short loc_180007869
0x1800078ab  sub     ecx, 1
0x1800078ae  jz      short loc_180007869
0x1800078b0  sub     ecx, 1
0x1800078b3  jz      short loc_180007869
0x1800078b5  sub     ecx, 1
0x1800078b8  jz      short loc_180007869
0x1800078ba  sub     ecx, 1
0x1800078bd  jz      short loc_180007869
0x1800078bf  sub     ecx, 1
0x1800078c2  jz      short loc_180007869
0x1800078c4  cmp     ecx, 3
0x1800078c7  jmp     short loc_1800078FC
0x1800078c9  sub     ecx, 0Eh
0x1800078cc  jz      short loc_180007869
0x1800078ce  sub     ecx, 2
0x1800078d1  jz      short loc_180007869
0x1800078d3  sub     ecx, 1
0x1800078d6  jz      short loc_180007869
0x1800078d8  sub     ecx, 1
0x1800078db  jz      short loc_180007869
0x1800078dd  sub     ecx, 1
0x1800078e0  jz      short loc_180007869
0x1800078e2  sub     ecx, 1
0x1800078e5  jz      short loc_180007869
0x1800078e7  sub     ecx, 1
0x1800078ea  jz      loc_180007869
0x1800078f0  sub     ecx, 1
0x1800078f3  jz      loc_180007869
0x1800078f9  cmp     ecx, 1
0x1800078fc  jz      loc_180007869
0x180007902  test    byte ptr cs:_bidGblFlags, 2
0x180007909  mov     ebx, 80040E1Dh
0x18000790e  jz      short loc_18000793F
0x180007910  mov     rax, cs:off_1800484D8; "<GenADTG::SaveColumnData|ADO|ERR>  HRES"...
0x180007917  test    rax, rax
0x18000791a  jz      short loc_18000793F
0x18000791c  mov     r8, cs:off_1800484D8; "<GenADTG::SaveColumnData|ADO|ERR>  HRES"...
0x180007923  mov     r9d, ebx
0x180007926  mov     rcx, cs:off_1800481C0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18000792d  mov     edx, 232400h
0x180007932  mov     dword ptr [rsp+30h+lpWideCharStr], 8C9h
0x18000793a  call    _bidTraceW
0x18000793f  mov     ecx, ebx; int
0x180007941  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180007947  mov     rax, [rdi]
0x18000794a  mov     [r15], rax
0x18000794d  mov     rbx, [rsp+30h+arg_0]
0x180007952  add     rsp, 30h
0x180007956  pop     r15
0x180007958  pop     r14
0x18000795a  pop     r13
0x18000795c  pop     r12
0x18000795e  pop     rdi
0x18000795f  pop     rsi
0x180007960  pop     rbp
0x180007961  retn
```
