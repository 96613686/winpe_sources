# SrvAllocateRkfEcp

- ea: `0x140033b84`
- end: `0x140033fd7`
- name: `SrvAllocateRkfEcp`
- size: `1107`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14007a240`

## callees

- `0x1400222ec`
- `0x140022958`
- `0x140033b84`
- `0x140038680`
- `0x140038980`

## import_xrefs

- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x140033c01`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x140033c01`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x140033f51`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x140033f51`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x140033f3b`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x140033f3b`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x140033d01`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x140033d01`
- `srvnet!SrvAdminNodeGetSignature` at `0x140033e61`
- `srvnet!SrvAdminNodeGetSignature` at `0x140033e61`

## pseudocode

```c
__int64 __fastcall SrvAllocateRkfEcp(__int64 a1, struct _ECP_LIST *a2)
{
  __int64 v2; // rax
  __int64 v3; // r14
  ULONG v5; // r12d
  char v6; // r13
  struct _ECP_LIST *v7; // rcx
  int v8; // ebx
  int v9; // edx
  unsigned int Parameter; // edi
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  ULONG v13; // esi
  PDEVICE_OBJECT v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  _QWORD *v17; // rcx
  int v18; // esi
  _OWORD *v19; // rax
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  char *v25; // rcx
  PVOID EcpContext[22]; // [rsp+30h] [rbp-59h] BYREF
  unsigned __int16 v28; // [rsp+F0h] [rbp+67h]
  ULONG EcpContextSize; // [rsp+100h] [rbp+77h] BYREF
  PVOID v31; // [rsp+108h] [rbp+7Fh] BYREF

  v2 = *(_QWORD *)(a1 + 96);
  v3 = *(_QWORD *)(a1 + 560);
  EcpContext[0] = 0;
  EcpContextSize = 0;
  v5 = 0;
  v31 = 0;
  v6 = 0;
  v28 = *(_WORD *)(*(_QWORD *)(v2 + 496) + 44LL);
  v7 = *(struct _ECP_LIST **)(v3 + 320);
  v8 = v28 < 0x311u ? 104 : 124;
  if ( !v7
    || FsRtlFindExtraCreateParameter(v7, &GUID_ECP_OPEN_AS_BLOCK_DEVICE, EcpContext, &EcpContextSize) < 0
    || EcpContextSize < 0xA8
    || (v9 = *((_DWORD *)EcpContext[0] + 7), (v9 & 1) == 0) && (v9 & 0x10) == 0 )
  {
    v13 = v28 < 0x311u ? 104 : 124;
LABEL_19:
    Parameter = FsRtlAllocateExtraCreateParameter(&Smb2RkfGuidEcpIn, v13, 0, 0, 0x5324534Cu, &v31);
    if ( (Parameter & 0x80000000) == 0 )
    {
      memset(v31, 0, v13);
      *((_DWORD *)v31 + 1) = v28 >= 0x311u;
      if ( v28 >= 0x311u )
        *((_DWORD *)v31 + 30) = v8;
      if ( *(_BYTE *)(v3 + 378) )
      {
        *(_DWORD *)v31 = 3;
      }
      else if ( *(_BYTE *)(v3 + 382) )
      {
        *(_DWORD *)v31 = 4;
      }
      else
      {
        *(_DWORD *)v31 = (*(_BYTE *)(v3 + 5) != 0) + 1;
      }
      if ( *(_BYTE *)(v3 + 379) )
        *((_DWORD *)v31 + 2) |= 2u;
      *((_DWORD *)v31 + 24) = *(_DWORD *)(v3 + 356);
      *((_OWORD *)v31 + 2) = *(_OWORD *)(v3 + 336);
      *((_OWORD *)v31 + 1) = Smb2RfsIdKey;
      if ( *(_BYTE *)(v3 + 400) )
      {
        v16 = *(_QWORD *)(*(_QWORD *)(a1 + 96) + 496LL);
        *((_OWORD *)v31 + 3) = *(_OWORD *)(v3 + 384);
        *((_OWORD *)v31 + 4) = *(_OWORD *)(v16 + 88);
        if ( v28 >= 0x311u )
        {
          v17 = v31;
          *((_QWORD *)v31 + 13) = *(_QWORD *)(v3 + 408);
          v17[14] = *(_QWORD *)(v3 + 416);
        }
      }
      v18 = (unsigned __int16)SrvAdminNodeGetSignature() >> 8;
      *((_DWORD *)v31 + 20) = v18;
      if ( v6 )
      {
        memset(&EcpContext[2], 0, 0x60u);
        EcpContext[2] = (PVOID)0x100100000LL;
        memset(&EcpContext[3], 255, 0x40u);
        LODWORD(EcpContext[12]) = 96;
        HIDWORD(EcpContext[12]) = EcpContextSize;
        if ( *((_DWORD *)v31 + 1) )
          v19 = (char *)v31 + *((unsigned int *)v31 + 30);
        else
          v19 = (char *)v31 + 104;
        v20 = *(_OWORD *)&EcpContext[4];
        *v19 = *(_OWORD *)&EcpContext[2];
        v21 = *(_OWORD *)&EcpContext[6];
        v19[1] = v20;
        v22 = *(_OWORD *)&EcpContext[8];
        v19[2] = v21;
        v23 = *(_OWORD *)&EcpContext[10];
        v19[3] = v22;
        v24 = *(_OWORD *)&EcpContext[12];
        v19[4] = v23;
        v19[5] = v24;
        if ( *((_DWORD *)v31 + 1) )
          v25 = (char *)v31 + *((unsigned int *)v31 + 30);
        else
          v25 = (char *)v31 + 104;
        memmove(v25 + 96, EcpContext[0], EcpContextSize);
        *((_DWORD *)v31 + 25) = v5;
      }
      Parameter = FsRtlInsertExtraCreateParameter(a2, v31);
      if ( (Parameter & 0x80000000) == 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 38, &WPP_857f2cc8c50b3da0e48609e9ae4069db_Traceguids, v31, v18);
        }
        return Parameter;
      }
      FsRtlFreeExtraCreateParameter(v31);
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        return Parameter;
      }
      v15 = 37;
    }
    else
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x14u)
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        return Parameter;
      }
      v15 = 36;
    }
    WPP_SF_qD(v14->AttachedDevice, v15, &WPP_857f2cc8c50b3da0e48609e9ae4069db_Traceguids, a1, Parameter);
    return Parameter;
  }
  v5 = EcpContextSize + 96;
  if ( EcpContextSize >= 0xFFFFFFA0 )
  {
    Parameter = -1073741675;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x14u)
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v12 = 34;
LABEL_11:
      WPP_SF_q(v11->AttachedDevice, v12, &WPP_857f2cc8c50b3da0e48609e9ae4069db_Traceguids, a1);
      return Parameter;
    }
    return Parameter;
  }
  v13 = v8 + v5;
  if ( v8 + v5 >= v5 )
  {
    v6 = 1;
    goto LABEL_19;
  }
  Parameter = -1073741675;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x14u)
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    v12 = 35;
    goto LABEL_11;
  }
  return Parameter;
}

