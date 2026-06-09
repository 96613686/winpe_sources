# Input::ImportantLicense::PredictComplexCase(Input::ComplexAbstraction const &)

- ea: `0x18001cc00`
- end: `0x18001d07d`
- name: `?PredictComplexCase@ImportantLicense@Input@@SA_NAEBVComplexAbstraction@2@@Z`
- size: `1149`
- prototype: `bool __fastcall(const struct Input::ComplexAbstraction *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180003c10`
- `0x180003c88`
- `0x18000e4b0`
- `0x18001cc00`
- `0x18001e7f0`
- `0x1800bf3b0`

## pseudocode

```c
bool __fastcall Input::ImportantLicense::PredictComplexCase(const struct Input::ComplexAbstraction *a1)
{
  double v1; // xmm0_8
  float v2; // xmm6_4
  float v3; // xmm0_4
  __int64 v4; // r9
  __int64 v5; // r8
  const unsigned int near *const *v6; // r10
  int v7; // r11d
  unsigned int v8; // ebx
  __int64 v9; // r9
  unsigned int v10; // ecx
  __int64 v11; // r8
  __int64 v12; // rcx
  __int64 MixedProvider; // rax
  unsigned int v14; // r9d
  void (__fastcall *v15)(bool (__fastcall *)(const struct Input::ComplexAbstraction *), unsigned __int64, __int64); // rax
  unsigned __int8 *retaddr; // [rsp+68h] [rbp+0h]
  int v18; // [rsp+80h] [rbp+18h]

  v1 = Input::IntegralSetting<float>::TransmitFlatMedia();
  v2 = *(float *)&v1;
  *(float *)&v1 = o_atan2f_0();
  v3 = o_sinf_0(*(float *)&v1 + *(float *)&v1);
  v4 = IntegralRelation::OddMap ^ 0xF4285559;
  v18 = *retaddr;
  v5 = ~(~(~(~((476496 * v18) | 0x5C10AC0) | (476496 * v18) & 0x5C10AC0) | 0xA3100)
       | ~(~((476496 * v18) | 0x5C10AC0) | (476496 * v18) & 0x5C10AC0) & 0xA3100u);
  if ( (_DWORD)v5 == ~((476496 * v18) ^ 0x5CB3BC0 | ~((476496 * v18) | 0x5CB3BC0))
                   + ((476496 * v18) ^ 0x5CB3BC0 | (476496 * v18) & 0x5CB3BC0)
                   - 476496 * v18
                   - 97205184
    || (_DWORD)v4 != 267204874 )
  {
    v6 = &ScatteredInformation::PaintShortTermException;
    v7 = ScatteredInformation::StripedSeries ^ 0x157E9386;
    v8 = 0;
    LODWORD(v9) = 0;
    do
    {
      v10 = *((_DWORD *)v6++ + 1);
      v11 = (unsigned __int8)((v7 ^ v10) / 0x9D28AF) - (unsigned int)v9 - 1;
      v12 = (unsigned __int8)(((unsigned int)v7 ^ *((_DWORD *)v6 - 2)) / 0x9D28AF) - (unsigned int)v9;
      v9 = (unsigned int)(v9 + 2);
      *((_QWORD *)&ScatteredInformation::StripedSeries + v12 + 1) = *((_QWORD *)&ScatteredInformation::StripedSeries
                                                                    + v11
                                                                    + 1);
    }
    while ( (unsigned int)v9 < 0x1E );
    IntegralRelation::OddMap = ScatteredInformation::StripedSeries ^ 0x157E9386;
    MixedProvider = GenerateMixedProvider(0x9FFF5F1FC020A080uLL, 1900323018, v11, v9);
    v14 = IntegralRelation::OddMap;
    v5 = MixedProvider;
    while ( *(_BYTE *)v5 != (unsigned __int8)((IntegralRelation::OddMap ^ 0xE48A768E) / 0x9D28AF)
         || *(_BYTE *)(v5 + 1) != (unsigned __int8)((IntegralRelation::OddMap ^ 0x80A19D34) / 0x9D28AF)
         || *(_BYTE *)(v5 + 2) != (unsigned __int8)((IntegralRelation::OddMap ^ 0x861CF870) / 0x9D28AF)
         || *(_BYTE *)(v5 + 3) != (unsigned __int8)((IntegralRelation::OddMap ^ 0xE2EEE854) / 0x9D28AF) )
    {
      ++v8;
      ++v5;
      if ( v8 >= 0x258 )
        goto LABEL_13;
    }
    retaddr = (unsigned __int8 *)v5;
    v14 = IntegralRelation::OddMap;
LABEL_13:
    v4 = v14 + 16;
    IntegralRelation::OddMap = v4;
  }
  v15 = (void (__fastcall *)(bool (__fastcall *)(const struct Input::ComplexAbstraction *), unsigned __int64, __int64))GenerateMixedProvider(0xAFBFDFBFC020E030uLL, 1090789482, v5, v4);
  v15(
    Input::ImportantLicense::PredictComplexCase,
    (unsigned __int64)Input::ImportantLicense::PredictComplexCase ^ 0x13BC58,
    244808);
  return (float)((float)(COERCE_FLOAT(LODWORD(v3) & _xmm) * (float)(v2 * 0.41419995)) + v2) > 0.97692305;
}

```

