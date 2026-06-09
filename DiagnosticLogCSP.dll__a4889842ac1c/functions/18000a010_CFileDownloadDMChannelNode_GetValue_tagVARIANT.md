# CFileDownloadDMChannelNode::GetValue(tagVARIANT *)

- ea: `0x18000a010`
- end: `0x18000a242`
- name: `?GetValue@CFileDownloadDMChannelNode@@UEAAJPEAUtagVARIANT@@@Z`
- size: `562`
- prototype: `__int64 __fastcall(CFileDownloadDMChannelNode *this, struct tagVARIANT *, int, int)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000108c`
- `0x1800090b4`
- `0x180009994`
- `0x18000a010`
- `0x1800116a4`
- `0x180011760`
- `0x180011980`
- `0x1800119fc`
- `0x180011dd0`
- `0x180014880`
- `0x180037010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000a08f`
- `OLEAUT32!__imp_VariantInit` at `0x18000a08f`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18000a17b`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18000a17b`

## pseudocode

```c
__int64 __fastcall CFileDownloadDMChannelNode::GetValue(
        CFileDownloadDMChannelNode *this,
        struct tagVARIANT *a2,
        int a3,
        int a4)
{
  CFileDownloadDMChannelNode *v5; // rsi
  int BlockIndexToRead; // ebx
  int BlockSizeKB; // eax
  struct IConfigManager2URI *v8; // rcx
  SAFEARRAY *Vector; // rax
  int BlockCount; // eax
  _OWORD v12[2]; // [rsp+30h] [rbp-20h] BYREF
  int v13; // [rsp+88h] [rbp+38h] BYREF
  struct tagSAFEARRAY *v14; // [rsp+90h] [rbp+40h] BYREF
  unsigned __int16 *v15; // [rsp+98h] [rbp+48h] BYREF

  v15 = 0;
  v5 = this;
  memset(v12, 0, sizeof(v12));
  if ( !a2 || (this = (CFileDownloadDMChannelNode *)*((_QWORD *)this + 3)) == 0 )
  {
    BlockIndexToRead = -2147024809;
    goto LABEL_32;
  }
  BlockIndexToRead = (*(__int64 (__fastcall **)(CFileDownloadDMChannelNode *, __int64, unsigned __int16 **))(*(_QWORD *)this + 88LL))(
                       this,
                       3,
                       &v15);
  if ( BlockIndexToRead >= 0 )
  {
    BlockIndexToRead = CFileDownload_DMChannel::Initialize((CFileDownload_DMChannel *)v12, v15);
    if ( BlockIndexToRead >= 0 )
    {
      VariantInit(a2);
      switch ( *((_DWORD *)v5 + 11) )
      {
        case 0x17:
          a2->vt = 3;
          BlockSizeKB = CFileDownload_DMChannel::GetBlockSizeKB((CFileDownload_DMChannel *)v12, &a2->lVal);
          goto LABEL_30;
        case 0x18:
          a2->vt = 3;
          BlockCount = CFileDownload_DMChannel::GetBlockCount((CFileDownload_DMChannel *)v12, &a2->lVal);
          BlockIndexToRead = BlockCount;
          if ( BlockCount == -2147024894 )
          {
            a2->lVal = -1;
          }
          else
          {
            if ( BlockCount != -2147019873 )
              goto LABEL_32;
            a2->lVal = -2;
          }
          break;
        case 0x19:
          a2->vt = 3;
          BlockSizeKB = CFileDownload_DMChannel::GetBlockIndexToRead((CFileDownload_DMChannel *)v12, &a2->lVal);
          goto LABEL_30;
        case 0x1A:
          v14 = 0;
          v13 = 0;
          BlockIndexToRead = CFileDownload_DMChannel::GetBlockIndexToRead((CFileDownload_DMChannel *)v12, &v13);
          if ( BlockIndexToRead < 0
            || (BlockIndexToRead = CFileDownload_DMChannel::GetBlockDataWithIndex(
                                     (CFileDownload_DMChannel *)v12,
                                     v13,
                                     &v14),
                BlockIndexToRead < 0) )
          {
            if ( BlockIndexToRead != -2147019873 && BlockIndexToRead != -2147024894 )
              goto LABEL_32;
            Vector = SafeArrayCreateVector(0x11u, 0, 0);
          }
          else
          {
            Vector = v14;
          }
          if ( !Vector )
          {
            BlockIndexToRead = -2147024882;
            goto LABEL_32;
          }
          a2->vt = 8209;
          a2->llVal = (LONGLONG)Vector;
          break;
        case 0x1C:
          v8 = (struct IConfigManager2URI *)*((_QWORD *)v5 + 3);
          v13 = 0;
          v14 = 0;
          BlockIndexToRead = CFileDownloadDMChannelNode::GetBlockNumber(v8, &v13);
          if ( BlockIndexToRead >= 0 )
          {
            BlockIndexToRead = CFileDownload_DMChannel::GetBlockDataWithIndex((CFileDownload_DMChannel *)v12, v13, &v14);
            if ( BlockIndexToRead >= 0 )
            {
              a2->llVal = (LONGLONG)v14;
              a2->vt = 8209;
            }
          }
          goto LABEL_32;
        default:
          BlockSizeKB = CCSPNodeImpl::GetValue(v5, a2);
LABEL_30:
          BlockIndexToRead = BlockSizeKB;
          goto LABEL_32;
      }
      BlockIndexToRead = 0;
    }
  }
LABEL_32:
  if ( (unsigned int)dword_180048E90 > 5 )
  {
    LODWORD(v14) = *((_DWORD *)v5 + 11);
    v13 = BlockIndexToRead;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)this,
      (unsigned int)byte_18003ED33,
      a3,
      a4,
      (__int64)&v14,
      (__int64)&v13);
  }
  CFileDownload_DMChannel::~CFileDownload_DMChannel((CFileDownload_DMChannel *)v12);
  return (unsigned int)BlockIndexToRead;
}

```

