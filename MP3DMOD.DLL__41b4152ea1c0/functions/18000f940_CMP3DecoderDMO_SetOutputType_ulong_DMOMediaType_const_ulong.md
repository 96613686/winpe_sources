# CMP3DecoderDMO::SetOutputType(ulong,_DMOMediaType const *,ulong)

- ea: `0x18000f940`
- end: `0x18000fb74`
- name: `?SetOutputType@CMP3DecoderDMO@@MEAAJKPEBU_DMOMediaType@@K@Z`
- size: `564`
- prototype: `__int64 __fastcall(CMP3DecoderDMO *this, int, const struct _DMOMediaType *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000f940`
- `0x1800114b1`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fb34`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fb4d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fb5a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fb34`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fb4d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fb5a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f964`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f964`
- `msdmo!MoFreeMediaType` at `0x18000f99c`
- `msdmo!MoFreeMediaType` at `0x18000fab9`
- `msdmo!MoFreeMediaType` at `0x18000f99c`
- `msdmo!MoFreeMediaType` at `0x18000fab9`
- `msdmo!MoCopyMediaType` at `0x18000fac6`
- `msdmo!MoCopyMediaType` at `0x18000fac6`

## pseudocode

```c
__int64 __fastcall CMP3DecoderDMO::SetOutputType(CMP3DecoderDMO *this, int a2, const struct _DMOMediaType *a3, char a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbp
  unsigned int v9; // ebx
  __int64 v10; // rax
  __int64 v11; // r8
  int v12; // edx
  unsigned int v13; // r10d
  int v14; // r9d
  __int64 v15; // r15
  unsigned int v16; // ecx
  HRESULT v17; // eax

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 200);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 5);
  if ( a2 )
  {
    v9 = -2147220991;
LABEL_36:
    LeaveCriticalSection(v4);
    return v9;
  }
  v9 = 0;
  if ( (a4 & 2) != 0 )
  {
    if ( *((_DWORD *)this + 3) )
    {
      if ( (a4 & 1) == 0 )
      {
        *((_DWORD *)this + 3) = 0;
        MoFreeMediaType((DMO_MEDIA_TYPE *)((char *)this + 104));
      }
    }
    else
    {
      v9 = 1;
    }
    goto LABEL_36;
  }
  if ( a3 && (!*((_DWORD *)a3 + 18) || *((_QWORD *)a3 + 10)) )
  {
    if ( !*((_DWORD *)this + 2) )
    {
      v9 = -2147220989;
      goto LABEL_36;
    }
    v10 = *(_QWORD *)((char *)a3 + 44) - *(_QWORD *)&FORMAT_WaveFormatEx.Data1;
    if ( !v10 )
      v10 = *(_QWORD *)((char *)a3 + 52) - *(_QWORD *)FORMAT_WaveFormatEx.Data4;
    if ( !v10 )
    {
      if ( *((_DWORD *)a3 + 18) < 0x12u )
        goto LABEL_34;
      v11 = *((_QWORD *)a3 + 10);
      v12 = *(_DWORD *)(v11 + 4);
      if ( !v12 )
        goto LABEL_34;
      v13 = *(unsigned __int16 *)(v11 + 2);
      if ( (unsigned __int16)(v13 - 1) <= 1u && ((*(_WORD *)(v11 + 14) - 8) & 0xFFE7) == 0 && *(_WORD *)(v11 + 14) != 24 )
      {
        v14 = *(unsigned __int16 *)(v11 + 12);
        if ( *(unsigned __int16 *)(v11 + 14) >> 3 << (v13 >> 1) == v14 && v12 * v14 == *(_DWORD *)(v11 + 8) )
        {
          v15 = *((_QWORD *)this + 12);
          if ( *(_WORD *)(v15 + 2) != 1 || (_WORD)v13 != 2 )
          {
            v16 = *(_DWORD *)(v15 + 4);
            if ( v12 == v16 || v12 == v16 >> 1 || v12 == v16 >> 2 )
            {
              if ( (a4 & 1) == 0 )
              {
                if ( *((_DWORD *)this + 3) )
                  MoFreeMediaType((DMO_MEDIA_TYPE *)((char *)this + 104));
                v17 = MoCopyMediaType((DMO_MEDIA_TYPE *)((char *)this + 104), (const DMO_MEDIA_TYPE *)a3);
                if ( v17 >= 0 )
                {
                  *((_DWORD *)this + 3) = 1;
                  *(_OWORD *)((char *)this + 458) = 0;
                  *(_OWORD *)((char *)this + 474) = 0;
                  *(_QWORD *)((char *)this + 490) = 0;
                  memcpy_0((char *)this + 458, *((const void **)a3 + 10), *((unsigned int *)a3 + 18));
                  *((_DWORD *)this + 128) = 2
                                          * ((*((unsigned __int16 *)this + 236)
                                            * (0x480
                                             / (unsigned int)(*(_DWORD *)(v15 + 4) / *(_DWORD *)((char *)this + 462)))) >> 3);
                  LeaveCriticalSection(v4);
                  return 0;
                }
                v9 = v17;
              }
              goto LABEL_36;
            }
          }
          goto LABEL_35;
        }
LABEL_34:
        v9 = -2147024809;
        goto LABEL_36;
      }
    }
LABEL_35:
    v9 = -2147220987;
    goto LABEL_36;
  }
  LeaveCriticalSection(v4);
  return 2147500035LL;
}

```

