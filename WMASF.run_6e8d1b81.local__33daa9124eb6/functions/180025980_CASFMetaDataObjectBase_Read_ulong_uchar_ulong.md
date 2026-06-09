# CASFMetaDataObjectBase::Read(ulong,uchar *,ulong *)

- ea: `0x180025980`
- end: `0x180025d2a`
- name: `?Read@CASFMetaDataObjectBase@@UEAAJKPEAEPEAK@Z`
- size: `938`
- prototype: `__int64 __fastcall(CASFMetaDataObjectBase *__hidden this, unsigned int, unsigned __int8 *, unsigned int *)`
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
- `0x180025980`
- `0x18003f2a0`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFMetaDataObjectBase::Read(
        CASFMetaDataObjectBase *this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  unsigned __int64 v4; // r12
  struct IWMSCriticalSection *v6; // rdx
  int v9; // edi
  unsigned int v10; // ebx
  unsigned __int64 v11; // rcx
  unsigned int v12; // eax
  unsigned __int16 v13; // cx
  unsigned __int8 *v14; // r12
  int v15; // eax
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  unsigned int v18; // r10d
  int v19; // edx
  bool v20; // zf
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // eax
  size_t v25; // r10
  size_t v26; // r13
  void *v27; // rax
  char *v28; // rbx
  size_t v29; // r12
  int v30; // r8d
  char *v31; // r13
  __int64 v32; // rax
  char *v33; // r9
  unsigned int v34; // ebx
  int v35; // r12d
  __int64 v36; // r12
  int (__fastcall ***v37)(_QWORD, GUID *, __int64 *); // rcx
  unsigned int v39; // [rsp+30h] [rbp-69h] BYREF
  unsigned __int16 v40; // [rsp+34h] [rbp-65h]
  int v41; // [rsp+38h] [rbp-61h]
  char v42[8]; // [rsp+40h] [rbp-59h] BYREF
  size_t Size; // [rsp+48h] [rbp-51h]
  _OWORD v44[2]; // [rsp+50h] [rbp-49h] BYREF
  unsigned int v45; // [rsp+70h] [rbp-29h] BYREF
  __int64 v46; // [rsp+78h] [rbp-21h] BYREF
  void *Block[2]; // [rsp+80h] [rbp-19h] BYREF
  void *v48[2]; // [rsp+90h] [rbp-9h]

  v4 = a2;
  v6 = (struct IWMSCriticalSection *)*((_QWORD *)this + 4);
  LODWORD(v46) = v4;
  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v42, v6);
  if ( !*((_QWORD *)this + 5) )
  {
    v9 = -1072887818;
    goto LABEL_53;
  }
  if ( !a4 )
    goto LABEL_54;
  v10 = 26;
  if ( !(_DWORD)v4 )
  {
LABEL_52:
    *a4 = 26;
    v9 = -1072887855;
    goto LABEL_53;
  }
  if ( !a3 )
  {
LABEL_54:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v42);
    return 2147942487LL;
  }
  if ( (unsigned int)v4 < 0x1A )
    goto LABEL_52;
  v9 = (*(__int64 (__fastcall **)(CASFMetaDataObjectBase *))(*(_QWORD *)this + 128LL))(this);
  if ( v9 < 0 )
    goto LABEL_53;
  *((_OWORD *)this + 3) = *(_OWORD *)a3;
  v11 = *((_QWORD *)a3 + 2);
  *((_QWORD *)this + 8) = v11;
  if ( v11 >= 0x100000000LL )
  {
    v9 = -1072887821;
    goto LABEL_53;
  }
  v9 = -1072887855;
  if ( v4 >= v11 )
  {
    v13 = *((_WORD *)a3 + 12);
    v14 = a3 + 26;
    v40 = v13;
    v15 = 0;
    v39 = 26;
    while ( 1 )
    {
      v41 = v15;
      if ( (unsigned __int16)v15 >= v13 )
      {
        v37 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 5);
        if ( v37 )
        {
          v46 = 0;
          if ( (**v37)(v37, &IID_IASFReadWriteTracker, &v46) >= 0 )
          {
            (*(void (__fastcall **)(__int64, unsigned __int8 *, _QWORD, char *))(*(_QWORD *)v46 + 72LL))(
              v46,
              a3,
              v10,
              (char *)this + 48);
            if ( v46 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
          }
        }
        *a4 = v10;
        CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v42);
        return 0;
      }
      v16 = *((_DWORD *)this + 16);
      *(_OWORD *)Block = 0;
      *(_OWORD *)v48 = 0;
      if ( (unsigned int)CHECK_FOR_SPACE(&v39, 0xCu, v16) == -1072887855 )
        goto LABEL_46;
      LODWORD(Block[0]) = *(_DWORD *)v14;
      v18 = *((unsigned __int16 *)v14 + 2);
      WORD2(Block[0]) = *((_WORD *)v14 + 3);
      v19 = *((_DWORD *)v14 + 2);
      LODWORD(v48[0]) = v19;
      if ( SHIDWORD(Block[0]) > 32770 )
      {
        v21 = HIDWORD(Block[0]) - 32771;
        v20 = HIDWORD(Block[0]) == 32771;
      }
      else
      {
        if ( HIDWORD(Block[0]) == 32770 || HIDWORD(Block[0]) == 2 )
        {
LABEL_28:
          v24 = 4;
          goto LABEL_29;
        }
        v21 = HIDWORD(Block[0]) - 3;
        v20 = HIDWORD(Block[0]) == 3;
      }
      if ( v20 )
        goto LABEL_28;
      v22 = v21 - 1;
      if ( v22 )
      {
        v23 = v22 - 1;
        if ( v23 )
        {
          if ( v23 != 1 )
            goto LABEL_30;
          v24 = 16;
        }
        else
        {
          v24 = 2;
        }
      }
      else
      {
        v24 = 8;
      }
LABEL_29:
      if ( v24 != v19 )
      {
        v9 = -2147418113;
        goto LABEL_53;
      }
LABEL_30:
      if ( (v18 & 1) != 0 || !(_WORD)v18 )
        goto LABEL_41;
      if ( (unsigned int)CHECK_FOR_SPACE(&v39, v18, v17) == -1072887855 )
      {
LABEL_46:
        v12 = v39;
        goto LABEL_12;
      }
      Size = v25;
      v26 = v25 >> 1;
      v27 = operator new[](saturated_mul(v25 >> 1, 2u));
      Block[1] = v27;
      if ( !v27 )
        goto LABEL_43;
      v28 = (char *)(v14 + 12);
      v29 = Size;
      memcpy_0(v27, v28, Size);
      v30 = v46;
      *((_WORD *)Block[1] + v26 - 1) = 0;
      v31 = &v28[v29];
      v32 = *(_QWORD *)this;
      v33 = &v28[v29];
      v34 = v39;
      v45 = 0;
      v35 = (*(__int64 (__fastcall **)(CASFMetaDataObjectBase *, void **, _QWORD, char *, unsigned int *))(v32 + 168))(
              this,
              Block,
              v30 - v39,
              v33,
              &v45);
      if ( v35 < 0 )
      {
        operator delete(Block[1]);
        v9 = v35;
        goto LABEL_53;
      }
      v10 = v45 + v34;
      v39 = v10;
      if ( LODWORD(v48[0]) && !v48[1] && SHIDWORD(Block[0]) < 0x8000 )
      {
        operator delete(Block[1]);
        operator delete(v48[1]);
LABEL_41:
        v9 = -1072887838;
        goto LABEL_53;
      }
      v36 = v45;
      v44[0] = *(_OWORD *)Block;
      v44[1] = *(_OWORD *)v48;
      if ( !(unsigned int)CTDynArray<CASFMetaDataObjectBase::METADATA_REC,20>::Add((char *)this + 80, v44) )
      {
        operator delete(Block[1]);
        operator delete(v48[1]);
LABEL_43:
        v9 = -2147024882;
        goto LABEL_53;
      }
      HIWORD(v15) = HIWORD(v41);
      v14 = (unsigned __int8 *)&v31[v36];
      v13 = v40;
      LOWORD(v15) = v41 + 1;
    }
  }
  v12 = *((_DWORD *)this + 16);
