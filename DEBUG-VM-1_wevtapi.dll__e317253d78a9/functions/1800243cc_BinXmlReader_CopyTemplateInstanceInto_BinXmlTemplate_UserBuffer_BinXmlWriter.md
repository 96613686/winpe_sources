# BinXmlReader::CopyTemplateInstanceInto(BinXmlTemplate &,UserBuffer &,BinXmlWriter &)

- ea: `0x1800243cc`
- end: `0x1800245f4`
- name: `?CopyTemplateInstanceInto@BinXmlReader@@AEAAXAEAVBinXmlTemplate@@AEAVUserBuffer@@AEAVBinXmlWriter@@@Z`
- size: `552`
- prototype: `void(BinXmlReader *__hidden this, struct BinXmlTemplate *, struct UserBuffer *, struct BinXmlWriter *)`
- caller_count: `3`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x18002404c`
- `0x1800243cc`
- `0x18002fd5c`

## callees

- `0x1800017cc`
- `0x180004e70`
- `0x1800058f4`
- `0x18000a4b4`
- `0x1800130b0`
- `0x180013650`
- `0x180024388`
- `0x1800243cc`
- `0x1800249f0`
- `0x18002e478`
- `0x18002f28c`
- `0x18002f324`
- `0x18002f454`
- `0x18002fd5c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall BinXmlReader::CopyTemplateInstanceInto(
        BinXmlReader *this,
        struct BinXmlTemplate *a2,
        struct UserBuffer *a3,
        struct BinXmlWriter *a4)
{
  unsigned int *v8; // r14
  unsigned int v9; // r12d
  __int64 v10; // rdx
  BinXmlTmplInstWriter *started; // rdi
  int v12; // ebx
  unsigned int v13; // ecx
  BinXmlReader *v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 *v17; // r8
  __int64 v18; // rdx
  __int64 v19; // xmm0_8
  unsigned int v20; // [rsp+20h] [rbp-B9h] BYREF
  __int64 v21; // [rsp+28h] [rbp-B1h] BYREF
  int v22; // [rsp+30h] [rbp-A9h]
  unsigned int v23; // [rsp+34h] [rbp-A5h]
  __int64 v24; // [rsp+38h] [rbp-A1h] BYREF
  int v25; // [rsp+40h] [rbp-99h]
  int v26; // [rsp+44h] [rbp-95h]
  _QWORD v27[6]; // [rsp+50h] [rbp-89h] BYREF
  _BYTE v28[24]; // [rsp+80h] [rbp-59h] BYREF
  __int128 v29; // [rsp+98h] [rbp-41h]
  __int64 v30; // [rsp+A8h] [rbp-31h]
  int v31; // [rsp+B0h] [rbp-29h]
  int v32; // [rsp+B4h] [rbp-25h]
  char v33; // [rsp+B8h] [rbp-21h]
  char v34; // [rsp+B9h] [rbp-20h]
  char v35; // [rsp+BAh] [rbp-1Fh]
  __int128 v36; // [rsp+C0h] [rbp-19h] BYREF
  __int128 v37; // [rsp+D0h] [rbp-9h]
  __int64 v38; // [rsp+E0h] [rbp+7h]
  __int64 v39; // [rsp+E8h] [rbp+Fh]

