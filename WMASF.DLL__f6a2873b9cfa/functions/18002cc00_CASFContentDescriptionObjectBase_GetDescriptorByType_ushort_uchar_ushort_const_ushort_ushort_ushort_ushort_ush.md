# CASFContentDescriptionObjectBase::GetDescriptorByType(ushort,uchar,ushort const *,ushort,ushort *,ushort *,ushort,ushort *,ushort *,ushort *)

- ea: `0x18002cc00`
- end: `0x18002cffc`
- name: `?GetDescriptorByType@CASFContentDescriptionObjectBase@@UEAAJGEPEBGGPEAG1G111@Z`
- size: `1020`
- prototype: `__int64 __fastcall(CASFContentDescriptionObjectBase *__hidden this, unsigned __int16, unsigned __int8, const unsigned __int16 *, unsigned __int16, unsigned __int16 *, unsigned __int16 *, unsigned __int16, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x18002c6c0`
- `0x18002cc00`
- `0x180030a00`
- `0x18003f2a0`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFContentDescriptionObjectBase::GetDescriptorByType(
        CASFContentDescriptionObjectBase *this,
        __int16 a2,
        char a3,
        const unsigned __int16 *a4,
        unsigned __int16 a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        unsigned __int16 a8,
        unsigned __int16 *a9,
        unsigned __int16 *a10,
        unsigned __int16 *a11)
{
  struct IWMSCriticalSection *v13; // rdx
  __int64 (__fastcall ***v14)(_QWORD, GUID *, __int64 *); // rcx
  int v15; // ebx
  __m128i v16; // xmm6
  int v17; // ebx
  unsigned __int16 v18; // r14
  int v19; // edi
  unsigned __int16 v20; // bx
  __int64 v21; // rax
  __int64 v22; // rax
  unsigned __int16 v23; // bx
  __int64 v24; // rax
  _WORD *v25; // xmm6_8
  __int64 v26; // rax
  unsigned __int16 v27; // cx
  __int64 v28; // rcx
  void *v29; // rbx
  unsigned __int16 *v30; // rdi
  unsigned __int16 v31; // ax
  _WORD *v32; // rdi
  _WORD *v33; // rdi
  const void *v34; // rdx
  _WORD *v35; // rbx
  unsigned __int16 v38; // [rsp+2Ch] [rbp-A5h]
  __int64 v40; // [rsp+40h] [rbp-91h] BYREF
  void *v41; // [rsp+48h] [rbp-89h]
  unsigned __int16 *v42; // [rsp+50h] [rbp-81h]
  void *v43; // [rsp+58h] [rbp-79h]
  void *Src; // [rsp+70h] [rbp-61h]
  _BYTE v45[24]; // [rsp+78h] [rbp-59h] BYREF
  _BYTE v46[24]; // [rsp+90h] [rbp-41h] BYREF
  __int64 v47; // [rsp+A8h] [rbp-29h] BYREF
  __int16 v48; // [rsp+B0h] [rbp-21h] BYREF

  v13 = (struct IWMSCriticalSection *)*((_QWORD *)this + 4);
  v41 = a6;
  v43 = a9;
  v42 = a11;
  CAutoCritSec::CAutoCritSec((CAutoCritSec *)&v40, v13);
  v14 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 5);
  if ( !v14 )
  {
    v15 = -1072887818;
LABEL_53:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v40);
    return (unsigned int)v15;
  }
  if ( !a6 && a5 || !a7 || !a9 && a8 || !a10 )
  {
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v40);
    return 2147942487LL;
  }
  v47 = 0;
  Src = 0;
  v16 = 0;
  v15 = ASFFindHeaderObject(
          v14,
          (__int64)&CLSID_ASFLanguageListObject,
          (__int64)&IID_IASFLanguageListObject,
          (__int64)&v47);
  if ( v15 < 0 )
    goto LABEL_53;
  v48 = 0;
  v17 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int16 *))(*(_QWORD *)v47 + 120LL))(
          v47,
          a4,
          &v48);
  if ( v47 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    v47 = 0;
  }
  if ( v17 < 0 && a4 )
  {
    v15 = -1072887854;
    goto LABEL_53;
  }
  v38 = 0;
  v18 = 0;
  v19 = 0;
  if ( v17 >= 0 && (v20 = 0, *((_DWORD *)this + 158)) )
  {
    while ( !v19 )
    {
      if ( *(_WORD *)(CTDynArray<CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20>::operator[](
                        (char *)this + 80,
                        v46,
                        v20)
                    + 4) == a2
        && *(_BYTE *)CTDynArray<CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20>::operator[](
                       (char *)this + 80,
                       v45,
                       v20) == a3
        && (v21 = CTDynArray<CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20>::operator[](
                    (char *)this + 80,
                    v46,
                    v20),
            *(_WORD *)(v21 + 2) == v48) )
      {
        v22 = CTDynArray<CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20>::operator[](
                (char *)this + 80,
                v45,
                v20);
        v18 = v20;
        v19 = 1;
        v38 = v20;
        v16 = *(__m128i *)v22;
        Src = *(void **)(v22 + 16);
      }
      else
      {
        v18 = v38;
      }
      if ( (unsigned int)++v20 >= *((_DWORD *)this + 158) )
      {
        if ( v19 )
          break;
        goto LABEL_25;
      }
    }
  }
  else
  {
LABEL_25:
    if ( a4 || (v23 = 0, !*((_DWORD *)this + 158)) )
    {
LABEL_52:
      v15 = -1072887824;
      goto LABEL_53;
    }
    while ( !v19 )
    {
      if ( *(_WORD *)(CTDynArray<CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20>::operator[](
                        (char *)this + 80,
                        v45,
                        v23)
                    + 4) == a2
        && *(_BYTE *)CTDynArray<CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20>::operator[](
                       (char *)this + 80,
                       v46,
                       v23) == a3 )
      {
        v24 = CTDynArray<CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20>::operator[](
                (char *)this + 80,
                v45,
                v23);
        v18 = v23;
        v38 = v23;
        v19 = 1;
        v16 = *(__m128i *)v24;
        Src = *(void **)(v24 + 16);
      }
      else
      {
        v18 = v38;
      }
      if ( (unsigned int)++v23 >= *((_DWORD *)this + 158) )
      {
        if ( !v19 )
          goto LABEL_52;
        break;
      }
    }
  }
  v25 = (_WORD *)_mm_srli_si128(v16, 8).m128i_u64[0];
  v26 = -1;
  if ( v25 )
  {
    v28 = -1;
    do
      ++v28;
    while ( v25[v28] );
    v27 = v28 + 1;
  }
  else
  {
    v27 = 1;
  }
  *a7 = v27;
  v29 = Src;
  do
    ++v26;
  while ( *((_WORD *)Src + v26) );
  v30 = a10;
  v31 = v26 + 1;
  *a10 = v31;
  if ( a5 < *a7 || a8 < v31 )
  {
    v15 = -1072887855;
    goto LABEL_53;
  }
  if ( v25 )
  {
    v32 = v41;
    memcpy_0(v41, v25, 2LL * *a7);
    v32[*a7 - 1] = 0;
LABEL_47:
    v30 = a10;
    goto LABEL_48;
  }
  if ( a5 )
  {
    v33 = v41;
    *a7 = 1;
    *v33 = 0;
    goto LABEL_47;
  }
