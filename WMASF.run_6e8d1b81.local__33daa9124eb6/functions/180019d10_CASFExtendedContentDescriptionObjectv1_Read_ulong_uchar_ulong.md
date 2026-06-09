# CASFExtendedContentDescriptionObjectv1::Read(ulong,uchar *,ulong *)

- ea: `0x180019d10`
- end: `0x18001a107`
- name: `?Read@CASFExtendedContentDescriptionObjectv1@@UEAAJKPEAEPEAK@Z`
- size: `1015`
- prototype: `__int64 __fastcall(CASFExtendedContentDescriptionObjectv1 *__hidden this, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops`

## callees

- `0x1800011c0`
- `0x1800011cc`
- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x18000da0c`
- `0x180019d10`
- `0x18001a110`
- `0x18001a164`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFExtendedContentDescriptionObjectv1::Read(
        CASFExtendedContentDescriptionObjectv1 *this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  unsigned __int64 v4; // rdi
  struct IWMSCriticalSection *v6; // rdx
  unsigned int v9; // esi
  unsigned __int8 *v10; // r12
  int v11; // ebx
  __int128 v12; // xmm0
  unsigned __int64 v13; // rcx
  unsigned __int8 *v14; // r13
  int i; // eax
  unsigned int v16; // ebx
  unsigned __int64 v17; // rdi
  unsigned __int8 *v18; // rax
  unsigned int v19; // r14d
  unsigned __int8 *v20; // r8
  int v21; // edi
  int v22; // r11d
  unsigned __int64 v23; // r14
  void *v24; // rax
  _WORD *v25; // r13
  int (__fastcall ***v26)(_QWORD, GUID *, unsigned __int8 **); // rcx
  unsigned __int16 v28[2]; // [rsp+30h] [rbp-59h] BYREF
  unsigned __int16 v29; // [rsp+34h] [rbp-55h] BYREF
  int v30; // [rsp+38h] [rbp-51h]
  __int128 v31; // [rsp+40h] [rbp-49h]
  void *Block[2]; // [rsp+50h] [rbp-39h]
  unsigned __int8 *v33; // [rsp+60h] [rbp-29h]
  unsigned __int8 *v34; // [rsp+68h] [rbp-21h]
  unsigned int *v35; // [rsp+70h] [rbp-19h]
  char v36[8]; // [rsp+78h] [rbp-11h] BYREF
  _OWORD v37[2]; // [rsp+80h] [rbp-9h] BYREF
  unsigned __int8 *v38; // [rsp+A0h] [rbp+17h] BYREF

  v4 = a2;
  v6 = (struct IWMSCriticalSection *)*((_QWORD *)this + 4);
  v35 = a4;
  v34 = a3;
  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v36, v6);
  v9 = 0;
  v10 = 0;
  Block[1] = 0;
  if ( !*((_QWORD *)this + 5) )
  {
    v11 = -1072887818;
    goto LABEL_54;
  }
  if ( !a4 )
    goto LABEL_53;
  if ( !(_DWORD)v4 )
  {
LABEL_52:
    *a4 = 26;
    v11 = -1072887855;
    goto LABEL_54;
  }
  if ( !a3 )
  {
LABEL_53:
    v11 = -2147024809;
    goto LABEL_54;
  }
  if ( (unsigned int)v4 < 0x1A )
    goto LABEL_52;
  v11 = (*(__int64 (__fastcall **)(CASFExtendedContentDescriptionObjectv1 *))(*(_QWORD *)this + 128LL))(this);
  if ( v11 >= 0 )
  {
    v12 = *(_OWORD *)a3;
    v38 = a3 + 24;
    *((_OWORD *)this + 3) = v12;
    v13 = *((_QWORD *)a3 + 2);
    *((_QWORD *)this + 8) = v13;
    if ( v13 >= 0x100000000LL )
    {
      v11 = -1072887821;
      goto LABEL_61;
    }
    if ( v4 < v13 )
    {
      v11 = -1072887855;
      *a4 = *((_DWORD *)this + 16);
      goto LABEL_61;
    }
    v14 = &a3[v13];
    v33 = v14;
    v29 = 0;
    v9 = 24;
    v11 = SafeReadWORD(&v29, &v38, v14);
    if ( v11 >= 0 )
    {
      v9 = 26;
      for ( i = 0; ; LOWORD(i) = v30 + 1 )
      {
        v30 = i;
        if ( (unsigned __int16)i >= v29 )
          break;
        v28[0] = 0;
        v31 = 0;
        *(_OWORD *)Block = 0;
        v11 = SafeReadWORD(v28, &v38, v14);
        if ( v11 < 0 )
          goto LABEL_51;
        v16 = v28[0];
        v9 += 2;
        if ( (v28[0] & 1) != 0 || !v28[0] )
        {
          v11 = -1072887838;
LABEL_51:
          v10 = (unsigned __int8 *)*((_QWORD *)&v31 + 1);
          goto LABEL_54;
        }
        v17 = (unsigned __int64)v28[0] >> 1;
        v18 = (unsigned __int8 *)operator new[](saturated_mul(v17, 2u));
        *((_QWORD *)&v31 + 1) = v18;
        v10 = v18;
        if ( !v18 )
        {
          v11 = -2147024882;
          goto LABEL_61;
        }
        v19 = v16;
        v11 = SafeReadBYTES(v18, &v38, v16, v14);
        if ( v11 < 0 )
          goto LABEL_54;
        *(_WORD *)&v10[2 * v17 - 2] = 0;
        v28[0] = 0;
        v9 += v19;
        v11 = SafeReadWORD(v28, &v38, v14);
        if ( v11 < 0 )
          goto LABEL_54;
        v9 += 2;
        if ( v28[0] )
        {
          switch ( v28[0] )
          {
            case 1u:
              v21 = 0;
              break;
            case 2u:
              v21 = 3;
              break;
            case 3u:
              v21 = 2;
              break;
            case 4u:
              v21 = 4;
              break;
            case 5u:
              v21 = 5;
              break;
            default:
              goto LABEL_44;
          }
        }
        else
        {
          v21 = 1;
        }
        DWORD1(v31) = v21;
        v28[0] = 0;
        v11 = SafeReadWORD(v28, &v38, v20);
        if ( v11 < 0 )
          goto LABEL_54;
        v23 = v28[0];
        v9 += 2;
        LODWORD(Block[0]) = v28[0];
        if ( v22 && v22 != v28[0] )
        {
LABEL_44:
          v11 = -1072887838;
          goto LABEL_54;
        }
        v24 = operator new[](v28[0]);
        Block[1] = v24;
        v25 = v24;
        if ( !v24 )
        {
          v11 = -2147024882;
          goto LABEL_54;
        }
        v11 = SafeReadBYTES((unsigned __int8 *)v24, &v38, v23, v33);
        if ( v11 < 0 )
          goto LABEL_54;
        if ( v21 == 1 )
        {
          if ( (v23 & 1) != 0 )
            goto LABEL_44;
          if ( (_DWORD)v23 )
            v25[(v23 >> 1) - 1] = 0;
        }
        v9 += v23;
        v37[0] = v31;
        v37[1] = *(_OWORD *)Block;
        if ( !(unsigned int)CTDynArray<CASFMetaDataObjectBase::METADATA_REC,20>::Add((char *)this + 80, v37) )
        {
          v11 = -2147024882;
          break;
        }
        HIWORD(i) = HIWORD(v30);
        v14 = v33;
      }
      if ( v11 >= 0 )
        goto LABEL_55;
    }
  }
LABEL_54:
  operator delete(v10);
  operator delete(Block[1]);
LABEL_55:
  v26 = (int (__fastcall ***)(_QWORD, GUID *, unsigned __int8 **))*((_QWORD *)this + 5);
  if ( v26 )
  {
    v38 = 0;
    if ( (**v26)(v26, &IID_IASFReadWriteTracker, &v38) >= 0 )
    {
      (*(void (__fastcall **)(unsigned __int8 *, unsigned __int8 *, _QWORD, char *))(*(_QWORD *)v38 + 72LL))(
        v38,
        v34,
        v9,
        (char *)this + 48);
      if ( v38 )
        (*(void (__fastcall **)(unsigned __int8 *))(*(_QWORD *)v38 + 16LL))(v38);
    }
  }
  if ( v35 )
    *v35 = v9;
LABEL_61:
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v36);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180019d10  mov     [rsp-8+arg_8], rbx
0x180019d15  push    rbp
0x180019d16  push    rsi
0x180019d17  push    rdi
0x180019d18  push    r12
0x180019d1a  push    r13
0x180019d1c  push    r14
0x180019d1e  push    r15
0x180019d20  lea     rbp, [rsp-27h]
0x180019d25  sub     rsp, 0B0h
0x180019d2c  mov     rax, cs:__security_cookie
0x180019d33  xor     rax, rsp
0x180019d36  mov     [rbp+57h+var_38], rax
0x180019d3a  mov     edi, edx
0x180019d3c  mov     r15, rcx
0x180019d3f  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x180019d43  mov     r14, r9
0x180019d46  lea     rcx, [rbp+57h+var_68]; this
0x180019d4a  mov     [rbp+57h+var_70], r9
0x180019d4e  mov     r13, r8
0x180019d51  mov     [rbp+57h+var_78], r8
0x180019d55  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x180019d5a  xor     esi, esi
0x180019d5c  xor     r12d, r12d
0x180019d5f  mov     [rbp+57h+Block+8], rsi
0x180019d63  cmp     [r15+28h], rsi
0x180019d67  jnz     short loc_180019D73
0x180019d69  mov     ebx, 0C00D07F6h
0x180019d6e  jmp     loc_18001A05E
0x180019d73  test    r14, r14
0x180019d76  jz      loc_18001A059
0x180019d7c  test    edi, edi
0x180019d7e  jz      loc_18001A04B
0x180019d84  test    r13, r13
0x180019d87  jz      loc_18001A059
0x180019d8d  cmp     edi, 1Ah
0x180019d90  jb      loc_18001A04B
0x180019d96  mov     rax, [r15]
0x180019d99  mov     rcx, r15
0x180019d9c  mov     rax, [rax+80h]
0x180019da3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019da8  mov     ebx, eax
0x180019daa  test    eax, eax
0x180019dac  js      loc_18001A05E
0x180019db2  movups  xmm0, xmmword ptr [r13+0]
0x180019db7  lea     rax, [r13+18h]
0x180019dbb  mov     [rbp+57h+var_40], rax
0x180019dbf  mov     rax, 100000000h
0x180019dc9  movdqu  xmmword ptr [r15+30h], xmm0
0x180019dcf  mov     rcx, [r13+10h]
0x180019dd3  mov     [r15+40h], rcx
0x180019dd7  cmp     rcx, rax
0x180019dda  jb      short loc_180019DE6
0x180019ddc  mov     ebx, 0C00D07F3h
0x180019de1  jmp     loc_18001A0D5
0x180019de6  cmp     rdi, rcx
0x180019de9  jnb     short loc_180019DFC
0x180019deb  mov     eax, [r15+40h]
0x180019def  mov     ebx, 0C00D07D1h
0x180019df4  mov     [r14], eax
0x180019df7  jmp     loc_18001A0D5
0x180019dfc  add     r13, rcx
0x180019dff  lea     rdx, [rbp+57h+var_40]; unsigned __int8 **
0x180019e03  xor     eax, eax
0x180019e05  mov     [rbp+57h+var_80], r13
0x180019e09  mov     r8, r13; unsigned __int8 *
0x180019e0c  mov     [rbp+57h+var_AC], ax
0x180019e10  lea     rcx, [rbp+57h+var_AC]; unsigned __int16 *
0x180019e14  mov     esi, 18h
0x180019e19  call    ?SafeReadWORD@@YAJPEAGAEAPEAEPEAE@Z; SafeReadWORD(ushort *,uchar * &,uchar *)
0x180019e1e  mov     ebx, eax
0x180019e20  test    eax, eax
0x180019e22  js      loc_18001A05E
0x180019e28  mov     esi, 1Ah
0x180019e2d  xor     eax, eax
0x180019e2f  lea     edi, [rsi-19h]
0x180019e32  mov     [rbp+57h+var_A8], eax
0x180019e35  cmp     ax, [rbp+57h+var_AC]
0x180019e39  jnb     loc_18001A029
0x180019e3f  xorps   xmm0, xmm0
0x180019e42  lea     rdx, [rbp+57h+var_40]; unsigned __int8 **
0x180019e46  xor     eax, eax
0x180019e48  lea     rcx, [rbp+57h+var_B0]; unsigned __int16 *
0x180019e4c  mov     r8, r13; unsigned __int8 *
0x180019e4f  mov     [rbp+57h+var_B0], ax
0x180019e53  movups  [rbp+57h+var_A0], xmm0
0x180019e57  movups  xmmword ptr [rbp-39h], xmm0
0x180019e5b  call    ?SafeReadWORD@@YAJPEAGAEAPEAEPEAE@Z; SafeReadWORD(ushort *,uchar * &,uchar *)
0x180019e60  mov     ebx, eax
0x180019e62  test    eax, eax
0x180019e64  js      loc_18001A045
0x180019e6a  movzx   ebx, [rbp+57h+var_B0]
0x180019e6e  add     esi, 2
0x180019e71  test    dil, bl
0x180019e74  jnz     loc_18001A040
0x180019e7a  xor     eax, eax
0x180019e7c  cmp     ax, bx
0x180019e7f  jz      loc_18001A040
0x180019e85  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180019e8c  mov     edi, ebx
0x180019e8e  shr     rdi, 1
0x180019e91  mov     eax, 2
0x180019e96  mul     rdi
0x180019e99  cmovb   rax, rcx
0x180019e9d  mov     rcx, rax; unsigned __int64
0x180019ea0  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180019ea5  mov     qword ptr [rbp+57h+var_A0+8], rax
0x180019ea9  mov     r12, rax
0x180019eac  test    rax, rax
0x180019eaf  jz      loc_18001A036
0x180019eb5  mov     r9, r13; unsigned __int8 *
0x180019eb8  lea     rdx, [rbp+57h+var_40]; unsigned __int8 **
0x180019ebc  mov     r8d, ebx; unsigned int
0x180019ebf  mov     rcx, rax; unsigned __int8 *
0x180019ec2  mov     r14d, ebx
0x180019ec5  call    ?SafeReadBYTES@@YAJPEAEAEAPEAEK0@Z; SafeReadBYTES(uchar *,uchar * &,ulong,uchar *)
0x180019eca  mov     ebx, eax
0x180019ecc  test    eax, eax
0x180019ece  js      loc_18001A05E
0x180019ed4  xor     eax, eax
0x180019ed6  lea     rdx, [rbp+57h+var_40]; unsigned __int8 **
0x180019eda  mov     r8, r13; unsigned __int8 *
0x180019edd  mov     [r12+rdi*2-2], ax
0x180019ee3  lea     rcx, [rbp+57h+var_B0]; unsigned __int16 *
0x180019ee7  mov     [rbp+57h+var_B0], ax
0x180019eeb  add     esi, r14d
0x180019eee  call    ?SafeReadWORD@@YAJPEAGAEAPEAEPEAE@Z; SafeReadWORD(ushort *,uchar * &,uchar *)
0x180019ef3  mov     ebx, eax
0x180019ef5  test    eax, eax
0x180019ef7  js      loc_18001A05E
0x180019efd  movzx   ecx, [rbp+57h+var_B0]
0x180019f01  xor     r11d, r11d
0x180019f04  add     esi, 2
0x180019f07  test    ecx, ecx
0x180019f09  jz      short loc_180019F54
0x180019f0b  sub     ecx, 1
0x180019f0e  jz      short loc_180019F50
0x180019f10  sub     ecx, 1
0x180019f13  jz      short loc_180019F49
0x180019f15  sub     ecx, 1
0x180019f18  jz      short loc_180019F3C
0x180019f1a  sub     ecx, 1
0x180019f1d  jz      short loc_180019F31
0x180019f1f  cmp     ecx, 1
0x180019f22  jnz     loc_18001A01D
0x180019f28  lea     edi, [rcx+4]
0x180019f2b  lea     r11d, [rcx+1]
0x180019f2f  jmp     short loc_180019F59
0x180019f31  mov     edi, 4
0x180019f36  lea     r11d, [rdi+4]
0x180019f3a  jmp     short loc_180019F59
0x180019f3c  mov     edi, 2
0x180019f41  mov     r11d, 4
0x180019f47  jmp     short loc_180019F59
0x180019f49  mov     edi, 3
0x180019f4e  jmp     short loc_180019F41
0x180019f50  xor     edi, edi
0x180019f52  jmp     short loc_180019F59
0x180019f54  mov     edi, 1
0x180019f59  xor     eax, eax
0x180019f5b  mov     dword ptr [rbp+57h+var_A0+4], edi
0x180019f5e  lea     rdx, [rbp+57h+var_40]; unsigned __int8 **
0x180019f62  mov     [rbp+57h+var_B0], ax
0x180019f66  lea     rcx, [rbp+57h+var_B0]; unsigned __int16 *
0x180019f6a  call    ?SafeReadWORD@@YAJPEAGAEAPEAEPEAE@Z; SafeReadWORD(ushort *,uchar * &,uchar *)
0x180019f6f  mov     ebx, eax
0x180019f71  test    eax, eax
0x180019f73  js      loc_18001A05E
0x180019f79  movzx   r14d, [rbp+57h+var_B0]
0x180019f7e  add     esi, 2
0x180019f81  mov     dword ptr [rbp+57h+Block], r14d
0x180019f85  test    r11d, r11d
0x180019f88  jz      short loc_180019F93
0x180019f8a  cmp     r11d, r14d
0x180019f8d  jnz     loc_18001A01D
0x180019f93  mov     rcx, r14; unsigned __int64
0x180019f96  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180019f9b  mov     [rbp+57h+Block+8], rax
0x180019f9f  mov     r13, rax
0x180019fa2  test    rax, rax
0x180019fa5  jz      loc_18001A02F
0x180019fab  mov     r9, [rbp+57h+var_80]; unsigned __int8 *
0x180019faf  lea     rdx, [rbp+57h+var_40]; unsigned __int8 **
0x180019fb3  mov     r8d, r14d; unsigned int
0x180019fb6  mov     rcx, rax; unsigned __int8 *
0x180019fb9  call    ?SafeReadBYTES@@YAJPEAEAEAPEAEK0@Z; SafeReadBYTES(uchar *,uchar * &,ulong,uchar *)
0x180019fbe  mov     ebx, eax
0x180019fc0  test    eax, eax
0x180019fc2  js      loc_18001A05E
0x180019fc8  cmp     edi, 1
0x180019fcb  mov     edi, 1
0x180019fd0  jnz     short loc_180019FEA
0x180019fd2  test    dil, r14b
0x180019fd5  jnz     short loc_18001A01D
0x180019fd7  test    r14d, r14d
0x180019fda  jz      short loc_180019FEA
0x180019fdc  mov     rcx, r14
0x180019fdf  shr     rcx, 1
0x180019fe2  xor     eax, eax
0x180019fe4  mov     [r13+rcx*2-2], ax
0x180019fea  movups  xmm0, [rbp+57h+var_A0]
0x180019fee  lea     rcx, [r15+50h]
0x180019ff2  add     esi, r14d
0x180019ff5  movups  xmm1, xmmword ptr [rbp+57h+Block]
0x180019ff9  lea     rdx, [rbp+57h+var_60]
0x180019ffd  movaps  [rbp+57h+var_60], xmm0
0x18001a001  movaps  [rbp+57h+var_50], xmm1
0x18001a005  call    ?Add@?$CTDynArray@UMETADATA_REC@CASFMetaDataObjectBase@@$0BE@@@QEAAHUMETADATA_REC@CASFMetaDataObjectBase@@PEAK@Z; CTDynArray<CASFMetaDataObjectBase::METADATA_REC,20>::Add(CASFMetaDataObjectBase::METADATA_REC,ulong *)
0x18001a00a  test    eax, eax
0x18001a00c  jz      short loc_18001A024
0x18001a00e  mov     eax, [rbp+57h+var_A8]
0x18001a011  mov     r13, [rbp+57h+var_80]
0x18001a015  add     ax, di
0x18001a018  jmp     loc_180019E32
0x18001a01d  mov     ebx, 0C00D07E2h
0x18001a022  jmp     short loc_18001A05E
0x18001a024  mov     ebx, 8007000Eh
0x18001a029  test    ebx, ebx
0x18001a02b  jns     short loc_18001A06F
0x18001a02d  jmp     short loc_18001A05E
0x18001a02f  mov     ebx, 8007000Eh
0x18001a034  jmp     short loc_18001A05E
0x18001a036  mov     ebx, 8007000Eh
0x18001a03b  jmp     loc_18001A0D5
0x18001a040  mov     ebx, 0C00D07E2h
0x18001a045  mov     r12, qword ptr [rbp+57h+var_A0+8]
0x18001a049  jmp     short loc_18001A05E
0x18001a04b  mov     dword ptr [r14], 1Ah
0x18001a052  mov     ebx, 0C00D07D1h
0x18001a057  jmp     short loc_18001A05E
0x18001a059  mov     ebx, 80070057h
0x18001a05e  mov     rcx, r12; Block
0x18001a061  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001a066  mov     rcx, [rbp+57h+Block+8]; Block
0x18001a06a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001a06f  mov     rcx, [r15+28h]
0x18001a073  test    rcx, rcx
0x18001a076  jz      short loc_18001A0CA
0x18001a078  mov     [rbp+57h+var_40], 0
0x18001a080  lea     r8, [rbp+57h+var_40]
0x18001a084  mov     rax, [rcx]
0x18001a087  lea     rdx, IID_IASFReadWriteTracker
0x18001a08e  mov     rax, [rax]
0x18001a091  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a096  test    eax, eax
0x18001a098  js      short loc_18001A0CA
0x18001a09a  mov     rcx, [rbp+57h+var_40]
0x18001a09e  lea     r9, [r15+30h]
0x18001a0a2  mov     rdx, [rbp+57h+var_78]
0x18001a0a6  mov     r8d, esi
0x18001a0a9  mov     rax, [rcx]
0x18001a0ac  mov     rax, [rax+48h]
0x18001a0b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0b5  mov     rcx, [rbp+57h+var_40]
0x18001a0b9  test    rcx, rcx
0x18001a0bc  jz      short loc_18001A0CA
0x18001a0be  mov     rax, [rcx]
0x18001a0c1  mov     rax, [rax+10h]
0x18001a0c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0ca  mov     rax, [rbp+57h+var_70]
0x18001a0ce  test    rax, rax
0x18001a0d1  jz      short loc_18001A0D5
0x18001a0d3  mov     [rax], esi
0x18001a0d5  lea     rcx, [rbp+57h+var_68]; this
0x18001a0d9  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18001a0de  mov     eax, ebx
0x18001a0e0  mov     rcx, [rbp+57h+var_38]
0x18001a0e4  xor     rcx, rsp; StackCookie
0x18001a0e7  call    __security_check_cookie
0x18001a0ec  mov     rbx, [rsp+0E0h+arg_8]
0x18001a0f4  add     rsp, 0B0h
0x18001a0fb  pop     r15
0x18001a0fd  pop     r14
0x18001a0ff  pop     r13
0x18001a101  pop     r12
0x18001a103  pop     rdi
0x18001a104  pop     rsi
0x18001a105  pop     rbp
0x18001a106  retn
```
