# CFileDownloadDMChannelNode::CreateNodeInstance(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *,int,ICSPNode * *,ulong *)

- ea: `0x1800099a0`
- end: `0x180009c1c`
- name: `?CreateNodeInstance@CFileDownloadDMChannelNode@@SAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@HPEAPEAUICSPNode@@PEAK@Z`
- size: `636`
- prototype: `static int(struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *, int, struct ICSPNode **, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001090`
- `0x180002bb8`
- `0x1800092f8`
- `0x1800099a0`
- `0x180009c24`
- `0x180011fe0`
- `0x180012774`
- `0x180039010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFileDownloadDMChannelNode::CreateNodeInstance(
        struct CConfigServiceProvider2Impl *a1,
        struct IConfigManager2URI *a2,
        const struct CSP_NODE_DATA *a3,
        __int64 a4,
        struct ICSPNode **a5,
        unsigned int *a6)
{
  struct ICSPNode *v9; // rdi
  struct ICSPNode **v10; // r15
  unsigned int *v11; // rax
  int BlockNumber; // ebx
  struct ICSPNode *v13; // rax
  int v14; // eax
  int v16; // [rsp+30h] [rbp-30h] BYREF
  int v17; // [rsp+34h] [rbp-2Ch] BYREF
  unsigned __int16 *v18; // [rsp+38h] [rbp-28h] BYREF
  _OWORD v19[2]; // [rsp+40h] [rbp-20h] BYREF
  struct ICSPNode *v20; // [rsp+90h] [rbp+30h] BYREF

  v17 = 0;
  v9 = 0;
  if ( a1 && a2 && a3 && (v10 = a5) != 0 && (v11 = a6) != 0 )
  {
    *a5 = 0;
    *v11 = 0;
    if ( (_DWORD)a4 )
    {
      BlockNumber = -2046820335;
      goto LABEL_33;
    }
    if ( !*((_DWORD *)a3 + 6) )
    {
      v18 = 0;
      BlockNumber = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, __int64, unsigned __int16 **))(*(_QWORD *)a2 + 88LL))(
                      a2,
                      3,
                      &v18);
      if ( BlockNumber < 0 )
        goto LABEL_33;
      memset(v19, 0, sizeof(v19));
      if ( (int)CFileDownload_DMChannel::Initialize((CFileDownload_DMChannel *)v19, v18) < 0 )
        goto LABEL_11;
      if ( *((_DWORD *)a3 + 3) != 22
        && *((_DWORD *)a3 + 3) != 23
        && *((_DWORD *)a3 + 3) != 24
        && *((_DWORD *)a3 + 3) != 25
        && *((_DWORD *)a3 + 3) != 26
        && *((_DWORD *)a3 + 3) != 27 )
      {
        if ( *((_DWORD *)a3 + 3) != 28 )
          goto LABEL_11;
        LODWORD(v20) = 0;
        v16 = 0;
        BlockNumber = CFileDownloadDMChannelNode::GetBlockNumber(a2, (int *)&v20);
        if ( BlockNumber < 0 )
          goto LABEL_12;
        BlockNumber = CFileDownload_DMChannel::GetBlockCount((CFileDownload_DMChannel *)v19, (DWORD *)&v16);
        if ( BlockNumber < 0 )
          goto LABEL_12;
        if ( (int)v20 < 0 || (int)v20 >= v16 )
        {
LABEL_11:
          BlockNumber = -2046820350;
LABEL_12:
          CFileDownload_DMChannel::~CFileDownload_DMChannel((CFileDownload_DMChannel *)v19);
          goto LABEL_33;
        }
      }
      CFileDownload_DMChannel::~CFileDownload_DMChannel((CFileDownload_DMChannel *)v19);
    }
    BlockNumber = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, int *))(*(_QWORD *)a2 + 136LL))(a2, &v17);
    if ( BlockNumber >= 0 )
    {
      if ( *((_DWORD *)a3 + 2) + 1 == v17 )
      {
        v13 = (struct ICSPNode *)operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
        v9 = v13;
        v20 = v13;
        if ( v13 )
        {
          *((_QWORD *)v13 + 2) = 0;
          *((_QWORD *)v13 + 3) = 0;
          *((_DWORD *)v13 + 16) = 1;
          *((_OWORD *)v13 + 2) = 0;
          *((_OWORD *)v13 + 3) = 0;
          *(_QWORD *)v13 = &CFileDownloadDMChannelNode::`vftable'{for `ICSPNode'};
          *((_QWORD *)v13 + 1) = &CDiagnosticLogNode::`vftable'{for `ICSPNodeTransactioning'};
          _InterlockedIncrement(&dword_18004B4E0);
          BlockNumber = (*(__int64 (__fastcall **)(struct ICSPNode *, struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *))(*(_QWORD *)v13 + 136LL))(
                          v13,
                          a1,
                          a2,
                          a3);
          if ( BlockNumber >= 0 )
          {
            *v10 = v9;
            v9 = 0;
          }
        }
        else
        {
          v9 = 0;
          BlockNumber = -2147024882;
        }
      }
      else
      {
        BlockNumber = -2147418113;
      }
    }
  }
  else
  {
    BlockNumber = -2147024809;
  }