LABEL_48:
  if ( v42 )
    *v42 = v18;
  v34 = v29;
  v35 = v43;
  memcpy_0(v43, v34, 2LL * *v30);
  v35[*v30 - 1] = 0;
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v40);
  return 0;
}

```

## disassembly

```asm
0x18002cc00  mov     rax, rsp
0x18002cc03  mov     [rax+10h], rbx
0x18002cc07  push    rbp
0x18002cc08  push    rsi
0x18002cc09  push    rdi
0x18002cc0a  push    r12
0x18002cc0c  push    r13
0x18002cc0e  push    r14
0x18002cc10  push    r15
0x18002cc12  lea     rbp, [rax-3Fh]
0x18002cc16  sub     rsp, 0D0h
0x18002cc1d  movaps  xmmword ptr [rax-48h], xmm6
0x18002cc21  mov     rax, cs:__security_cookie
0x18002cc28  xor     rax, rsp
0x18002cc2b  mov     [rbp+37h+var_50], rax
0x18002cc2f  mov     rax, [rbp+37h+arg_50]
0x18002cc36  mov     rsi, rcx
0x18002cc39  mov     rbx, [rbp+37h+arg_28]
0x18002cc3d  mov     r12, r9
0x18002cc40  mov     r14, [rbp+37h+arg_40]
0x18002cc47  mov     rdi, [rbp+37h+arg_48]
0x18002cc4e  mov     r13, [rbp+37h+arg_30]
0x18002cc52  mov     word ptr [rsp+100h+var_D8], dx
0x18002cc57  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x18002cc5b  lea     rcx, [rsp+100h+var_C8]; this
0x18002cc60  mov     byte ptr [rsp+100h+var_E0], r8b
0x18002cc65  mov     [rsp+100h+var_C0], rbx
0x18002cc6a  mov     [rbp+37h+var_B0], r14
0x18002cc6e  mov     qword ptr [rsp+100h+var_D0], rdi
0x18002cc73  mov     [rsp+100h+var_B8], rax
0x18002cc78  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18002cc7d  mov     rcx, [rsi+28h]
0x18002cc81  xor     r15d, r15d
0x18002cc84  test    rcx, rcx
0x18002cc87  jnz     short loc_18002CC93
0x18002cc89  mov     ebx, 0C00D07F6h
0x18002cc8e  jmp     loc_18002CFB3
0x18002cc93  test    rbx, rbx
0x18002cc96  jnz     short loc_18002CCA3
0x18002cc98  cmp     r15w, [rbp+37h+arg_20]
0x18002cc9d  jnz     loc_18002CFC1
0x18002cca3  test    r13, r13
0x18002cca6  jz      loc_18002CFC1
0x18002ccac  test    r14, r14
0x18002ccaf  jnz     short loc_18002CCBC
0x18002ccb1  cmp     r15w, [rbp+37h+arg_38]
0x18002ccb6  jnz     loc_18002CFC1
0x18002ccbc  test    rdi, rdi
0x18002ccbf  jz      loc_18002CFC1
0x18002ccc5  xor     eax, eax
0x18002ccc7  mov     [rbp+37h+var_60], r15
0x18002cccb  lea     r9, [rbp+37h+var_60]
0x18002cccf  mov     [rbp+37h+Src], rax
0x18002ccd3  lea     r8, IID_IASFLanguageListObject
0x18002ccda  xorps   xmm6, xmm6
0x18002ccdd  lea     rdx, CLSID_ASFLanguageListObject
0x18002cce4  call    ASFFindHeaderObject
0x18002cce9  mov     ebx, eax
0x18002cceb  test    eax, eax
0x18002cced  js      loc_18002CFB3
0x18002ccf3  mov     rcx, [rbp+37h+var_60]
0x18002ccf7  lea     r8, [rbp+37h+var_58]
0x18002ccfb  mov     [rbp+37h+var_58], r15w
0x18002cd00  mov     rdx, r12
0x18002cd03  mov     rax, [rcx]
0x18002cd06  mov     rax, [rax+78h]
0x18002cd0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd0f  mov     rcx, [rbp+37h+var_60]
0x18002cd13  mov     ebx, eax
0x18002cd15  test    rcx, rcx
0x18002cd18  jz      short loc_18002CD2A
0x18002cd1a  mov     rdx, [rcx]
0x18002cd1d  mov     rax, [rdx+10h]
0x18002cd21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd26  mov     [rbp+37h+var_60], r15
0x18002cd2a  test    ebx, ebx
0x18002cd2c  jns     short loc_18002CD3D
0x18002cd2e  test    r12, r12
0x18002cd31  jz      short loc_18002CD3D
0x18002cd33  mov     ebx, 0C00D07D2h
0x18002cd38  jmp     loc_18002CFB3
0x18002cd3d  mov     [rsp+100h+var_DC], r15d
0x18002cd42  mov     r14d, r15d
0x18002cd45  mov     edi, r15d
0x18002cd48  mov     r8d, 1
0x18002cd4e  test    ebx, ebx
0x18002cd50  js      loc_18002CE1A
0x18002cd56  mov     ebx, r15d
0x18002cd59  cmp     [rsi+278h], r15d
0x18002cd60  jbe     loc_18002CE1A
0x18002cd66  test    edi, edi
0x18002cd68  jnz     loc_18002CECE
0x18002cd6e  movzx   r14d, bx
0x18002cd72  lea     r15, [rsi+50h]
0x18002cd76  mov     r8d, r14d
0x18002cd79  lea     rdx, [rbp+37h+var_78]
0x18002cd7d  mov     rcx, r15
0x18002cd80  call    ??A?$CTDynArray@UCONTENT_DESCRIPTION_REC@CASFContentDescriptionObjectBase@@$0BE@@@QEBA?AUCONTENT_DESCRIPTION_REC@CASFContentDescriptionObjectBase@@K@Z; CTDynArray<CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20>::operator[](ulong)
0x18002cd85  movzx   ecx, word ptr [rsp+100h+var_D8]
0x18002cd8a  cmp     [rax+4], cx
0x18002cd8e  jnz     short loc_18002CDEE
0x18002cd90  mov     r8d, r14d
0x18002cd93  lea     rdx, [rbp+37h+var_90]
0x18002cd97  mov     rcx, r15
0x18002cd9a  call    ??A?$CTDynArray@UCONTENT_DESCRIPTION_REC@CASFContentDescriptionObjectBase@@$0BE@@@QEBA?AUCONTENT_DESCRIPTION_REC@CASFContentDescriptionObjectBase@@K@Z; CTDynArray<CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20>::operator[](ulong)
0x18002cd9f  mov     cl, byte ptr [rsp+100h+var_E0]
0x18002cda3  cmp     [rax], cl
0x18002cda5  jnz     short loc_18002CDEE
0x18002cda7  mov     r8d, r14d
0x18002cdaa  lea     rdx, [rbp+37h+var_78]
0x18002cdae  mov     rcx, r15
0x18002cdb1  call    ??A?$CTDynArray@UCONTENT_DESCRIPTION_REC@CASFContentDescriptionObjectBase@@$0BE@@@QEBA?AUCONTENT_DESCRIPTION_REC@CASFContentDescriptionObjectBase@@K@Z; CTDynArray<CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20>::operator[](ulong)
0x18002cdb6  movzx   edx, [rbp+37h+var_58]
0x18002cdba  cmp     [rax+2], dx
0x18002cdbe  jnz     short loc_18002CDEE
0x18002cdc0  mov     r8d, r14d
0x18002cdc3  lea     rdx, [rbp+37h+var_90]
0x18002cdc7  mov     rcx, r15
0x18002cdca  call    ??A?$CTDynArray@UCONTENT_DESCRIPTION_REC@CASFContentDescriptionObjectBase@@$0BE@@@QEBA?AUCONTENT_DESCRIPTION_REC@CASFContentDescriptionObjectBase@@K@Z; CTDynArray<CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20>::operator[](ulong)
0x18002cdcf  lea     r8d, [rdi+1]
0x18002cdd3  movzx   r14d, bx
0x18002cdd7  mov     edi, r8d
0x18002cdda  mov     [rsp+100h+var_DC], r14d
0x18002cddf  movsd   xmm0, qword ptr [rax+10h]
0x18002cde4  movups  xmm6, xmmword ptr [rax]
0x18002cde7  movsd   [rbp+37h+Src], xmm0
0x18002cdec  jmp     short loc_18002CDF9
0x18002cdee  mov     r14d, [rsp+100h+var_DC]
0x18002cdf3  mov     r8d, 1
0x18002cdf9  add     bx, r8w
0x18002cdfd  mov     r15d, 0
0x18002ce03  movzx   eax, bx
0x18002ce06  cmp     eax, [rsi+278h]
0x18002ce0c  jb      loc_18002CD66
0x18002ce12  test    edi, edi
0x18002ce14  jnz     loc_18002CECE
0x18002ce1a  test    r12, r12
0x18002ce1d  jnz     loc_18002CFAE
0x18002ce23  mov     ebx, r15d
0x18002ce26  cmp     [rsi+278h], r15d
0x18002ce2d  jbe     loc_18002CFAE
0x18002ce33  test    edi, edi
0x18002ce35  jnz     loc_18002CECE
0x18002ce3b  movzx   r14d, bx
0x18002ce3f  lea     r15, [rsi+50h]
0x18002ce43  mov     r8d, r14d
0x18002ce46  lea     rdx, [rbp+37h+var_90]
0x18002ce4a  mov     rcx, r15
0x18002ce4d  call    ??A?$CTDynArray@UCONTENT_DESCRIPTION_REC@CASFContentDescriptionObjectBase@@$0BE@@@QEBA?AUCONTENT_DESCRIPTION_REC@CASFContentDescriptionObjectBase@@K@Z; CTDynArray<CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20>::operator[](ulong)
0x18002ce52  movzx   ecx, word ptr [rsp+100h+var_D8]
0x18002ce57  cmp     [rax+4], cx
0x18002ce5b  jnz     short loc_18002CEA2
0x18002ce5d  mov     r8d, r14d
0x18002ce60  lea     rdx, [rbp+37h+var_78]
0x18002ce64  mov     rcx, r15
0x18002ce67  call    ??A?$CTDynArray@UCONTENT_DESCRIPTION_REC@CASFContentDescriptionObjectBase@@$0BE@@@QEBA?AUCONTENT_DESCRIPTION_REC@CASFContentDescriptionObjectBase@@K@Z; CTDynArray<CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20>::operator[](ulong)
0x18002ce6c  mov     cl, byte ptr [rsp+100h+var_E0]
0x18002ce70  cmp     [rax], cl
0x18002ce72  jnz     short loc_18002CEA2
0x18002ce74  mov     r8d, r14d
0x18002ce77  lea     rdx, [rbp+37h+var_90]
0x18002ce7b  mov     rcx, r15
0x18002ce7e  call    ??A?$CTDynArray@UCONTENT_DESCRIPTION_REC@CASFContentDescriptionObjectBase@@$0BE@@@QEBA?AUCONTENT_DESCRIPTION_REC@CASFContentDescriptionObjectBase@@K@Z; CTDynArray<CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20>::operator[](ulong)
0x18002ce83  movzx   r14d, bx
0x18002ce87  lea     r8d, [rdi+1]
0x18002ce8b  mov     [rsp+100h+var_DC], r14d
0x18002ce90  mov     edi, r8d
0x18002ce93  movsd   xmm0, qword ptr [rax+10h]
0x18002ce98  movups  xmm6, xmmword ptr [rax]
0x18002ce9b  movsd   [rbp+37h+Src], xmm0
0x18002cea0  jmp     short loc_18002CEAD
0x18002cea2  mov     r14d, [rsp+100h+var_DC]
0x18002cea7  mov     r8d, 1
0x18002cead  add     bx, r8w
0x18002ceb1  mov     r15d, 0
0x18002ceb7  movzx   eax, bx
0x18002ceba  cmp     eax, [rsi+278h]
0x18002cec0  jb      loc_18002CE33
0x18002cec6  test    edi, edi
0x18002cec8  jz      loc_18002CFAE
0x18002cece  psrldq  xmm6, 8
0x18002ced3  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002ced7  movq    rdx, xmm6; Src
0x18002cedc  test    rdx, rdx
0x18002cedf  jnz     short loc_18002CEE7
0x18002cee1  movzx   ecx, r8w
0x18002cee5  jmp     short loc_18002CEF8
0x18002cee7  mov     rcx, rax
0x18002ceea  inc     rcx
0x18002ceed  cmp     [rdx+rcx*2], r15w
0x18002cef2  jnz     short loc_18002CEEA
0x18002cef4  add     cx, r8w
0x18002cef8  mov     [r13+0], cx
0x18002cefd  mov     rbx, [rbp+37h+Src]
0x18002cf01  inc     rax
0x18002cf04  cmp     [rbx+rax*2], r15w
0x18002cf09  jnz     short loc_18002CF01
0x18002cf0b  mov     rdi, qword ptr [rsp+100h+var_D0]
0x18002cf10  add     ax, r8w
0x18002cf14  movzx   ecx, [rbp+37h+arg_20]
0x18002cf18  mov     [rdi], ax
0x18002cf1b  cmp     cx, [r13+0]
0x18002cf20  jb      loc_18002CFA7
0x18002cf26  cmp     [rbp+37h+arg_38], ax
0x18002cf2a  jb      short loc_18002CFA7
0x18002cf2c  test    rdx, rdx
0x18002cf2f  jz      short loc_18002CF53
0x18002cf31  movzx   r8d, word ptr [r13+0]
0x18002cf36  mov     rdi, [rsp+100h+var_C0]
0x18002cf3b  add     r8, r8; Size
0x18002cf3e  mov     rcx, rdi; void *
0x18002cf41  call    memcpy_0
0x18002cf46  movzx   ecx, word ptr [r13+0]
0x18002cf4b  mov     [rdi+rcx*2-2], r15w
0x18002cf51  jmp     short loc_18002CF67
0x18002cf53  cmp     r15w, cx
0x18002cf57  jz      short loc_18002CF6C
0x18002cf59  mov     rdi, [rsp+100h+var_C0]
0x18002cf5e  mov     [r13+0], r8w
0x18002cf63  mov     [rdi], r15w
0x18002cf67  mov     rdi, qword ptr [rsp+100h+var_D0]
0x18002cf6c  mov     rax, [rsp+100h+var_B8]
0x18002cf71  test    rax, rax
0x18002cf74  jz      short loc_18002CF7A
0x18002cf76  mov     [rax], r14w
0x18002cf7a  movzx   r8d, word ptr [rdi]
0x18002cf7e  mov     rdx, rbx; Src
0x18002cf81  mov     rbx, [rbp+37h+var_B0]
0x18002cf85  add     r8, r8; Size
0x18002cf88  mov     rcx, rbx; void *
0x18002cf8b  call    memcpy_0
0x18002cf90  movzx   ecx, word ptr [rdi]
0x18002cf93  mov     [rbx+rcx*2-2], r15w
0x18002cf99  lea     rcx, [rsp+100h+var_C8]; this
0x18002cf9e  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18002cfa3  xor     eax, eax
0x18002cfa5  jmp     short loc_18002CFD0
0x18002cfa7  mov     ebx, 0C00D07D1h
0x18002cfac  jmp     short loc_18002CFB3
0x18002cfae  mov     ebx, 0C00D07F0h
0x18002cfb3  lea     rcx, [rsp+100h+var_C8]; this
0x18002cfb8  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18002cfbd  mov     eax, ebx
0x18002cfbf  jmp     short loc_18002CFD0
0x18002cfc1  lea     rcx, [rsp+100h+var_C8]; this
0x18002cfc6  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18002cfcb  mov     eax, 80070057h
0x18002cfd0  mov     rcx, [rbp+37h+var_50]
0x18002cfd4  xor     rcx, rsp; StackCookie
0x18002cfd7  call    __security_check_cookie
0x18002cfdc  lea     r11, [rsp+100h+var_30]
0x18002cfe4  mov     rbx, [r11+48h]
0x18002cfe8  movaps  xmm6, xmmword ptr [r11-10h]
0x18002cfed  mov     rsp, r11
0x18002cff0  pop     r15
0x18002cff2  pop     r14
0x18002cff4  pop     r13
0x18002cff6  pop     r12
0x18002cff8  pop     rdi
0x18002cff9  pop     rsi
0x18002cffa  pop     rbp
0x18002cffb  retn
```
