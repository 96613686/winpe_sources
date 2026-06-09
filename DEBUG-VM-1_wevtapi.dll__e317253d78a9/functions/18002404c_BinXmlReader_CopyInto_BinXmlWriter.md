# BinXmlReader::CopyInto(BinXmlWriter &)

- ea: `0x18002404c`
- end: `0x180024331`
- name: `?CopyInto@BinXmlReader@@QEAAXAEAVBinXmlWriter@@@Z`
- size: `741`
- prototype: `void(BinXmlReader *__hidden this, struct BinXmlWriter *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800303fc`
- `0x1800355b8`

## callees

- `0x180003780`
- `0x180008b20`
- `0x18002404c`
- `0x180024338`
- `0x180024388`
- `0x1800243cc`
- `0x1800249f0`
- `0x18002fd5c`

## pseudocode

```c
void __fastcall BinXmlReader::CopyInto(BinXmlReader *this, WriteBuffer **a2)
{
  WriteBuffer *v2; // rdi
  int v4; // eax
  unsigned int v6; // r14d
  WriteBuffer *v7; // rax
  __int64 **v8; // rax
  __int64 *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rax
  unsigned int v13; // r15d
  int v14; // r12d
  __int64 *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rax
  __int64 v19; // rdx
  __int64 *v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // rdx
  unsigned int v24; // ebx
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 *v28; // r8
  __int64 v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // rax
  _BYTE v33[4]; // [rsp+20h] [rbp-50h] BYREF
  int v34; // [rsp+24h] [rbp-4Ch] BYREF
  __int64 v35; // [rsp+28h] [rbp-48h] BYREF
  int v36; // [rsp+30h] [rbp-40h]
  int v37; // [rsp+34h] [rbp-3Ch]
  __int128 v38; // [rsp+38h] [rbp-38h] BYREF
  __int128 v39; // [rsp+48h] [rbp-28h]
  __int64 v40; // [rsp+58h] [rbp-18h]
  WriteBuffer *v41; // [rsp+60h] [rbp-10h]

  v2 = *a2;
  v4 = *((_DWORD *)this + 46);
  v6 = *((_DWORD *)*a2 + 4);
  if ( v4 )
  {
    WriteBuffer::SetCurrentIndex(v2, v4 + v6);
    WriteBuffer::SetCurrentIndex(v2, v6);
  }
  if ( *((_BYTE *)this + 189) )
  {
    v40 = *((_QWORD *)this + 11);
    v7 = a2[1];
    v38 = 0;
    v41 = v7;
    v8 = (__int64 **)*((_QWORD *)this + 3);
    v39 = 0;
    v33[0] = 0;
    v9 = *v8;
    v10 = **v8;
    v11 = (*v8)[1];
    *(_QWORD *)&v39 = (*v8)[2];
    v12 = v9[3];
    *(_QWORD *)&v38 = v10;
    *((_QWORD *)&v39 + 1) = v12;
    *((_QWORD *)&v38 + 1) = v11;
    BinXmlWriter::CopyTemplate((BinXmlWriter *)a2, (struct BinXmlTemplate *)&v38);
    WriteBuffer::Write(
      v2,
      *(const void **)(*((_QWORD *)this + 3) + 24LL),
      *(_DWORD *)(*((_QWORD *)this + 3) + 32LL) - 4);
    v13 = *((_DWORD *)v2 + 4);
    WriteBuffer::SetCurrentIndex(v2, v13 + 4);
    WriteBuffer::Write(v2, *(const void **)(*((_QWORD *)this + 3) + 8LL), *(_DWORD *)(*((_QWORD *)this + 3) + 16LL));
    v14 = *((_DWORD *)v2 + 4);
    v15 = *(__int64 **)(*((_QWORD *)this + 3) + 40LL);
    v16 = *v15;
    v17 = v15[1];
    *(_QWORD *)&v39 = v15[2];
    v18 = v15[3];
    *(_QWORD *)&v38 = v16;
    *((_QWORD *)&v39 + 1) = v18;
    *((_QWORD *)&v38 + 1) = v17;
    BinXmlWriter::CopyTemplate((BinXmlWriter *)a2, (struct BinXmlTemplate *)&v38);
    WriteBuffer::Write(v2, *(const void **)(*((_QWORD *)this + 3) + 64LL), *(_DWORD *)(*((_QWORD *)this + 3) + 72LL));
    v19 = *((_QWORD *)this + 3);
    if ( *(_QWORD *)(v19 + 56) )
      WriteBuffer::Write(v2, *(const void **)(v19 + 48), *(_DWORD *)(v19 + 56));
    if ( *((_DWORD *)this + 8) == 3 )
    {
      v20 = *(__int64 **)(*((_QWORD *)this + 3) + 80LL);
      v21 = *v20;
      v22 = v20[1];
      v39 = *((_OWORD *)v20 + 1);
      *(_QWORD *)&v38 = v21;
      *((_QWORD *)&v38 + 1) = v22;
      BinXmlWriter::CopyTemplate((BinXmlWriter *)a2, (struct BinXmlTemplate *)&v38);
      WriteBuffer::Write(
        v2,
        *(const void **)(*((_QWORD *)this + 3) + 104LL),
        *(_DWORD *)(*((_QWORD *)this + 3) + 112LL));
      v23 = *((_QWORD *)this + 3);
      if ( *(_QWORD *)(v23 + 96) )
        WriteBuffer::Write(v2, *(const void **)(v23 + 88), *(_DWORD *)(v23 + 96));
    }
    WriteBuffer::Write(v2, v33, 1u);
    v24 = *((_DWORD *)v2 + 4);
    v34 = (v24 - v14) | 0x210000;
    WriteBuffer::SetCurrentIndex(v2, v13);
    WriteBuffer::Write(v2, &v34, 4u);
    WriteBuffer::SetCurrentIndex(v2, v24);
    WriteBuffer::Write(v2, v33, 1u);
  }
  else
  {
    v25 = *((unsigned int *)this + 9);
    v26 = *((_QWORD *)this + 3);
    v27 = 5 * v25;
    v28 = *(__int64 **)(v26 + 40 * v25);
    if ( v28 && *(_QWORD *)(v26 + 40 * v25 + 16) )
    {
      v29 = *(_QWORD *)(v26 + 40 * v25 + 24);
      v38 = 0;
      v35 = v29;
      LODWORD(v29) = *(_DWORD *)(v26 + 8 * v27 + 32);
      v39 = 0;
      v37 = v29;
      v40 = *((_QWORD *)this + 11);
      v41 = a2[1];
      v30 = *v28;
      v31 = v28[1];
      *(_QWORD *)&v39 = v28[2];
      v32 = v28[3];
      *(_QWORD *)&v38 = v30;
      *((_QWORD *)&v38 + 1) = v31;
      v36 = 0;
      *((_QWORD *)&v39 + 1) = v32;
      BinXmlReader::CopyTemplateInstanceInto(
        this,
        (struct BinXmlTemplate *)&v38,
        (struct UserBuffer *)&v35,
        (struct BinXmlWriter *)a2);
      BinXmlWriter::EndOfFile((BinXmlWriter *)a2);
    }
    else
    {
      BinXmlReader::InternalCopyInto(this, (struct BinXmlWriter *)a2);
    }
  }
  *((_DWORD *)this + 46) = *((_DWORD *)v2 + 4) - v6;
}

```

