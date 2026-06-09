# CASFStreamPropertiesObjectExv1::Read(ulong,uchar *,ulong *)

- ea: `0x180015a70`
- end: `0x180015f4c`
- name: `?Read@CASFStreamPropertiesObjectExv1@@UEAAJKPEAEPEAK@Z`
- size: `1244`
- prototype: `__int64 __fastcall(struct IWMSCriticalSection **this, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001174`
- `0x1800011c0`
- `0x1800011cc`
- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x180009dd8`
- `0x180015a70`
- `0x180015f54`
- `0x180016054`
- `0x18003f2a0`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFStreamPropertiesObjectExv1::Read(
        struct IWMSCriticalSection **this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  int v8; // ebx
  __int64 v9; // r9
  unsigned __int8 *v10; // rcx
  __int64 v11; // rdx
  int v12; // eax
  unsigned __int8 *v13; // r12
  int v14; // eax
  unsigned __int16 v15; // dx
  unsigned __int16 v16; // r8
  void **v17; // rsi
  unsigned int v18; // r8d
  unsigned int v19; // edx
  unsigned int v20; // edx
  void *v21; // rax
  __int64 v22; // r12
  int i; // eax
  unsigned int v24; // r8d
  unsigned int v25; // edx
  unsigned int v26; // edx
  void *v27; // rax
  unsigned __int64 v28; // r12
  unsigned int v29; // esi
  struct IWMSCriticalSection *v30; // rcx
  struct IWMSCriticalSection *v31; // rcx
  int v32; // eax
  struct IWMSCriticalSection *v33; // rcx
  struct IWMSCriticalSection *v34; // rcx
  struct IWMSCriticalSection *v36; // rcx
  unsigned int v37; // [rsp+30h] [rbp-48h] BYREF
  unsigned __int16 v38; // [rsp+34h] [rbp-44h]
  char v39[8]; // [rsp+38h] [rbp-40h] BYREF
  unsigned __int64 v40; // [rsp+40h] [rbp-38h]
  unsigned __int8 *v41; // [rsp+48h] [rbp-30h]
  __int64 v42; // [rsp+50h] [rbp-28h] BYREF
  struct IWMSCriticalSection *v43; // [rsp+58h] [rbp-20h] BYREF
  unsigned __int16 v44; // [rsp+60h] [rbp-18h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v39, this[4]);
  if ( !this[5] )
  {
    v8 = -1072887818;
    goto LABEL_51;
  }
  if ( !a4 )
    goto LABEL_52;
  v9 = 88;
  if ( !a2 )
  {
LABEL_50:
    *a4 = 88;
    v8 = -1072887855;
    goto LABEL_51;
  }
  if ( !a3 )
  {
LABEL_52:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v39);
    return 2147942487LL;
  }
  if ( a2 < 0x58 )
    goto LABEL_50;
  v10 = a3 + 40;
  v11 = 0;
  *((_OWORD *)this + 3) = *(_OWORD *)a3;
  this[8] = (struct IWMSCriticalSection *)*((_QWORD *)a3 + 2);
  this[11] = (struct IWMSCriticalSection *)*((_QWORD *)a3 + 3);
  this[12] = (struct IWMSCriticalSection *)*((_QWORD *)a3 + 4);
  do
  {
    v12 = *(_DWORD *)v10;
    v10 += 4;
    *((_DWORD *)this + v11++ + 26) = v12;
  }
  while ( v11 != 8 );
  v13 = v10 + 16;
  *((_WORD *)this + 68) = *(_WORD *)v10;
  v8 = -1072887855;
  *((_WORD *)this + 69) = *((_WORD *)v10 + 1);
  this[18] = *(struct IWMSCriticalSection **)(v10 + 4);
  v14 = 0;
  v15 = *((_WORD *)v10 + 6);
  v16 = *((_WORD *)v10 + 7);
  v44 = v15;
  v38 = v16;
  v37 = 88;
  while ( 1 )
  {
    LODWORD(v42) = v14;
    if ( (unsigned __int16)v14 >= v15 )
      break;
    v17 = (void **)operator new(0x10u);
    if ( !v17 )
      goto LABEL_21;
    if ( (unsigned int)CHECK_FOR_SPACE(&v37, 4u, a2) == -1072887855
      || (*((_WORD *)v17 + 4) = *(_WORD *)v13,
          v19 = *((unsigned __int16 *)v13 + 1),
          LODWORD(v43) = v19,
          (unsigned int)CHECK_FOR_SPACE(&v37, v19, v18) == -1072887855) )
    {
LABEL_24:
      *a4 = v37;
      operator delete(v17);
      goto LABEL_51;
    }
    if ( (v20 & 1) != 0 || !(_WORD)v20 )
    {
      operator delete(v17);
LABEL_23:
      v8 = -1072887838;
      goto LABEL_51;
    }
    v40 = (unsigned __int64)v20 >> 1;
    v21 = operator new[](saturated_mul(v40, 2u));
    *v17 = v21;
    if ( !v21 )
      goto LABEL_20;
    v41 = v13 + 4;
    memcpy_0(v21, v13 + 4, (unsigned __int16)v43);
    *((_WORD *)*v17 + v40 - 1) = 0;
    if ( (int)CTSparseBlock<unsigned long,CASFStreamPropertiesObjectExv1::_STREAM_NAME *,20,1>::SetValue(
                this + 48,
                *((unsigned int *)this + 150),
                v17) < 0 )
    {
      operator delete(*v17);
LABEL_20:
      operator delete(v17);
LABEL_21:
      v8 = -2147024882;
      goto LABEL_51;
    }
    v22 = (unsigned __int16)v43;
    ++*((_DWORD *)this + 150);
    v13 = &v41[v22];
    HIWORD(v14) = WORD1(v42);
    v15 = v44;
    LOWORD(v14) = v42 + 1;
  }
  for ( i = 0; ; LOWORD(i) = v42 + 1 )
  {
    LODWORD(v42) = i;
    if ( (unsigned __int16)i >= v38 )
      break;
    v17 = (void **)operator new(0x28u);
    if ( !v17 )
      goto LABEL_21;
    if ( (unsigned int)CHECK_FOR_SPACE(&v37, 0x16u, a2) == -1072887855 )
      goto LABEL_24;
    *(_OWORD *)v17 = *(_OWORD *)v13;
    *((_WORD *)v17 + 8) = *((_WORD *)v13 + 8);
    v25 = *(_DWORD *)(v13 + 18);
    *((_DWORD *)v17 + 8) = v25;
    if ( (unsigned int)CHECK_FOR_SPACE(&v37, v25, v24) == -1072887855 )
    {
      *a4 = v37;
      goto LABEL_51;
    }
    v27 = operator new[](v26);
    v17[3] = v27;
    if ( !v27 )
      goto LABEL_20;
    v40 = *((unsigned int *)v17 + 8);
    v41 = v13 + 22;
    memcpy_0(v27, v13 + 22, (unsigned int)v40);
    if ( (int)CTSparseBlock<unsigned long,CASFStreamPropertiesObjectExv1::_DATA_UNIT_EXTENSION *,20,1>::SetValue(
                this + 20,
                *((unsigned int *)this + 94),
                v17) < 0 )
      goto LABEL_20;
    v28 = v40;
    ++*((_DWORD *)this + 94);
    v13 = &v41[v28];
    HIWORD(i) = WORD1(v42);
  }
  v29 = v37;
  if ( v37 < (unsigned __int64)this[8] )
  {
    v30 = this[5];
    v43 = 0;
    v8 = (*(__int64 (__fastcall **)(struct IWMSCriticalSection *, GUID *, struct IWMSCriticalSection **, __int64))(*(_QWORD *)v30 + 56LL))(
           v30,
           &CLSID_ASFStreamPropertiesObjectv1,
           &v43,
           v9);
    if ( v8 < 0 )
    {
LABEL_51:
      CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v39);
      return (unsigned int)v8;
    }
    v31 = v43;
    this[19] = v43;
    LODWORD(v42) = 0;
    v32 = (*(__int64 (__fastcall **)(struct IWMSCriticalSection *, _QWORD, unsigned __int8 *, __int64 *))(*(_QWORD *)v31 + 64LL))(
            v31,
            a2 - v29,
            v13,
            &v42);
    v33 = this[19];
    v8 = v32;
    if ( v32 < 0 )
    {
      (*(void (__fastcall **)(struct IWMSCriticalSection *))(*(_QWORD *)v33 + 16LL))(v33);
      this[19] = 0;
      goto LABEL_51;
    }
    v44 = 0;
    if ( (*(int (__fastcall **)(struct IWMSCriticalSection *, unsigned __int16 *))(*(_QWORD *)v33 + 304LL))(v33, &v44) < 0
      || v44 != *((_WORD *)this + 68) )
    {
      v36 = this[19];
      if ( v36 )
      {
        (*(void (__fastcall **)(struct IWMSCriticalSection *))(*(_QWORD *)v36 + 16LL))(v36);
        this[19] = 0;
      }
      goto LABEL_23;
    }
    *((_WORD *)this[19] + 93) = *((_WORD *)this + 69);
    v29 += v42;
  }
  *a4 = v29;
  v34 = this[5];
  if ( v34 )
  {
    v42 = 0;
    if ( (**(int (__fastcall ***)(struct IWMSCriticalSection *, GUID *, __int64 *, __int64))v34)(
           v34,
           &IID_IASFReadWriteTracker,
           &v42,
           v9) >= 0 )
    {
      (*(void (__fastcall **)(__int64, unsigned __int8 *, _QWORD, char *))(*(_QWORD *)v42 + 72LL))(
        v42,
        a3,
        *a4,
        (char *)this + 48);
      if ( v42 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    }
  }
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v39);
  return 0;
}

```

