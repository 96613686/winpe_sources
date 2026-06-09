# TpmCreateClaimSubjectOnly

- ea: `0x180051618`
- end: `0x180051d7f`
- name: `TpmCreateClaimSubjectOnly`
- size: `1895`
- prototype: `__int64 __fastcall(int, int, int, int, rsize_t, __int64, int, __int64, int)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180050bb0`

## callees

- `0x18000f240`
- `0x180015660`
- `0x1800157c0`
- `0x18001c308`
- `0x180048094`
- `0x180051618`
- `0x180051d88`
- `0x180051e68`
- `0x180059034`
- `0x1800764d0`
- `0x1800768a0`
- `0x180076998`
- `0x18007704c`
- `0x18009366c`
- `0x180097b70`

## import_xrefs

- `tbs!Tbsi_GetDeviceInfo` at `0x1800519c2`
- `tbs!Tbsi_GetDeviceInfo` at `0x1800519c2`

## string_xrefs

- `0x180051663`: `TpmCreateClaimSubjectOnly`

## pseudocode

```c
__int64 __fastcall TpmCreateClaimSubjectOnly(
        __int64 a1,
        void *a2,
        void *a3,
        unsigned __int8 *a4,
        rsize_t a5,
        __int64 a6,
        int a7,
        __int64 a8,
        int a9)
{
  void *v12; // rdx
  unsigned __int8 *v13; // rdi
  size_t v14; // r15
  unsigned __int8 *v15; // r14
  unsigned int v16; // r12d
  int Property; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  unsigned __int8 *v22; // rax
  void *v23; // rdx
  int v24; // eax
  bool v25; // si
  int v26; // ebx
  int v27; // eax
  char v28; // al
  int v29; // eax
  int v30; // eax
  int v31; // eax
  unsigned int v32; // r15d
  char v33; // cl
  int v34; // edx
  unsigned __int8 *Source; // rax
  int v36; // eax
  int v37; // eax
  size_t v38; // r12
  int v39; // esi
  unsigned __int8 *v40; // rax
  unsigned __int8 *v41; // rbx
  const struct std::nothrow_t *v42; // rdx
  int v43; // eax
  int v44; // eax
  int v45; // eax
  __int64 v46; // rax
  unsigned __int8 *v47; // rcx
  const struct std::nothrow_t *v48; // rdx
  unsigned __int8 *v49; // rax
  __int64 v50; // rax
  unsigned __int8 *v51; // rcx
  unsigned int v52; // ebx
  rsize_t v54; // [rsp+20h] [rbp-E0h]
  rsize_t SourceSize; // [rsp+40h] [rbp-C0h]
  rsize_t SourceSizea; // [rsp+40h] [rbp-C0h]
  rsize_t SourceSizeb; // [rsp+40h] [rbp-C0h]
  rsize_t v58; // [rsp+50h] [rbp-B0h]
  int DeviceInfo; // [rsp+60h] [rbp-A0h] BYREF
  char v60[4]; // [rsp+64h] [rbp-9Ch] BYREF
  int Size; // [rsp+68h] [rbp-98h] BYREF
  int Size_4; // [rsp+6Ch] [rbp-94h]
  size_t v63; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v64; // [rsp+78h] [rbp-88h] BYREF
  int v65; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned int v66; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v67; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned __int8 *v68; // [rsp+88h] [rbp-78h] BYREF
  void *v69; // [rsp+90h] [rbp-70h] BYREF
  TBS_HCONTEXT hContext; // [rsp+98h] [rbp-68h] BYREF
  int v71[2]; // [rsp+A0h] [rbp-60h]
  int v72[2]; // [rsp+A8h] [rbp-58h]
  void *v73; // [rsp+B0h] [rbp-50h]
  int *v74[3]; // [rsp+B8h] [rbp-48h] BYREF
  int *v75[3]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v76; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v77; // [rsp+F8h] [rbp-8h] BYREF
  int v78; // [rsp+108h] [rbp+8h]

  *(_QWORD *)v71 = a6;
  v73 = a2;
  *(_QWORD *)v72 = a8;
  v68 = a4;
  DeviceInfo = 0;
  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v75, L"TpmCreateClaimSubjectOnly", &DeviceInfo);
  hContext = 0;
  v67 = 0;
  v13 = 0;
  v66 = 0;
  LODWORD(v14) = 0;
  v60[0] = 0;
  v15 = 0;
  v69 = 0;
  v16 = 0;
  v78 = 0;
  Size = 0;
  v63 = 0;
  v64 = 0;
  v76 = 0;
  v77 = 0;
  if ( !a1 || !a2 || !a3 || *(_QWORD *)v71 && !a7 || !*(_QWORD *)v72 || (a9 & 2) == 0 )
    goto LABEL_67;
  Property = ProviderGetProperty(a1, 0x41u, (__int64)&hContext, 8u, (int)&Size);
  DeviceInfo = SecurityStatusFromHResult(Property);
  if ( DeviceInfo < 0 )
    goto LABEL_68;
  v18 = ProviderGetProperty((__int64)a2, 0x41u, (__int64)&v67, 4u, (int)&Size);
  DeviceInfo = SecurityStatusFromHResult(v18);
  if ( DeviceInfo < 0 )
    goto LABEL_68;
  v19 = ProviderGetProperty((__int64)a2, 0xDu, (__int64)&v64, 4u, (int)&Size);
  DeviceInfo = SecurityStatusFromHResult(v19);
  if ( DeviceInfo < 0 )
    goto LABEL_68;
  v20 = ProviderGetProperty((__int64)a3, 0x41u, (__int64)&v66, 4u, (int)&Size);
  DeviceInfo = SecurityStatusFromHResult(v20);
  if ( DeviceInfo < 0 )
    goto LABEL_68;
  v21 = ProviderExportKey(a3, v12, L"OpaqueKeyBlob", 0, 0, (unsigned int *)&Size, 0);
  DeviceInfo = SecurityStatusFromHResult(v21);
  if ( DeviceInfo < 0 )
    goto LABEL_68;
  v14 = (unsigned int)Size;
  Size_4 = Size;
  if ( !Size )
    goto LABEL_67;
  v22 = (unsigned __int8 *)operator new[]((unsigned int)Size, (const struct std::nothrow_t *)&std::nothrow);
  v13 = v22;
  if ( !v22 )
  {
    DeviceInfo = -2147024882;
    goto LABEL_68;
  }
  memset_0(v22, 0, v14);
  DeviceInfo = 0;
  v24 = ProviderExportKey(a3, v23, L"OpaqueKeyBlob", v13, v14, (unsigned int *)&Size, 0);
  DeviceInfo = SecurityStatusFromHResult(v24);
  if ( DeviceInfo >= 0 )
  {
    v65 = 0;
    KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v74, L"KeyPolicyNeedsPinForCertify", &v65);
    v25 = 1;
    if ( (unsigned int)v14 >= 0x34 && *((_DWORD *)v13 + 2) == 2 )
      v25 = *((_DWORD *)v13 + 8) < 0xB0u;
    v26 = v65;
    KspFunctionLogger::~KspFunctionLogger(v74);
    DeviceInfo = v26;
    if ( v26 >= 0 )
    {
      if ( v25 )
      {
        v27 = ProviderGetProperty((__int64)a3, 0x39u, (__int64)v60, 1u, (int)&Size);
        DeviceInfo = SecurityStatusFromHResult(v27);
        if ( DeviceInfo < 0 )
          goto LABEL_68;
        v28 = v60[0];
        if ( !v60[0] )
          goto LABEL_28;
        v29 = ProviderGetProperty((__int64)a3, 0x57u, 0, 0, (int)&Size);
        DeviceInfo = SecurityStatusFromHResult(v29);
        if ( DeviceInfo < 0 )
          goto LABEL_68;
        v16 = Size;
        HIDWORD(v63) = Size;
        v30 = AllocateAndZero(&v69, (unsigned int)Size);
        v15 = (unsigned __int8 *)v69;
        DeviceInfo = v30;
        if ( v30 < 0 )
          goto LABEL_68;
        v31 = ProviderGetProperty((__int64)a3, 0x57u, (__int64)v69, v16, (int)&Size);
        DeviceInfo = SecurityStatusFromHResult(v31);
        if ( DeviceInfo < 0 )
          goto LABEL_68;
      }
      v28 = v60[0];
      if ( v60[0] )
      {
LABEL_29:
        DeviceInfo = Tbsi_GetDeviceInfo(16, &v76);
        if ( DeviceInfo < 0 )
          goto LABEL_68;
        if ( DWORD1(v76) == 1 )
        {
          if ( a9 == 258 )
          {
            DeviceInfo = -2144795643;
            goto LABEL_68;
          }
          v32 = a5;
          if ( v68 && (_DWORD)a5 )
          {
            v33 = 1;
            v34 = a5;
          }
          else
          {
            v33 = 0;
            v34 = 20;
          }
          Source = (unsigned __int8 *)&v77;
          if ( v33 )
            Source = v68;
          LODWORD(SourceSize) = v34;
          v36 = KeyAtt_PcpCertifyKey12(
                  hContext,
                  v67,
                  0,
                  0,
                  v66,
                  v15,
                  v16,
                  Source,
                  SourceSize,
                  0,
                  0,
                  (unsigned int *)&v63);
        }
        else
        {
          if ( DWORD1(v76) != 2 )
          {
            DeviceInfo = -2144795619;
            goto LABEL_68;
          }
          v32 = a5;
          v37 = PCP20CommonpCertifyKey((TpmObject *)a3, v73, v15, v16, v68, a5, 0, 0, (unsigned int *)&v63);
          v36 = SecurityStatusFromHResult(v37);
        }
        DeviceInfo = v36;
        if ( v36 < 0 )
        {
LABEL_43:
          LODWORD(v14) = Size_4;
          goto LABEL_68;
        }
        if ( v64 > (unsigned int)v63 )
        {
          DeviceInfo = -2147467259;
          goto LABEL_43;
        }
        v38 = (unsigned int)v63;
        if ( (_DWORD)v63 )
        {
          v39 = v63 - v64;
          v40 = (unsigned __int8 *)operator new[]((unsigned int)v63, (const struct std::nothrow_t *)&std::nothrow);
          v41 = v40;
          if ( !v40 )
          {
            v16 = HIDWORD(v63);
            DeviceInfo = -2147024882;
            goto LABEL_43;
          }
          memset_0(v40, 0, v38);
          DeviceInfo = 0;
          if ( DWORD1(v76) == 1 )
          {
            LODWORD(SourceSizea) = v32;
            v43 = KeyAtt_PcpCertifyKey12(
                    hContext,
                    v67,
                    0,
                    0,
                    v66,
                    v15,
                    HIDWORD(v63),
                    v68,
                    SourceSizea,
                    v41,
                    v63,
                    (unsigned int *)&Size);
          }
          else
          {
            if ( DWORD1(v76) != 2 )
            {
              DeviceInfo = -2144795619;
              goto LABEL_61;
            }
            v45 = PCP20CommonpCertifyKey(
                    (TpmObject *)a3,
                    v73,
                    v15,
                    HIDWORD(v63),
                    v68,
                    v32,
                    v41,
                    v63,
                    (unsigned int *)&Size);
            v43 = SecurityStatusFromHResult(v45);
          }
          DeviceInfo = v43;
          if ( v43 >= 0 )
          {
            LODWORD(v14) = Size_4;
            LODWORD(v68) = 0;
            v65 = v39;
            if ( a9 == 2 )
            {
              LODWORD(v58) = v64;
              LODWORD(SourceSizeb) = v39;
              LODWORD(v54) = Size_4;
              v44 = AssembleStandardSubjectAttestationOutput(
                      v72[0],
                      v71[0],
                      a7,
                      (int)v13,
                      v54,
                      (__int64)v41,
                      v63,
                      (__int64)&v68,
                      SourceSizeb,
                      (__int64)&v65,
                      v58);
            }
            else
            {
              if ( a9 != 258 )
              {
                DeviceInfo = -2144795620;
                goto LABEL_62;
              }
              LODWORD(v58) = v64;
              LODWORD(SourceSizeb) = v39;
              v44 = AssembleWebAuthSubjectAttestationOutput(
                      v72[0],
                      v71[0],
                      a7,
                      (int)v13,
                      Size_4,
                      (__int64)v41,
                      v63,
                      (__int64)&v68,
                      SourceSizeb,
                      (__int64)&v65,
                      v58);
            }
            DeviceInfo = v44;
LABEL_62:
            v46 = (unsigned int)v63;
            if ( (_DWORD)v63 )
            {
              v47 = v41;
              do
              {
                *v47++ = 0;
                --v46;
              }
              while ( v46 );
            }
            operator delete(v41, v42);
            v16 = HIDWORD(v63);
            goto LABEL_68;
          }
LABEL_61:
          LODWORD(v14) = Size_4;
          goto LABEL_62;
        }
        v16 = HIDWORD(v63);
        LODWORD(v14) = Size_4;
LABEL_67:
        DeviceInfo = -2147024809;
        goto LABEL_68;
      }
LABEL_28:
      v15 = 0;
      v16 &= -(v28 != 0);
      HIDWORD(v63) = v16;
      goto LABEL_29;
    }
  }
LABEL_68:
  if ( v15 )
  {
    v48 = (const struct std::nothrow_t *)v16;
    if ( v16 )
    {
      v49 = v15;
      do
      {
        *v49++ = 0;
        v48 = (const struct std::nothrow_t *)((char *)v48 - 1);
      }
      while ( v48 );
    }
    operator delete(v15, v48);
  }
  if ( v13 )
  {
    v50 = (unsigned int)v14;
    if ( (_DWORD)v14 )
    {
      v51 = v13;
      do
      {
        *v51++ = 0;
        --v50;
      }
      while ( v50 );
    }
    operator delete(v13, (const struct std::nothrow_t *)v12);
  }
  v52 = DeviceInfo;
  KspFunctionLogger::~KspFunctionLogger(v75);
  return v52;
}

```