## disassembly

```asm
0x18000a010  push    rbp
0x18000a012  push    rbx
0x18000a013  push    rsi
0x18000a014  push    rdi
0x18000a015  push    r15
0x18000a017  mov     rbp, rsp
0x18000a01a  sub     rsp, 50h
0x18000a01e  mov     [rbp+arg_18], 0
0x18000a026  xorps   xmm0, xmm0
0x18000a029  xorps   xmm1, xmm1
0x18000a02c  mov     rdi, rdx
0x18000a02f  mov     rsi, rcx
0x18000a032  movdqu  [rbp+var_20], xmm0
0x18000a037  movdqu  [rbp+var_10], xmm1
0x18000a03c  test    rdx, rdx
0x18000a03f  jz      loc_18000A1F5
0x18000a045  mov     rcx, [rcx+18h]
0x18000a049  test    rcx, rcx
0x18000a04c  jz      loc_18000A1F5
0x18000a052  mov     rax, [rcx]
0x18000a055  lea     r8, [rbp+arg_18]
0x18000a059  mov     r15d, 3
0x18000a05f  mov     edx, r15d
0x18000a062  mov     rax, [rax+58h]
0x18000a066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a06b  mov     ebx, eax
0x18000a06d  test    eax, eax
0x18000a06f  js      loc_18000A1FA
0x18000a075  mov     rdx, [rbp+arg_18]; unsigned __int16 *
0x18000a079  lea     rcx, [rbp+var_20]; this
0x18000a07d  call    ?Initialize@CFileDownload_DMChannel@@QEAAJPEBG@Z; CFileDownload_DMChannel::Initialize(ushort const *)
0x18000a082  mov     ebx, eax
0x18000a084  test    eax, eax
0x18000a086  js      loc_18000A1FA
0x18000a08c  mov     rcx, rdi; pvarg
0x18000a08f  call    cs:__imp_VariantInit
0x18000a095  mov     ecx, [rsi+2Ch]
0x18000a098  sub     ecx, 17h
0x18000a09b  jz      loc_18000A1E0
0x18000a0a1  sub     ecx, 1
0x18000a0a4  jz      loc_18000A1AB
0x18000a0aa  sub     ecx, 1
0x18000a0ad  jz      loc_18000A198
0x18000a0b3  sub     ecx, 1
0x18000a0b6  jz      short loc_18000A11F
0x18000a0b8  cmp     ecx, 2
0x18000a0bb  jz      short loc_18000A0CD
0x18000a0bd  mov     rdx, rdi; struct tagVARIANT *
0x18000a0c0  mov     rcx, rsi; this
0x18000a0c3  call    ?GetValue@CCSPNodeImpl@@UEAAJPEAUtagVARIANT@@@Z; CCSPNodeImpl::GetValue(tagVARIANT *)
0x18000a0c8  jmp     loc_18000A1F1
0x18000a0cd  mov     rcx, [rsi+18h]; struct IConfigManager2URI *
0x18000a0d1  lea     rdx, [rbp+arg_8]; int *
0x18000a0d5  mov     [rbp+arg_8], 0
0x18000a0dc  mov     [rbp+arg_10], 0
0x18000a0e4  call    ?GetBlockNumber@CFileDownloadDMChannelNode@@KAJPEAUIConfigManager2URI@@AEAH@Z; CFileDownloadDMChannelNode::GetBlockNumber(IConfigManager2URI *,int &)
0x18000a0e9  mov     ebx, eax
0x18000a0eb  test    eax, eax
0x18000a0ed  js      loc_18000A1FA
0x18000a0f3  mov     edx, [rbp+arg_8]; int
0x18000a0f6  lea     r8, [rbp+arg_10]; struct tagSAFEARRAY **
0x18000a0fa  lea     rcx, [rbp+var_20]; this
0x18000a0fe  call    ?GetBlockDataWithIndex@CFileDownload_DMChannel@@QEAAJJAEAPEAUtagSAFEARRAY@@@Z; CFileDownload_DMChannel::GetBlockDataWithIndex(long,tagSAFEARRAY * &)
0x18000a103  mov     ebx, eax
0x18000a105  test    eax, eax
0x18000a107  js      loc_18000A1FA
0x18000a10d  mov     rax, [rbp+arg_10]
0x18000a111  mov     [rdi+8], rax
0x18000a115  mov     word ptr [rdi], 2011h
0x18000a11a  jmp     loc_18000A1FA
0x18000a11f  lea     rdx, [rbp+arg_8]; int *
0x18000a123  mov     [rbp+arg_10], 0
0x18000a12b  lea     rcx, [rbp+var_20]; this
0x18000a12f  mov     [rbp+arg_8], 0
0x18000a136  call    ?GetBlockIndexToRead@CFileDownload_DMChannel@@QEAAJAEAJ@Z; CFileDownload_DMChannel::GetBlockIndexToRead(long &)
0x18000a13b  mov     ebx, eax
0x18000a13d  test    eax, eax
0x18000a13f  js      short loc_18000A15D
0x18000a141  mov     edx, [rbp+arg_8]; int
0x18000a144  lea     r8, [rbp+arg_10]; struct tagSAFEARRAY **
0x18000a148  lea     rcx, [rbp+var_20]; this
0x18000a14c  call    ?GetBlockDataWithIndex@CFileDownload_DMChannel@@QEAAJJAEAPEAUtagSAFEARRAY@@@Z; CFileDownload_DMChannel::GetBlockDataWithIndex(long,tagSAFEARRAY * &)
0x18000a151  mov     ebx, eax
0x18000a153  test    eax, eax
0x18000a155  js      short loc_18000A15D
0x18000a157  mov     rax, [rbp+arg_10]
0x18000a15b  jmp     short loc_18000A181
0x18000a15d  cmp     ebx, 8007139Fh
0x18000a163  jz      short loc_18000A171
0x18000a165  cmp     ebx, 80070002h
0x18000a16b  jnz     loc_18000A1FA
0x18000a171  mov     ecx, 11h; vt
0x18000a176  xor     r8d, r8d; cElements
0x18000a179  xor     edx, edx; lLbound
0x18000a17b  call    cs:__imp_SafeArrayCreateVector
0x18000a181  test    rax, rax
0x18000a184  jnz     short loc_18000A18D
0x18000a186  mov     ebx, 8007000Eh
0x18000a18b  jmp     short loc_18000A1FA
0x18000a18d  mov     word ptr [rdi], 2011h
0x18000a192  mov     [rdi+8], rax
0x18000a196  jmp     short loc_18000A1DC
0x18000a198  lea     rdx, [rdi+8]; int *
0x18000a19c  mov     [rdi], r15w
0x18000a1a0  lea     rcx, [rbp+var_20]; this
0x18000a1a4  call    ?GetBlockIndexToRead@CFileDownload_DMChannel@@QEAAJAEAJ@Z; CFileDownload_DMChannel::GetBlockIndexToRead(long &)
0x18000a1a9  jmp     short loc_18000A1F1
0x18000a1ab  lea     rdx, [rdi+8]; int *
0x18000a1af  mov     [rdi], r15w
0x18000a1b3  lea     rcx, [rbp+var_20]; this
0x18000a1b7  call    ?GetBlockCount@CFileDownload_DMChannel@@QEAAJAEAJ@Z; CFileDownload_DMChannel::GetBlockCount(long &)
0x18000a1bc  mov     ebx, eax
0x18000a1be  cmp     eax, 80070002h
0x18000a1c3  jnz     short loc_18000A1CE
0x18000a1c5  mov     dword ptr [rdi+8], 0FFFFFFFFh
0x18000a1cc  jmp     short loc_18000A1DC
0x18000a1ce  cmp     eax, 8007139Fh
0x18000a1d3  jnz     short loc_18000A1FA
0x18000a1d5  mov     dword ptr [rdi+8], 0FFFFFFFEh
0x18000a1dc  xor     ebx, ebx
0x18000a1de  jmp     short loc_18000A1FA
0x18000a1e0  lea     rdx, [rdi+8]; int *
0x18000a1e4  mov     [rdi], r15w
0x18000a1e8  lea     rcx, [rbp+var_20]; this
0x18000a1ec  call    ?GetBlockSizeKB@CFileDownload_DMChannel@@QEAAJAEAJ@Z; CFileDownload_DMChannel::GetBlockSizeKB(long &)
0x18000a1f1  mov     ebx, eax
0x18000a1f3  jmp     short loc_18000A1FA
0x18000a1f5  mov     ebx, 80070057h
0x18000a1fa  mov     eax, cs:dword_180048E90
0x18000a200  cmp     eax, 5
0x18000a203  jbe     short loc_18000A22C
0x18000a205  mov     eax, [rsi+2Ch]
0x18000a208  lea     rdx, byte_18003ED33
0x18000a20f  mov     dword ptr [rbp+arg_10], eax
0x18000a212  lea     rax, [rbp+arg_8]
0x18000a216  mov     [rsp+50h+var_28], rax
0x18000a21b  lea     rax, [rbp+arg_10]
0x18000a21f  mov     [rsp+50h+var_30], rax
0x18000a224  mov     [rbp+arg_8], ebx
0x18000a227  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000a22c  lea     rcx, [rbp+var_20]; this
0x18000a230  call    ??1CFileDownload_DMChannel@@QEAA@XZ; CFileDownload_DMChannel::~CFileDownload_DMChannel(void)
0x18000a235  mov     eax, ebx
0x18000a237  add     rsp, 50h
0x18000a23b  pop     r15
0x18000a23d  pop     rdi
0x18000a23e  pop     rsi
0x18000a23f  pop     rbx
0x18000a240  pop     rbp
0x18000a241  retn
```