  v20 = 0;
  UserBuffer::Read4(a3, &v20);
  v8 = (unsigned int *)(*(_QWORD *)a3 + *((unsigned int *)a3 + 2));
  v9 = v20;
  UserBuffer::Advance(a3, 4 * v20);
  v27[0] = *(_QWORD *)a4;
  v27[1] = *((_QWORD *)a4 + 1);
  v27[2] = *((_QWORD *)a4 + 2);
  v27[3] = v27[0];
  v27[4] = 0;
  v27[5] = 0;
  utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(
    v28,
    v10);
  v29 = 0;
  v30 = *((_QWORD *)a4 + 11);
  v31 = *((_DWORD *)a4 + 24);
  v32 = 0;
  v33 = 0;
  v34 = *((_BYTE *)a4 + 105);
  v35 = 0;
  started = BinXmlWriter::StartTemplateInstance((BinXmlWriter *)v27, v9, a2);
  v12 = 0;
  if ( v9 )
  {
    while ( 1 )
    {
      v13 = *v8++;
      v21 = 0;
      v22 = -1;
      v23 = HIWORD(v13);
      if ( HIWORD(v13) - 32 <= 1u )
        break;
      BinXmlReader::NextValueData(this, this, (struct BinXmlVariant *)&v21, (unsigned __int16)v13);
      BinXmlTmplInstWriter::Value(started, (struct BinXmlVariant *)&v21);
LABEL_11:
      if ( ++v12 >= v9 )
        goto LABEL_12;
    }
    BinXmlTmplInstWriter::StartOpenContent(started);
    v14 = this;
    if ( v23 == 32 )
    {
      BinXmlReader::NextReaderData(this);
      v15 = *((unsigned int *)this + 9);
      v16 = *((_QWORD *)this + 3);
      v17 = *(__int64 **)(v16 + 40 * v15);
      if ( v17 )
      {
        v24 = *(_QWORD *)(v16 + 40 * v15 + 24);
        v25 = 0;
        v26 = *(_DWORD *)(v16 + 40 * v15 + 32);
        v36 = 0;
        v37 = 0;
        v38 = *((_QWORD *)this + 11);
        v39 = *((_QWORD *)a4 + 1);
        v18 = *v17;
        v19 = v17[1];
        v37 = *((_OWORD *)v17 + 1);
        *(_QWORD *)&v36 = v18;
        *((_QWORD *)&v36 + 1) = v19;
        BinXmlReader::CopyTemplateInstanceInto(this, (struct BinXmlTemplate *)&v36, (struct UserBuffer *)&v24, a4);
        BinXmlWriter::EndOfFile(a4);
LABEL_10:
        BinXmlTmplInstWriter::AdjustValueSpec(started, 0x21u);
        goto LABEL_11;
      }
      v14 = this;
    }
    else
    {
      *((_QWORD *)this + 2) = this;
    }
    BinXmlReader::InternalCopyInto(v14, (struct BinXmlWriter *)v27);
    goto LABEL_10;
  }
LABEL_12:
  utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(v28);
}

