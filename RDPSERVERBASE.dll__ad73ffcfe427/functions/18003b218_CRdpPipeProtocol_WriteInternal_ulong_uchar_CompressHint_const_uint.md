# CRdpPipeProtocol::WriteInternal(ulong,uchar *,_CompressHint const *,uint)

- ea: `0x18003b218`
- end: `0x18003b648`
- name: `?WriteInternal@CRdpPipeProtocol@@IEAAJKPEAEPEBU_CompressHint@@I@Z`
- size: `1072`
- prototype: `__int64 __usercall@<rax>(CRdpPipeProtocol *__hidden this@<rcx>, unsigned int@<edx>, unsigned __int8 *@<r8>, const struct _CompressHint *@<r9>, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18003b190`

## callees

- `0x18000ce04`
- `0x180029e30`
- `0x18002aafc`
- `0x18002b14c`
- `0x18003b218`
- `0x180076090`
- `0x180079770`
- `0x180158180`
- `0x18019c010`

## import_xrefs

- `RDPBASE!?GetInstance@PipelineClock@@SAAEAV1@XZ` at `0x18003b2cb`
- `RDPBASE!?GetInstance@PipelineClock@@SAAEAV1@XZ` at `0x18003b394`
- `RDPBASE!?GetInstance@PipelineClock@@SAAEAV1@XZ` at `0x18003b2cb`
- `RDPBASE!?GetInstance@PipelineClock@@SAAEAV1@XZ` at `0x18003b394`
- `RDPBASE!?GetMillisecondCount@PipelineClock@@QEAAIXZ` at `0x18003b2d4`
- `RDPBASE!?GetMillisecondCount@PipelineClock@@QEAAIXZ` at `0x18003b39d`
- `RDPBASE!?GetMillisecondCount@PipelineClock@@QEAAIXZ` at `0x18003b2d4`
- `RDPBASE!?GetMillisecondCount@PipelineClock@@QEAAIXZ` at `0x18003b39d`

## string_xrefs

- `0x18003b3bd`: `IID_IRdpPipeProtocol`
- `0x18003b3e0`: `IID_IRdpPipeProtocol`
- `0x18003b473`: `IID_IRdpPipeProtocol`
- `0x18003b5e1`: `IID_IRdpPipeProtocol`
- `0x18003b434`: `Failed GetReadPtr on encoder buffer`
- `0x18003b3b0`: `BaseProtocolError_WriteInternalNullPointer`
- `0x18003b3d3`: `BaseProtocolError_WriteInternalCommitFail`
- `0x18003b421`: `Failed to commit encoder buffer`
- `0x18003b466`: `BaseProtocolError_WriteInternalGetReadPtrFail`
- `0x18003b5d4`: `BaseProtocolError_WriteInternalFlushFail`

## pseudocode

