# _CacheOrUploadHttpRequestSuccess

- ea: `0x180049d1c`
- end: `0x18004a1b5`
- name: `_CacheOrUploadHttpRequestSuccess`
- size: `1177`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180048fe0`
- `0x18004b394`
- `0x18004b464`

## callees

- `0x180001644`
- `0x18000316c`
- `0x180049d1c`
- `0x18004b84c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180049dbb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180049e69`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180049dbb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180049e69`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049d6f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049d6f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a19b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a19b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180049f6e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180049f6e`

## pseudocode

```c
void __fastcall CacheOrUploadHttpRequestSuccess(
        CloudSettings *a1,
        unsigned __int16 a2,
        unsigned __int64 a3,
        __int64 a4,
        _WORD *a5,
        int a6,
        char a7)
{
  CloudSettings *v9; // rsi
  unsigned __int8 v10; // bl
  unsigned int v11; // r15d
  __int64 v12; // r12
  __int64 *v13; // r14
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 *v16; // rax
  __int64 *v17; // rcx
  unsigned __int8 v18; // bl
  __int64 *v19; // rdx
  unsigned __int16 v20; // cx
  unsigned __int8 v21; // al
  __int64 v22; // rdx
  __int16 v23; // ax
  _WORD *v24; // rcx
  __int64 v25; // r8
  _WORD *v26; // rax
  _WORD *v27; // rcx
  __int64 v28; // r9
  ULONGLONG TickCount64; // r15
  unsigned int v30; // esi
  __int64 v31; // rdi
  __int64 *v32; // r14
  __int64 v33; // rbx
  __int64 v34; // r12
  __int64 v35; // rdx
  __int16 v36[2]; // [rsp+90h] [rbp-80h] BYREF
  unsigned int v37; // [rsp+94h] [rbp-7Ch]
  int v38; // [rsp+98h] [rbp-78h] BYREF
  int v39; // [rsp+9Ch] [rbp-74h] BYREF
  const wchar_t *v40; // [rsp+A0h] [rbp-70h] BYREF
  const wchar_t *v41; // [rsp+A8h] [rbp-68h] BYREF
  __int64 v42; // [rsp+B0h] [rbp-60h] BYREF
  __int64 v43; // [rsp+B8h] [rbp-58h] BYREF
  __int64 v44; // [rsp+C0h] [rbp-50h] BYREF
  __int64 v45; // [rsp+C8h] [rbp-48h] BYREF
  wchar_t *v46; // [rsp+D0h] [rbp-40h] BYREF
  wchar_t *v47; // [rsp+D8h] [rbp-38h] BYREF
  __int64 *v48; // [rsp+E0h] [rbp-30h] BYREF
  __int16 *v49; // [rsp+E8h] [rbp-28h] BYREF
  ULONGLONG v50; // [rsp+F0h] [rbp-20h]

  v9 = a1;
  if ( !byte_180066498 )
    return;
  if ( (*(_BYTE *)CloudSettings::GetCloudSettingsSnapshot(a1) & 2) == 0 )
  {
    byte_180066499 = 0;
    return;
  }
  EnterCriticalSection(&stru_180066690);
  if ( v9 && a4 )
  {
    v10 = byte_180066499;
    v11 = 0;
    v12 = 2147483646;
    if ( byte_180066499 )
    {
      while ( 1 )
      {
        v13 = &qword_180066730[1179 * v11];
        if ( !(unsigned int)_o__wcsicmp(v13, v9) )
          break;
        v10 = byte_180066499;
        if ( ++v11 >= (unsigned __int8)byte_180066499 )
          goto LABEL_12;
      }
      if ( v13 )
        goto LABEL_19;
      v10 = byte_180066499;
    }
LABEL_12:
    v13 = &qword_180066730[1179 * v10];
    memset_0(v13, 0, 0x24D8u);
    v14 = 2147483646;
    v15 = 256;
    v16 = v13;
    do
    {
      if ( !v14 )
        break;
      if ( !*(_WORD *)v9 )
        break;
      *(_WORD *)v16 = *(_WORD *)v9;
      v9 = (CloudSettings *)((char *)v9 + 2);
      v16 = (__int64 *)((char *)v16 + 2);
      --v14;
      --v15;
    }
    while ( v15 );
    v17 = (__int64 *)((char *)v16 - 2);
    if ( v15 )
      v17 = v16;
    byte_180066499 = v10 + 1;
    *(_WORD *)v17 = 0;
LABEL_19:
    v18 = 0;
    while ( (unsigned int)_o__wcsicmp(a4, off_1800515A0[v18]) && v18 != 4 )
    {
      if ( ++v18 >= 5u )
      {
        v19 = 0;
        goto LABEL_25;
      }
    }
    v19 = &v13[223 * v18 + 64];
LABEL_25:
    *(_BYTE *)v19 = 1;
    v20 = 200;
    v21 = 0;
    while ( a2 >= v20 && v21 != 5 )
    {
      v20 += 100;
      if ( ++v21 >= 6u )
      {
        v22 = 0;
        goto LABEL_31;
      }
    }
    v22 = (__int64)&v19[37 * v21 + 1];
LABEL_31:
    v23 = *(_WORD *)(v22 + 4);
    if ( v23 )
    {
      if ( a3 >= *(_QWORD *)(v22 + 8) )
      {
        if ( a3 > *(_QWORD *)(v22 + 16) )
          *(_QWORD *)(v22 + 16) = a3;
      }
      else
      {
        *(_QWORD *)(v22 + 8) = a3;
      }
    }
    else
    {
      v24 = a5;
      *(_QWORD *)(v22 + 8) = a3;
      *(_QWORD *)(v22 + 16) = a3;
      if ( a5 )
      {
        v25 = 129;
        v26 = (_WORD *)(v22 + 32);
        do
        {
          if ( !v12 )
            break;
          if ( !*v24 )
            break;
          *v26++ = *v24++;
          --v12;
          --v25;
        }
        while ( v25 );
        v27 = v26 - 1;
        if ( v25 )
          v27 = v26;
        *v27 = 0;
        v23 = *(_WORD *)(v22 + 4);
      }
    }
    *(_QWORD *)(v22 + 24) += a3;
    *(_WORD *)(v22 + 4) = v23 + 1;
    *(_DWORD *)v22 |= a6;
  }
  TickCount64 = GetTickCount64();
  v50 = TickCount64;
  if ( TickCount64 - qword_18007D7A0 >= 0x493E0 || byte_180066499 == 10 || a7 )
  {
    v37 = 0;
    v30 = 0;
    if ( byte_180066499 )
    {
      do
      {
        v31 = 0;
        v32 = &qword_180066730[1179 * v30];
        do
        {
          if ( LOBYTE(v32[223 * v31 + 64]) )
          {
            v33 = 0;
            v34 = (__int64)&v32[223 * v31 + 65];
            do
            {
              v35 = 296 * v33;
              if ( *(_WORD *)(296 * v33 + v34 + 4)
                && (unsigned int)dword_1800652E8 > 5
                && (qword_1800652F8 & 0x400000000000LL) != 0
                && (qword_180065300 & 0x400000000000LL) == qword_180065300 )
              {
                v38 = 1;
                v40 = L"3.2";
                v41 = L"HTTP";
                v39 = *(_DWORD *)(v35 + v34);
                v48 = &qword_180066730[1179 * v30];
                v42 = v35 + v34 + 32;
                v43 = *(_QWORD *)(v35 + v34 + 16);
                v44 = *(_QWORD *)(v35 + v34 + 8);
                v45 = *(_QWORD *)(v35 + v34 + 24);
                v36[0] = *(_WORD *)(v35 + v34 + 4);
                v46 = off_1800515D0[v33];
                v47 = off_1800515A0[v31];
                v49 = &word_1800666C0;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
                  qword_180065300,
                  (__int64)&dword_18005B77C,
                  0x400000000000LL,
                  v28,
                  &v49,
                  &v48,
                  &v47,
                  &v46,
                  (__int64)v36,
                  (__int64)&v45,
                  (__int64)&v44,
                  (__int64)&v43,
                  &v42,
                  (__int64)&v39,
                  &v41,
                  (__int64)&v38,
                  &v40);
              }
              ++v33;
            }
            while ( v33 != 6 );
          }
          ++v31;
        }
        while ( v31 != 5 );
        v30 = v37 + 1;
        v37 = v30;
      }
      while ( v30 < (unsigned __int8)byte_180066499 );
      TickCount64 = v50;
    }
    qword_18007D7A0 = TickCount64;
    byte_180066499 = 0;
  }
  LeaveCriticalSection(&stru_180066690);
}