## disassembly

```asm
0x18001cc00  push    rbx
0x18001cc02  sub     rsp, 60h
0x18001cc06  movaps  [rsp+68h+var_38], xmm7
0x18001cc0b  mov     rbx, rcx
0x18001cc0e  movaps  [rsp+68h+var_28], xmm6
0x18001cc13  call    ?TransmitFlatMedia@?$IntegralSetting@M@Input@@QEBAMXZ; Input::IntegralSetting<float>::TransmitFlatMedia(void)
0x18001cc18  movss   xmm1, dword ptr [rbx+8]
0x18001cc1d  movaps  xmm6, xmm0
0x18001cc20  movss   xmm0, dword ptr [rbx]
0x18001cc24  call    _o_atan2f_0
0x18001cc29  addss   xmm0, xmm0; X
0x18001cc2d  call    _o_sinf_0
0x18001cc32  mov     rax, [rsp+68h]
0x18001cc37  movaps  xmm1, xmm6
0x18001cc3a  mulss   xmm1, cs:__real@3ed41204
0x18001cc42  movaps  xmm7, xmm0
0x18001cc45  mov     r9d, cs:?OddMap@IntegralRelation@@2IA; uint IntegralRelation::OddMap
0x18001cc4c  andps   xmm7, cs:__xmm@7fffffff7fffffff7fffffff7fffffff
0x18001cc53  xor     r9d, 0F4285559h
0x18001cc5a  movzx   ecx, byte ptr [rax]
0x18001cc5d  mov     [rsp+68h+arg_10], ecx
0x18001cc64  mov     eax, [rsp+68h+arg_10]
0x18001cc6b  imul    ecx, eax, 74550h
0x18001cc71  mov     [rsp+68h+arg_0], 5C10AC0h
0x18001cc79  mov     eax, [rsp+68h+arg_0]
0x18001cc7d  mov     [rsp+68h+var_48], eax
0x18001cc81  mulss   xmm7, xmm1
0x18001cc85  mov     [rsp+68h+arg_8], ecx
0x18001cc89  mov     eax, [rsp+68h+arg_8]
0x18001cc8d  mov     [rsp+68h+arg_18], eax
0x18001cc94  mov     ecx, [rsp+68h+arg_18]
0x18001cc9b  addss   xmm7, xmm6
0x18001cc9f  mov     eax, [rsp+68h+var_48]
0x18001cca3  or      ecx, eax
0x18001cca5  mov     eax, [rsp+68h+arg_0]
0x18001cca9  not     ecx
0x18001ccab  mov     [rsp+68h+arg_18], eax
0x18001ccb2  mov     eax, [rsp+68h+arg_8]
0x18001ccb6  mov     [rsp+68h+arg_0], eax
0x18001ccba  mov     [rsp+68h+var_48], ecx
0x18001ccbe  mov     ecx, [rsp+68h+arg_0]
0x18001ccc2  mov     eax, [rsp+68h+arg_18]
0x18001ccc9  and     ecx, eax
0x18001cccb  mov     [rsp+68h+arg_0], ecx
0x18001cccf  mov     ecx, [rsp+68h+arg_0]
0x18001ccd3  mov     eax, [rsp+68h+var_48]
0x18001ccd7  or      ecx, eax
0x18001ccd9  not     ecx
0x18001ccdb  mov     [rsp+68h+arg_0], 0A3100h
0x18001cce3  mov     eax, [rsp+68h+arg_0]
0x18001cce7  mov     [rsp+68h+arg_8], ecx
0x18001cceb  mov     [rsp+68h+var_48], eax
0x18001ccef  mov     eax, [rsp+68h+arg_8]
0x18001ccf3  mov     [rsp+68h+arg_18], eax
0x18001ccfa  mov     ecx, [rsp+68h+arg_18]
0x18001cd01  mov     eax, [rsp+68h+var_48]
0x18001cd05  or      ecx, eax
0x18001cd07  mov     eax, [rsp+68h+arg_0]
0x18001cd0b  not     ecx
0x18001cd0d  mov     [rsp+68h+arg_18], eax
0x18001cd14  mov     eax, [rsp+68h+arg_8]
0x18001cd18  mov     [rsp+68h+arg_0], eax
0x18001cd1c  mov     [rsp+68h+var_48], ecx
0x18001cd20  mov     ecx, [rsp+68h+arg_0]
0x18001cd24  mov     eax, [rsp+68h+arg_18]
0x18001cd2b  and     ecx, eax
0x18001cd2d  mov     [rsp+68h+arg_0], ecx
0x18001cd31  mov     r8d, [rsp+68h+arg_0]
0x18001cd36  mov     eax, [rsp+68h+var_48]
0x18001cd3a  or      r8d, eax
0x18001cd3d  mov     [rsp+68h+arg_0], 5C10AC0h
0x18001cd45  not     r8d
0x18001cd48  mov     eax, [rsp+68h+arg_0]
0x18001cd4c  mov     [rsp+68h+var_48], eax
0x18001cd50  mov     [rsp+68h+arg_8], 0A3100h
0x18001cd58  mov     eax, [rsp+68h+arg_8]
0x18001cd5c  mov     [rsp+68h+arg_18], eax
0x18001cd63  mov     ecx, [rsp+68h+arg_18]
0x18001cd6a  mov     eax, [rsp+68h+var_48]
0x18001cd6e  or      ecx, eax
0x18001cd70  mov     eax, [rsp+68h+arg_0]
0x18001cd74  not     ecx
0x18001cd76  mov     [rsp+68h+var_48], ecx
0x18001cd7a  movaps  xmm6, [rsp+68h+var_28]
0x18001cd7f  mov     [rsp+68h+arg_18], eax
0x18001cd86  mov     eax, [rsp+68h+arg_8]
0x18001cd8a  mov     [rsp+68h+arg_0], eax
0x18001cd8e  mov     ecx, [rsp+68h+arg_0]
0x18001cd92  mov     eax, [rsp+68h+arg_18]
0x18001cd99  and     ecx, eax
0x18001cd9b  mov     [rsp+68h+arg_0], ecx
0x18001cd9f  mov     ecx, [rsp+68h+arg_0]
0x18001cda3  mov     eax, [rsp+68h+var_48]
0x18001cda7  or      ecx, eax
0x18001cda9  mov     eax, [rsp+68h+arg_10]
0x18001cdb0  not     ecx
0x18001cdb2  mov     [rsp+68h+arg_8], ecx
0x18001cdb6  imul    ecx, eax, 74550h
0x18001cdbc  mov     eax, [rsp+68h+arg_8]
0x18001cdc0  mov     [rsp+68h+arg_10], eax
0x18001cdc7  mov     [rsp+68h+arg_0], ecx
0x18001cdcb  mov     eax, [rsp+68h+arg_0]
0x18001cdcf  mov     [rsp+68h+arg_18], eax
0x18001cdd6  mov     eax, [rsp+68h+arg_10]
0x18001cddd  mov     [rsp+68h+var_40], eax
0x18001cde1  mov     eax, [rsp+68h+arg_18]
0x18001cde8  mov     [rsp+68h+var_48], eax
0x18001cdec  mov     ecx, [rsp+68h+var_48]
0x18001cdf0  mov     eax, [rsp+68h+var_40]
0x18001cdf4  xor     ecx, eax
0x18001cdf6  mov     eax, [rsp+68h+arg_10]
0x18001cdfd  mov     [rsp+68h+var_40], eax
0x18001ce01  mov     eax, [rsp+68h+arg_18]
0x18001ce08  mov     [rsp+68h+arg_10], eax
0x18001ce0f  mov     [rsp+68h+var_48], ecx
0x18001ce13  mov     ecx, [rsp+68h+arg_10]
0x18001ce1a  mov     eax, [rsp+68h+var_40]
0x18001ce1e  and     ecx, eax
0x18001ce20  mov     [rsp+68h+arg_10], ecx
0x18001ce27  mov     edx, [rsp+68h+arg_10]
0x18001ce2e  mov     eax, [rsp+68h+var_48]
0x18001ce32  or      edx, eax
0x18001ce34  mov     eax, [rsp+68h+arg_8]
0x18001ce38  mov     [rsp+68h+arg_10], eax
0x18001ce3f  mov     eax, [rsp+68h+arg_0]
0x18001ce43  mov     [rsp+68h+arg_18], eax
0x18001ce4a  mov     eax, [rsp+68h+arg_10]
0x18001ce51  mov     [rsp+68h+var_48], eax
0x18001ce55  mov     eax, [rsp+68h+arg_18]
0x18001ce5c  mov     [rsp+68h+var_40], eax
0x18001ce60  mov     ecx, [rsp+68h+var_40]
0x18001ce64  mov     eax, [rsp+68h+var_48]
0x18001ce68  xor     ecx, eax
0x18001ce6a  mov     eax, [rsp+68h+arg_10]
0x18001ce71  mov     [rsp+68h+var_48], ecx
0x18001ce75  mov     [rsp+68h+var_40], eax
0x18001ce79  mov     eax, [rsp+68h+arg_18]
0x18001ce80  mov     [rsp+68h+arg_10], eax
0x18001ce87  mov     ecx, [rsp+68h+arg_10]
0x18001ce8e  mov     eax, [rsp+68h+var_40]
0x18001ce92  or      ecx, eax
0x18001ce94  not     ecx
0x18001ce96  mov     [rsp+68h+arg_10], ecx
0x18001ce9d  mov     ecx, [rsp+68h+arg_10]
0x18001cea4  mov     eax, [rsp+68h+var_48]
0x18001cea8  or      ecx, eax
0x18001ceaa  mov     eax, [rsp+68h+arg_0]
0x18001ceae  not     ecx
0x18001ceb0  add     edx, ecx
0x18001ceb2  sub     edx, eax
0x18001ceb4  mov     eax, [rsp+68h+arg_8]
0x18001ceb8  sub     edx, eax
0x18001ceba  cmp     r8d, edx
0x18001cebd  jz      short loc_18001CECC
0x18001cebf  cmp     r9d, 0FED390Ah
0x18001cec6  jz      loc_18001D033
0x18001cecc  mov     r11d, cs:?StripedSeries@ScatteredInformation@@2V1@A; ScatteredInformation ScatteredInformation::StripedSeries
0x18001ced3  lea     r10, ?PaintShortTermException@ScatteredInformation@@2QBIB; uint const near * const ScatteredInformation::PaintShortTermException
0x18001ceda  xor     r11d, 157E9386h
0x18001cee1  mov     [rsp+68h+var_10], rdi
0x18001cee6  xor     ebx, ebx
0x18001cee8  lea     rdi, ?StripedSeries@ScatteredInformation@@2V1@A; ScatteredInformation ScatteredInformation::StripedSeries
0x18001ceef  mov     r9d, ebx
0x18001cef2  nop     dword ptr [rax+00h]
0x18001cef6  nop     word ptr [rax+rax+00000000h]
0x18001cf00  mov     ecx, [r10+4]
0x18001cf04  lea     r10, [r10+8]
0x18001cf08  xor     ecx, r11d
0x18001cf0b  mov     eax, 68404C21h
0x18001cf10  mul     ecx
0x18001cf12  mov     ecx, [r10-8]
0x18001cf16  mov     eax, 68404C21h
0x18001cf1b  xor     ecx, r11d
0x18001cf1e  shr     edx, 16h
0x18001cf21  movzx   r8d, dl
0x18001cf25  mul     ecx
0x18001cf27  sub     r8d, r9d
0x18001cf2a  shr     edx, 16h
0x18001cf2d  dec     r8d
0x18001cf30  movzx   ecx, dl
0x18001cf33  sub     ecx, r9d
0x18001cf36  add     r9d, 2
0x18001cf3a  mov     rax, [rdi+r8*8+8]
0x18001cf3f  mov     [rdi+rcx*8+8], rax
0x18001cf44  cmp     r9d, 1Eh
0x18001cf48  jb      short loc_18001CF00
0x18001cf4a  mov     eax, cs:?StripedSeries@ScatteredInformation@@2V1@A; ScatteredInformation ScatteredInformation::StripedSeries
0x18001cf50  lea     rdi, [rsp+68h]
0x18001cf55  xor     eax, 157E9386h
0x18001cf5a  mov     edx, 7144A0CAh
0x18001cf5f  mov     rcx, 9FFF5F1FC020A080h
0x18001cf69  mov     cs:?OddMap@IntegralRelation@@2IA, eax; uint IntegralRelation::OddMap
0x18001cf6f  call    GenerateMixedProvider
0x18001cf74  mov     r9d, cs:?OddMap@IntegralRelation@@2IA; uint IntegralRelation::OddMap
0x18001cf7b  mov     r8, rax
0x18001cf7e  mov     ecx, r9d
0x18001cf81  mov     eax, 68404C21h
0x18001cf86  xor     ecx, 0E48A768Eh
0x18001cf8c  mul     ecx
0x18001cf8e  mov     r10d, edx
0x18001cf91  shr     r10d, 16h
0x18001cf95  cmp     [r8], r10b
0x18001cf98  jnz     short loc_18001CFE5
0x18001cf9a  mov     ecx, r9d
0x18001cf9d  mov     eax, 68404C21h
0x18001cfa2  xor     ecx, 80A19D34h
0x18001cfa8  mul     ecx
0x18001cfaa  shr     edx, 16h
0x18001cfad  cmp     [r8+1], dl
0x18001cfb1  jnz     short loc_18001CFE5
0x18001cfb3  mov     ecx, r9d
0x18001cfb6  mov     eax, 68404C21h
0x18001cfbb  xor     ecx, 861CF870h
0x18001cfc1  mul     ecx
0x18001cfc3  shr     edx, 16h
0x18001cfc6  cmp     [r8+2], dl
0x18001cfca  jnz     short loc_18001CFE5
0x18001cfcc  mov     ecx, r9d
0x18001cfcf  mov     eax, 68404C21h
0x18001cfd4  xor     ecx, 0E2EEE854h
0x18001cfda  mul     ecx
0x18001cfdc  shr     edx, 16h
0x18001cfdf  cmp     [r8+3], dl
0x18001cfe3  jz      short loc_18001CFF4
0x18001cfe5  inc     ebx
0x18001cfe7  inc     r8
0x18001cfea  cmp     ebx, 258h
0x18001cff0  jb      short loc_18001CF95
0x18001cff2  jmp     short loc_18001D023
0x18001cff4  mov     [rdi], r8
0x18001cff7  xorps   xmm0, xmm0
0x18001cffa  movups  xmmword ptr [rdi+8], xmm0
0x18001cffe  xor     eax, eax
0x18001d000  movups  xmmword ptr [rdi+18h], xmm0
0x18001d004  movups  xmmword ptr [rdi+28h], xmm0
0x18001d008  movups  xmmword ptr [rdi+38h], xmm0
0x18001d00c  movups  xmmword ptr [rdi+48h], xmm0
0x18001d010  movups  xmmword ptr [rdi+58h], xmm0
0x18001d014  movups  xmmword ptr [rdi+68h], xmm0
0x18001d018  mov     [rdi+78h], rax
0x18001d01c  mov     r9d, cs:?OddMap@IntegralRelation@@2IA; uint IntegralRelation::OddMap
0x18001d023  mov     rdi, [rsp+68h+var_10]
0x18001d028  add     r9d, 10h
0x18001d02c  mov     cs:?OddMap@IntegralRelation@@2IA, r9d; uint IntegralRelation::OddMap
0x18001d033  mov     edx, 4104206Ah
0x18001d038  mov     rcx, 0AFBFDFBFC020E030h
0x18001d042  call    GenerateMixedProvider
0x18001d047  lea     rdx, ?PredictComplexCase@ImportantLicense@Input@@SA_NAEBVComplexAbstraction@2@@Z; Input::ImportantLicense::PredictComplexCase(Input::ComplexAbstraction const &)
0x18001d04e  mov     r8d, 3BC48h
0x18001d054  xor     rdx, 13BC58h
0x18001d05b  lea     rcx, ?PredictComplexCase@ImportantLicense@Input@@SA_NAEBVComplexAbstraction@2@@Z; Input::ImportantLicense::PredictComplexCase(Input::ComplexAbstraction const &)
0x18001d062  call    cs:__guard_dispatch_icall_fptr
0x18001d068  comiss  xmm7, cs:__real@3f7a17a1
0x18001d06f  movaps  xmm7, [rsp+68h+var_38]
0x18001d074  setnbe  al
0x18001d077  add     rsp, 60h
0x18001d07b  pop     rbx
0x18001d07c  retn
```