## disassembly

```asm
0x18002404c  mov     [rsp-28h+arg_10], rbx
0x180024051  mov     [rsp-28h+arg_18], rsi
0x180024056  push    rbp
0x180024057  push    rdi
0x180024058  push    r12
0x18002405a  push    r14
0x18002405c  push    r15
0x18002405e  mov     rbp, rsp
0x180024061  sub     rsp, 70h
0x180024065  mov     rax, cs:__security_cookie
0x18002406c  xor     rax, rsp
0x18002406f  mov     [rbp+var_8], rax
0x180024073  mov     rdi, [rdx]
0x180024076  mov     rbx, rdx
0x180024079  mov     eax, [rcx+0B8h]
0x18002407f  mov     rsi, rcx
0x180024082  mov     r14d, [rdi+10h]
0x180024086  test    eax, eax
0x180024088  jz      short loc_1800240A1
0x18002408a  lea     edx, [rax+r14]; unsigned int
0x18002408e  mov     rcx, rdi; this
0x180024091  call    ?SetCurrentIndex@WriteBuffer@@QEAAXK@Z; WriteBuffer::SetCurrentIndex(ulong)
0x180024096  mov     edx, r14d; unsigned int
0x180024099  mov     rcx, rdi; this
0x18002409c  call    ?SetCurrentIndex@WriteBuffer@@QEAAXK@Z; WriteBuffer::SetCurrentIndex(ulong)
0x1800240a1  cmp     byte ptr [rsi+0BDh], 0
0x1800240a8  jz      loc_18002426A
0x1800240ae  mov     rax, [rsi+58h]
0x1800240b2  xorps   xmm0, xmm0
0x1800240b5  mov     [rbp+var_18], rax
0x1800240b9  mov     rax, [rbx+8]
0x1800240bd  movdqu  [rbp+var_38], xmm0
0x1800240c2  mov     [rbp+var_10], rax
0x1800240c6  mov     rax, [rsi+18h]
0x1800240ca  movups  [rbp+var_28], xmm0
0x1800240ce  mov     [rbp+var_50], 0
0x1800240d2  mov     rcx, [rax]
0x1800240d5  mov     rax, [rcx+10h]
0x1800240d9  mov     rdx, [rcx]
0x1800240dc  mov     r8, [rcx+8]
0x1800240e0  mov     qword ptr [rbp+var_28], rax
0x1800240e4  mov     rax, [rcx+18h]
0x1800240e8  mov     rcx, rbx; this
0x1800240eb  mov     qword ptr [rbp+var_38], rdx
0x1800240ef  lea     rdx, [rbp+var_38]; struct BinXmlTemplate *
0x1800240f3  mov     qword ptr [rbp+var_28+8], rax
0x1800240f7  mov     qword ptr [rbp+var_38+8], r8
0x1800240fb  call    ?CopyTemplate@BinXmlWriter@@QEAAXPEAVBinXmlTemplate@@@Z; BinXmlWriter::CopyTemplate(BinXmlTemplate *)
0x180024100  mov     rdx, [rsi+18h]
0x180024104  mov     rcx, rdi; this
0x180024107  mov     r8d, [rdx+20h]
0x18002410b  mov     rdx, [rdx+18h]; void *
0x18002410f  sub     r8d, 4; unsigned int
0x180024113  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x180024118  mov     r15d, [rdi+10h]
0x18002411c  mov     rcx, rdi; this
0x18002411f  lea     edx, [r15+4]; unsigned int
0x180024123  call    ?SetCurrentIndex@WriteBuffer@@QEAAXK@Z; WriteBuffer::SetCurrentIndex(ulong)
0x180024128  mov     rdx, [rsi+18h]
0x18002412c  mov     rcx, rdi; this
0x18002412f  mov     r8d, [rdx+10h]; unsigned int
0x180024133  mov     rdx, [rdx+8]; void *
0x180024137  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x18002413c  mov     rax, [rsi+18h]
0x180024140  mov     r12d, [rdi+10h]
0x180024144  mov     rcx, [rax+28h]
0x180024148  mov     rax, [rcx+10h]
0x18002414c  mov     rdx, [rcx]
0x18002414f  mov     r8, [rcx+8]
0x180024153  mov     qword ptr [rbp+var_28], rax
0x180024157  mov     rax, [rcx+18h]
0x18002415b  mov     rcx, rbx; this
0x18002415e  mov     qword ptr [rbp+var_38], rdx
0x180024162  lea     rdx, [rbp+var_38]; struct BinXmlTemplate *
0x180024166  mov     qword ptr [rbp+var_28+8], rax
0x18002416a  mov     qword ptr [rbp+var_38+8], r8
0x18002416e  call    ?CopyTemplate@BinXmlWriter@@QEAAXPEAVBinXmlTemplate@@@Z; BinXmlWriter::CopyTemplate(BinXmlTemplate *)
0x180024173  mov     rdx, [rsi+18h]
0x180024177  mov     rcx, rdi; this
0x18002417a  mov     r8d, [rdx+48h]; unsigned int
0x18002417e  mov     rdx, [rdx+40h]; void *
0x180024182  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x180024187  mov     rdx, [rsi+18h]
0x18002418b  cmp     qword ptr [rdx+38h], 0
0x180024190  jz      short loc_1800241A2
0x180024192  mov     r8d, [rdx+38h]; unsigned int
0x180024196  mov     rcx, rdi; this
0x180024199  mov     rdx, [rdx+30h]; void *
0x18002419d  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x1800241a2  cmp     dword ptr [rsi+20h], 3
0x1800241a6  jnz     short loc_18002420A
0x1800241a8  mov     rax, [rsi+18h]
0x1800241ac  mov     rcx, rbx; this
0x1800241af  mov     rdx, [rax+50h]
0x1800241b3  mov     rax, [rdx+10h]
0x1800241b7  mov     r8, [rdx]
0x1800241ba  mov     r9, [rdx+8]
0x1800241be  mov     qword ptr [rbp+var_28], rax
0x1800241c2  mov     rax, [rdx+18h]
0x1800241c6  lea     rdx, [rbp+var_38]; struct BinXmlTemplate *
0x1800241ca  mov     qword ptr [rbp+var_28+8], rax
0x1800241ce  mov     qword ptr [rbp+var_38], r8
0x1800241d2  mov     qword ptr [rbp+var_38+8], r9
0x1800241d6  call    ?CopyTemplate@BinXmlWriter@@QEAAXPEAVBinXmlTemplate@@@Z; BinXmlWriter::CopyTemplate(BinXmlTemplate *)
0x1800241db  mov     rdx, [rsi+18h]
0x1800241df  mov     rcx, rdi; this
0x1800241e2  mov     r8d, [rdx+70h]; unsigned int
0x1800241e6  mov     rdx, [rdx+68h]; void *
0x1800241ea  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x1800241ef  mov     rdx, [rsi+18h]
0x1800241f3  cmp     qword ptr [rdx+60h], 0
0x1800241f8  jz      short loc_18002420A
0x1800241fa  mov     r8d, [rdx+60h]; unsigned int
0x1800241fe  mov     rcx, rdi; this
0x180024201  mov     rdx, [rdx+58h]; void *
0x180024205  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x18002420a  mov     r8d, 1; unsigned int
0x180024210  lea     rdx, [rbp+var_50]; void *
0x180024214  mov     rcx, rdi; this
0x180024217  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x18002421c  mov     ebx, [rdi+10h]
0x18002421f  mov     edx, r15d; unsigned int
0x180024222  mov     eax, ebx
0x180024224  mov     rcx, rdi; this
0x180024227  sub     eax, r12d
0x18002422a  or      eax, 210000h
0x18002422f  mov     [rbp+var_4C], eax
0x180024232  call    ?SetCurrentIndex@WriteBuffer@@QEAAXK@Z; WriteBuffer::SetCurrentIndex(ulong)
0x180024237  mov     r8d, 4; unsigned int
0x18002423d  lea     rdx, [rbp+var_4C]; void *
0x180024241  mov     rcx, rdi; this
0x180024244  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x180024249  mov     edx, ebx; unsigned int
0x18002424b  mov     rcx, rdi; this
0x18002424e  call    ?SetCurrentIndex@WriteBuffer@@QEAAXK@Z; WriteBuffer::SetCurrentIndex(ulong)
0x180024253  mov     r8d, 1; unsigned int
0x180024259  lea     rdx, [rbp+var_50]; void *
0x18002425d  mov     rcx, rdi; this
0x180024260  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x180024265  jmp     loc_180024300
0x18002426a  mov     eax, [rsi+24h]
0x18002426d  mov     rdx, [rsi+18h]
0x180024271  lea     rcx, [rax+rax*4]
0x180024275  mov     r8, [rdx+rcx*8]
0x180024279  test    r8, r8
0x18002427c  jz      short loc_1800242F5
0x18002427e  cmp     qword ptr [rdx+rcx*8+10h], 0
0x180024284  jz      short loc_1800242F5
0x180024286  mov     rax, [rdx+rcx*8+18h]
0x18002428b  xorps   xmm0, xmm0
0x18002428e  movdqu  [rbp+var_38], xmm0
0x180024293  mov     [rbp+var_48], rax
0x180024297  mov     r9, rbx; struct BinXmlWriter *
0x18002429a  mov     eax, [rdx+rcx*8+20h]
0x18002429e  movups  [rbp+var_28], xmm0
0x1800242a2  mov     [rbp+var_3C], eax
0x1800242a5  mov     rax, [rsi+58h]
0x1800242a9  mov     [rbp+var_18], rax
0x1800242ad  mov     rax, [rbx+8]
0x1800242b1  mov     [rbp+var_10], rax
0x1800242b5  mov     rax, [r8+10h]
0x1800242b9  mov     rcx, [r8]
0x1800242bc  mov     rdx, [r8+8]
0x1800242c0  mov     qword ptr [rbp+var_28], rax
0x1800242c4  mov     rax, [r8+18h]
0x1800242c8  lea     r8, [rbp+var_48]; struct UserBuffer *
0x1800242cc  mov     qword ptr [rbp+var_38], rcx
0x1800242d0  mov     rcx, rsi; this
0x1800242d3  mov     qword ptr [rbp+var_38+8], rdx
0x1800242d7  lea     rdx, [rbp+var_38]; struct BinXmlTemplate *
0x1800242db  mov     [rbp+var_40], 0
0x1800242e2  mov     qword ptr [rbp+var_28+8], rax
0x1800242e6  call    ?CopyTemplateInstanceInto@BinXmlReader@@AEAAXAEAVBinXmlTemplate@@AEAVUserBuffer@@AEAVBinXmlWriter@@@Z; BinXmlReader::CopyTemplateInstanceInto(BinXmlTemplate &,UserBuffer &,BinXmlWriter &)
0x1800242eb  mov     rcx, rbx; this
0x1800242ee  call    ?EndOfFile@BinXmlWriter@@QEAAXXZ; BinXmlWriter::EndOfFile(void)
0x1800242f3  jmp     short loc_180024300
0x1800242f5  mov     rdx, rbx; struct BinXmlWriter *
0x1800242f8  mov     rcx, rsi; this
0x1800242fb  call    ?InternalCopyInto@BinXmlReader@@AEAAXAEAVBinXmlWriter@@@Z; BinXmlReader::InternalCopyInto(BinXmlWriter &)
0x180024300  mov     eax, [rdi+10h]
0x180024303  sub     eax, r14d
0x180024306  mov     [rsi+0B8h], eax
0x18002430c  mov     rcx, [rbp+var_8]
0x180024310  xor     rcx, rsp; StackCookie
0x180024313  call    __security_check_cookie
0x180024318  lea     r11, [rsp+70h+var_s0]
0x18002431d  mov     rbx, [r11+40h]
0x180024321  mov     rsi, [r11+48h]
0x180024325  mov     rsp, r11
0x180024328  pop     r15
0x18002432a  pop     r14
0x18002432c  pop     r12
0x18002432e  pop     rdi
0x18002432f  pop     rbp
0x180024330  retn
```