LABEL_12:
  *a4 = v12;
LABEL_53:
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v42);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180025980  push    rbp
0x180025982  push    rbx
0x180025983  push    rsi
0x180025984  push    rdi
0x180025985  push    r12
0x180025987  push    r13
0x180025989  push    r14
0x18002598b  push    r15
0x18002598d  lea     rbp, [rsp-1Fh]
0x180025992  sub     rsp, 0B8h
0x180025999  mov     rax, cs:__security_cookie
0x1800259a0  xor     rax, rsp
0x1800259a3  mov     [rbp+57h+var_50], rax
0x1800259a7  mov     r12d, edx
0x1800259aa  mov     rsi, rcx
0x1800259ad  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x1800259b1  mov     r14, r9
0x1800259b4  lea     rcx, [rbp+57h+var_B0]; this
0x1800259b8  mov     dword ptr [rbp+57h+var_78], r12d
0x1800259bc  mov     r15, r8
0x1800259bf  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x1800259c4  cmp     qword ptr [rsi+28h], 0
0x1800259c9  jnz     short loc_1800259D5
0x1800259cb  mov     edi, 0C00D07F6h
0x1800259d0  jmp     loc_180025CEF
0x1800259d5  test    r14, r14
0x1800259d8  jz      loc_180025CFC
0x1800259de  mov     ebx, 1Ah
0x1800259e3  test    r12d, r12d
0x1800259e6  jz      loc_180025CE7
0x1800259ec  test    r15, r15
0x1800259ef  jz      loc_180025CFC
0x1800259f5  cmp     r12d, ebx
0x1800259f8  jb      loc_180025CE7
0x1800259fe  mov     rax, [rsi]
0x180025a01  mov     rcx, rsi
0x180025a04  mov     rax, [rax+80h]
0x180025a0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a10  mov     edi, eax
0x180025a12  test    eax, eax
0x180025a14  js      loc_180025CEF
0x180025a1a  movups  xmm0, xmmword ptr [r15]
0x180025a1e  mov     rax, 100000000h
0x180025a28  movdqu  xmmword ptr [rsi+30h], xmm0
0x180025a2d  mov     rcx, [r15+10h]
0x180025a31  mov     [rsi+40h], rcx
0x180025a35  cmp     rcx, rax
0x180025a38  jb      short loc_180025A44
0x180025a3a  mov     edi, 0C00D07F3h
0x180025a3f  jmp     loc_180025CEF
0x180025a44  mov     edi, 0C00D07D1h
0x180025a49  cmp     r12, rcx
0x180025a4c  jnb     short loc_180025A59
0x180025a4e  mov     eax, [rsi+40h]
0x180025a51  mov     [r14], eax
0x180025a54  jmp     loc_180025CEF
0x180025a59  movzx   ecx, word ptr [r15+18h]
0x180025a5e  lea     r12, [r15+1Ah]
0x180025a62  mov     [rbp+57h+var_BC], cx
0x180025a66  xor     eax, eax
0x180025a68  mov     [rbp+57h+var_C0], ebx
0x180025a6b  mov     [rbp+57h+var_B8], eax
0x180025a6e  cmp     ax, cx
0x180025a71  jnb     loc_180025C7D
0x180025a77  mov     r8d, [rsi+40h]; unsigned int
0x180025a7b  lea     rcx, [rbp+57h+var_C0]; unsigned int *
0x180025a7f  xorps   xmm0, xmm0
0x180025a82  mov     edx, 0Ch; unsigned int
0x180025a87  movups  xmmword ptr [rbp+57h+Block], xmm0
0x180025a8b  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x180025a8f  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x180025a94  cmp     eax, edi
0x180025a96  jz      loc_180025C75
0x180025a9c  movzx   eax, word ptr [r12]
0x180025aa1  mov     word ptr [rbp+57h+Block], ax
0x180025aa5  movzx   eax, word ptr [r12+2]
0x180025aab  mov     word ptr [rbp+57h+Block+2], ax
0x180025aaf  movzx   eax, word ptr [r12+6]
0x180025ab5  movzx   r10d, word ptr [r12+4]
0x180025abb  mov     word ptr [rbp+57h+Block+4], ax
0x180025abf  mov     ecx, dword ptr [rbp+57h+Block+4]
0x180025ac2  mov     edx, [r12+8]
0x180025ac7  mov     dword ptr [rbp+57h+var_60], edx
0x180025aca  cmp     ecx, 8002h
0x180025ad0  jg      short loc_180025AF2
0x180025ad2  jz      short loc_180025B08
0x180025ad4  sub     ecx, 2
0x180025ad7  jz      short loc_180025B08
0x180025ad9  sub     ecx, 1
0x180025adc  jz      short loc_180025B08
0x180025ade  sub     ecx, 1
0x180025ae1  jz      short loc_180025B01
0x180025ae3  sub     ecx, 1
0x180025ae6  jz      short loc_180025AFA
0x180025ae8  cmp     ecx, 1
0x180025aeb  jnz     short loc_180025B15
0x180025aed  lea     eax, [rcx+0Fh]
0x180025af0  jmp     short loc_180025B0D
0x180025af2  sub     ecx, 8003h
0x180025af8  jmp     short loc_180025ADC
0x180025afa  mov     eax, 2
0x180025aff  jmp     short loc_180025B0D
0x180025b01  mov     eax, 8
0x180025b06  jmp     short loc_180025B0D
0x180025b08  mov     eax, 4
0x180025b0d  cmp     eax, edx
0x180025b0f  jnz     loc_180025C6E
0x180025b15  test    r10b, 1
0x180025b19  jnz     loc_180025C37
0x180025b1f  xor     eax, eax
0x180025b21  cmp     ax, r10w
0x180025b25  jz      loc_180025C37
0x180025b2b  mov     edx, r10d; unsigned int
0x180025b2e  lea     rcx, [rbp+57h+var_C0]; unsigned int *
0x180025b32  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x180025b37  cmp     eax, edi
0x180025b39  jz      loc_180025C75
0x180025b3f  mov     r13, r10
0x180025b42  mov     [rbp+57h+Size], r10
0x180025b46  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180025b4d  shr     r13, 1
0x180025b50  mov     eax, 2
0x180025b55  mul     r13
0x180025b58  cmovb   rax, rcx
0x180025b5c  mov     rcx, rax; unsigned __int64
0x180025b5f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180025b64  mov     [rbp+57h+Block+8], rax
0x180025b68  test    rax, rax
0x180025b6b  jz      loc_180025C53
0x180025b71  lea     rbx, [r12+0Ch]
0x180025b76  mov     rcx, rax; void *
0x180025b79  mov     r12, [rbp+57h+Size]
0x180025b7d  mov     rdx, rbx; Src
0x180025b80  mov     r8, r12; Size
0x180025b83  call    memcpy_0
0x180025b88  mov     rax, [rbp+57h+Block+8]
0x180025b8c  lea     rdx, [rbp+57h+Block]
0x180025b90  mov     r8d, dword ptr [rbp+57h+var_78]
0x180025b94  xor     ecx, ecx
0x180025b96  mov     [rax+r13*2-2], cx
0x180025b9c  lea     r13, [r12+rbx]
0x180025ba0  mov     rax, [rsi]
0x180025ba3  mov     r9, r13
0x180025ba6  mov     ebx, [rbp+57h+var_C0]
0x180025ba9  sub     r8d, ebx
0x180025bac  mov     [rbp+57h+var_80], ecx
0x180025baf  lea     rcx, [rbp+57h+var_80]
0x180025bb3  mov     [rsp+0F0h+var_D0], rcx
0x180025bb8  mov     rcx, rsi
0x180025bbb  mov     rax, [rax+0A8h]
0x180025bc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025bc7  mov     r12d, eax
0x180025bca  test    eax, eax
0x180025bcc  js      loc_180025C5D
0x180025bd2  add     ebx, [rbp+57h+var_80]
0x180025bd5  cmp     dword ptr [rbp+57h+var_60], 0
0x180025bd9  mov     [rbp+57h+var_C0], ebx
0x180025bdc  jz      short loc_180025BEE
0x180025bde  cmp     [rbp+57h+var_60+8], 0
0x180025be3  jnz     short loc_180025BEE
0x180025be5  cmp     dword ptr [rbp+57h+Block+4], 8000h
0x180025bec  jl      short loc_180025C25
0x180025bee  movups  xmm0, xmmword ptr [rbp+57h+Block]
0x180025bf2  mov     r12d, [rbp+57h+var_80]
0x180025bf6  lea     rcx, [rsi+50h]
0x180025bfa  movups  xmm1, xmmword ptr [rbp+57h+var_60]
0x180025bfe  lea     rdx, [rbp+57h+var_A0]
0x180025c02  movaps  [rbp+57h+var_A0], xmm0
0x180025c06  movaps  [rbp+57h+var_90], xmm1
0x180025c0a  call    ?Add@?$CTDynArray@UMETADATA_REC@CASFMetaDataObjectBase@@$0BE@@@QEAAHUMETADATA_REC@CASFMetaDataObjectBase@@PEAK@Z; CTDynArray<CASFMetaDataObjectBase::METADATA_REC,20>::Add(CASFMetaDataObjectBase::METADATA_REC,ulong *)
0x180025c0f  test    eax, eax
0x180025c11  jz      short loc_180025C41
0x180025c13  mov     eax, [rbp+57h+var_B8]
0x180025c16  add     r12, r13
0x180025c19  movzx   ecx, [rbp+57h+var_BC]
0x180025c1d  inc     ax
0x180025c20  jmp     loc_180025A6B
0x180025c25  mov     rcx, [rbp+57h+Block+8]; Block
0x180025c29  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180025c2e  mov     rcx, [rbp+57h+var_60+8]; Block
0x180025c32  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180025c37  mov     edi, 0C00D07E2h
0x180025c3c  jmp     loc_180025CEF
0x180025c41  mov     rcx, [rbp+57h+Block+8]; Block
0x180025c45  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180025c4a  mov     rcx, [rbp+57h+var_60+8]; Block
0x180025c4e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180025c53  mov     edi, 8007000Eh
0x180025c58  jmp     loc_180025CEF
0x180025c5d  mov     rcx, [rbp+57h+Block+8]; Block
0x180025c61  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180025c66  mov     edi, r12d
0x180025c69  jmp     loc_180025CEF
0x180025c6e  mov     edi, 8000FFFFh
0x180025c73  jmp     short loc_180025CEF
0x180025c75  mov     eax, [rbp+57h+var_C0]
0x180025c78  jmp     loc_180025A51
0x180025c7d  mov     rcx, [rsi+28h]
0x180025c81  test    rcx, rcx
0x180025c84  jz      short loc_180025CD7
0x180025c86  mov     [rbp+57h+var_78], 0
0x180025c8e  lea     r8, [rbp+57h+var_78]
0x180025c92  mov     rax, [rcx]
0x180025c95  lea     rdx, IID_IASFReadWriteTracker
0x180025c9c  mov     rax, [rax]
0x180025c9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ca4  test    eax, eax
0x180025ca6  js      short loc_180025CD7
0x180025ca8  mov     rcx, [rbp+57h+var_78]
0x180025cac  lea     r9, [rsi+30h]
0x180025cb0  mov     r8d, ebx
0x180025cb3  mov     rdx, r15
0x180025cb6  mov     rax, [rcx]
0x180025cb9  mov     rax, [rax+48h]
0x180025cbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025cc2  mov     rcx, [rbp+57h+var_78]
0x180025cc6  test    rcx, rcx
0x180025cc9  jz      short loc_180025CD7
0x180025ccb  mov     rax, [rcx]
0x180025cce  mov     rax, [rax+10h]
0x180025cd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025cd7  lea     rcx, [rbp+57h+var_B0]; this
0x180025cdb  mov     [r14], ebx
0x180025cde  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180025ce3  xor     eax, eax
0x180025ce5  jmp     short loc_180025D0A
0x180025ce7  mov     [r14], ebx
0x180025cea  mov     edi, 0C00D07D1h
0x180025cef  lea     rcx, [rbp+57h+var_B0]; this
0x180025cf3  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180025cf8  mov     eax, edi
0x180025cfa  jmp     short loc_180025D0A
0x180025cfc  lea     rcx, [rbp+57h+var_B0]; this
0x180025d00  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180025d05  mov     eax, 80070057h
0x180025d0a  mov     rcx, [rbp+57h+var_50]
0x180025d0e  xor     rcx, rsp; StackCookie
0x180025d11  call    __security_check_cookie
0x180025d16  add     rsp, 0B8h
0x180025d1d  pop     r15
0x180025d1f  pop     r14
0x180025d21  pop     r13
0x180025d23  pop     r12
0x180025d25  pop     rdi
0x180025d26  pop     rsi
0x180025d27  pop     rbx
0x180025d28  pop     rbp
0x180025d29  retn
```
