# StructuredQuery1::WritePROPVARIANT(IStream *,tagPROPVARIANT const &)

- ea: `0x180037e50`
- end: `0x1800382c5`
- name: `?WritePROPVARIANT@StructuredQuery1@@YAJPEAUIStream@@AEBUtagPROPVARIANT@@@Z`
- size: `1141`
- prototype: `__int64 __fastcall(StructuredQuery1 *__hidden this, struct IStream *, const struct tagPROPVARIANT *)`
- caller_count: `3`
- callee_count: `11`
- tags: ``

## callers

- `0x180037350`
- `0x180037740`
- `0x180037e50`

## callees

- `0x180036c70`
- `0x180037e50`
- `0x18005b434`
- `0x18005c914`
- `0x18005c964`
- `0x18006bde8`
- `0x18006be34`
- `0x18006be84`
- `0x18006c5bc`
- `0x18006c62c`
- `0x18008b010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180037e79`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180037ede`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180037f43`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180037fc1`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18003807e`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180038113`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18003814d`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180038187`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1800381cc`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180038221`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18008a1cf`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18008a1fd`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180037e79`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180037ede`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180037f43`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180037fc1`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18003807e`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180038113`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18003814d`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180038187`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1800381cc`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180038221`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18008a1cf`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18008a1fd`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::WritePROPVARIANT(
        StructuredQuery1 *this,
        struct IStream *a2,
        const struct tagPROPVARIANT *a3)
{
  struct IStream *v3; // rbx
  HRESULT v5; // edi
  __int16 v6; // dx
  int v7; // eax
  unsigned int *v8; // rsi
  __int64 v9; // rax
  int v10; // eax
  ULONG v12; // r8d
  struct IStream *v13; // rdx
  IStream *v14; // rcx
  _QWORD *v16; // rbx
  _QWORD *v17; // rcx
  struct IStream *v18; // r8
  struct IStream *v19; // rsi
  void **v20; // rsi
  void **v21; // rbx
  void **v22; // rsi
  void **v23; // rsi
  void **v24; // rbx
  void **v25; // rsi
  unsigned int *v26; // rsi
  __int64 v27; // rbx
  __int64 v28; // rsi
  unsigned int *v29; // rsi
  const struct tagPROPVARIANT *v30; // r8
  struct IStream *v31; // rbx
  struct IStream *v32; // rsi
  const wchar_t *v33; // r8
  struct IStream **v34; // rbx
  struct IStream **v35; // rsi
  int v36; // eax
  int v37; // eax
  int v38; // eax
  int v39; // eax
  StructuredQuery1 *pv; // [rsp+38h] [rbp+10h] BYREF

  v3 = a2;
  if ( (*(_WORD *)a2 & 0x2000) == 0 )
  {
    v5 = IStream_Write(this, a2, 2u);
    if ( v5 >= 0 )
    {
      v6 = *(_WORD *)v3;
      v7 = *(_WORD *)v3 & 0xFFF;
      switch ( v7 )
      {
        case 31:
          v8 = (unsigned int *)((char *)v3 + 8);
          if ( (v6 & 0x1000) != 0 )
          {
            v5 = IStream_Write(this, (char *)v3 + 8, 4u);
            if ( v5 >= 0 )
            {
              v34 = (struct IStream **)*((_QWORD *)v3 + 2);
              v35 = &v34[*v8];
              do
              {
                if ( v34 == v35 )
                  break;
                v39 = StructuredQuery1::WritePWSTR(this, *v34++, v33);
                v5 = v39;
              }
              while ( v39 >= 0 );
            }
          }
          else
          {
            v3 = *(struct IStream **)v8;
            if ( *(_QWORD *)v8 )
            {
              v9 = -1;
              do
                ++v9;
              while ( *((_WORD *)v3 + v9) );
              v10 = v9 + 1;
            }
            else
            {
              v10 = 0;
            }
            LODWORD(pv) = v10;
            v5 = IStream_Write(this, &pv, 4u);
            if ( v5 >= 0 && (_DWORD)pv )
            {
              v12 = 2 * (_DWORD)pv - 2;
              goto LABEL_17;
            }
          }
          break;
        case 3:
LABEL_13:
          v3 = (struct IStream *)((char *)v3 + 8);
          if ( (v6 & 0x1000) == 0 )
          {
            if ( (v6 & 0x4000) != 0 )
              v3 = *(struct IStream **)v3;
            v12 = 4;
LABEL_17:
            v13 = v3;
LABEL_18:
            v14 = this;
            return (unsigned int)IStream_Write(v14, v13, v12);
          }
          v5 = StructuredQuery1::WriteBlob_long_(this);
          break;
        case 4095:
LABEL_83:
          StructuredQuery1::WriteBlob_unsigned_char_(this);
          break;
        default:
          switch ( *(_WORD *)v3 & 0xFFF )
          {
            case 0:
            case 1:
            case 0x18:
              return (unsigned int)v5;
            case 2:
            case 0xB:
            case 0x12:
              v3 = (struct IStream *)((char *)v3 + 8);
              if ( (v6 & 0x1000) != 0 )
                return (unsigned int)StructuredQuery1::WriteBlob_short_(this);
              if ( (v6 & 0x4000) != 0 )
                v3 = *(struct IStream **)v3;
              v12 = 2;
              goto LABEL_17;
            case 4:
            case 0xA:
            case 0x13:
            case 0x16:
            case 0x17:
            case 0x19:
              goto LABEL_13;
            case 5:
            case 6:
            case 7:
            case 0x14:
            case 0x15:
            case 0x40:
              v16 = (_QWORD *)((char *)v3 + 8);
              if ( (v6 & 0x1000) != 0 )
              {
                return (unsigned int)StructuredQuery1::WriteBlob_double_(this);
              }
              else
              {
                if ( (v6 & 0x4000) != 0 )
                  v16 = (_QWORD *)*v16;
                return (unsigned int)IStream_Write(this, v16, 8u);
              }
            case 8:
              v20 = (void **)((char *)v3 + 8);
              if ( (v6 & 0x1000) != 0 )
              {
                v5 = IStream_Write(this, (char *)v3 + 8, 4u);
                if ( v5 >= 0 )
                {
                  v21 = (void **)*((_QWORD *)v3 + 2);
                  v22 = &v21[*(unsigned int *)v20];
                  do
                  {
                    if ( v21 == v22 )
                      break;
                    v36 = StructuredQuery1::WriteBSTR(this, *v21++);
                    v5 = v36;
                  }
                  while ( v36 >= 0 );
                }
                return (unsigned int)v5;
              }
              if ( (v6 & 0x4000) != 0 )
                v20 = (void **)*v20;
              return (unsigned int)StructuredQuery1::WriteBSTR(this, *v20);
            case 9:
            case 0xD:
              v17 = (_QWORD *)((char *)v3 + 8);
              pv = 0;
              if ( (v6 & 0x4000) != 0 )
                v17 = (_QWORD *)*v17;
              v5 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, StructuredQuery1 **))*v17)(
                     *v17,
                     &GUID_00000109_0000_0000_c000_000000000046,
                     &pv);
              if ( v5 >= 0 )
              {
                v5 = StructuredQuery1::SaveToStream(pv, (struct IPersistStream *)this, v18);
                (*(void (__fastcall **)(StructuredQuery1 *))(*(_QWORD *)pv + 16LL))(pv);
              }
              return (unsigned int)v5;
            case 0xC:
              if ( (v6 & 0x1000) != 0 )
              {
                v29 = (unsigned int *)((char *)v3 + 8);
                v5 = IStream_Write(this, (char *)v3 + 8, 4u);
                if ( v5 >= 0 )
                {
                  v31 = (struct IStream *)*((_QWORD *)v3 + 2);
                  v32 = (struct IStream *)((char *)v31 + 24 * *v29);
                  do
                  {
                    if ( v31 == v32 )
                      break;
                    v38 = StructuredQuery1::WritePROPVARIANT(this, v31, v30);
                    v31 = (struct IStream *)((char *)v31 + 24);
                    v5 = v38;
                  }
                  while ( v38 >= 0 );
                }
              }
              else
              {
                if ( (v6 & 0x4000) != 0 )
                  return (unsigned int)StructuredQuery1::WritePROPVARIANT(
                                         this,
                                         *((struct IStream **)v3 + 1),
                                         &_ImageBase);
                return (unsigned int)-2147024809;
              }
              return (unsigned int)v5;
            case 0xE:
              if ( (v6 & 0x4000) != 0 )
                v3 = (struct IStream *)*((_QWORD *)v3 + 1);
              v12 = 16;
              goto LABEL_17;
            case 0x10:
            case 0x11:
              v3 = (struct IStream *)((char *)v3 + 8);
              if ( (v6 & 0x1000) == 0 )
              {
                if ( (v6 & 0x4000) != 0 )
                  v3 = *(struct IStream **)v3;
                v12 = 1;
                goto LABEL_17;
              }
              v19 = (struct IStream *)*((_QWORD *)v3 + 1);
              LODWORD(pv) = *(_DWORD *)v3;
              v5 = IStream_Write(this, &pv, 4u);
              if ( v5 < 0 )
                return (unsigned int)v5;
              v12 = (unsigned int)pv;
              v13 = v19;
              goto LABEL_18;
            case 0x1E:
              v23 = (void **)((char *)v3 + 8);
              if ( (v6 & 0x1000) == 0 )
                return (unsigned int)StructuredQuery1::WritePSTR(this, *v23);
              v5 = IStream_Write(this, (char *)v3 + 8, 4u);
              if ( v5 >= 0 )
              {
                v24 = (void **)*((_QWORD *)v3 + 2);
                v25 = &v24[*(unsigned int *)v23];
                do
                {
                  if ( v24 == v25 )
                    break;
                  v37 = StructuredQuery1::WritePSTR(this, *v24++);
                  v5 = v37;
                }
                while ( v37 >= 0 );
              }
              return (unsigned int)v5;
            case 0x41:
            case 0x46:
              goto LABEL_83;
            case 0x47:
              v26 = (unsigned int *)((char *)v3 + 8);
              if ( (v6 & 0x1000) != 0 )
              {
                v5 = IStream_Write(this, (char *)v3 + 8, 4u);
                if ( v5 >= 0 )
                {
                  v27 = *((_QWORD *)v3 + 2);
                  v28 = v27 + 16LL * *v26;
                  while ( v27 != v28 )
                  {
                    v5 = IStream_Write(this, (const void *)(v27 + 4), 4u);
                    if ( v5 < 0 )
                      break;
                    StructuredQuery1::WriteBlob_unsigned_char_(this);
                    v27 += 16;
                  }
                }
                return (unsigned int)v5;
              }
              v5 = IStream_Write(this, (const void *)(*(_QWORD *)v26 + 4LL), 4u);
              if ( v5 < 0 )
                return (unsigned int)v5;
              goto LABEL_83;
            case 0x48:
              v14 = this;
              if ( (v6 & 0x1000) != 0 )
                return (unsigned int)StructuredQuery1::WriteBlob__GUID_(this);
              v13 = (struct IStream *)*((_QWORD *)v3 + 1);
              v12 = 16;
              break;
            default:
              return (unsigned int)-2147467263;
          }
          return (unsigned int)IStream_Write(v14, v13, v12);
      }
    }
    return (unsigned int)v5;
  }
  return 2147500033LL;
}

```

