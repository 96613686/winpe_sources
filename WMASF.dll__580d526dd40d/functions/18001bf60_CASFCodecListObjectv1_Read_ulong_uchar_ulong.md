# CASFCodecListObjectv1::Read(ulong,uchar *,ulong *)

- ea: `0x18001bf60`
- end: `0x18001c36b`
- name: `?Read@CASFCodecListObjectv1@@UEAAJKPEAEPEAK@Z`
- size: `1035`
- prototype: `__int64 __fastcall(CASFCodecListObjectv1 *__hidden this, unsigned int, unsigned __int8 *, unsigned int *)`
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
- `0x18001bf60`
- `0x18001c374`
- `0x18003f2a0`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFCodecListObjectv1::Read(
        CASFCodecListObjectv1 *this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  unsigned __int64 v4; // rbx
  unsigned int v8; // esi
  unsigned __int64 v9; // rcx
  __int128 v10; // xmm0
  unsigned __int8 *v11; // rbx
  int v12; // edi
  void *v13; // r12
  unsigned int v14; // ecx
  unsigned int v15; // eax
  unsigned int v16; // edx
  unsigned int v17; // r8d
  unsigned __int64 v18; // rdx
  unsigned int v19; // r8d
  int v20; // r10d
  unsigned __int16 *v21; // rdi
  unsigned __int64 v22; // r10
  __int64 v23; // rbx
  void *v24; // rax
  size_t v25; // rbx
  _WORD *v26; // rax
  __int64 v27; // rdx
  unsigned __int64 v28; // r11
  unsigned __int64 v29; // rbx
  _WORD *v30; // rdi
  unsigned __int64 v31; // rax
  unsigned int v32; // r8d
  void *v33; // r10
  size_t v34; // rbx
  _WORD *v35; // rax
  __int64 v36; // r12
  void *v37; // r10
  _WORD *v38; // rbx
  __int64 v39; // rdx
  int (__fastcall ***v40)(_QWORD, GUID *, __int64 *); // rcx
  unsigned int v42; // [rsp+30h] [rbp-69h] BYREF
  void *v43; // [rsp+38h] [rbp-61h]
  unsigned int v44; // [rsp+40h] [rbp-59h]
  _WORD *v45; // [rsp+48h] [rbp-51h]
  char v46[8]; // [rsp+50h] [rbp-49h] BYREF
  void *Block[2]; // [rsp+58h] [rbp-41h]
  void *v48[2]; // [rsp+68h] [rbp-31h]
  _OWORD v49[2]; // [rsp+80h] [rbp-19h] BYREF
  void *v50; // [rsp+A0h] [rbp+7h]
  __int64 v51; // [rsp+B0h] [rbp+17h] BYREF

  v4 = a2;
  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v46, *((struct IWMSCriticalSection **)this + 4));
  if ( !*((_QWORD *)this + 5) )
  {
    v8 = -1072887818;
LABEL_51:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v46);
    return v8;
  }
  if ( !a4 )
    goto LABEL_52;
  if ( !(_DWORD)v4 )
  {
LABEL_50:
    *a4 = 44;
    v8 = -1072887855;
    goto LABEL_51;
  }
  if ( !a3 )
  {
LABEL_52:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v46);
    return 2147942487LL;
  }
  if ( (unsigned int)v4 < 0x2C )
    goto LABEL_50;
  v8 = -1072887855;
  *((_OWORD *)this + 3) = *(_OWORD *)a3;
  v9 = *((_QWORD *)a3 + 2);
  *((_QWORD *)this + 8) = v9;
  if ( v4 < v9 )
  {
    *a4 = v9;
    goto LABEL_51;
  }
  v10 = *(_OWORD *)(a3 + 24);
  v11 = a3 + 44;
  v42 = 44;
  v12 = 0;
  v13 = 0;
  *(_OWORD *)((char *)this + 84) = v10;
  v14 = *((_DWORD *)a3 + 10);
  v15 = 0;
  LODWORD(v51) = v14;
  while ( 1 )
  {
    v44 = v15;
    *(_OWORD *)v48 = 0;
    *(_OWORD *)Block = 0;
    if ( v15 >= v14 )
      break;
    if ( (unsigned int)CHECK_FOR_SPACE(&v42, 2u, *((_DWORD *)this + 16)) == -1072887855 )
      goto LABEL_35;
    LOWORD(Block[0]) = *(_WORD *)v11;
    if ( (unsigned int)CHECK_FOR_SPACE(&v42, v16, v17) == -1072887855 )
      goto LABEL_35;
    v20 = *((unsigned __int16 *)v11 + 1);
    v21 = (unsigned __int16 *)(v11 + 4);
    if ( (_WORD)v20 )
    {
      LODWORD(v43) = *((unsigned __int16 *)v11 + 1);
      if ( (unsigned int)CHECK_FOR_SPACE(&v42, 2 * v20, v19) == -1072887855 )
        goto LABEL_35;
      v23 = (unsigned int)v22;
      v24 = operator new[](saturated_mul(v22, 2u));
      Block[1] = v24;
      if ( !v24 )
      {
LABEL_49:
        v12 = -2147024882;
        break;
      }
      v25 = 2 * v23;
      memcpy_0(v24, v21, v25);
      v21 = (unsigned __int16 *)((char *)v21 + v25);
      *((_WORD *)Block[1] + (int)v43 - 1) = 0;
    }
    else
    {
      v26 = operator new[](v18);
      Block[1] = v26;
      if ( !v26 )
        goto LABEL_49;
      *v26 = 0;
    }
    if ( (unsigned int)CHECK_FOR_SPACE(&v42, 2u, *((_DWORD *)this + 16)) == -1072887855 )
      goto LABEL_35;
    v29 = *v21;
    v30 = (unsigned __int16 *)((char *)v21 + v27);
    v45 = v30;
    if ( (_WORD)v29 )
    {
      v31 = v29 * (unsigned int)v28;
      if ( !is_mul_ok(v29, (unsigned int)v28) )
        v31 = v28 - 3;
      v48[0] = operator new[](v31);
      if ( !v48[0] )
        goto LABEL_49;
      v32 = *((_DWORD *)this + 16);
      LODWORD(v43) = v29;
      if ( (unsigned int)CHECK_FOR_SPACE(&v42, 2 * (int)v29, v32) == -1072887855 )
        goto LABEL_35;
      v34 = 2 * v29;
      memcpy_0(v33, v30, v34);
      v30 = (_WORD *)((char *)v30 + v34);
      v45 = v30;
      *((_WORD *)v48[0] + (int)v43 - 1) = 0;
    }
    else
    {
      v35 = operator new[](v28);
      v48[0] = v35;
      if ( !v35 )
        goto LABEL_49;
      *v35 = 0;
    }
    if ( (unsigned int)CHECK_FOR_SPACE(&v42, 2u, *((_DWORD *)this + 16)) == -1072887855 )
      goto LABEL_35;
    v36 = (unsigned __int16)*v30;
    LOWORD(v48[1]) = *v30;
    v43 = operator new[](LOWORD(v48[1]));
    if ( !v43 )
    {
      v13 = 0;
      v12 = -2147024882;
      break;
    }
    v12 = CHECK_FOR_SPACE(&v42, v36, *((_DWORD *)this + 16));
    if ( v12 == -1072887855 )
    {
      v13 = v43;
LABEL_35:
      v12 = -1072887855;
      *a4 = v42;
      break;
    }
    v38 = v45 + 1;
    memcpy_0(v37, v45 + 1, (unsigned int)v36);
    v39 = *((unsigned int *)this + 248);
    v11 = (unsigned __int8 *)v38 + v36;
    v49[0] = *(_OWORD *)Block;
    v49[1] = *(_OWORD *)v48;
    v50 = v43;
    if ( (int)CTSparseBlock<unsigned long,CASFCodecListObjectv1::CODEC_LIST_ENTRY,20,0>::SetValue(
                (char *)this + 104,
                v39,
                v49) >= 0 )
      ++*((_DWORD *)this + 248);
    v13 = 0;
    v14 = v51;
    v15 = v44 + 1;
  }
  if ( Block[1] )
    operator delete(Block[1]);
  if ( v48[0] )
    operator delete(v48[0]);
  if ( v13 )
    operator delete(v13);
  if ( v12 >= 0 )
  {
    *a4 = v42;
    v40 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 5);
    if ( v40 )
    {
      v51 = 0;
      if ( (**v40)(v40, &IID_IASFReadWriteTracker, &v51) >= 0 )
      {
        (*(void (__fastcall **)(__int64, unsigned __int8 *, _QWORD, char *))(*(_QWORD *)v51 + 72LL))(
          v51,
          a3,
          *a4,
          (char *)this + 48);
        if ( v51 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
      }
    }
  }
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v46);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18001bf60  mov     [rsp-8+arg_8], rbx
0x18001bf65  push    rbp
0x18001bf66  push    rsi
0x18001bf67  push    rdi
0x18001bf68  push    r12
0x18001bf6a  push    r13
0x18001bf6c  push    r14
0x18001bf6e  push    r15
0x18001bf70  lea     rbp, [rsp-27h]
0x18001bf75  sub     rsp, 0C0h
0x18001bf7c  mov     rax, cs:__security_cookie
0x18001bf83  xor     rax, rsp
0x18001bf86  mov     [rbp+57h+var_38], rax
0x18001bf8a  mov     ebx, edx
0x18001bf8c  mov     r15, rcx
0x18001bf8f  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x18001bf93  mov     r14, r9
0x18001bf96  lea     rcx, [rbp+57h+var_A0]; this
0x18001bf9a  mov     r13, r8
0x18001bf9d  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18001bfa2  xor     r11d, r11d
0x18001bfa5  cmp     [r15+28h], r11
0x18001bfa9  jnz     short loc_18001BFB5
0x18001bfab  mov     esi, 0C00D07F6h
0x18001bfb0  jmp     loc_18001C329
0x18001bfb5  test    r14, r14
0x18001bfb8  jz      loc_18001C336
0x18001bfbe  mov     edx, 2Ch ; ','
0x18001bfc3  test    ebx, ebx
0x18001bfc5  jz      loc_18001C321
0x18001bfcb  test    r13, r13
0x18001bfce  jz      loc_18001C336
0x18001bfd4  cmp     ebx, edx
0x18001bfd6  jb      loc_18001C321
0x18001bfdc  movups  xmm0, xmmword ptr [r13+0]
0x18001bfe1  mov     esi, 0C00D07D1h
0x18001bfe6  movdqu  xmmword ptr [r15+30h], xmm0
0x18001bfec  mov     rcx, [r13+10h]
0x18001bff0  mov     [r15+40h], rcx
0x18001bff4  cmp     rbx, rcx
0x18001bff7  jnb     short loc_18001C003
0x18001bff9  mov     eax, ecx
0x18001bffb  mov     [r14], ecx
0x18001bffe  jmp     loc_18001C329
0x18001c003  movups  xmm0, xmmword ptr [r13+18h]
0x18001c008  lea     rbx, [r13+2Ch]
0x18001c00c  mov     [rbp+57h+var_C0], edx
0x18001c00f  mov     edi, r11d
0x18001c012  xor     r12d, r12d
0x18001c015  movdqu  xmmword ptr [r15+54h], xmm0
0x18001c01b  mov     ecx, [r13+28h]
0x18001c01f  mov     eax, r11d
0x18001c022  mov     dword ptr [rbp+57h+var_40], ecx
0x18001c025  mov     [rbp+57h+var_B0], eax
0x18001c028  xorps   xmm0, xmm0
0x18001c02b  movups  xmmword ptr [rbp+57h+var_88], xmm0
0x18001c02f  movups  xmmword ptr [rbp+57h+Block], xmm0
0x18001c033  cmp     eax, ecx
0x18001c035  jnb     loc_18001C271
0x18001c03b  mov     r8d, [r15+40h]; unsigned int
0x18001c03f  lea     rcx, [rbp+57h+var_C0]; unsigned int *
0x18001c043  mov     edx, 2; unsigned int
0x18001c048  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x18001c04d  cmp     eax, esi
0x18001c04f  jz      loc_18001C269
0x18001c055  movzx   eax, word ptr [rbx]
0x18001c058  lea     rcx, [rbp+57h+var_C0]; unsigned int *
0x18001c05c  mov     word ptr [rbp+57h+Block], ax
0x18001c060  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x18001c065  cmp     eax, esi
0x18001c067  jz      loc_18001C269
0x18001c06d  movzx   r10d, word ptr [rbx+2]
0x18001c072  lea     rdi, [rbx+4]
0x18001c076  test    r10w, r10w
0x18001c07a  jz      short loc_18001C0E7
0x18001c07c  lea     edx, [r10+r10]; unsigned int
0x18001c080  mov     dword ptr [rbp+57h+var_B8], r10d
0x18001c084  lea     rcx, [rbp+57h+var_C0]; unsigned int *
0x18001c088  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x18001c08d  cmp     eax, esi
0x18001c08f  jz      loc_18001C269
0x18001c095  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001c09c  mov     eax, 2
0x18001c0a1  mul     r10
0x18001c0a4  mov     ebx, r10d
0x18001c0a7  cmovb   rax, rcx
0x18001c0ab  mov     rcx, rax; unsigned __int64
0x18001c0ae  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001c0b3  mov     [rbp+57h+Block+8], rax
0x18001c0b7  test    rax, rax
0x18001c0ba  jz      loc_18001C317
0x18001c0c0  add     rbx, rbx
0x18001c0c3  mov     rdx, rdi; Src
0x18001c0c6  mov     r8, rbx; Size
0x18001c0c9  mov     rcx, rax; void *
0x18001c0cc  call    memcpy_0
0x18001c0d1  movsxd  rcx, dword ptr [rbp+57h+var_B8]
0x18001c0d5  add     rdi, rbx
0x18001c0d8  mov     rdx, [rbp+57h+Block+8]
0x18001c0dc  xor     r10d, r10d
0x18001c0df  mov     [rdx+rcx*2-2], r10w
0x18001c0e5  jmp     short loc_18001C103
0x18001c0e7  mov     rcx, rdx; unsigned __int64
0x18001c0ea  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001c0ef  xor     r10d, r10d
0x18001c0f2  mov     [rbp+57h+Block+8], rax
0x18001c0f6  test    rax, rax
0x18001c0f9  jz      loc_18001C317
0x18001c0ff  mov     [rax], r10w
0x18001c103  mov     r8d, [r15+40h]; unsigned int
0x18001c107  lea     rcx, [rbp+57h+var_C0]; unsigned int *
0x18001c10b  mov     r11d, 2
0x18001c111  mov     edx, r11d; unsigned int
0x18001c114  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x18001c119  cmp     eax, esi
0x18001c11b  jz      loc_18001C269
0x18001c121  movzx   ebx, word ptr [rdi]
0x18001c124  add     rdi, rdx
0x18001c127  mov     [rbp+57h+var_A8], rdi
0x18001c12b  test    bx, bx
0x18001c12e  jz      short loc_18001C19A
0x18001c130  lea     rcx, [r11-3]
0x18001c134  mov     eax, r11d
0x18001c137  mul     rbx
0x18001c13a  cmovb   rax, rcx
0x18001c13e  mov     rcx, rax; unsigned __int64
0x18001c141  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001c146  mov     [rbp+57h+var_88], rax
0x18001c14a  mov     r10, rax
0x18001c14d  test    rax, rax
0x18001c150  jz      loc_18001C317
0x18001c156  mov     r8d, [r15+40h]; unsigned int
0x18001c15a  lea     edx, [rbx+rbx]; unsigned int
0x18001c15d  lea     rcx, [rbp+57h+var_C0]; unsigned int *
0x18001c161  mov     dword ptr [rbp+57h+var_B8], ebx
0x18001c164  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x18001c169  cmp     eax, esi
0x18001c16b  jz      loc_18001C269
0x18001c171  mov     rdx, rdi; Src
0x18001c174  add     rbx, rbx
0x18001c177  mov     rcx, r10; void *
0x18001c17a  mov     r8, rbx; Size
0x18001c17d  call    memcpy_0
0x18001c182  movsxd  rcx, dword ptr [rbp+57h+var_B8]
0x18001c186  add     rdi, rbx
0x18001c189  mov     rdx, [rbp+57h+var_88]
0x18001c18d  xor     ebx, ebx
0x18001c18f  mov     [rbp+57h+var_A8], rdi
0x18001c193  mov     [rdx+rcx*2-2], bx
0x18001c198  jmp     short loc_18001C1B4
0x18001c19a  mov     rcx, r11; unsigned __int64
0x18001c19d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001c1a2  xor     ebx, ebx
0x18001c1a4  mov     [rbp+57h+var_88], rax
0x18001c1a8  test    rax, rax
0x18001c1ab  jz      loc_18001C317
0x18001c1b1  mov     [rax], bx
0x18001c1b4  mov     r8d, [r15+40h]; unsigned int
0x18001c1b8  lea     rcx, [rbp+57h+var_C0]; unsigned int *
0x18001c1bc  mov     edx, 2; unsigned int
0x18001c1c1  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x18001c1c6  cmp     eax, esi
0x18001c1c8  jz      loc_18001C269
0x18001c1ce  movzx   r12d, word ptr [rdi]
0x18001c1d2  mov     ecx, r12d; unsigned __int64
0x18001c1d5  mov     word ptr [rbp+57h+var_88+8], r12w
0x18001c1da  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001c1df  mov     [rbp+57h+var_B8], rax
0x18001c1e3  mov     r10, rax
0x18001c1e6  test    rax, rax
0x18001c1e9  jz      loc_18001C309
0x18001c1ef  mov     r8d, [r15+40h]; unsigned int
0x18001c1f3  lea     rcx, [rbp+57h+var_C0]; unsigned int *
0x18001c1f7  mov     edx, r12d; unsigned int
0x18001c1fa  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x18001c1ff  mov     edi, eax
0x18001c201  cmp     eax, esi
0x18001c203  jz      short loc_18001C265
0x18001c205  mov     rbx, [rbp+57h+var_A8]
0x18001c209  mov     r8d, r12d; Size
0x18001c20c  add     rbx, 2
0x18001c210  mov     rcx, r10; void *
0x18001c213  mov     rdx, rbx; Src
0x18001c216  call    memcpy_0
0x18001c21b  movups  xmm0, xmmword ptr [rbp+57h+Block]
0x18001c21f  mov     edx, [r15+3E0h]
0x18001c226  add     rbx, r12
0x18001c229  movups  xmm1, xmmword ptr [rbp+57h+var_88]
0x18001c22d  mov     r12, [rbp+57h+var_B8]
0x18001c231  lea     r8, [rbp+57h+var_70]
0x18001c235  lea     rcx, [r15+68h]
0x18001c239  movaps  [rbp+57h+var_70], xmm0
0x18001c23d  movaps  [rbp+57h+var_60], xmm1
0x18001c241  mov     [rbp+57h+var_50], r12
0x18001c245  call    ?SetValue@?$CTSparseBlock@KUCODEC_LIST_ENTRY@CASFCodecListObjectv1@@$0BE@$0A@@@QEAAJKUCODEC_LIST_ENTRY@CASFCodecListObjectv1@@@Z; CTSparseBlock<ulong,CASFCodecListObjectv1::CODEC_LIST_ENTRY,20,0>::SetValue(ulong,CASFCodecListObjectv1::CODEC_LIST_ENTRY)
0x18001c24a  test    eax, eax
0x18001c24c  js      short loc_18001C255
0x18001c24e  inc     dword ptr [r15+3E0h]
0x18001c255  mov     eax, [rbp+57h+var_B0]
0x18001c258  xor     r12d, r12d
0x18001c25b  mov     ecx, dword ptr [rbp+57h+var_40]
0x18001c25e  inc     eax
0x18001c260  jmp     loc_18001C025
0x18001c265  mov     r12, [rbp+57h+var_B8]
0x18001c269  mov     eax, [rbp+57h+var_C0]
0x18001c26c  mov     edi, esi
0x18001c26e  mov     [r14], eax
0x18001c271  mov     rcx, [rbp+57h+Block+8]; Block
0x18001c275  xor     ebx, ebx
0x18001c277  test    rcx, rcx
0x18001c27a  jz      short loc_18001C281
0x18001c27c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001c281  mov     rcx, [rbp+57h+var_88]; Block
0x18001c285  test    rcx, rcx
0x18001c288  jz      short loc_18001C28F
0x18001c28a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001c28f  test    r12, r12
0x18001c292  jz      short loc_18001C29C
0x18001c294  mov     rcx, r12; Block
0x18001c297  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001c29c  test    edi, edi
0x18001c29e  js      short loc_18001C2FC
0x18001c2a0  mov     eax, [rbp+57h+var_C0]
0x18001c2a3  mov     [r14], eax
0x18001c2a6  mov     rcx, [r15+28h]
0x18001c2aa  test    rcx, rcx
0x18001c2ad  jz      short loc_18001C2FC
0x18001c2af  mov     [rbp+57h+var_40], rbx
0x18001c2b3  lea     r8, [rbp+57h+var_40]
0x18001c2b7  mov     rax, [rcx]
0x18001c2ba  lea     rdx, IID_IASFReadWriteTracker
0x18001c2c1  mov     rax, [rax]
0x18001c2c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c2c9  test    eax, eax
0x18001c2cb  js      short loc_18001C2FC
0x18001c2cd  mov     rcx, [rbp+57h+var_40]
0x18001c2d1  lea     r9, [r15+30h]
0x18001c2d5  mov     r8d, [r14]
0x18001c2d8  mov     rdx, r13
0x18001c2db  mov     rax, [rcx]
0x18001c2de  mov     rax, [rax+48h]
0x18001c2e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c2e7  mov     rcx, [rbp+57h+var_40]
0x18001c2eb  test    rcx, rcx
0x18001c2ee  jz      short loc_18001C2FC
0x18001c2f0  mov     rax, [rcx]
0x18001c2f3  mov     rax, [rax+10h]
0x18001c2f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c2fc  lea     rcx, [rbp+57h+var_A0]; this
0x18001c300  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18001c305  mov     eax, edi
0x18001c307  jmp     short loc_18001C344
0x18001c309  mov     r12, [rbp+57h+var_B8]
0x18001c30d  mov     edi, 8007000Eh
0x18001c312  jmp     loc_18001C271
0x18001c317  mov     edi, 8007000Eh
0x18001c31c  jmp     loc_18001C271
0x18001c321  mov     [r14], edx
0x18001c324  mov     esi, 0C00D07D1h
0x18001c329  lea     rcx, [rbp+57h+var_A0]; this
0x18001c32d  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18001c332  mov     eax, esi
0x18001c334  jmp     short loc_18001C344
0x18001c336  lea     rcx, [rbp+57h+var_A0]; this
0x18001c33a  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18001c33f  mov     eax, 80070057h
0x18001c344  mov     rcx, [rbp+57h+var_38]
0x18001c348  xor     rcx, rsp; StackCookie
0x18001c34b  call    __security_check_cookie
0x18001c350  mov     rbx, [rsp+0F0h+arg_8]
0x18001c358  add     rsp, 0C0h
0x18001c35f  pop     r15
0x18001c361  pop     r14
0x18001c363  pop     r13
0x18001c365  pop     r12
0x18001c367  pop     rdi
0x18001c368  pop     rsi
0x18001c369  pop     rbp
0x18001c36a  retn
```