```c
__int64 __fastcall CRdpPipeProtocol::WriteInternal(
        CRdpPipeProtocol *this,
        unsigned int a2,
        unsigned __int8 *a3,
        const struct _CompressHint *a4,
        unsigned int a5)
{
  CTSCriticalSection *v5; // rsi
  __int64 v7; // rbx
  __int64 v10; // rdi
  __int64 v11; // rcx
  __int64 v12; // rcx
  signed int v13; // eax
  int v14; // esi
  unsigned int MillisecondCount; // ebp
  PipelineClock *v16; // rax
  signed int v17; // eax
  unsigned int v18; // r9d
  __int64 i; // r10
  PipelineClock *Instance; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v23; // edx
  const char *v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // r8
  unsigned int v27; // eax
  signed int v28; // eax
  unsigned int v29; // eax
  int v30; // [rsp+20h] [rbp-48h]
  __int64 v31; // [rsp+30h] [rbp-38h] BYREF
  __int64 v32; // [rsp+70h] [rbp+8h] BYREF
  unsigned int v33; // [rsp+80h] [rbp+18h] BYREF
  int v34; // [rsp+84h] [rbp+1Ch]

  v34 = HIDWORD(a3);
  v5 = (CRdpPipeProtocol *)((char *)this + 712);
  v7 = 0;
  v31 = 0;
  v33 = 0;
  v10 = 0;
  CTSCriticalSection::Lock((CRdpPipeProtocol *)((char *)this + 712));
  v11 = *((_QWORD *)this + 21);
  if ( v11 )
  {
    v7 = *((_QWORD *)this + 21);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
  }
  v12 = *((_QWORD *)this + 15);
  if ( v12 )
  {
    v10 = *((_QWORD *)this + 15);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
  }
  if ( v5 )
    CTSCriticalSection::UnLock(v5);
  if ( !v7 )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpPipeProtocol",
      "BaseProtocolError_WriteInternalNullPointer",
      (char *)0x7DD,
      0x80004003,
      v30);
    v14 = -2147418113;
    goto LABEL_16;
  }
  v13 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v7 + 40LL))(v7, a2);
  v14 = v13;
  if ( v13 < 0 )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpPipeProtocol",
      "BaseProtocolError_WriteInternalCommitFail",
      (char *)0x7E5,
      v13,
      v30);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_16;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v23 = 106;
    v24 = "Failed to commit encoder buffer";
LABEL_27:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v23,
      (unsigned int)&WPP_3bbb71033af43e0060aa7c269e4e67ad_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v24,
      v14);
    goto LABEL_16;
  }
  if ( *((_DWORD *)this + 187) )
  {
    Instance = (PipelineClock *)PipelineClock::GetInstance();
    MillisecondCount = PipelineClock::GetMillisecondCount(Instance);
  }
  else
  {
    MillisecondCount = 0;
    v16 = (PipelineClock *)PipelineClock::GetInstance();
    *((_DWORD *)this + 187) = PipelineClock::GetMillisecondCount(v16);
  }
  v17 = (*(__int64 (__fastcall **)(__int64, __int64 *, unsigned int *))(*(_QWORD *)v7 + 24LL))(v7, &v31, &v33);
  v14 = v17;
  if ( v17 < 0 )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpPipeProtocol",
      "BaseProtocolError_WriteInternalGetReadPtrFail",
      (char *)0x7F2,
      v17,
      v30);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_16;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v23 = 107;
    v24 = "Failed GetReadPtr on encoder buffer";
    goto LABEL_27;
  }
  v18 = a5;
  for ( i = 0;
        (unsigned int)i < v18;
        *((_DWORD *)this + 3 * (unsigned int)(*((_DWORD *)this + 956))++ + 208) = *((_DWORD *)a4 + v26 + 2) )
  {
    v25 = *((unsigned int *)this + 956);
    if ( (unsigned int)v25 >= 0xFA )
      break;
    v26 = 3 * i;
    i = (unsigned int)(i + 1);
    *((_DWORD *)this + 3 * v25 + 206) = v33 + *((_DWORD *)a4 + v26) - a2;
    *((_DWORD *)this + 3 * *((unsigned int *)this + 956) + 207) = *((_DWORD *)a4 + v26 + 1);
  }
  if ( *((_DWORD *)this + 956) >= 0xFAu || v33 > 0x4000 || MillisecondCount > *((_DWORD *)this + 187) + 20 )
  {
    v32 = 0;
    if ( !v10 )
      goto LABEL_43;
    v14 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v10)(v10, &IID_IRdpPipeManager, &v32);
    if ( v14 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v27 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        108,
        (unsigned int)&WPP_3bbb71033af43e0060aa7c269e4e67ad_Traceguids,
        v27,
        (__int64)"Failed to QI for the pipe manager",
        v14);
    }
    if ( !v32 || (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v32 + 232LL))(v32) )
    {
LABEL_43:
      v28 = CRdpPipeProtocol::Flush(this);
      v14 = v28;
      if ( v28 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpPipeProtocol",
          "BaseProtocolError_WriteInternalFlushFail",
          (char *)0x817,
          v28,
          v30);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v29 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            109,
            (unsigned int)&WPP_3bbb71033af43e0060aa7c269e4e67ad_Traceguids,
            v29,
            (__int64)"Failed to flush encoder buffer",
            v14);
        }
      }
    }
    TCntPtr<IRdpVCMgr>::SafeRelease(&v32);
  }
LABEL_16:
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18003b218  mov     rax, rsp
0x18003b21b  mov     [rax+10h], rbx
0x18003b21f  mov     [rax+20h], rbp
0x18003b223  mov     [rax+18h], r8
0x18003b227  push    rsi
0x18003b228  push    rdi
0x18003b229  push    r12
0x18003b22b  push    r14
0x18003b22d  push    r15
0x18003b22f  sub     rsp, 40h
0x18003b233  lea     rsi, [rcx+2C8h]
0x18003b23a  mov     r14, rcx
0x18003b23d  xor     ebx, ebx
0x18003b23f  mov     rcx, rsi; this
0x18003b242  mov     r12, r9
0x18003b245  mov     [rax-38h], rbx
0x18003b249  mov     r15d, edx
0x18003b24c  mov     [rax+18h], ebx
0x18003b24f  xor     edi, edi
0x18003b251  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x18003b256  mov     rcx, [r14+0A8h]
0x18003b25d  test    rcx, rcx
0x18003b260  jz      short loc_18003B271
0x18003b262  mov     rax, [rcx]
0x18003b265  mov     rbx, rcx
0x18003b268  mov     rax, [rax+8]
0x18003b26c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b271  mov     rcx, [r14+78h]
0x18003b275  test    rcx, rcx
0x18003b278  jz      short loc_18003B289
0x18003b27a  mov     rax, [rcx]
0x18003b27d  mov     rdi, rcx
0x18003b280  mov     rax, [rax+8]
0x18003b284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b289  test    rsi, rsi
0x18003b28c  jz      short loc_18003B296
0x18003b28e  mov     rcx, rsi; this
0x18003b291  call    ?UnLock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::UnLock(void)
0x18003b296  test    rbx, rbx
0x18003b299  jz      loc_18003B3AA
0x18003b29f  mov     rax, [rbx]
0x18003b2a2  mov     edx, r15d
0x18003b2a5  mov     rcx, rbx
0x18003b2a8  mov     rax, [rax+28h]
0x18003b2ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b2b1  mov     esi, eax
0x18003b2b3  test    eax, eax
0x18003b2b5  js      loc_18003B3D0
0x18003b2bb  cmp     dword ptr [r14+2ECh], 0
0x18003b2c3  jnz     loc_18003B394
0x18003b2c9  xor     ebp, ebp
0x18003b2cb  call    cs:__imp_?GetInstance@PipelineClock@@SAAEAV1@XZ; PipelineClock::GetInstance(void)
0x18003b2d1  mov     rcx, rax
0x18003b2d4  call    cs:__imp_?GetMillisecondCount@PipelineClock@@QEAAIXZ; PipelineClock::GetMillisecondCount(void)
0x18003b2da  mov     [r14+2ECh], eax
0x18003b2e1  mov     rcx, [rbx]
0x18003b2e4  lea     r8, [rsp+68h+arg_10]
0x18003b2ec  lea     rdx, [rsp+68h+var_38]
0x18003b2f1  mov     rax, [rcx+18h]
0x18003b2f5  mov     rcx, rbx
0x18003b2f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b2fd  mov     esi, eax
0x18003b2ff  test    eax, eax
0x18003b301  js      loc_18003B463
0x18003b307  mov     r9d, [rsp+68h+arg_20]
0x18003b30f  xor     r10d, r10d
0x18003b312  mov     r11d, 0FAh
0x18003b318  test    r9d, r9d
0x18003b31b  jnz     loc_18003B4AF
0x18003b321  cmp     [r14+0EF0h], r11d
0x18003b328  jnb     loc_18003B521
0x18003b32e  cmp     [rsp+68h+arg_10], 4000h
0x18003b339  ja      loc_18003B521
0x18003b33f  mov     eax, [r14+2ECh]
0x18003b346  add     eax, 14h
0x18003b349  cmp     ebp, eax
0x18003b34b  ja      loc_18003B521
0x18003b351  test    rdi, rdi
0x18003b354  jz      short loc_18003B365
0x18003b356  mov     rax, [rdi]
0x18003b359  mov     rcx, rdi
0x18003b35c  mov     rax, [rax+10h]
0x18003b360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b365  test    rbx, rbx
0x18003b368  jz      short loc_18003B379
0x18003b36a  mov     rax, [rbx]
0x18003b36d  mov     rcx, rbx
0x18003b370  mov     rax, [rax+10h]
0x18003b374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b379  lea     r11, [rsp+68h+var_28]
0x18003b37e  mov     eax, esi
0x18003b380  mov     rbx, [r11+38h]
0x18003b384  mov     rbp, [r11+48h]
0x18003b388  mov     rsp, r11
0x18003b38b  pop     r15
0x18003b38d  pop     r14
0x18003b38f  pop     r12
0x18003b391  pop     rdi
0x18003b392  pop     rsi
0x18003b393  retn
0x18003b394  call    cs:__imp_?GetInstance@PipelineClock@@SAAEAV1@XZ; PipelineClock::GetInstance(void)
0x18003b39a  mov     rcx, rax
0x18003b39d  call    cs:__imp_?GetMillisecondCount@PipelineClock@@QEAAIXZ; PipelineClock::GetMillisecondCount(void)
0x18003b3a3  mov     ebp, eax
0x18003b3a5  jmp     loc_18003B2E1
0x18003b3aa  mov     r9d, 80004003h; unsigned int
0x18003b3b0  lea     rdx, aBaseprotocoler_36; "BaseProtocolError_WriteInternalNullPoin"...
0x18003b3b7  mov     r8d, 7DDh; char *
0x18003b3bd  lea     rcx, aIidIrdppipepro; "IID_IRdpPipeProtocol"
0x18003b3c4  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18003b3c9  mov     esi, 8000FFFFh
0x18003b3ce  jmp     short loc_18003B351
0x18003b3d0  mov     r9d, esi; unsigned int
0x18003b3d3  lea     rdx, aBaseprotocoler_46; "BaseProtocolError_WriteInternalCommitFa"...
0x18003b3da  mov     r8d, 7E5h; char *
0x18003b3e0  lea     rcx, aIidIrdppipepro; "IID_IRdpPipeProtocol"
0x18003b3e7  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18003b3ec  mov     rax, cs:WPP_GLOBAL_Control
0x18003b3f3  lea     rbp, WPP_GLOBAL_Control
0x18003b3fa  cmp     rax, rbp
0x18003b3fd  jz      loc_18003B351
0x18003b403  test    byte ptr [rax+1Ch], 8
0x18003b407  jz      loc_18003B351
0x18003b40d  cmp     byte ptr [rax+19h], 2
0x18003b411  jb      loc_18003B351
0x18003b417  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003b41c  mov     edx, 6Ah ; 'j'
0x18003b421  lea     rcx, aFailedToCommit; "Failed to commit encoder buffer"
0x18003b428  jmp     short loc_18003B43B
0x18003b42a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003b42f  mov     edx, 6Bh ; 'k'
0x18003b434  lea     rcx, aFailedGetreadp; "Failed GetReadPtr on encoder buffer"
0x18003b43b  mov     [rsp+68h+var_40], esi
0x18003b43f  lea     r8, WPP_3bbb71033af43e0060aa7c269e4e67ad_Traceguids
0x18003b446  mov     qword ptr [rsp+68h+var_48], rcx
0x18003b44b  mov     r9d, eax
0x18003b44e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b455  mov     rcx, [rcx+10h]
0x18003b459  call    WPP_SF_DsD
0x18003b45e  jmp     loc_18003B351
0x18003b463  mov     r9d, esi; unsigned int
0x18003b466  lea     rdx, aBaseprotocoler_29; "BaseProtocolError_WriteInternalGetReadP"...
0x18003b46d  mov     r8d, 7F2h; char *
0x18003b473  lea     rcx, aIidIrdppipepro; "IID_IRdpPipeProtocol"
0x18003b47a  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18003b47f  mov     rax, cs:WPP_GLOBAL_Control
0x18003b486  lea     rbp, WPP_GLOBAL_Control
0x18003b48d  cmp     rax, rbp
0x18003b490  jz      loc_18003B351
0x18003b496  test    byte ptr [rax+1Ch], 8
0x18003b49a  jz      loc_18003B351
0x18003b4a0  cmp     byte ptr [rax+19h], 2
0x18003b4a4  jb      loc_18003B351
0x18003b4aa  jmp     loc_18003B42A
0x18003b4af  mov     ecx, [r14+0EF0h]
0x18003b4b6  cmp     ecx, r11d
0x18003b4b9  jnb     loc_18003B321
0x18003b4bf  lea     r8, [r10+r10*2]
0x18003b4c3  inc     r10d
0x18003b4c6  mov     edx, [r12+r8*4]
0x18003b4ca  lea     rcx, [rcx+rcx*2]
0x18003b4ce  sub     edx, r15d
0x18003b4d1  add     edx, [rsp+68h+arg_10]
0x18003b4d8  mov     [r14+rcx*4+338h], edx
0x18003b4e0  mov     eax, [r14+0EF0h]
0x18003b4e7  add     rax, 45h ; 'E'
0x18003b4eb  lea     rcx, [rax+rax*2]
0x18003b4ef  mov     eax, [r12+r8*4+4]
0x18003b4f4  mov     [r14+rcx*4], eax
0x18003b4f8  mov     eax, [r14+0EF0h]
0x18003b4ff  lea     rcx, [rax+rax*2]
0x18003b503  mov     eax, [r12+r8*4+8]
0x18003b508  mov     [r14+rcx*4+340h], eax
0x18003b510  inc     dword ptr [r14+0EF0h]
0x18003b517  cmp     r10d, r9d
0x18003b51a  jb      short loc_18003B4AF
0x18003b51c  jmp     loc_18003B321
0x18003b521  mov     [rsp+68h+arg_0], 0
0x18003b52a  lea     rbp, WPP_GLOBAL_Control
0x18003b531  test    rdi, rdi
0x18003b534  jz      loc_18003B5C3
0x18003b53a  mov     rax, [rdi]
0x18003b53d  lea     r8, [rsp+68h+arg_0]
0x18003b542  lea     rdx, IID_IRdpPipeManager
0x18003b549  mov     rcx, rdi
0x18003b54c  mov     rax, [rax]
0x18003b54f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b554  mov     esi, eax
0x18003b556  test    eax, eax
0x18003b558  jns     short loc_18003B5A6
0x18003b55a  mov     rax, cs:WPP_GLOBAL_Control
0x18003b561  cmp     rax, rbp
0x18003b564  jz      short loc_18003B5A6
0x18003b566  test    byte ptr [rax+1Ch], 8
0x18003b56a  jz      short loc_18003B5A6
0x18003b56c  cmp     byte ptr [rax+19h], 2
0x18003b570  jb      short loc_18003B5A6
0x18003b572  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003b577  lea     rcx, aFailedToQiForT; "Failed to QI for the pipe manager"
0x18003b57e  mov     [rsp+68h+var_40], esi
0x18003b582  mov     qword ptr [rsp+68h+var_48], rcx; int
0x18003b587  lea     r8, WPP_3bbb71033af43e0060aa7c269e4e67ad_Traceguids
0x18003b58e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b595  mov     edx, 6Ch ; 'l'
0x18003b59a  mov     r9d, eax
0x18003b59d  mov     rcx, [rcx+10h]
0x18003b5a1  call    WPP_SF_DsD
0x18003b5a6  mov     rcx, [rsp+68h+arg_0]
0x18003b5ab  test    rcx, rcx
0x18003b5ae  jz      short loc_18003B5C3
0x18003b5b0  mov     rax, [rcx]
0x18003b5b3  mov     rax, [rax+0E8h]
0x18003b5ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b5bf  test    eax, eax
0x18003b5c1  jz      short loc_18003B639
0x18003b5c3  mov     rcx, r14; this
0x18003b5c6  call    ?Flush@CRdpPipeProtocol@@UEAAJXZ; CRdpPipeProtocol::Flush(void)
0x18003b5cb  mov     esi, eax
0x18003b5cd  test    eax, eax
0x18003b5cf  jns     short loc_18003B639
0x18003b5d1  mov     r9d, eax; unsigned int
0x18003b5d4  lea     rdx, aBaseprotocoler_37; "BaseProtocolError_WriteInternalFlushFai"...
0x18003b5db  mov     r8d, 817h; char *
0x18003b5e1  lea     rcx, aIidIrdppipepro; "IID_IRdpPipeProtocol"
0x18003b5e8  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18003b5ed  mov     rax, cs:WPP_GLOBAL_Control
0x18003b5f4  cmp     rax, rbp
0x18003b5f7  jz      short loc_18003B639
0x18003b5f9  test    byte ptr [rax+1Ch], 8
0x18003b5fd  jz      short loc_18003B639
0x18003b5ff  cmp     byte ptr [rax+19h], 2
0x18003b603  jb      short loc_18003B639
0x18003b605  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003b60a  lea     rcx, aFailedToFlushE_0; "Failed to flush encoder buffer"
0x18003b611  mov     [rsp+68h+var_40], esi
0x18003b615  mov     qword ptr [rsp+68h+var_48], rcx
0x18003b61a  lea     r8, WPP_3bbb71033af43e0060aa7c269e4e67ad_Traceguids
0x18003b621  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b628  mov     edx, 6Dh ; 'm'
0x18003b62d  mov     r9d, eax
0x18003b630  mov     rcx, [rcx+10h]
0x18003b634  call    WPP_SF_DsD
0x18003b639  lea     rcx, [rsp+68h+arg_0]
0x18003b63e  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x18003b643  jmp     loc_18003B351
```
