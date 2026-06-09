# CASFContentDescriptionObjectv1::Read(ulong,uchar *,ulong *)

- ea: `0x18001a540`
- end: `0x18001a936`
- name: `?Read@CASFContentDescriptionObjectv1@@UEAAJKPEAEPEAK@Z`
- size: `1014`
- prototype: `__int64 __fastcall(CASFContentDescriptionObjectv1 *__hidden this, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x1800011c0`
- `0x1800011cc`
- `0x1800015d0`
- `0x180001ee8`
- `0x1800021dc`
- `0x18000220c`
- `0x180009dd8`
- `0x18001a3a0`
- `0x18001a540`
- `0x18003f2a0`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFContentDescriptionObjectv1::Read(
        CASFContentDescriptionObjectv1 *this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  unsigned __int64 v4; // r12
  struct IWMSCriticalSection *v6; // rdx
  int v9; // edi
  __int128 v10; // xmm0
  unsigned __int64 v11; // rcx
  unsigned __int16 v12; // dx
  unsigned __int16 v13; // ax
  unsigned int v14; // r8d
  unsigned int v15; // r10d
  unsigned int v16; // r9d
  unsigned int v17; // ecx
  unsigned int v18; // eax
  unsigned int v19; // ecx
  unsigned int v20; // eax
  size_t v21; // rdi
  void *v22; // rax
  void *v23; // rsi
  unsigned __int8 *v24; // r15
  unsigned int v25; // r10d
  unsigned __int8 *v26; // rdx
  __int64 v27; // rbx
  unsigned __int16 v28; // dx
  unsigned int v29; // r10d
  __int64 v30; // rbx
  unsigned __int16 v31; // dx
  unsigned __int16 v32; // dx
  __int64 v33; // rbx
  unsigned __int16 v34; // dx
  unsigned __int16 v35; // dx
  __int64 v36; // rbx
  unsigned __int16 v37; // dx
  unsigned __int16 v38; // dx
  unsigned __int64 v39; // rbx
  unsigned __int16 v40; // dx
  int (__fastcall ***v41)(_QWORD, GUID *, size_t *); // rcx
  GUID *v42; // rbx
  unsigned int v44; // [rsp+30h] [rbp-40h] BYREF
  unsigned __int16 v45; // [rsp+34h] [rbp-3Ch]
  unsigned __int16 v46; // [rsp+36h] [rbp-3Ah]
  unsigned int v47; // [rsp+38h] [rbp-38h]
  unsigned int v48; // [rsp+3Ch] [rbp-34h]
  unsigned int v49; // [rsp+40h] [rbp-30h]
  _BYTE v50[8]; // [rsp+48h] [rbp-28h] BYREF
  GUID *v51; // [rsp+50h] [rbp-20h]
  unsigned __int8 *v52; // [rsp+58h] [rbp-18h]
  size_t Size; // [rsp+60h] [rbp-10h] BYREF

  v4 = a2;
  v6 = (struct IWMSCriticalSection *)*((_QWORD *)this + 4);
  v52 = a3;
  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v50, v6);
  if ( !*((_QWORD *)this + 5) )
  {
    v9 = -1072887818;
LABEL_46:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v50);
    return (unsigned int)v9;
  }
  if ( !a4 )
    goto LABEL_47;
  if ( !(_DWORD)v4 )
  {
LABEL_44:
    *a4 = 34;
    goto LABEL_45;
  }
  if ( !a3 )
  {
LABEL_47:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v50);
    return 2147942487LL;
  }
  if ( (unsigned int)v4 < 0x22 )
    goto LABEL_44;
  v9 = (*(__int64 (__fastcall **)(CASFContentDescriptionObjectv1 *))(*(_QWORD *)this + 128LL))(this);
  if ( v9 < 0 )
    goto LABEL_46;
  v10 = *(_OWORD *)a3;
  v51 = (GUID *)((char *)this + 48);
  *((_OWORD *)this + 3) = v10;
  v11 = *((_QWORD *)a3 + 2);
  *((_QWORD *)this + 8) = v11;
  if ( v11 >= 0x100000000LL )
  {
    v9 = -1072887821;
    goto LABEL_46;
  }
  if ( v4 < v11 )
  {
    *a4 = *((_DWORD *)this + 16);
LABEL_45:
    v9 = -1072887855;
    goto LABEL_46;
  }
  v12 = *((_WORD *)a3 + 13);
  v13 = *((_WORD *)a3 + 12);
  v14 = *((unsigned __int16 *)a3 + 14);
  v15 = *((unsigned __int16 *)a3 + 15);
  v16 = *((unsigned __int16 *)a3 + 16);
  if ( v13 <= v12 )
    v13 = *((_WORD *)a3 + 13);
  v45 = *((_WORD *)a3 + 12);
  v17 = v13;
  v18 = v14;
  v46 = v12;
  v47 = v14;
  if ( v17 > v14 )
    v18 = v17;
  v48 = v15;
  v49 = v16;
  v19 = v15;
  v44 = 34;
  if ( v18 > v15 )
    v19 = v18;
  v20 = v16;
  if ( v19 > v16 )
    v20 = v19;
  v21 = v20 + 2;
  Size = v21;
  v22 = operator new[](v21);
  v23 = v22;
  if ( !v22 )
  {
    v9 = -2147024882;
    goto LABEL_46;
  }
  v24 = a3 + 34;
  memset_0(v22, 0, v21);
  v9 = -1072887855;
  if ( v45 )
  {
    if ( (unsigned int)CHECK_FOR_SPACE(&v44, v45, v4) == -1072887855 )
      goto LABEL_36;
    v26 = a3 + 34;
    v27 = v25;
    memcpy_0(v23, v26, v25);
    v24 += v27;
    *((_WORD *)v23 + ((unsigned __int64)(unsigned int)v27 >> 1)) = 0;
    CASFContentDescriptionObjectv1::InternalAdd(this, v28, 2u, (const unsigned __int16 *)v23);
  }
  memset_0(v23, 0, Size);
  if ( v46 )
  {
    if ( (unsigned int)CHECK_FOR_SPACE(&v44, v46, v4) == -1072887855 )
      goto LABEL_36;
    v30 = v29;
    memcpy_0(v23, v24, v29);
    v24 += v30;
    *((_WORD *)v23 + ((unsigned __int64)(unsigned int)v30 >> 1)) = 0;
    CASFContentDescriptionObjectv1::InternalAdd(this, v31, 1u, (const unsigned __int16 *)v23);
  }
  memset_0(v23, 0, Size);
  if ( (_WORD)v47 )
  {
    if ( (unsigned int)CHECK_FOR_SPACE(&v44, v47, v4) == -1072887855 )
      goto LABEL_36;
    v33 = v32;
    memcpy_0(v23, v24, v32);
    v24 += v33;
    *((_WORD *)v23 + ((unsigned __int64)(unsigned int)v33 >> 1)) = 0;
    CASFContentDescriptionObjectv1::InternalAdd(this, v34, 3u, (const unsigned __int16 *)v23);
  }
  memset_0(v23, 0, Size);
  if ( (_WORD)v48 )
  {
    if ( (unsigned int)CHECK_FOR_SPACE(&v44, v48, v4) != -1072887855 )
    {
      v36 = v35;
      memcpy_0(v23, v24, v35);
      v24 += v36;
      *((_WORD *)v23 + ((unsigned __int64)(unsigned int)v36 >> 1)) = 0;
      CASFContentDescriptionObjectv1::InternalAdd(this, v37, 4u, (const unsigned __int16 *)v23);
      goto LABEL_34;
    }
LABEL_36:
    operator delete(v23);
    *a4 = v44;
    goto LABEL_46;
  }
