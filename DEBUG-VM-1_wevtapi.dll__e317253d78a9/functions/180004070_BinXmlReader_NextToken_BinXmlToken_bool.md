# BinXmlReader::NextToken(BinXmlToken &,bool)

- ea: `0x180004070`
- end: `0x180004998`
- name: `?NextToken@BinXmlReader@@QEAAXAEAUBinXmlToken@@_N@Z`
- size: `2344`
- prototype: `void __fastcall(BinXmlReader *__hidden this, struct BinXmlToken *, bool)`
- caller_count: `5`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003158`
- `0x1800031f0`
- `0x180003aa0`
- `0x180007ae4`
- `0x18002fd5c`

## callees

- `0x180002098`
- `0x1800023e8`
- `0x180003780`
- `0x180003860`
- `0x180003a5c`
- `0x180003d20`
- `0x180004070`
- `0x1800049a0`
- `0x180004db0`
- `0x180004e70`
- `0x1800058f4`
- `0x180005ad4`
- `0x180008b20`
- `0x1800130f0`
- `0x180013690`
- `0x180013b40`
- `0x18001ef70`
- `0x1800231d0`
- `0x180023548`
- `0x180038fb4`
- `0x18003c010`

## pseudocode

```c
void __fastcall BinXmlReader::NextToken(BinXmlReader *this, struct BinXmlToken *a2, char a3)
{
  __int16 v6; // r11
  __int64 v7; // rdx
  __int64 v8; // r8
  char v9; // r9
  int v10; // eax
  bool v11; // r9
  __int64 v12; // rcx
  int v13; // edx
  char IsNextSubstValueNull; // al
  __int64 v15; // rdx
  __int64 v16; // r8
  bool v17; // zf
  int v18; // r10d
  __int64 v19; // r8
  unsigned int v20; // eax
  unsigned int v21; // r9d
  BinXmlReader *v22; // r11
  __int64 v23; // r11
  int v24; // edx
  unsigned int v25; // r8d
  __int64 v26; // rcx
  unsigned int v27; // eax
  unsigned int v28; // edx
  unsigned int v29; // r9d
  __int64 v30; // rcx
  unsigned int v31; // eax
  __int64 v32; // rax
  __int64 v33; // rcx
  unsigned int v34; // eax
  unsigned int v35; // r11d
  unsigned int v36; // r10d
  unsigned int v37; // ebx
  __int64 v38; // r8
  __int64 v39; // r9
  int v40; // edx
  __int64 v41; // rdx
  int v42; // r8d
  void (__fastcall ***v43)(_QWORD, __int64, char *); // rcx
  _QWORD *v44; // rbx
  __int64 v45; // rdx
  __int64 v46; // rcx
  int v47; // r8d
  unsigned int v48; // ecx
  __int64 v49; // r8
  __int64 v50; // r9
  int v51; // ecx
  WriteBuffer *v52; // rbx
  unsigned int *v53; // rdi
  __int64 v54; // rcx
  __int64 v55; // rcx
  __int64 v56; // rax
  int v57; // edx
  unsigned int v58; // eax
  _DWORD *v59; // rdi
  __int64 v60; // rax
  __int64 v61; // r11
  __int16 *v62; // rdx
  __int128 pExceptionObject; // [rsp+20h] [rbp-30h] BYREF
  __int64 v64; // [rsp+30h] [rbp-20h]
  int v65; // [rsp+38h] [rbp-18h]
  int v66; // [rsp+3Ch] [rbp-14h]
  int v67; // [rsp+40h] [rbp-10h]
  __int16 v68; // [rsp+80h] [rbp+30h] BYREF

  *(_QWORD *)((char *)a2 + 12) = 0;
  *((_BYTE *)a2 + 20) = 0;
LABEL_2:
  while ( 2 )
  {
    v6 = -1;
    while ( 1 )
    {
      while ( 1 )
      {
        while ( 1 )
        {
          v7 = *((_QWORD *)this + 2);
          LOBYTE(v68) = 0;
          v8 = *(unsigned int *)(v7 + 8);
          if ( (unsigned int)v8 >= *(_DWORD *)(v7 + 12) )
            goto LABEL_60;
          v9 = *(_BYTE *)(v8 + *(_QWORD *)v7);
          *(_DWORD *)(v7 + 8) = v8 + 1;
          v10 = v9 & 0x1F;
          v11 = (v9 & 0x40) != 0;
          *((_DWORD *)a2 + 4) = v10;
          *((_BYTE *)a2 + 20) = v11;
          if ( v10 != 1 )
            break;
          BinXmlReader::OpenStartElementTag(this, v11, (bool *)&v68);
          *((_DWORD *)a2 + 3) = 34;
          *(_QWORD *)a2 = (char *)this + 104;
          IsNextSubstValueNull = v68;
LABEL_11:
          v6 = -1;
LABEL_12:
          if ( !IsNextSubstValueNull )
            return;
        }
        if ( v10 != 14 )
          break;
LABEL_14:
        v15 = *((_QWORD *)this + 2);
        v16 = *(unsigned int *)(v15 + 8);
        if ( (unsigned int)(*(_DWORD *)(v15 + 12) - v16) < 2 )
          goto LABEL_60;
        v17 = *((_BYTE *)this + 188) == 0;
        v18 = *(unsigned __int16 *)(v16 + *(_QWORD *)v15);
        *(_DWORD *)(v15 + 8) = v16 + 2;
        if ( !v17 )
        {
          v49 = *((_QWORD *)this + 2);
          v50 = *(unsigned int *)(v49 + 8);
          if ( (unsigned int)v50 >= *(_DWORD *)(v49 + 12) )
            goto LABEL_60;
          v51 = *(unsigned __int8 *)(v50 + *(_QWORD *)v49);
          *(_DWORD *)(v49 + 8) = v50 + 1;
          *((_DWORD *)a2 + 3) = 8;
          *(_DWORD *)a2 = v18 | (v51 << 16);
          return;
        }
        if ( (_WORD)v18 == v6 )
        {
          v25 = 0;
          v29 = 0;
          v28 = 0;
        }
        else
        {
          v19 = *((_QWORD *)this + 9);
          if ( *((_QWORD *)this + 8) == v19 )
          {
            if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_2e7dc5ef0fe83399c91a1315b54063e2_Traceguids, 13);
            }
            v64 = 0;
            v65 = 13;
            v66 = -1;
            pExceptionObject = 0;
            v67 = 1174;
            throw (EvtException *)&pExceptionObject;
          }
          v20 = *(_DWORD *)(v19 - 16);
          if ( v20 )
          {
            v21 = *((_DWORD *)this + 3);
            if ( v20 > v21 )
              goto LABEL_60;
            v22 = this;
          }
          else
          {
            v60 = *((_QWORD *)this + 3);
            v61 = 5LL * *(unsigned __int16 *)(v19 - 8) + 3;
            v21 = *(_DWORD *)(v60 + 8 * v61 + 8);
            v22 = (BinXmlReader *)(v60 + 8 * v61);
            if ( v21 < 4 )
              goto LABEL_60;
            v20 = 4;
          }
          v23 = *(_QWORD *)v22;
          v24 = 0;
          v25 = *(_DWORD *)(v19 - 12);
          if ( v18 )
          {
            while ( v21 - v20 >= 4 )
            {
              v26 = v20;
              ++v24;
              v20 += 4;
              v25 += *(unsigned __int16 *)(v26 + v23);
              if ( v24 >= v18 )
                goto LABEL_24;
            }
LABEL_60:
            UserBuffer::ThrowUnexpectedEOFException();
          }
LABEL_24:
          if ( v21 - v20 < 4 )
            goto LABEL_60;
          v27 = *(_DWORD *)(v20 + v23);
          v28 = HIWORD(v27);
          v6 = -1;
          v29 = (unsigned __int16)v27;
        }
        v30 = *((_QWORD *)this + 2);
        v31 = *(_DWORD *)(v30 + 8);
        if ( v31 >= *(_DWORD *)(v30 + 12) )
          goto LABEL_60;
        *(_DWORD *)(v30 + 8) = v31 + 1;
        if ( v29 )
        {
          if ( v25 > *((_DWORD *)this + 3) )
            goto LABEL_60;
          *((_DWORD *)this + 2) = v25;
        }
        if ( v28 == 32 )
        {
          BinXmlReader::NextReaderData(this);
          goto LABEL_2;
        }
        if ( v28 != 33 )
        {
          *((_DWORD *)a2 + 3) = v28;
          *((_DWORD *)a2 + 4) = 5;
          BinXmlReader::NextValueData(this, this, a2, v29);
          return;
        }
        *((_QWORD *)this + 2) = this;
      }
      if ( v10 != 15 )
        break;
      v12 = *((_QWORD *)this + 2);
      if ( !*(_QWORD *)v12 )
        goto LABEL_60;
      v13 = *(_DWORD *)(v12 + 8);
      if ( (unsigned int)(*(_DWORD *)(v12 + 12) - v13) < 3 )
        goto LABEL_60;
      *(_DWORD *)(v12 + 8) = v13 + 3;
    }
    switch ( v10 )
    {
      case 0:
        if ( *((BinXmlReader **)this + 2) == this )
        {
          v32 = *((_QWORD *)this + 9);
          if ( *((_QWORD *)this + 8) == v32 )
            return;
          *((_QWORD *)this + 2) = v32 - 32;
          IsNextSubstValueNull = a3;
          goto LABEL_12;
        }
        v33 = *((_QWORD *)this + 9);
        if ( *((_QWORD *)this + 8) == v33 )
        {
          if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_2e7dc5ef0fe83399c91a1315b54063e2_Traceguids, 13);
          }
          v64 = 0;
          v65 = 13;
          v66 = -1;
          pExceptionObject = 0;
          v67 = 1770;
          throw (EvtException *)&pExceptionObject;
        }
        v34 = *(_DWORD *)(v33 - 16);
        if ( !v34 )
        {
          utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::pop_back((char *)this + 64);
          v54 = *((_QWORD *)this + 9);
          if ( *((_QWORD *)this + 8) == v54 )
          {
            IsNextSubstValueNull = 0;
          }
          else
          {
            *((_QWORD *)this + 2) = v54 - 32;
            v55 = 5LL * *(unsigned __int16 *)(v54 - 8);
            v56 = *((_QWORD *)this + 3);
            v57 = *(_DWORD *)(v56 + 8 * v55 + 16);
            *(_QWORD *)this = *(_QWORD *)(v56 + 8 * v55 + 8);
            IsNextSubstValueNull = 1;
            *((_DWORD *)this + 2) = 0;
            *((_DWORD *)this + 3) = v57;
          }
          goto LABEL_12;
        }
        *((_QWORD *)this + 2) = this;
        if ( v34 > *((_DWORD *)this + 3) )
          goto LABEL_60;
        *((_DWORD *)this + 2) = v34;
        v35 = 0;
        v36 = 0;
        v37 = (*(_DWORD *)(v33 - 12) - v34) >> 2;
        if ( v37 )
        {
          do
          {
            v38 = *((_QWORD *)this + 2);
            v39 = *(unsigned int *)(v38 + 8);
            if ( (unsigned int)(*(_DWORD *)(v38 + 12) - v39) < 4 )
              goto LABEL_60;
            ++v36;
            v40 = *(_DWORD *)(v39 + *(_QWORD *)v38);
            *(_DWORD *)(v38 + 8) = v39 + 4;
            v35 += (unsigned __int16)v40;
          }
          while ( v36 < v37 );
        }
        v41 = *((_QWORD *)this + 2);
        if ( !*(_QWORD *)v41 )
          goto LABEL_60;
        if ( v35 > 0x10000000 )
          goto LABEL_60;
        v42 = *(_DWORD *)(v41 + 8);
        if ( v35 > *(_DWORD *)(v41 + 12) - v42 )
          goto LABEL_60;
        *(_DWORD *)(v41 + 8) = v42 + v35;
        utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::pop_back((char *)this + 64);
        if ( *((_QWORD *)this + 8) != *((_QWORD *)this + 9) )
          continue;
        return;
      case 2:
        return;
      case 3:
      case 4:
        BinXmlReader::EndElementTag(this);
        return;
      case 5:
        BinXmlReader::NextValue(this, *((struct UserBuffer **)this + 2), a2);
        if ( !a3 )
          return;
        v52 = (BinXmlReader *)((char *)this + 152);
        v53 = (unsigned int *)((char *)this + 168);
        if ( !*((_BYTE *)a2 + 20) && !*v53 )
          goto LABEL_64;
        WriteCharDataText((BinXmlReader *)((char *)this + 152), (float *)a2, 0, 0);
        if ( *((_BYTE *)a2 + 20) )
          goto LABEL_65;
        *(_QWORD *)a2 = *((_QWORD *)this + 16);
        v58 = *v53;
        goto LABEL_72;
      case 6:
        v43 = (void (__fastcall ***)(_QWORD, __int64, char *))*((_QWORD *)this + 11);
        v44 = (_QWORD *)((char *)this + 104);
        v45 = *((_QWORD *)this + 2);
        if ( v43 )
        {
          (**v43)(v43, v45, (char *)this + 104);
        }
        else
        {
          v46 = *(unsigned int *)(v45 + 8);
          if ( (unsigned int)(*(_DWORD *)(v45 + 12) - v46) < 4 )
            goto LABEL_60;
          *((_DWORD *)this + 28) = *(_DWORD *)(v46 + *(_QWORD *)v45);
          *(_DWORD *)(v45 + 8) += 4;
          *v44 = *(_QWORD *)v45 + *(unsigned int *)(v45 + 8);
          if ( !*(_QWORD *)v45 )
            goto LABEL_60;
          v47 = *(_DWORD *)(v45 + 8);
          v48 = 2 * *((unsigned __int16 *)this + 57) + 2;
          if ( v48 > *(_DWORD *)(v45 + 12) - v47 )
            goto LABEL_60;
          *(_DWORD *)(v45 + 8) = v48 + v47;
          *((_BYTE *)this + 116) = 1;
        }
        *((_DWORD *)a2 + 3) = 34;
        *(_QWORD *)a2 = v44;
        IsNextSubstValueNull = BinXmlReader::IsNextSubstValueNull(this);
        goto LABEL_11;
      case 7:
      case 11:
        *((_DWORD *)a2 + 3) = 1;
        ReadLPString(*((_QWORD *)this + 2), (char *)a2 + 8, a2);
        return;
      case 8:
        *((_DWORD *)a2 + 3) = 6;
        UserBuffer::Read2(*((UserBuffer **)this + 2), a2);
        if ( !a3 )
          return;
        v52 = (BinXmlReader *)((char *)this + 152);
        v59 = (_DWORD *)((char *)this + 168);
        if ( !*((_BYTE *)a2 + 20) && !*v59 )
          goto LABEL_64;
        WriteBuffer::Write((BinXmlReader *)((char *)this + 152), a2, 2u);
        if ( *((_BYTE *)a2 + 20) )
          goto LABEL_65;
        *(_QWORD *)a2 = *((_QWORD *)this + 16);
        *((_DWORD *)a2 + 2) = *v59 >> 1;
        *((_DWORD *)a2 + 3) = 1;
        *((_DWORD *)a2 + 4) = 5;
        goto LABEL_64;
      case 9:
        BinXmlReader::NextName(this, (BinXmlReader *)((char *)this + 104));
        *((_DWORD *)a2 + 3) = 34;
        *(_QWORD *)a2 = (char *)this + 104;
        if ( !a3 )
          return;
        if ( !*((_BYTE *)a2 + 20) && !*((_DWORD *)this + 42) )
        {
          v52 = (BinXmlReader *)((char *)this + 152);
LABEL_64:
          WriteBuffer::SetCurrentIndex(v52, 0);
          goto LABEL_65;
        }
        v68 = 0;
        if ( *((_WORD *)this + 57) == 3
          && !(unsigned int)UnalignedStringCompareI(L"amp", *((const wchar_t **)this + 13), 3u) )
        {
          v68 = 38;
          v52 = (BinXmlReader *)((char *)this + 152);
LABEL_88:
          v62 = &v68;
          goto LABEL_89;
        }
        if ( *(_WORD *)(*(_QWORD *)a2 + 10LL) == 2
          && !(unsigned int)UnalignedStringCompareI(L"lt", **(const wchar_t ***)a2, 2u) )
        {
          v52 = (BinXmlReader *)((char *)this + 152);
          v68 = 60;
          goto LABEL_88;
        }
        if ( *(_WORD *)(*(_QWORD *)a2 + 10LL) == 2
          && !(unsigned int)UnalignedStringCompareI(L"gt", **(const wchar_t ***)a2, 2u) )
        {
          v52 = (BinXmlReader *)((char *)this + 152);
          v68 = 62;
          goto LABEL_88;
        }
        if ( *(_WORD *)(*(_QWORD *)a2 + 10LL) == 4
          && !(unsigned int)UnalignedStringCompareI(L"apos", **(const wchar_t ***)a2, 4u) )
        {
          v52 = (BinXmlReader *)((char *)this + 152);
          v68 = 39;
          goto LABEL_88;
        }
        if ( *(_WORD *)(*(_QWORD *)a2 + 10LL) == 4
          && !(unsigned int)UnalignedStringCompareI(L"quot", **(const wchar_t ***)a2, 4u) )
        {
          v68 = 34;
        }
        v52 = (BinXmlReader *)((char *)this + 152);
        if ( v68 )
          goto LABEL_88;
        WriteBuffer::Write((BinXmlReader *)((char *)this + 152), L"&", 2u);
        WriteNameText((char *)this + 152, (char *)this + 104);
        v62 = L";";
