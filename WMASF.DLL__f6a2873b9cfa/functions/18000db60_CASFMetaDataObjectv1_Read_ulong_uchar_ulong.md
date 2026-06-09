# CASFMetaDataObjectv1::Read(ulong,uchar *,ulong *)

- ea: `0x18000db60`
- end: `0x18000dff5`
- name: `?Read@CASFMetaDataObjectv1@@UEAAJKPEAEPEAK@Z`
- size: `1173`
- prototype: `int(CASFMetaDataObjectv1 *__hidden this, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops`

## callees

- `0x1800011c0`
- `0x1800011cc`
- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x180009dd8`
- `0x18000da0c`
- `0x18000db60`
- `0x18003f2a0`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFMetaDataObjectv1::Read(
        CASFMetaDataObjectv1 *this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  unsigned __int64 v4; // r13
  struct IWMSCriticalSection *v6; // rdx
  int v9; // edi
  __int128 v10; // xmm0
  unsigned __int64 v11; // rcx
  unsigned __int16 v12; // cx
  int v13; // eax
  int v14; // ebx
  int v15; // edx
  unsigned int v16; // r8d
  __int16 *v17; // r11
  __int16 v18; // ax
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  unsigned int v25; // r8d
  int v26; // r10d
  __int64 v27; // r11
  size_t v28; // rsi
  __int16 v29; // r10
  size_t v30; // r10
  _WORD *v31; // rax
  _WORD *v32; // r15
  _DWORD *v33; // rax
  void *v34; // rsi
  char *v35; // rdx
  __int64 v36; // rbx
  void *v37; // rax
  void *v38; // rcx
  int (__fastcall ***v39)(_QWORD, GUID *, char **); // rcx
  unsigned int v40; // ebx
  unsigned int v42; // [rsp+30h] [rbp-59h] BYREF
  unsigned __int16 v43; // [rsp+34h] [rbp-55h]
  size_t Size; // [rsp+38h] [rbp-51h]
  unsigned int v45; // [rsp+40h] [rbp-49h]
  int v46; // [rsp+44h] [rbp-45h]
  size_t v47; // [rsp+48h] [rbp-41h]
  __int128 v48; // [rsp+50h] [rbp-39h]
  __int128 v49; // [rsp+60h] [rbp-29h]
  char v50[8]; // [rsp+70h] [rbp-19h] BYREF
  unsigned __int8 *v51; // [rsp+78h] [rbp-11h]
  _OWORD v52[2]; // [rsp+80h] [rbp-9h] BYREF
  char *v53; // [rsp+A0h] [rbp+17h] BYREF

  v4 = a2;
  v6 = (struct IWMSCriticalSection *)*((_QWORD *)this + 4);
  v51 = a3;
  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v50, v6);
  if ( !*((_QWORD *)this + 5) )
  {
    v9 = -1072887818;
    goto LABEL_64;
  }
  if ( !a4 )
    goto LABEL_65;
  if ( !(_DWORD)v4 )
  {
LABEL_62:
    *a4 = 26;
    goto LABEL_63;
  }
  if ( !a3 )
  {
LABEL_65:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v50);
    return 2147942487LL;
  }
  if ( (unsigned int)v4 < 0x1A )
    goto LABEL_62;
  v9 = (*(__int64 (__fastcall **)(CASFMetaDataObjectv1 *))(*(_QWORD *)this + 128LL))(this);
  if ( v9 < 0 )
    goto LABEL_64;
  v10 = *(_OWORD *)a3;
  v42 = 24;
  *((_OWORD *)this + 3) = v10;
  v11 = *((_QWORD *)a3 + 2);
  *((_QWORD *)this + 8) = v11;
  if ( v11 >= 0x100000000LL )
  {
    v9 = -1072887821;
    goto LABEL_64;
  }
  if ( v4 < v11 )
  {
    *a4 = *((_DWORD *)this + 16);
LABEL_63:
    v9 = -1072887855;
    goto LABEL_64;
  }
  v9 = -1072887855;
  if ( (unsigned int)CHECK_FOR_SPACE(&v42, 2u, v4) == -1072887855 )
  {
LABEL_56:
    *a4 = v42;
    goto LABEL_64;
  }
  v12 = *((_WORD *)a3 + 12);
  v13 = 0;
  v43 = v12;
  v53 = (char *)(a3 + 26);
  v14 = 1;
  while ( 1 )
  {
    v46 = v13;
    if ( (unsigned __int16)v13 >= v12 )
    {
      v39 = (int (__fastcall ***)(_QWORD, GUID *, char **))*((_QWORD *)this + 5);
      v40 = v42;
      if ( v39 )
      {
        v53 = 0;
        if ( (**v39)(v39, &IID_IASFReadWriteTracker, &v53) >= 0 )
        {
          (*(void (__fastcall **)(char *, unsigned __int8 *, _QWORD, char *))(*(_QWORD *)v53 + 72LL))(
            v53,
            v51,
            v40,
            (char *)this + 48);
          if ( v53 )
            (*(void (__fastcall **)(char *))(*(_QWORD *)v53 + 16LL))(v53);
        }
      }
      *a4 = v40;
      CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v50);
      return 0;
    }
    if ( (unsigned int)CHECK_FOR_SPACE(&v42, 8u, v4) == -1072887855 )
      goto LABEL_56;
    v18 = *v17;
    v19 = (unsigned __int16)v17[3];
    v48 = 0;
    LOWORD(v48) = v18;
    WORD1(v48) = v17[1];
    v49 = 0;
    if ( v19 )
    {
      v20 = v19 - 1;
      if ( v20 )
      {
        v21 = v20 - 1;
        if ( v21 )
        {
          v22 = v21 - 1;
          if ( v22 )
          {
            v23 = v22 - 1;
            if ( v23 )
            {
              v24 = v23 - 1;
              if ( v24 )
              {
                if ( v24 != 1 )
                  goto LABEL_50;
                v14 = v15 - 2;
              }
              else
              {
                v14 = 5;
              }
            }
            else
            {
              v14 = 4;
            }
          }
          else
          {
            v14 = 2;
          }
        }
        else
        {
          v14 = 3;
        }
      }
      else
      {
        v14 = 0;
      }
    }
    DWORD1(v48) = v14;
    if ( (unsigned int)CHECK_FOR_SPACE(&v42, 4u, v16) == -1072887855 )
      goto LABEL_56;
    v28 = *(unsigned int *)(v27 + 8);
    v45 = v28;
    LODWORD(v49) = v28;
    if ( v26 && v26 != (_DWORD)v28 )
    {
      v9 = -2147418113;
      goto LABEL_64;
    }
    v29 = *(_WORD *)(v27 + 4);
    if ( (v29 & 1) != 0 || !v29 )
      goto LABEL_50;
    if ( (unsigned int)CHECK_FOR_SPACE(&v42, *(unsigned __int16 *)(v27 + 4), v25) == -1072887855 )
      goto LABEL_56;
    Size = v30;
    v47 = (unsigned __int64)(unsigned int)v30 >> 1;
    v31 = operator new[](saturated_mul(v47, 2u));
    *((_QWORD *)&v48 + 1) = v31;
    v32 = v31;
    if ( !v31 )
      goto LABEL_54;
    v53 += 12;
    memcpy_0(v31, v53, Size);
    v32[v47 - 1] = 0;
    if ( (unsigned int)CHECK_FOR_SPACE(&v42, v28, v4) == -1072887855 )
    {
      operator delete(v32);
      goto LABEL_56;
    }
    if ( v14 == 3 )
    {
      v33 = operator new[](4u);
      *((_QWORD *)&v49 + 1) = v33;
      v34 = v33;
      if ( !v33 )
        break;
      v35 = &v53[Size];
      *v33 = 0;
      v36 = v45;
      memcpy_0(v33, v35, v45);
      LODWORD(v49) = 4;
      v53 += v36 + Size;
LABEL_40:
      v14 = 1;
      goto LABEL_41;
    }
    v47 = v28;
    v37 = operator new[](v28);
    *((_QWORD *)&v49 + 1) = v37;
    v34 = v37;
    if ( !v37 )
      break;
    memcpy_0(v37, &v53[Size], v47);
    v53 += v47 + Size;
    if ( v14 != 1 )
      goto LABEL_40;
    if ( (v45 & 1) != 0 )
    {
      operator delete(v32);
      operator delete(v34);
LABEL_50:
      v9 = -1072887838;
      goto LABEL_64;
    }
    if ( v45 )
      *((_WORD *)v34 + (v47 >> 1) - 1) = 0;
LABEL_41:
    v52[0] = v48;
    v52[1] = v49;
    if ( !(unsigned int)CTDynArray<CASFMetaDataObjectBase::METADATA_REC,20>::Add((char *)this + 80, v52) )
    {
      operator delete(v32);
      v38 = v34;
      goto LABEL_53;
    }
    HIWORD(v13) = HIWORD(v46);
    LOWORD(v13) = v46 + 1;
    v12 = v43;
  }
  v38 = v32;
LABEL_53:
  operator delete(v38);
LABEL_54:
  v9 = -2147024882;
LABEL_64:
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v50);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000db60  mov     [rsp-8+arg_8], rbx
0x18000db65  push    rbp
0x18000db66  push    rsi
0x18000db67  push    rdi
0x18000db68  push    r12
0x18000db6a  push    r13
0x18000db6c  push    r14
0x18000db6e  push    r15
0x18000db70  lea     rbp, [rsp-27h]
0x18000db75  sub     rsp, 0B0h
0x18000db7c  mov     rax, cs:__security_cookie
0x18000db83  xor     rax, rsp
0x18000db86  mov     [rbp+57h+var_38], rax
0x18000db8a  mov     r13d, edx
0x18000db8d  mov     r14, rcx
0x18000db90  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x18000db94  mov     r12, r9
0x18000db97  lea     rcx, [rbp+57h+var_70]; this
0x18000db9b  mov     [rbp+57h+var_68], r8
0x18000db9f  mov     rsi, r8
0x18000dba2  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18000dba7  cmp     qword ptr [r14+28h], 0
0x18000dbac  jnz     short loc_18000DBB8
0x18000dbae  mov     edi, 0C00D07F6h
0x18000dbb3  jmp     loc_18000DFB3
0x18000dbb8  test    r12, r12
0x18000dbbb  jz      loc_18000DFC0
0x18000dbc1  test    r13d, r13d
0x18000dbc4  jz      loc_18000DFA6
0x18000dbca  test    rsi, rsi
0x18000dbcd  jz      loc_18000DFC0
0x18000dbd3  cmp     r13d, 1Ah
0x18000dbd7  jb      loc_18000DFA6
0x18000dbdd  mov     rax, [r14]
0x18000dbe0  mov     rcx, r14
0x18000dbe3  mov     rax, [rax+80h]
0x18000dbea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbef  mov     edi, eax
0x18000dbf1  test    eax, eax
0x18000dbf3  js      loc_18000DFB3
0x18000dbf9  movups  xmm0, xmmword ptr [rsi]
0x18000dbfc  mov     rax, 100000000h
0x18000dc06  mov     [rbp+57h+var_B0], 18h
0x18000dc0d  movdqu  xmmword ptr [r14+30h], xmm0
0x18000dc13  mov     rcx, [rsi+10h]
0x18000dc17  mov     [r14+40h], rcx
0x18000dc1b  cmp     rcx, rax
0x18000dc1e  jb      short loc_18000DC2A
0x18000dc20  mov     edi, 0C00D07F3h
0x18000dc25  jmp     loc_18000DFB3
0x18000dc2a  cmp     r13, rcx
0x18000dc2d  jnb     short loc_18000DC3C
0x18000dc2f  mov     eax, [r14+40h]
0x18000dc33  mov     [r12], eax
0x18000dc37  jmp     loc_18000DFAE
0x18000dc3c  mov     r15d, 2
0x18000dc42  lea     rcx, [rbp+57h+var_B0]; unsigned int *
0x18000dc46  mov     edx, r15d; unsigned int
0x18000dc49  mov     r8d, r13d; unsigned int
0x18000dc4c  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x18000dc51  mov     edi, 0C00D07D1h
0x18000dc56  cmp     eax, edi
0x18000dc58  jz      loc_18000DF2E
0x18000dc5e  movzx   ecx, word ptr [rsi+18h]
0x18000dc62  lea     r11, [rsi+1Ah]
0x18000dc66  xor     eax, eax
0x18000dc68  mov     [rbp+57h+var_AC], cx
0x18000dc6c  mov     [rbp+57h+var_40], r11
0x18000dc70  lea     ebx, [rax+1]
0x18000dc73  mov     dword ptr [rbp+57h+var_A0+4], eax
0x18000dc76  cmp     ax, cx
0x18000dc79  jnb     loc_18000DF37
0x18000dc7f  mov     r8d, r13d; unsigned int
0x18000dc82  lea     rcx, [rbp+57h+var_B0]; unsigned int *
0x18000dc86  mov     edx, 8; unsigned int
0x18000dc8b  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x18000dc90  cmp     eax, edi
0x18000dc92  jz      loc_18000DF2E
0x18000dc98  movzx   eax, word ptr [r11]
0x18000dc9c  xorps   xmm0, xmm0
0x18000dc9f  movzx   ecx, word ptr [r11+6]
0x18000dca4  xor     r10d, r10d
0x18000dca7  movups  [rbp+57h+var_90], xmm0
0x18000dcab  mov     word ptr [rbp+57h+var_90], ax
0x18000dcaf  movzx   eax, word ptr [r11+2]
0x18000dcb4  mov     word ptr [rbp+57h+var_90+2], ax
0x18000dcb8  movups  [rbp+57h+var_80], xmm0
0x18000dcbc  test    ecx, ecx
0x18000dcbe  jz      short loc_18000DD13
0x18000dcc0  sub     ecx, 1
0x18000dcc3  jz      short loc_18000DD11
0x18000dcc5  sub     ecx, 1
0x18000dcc8  jz      short loc_18000DD0A
0x18000dcca  sub     ecx, 1
0x18000dccd  jz      short loc_18000DCFF
0x18000dccf  sub     ecx, 1
0x18000dcd2  jz      short loc_18000DCF5
0x18000dcd4  sub     ecx, 1
0x18000dcd7  jz      short loc_18000DCEB
0x18000dcd9  cmp     ecx, 1
0x18000dcdc  jnz     loc_18000DEFD
0x18000dce2  lea     ebx, [rdx-2]
0x18000dce5  lea     r10d, [rdx+8]
0x18000dce9  jmp     short loc_18000DD13
0x18000dceb  mov     ebx, 5
0x18000dcf0  mov     r10d, r15d
0x18000dcf3  jmp     short loc_18000DD13
0x18000dcf5  mov     ebx, 4
0x18000dcfa  mov     r10d, edx
0x18000dcfd  jmp     short loc_18000DD13
0x18000dcff  mov     ebx, r15d
0x18000dd02  mov     r10d, 4
0x18000dd08  jmp     short loc_18000DD13
0x18000dd0a  mov     ebx, 3
0x18000dd0f  jmp     short loc_18000DCF0
0x18000dd11  xor     ebx, ebx
0x18000dd13  mov     edx, 4; unsigned int
0x18000dd18  mov     dword ptr [rbp+57h+var_90+4], ebx
0x18000dd1b  lea     rcx, [rbp+57h+var_B0]; unsigned int *
0x18000dd1f  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x18000dd24  cmp     eax, edi
0x18000dd26  jz      loc_18000DF2E
0x18000dd2c  mov     esi, [r11+8]
0x18000dd30  mov     dword ptr [rbp+57h+var_A0], esi
0x18000dd33  mov     dword ptr [rbp+57h+var_80], esi
0x18000dd36  test    r10d, r10d
0x18000dd39  jz      short loc_18000DD44
0x18000dd3b  cmp     r10d, esi
0x18000dd3e  jnz     loc_18000DEE3
0x18000dd44  movzx   r10d, word ptr [r11+4]
0x18000dd49  test    r10b, 1
0x18000dd4d  jnz     loc_18000DEFD
0x18000dd53  xor     eax, eax
0x18000dd55  cmp     ax, r10w
0x18000dd59  jz      loc_18000DEFD
0x18000dd5f  mov     edx, r10d; unsigned int
0x18000dd62  lea     rcx, [rbp+57h+var_B0]; unsigned int *
0x18000dd66  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x18000dd6b  cmp     eax, edi
0x18000dd6d  jz      loc_18000DF2E
0x18000dd73  mov     ecx, r10d
0x18000dd76  mov     [rbp+57h+Size], r10
0x18000dd7a  shr     rcx, 1
0x18000dd7d  mov     rax, r15
0x18000dd80  mul     rcx
0x18000dd83  mov     [rbp+57h+var_98], rcx
0x18000dd87  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000dd8e  cmovb   rax, rcx
0x18000dd92  mov     rcx, rax; unsigned __int64
0x18000dd95  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000dd9a  mov     qword ptr [rbp+57h+var_90+8], rax
0x18000dd9e  mov     r15, rax
0x18000dda1  test    rax, rax
0x18000dda4  jz      loc_18000DF1C
0x18000ddaa  mov     rax, [rbp+57h+var_40]
0x18000ddae  mov     rcx, r15; void *
0x18000ddb1  mov     r8, [rbp+57h+Size]; Size
0x18000ddb5  add     rax, 0Ch
0x18000ddb9  mov     rdx, rax; Src
0x18000ddbc  mov     [rbp+57h+var_40], rax
0x18000ddc0  call    memcpy_0
0x18000ddc5  mov     rcx, [rbp+57h+var_98]
0x18000ddc9  xor     eax, eax
0x18000ddcb  mov     r8d, r13d; unsigned int
0x18000ddce  mov     edx, esi; unsigned int
0x18000ddd0  mov     [r15+rcx*2-2], ax
0x18000ddd6  lea     rcx, [rbp+57h+var_B0]; unsigned int *
0x18000ddda  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x18000dddf  cmp     eax, edi
0x18000dde1  jz      loc_18000DF26
0x18000dde7  cmp     ebx, 3
0x18000ddea  jnz     loc_18000DE7D
0x18000ddf0  lea     ecx, [rbx+1]; unsigned __int64
0x18000ddf3  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000ddf8  mov     qword ptr [rbp+57h+var_80+8], rax
0x18000ddfc  mov     rsi, rax
0x18000ddff  test    rax, rax
0x18000de02  jz      loc_18000DF14
0x18000de08  mov     rdx, [rbp+57h+var_40]
0x18000de0c  xor     eax, eax
0x18000de0e  add     rdx, [rbp+57h+Size]; Src
0x18000de12  mov     rcx, rsi; void *
0x18000de15  mov     [rsi], eax
0x18000de17  mov     eax, dword ptr [rbp+57h+var_A0]
0x18000de1a  mov     r8d, eax; Size
0x18000de1d  mov     ebx, eax
0x18000de1f  call    memcpy_0
0x18000de24  mov     rax, [rbp+57h+var_40]
0x18000de28  add     rax, [rbp+57h+Size]
0x18000de2c  add     rax, rbx
0x18000de2f  mov     dword ptr [rbp+57h+var_80], 4
0x18000de36  mov     [rbp+57h+var_40], rax
0x18000de3a  mov     ebx, 1
0x18000de3f  movups  xmm0, [rbp+57h+var_90]
0x18000de43  lea     rcx, [r14+50h]
0x18000de47  movups  xmm1, [rbp+57h+var_80]
0x18000de4b  lea     rdx, [rbp+57h+var_60]
0x18000de4f  movaps  [rbp+57h+var_60], xmm0
0x18000de53  movaps  [rbp+57h+var_50], xmm1
0x18000de57  call    ?Add@?$CTDynArray@UMETADATA_REC@CASFMetaDataObjectBase@@$0BE@@@QEAAHUMETADATA_REC@CASFMetaDataObjectBase@@PEAK@Z; CTDynArray<CASFMetaDataObjectBase::METADATA_REC,20>::Add(CASFMetaDataObjectBase::METADATA_REC,ulong *)
0x18000de5c  test    eax, eax
0x18000de5e  jz      loc_18000DF07
0x18000de64  mov     eax, dword ptr [rbp+57h+var_A0+4]
0x18000de67  mov     r15d, 2
0x18000de6d  mov     r11, [rbp+57h+var_40]
0x18000de71  add     ax, bx
0x18000de74  movzx   ecx, [rbp+57h+var_AC]
0x18000de78  jmp     loc_18000DC73
0x18000de7d  mov     rcx, rsi; unsigned __int64
0x18000de80  mov     [rbp+57h+var_98], rsi
0x18000de84  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000de89  mov     qword ptr [rbp+57h+var_80+8], rax
0x18000de8d  mov     rsi, rax
0x18000de90  test    rax, rax
0x18000de93  jz      short loc_18000DF14
0x18000de95  mov     rdx, [rbp+57h+var_40]
0x18000de99  mov     rcx, rax; void *
0x18000de9c  add     rdx, [rbp+57h+Size]; Src
0x18000dea0  mov     r8, [rbp+57h+var_98]; Size
0x18000dea4  call    memcpy_0
0x18000dea9  mov     rax, [rbp+57h+var_40]
0x18000dead  add     rax, [rbp+57h+Size]
0x18000deb1  mov     rcx, [rbp+57h+var_98]
0x18000deb5  add     rax, rcx
0x18000deb8  mov     [rbp+57h+var_40], rax
0x18000debc  cmp     ebx, 1
0x18000debf  jnz     loc_18000DE3A
0x18000dec5  mov     eax, dword ptr [rbp+57h+var_A0]
0x18000dec8  test    bl, al
0x18000deca  jnz     short loc_18000DEED
0x18000decc  test    eax, eax
0x18000dece  jz      loc_18000DE3F
0x18000ded4  shr     rcx, 1
0x18000ded7  xor     eax, eax
0x18000ded9  mov     [rsi+rcx*2-2], ax
0x18000dede  jmp     loc_18000DE3F
0x18000dee3  mov     edi, 8000FFFFh
0x18000dee8  jmp     loc_18000DFB3
0x18000deed  mov     rcx, r15; Block
0x18000def0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000def5  mov     rcx, rsi; Block
0x18000def8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000defd  mov     edi, 0C00D07E2h
0x18000df02  jmp     loc_18000DFB3
0x18000df07  mov     rcx, r15; Block
0x18000df0a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000df0f  mov     rcx, rsi
0x18000df12  jmp     short loc_18000DF17
0x18000df14  mov     rcx, r15; Block
0x18000df17  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000df1c  mov     edi, 8007000Eh
0x18000df21  jmp     loc_18000DFB3
0x18000df26  mov     rcx, r15; Block
0x18000df29  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000df2e  mov     eax, [rbp+57h+var_B0]
0x18000df31  mov     [r12], eax
0x18000df35  jmp     short loc_18000DFB3
0x18000df37  mov     rcx, [r14+28h]
0x18000df3b  mov     ebx, [rbp+57h+var_B0]
0x18000df3e  test    rcx, rcx
0x18000df41  jz      short loc_18000DF95
0x18000df43  mov     [rbp+57h+var_40], 0
0x18000df4b  lea     r8, [rbp+57h+var_40]
0x18000df4f  mov     rax, [rcx]
0x18000df52  lea     rdx, IID_IASFReadWriteTracker
0x18000df59  mov     rax, [rax]
0x18000df5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df61  test    eax, eax
0x18000df63  js      short loc_18000DF95
0x18000df65  mov     rcx, [rbp+57h+var_40]
0x18000df69  lea     r9, [r14+30h]
0x18000df6d  mov     rdx, [rbp+57h+var_68]
0x18000df71  mov     r8d, ebx
0x18000df74  mov     rax, [rcx]
0x18000df77  mov     rax, [rax+48h]
0x18000df7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df80  mov     rcx, [rbp+57h+var_40]
0x18000df84  test    rcx, rcx
0x18000df87  jz      short loc_18000DF95
0x18000df89  mov     rax, [rcx]
0x18000df8c  mov     rax, [rax+10h]
0x18000df90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df95  lea     rcx, [rbp+57h+var_70]; this
0x18000df99  mov     [r12], ebx
0x18000df9d  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18000dfa2  xor     eax, eax
0x18000dfa4  jmp     short loc_18000DFCE
0x18000dfa6  mov     dword ptr [r12], 1Ah
0x18000dfae  mov     edi, 0C00D07D1h
0x18000dfb3  lea     rcx, [rbp+57h+var_70]; this
0x18000dfb7  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18000dfbc  mov     eax, edi
0x18000dfbe  jmp     short loc_18000DFCE
0x18000dfc0  lea     rcx, [rbp+57h+var_70]; this
0x18000dfc4  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18000dfc9  mov     eax, 80070057h
0x18000dfce  mov     rcx, [rbp+57h+var_38]
0x18000dfd2  xor     rcx, rsp; StackCookie
0x18000dfd5  call    __security_check_cookie
0x18000dfda  mov     rbx, [rsp+0E0h+arg_8]
  ... truncated ...
```