## disassembly

```asm
0x18000f940  push    rbx
0x18000f942  push    rbp
0x18000f943  push    rsi
0x18000f944  push    rdi
0x18000f945  push    r12
0x18000f947  push    r14
0x18000f949  push    r15
0x18000f94b  sub     rsp, 20h
0x18000f94f  lea     rbp, [rcx+0C8h]
0x18000f956  mov     rdi, rcx
0x18000f959  mov     rcx, rbp; lpCriticalSection
0x18000f95c  mov     r14d, r9d
0x18000f95f  mov     rsi, r8
0x18000f962  mov     ebx, edx
0x18000f964  call    cs:__imp_EnterCriticalSection
0x18000f96a  mov     r12d, 1
0x18000f970  cmp     ebx, r12d
0x18000f973  jb      short loc_18000F97F
0x18000f975  mov     ebx, 80040201h
0x18000f97a  jmp     loc_18000FB4A
0x18000f97f  xor     ebx, ebx
0x18000f981  test    r14b, 2
0x18000f985  jz      short loc_18000F9AF
0x18000f987  cmp     [rdi+0Ch], ebx
0x18000f98a  jz      short loc_18000F9A7
0x18000f98c  test    r12b, r14b
0x18000f98f  jnz     loc_18000FB4A
0x18000f995  lea     rcx, [rdi+68h]; pmt
0x18000f999  mov     [rdi+0Ch], ebx
0x18000f99c  call    cs:__imp_MoFreeMediaType
0x18000f9a2  jmp     loc_18000FB4A
0x18000f9a7  mov     ebx, r12d
0x18000f9aa  jmp     loc_18000FB4A
0x18000f9af  test    rsi, rsi
0x18000f9b2  jz      loc_18000FB57
0x18000f9b8  cmp     [rsi+48h], ebx
0x18000f9bb  jbe     short loc_18000F9C7
0x18000f9bd  cmp     [rsi+50h], rbx
0x18000f9c1  jz      loc_18000FB57
0x18000f9c7  cmp     [rdi+8], ebx
0x18000f9ca  jnz     short loc_18000F9D6
0x18000f9cc  mov     ebx, 80040203h
0x18000f9d1  jmp     loc_18000FB4A
0x18000f9d6  mov     rax, [rsi+2Ch]
0x18000f9da  sub     rax, qword ptr cs:FORMAT_WaveFormatEx.Data1
0x18000f9e1  jnz     short loc_18000F9EE
0x18000f9e3  mov     rax, [rsi+34h]
0x18000f9e7  sub     rax, qword ptr cs:FORMAT_WaveFormatEx.Data4
0x18000f9ee  test    rax, rax
0x18000f9f1  jnz     loc_18000FB45
0x18000f9f7  cmp     dword ptr [rsi+48h], 12h
0x18000f9fb  jb      loc_18000FB3E
0x18000fa01  mov     r8, [rsi+50h]
0x18000fa05  mov     edx, [r8+4]
0x18000fa09  test    edx, edx
0x18000fa0b  jz      loc_18000FB3E
0x18000fa11  movzx   r10d, word ptr [r8+2]
0x18000fa16  movzx   eax, r10w
0x18000fa1a  sub     ax, r12w
0x18000fa1e  cmp     ax, r12w
0x18000fa22  ja      loc_18000FB45
0x18000fa28  movzx   eax, word ptr [r8+0Eh]
0x18000fa2d  mov     ecx, 0FFE7h
0x18000fa32  sub     ax, 8
0x18000fa36  test    cx, ax
0x18000fa39  jnz     loc_18000FB45
0x18000fa3f  cmp     word ptr [r8+0Eh], 18h
0x18000fa45  jz      loc_18000FB45
0x18000fa4b  movzx   eax, word ptr [r8+0Eh]
0x18000fa50  mov     ecx, r10d
0x18000fa53  movzx   r9d, word ptr [r8+0Ch]
0x18000fa58  shr     eax, 3
0x18000fa5b  shr     ecx, 1
0x18000fa5d  shl     eax, cl
0x18000fa5f  cmp     eax, r9d
0x18000fa62  jnz     loc_18000FB3E
0x18000fa68  imul    r9d, edx
0x18000fa6c  cmp     r9d, [r8+8]
0x18000fa70  jnz     loc_18000FB3E
0x18000fa76  mov     r15, [rdi+60h]
0x18000fa7a  cmp     [r15+2], r12w
0x18000fa7f  jnz     short loc_18000FA8C
0x18000fa81  cmp     r10w, 2
0x18000fa86  jz      loc_18000FB45
0x18000fa8c  mov     ecx, [r15+4]
0x18000fa90  cmp     edx, ecx
0x18000fa92  jz      short loc_18000FAA7
0x18000fa94  mov     eax, ecx
0x18000fa96  shr     eax, 1
0x18000fa98  cmp     edx, eax
0x18000fa9a  jz      short loc_18000FAA7
0x18000fa9c  shr     ecx, 2
0x18000fa9f  cmp     edx, ecx
0x18000faa1  jnz     loc_18000FB45
0x18000faa7  test    r12b, r14b
0x18000faaa  jnz     loc_18000FB4A
0x18000fab0  cmp     [rdi+0Ch], ebx
0x18000fab3  jz      short loc_18000FABF
0x18000fab5  lea     rcx, [rdi+68h]; pmt
0x18000fab9  call    cs:__imp_MoFreeMediaType
0x18000fabf  mov     rdx, rsi; pmtSrc
0x18000fac2  lea     rcx, [rdi+68h]; pmtDest
0x18000fac6  call    cs:__imp_MoCopyMediaType
0x18000facc  test    eax, eax
0x18000face  jns     short loc_18000FAD4
0x18000fad0  mov     ebx, eax
0x18000fad2  jmp     short loc_18000FB4A
0x18000fad4  mov     [rdi+0Ch], r12d
0x18000fad8  lea     rcx, [rdi+1CAh]; void *
0x18000fadf  xorps   xmm0, xmm0
0x18000fae2  xor     eax, eax
0x18000fae4  movups  xmmword ptr [rcx], xmm0
0x18000fae7  movups  xmmword ptr [rcx+10h], xmm0
0x18000faeb  mov     [rcx+20h], rax
0x18000faef  mov     r8d, [rsi+48h]; Size
0x18000faf3  mov     rdx, [rsi+50h]; Src
0x18000faf7  call    memcpy_0
0x18000fafc  mov     eax, [r15+4]
0x18000fb00  xor     edx, edx
0x18000fb02  div     dword ptr [rdi+1CEh]
0x18000fb08  xor     edx, edx
0x18000fb0a  mov     rcx, rbp; lpCriticalSection
0x18000fb0d  mov     r8d, eax
0x18000fb10  mov     eax, 480h
0x18000fb15  div     r8d
0x18000fb18  mov     r8d, eax
0x18000fb1b  movzx   eax, word ptr [rdi+1D8h]
0x18000fb22  imul    r8d, eax
0x18000fb26  shr     r8d, 3
0x18000fb2a  add     r8d, r8d
0x18000fb2d  mov     [rdi+200h], r8d
0x18000fb34  call    cs:__imp_LeaveCriticalSection
0x18000fb3a  xor     eax, eax
0x18000fb3c  jmp     short loc_18000FB65
0x18000fb3e  mov     ebx, 80070057h
0x18000fb43  jmp     short loc_18000FB4A
0x18000fb45  mov     ebx, 80040205h
0x18000fb4a  mov     rcx, rbp; lpCriticalSection
0x18000fb4d  call    cs:__imp_LeaveCriticalSection
0x18000fb53  mov     eax, ebx
0x18000fb55  jmp     short loc_18000FB65
0x18000fb57  mov     rcx, rbp; lpCriticalSection
0x18000fb5a  call    cs:__imp_LeaveCriticalSection
0x18000fb60  mov     eax, 80004003h
0x18000fb65  add     rsp, 20h
0x18000fb69  pop     r15
0x18000fb6b  pop     r14
0x18000fb6d  pop     r12
0x18000fb6f  pop     rdi
0x18000fb70  pop     rsi
0x18000fb71  pop     rbp
0x18000fb72  pop     rbx
0x18000fb73  retn
```
