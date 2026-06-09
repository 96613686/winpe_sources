# _CacheOrUploadOnBoxRequestFailure

- ea: `0x18004a1bc`
- end: `0x18004a596`
- name: `_CacheOrUploadOnBoxRequestFailure`
- size: `986`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180048fe0`
- `0x18004b394`
- `0x18004b464`

## callees

- `0x180001300`
- `0x1800026b0`
- `0x18000316c`
- `0x18004a1bc`
- `0x18004b84c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004a25d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004a25d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a21d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a21d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a570`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a570`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004a376`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004a376`

## pseudocode

```c
void __fastcall CacheOrUploadOnBoxRequestFailure(CloudSettings *a1, int a2, unsigned __int64 a3, int a4, char a5)
{
  CloudSettings *v7; // rsi
  unsigned int v9; // r14d
  unsigned __int8 v10; // di
  __int64 *v11; // rbx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 *v14; // rax
  __int64 *v15; // rcx
  __int64 v16; // r8
  unsigned int v17; // edx
  __int64 *v18; // rcx
  ULONGLONG TickCount64; // rax
  unsigned __int8 v20; // dl
  __int64 v21; // r14
  unsigned __int8 v22; // di
  unsigned __int8 v23; // si
  __int64 *v24; // rbx
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rax
  int v28; // [rsp+30h] [rbp-D0h] BYREF
  int v29; // [rsp+34h] [rbp-CCh] BYREF
  int v30; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v31; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v32; // [rsp+48h] [rbp-B8h] BYREF
  ULONGLONG v33; // [rsp+50h] [rbp-B0h]
  struct _EVENT_DATA_DESCRIPTOR v34; // [rsp+60h] [rbp-A0h] BYREF
  __int16 *v35; // [rsp+80h] [rbp-80h]
  int v36; // [rsp+88h] [rbp-78h]
  int v37; // [rsp+8Ch] [rbp-74h]
  __int64 *v38; // [rsp+90h] [rbp-70h]
  int v39; // [rsp+98h] [rbp-68h]
  int v40; // [rsp+9Ch] [rbp-64h]
  int *v41; // [rsp+A0h] [rbp-60h]
  __int64 v42; // [rsp+A8h] [rbp-58h]
  __int64 *v43; // [rsp+B0h] [rbp-50h]
  __int64 v44; // [rsp+B8h] [rbp-48h]
  __int64 *v45; // [rsp+C0h] [rbp-40h]
  __int64 v46; // [rsp+C8h] [rbp-38h]
  int *v47; // [rsp+D0h] [rbp-30h]
  __int64 v48; // [rsp+D8h] [rbp-28h]
  int *v49; // [rsp+E0h] [rbp-20h]
  __int64 v50; // [rsp+E8h] [rbp-18h]
  const wchar_t *v51; // [rsp+F0h] [rbp-10h]
  __int64 v52; // [rsp+F8h] [rbp-8h]

  v28 = a4;
  v7 = a1;
  if ( !byte_180066498 )
    return;
  if ( (*(_BYTE *)CloudSettings::GetCloudSettingsSnapshot(a1) & 2) == 0 )
  {
    byte_18006649A = 0;
    return;
  }
  EnterCriticalSection(&stru_180066690);
  if ( v7 )
  {
    v9 = 0;
    v10 = byte_18006649A;
    if ( byte_18006649A )
    {
      while ( 1 )
      {
        v11 = &qword_18007D7B0[105 * v9];
        if ( !(unsigned int)_o__wcsicmp(v11, v7) )
          break;
        v10 = byte_18006649A;
        if ( ++v9 >= (unsigned __int8)byte_18006649A )
          goto LABEL_11;
      }
      if ( v11 )
        goto LABEL_18;
      v10 = byte_18006649A;
    }
LABEL_11:
    v11 = &qword_18007D7B0[105 * v10];
    memset_0(v11, 0, 0x348u);
    v12 = 2147483646;
    v13 = 256;
    v14 = v11;
    do
    {
      if ( !v12 )
        break;
      if ( !*(_WORD *)v7 )
        break;
      *(_WORD *)v14 = *(_WORD *)v7;
      v7 = (CloudSettings *)((char *)v7 + 2);
      v14 = (__int64 *)((char *)v14 + 2);
      --v12;
      --v13;
    }
    while ( v13 );
    v15 = (__int64 *)((char *)v14 - 2);
    if ( v13 )
      v15 = v14;
    byte_18006649A = v10 + 1;
    *(_WORD *)v15 = 0;
LABEL_18:
    v16 = *((unsigned __int8 *)v11 + 832);
    v17 = 0;
    if ( *((_BYTE *)v11 + 832) )
    {
      while ( 1 )
      {
        v18 = &v11[4 * v17 + 64];
        if ( *(_DWORD *)v18 == a2 )
          break;
        if ( (int)++v17 >= (int)v16 )
          goto LABEL_21;
      }
    }
    else
    {
LABEL_21:
      v18 = &v11[4 * v16 + 64];
      *(__int64 *)((char *)v18 + 4) = 0;
      *((_DWORD *)v18 + 3) = 0;
      v18[3] = 0;
      *(_DWORD *)v18 = a2;
      v18[2] = a3;
      if ( ++*((_BYTE *)v11 + 832) == 10 )
        a5 = 1;
    }
    *((_DWORD *)v18 + 6) |= v28;
    ++*((_DWORD *)v18 + 1);
    v18[1] += a3;
    if ( a3 < v18[2] )
      v18[2] = a3;
  }
  TickCount64 = GetTickCount64();
  v20 = byte_18006649A;
  v21 = TickCount64;
  v33 = TickCount64;
  if ( TickCount64 - qword_180066728 >= 0x493E0 || byte_18006649A == 10 || a5 )
  {
    v22 = 0;
    if ( byte_18006649A )
    {
      do
      {
        v23 = 0;
        v24 = &qword_18007D7B0[105 * v22];
        if ( *((_BYTE *)v24 + 832) )
        {
          do
          {
            if ( (unsigned int)dword_1800652E8 > 5
              && (qword_1800652F8 & 0x400000000000LL) != 0
              && (qword_180065300 & 0x400000000000LL) == qword_180065300 )
            {
              v25 = 4 * (v23 + 16LL);
              v28 = v24[v25 + 3];
              v29 = HIDWORD(v24[v25]);
              v31 = v24[v25 + 2];
              v32 = v24[v25 + 1];
              v30 = v24[v25];
              v51 = L"3.2";
              v49 = &v28;
              v47 = &v29;
              v45 = &v31;
              v43 = &v32;
              v41 = &v30;
              v26 = -1;
              v52 = 8;
              v50 = 4;
              v48 = 4;
              v46 = 8;
              v44 = 8;
              v42 = 4;
              do
                ++v26;
              while ( *((_WORD *)v24 + v26) );
              v38 = &qword_18007D7B0[105 * v22];
              v39 = 2 * v26 + 2;
              v27 = -1;
              v40 = 0;
              do
                ++v27;
              while ( word_1800666C0[v27] );
              v35 = word_1800666C0;
              v36 = 2 * v27 + 2;
              v37 = 0;
              tlgWriteTransfer_EventWriteTransfer(
                (__int64)&dword_1800652E8,
                (unsigned __int8 *)byte_18005B88D,
                0,
                0,
                0xAu,
                &v34);
            }
            ++v23;
          }
          while ( v23 < *((_BYTE *)v24 + 832) );
          v20 = byte_18006649A;
        }
        ++v22;
      }
      while ( v22 < v20 );
      v21 = v33;
    }
    qword_180066728 = v21;
    byte_18006649A = 0;
  }
  LeaveCriticalSection(&stru_180066690);
}

```