## disassembly

```asm
0x180037e50  mov     [rsp+arg_10], rbx
0x180037e55  mov     [rsp+arg_18], rbp
0x180037e5a  push    rdi
0x180037e5b  sub     rsp, 20h
0x180037e5f  mov     eax, 2000h
0x180037e64  mov     rbx, rdx
0x180037e67  mov     rbp, rcx
0x180037e6a  test    [rdx], ax
0x180037e6d  jnz     loc_180037F01
0x180037e73  mov     r8d, 2; cb
0x180037e79  call    cs:__imp_IStream_Write
0x180037e7f  mov     edi, eax
0x180037e81  test    eax, eax
0x180037e83  js      short loc_180037EEF
0x180037e85  movzx   edx, word ptr [rbx]
0x180037e88  mov     eax, edx
0x180037e8a  mov     [rsp+28h+arg_0], rsi
0x180037e8f  and     eax, 0FFFh
0x180037e94  cmp     eax, 1Fh
0x180037e97  jnz     short loc_180037F18
0x180037e99  bt      dx, 0Ch
0x180037e9e  lea     rsi, [rbx+8]
0x180037ea2  jb      loc_180038215
0x180037ea8  mov     rbx, [rsi]
0x180037eab  test    rbx, rbx
0x180037eae  jz      loc_180037F61
0x180037eb4  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180037ebb  nop     dword ptr [rax+rax+00h]
0x180037ec0  inc     rax
0x180037ec3  cmp     word ptr [rbx+rax*2], 0
0x180037ec8  jnz     short loc_180037EC0
0x180037eca  inc     eax
0x180037ecc  mov     r8d, 4; cb
0x180037ed2  mov     dword ptr [rsp+28h+pv], eax
0x180037ed6  lea     rdx, [rsp+28h+pv]; pv
0x180037edb  mov     rcx, rbp; pstm
0x180037ede  call    cs:__imp_IStream_Write
0x180037ee4  mov     edi, eax
0x180037ee6  test    eax, eax
0x180037ee8  jns     short loc_180037F4D
0x180037eea  mov     rsi, [rsp+28h+arg_0]; jumptable 0000000180037F99 cases 0,1,24
0x180037eef  mov     eax, edi
0x180037ef1  mov     rbx, [rsp+28h+arg_10]
0x180037ef6  mov     rbp, [rsp+28h+arg_18]
0x180037efb  add     rsp, 20h
0x180037eff  pop     rdi
0x180037f00  retn
0x180037f01  mov     rbx, [rsp+28h+arg_10]
0x180037f06  mov     edi, 80004001h
0x180037f0b  mov     rbp, [rsp+28h+arg_18]
0x180037f10  mov     eax, edi
0x180037f12  add     rsp, 20h
0x180037f16  pop     rdi
0x180037f17  retn
0x180037f18  cmp     eax, 3
0x180037f1b  jnz     short loc_180037F68
0x180037f1d  add     rbx, 8; jumptable 0000000180037F99 cases 4,10,19,22,23,25
0x180037f21  bt      dx, 0Ch
0x180037f26  jb      loc_180037FCE
0x180037f2c  bt      dx, 0Eh
0x180037f31  jb      loc_18003820D
0x180037f37  mov     r8d, 4; cb
0x180037f3d  mov     rdx, rbx; pv
0x180037f40  mov     rcx, rbp; pstm
0x180037f43  call    cs:__imp_IStream_Write
0x180037f49  mov     edi, eax
0x180037f4b  jmp     short loc_180037EEA; jumptable 0000000180037F99 cases 0,1,24
0x180037f4d  mov     r8d, dword ptr [rsp+28h+pv]
0x180037f52  test    r8d, r8d
0x180037f55  jz      short loc_180037EEA; jumptable 0000000180037F99 cases 0,1,24
0x180037f57  lea     r8d, ds:0FFFFFFFFFFFFFFFEh[r8*2]
0x180037f5f  jmp     short loc_180037F3D
0x180037f61  xor     eax, eax
0x180037f63  jmp     loc_180037ECC
0x180037f68  cmp     eax, 0FFFh
0x180037f6d  jz      loc_1800381F9; jumptable 0000000180037F99 cases 65,70
0x180037f73  cmp     eax, 48h; switch 73 cases
0x180037f76  ja      def_180037F99; jumptable 0000000180037F99 default case, cases 3,15,26-29,31-63,66-69
0x180037f7c  lea     r8, __ImageBase; struct tagPROPVARIANT *
0x180037f83  cdqe
0x180037f85  movzx   eax, ds:(byte_18003827C - 180000000h)[r8+rax]
0x180037f8e  mov     ecx, ds:(jpt_180037F99 - 180000000h)[r8+rax*4]
0x180037f96  add     rcx, r8
0x180037f99  jmp     rcx; switch jump
0x180037f9b  add     rbx, 8; jumptable 0000000180037F99 cases 5-7,20,21,64
0x180037f9f  bt      dx, 0Ch
0x180037fa4  jb      loc_180038042
0x180037faa  bt      dx, 0Eh
0x180037faf  jb      loc_1800380BD
0x180037fb5  mov     r8d, 8; cb
0x180037fbb  mov     rdx, rbx; pv
0x180037fbe  mov     rcx, rbp; pstm
0x180037fc1  call    cs:__imp_IStream_Write
0x180037fc7  mov     edi, eax
0x180037fc9  jmp     loc_180037EEA; jumptable 0000000180037F99 cases 0,1,24
0x180037fce  mov     r8, [rbx+8]
0x180037fd2  mov     rcx, rbp; pstm
0x180037fd5  mov     edx, [rbx]
0x180037fd7  call    StructuredQuery1__WriteBlob_long_
0x180037fdc  mov     edi, eax
0x180037fde  jmp     loc_180037EEA; jumptable 0000000180037F99 cases 0,1,24
0x180037fe3  xor     eax, eax; jumptable 0000000180037F99 cases 9,13
0x180037fe5  lea     rcx, [rbx+8]
0x180037fe9  bt      dx, 0Eh
0x180037fee  mov     [rsp+28h+pv], rax
0x180037ff3  jb      loc_1800381A9
0x180037ff9  mov     rcx, [rcx]
0x180037ffc  lea     r8, [rsp+28h+pv]
0x180038001  lea     rdx, _GUID_00000109_0000_0000_c000_000000000046
0x180038008  mov     rax, [rcx]
0x18003800b  mov     rax, [rax]
0x18003800e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038013  mov     edi, eax
0x180038015  test    eax, eax
0x180038017  js      loc_180037EEA; jumptable 0000000180037F99 cases 0,1,24
0x18003801d  mov     rcx, [rsp+28h+pv]; this
0x180038022  mov     rdx, rbp; struct IPersistStream *
0x180038025  call    ?SaveToStream@StructuredQuery1@@YAJPEAUIPersistStream@@PEAUIStream@@@Z; StructuredQuery1::SaveToStream(IPersistStream *,IStream *)
0x18003802a  mov     rcx, [rsp+28h+pv]
0x18003802f  mov     edi, eax
0x180038031  mov     rax, [rcx]
0x180038034  mov     rax, [rax+10h]
0x180038038  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003803d  jmp     loc_180037EEA; jumptable 0000000180037F99 cases 0,1,24
0x180038042  mov     r8, [rbx+8]
0x180038046  mov     rcx, rbp; pstm
0x180038049  mov     edx, [rbx]
0x18003804b  call    StructuredQuery1__WriteBlob_double_
0x180038050  mov     edi, eax
0x180038052  jmp     loc_180037EEA; jumptable 0000000180037F99 cases 0,1,24
0x180038057  add     rbx, 8; jumptable 0000000180037F99 cases 16,17
0x18003805b  bt      dx, 0Ch
0x180038060  jnb     loc_18008A106
0x180038066  mov     eax, [rbx]
0x180038068  lea     rdx, [rsp+28h+pv]; pv
0x18003806d  mov     rsi, [rbx+8]
0x180038071  mov     r8d, 4; cb
0x180038077  mov     rcx, rbp; pstm
0x18003807a  mov     dword ptr [rsp+28h+pv], eax
0x18003807e  call    cs:__imp_IStream_Write
0x180038084  mov     edi, eax
0x180038086  test    eax, eax
0x180038088  js      loc_180037EEA; jumptable 0000000180037F99 cases 0,1,24
0x18003808e  mov     r8d, dword ptr [rsp+28h+pv]
0x180038093  mov     rdx, rsi
0x180038096  jmp     loc_180037F40
0x18003809b  add     rbx, 8; jumptable 0000000180037F99 cases 2,11,18
0x18003809f  bt      dx, 0Ch
0x1800380a4  jnb     loc_18008A11B
0x1800380aa  mov     r8, [rbx+8]
0x1800380ae  mov     rcx, rbp; pstm
0x1800380b1  mov     edx, [rbx]
0x1800380b3  call    StructuredQuery1__WriteBlob_short_
0x1800380b8  jmp     loc_180037F49
0x1800380bd  mov     rbx, [rbx]
0x1800380c0  jmp     loc_180037FB5
0x1800380c5  bt      dx, 0Eh; jumptable 0000000180037F99 case 14
0x1800380ca  jnb     loc_18008A130
0x1800380d0  mov     rbx, [rbx+8]
0x1800380d4  jmp     loc_18008A130
0x1800380d9  bt      dx, 0Ch; jumptable 0000000180037F99 case 72
0x1800380de  mov     rcx, rbp; pstm
0x1800380e1  jnb     loc_18008A13B
0x1800380e7  mov     r8, [rbx+10h]
0x1800380eb  mov     edx, [rbx+8]
0x1800380ee  call    StructuredQuery1__WriteBlob__GUID_
0x1800380f3  jmp     loc_180037F49
0x1800380f8  bt      dx, 0Ch; jumptable 0000000180037F99 case 8
0x1800380fd  lea     rsi, [rbx+8]
0x180038101  jnb     loc_18008A16D
0x180038107  mov     r8d, 4; cb
0x18003810d  mov     rdx, rsi; pv
0x180038110  mov     rcx, rbp; pstm
0x180038113  call    cs:__imp_IStream_Write
0x180038119  mov     edi, eax
0x18003811b  test    eax, eax
0x18003811d  js      loc_180037EEA; jumptable 0000000180037F99 cases 0,1,24
0x180038123  mov     rbx, [rbx+10h]
0x180038127  mov     eax, [rsi]
0x180038129  lea     rsi, [rbx+rax*8]
0x18003812d  jmp     loc_18008A14A
0x180038132  bt      dx, 0Ch; jumptable 0000000180037F99 case 30
0x180038137  mov     rcx, rbp; pstm
0x18003813a  lea     rsi, [rbx+8]
0x18003813e  jnb     loc_18008A1AB
0x180038144  mov     r8d, 4; cb
0x18003814a  mov     rdx, rsi; pv
0x18003814d  call    cs:__imp_IStream_Write
0x180038153  mov     edi, eax
0x180038155  test    eax, eax
0x180038157  js      loc_180037EEA; jumptable 0000000180037F99 cases 0,1,24
0x18003815d  mov     rbx, [rbx+10h]
0x180038161  mov     eax, [rsi]
0x180038163  lea     rsi, [rbx+rax*8]
0x180038167  jmp     loc_18008A188
0x18003816c  bt      dx, 0Ch; jumptable 0000000180037F99 case 71
0x180038171  mov     r8d, 4; cb
0x180038177  lea     rsi, [rbx+8]
0x18003817b  mov     rcx, rbp; pstm
0x18003817e  jnb     loc_18008A1F6
0x180038184  mov     rdx, rsi; pv
0x180038187  call    cs:__imp_IStream_Write
0x18003818d  mov     edi, eax
0x18003818f  test    eax, eax
0x180038191  js      loc_180037EEA; jumptable 0000000180037F99 cases 0,1,24
0x180038197  mov     esi, [rsi]
0x180038199  mov     rbx, [rbx+10h]
0x18003819d  shl     rsi, 4
0x1800381a1  add     rsi, rbx
0x1800381a4  jmp     loc_18008A1B9
0x1800381a9  mov     rcx, [rcx]
0x1800381ac  jmp     loc_180037FF9
0x1800381b1  bt      dx, 0Ch; jumptable 0000000180037F99 case 12
0x1800381b6  jnb     loc_18008A24B
0x1800381bc  lea     rsi, [rbx+8]
0x1800381c0  mov     r8d, 4; cb
0x1800381c6  mov     rdx, rsi; pv
0x1800381c9  mov     rcx, rbp; pstm
0x1800381cc  call    cs:__imp_IStream_Write
0x1800381d2  mov     edi, eax
0x1800381d4  test    eax, eax
0x1800381d6  js      loc_180037EEA; jumptable 0000000180037F99 cases 0,1,24
0x1800381dc  mov     eax, [rsi]
0x1800381de  mov     rbx, [rbx+10h]
0x1800381e2  lea     rcx, [rax+rax*2]
0x1800381e6  lea     rsi, [rbx+rcx*8]
0x1800381ea  jmp     loc_18008A228
0x1800381ef  mov     edi, 80004001h; jumptable 0000000180037F99 default case, cases 3,15,26-29,31-63,66-69
0x1800381f4  jmp     loc_180037EEA; jumptable 0000000180037F99 cases 0,1,24
0x1800381f9  mov     r8, [rbx+10h]; jumptable 0000000180037F99 cases 65,70
0x1800381fd  mov     rcx, rbp; pstm
0x180038200  mov     edx, [rbx+8]
0x180038203  call    StructuredQuery1__WriteBlob_unsigned_char_
0x180038208  jmp     loc_180037EEA; jumptable 0000000180037F99 cases 0,1,24
0x18003820d  mov     rbx, [rbx]
0x180038210  jmp     loc_180037F37
0x180038215  mov     r8d, 4; cb
0x18003821b  mov     rdx, rsi; pv
0x18003821e  mov     rcx, rbp; pstm
0x180038221  call    cs:__imp_IStream_Write
0x180038227  mov     edi, eax
0x180038229  test    eax, eax
0x18003822b  js      loc_180037EEA; jumptable 0000000180037F99 cases 0,1,24
0x180038231  mov     rbx, [rbx+10h]
0x180038235  mov     eax, [rsi]
0x180038237  lea     rsi, [rbx+rax*8]
0x18003823b  jmp     loc_18008A26E
0x18008a106  bt      dx, 0Eh
0x18008a10b  jnb     short loc_18008A110
0x18008a10d  mov     rbx, [rbx]
0x18008a110  mov     r8d, 1
0x18008a116  jmp     loc_180037F3D
0x18008a11b  bt      dx, 0Eh
0x18008a120  jnb     short loc_18008A125
0x18008a122  mov     rbx, [rbx]
0x18008a125  mov     r8d, 2
0x18008a12b  jmp     loc_180037F3D
0x18008a130  mov     r8d, 10h
0x18008a136  jmp     loc_180037F3D
0x18008a13b  mov     rdx, [rbx+8]
0x18008a13f  mov     r8d, 10h
0x18008a145  jmp     loc_180037F43
0x18008a14a  cmp     rbx, rsi
0x18008a14d  jz      loc_180037EEA; jumptable 0000000180037F99 cases 0,1,24
0x18008a153  mov     rdx, [rbx]; pv
0x18008a156  mov     rcx, rbp; pstm
0x18008a159  call    StructuredQuery1__WriteBSTR
0x18008a15e  add     rbx, 8
0x18008a162  mov     edi, eax
0x18008a164  test    eax, eax
0x18008a166  jns     short loc_18008A14A
0x18008a168  jmp     loc_180037EEA; jumptable 0000000180037F99 cases 0,1,24
0x18008a16d  bt      dx, 0Eh
0x18008a172  jnb     short loc_18008A177
0x18008a174  mov     rsi, [rsi]
0x18008a177  mov     rdx, [rsi]; pv
0x18008a17a  mov     rcx, rbp; pstm
0x18008a17d  call    StructuredQuery1__WriteBSTR
0x18008a182  nop
0x18008a183  jmp     loc_180037F49
0x18008a188  cmp     rbx, rsi
0x18008a18b  jz      loc_180037EEA; jumptable 0000000180037F99 cases 0,1,24
0x18008a191  mov     rdx, [rbx]; pv
0x18008a194  mov     rcx, rbp; pstm
0x18008a197  call    StructuredQuery1__WritePSTR
0x18008a19c  add     rbx, 8
0x18008a1a0  mov     edi, eax
0x18008a1a2  test    eax, eax
0x18008a1a4  jns     short loc_18008A188
0x18008a1a6  jmp     loc_180037EEA; jumptable 0000000180037F99 cases 0,1,24
0x18008a1ab  mov     rdx, [rsi]; pv
0x18008a1ae  call    StructuredQuery1__WritePSTR
0x18008a1b3  nop
0x18008a1b4  jmp     loc_180037F49
0x18008a1b9  cmp     rbx, rsi
0x18008a1bc  jz      loc_180037EEA; jumptable 0000000180037F99 cases 0,1,24
0x18008a1c2  lea     rdx, [rbx+4]; pv
0x18008a1c6  mov     r8d, 4; cb
0x18008a1cc  mov     rcx, rbp; pstm
0x18008a1cf  call    cs:__imp_IStream_Write
  ... truncated ...
```
