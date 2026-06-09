# CAVICmpStream::ICCrunch(tagBITMAPINFOHEADER *,void *)

- ea: `0x18000d86c`
- end: `0x18000db79`
- name: `?ICCrunch@CAVICmpStream@@QEAAJPEAUtagBITMAPINFOHEADER@@PEAX@Z`
- size: `781`
- prototype: `int(CAVICmpStream *__hidden this, struct tagBITMAPINFOHEADER *, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000dc50`
- `0x18000e970`

## callees

- `0x180001460`
- `0x18000d86c`

## import_xrefs

- `MSVFW32!ICCompress` at `0x18000da18`
- `MSVFW32!ICCompress` at `0x18000da18`
- `MSVFW32!ICDecompress` at `0x18000db1c`
- `MSVFW32!ICDecompress` at `0x18000db1c`

## pseudocode

```c
__int64 __fastcall CAVICmpStream::ICCrunch(CAVICmpStream *this, struct tagBITMAPINFOHEADER *a2, void *a3)
{
  int v3; // r9d
  struct tagBITMAPINFOHEADER *lpbiInput; // r10
  DWORD dwQuality; // ebp
  unsigned int v7; // edi
  void *lpBits; // r11
  int v9; // ecx
  int v10; // edx
  int v11; // r8d
  _DWORD *v12; // rsi
  DWORD v13; // r13d
  DWORD dwFrameSize; // edi
  unsigned int v15; // r10d
  int v16; // r12d
  int v17; // ecx
  DWORD v18; // eax
  DWORD v19; // r15d
  DWORD v20; // r14d
  struct tagBITMAPINFOHEADER *lpbiPrev; // rax
  void *lpPrev; // rcx
  DWORD v23; // ecx
  DWORD v24; // edx
  int v25; // ecx
  DWORD v26; // ecx
  struct tagBITMAPINFOHEADER *v27; // rdx
  __int64 result; // rax
  int v29; // [rsp+70h] [rbp-68h]
  int v30; // [rsp+74h] [rbp-64h]
  int v31; // [rsp+7Ch] [rbp-5Ch]
  DWORD dwFlags; // [rsp+90h] [rbp-48h] BYREF
  DWORD ckid; // [rsp+94h] [rbp-44h] BYREF

  v3 = *((_DWORD *)this + 89);
  lpbiInput = a2;
  dwQuality = *((_DWORD *)this + 23);
  v7 = *((_DWORD *)this + 93);
  lpBits = a3;
  v9 = *((_DWORD *)this + 68);
  v10 = v3 & 0x20;
  v11 = 0;
  v30 = v10;
  v29 = 1;
  v12 = (_DWORD *)((char *)this + 348);
  if ( !v9 )
    goto LABEL_4;
  v13 = 0;
  if ( !*v12 )
  {
LABEL_14:
    if ( !v9 )
      goto LABEL_7;
    dwFrameSize = *((_DWORD *)this + 96) + v7;
    goto LABEL_16;
  }
  if ( v9 - *((_DWORD *)this + 95) >= *v12 )
LABEL_4:
    v13 = 1;
  if ( !*v12 )
    goto LABEL_14;
  if ( !v9 )
  {
LABEL_7:
    dwFrameSize = 0xFFFFFF;
    goto LABEL_17;
  }
  v15 = *((_DWORD *)this + 96);
  if ( v13 )
  {
    dwFrameSize = v15 + v7;
  }
  else
  {
    if ( v15 <= v7 )
      v11 = v7 / *v12;
    v10 = v3 & 0x20;
    dwFrameSize = (v11 + v15) / *v12 - v11 + v7;
    v11 = v15 + v11 - (v11 + v15) / *v12;
  }
  lpbiInput = a2;
LABEL_16:
  *((_DWORD *)this + 96) = v11;
  if ( !dwFrameSize )
  {
LABEL_18:
    v16 = 0;
    goto LABEL_19;
  }
LABEL_17:
  v16 = 1;
  if ( (v3 & 3) != 1 )
    goto LABEL_18;
LABEL_19:
  v17 = v13;
  v18 = 16 * v13;
  v19 = 0;
  v20 = dwQuality;
  if ( v10 )
    v17 = 1;
  v31 = v17;
  while ( 1 )
  {
    ckid = 0;
    dwFlags = v18;
    if ( v17 )
    {
      lpbiPrev = 0;
      lpPrev = 0;
    }
    else
    {
      lpbiPrev = (struct tagBITMAPINFOHEADER *)*((_QWORD *)this + 38);
      lpPrev = (void *)*((_QWORD *)this + 39);
    }
    v23 = ICCompress(
            *((HIC *)this + 35),
            v13,
            *((LPBITMAPINFOHEADER *)this + 36),
            *((LPVOID *)this + 37),
            lpbiInput,
            lpBits,
            &ckid,
            &dwFlags,
            *((_DWORD *)this + 68),
            dwFrameSize,
            dwQuality,
            lpbiPrev,
            lpPrev);
    if ( v23 )
      break;
    if ( !v16 )
      goto LABEL_40;
    v24 = *(_DWORD *)(*((_QWORD *)this + 36) + 20LL);
    if ( v24 <= dwFrameSize )
    {
      if ( v20 - dwQuality <= 0xA )
        goto LABEL_40;
      v25 = dwFrameSize >> 3;
      if ( dwFrameSize >> 3 > 0x200 )
        v25 = 512;
      if ( (int)(dwFrameSize - v24) <= v25 || v29 )
      {
LABEL_40:
        v26 = dwFlags;
        if ( (dwFlags & 0x10) != 0 )
          *((_DWORD *)this + 95) = *((_DWORD *)this + 68);
        *((_DWORD *)this + 94) = dwQuality;
        if ( *v12 != 1 )
        {
          v27 = (struct tagBITMAPINFOHEADER *)*((_QWORD *)this + 38);
          if ( v27 )
          {
            if ( !v30 )
            {
              ICDecompress(
                *((HIC *)this + 35),
                0,
                *((LPBITMAPINFOHEADER *)this + 36),
                *((LPVOID *)this + 37),
                v27,
                *((LPVOID *)this + 39));
              v26 = dwFlags;
            }
          }
        }
        *((_DWORD *)this + 97) = ckid;
        result = 0;
        *((_DWORD *)this + 98) = v26;
        return result;
      }
      v19 = dwQuality;
LABEL_34:
      dwQuality = (v20 + v19) >> 1;
      goto LABEL_35;
    }
    if ( v20 - v19 <= 1 )
      goto LABEL_40;
    v20 = dwQuality;
    if ( !v29 || dwQuality == *((_DWORD *)this + 94) )
      goto LABEL_34;
    dwQuality = *((_DWORD *)this + 94);
LABEL_35:
    v18 = 16 * v13;
    v17 = v31;
    lpbiInput = a2;
    lpBits = a3;
    v29 = 0;
  }
  result = 2147762280LL;
  if ( v23 == -2 )
    return 2147762278LL;
  return result;
}

```

