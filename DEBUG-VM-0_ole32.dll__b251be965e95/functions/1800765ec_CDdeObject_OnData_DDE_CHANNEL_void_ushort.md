# CDdeObject::OnData(DDE_CHANNEL *,void *,ushort)

- ea: `0x1800765ec`
- end: `0x1800769d3`
- name: `?OnData@CDdeObject@@QEAAJPEAVDDE_CHANNEL@@PEAXG@Z`
- size: `999`
- prototype: `HRESULT __fastcall(CDdeObject *this, DDE_CHANNEL *pChannel, void *hDdeData, unsigned __int16 aItem)`
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18007a850`

## callees

- `0x18004d620`
- `0x180052390`
- `0x180053014`
- `0x1800758b0`
- `0x1800760cc`
- `0x1800765ec`
- `0x1800770e0`
- `0x180077798`
- `0x180077b54`
- `0x180077dd8`
- `0x18007808c`
- `0x1800781f8`

## import_xrefs

- `KERNELBASE!GlobalFree` at `0x1800766ee`
- `KERNELBASE!GlobalFree` at `0x1800767dd`
- `KERNELBASE!GlobalFree` at `0x1800766ee`
- `KERNELBASE!GlobalFree` at `0x1800767dd`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800766e5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18007674d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180076785`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800767d4`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180076831`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800766e5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18007674d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180076785`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800767d4`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180076831`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800766b7`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180076756`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800766b7`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180076756`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180076778`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x1800769ab`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180076778`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x1800769ab`
- `USER32!PackDDElParam` at `0x18007667e`
- `USER32!PackDDElParam` at `0x18007670d`
- `USER32!PackDDElParam` at `0x18007667e`
- `USER32!PackDDElParam` at `0x18007670d`
- `api-ms-win-core-com-private-l1-1-0!InternalSTAInvoke` at `0x180076948`
- `api-ms-win-core-com-private-l1-1-0!InternalSTAInvoke` at `0x180076948`

## pseudocode

```c
__int64 __fastcall CDdeObject::OnData(CDdeObject *this, DDE_CHANNEL *pChannel, void *hDdeData, unsigned __int16 aItem)
{
  unsigned int iAwaitAck; // eax
  UINT_PTR v5; // r15
  tagDDECALLDATA *pCD; // rax
  unsigned int v10; // esi
  LPARAM v11; // rax
  char *v13; // rax
  char *v14; // r12
  unsigned __int16 v15; // ax
  LPARAM v16; // rax
  __int16 *v17; // rax
  __int16 *v18; // rbx
  unsigned __int16 v19; // bx
  void *v20; // rax
  int v21; // r8d
  int v22; // r13d
  int *p_m_iAdvSave; // rdx
  __int16 v24; // r12
  DDE_CHANNEL *v25; // rdx
  tagDDECALLDATA *v26; // rax
  int v27; // [rsp+40h] [rbp-C0h]
  unsigned __int16 v28; // [rsp+44h] [rbp-BCh]
  unsigned int dwFault; // [rsp+48h] [rbp-B8h] BYREF
  int iAdvOpt; // [rsp+4Ch] [rbp-B4h] BYREF
  tagDISPATCHDATA dispatchdata; // [rsp+50h] [rbp-B0h] BYREF
  tagDDEDISPATCHDATA ddedispdata; // [rsp+60h] [rbp-A0h] BYREF
  tagRPCOLEMESSAGE rpcMsg; // [rsp+80h] [rbp-80h] BYREF
  _RPC_SERVER_INTERFACE RpcInterfaceInfo; // [rsp+D0h] [rbp-30h] BYREF

  iAwaitAck = pChannel->iAwaitAck;
  v5 = aItem;
  iAdvOpt = 0;
  dwFault = iAwaitAck;
  if ( iAwaitAck == 1 || iAwaitAck == 8 )
  {
    pCD = pChannel->pCD;
    pChannel->iAwaitAck = 0;
    if ( pCD )
    {
      pChannel->CallState = SERVERCALLEX_ISHANDLED;
      pChannel->hres = 0;
      pCD->fDone = 1;
    }
  }
  v10 = wScanItemOptions(aItem, &iAdvOpt);
  if ( v10 )
  {
    v11 = PackDDElParam(0x3E4u, 0, v5);
    if ( !wPostMessageToServer(pChannel, 0x3E4u, v11, 1) )
      return (unsigned int)-2147418105;
    return v10;
  }
  if ( !hDdeData )
    return 2147549200LL;
  v13 = (char *)GlobalLock(hDdeData);
  v14 = v13;
  if ( !v13 )
    return 2147942414LL;
  v15 = *(_WORD *)v13;
  v28 = v15;
  if ( pChannel->bTerminating )
  {
    GlobalUnlock(hDdeData);
    GlobalFree(hDdeData);
$exitRtn_6:
    if ( v28 < 0x8000u && (_WORD)v5 )
      GlobalDeleteAtom(v5);
    return v10;
  }
  if ( v15 >= 0x8000u )
  {
    v16 = PackDDElParam(0x3E4u, 0x8000u, v5);
    if ( !wPostMessageToServer(pChannel, 0x3E4u, v16, 1) )
      return 2147549191LL;
  }
  if ( pChannel->iAwaitAck != 8 || (*(_WORD *)v14 & 0x1000) == 0 )
  {
    if ( *((_WORD *)v14 + 1) == g_cfBinary && (_WORD)v5 == aStdDocName )
    {
      CDdeObject::ChangeTopic(this, v14 + 4);
      GlobalUnlock(hDdeData);
      GlobalFree(hDdeData);
      return 0;
    }
    v27 = 0;
    v22 = iAdvOpt;
    if ( iAdvOpt )
    {
      if ( iAdvOpt == 1 )
      {
        p_m_iAdvSave = &this->m_iAdvSave;
      }
      else
      {
        if ( iAdvOpt != 2 )
          goto LABEL_37;
        p_m_iAdvSave = &this->m_iAdvClose;
      }
      v27 = CDdeObject::CanCallBack((CDdeObject *)(unsigned int)(iAdvOpt - 1), p_m_iAdvSave);
    }
    else
    {
      v27 = 1;
    }
LABEL_37:
    v24 = *(_WORD *)v14;
    GlobalUnlock(hDdeData);
    v10 = CDdeObject::KeepData(this, v25, hDdeData);
    if ( v10 )
    {
      if ( dwFault == 1 || dwFault == 8 )
      {
        v26 = pChannel->pCD;
        if ( v26 )
        {
          pChannel->CallState = SERVERCALLEX_ISHANDLED;
          pChannel->hres = v10;
          v26->fDone = 1;
        }
      }
    }
    else if ( (v24 & 0x1000) != 0 )
    {
      v10 = 0;
    }
    else
    {
      ++pChannel->m_cRefs;
      if ( v27 )
      {
        if ( v22 )
        {
          *(_QWORD *)&ddedispdata.wDispFunc = 1;
          *(&ddedispdata.iArg + 1) = 0;
          *(_QWORD *)&dispatchdata.scode = 0;
          dwFault = 0;
          memset_0(&rpcMsg, 0, sizeof(rpcMsg));
          memset_0(&RpcInterfaceInfo, 0, sizeof(RpcInterfaceInfo));
          rpcMsg.cbBuffer = 16;
          rpcMsg.reserved2[1] = &RpcInterfaceInfo;
          rpcMsg.iMethod = 6;
          rpcMsg.Buffer = &dispatchdata;
          ddedispdata.pCDdeObject = this;
          dispatchdata.pData = &ddedispdata;
          ddedispdata.iArg = v22;
          RpcInterfaceInfo.InterfaceId.SyntaxGUID = IID_IDataAdviseHolder;
          InternalSTAInvoke(&rpcMsg, 1, &this->m_RpcStubBuffer, pChannel, 0, 0, &dwFault);
        }
        if ( v22 != 2 || (this->m_fGotCloseData = 1, (v10 = CDdeObject::OleCallBack(this, 1, pChannel)) == 0) )
          v10 = CDdeObject::OleCallBack(this, v22, pChannel);
      }
      if ( !DDE_CHANNEL::ReleaseReference(pChannel) )
        this->m_pDocChannel = 0;
    }
    goto $exitRtn_6;
  }
  GlobalUnlock(hDdeData);
  v17 = (__int16 *)GlobalLock(hDdeData);
  v18 = v17;
  if ( !v17 )
    return 2147942414LL;
  if ( *v17 >= 0 && (_WORD)v5 )
    GlobalDeleteAtom(v5);
  v19 = v18[1];
  GlobalUnlock(hDdeData);
  v20 = wHandleFromDdeData(hDdeData);
  if ( v20 )
    wFreeData(v20, v19, v21);
  return 0;
}

