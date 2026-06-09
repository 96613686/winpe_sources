# A2dpInbandSbcCodec::OutParms::ComputeFromMtuAndStore(int,int,PacketTypes const &,int,int,SBC *,SBC_CONFIG *,unsigned __int64)

- ea: `0x14003e748`
- end: `0x14003ed05`
- name: `?ComputeFromMtuAndStore@OutParms@A2dpInbandSbcCodec@@QEAAJHHAEBUPacketTypes@@HHPEAVSBC@@PEAUSBC_CONFIG@@_K@Z`
- size: `1469`
- prototype: `__int64 __usercall@<rax>(A2dpInbandSbcCodec::OutParms *__hidden this@<rcx>, int@<edx>, int@<r8d>, const struct PacketTypes *@<r9>, int, int, struct SBC *, struct SBC_CONFIG *, unsigned __int64)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14003efcc`
- `0x140040b40`

## callees

- `0x140001008`
- `0x14000700c`
- `0x1400102e0`
- `0x140010814`
- `0x140010920`
- `0x140012400`
- `0x140014d0c`
- `0x14001c74c`
- `0x14003e710`
- `0x14003e748`
- `0x140040d54`
- `0x14005ce00`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14003ec95`
- `ntoskrnl!ExAllocatePool2` at `0x14003ec95`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ecd5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ecd5`

## pseudocode