## disassembly

```asm
0x18000d86c  mov     [rsp+arg_18], rbx
0x18000d871  push    rbp
0x18000d872  push    rsi
0x18000d873  push    rdi
0x18000d874  push    r12
0x18000d876  push    r13
0x18000d878  push    r14
0x18000d87a  push    r15
0x18000d87c  sub     rsp, 0A0h
0x18000d883  mov     rax, cs:__security_cookie
0x18000d88a  xor     rax, rsp
0x18000d88d  mov     [rsp+0D8h+var_40], rax
0x18000d895  mov     r9d, [rcx+164h]
0x18000d89c  mov     r10, rdx
0x18000d89f  mov     ebp, [rcx+5Ch]
0x18000d8a2  mov     rbx, rcx
0x18000d8a5  mov     edi, [rcx+174h]
0x18000d8ab  mov     r11, r8
0x18000d8ae  mov     ecx, [rcx+110h]
0x18000d8b4  mov     r14d, 1
0x18000d8ba  mov     [rsp+0D8h+var_58], rdx
0x18000d8c2  mov     edx, r9d
0x18000d8c5  and     edx, 20h
0x18000d8c8  mov     [rsp+0D8h+var_50], r8
0x18000d8d0  xor     r8d, r8d
0x18000d8d3  mov     [rsp+0D8h+var_64], edx
0x18000d8d7  mov     [rsp+0D8h+var_68], r14d
0x18000d8dc  lea     rsi, [rbx+15Ch]
0x18000d8e3  test    ecx, ecx
0x18000d8e5  jz      short loc_18000D8FB
0x18000d8e7  mov     r13d, r8d
0x18000d8ea  cmp     [rsi], r8d
0x18000d8ed  jz      short loc_18000D94F
0x18000d8ef  mov     eax, ecx
0x18000d8f1  sub     eax, [rbx+17Ch]
0x18000d8f7  cmp     eax, [rsi]
0x18000d8f9  jl      short loc_18000D8FE
0x18000d8fb  mov     r13d, r14d
0x18000d8fe  cmp     [rsi], r8d
0x18000d901  jbe     short loc_18000D94F
0x18000d903  test    ecx, ecx
0x18000d905  jnz     short loc_18000D90E
0x18000d907  mov     edi, 0FFFFFFh
0x18000d90c  jmp     short loc_18000D967
0x18000d90e  mov     r10d, [rbx+180h]
0x18000d915  test    r13d, r13d
0x18000d918  jz      short loc_18000D91F
0x18000d91a  add     edi, r10d
0x18000d91d  jmp     short loc_18000D945
0x18000d91f  xor     edx, edx
0x18000d921  mov     eax, edi
0x18000d923  div     dword ptr [rsi]
0x18000d925  cmp     r10d, edi
0x18000d928  cmovbe  r8d, eax
0x18000d92c  xor     edx, edx
0x18000d92e  lea     eax, [r8+r10]
0x18000d932  div     dword ptr [rsi]
0x18000d934  mov     edx, [rsp+0D8h+var_64]
0x18000d938  mov     ecx, eax
0x18000d93a  sub     ecx, r8d
0x18000d93d  sub     r8d, eax
0x18000d940  add     edi, ecx
0x18000d942  add     r8d, r10d
0x18000d945  mov     r10, [rsp+0D8h+var_58]
0x18000d94d  jmp     short loc_18000D959
0x18000d94f  test    ecx, ecx
0x18000d951  jz      short loc_18000D907
0x18000d953  add     edi, [rbx+180h]
0x18000d959  mov     [rbx+180h], r8d
0x18000d960  xor     r8d, r8d
0x18000d963  test    edi, edi
0x18000d965  jz      short loc_18000D973
0x18000d967  and     r9b, 3
0x18000d96b  mov     r12d, r14d
0x18000d96e  cmp     r9b, r14b
0x18000d971  jz      short loc_18000D976
0x18000d973  mov     r12d, r8d
0x18000d976  mov     eax, r13d
0x18000d979  mov     ecx, r13d
0x18000d97c  shl     eax, 4
0x18000d97f  mov     r15d, r8d
0x18000d982  test    edx, edx
0x18000d984  mov     [rsp+0D8h+var_60], eax
0x18000d988  mov     edx, 1
0x18000d98d  mov     r14d, ebp
0x18000d990  cmovnz  ecx, edx
0x18000d993  mov     [rsp+0D8h+var_5C], ecx
0x18000d997  mov     [rsp+0D8h+ckid], r8d
0x18000d99f  mov     [rsp+0D8h+dwFlags], eax
0x18000d9a6  test    ecx, ecx
0x18000d9a8  jz      short loc_18000D9B2
0x18000d9aa  mov     rax, r8
0x18000d9ad  mov     rcx, r8
0x18000d9b0  jmp     short loc_18000D9C0
0x18000d9b2  mov     rax, [rbx+130h]
0x18000d9b9  mov     rcx, [rbx+138h]
0x18000d9c0  mov     r9, [rbx+128h]; lpData
0x18000d9c7  mov     edx, r13d; dwFlags
0x18000d9ca  mov     r8, [rbx+120h]; lpbiOutput
0x18000d9d1  mov     [rsp+0D8h+lpPrev], rcx; lpPrev
0x18000d9d6  mov     rcx, [rbx+118h]; hic
0x18000d9dd  mov     [rsp+0D8h+lpbiPrev], rax; lpbiPrev
0x18000d9e2  mov     eax, [rbx+110h]
0x18000d9e8  mov     [rsp+0D8h+dwQuality], ebp; dwQuality
0x18000d9ec  mov     [rsp+0D8h+dwFrameSize], edi; dwFrameSize
0x18000d9f0  mov     [rsp+0D8h+lFrameNum], eax; lFrameNum
0x18000d9f4  lea     rax, [rsp+0D8h+dwFlags]
0x18000d9fc  mov     [rsp+0D8h+lpdwFlags], rax; lpdwFlags
0x18000da01  lea     rax, [rsp+0D8h+ckid]
0x18000da09  mov     [rsp+0D8h+lpckid], rax; lpckid
0x18000da0e  mov     [rsp+0D8h+lpBits], r11; lpBits
0x18000da13  mov     [rsp+0D8h+lpbiInput], r10; lpbiInput
0x18000da18  call    cs:__imp_ICCompress
0x18000da1e  xor     r8d, r8d
0x18000da21  mov     ecx, eax
0x18000da23  test    eax, eax
0x18000da25  jnz     loc_18000DB40
0x18000da2b  test    r12d, r12d
0x18000da2e  jz      loc_18000DABA
0x18000da34  mov     rax, [rbx+120h]
0x18000da3b  mov     edx, [rax+14h]
0x18000da3e  cmp     edx, edi
0x18000da40  ja      short loc_18000DA95
0x18000da42  mov     eax, r14d
0x18000da45  sub     eax, ebp
0x18000da47  cmp     eax, 0Ah
0x18000da4a  jbe     short loc_18000DABA
0x18000da4c  mov     eax, 200h
0x18000da51  mov     ecx, edi
0x18000da53  shr     ecx, 3
0x18000da56  cmp     ecx, eax
0x18000da58  cmova   ecx, eax
0x18000da5b  mov     eax, edi
0x18000da5d  sub     eax, edx
0x18000da5f  cmp     eax, ecx
0x18000da61  jle     short loc_18000DABA
0x18000da63  cmp     [rsp+0D8h+var_68], r8d
0x18000da68  jnz     short loc_18000DABA
0x18000da6a  mov     r15d, ebp
0x18000da6d  lea     ebp, [r14+r15]
0x18000da71  shr     ebp, 1
0x18000da73  mov     eax, [rsp+0D8h+var_60]
0x18000da77  mov     ecx, [rsp+0D8h+var_5C]
0x18000da7b  mov     r10, [rsp+0D8h+var_58]
0x18000da83  mov     r11, [rsp+0D8h+var_50]
0x18000da8b  mov     [rsp+0D8h+var_68], r8d
0x18000da90  jmp     loc_18000D997
0x18000da95  sub     r14d, r15d
0x18000da98  mov     edx, 1
0x18000da9d  cmp     r14d, edx
0x18000daa0  jbe     short loc_18000DABF
0x18000daa2  mov     r14d, ebp
0x18000daa5  cmp     [rsp+0D8h+var_68], r8d
0x18000daaa  jz      short loc_18000DA6D
0x18000daac  mov     eax, [rbx+178h]
0x18000dab2  cmp     ebp, eax
0x18000dab4  jz      short loc_18000DA6D
0x18000dab6  mov     ebp, eax
0x18000dab8  jmp     short loc_18000DA73
0x18000daba  mov     edx, 1
0x18000dabf  mov     ecx, [rsp+0D8h+dwFlags]
0x18000dac6  test    cl, 10h
0x18000dac9  jz      short loc_18000DAD7
0x18000dacb  mov     eax, [rbx+110h]
0x18000dad1  mov     [rbx+17Ch], eax
0x18000dad7  mov     [rbx+178h], ebp
0x18000dadd  cmp     [rsi], edx
0x18000dadf  jz      short loc_18000DB29
0x18000dae1  mov     rdx, [rbx+130h]
0x18000dae8  test    rdx, rdx
0x18000daeb  jz      short loc_18000DB29
0x18000daed  cmp     [rsp+0D8h+var_64], r8d
0x18000daf2  jnz     short loc_18000DB29
0x18000daf4  mov     rax, [rbx+138h]
0x18000dafb  mov     r9, [rbx+128h]; lpData
0x18000db02  mov     r8, [rbx+120h]; lpbiFormat
0x18000db09  mov     rcx, [rbx+118h]; hic
0x18000db10  mov     [rsp+0D8h+lpBits], rax; lpBits
0x18000db15  mov     [rsp+0D8h+lpbiInput], rdx; lpbi
0x18000db1a  xor     edx, edx; dwFlags
0x18000db1c  call    cs:__imp_ICDecompress
0x18000db22  mov     ecx, [rsp+0D8h+dwFlags]
0x18000db29  mov     eax, [rsp+0D8h+ckid]
0x18000db30  mov     [rbx+184h], eax
0x18000db36  xor     eax, eax
0x18000db38  mov     [rbx+188h], ecx
0x18000db3e  jmp     short loc_18000DB4E
0x18000db40  mov     eax, 80044068h
0x18000db45  cmp     ecx, 0FFFFFFFEh
0x18000db48  lea     edx, [rax-2]
0x18000db4b  cmovz   eax, edx
0x18000db4e  mov     rcx, [rsp+0D8h+var_40]
0x18000db56  xor     rcx, rsp; StackCookie
0x18000db59  call    __security_check_cookie
0x18000db5e  mov     rbx, [rsp+0D8h+arg_18]
0x18000db66  add     rsp, 0A0h
0x18000db6d  pop     r15
0x18000db6f  pop     r14
0x18000db71  pop     r13
0x18000db73  pop     r12
0x18000db75  pop     rdi
0x18000db76  pop     rsi
0x18000db77  pop     rbp
0x18000db78  retn
```
