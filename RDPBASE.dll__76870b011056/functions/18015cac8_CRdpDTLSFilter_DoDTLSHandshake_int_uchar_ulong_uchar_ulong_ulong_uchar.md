# CRdpDTLSFilter::DoDTLSHandshake(int,uchar *,ulong,uchar * *,ulong *,ulong *,uchar *)

- ea: `0x18015cac8`
- end: `0x18015cf58`
- name: `?DoDTLSHandshake@CRdpDTLSFilter@@QEAAJHPEAEKPEAPEAEPEAK20@Z`
- size: `1168`
- prototype: `__int64 __usercall@<rax>(CRdpDTLSFilter *__hidden this@<rcx>, int@<edx>, unsigned __int8 *@<r8>, unsigned int@<r9d>, unsigned __int8 **, unsigned int *, unsigned int *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800fa994`

## callees

- `0x1800711c8`
- `0x180071a60`
- `0x1800721d4`
- `0x180078c20`
- `0x180079624`
- `0x18007969c`
- `0x18015cac8`
- `0x18015dc60`
- `0x18015dec0`
- `0x180162010`

## import_xrefs

- `SspiCli!AcceptSecurityContext` at `0x18015cc5e`
- `SspiCli!AcceptSecurityContext` at `0x18015cc5e`
- `SspiCli!InitializeSecurityContextW` at `0x18015ccce`
- `SspiCli!InitializeSecurityContextW` at `0x18015ccce`
- `SspiCli!FreeContextBuffer` at `0x18015cd04`
- `SspiCli!FreeContextBuffer` at `0x18015cf19`
- `SspiCli!FreeContextBuffer` at `0x18015cd04`
- `SspiCli!FreeContextBuffer` at `0x18015cf19`

## string_xrefs

- `0x18015ce4c`: `OnHandshakeCompleted`

## pseudocode