LABEL_34:
  memset_0(v23, 0, Size);
  if ( (_WORD)v49 )
  {
    if ( (unsigned int)CHECK_FOR_SPACE(&v44, v49, v4) == -1072887855 )
      goto LABEL_36;
    v39 = v38;
    memcpy_0(v23, v24, v38);
    *((_WORD *)v23 + (v39 >> 1)) = 0;
    CASFContentDescriptionObjectv1::InternalAdd(this, v40, 0x4Au, (const unsigned __int16 *)v23);
  }
  operator delete(v23);
  v41 = (int (__fastcall ***)(_QWORD, GUID *, size_t *))*((_QWORD *)this + 5);
  if ( v41 && (Size = 0, (**v41)(v41, &IID_IASFReadWriteTracker, &Size) >= 0) )
  {
    v42 = (GUID *)((char *)this + 48);
    (*(void (__fastcall **)(size_t, unsigned __int8 *, _QWORD, char *))(*(_QWORD *)Size + 72LL))(
      Size,
      v52,
      v44,
      (char *)this + 48);
    if ( Size )
      (*(void (__fastcall **)(size_t))(*(_QWORD *)Size + 16LL))(Size);
  }
  else
  {
    v42 = v51;
  }
  *a4 = v44;
  *v42 = CLSID_ASFContentDescriptionObjectv1;
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v50);
  return 0;
}