LABEL_33:
  if ( (unsigned int)dword_18004AE90 > 5 )
  {
    LODWORD(v20) = BlockNumber;
    if ( a3 )
      v14 = *((_DWORD *)a3 + 3);
    else
      v14 = -1;
    v16 = v14;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)a1,
      (unsigned __int8 *)&word_180040DCE,
      (__int64)a3,
      a4,
      (__int64)&v16,
      (__int64)&v20);
  }
  if ( v9 )
    (*(void (__fastcall **)(struct ICSPNode *))(*(_QWORD *)v9 + 16LL))(v9);
  return (unsigned int)BlockNumber;
}

```

## disassembly

```asm
0x1800099a0  mov     [rsp-28h+arg_8], rbx
0x1800099a5  mov     [rsp-28h+arg_10], rsi
0x1800099aa  push    rbp
0x1800099ab  push    rdi
0x1800099ac  push    r12
0x1800099ae  push    r14
0x1800099b0  push    r15
0x1800099b2  mov     rbp, rsp
0x1800099b5  sub     rsp, 60h
0x1800099b9  mov     rsi, r8
0x1800099bc  mov     r14, rdx
0x1800099bf  mov     r12, rcx
0x1800099c2  mov     [rbp+var_2C], 0
0x1800099c9  xor     edi, edi
0x1800099cb  test    rcx, rcx
0x1800099ce  jz      loc_180009BAB
0x1800099d4  test    rdx, rdx
0x1800099d7  jz      loc_180009BAB
0x1800099dd  test    r8, r8
0x1800099e0  jz      loc_180009BAB
0x1800099e6  mov     r15, [rbp+arg_20]
0x1800099ea  test    r15, r15
0x1800099ed  jz      loc_180009BAB
0x1800099f3  mov     rax, [rbp+arg_28]
0x1800099f7  test    rax, rax
0x1800099fa  jz      loc_180009BAB
0x180009a00  mov     [r15], rdi
0x180009a03  mov     [rax], edi
0x180009a05  test    r9d, r9d
0x180009a08  jz      short loc_180009A14
0x180009a0a  mov     ebx, 86000011h
0x180009a0f  jmp     loc_180009BB0
0x180009a14  cmp     [r8+18h], edi
0x180009a18  jnz     loc_180009AE6
0x180009a1e  mov     [rbp+var_28], rdi
0x180009a22  mov     rax, [rdx]
0x180009a25  lea     r8, [rbp+var_28]
0x180009a29  mov     edx, 3
0x180009a2e  mov     rcx, r14
0x180009a31  mov     rax, [rax+58h]
0x180009a35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a3a  mov     ebx, eax
0x180009a3c  test    eax, eax
0x180009a3e  js      loc_180009BB0
0x180009a44  xorps   xmm0, xmm0
0x180009a47  movdqu  [rbp+var_20], xmm0
0x180009a4c  xorps   xmm1, xmm1
0x180009a4f  movdqu  [rbp+var_10], xmm1
0x180009a54  mov     rdx, [rbp+var_28]; unsigned __int16 *
0x180009a58  lea     rcx, [rbp+var_20]; this
0x180009a5c  call    ?Initialize@CFileDownload_DMChannel@@QEAAJPEBG@Z; CFileDownload_DMChannel::Initialize(ushort const *)
0x180009a61  test    eax, eax
0x180009a63  jns     short loc_180009A78
0x180009a65  mov     ebx, 86000002h
0x180009a6a  lea     rcx, [rbp+var_20]; this
0x180009a6e  call    ??1CFileDownload_DMChannel@@QEAA@XZ; CFileDownload_DMChannel::~CFileDownload_DMChannel(void)
0x180009a73  jmp     loc_180009BB0
0x180009a78  mov     ecx, [rsi+0Ch]
0x180009a7b  sub     ecx, 16h
0x180009a7e  jz      short loc_180009ADD
0x180009a80  sub     ecx, 1
0x180009a83  jz      short loc_180009ADD
0x180009a85  sub     ecx, 1
0x180009a88  jz      short loc_180009ADD
0x180009a8a  sub     ecx, 1
0x180009a8d  jz      short loc_180009ADD
0x180009a8f  sub     ecx, 1
0x180009a92  jz      short loc_180009ADD
0x180009a94  sub     ecx, 1
0x180009a97  jz      short loc_180009ADD
0x180009a99  cmp     ecx, 1
0x180009a9c  jnz     short loc_180009A65
0x180009a9e  mov     dword ptr [rbp+arg_0], 0
0x180009aa5  mov     [rbp+var_30], 0
0x180009aac  lea     rdx, [rbp+arg_0]; int *
0x180009ab0  mov     rcx, r14; struct IConfigManager2URI *
0x180009ab3  call    ?GetBlockNumber@CFileDownloadDMChannelNode@@KAJPEAUIConfigManager2URI@@AEAH@Z; CFileDownloadDMChannelNode::GetBlockNumber(IConfigManager2URI *,int &)
0x180009ab8  mov     ebx, eax
0x180009aba  test    eax, eax
0x180009abc  js      short loc_180009A6A
0x180009abe  lea     rdx, [rbp+var_30]; int *
0x180009ac2  lea     rcx, [rbp+var_20]; this
0x180009ac6  call    ?GetBlockCount@CFileDownload_DMChannel@@QEAAJAEAJ@Z; CFileDownload_DMChannel::GetBlockCount(long &)
0x180009acb  mov     ebx, eax
0x180009acd  test    eax, eax
0x180009acf  js      short loc_180009A6A
0x180009ad1  mov     eax, dword ptr [rbp+arg_0]
0x180009ad4  test    eax, eax
0x180009ad6  js      short loc_180009A65
0x180009ad8  cmp     eax, [rbp+var_30]
0x180009adb  jge     short loc_180009A65
0x180009add  lea     rcx, [rbp+var_20]; this
0x180009ae1  call    ??1CFileDownload_DMChannel@@QEAA@XZ; CFileDownload_DMChannel::~CFileDownload_DMChannel(void)
0x180009ae6  mov     rax, [r14]
0x180009ae9  lea     rdx, [rbp+var_2C]
0x180009aed  mov     rcx, r14
0x180009af0  mov     rax, [rax+88h]
0x180009af7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009afc  mov     ebx, eax
0x180009afe  test    eax, eax
0x180009b00  js      loc_180009BB0
0x180009b06  mov     eax, [rsi+8]
0x180009b09  inc     eax
0x180009b0b  cmp     eax, [rbp+var_2C]
0x180009b0e  jz      short loc_180009B1A
0x180009b10  mov     ebx, 8000FFFFh
0x180009b15  jmp     loc_180009BB0
0x180009b1a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009b21  mov     ecx, 48h ; 'H'; unsigned __int64
0x180009b26  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009b2b  mov     rdi, rax
0x180009b2e  mov     [rbp+arg_0], rax
0x180009b32  test    rax, rax
0x180009b35  jz      short loc_180009BA2
0x180009b37  mov     qword ptr [rax+10h], 0
0x180009b3f  mov     qword ptr [rax+18h], 0
0x180009b47  mov     dword ptr [rax+40h], 1
0x180009b4e  xorps   xmm0, xmm0
0x180009b51  movups  xmmword ptr [rax+20h], xmm0
0x180009b55  movups  xmmword ptr [rax+30h], xmm0
0x180009b59  lea     rax, ??_7CFileDownloadDMChannelNode@@6BICSPNode@@@; const CFileDownloadDMChannelNode::`vftable'{for `ICSPNode'}
0x180009b60  mov     [rdi], rax
0x180009b63  lea     rax, ??_7CDiagnosticLogNode@@6BICSPNodeTransactioning@@@; const CDiagnosticLogNode::`vftable'{for `ICSPNodeTransactioning'}
0x180009b6a  mov     [rdi+8], rax
0x180009b6e  lock inc cs:dword_18004B4E0
0x180009b75  test    rdi, rdi
0x180009b78  jz      short loc_180009BA4
0x180009b7a  mov     rax, [rdi]
0x180009b7d  mov     r9, rsi
0x180009b80  mov     r8, r14
0x180009b83  mov     rdx, r12
0x180009b86  mov     rcx, rdi
0x180009b89  mov     rax, [rax+88h]
0x180009b90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b95  mov     ebx, eax
0x180009b97  test    eax, eax
0x180009b99  js      short loc_180009BB0
0x180009b9b  mov     [r15], rdi
0x180009b9e  xor     edi, edi
0x180009ba0  jmp     short loc_180009BB0
0x180009ba2  xor     edi, edi
0x180009ba4  mov     ebx, 8007000Eh
0x180009ba9  jmp     short loc_180009BB0
0x180009bab  mov     ebx, 80070057h
0x180009bb0  mov     eax, cs:dword_18004AE90
0x180009bb6  cmp     eax, 5
0x180009bb9  jbe     short loc_180009BEC
0x180009bbb  mov     dword ptr [rbp+arg_0], ebx
0x180009bbe  test    rsi, rsi
0x180009bc1  jz      short loc_180009BC8
0x180009bc3  mov     eax, [rsi+0Ch]
0x180009bc6  jmp     short loc_180009BCB
0x180009bc8  or      eax, 0FFFFFFFFh
0x180009bcb  mov     [rbp+var_30], eax
0x180009bce  lea     rax, [rbp+arg_0]
0x180009bd2  mov     [rsp+60h+var_38], rax
0x180009bd7  lea     rax, [rbp+var_30]
0x180009bdb  mov     [rsp+60h+var_40], rax
0x180009be0  lea     rdx, word_180040DCE
0x180009be7  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180009bec  test    rdi, rdi
0x180009bef  jz      short loc_180009C00
0x180009bf1  mov     rax, [rdi]
0x180009bf4  mov     rcx, rdi
0x180009bf7  mov     rax, [rax+10h]
0x180009bfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c00  mov     eax, ebx
0x180009c02  lea     r11, [rsp+60h+var_s0]
0x180009c07  mov     rbx, [r11+38h]
0x180009c0b  mov     rsi, [r11+40h]
0x180009c0f  mov     rsp, r11
0x180009c12  pop     r15
0x180009c14  pop     r14
0x180009c16  pop     r12
0x180009c18  pop     rdi
0x180009c19  pop     rbp
0x180009c1a  retn
```
