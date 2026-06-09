# CASFMetaDataObjectBase::GetDescriptorEx(ushort,ushort *,ushort *,ushort,ushort *,ushort *,__MIDL___MIDL_itf_asfv2_0000_0000_0001 *,ulong,uchar *,ulong *)

- ea: `0x180025240`
- end: `0x18002544f`
- name: `?GetDescriptorEx@CASFMetaDataObjectBase@@UEAAJGPEAG0G00PEAW4__MIDL___MIDL_itf_asfv2_0000_0000_0001@@KPEAEPEAK@Z`
- size: `527`
- prototype: `__int64 __fastcall(CASFMetaDataObjectBase *__hidden this, unsigned __int16, unsigned __int16 *, unsigned __int16 *, unsigned __int16, unsigned __int16 *, unsigned __int16 *, enum __MIDL___MIDL_itf_asfv2_0000_0000_0001 *, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800021dc`
- `0x18000220c`
- `0x180024b8c`
- `0x180025240`
- `0x18003f2a0`

## pseudocode

```c
__int64 __fastcall CASFMetaDataObjectBase::GetDescriptorEx(
        struct IWMSCriticalSection **this,
        unsigned __int16 a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        enum __MIDL___MIDL_itf_asfv2_0000_0000_0001 *a8,
        unsigned int a9,
        unsigned __int8 *a10,
        unsigned int *a11)
{
  unsigned int v11; // edi
  unsigned int v15; // ebx
  unsigned __int16 *v16; // r14
  enum __MIDL___MIDL_itf_asfv2_0000_0000_0001 *v17; // r15
  unsigned int *v18; // r13
  __m128i *v19; // rax
  __m128i v20; // xmm2
  __m128i v21; // xmm6
  __int64 v22; // rcx
  int v23; // ebp
  _WORD *v24; // xmm2_8
  __int64 v25; // rax
  unsigned __int16 *v26; // rdi
  unsigned __int16 v27; // ax
  unsigned __int16 i; // bp
  __m128i *v29; // rax
  unsigned __int8 *v30; // rcx
  unsigned int v31; // eax
  const void *v32; // rdx
  _BYTE v34[32]; // [rsp+20h] [rbp-78h] BYREF
  char v35; // [rsp+A0h] [rbp+8h] BYREF

  v11 = a2;
  CAutoCritSec::CAutoCritSec((CAutoCritSec *)&v35, this[4]);
  if ( !this[5] )
  {
    v15 = -1072887818;
    goto LABEL_31;
  }
  if ( a3 )
  {
    v16 = a7;
    if ( a7 )
    {
      v17 = a8;
      if ( a8 )
      {
        v18 = a11;
        if ( a11 )
        {
          if ( v11 < *((_DWORD *)this + 200) )
          {
            if ( *a3 == 0xFFFF )
            {
              v19 = (__m128i *)CTDynArray<CASFMetaDataObjectBase::METADATA_REC,20>::operator[](this + 10, v34, v11);
              v20 = *v19;
              v21 = v19[1];
              v22 = v19->m128i_i64[0];
LABEL_10:
              v23 = 0;
              *a3 = _mm_extract_epi16(v20, 1);
              *(_DWORD *)v17 = _mm_cvtsi128_si32(_mm_srli_si128(v20, 4));
              if ( a4 )
                *a4 = v22;
              v24 = (_WORD *)_mm_srli_si128(v20, 8).m128i_u64[0];
              v25 = -1;
              do
                ++v25;
              while ( v24[v25] );
              v26 = a6;
              v27 = v25 + 1;
              *v16 = v27;
              v15 = -1072887855;
              if ( v26 )
              {
                if ( a5 >= v27 )
                {
                  memcpy_0(v26, v24, 2LL * v27);
                  v26[*v16 - 1] = 0;
                }
                else
                {
                  v23 = -1072887855;
                }
              }
              v30 = a10;
              v31 = _mm_cvtsi128_si32(v21);
              *v18 = v31;
              if ( v30 )
              {
                if ( v23 == -1072887855 || a9 < v31 )
                  goto LABEL_31;
                v32 = (const void *)_mm_srli_si128(v21, 8).m128i_u64[0];
                if ( v32 )
                  memcpy_0(v30, v32, v31);
              }
              CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v35);
              return 0;
            }
            for ( i = 0; (unsigned int)i < *((_DWORD *)this + 200); ++i )
            {
              v29 = (__m128i *)CTDynArray<CASFMetaDataObjectBase::METADATA_REC,20>::operator[](this + 10, v34, i);
              v20 = *v29;
              v21 = v29[1];
              v22 = v29->m128i_i64[0];
              if ( WORD1(v29->m128i_i64[0]) == *a3 )
              {
                if ( !(_WORD)v11 )
                  goto LABEL_10;
                LOWORD(v11) = v11 - 1;
              }
            }
          }
          v15 = -1072887824;
LABEL_31:
          CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v35);
          return v15;
        }
      }
    }
  }
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v35);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180025240  mov     rax, rsp
0x180025243  push    rbx
0x180025244  push    rbp
0x180025245  push    rsi
0x180025246  push    rdi
0x180025247  push    r12
0x180025249  push    r13
0x18002524b  push    r14
0x18002524d  push    r15
0x18002524f  sub     rsp, 58h
0x180025253  movzx   edi, dx
0x180025256  mov     rbx, rcx
0x180025259  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x18002525d  mov     r12, r9
0x180025260  lea     rcx, [rax+8]; this
0x180025264  movaps  xmmword ptr [rax-58h], xmm6
0x180025268  mov     rsi, r8
0x18002526b  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x180025270  xor     r9d, r9d
0x180025273  cmp     [rbx+28h], r9
0x180025277  jnz     short loc_180025283
0x180025279  mov     ebx, 0C00D07F6h
0x18002527e  jmp     loc_180025416
0x180025283  test    rsi, rsi
0x180025286  jz      loc_180025427
0x18002528c  mov     r14, [rsp+98h+arg_30]
0x180025294  test    r14, r14
0x180025297  jz      loc_180025427
0x18002529d  mov     r15, [rsp+98h+arg_38]
0x1800252a5  test    r15, r15
0x1800252a8  jz      loc_180025427
0x1800252ae  mov     r13, [rsp+98h+arg_50]
0x1800252b6  test    r13, r13
0x1800252b9  jz      loc_180025427
0x1800252bf  mov     r8d, edi
0x1800252c2  cmp     edi, [rbx+320h]
0x1800252c8  jnb     loc_180025411
0x1800252ce  mov     eax, 0FFFFh
0x1800252d3  cmp     ax, [rsi]
0x1800252d6  jnz     short loc_180025357
0x1800252d8  lea     rcx, [rbx+50h]
0x1800252dc  lea     rdx, [rsp+98h+var_78]
0x1800252e1  call    ??A?$CTDynArray@UMETADATA_REC@CASFMetaDataObjectBase@@$0BE@@@QEBA?AUMETADATA_REC@CASFMetaDataObjectBase@@K@Z; CTDynArray<CASFMetaDataObjectBase::METADATA_REC,20>::operator[](ulong)
0x1800252e6  xor     r9d, r9d
0x1800252e9  movups  xmm2, xmmword ptr [rax]
0x1800252ec  movups  xmm6, xmmword ptr [rax+10h]
0x1800252f0  movq    rcx, xmm2
0x1800252f5  movdqa  xmm0, xmm2
0x1800252f9  mov     ebp, r9d
0x1800252fc  psrldq  xmm0, 4
0x180025301  pextrw  eax, xmm2, 1
0x180025306  mov     [rsi], ax
0x180025309  movd    dword ptr [r15], xmm0
0x18002530e  test    r12, r12
0x180025311  jz      short loc_180025318
0x180025313  mov     [r12], cx
0x180025318  psrldq  xmm2, 8
0x18002531d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180025321  movq    rdx, xmm2; Src
0x180025326  inc     rax
0x180025329  cmp     [rdx+rax*2], r9w
0x18002532e  jnz     short loc_180025326
0x180025330  mov     rdi, [rsp+98h+arg_28]
0x180025338  inc     ax
0x18002533b  mov     [r14], ax
0x18002533f  mov     ebx, 0C00D07D1h
0x180025344  test    rdi, rdi
0x180025347  jz      short loc_1800253C7
0x180025349  cmp     [rsp+98h+arg_20], ax
0x180025351  jnb     short loc_1800253AB
0x180025353  mov     ebp, ebx
0x180025355  jmp     short loc_1800253C7
0x180025357  mov     ebp, r9d
0x18002535a  movzx   r8d, bp
0x18002535e  cmp     r8d, [rbx+320h]
0x180025365  jnb     loc_180025411
0x18002536b  lea     rcx, [rbx+50h]
0x18002536f  lea     rdx, [rsp+98h+var_78]
0x180025374  call    ??A?$CTDynArray@UMETADATA_REC@CASFMetaDataObjectBase@@$0BE@@@QEBA?AUMETADATA_REC@CASFMetaDataObjectBase@@K@Z; CTDynArray<CASFMetaDataObjectBase::METADATA_REC,20>::operator[](ulong)
0x180025379  movups  xmm2, xmmword ptr [rax]
0x18002537c  movups  xmm6, xmmword ptr [rax+10h]
0x180025380  movq    rcx, xmm2
0x180025385  mov     rax, rcx
0x180025388  shr     rax, 10h
0x18002538c  cmp     ax, [rsi]
0x18002538f  jnz     short loc_1800253A6
0x180025391  xor     r9d, r9d
0x180025394  cmp     r9w, di
0x180025398  jz      loc_1800252F5
0x18002539e  mov     eax, 0FFFFh
0x1800253a3  add     di, ax
0x1800253a6  inc     bp
0x1800253a9  jmp     short loc_18002535A
0x1800253ab  movzx   r8d, ax
0x1800253af  mov     rcx, rdi; void *
0x1800253b2  add     r8, r8; Size
0x1800253b5  call    memcpy_0
0x1800253ba  movzx   ecx, word ptr [r14]
0x1800253be  xor     r9d, r9d
0x1800253c1  mov     [rdi+rcx*2-2], r9w
0x1800253c7  mov     rcx, [rsp+98h+arg_48]; void *
0x1800253cf  movd    eax, xmm6
0x1800253d3  mov     [r13+0], eax
0x1800253d7  test    rcx, rcx
0x1800253da  jz      short loc_180025400
0x1800253dc  cmp     ebp, ebx
0x1800253de  jz      short loc_180025416
0x1800253e0  cmp     [rsp+98h+arg_40], eax
0x1800253e7  jb      short loc_180025416
0x1800253e9  psrldq  xmm6, 8
0x1800253ee  movq    rdx, xmm6; Src
0x1800253f3  test    rdx, rdx
0x1800253f6  jz      short loc_180025400
0x1800253f8  mov     r8d, eax; Size
0x1800253fb  call    memcpy_0
0x180025400  lea     rcx, [rsp+98h+arg_0]; this
0x180025408  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18002540d  xor     eax, eax
0x18002540f  jmp     short loc_180025439
0x180025411  mov     ebx, 0C00D07F0h
0x180025416  lea     rcx, [rsp+98h+arg_0]; this
0x18002541e  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180025423  mov     eax, ebx
0x180025425  jmp     short loc_180025439
0x180025427  lea     rcx, [rsp+98h+arg_0]; this
0x18002542f  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180025434  mov     eax, 80070057h
0x180025439  movaps  xmm6, [rsp+98h+var_58]
0x18002543e  add     rsp, 58h
0x180025442  pop     r15
0x180025444  pop     r14
0x180025446  pop     r13
0x180025448  pop     r12
0x18002544a  pop     rdi
0x18002544b  pop     rsi
0x18002544c  pop     rbp
0x18002544d  pop     rbx
0x18002544e  retn
```
