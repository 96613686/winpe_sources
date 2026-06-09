# RangeSet::InitializeByMergingWithTripleCoreFragment(RangeSet const &,SharedRefPtr<ICoreFragment> &,SharedRefPtr<ICoreFragment> &,TripleMergeContext &,SyncIdCache *)

- ea: `0x18008fd10`
- end: `0x18008ff56`
- name: `?InitializeByMergingWithTripleCoreFragment@RangeSet@@QEAAJAEBV1@AEAV?$SharedRefPtr@UICoreFragment@@@@1AEAVTripleMergeContext@@PEAVSyncIdCache@@@Z`
- size: `582`
- prototype: `__int64 __usercall@<rax>(RangeSet *this@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x18008de60`

## callees

- `0x180008ab0`
- `0x180011f60`
- `0x1800137c0`
- `0x18001a038`
- `0x18001ae20`
- `0x180025740`
- `0x180029388`
- `0x18008f390`
- `0x18008f504`
- `0x18008fd10`
- `0x1800904ec`
- `0x18009071c`
- `0x180090970`

## pseudocode

```c
__int64 __fastcall RangeSet::InitializeByMergingWithTripleCoreFragment(
        RangeSet *this,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  int v10; // eax
  __int64 v11; // r13
  unsigned int v12; // edi
  int v13; // ebx
  int v14; // esi
  int v15; // eax
  __int64 v16; // rcx
  _BYTE v18[4]; // [rsp+40h] [rbp-C0h] BYREF
  int v19; // [rsp+44h] [rbp-BCh]
  __int64 v20; // [rsp+48h] [rbp-B8h]
  int v21; // [rsp+50h] [rbp-B0h]
  _BYTE v22[4]; // [rsp+60h] [rbp-A0h] BYREF
  int v23; // [rsp+64h] [rbp-9Ch]
  __int64 v24; // [rsp+68h] [rbp-98h]
  char v25[4]; // [rsp+70h] [rbp-90h] BYREF
  int v26; // [rsp+74h] [rbp-8Ch]
  __int64 v27; // [rsp+78h] [rbp-88h]
  char v28[4]; // [rsp+80h] [rbp-80h] BYREF
  int v29; // [rsp+84h] [rbp-7Ch]
  __int64 v30; // [rsp+88h] [rbp-78h]
  int v31; // [rsp+90h] [rbp-70h]
  char v32[4]; // [rsp+94h] [rbp-6Ch] BYREF
  char v33; // [rsp+98h] [rbp-68h] BYREF
  char v34[8]; // [rsp+A0h] [rbp-60h] BYREF
  char v35; // [rsp+A8h] [rbp-58h] BYREF
  char v36[8]; // [rsp+B0h] [rbp-50h] BYREF
  int v37; // [rsp+B8h] [rbp-48h]
  int v38; // [rsp+BCh] [rbp-44h]
  int v39; // [rsp+C4h] [rbp-3Ch]
  int v40; // [rsp+C8h] [rbp-38h]
  int v41; // [rsp+CCh] [rbp-34h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      WPP_ff88f7f000e13ecf98ed337d60498caa_Traceguids,
      "RangeSet::InitializeByMergingWithTripleCoreFragment");
  }
  if ( (RangeSet *)((char *)this + 40) != (RangeSet *)(a2 + 40) )
  {
    *((_DWORD *)this + 10) = *(_DWORD *)(a2 + 40);
    *((_WORD *)this + 22) = *(_WORD *)(a2 + 44);
  }
  v10 = *(_DWORD *)(a2 + 8);
  v11 = a5;
  *((_DWORD *)this + 2) = 0;
  if ( !v10 )
    v10 = 16;
  *((_DWORD *)this + 8) = 0;
  *((_DWORD *)this + 4) = v10;
  RangeSet::IteratorWithTripleCoreFragment::IteratorWithTripleCoreFragment(
    (__int64)v22,
    a2,
    a3,
    a4,
    *(_QWORD *)(v11 + 64),
    a6);
  v12 = RangeSet::IteratorWithTripleCoreFragment::MoveToBeginning(v22, v22, v25, v28, v32, v34, v36);
  if ( v12 )
    goto LABEL_25;
  TripleIterator<RangeSet::IteratorWithTripleCoreFragment,unsigned long,SharedRefPtr<IClockVector>,SharedRefPtr<IClockVector>>::UpdateIteratorState((struct SyncId *)v22);
  v13 = -1;
  do
  {
    if ( v39 && v40 && v41 )
      break;
    LODWORD(a5) = 0;
    v12 = TripleMergeContext::MergeTripleVectors(v11, v31, (unsigned int)&v33, (unsigned int)&v35, (__int64)&a5);
    if ( v12 )
      goto LABEL_25;
    v14 = a5;
    if ( v13 == -1 || v13 != (_DWORD)a5 )
    {
      if ( v37 )
      {
        v15 = v23;
        v16 = v24;
      }
      else if ( v38 )
      {
        v15 = v26;
        v16 = v27;
      }
      else
      {
        v15 = v29;
        v16 = v30;
      }
      v20 = v16;
      v19 = v15;
      SyncId::AddRef((SyncId *)v18);
      v21 = v14;
      v12 = RangeSet::RangeVector::Add((RangeSet *)((char *)this + 8), (const struct Range *)v18);
      SyncId::~SyncId((SyncId *)v18);
      if ( v12 )
        goto LABEL_25;
    }
    v13 = v14;
    v12 = TripleIterator<RangeSet::IteratorWithTripleCoreFragment,unsigned long,SharedRefPtr<IClockVector>,SharedRefPtr<IClockVector>>::MoveNext((struct SyncId *)v22);
  }
  while ( !v12 );
  if ( v12 )
LABEL_25:
    RangeSet::Recycle(this);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      (unsigned int)WPP_ff88f7f000e13ecf98ed337d60498caa_Traceguids,
      (unsigned int)"RangeSet::InitializeByMergingWithTripleCoreFragment",
      v12);
  }
  RangeSet::IteratorWithTripleCoreFragment::~IteratorWithTripleCoreFragment((RangeSet::IteratorWithTripleCoreFragment *)v22);
  return v12;
}

```

