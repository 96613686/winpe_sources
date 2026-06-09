# FontSetBuilder::AddProperties(DWRITE_FONT_PROPERTY_ID,FontNameDictionary const &)

- ea: `0x180050ad0`
- end: `0x180050fed`
- name: `?AddProperties@FontSetBuilder@@QEAA?AU?$RangeImpl@I@@W4DWRITE_FONT_PROPERTY_ID@@AEBVFontNameDictionary@@@Z`
- size: `1309`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180051f98`

## callees

- `0x180050ad0`
- `0x180051790`
- `0x180052a20`
- `0x180075428`
- `0x18009e3b8`
- `0x18009e420`
- `0x1800aaa58`
- `0x1800aaf88`
- `0x1800ab0aa`
- `0x1800ab168`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180050f3e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180050f54`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180050f3e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180050f54`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_DWORD *__fastcall FontSetBuilder::AddProperties(_QWORD *a1, __int64 a2, int a3, unsigned int *a4)
{
  unsigned int *v4; // rdi
  _DWORD *v5; // rbp
  unsigned int v6; // esi
  _QWORD *v7; // r14
  __int64 v8; // rax
  __int64 v9; // r10
  unsigned int *v10; // r8
  unsigned __int64 v11; // r15
  unsigned __int64 v12; // rcx
  unsigned __int64 i; // rdx
  __int64 v14; // rbx
  __int64 v15; // r11
  __int64 v16; // r10
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // rcx
  unsigned __int64 v19; // rax
  unsigned __int64 v20; // rcx
  __int64 v21; // r13
  unsigned __int64 v22; // rax
  unsigned __int64 v23; // rcx
  unsigned __int64 v24; // rax
  _WORD *v25; // rbp
  __int64 v26; // rsi
  __int64 v27; // r15
  unsigned __int64 v28; // rax
  volatile signed __int32 *v29; // rax
  __int64 v30; // rdx
  volatile signed __int32 *v31; // rbx
  void *v32; // rcx
  void *v33; // rcx
  unsigned __int64 v34; // rax
  volatile signed __int32 *v35; // rax
  volatile signed __int32 *v36; // rbx
  size_t v37; // r8
  void *v38; // rcx
  void *v39; // rcx
  __int64 v41; // rbx
  int v42; // [rsp+24h] [rbp-A4h]
  unsigned int v43; // [rsp+28h] [rbp-A0h]
  int v44; // [rsp+2Ch] [rbp-9Ch]
  int v45; // [rsp+30h] [rbp-98h]
  void *Src; // [rsp+38h] [rbp-90h]
  _BYTE v47[96]; // [rsp+68h] [rbp-60h] BYREF
  _DWORD *v49; // [rsp+D8h] [rbp+10h]
  unsigned int *v51; // [rsp+E8h] [rbp+20h]

  v51 = a4;
  v49 = (_DWORD *)a2;
  v4 = a4;
  v5 = (_DWORD *)a2;
  v6 = a4[2];
  v43 = v6;
  v7 = a1 + 9;
  v8 = a1[10];
  v9 = a1[9];
  v10 = (unsigned int *)0xAAAAAAAAAAAAAAABLL;
  v11 = 0xAAAAAAAAAAAAAAABuLL * ((v8 - v9) >> 3);
  v45 = -1431655765 * ((v8 - v9) >> 3);
  v12 = 0xFFFFFFFFLL;
  if ( v11 > 0xFFFFFFFF || (v12 = (unsigned int)v11 + v6, v44 = v12, (unsigned int)v12 < (unsigned int)v11) )
LABEL_71:
    SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(v12, a2, v10, a4);
  if ( (unsigned int)v12 < v11 )
  {
    v41 = v9 + 24 * v12;
    std::_Destroy_range<std::allocator<FontSetBuilder::FontProperty>>(v41, v8);
    v7[1] = v41;
  }
  else if ( (unsigned int)v12 > v11 )
  {
    if ( (unsigned int)v12 > 0xAAAAAAAAAAAAAAABuLL * ((v7[2] - v9) >> 3) )
    {
      std::vector<FontSetBuilder::FontProperty>::_Resize_reallocate<std::_Value_init_tag>(v7);
    }
    else
    {
      for ( i = (unsigned int)v12 - v11; i; --i )
      {
        *(_OWORD *)v8 = 0;
        *(_QWORD *)(v8 + 16) = 0;
        *(_QWORD *)(v8 + 8) = &DWrite::RefString::empty_;
        *(_QWORD *)(v8 + 16) = &DWrite::RefString::empty_;
        v8 += 24;
      }
      v7[1] = v8;
    }
  }
  v14 = 0;
  v42 = 0;
  if ( v6 )
  {
    while ( 1 )
    {
      if ( (unsigned int)v14 >= v4[2] )
        FailAsExceptionPolicy<InvalidCacheDataException>::OnOutOfRange(*(_QWORD *)v4);
      a4 = (unsigned int *)(*(_QWORD *)v4 + 8 * v14);
      v15 = *((_QWORD *)v4 + 2);
      v16 = *((_QWORD *)v4 + 3);
      v12 = *a4;
      a2 = (unsigned int)v16;
      if ( v12 > (unsigned int)v16
        || (unsigned int)v16 - v12 < 4
        || (v10 = (unsigned int *)(v12 + v15), (((_BYTE)v12 + (_BYTE)v15) & 3) != 0) )
      {
LABEL_78:
        FailAsExceptionPolicy<InvalidCacheDataException>::OnOutOfRange(v15);
      }
      v17 = v12 + 4;
      if ( v12 + 4 < v12 )
        goto LABEL_71;
      if ( v17 > 0xFFFFFFFF )
        goto LABEL_71;
      v12 = (unsigned int)v17 + 1LL;
      if ( v12 < (unsigned int)v17 || v12 > 0xFFFFFFFF )
        goto LABEL_71;
      v18 = (unsigned int)v12 & 0xFFFFFFFE;
      if ( v18 > (unsigned int)v16 )
        goto LABEL_78;
      v19 = *v10;
      if ( ((unsigned int)v16 - v18) >> 1 < v19 )
        goto LABEL_78;
      v20 = v15 + v18;
      Src = (void *)v20;
      if ( (v20 & 1) != 0 )
        goto LABEL_78;
      if ( !(_DWORD)v19 )
        goto LABEL_78;
      v21 = (unsigned int)(v19 - 1);
      if ( *(_WORD *)(v20 + 2 * v21) )
        goto LABEL_78;
      v12 = a4[1];
      a2 = (unsigned int)v16;
      if ( v12 > (unsigned int)v16 )
        goto LABEL_78;
      if ( (unsigned int)v16 - v12 < 4 )
        goto LABEL_78;
      v10 = (unsigned int *)(v12 + v15);
      if ( (((_BYTE)v12 + (_BYTE)v15) & 3) != 0 )
        goto LABEL_78;
      v22 = v12 + 4;
      if ( v12 + 4 < v12 )
        goto LABEL_71;
      if ( v22 > 0xFFFFFFFF )
        goto LABEL_71;
      v12 = (unsigned int)v22 + 1LL;
      if ( v12 < (unsigned int)v22 || v12 > 0xFFFFFFFF )
        goto LABEL_71;
      v23 = (unsigned int)v12 & 0xFFFFFFFE;
      if ( v23 > (unsigned int)v16 )
        goto LABEL_78;
      v24 = *v10;
      if ( ((unsigned int)v16 - v23) >> 1 < v24 )
        goto LABEL_78;
      v25 = (_WORD *)(v15 + v23);
      if ( (((_BYTE)v15 + (_BYTE)v23) & 1) != 0 )
        goto LABEL_78;
      if ( !(_DWORD)v24 )
        goto LABEL_78;
      v26 = (unsigned int)(v24 - 1);
      if ( v25[v26] )
        goto LABEL_78;
      v27 = a1[9] + 24LL * (unsigned int)(v14 + v11);
      *(_DWORD *)v27 = a3;
      if ( (_DWORD)v24 == 1 )
      {
        v31 = (volatile signed __int32 *)&DWrite::RefString::empty_;
      }
      else
      {
        a2 = 0xFFFFFFFFLL;
        v12 = 2LL * (unsigned int)v26;
        if ( !is_mul_ok(2u, v26) )
          goto LABEL_71;
        v28 = (unsigned int)v12;
        v12 = (unsigned int)v12 + 10LL;
        if ( v12 < v28 || v12 > 0xFFFFFFFF )
          goto LABEL_71;
        v29 = (volatile signed __int32 *)operator new((unsigned int)v12);
        v31 = v29;
        *v29 = 1;
        *((_DWORD *)v29 + 1) = v26;
        if ( v25 && 2 * v26 )
        {
          v32 = (void *)(v29 + 2);
          if ( v29 == (volatile signed __int32 *)-8LL )
          {
            *(_DWORD *)_o__errno(v32, v30, v10) = 22;
            invalid_parameter_noinfo();
          }
          else
          {
            memcpy_0(v32, v25, 2 * v26);
          }
        }
        *((_WORD *)v31 + v26 + 4) = 0;
      }
      _InterlockedIncrement(v31);
      v33 = *(void **)(v27 + 8);
      if ( v33 != &DWrite::RefString::empty_ && _InterlockedExchangeAdd((volatile signed __int32 *)v33, 0xFFFFFFFF) == 1 )
        operator delete(v33);
      *(_QWORD *)(v27 + 8) = v31;
      if ( v31 != (volatile signed __int32 *)&DWrite::RefString::empty_ && _InterlockedExchangeAdd(v31, 0xFFFFFFFF) == 1 )
        operator delete((void *)v31);
      if ( (_DWORD)v21 )
      {
        a2 = 0xFFFFFFFFLL;
        v12 = 2LL * (unsigned int)v21;
        if ( !is_mul_ok(2u, v21) )
          goto LABEL_71;
        v34 = (unsigned int)v12;
        v12 = (unsigned int)v12 + 10LL;
        if ( v12 < v34 || v12 > 0xFFFFFFFF )
          goto LABEL_71;
        v35 = (volatile signed __int32 *)operator new((unsigned int)v12);
        v36 = v35;
        *v35 = 1;
        *((_DWORD *)v35 + 1) = v21;
        if ( Src )
        {
          v37 = 2 * v21;
          if ( 2 * v21 )
          {
            v38 = (void *)(v35 + 2);
            if ( v35 == (volatile signed __int32 *)-8LL )
            {
              *(_DWORD *)_o__errno(v38, Src, v37) = 22;
              invalid_parameter_noinfo();
            }
            else
            {
              memcpy_0(v38, Src, v37);
            }
          }
        }
        *((_WORD *)v36 + v21 + 4) = 0;
      }
      else
      {
        v36 = (volatile signed __int32 *)&DWrite::RefString::empty_;
      }
      _InterlockedIncrement(v36);
      v39 = *(void **)(v27 + 16);
      if ( v39 != &DWrite::RefString::empty_ && _InterlockedExchangeAdd((volatile signed __int32 *)v39, 0xFFFFFFFF) == 1 )
        operator delete(v39);
      *(_QWORD *)(v27 + 16) = v36;
      if ( v36 != (volatile signed __int32 *)&DWrite::RefString::empty_ && _InterlockedExchangeAdd(v36, 0xFFFFFFFF) == 1 )
        operator delete((void *)v36);
      if ( a3 == 6 )
        std::_Tree<std::_Tset_traits<DWrite::RefString,std::less<DWrite::RefString>,std::allocator<DWrite::RefString>,0>>::_Emplace<DWrite::RefString const &>(
          a1 + 12,
          (__int64)v47,
          (volatile signed __int32 **)(v27 + 8));
      v14 = (unsigned int)(v42 + 1);
      v42 = v14;
      LODWORD(v11) = v45;
      if ( (unsigned int)v14 >= v43 )
        break;
      v4 = v51;
    }
    v5 = v49;
  }
  *v5 = v11;
  v5[1] = v44;
  return v5;
}

```