```

## disassembly

```asm
0x18001a540  mov     [rsp-38h+arg_8], rbx
0x18001a545  push    rbp
0x18001a546  push    rsi
0x18001a547  push    rdi
0x18001a548  push    r12
0x18001a54a  push    r13
0x18001a54c  push    r14
0x18001a54e  push    r15
0x18001a550  mov     rbp, rsp
0x18001a553  sub     rsp, 70h
0x18001a557  mov     rax, cs:__security_cookie
0x18001a55e  xor     rax, rsp
0x18001a561  mov     [rbp+var_8], rax
0x18001a565  mov     r12d, edx
0x18001a568  mov     rbx, r8
0x18001a56b  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x18001a56f  mov     r14, rcx
0x18001a572  lea     rcx, [rbp+var_28]; this
0x18001a576  mov     [rbp+var_18], rbx
0x18001a57a  mov     r13, r9
0x18001a57d  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18001a582  xor     r15d, r15d
0x18001a585  cmp     [r14+28h], r15
0x18001a589  jnz     short loc_18001A595
0x18001a58b  mov     edi, 0C00D07F6h
0x18001a590  jmp     loc_18001A8F7
0x18001a595  test    r13, r13
0x18001a598  jz      loc_18001A904
0x18001a59e  mov     esi, 22h ; '"'
0x18001a5a3  test    r12d, r12d
0x18001a5a6  jz      loc_18001A8EE
0x18001a5ac  test    rbx, rbx
0x18001a5af  jz      loc_18001A904
0x18001a5b5  cmp     r12d, esi
0x18001a5b8  jb      loc_18001A8EE
0x18001a5be  mov     rax, [r14]
0x18001a5c1  mov     rcx, r14
0x18001a5c4  mov     rax, [rax+80h]
0x18001a5cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a5d0  mov     edi, eax
0x18001a5d2  test    eax, eax
0x18001a5d4  js      loc_18001A8F7
0x18001a5da  movups  xmm0, xmmword ptr [rbx]
0x18001a5dd  lea     rax, [r14+30h]
0x18001a5e1  mov     [rbp+var_20], rax
0x18001a5e5  movdqu  xmmword ptr [rax], xmm0
0x18001a5e9  mov     rcx, [rbx+10h]
0x18001a5ed  mov     rax, 100000000h
0x18001a5f7  mov     [r14+40h], rcx
0x18001a5fb  cmp     rcx, rax
0x18001a5fe  jb      short loc_18001A60A
0x18001a600  mov     edi, 0C00D07F3h
0x18001a605  jmp     loc_18001A8F7
0x18001a60a  cmp     r12, rcx
0x18001a60d  jnb     short loc_18001A61C
0x18001a60f  mov     eax, [r14+40h]
0x18001a613  mov     [r13+0], eax
0x18001a617  jmp     loc_18001A8F2
0x18001a61c  movzx   ecx, word ptr [rbx+18h]
0x18001a620  movzx   edx, word ptr [rbx+1Ah]
0x18001a624  movzx   eax, cx
0x18001a627  movzx   r8d, word ptr [rbx+1Ch]
0x18001a62c  cmp     cx, dx
0x18001a62f  movzx   r10d, word ptr [rbx+1Eh]
0x18001a634  movzx   r9d, word ptr [rbx+20h]
0x18001a639  cmovbe  ax, dx
0x18001a63d  mov     [rbp+var_3C], cx
0x18001a641  movzx   ecx, ax
0x18001a644  mov     eax, r8d
0x18001a647  cmp     ecx, r8d
0x18001a64a  mov     [rbp+var_3A], dx
0x18001a64e  mov     [rbp+var_38], r8d
0x18001a652  cmova   eax, ecx
0x18001a655  mov     [rbp+var_34], r10d
0x18001a659  cmp     eax, r10d
0x18001a65c  mov     [rbp+var_30], r9d
0x18001a660  mov     ecx, r10d
0x18001a663  mov     [rbp+var_40], esi
0x18001a666  cmova   ecx, eax
0x18001a669  mov     eax, r9d
0x18001a66c  cmp     ecx, r9d
0x18001a66f  cmova   eax, ecx
0x18001a672  add     eax, 2
0x18001a675  mov     edi, eax
0x18001a677  mov     ecx, eax; unsigned __int64
0x18001a679  mov     [rbp+Size], rdi
0x18001a67d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001a682  mov     rsi, rax
0x18001a685  test    rax, rax
0x18001a688  jnz     short loc_18001A694
0x18001a68a  mov     edi, 8007000Eh
0x18001a68f  jmp     loc_18001A8F7
0x18001a694  mov     r8, rdi; Size
0x18001a697  lea     r15, [rbx+22h]
0x18001a69b  xor     edx, edx; Val
0x18001a69d  mov     rcx, rsi; void *
0x18001a6a0  call    memset_0
0x18001a6a5  movzx   r10d, [rbp+var_3C]
0x18001a6aa  mov     edi, 0C00D07D1h
0x18001a6af  test    r10w, r10w
0x18001a6b3  jz      short loc_18001A6F9
0x18001a6b5  mov     edx, r10d; unsigned int
0x18001a6b8  lea     rcx, [rbp+var_40]; unsigned int *
0x18001a6bc  mov     r8d, r12d; unsigned int
0x18001a6bf  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x18001a6c4  cmp     eax, edi
0x18001a6c6  jz      loc_18001A826
0x18001a6cc  mov     r8d, r10d; Size
0x18001a6cf  mov     rdx, r15; Src
0x18001a6d2  mov     rcx, rsi; void *
0x18001a6d5  mov     ebx, r10d
0x18001a6d8  call    memcpy_0
0x18001a6dd  xor     eax, eax
0x18001a6df  mov     ecx, ebx
0x18001a6e1  shr     rcx, 1
0x18001a6e4  add     r15, rbx
0x18001a6e7  mov     r9, rsi; unsigned __int16 *
0x18001a6ea  mov     r8b, 2; unsigned __int8
0x18001a6ed  mov     [rsi+rcx*2], ax
0x18001a6f1  mov     rcx, r14; this
0x18001a6f4  call    ?InternalAdd@CASFContentDescriptionObjectv1@@IEAAJGEPEBG@Z; CASFContentDescriptionObjectv1::InternalAdd(ushort,uchar,ushort const *)
0x18001a6f9  mov     r8, [rbp+Size]; Size
0x18001a6fd  xor     edx, edx; Val
0x18001a6ff  mov     rcx, rsi; void *
0x18001a702  call    memset_0
0x18001a707  movzx   r10d, [rbp+var_3A]
0x18001a70c  test    r10w, r10w
0x18001a710  jz      short loc_18001A756
0x18001a712  mov     edx, r10d; unsigned int
0x18001a715  lea     rcx, [rbp+var_40]; unsigned int *
0x18001a719  mov     r8d, r12d; unsigned int
0x18001a71c  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x18001a721  cmp     eax, edi
0x18001a723  jz      loc_18001A826
0x18001a729  mov     r8d, r10d; Size
0x18001a72c  mov     rdx, r15; Src
0x18001a72f  mov     rcx, rsi; void *
0x18001a732  mov     ebx, r10d
0x18001a735  call    memcpy_0
0x18001a73a  xor     eax, eax
0x18001a73c  mov     ecx, ebx
0x18001a73e  shr     rcx, 1
0x18001a741  add     r15, rbx
0x18001a744  mov     r9, rsi; unsigned __int16 *
0x18001a747  mov     r8b, 1; unsigned __int8
0x18001a74a  mov     [rsi+rcx*2], ax
0x18001a74e  mov     rcx, r14; this
0x18001a751  call    ?InternalAdd@CASFContentDescriptionObjectv1@@IEAAJGEPEBG@Z; CASFContentDescriptionObjectv1::InternalAdd(ushort,uchar,ushort const *)
0x18001a756  mov     r8, [rbp+Size]; Size
0x18001a75a  xor     edx, edx; Val
0x18001a75c  mov     rcx, rsi; void *
0x18001a75f  call    memset_0
0x18001a764  mov     edx, [rbp+var_38]; unsigned int
0x18001a767  test    dx, dx
0x18001a76a  jz      short loc_18001A7AD
0x18001a76c  mov     r8d, r12d; unsigned int
0x18001a76f  lea     rcx, [rbp+var_40]; unsigned int *
0x18001a773  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x18001a778  cmp     eax, edi
0x18001a77a  jz      loc_18001A826
0x18001a780  movzx   ebx, dx
0x18001a783  mov     rcx, rsi; void *
0x18001a786  mov     r8d, ebx; Size
0x18001a789  mov     rdx, r15; Src
0x18001a78c  call    memcpy_0
0x18001a791  xor     eax, eax
0x18001a793  mov     ecx, ebx
0x18001a795  shr     rcx, 1
0x18001a798  add     r15, rbx
0x18001a79b  mov     r9, rsi; unsigned __int16 *
0x18001a79e  mov     r8b, 3; unsigned __int8
0x18001a7a1  mov     [rsi+rcx*2], ax
0x18001a7a5  mov     rcx, r14; this
0x18001a7a8  call    ?InternalAdd@CASFContentDescriptionObjectv1@@IEAAJGEPEBG@Z; CASFContentDescriptionObjectv1::InternalAdd(ushort,uchar,ushort const *)
0x18001a7ad  mov     r8, [rbp+Size]; Size
0x18001a7b1  xor     edx, edx; Val
0x18001a7b3  mov     rcx, rsi; void *
0x18001a7b6  call    memset_0
0x18001a7bb  mov     edx, [rbp+var_34]; unsigned int
0x18001a7be  test    dx, dx
0x18001a7c1  jz      short loc_18001A800
0x18001a7c3  mov     r8d, r12d; unsigned int
0x18001a7c6  lea     rcx, [rbp+var_40]; unsigned int *
0x18001a7ca  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x18001a7cf  cmp     eax, edi
0x18001a7d1  jz      short loc_18001A826
0x18001a7d3  movzx   ebx, dx
0x18001a7d6  mov     rcx, rsi; void *
0x18001a7d9  mov     r8d, ebx; Size
0x18001a7dc  mov     rdx, r15; Src
0x18001a7df  call    memcpy_0
0x18001a7e4  xor     eax, eax
0x18001a7e6  mov     ecx, ebx
0x18001a7e8  shr     rcx, 1
0x18001a7eb  add     r15, rbx
0x18001a7ee  mov     r9, rsi; unsigned __int16 *
0x18001a7f1  mov     r8b, 4; unsigned __int8
0x18001a7f4  mov     [rsi+rcx*2], ax
0x18001a7f8  mov     rcx, r14; this
0x18001a7fb  call    ?InternalAdd@CASFContentDescriptionObjectv1@@IEAAJGEPEBG@Z; CASFContentDescriptionObjectv1::InternalAdd(ushort,uchar,ushort const *)
0x18001a800  mov     r8, [rbp+Size]; Size
0x18001a804  xor     edx, edx; Val
0x18001a806  mov     rcx, rsi; void *
0x18001a809  call    memset_0
0x18001a80e  mov     edx, [rbp+var_30]; unsigned int
0x18001a811  test    dx, dx
0x18001a814  jz      short loc_18001A864
0x18001a816  mov     r8d, r12d; unsigned int
0x18001a819  lea     rcx, [rbp+var_40]; unsigned int *
0x18001a81d  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x18001a822  cmp     eax, edi
0x18001a824  jnz     short loc_18001A83A
0x18001a826  mov     rcx, rsi; Block
0x18001a829  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001a82e  mov     eax, [rbp+var_40]
0x18001a831  mov     [r13+0], eax
0x18001a835  jmp     loc_18001A8F7
0x18001a83a  movzx   ebx, dx
0x18001a83d  mov     rcx, rsi; void *
0x18001a840  mov     r8d, ebx; Size
0x18001a843  mov     rdx, r15; Src
0x18001a846  call    memcpy_0
0x18001a84b  shr     rbx, 1
0x18001a84e  xor     edi, edi
0x18001a850  mov     r9, rsi; unsigned __int16 *
0x18001a853  mov     r8b, 4Ah ; 'J'; unsigned __int8
0x18001a856  mov     rcx, r14; this
0x18001a859  mov     [rsi+rbx*2], di
0x18001a85d  call    ?InternalAdd@CASFContentDescriptionObjectv1@@IEAAJGEPEBG@Z; CASFContentDescriptionObjectv1::InternalAdd(ushort,uchar,ushort const *)
0x18001a862  jmp     short loc_18001A866
0x18001a864  xor     edi, edi
0x18001a866  mov     rcx, rsi; Block
0x18001a869  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001a86e  mov     rcx, [r14+28h]
0x18001a872  test    rcx, rcx
0x18001a875  jz      short loc_18001A8CB
0x18001a877  mov     [rbp+Size], rdi
0x18001a87b  lea     r8, [rbp+Size]
0x18001a87f  mov     rax, [rcx]
0x18001a882  lea     rdx, IID_IASFReadWriteTracker
0x18001a889  mov     rax, [rax]
0x18001a88c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a891  test    eax, eax
0x18001a893  js      short loc_18001A8CB
0x18001a895  mov     rcx, [rbp+Size]
0x18001a899  lea     rbx, [r14+30h]
0x18001a89d  mov     r8d, [rbp+var_40]
0x18001a8a1  mov     r9, rbx
0x18001a8a4  mov     rdx, [rbp+var_18]
0x18001a8a8  mov     rax, [rcx]
0x18001a8ab  mov     rax, [rax+48h]
0x18001a8af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a8b4  mov     rcx, [rbp+Size]
0x18001a8b8  test    rcx, rcx
0x18001a8bb  jz      short loc_18001A8CF
0x18001a8bd  mov     rax, [rcx]
0x18001a8c0  mov     rax, [rax+10h]
0x18001a8c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a8c9  jmp     short loc_18001A8CF
0x18001a8cb  mov     rbx, [rbp+var_20]
0x18001a8cf  mov     eax, [rbp+var_40]
0x18001a8d2  lea     rcx, [rbp+var_28]; this
0x18001a8d6  mov     [r13+0], eax
0x18001a8da  movups  xmm0, xmmword ptr cs:CLSID_ASFContentDescriptionObjectv1.Data1
0x18001a8e1  movdqu  xmmword ptr [rbx], xmm0
0x18001a8e5  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18001a8ea  xor     eax, eax
0x18001a8ec  jmp     short loc_18001A912
0x18001a8ee  mov     [r13+0], esi
0x18001a8f2  mov     edi, 0C00D07D1h
0x18001a8f7  lea     rcx, [rbp+var_28]; this
0x18001a8fb  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18001a900  mov     eax, edi
0x18001a902  jmp     short loc_18001A912
0x18001a904  lea     rcx, [rbp+var_28]; this
0x18001a908  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18001a90d  mov     eax, 80070057h
0x18001a912  mov     rcx, [rbp+var_8]
0x18001a916  xor     rcx, rsp; StackCookie
0x18001a919  call    __security_check_cookie
0x18001a91e  mov     rbx, [rsp+70h+arg_8]
0x18001a926  add     rsp, 70h
0x18001a92a  pop     r15
0x18001a92c  pop     r14
0x18001a92e  pop     r13
0x18001a930  pop     r12
0x18001a932  pop     rdi
0x18001a933  pop     rsi
0x18001a934  pop     rbp
0x18001a935  retn
```