## disassembly

```asm
0x180015a70  push    rbp
0x180015a72  push    rbx
0x180015a73  push    rsi
0x180015a74  push    rdi
0x180015a75  push    r12
0x180015a77  push    r13
0x180015a79  push    r14
0x180015a7b  push    r15
0x180015a7d  mov     rbp, rsp
0x180015a80  sub     rsp, 78h
0x180015a84  mov     rax, cs:__security_cookie
0x180015a8b  xor     rax, rsp
0x180015a8e  mov     [rbp+var_10], rax
0x180015a92  mov     r15d, edx
0x180015a95  mov     rdi, rcx
0x180015a98  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x180015a9c  mov     r14, r9
0x180015a9f  lea     rcx, [rbp+var_40]; this
0x180015aa3  mov     r13, r8
0x180015aa6  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x180015aab  cmp     qword ptr [rdi+28h], 0
0x180015ab0  jnz     short loc_180015ABC
0x180015ab2  mov     ebx, 0C00D07F6h
0x180015ab7  jmp     loc_180015F14
0x180015abc  test    r14, r14
0x180015abf  jz      loc_180015F21
0x180015ac5  mov     r9d, 58h ; 'X'
0x180015acb  test    r15d, r15d
0x180015ace  jz      loc_180015F0C
0x180015ad4  test    r13, r13
0x180015ad7  jz      loc_180015F21
0x180015add  cmp     r15d, r9d
0x180015ae0  jb      loc_180015F0C
0x180015ae6  movups  xmm0, xmmword ptr [r13+0]
0x180015aeb  lea     rcx, [r13+28h]
0x180015aef  xor     edx, edx
0x180015af1  lea     r10d, [r9-57h]
0x180015af5  movdqu  xmmword ptr [rdi+30h], xmm0
0x180015afa  mov     rax, [r13+10h]
0x180015afe  mov     [rdi+40h], rax
0x180015b02  mov     rax, [r13+18h]
0x180015b06  mov     [rdi+58h], rax
0x180015b0a  mov     rax, [r13+20h]
0x180015b0e  mov     [rdi+60h], rax
0x180015b12  mov     eax, [rcx]
0x180015b14  lea     rcx, [rcx+4]
0x180015b18  mov     [rdi+rdx*4+68h], eax
0x180015b1c  add     rdx, r10
0x180015b1f  cmp     rdx, 8
0x180015b23  jnz     short loc_180015B12
0x180015b25  movzx   eax, word ptr [rcx]
0x180015b28  lea     r12, [rcx+10h]
0x180015b2c  mov     [rdi+88h], ax
0x180015b33  mov     ebx, 0C00D07D1h
0x180015b38  movzx   eax, word ptr [rcx+2]
0x180015b3c  mov     [rdi+8Ah], ax
0x180015b43  mov     rax, [rcx+4]
0x180015b47  mov     [rdi+90h], rax
0x180015b4e  xor     eax, eax
0x180015b50  movzx   edx, word ptr [rcx+0Ch]
0x180015b54  movzx   r8d, word ptr [rcx+0Eh]
0x180015b59  mov     [rbp+var_18], dx
0x180015b5d  mov     [rbp+var_44], r8w
0x180015b62  mov     [rbp+var_48], r9d
0x180015b66  mov     dword ptr [rbp+var_28], eax
0x180015b69  cmp     ax, dx
0x180015b6c  jnb     loc_180015CB8
0x180015b72  mov     ecx, 10h; Size
0x180015b77  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015b7c  mov     rsi, rax
0x180015b7f  test    rax, rax
0x180015b82  jz      loc_180015C7F
0x180015b88  mov     r8d, r15d; unsigned int
0x180015b8b  lea     rcx, [rbp+var_48]; unsigned int *
0x180015b8f  mov     edx, 4; unsigned int
0x180015b94  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x180015b99  cmp     eax, ebx
0x180015b9b  jz      loc_180015CA0
0x180015ba1  movzx   ecx, word ptr [r12]
0x180015ba6  mov     [rsi+8], cx
0x180015baa  lea     rcx, [rbp+var_48]; unsigned int *
0x180015bae  movzx   edx, word ptr [r12+2]; unsigned int
0x180015bb4  mov     dword ptr [rbp+var_20], edx
0x180015bb7  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x180015bbc  cmp     eax, ebx
0x180015bbe  jz      loc_180015CA0
0x180015bc4  test    dl, 1
0x180015bc7  jnz     loc_180015C89
0x180015bcd  xor     eax, eax
0x180015bcf  cmp     ax, dx
0x180015bd2  jz      loc_180015C89
0x180015bd8  mov     ecx, edx
0x180015bda  mov     eax, 2
0x180015bdf  shr     rcx, 1
0x180015be2  mul     rcx
0x180015be5  mov     [rbp+var_38], rcx
0x180015be9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180015bf0  cmovb   rax, rcx
0x180015bf4  mov     rcx, rax; unsigned __int64
0x180015bf7  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180015bfc  mov     [rsi], rax
0x180015bff  test    rax, rax
0x180015c02  jz      short loc_180015C72
0x180015c04  movzx   r8d, word ptr [rbp+var_20]; Size
0x180015c09  lea     rcx, [r12+4]
0x180015c0e  mov     [rbp+var_30], rcx
0x180015c12  mov     rdx, rcx; Src
0x180015c15  mov     rcx, rax; void *
0x180015c18  call    memcpy_0
0x180015c1d  mov     rcx, [rsi]
0x180015c20  xor     eax, eax
0x180015c22  mov     rdx, [rbp+var_38]
0x180015c26  mov     r8, rsi
0x180015c29  mov     [rcx+rdx*2-2], ax
0x180015c2e  lea     rcx, [rdi+180h]
0x180015c35  mov     edx, [rdi+258h]
0x180015c3b  call    ?SetValue@?$CTSparseBlock@KPEAU_STREAM_NAME@CASFStreamPropertiesObjectExv1@@$0BE@$00@@QEAAJKPEAU_STREAM_NAME@CASFStreamPropertiesObjectExv1@@@Z; CTSparseBlock<ulong,CASFStreamPropertiesObjectExv1::_STREAM_NAME *,20,1>::SetValue(ulong,CASFStreamPropertiesObjectExv1::_STREAM_NAME *)
0x180015c40  test    eax, eax
0x180015c42  js      short loc_180015C6A
0x180015c44  movzx   r12d, word ptr [rbp+var_20]
0x180015c49  mov     r10d, 1
0x180015c4f  add     [rdi+258h], r10d
0x180015c56  add     r12, [rbp+var_30]
0x180015c5a  mov     eax, dword ptr [rbp+var_28]
0x180015c5d  movzx   edx, [rbp+var_18]
0x180015c61  add     ax, r10w
0x180015c65  jmp     loc_180015B66
0x180015c6a  mov     rcx, [rsi]; Block
0x180015c6d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180015c72  mov     edx, 10h
0x180015c77  mov     rcx, rsi; Block
0x180015c7a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180015c7f  mov     ebx, 8007000Eh
0x180015c84  jmp     loc_180015F14
0x180015c89  mov     edx, 10h
0x180015c8e  mov     rcx, rsi; Block
0x180015c91  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180015c96  mov     ebx, 0C00D07E2h
0x180015c9b  jmp     loc_180015F14
0x180015ca0  mov     edx, 10h
0x180015ca5  mov     eax, [rbp+var_48]
0x180015ca8  mov     rcx, rsi; Block
0x180015cab  mov     [r14], eax
0x180015cae  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180015cb3  jmp     loc_180015F14
0x180015cb8  xor     eax, eax
0x180015cba  mov     dword ptr [rbp+var_28], eax
0x180015cbd  cmp     ax, [rbp+var_44]
0x180015cc1  jnb     loc_180015D9E
0x180015cc7  mov     ecx, 28h ; '('; Size
0x180015ccc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015cd1  mov     rsi, rax
0x180015cd4  test    rax, rax
0x180015cd7  jz      short loc_180015C7F
0x180015cd9  mov     r8d, r15d; unsigned int
0x180015cdc  lea     rcx, [rbp+var_48]; unsigned int *
0x180015ce0  mov     edx, 16h; unsigned int
0x180015ce5  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x180015cea  cmp     eax, ebx
0x180015cec  jz      loc_180015D94
0x180015cf2  movups  xmm0, xmmword ptr [r12]
0x180015cf7  lea     rcx, [rbp+var_48]; unsigned int *
0x180015cfb  movdqu  xmmword ptr [rsi], xmm0
0x180015cff  movzx   eax, word ptr [r12+10h]
0x180015d05  mov     [rsi+10h], ax
0x180015d09  mov     edx, [r12+12h]; unsigned int
0x180015d0e  mov     [rsi+20h], edx
0x180015d11  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x180015d16  cmp     eax, ebx
0x180015d18  jz      short loc_180015D89
0x180015d1a  mov     ecx, edx; unsigned __int64
0x180015d1c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180015d21  mov     [rsi+18h], rax
0x180015d25  test    rax, rax
0x180015d28  jz      short loc_180015D7F
0x180015d2a  mov     edx, [rsi+20h]
0x180015d2d  lea     rcx, [r12+16h]
0x180015d32  mov     [rbp+var_38], rdx
0x180015d36  mov     r8d, edx; Size
0x180015d39  mov     rdx, rcx; Src
0x180015d3c  mov     [rbp+var_30], rcx
0x180015d40  mov     rcx, rax; void *
0x180015d43  call    memcpy_0
0x180015d48  mov     edx, [rdi+178h]
0x180015d4e  lea     rcx, [rdi+0A0h]
0x180015d55  mov     r8, rsi
0x180015d58  call    ?SetValue@?$CTSparseBlock@KPEAU_DATA_UNIT_EXTENSION@CASFStreamPropertiesObjectExv1@@$0BE@$00@@QEAAJKPEAU_DATA_UNIT_EXTENSION@CASFStreamPropertiesObjectExv1@@@Z; CTSparseBlock<ulong,CASFStreamPropertiesObjectExv1::_DATA_UNIT_EXTENSION *,20,1>::SetValue(ulong,CASFStreamPropertiesObjectExv1::_DATA_UNIT_EXTENSION *)
0x180015d5d  test    eax, eax
0x180015d5f  js      short loc_180015D7F
0x180015d61  mov     r12, [rbp+var_38]
0x180015d65  mov     edx, 1
0x180015d6a  add     [rdi+178h], edx
0x180015d70  add     r12, [rbp+var_30]
0x180015d74  mov     eax, dword ptr [rbp+var_28]
0x180015d77  add     ax, dx
0x180015d7a  jmp     loc_180015CBA
0x180015d7f  mov     edx, 28h ; '('
0x180015d84  jmp     loc_180015C77
0x180015d89  mov     eax, [rbp+var_48]
0x180015d8c  mov     [r14], eax
0x180015d8f  jmp     loc_180015F14
0x180015d94  mov     edx, 28h ; '('
0x180015d99  jmp     loc_180015CA5
0x180015d9e  mov     esi, [rbp+var_48]
0x180015da1  cmp     rsi, [rdi+40h]
0x180015da5  jnb     loc_180015E76
0x180015dab  mov     rcx, [rdi+28h]
0x180015daf  lea     r8, [rbp+var_20]
0x180015db3  mov     [rbp+var_20], 0
0x180015dbb  lea     rdx, CLSID_ASFStreamPropertiesObjectv1
0x180015dc2  mov     rax, [rcx]
0x180015dc5  mov     rax, [rax+38h]
0x180015dc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015dce  mov     ebx, eax
0x180015dd0  test    eax, eax
0x180015dd2  js      loc_180015F14
0x180015dd8  mov     rcx, [rbp+var_20]
0x180015ddc  lea     r9, [rbp+var_28]
0x180015de0  mov     [rdi+98h], rcx
0x180015de7  sub     r15d, esi
0x180015dea  mov     dword ptr [rbp+var_28], 0
0x180015df1  mov     r8, r12
0x180015df4  mov     edx, r15d
0x180015df7  mov     rax, [rcx]
0x180015dfa  mov     rax, [rax+40h]
0x180015dfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e03  mov     rcx, [rdi+98h]
0x180015e0a  mov     ebx, eax
0x180015e0c  test    eax, eax
0x180015e0e  jns     short loc_180015E2C
0x180015e10  mov     rax, [rcx]
0x180015e13  mov     rax, [rax+10h]
0x180015e17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e1c  mov     qword ptr [rdi+98h], 0
0x180015e27  jmp     loc_180015F14
0x180015e2c  xor     eax, eax
0x180015e2e  lea     rdx, [rbp+var_18]
0x180015e32  mov     [rbp+var_18], ax
0x180015e36  mov     rax, [rcx]
0x180015e39  mov     rax, [rax+130h]
0x180015e40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e45  test    eax, eax
0x180015e47  js      loc_180015EE0
0x180015e4d  movzx   eax, word ptr [rdi+88h]
0x180015e54  cmp     [rbp+var_18], ax
0x180015e58  jnz     loc_180015EE0
0x180015e5e  mov     rcx, [rdi+98h]
0x180015e65  movzx   eax, word ptr [rdi+8Ah]
0x180015e6c  mov     [rcx+0BAh], ax
0x180015e73  add     esi, dword ptr [rbp+var_28]
0x180015e76  mov     [r14], esi
0x180015e79  mov     rcx, [rdi+28h]
0x180015e7d  test    rcx, rcx
0x180015e80  jz      short loc_180015ED3
0x180015e82  mov     [rbp+var_28], 0
0x180015e8a  lea     r8, [rbp+var_28]
0x180015e8e  mov     rax, [rcx]
0x180015e91  lea     rdx, IID_IASFReadWriteTracker
0x180015e98  mov     rax, [rax]
0x180015e9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ea0  test    eax, eax
0x180015ea2  js      short loc_180015ED3
0x180015ea4  mov     rcx, [rbp+var_28]
0x180015ea8  lea     r9, [rdi+30h]
0x180015eac  mov     r8d, [r14]
0x180015eaf  mov     rdx, r13
0x180015eb2  mov     rax, [rcx]
0x180015eb5  mov     rax, [rax+48h]
0x180015eb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ebe  mov     rcx, [rbp+var_28]
0x180015ec2  test    rcx, rcx
0x180015ec5  jz      short loc_180015ED3
0x180015ec7  mov     rax, [rcx]
0x180015eca  mov     rax, [rax+10h]
0x180015ece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ed3  lea     rcx, [rbp+var_40]; this
0x180015ed7  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180015edc  xor     eax, eax
0x180015ede  jmp     short loc_180015F2F
0x180015ee0  mov     rcx, [rdi+98h]
0x180015ee7  test    rcx, rcx
0x180015eea  jz      loc_180015C96
0x180015ef0  mov     rax, [rcx]
0x180015ef3  mov     rax, [rax+10h]
0x180015ef7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015efc  mov     qword ptr [rdi+98h], 0
0x180015f07  jmp     loc_180015C96
0x180015f0c  mov     [r14], r9d
0x180015f0f  mov     ebx, 0C00D07D1h
0x180015f14  lea     rcx, [rbp+var_40]; this
0x180015f18  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180015f1d  mov     eax, ebx
0x180015f1f  jmp     short loc_180015F2F
0x180015f21  lea     rcx, [rbp+var_40]; this
0x180015f25  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180015f2a  mov     eax, 80070057h
0x180015f2f  mov     rcx, [rbp+var_10]
0x180015f33  xor     rcx, rsp; StackCookie
0x180015f36  call    __security_check_cookie
0x180015f3b  add     rsp, 78h
  ... truncated ...
```