## disassembly

```asm
0x18004a1bc  push    rbp
0x18004a1be  push    rbx
0x18004a1bf  push    rsi
0x18004a1c0  push    rdi
0x18004a1c1  push    r12
0x18004a1c3  push    r13
0x18004a1c5  push    r14
0x18004a1c7  push    r15
0x18004a1c9  lea     rbp, [rsp-18h]
0x18004a1ce  sub     rsp, 118h
0x18004a1d5  mov     rax, cs:__security_cookie
0x18004a1dc  xor     rax, rsp
0x18004a1df  mov     [rbp+50h+var_50], rax
0x18004a1e3  xor     edi, edi
0x18004a1e5  mov     [rsp+150h+var_120], r9d
0x18004a1ea  cmp     cs:byte_180066498, dil
0x18004a1f1  mov     r15, r8
0x18004a1f4  mov     r13d, edx
0x18004a1f7  mov     rsi, rcx
0x18004a1fa  jz      loc_18004A576
0x18004a200  call    ?GetCloudSettingsSnapshot@CloudSettings@@QEAAAEBUWinHttpSettings@@XZ; CloudSettings::GetCloudSettingsSnapshot(void)
0x18004a205  test    byte ptr [rax], 2
0x18004a208  jnz     short loc_18004A216
0x18004a20a  mov     cs:byte_18006649A, dil
0x18004a211  jmp     loc_18004A576
0x18004a216  lea     rcx, stru_180066690; lpCriticalSection
0x18004a21d  call    cs:__imp_EnterCriticalSection
0x18004a223  movzx   r12d, [rbp+50h+arg_20]
0x18004a22b  test    rsi, rsi
0x18004a22e  jz      loc_18004A376
0x18004a234  mov     r14d, edi
0x18004a237  mov     dil, cs:byte_18006649A
0x18004a23e  test    dil, dil
0x18004a241  jz      short loc_18004A28E
0x18004a243  mov     eax, r14d
0x18004a246  mov     rdx, rsi
0x18004a249  imul    rbx, rax, 348h
0x18004a250  lea     rax, qword_18007D7B0
0x18004a257  add     rbx, rax
0x18004a25a  mov     rcx, rbx
0x18004a25d  call    cs:__imp__o__wcsicmp
0x18004a263  xor     edi, edi
0x18004a265  test    eax, eax
0x18004a267  jz      short loc_18004A27A
0x18004a269  movzx   edi, cs:byte_18006649A
0x18004a270  inc     r14d
0x18004a273  cmp     r14d, edi
0x18004a276  jb      short loc_18004A243
0x18004a278  jmp     short loc_18004A28E
0x18004a27a  test    rbx, rbx
0x18004a27d  jz      short loc_18004A287
0x18004a27f  mov     r10d, 1
0x18004a285  jmp     short loc_18004A305
0x18004a287  mov     dil, cs:byte_18006649A
0x18004a28e  movzx   eax, dil
0x18004a292  xor     edx, edx; Val
0x18004a294  imul    rbx, rax, 348h
0x18004a29b  lea     rax, qword_18007D7B0
0x18004a2a2  mov     r8d, 348h; Size
0x18004a2a8  add     rbx, rax
0x18004a2ab  mov     rcx, rbx; void *
0x18004a2ae  call    memset_0
0x18004a2b3  xor     r9d, r9d
0x18004a2b6  mov     ecx, 7FFFFFFEh
0x18004a2bb  mov     edx, 100h
0x18004a2c0  mov     rax, rbx
0x18004a2c3  lea     r10d, [r9+1]
0x18004a2c7  test    rcx, rcx
0x18004a2ca  jz      short loc_18004A2EA
0x18004a2cc  movzx   r8d, word ptr [rsi]
0x18004a2d0  test    r8w, r8w
0x18004a2d4  jz      short loc_18004A2EA
0x18004a2d6  mov     [rax], r8w
0x18004a2da  add     rsi, 2
0x18004a2de  add     rax, 2
0x18004a2e2  sub     rcx, r10
0x18004a2e5  sub     rdx, r10
0x18004a2e8  jnz     short loc_18004A2C7
0x18004a2ea  test    rdx, rdx
0x18004a2ed  lea     rcx, [rax-2]
0x18004a2f1  cmovnz  rcx, rax
0x18004a2f5  add     dil, r10b
0x18004a2f8  mov     cs:byte_18006649A, dil
0x18004a2ff  xor     edi, edi
0x18004a301  mov     [rcx], r9w
0x18004a305  movzx   r8d, byte ptr [rbx+340h]
0x18004a30d  mov     edx, edi
0x18004a30f  test    r8d, r8d
0x18004a312  jz      short loc_18004A32E
0x18004a314  mov     ecx, edx
0x18004a316  add     rcx, 10h
0x18004a31a  shl     rcx, 5
0x18004a31e  add     rcx, rbx
0x18004a321  cmp     [rcx], r13d
0x18004a324  jz      short loc_18004A35D
0x18004a326  add     edx, r10d
0x18004a329  cmp     edx, r8d
0x18004a32c  jl      short loc_18004A314
0x18004a32e  lea     rcx, [r8+10h]
0x18004a332  shl     rcx, 5
0x18004a336  add     rcx, rbx
0x18004a339  mov     [rcx+4], rdi
0x18004a33d  mov     [rcx+0Ch], edi
0x18004a340  mov     [rcx+18h], rdi
0x18004a344  mov     [rcx], r13d
0x18004a347  mov     [rcx+10h], r15
0x18004a34b  add     [rbx+340h], r10b
0x18004a352  cmp     byte ptr [rbx+340h], 0Ah
0x18004a359  cmovz   r12d, r10d
0x18004a35d  mov     eax, [rsp+150h+var_120]
0x18004a361  or      [rcx+18h], eax
0x18004a364  add     [rcx+4], r10d
0x18004a368  add     [rcx+8], r15
0x18004a36c  cmp     r15, [rcx+10h]
0x18004a370  jnb     short loc_18004A376
0x18004a372  mov     [rcx+10h], r15
0x18004a376  call    cs:__imp_GetTickCount64
0x18004a37c  mov     dl, cs:byte_18006649A
0x18004a382  mov     rcx, rax
0x18004a385  sub     rcx, cs:qword_180066728
0x18004a38c  mov     r14, rax
0x18004a38f  mov     [rsp+150h+var_100], rax
0x18004a394  cmp     rcx, 493E0h
0x18004a39b  jnb     short loc_18004A3AB
0x18004a39d  cmp     dl, 0Ah
0x18004a3a0  jz      short loc_18004A3AB
0x18004a3a2  test    r12b, r12b
0x18004a3a5  jz      loc_18004A569
0x18004a3ab  xor     r12d, r12d
0x18004a3ae  mov     dil, r12b
0x18004a3b1  test    dl, dl
0x18004a3b3  jz      loc_18004A55B
0x18004a3b9  mov     r15, 400000000000h
0x18004a3c3  lea     r13, word_1800666C0
0x18004a3ca  lea     r14d, [r12+1]
0x18004a3cf  movzx   eax, dil
0x18004a3d3  mov     sil, r12b
0x18004a3d6  imul    rbx, rax, 348h
0x18004a3dd  lea     rax, qword_18007D7B0
0x18004a3e4  add     rbx, rax
0x18004a3e7  cmp     [rbx+340h], r12b
0x18004a3ee  jbe     loc_18004A54A
0x18004a3f4  mov     eax, cs:dword_1800652E8
0x18004a3fa  cmp     eax, 5
0x18004a3fd  jbe     loc_18004A534
0x18004a403  mov     rcx, cs:qword_180065300
0x18004a40a  mov     rax, cs:qword_1800652F8
0x18004a411  test    r15, rax
0x18004a414  jz      loc_18004A534
0x18004a41a  mov     rax, rcx
0x18004a41d  and     rax, r15
0x18004a420  cmp     rax, rcx
0x18004a423  jnz     loc_18004A534
0x18004a429  movzx   ecx, sil
0x18004a42d  add     rcx, 10h
0x18004a431  shl     rcx, 5
0x18004a435  mov     eax, [rcx+rbx+18h]
0x18004a439  mov     [rsp+150h+var_120], eax
0x18004a43d  mov     eax, [rcx+rbx+4]
0x18004a441  mov     [rsp+150h+var_11C], eax
0x18004a445  mov     rax, [rcx+rbx+10h]
0x18004a44a  mov     [rsp+150h+var_110], rax
0x18004a44f  mov     rax, [rcx+rbx+8]
0x18004a454  mov     [rsp+150h+var_108], rax
0x18004a459  mov     eax, [rcx+rbx]
0x18004a45c  mov     [rsp+150h+var_118], eax
0x18004a460  lea     rax, a32; "3.2"
0x18004a467  mov     [rbp+50h+var_60], rax
0x18004a46b  lea     rax, [rsp+150h+var_120]
0x18004a470  mov     [rbp+50h+var_70], rax
0x18004a474  lea     rax, [rsp+150h+var_11C]
0x18004a479  mov     [rbp+50h+var_80], rax
0x18004a47d  lea     rax, [rsp+150h+var_110]
0x18004a482  mov     [rbp+50h+var_90], rax
0x18004a486  lea     rax, [rsp+150h+var_108]
0x18004a48b  mov     [rbp+50h+var_A0], rax
0x18004a48f  lea     rax, [rsp+150h+var_118]
0x18004a494  mov     [rbp+50h+var_B0], rax
0x18004a498  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004a49c  mov     [rbp+50h+var_58], 8
0x18004a4a4  mov     [rbp+50h+var_68], 4
0x18004a4ac  mov     [rbp+50h+var_78], 4
0x18004a4b4  mov     [rbp+50h+var_88], 8
0x18004a4bc  mov     [rbp+50h+var_98], 8
0x18004a4c4  mov     [rbp+50h+var_A8], 4
0x18004a4cc  inc     rax
0x18004a4cf  cmp     [rbx+rax*2], r12w
0x18004a4d4  jnz     short loc_18004A4CC
0x18004a4d6  lea     eax, ds:2[rax*2]
0x18004a4dd  mov     [rbp+50h+var_C0], rbx
0x18004a4e1  mov     [rbp+50h+var_B8], eax
0x18004a4e4  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004a4e8  mov     [rbp+50h+var_B4], r12d
0x18004a4ec  inc     rax
0x18004a4ef  cmp     [r13+rax*2+0], r12w
0x18004a4f5  jnz     short loc_18004A4EC
0x18004a4f7  lea     eax, ds:2[rax*2]
0x18004a4fe  mov     [rbp+50h+var_D0], r13
0x18004a502  mov     [rbp+50h+var_C8], eax
0x18004a505  lea     rdx, byte_18005B88D
0x18004a50c  lea     rax, [rsp+150h+var_F0]
0x18004a511  mov     [rbp+50h+var_C4], r12d
0x18004a515  mov     [rsp+150h+var_128], rax
0x18004a51a  lea     rcx, dword_1800652E8
0x18004a521  xor     r9d, r9d
0x18004a524  mov     [rsp+150h+var_130], 0Ah
0x18004a52c  xor     r8d, r8d
0x18004a52f  call    _tlgWriteTransfer_EventWriteTransfer
0x18004a534  add     sil, r14b
0x18004a537  cmp     sil, [rbx+340h]
0x18004a53e  jb      loc_18004A3F4
0x18004a544  mov     dl, cs:byte_18006649A
0x18004a54a  add     dil, r14b
0x18004a54d  cmp     dil, dl
0x18004a550  jb      loc_18004A3CF
0x18004a556  mov     r14, [rsp+150h+var_100]
0x18004a55b  mov     cs:qword_180066728, r14
0x18004a562  mov     cs:byte_18006649A, r12b
0x18004a569  lea     rcx, stru_180066690; lpCriticalSection
0x18004a570  call    cs:__imp_LeaveCriticalSection
0x18004a576  mov     rcx, [rbp+50h+var_50]
0x18004a57a  xor     rcx, rsp; StackCookie
0x18004a57d  call    __security_check_cookie
0x18004a582  add     rsp, 118h
0x18004a589  pop     r15
0x18004a58b  pop     r14
0x18004a58d  pop     r13
0x18004a58f  pop     r12
0x18004a591  pop     rdi
0x18004a592  pop     rsi
0x18004a593  pop     rbx
0x18004a594  pop     rbp
0x18004a595  retn
```