LABEL_89:
        WriteBuffer::Write(v52, v62, 2u);
        if ( !*((_BYTE *)a2 + 20) )
        {
          *((_DWORD *)a2 + 4) = 5;
          *(_QWORD *)a2 = *((_QWORD *)this + 16);
          v58 = *((_DWORD *)this + 42);
LABEL_72:
          *((_DWORD *)a2 + 2) = v58 >> 1;
          *((_DWORD *)a2 + 3) = 1;
          goto LABEL_64;
        }
LABEL_65:
        IsNextSubstValueNull = *((_BYTE *)a2 + 20);
        goto LABEL_11;
      case 10:
        BinXmlReader::NextName(this, (BinXmlReader *)((char *)this + 104));
        *((_DWORD *)a2 + 3) = 34;
        *(_QWORD *)a2 = (char *)this + 104;
        return;
      case 12:
        if ( !a3 )
          return;
        BinXmlReader::StartTemplateInstanceToken(this);
        continue;
      case 13:
        goto LABEL_14;
      default:
        if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_2e7dc5ef0fe83399c91a1315b54063e2_Traceguids, 13);
        }
        v64 = 0;
        v65 = 13;
        v66 = -1;
        pExceptionObject = 0;
        v67 = 1846;
        throw (EvtException *)&pExceptionObject;
    }
  }
}