```

## disassembly

```asm
0x1800765ec  push    rbp
0x1800765ee  push    rbx
0x1800765ef  push    rsi
0x1800765f0  push    rdi
0x1800765f1  push    r12
0x1800765f3  push    r13
0x1800765f5  push    r14
0x1800765f7  push    r15
0x1800765f9  lea     rbp, [rsp-48h]
0x1800765fe  sub     rsp, 148h
0x180076605  mov     rax, cs:__security_cookie
0x18007660c  xor     rax, rsp
0x18007660f  mov     [rbp+80h+var_50], rax
0x180076613  mov     eax, [pChannel+58h]
0x180076616  xor     r13d, r13d
0x180076619  movzx   r15d, aItem
0x18007661d  mov     rdi, hDdeData
0x180076620  mov     rbx, pChannel
0x180076623  mov     [rsp+180h+iAdvOpt], r13d
0x180076628  mov     r14, this
0x18007662b  mov     [rsp+180h+dwFault], eax
0x18007662f  lea     r12d, [r13+1]
0x180076633  cmp     eax, r12d
0x180076636  jz      short loc_18007663D
0x180076638  cmp     eax, 8
0x18007663b  jnz     short loc_18007665C
0x18007663d  mov     rax, [pChannel+80h]
0x180076644  mov     [pChannel+58h], r13d
0x180076648  test    rax, rax
0x18007664b  jz      short loc_18007665C
0x18007664d  mov     [pChannel+88h], r13d
0x180076654  mov     [pChannel+5Ch], r13d
0x180076658  mov     [rax+2Ch], r12d
0x18007665c  lea     pChannel, [rsp+180h+iAdvOpt]; lpoptions
0x180076661  movzx   ecx, r15w; aItem
0x180076665  call    ?wScanItemOptions@@YAJGPEAH@Z; wScanItemOptions(ushort,int *)
0x18007666a  mov     esi, eax
0x18007666c  test    eax, eax
0x18007666e  jz      short loc_1800766A5
0x180076670  mov     r13d, 3E4h
0x180076676  mov     hDdeData, r15; uiHi
0x180076679  mov     ecx, r13d; msg
0x18007667c  xor     edx, edx; uiLo
0x18007667e  call    cs:__imp_PackDDElParam
0x180076684  mov     r9d, r12d; fFreeOnError
0x180076687  movzx   edx, r13w; wMsg
0x18007668b  mov     hDdeData, rax; lParam
0x18007668e  mov     this, rbx; pChannel
0x180076691  call    ?wPostMessageToServer@@YAHPEAVDDE_CHANNEL@@G_JH@Z; wPostMessageToServer(DDE_CHANNEL *,ushort,__int64,int)
0x180076696  test    eax, eax
0x180076698  mov     ecx, 80010007h
0x18007669d  cmovz   esi, ecx
0x1800766a0  jmp     loc_1800769B1
0x1800766a5  test    rdi, rdi
0x1800766a8  jnz     short loc_1800766B4
0x1800766aa  mov     eax, 80010010h
0x1800766af  jmp     loc_1800769B3
0x1800766b4  mov     this, rdi; hMem
0x1800766b7  call    cs:__imp_GlobalLock
0x1800766bd  mov     r12, rax
0x1800766c0  test    rax, rax
0x1800766c3  jnz     short loc_1800766CF
0x1800766c5  mov     eax, 8007000Eh
0x1800766ca  jmp     loc_1800769B3
0x1800766cf  mov     ecx, 8000h
0x1800766d4  movzx   eax, word ptr [rax]
0x1800766d7  mov     [rsp+180h+var_13C], ax
0x1800766dc  cmp     [rbx+28h], r13d
0x1800766e0  jz      short loc_1800766F9
0x1800766e2  mov     this, rdi; hMem
0x1800766e5  call    cs:__imp_GlobalUnlock
0x1800766eb  mov     this, rdi; hMem
0x1800766ee  call    cs:__imp_GlobalFree
0x1800766f4  jmp     $exitRtn_6
0x1800766f9  cmp     ax, cx
0x1800766fc  jb      short loc_180076738
0x1800766fe  mov     pChannel, this; uiLo
0x180076701  mov     r13d, 3E4h
0x180076707  mov     ecx, r13d; msg
0x18007670a  mov     hDdeData, r15; uiHi
0x18007670d  call    cs:__imp_PackDDElParam
0x180076713  mov     edx, r13d; wMsg
0x180076716  mov     r9d, 1; fFreeOnError
0x18007671c  mov     hDdeData, rax; lParam
0x18007671f  mov     this, rbx; pChannel
0x180076722  call    ?wPostMessageToServer@@YAHPEAVDDE_CHANNEL@@G_JH@Z; wPostMessageToServer(DDE_CHANNEL *,ushort,__int64,int)
0x180076727  xor     r13d, r13d
0x18007672a  test    eax, eax
0x18007672c  jnz     short loc_180076738
0x18007672e  mov     eax, 80010007h
0x180076733  jmp     loc_1800769B3
0x180076738  cmp     dword ptr [rbx+58h], 8
0x18007673c  mov     eax, 1000h
0x180076741  jnz     short loc_1800767AB
0x180076743  test    [r12], ax
0x180076748  jz      short loc_1800767AB
0x18007674a  mov     this, rdi; hMem
0x18007674d  call    cs:__imp_GlobalUnlock
0x180076753  mov     this, rdi; hMem
0x180076756  call    cs:__imp_GlobalLock
0x18007675c  mov     rbx, rax
0x18007675f  test    rax, rax
0x180076762  jz      loc_1800766C5
0x180076768  cmp     [rax], r13w
0x18007676c  jl      short loc_18007677E
0x18007676e  test    r15w, r15w
0x180076772  jz      short loc_18007677E
0x180076774  movzx   ecx, r15w; nAtom
0x180076778  call    cs:__imp_GlobalDeleteAtom
0x18007677e  movzx   ebx, word ptr [rbx+2]
0x180076782  mov     this, rdi; hMem
0x180076785  call    cs:__imp_GlobalUnlock
0x18007678b  mov     this, rdi; hDdeData
0x18007678e  call    ?wHandleFromDdeData@@YAPEAXPEAX@Z; wHandleFromDdeData(void *)
0x180076793  test    rax, rax
0x180076796  jz      short loc_1800767A3
0x180076798  movzx   edx, bx; cfFormat
0x18007679b  mov     this, rax; hData
0x18007679e  call    ?wFreeData@@YAXPEAXGH@Z; wFreeData(void *,ushort,int)
0x1800767a3  mov     eax, r13d
0x1800767a6  jmp     loc_1800769B3
0x1800767ab  movzx   eax, cs:?g_cfBinary@@3GA; ushort g_cfBinary
0x1800767b2  cmp     [r12+2], ax
0x1800767b8  jnz     short loc_1800767EA
0x1800767ba  cmp     r15w, cs:?aStdDocName@@3GA; ushort aStdDocName
0x1800767c2  jnz     short loc_1800767EA
0x1800767c4  lea     pChannel, [r12+4]; lpszTopic
0x1800767c9  mov     this, r14; this
0x1800767cc  call    ?ChangeTopic@CDdeObject@@AEAAJPEAD@Z; CDdeObject::ChangeTopic(char *)
0x1800767d1  mov     this, rdi; hMem
0x1800767d4  call    cs:__imp_GlobalUnlock
0x1800767da  mov     this, rdi; hMem
0x1800767dd  call    cs:__imp_GlobalFree
0x1800767e3  xor     eax, eax
0x1800767e5  jmp     loc_1800769B3
0x1800767ea  mov     [rsp+180h+var_140], r13d
0x1800767ef  mov     r13d, [rsp+180h+iAdvOpt]
0x1800767f4  mov     ecx, r13d
0x1800767f7  test    r13d, r13d
0x1800767fa  jz      short loc_180076821
0x1800767fc  sub     ecx, 1; this
0x1800767ff  jz      short loc_18007680F
0x180076801  cmp     ecx, 1
0x180076804  jnz     short loc_180076829
0x180076806  lea     pChannel, [r14+118h]
0x18007680d  jmp     short loc_180076816
0x18007680f  lea     pChannel, [r14+11Ch]; lpCount
0x180076816  call    ?CanCallBack@CDdeObject@@AEAAHPEAH@Z; CDdeObject::CanCallBack(int *)
0x18007681b  mov     [rsp+180h+var_140], eax
0x18007681f  jmp     short loc_180076829
0x180076821  mov     [rsp+180h+var_140], 1
0x180076829  movzx   r12d, word ptr [r12]
0x18007682e  mov     this, rdi; hMem
0x180076831  call    cs:__imp_GlobalUnlock
0x180076837  mov     hDdeData, rdi; void *
0x18007683a  mov     this, r14; this
0x18007683d  call    ?KeepData@CDdeObject@@AEAAJPEAVDDE_CHANNEL@@PEAX@Z; CDdeObject::KeepData(DDE_CHANNEL *,void *)
0x180076842  xor     edi, edi
0x180076844  mov     esi, eax
0x180076846  test    eax, eax
0x180076848  jz      short loc_180076885
0x18007684a  mov     eax, [rsp+180h+dwFault]
0x18007684e  cmp     eax, 1
0x180076851  jz      short loc_18007685C
0x180076853  cmp     eax, 8
0x180076856  jnz     $exitRtn_6
0x18007685c  mov     rax, [rbx+80h]
0x180076863  xor     r13d, r13d
0x180076866  test    rax, rax
0x180076869  jz      $exitRtn_6
0x18007686f  mov     [rbx+88h], r13d
0x180076876  mov     [rbx+5Ch], esi
0x180076879  mov     dword ptr [rax+2Ch], 1
0x180076880  jmp     $exitRtn_6
0x180076885  bt      r12w, 0Ch
0x18007688b  jnb     short loc_180076898
0x18007688d  xor     r13d, r13d
0x180076890  mov     esi, r13d
0x180076893  jmp     $exitRtn_6
0x180076898  mov     r12d, 1
0x18007689e  add     [rbx+10h], r12d
0x1800768a2  cmp     [rsp+180h+var_140], edi
0x1800768a6  jz      $errRel
0x1800768ac  test    r13d, r13d
0x1800768af  jz      loc_18007694E
0x1800768b5  xor     edx, edx; Val
0x1800768b7  mov     qword ptr [rsp+180h+ddedispdata.wDispFunc], r12
0x1800768bc  lea     r8d, [r12+4Fh]; Size
0x1800768c1  mov     dword ptr [rsp+180h+ddedispdata+14h], edi
0x1800768c5  lea     this, [rbp+80h+rpcMsg]; void *
0x1800768c9  mov     qword ptr [rsp+180h+dispatchdata.scode], rdi
0x1800768ce  mov     [rsp+180h+dwFault], edi
0x1800768d2  call    memset_0
0x1800768d7  xor     edx, edx; Val
0x1800768d9  lea     r8d, [r12+5Fh]; Size
0x1800768de  lea     this, [rbp+80h+RpcInterfaceInfo]; void *
0x1800768e2  call    memset_0
0x1800768e7  movups  xmm0, xmmword ptr cs:IID_IDataAdviseHolder.Data1
0x1800768ee  lea     rax, [rbp+80h+RpcInterfaceInfo]
0x1800768f2  mov     [rbp+80h+rpcMsg.cbBuffer], 10h
0x1800768f9  mov     [rbp+80h+rpcMsg.reserved2+8], rax
0x1800768fd  lea     hDdeData, [r14+68h]
0x180076901  lea     rax, [rsp+180h+dispatchdata]
0x180076906  mov     [rbp+80h+rpcMsg.iMethod], 6
0x18007690d  mov     [rbp+80h+rpcMsg.Buffer], rax
0x180076911  lea     this, [rbp+80h+rpcMsg]
0x180076915  lea     rax, [rsp+180h+ddedispdata]
0x18007691a  mov     [rsp+180h+ddedispdata.pCDdeObject], r14
0x18007691f  mov     [rsp+180h+dispatchdata.pData], rax
0x180076924  mov     r9, rbx
0x180076927  lea     rax, [rsp+180h+dwFault]
0x18007692c  mov     [rsp+180h+ddedispdata.iArg], r13d
0x180076931  mov     [rsp+180h+var_150], rax
0x180076936  mov     edx, r12d
0x180076939  mov     [rsp+180h+var_158], rdi
0x18007693e  mov     [rsp+180h+var_160], rdi
0x180076943  movdqu  xmmword ptr [rbp+80h+RpcInterfaceInfo.InterfaceId.SyntaxGUID.Data1], xmm0
0x180076948  call    cs:__imp_InternalSTAInvoke
0x18007694e  cmp     r13d, 2
0x180076952  jnz     short loc_18007696F
0x180076954  mov     hDdeData, rbx; pChannel
0x180076957  mov     [r14+0F8h], r12d
0x18007695e  mov     edx, r12d; iAdvOpt
0x180076961  mov     this, r14; this
0x180076964  call    ?OleCallBack@CDdeObject@@QEAAJHPEAVDDE_CHANNEL@@@Z; CDdeObject::OleCallBack(int,DDE_CHANNEL *)
0x180076969  mov     esi, eax
0x18007696b  test    eax, eax
0x18007696d  jnz     short $errRel
0x18007696f  mov     hDdeData, rbx; pChannel
0x180076972  mov     edx, r13d; iAdvOpt
0x180076975  mov     this, r14; this
0x180076978  call    ?OleCallBack@CDdeObject@@QEAAJHPEAVDDE_CHANNEL@@@Z; CDdeObject::OleCallBack(int,DDE_CHANNEL *)
0x18007697d  mov     esi, eax
0x18007697f  mov     this, rbx; this
0x180076982  call    ?ReleaseReference@DDE_CHANNEL@@QEAAKXZ; DDE_CHANNEL::ReleaseReference(void)
0x180076987  xor     r13d, r13d
0x18007698a  test    eax, eax
0x18007698c  jnz     short $exitRtn_6
0x18007698e  mov     [r14+158h], r13
0x180076995  mov     eax, 8000h
0x18007699a  cmp     [rsp+180h+var_13C], ax
0x18007699f  jnb     short loc_1800769B1
0x1800769a1  test    r15w, r15w
0x1800769a5  jz      short loc_1800769B1
0x1800769a7  movzx   ecx, r15w; nAtom
0x1800769ab  call    cs:__imp_GlobalDeleteAtom
0x1800769b1  mov     eax, esi
0x1800769b3  mov     this, [rbp+80h+var_50]
0x1800769b7  xor     this, rsp; StackCookie
0x1800769ba  call    __security_check_cookie
0x1800769bf  add     rsp, 148h
0x1800769c6  pop     r15
0x1800769c8  pop     r14
0x1800769ca  pop     r13
0x1800769cc  pop     r12
0x1800769ce  pop     rdi
0x1800769cf  pop     rsi
0x1800769d0  pop     rbx
0x1800769d1  pop     rbp
0x1800769d2  retn
```
