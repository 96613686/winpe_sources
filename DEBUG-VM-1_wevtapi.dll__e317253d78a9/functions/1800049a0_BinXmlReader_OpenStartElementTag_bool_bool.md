# BinXmlReader::OpenStartElementTag(bool,bool &)

- ea: `0x1800049a0`
- end: `0x180004da3`
- name: `?OpenStartElementTag@BinXmlReader@@AEAAX_NAEA_N@Z`
- size: `1027`
- prototype: `void __fastcall(BinXmlReader *__hidden this, bool, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180004070`

## callees

- `0x180003aa0`
- `0x1800049a0`
- `0x180013650`
- `0x18001e850`
- `0x1800231d0`
- `0x180023548`
- `0x180038fb4`
- `0x18003c010`

## pseudocode

```c
void __fastcall BinXmlReader::OpenStartElementTag(BinXmlReader *this, char a2, bool *a3)
{
  unsigned int *v3; // r9
  __int64 v7; // r10
  int v8; // edi
  __int64 v9; // rax
  __int64 v10; // r8
  unsigned int v11; // eax
  unsigned int v12; // r9d
  __int64 v13; // r10
  int v14; // r8d
  int v15; // edx
  __int64 v16; // rcx
  _OWORD *v17; // rax
  __int64 v18; // r8
  __int64 v19; // r9
  int v20; // edx
  _QWORD *v21; // r8
  __int64 v22; // rdi
  void (__fastcall ***v23)(_QWORD, __int64, _QWORD *); // rcx
  __int64 v24; // rdx
  __int64 v25; // rcx
  int v26; // r9d
  unsigned int v27; // ecx
  __int64 v28; // r8
  __int64 v29; // r9
  int v30; // edx
  unsigned int v31; // edx
  __int64 v32; // rax
  __int128 v33; // [rsp+20h] [rbp-48h] BYREF
  __int128 pExceptionObject; // [rsp+30h] [rbp-38h] BYREF
  __int64 v35; // [rsp+40h] [rbp-28h]
  int v36; // [rsp+48h] [rbp-20h]
  int v37; // [rsp+4Ch] [rbp-1Ch]
  int v38; // [rsp+50h] [rbp-18h]

  v3 = (unsigned int *)*((_QWORD *)this + 2);
  *a3 = 0;
  *(_QWORD *)((char *)&v33 + 4) = 0;
  v7 = v3[2];
  *(_QWORD *)&v33 = (unsigned int)(v7 - 1);
  if ( v3 == (unsigned int *)this )
  {
    HIDWORD(v33) = -1;
    if ( *((_BYTE *)this + 188) )
      UserBuffer::Advance((UserBuffer *)v3, 2u);
  }
  else
  {
    HIDWORD(v33) = (__int64)(*((_QWORD *)this + 9) - *((_QWORD *)this + 8)) >> 5;
    if ( v3[3] - (unsigned int)v7 < 2 )
      goto LABEL_33;
    v8 = *(unsigned __int16 *)(v7 + *(_QWORD *)v3);
    v3[2] = v7 + 2;
    if ( (_WORD)v8 != 0xFFFF )
    {
      v9 = *((_QWORD *)this + 9);
      if ( *((_QWORD *)this + 8) == v9 )
      {
        if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_2e7dc5ef0fe83399c91a1315b54063e2_Traceguids, 13);
        }
        v35 = 0;
        v36 = 13;
        v37 = -1;
        pExceptionObject = 0;
        v38 = 1174;
        throw (EvtException *)&pExceptionObject;
      }
      v10 = *((_QWORD *)this + 9);
      v11 = *(_DWORD *)(v9 - 16);
      if ( v11 )
      {
        v12 = *((_DWORD *)this + 3);
        if ( v11 > v12 )
          goto LABEL_33;
        v13 = *(_QWORD *)this;
      }
      else
      {
        v32 = *((_QWORD *)this + 3);
        v12 = *(_DWORD *)(v32 + 40LL * *(unsigned __int16 *)(v10 - 8) + 32);
        if ( v12 < 4 )
          goto LABEL_33;
        v13 = *(_QWORD *)(v32 + 40LL * *(unsigned __int16 *)(v10 - 8) + 24);
        v11 = 4;
      }
      v14 = *(_DWORD *)(v10 - 12);
      v15 = 0;
      if ( (_WORD)v8 )
      {
        while ( v12 - v11 >= 4 )
        {
          v16 = v11;
          ++v15;
          v11 += 4;
          v14 += *(unsigned __int16 *)(v16 + v13);
          if ( v15 >= v8 )
            goto LABEL_11;
        }
LABEL_33:
        UserBuffer::ThrowUnexpectedEOFException();
      }
LABEL_11:
      if ( v12 - v11 < 4 )
        goto LABEL_33;
      if ( v14 && (*(_DWORD *)(v11 + v13) & 0xFFFF0000) == 0 )
        *a3 = 1;
    }
  }
  v17 = (_OWORD *)*((_QWORD *)this + 6);
  if ( v17 == *((_OWORD **)this + 7) )
  {
    if ( !(unsigned __int8)utl::vector<BinXmlReader::ElementInfo,utl::allocator<BinXmlReader::ElementInfo>>::_PushBackOne2<BinXmlReader::ElementInfo const &>(
                             (char *)this + 40,
                             &v33) )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_2e7dc5ef0fe83399c91a1315b54063e2_Traceguids, 14);
      }
      v35 = 0;
      v36 = 14;
      v37 = -1;
      pExceptionObject = 0;
      v38 = 1283;
      throw (EvtException *)&pExceptionObject;
    }
  }
  else
  {
    *v17 = v33;
    *((_QWORD *)this + 6) += 16LL;
  }
  v18 = *((_QWORD *)this + 2);
  v19 = *(unsigned int *)(v18 + 8);
  if ( (unsigned int)(*(_DWORD *)(v18 + 12) - v19) < 4 )
    goto LABEL_33;
  v20 = *(_DWORD *)(v19 + *(_QWORD *)v18);
  *(_DWORD *)(v18 + 8) = v19 + 4;
  v21 = (_QWORD *)((char *)this + 104);
  v22 = *((_QWORD *)this + 6);
  *(_DWORD *)(v22 - 12) = v20 + *(_DWORD *)(*((_QWORD *)this + 2) + 8LL) - 1;
  v23 = (void (__fastcall ***)(_QWORD, __int64, _QWORD *))*((_QWORD *)this + 11);
  v24 = *((_QWORD *)this + 2);
  if ( v23 )
  {
    (**v23)(v23, v24, v21);
  }
  else
  {
    v25 = *(unsigned int *)(v24 + 8);
    if ( (unsigned int)(*(_DWORD *)(v24 + 12) - v25) < 4 )
      goto LABEL_33;
    *((_DWORD *)this + 28) = *(_DWORD *)(v25 + *(_QWORD *)v24);
    *(_DWORD *)(v24 + 8) += 4;
    *v21 = *(_QWORD *)v24 + *(unsigned int *)(v24 + 8);
    if ( !*(_QWORD *)v24 )
      goto LABEL_33;
    v26 = *(_DWORD *)(v24 + 8);
    v27 = 2 * *((unsigned __int16 *)this + 57) + 2;
    if ( v27 > *(_DWORD *)(v24 + 12) - v26 )
      goto LABEL_33;
    *(_DWORD *)(v24 + 8) = v27 + v26;
    *((_BYTE *)this + 116) = 1;
  }
  if ( a2 )
  {
    v28 = *((_QWORD *)this + 2);
    v29 = *(unsigned int *)(v28 + 8);
    if ( (unsigned int)(*(_DWORD *)(v28 + 12) - v29) < 4 )
      goto LABEL_33;
    v30 = *(_DWORD *)(v29 + *(_QWORD *)v28);
    *(_DWORD *)(v28 + 8) = v29 + 4;
    v31 = *(_DWORD *)(*((_QWORD *)this + 2) + 8LL) + v30;
    *(_DWORD *)(v22 - 8) = v31;
    if ( v31 > *(_DWORD *)(*((_QWORD *)this + 2) + 12LL) )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_2e7dc5ef0fe83399c91a1315b54063e2_Traceguids, 13);
      }
      v35 = 0;
      v36 = 13;
      v37 = -1;
      pExceptionObject = 0;
      v38 = 1326;
      throw (EvtException *)&pExceptionObject;
    }
  }
  else
  {
    *(_DWORD *)(v22 - 8) = *(_DWORD *)(*((_QWORD *)this + 2) + 8LL);
  }
  if ( *a3 )
    BinXmlReader::SeekToEndOfCurrentElement(this);
}

```