```

## disassembly

```asm
0x180049d1c  mov     [rsp-8+arg_8], dx
0x180049d21  push    rbp
0x180049d22  push    rbx
0x180049d23  push    rsi
0x180049d24  push    rdi
0x180049d25  push    r12
0x180049d27  push    r13
0x180049d29  push    r14
0x180049d2b  push    r15
0x180049d2d  lea     rbp, [rsp+8]
0x180049d32  sub     rsp, 108h
0x180049d39  xor     r14d, r14d
0x180049d3c  mov     r13, r9
0x180049d3f  cmp     cs:byte_180066498, r14b
0x180049d46  mov     rdi, r8
0x180049d49  mov     rsi, rcx
0x180049d4c  jz      loc_18004A1A1
0x180049d52  call    ?GetCloudSettingsSnapshot@CloudSettings@@QEAAAEBUWinHttpSettings@@XZ; CloudSettings::GetCloudSettingsSnapshot(void)
0x180049d57  test    byte ptr [rax], 2
0x180049d5a  jnz     short loc_180049D68
0x180049d5c  mov     cs:byte_180066499, r14b
0x180049d63  jmp     loc_18004A1A1
0x180049d68  lea     rcx, stru_180066690; lpCriticalSection
0x180049d6f  call    cs:__imp_EnterCriticalSection
0x180049d75  lea     rbx, qword_180066730
0x180049d7c  test    rsi, rsi
0x180049d7f  jz      loc_180049F68
0x180049d85  test    r13, r13
0x180049d88  jz      loc_180049F68
0x180049d8e  mov     bl, cs:byte_180066499
0x180049d94  mov     r15d, r14d
0x180049d97  mov     r12d, 7FFFFFFEh
0x180049d9d  test    bl, bl
0x180049d9f  jz      short loc_180049DE7
0x180049da1  mov     eax, r15d
0x180049da4  mov     rdx, rsi
0x180049da7  imul    r14, rax, 24D8h
0x180049dae  lea     rax, qword_180066730
0x180049db5  add     r14, rax
0x180049db8  mov     rcx, r14
0x180049dbb  call    cs:__imp__o__wcsicmp
0x180049dc1  test    eax, eax
0x180049dc3  jz      short loc_180049DD9
0x180049dc5  movzx   ebx, cs:byte_180066499
0x180049dcc  inc     r15d
0x180049dcf  cmp     r15d, ebx
0x180049dd2  jb      short loc_180049DA1
0x180049dd4  xor     r15d, r15d
0x180049dd7  jmp     short loc_180049DE7
0x180049dd9  xor     r15d, r15d
0x180049ddc  test    r14, r14
0x180049ddf  jnz     short loc_180049E51
0x180049de1  mov     bl, cs:byte_180066499
0x180049de7  movzx   eax, bl
0x180049dea  xor     edx, edx; Val
0x180049dec  imul    r14, rax, 24D8h
0x180049df3  lea     rax, qword_180066730
0x180049dfa  mov     r8d, 24D8h; Size
0x180049e00  add     r14, rax
0x180049e03  mov     rcx, r14; void *
0x180049e06  call    memset_0
0x180049e0b  mov     rcx, r12
0x180049e0e  mov     edx, 100h
0x180049e13  mov     rax, r14
0x180049e16  test    rcx, rcx
0x180049e19  jz      short loc_180049E3A
0x180049e1b  movzx   r8d, word ptr [rsi]
0x180049e1f  test    r8w, r8w
0x180049e23  jz      short loc_180049E3A
0x180049e25  mov     [rax], r8w
0x180049e29  add     rsi, 2
0x180049e2d  add     rax, 2
0x180049e31  dec     rcx
0x180049e34  sub     rdx, 1
0x180049e38  jnz     short loc_180049E16
0x180049e3a  test    rdx, rdx
0x180049e3d  lea     rcx, [rax-2]
0x180049e41  cmovnz  rcx, rax
0x180049e45  inc     bl
0x180049e47  mov     cs:byte_180066499, bl
0x180049e4d  mov     [rcx], r15w
0x180049e51  mov     bl, r15b
0x180049e54  lea     rax, __ImageBase
0x180049e5b  movzx   esi, bl
0x180049e5e  mov     rcx, r13
0x180049e61  mov     rdx, ds:rva off_1800515A0[rax+rsi*8]; "GET" ...
0x180049e69  call    cs:__imp__o__wcsicmp
0x180049e6f  test    eax, eax
0x180049e71  jz      short loc_180049E87
0x180049e73  cmp     bl, 4
0x180049e76  jz      short loc_180049E87
0x180049e78  inc     bl
0x180049e7a  cmp     bl, 5
0x180049e7d  jb      short loc_180049E54
0x180049e7f  xor     r14d, r14d
0x180049e82  mov     edx, r14d
0x180049e85  jmp     short loc_180049E9B
0x180049e87  imul    rdx, rsi, 6F8h
0x180049e8e  add     r14, 200h
0x180049e95  add     rdx, r14
0x180049e98  xor     r14d, r14d
0x180049e9b  movzx   r8d, [rbp+30h+arg_8]
0x180049ea0  mov     r13d, 1
0x180049ea6  mov     [rdx], r13b
0x180049ea9  mov     ecx, 0C8h
0x180049eae  mov     al, r14b
0x180049eb1  cmp     r8w, cx
0x180049eb5  jb      short loc_180049ECB
0x180049eb7  cmp     al, 5
0x180049eb9  jz      short loc_180049ECB
0x180049ebb  add     cx, 64h ; 'd'
0x180049ebf  add     al, r13b
0x180049ec2  cmp     al, 6
0x180049ec4  jb      short loc_180049EB1
0x180049ec6  mov     rdx, r14
0x180049ec9  jmp     short loc_180049EDC
0x180049ecb  movzx   eax, al
0x180049ece  add     rdx, 8
0x180049ed2  imul    rcx, rax, 128h
0x180049ed9  add     rdx, rcx
0x180049edc  movzx   eax, word ptr [rdx+4]
0x180049ee0  test    ax, ax
0x180049ee3  jnz     short loc_180049F38
0x180049ee5  mov     rcx, [rbp+30h+arg_20]
0x180049ee9  mov     [rdx+8], rdi
0x180049eed  mov     [rdx+10h], rdi
0x180049ef1  test    rcx, rcx
0x180049ef4  jz      short loc_180049F4E
0x180049ef6  mov     r8d, 81h
0x180049efc  lea     rax, [rdx+20h]
0x180049f00  test    r12, r12
0x180049f03  jz      short loc_180049F23
0x180049f05  movzx   r9d, word ptr [rcx]
0x180049f09  test    r9w, r9w
0x180049f0d  jz      short loc_180049F23
0x180049f0f  mov     [rax], r9w
0x180049f13  add     rcx, 2
0x180049f17  add     rax, 2
0x180049f1b  sub     r12, r13
0x180049f1e  sub     r8, r13
0x180049f21  jnz     short loc_180049F00
0x180049f23  lea     rcx, [rax-2]
0x180049f27  test    r8, r8
0x180049f2a  cmovnz  rcx, rax
0x180049f2e  mov     [rcx], r14w
0x180049f32  movzx   eax, word ptr [rdx+4]
0x180049f36  jmp     short loc_180049F4E
0x180049f38  cmp     rdi, [rdx+8]
0x180049f3c  jnb     short loc_180049F44
0x180049f3e  mov     [rdx+8], rdi
0x180049f42  jmp     short loc_180049F4E
0x180049f44  cmp     rdi, [rdx+10h]
0x180049f48  jbe     short loc_180049F4E
0x180049f4a  mov     [rdx+10h], rdi
0x180049f4e  add     [rdx+18h], rdi
0x180049f52  lea     rbx, qword_180066730
0x180049f59  add     ax, r13w
0x180049f5d  mov     [rdx+4], ax
0x180049f61  mov     eax, [rbp+30h+arg_28]
0x180049f64  or      [rdx], eax
0x180049f66  jmp     short loc_180049F6E
0x180049f68  mov     r13d, 1
0x180049f6e  call    cs:__imp_GetTickCount64
0x180049f74  mov     dl, cs:byte_180066499
0x180049f7a  mov     rcx, rax
0x180049f7d  sub     rcx, cs:qword_18007D7A0
0x180049f84  mov     r15, rax
0x180049f87  mov     [rbp+30h+var_50], rax
0x180049f8b  cmp     rcx, 493E0h
0x180049f92  jnb     short loc_180049FA3
0x180049f94  cmp     dl, 0Ah
0x180049f97  jz      short loc_180049FA3
0x180049f99  cmp     [rbp+30h+arg_30], r14b
0x180049f9d  jz      loc_18004A194
0x180049fa3  mov     [rbp+30h+var_AC], r14d
0x180049fa7  mov     esi, r14d
0x180049faa  test    dl, dl
0x180049fac  jz      loc_18004A186
0x180049fb2  mov     r8, 400000000000h
0x180049fbc  xor     r15d, r15d
0x180049fbf  mov     eax, esi
0x180049fc1  mov     rdi, r15
0x180049fc4  imul    r14, rax, 24D8h
0x180049fcb  lea     rsi, __ImageBase
0x180049fd2  add     r14, rbx
0x180049fd5  imul    rax, rdi, 6F8h
0x180049fdc  cmp     [rax+r14+200h], r15b
0x180049fe4  jz      loc_18004A153
0x180049fea  lea     r12, [r14+208h]
0x180049ff1  mov     rbx, r15
0x180049ff4  add     r12, rax
0x180049ff7  imul    rdx, rbx, 128h
0x180049ffe  cmp     [rdx+r12+4], r15w
0x18004a004  jbe     loc_18004A146
0x18004a00a  mov     eax, cs:dword_1800652E8
0x18004a010  cmp     eax, 5
0x18004a013  jbe     loc_18004A146
0x18004a019  mov     rcx, cs:qword_180065300
0x18004a020  mov     rax, cs:qword_1800652F8
0x18004a027  test    r8, rax
0x18004a02a  jz      loc_18004A146
0x18004a030  mov     rax, rcx
0x18004a033  and     rax, r8
0x18004a036  cmp     rax, rcx
0x18004a039  jnz     loc_18004A146
0x18004a03f  lea     rax, a32; "3.2"
0x18004a046  mov     [rbp+30h+var_A8], r13d
0x18004a04a  mov     [rbp+30h+var_A0], rax
0x18004a04e  lea     rax, aHttp; "HTTP"
0x18004a055  mov     [rbp+30h+var_98], rax
0x18004a059  mov     eax, [rdx+r12]
0x18004a05d  mov     [rbp+30h+var_A4], eax
0x18004a060  lea     rax, [r12+20h]
0x18004a065  add     rax, rdx
0x18004a068  mov     [rbp+30h+var_60], r14
0x18004a06c  mov     [rbp+30h+var_90], rax
0x18004a070  mov     rax, [rdx+r12+10h]
0x18004a075  mov     [rbp+30h+var_88], rax
0x18004a079  mov     rax, [rdx+r12+8]
0x18004a07e  mov     [rbp+30h+var_80], rax
0x18004a082  mov     rax, [rdx+r12+18h]
0x18004a087  mov     [rbp+30h+var_78], rax
0x18004a08b  movzx   eax, word ptr [rdx+r12+4]
0x18004a091  lea     rdx, dword_18005B77C
0x18004a098  mov     [rbp+30h+var_B0], ax
0x18004a09c  mov     rax, ds:rva off_1800515D0[rsi+rbx*8]; "1XX" ...
0x18004a0a4  mov     [rbp+30h+var_70], rax
0x18004a0a8  mov     rax, ds:rva off_1800515A0[rsi+rdi*8]; "GET" ...
0x18004a0b0  mov     [rbp+30h+var_68], rax
0x18004a0b4  lea     rax, word_1800666C0
0x18004a0bb  mov     [rbp+30h+var_58], rax
0x18004a0bf  lea     rax, [rbp+30h+var_A0]
0x18004a0c3  mov     [rsp+140h+var_C0], rax
0x18004a0cb  lea     rax, [rbp+30h+var_A8]
0x18004a0cf  mov     [rsp+140h+var_C8], rax
0x18004a0d4  lea     rax, [rbp+30h+var_98]
0x18004a0d8  mov     [rsp+140h+var_D0], rax
0x18004a0dd  lea     rax, [rbp+30h+var_A4]
0x18004a0e1  mov     [rsp+140h+var_D8], rax
0x18004a0e6  lea     rax, [rbp+30h+var_90]
0x18004a0ea  mov     [rsp+140h+var_E0], rax
0x18004a0ef  lea     rax, [rbp+30h+var_88]
0x18004a0f3  mov     [rsp+140h+var_E8], rax
0x18004a0f8  lea     rax, [rbp+30h+var_80]
0x18004a0fc  mov     [rsp+140h+var_F0], rax
0x18004a101  lea     rax, [rbp+30h+var_78]
0x18004a105  mov     [rsp+140h+var_F8], rax
0x18004a10a  lea     rax, [rbp+30h+var_B0]
0x18004a10e  mov     [rsp+140h+var_100], rax
0x18004a113  lea     rax, [rbp+30h+var_70]
0x18004a117  mov     [rsp+140h+var_108], rax
0x18004a11c  lea     rax, [rbp+30h+var_68]
0x18004a120  mov     [rsp+140h+var_110], rax
0x18004a125  lea     rax, [rbp+30h+var_60]
0x18004a129  mov     [rsp+140h+var_118], rax
0x18004a12e  lea     rax, [rbp+30h+var_58]
0x18004a132  mov     [rsp+140h+var_120], rax
0x18004a137  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@U1@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByVal@$07@@U3@U3@U1@U?$_tlgWrapperByVal@$03@@U1@U4@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@333AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByVal@$07@@553AEBU?$_tlgWrapperByVal@$03@@363@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18004a13c  mov     r8, 400000000000h
0x18004a146  add     rbx, r13
0x18004a149  cmp     rbx, 6
0x18004a14d  jnz     loc_180049FF7
0x18004a153  inc     rdi
0x18004a156  cmp     rdi, 5
0x18004a15a  jnz     loc_180049FD5
0x18004a160  mov     esi, [rbp+30h+var_AC]
0x18004a163  lea     rbx, qword_180066730
0x18004a16a  movzx   eax, cs:byte_180066499
0x18004a171  add     esi, r13d
0x18004a174  mov     [rbp+30h+var_AC], esi
0x18004a177  cmp     esi, eax
0x18004a179  jb      loc_180049FBF
0x18004a17f  mov     r15, [rbp+30h+var_50]
0x18004a183  xor     r14d, r14d
0x18004a186  mov     cs:qword_18007D7A0, r15
0x18004a18d  mov     cs:byte_180066499, r14b
0x18004a194  lea     rcx, stru_180066690; lpCriticalSection
0x18004a19b  call    cs:__imp_LeaveCriticalSection
0x18004a1a1  add     rsp, 108h
0x18004a1a8  pop     r15
0x18004a1aa  pop     r14
0x18004a1ac  pop     r13
0x18004a1ae  pop     r12
0x18004a1b0  pop     rdi
0x18004a1b1  pop     rsi
0x18004a1b2  pop     rbx
0x18004a1b3  pop     rbp
0x18004a1b4  retn
```
