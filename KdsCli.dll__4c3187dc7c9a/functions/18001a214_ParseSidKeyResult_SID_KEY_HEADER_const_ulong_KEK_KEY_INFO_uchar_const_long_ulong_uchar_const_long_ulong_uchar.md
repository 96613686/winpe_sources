# ParseSidKeyResult(_SID_KEY_HEADER const *,ulong,_KEK_KEY_INFO *,uchar * const,long *,ulong *,uchar * const,long *,ulong *,uchar * *)

- ea: `0x18001a214`
- end: `0x18001a448`
- name: `?ParseSidKeyResult@@YAJPEBU_SID_KEY_HEADER@@KPEAU_KEK_KEY_INFO@@QEAEPEAJPEAK234PEAPEAE@Z`
- size: `564`
- prototype: `__int64 __fastcall(const struct _SID_KEY_HEADER *, unsigned int, struct _KEK_KEY_INFO *, unsigned __int8 *const, int *, unsigned int *, unsigned __int8 *const, int *, unsigned int *, unsigned __int8 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180016b30`
- `0x180018c7c`

## callees

- `0x180010a94`
- `0x18001a214`
- `0x18001a450`

## string_xrefs

- `0x18001a252`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyrpcclient.cxx`

## pseudocode

```c
__int64 __fastcall ParseSidKeyResult(
        const struct _SID_KEY_HEADER *a1,
        unsigned int a2,
        struct _KEK_KEY_INFO *a3,
        unsigned __int8 *const a4,
        int *a5,
        unsigned int *a6,
        unsigned __int8 *const a7,
        int *a8,
        unsigned int *a9,
        unsigned __int8 **a10)
{
  int v11; // ebp
  int v14; // esi
  unsigned __int8 *v15; // r15
  int v16; // eax
  unsigned int v17; // r14d
  unsigned int v18; // r9d
  unsigned int v19; // ecx
  unsigned int v20; // eax
  int v21; // eax
  unsigned int v22; // edx
  __int64 v23; // rax
  char *v24; // rdx
  __int64 v25; // rcx
  char *v26; // rdx

  v11 = 0;
  v14 = 0;
  v15 = 0;
  v16 = ValidateSIDKey(a1, a2, 1);
  v17 = v16;
  if ( v16 < 0 )
  {
    v18 = 335;
    v19 = v16;
LABEL_3:
    SidKeyDebugTraceError(v19, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyrpcclient.cxx", v18);
    goto LABEL_32;
  }
  if ( a3 )
  {
    if ( *((_QWORD *)a3 + 3) != *((_QWORD *)a1 + 3)
      || *((_QWORD *)a3 + 4) != *((_QWORD *)a1 + 4)
      || (*((_BYTE *)a1 + 8) & 1) != 0
      || *((_DWORD *)a3 + 3) != *((_DWORD *)a1 + 3)
      || (v20 = *((_DWORD *)a3 + 4), v20 > *((_DWORD *)a1 + 4))
      || v20 == *((_DWORD *)a1 + 4) && *((_DWORD *)a3 + 5) > *((_DWORD *)a1 + 5) )
    {
      v17 = -2146893821;
      v18 = 349;
      v19 = -2146893821;
      goto LABEL_3;
    }
  }
  v21 = *((_DWORD *)a1 + 17);
  if ( a3 )
  {
    if ( v21 )
    {
      v22 = *((_DWORD *)a1 + 4);
      v11 = v22 + ~*((_DWORD *)a3 + 4);
      if ( v11 > 0 )
        *a6 = v22 - 2;
      if ( v22 <= *((_DWORD *)a3 + 4) )
      {
        v14 = *((_DWORD *)a1 + 5) - *((_DWORD *)a3 + 5);
        if ( v14 > 0 )
          *a9 = *((_DWORD *)a1 + 5) - 1;
        goto LABEL_26;
      }
    }
    else
    {
      v11 = *((_DWORD *)a1 + 4) - *((_DWORD *)a3 + 4);
      if ( v11 > 0 )
        *a6 = *((_DWORD *)a1 + 4) - 1;
    }
    v14 = 32 - *((_DWORD *)a3 + 5);
  }
  else
  {
    if ( v21 )
      goto LABEL_26;
    v14 = 1;
  }
  *a9 = 31;
LABEL_26:
  if ( (*((_BYTE *)a1 + 8) & 1) != 0 )
  {
    v15 = (unsigned __int8 *)a1
        + *((unsigned int *)a1 + 10)
        + *((unsigned int *)a1 + 11)
        + *((unsigned int *)a1 + 12)
        + *((unsigned int *)a1 + 13)
        + *((unsigned int *)a1 + 18)
        + (unsigned __int64)*((unsigned int *)a1 + 19)
        + *((unsigned int *)a1 + 16)
        + 80;
  }
  else
  {
    if ( *((_DWORD *)a1 + 16) )
    {
      v23 = *((unsigned int *)a1 + 10);
      v24 = (char *)a1
          + *((unsigned int *)a1 + 18)
          + *((unsigned int *)a1 + 19)
          + *((unsigned int *)a1 + 13)
          + *((unsigned int *)a1 + 12)
          + (unsigned __int64)*((unsigned int *)a1 + 11);
      *(_OWORD *)a4 = *(_OWORD *)&v24[v23 + 80];
      *((_OWORD *)a4 + 1) = *(_OWORD *)&v24[v23 + 96];
      *((_OWORD *)a4 + 2) = *(_OWORD *)&v24[v23 + 112];
      *((_OWORD *)a4 + 3) = *(_OWORD *)&v24[v23 + 128];
    }
    if ( *((_DWORD *)a1 + 17) )
    {
      v25 = *((unsigned int *)a1 + 12);
      v26 = (char *)a1
          + *((unsigned int *)a1 + 13)
          + *((unsigned int *)a1 + 10)
          + *((unsigned int *)a1 + 16)
          + *((unsigned int *)a1 + 19)
          + *((unsigned int *)a1 + 11)
          + (unsigned __int64)*((unsigned int *)a1 + 18);
      *(_OWORD *)a7 = *(_OWORD *)&v26[v25 + 80];
      *((_OWORD *)a7 + 1) = *(_OWORD *)&v26[v25 + 96];
      *((_OWORD *)a7 + 2) = *(_OWORD *)&v26[v25 + 112];
      *((_OWORD *)a7 + 3) = *(_OWORD *)&v26[v25 + 128];
    }
  }
LABEL_32:
  *a5 = v11;
  *a8 = v14;
  *a10 = v15;
  return v17;
}

```

## disassembly

```asm
0x18001a214  push    rbx
0x18001a216  push    rbp
0x18001a217  push    rsi
0x18001a218  push    rdi
0x18001a219  push    r12
0x18001a21b  push    r14
0x18001a21d  push    r15
0x18001a21f  sub     rsp, 20h
0x18001a223  mov     rdi, r8
0x18001a226  xor     ebp, ebp
0x18001a228  mov     r12, r9
0x18001a22b  mov     rbx, rcx
0x18001a22e  xor     esi, esi
0x18001a230  xor     r15d, r15d
0x18001a233  lea     r8d, [rbp+1]; int
0x18001a237  call    ?ValidateSIDKey@@YAJPEBU_SID_KEY_HEADER@@KH@Z; ValidateSIDKey(_SID_KEY_HEADER const *,ulong,int)
0x18001a23c  mov     r14d, eax
0x18001a23f  test    eax, eax
0x18001a241  jns     short loc_18001A263
0x18001a243  mov     r9d, 14Fh; unsigned int
0x18001a249  mov     ecx, eax; unsigned int
0x18001a24b  lea     rdx, aHr; "hr"
0x18001a252  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18001a259  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18001a25e  jmp     loc_18001A417
0x18001a263  test    rdi, rdi
0x18001a266  jz      short loc_18001A2AF
0x18001a268  mov     rax, [rdi+18h]
0x18001a26c  cmp     rax, [rbx+18h]
0x18001a270  jnz     short loc_18001A29C
0x18001a272  mov     rax, [rdi+20h]
0x18001a276  cmp     rax, [rbx+20h]
0x18001a27a  jnz     short loc_18001A29C
0x18001a27c  test    byte ptr [rbx+8], 1
0x18001a280  jnz     short loc_18001A29C
0x18001a282  mov     eax, [rbx+0Ch]
0x18001a285  cmp     [rdi+0Ch], eax
0x18001a288  jnz     short loc_18001A29C
0x18001a28a  mov     eax, [rdi+10h]
0x18001a28d  cmp     eax, [rbx+10h]
0x18001a290  ja      short loc_18001A29C
0x18001a292  jnz     short loc_18001A2AF
0x18001a294  mov     eax, [rbx+14h]
0x18001a297  cmp     [rdi+14h], eax
0x18001a29a  jbe     short loc_18001A2AF
0x18001a29c  mov     r14d, 80090003h
0x18001a2a2  mov     r9d, 15Dh
0x18001a2a8  mov     ecx, 80090003h
0x18001a2ad  jmp     short loc_18001A24B
0x18001a2af  mov     eax, [rbx+44h]
0x18001a2b2  test    rdi, rdi
0x18001a2b5  jz      short loc_18001A317
0x18001a2b7  test    eax, eax
0x18001a2b9  jnz     short loc_18001A2DD
0x18001a2bb  mov     ecx, [rbx+10h]
0x18001a2be  mov     ebp, ecx
0x18001a2c0  sub     ebp, [rdi+10h]
0x18001a2c3  test    ebp, ebp
0x18001a2c5  jle     short loc_18001A2D3
0x18001a2c7  mov     rax, [rsp+58h+arg_28]
0x18001a2cf  dec     ecx
0x18001a2d1  mov     [rax], ecx
0x18001a2d3  mov     esi, 20h ; ' '
0x18001a2d8  sub     esi, [rdi+14h]
0x18001a2db  jmp     short loc_18001A31E
0x18001a2dd  mov     ebp, [rdi+10h]
0x18001a2e0  mov     edx, [rbx+10h]
0x18001a2e3  not     ebp
0x18001a2e5  add     ebp, edx
0x18001a2e7  test    ebp, ebp
0x18001a2e9  jle     short loc_18001A2F8
0x18001a2eb  mov     rax, [rsp+58h+arg_28]
0x18001a2f3  lea     ecx, [rdx-2]
0x18001a2f6  mov     [rax], ecx
0x18001a2f8  cmp     edx, [rdi+10h]
0x18001a2fb  ja      short loc_18001A2D3
0x18001a2fd  mov     ecx, [rbx+14h]
0x18001a300  mov     esi, ecx
0x18001a302  sub     esi, [rdi+14h]
0x18001a305  test    esi, esi
0x18001a307  jle     short loc_18001A32C
0x18001a309  mov     rax, [rsp+58h+arg_40]
0x18001a311  dec     ecx
0x18001a313  mov     [rax], ecx
0x18001a315  jmp     short loc_18001A32C
0x18001a317  test    eax, eax
0x18001a319  jnz     short loc_18001A32C
0x18001a31b  lea     esi, [rax+1]
0x18001a31e  mov     rax, [rsp+58h+arg_40]
0x18001a326  mov     dword ptr [rax], 1Fh
0x18001a32c  test    byte ptr [rbx+8], 1
0x18001a330  jz      short loc_18001A366
0x18001a332  mov     eax, [rbx+48h]
0x18001a335  mov     edx, [rbx+4Ch]
0x18001a338  mov     r15d, [rbx+28h]
0x18001a33c  add     rdx, rax
0x18001a33f  mov     eax, [rbx+34h]
0x18001a342  add     r15, rbx
0x18001a345  add     rdx, rax
0x18001a348  mov     eax, [rbx+30h]
0x18001a34b  add     rdx, rax
0x18001a34e  mov     eax, [rbx+2Ch]
0x18001a351  add     rdx, rax
0x18001a354  mov     eax, [rbx+40h]
0x18001a357  add     rax, 50h ; 'P'
0x18001a35b  add     r15, rdx
0x18001a35e  add     r15, rax
0x18001a361  jmp     loc_18001A417
0x18001a366  cmp     [rbx+40h], r15d
0x18001a36a  jz      short loc_18001A3BB
0x18001a36c  mov     eax, [rbx+30h]
0x18001a36f  mov     ecx, [rbx+2Ch]
0x18001a372  mov     edx, [rbx+48h]
0x18001a375  add     rcx, rax
0x18001a378  mov     eax, [rbx+34h]
0x18001a37b  add     rdx, rbx
0x18001a37e  add     rcx, rax
0x18001a381  mov     eax, [rbx+4Ch]
0x18001a384  add     rcx, rax
0x18001a387  mov     eax, [rbx+28h]
0x18001a38a  add     rdx, rcx
0x18001a38d  movups  xmm0, xmmword ptr [rax+rdx+50h]
0x18001a392  movaps  xmmword ptr [r12], xmm0
0x18001a397  movups  xmm1, xmmword ptr [rax+rdx+60h]
0x18001a39c  movaps  xmmword ptr [r12+10h], xmm1
0x18001a3a2  movups  xmm0, xmmword ptr [rax+rdx+70h]
0x18001a3a7  movaps  xmmword ptr [r12+20h], xmm0
0x18001a3ad  movups  xmm1, xmmword ptr [rax+rdx+80h]
0x18001a3b5  movaps  xmmword ptr [r12+30h], xmm1
0x18001a3bb  cmp     [rbx+44h], r15d
0x18001a3bf  jz      short loc_18001A417
0x18001a3c1  mov     ecx, [rbx+30h]
0x18001a3c4  mov     eax, [rbx+2Ch]
0x18001a3c7  mov     r8d, [rbx+48h]
0x18001a3cb  mov     edx, [rbx+34h]
0x18001a3ce  add     r8, rax
0x18001a3d1  mov     eax, [rbx+4Ch]
0x18001a3d4  add     rdx, rbx
0x18001a3d7  add     r8, rax
0x18001a3da  mov     eax, [rbx+40h]
0x18001a3dd  add     r8, rax
0x18001a3e0  mov     eax, [rbx+28h]
0x18001a3e3  add     r8, rax
0x18001a3e6  mov     rax, [rsp+58h+arg_30]
0x18001a3ee  add     rdx, r8
0x18001a3f1  movups  xmm0, xmmword ptr [rcx+rdx+50h]
0x18001a3f6  movaps  xmmword ptr [rax], xmm0
0x18001a3f9  movups  xmm1, xmmword ptr [rcx+rdx+60h]
0x18001a3fe  movaps  xmmword ptr [rax+10h], xmm1
0x18001a402  movups  xmm0, xmmword ptr [rcx+rdx+70h]
0x18001a407  movaps  xmmword ptr [rax+20h], xmm0
0x18001a40b  movups  xmm1, xmmword ptr [rcx+rdx+80h]
0x18001a413  movaps  xmmword ptr [rax+30h], xmm1
0x18001a417  mov     rax, [rsp+58h+arg_20]
0x18001a41f  mov     [rax], ebp
0x18001a421  mov     rax, [rsp+58h+arg_38]
0x18001a429  mov     [rax], esi
0x18001a42b  mov     rax, [rsp+58h+arg_48]
0x18001a433  mov     [rax], r15
0x18001a436  mov     eax, r14d
0x18001a439  add     rsp, 20h
0x18001a43d  pop     r15
0x18001a43f  pop     r14
0x18001a441  pop     r12
0x18001a443  pop     rdi
0x18001a444  pop     rsi
0x18001a445  pop     rbp
0x18001a446  pop     rbx
0x18001a447  retn
```