```c
__int64 __fastcall CRdpDTLSFilter::DoDTLSHandshake(
        CRdpDTLSFilter *this,
        int a2,
        unsigned __int8 *a3,
        unsigned int a4,
        unsigned __int8 **a5,
        unsigned int *a6,
        unsigned int *a7,
        unsigned __int8 *a8)
{
  unsigned int v9; // eax
  signed int v10; // ebx
  unsigned int v11; // esi
  struct _SecHandle *v12; // rdx
  struct _SecHandle *v13; // rax
  SECURITY_STATUS v14; // eax
  struct _SecHandle *v15; // rax
  bool v16; // sf
  __int64 v17; // rdx
  __int64 v18; // r8
  int ActivityIdPrefix; // eax
  int v20; // edx
  const char *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rdx
  __int64 v25; // r8
  unsigned int v26; // eax
  unsigned int v27; // eax
  const void *v28; // r8
  rsize_t v29; // rdx
  unsigned int pfContextAttr; // [rsp+60h] [rbp-A0h] BYREF
  SECURITY_INTEGER ptsExpiry; // [rsp+68h] [rbp-98h] BYREF
  struct _SecBufferDesc pOutput; // [rsp+70h] [rbp-90h] BYREF
  struct _SecBufferDesc pInput; // [rsp+80h] [rbp-80h] BYREF
  _BYTE Size[20]; // [rsp+90h] [rbp-70h] BYREF
  PVOID pvContextBuffer[2]; // [rsp+A4h] [rbp-5Ch]
  _BYTE v37[28]; // [rsp+B4h] [rbp-4Ch]
  _QWORD v38[8]; // [rsp+D0h] [rbp-30h] BYREF

  *(_OWORD *)v37 = 0;
  *a8 = 0;
  v9 = 0;
  pfContextAttr = 0;
  ptsExpiry.QuadPart = 0;
  *(_OWORD *)&Size[4] = 0;
  memset(v38, 0, sizeof(v38));
  *(_OWORD *)pvContextBuffer = 0;
  *(_OWORD *)&v37[12] = 0;
  *((_DWORD *)this + 17) = 2;
  if ( !a5 || !a6 )
  {
    v10 = -2147024809;
    goto LABEL_65;
  }
  if ( a2 )
  {
    if ( ++*((_DWORD *)this + 36) > 0x28u )
    {
      v10 = -2147467259;
LABEL_65:
      *((_DWORD *)this + 52) = v10;
      *((_DWORD *)this + 34) = 9;
      return (unsigned int)v10;
    }
  }
  if ( a3 )
  {
    v9 = 2;
    v38[0] = a4 | 0x200000000LL;
    *(_OWORD *)&v38[1] = (unsigned __int64)a3;
    v38[3] = 0;
    if ( *((_DWORD *)this + 16) )
    {
      LODWORD(v38[4]) = *((_DWORD *)this + 51);
      v38[5] = (char *)this + 172;
      v9 = 3;
      HIDWORD(v38[4]) = 5;
    }
  }
  pInput.cBuffers = v9;
  pInput.pBuffers = (PSecBuffer)v38;
  v11 = 1;
  pInput.ulVersion = 0;
  *(_QWORD *)Size = 0x200000000LL;
  *(_QWORD *)&Size[8] = 0;
  if ( a3 )
  {
    LODWORD(pvContextBuffer[0]) = 17;
    v11 = 2;
    *(_DWORD *)&Size[16] = 0;
    *(PVOID *)((char *)pvContextBuffer + 4) = 0;
  }
  pOutput.ulVersion = 0;
  v12 = (struct _SecHandle *)((char *)this + 24);
  pOutput.pBuffers = (PSecBuffer)Size;
  pOutput.cBuffers = v11;
  if ( *((_DWORD *)this + 16) )
  {
    if ( v12->dwLower == -1 || (v13 = (struct _SecHandle *)((char *)this + 24), *((_QWORD *)this + 4) == -1) )
      v13 = 0;
    v14 = AcceptSecurityContext(
            (PCredHandle)((char *)this + 8),
            v13,
            &pInput,
            *((_DWORD *)this + 10),
            0x10u,
            (PCtxtHandle)((char *)this + 24),
            &pOutput,
            &pfContextAttr,
            &ptsExpiry);
  }
  else
  {
    if ( v12->dwLower == -1 || (v15 = 0, *((_QWORD *)this + 4) == -1) )
      v15 = (struct _SecHandle *)((char *)this + 24);
    if ( v12->dwLower == -1 || *((_QWORD *)this + 4) == -1 )
      v12 = 0;
    v14 = InitializeSecurityContextW(
            (PCredHandle)((char *)this + 8),
            v12,
            *((SEC_WCHAR **)this + 6),
            *((_DWORD *)this + 10),
            0,
            0x10u,
            &pInput,
            0,
            v15,
            &pOutput,
            &pfContextAttr,
            0);
  }
  v10 = v14;
  if ( v11 > 1 && *(_DWORD *)&Size[16] && *(PVOID *)((char *)pvContextBuffer + 4) )
  {
    if ( v14 >= 0 || *(_DWORD *)Size )
    {
      FreeContextBuffer(*(PVOID *)((char *)pvContextBuffer + 4));
    }
    else
    {
      pfContextAttr |= 0x4000u;
      *(_DWORD *)Size = *(_DWORD *)&Size[16];
      *(PVOID *)&Size[8] = *(PVOID *)((char *)pvContextBuffer + 4);
    }
    *(PVOID *)((char *)pvContextBuffer + 4) = 0;
    *(_DWORD *)&Size[16] = 0;
  }
  switch ( v10 )
  {
    case -2146893047:
      goto LABEL_56;
    case -2146893032:
      *((_DWORD *)this + 34) = 5;
      goto LABEL_55;
    case 0:
      *((_DWORD *)this + 34) = 6;
      v10 = CRdpDTLSFilter::ResizeBufferForDataTransfer(this);
      if ( v10 >= 0 )
      {
        v10 = CRdpDTLSFilter::OnHandshakeCompleted(this);
        if ( v10 >= 0 )
        {
          *a8 = 1;
          *((_DWORD *)this + 17) = 3;
          goto LABEL_56;
        }
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_65;
        }
        ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v22, v23);
        v20 = 24;
        v21 = "OnHandshakeCompleted";
      }
      else
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_65;
        }
        ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v17, v18);
        v20 = 23;
        v21 = "ResizeBufferForDataTransfer failed";
      }
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v20,
        (unsigned int)WPP_9c7e9ce55f693cc8674c24007b6c55bd_Traceguids,
        ActivityIdPrefix,
        (__int64)v21,
        v10);
      goto LABEL_65;
    case 590610:
      *((_DWORD *)this + 34) = 4;
LABEL_55:
      *a7 = *((_DWORD *)this + 35);
      goto LABEL_56;
  }
  if ( v10 != 590692 )
  {
    v16 = v10 < 0;
    if ( v10 > 0 )
    {
      v10 = (unsigned __int16)v10 | 0x80070000;
      v16 = v10 < 0;
    }
    if ( v16 )
      goto LABEL_65;
    return (unsigned int)v10;
  }
  *((_DWORD *)this + 34) = 3;
LABEL_56:
  v10 = 0;
  if ( *(_QWORD *)&Size[8] && *(_DWORD *)Size )
  {
    v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int8 **))(**((_QWORD **)this + 7) + 24LL))(
            *((_QWORD *)this + 7),
            *(unsigned int *)Size,
            a5);
    if ( v10 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v26 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v24, v25);
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_9c7e9ce55f693cc8674c24007b6c55bd_Traceguids, v26, v10);
      }
      goto LABEL_65;
    }
    memset_0(*a5, 0, *(unsigned int *)Size);
    v27 = *(_DWORD *)Size;
    v28 = *(const void **)&Size[8];
    v29 = *(unsigned int *)Size;
    *a6 = *(_DWORD *)Size;
    memcpy_s(*a5, v29, v28, v27);
    FreeContextBuffer(*(PVOID *)&Size[8]);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18015cac8  push    rbp
0x18015caca  push    rbx
0x18015cacb  push    rsi
0x18015cacc  push    rdi
0x18015cacd  push    r12
0x18015cacf  push    r13
0x18015cad1  push    r14
0x18015cad3  push    r15
0x18015cad5  lea     rbp, [rsp-28h]
0x18015cada  sub     rsp, 128h
0x18015cae1  mov     rax, cs:__security_cookie
0x18015cae8  xor     rax, rsp
0x18015caeb  mov     [rbp+60h+var_50], rax
0x18015caef  mov     r12, [rbp+60h+arg_38]
0x18015caf6  xor     r10d, r10d
0x18015caf9  mov     r14, [rbp+60h+arg_20]
0x18015cb00  xorps   xmm0, xmm0
0x18015cb03  mov     r13, [rbp+60h+arg_28]
0x18015cb0a  xorps   xmm1, xmm1
0x18015cb0d  mov     r15, [rbp+60h+arg_30]
0x18015cb14  mov     rdi, rcx
0x18015cb17  movups  xmmword ptr [rbp+60h+var_AC], xmm0
0x18015cb1b  mov     [r12], r10b
0x18015cb1f  xor     eax, eax
0x18015cb21  movups  xmmword ptr [rbp+60h+var_6C], xmm1
0x18015cb25  mov     [rsp+160h+var_100], r10d
0x18015cb2a  mov     qword ptr [rsp+160h+var_F8], r10
0x18015cb2f  movups  xmmword ptr [rbp+60h+Size+4], xmm0
0x18015cb33  mov     [rbp+60h+var_90], r10d
0x18015cb37  movups  xmmword ptr [rbp+60h+pvContextBuffer], xmm0
0x18015cb3b  movups  xmmword ptr [rbp+60h+var_AC+0Ch], xmm0
0x18015cb3f  movups  [rbp+60h+var_8C], xmm1
0x18015cb43  movups  [rbp+60h+var_7C], xmm1
0x18015cb47  movups  xmmword ptr [rbp+60h+var_6C+0Ch], xmm1
0x18015cb4b  lea     ecx, [rax+2]
0x18015cb4e  mov     [rdi+44h], ecx
0x18015cb51  test    r14, r14
0x18015cb54  jz      loc_18015CF21
0x18015cb5a  test    r13, r13
0x18015cb5d  jz      loc_18015CF21
0x18015cb63  test    edx, edx
0x18015cb65  jz      short loc_18015CB80
0x18015cb67  inc     dword ptr [rdi+90h]
0x18015cb6d  cmp     dword ptr [rdi+90h], 28h ; '('
0x18015cb74  jbe     short loc_18015CB80
0x18015cb76  mov     ebx, 80004005h
0x18015cb7b  jmp     loc_18015CF26
0x18015cb80  test    r8, r8
0x18015cb83  jz      short loc_18015CBC0
0x18015cb85  mov     eax, ecx
0x18015cb87  mov     dword ptr [rbp+60h+var_8C], ecx
0x18015cb8a  mov     [rbp+60h+var_90], r9d
0x18015cb8e  mov     qword ptr [rbp+60h+var_8C+4], r8
0x18015cb92  mov     qword ptr [rbp+60h+var_8C+0Ch], r10
0x18015cb96  mov     qword ptr [rbp+60h+var_7C+4], r10
0x18015cb9a  cmp     [rdi+40h], r10d
0x18015cb9e  jz      short loc_18015CBC0
0x18015cba0  mov     eax, [rdi+0CCh]
0x18015cba6  mov     dword ptr [rbp+60h+var_7C+0Ch], eax
0x18015cba9  lea     rax, [rdi+0ACh]
0x18015cbb0  mov     qword ptr [rbp+60h+var_6C+4], rax
0x18015cbb4  mov     eax, 3
0x18015cbb9  mov     dword ptr [rbp+60h+var_6C], 5
0x18015cbc0  mov     [rbp+60h+pInput.cBuffers], eax
0x18015cbc3  lea     rax, [rbp+60h+var_90]
0x18015cbc7  mov     [rbp+60h+pInput.pBuffers], rax
0x18015cbcb  mov     esi, 1
0x18015cbd0  mov     [rbp+60h+pInput.ulVersion], r10d
0x18015cbd4  mov     dword ptr [rbp+60h+Size+4], ecx
0x18015cbd7  mov     dword ptr [rbp+60h+Size], r10d
0x18015cbdb  mov     qword ptr [rbp+60h+Size+8], r10
0x18015cbdf  test    r8, r8
0x18015cbe2  jz      short loc_18015CBF5
0x18015cbe4  mov     dword ptr [rbp+60h+pvContextBuffer], 11h
0x18015cbeb  mov     esi, ecx
0x18015cbed  mov     dword ptr [rbp+60h+Size+10h], r10d
0x18015cbf1  mov     [rbp+60h+pvContextBuffer+4], r10
0x18015cbf5  lea     rax, [rbp+60h+Size]
0x18015cbf9  mov     [rsp+160h+var_F0.ulVersion], r10d
0x18015cbfe  lea     rdx, [rdi+18h]
0x18015cc02  mov     [rsp+160h+var_F0.pBuffers], rax
0x18015cc07  mov     [rsp+160h+var_F0.cBuffers], esi
0x18015cc0b  cmp     [rdi+40h], r10d
0x18015cc0f  jz      short loc_18015CC66
0x18015cc11  cmp     qword ptr [rdx], 0FFFFFFFFFFFFFFFFh
0x18015cc15  jz      short loc_18015CC21
0x18015cc17  cmp     qword ptr [rdi+20h], 0FFFFFFFFFFFFFFFFh
0x18015cc1c  mov     rax, rdx
0x18015cc1f  jnz     short loc_18015CC24
0x18015cc21  mov     rax, r10
0x18015cc24  mov     r9d, [rdi+28h]; fContextReq
0x18015cc28  lea     r8, [rsp+160h+var_F8]
0x18015cc2d  mov     [rsp+160h+ptsExpiry], r8; ptsExpiry
0x18015cc32  lea     rcx, [rdi+8]; phCredential
0x18015cc36  lea     r8, [rsp+160h+var_100]
0x18015cc3b  mov     [rsp+160h+pfContextAttr], r8; pfContextAttr
0x18015cc40  lea     r8, [rsp+160h+var_F0]
0x18015cc45  mov     [rsp+160h+pOutput], r8; pOutput
0x18015cc4a  lea     r8, [rbp+60h+pInput]; pInput
0x18015cc4e  mov     [rsp+160h+phNewContext], rdx; phNewContext
0x18015cc53  mov     rdx, rax; phContext
0x18015cc56  mov     [rsp+160h+TargetDataRep], 10h; TargetDataRep
0x18015cc5e  call    cs:__imp_AcceptSecurityContext
0x18015cc64  jmp     short loc_18015CCD4
0x18015cc66  cmp     qword ptr [rdx], 0FFFFFFFFFFFFFFFFh
0x18015cc6a  jz      short loc_18015CC76
0x18015cc6c  cmp     qword ptr [rdi+20h], 0FFFFFFFFFFFFFFFFh
0x18015cc71  mov     rax, r10
0x18015cc74  jnz     short loc_18015CC79
0x18015cc76  mov     rax, rdx
0x18015cc79  cmp     qword ptr [rdx], 0FFFFFFFFFFFFFFFFh
0x18015cc7d  jz      short loc_18015CC86
0x18015cc7f  cmp     qword ptr [rdi+20h], 0FFFFFFFFFFFFFFFFh
0x18015cc84  jnz     short loc_18015CC89
0x18015cc86  mov     rdx, r10; phContext
0x18015cc89  mov     r9d, [rdi+28h]; fContextReq
0x18015cc8d  lea     r8, [rsp+160h+var_100]
0x18015cc92  mov     [rsp+160h+var_108], r10; ptsExpiry
0x18015cc97  lea     rcx, [rdi+8]; phCredential
0x18015cc9b  mov     [rsp+160h+var_110], r8; pfContextAttr
0x18015cca0  lea     r8, [rsp+160h+var_F0]
0x18015cca5  mov     [rsp+160h+var_118], r8; pOutput
0x18015ccaa  mov     r8, [rdi+30h]; pszTargetName
0x18015ccae  mov     [rsp+160h+ptsExpiry], rax; phNewContext
0x18015ccb3  lea     rax, [rbp+60h+pInput]
0x18015ccb7  mov     dword ptr [rsp+160h+pfContextAttr], r10d; Reserved2
0x18015ccbc  mov     [rsp+160h+pOutput], rax; pInput
0x18015ccc1  mov     dword ptr [rsp+160h+phNewContext], 10h; TargetDataRep
0x18015ccc9  mov     [rsp+160h+TargetDataRep], r10d; Reserved1
0x18015ccce  call    cs:__imp_InitializeSecurityContextW
0x18015ccd4  mov     ebx, eax
0x18015ccd6  cmp     esi, 1
0x18015ccd9  jbe     short loc_18015CD19
0x18015ccdb  mov     eax, dword ptr [rbp+60h+Size+10h]
0x18015ccde  test    eax, eax
0x18015cce0  jz      short loc_18015CD19
0x18015cce2  mov     rcx, [rbp+60h+pvContextBuffer+4]; pvContextBuffer
0x18015cce6  test    rcx, rcx
0x18015cce9  jz      short loc_18015CD19
0x18015cceb  test    ebx, ebx
0x18015cced  jns     short loc_18015CD04
0x18015ccef  cmp     dword ptr [rbp+60h+Size], 0
0x18015ccf3  jnz     short loc_18015CD04
0x18015ccf5  bts     [rsp+160h+var_100], 0Eh
0x18015ccfb  mov     dword ptr [rbp+60h+Size], eax
0x18015ccfe  mov     qword ptr [rbp+60h+Size+8], rcx
0x18015cd02  jmp     short loc_18015CD0A
0x18015cd04  call    cs:__imp_FreeContextBuffer
0x18015cd0a  mov     [rbp+60h+pvContextBuffer+4], 0
0x18015cd12  mov     dword ptr [rbp+60h+Size+10h], 0
0x18015cd19  cmp     ebx, 80090309h
0x18015cd1f  jz      loc_18015CE76
0x18015cd25  cmp     ebx, 80090318h
0x18015cd2b  jz      loc_18015CE63
0x18015cd31  test    ebx, ebx
0x18015cd33  jz      short loc_18015CD8D
0x18015cd35  cmp     ebx, 90312h
0x18015cd3b  jz      short loc_18015CD7E
0x18015cd3d  cmp     ebx, 90320h
0x18015cd43  jz      short loc_18015CD64
0x18015cd45  cmp     ebx, 9035Ch
0x18015cd4b  jz      short loc_18015CD64
0x18015cd4d  cmp     ebx, 90364h
0x18015cd53  jnz     short loc_18015CD64
0x18015cd55  mov     dword ptr [rdi+88h], 3
0x18015cd5f  jmp     loc_18015CE76
0x18015cd64  test    ebx, ebx
0x18015cd66  jle     short loc_18015CD73
0x18015cd68  movzx   ebx, bx
0x18015cd6b  or      ebx, 80070000h
0x18015cd71  test    ebx, ebx
0x18015cd73  jns     loc_18015CF36
0x18015cd79  jmp     loc_18015CF26
0x18015cd7e  mov     dword ptr [rdi+88h], 4
0x18015cd88  jmp     loc_18015CE6D
0x18015cd8d  mov     rcx, rdi; this
0x18015cd90  mov     dword ptr [rdi+88h], 6
0x18015cd9a  call    ?ResizeBufferForDataTransfer@CRdpDTLSFilter@@AEAAJXZ; CRdpDTLSFilter::ResizeBufferForDataTransfer(void)
0x18015cd9f  mov     ebx, eax
0x18015cda1  test    eax, eax
0x18015cda3  jns     short loc_18015CE09
0x18015cda5  mov     rcx, cs:WPP_GLOBAL_Control
0x18015cdac  lea     rax, WPP_GLOBAL_Control
0x18015cdb3  cmp     rcx, rax
0x18015cdb6  jz      loc_18015CF26
0x18015cdbc  test    byte ptr [rcx+1Ch], 8
0x18015cdc0  jz      loc_18015CF26
0x18015cdc6  cmp     byte ptr [rcx+19h], 2
0x18015cdca  jb      loc_18015CF26
0x18015cdd0  call    RdpX_GetActivityIdPrefix
0x18015cdd5  mov     edx, 17h
0x18015cdda  lea     rcx, aResizebufferfo; "ResizeBufferForDataTransfer failed"
0x18015cde1  mov     dword ptr [rsp+160h+phNewContext], ebx
0x18015cde5  lea     r8, WPP_9c7e9ce55f693cc8674c24007b6c55bd_Traceguids
0x18015cdec  mov     qword ptr [rsp+160h+TargetDataRep], rcx
0x18015cdf1  mov     r9d, eax
0x18015cdf4  mov     rcx, cs:WPP_GLOBAL_Control
0x18015cdfb  mov     rcx, [rcx+10h]
0x18015cdff  call    WPP_SF_DsD
0x18015ce04  jmp     loc_18015CF26
0x18015ce09  mov     rcx, rdi; this
0x18015ce0c  call    ?OnHandshakeCompleted@CRdpDTLSFilter@@AEAAJXZ; CRdpDTLSFilter::OnHandshakeCompleted(void)
0x18015ce11  mov     ebx, eax
0x18015ce13  test    eax, eax
0x18015ce15  jns     short loc_18015CE55
0x18015ce17  mov     rcx, cs:WPP_GLOBAL_Control
0x18015ce1e  lea     rax, WPP_GLOBAL_Control
0x18015ce25  cmp     rcx, rax
0x18015ce28  jz      loc_18015CF26
0x18015ce2e  test    byte ptr [rcx+1Ch], 8
0x18015ce32  jz      loc_18015CF26
0x18015ce38  cmp     byte ptr [rcx+19h], 2
0x18015ce3c  jb      loc_18015CF26
0x18015ce42  call    RdpX_GetActivityIdPrefix
0x18015ce47  mov     edx, 18h
0x18015ce4c  lea     rcx, aOnhandshakecom_0; "OnHandshakeCompleted"
0x18015ce53  jmp     short loc_18015CDE1
0x18015ce55  mov     byte ptr [r12], 1
0x18015ce5a  mov     dword ptr [rdi+44h], 3
0x18015ce61  jmp     short loc_18015CE76
0x18015ce63  mov     dword ptr [rdi+88h], 5
0x18015ce6d  mov     eax, [rdi+8Ch]
0x18015ce73  mov     [r15], eax
0x18015ce76  xor     ebx, ebx
0x18015ce78  cmp     qword ptr [rbp+60h+Size+8], rbx
0x18015ce7c  jz      loc_18015CF36
0x18015ce82  mov     edx, dword ptr [rbp+60h+Size]
0x18015ce85  test    edx, edx
0x18015ce87  jz      loc_18015CF36
0x18015ce8d  mov     rcx, [rdi+38h]
0x18015ce91  mov     r8, r14
0x18015ce94  mov     rax, [rcx]
0x18015ce97  mov     rax, [rax+18h]
0x18015ce9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015cea0  mov     ebx, eax
0x18015cea2  test    eax, eax
0x18015cea4  jns     short loc_18015CEEF
0x18015cea6  mov     rcx, cs:WPP_GLOBAL_Control
0x18015cead  lea     rax, WPP_GLOBAL_Control
0x18015ceb4  cmp     rcx, rax
0x18015ceb7  jz      short loc_18015CF26
0x18015ceb9  test    byte ptr [rcx+1Ch], 8
0x18015cebd  jz      short loc_18015CF26
0x18015cebf  cmp     byte ptr [rcx+19h], 2
0x18015cec3  jb      short loc_18015CF26
0x18015cec5  call    RdpX_GetActivityIdPrefix
0x18015ceca  mov     rcx, cs:WPP_GLOBAL_Control
0x18015ced1  lea     r8, WPP_9c7e9ce55f693cc8674c24007b6c55bd_Traceguids
0x18015ced8  mov     edx, 1Ah
0x18015cedd  mov     [rsp+160h+TargetDataRep], ebx
0x18015cee1  mov     r9d, eax
0x18015cee4  mov     rcx, [rcx+10h]
0x18015cee8  call    WPP_SF_Dd
0x18015ceed  jmp     short loc_18015CF26
0x18015ceef  mov     r8d, dword ptr [rbp+60h+Size]; Size
0x18015cef3  xor     edx, edx; Val
0x18015cef5  mov     rcx, [r14]; void *
0x18015cef8  call    memset_0
0x18015cefd  mov     eax, dword ptr [rbp+60h+Size]
0x18015cf00  mov     r8, qword ptr [rbp+60h+Size+8]; Source
0x18015cf04  mov     edx, eax; DestinationSize
0x18015cf06  mov     [r13+0], eax
0x18015cf0a  mov     r9d, eax; SourceSize
0x18015cf0d  mov     rcx, [r14]; Destination
0x18015cf10  call    memcpy_s
0x18015cf15  mov     rcx, qword ptr [rbp+60h+Size+8]; pvContextBuffer
0x18015cf19  call    cs:__imp_FreeContextBuffer
0x18015cf1f  jmp     short loc_18015CF36
0x18015cf21  mov     ebx, 80070057h
0x18015cf26  mov     [rdi+0D0h], ebx
0x18015cf2c  mov     dword ptr [rdi+88h], 9
0x18015cf36  mov     eax, ebx
0x18015cf38  mov     rcx, [rbp+60h+var_50]
0x18015cf3c  xor     rcx, rsp; StackCookie
0x18015cf3f  call    __security_check_cookie
0x18015cf44  add     rsp, 128h
0x18015cf4b  pop     r15
0x18015cf4d  pop     r14
0x18015cf4f  pop     r13
0x18015cf51  pop     r12
0x18015cf53  pop     rdi
0x18015cf54  pop     rsi
0x18015cf55  pop     rbx
0x18015cf56  pop     rbp
0x18015cf57  retn
```