## disassembly

```asm
0x18008fd10  push    rbp
0x18008fd12  push    rbx
0x18008fd13  push    rsi
0x18008fd14  push    rdi
0x18008fd15  push    r13
0x18008fd17  push    r14
0x18008fd19  push    r15
0x18008fd1b  lea     rbp, [rsp-30h]
0x18008fd20  sub     rsp, 130h
0x18008fd27  mov     rdi, r9
0x18008fd2a  mov     rsi, r8
0x18008fd2d  mov     rbx, rdx
0x18008fd30  mov     r14, rcx
0x18008fd33  mov     rcx, cs:WPP_GLOBAL_Control
0x18008fd3a  lea     rax, WPP_GLOBAL_Control
0x18008fd41  cmp     rcx, rax
0x18008fd44  jz      short loc_18008FD6E
0x18008fd46  test    byte ptr [rcx+1Ch], 40h
0x18008fd4a  jz      short loc_18008FD6E
0x18008fd4c  cmp     byte ptr [rcx+19h], 5
0x18008fd50  jb      short loc_18008FD6E
0x18008fd52  mov     rcx, [rcx+10h]
0x18008fd56  lea     r9, aRangesetInitia_5; "RangeSet::InitializeByMergingWithTriple"...
0x18008fd5d  mov     edx, 12h
0x18008fd62  lea     r8, WPP_ff88f7f000e13ecf98ed337d60498caa_Traceguids
0x18008fd69  call    WPP_SF_s
0x18008fd6e  lea     rcx, [rbx+28h]
0x18008fd72  lea     rdx, [r14+28h]
0x18008fd76  cmp     rdx, rcx
0x18008fd79  jz      short loc_18008FD87
0x18008fd7b  mov     eax, [rcx]
0x18008fd7d  mov     [rdx], eax
0x18008fd7f  movzx   eax, word ptr [rcx+4]
0x18008fd83  mov     [rdx+4], ax
0x18008fd87  mov     eax, [rbx+8]
0x18008fd8a  mov     ecx, 10h
0x18008fd8f  mov     r13, [rbp+60h+arg_20]
0x18008fd96  test    eax, eax
0x18008fd98  mov     dword ptr [r14+8], 0
0x18008fda0  mov     r9, rdi
0x18008fda3  cmovz   eax, ecx
0x18008fda6  mov     dword ptr [r14+20h], 0
0x18008fdae  mov     [r14+10h], eax
0x18008fdb2  lea     rcx, [rsp+160h+var_100]
0x18008fdb7  mov     rax, [rbp+60h+arg_28]
0x18008fdbe  mov     r8, rsi
0x18008fdc1  mov     [rsp+160h+var_138], rax
0x18008fdc6  mov     rdx, rbx
0x18008fdc9  mov     rax, [r13+40h]
0x18008fdcd  mov     [rsp+160h+var_140], rax
0x18008fdd2  call    ??0IteratorWithTripleCoreFragment@RangeSet@@QEAA@AEBV1@AEAV?$SharedRefPtr@UICoreFragment@@@@1PEAEPEAVSyncIdCache@@@Z; RangeSet::IteratorWithTripleCoreFragment::IteratorWithTripleCoreFragment(RangeSet const &,SharedRefPtr<ICoreFragment> &,SharedRefPtr<ICoreFragment> &,uchar *,SyncIdCache *)
0x18008fdd7  lea     rax, [rbp+60h+var_B0]
0x18008fddb  mov     [rsp+160h+var_130], rax
0x18008fde0  lea     r9, [rbp+60h+var_E0]
0x18008fde4  lea     rax, [rbp+60h+var_C0]
0x18008fde8  mov     [rsp+160h+var_138], rax
0x18008fded  lea     r8, [rsp+160h+var_F0]
0x18008fdf2  lea     rax, [rbp+60h+var_CC]
0x18008fdf6  lea     rdx, [rsp+160h+var_100]
0x18008fdfb  mov     [rsp+160h+var_140], rax
0x18008fe00  lea     rcx, [rsp+160h+var_100]
0x18008fe05  call    ?MoveToBeginning@IteratorWithTripleCoreFragment@RangeSet@@QEAAJAEAVSyncId@@00AEAKAEAV?$SharedRefPtr@UIClockVector@@@@2@Z; RangeSet::IteratorWithTripleCoreFragment::MoveToBeginning(SyncId &,SyncId &,SyncId &,ulong &,SharedRefPtr<IClockVector> &,SharedRefPtr<IClockVector> &)
0x18008fe0a  mov     edi, eax
0x18008fe0c  test    eax, eax
0x18008fe0e  jnz     loc_18008FEF1
0x18008fe14  lea     rcx, [rsp+160h+var_100]; struct SyncId *
0x18008fe19  call    ?UpdateIteratorState@?$TripleIterator@VIteratorWithTripleCoreFragment@RangeSet@@KV?$SharedRefPtr@UIClockVector@@@@V3@@@AEAAXXZ; TripleIterator<RangeSet::IteratorWithTripleCoreFragment,ulong,SharedRefPtr<IClockVector>,SharedRefPtr<IClockVector>>::UpdateIteratorState(void)
0x18008fe1e  or      ebx, 0FFFFFFFFh
0x18008fe21  cmp     [rbp+60h+var_9C], 0
0x18008fe25  jz      short loc_18008FE37
0x18008fe27  cmp     [rbp+60h+var_98], 0
0x18008fe2b  jz      short loc_18008FE37
0x18008fe2d  cmp     [rbp+60h+var_94], 0
0x18008fe31  jnz     loc_18008FEED
0x18008fe37  mov     edx, [rbp+60h+var_D0]
0x18008fe3a  lea     rax, [rbp+60h+arg_20]
0x18008fe41  lea     r9, [rbp+60h+var_B8]
0x18008fe45  mov     [rsp+160h+var_140], rax
0x18008fe4a  lea     r8, [rbp+60h+var_C8]
0x18008fe4e  mov     dword ptr [rbp+60h+arg_20], 0
0x18008fe58  mov     rcx, r13
0x18008fe5b  call    ?MergeTripleVectors@TripleMergeContext@@QEAAJKAEAV?$SharedRefPtr@UIClockVector@@@@0AEAK@Z; TripleMergeContext::MergeTripleVectors(ulong,SharedRefPtr<IClockVector> &,SharedRefPtr<IClockVector> &,ulong &)
0x18008fe60  mov     edi, eax
0x18008fe62  test    eax, eax
0x18008fe64  jnz     loc_18008FEF1
0x18008fe6a  mov     esi, dword ptr [rbp+60h+arg_20]
0x18008fe70  cmp     ebx, 0FFFFFFFFh
0x18008fe73  jz      short loc_18008FE79
0x18008fe75  cmp     ebx, esi
0x18008fe77  jz      short loc_18008FED7
0x18008fe79  cmp     [rbp+60h+var_A8], 0
0x18008fe7d  jz      short loc_18008FE8A
0x18008fe7f  mov     eax, [rsp+160h+var_FC]
0x18008fe83  mov     rcx, [rsp+160h+var_F8]
0x18008fe88  jmp     short loc_18008FEA2
0x18008fe8a  cmp     [rbp+60h+var_A4], 0
0x18008fe8e  jz      short loc_18008FE9B
0x18008fe90  mov     eax, [rsp+160h+var_EC]
0x18008fe94  mov     rcx, [rsp+160h+var_E8]
0x18008fe99  jmp     short loc_18008FEA2
0x18008fe9b  mov     eax, [rbp+60h+var_DC]
0x18008fe9e  mov     rcx, [rbp+60h+var_D8]
0x18008fea2  mov     [rsp+160h+var_118], rcx
0x18008fea7  lea     rcx, [rsp+160h+var_120]; this
0x18008feac  mov     [rsp+160h+var_11C], eax
0x18008feb0  call    ?AddRef@SyncId@@AEAAXXZ; SyncId::AddRef(void)
0x18008feb5  lea     rdx, [rsp+160h+var_120]; struct Range *
0x18008feba  mov     [rsp+160h+var_110], esi
0x18008febe  lea     rcx, [r14+8]; this
0x18008fec2  call    ?Add@RangeVector@RangeSet@@QEAAJAEBURange@@@Z; RangeSet::RangeVector::Add(Range const &)
0x18008fec7  lea     rcx, [rsp+160h+var_120]; this
0x18008fecc  mov     edi, eax
0x18008fece  call    ??1SyncId@@QEAA@XZ; SyncId::~SyncId(void)
0x18008fed3  test    edi, edi
0x18008fed5  jnz     short loc_18008FEF1
0x18008fed7  lea     rcx, [rsp+160h+var_100]; struct SyncId *
0x18008fedc  mov     ebx, esi
0x18008fede  call    ?MoveNext@?$TripleIterator@VIteratorWithTripleCoreFragment@RangeSet@@KV?$SharedRefPtr@UIClockVector@@@@V3@@@QEAAJXZ; TripleIterator<RangeSet::IteratorWithTripleCoreFragment,ulong,SharedRefPtr<IClockVector>,SharedRefPtr<IClockVector>>::MoveNext(void)
0x18008fee3  mov     edi, eax
0x18008fee5  test    eax, eax
0x18008fee7  jz      loc_18008FE21
0x18008feed  test    edi, edi
0x18008feef  jz      short loc_18008FEF9
0x18008fef1  mov     rcx, r14; this
0x18008fef4  call    ?Recycle@RangeSet@@QEAAXXZ; RangeSet::Recycle(void)
0x18008fef9  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ff00  lea     rax, WPP_GLOBAL_Control
0x18008ff07  cmp     rcx, rax
0x18008ff0a  jz      short loc_18008FF38
0x18008ff0c  test    byte ptr [rcx+1Ch], 40h
0x18008ff10  jz      short loc_18008FF38
0x18008ff12  cmp     byte ptr [rcx+19h], 5
0x18008ff16  jb      short loc_18008FF38
0x18008ff18  mov     rcx, [rcx+10h]
0x18008ff1c  lea     r9, aRangesetInitia_5; "RangeSet::InitializeByMergingWithTriple"...
0x18008ff23  mov     edx, 13h
0x18008ff28  mov     dword ptr [rsp+160h+var_140], edi
0x18008ff2c  lea     r8, WPP_ff88f7f000e13ecf98ed337d60498caa_Traceguids
0x18008ff33  call    WPP_SF_sD
0x18008ff38  lea     rcx, [rsp+160h+var_100]; this
0x18008ff3d  call    ??1IteratorWithTripleCoreFragment@RangeSet@@QEAA@XZ; RangeSet::IteratorWithTripleCoreFragment::~IteratorWithTripleCoreFragment(void)
0x18008ff42  mov     eax, edi
0x18008ff44  add     rsp, 130h
0x18008ff4b  pop     r15
0x18008ff4d  pop     r14
0x18008ff4f  pop     r13
0x18008ff51  pop     rdi
0x18008ff52  pop     rsi
0x18008ff53  pop     rbx
0x18008ff54  pop     rbp
0x18008ff55  retn
```