## disassembly

```asm
0x1800049a0  push    rbp
0x1800049a2  push    rbx
0x1800049a3  push    rsi
0x1800049a4  push    rdi
0x1800049a5  push    r14
0x1800049a7  push    r15
0x1800049a9  mov     rbp, rsp
0x1800049ac  sub     rsp, 68h
0x1800049b0  mov     r9, [rcx+10h]
0x1800049b4  xor     r15d, r15d
0x1800049b7  mov     byte ptr [r8], 0
0x1800049bb  mov     rsi, r8
0x1800049be  mov     qword ptr [rbp+var_48+4], r15
0x1800049c2  movzx   r14d, dl
0x1800049c6  mov     rbx, rcx
0x1800049c9  mov     r10d, [r9+8]
0x1800049cd  lea     eax, [r10-1]
0x1800049d1  mov     dword ptr [rbp+var_48], eax
0x1800049d4  cmp     r9, rcx
0x1800049d7  jz      loc_180004AA4
0x1800049dd  mov     rax, [rcx+48h]
0x1800049e1  sub     rax, [rcx+40h]
0x1800049e5  sar     rax, 5
0x1800049e9  mov     dword ptr [rbp+var_48+0Ch], eax
0x1800049ec  mov     eax, [r9+0Ch]
0x1800049f0  sub     eax, r10d
0x1800049f3  cmp     eax, 2
0x1800049f6  jb      loc_180004C23
0x1800049fc  mov     rax, [r9]
0x1800049ff  movzx   edi, word ptr [r10+rax]
0x180004a04  lea     eax, [r10+2]
0x180004a08  mov     [r9+8], eax
0x180004a0c  mov     eax, 0FFFFh
0x180004a11  cmp     di, ax
0x180004a14  jz      loc_180004AB8
0x180004a1a  mov     rax, [rcx+48h]
0x180004a1e  cmp     [rcx+40h], rax
0x180004a22  jz      loc_180004CF1
0x180004a28  mov     r8, rax
0x180004a2b  mov     eax, [rax-10h]
0x180004a2e  test    eax, eax
0x180004a30  jz      loc_180004C4D
0x180004a36  mov     r9d, [rcx+0Ch]
0x180004a3a  cmp     eax, r9d
0x180004a3d  ja      loc_180004C23
0x180004a43  mov     r10, [rcx]
0x180004a46  mov     r8d, [r8-0Ch]
0x180004a4a  mov     edx, r15d
0x180004a4d  cmp     r15w, di
0x180004a51  jnb     short loc_180004A81
0x180004a53  nop     dword ptr [rax+00h]
0x180004a57  nop     word ptr [rax+rax+00000000h]
0x180004a60  mov     ecx, r9d
0x180004a63  sub     ecx, eax
0x180004a65  cmp     ecx, 4
0x180004a68  jb      loc_180004C23
0x180004a6e  mov     ecx, eax
0x180004a70  inc     edx
0x180004a72  add     eax, 4
0x180004a75  movzx   ecx, word ptr [rcx+r10]
0x180004a7a  add     r8d, ecx
0x180004a7d  cmp     edx, edi
0x180004a7f  jl      short loc_180004A60
0x180004a81  sub     r9d, eax
0x180004a84  cmp     r9d, 4
0x180004a88  jb      loc_180004C23
0x180004a8e  test    r8d, r8d
0x180004a91  jz      short loc_180004AB8
0x180004a93  mov     ecx, eax
0x180004a95  test    dword ptr [rcx+r10], 0FFFF0000h
0x180004a9d  jnz     short loc_180004AB8
0x180004a9f  mov     byte ptr [rsi], 1
0x180004aa2  jmp     short loc_180004AB8
0x180004aa4  mov     dword ptr [rbp+var_48+0Ch], 0FFFFFFFFh
0x180004aab  cmp     [rcx+0BCh], r15b
0x180004ab2  jnz     loc_180004D5D
0x180004ab8  mov     rax, [rbx+30h]
0x180004abc  lea     rcx, [rbx+28h]
0x180004ac0  cmp     rax, [rcx+10h]
0x180004ac4  jz      loc_180004C74
0x180004aca  movups  xmm0, [rbp+var_48]
0x180004ace  movups  xmmword ptr [rax], xmm0
0x180004ad1  add     qword ptr [rcx+8], 10h
0x180004ad6  mov     r8, [rbx+10h]
0x180004ada  mov     r9d, [r8+8]
0x180004ade  mov     eax, [r8+0Ch]
0x180004ae2  sub     eax, r9d
0x180004ae5  cmp     eax, 4
0x180004ae8  jb      loc_180004C23
0x180004aee  mov     rax, [r8]
0x180004af1  mov     edx, [r9+rax]
0x180004af5  lea     eax, [r9+4]
0x180004af9  mov     [r8+8], eax
0x180004afd  lea     r8, [rbx+68h]
0x180004b01  mov     rax, [rbx+10h]
0x180004b05  mov     rdi, [rbx+30h]
0x180004b09  mov     eax, [rax+8]
0x180004b0c  dec     eax
0x180004b0e  add     eax, edx
0x180004b10  mov     [rdi-0Ch], eax
0x180004b13  mov     rcx, [rbx+58h]
0x180004b17  mov     rdx, [rbx+10h]
0x180004b1b  test    rcx, rcx
0x180004b1e  jnz     loc_180004C3D
0x180004b24  mov     ecx, [rdx+8]
0x180004b27  mov     eax, [rdx+0Ch]
0x180004b2a  sub     eax, ecx
0x180004b2c  cmp     eax, 4
0x180004b2f  jb      loc_180004C23
0x180004b35  mov     rax, [rdx]
0x180004b38  mov     ecx, [rcx+rax]
0x180004b3b  mov     [r8+8], ecx
0x180004b3f  add     dword ptr [rdx+8], 4
0x180004b43  mov     eax, [rdx+8]
0x180004b46  add     rax, [rdx]
0x180004b49  mov     [r8], rax
0x180004b4c  cmp     [rdx], r15
0x180004b4f  jz      loc_180004C23
0x180004b55  movzx   eax, word ptr [r8+0Ah]
0x180004b5a  mov     r9d, [rdx+8]
0x180004b5e  lea     ecx, ds:2[rax*2]
0x180004b65  mov     eax, [rdx+0Ch]
0x180004b68  sub     eax, r9d
0x180004b6b  cmp     ecx, eax
0x180004b6d  ja      loc_180004C23
0x180004b73  lea     eax, [rcx+r9]
0x180004b77  mov     [rdx+8], eax
0x180004b7a  mov     byte ptr [r8+0Ch], 1
0x180004b7f  test    r14b, r14b
0x180004b82  jnz     short loc_180004BA4
0x180004b84  mov     rax, [rbx+10h]
0x180004b88  mov     ecx, [rax+8]
0x180004b8b  mov     [rdi-8], ecx
0x180004b8e  cmp     [rsi], r15b
0x180004b91  jnz     loc_180004C29
0x180004b97  add     rsp, 68h
0x180004b9b  pop     r15
0x180004b9d  pop     r14
0x180004b9f  pop     rdi
0x180004ba0  pop     rsi
0x180004ba1  pop     rbx
0x180004ba2  pop     rbp
0x180004ba3  retn
0x180004ba4  mov     r8, [rbx+10h]
0x180004ba8  mov     r9d, [r8+8]
0x180004bac  mov     eax, [r8+0Ch]
0x180004bb0  sub     eax, r9d
0x180004bb3  cmp     eax, 4
0x180004bb6  jb      short loc_180004C23
0x180004bb8  mov     rax, [r8]
0x180004bbb  mov     edx, [r9+rax]
0x180004bbf  lea     eax, [r9+4]
0x180004bc3  mov     [r8+8], eax
0x180004bc7  mov     rax, [rbx+10h]
0x180004bcb  add     edx, [rax+8]
0x180004bce  mov     [rdi-8], edx
0x180004bd1  mov     rax, [rbx+10h]
0x180004bd5  cmp     edx, [rax+0Ch]
0x180004bd8  jbe     short loc_180004B8E
0x180004bda  mov     rcx, cs:WPP_GLOBAL_Control
0x180004be1  lea     rax, WPP_GLOBAL_Control
0x180004be8  cmp     rcx, rax
0x180004beb  jnz     loc_180004D6F
0x180004bf1  xorps   xmm0, xmm0
0x180004bf4  mov     [rbp+var_28], r15
0x180004bf8  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180004bff  mov     [rbp+var_20], 0Dh
0x180004c06  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180004c0a  mov     [rbp+var_1C], 0FFFFFFFFh
0x180004c11  movdqu  [rbp+pExceptionObject], xmm0
0x180004c16  mov     [rbp+var_18], 52Eh
0x180004c1d  call    _CxxThrowException_0
0x180004c23  call    ?ThrowUnexpectedEOFException@UserBuffer@@CAXXZ; UserBuffer::ThrowUnexpectedEOFException(void)
0x180004c29  mov     rcx, rbx; this
0x180004c2c  add     rsp, 68h
0x180004c30  pop     r15
0x180004c32  pop     r14
0x180004c34  pop     rdi
0x180004c35  pop     rsi
0x180004c36  pop     rbx
0x180004c37  pop     rbp
0x180004c38  jmp     ?SeekToEndOfCurrentElement@BinXmlReader@@QEAAXXZ; BinXmlReader::SeekToEndOfCurrentElement(void)
0x180004c3d  mov     rax, [rcx]
0x180004c40  mov     rax, [rax]
0x180004c43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c48  jmp     loc_180004B7F
0x180004c4d  movzx   eax, word ptr [r8-8]
0x180004c52  lea     rcx, [rax+rax*4]
0x180004c56  mov     rax, [rbx+18h]
0x180004c5a  mov     r9d, [rax+rcx*8+20h]
0x180004c5f  cmp     r9d, 4
0x180004c63  jb      short loc_180004C23
0x180004c65  mov     r10, [rax+rcx*8+18h]
0x180004c6a  mov     eax, 4
0x180004c6f  jmp     loc_180004A46
0x180004c74  lea     rdx, [rbp+var_48]
0x180004c78  call    ??$_PushBackOne2@AEBUElementInfo@BinXmlReader@@@?$vector@UElementInfo@BinXmlReader@@V?$allocator@UElementInfo@BinXmlReader@@@utl@@@utl@@AEAA_NAEBUElementInfo@BinXmlReader@@@Z; utl::vector<BinXmlReader::ElementInfo,utl::allocator<BinXmlReader::ElementInfo>>::_PushBackOne2<BinXmlReader::ElementInfo const &>(BinXmlReader::ElementInfo const &)
0x180004c7d  test    al, al
0x180004c7f  jnz     loc_180004AD6
0x180004c85  mov     rcx, cs:WPP_GLOBAL_Control
0x180004c8c  lea     rax, WPP_GLOBAL_Control
0x180004c93  cmp     rcx, rax
0x180004c96  jz      short loc_180004CBF
0x180004c98  test    byte ptr [rcx+1Ch], 2
0x180004c9c  jz      short loc_180004CBF
0x180004c9e  cmp     byte ptr [rcx+19h], 2
0x180004ca2  jb      short loc_180004CBF
0x180004ca4  mov     rcx, [rcx+10h]
0x180004ca8  lea     r8, WPP_2e7dc5ef0fe83399c91a1315b54063e2_Traceguids
0x180004caf  mov     edx, 21h ; '!'
0x180004cb4  mov     r9d, 0Eh
0x180004cba  call    WPP_SF_D
0x180004cbf  xorps   xmm0, xmm0
0x180004cc2  mov     [rbp+var_28], r15
0x180004cc6  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180004ccd  mov     [rbp+var_20], 0Eh
0x180004cd4  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180004cd8  mov     [rbp+var_1C], 0FFFFFFFFh
0x180004cdf  movdqu  [rbp+pExceptionObject], xmm0
0x180004ce4  mov     [rbp+var_18], 503h
0x180004ceb  call    _CxxThrowException_0
0x180004cf1  mov     rcx, cs:WPP_GLOBAL_Control
0x180004cf8  lea     rax, WPP_GLOBAL_Control
0x180004cff  cmp     rcx, rax
0x180004d02  jz      short loc_180004D2B
0x180004d04  test    byte ptr [rcx+1Ch], 2
0x180004d08  jz      short loc_180004D2B
0x180004d0a  cmp     byte ptr [rcx+19h], 2
0x180004d0e  jb      short loc_180004D2B
0x180004d10  mov     rcx, [rcx+10h]
0x180004d14  lea     r8, WPP_2e7dc5ef0fe83399c91a1315b54063e2_Traceguids
0x180004d1b  mov     edx, 20h ; ' '
0x180004d20  mov     r9d, 0Dh
0x180004d26  call    WPP_SF_D
0x180004d2b  xorps   xmm0, xmm0
0x180004d2e  mov     [rbp+var_28], r15
0x180004d32  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180004d39  mov     [rbp+var_20], 0Dh
0x180004d40  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180004d44  mov     [rbp+var_1C], 0FFFFFFFFh
0x180004d4b  movdqu  [rbp+pExceptionObject], xmm0
0x180004d50  mov     [rbp+var_18], 496h
0x180004d57  call    _CxxThrowException_0
0x180004d5d  mov     edx, 2; unsigned int
0x180004d62  mov     rcx, r9; this
0x180004d65  call    ?Advance@UserBuffer@@QEAAXK@Z; UserBuffer::Advance(ulong)
0x180004d6a  jmp     loc_180004AB8
0x180004d6f  test    byte ptr [rcx+1Ch], 2
0x180004d73  jz      loc_180004BF1
0x180004d79  cmp     byte ptr [rcx+19h], 2
0x180004d7d  jb      loc_180004BF1
0x180004d83  mov     rcx, [rcx+10h]
0x180004d87  lea     r8, WPP_2e7dc5ef0fe83399c91a1315b54063e2_Traceguids
0x180004d8e  mov     edx, 22h ; '"'
0x180004d93  mov     r9d, 0Dh
0x180004d99  call    WPP_SF_D
0x180004d9e  jmp     loc_180004BF1
```