```c
__int64 __fastcall A2dpInbandSbcCodec::OutParms::ComputeFromMtuAndStore(
        A2dpInbandSbcCodec::OutParms *this,
        __int64 a2,
        __int64 a3,
        const struct PacketTypes *a4,
        int a5,
        int a6,
        struct SBC *a7,
        struct SBC_CONFIG *a8,
        struct SBC_CONFIG *a9)
{
  int v10; // r14d
  int v11; // ebx
  struct SBC_CONFIG *v12; // r12
  int v13; // r10d
  int v14; // eax
  int v15; // ecx
  int v16; // eax
  int v17; // r13d
  PacketTypes *v18; // r9
  unsigned int v19; // r10d
  unsigned int MaxL2capPayloadSize; // eax
  int v21; // edx
  int *v22; // r9
  int v23; // ebx
  __int64 v24; // r8
  _UNKNOWN **v25; // rdx
  char v26; // si
  int v27; // r15d
  bool v28; // zf
  struct SBC *v29; // r14
  bool v30; // al
  int v31; // r14d
  int v32; // r11d
  int v33; // ecx
  __int64 v34; // r13
  int v35; // r9d
  int v36; // edx
  unsigned int v37; // r11d
  int v38; // ecx
  bool v39; // cc
  int v40; // eax
  int v41; // r10d
  __int64 v42; // rax
  __int64 v43; // rdx
  __int128 v44; // xmm1
  __int64 v45; // xmm0_8
  int v46; // r13d
  int v47; // ebx
  int v48; // r14d
  int v49; // ecx
  int v50; // r8d
  int v51; // r9d
  int v52; // eax
  unsigned int v53; // ebx
  SBC *v54; // rcx
  bool v55; // r8
  size_t v56; // r14
  void *Pool2; // rax
  void *v58; // rbx
  void *v59; // rsi
  int *v61; // [rsp+20h] [rbp-B9h]
  int v62; // [rsp+20h] [rbp-B9h]
  int v63; // [rsp+28h] [rbp-B1h]
  int v64; // [rsp+38h] [rbp-A1h]
  __int64 v65; // [rsp+70h] [rbp-69h] BYREF
  __int64 v66; // [rsp+78h] [rbp-61h] BYREF
  __int128 v67; // [rsp+80h] [rbp-59h]
  __int128 v68; // [rsp+90h] [rbp-49h]
  __int64 v69; // [rsp+A0h] [rbp-39h]
  __int64 v70; // [rsp+A8h] [rbp-31h] BYREF
  __int64 v71; // [rsp+B0h] [rbp-29h] BYREF
  __int64 v72; // [rsp+B8h] [rbp-21h] BYREF
  __int64 v73; // [rsp+C0h] [rbp-19h] BYREF
  __int64 v74; // [rsp+C8h] [rbp-11h] BYREF
  __int64 v75; // [rsp+D0h] [rbp-9h] BYREF
  int v76; // [rsp+D8h] [rbp-1h]
  int v77; // [rsp+DCh] [rbp+3h]
  __int64 v78; // [rsp+120h] [rbp+47h] BYREF
  bool v79; // [rsp+128h] [rbp+4Fh]
  int v80; // [rsp+130h] [rbp+57h]

  v80 = a3;
  v10 = *((_DWORD *)this + 12);
  v11 = 335;
  v12 = a8;
  v13 = 335;
  v77 = *((_DWORD *)this + 14);
  if ( (_DWORD)a2 )
    v13 = a2;
  v76 = v10;
  *((_DWORD *)this + 14) = v13;
  v14 = SBC::SbcSampleFrequencyEnumToHz(*(unsigned int *)v12, a2, a3, a4);
  v15 = *((_DWORD *)v12 + 1);
  LODWORD(v71) = v14;
  v16 = *((_DWORD *)v12 + 3);
  v17 = *((_DWORD *)v12 + 2) * v15;
  LODWORD(v75) = v15;
  LODWORD(v74) = v16;
  LODWORD(v66) = *((_DWORD *)v12 + 4);
  LODWORD(a8) = v17;
  MaxL2capPayloadSize = PacketTypes::GetMaxL2capPayloadSize(v18, v19);
  if ( MaxL2capPayloadSize > 0x14F )
    v11 = MaxL2capPayloadSize;
  LODWORD(v70) = v11 - 13;
  v23 = SBC::CalculateBitPool(v12, v21, a6, v22, v61);
  v25 = &WPP_RECORDER_INITIALIZED;
  v69 = 0;
  v26 = 1;
  LODWORD(v65) = a5;
  v68 = 0;
  v27 = 0;
  v67 = 0;
  if ( v23 >= a5 )
  {
    v28 = v10 == 13;
    v29 = a7;
    v30 = v28;
    v79 = v28;
    while ( 1 )
    {
      *((_DWORD *)v12 + 6) = v23;
      if ( SBC::ConfigEncode(v29, v12, v30) >= 0 )
      {
        v31 = *((_DWORD *)v29 + 17);
        if ( v31 <= (int)v70 )
        {
          v32 = (int)v70 / v31;
          if ( (int)v70 / v31 > 15 )
            v32 = 15;
          v33 = v17 * v32;
          v34 = (int)v71;
          LODWORD(v73) = v32;
          v24 = (unsigned int)(v32 * v31 + 13);
          LODWORD(v78) = v24;
          v35 = 1000 * v33 / (int)v71;
          v36 = 8000 * (int)v24 % v35;
          LODWORD(v72) = 8000 * (int)v24 / v35;
          LOBYTE(v36) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                     && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
                     && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
          if ( (_BYTE)v36 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v24) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_DDDD(
              WPP_GLOBAL_Control->AttachedDevice,
              v36,
              v24,
              WPP_GLOBAL_Control->DeviceExtension,
              v62,
              10,
              59,
              (__int64)WPP_3d3725b6925c3aba701f93e71ec4d2db_Traceguids,
              v23,
              v31,
              v32,
              v35);
          }
          LOBYTE(v36) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                     && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
                     && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
          if ( (_BYTE)v36 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v24) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_qD(
              WPP_GLOBAL_Control->AttachedDevice,
              v36,
              v24,
              WPP_GLOBAL_Control->DeviceExtension,
              4,
              16,
              60,
              (__int64)WPP_3d3725b6925c3aba701f93e71ec4d2db_Traceguids,
              8 * v71 * v31,
              (char)a8);
          }
          v37 = v72;
          if ( (int)v72 <= v80 )
          {
            if ( !v27 )
            {
              v38 = a5;
              v39 = a5 <= 20;
              *(_OWORD *)this = 0;
              if ( v39 )
                v38 = 20;
              *((_OWORD *)this + 1) = 0;
              v40 = v23 + 30 * v23 / a6 - 30;
              if ( v40 < v38 )
                v40 = v38;
              LODWORD(v65) = v40;
              *((_QWORD *)this + 4) = 0;
            }
            v27 = v23;
            v41 = v78;
            LODWORD(v69) = v78;
            *((_QWORD *)&v68 + 1) = __PAIR64__(v37, v23);
            v42 = 10000000 * (int)a8 * (__int64)(int)v73 / v34;
            v43 = 10000000 * (int)a8 * (__int64)(int)v73 % v34;
            v17 = (int)a8;
            *(_QWORD *)&v68 = v42;
            *(_QWORD *)&v67 = __PAIR64__(v73, v31);
            DWORD2(v67) = 2 * v66 * (_DWORD)a8;
            LOBYTE(v43) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                       && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
                       && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
            if ( (_BYTE)v43 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v24) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
              WPP_RECORDER_AND_TRACE_SF_ddddd(
                WPP_GLOBAL_Control->AttachedDevice,
                v43,
                v24,
                WPP_GLOBAL_Control->DeviceExtension,
                v62,
                v63,
                61,
                v64,
                v37,
                v78,
                v23,
                v73,
                v31);
              v41 = v78;
            }
            v29 = a7;
            if ( v41 > *((_DWORD *)this + 8) )
            {
              v44 = v68;
              *(_OWORD *)this = v67;
              v45 = v69;
              *((_OWORD *)this + 1) = v44;
              *((_QWORD *)this + 4) = v45;
            }
            goto LABEL_46;
          }
          v17 = (int)a8;
        }
        v29 = a7;
      }
LABEL_46:
      v30 = v79;
      if ( --v23 < (int)v65 )
      {
        v25 = &WPP_RECORDER_INITIALIZED;
        break;
      }
    }
  }
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) == 0
    || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
  {
    v26 = 0;
  }
  LOBYTE(v24) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( !v26 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v47 = v69;
    v48 = HIDWORD(v68);
    v46 = DWORD1(v67);
  }
  else
  {
    LOBYTE(v25) = v26;
    v46 = DWORD1(v67);
    v47 = v69;
    v48 = HIDWORD(v68);
    WPP_RECORDER_AND_TRACE_SF_ddddd(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)v25,
      v24,
      WPP_GLOBAL_Control->DeviceExtension,
      v62,
      v63,
      62,
      v64,
      SBYTE12(v68),
      v69,
      v27,
      SBYTE4(v67),
      v67);
  }
  if ( (unsigned int)dword_14006F0F8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_14006F0F8, 0x400000000000LL, v24) )
  {
    a8 = a9;
    v78 = (int)v74;
    v74 = (int)v66;
    v75 = (int)v75;
    v73 = (int)v67;
    v72 = v46;
    v71 = v27;
    v70 = v47;
    v66 = v48;
    v65 = 50333696;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
      v49,
      (unsigned int)&byte_14006A3E7,
      v50,
      v51,
      (__int64)&v65,
      (__int64)&v66,
      (__int64)&v70,
      (__int64)&v71,
      (__int64)&v72,
      (__int64)&v73,
      (__int64)&v75,
      (__int64)&v74,
      (__int64)&v78,
      (__int64)&a8);
  }
  v52 = *((_DWORD *)this + 6);
  if ( v52 >= 2 )
  {
    v54 = a7;
    v55 = v76 == 13;
    *((_DWORD *)v12 + 6) = v52;
    if ( SBC::ConfigEncode(v54, v12, v55) >= 0 )
    {
      v56 = v77;
      if ( *((_DWORD *)this + 14) > v77 )
      {
        Pool2 = (void *)ExAllocatePool2(64, *((int *)this + 14), 1128354882);
        v58 = Pool2;
        if ( !Pool2 )
        {
          v53 = -1073741670;
          goto LABEL_65;
        }
        v59 = (void *)*((_QWORD *)this + 8);
        if ( v59 )
        {
          memmove(Pool2, *((const void **)this + 8), v56);
          ExFreePoolWithTag(v59, 0x43415442u);
        }
        *((_QWORD *)this + 8) = v58;
      }
      return 0;
    }
  }
  v53 = -1073741811;
LABEL_65:
  A2dpInbandSbcCodec::OutParms::Cleanup(this);
  return v53;
}

```