```

## disassembly

```asm
0x140033b84  mov     [rsp-8+EcpList], rdx
0x140033b89  push    rbp
0x140033b8a  push    rbx
0x140033b8b  push    rsi
0x140033b8c  push    rdi
0x140033b8d  push    r12
0x140033b8f  push    r13
0x140033b91  push    r14
0x140033b93  push    r15
0x140033b95  lea     rbp, [rsp-1Fh]
0x140033b9a  sub     rsp, 0A8h
0x140033ba1  mov     rax, [rcx+60h]
0x140033ba5  xor     edi, edi
0x140033ba7  mov     r14, [rcx+230h]
0x140033bae  mov     r15, rcx
0x140033bb1  mov     [rbp+57h+EcpContext], rdi
0x140033bb5  mov     ecx, 311h
0x140033bba  mov     [rbp+57h+EcpContextSize], edi
0x140033bbd  mov     r12d, edi
0x140033bc0  mov     [rbp+57h+arg_18], rdi
0x140033bc4  mov     r13b, dil
0x140033bc7  mov     r8, [rax+1F0h]
0x140033bce  movzx   eax, word ptr [r8+2Ch]
0x140033bd3  cmp     ax, cx
0x140033bd6  mov     [rbp+57h+arg_0], ax
0x140033bda  mov     rcx, [r14+140h]; EcpList
0x140033be1  sbb     ebx, ebx
0x140033be3  and     ebx, 0FFFFFFECh
0x140033be6  add     ebx, 7Ch ; '|'
0x140033be9  test    rcx, rcx
0x140033bec  jz      loc_140033CDF
0x140033bf2  lea     r9, [rbp+57h+EcpContextSize]; EcpContextSize
0x140033bf6  lea     r8, [rbp+57h+EcpContext]; EcpContext
0x140033bfa  lea     rdx, GUID_ECP_OPEN_AS_BLOCK_DEVICE; EcpType
0x140033c01  call    cs:__imp_FsRtlFindExtraCreateParameter
0x140033c08  nop     dword ptr [rax+rax+00h]
0x140033c0d  test    eax, eax
0x140033c0f  js      loc_140033CDF
0x140033c15  mov     ecx, [rbp+57h+EcpContextSize]
0x140033c18  test    ecx, ecx
0x140033c1a  jz      loc_140033CDF
0x140033c20  cmp     ecx, 0A8h
0x140033c26  jb      loc_140033CDF
0x140033c2c  mov     rax, [rbp+57h+EcpContext]
0x140033c30  mov     edx, [rax+1Ch]
0x140033c33  test    dl, 1
0x140033c36  jnz     short loc_140033C41
0x140033c38  test    dl, 10h
0x140033c3b  jz      loc_140033CDF
0x140033c41  lea     r12d, [rcx+60h]
0x140033c45  cmp     r12d, 60h ; '`'
0x140033c49  jnb     short loc_140033C99
0x140033c4b  mov     edi, 0C0000095h
0x140033c50  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140033c57  lea     rax, WPP_GLOBAL_Control
0x140033c5e  cmp     rcx, rax
0x140033c61  jz      loc_140033FC0
0x140033c67  bt      dword ptr [rcx+2Ch], 14h
0x140033c6c  jnb     loc_140033FC0
0x140033c72  cmp     byte ptr [rcx+29h], 1
0x140033c76  jb      loc_140033FC0
0x140033c7c  mov     edx, 22h ; '"'
0x140033c81  mov     rcx, [rcx+18h]
0x140033c85  lea     r8, WPP_857f2cc8c50b3da0e48609e9ae4069db_Traceguids
0x140033c8c  mov     r9, r15
0x140033c8f  call    WPP_SF_q
0x140033c94  jmp     loc_140033FC0
0x140033c99  lea     esi, [rbx+r12]
0x140033c9d  cmp     esi, r12d
0x140033ca0  jb      short loc_140033CA7
0x140033ca2  mov     r13b, 1
0x140033ca5  jmp     short loc_140033CE1
0x140033ca7  mov     edi, 0C0000095h
0x140033cac  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140033cb3  lea     rax, WPP_GLOBAL_Control
0x140033cba  cmp     rcx, rax
0x140033cbd  jz      loc_140033FC0
0x140033cc3  bt      dword ptr [rcx+2Ch], 14h
0x140033cc8  jnb     loc_140033FC0
0x140033cce  cmp     byte ptr [rcx+29h], 1
0x140033cd2  jb      loc_140033FC0
0x140033cd8  mov     edx, 23h ; '#'
0x140033cdd  jmp     short loc_140033C81
0x140033cdf  mov     esi, ebx
0x140033ce1  lea     rax, [rbp+57h+arg_18]
0x140033ce5  xor     r9d, r9d; CleanupCallback
0x140033ce8  mov     [rsp+0E0h+var_B8], rax; EcpContext
0x140033ced  lea     rcx, Smb2RkfGuidEcpIn; EcpType
0x140033cf4  xor     r8d, r8d; Flags
0x140033cf7  mov     [rsp+0E0h+PoolTag], 5324534Ch; PoolTag
0x140033cff  mov     edx, esi; SizeOfContext
0x140033d01  call    cs:__imp_FsRtlAllocateExtraCreateParameter
0x140033d08  nop     dword ptr [rax+rax+00h]
0x140033d0d  mov     edi, eax
0x140033d0f  test    eax, eax
0x140033d11  jns     short loc_140033D60
0x140033d13  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140033d1a  lea     rax, WPP_GLOBAL_Control
0x140033d21  cmp     rcx, rax
0x140033d24  jz      loc_140033FC0
0x140033d2a  bt      dword ptr [rcx+2Ch], 14h
0x140033d2f  jnb     loc_140033FC0
0x140033d35  cmp     byte ptr [rcx+29h], 1
0x140033d39  jb      loc_140033FC0
0x140033d3f  mov     edx, 24h ; '$'
0x140033d44  mov     rcx, [rcx+18h]
0x140033d48  lea     r8, WPP_857f2cc8c50b3da0e48609e9ae4069db_Traceguids
0x140033d4f  mov     r9, r15
0x140033d52  mov     [rsp+0E0h+PoolTag], edi
0x140033d56  call    WPP_SF_qD
0x140033d5b  jmp     loc_140033FC0
0x140033d60  mov     rcx, [rbp+57h+arg_18]; void *
0x140033d64  xor     edx, edx; Val
0x140033d66  mov     r8d, esi; Size
0x140033d69  call    memset
0x140033d6e  movzx   edx, [rbp+57h+arg_0]
0x140033d72  xor     edi, edi
0x140033d74  mov     rax, [rbp+57h+arg_18]
0x140033d78  mov     ecx, edi
0x140033d7a  mov     r8d, 311h
0x140033d80  cmp     dx, r8w
0x140033d84  setnb   cl
0x140033d87  mov     [rax+4], ecx
0x140033d8a  jb      short loc_140033D93
0x140033d8c  mov     rax, [rbp+57h+arg_18]
0x140033d90  mov     [rax+78h], ebx
0x140033d93  cmp     [r14+17Ah], dil
0x140033d9a  jz      short loc_140033DA8
0x140033d9c  mov     rax, [rbp+57h+arg_18]
0x140033da0  mov     dword ptr [rax], 3
0x140033da6  jmp     short loc_140033DCF
0x140033da8  cmp     [r14+17Eh], dil
0x140033daf  jz      short loc_140033DBD
0x140033db1  mov     rax, [rbp+57h+arg_18]
0x140033db5  mov     dword ptr [rax], 4
0x140033dbb  jmp     short loc_140033DCF
0x140033dbd  mov     al, [r14+5]
0x140033dc1  neg     al
0x140033dc3  mov     rax, [rbp+57h+arg_18]
0x140033dc7  sbb     ecx, ecx
0x140033dc9  neg     ecx
0x140033dcb  inc     ecx
0x140033dcd  mov     [rax], ecx
0x140033dcf  cmp     [r14+17Bh], dil
0x140033dd6  jz      short loc_140033DE0
0x140033dd8  mov     rax, [rbp+57h+arg_18]
0x140033ddc  or      dword ptr [rax+8], 2
0x140033de0  mov     rax, [rbp+57h+arg_18]
0x140033de4  mov     ecx, [r14+164h]
0x140033deb  mov     [rax+60h], ecx
0x140033dee  mov     rax, [rbp+57h+arg_18]
0x140033df2  movups  xmm0, xmmword ptr [r14+150h]
0x140033dfa  movdqu  xmmword ptr [rax+20h], xmm0
0x140033dff  mov     rax, [rbp+57h+arg_18]
0x140033e03  movups  xmm1, cs:Smb2RfsIdKey
0x140033e0a  movdqu  xmmword ptr [rax+10h], xmm1
0x140033e0f  cmp     [r14+190h], dil
0x140033e16  jz      short loc_140033E61
0x140033e18  mov     rax, [r15+60h]
0x140033e1c  movups  xmm0, xmmword ptr [r14+180h]
0x140033e24  mov     rcx, [rax+1F0h]
0x140033e2b  mov     rax, [rbp+57h+arg_18]
0x140033e2f  movdqu  xmmword ptr [rax+30h], xmm0
0x140033e34  mov     rax, [rbp+57h+arg_18]
0x140033e38  movups  xmm1, xmmword ptr [rcx+58h]
0x140033e3c  movdqu  xmmword ptr [rax+40h], xmm1
0x140033e41  cmp     dx, r8w
0x140033e45  jb      short loc_140033E61
0x140033e47  mov     rax, [r14+198h]
0x140033e4e  mov     rcx, [rbp+57h+arg_18]
0x140033e52  mov     [rcx+68h], rax
0x140033e56  mov     rax, [r14+1A0h]
0x140033e5d  mov     [rcx+70h], rax
0x140033e61  call    cs:__imp_SrvAdminNodeGetSignature
0x140033e68  nop     dword ptr [rax+rax+00h]
0x140033e6d  movzx   esi, ax
0x140033e70  mov     ebx, 100000h
0x140033e75  mov     rax, [rbp+57h+arg_18]
0x140033e79  shr     esi, 8
0x140033e7c  mov     [rax+50h], esi
0x140033e7f  test    r13b, r13b
0x140033e82  jz      loc_140033F33
0x140033e88  mov     r14d, 60h ; '`'
0x140033e8e  lea     rcx, [rbp+57h+var_A0]; void *
0x140033e92  mov     r8d, r14d; Size
0x140033e95  xor     edx, edx; Val
0x140033e97  call    memset
0x140033e9c  mov     edx, 0FFh; Val
0x140033ea1  mov     dword ptr [rbp+57h+var_A0], ebx
0x140033ea4  lea     r8d, [r14-20h]; Size
0x140033ea8  mov     dword ptr [rbp+57h+var_A0+4], 1
0x140033eaf  lea     rcx, [rbp+57h+var_A0+8]; void *
0x140033eb3  call    memset
0x140033eb8  mov     rcx, [rbp+57h+arg_18]
0x140033ebc  mov     eax, [rbp+57h+EcpContextSize]
0x140033ebf  mov     dword ptr [rbp+57h+var_50], r14d
0x140033ec3  mov     dword ptr [rbp+57h+var_50+4], eax
0x140033ec6  cmp     [rcx+4], edi
0x140033ec9  jnz     short loc_140033ED1
0x140033ecb  lea     rax, [rcx+68h]
0x140033ecf  jmp     short loc_140033ED7
0x140033ed1  mov     eax, [rcx+78h]
0x140033ed4  add     rax, rcx
0x140033ed7  movaps  xmm0, [rbp+57h+var_A0]
0x140033edb  movaps  xmm1, [rbp+57h+var_90]
0x140033edf  movups  xmmword ptr [rax], xmm0
0x140033ee2  movaps  xmm0, [rbp+57h+var_80]
0x140033ee6  movups  xmmword ptr [rax+10h], xmm1
0x140033eea  movaps  xmm1, [rbp+57h+var_70]
0x140033eee  movups  xmmword ptr [rax+20h], xmm0
0x140033ef2  movaps  xmm0, [rbp+57h+var_60]
0x140033ef6  movups  xmmword ptr [rax+30h], xmm1
0x140033efa  movaps  xmm1, [rbp+57h+var_50]
0x140033efe  movups  xmmword ptr [rax+40h], xmm0
0x140033f02  movups  xmmword ptr [rax+50h], xmm1
0x140033f06  mov     rax, [rbp+57h+arg_18]
0x140033f0a  cmp     [rax+4], edi
0x140033f0d  jnz     short loc_140033F15
0x140033f0f  lea     rcx, [rax+68h]
0x140033f13  jmp     short loc_140033F1B
0x140033f15  mov     ecx, [rax+78h]
0x140033f18  add     rcx, rax
0x140033f1b  mov     r8d, [rbp+57h+EcpContextSize]; Size
0x140033f1f  add     rcx, r14; void *
0x140033f22  mov     rdx, [rbp+57h+EcpContext]; Src
0x140033f26  call    memmove
0x140033f2b  mov     rax, [rbp+57h+arg_18]
0x140033f2f  mov     [rax+64h], r12d
0x140033f33  mov     rdx, [rbp+57h+arg_18]; EcpContext
0x140033f37  mov     rcx, [rbp+57h+EcpList]; EcpList
0x140033f3b  call    cs:__imp_FsRtlInsertExtraCreateParameter
0x140033f42  nop     dword ptr [rax+rax+00h]
0x140033f47  mov     edi, eax
0x140033f49  test    eax, eax
0x140033f4b  jns     short loc_140033F85
0x140033f4d  mov     rcx, [rbp+57h+arg_18]; EcpContext
0x140033f51  call    cs:__imp_FsRtlFreeExtraCreateParameter
0x140033f58  nop     dword ptr [rax+rax+00h]
0x140033f5d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140033f64  lea     rax, WPP_GLOBAL_Control
0x140033f6b  cmp     rcx, rax
0x140033f6e  jz      short loc_140033FC0
0x140033f70  test    [rcx+2Ch], ebx
0x140033f73  jz      short loc_140033FC0
0x140033f75  cmp     byte ptr [rcx+29h], 1
0x140033f79  jb      short loc_140033FC0
0x140033f7b  mov     edx, 25h ; '%'
0x140033f80  jmp     loc_140033D44
0x140033f85  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140033f8c  lea     rax, WPP_GLOBAL_Control
0x140033f93  cmp     rcx, rax
0x140033f96  jz      short loc_140033FC0
0x140033f98  test    [rcx+2Ch], ebx
0x140033f9b  jz      short loc_140033FC0
0x140033f9d  cmp     byte ptr [rcx+29h], 2
0x140033fa1  jb      short loc_140033FC0
0x140033fa3  mov     r9, [rbp+57h+arg_18]
0x140033fa7  lea     r8, WPP_857f2cc8c50b3da0e48609e9ae4069db_Traceguids
0x140033fae  mov     rcx, [rcx+18h]
0x140033fb2  mov     edx, 26h ; '&'
0x140033fb7  mov     [rsp+0E0h+PoolTag], esi
0x140033fbb  call    WPP_SF_qD
0x140033fc0  mov     eax, edi
0x140033fc2  add     rsp, 0A8h
0x140033fc9  pop     r15
0x140033fcb  pop     r14
0x140033fcd  pop     r13
0x140033fcf  pop     r12
0x140033fd1  pop     rdi
0x140033fd2  pop     rsi
0x140033fd3  pop     rbx
0x140033fd4  pop     rbp
0x140033fd5  retn
```