## disassembly

```asm
0x180051618  push    rbp
0x18005161a  push    rbx
0x18005161b  push    rsi
0x18005161c  push    rdi
0x18005161d  push    r12
0x18005161f  push    r13
0x180051621  push    r14
0x180051623  push    r15
0x180051625  lea     rbp, [rsp-28h]
0x18005162a  sub     rsp, 128h
0x180051631  mov     rax, cs:__security_cookie
0x180051638  xor     rax, rsp
0x18005163b  mov     [rbp+60h+var_50], rax
0x18005163f  mov     rax, [rbp+60h+arg_28]
0x180051646  mov     r13, r8
0x180051649  mov     qword ptr [rbp+60h+var_C0], rax
0x18005164d  lea     r8, [rsp+160h+var_100]; int *
0x180051652  mov     rax, [rbp+60h+arg_38]
0x180051659  mov     rsi, rdx
0x18005165c  mov     [rbp+60h+var_B0], rdx
0x180051660  mov     rbx, rcx
0x180051663  lea     rdx, aTpmcreateclaim; "TpmCreateClaimSubjectOnly"
0x18005166a  mov     qword ptr [rbp+60h+var_B8], rax
0x18005166e  lea     rcx, [rbp+60h+var_90]; this
0x180051672  mov     [rbp+60h+var_D8], r9
0x180051676  mov     [rsp+160h+var_100], 0
0x18005167e  call    ??0KspFunctionLogger@@QEAA@QEBGAEBJ@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,long const &)
0x180051683  xor     ecx, ecx
0x180051685  xor     eax, eax
0x180051687  mov     [rbp+60h+hContext], rcx
0x18005168b  xorps   xmm0, xmm0
0x18005168e  mov     [rbp+60h+var_DC], ecx
0x180051691  mov     edi, ecx
0x180051693  mov     [rbp+60h+var_E0], ecx
0x180051696  mov     r15d, ecx
0x180051699  mov     [rsp+160h+var_FC], cl
0x18005169d  mov     r14d, ecx
0x1800516a0  mov     [rbp+60h+var_D0], rcx
0x1800516a4  mov     r12d, ecx
0x1800516a7  mov     dword ptr [rsp+160h+var_F0+4], ecx
0x1800516ab  mov     [rbp+60h+var_58], eax
0x1800516ae  mov     dword ptr [rsp+160h+Size], ecx
0x1800516b2  mov     dword ptr [rsp+160h+var_F0], ecx
0x1800516b6  mov     dword ptr [rsp+160h+var_E8], ecx
0x1800516ba  movups  [rbp+60h+var_78], xmm0
0x1800516be  movups  [rbp+60h+var_68], xmm0
0x1800516c2  test    rbx, rbx
0x1800516c5  jz      loc_180051CF2
0x1800516cb  test    rsi, rsi
0x1800516ce  jz      loc_180051CF2
0x1800516d4  test    r13, r13
0x1800516d7  jz      loc_180051CF2
0x1800516dd  cmp     qword ptr [rbp+60h+var_C0], rcx
0x1800516e1  jz      short loc_1800516EF
0x1800516e3  cmp     [rbp+60h+arg_30], ecx
0x1800516e9  jz      loc_180051CF2
0x1800516ef  cmp     qword ptr [rbp+60h+var_B8], rcx
0x1800516f3  jz      loc_180051CF2
0x1800516f9  test    byte ptr [rbp+60h+arg_40], 2
0x180051700  jz      loc_180051CF2
0x180051706  mov     r9d, 8
0x18005170c  lea     rax, [rsp+160h+Size]
0x180051711  lea     r8, [rbp+60h+hContext]
0x180051715  mov     [rsp+160h+var_140], rax
0x18005171a  mov     rcx, rbx
0x18005171d  lea     edx, [r9+39h]
0x180051721  call    ?ProviderGetProperty@@YAJPEAXW4KspProp@@PEAEKPEAK@Z; ProviderGetProperty(void *,KspProp,uchar *,ulong,ulong *)
0x180051726  mov     ecx, eax; int
0x180051728  call    ?SecurityStatusFromHResult@@YAJJ@Z; SecurityStatusFromHResult(long)
0x18005172d  mov     [rsp+160h+var_100], eax
0x180051731  test    eax, eax
0x180051733  js      loc_180051CFA
0x180051739  mov     ebx, 4
0x18005173e  lea     rax, [rsp+160h+Size]
0x180051743  mov     r9d, ebx
0x180051746  mov     [rsp+160h+var_140], rax
0x18005174b  lea     r8, [rbp+60h+var_DC]
0x18005174f  mov     rcx, rsi
0x180051752  lea     edx, [rbx+3Dh]
0x180051755  call    ?ProviderGetProperty@@YAJPEAXW4KspProp@@PEAEKPEAK@Z; ProviderGetProperty(void *,KspProp,uchar *,ulong,ulong *)
0x18005175a  mov     ecx, eax; int
0x18005175c  call    ?SecurityStatusFromHResult@@YAJJ@Z; SecurityStatusFromHResult(long)
0x180051761  mov     [rsp+160h+var_100], eax
0x180051765  test    eax, eax
0x180051767  js      loc_180051CFA
0x18005176d  lea     rax, [rsp+160h+Size]
0x180051772  mov     r9d, ebx
0x180051775  lea     r8, [rsp+160h+var_E8]
0x18005177a  mov     [rsp+160h+var_140], rax
0x18005177f  lea     edx, [rbx+9]
0x180051782  mov     rcx, rsi
0x180051785  call    ?ProviderGetProperty@@YAJPEAXW4KspProp@@PEAEKPEAK@Z; ProviderGetProperty(void *,KspProp,uchar *,ulong,ulong *)
0x18005178a  mov     ecx, eax; int
0x18005178c  call    ?SecurityStatusFromHResult@@YAJJ@Z; SecurityStatusFromHResult(long)
0x180051791  mov     [rsp+160h+var_100], eax
0x180051795  test    eax, eax
0x180051797  js      loc_180051CFA
0x18005179d  lea     rax, [rsp+160h+Size]
0x1800517a2  mov     r9d, ebx
0x1800517a5  lea     r8, [rbp+60h+var_E0]
0x1800517a9  mov     [rsp+160h+var_140], rax
0x1800517ae  lea     edx, [rbx+3Dh]
0x1800517b1  mov     rcx, r13
0x1800517b4  call    ?ProviderGetProperty@@YAJPEAXW4KspProp@@PEAEKPEAK@Z; ProviderGetProperty(void *,KspProp,uchar *,ulong,ulong *)
0x1800517b9  mov     ecx, eax; int
0x1800517bb  call    ?SecurityStatusFromHResult@@YAJJ@Z; SecurityStatusFromHResult(long)
0x1800517c0  mov     [rsp+160h+var_100], eax
0x1800517c4  test    eax, eax
0x1800517c6  js      loc_180051CFA
0x1800517cc  lea     rax, [rsp+160h+Size]
0x1800517d1  mov     dword ptr [rsp+160h+var_130], edi; unsigned int
0x1800517d5  mov     [rsp+160h+var_138], rax; unsigned int *
0x1800517da  lea     r8, aOpaquekeyblob; "OpaqueKeyBlob"
0x1800517e1  xor     r9d, r9d; unsigned __int8 *
0x1800517e4  mov     dword ptr [rsp+160h+var_140], edi; unsigned int
0x1800517e8  mov     rcx, r13; void *
0x1800517eb  call    ?ProviderExportKey@@YAJPEAX0PEBGPEAEKPEAKK@Z; ProviderExportKey(void *,void *,ushort const *,uchar *,ulong,ulong *,ulong)
0x1800517f0  mov     ecx, eax; int
0x1800517f2  call    ?SecurityStatusFromHResult@@YAJJ@Z; SecurityStatusFromHResult(long)
0x1800517f7  mov     [rsp+160h+var_100], eax
0x1800517fb  test    eax, eax
0x1800517fd  js      loc_180051CFA
0x180051803  mov     r15d, dword ptr [rsp+160h+Size]
0x180051808  mov     dword ptr [rsp+160h+Size+4], r15d
0x18005180d  test    r15d, r15d
0x180051810  jz      loc_180051CF2
0x180051816  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005181d  mov     ecx, r15d; unsigned __int64
0x180051820  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180051825  mov     rdi, rax
0x180051828  test    rax, rax
0x18005182b  jnz     short loc_18005183A
0x18005182d  mov     [rsp+160h+var_100], 8007000Eh
0x180051835  jmp     loc_180051CFA
0x18005183a  mov     r8, r15; Size
0x18005183d  xor     edx, edx; Val
0x18005183f  mov     rcx, rdi; void *
0x180051842  call    memset_0
0x180051847  lea     rax, [rsp+160h+Size]
0x18005184c  mov     dword ptr [rsp+160h+var_130], r12d; unsigned int
0x180051851  mov     [rsp+160h+var_138], rax; unsigned int *
0x180051856  lea     r8, aOpaquekeyblob; "OpaqueKeyBlob"
0x18005185d  mov     r9, rdi; unsigned __int8 *
0x180051860  mov     dword ptr [rsp+160h+var_140], r15d; unsigned int
0x180051865  mov     rcx, r13; void *
0x180051868  mov     [rsp+160h+var_100], r12d
0x18005186d  call    ?ProviderExportKey@@YAJPEAX0PEBGPEAEKPEAKK@Z; ProviderExportKey(void *,void *,ushort const *,uchar *,ulong,ulong *,ulong)
0x180051872  mov     ecx, eax; int
0x180051874  call    ?SecurityStatusFromHResult@@YAJJ@Z; SecurityStatusFromHResult(long)
0x180051879  mov     [rsp+160h+var_100], eax
0x18005187d  test    eax, eax
0x18005187f  js      loc_180051CFA
0x180051885  lea     r8, [rsp+160h+var_E8+4]; int *
0x18005188a  mov     dword ptr [rsp+160h+var_E8+4], r12d
0x18005188f  lea     rdx, aKeypolicyneeds; "KeyPolicyNeedsPinForCertify"
0x180051896  lea     rcx, [rbp+60h+var_A8]; this
0x18005189a  call    ??0KspFunctionLogger@@QEAA@QEBGAEBJ@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,long const &)
0x18005189f  mov     sil, 1
0x1800518a2  cmp     r15d, 34h ; '4'
0x1800518a6  jb      short loc_1800518BA
0x1800518a8  cmp     dword ptr [rdi+8], 2
0x1800518ac  jnz     short loc_1800518BA
0x1800518ae  cmp     dword ptr [rdi+20h], 0B0h
0x1800518b5  sbb     al, al
0x1800518b7  and     sil, al
0x1800518ba  mov     ebx, dword ptr [rsp+160h+var_E8+4]
0x1800518be  lea     rcx, [rbp+60h+var_A8]; this
0x1800518c2  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x1800518c7  mov     [rsp+160h+var_100], ebx
0x1800518cb  test    ebx, ebx
0x1800518cd  js      loc_180051CFA
0x1800518d3  test    sil, sil
0x1800518d6  jz      loc_1800519A0
0x1800518dc  mov     r9d, 1
0x1800518e2  lea     rax, [rsp+160h+Size]
0x1800518e7  lea     r8, [rsp+160h+var_FC]
0x1800518ec  mov     [rsp+160h+var_140], rax
0x1800518f1  mov     rcx, r13
0x1800518f4  lea     edx, [r9+38h]
0x1800518f8  call    ?ProviderGetProperty@@YAJPEAXW4KspProp@@PEAEKPEAK@Z; ProviderGetProperty(void *,KspProp,uchar *,ulong,ulong *)
0x1800518fd  mov     ecx, eax; int
0x1800518ff  call    ?SecurityStatusFromHResult@@YAJJ@Z; SecurityStatusFromHResult(long)
0x180051904  mov     [rsp+160h+var_100], eax
0x180051908  test    eax, eax
0x18005190a  js      loc_180051CFA
0x180051910  mov     al, [rsp+160h+var_FC]
0x180051914  test    al, al
0x180051916  jz      loc_1800519A8
0x18005191c  xor     r9d, r9d
0x18005191f  lea     rax, [rsp+160h+Size]
0x180051924  xor     r8d, r8d
0x180051927  mov     [rsp+160h+var_140], rax
0x18005192c  mov     rcx, r13
0x18005192f  lea     ebx, [r9+57h]
0x180051933  mov     edx, ebx
0x180051935  call    ?ProviderGetProperty@@YAJPEAXW4KspProp@@PEAEKPEAK@Z; ProviderGetProperty(void *,KspProp,uchar *,ulong,ulong *)
0x18005193a  mov     ecx, eax; int
0x18005193c  call    ?SecurityStatusFromHResult@@YAJJ@Z; SecurityStatusFromHResult(long)
0x180051941  mov     [rsp+160h+var_100], eax
0x180051945  test    eax, eax
0x180051947  js      loc_180051CFA
0x18005194d  mov     r12d, dword ptr [rsp+160h+Size]
0x180051952  lea     rcx, [rbp+60h+var_D0]; void **
0x180051956  mov     edx, r12d; unsigned __int64
0x180051959  mov     dword ptr [rsp+160h+var_F0+4], r12d
0x18005195e  call    ?AllocateAndZero@@YAJPEAPEAX_K@Z; AllocateAndZero(void * *,unsigned __int64)
0x180051963  mov     r14, [rbp+60h+var_D0]
0x180051967  mov     [rsp+160h+var_100], eax
0x18005196b  test    eax, eax
0x18005196d  js      loc_180051CFA
0x180051973  lea     rax, [rsp+160h+Size]
0x180051978  mov     r9d, r12d
0x18005197b  mov     r8, r14
0x18005197e  mov     [rsp+160h+var_140], rax
0x180051983  mov     edx, ebx
0x180051985  mov     rcx, r13
0x180051988  call    ?ProviderGetProperty@@YAJPEAXW4KspProp@@PEAEKPEAK@Z; ProviderGetProperty(void *,KspProp,uchar *,ulong,ulong *)
0x18005198d  mov     ecx, eax; int
0x18005198f  call    ?SecurityStatusFromHResult@@YAJJ@Z; SecurityStatusFromHResult(long)
0x180051994  mov     [rsp+160h+var_100], eax
0x180051998  test    eax, eax
0x18005199a  js      loc_180051CFA
0x1800519a0  mov     al, [rsp+160h+var_FC]
0x1800519a4  test    al, al
0x1800519a6  jnz     short loc_1800519B9
0x1800519a8  xor     r14d, r14d
0x1800519ab  neg     al
0x1800519ad  sbb     eax, eax
0x1800519af  and     eax, r12d
0x1800519b2  mov     r12d, eax
0x1800519b5  mov     dword ptr [rsp+160h+var_F0+4], eax
0x1800519b9  lea     rdx, [rbp+60h+var_78]
0x1800519bd  mov     ecx, 10h
0x1800519c2  call    cs:__imp_Tbsi_GetDeviceInfo
0x1800519c9  nop     dword ptr [rax+rax+00h]
0x1800519ce  mov     [rsp+160h+var_100], eax
0x1800519d2  test    eax, eax
0x1800519d4  js      loc_180051CFA
0x1800519da  cmp     dword ptr [rbp+60h+var_78+4], 1
0x1800519de  jnz     loc_180051A95
0x1800519e4  cmp     [rbp+60h+arg_40], 102h
0x1800519ee  jnz     short loc_1800519FD
0x1800519f0  mov     [rsp+160h+var_100], 80290405h
0x1800519f8  jmp     loc_180051CFA
0x1800519fd  mov     r8, [rbp+60h+var_D8]
0x180051a01  mov     r15d, dword ptr [rbp+60h+arg_20]
0x180051a08  test    r8, r8
0x180051a0b  jz      short loc_180051A19
0x180051a0d  test    r15d, r15d
0x180051a10  jz      short loc_180051A19
0x180051a12  mov     cl, 1
0x180051a14  mov     edx, r15d
0x180051a17  jmp     short loc_180051A20
0x180051a19  xor     cl, cl
0x180051a1b  mov     edx, 14h
0x180051a20  test    cl, cl
0x180051a22  lea     rax, [rbp+60h+var_68]
0x180051a26  lea     rcx, [rsp+160h+var_F0]
0x180051a2b  mov     [rsp+160h+var_108], rcx; unsigned int *
0x180051a30  cmovnz  rax, r8
0x180051a34  mov     rcx, [rbp+60h+hContext]; hContext
0x180051a38  xor     r9d, r9d; unsigned int
0x180051a3b  mov     dword ptr [rsp+160h+var_110], 0; unsigned int
0x180051a43  xor     r8d, r8d; unsigned __int8 *
0x180051a46  mov     [rsp+160h+var_118], 0; unsigned __int8 *
0x180051a4f  mov     dword ptr [rsp+160h+SourceSize], edx; SourceSize
0x180051a53  mov     edx, [rbp+60h+var_DC]; unsigned int
0x180051a56  mov     [rsp+160h+Source], rax; Source
0x180051a5b  mov     eax, [rbp+60h+var_E0]
0x180051a5e  mov     dword ptr [rsp+160h+var_130], r12d; unsigned int
0x180051a63  mov     [rsp+160h+var_138], r14; unsigned __int8 *
0x180051a68  mov     dword ptr [rsp+160h+var_140], eax; unsigned int
0x180051a6c  call    ?KeyAtt_PcpCertifyKey12@@YAJPEAXIPEAEII1IPEBEI1IPEAI@Z; KeyAtt_PcpCertifyKey12(void *,uint,uchar *,uint,uint,uchar *,uint,uchar const *,uint,uchar *,uint,uint *)
0x180051a71  mov     [rsp+160h+var_100], eax
0x180051a75  test    eax, eax
0x180051a77  js      short loc_180051A8B
0x180051a79  mov     esi, dword ptr [rsp+160h+var_F0]
0x180051a7d  cmp     dword ptr [rsp+160h+var_E8], esi
0x180051a81  jbe     short loc_180051AEA
0x180051a83  mov     [rsp+160h+var_100], 80004005h
0x180051a8b  mov     r15d, dword ptr [rsp+160h+Size+4]
0x180051a90  jmp     loc_180051CFA
0x180051a95  cmp     dword ptr [rbp+60h+var_78+4], 2
0x180051a99  jnz     loc_180051D72
0x180051a9f  mov     r15d, dword ptr [rbp+60h+arg_20]
0x180051aa6  lea     rax, [rsp+160h+var_F0]
0x180051aab  mov     rdx, [rbp+60h+var_B0]; void *
0x180051aaf  mov     r9d, r12d; unsigned int
0x180051ab2  mov     [rsp+160h+SourceSize], rax; unsigned int *
0x180051ab7  mov     r8, r14; unsigned __int8 *
0x180051aba  mov     rax, [rbp+60h+var_D8]
0x180051abe  mov     rcx, r13; this
0x180051ac1  mov     dword ptr [rsp+160h+Source], 0; unsigned int
0x180051ac9  mov     [rsp+160h+var_130], 0; unsigned __int8 *
0x180051ad2  mov     dword ptr [rsp+160h+var_138], r15d; unsigned int
0x180051ad7  mov     [rsp+160h+var_140], rax; unsigned __int8 *
0x180051adc  call    ?PCP20CommonpCertifyKey@@YAJPEAX0PEAEK1K1IPEAK@Z; PCP20CommonpCertifyKey(void *,void *,uchar *,ulong,uchar *,ulong,uchar *,uint,ulong *)
0x180051ae1  mov     ecx, eax; int
0x180051ae3  call    ?SecurityStatusFromHResult@@YAJJ@Z; SecurityStatusFromHResult(long)
0x180051ae8  jmp     short loc_180051A71
  ... truncated ...
```