## disassembly

```asm
0x14003e748  mov     [rsp-8+arg_18], rbx
0x14003e74d  mov     [rsp-8+arg_10], r8d
0x14003e752  push    rbp
0x14003e753  push    rsi
0x14003e754  push    rdi
0x14003e755  push    r12
0x14003e757  push    r13
0x14003e759  push    r14
0x14003e75b  push    r15
0x14003e75d  lea     rbp, [rsp-7]
0x14003e762  sub     rsp, 0E0h
0x14003e769  mov     eax, [rcx+38h]
0x14003e76c  mov     rdi, rcx
0x14003e76f  mov     r14d, [rcx+30h]
0x14003e773  mov     ebx, 14Fh
0x14003e778  mov     r12, [rbp+37h+arg_38]
0x14003e77c  test    edx, edx
0x14003e77e  mov     r10d, ebx
0x14003e781  mov     [rbp+37h+var_34], eax
0x14003e784  cmovnz  r10d, edx
0x14003e788  mov     [rbp+37h+var_38], r14d
0x14003e78c  mov     [rcx+38h], r10d
0x14003e790  mov     ecx, [r12]
0x14003e794  call    ?SbcSampleFrequencyEnumToHz@SBC@@SAHW4SbcSampleFrequency@@@Z; SBC::SbcSampleFrequencyEnumToHz(SbcSampleFrequency)
0x14003e799  mov     ecx, [r12+4]
0x14003e79e  mov     edx, r10d; unsigned int
0x14003e7a1  mov     r13d, ecx
0x14003e7a4  mov     dword ptr [rbp+37h+var_60], eax
0x14003e7a7  mov     eax, [r12+0Ch]
0x14003e7ac  imul    r13d, [r12+8]
0x14003e7b2  mov     dword ptr [rbp+37h+var_40], ecx
0x14003e7b5  mov     rcx, r9; this
0x14003e7b8  mov     dword ptr [rbp+37h+var_48], eax
0x14003e7bb  mov     eax, [r12+10h]
0x14003e7c0  mov     dword ptr [rbp+37h+var_98], eax
0x14003e7c3  mov     dword ptr [rbp+37h+arg_38], r13d
0x14003e7c7  call    ?GetMaxL2capPayloadSize@PacketTypes@@QEBAKK@Z; PacketTypes::GetMaxL2capPayloadSize(ulong)
0x14003e7cc  mov     r8d, [rbp+37h+arg_28]; int
0x14003e7d0  cmp     eax, ebx
0x14003e7d2  mov     rcx, r12; struct SBC_CONFIG *
0x14003e7d5  cmova   ebx, eax
0x14003e7d8  add     ebx, 0FFFFFFF3h
0x14003e7db  mov     dword ptr [rbp+37h+var_68], ebx
0x14003e7de  call    ?CalculateBitPool@SBC@@SAHAEBUSBC_CONFIG@@HHPEAH1@Z; SBC::CalculateBitPool(SBC_CONFIG const &,int,int,int *,int *)
0x14003e7e3  mov     ebx, eax
0x14003e7e5  lea     rdx, WPP_RECORDER_INITIALIZED
0x14003e7ec  xor     eax, eax
0x14003e7ee  xorps   xmm0, xmm0
0x14003e7f1  mov     [rbp+37h+var_70], rax
0x14003e7f5  mov     esi, 1
0x14003e7fa  mov     eax, [rbp+37h+arg_20]
0x14003e7fd  mov     dword ptr [rbp+37h+var_A0], eax
0x14003e800  movups  [rbp+37h+var_80], xmm0
0x14003e804  mov     r15d, dword ptr [rbp+37h+var_80+8]
0x14003e808  movups  [rbp+37h+var_90], xmm0
0x14003e80c  cmp     ebx, eax
0x14003e80e  jl      loc_14003EAE6
0x14003e814  cmp     r14d, 0Dh
0x14003e818  mov     r14, [rbp+37h+arg_30]
0x14003e81c  setz    al
0x14003e81f  mov     [rbp+37h+arg_8], al
0x14003e822  mov     r8b, al; bool
0x14003e825  mov     [r12+18h], ebx
0x14003e82a  mov     rdx, r12; struct SBC_CONFIG *
0x14003e82d  mov     rcx, r14; this
0x14003e830  call    ?ConfigEncode@SBC@@QEAAJAEBUSBC_CONFIG@@_N@Z; SBC::ConfigEncode(SBC_CONFIG const &,bool)
0x14003e835  test    eax, eax
0x14003e837  js      loc_14003EAD1
0x14003e83d  movsxd  r14, dword ptr [r14+44h]
0x14003e841  mov     eax, dword ptr [rbp+37h+var_68]
0x14003e844  cmp     r14d, eax
0x14003e847  jg      loc_14003EACD
0x14003e84d  cdq
0x14003e84e  mov     r8d, r14d
0x14003e851  idiv    r14d
0x14003e854  mov     r11d, eax
0x14003e857  mov     eax, 0Fh
0x14003e85c  cmp     r11d, eax
0x14003e85f  cmovg   r11d, eax
0x14003e863  mov     ecx, r11d
0x14003e866  imul    r8d, r11d
0x14003e86a  imul    ecx, r13d
0x14003e86e  movsxd  r13, dword ptr [rbp+37h+var_60]
0x14003e872  mov     dword ptr [rbp+37h+var_50], r11d
0x14003e876  add     r8d, 0Dh
0x14003e87a  imul    eax, ecx, 3E8h
0x14003e880  mov     dword ptr [rbp+37h+arg_0], r8d
0x14003e884  cdq
0x14003e885  idiv    r13d
0x14003e888  mov     r9d, eax
0x14003e88b  imul    eax, r8d, 1F40h
0x14003e892  cdq
0x14003e893  idiv    r9d
0x14003e896  mov     dword ptr [rbp+37h+var_58], eax
0x14003e899  mov     r10, cs:WPP_GLOBAL_Control
0x14003e8a0  lea     rax, WPP_GLOBAL_Control
0x14003e8a7  cmp     r10, rax
0x14003e8aa  jz      short loc_14003E8C2
0x14003e8ac  test    dword ptr [r10+2Ch], 200h
0x14003e8b4  jz      short loc_14003E8C2
0x14003e8b6  cmp     byte ptr [r10+29h], 4
0x14003e8bb  jb      short loc_14003E8C2
0x14003e8bd  mov     dl, sil
0x14003e8c0  jmp     short loc_14003E8C4
0x14003e8c2  xor     dl, dl
0x14003e8c4  lea     rax, WPP_RECORDER_INITIALIZED
0x14003e8cb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003e8d2  setnz   r8b
0x14003e8d6  test    dl, dl
0x14003e8d8  jnz     short loc_14003E8DF
0x14003e8da  test    r8b, r8b
0x14003e8dd  jz      short loc_14003E91A
0x14003e8df  mov     dword ptr [rsp+110h+var_B8], r9d
0x14003e8e4  lea     rcx, WPP_3d3725b6925c3aba701f93e71ec4d2db_Traceguids
0x14003e8eb  mov     r9, [r10+40h]
0x14003e8ef  mov     dword ptr [rsp+110h+var_C0], r11d
0x14003e8f4  mov     dword ptr [rsp+110h+var_C8], r14d
0x14003e8f9  mov     dword ptr [rsp+110h+var_D0], ebx
0x14003e8fd  mov     [rsp+110h+var_D8], rcx
0x14003e902  mov     rcx, [r10+18h]
0x14003e906  mov     word ptr [rsp+110h+var_E0], 3Bh ; ';'
0x14003e90d  mov     dword ptr [rsp+110h+var_E8], 0Ah
0x14003e915  call    WPP_RECORDER_AND_TRACE_SF_DDDD
0x14003e91a  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e921  lea     rax, WPP_GLOBAL_Control
0x14003e928  cmp     rcx, rax
0x14003e92b  jz      short loc_14003E941
0x14003e92d  test    dword ptr [rcx+2Ch], 8000h
0x14003e934  jz      short loc_14003E941
0x14003e936  cmp     byte ptr [rcx+29h], 4
0x14003e93a  jb      short loc_14003E941
0x14003e93c  mov     dl, sil
0x14003e93f  jmp     short loc_14003E943
0x14003e941  xor     dl, dl
0x14003e943  lea     rax, WPP_RECORDER_INITIALIZED
0x14003e94a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003e951  setnz   r8b
0x14003e955  test    dl, dl
0x14003e957  jnz     short loc_14003E95E
0x14003e959  test    r8b, r8b
0x14003e95c  jz      short loc_14003E9A4
0x14003e95e  mov     r9d, dword ptr [rbp+37h+arg_38]
0x14003e962  mov     rax, r14
0x14003e965  mov     dword ptr [rsp+110h+var_C8], r9d
0x14003e96a  mov     r9, [rcx+40h]
0x14003e96e  mov     rcx, [rcx+18h]
0x14003e972  imul    rax, r13
0x14003e976  shl     rax, 3
0x14003e97a  mov     [rsp+110h+var_D0], rax
0x14003e97f  lea     rax, WPP_3d3725b6925c3aba701f93e71ec4d2db_Traceguids
0x14003e986  mov     [rsp+110h+var_D8], rax
0x14003e98b  mov     word ptr [rsp+110h+var_E0], 3Ch ; '<'
0x14003e992  mov     dword ptr [rsp+110h+var_E8], 10h
0x14003e99a  mov     byte ptr [rsp+110h+var_F0], 4
0x14003e99f  call    WPP_RECORDER_AND_TRACE_SF_qD
0x14003e9a4  mov     r11d, dword ptr [rbp+37h+var_58]
0x14003e9a8  cmp     r11d, [rbp+37h+arg_10]
0x14003e9ac  jg      loc_14003EAC9
0x14003e9b2  test    r15d, r15d
0x14003e9b5  jnz     short loc_14003E9E7
0x14003e9b7  mov     ecx, [rbp+37h+arg_20]
0x14003e9ba  lea     edx, [r15+14h]
0x14003e9be  cmp     ecx, edx
0x14003e9c0  xorps   xmm0, xmm0
0x14003e9c3  movups  xmmword ptr [rdi], xmm0
0x14003e9c6  cmovle  ecx, edx
0x14003e9c9  imul    eax, ebx, 1Eh
0x14003e9cc  movups  xmmword ptr [rdi+10h], xmm0
0x14003e9d0  cdq
0x14003e9d1  idiv    [rbp+37h+arg_28]
0x14003e9d4  add     eax, 0FFFFFFE2h
0x14003e9d7  add     eax, ebx
0x14003e9d9  cmp     eax, ecx
0x14003e9db  cmovl   eax, ecx
0x14003e9de  mov     dword ptr [rbp+37h+var_A0], eax
0x14003e9e1  xor     eax, eax
0x14003e9e3  mov     [rdi+20h], rax
0x14003e9e7  movsxd  r9, dword ptr [rbp+37h+var_50]
0x14003e9eb  mov     r15d, ebx
0x14003e9ee  movsxd  rax, dword ptr [rbp+37h+arg_38]
0x14003e9f2  mov     rcx, r9
0x14003e9f5  mov     r10d, dword ptr [rbp+37h+arg_0]
0x14003e9f9  imul    rcx, rax
0x14003e9fd  mov     dword ptr [rbp+37h+var_80+0Ch], r11d
0x14003ea01  imul    rax, rcx, 989680h
0x14003ea08  mov     dword ptr [rbp+37h+var_70], r10d
0x14003ea0c  cqo
0x14003ea0e  mov     dword ptr [rbp+37h+var_80+8], ebx
0x14003ea11  idiv    r13
0x14003ea14  mov     r13d, dword ptr [rbp+37h+arg_38]
0x14003ea18  mov     qword ptr [rbp+37h+var_80], rax
0x14003ea1c  mov     eax, r13d
0x14003ea1f  imul    eax, dword ptr [rbp+37h+var_98]
0x14003ea23  mov     dword ptr [rbp+37h+var_90+4], r9d
0x14003ea27  mov     dword ptr [rbp+37h+var_90], r14d
0x14003ea2b  add     eax, eax
0x14003ea2d  mov     dword ptr [rbp+37h+var_90+8], eax
0x14003ea30  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ea37  lea     rax, WPP_GLOBAL_Control
0x14003ea3e  cmp     rcx, rax
0x14003ea41  jz      short loc_14003EA57
0x14003ea43  test    dword ptr [rcx+2Ch], 8000h
0x14003ea4a  jz      short loc_14003EA57
0x14003ea4c  cmp     byte ptr [rcx+29h], 4
0x14003ea50  jb      short loc_14003EA57
0x14003ea52  mov     dl, sil
0x14003ea55  jmp     short loc_14003EA59
0x14003ea57  xor     dl, dl
0x14003ea59  lea     rax, WPP_RECORDER_INITIALIZED
0x14003ea60  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003ea67  setnz   r8b
0x14003ea6b  test    dl, dl
0x14003ea6d  jnz     short loc_14003EA74
0x14003ea6f  test    r8b, r8b
0x14003ea72  jz      short loc_14003EAA4
0x14003ea74  mov     dword ptr [rsp+110h+var_B0], r14d
0x14003ea79  mov     dword ptr [rsp+110h+var_B8], r9d
0x14003ea7e  mov     r9, [rcx+40h]
0x14003ea82  mov     rcx, [rcx+18h]
0x14003ea86  mov     dword ptr [rsp+110h+var_C0], ebx
0x14003ea8a  mov     dword ptr [rsp+110h+var_C8], r10d
0x14003ea8f  mov     dword ptr [rsp+110h+var_D0], r11d
0x14003ea94  mov     word ptr [rsp+110h+var_E0], 3Dh ; '='
0x14003ea9b  call    WPP_RECORDER_AND_TRACE_SF_ddddd
0x14003eaa0  mov     r10d, dword ptr [rbp+37h+arg_0]
0x14003eaa4  mov     r14, [rbp+37h+arg_30]
0x14003eaa8  cmp     r10d, [rdi+20h]
0x14003eaac  jle     short loc_14003EAD1
0x14003eaae  movups  xmm0, [rbp+37h+var_90]
0x14003eab2  movups  xmm1, [rbp+37h+var_80]
0x14003eab6  movups  xmmword ptr [rdi], xmm0
0x14003eab9  movsd   xmm0, [rbp+37h+var_70]
0x14003eabe  movups  xmmword ptr [rdi+10h], xmm1
0x14003eac2  movsd   qword ptr [rdi+20h], xmm0
0x14003eac7  jmp     short loc_14003EAD1
0x14003eac9  mov     r13d, dword ptr [rbp+37h+arg_38]
0x14003eacd  mov     r14, [rbp+37h+arg_30]
0x14003ead1  mov     al, [rbp+37h+arg_8]
0x14003ead4  sub     ebx, esi
0x14003ead6  cmp     ebx, dword ptr [rbp+37h+var_A0]
0x14003ead9  jge     loc_14003E822
0x14003eadf  lea     rdx, WPP_RECORDER_INITIALIZED
0x14003eae6  mov     rcx, cs:WPP_GLOBAL_Control
0x14003eaed  lea     rax, WPP_GLOBAL_Control
0x14003eaf4  cmp     rcx, rax
0x14003eaf7  jz      short loc_14003EB08
0x14003eaf9  test    dword ptr [rcx+2Ch], 8000h
0x14003eb00  jz      short loc_14003EB08
0x14003eb02  cmp     byte ptr [rcx+29h], 4
0x14003eb06  jnb     short loc_14003EB0B
0x14003eb08  xor     sil, sil
0x14003eb0b  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14003eb12  setnz   r8b
0x14003eb16  test    sil, sil
0x14003eb19  jnz     short loc_14003EB20
0x14003eb1b  test    r8b, r8b
0x14003eb1e  jz      short loc_14003EB5E
0x14003eb20  mov     eax, dword ptr [rbp+37h+var_90]
0x14003eb23  mov     dl, sil
0x14003eb26  mov     r9, [rcx+40h]
0x14003eb2a  mov     r13d, dword ptr [rbp+37h+var_90+4]
0x14003eb2e  mov     ebx, dword ptr [rbp+37h+var_70]
0x14003eb31  mov     r14d, dword ptr [rbp+37h+var_80+0Ch]
0x14003eb35  mov     rcx, [rcx+18h]
0x14003eb39  mov     dword ptr [rsp+110h+var_B0], eax
0x14003eb3d  mov     dword ptr [rsp+110h+var_B8], r13d
0x14003eb42  mov     dword ptr [rsp+110h+var_C0], r15d
0x14003eb47  mov     dword ptr [rsp+110h+var_C8], ebx
0x14003eb4b  mov     dword ptr [rsp+110h+var_D0], r14d
0x14003eb50  mov     word ptr [rsp+110h+var_E0], 3Eh ; '>'
0x14003eb57  call    WPP_RECORDER_AND_TRACE_SF_ddddd
0x14003eb5c  jmp     short loc_14003EB69
0x14003eb5e  mov     ebx, dword ptr [rbp+37h+var_70]
0x14003eb61  mov     r14d, dword ptr [rbp+37h+var_80+0Ch]
0x14003eb65  mov     r13d, dword ptr [rbp+37h+var_90+4]
0x14003eb69  mov     eax, cs:dword_14006F0F8
0x14003eb6f  cmp     eax, 5
0x14003eb72  jbe     loc_14003EC4B
0x14003eb78  mov     rdx, 400000000000h
0x14003eb82  lea     rcx, dword_14006F0F8
0x14003eb89  call    _tlgKeywordOn
0x14003eb8e  test    al, al
0x14003eb90  jz      loc_14003EC4B
0x14003eb96  mov     rax, [rbp+37h+arg_40]
0x14003eb9d  lea     rdx, byte_14006A3E7
0x14003eba4  mov     [rbp+37h+arg_38], rax
0x14003eba8  movsxd  rax, dword ptr [rbp+37h+var_48]
0x14003ebac  mov     [rbp+37h+arg_0], rax
0x14003ebb0  movsxd  rax, dword ptr [rbp+37h+var_98]
0x14003ebb4  mov     [rbp+37h+var_48], rax
0x14003ebb8  movsxd  rax, dword ptr [rbp+37h+var_40]
0x14003ebbc  mov     [rbp+37h+var_40], rax
0x14003ebc0  movsxd  rax, dword ptr [rbp+37h+var_90]
0x14003ebc4  mov     [rbp+37h+var_50], rax
0x14003ebc8  movsxd  rax, r13d
0x14003ebcb  mov     [rbp+37h+var_58], rax
0x14003ebcf  movsxd  rax, r15d
0x14003ebd2  mov     [rbp+37h+var_60], rax
0x14003ebd6  movsxd  rax, ebx
0x14003ebd9  mov     [rbp+37h+var_68], rax
  ... truncated ...
```
