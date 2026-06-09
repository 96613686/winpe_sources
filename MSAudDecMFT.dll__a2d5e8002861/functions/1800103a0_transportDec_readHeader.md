# transportDec_readHeader

- ea: `0x1800103a0`
- end: `0x18001082f`
- name: `transportDec_readHeader`
- size: `1167`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18000e684`
- `0x1800113bc`

## callees

- `0x18000e9b0`
- `0x1800103a0`
- `0x180010838`
- `0x1800110c0`
- `0x18001112c`
- `0x18001115c`
- `0x1800111d0`
- `0x180078914`
- `0x180078b60`
- `0x1800960c0`

## pseudocode

```c
__int64 __fastcall transportDec_readHeader(
        unsigned int *a1,
        int *a2,
        int a3,
        int a4,
        int *a5,
        int *a6,
        int *a7,
        int *a8,
        _DWORD *a9)
{
  unsigned int PayloadLengthInfo; // edi
  int v13; // ecx
  int v14; // r15d
  int v15; // eax
  __int64 v16; // r8
  int v17; // r13d
  int *v18; // rsi
  char v19; // r13
  int v20; // r14d
  unsigned int DecodeHeader; // eax
  __int64 v22; // r8
  int v23; // eax
  int v24; // eax
  int RawDataBlockLength; // eax
  int v26; // r13d
  int v27; // r12d
  _DWORD *v28; // r14
  unsigned int v30; // eax
  __int64 v31; // r8
  unsigned int v32; // eax
  bool v33; // zf
  char v34; // r8
  int v35; // r13d
  unsigned int i; // ecx
  signed int v37; // eax
  unsigned int v38; // edx
  __int64 v39; // rcx
  int v40; // [rsp+40h] [rbp-58h]
  int v41; // [rsp+44h] [rbp-54h]
  int v42[20]; // [rsp+48h] [rbp-50h] BYREF
  char v43; // [rsp+A0h] [rbp+8h] BYREF
  int v44; // [rsp+A8h] [rbp+10h]
  int v45; // [rsp+B0h] [rbp+18h]
  int v46; // [rsp+B8h] [rbp+20h]

  v46 = a4;
  v45 = a3;
  PayloadLengthInfo = 0;
  v41 = *a5;
  if ( a6 )
    v13 = *a6;
  else
    v13 = 0;
  v14 = (int)a7;
  v44 = v13;
  if ( a7 )
    v14 = *a7;
  v15 = (int)a8;
  if ( a8 )
    v15 = *a8;
  v42[0] = v15;
  CDKsyncCache_0(a2);
  v17 = a2[2];
  v40 = v17;
  if ( *a1 != 2 )
  {
    if ( *a1 != 6 && *a1 != 7 )
    {
      if ( *a1 != 10 )
      {
        v14 = 0;
        v18 = (int *)(a1 + 961);
        v27 = a2[2];
        goto LABEL_46;
      }
      if ( (int)a1[961] <= 0 )
      {
        v30 = CDKreadBits(a2, 13, v16);
        a1[54] = v30;
        v14 = 8 * v30;
      }
    }
    v18 = (int *)(a1 + 961);
    if ( (int)a1[961] > 0 )
    {
      PayloadLengthInfo = CLatmDemux_ReadPayloadLengthInfo(a2, a1 + 48);
      if ( !PayloadLengthInfo )
        goto LABEL_60;
    }
    else
    {
      CDKsyncCache_0(a2);
      v31 = *a1;
      a1[958] = a2[2];
      v32 = CLatmDemux_Read(a2, a1 + 48, v31, a1 + 2, a1 + 78, v42, a4);
      PayloadLengthInfo = v32;
      if ( v32 )
      {
        if ( v32 == 257 || v32 - 512 <= 5 )
          goto LABEL_44;
        goto LABEL_69;
      }
      v33 = *a1 == 10;
      *v18 = *((unsigned __int8 *)a1 + 224);
      if ( !v33 || (CDKsyncCache_0(a2), v14 += a2[2] - v17 + 13, v14 > 0) )
      {
LABEL_60:
        v34 = *((_BYTE *)a1 + 225);
        v35 = 0;
        for ( i = 0; ; ++i )
        {
          v37 = 0;
          if ( v34 )
            v37 = *((unsigned __int8 *)a1 + 226);
          if ( (int)i >= v37 )
            break;
          v38 = 0;
          if ( v34 && i < *((unsigned __int8 *)a1 + 226) )
            v38 = a1[4 * i + 51];
          v35 += v38;
        }
        --*v18;
        v41 = v35;
        goto LABEL_45;
      }
    }
LABEL_69:
    PayloadLengthInfo = 258;
LABEL_44:
    *v18 = 0;
LABEL_45:
    v27 = v40;
LABEL_46:
    v26 = v44;
    goto LABEL_28;
  }
  v18 = (int *)(a1 + 961);
  if ( (int)a1[961] > 0 )
  {
    CDKcrcReset((struct CDK_CRCINFO *)(a1 + 54));
    *((_BYTE *)a1 + 209) = 0;
  }
  else
  {
    CDKsyncCache_0(a2);
    v19 = 1;
    a1[958] = a2[2];
    v20 = 0;
    v43 = 0;
    while ( 1 )
    {
      if ( v20 >= 2 )
        goto LABEL_23;
      if ( v20 > 0 )
      {
        CDKsyncCache_0(a2);
        CDKpushBack(a2, a1[958] - a2[2]);
        v19 = 2;
      }
      DecodeHeader = adtsRead_DecodeHeader((__int64)(a1 + 48), (__int64)(a1 + 78), (__int64)a2, v46);
      PayloadLengthInfo = DecodeHeader;
      if ( DecodeHeader )
        break;
      LOBYTE(v22) = v19;
      v23 = (*((__int64 (__fastcall **)(_QWORD, unsigned int *, __int64, char *))a1 + 1))(
              *((_QWORD *)a1 + 2),
              a1 + 78,
              v22,
              &v43);
      if ( v23 )
      {
        PayloadLengthInfo = 515;
        if ( v23 == 515 )
          goto LABEL_45;
        goto LABEL_22;
      }
      v24 = *((unsigned __int8 *)a1 + 208) + 1;
      v42[0] = 1;
      *v18 = v24;
      if ( !v20
        && v43
        && (*((unsigned int (__fastcall **)(_QWORD, unsigned int *))a1 + 5))(*((_QWORD *)a1 + 6), a1 + 78) )
      {
        PayloadLengthInfo = 1025;
        goto LABEL_23;
      }
      ++v20;
    }
    if ( DecodeHeader != 257 )
LABEL_22:
      PayloadLengthInfo = 258;
LABEL_23:
    if ( PayloadLengthInfo )
      goto LABEL_44;
  }
  --*v18;
  RawDataBlockLength = adtsRead_GetRawDataBlockLength(
                         (struct STRUCT_ADTS *)(a1 + 48),
                         (unsigned int)*((unsigned __int8 *)a1 + 208) - *v18);
  v26 = v44;
  v41 = RawDataBlockLength;
  if ( RawDataBlockLength <= 0 )
    v26 = 0;
  CDKsyncCache_0(a2);
  v27 = v40;
  v14 = a2[2] + 8 * *((unsigned __int16 *)a1 + 102) - v40 - v45;
  if ( v14 <= 0 )
    PayloadLengthInfo = 258;
LABEL_28:
  v28 = a9;
  *a5 = v41;
  if ( v28 )
  {
    CDKsyncCache_0(a2);
    *v28 += v27 - a2[2];
  }
  if ( *((_BYTE *)a1 + 3828) && PayloadLengthInfo )
  {
    *v18 = 0;
    *((_BYTE *)a1 + 3824) = 0;
    *(unsigned int *)((char *)a1 + 3825) = 0;
    *(_WORD *)((char *)a1 + 3829) = 0;
    (*((void (__fastcall **)(_QWORD))a1 + 7))(*((_QWORD *)a1 + 8));
  }
  if ( a8 )
    *a8 = v42[0];
  if ( a6 )
    *a6 = v26;
  if ( a7 )
    *a7 = v14;
  if ( PayloadLengthInfo == 257 && *a1 <= 0x3C )
  {
    v39 = 0x10000000010010C1LL;
    if ( _bittest64(&v39, (int)*a1) )
      return 258;
  }
  return PayloadLengthInfo;
}