```

## disassembly

```asm
0x1800243cc  push    rbp
0x1800243ce  push    rbx
0x1800243cf  push    rsi
0x1800243d0  push    rdi
0x1800243d1  push    r12
0x1800243d3  push    r14
0x1800243d5  push    r15
0x1800243d7  lea     rbp, [rsp-27h]
0x1800243dc  sub     rsp, 100h
0x1800243e3  mov     rax, cs:__security_cookie
0x1800243ea  xor     rax, rsp
0x1800243ed  mov     [rbp+57h+var_40], rax
0x1800243f1  mov     r15, r9
0x1800243f4  mov     rbx, r8
0x1800243f7  mov     rdi, rdx
0x1800243fa  mov     rsi, rcx
0x1800243fd  mov     [rsp+130h+var_110], 0
0x180024405  lea     rdx, [rsp+130h+var_110]; void *
0x18002440a  mov     rcx, r8; this
0x18002440d  call    ?Read4@UserBuffer@@QEAAXPEAX@Z; UserBuffer::Read4(void *)
0x180024412  mov     r14d, [rbx+8]
0x180024416  add     r14, [rbx]
0x180024419  mov     r12d, [rsp+130h+var_110]
0x18002441e  lea     edx, ds:0[r12*4]; unsigned int
0x180024426  mov     rcx, rbx; this
0x180024429  call    ?Advance@UserBuffer@@QEAAXK@Z; UserBuffer::Advance(ulong)
0x18002442e  mov     rcx, [r15]
0x180024431  mov     [rsp+130h+var_E0], rcx
0x180024436  mov     rax, [r15+8]
0x18002443a  mov     [rsp+130h+var_D8], rax
0x18002443f  mov     rax, [r15+10h]
0x180024443  mov     [rbp+57h+var_D0], rax
0x180024447  mov     [rbp+57h+var_C8], rcx
0x18002444b  mov     [rbp+57h+var_C0], 0
0x180024453  mov     [rbp+57h+var_B8], 0
0x18002445b  lea     rcx, [rbp+57h+var_B0]
0x18002445f  call    ??0?$vector@UTmplInstInfo@BinXmlReader@@V?$allocator@UTmplInstInfo@BinXmlReader@@@utl@@@utl@@QEAA@XZ; utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(void)
0x180024464  xorps   xmm0, xmm0
0x180024467  movups  [rbp+57h+var_98], xmm0
0x18002446b  mov     rax, [r15+58h]
0x18002446f  mov     [rbp+57h+var_88], rax
0x180024473  mov     eax, [r15+60h]
0x180024477  mov     [rbp+57h+var_80], eax
0x18002447a  mov     [rbp+57h+var_7C], 0
0x180024481  mov     [rbp+57h+var_78], 0
0x180024485  mov     al, [r15+69h]
0x180024489  mov     [rbp+57h+var_77], al
0x18002448c  mov     [rbp+57h+var_76], 0
0x180024490  mov     r8, rdi; struct BinXmlTemplate *
0x180024493  mov     edx, r12d; unsigned int
0x180024496  lea     rcx, [rsp+130h+var_E0]; this
0x18002449b  call    ?StartTemplateInstance@BinXmlWriter@@QEAAPEAVBinXmlTmplInstWriter@@KPEAVBinXmlTemplate@@@Z; BinXmlWriter::StartTemplateInstance(ulong,BinXmlTemplate *)
0x1800244a0  mov     rdi, rax
0x1800244a3  xor     ebx, ebx
0x1800244a5  test    r12d, r12d
0x1800244a8  jz      loc_1800245CD
0x1800244ae  mov     ecx, [r14]
0x1800244b1  lea     r14, [r14+4]
0x1800244b5  mov     [rsp+130h+var_108], 0
0x1800244be  mov     [rsp+130h+var_100], 0FFFFFFFFh
0x1800244c6  mov     eax, ecx
0x1800244c8  shr     eax, 10h
0x1800244cb  mov     [rsp+130h+var_FC], eax
0x1800244cf  add     eax, 0FFFFFFE0h
0x1800244d2  cmp     eax, 1
0x1800244d5  jbe     short loc_1800244FD
0x1800244d7  movzx   r9d, cx; unsigned int
0x1800244db  lea     r8, [rsp+130h+var_108]; struct BinXmlVariant *
0x1800244e0  mov     rdx, rsi; struct UserBuffer *
0x1800244e3  mov     rcx, rsi; this
0x1800244e6  call    ?NextValueData@BinXmlReader@@AEAAXAEAVUserBuffer@@AEAUBinXmlVariant@@K@Z; BinXmlReader::NextValueData(UserBuffer &,BinXmlVariant &,ulong)
0x1800244eb  lea     rdx, [rsp+130h+var_108]; struct BinXmlVariant *
0x1800244f0  mov     rcx, rdi; this
0x1800244f3  call    ?Value@BinXmlTmplInstWriter@@QEAAXAEAUBinXmlVariant@@@Z; BinXmlTmplInstWriter::Value(BinXmlVariant &)
0x1800244f8  jmp     loc_1800245C2
0x1800244fd  mov     rcx, rdi; this
0x180024500  call    ?StartOpenContent@BinXmlTmplInstWriter@@QEAAXXZ; BinXmlTmplInstWriter::StartOpenContent(void)
0x180024505  mov     rcx, rsi; this
0x180024508  cmp     [rsp+130h+var_FC], 20h ; ' '
0x18002450d  jnz     loc_1800245A7
0x180024513  call    ?NextReaderData@BinXmlReader@@AEAAXXZ; BinXmlReader::NextReaderData(void)
0x180024518  mov     eax, [rsi+24h]
0x18002451b  lea     rcx, [rax+rax*4]
0x18002451f  mov     rdx, [rsi+18h]
0x180024523  mov     r8, [rdx+rcx*8]
0x180024527  test    r8, r8
0x18002452a  jz      short loc_1800245A2
0x18002452c  mov     rax, [rdx+rcx*8+18h]
0x180024531  mov     [rsp+130h+var_F8], rax
0x180024536  mov     [rsp+130h+var_F0], 0
0x18002453e  mov     eax, [rdx+rcx*8+20h]
0x180024542  mov     [rsp+130h+var_EC], eax
0x180024546  xorps   xmm0, xmm0
0x180024549  movdqu  [rbp+57h+var_70], xmm0
0x18002454e  movups  [rbp+57h+var_60], xmm0
0x180024552  mov     rax, [rsi+58h]
0x180024556  mov     [rbp+57h+var_50], rax
0x18002455a  mov     rax, [r15+8]
0x18002455e  mov     [rbp+57h+var_48], rax
0x180024562  mov     rdx, [r8]
0x180024565  movq    xmm0, qword ptr [r8+8]
0x18002456b  mov     rax, [r8+10h]
0x18002456f  mov     qword ptr [rbp+57h+var_60], rax
0x180024573  mov     rax, [r8+18h]
0x180024577  mov     qword ptr [rbp+57h+var_60+8], rax
0x18002457b  mov     qword ptr [rbp+57h+var_70], rdx
0x18002457f  movq    qword ptr [rbp+57h+var_70+8], xmm0
0x180024584  mov     r9, r15; struct BinXmlWriter *
0x180024587  lea     r8, [rsp+130h+var_F8]; struct UserBuffer *
0x18002458c  lea     rdx, [rbp+57h+var_70]; struct BinXmlTemplate *
0x180024590  mov     rcx, rsi; this
0x180024593  call    ?CopyTemplateInstanceInto@BinXmlReader@@AEAAXAEAVBinXmlTemplate@@AEAVUserBuffer@@AEAVBinXmlWriter@@@Z; BinXmlReader::CopyTemplateInstanceInto(BinXmlTemplate &,UserBuffer &,BinXmlWriter &)
0x180024598  mov     rcx, r15; this
0x18002459b  call    ?EndOfFile@BinXmlWriter@@QEAAXXZ; BinXmlWriter::EndOfFile(void)
0x1800245a0  jmp     short loc_1800245B5
0x1800245a2  mov     rcx, rsi
0x1800245a5  jmp     short loc_1800245AB
0x1800245a7  mov     [rsi+10h], rsi
0x1800245ab  lea     rdx, [rsp+130h+var_E0]; struct BinXmlWriter *
0x1800245b0  call    ?InternalCopyInto@BinXmlReader@@AEAAXAEAVBinXmlWriter@@@Z; BinXmlReader::InternalCopyInto(BinXmlWriter &)
0x1800245b5  mov     edx, 21h ; '!'; unsigned int
0x1800245ba  mov     rcx, rdi; this
0x1800245bd  call    ?AdjustValueSpec@BinXmlTmplInstWriter@@AEAAXK@Z; BinXmlTmplInstWriter::AdjustValueSpec(ulong)
0x1800245c2  inc     ebx
0x1800245c4  cmp     ebx, r12d
0x1800245c7  jb      loc_1800244AE
0x1800245cd  lea     rcx, [rbp+57h+var_B0]
0x1800245d1  call    ?_Uninit@?$vector@Utag_EvtRpcVariant@@V?$allocator@Utag_EvtRpcVariant@@@utl@@@utl@@AEAAXXZ; utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(void)
0x1800245d6  mov     rcx, [rbp+57h+var_40]
0x1800245da  xor     rcx, rsp; StackCookie
0x1800245dd  call    __security_check_cookie
0x1800245e2  add     rsp, 100h
0x1800245e9  pop     r15
0x1800245eb  pop     r14
0x1800245ed  pop     r12
0x1800245ef  pop     rdi
0x1800245f0  pop     rsi
0x1800245f1  pop     rbx
0x1800245f2  pop     rbp
0x1800245f3  retn
```