```

## disassembly

```asm
0x180004070  mov     [rsp-28h+arg_10], rbx
0x180004075  mov     [rsp-28h+arg_18], rsi
0x18000407a  push    rbp
0x18000407b  push    r12
0x18000407d  push    r13
0x18000407f  push    r14
0x180004081  push    r15
0x180004083  mov     rbp, rsp
0x180004086  sub     rsp, 50h
0x18000408a  xor     r12d, r12d
0x18000408d  mov     [rsp+50h+arg_8], rdi
0x180004095  mov     [rdx+0Ch], r12
0x180004099  movzx   r15d, r8b
0x18000409d  mov     [rdx+14h], r12b
0x1800040a1  mov     r14, rdx
0x1800040a4  mov     rsi, rcx
0x1800040a7  mov     r13d, 22h ; '"'
0x1800040ad  mov     ebx, 26h ; '&'
0x1800040b2  mov     r11d, 0FFFFh
0x1800040b8  lea     r10, __ImageBase
0x1800040bf  mov     rdx, [rsi+10h]
0x1800040c3  mov     byte ptr [rbp+arg_0], r12b
0x1800040c7  mov     r8d, [rdx+8]
0x1800040cb  cmp     r8d, [rdx+0Ch]
0x1800040cf  jnb     loc_180004488
0x1800040d5  mov     rax, [rdx]
0x1800040d8  movzx   r9d, byte ptr [r8+rax]
0x1800040dd  lea     eax, [r8+1]
0x1800040e1  mov     [rdx+8], eax
0x1800040e4  mov     eax, r9d
0x1800040e7  shr     r9b, 6
0x1800040eb  and     eax, 1Fh
0x1800040ee  and     r9b, 1
0x1800040f2  mov     [r14+10h], eax
0x1800040f6  mov     [r14+14h], r9b
0x1800040fa  cmp     eax, 1
0x1800040fd  jz      short loc_180004137
0x1800040ff  cmp     eax, 0Eh
0x180004102  jz      loc_18000418D; jumptable 00000001800042BF case 13
0x180004108  cmp     eax, 0Fh
0x18000410b  jnz     loc_1800042A9
0x180004111  mov     rcx, [rsi+10h]
0x180004115  cmp     [rcx], r12
0x180004118  jz      loc_180004488
0x18000411e  mov     eax, [rcx+0Ch]
0x180004121  mov     edx, [rcx+8]
0x180004124  sub     eax, edx
0x180004126  cmp     eax, 3
0x180004129  jb      loc_180004488
0x18000412f  lea     eax, [rdx+3]
0x180004132  mov     [rcx+8], eax
0x180004135  jmp     short loc_1800040BF
0x180004137  lea     r8, [rbp+arg_0]; bool *
0x18000413b  movzx   edx, r9b; bool
0x18000413f  mov     rcx, rsi; this
0x180004142  call    ?OpenStartElementTag@BinXmlReader@@AEAAX_NAEA_N@Z; BinXmlReader::OpenStartElementTag(bool,bool &)
0x180004147  lea     rax, [rsi+68h]
0x18000414b  mov     [r14+0Ch], r13d
0x18000414f  mov     [r14], rax
0x180004152  movzx   eax, byte ptr [rbp+arg_0]
0x180004156  mov     r11d, 0FFFFh
0x18000415c  lea     r10, __ImageBase
0x180004163  test    al, al
0x180004165  jnz     loc_1800040BF
0x18000416b  mov     rdi, [rsp+50h+arg_8]; jumptable 00000001800042BF case 2
0x180004173  lea     r11, [rsp+50h+var_s0]
0x180004178  mov     rbx, [r11+40h]
0x18000417c  mov     rsi, [r11+48h]
0x180004180  mov     rsp, r11
0x180004183  pop     r15
0x180004185  pop     r14
0x180004187  pop     r13
0x180004189  pop     r12
0x18000418b  pop     rbp
0x18000418c  retn
0x18000418d  mov     rdx, [rsi+10h]; jumptable 00000001800042BF case 13
0x180004191  mov     r8d, [rdx+8]
0x180004195  mov     eax, [rdx+0Ch]
0x180004198  sub     eax, r8d
0x18000419b  cmp     eax, 2
0x18000419e  jb      loc_180004488
0x1800041a4  mov     rax, [rdx]
0x1800041a7  cmp     [rsi+0BCh], r12b
0x1800041ae  movzx   r10d, word ptr [r8+rax]
0x1800041b3  lea     eax, [r8+2]
0x1800041b7  mov     [rdx+8], eax
0x1800041ba  jnz     loc_180004454
0x1800041c0  cmp     r10w, r11w
0x1800041c4  jz      loc_1800044D8
0x1800041ca  mov     r8, [rsi+48h]
0x1800041ce  cmp     [rsi+40h], r8
0x1800041d2  jz      loc_1800048F1
0x1800041d8  mov     eax, [r8-10h]
0x1800041dc  test    eax, eax
0x1800041de  jz      loc_1800045F7
0x1800041e4  mov     r9d, [rsi+0Ch]
0x1800041e8  cmp     eax, r9d
0x1800041eb  ja      loc_180004488
0x1800041f1  mov     r11, rsi
0x1800041f4  mov     r11, [r11]
0x1800041f7  mov     edx, r12d
0x1800041fa  mov     r8d, [r8-0Ch]
0x1800041fe  test    r10d, r10d
0x180004201  jz      short loc_180004232
0x180004203  nop     dword ptr [rax+00h]
0x180004207  nop     word ptr [rax+rax+00000000h]
0x180004210  mov     ecx, r9d
0x180004213  sub     ecx, eax
0x180004215  cmp     ecx, 4
0x180004218  jb      loc_180004488
0x18000421e  mov     ecx, eax
0x180004220  inc     edx
0x180004222  add     eax, 4
0x180004225  movzx   ecx, word ptr [rcx+r11]
0x18000422a  add     r8d, ecx
0x18000422d  cmp     edx, r10d
0x180004230  jl      short loc_180004210
0x180004232  sub     r9d, eax
0x180004235  cmp     r9d, 4
0x180004239  jb      loc_180004488
0x18000423f  mov     ecx, eax
0x180004241  mov     eax, [rcx+r11]
0x180004245  mov     edx, eax
0x180004247  shr     edx, 10h
0x18000424a  mov     r11d, 0FFFFh
0x180004250  movzx   r9d, ax; unsigned int
0x180004254  mov     rcx, [rsi+10h]
0x180004258  mov     eax, [rcx+8]
0x18000425b  cmp     eax, [rcx+0Ch]
0x18000425e  jnb     loc_180004488
0x180004264  inc     eax
0x180004266  mov     [rcx+8], eax
0x180004269  test    r9d, r9d
0x18000426c  jz      short loc_18000427C
0x18000426e  cmp     r8d, [rsi+0Ch]
0x180004272  ja      loc_180004488
0x180004278  mov     [rsi+8], r8d
0x18000427c  cmp     edx, 20h ; ' '
0x18000427f  jz      short loc_1800042E6
0x180004281  cmp     edx, 21h ; '!'
0x180004284  jz      loc_1800045EE
0x18000428a  mov     [r14+0Ch], edx
0x18000428e  mov     r8, r14; struct BinXmlVariant *
0x180004291  mov     rdx, rsi; struct UserBuffer *
0x180004294  mov     dword ptr [r14+10h], 5
0x18000429c  mov     rcx, rsi; this
0x18000429f  call    ?NextValueData@BinXmlReader@@AEAAXAEAVUserBuffer@@AEAUBinXmlVariant@@K@Z; BinXmlReader::NextValueData(UserBuffer &,BinXmlVariant &,ulong)
0x1800042a4  jmp     loc_18000416B; jumptable 00000001800042BF case 2
0x1800042a9  cmp     eax, 0Dh; switch 14 cases
0x1800042ac  ja      def_1800042BF; jumptable 00000001800042BF default case, case 1
0x1800042b2  cdqe
0x1800042b4  mov     ecx, ds:(jpt_1800042BF - 180000000h)[r10+rax*4]
0x1800042bc  add     rcx, r10
0x1800042bf  jmp     rcx; switch jump
0x1800042c1  cmp     [rsi+10h], rsi; jumptable 00000001800042BF case 0
0x1800042c5  jnz     short loc_180004316
0x1800042c7  mov     rax, [rsi+48h]
0x1800042cb  cmp     [rsi+40h], rax
0x1800042cf  jz      loc_18000416B; jumptable 00000001800042BF case 2
0x1800042d5  add     rax, 0FFFFFFFFFFFFFFE0h
0x1800042d9  mov     [rsi+10h], rax
0x1800042dd  movzx   eax, r15b
0x1800042e1  jmp     loc_180004163
0x1800042e6  mov     rcx, rsi; this
0x1800042e9  call    ?NextReaderData@BinXmlReader@@AEAAXXZ; BinXmlReader::NextReaderData(void)
0x1800042ee  jmp     loc_1800040B2
0x1800042f3  test    r15b, r15b; jumptable 00000001800042BF case 12
0x1800042f6  jz      loc_18000416B; jumptable 00000001800042BF case 2
0x1800042fc  mov     rcx, rsi; this
0x1800042ff  call    ?StartTemplateInstanceToken@BinXmlReader@@AEAAXXZ; BinXmlReader::StartTemplateInstanceToken(void)
0x180004304  jmp     loc_1800040B2
0x180004309  mov     rcx, rsi; jumptable 00000001800042BF cases 3,4
0x18000430c  call    ?EndElementTag@BinXmlReader@@AEAAXXZ; BinXmlReader::EndElementTag(void)
0x180004311  jmp     loc_18000416B; jumptable 00000001800042BF case 2
0x180004316  mov     rcx, [rsi+48h]
0x18000431a  cmp     [rsi+40h], rcx
0x18000431e  jz      loc_1800047E1
0x180004324  mov     eax, [rcx-10h]
0x180004327  test    eax, eax
0x180004329  jz      loc_1800044E6
0x18000432f  mov     [rsi+10h], rsi
0x180004333  cmp     eax, [rsi+0Ch]
0x180004336  ja      loc_180004488
0x18000433c  mov     [rsi+8], eax
0x18000433f  mov     r11d, r12d
0x180004342  mov     ebx, [rcx-0Ch]
0x180004345  mov     r10d, r12d
0x180004348  sub     ebx, eax
0x18000434a  shr     ebx, 2
0x18000434d  test    ebx, ebx
0x18000434f  jz      short loc_180004386
0x180004351  mov     r8, [rsi+10h]
0x180004355  mov     r9d, [r8+8]
0x180004359  mov     eax, [r8+0Ch]
0x18000435d  sub     eax, r9d
0x180004360  cmp     eax, 4
0x180004363  jb      loc_180004488
0x180004369  mov     rax, [r8]
0x18000436c  inc     r10d
0x18000436f  mov     edx, [r9+rax]
0x180004373  lea     eax, [r9+4]
0x180004377  mov     [r8+8], eax
0x18000437b  movzx   eax, dx
0x18000437e  add     r11d, eax
0x180004381  cmp     r10d, ebx
0x180004384  jb      short loc_180004351
0x180004386  mov     rdx, [rsi+10h]
0x18000438a  cmp     [rdx], r12
0x18000438d  jz      loc_180004488
0x180004393  cmp     r11d, 10000000h
0x18000439a  ja      loc_180004488
0x1800043a0  mov     eax, [rdx+0Ch]
0x1800043a3  mov     r8d, [rdx+8]
0x1800043a7  sub     eax, r8d
0x1800043aa  cmp     r11d, eax
0x1800043ad  ja      loc_180004488
0x1800043b3  lea     eax, [r8+r11]
0x1800043b7  lea     rcx, [rsi+40h]
0x1800043bb  mov     [rdx+8], eax
0x1800043be  call    ?pop_back@?$vector@UTmplInstInfo@BinXmlReader@@V?$allocator@UTmplInstInfo@BinXmlReader@@@utl@@@utl@@QEAAXXZ; utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::pop_back(void)
0x1800043c3  mov     rax, [rsi+48h]
0x1800043c7  cmp     [rsi+40h], rax
0x1800043cb  jz      loc_18000416B; jumptable 00000001800042BF case 2
0x1800043d1  jmp     loc_1800040AD
0x1800043d6  mov     rcx, [rsi+58h]; jumptable 00000001800042BF case 6
0x1800043da  lea     rbx, [rsi+68h]
0x1800043de  mov     rdx, [rsi+10h]
0x1800043e2  test    rcx, rcx
0x1800043e5  jnz     loc_1800045DB
0x1800043eb  mov     ecx, [rdx+8]
0x1800043ee  mov     eax, [rdx+0Ch]
0x1800043f1  sub     eax, ecx
0x1800043f3  cmp     eax, 4
0x1800043f6  jb      loc_180004488
0x1800043fc  mov     rax, [rdx]
0x1800043ff  mov     ecx, [rcx+rax]
0x180004402  mov     [rbx+8], ecx
0x180004405  add     dword ptr [rdx+8], 4
0x180004409  mov     eax, [rdx+8]
0x18000440c  add     rax, [rdx]
0x18000440f  mov     [rbx], rax
0x180004412  cmp     [rdx], r12
0x180004415  jz      short loc_180004488
0x180004417  movzx   eax, word ptr [rbx+0Ah]
0x18000441b  mov     r8d, [rdx+8]
0x18000441f  lea     ecx, ds:2[rax*2]
0x180004426  mov     eax, [rdx+0Ch]
0x180004429  sub     eax, r8d
0x18000442c  cmp     ecx, eax
0x18000442e  ja      short loc_180004488
0x180004430  lea     eax, [rcx+r8]
0x180004434  mov     [rdx+8], eax
0x180004437  mov     byte ptr [rbx+0Ch], 1
0x18000443b  mov     rcx, rsi; this
0x18000443e  mov     [r14+0Ch], r13d
0x180004442  mov     [r14], rbx
0x180004445  call    ?IsNextSubstValueNull@BinXmlReader@@AEAA_NXZ; BinXmlReader::IsNextSubstValueNull(void)
0x18000444a  mov     ebx, 26h ; '&'
0x18000444f  jmp     loc_180004156
0x180004454  mov     r8, [rsi+10h]
0x180004458  mov     r9d, [r8+8]
0x18000445c  cmp     r9d, [r8+0Ch]
0x180004460  jnb     short loc_180004488
0x180004462  mov     rax, [r8]
0x180004465  movzx   ecx, byte ptr [r9+rax]
0x18000446a  lea     eax, [r9+1]
0x18000446e  mov     [r8+8], eax
0x180004472  shl     ecx, 10h
0x180004475  or      ecx, r10d
0x180004478  mov     dword ptr [r14+0Ch], 8
0x180004480  mov     [r14], ecx
0x180004483  jmp     loc_18000416B; jumptable 00000001800042BF case 2
0x180004488  call    ?ThrowUnexpectedEOFException@UserBuffer@@CAXXZ; UserBuffer::ThrowUnexpectedEOFException(void)
0x18000448e  mov     rdx, [rsi+10h]; jumptable 00000001800042BF case 5
0x180004492  mov     r8, r14; struct BinXmlVariant *
0x180004495  mov     rcx, rsi; this
0x180004498  call    ?NextValue@BinXmlReader@@AEAAXAEAVUserBuffer@@AEAUBinXmlVariant@@@Z; BinXmlReader::NextValue(UserBuffer &,BinXmlVariant &)
0x18000449d  test    r15b, r15b
0x1800044a0  jz      loc_18000416B; jumptable 00000001800042BF case 2
0x1800044a6  lea     rbx, [rsi+98h]
0x1800044ad  lea     rdi, [rsi+0A8h]
0x1800044b4  cmp     [r14+14h], r12b
0x1800044b8  jnz     short loc_18000452E
0x1800044ba  cmp     [rdi], r12d
0x1800044bd  ja      short loc_18000452E
0x1800044bf  xor     edx, edx; unsigned int
0x1800044c1  mov     rcx, rbx; this
0x1800044c4  call    ?SetCurrentIndex@WriteBuffer@@QEAAXK@Z; WriteBuffer::SetCurrentIndex(ulong)
0x1800044c9  movzx   eax, byte ptr [r14+14h]
0x1800044ce  mov     ebx, 26h ; '&'
0x1800044d3  jmp     loc_180004156
0x1800044d8  mov     r8d, r12d
0x1800044db  mov     r9d, r12d
0x1800044de  mov     edx, r12d
0x1800044e1  jmp     loc_180004254
0x1800044e6  lea     rcx, [rsi+40h]
0x1800044ea  call    ?pop_back@?$vector@UTmplInstInfo@BinXmlReader@@V?$allocator@UTmplInstInfo@BinXmlReader@@@utl@@@utl@@QEAAXXZ; utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::pop_back(void)
0x1800044ef  mov     rcx, [rsi+48h]
0x1800044f3  cmp     [rsi+40h], rcx
0x1800044f7  jnz     short loc_180004500
  ... truncated ...
```