```

## disassembly

```asm
0x1800103a0  mov     [rsp+arg_18], r9d
0x1800103a5  mov     [rsp+arg_10], r8d
0x1800103aa  push    rbx
0x1800103ab  push    rbp
0x1800103ac  push    rsi
0x1800103ad  push    rdi
0x1800103ae  push    r12
0x1800103b0  push    r13
0x1800103b2  push    r14
0x1800103b4  push    r15
0x1800103b6  sub     rsp, 58h
0x1800103ba  mov     rax, [rsp+98h+arg_20]
0x1800103c2  xor     edi, edi
0x1800103c4  mov     r12d, r9d
0x1800103c7  mov     rbp, rdx
0x1800103ca  mov     rbx, rcx
0x1800103cd  mov     eax, [rax]
0x1800103cf  mov     [rsp+98h+var_54], eax
0x1800103d3  mov     rax, [rsp+98h+arg_28]
0x1800103db  test    rax, rax
0x1800103de  jz      loc_180010639
0x1800103e4  mov     ecx, [rax]
0x1800103e6  mov     r15, [rsp+98h+arg_30]
0x1800103ee  mov     [rsp+98h+arg_8], ecx
0x1800103f5  test    r15, r15
0x1800103f8  jz      loc_18001062F
0x1800103fe  mov     r15d, [r15]
0x180010401  mov     rax, [rsp+98h+arg_38]
0x180010409  test    rax, rax
0x18001040c  jz      loc_180010634
0x180010412  mov     eax, [rax]
0x180010414  mov     rcx, rbp
0x180010417  mov     [rsp+98h+var_50], eax
0x18001041b  call    CDKsyncCache_0
0x180010420  mov     ecx, [rbx]
0x180010422  mov     r13d, [rbp+8]
0x180010426  mov     [rsp+98h+var_58], r13d
0x18001042b  sub     ecx, 2
0x18001042e  jnz     loc_18001066E
0x180010434  lea     rsi, [rbx+0F04h]
0x18001043b  cmp     [rsi], edi
0x18001043d  jg      loc_180010528
0x180010443  mov     rcx, rbp
0x180010446  call    CDKsyncCache_0
0x18001044b  mov     eax, [rbp+8]
0x18001044e  mov     r13b, 1
0x180010451  mov     [rbx+0EF8h], eax
0x180010457  xor     r14d, r14d
0x18001045a  mov     [rsp+98h+arg_0], dil
0x180010462  cmp     r14d, 2
0x180010466  jge     loc_180010520
0x18001046c  test    r14d, r14d
0x18001046f  jle     short loc_18001048D
0x180010471  mov     rcx, rbp
0x180010474  call    CDKsyncCache_0
0x180010479  mov     edx, [rbx+0EF8h]
0x18001047f  mov     rcx, rbp
0x180010482  sub     edx, [rbp+8]
0x180010485  call    CDKpushBack
0x18001048a  mov     r13b, 2
0x18001048d  mov     r9d, [rsp+98h+arg_18]
0x180010495  lea     r12, [rbx+138h]
0x18001049c  mov     rdx, r12
0x18001049f  lea     rcx, [rbx+0C0h]
0x1800104a6  mov     r8, rbp
0x1800104a9  call    ?adtsRead_DecodeHeader@@YA?AW4TRANSPORTDEC_ERROR@@PEAUSTRUCT_ADTS@@PEAUCSAudioSpecificConfig@@PEAUCDK_BITSTREAM@@H@Z; adtsRead_DecodeHeader(STRUCT_ADTS *,CSAudioSpecificConfig *,CDK_BITSTREAM *,int)
0x1800104ae  mov     edi, eax
0x1800104b0  test    eax, eax
0x1800104b2  jnz     loc_180010640
0x1800104b8  mov     rcx, [rbx+10h]
0x1800104bc  lea     r9, [rsp+98h+arg_0]
0x1800104c4  mov     rax, [rbx+8]
0x1800104c8  mov     r8b, r13b
0x1800104cb  mov     rdx, r12
0x1800104ce  call    cs:__guard_dispatch_icall_fptr
0x1800104d4  test    eax, eax
0x1800104d6  jnz     loc_1800107AF
0x1800104dc  movzx   eax, byte ptr [rbx+0D0h]
0x1800104e3  inc     eax
0x1800104e5  mov     [rsp+98h+var_50], 1
0x1800104ed  mov     [rsi], eax
0x1800104ef  test    r14d, r14d
0x1800104f2  jz      short loc_1800104FC
0x1800104f4  inc     r14d
0x1800104f7  jmp     loc_180010462
0x1800104fc  cmp     [rsp+98h+arg_0], 0
0x180010504  jz      short loc_1800104F4
0x180010506  mov     rcx, [rbx+30h]
0x18001050a  mov     rdx, r12
0x18001050d  mov     rax, [rbx+28h]
0x180010511  call    cs:__guard_dispatch_icall_fptr
0x180010517  test    eax, eax
0x180010519  jz      short loc_1800104F4
0x18001051b  mov     edi, 401h
0x180010520  mov     r14d, 102h
0x180010526  jmp     short loc_180010546
0x180010528  lea     rcx, [rbx+0D8h]; struct CDK_CRCINFO *
0x18001052f  call    ?CDKcrcReset@@YAXPEAUCDK_CRCINFO@@@Z; CDKcrcReset(CDK_CRCINFO *)
0x180010534  mov     [rbx+0D1h], dil
0x18001053b  mov     r14d, 102h
0x180010541  jmp     short loc_18001054E
0x180010543  mov     edi, r14d
0x180010546  test    edi, edi
0x180010548  jnz     loc_180010656
0x18001054e  dec     dword ptr [rsi]
0x180010550  lea     rcx, [rbx+0C0h]; struct STRUCT_ADTS *
0x180010557  movzx   edx, byte ptr [rcx+10h]
0x18001055b  sub     edx, [rsi]; int
0x18001055d  call    ?adtsRead_GetRawDataBlockLength@@YAHPEAUSTRUCT_ADTS@@H@Z; adtsRead_GetRawDataBlockLength(STRUCT_ADTS *,int)
0x180010562  mov     r13d, [rsp+98h+arg_8]
0x18001056a  xor     ecx, ecx
0x18001056c  test    eax, eax
0x18001056e  mov     [rsp+98h+var_54], eax
0x180010572  cmovle  r13d, ecx
0x180010576  mov     rcx, rbp
0x180010579  call    CDKsyncCache_0
0x18001057e  movzx   r15d, word ptr [rbx+0CCh]
0x180010586  mov     r12d, [rsp+98h+var_58]
0x18001058b  shl     r15d, 3
0x18001058f  sub     r15d, r12d
0x180010592  sub     r15d, [rsp+98h+arg_10]
0x18001059a  add     r15d, [rbp+8]
0x18001059e  test    r15d, r15d
0x1800105a1  cmovle  edi, r14d
0x1800105a5  mov     rcx, [rsp+98h+arg_20]
0x1800105ad  mov     r14, [rsp+98h+arg_40]
0x1800105b5  mov     eax, [rsp+98h+var_54]
0x1800105b9  mov     [rcx], eax
0x1800105bb  test    r14, r14
0x1800105be  jz      short loc_1800105CF
0x1800105c0  mov     rcx, rbp
0x1800105c3  call    CDKsyncCache_0
0x1800105c8  sub     r12d, [rbp+8]
0x1800105cc  add     [r14], r12d
0x1800105cf  cmp     byte ptr [rbx+0EF4h], 0
0x1800105d6  jnz     loc_1800107C7
0x1800105dc  mov     rcx, [rsp+98h+arg_38]
0x1800105e4  test    rcx, rcx
0x1800105e7  jz      short loc_1800105EF
0x1800105e9  mov     eax, [rsp+98h+var_50]
0x1800105ed  mov     [rcx], eax
0x1800105ef  mov     rax, [rsp+98h+arg_28]
0x1800105f7  test    rax, rax
0x1800105fa  jz      short loc_1800105FF
0x1800105fc  mov     [rax], r13d
0x1800105ff  mov     rax, [rsp+98h+arg_30]
0x180010607  test    rax, rax
0x18001060a  jz      short loc_18001060F
0x18001060c  mov     [rax], r15d
0x18001060f  cmp     edi, 101h
0x180010615  jz      loc_180010805
0x18001061b  mov     eax, edi
0x18001061d  add     rsp, 58h
0x180010621  pop     r15
0x180010623  pop     r14
0x180010625  pop     r13
0x180010627  pop     r12
0x180010629  pop     rdi
0x18001062a  pop     rsi
0x18001062b  pop     rbp
0x18001062c  pop     rbx
0x18001062d  retn
0x18001062f  jmp     loc_180010401
0x180010634  jmp     loc_180010414
0x180010639  xor     ecx, ecx
0x18001063b  jmp     loc_1800103E6
0x180010640  mov     r14d, 102h
0x180010646  cmp     eax, 101h
0x18001064b  jz      loc_180010546
0x180010651  jmp     loc_180010543
0x180010656  mov     dword ptr [rsi], 0
0x18001065c  mov     r12d, [rsp+98h+var_58]
0x180010661  mov     r13d, [rsp+98h+arg_8]
0x180010669  jmp     loc_1800105A5
0x18001066e  sub     ecx, 4
0x180010671  jz      short loc_1800106AF
0x180010673  sub     ecx, 1
0x180010676  jz      short loc_1800106AF
0x180010678  cmp     ecx, 3
0x18001067b  jz      short loc_18001068C
0x18001067d  xor     r15d, r15d
0x180010680  lea     rsi, [rbx+0F04h]
0x180010687  mov     r12d, r13d
0x18001068a  jmp     short loc_180010661
0x18001068c  cmp     [rbx+0F04h], edi
0x180010692  jg      short loc_1800106AF
0x180010694  mov     edx, 0Dh
0x180010699  mov     rcx, rbp
0x18001069c  call    CDKreadBits
0x1800106a1  mov     [rbx+0D8h], eax
0x1800106a7  lea     r15d, ds:0[rax*8]
0x1800106af  lea     rsi, [rbx+0F04h]
0x1800106b6  mov     rcx, rbp
0x1800106b9  lea     r14, [rbx+0C0h]
0x1800106c0  cmp     [rsi], edi
0x1800106c2  jg      loc_18001078B
0x1800106c8  call    CDKsyncCache_0
0x1800106cd  mov     eax, [rbp+8]
0x1800106d0  lea     rcx, [rsp+98h+var_50]
0x1800106d5  mov     r8d, [rbx]
0x1800106d8  lea     r9, [rbx+8]
0x1800106dc  mov     [rbx+0EF8h], eax
0x1800106e2  mov     rdx, r14
0x1800106e5  mov     [rsp+98h+var_68], r12d
0x1800106ea  lea     rax, [rbx+138h]
0x1800106f1  mov     [rsp+98h+var_70], rcx
0x1800106f6  mov     rcx, rbp
0x1800106f9  mov     [rsp+98h+var_78], rax
0x1800106fe  call    ?CLatmDemux_Read@@YA?AW4TRANSPORTDEC_ERROR@@PEAUCDK_BITSTREAM@@PEAUCLatmDemux@@W4TRANSPORT_TYPE@@PEAUCSTpCallBacks@@PEAUCSAudioSpecificConfig@@PEAHH@Z; CLatmDemux_Read(CDK_BITSTREAM *,CLatmDemux *,TRANSPORT_TYPE,CSTpCallBacks *,CSAudioSpecificConfig *,int *,int)
0x180010703  mov     edi, eax
0x180010705  test    eax, eax
0x180010707  jz      short loc_180010725
0x180010709  cmp     eax, 101h
0x18001070e  jz      loc_180010656
0x180010714  lea     ecx, [rax-200h]
0x18001071a  cmp     ecx, 5
0x18001071d  jbe     loc_180010656
0x180010723  jmp     short loc_180010799
0x180010725  cmp     dword ptr [rbx], 0Ah
0x180010728  movzx   eax, byte ptr [rbx+0E0h]
0x18001072f  mov     [rsi], eax
0x180010731  jnz     short loc_18001074C
0x180010733  mov     rcx, rbp
0x180010736  call    CDKsyncCache_0
0x18001073b  mov     eax, [rbp+8]
0x18001073e  sub     eax, r13d
0x180010741  add     eax, 0Dh
0x180010744  add     r15d, eax
0x180010747  test    r15d, r15d
0x18001074a  jle     short loc_180010799
0x18001074c  mov     r8b, [rbx+0E1h]
0x180010753  xor     r13d, r13d
0x180010756  xor     ecx, ecx
0x180010758  xor     eax, eax
0x18001075a  test    r8b, r8b
0x18001075d  jz      short loc_180010766
0x18001075f  movzx   eax, byte ptr [rbx+0E2h]
0x180010766  cmp     ecx, eax
0x180010768  jge     short loc_1800107A3
0x18001076a  xor     edx, edx
0x18001076c  test    r8b, r8b
0x18001076f  jz      short loc_180010784
0x180010771  movzx   eax, byte ptr [r14+22h]
0x180010776  cmp     ecx, eax
0x180010778  jnb     short loc_180010784
0x18001077a  mov     eax, ecx
0x18001077c  add     rax, rax
0x18001077f  mov     edx, [r14+rax*8+0Ch]
0x180010784  add     r13d, edx
0x180010787  inc     ecx
0x180010789  jmp     short loc_180010758
0x18001078b  mov     rdx, r14
0x18001078e  call    ?CLatmDemux_ReadPayloadLengthInfo@@YA?AW4TRANSPORTDEC_ERROR@@PEAUCDK_BITSTREAM@@PEAUCLatmDemux@@@Z; CLatmDemux_ReadPayloadLengthInfo(CDK_BITSTREAM *,CLatmDemux *)
0x180010793  mov     edi, eax
0x180010795  test    eax, eax
0x180010797  jz      short loc_18001074C
0x180010799  mov     edi, 102h
0x18001079e  jmp     loc_180010656
0x1800107a3  dec     dword ptr [rsi]
0x1800107a5  mov     [rsp+98h+var_54], r13d
0x1800107aa  jmp     loc_18001065C
0x1800107af  mov     edi, 203h
0x1800107b4  cmp     eax, edi
0x1800107b6  jz      loc_18001065C
0x1800107bc  mov     r14d, 102h
0x1800107c2  jmp     loc_180010543
0x1800107c7  test    edi, edi
0x1800107c9  jz      loc_1800105DC
0x1800107cf  mov     dword ptr [rsi], 0
0x1800107d5  lea     rdx, [rbx+0EF0h]
0x1800107dc  mov     byte ptr [rdx], 0
0x1800107df  mov     dword ptr [rbx+0EF1h], 0
0x1800107e9  mov     word ptr [rbx+0EF5h], 0
0x1800107f2  mov     rcx, [rbx+40h]
0x1800107f6  mov     rax, [rbx+38h]
0x1800107fa  call    cs:__guard_dispatch_icall_fptr
0x180010800  jmp     loc_1800105DC
0x180010805  cmp     dword ptr [rbx], 3Ch ; '<'
0x180010808  ja      loc_18001061B
0x18001080e  movsxd  rax, dword ptr [rbx]
0x180010811  mov     rcx, 10000000010010C1h
0x18001081b  bt      rcx, rax
0x18001081f  jnb     loc_18001061B
0x180010825  mov     edi, 102h
0x18001082a  jmp     loc_18001061B
```