## disassembly

```asm
0x180050ad0  mov     [rsp+arg_18], r9
0x180050ad5  mov     [rsp+arg_10], r8d
0x180050ada  mov     [rsp+arg_8], rdx
0x180050adf  mov     [rsp+arg_0], rcx
0x180050ae4  push    rbx
0x180050ae5  push    rbp
0x180050ae6  push    rsi
0x180050ae7  push    rdi
0x180050ae8  push    r12
0x180050aea  push    r13
0x180050aec  push    r14
0x180050aee  push    r15
0x180050af0  sub     rsp, 88h
0x180050af7  mov     rdi, r9
0x180050afa  mov     rbp, rdx
0x180050afd  mov     esi, [r9+8]
0x180050b01  mov     [rsp+0C8h+var_A0], esi
0x180050b05  lea     r14, [rcx+48h]
0x180050b09  mov     rax, [r14+8]
0x180050b0d  mov     r10, [r14]
0x180050b10  mov     r15, rax
0x180050b13  sub     r15, r10
0x180050b16  sar     r15, 3
0x180050b1a  mov     r8, 0AAAAAAAAAAAAAAABh
0x180050b24  imul    r15, r8
0x180050b28  mov     [rsp+0C8h+var_98], r15
0x180050b2d  mov     ecx, 0FFFFFFFFh
0x180050b32  cmp     r15, rcx
0x180050b35  ja      loc_180050F38
0x180050b3b  lea     ecx, [r15+rsi]
0x180050b3f  mov     [rsp+0C8h+var_9C], ecx
0x180050b43  cmp     ecx, r15d
0x180050b46  jb      loc_180050F38
0x180050b4c  mov     edx, ecx
0x180050b4e  lea     r12, ?empty_@RefString@DWrite@@0UData@12@A; DWrite::RefString::Data DWrite::RefString::empty_
0x180050b55  cmp     rdx, r15
0x180050b58  jb      loc_180050FC8
0x180050b5e  jbe     short loc_180050BBD
0x180050b60  mov     rcx, [r14+10h]
0x180050b64  sub     rcx, r10
0x180050b67  sar     rcx, 3
0x180050b6b  imul    rcx, r8
0x180050b6f  cmp     rdx, rcx
0x180050b72  ja      loc_180050FBB
0x180050b78  sub     rdx, r15
0x180050b7b  mov     [rsp+0C8h+var_88], rax
0x180050b80  mov     [rsp+0C8h+var_80], rax
0x180050b85  mov     [rsp+0C8h+var_78], r14
0x180050b8a  jz      short loc_180050BB4
0x180050b8c  mov     [rsp+0C8h+Src], rax
0x180050b91  xorps   xmm0, xmm0
0x180050b94  xor     ecx, ecx
0x180050b96  movups  xmmword ptr [rax], xmm0
0x180050b99  mov     [rax+10h], rcx
0x180050b9d  mov     [rax+8], r12
0x180050ba1  mov     [rax+10h], r12
0x180050ba5  add     rax, 18h
0x180050ba9  mov     [rsp+0C8h+var_80], rax
0x180050bae  sub     rdx, 1
0x180050bb2  jnz     short loc_180050B8C
0x180050bb4  mov     [rsp+0C8h+var_88], rax
0x180050bb9  mov     [r14+8], rax
0x180050bbd  xor     ebx, ebx
0x180050bbf  mov     [rsp+0C8h+var_A4], ebx
0x180050bc3  test    esi, esi
0x180050bc5  jz      loc_180050F72
0x180050bcb  mov     esi, 0FFFFFFFEh
0x180050bd0  mov     rdx, [rdi]
0x180050bd3  cmp     ebx, [rdi+8]
0x180050bd6  jnb     loc_180050FE4
0x180050bdc  lea     r9, [rdx+rbx*8]
0x180050be0  mov     r11, [rdi+10h]
0x180050be4  mov     r10, [rdi+18h]
0x180050be8  mov     ecx, [r9]
0x180050beb  mov     edx, r10d
0x180050bee  cmp     rcx, rdx
0x180050bf1  ja      loc_180050FB2
0x180050bf7  mov     eax, edx
0x180050bf9  sub     rax, rcx
0x180050bfc  cmp     rax, 4
0x180050c00  jb      loc_180050FB2
0x180050c06  lea     r8, [rcx+r11]
0x180050c0a  test    r8b, 3
0x180050c0e  jnz     loc_180050FB2
0x180050c14  lea     rax, [rcx+4]
0x180050c18  cmp     rax, rcx
0x180050c1b  jb      loc_180050F38
0x180050c21  mov     edi, 0FFFFFFFFh
0x180050c26  cmp     rax, rdi
0x180050c29  ja      loc_180050F38
0x180050c2f  mov     eax, eax
0x180050c31  lea     rcx, [rax+1]
0x180050c35  cmp     rcx, rax
0x180050c38  jb      loc_180050F38
0x180050c3e  cmp     rcx, rdi
0x180050c41  ja      loc_180050F38
0x180050c47  and     rcx, rsi
0x180050c4a  cmp     rcx, rdx
0x180050c4d  ja      loc_180050FB2
0x180050c53  mov     eax, [r8]
0x180050c56  sub     rdx, rcx
0x180050c59  shr     rdx, 1
0x180050c5c  cmp     rdx, rax
0x180050c5f  jb      loc_180050FB2
0x180050c65  add     rcx, r11
0x180050c68  mov     [rsp+0C8h+Src], rcx
0x180050c6d  test    cl, 1
0x180050c70  jnz     loc_180050FB2
0x180050c76  test    eax, eax
0x180050c78  jz      loc_180050FB2
0x180050c7e  lea     r13d, [rax-1]
0x180050c82  mov     r12d, r13d
0x180050c85  cmp     word ptr [rcx+r13*2], 0
0x180050c8b  jnz     loc_180050FB2
0x180050c91  mov     ecx, [r9+4]
0x180050c95  mov     edx, r10d
0x180050c98  cmp     rcx, rdx
0x180050c9b  ja      loc_180050FB2
0x180050ca1  mov     eax, edx
0x180050ca3  sub     rax, rcx
0x180050ca6  cmp     rax, 4
0x180050caa  jb      loc_180050FB2
0x180050cb0  lea     r8, [rcx+r11]
0x180050cb4  test    r8b, 3
0x180050cb8  jnz     loc_180050FB2
0x180050cbe  lea     rax, [rcx+4]
0x180050cc2  cmp     rax, rcx
0x180050cc5  jb      loc_180050F38
0x180050ccb  cmp     rax, rdi
0x180050cce  ja      loc_180050F38
0x180050cd4  mov     eax, eax
0x180050cd6  lea     rcx, [rax+1]
0x180050cda  cmp     rcx, rax
0x180050cdd  jb      loc_180050F38
0x180050ce3  cmp     rcx, rdi
0x180050ce6  ja      loc_180050F38
0x180050cec  and     rcx, rsi
0x180050cef  cmp     rcx, rdx
0x180050cf2  ja      loc_180050FB2
0x180050cf8  mov     eax, [r8]
0x180050cfb  sub     rdx, rcx
0x180050cfe  shr     rdx, 1
0x180050d01  cmp     rdx, rax
0x180050d04  jb      loc_180050FB2
0x180050d0a  lea     rbp, [r11+rcx]
0x180050d0e  test    bpl, 1
0x180050d12  jnz     loc_180050FB2
0x180050d18  test    eax, eax
0x180050d1a  jz      loc_180050FB2
0x180050d20  lea     esi, [rax-1]
0x180050d23  mov     edi, esi
0x180050d25  lea     r14, [rsi+rsi]
0x180050d29  cmp     word ptr [r14+rbp], 0
0x180050d2f  jnz     loc_180050FB2
0x180050d35  lea     eax, [rbx+r15]
0x180050d39  lea     rdx, [rax+rax*2]
0x180050d3d  mov     rax, [rsp+0C8h+arg_0]
0x180050d45  mov     rax, [rax+48h]
0x180050d49  lea     r15, [rax+rdx*8]
0x180050d4d  mov     eax, [rsp+0C8h+arg_10]
0x180050d54  mov     [r15], eax
0x180050d57  test    esi, esi
0x180050d59  jz      loc_180050F94
0x180050d5f  mov     edx, 0FFFFFFFFh
0x180050d64  cmp     rdi, rdx
0x180050d67  ja      loc_180050F38
0x180050d6d  mov     ecx, esi
0x180050d6f  add     rcx, rcx
0x180050d72  mov     rax, rcx
0x180050d75  shr     rax, 20h
0x180050d79  test    eax, eax
0x180050d7b  jnz     loc_180050F38
0x180050d81  mov     eax, ecx
0x180050d83  lea     rcx, [rax+0Ah]
0x180050d87  cmp     rcx, rax
0x180050d8a  jb      loc_180050F38
0x180050d90  cmp     rcx, rdx
0x180050d93  ja      loc_180050F38
0x180050d99  mov     ecx, ecx; Size
0x180050d9b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180050da0  mov     rbx, rax
0x180050da3  mov     dword ptr [rax], 1
0x180050da9  mov     [rax+4], esi
0x180050dac  test    rbp, rbp
0x180050daf  jz      short loc_180050DCE
0x180050db1  test    r14, r14
0x180050db4  jz      short loc_180050DCE
0x180050db6  lea     rcx, [rax+8]; void *
0x180050dba  test    rcx, rcx
0x180050dbd  jz      loc_180050F3E
0x180050dc3  mov     r8, r14; Size
0x180050dc6  mov     rdx, rbp; Src
0x180050dc9  call    memcpy_0
0x180050dce  xor     eax, eax
0x180050dd0  mov     [rbx+rsi*2+8], ax
0x180050dd5  lea     rsi, ?empty_@RefString@DWrite@@0UData@12@A; DWrite::RefString::Data DWrite::RefString::empty_
0x180050ddc  mov     [rsp+0C8h+var_70], rbx
0x180050de1  lock inc dword ptr [rbx]
0x180050de4  mov     rcx, [r15+8]; Block
0x180050de8  cmp     rcx, rsi
0x180050deb  jz      short loc_180050E00
0x180050ded  mov     eax, 0FFFFFFFFh
0x180050df2  lock xadd [rcx], eax
0x180050df6  cmp     eax, 1
0x180050df9  jnz     short loc_180050E00
0x180050dfb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180050e00  mov     [r15+8], rbx
0x180050e04  cmp     rbx, rsi
0x180050e07  jz      short loc_180050E1F
0x180050e09  mov     eax, 0FFFFFFFFh
0x180050e0e  lock xadd [rbx], eax
0x180050e12  cmp     eax, 1
0x180050e15  jnz     short loc_180050E1F
0x180050e17  mov     rcx, rbx; Block
0x180050e1a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180050e1f  test    r13d, r13d
0x180050e22  jz      loc_180050FA3
0x180050e28  mov     edx, 0FFFFFFFFh
0x180050e2d  cmp     r12, rdx
0x180050e30  ja      loc_180050F38
0x180050e36  mov     ecx, r13d
0x180050e39  add     rcx, rcx
0x180050e3c  mov     rax, rcx
0x180050e3f  shr     rax, 20h
0x180050e43  test    eax, eax
0x180050e45  jnz     loc_180050F38
0x180050e4b  mov     eax, ecx
0x180050e4d  lea     rcx, [rax+0Ah]
0x180050e51  cmp     rcx, rax
0x180050e54  jb      loc_180050F38
0x180050e5a  cmp     rcx, rdx
0x180050e5d  ja      loc_180050F38
0x180050e63  mov     ecx, ecx; Size
0x180050e65  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180050e6a  mov     rbx, rax
0x180050e6d  mov     dword ptr [rax], 1
0x180050e73  mov     [rax+4], r13d
0x180050e77  mov     rdx, [rsp+0C8h+Src]; Src
0x180050e7c  test    rdx, rdx
0x180050e7f  jz      short loc_180050EA0
0x180050e81  lea     r8, ds:0[r13*2]; Size
0x180050e89  test    r8, r8
0x180050e8c  jz      short loc_180050EA0
0x180050e8e  lea     rcx, [rax+8]; void *
0x180050e92  test    rcx, rcx
0x180050e95  jz      loc_180050F54
0x180050e9b  call    memcpy_0
0x180050ea0  xor     eax, eax
0x180050ea2  mov     [rbx+r13*2+8], ax
0x180050ea8  lea     r12, ?empty_@RefString@DWrite@@0UData@12@A; DWrite::RefString::Data DWrite::RefString::empty_
0x180050eaf  mov     [rsp+0C8h+var_68], rbx
0x180050eb4  lock inc dword ptr [rbx]
0x180050eb7  mov     rcx, [r15+10h]; Block
0x180050ebb  cmp     rcx, r12
0x180050ebe  jz      short loc_180050ED3
0x180050ec0  mov     eax, 0FFFFFFFFh
0x180050ec5  lock xadd [rcx], eax
0x180050ec9  cmp     eax, 1
0x180050ecc  jnz     short loc_180050ED3
0x180050ece  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180050ed3  mov     [r15+10h], rbx
0x180050ed7  cmp     rbx, r12
0x180050eda  jz      short loc_180050EF2
0x180050edc  mov     eax, 0FFFFFFFFh
0x180050ee1  lock xadd [rbx], eax
0x180050ee5  cmp     eax, 1
0x180050ee8  jnz     short loc_180050EF2
0x180050eea  mov     rcx, rbx; Block
0x180050eed  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180050ef2  cmp     [rsp+0C8h+arg_10], 6
0x180050efa  jnz     short loc_180050F16
0x180050efc  mov     rcx, [rsp+0C8h+arg_0]
0x180050f04  add     rcx, 60h ; '`'
0x180050f08  lea     r8, [r15+8]
0x180050f0c  lea     rdx, [rsp+0C8h+var_60]
0x180050f11  call    ??$_Emplace@AEBVRefString@DWrite@@@?$_Tree@V?$_Tset_traits@VRefString@DWrite@@U?$less@VRefString@DWrite@@@std@@V?$allocator@VRefString@DWrite@@@4@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@VRefString@DWrite@@PEAX@std@@_N@1@AEBVRefString@DWrite@@@Z; std::_Tree<std::_Tset_traits<DWrite::RefString,std::less<DWrite::RefString>,std::allocator<DWrite::RefString>,0>>::_Emplace<DWrite::RefString const &>(DWrite::RefString const &)
0x180050f16  mov     ebx, [rsp+0C8h+var_A4]
0x180050f1a  inc     ebx
0x180050f1c  mov     [rsp+0C8h+var_A4], ebx
0x180050f20  mov     r15, [rsp+0C8h+var_98]
0x180050f25  cmp     ebx, [rsp+0C8h+var_A0]
0x180050f29  jnb     short loc_180050F6A
0x180050f2b  mov     rdi, [rsp+0C8h+arg_18]
0x180050f33  jmp     loc_180050BCB
0x180050f38  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VException@@@@SAXXZ; SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(void)
0x180050f3e  call    cs:__imp__o__errno
0x180050f44  mov     dword ptr [rax], 16h
0x180050f4a  call    _invalid_parameter_noinfo
0x180050f4f  jmp     loc_180050DCE
0x180050f54  call    cs:__imp__o__errno
0x180050f5a  mov     dword ptr [rax], 16h
0x180050f60  call    _invalid_parameter_noinfo
0x180050f65  jmp     loc_180050EA0
0x180050f6a  mov     rbp, [rsp+0C8h+arg_8]
0x180050f72  mov     [rbp+0], r15d
0x180050f76  mov     eax, [rsp+0C8h+var_9C]
0x180050f7a  mov     [rbp+4], eax
0x180050f7d  mov     rax, rbp
0x180050f80  add     rsp, 88h
0x180050f87  pop     r15
  ... truncated ...
```
