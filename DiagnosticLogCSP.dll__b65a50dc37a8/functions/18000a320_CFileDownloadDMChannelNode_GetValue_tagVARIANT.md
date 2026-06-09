# CFileDownloadDMChannelNode::GetValue(tagVARIANT *)

- ea: `0x18000a320`
- end: `0x18000a55f`
- name: `?GetValue@CFileDownloadDMChannelNode@@UEAAJPEAUtagVARIANT@@@Z`
- size: `575`
- prototype: `__int64 __fastcall(CFileDownloadDMChannelNode *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001090`
- `0x1800092f8`
- `0x180009c24`
- `0x18000a320`
- `0x180011fe0`
- `0x18001209c`
- `0x1800122f4`
- `0x180012374`
- `0x180012774`
- `0x180015350`
- `0x180039010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000a39f`
- `OLEAUT32!__imp_VariantInit` at `0x18000a39f`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18000a491`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18000a491`

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
          BlockSizeKB = CFileDownload_DMChannel::GetBlockSizeKB(
                          (CFileDownload_DMChannel *)v12,
                          (unsigned int *)&a2->cyVal);
          goto LABEL_30;
        case 0x18:
          a2->vt = 3;
          BlockCount = CFileDownload_DMChannel::GetBlockCount((CFileDownload_DMChannel *)v12, (DWORD *)&a2->cyVal);
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
  if ( (unsigned int)dword_18004AE90 > 5 )
  {
    LODWORD(v14) = *((_DWORD *)v5 + 11);
    v13 = BlockIndexToRead;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)this,
      (unsigned int)byte_180040D33,
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
0x18000a320  push    rbp
0x18000a322  push    rbx
0x18000a323  push    rsi
0x18000a324  push    rdi
0x18000a325  push    r15
0x18000a327  mov     rbp, rsp
0x18000a32a  sub     rsp, 50h
0x18000a32e  mov     [rbp+arg_18], 0
0x18000a336  xorps   xmm0, xmm0
0x18000a339  xorps   xmm1, xmm1
0x18000a33c  mov     rdi, rdx
0x18000a33f  mov     rsi, rcx
0x18000a342  movdqu  [rbp+var_20], xmm0
0x18000a347  movdqu  [rbp+var_10], xmm1
0x18000a34c  test    rdx, rdx
0x18000a34f  jz      loc_18000A511
0x18000a355  mov     rcx, [rcx+18h]
0x18000a359  test    rcx, rcx
0x18000a35c  jz      loc_18000A511
0x18000a362  mov     rax, [rcx]
0x18000a365  lea     r8, [rbp+arg_18]
0x18000a369  mov     r15d, 3
0x18000a36f  mov     edx, r15d
0x18000a372  mov     rax, [rax+58h]
0x18000a376  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a37b  mov     ebx, eax
0x18000a37d  test    eax, eax
0x18000a37f  js      loc_18000A516
0x18000a385  mov     rdx, [rbp+arg_18]; unsigned __int16 *
0x18000a389  lea     rcx, [rbp+var_20]; this
0x18000a38d  call    ?Initialize@CFileDownload_DMChannel@@QEAAJPEBG@Z; CFileDownload_DMChannel::Initialize(ushort const *)
0x18000a392  mov     ebx, eax
0x18000a394  test    eax, eax
0x18000a396  js      loc_18000A516
0x18000a39c  mov     rcx, rdi; pvarg
0x18000a39f  call    cs:__imp_VariantInit
0x18000a3a6  nop     dword ptr [rax+rax+00h]
0x18000a3ab  mov     ecx, [rsi+2Ch]
0x18000a3ae  sub     ecx, 17h
0x18000a3b1  jz      loc_18000A4FC
0x18000a3b7  sub     ecx, 1
0x18000a3ba  jz      loc_18000A4C7
0x18000a3c0  sub     ecx, 1
0x18000a3c3  jz      loc_18000A4B4
0x18000a3c9  sub     ecx, 1
0x18000a3cc  jz      short loc_18000A435
0x18000a3ce  cmp     ecx, 2
0x18000a3d1  jz      short loc_18000A3E3
0x18000a3d3  mov     rdx, rdi; struct tagVARIANT *
0x18000a3d6  mov     rcx, rsi; this
0x18000a3d9  call    ?GetValue@CCSPNodeImpl@@UEAAJPEAUtagVARIANT@@@Z; CCSPNodeImpl::GetValue(tagVARIANT *)
0x18000a3de  jmp     loc_18000A50D
0x18000a3e3  mov     rcx, [rsi+18h]; struct IConfigManager2URI *
0x18000a3e7  lea     rdx, [rbp+arg_8]; int *
0x18000a3eb  mov     [rbp+arg_8], 0
0x18000a3f2  mov     [rbp+arg_10], 0
0x18000a3fa  call    ?GetBlockNumber@CFileDownloadDMChannelNode@@KAJPEAUIConfigManager2URI@@AEAH@Z; CFileDownloadDMChannelNode::GetBlockNumber(IConfigManager2URI *,int &)
0x18000a3ff  mov     ebx, eax
0x18000a401  test    eax, eax
0x18000a403  js      loc_18000A516
0x18000a409  mov     edx, [rbp+arg_8]; int
0x18000a40c  lea     r8, [rbp+arg_10]; struct tagSAFEARRAY **
0x18000a410  lea     rcx, [rbp+var_20]; this
0x18000a414  call    ?GetBlockDataWithIndex@CFileDownload_DMChannel@@QEAAJJAEAPEAUtagSAFEARRAY@@@Z; CFileDownload_DMChannel::GetBlockDataWithIndex(long,tagSAFEARRAY * &)
0x18000a419  mov     ebx, eax
0x18000a41b  test    eax, eax
0x18000a41d  js      loc_18000A516
0x18000a423  mov     rax, [rbp+arg_10]
0x18000a427  mov     [rdi+8], rax
0x18000a42b  mov     word ptr [rdi], 2011h
0x18000a430  jmp     loc_18000A516
0x18000a435  lea     rdx, [rbp+arg_8]; int *
0x18000a439  mov     [rbp+arg_10], 0
0x18000a441  lea     rcx, [rbp+var_20]; this
0x18000a445  mov     [rbp+arg_8], 0
0x18000a44c  call    ?GetBlockIndexToRead@CFileDownload_DMChannel@@QEAAJAEAJ@Z; CFileDownload_DMChannel::GetBlockIndexToRead(long &)
0x18000a451  mov     ebx, eax
0x18000a453  test    eax, eax
0x18000a455  js      short loc_18000A473
0x18000a457  mov     edx, [rbp+arg_8]; int
0x18000a45a  lea     r8, [rbp+arg_10]; struct tagSAFEARRAY **
0x18000a45e  lea     rcx, [rbp+var_20]; this
0x18000a462  call    ?GetBlockDataWithIndex@CFileDownload_DMChannel@@QEAAJJAEAPEAUtagSAFEARRAY@@@Z; CFileDownload_DMChannel::GetBlockDataWithIndex(long,tagSAFEARRAY * &)
0x18000a467  mov     ebx, eax
0x18000a469  test    eax, eax
0x18000a46b  js      short loc_18000A473
0x18000a46d  mov     rax, [rbp+arg_10]
0x18000a471  jmp     short loc_18000A49D
0x18000a473  cmp     ebx, 8007139Fh
0x18000a479  jz      short loc_18000A487
0x18000a47b  cmp     ebx, 80070002h
0x18000a481  jnz     loc_18000A516
0x18000a487  mov     ecx, 11h; vt
0x18000a48c  xor     r8d, r8d; cElements
0x18000a48f  xor     edx, edx; lLbound
0x18000a491  call    cs:__imp_SafeArrayCreateVector
0x18000a498  nop     dword ptr [rax+rax+00h]
0x18000a49d  test    rax, rax
0x18000a4a0  jnz     short loc_18000A4A9
0x18000a4a2  mov     ebx, 8007000Eh
0x18000a4a7  jmp     short loc_18000A516
0x18000a4a9  mov     word ptr [rdi], 2011h
0x18000a4ae  mov     [rdi+8], rax
0x18000a4b2  jmp     short loc_18000A4F8
0x18000a4b4  lea     rdx, [rdi+8]; int *
0x18000a4b8  mov     [rdi], r15w
0x18000a4bc  lea     rcx, [rbp+var_20]; this
0x18000a4c0  call    ?GetBlockIndexToRead@CFileDownload_DMChannel@@QEAAJAEAJ@Z; CFileDownload_DMChannel::GetBlockIndexToRead(long &)
0x18000a4c5  jmp     short loc_18000A50D
0x18000a4c7  lea     rdx, [rdi+8]; int *
0x18000a4cb  mov     [rdi], r15w
0x18000a4cf  lea     rcx, [rbp+var_20]; this
0x18000a4d3  call    ?GetBlockCount@CFileDownload_DMChannel@@QEAAJAEAJ@Z; CFileDownload_DMChannel::GetBlockCount(long &)
0x18000a4d8  mov     ebx, eax
0x18000a4da  cmp     eax, 80070002h
0x18000a4df  jnz     short loc_18000A4EA
0x18000a4e1  mov     dword ptr [rdi+8], 0FFFFFFFFh
0x18000a4e8  jmp     short loc_18000A4F8
0x18000a4ea  cmp     eax, 8007139Fh
0x18000a4ef  jnz     short loc_18000A516
0x18000a4f1  mov     dword ptr [rdi+8], 0FFFFFFFEh
0x18000a4f8  xor     ebx, ebx
0x18000a4fa  jmp     short loc_18000A516
0x18000a4fc  lea     rdx, [rdi+8]; int *
0x18000a500  mov     [rdi], r15w
0x18000a504  lea     rcx, [rbp+var_20]; this
0x18000a508  call    ?GetBlockSizeKB@CFileDownload_DMChannel@@QEAAJAEAJ@Z; CFileDownload_DMChannel::GetBlockSizeKB(long &)
0x18000a50d  mov     ebx, eax
0x18000a50f  jmp     short loc_18000A516
0x18000a511  mov     ebx, 80070057h
0x18000a516  mov     eax, cs:dword_18004AE90
0x18000a51c  cmp     eax, 5
0x18000a51f  jbe     short loc_18000A548
0x18000a521  mov     eax, [rsi+2Ch]
0x18000a524  lea     rdx, byte_180040D33
0x18000a52b  mov     dword ptr [rbp+arg_10], eax
0x18000a52e  lea     rax, [rbp+arg_8]
0x18000a532  mov     [rsp+50h+var_28], rax
0x18000a537  lea     rax, [rbp+arg_10]
0x18000a53b  mov     [rsp+50h+var_30], rax
0x18000a540  mov     [rbp+arg_8], ebx
0x18000a543  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000a548  lea     rcx, [rbp+var_20]; this
0x18000a54c  call    ??1CFileDownload_DMChannel@@QEAA@XZ; CFileDownload_DMChannel::~CFileDownload_DMChannel(void)
0x18000a551  mov     eax, ebx
0x18000a553  add     rsp, 50h
0x18000a557  pop     r15
0x18000a559  pop     rdi
0x18000a55a  pop     rsi
0x18000a55b  pop     rbx
0x18000a55c  pop     rbp
0x18000a55d  retn
```
