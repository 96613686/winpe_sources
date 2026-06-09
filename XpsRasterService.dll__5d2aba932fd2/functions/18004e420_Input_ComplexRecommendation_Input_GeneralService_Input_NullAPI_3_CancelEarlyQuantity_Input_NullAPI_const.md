# Input::ComplexRecommendation<Input::GeneralService,Input::NullAPI,3>::CancelEarlyQuantity(Input::NullAPI const &)

- ea: `0x18004e420`
- end: `0x18004e895`
- name: `?CancelEarlyQuantity@?$ComplexRecommendation@VGeneralService@Input@@VNullAPI@2@$02@Input@@QEAAXAEBVNullAPI@2@@Z`
- size: `1141`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004fc10`

## callees

- `0x180003180`
- `0x18004e420`
- `0x1800a0303`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Input::ComplexRecommendation<Input::GeneralService,Input::NullAPI,3>::CancelEarlyQuantity(
        __int64 a1,
        __int128 *a2)
{
  __int64 v2; // rbx
  __int64 v3; // rsi
  int v4; // ecx
  int v5; // eax
  __int64 result; // rax
  int v7; // ecx
  int v8; // eax
  int v9; // eax
  int v10; // ecx
  int v11; // eax
  __int128 v12; // [rsp+20h] [rbp-E0h]
  __int128 v13; // [rsp+30h] [rbp-D0h]
  __int128 v14; // [rsp+40h] [rbp-C0h]
  __int128 v15; // [rsp+50h] [rbp-B0h]
  __int128 v16; // [rsp+60h] [rbp-A0h]
  __int128 v17; // [rsp+70h] [rbp-90h]
  __int128 v18; // [rsp+80h] [rbp-80h]
  __int64 v19; // [rsp+90h] [rbp-70h]
  unsigned int v20; // [rsp+98h] [rbp-68h]
  __int128 v21; // [rsp+A0h] [rbp-60h]
  __int128 v22; // [rsp+B0h] [rbp-50h]
  __int128 v23; // [rsp+C0h] [rbp-40h]
  __int128 v24; // [rsp+D0h] [rbp-30h]
  __int128 v25; // [rsp+E0h] [rbp-20h]
  __int128 v26; // [rsp+F0h] [rbp-10h]
  __int128 v27; // [rsp+100h] [rbp+0h]
  __int64 v28; // [rsp+110h] [rbp+10h]
  unsigned int v29; // [rsp+118h] [rbp+18h]
  __int128 v30; // [rsp+120h] [rbp+20h]
  __int128 v31; // [rsp+130h] [rbp+30h]
  __int128 v32; // [rsp+140h] [rbp+40h]
  __int128 v33; // [rsp+150h] [rbp+50h]
  __int128 v34; // [rsp+160h] [rbp+60h]
  __int128 v35; // [rsp+170h] [rbp+70h]
  __int128 v36; // [rsp+180h] [rbp+80h]
  __int64 v37; // [rsp+190h] [rbp+90h]
  unsigned int v38; // [rsp+198h] [rbp+98h]
  __int128 Buf2; // [rsp+1A0h] [rbp+A0h] BYREF
  __int128 v40; // [rsp+1B0h] [rbp+B0h]
  __int128 v41; // [rsp+1C0h] [rbp+C0h]
  __int128 v42; // [rsp+1D0h] [rbp+D0h]
  _BYTE v43[48]; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 v44; // [rsp+210h] [rbp+110h]
  unsigned int v45; // [rsp+218h] [rbp+118h]

  memset(&v43[8], 0, 36);
  v12 = *a2;
  v13 = a2[1];
  v14 = a2[2];
  v15 = a2[3];
  v16 = a2[4];
  v17 = a2[5];
  v18 = a2[6];
  v19 = *((_QWORD *)a2 + 14);
  v20 = *((_DWORD *)a2 + 30);
  v2 = a1 + 4;
  v3 = 3;
  do
  {
    v4 = 1;
    while ( _InterlockedExchange((volatile __int32 *)v2, 1) )
    {
      while ( *(_DWORD *)v2 )
      {
        v5 = v4;
        if ( !v4 )
          goto LABEL_8;
        do
        {
          _mm_pause();
          --v5;
        }
        while ( v5 );
        if ( v4 >= 64 )
          v4 = 64;
        else
LABEL_8:
          v4 *= 2;
      }
    }
    v21 = *(_OWORD *)(v2 + 4);
    v22 = *(_OWORD *)(v2 + 20);
    v23 = *(_OWORD *)(v2 + 36);
    v24 = *(_OWORD *)(v2 + 52);
    v25 = *(_OWORD *)(v2 + 68);
    v26 = *(_OWORD *)(v2 + 84);
    v27 = *(_OWORD *)(v2 + 100);
    v28 = *(_QWORD *)(v2 + 116);
    v29 = *(_DWORD *)(v2 + 124);
    _InterlockedExchange((volatile __int32 *)v2, 0);
    Buf2 = v21;
    v40 = v22;
    v41 = v23;
    v42 = v24;
    *(_OWORD *)v43 = v25;
    *(_OWORD *)&v43[16] = v26;
    *(_OWORD *)&v43[32] = v27;
    v44 = v28;
    result = v29;
    v45 = v29;
    if ( *(float *)&v12 > *(float *)&v21 )
    {
      while ( 1 )
      {
        v7 = 1;
        while ( _InterlockedExchange((volatile __int32 *)v2, 1) )
        {
          while ( *(_DWORD *)v2 )
          {
            v8 = v7;
            if ( !v7 )
              goto LABEL_18;
            do
            {
              _mm_pause();
              --v8;
            }
            while ( v8 );
            if ( v7 >= 64 )
              v7 = 64;
            else
LABEL_18:
              v7 *= 2;
          }
        }
        v9 = memcmp_0((const void *)(v2 + 4), &Buf2, 0x7Cu);
        if ( v9 )
        {
          Buf2 = *(_OWORD *)(v2 + 4);
          v40 = *(_OWORD *)(v2 + 20);
          v41 = *(_OWORD *)(v2 + 36);
          v42 = *(_OWORD *)(v2 + 52);
          *(_OWORD *)v43 = *(_OWORD *)(v2 + 68);
          *(_OWORD *)&v43[16] = *(_OWORD *)(v2 + 84);
          *(_OWORD *)&v43[32] = *(_OWORD *)(v2 + 100);
          v44 = *(_QWORD *)(v2 + 116);
          v45 = *(_DWORD *)(v2 + 124);
        }
        else
        {
          *(_OWORD *)(v2 + 4) = v12;
          *(_OWORD *)(v2 + 20) = v13;
          *(_OWORD *)(v2 + 36) = v14;
          *(_OWORD *)(v2 + 52) = v15;
          *(_OWORD *)(v2 + 68) = v16;
          *(_OWORD *)(v2 + 84) = v17;
          *(_OWORD *)(v2 + 100) = v18;
          *(_QWORD *)(v2 + 116) = v19;
          *(_DWORD *)(v2 + 124) = v20;
        }
        _InterlockedExchange((volatile __int32 *)v2, 0);
        if ( !v9 )
          break;
        v10 = 1;
        while ( _InterlockedExchange((volatile __int32 *)v2, 1) )
        {
          while ( *(_DWORD *)v2 )
          {
            v11 = v10;
            if ( !v10 )
              goto LABEL_31;
            do
            {
              _mm_pause();
              --v11;
            }
            while ( v11 );
            if ( v10 >= 64 )
              v10 = 64;
            else
LABEL_31:
              v10 *= 2;
          }
        }
        v30 = *(_OWORD *)(v2 + 4);
        v31 = *(_OWORD *)(v2 + 20);
        v32 = *(_OWORD *)(v2 + 36);
        v33 = *(_OWORD *)(v2 + 52);
        v34 = *(_OWORD *)(v2 + 68);
        v35 = *(_OWORD *)(v2 + 84);
        v36 = *(_OWORD *)(v2 + 100);
        v37 = *(_QWORD *)(v2 + 116);
        v38 = *(_DWORD *)(v2 + 124);
        _InterlockedExchange((volatile __int32 *)v2, 0);
        Buf2 = v30;
        v40 = v31;
        v41 = v32;
        v42 = v33;
        *(_OWORD *)v43 = v34;
        *(_OWORD *)&v43[16] = v35;
        *(_OWORD *)&v43[32] = v36;
        v44 = v37;
        result = v38;
        v45 = v38;
        if ( *(float *)&v12 <= *(float *)&v30 )
          goto LABEL_37;
      }
      v12 = Buf2;
      v13 = v40;
      v14 = v41;
      v15 = v42;
      v16 = *(_OWORD *)v43;
      v17 = *(_OWORD *)&v43[16];
      v18 = *(_OWORD *)&v43[32];
      v19 = v44;
      result = v45;
      v20 = v45;
    }
LABEL_37:
    v2 += 128;
    --v3;
  }
  while ( v3 );
  return result;
}

```

## disassembly

```asm
0x18004e420  mov     [rsp-8+arg_8], rbx
0x18004e425  mov     [rsp-8+arg_10], rsi
0x18004e42a  mov     [rsp-8+arg_18], rdi
0x18004e42f  push    rbp
0x18004e430  lea     rbp, [rsp-130h]
0x18004e438  sub     rsp, 230h
0x18004e43f  mov     rax, cs:__security_cookie
0x18004e446  xor     rax, rsp
0x18004e449  mov     [rbp+130h+var_10], rax
0x18004e450  xorps   xmm0, xmm0
0x18004e453  xor     eax, eax
0x18004e455  movups  [rbp+130h+var_48], xmm0
0x18004e45c  movups  [rbp+130h+var_38], xmm0
0x18004e463  mov     [rbp+130h+var_28], eax
0x18004e469  movups  xmm0, xmmword ptr [rdx]
0x18004e46c  movaps  [rsp+230h+var_210], xmm0
0x18004e471  movups  xmm1, xmmword ptr [rdx+10h]
0x18004e475  movaps  [rsp+230h+var_200], xmm1
0x18004e47a  movups  xmm0, xmmword ptr [rdx+20h]
0x18004e47e  movaps  [rsp+230h+var_1F0], xmm0
0x18004e483  movups  xmm1, xmmword ptr [rdx+30h]
0x18004e487  movaps  [rsp+230h+var_1E0], xmm1
0x18004e48c  movups  xmm0, xmmword ptr [rdx+40h]
0x18004e490  movaps  [rsp+230h+var_1D0], xmm0
0x18004e495  movups  xmm1, xmmword ptr [rdx+50h]
0x18004e499  movaps  [rsp+230h+var_1C0], xmm1
0x18004e49e  movups  xmm0, xmmword ptr [rdx+60h]
0x18004e4a2  movaps  [rbp+130h+var_1B0], xmm0
0x18004e4a6  movsd   xmm1, qword ptr [rdx+70h]
0x18004e4ab  movsd   [rbp+130h+var_1A0], xmm1
0x18004e4b0  mov     eax, [rdx+78h]
0x18004e4b3  mov     [rbp+130h+var_198], eax
0x18004e4b6  lea     rbx, [rcx+4]
0x18004e4ba  mov     esi, 3
0x18004e4bf  nop
0x18004e4c0  mov     ecx, 1
0x18004e4c5  mov     eax, ecx
0x18004e4c7  xchg    eax, [rbx]
0x18004e4c9  test    eax, eax
0x18004e4cb  jz      short loc_18004E504
0x18004e4cd  nop     dword ptr [rax]
0x18004e4d0  mov     eax, [rbx]
0x18004e4d2  test    eax, eax
0x18004e4d4  jz      short loc_18004E4F9
0x18004e4d6  mov     eax, ecx
0x18004e4d8  test    ecx, ecx
0x18004e4da  jz      short loc_18004E4F1
0x18004e4dc  nop     dword ptr [rax+00h]
0x18004e4e0  pause
0x18004e4e2  sub     eax, 1
0x18004e4e5  jnz     short loc_18004E4E0
0x18004e4e7  cmp     ecx, 40h ; '@'
0x18004e4ea  jl      short loc_18004E4F1
0x18004e4ec  lea     ecx, [rax+40h]
0x18004e4ef  jmp     short loc_18004E4F3
0x18004e4f1  add     ecx, ecx
0x18004e4f3  mov     eax, [rbx]
0x18004e4f5  test    eax, eax
0x18004e4f7  jnz     short loc_18004E4D6
0x18004e4f9  mov     eax, 1
0x18004e4fe  xchg    eax, [rbx]
0x18004e500  test    eax, eax
0x18004e502  jnz     short loc_18004E4D0
0x18004e504  movups  xmm0, xmmword ptr [rbx+4]
0x18004e508  movaps  [rbp+130h+var_190], xmm0
0x18004e50c  movups  xmm1, xmmword ptr [rbx+14h]
0x18004e510  movaps  [rbp+130h+var_180], xmm1
0x18004e514  movups  xmm0, xmmword ptr [rbx+24h]
0x18004e518  movaps  [rbp+130h+var_170], xmm0
0x18004e51c  movups  xmm1, xmmword ptr [rbx+34h]
0x18004e520  movaps  [rbp+130h+var_160], xmm1
0x18004e524  movups  xmm0, xmmword ptr [rbx+44h]
0x18004e528  movaps  [rbp+130h+var_150], xmm0
0x18004e52c  movups  xmm1, xmmword ptr [rbx+54h]
0x18004e530  movaps  [rbp+130h+var_140], xmm1
0x18004e534  movups  xmm0, xmmword ptr [rbx+64h]
0x18004e538  movaps  [rbp+130h+var_130], xmm0
0x18004e53c  movsd   xmm1, qword ptr [rbx+74h]
0x18004e541  movsd   [rbp+130h+var_120], xmm1
0x18004e546  mov     eax, [rbx+7Ch]
0x18004e549  mov     [rbp+130h+var_118], eax
0x18004e54c  xor     eax, eax
0x18004e54e  xchg    eax, [rbx]
0x18004e550  movaps  xmm2, [rbp+130h+var_190]
0x18004e554  movaps  [rbp+130h+Buf2], xmm2
0x18004e55b  movaps  xmm0, [rbp+130h+var_180]
0x18004e55f  movaps  [rbp+130h+var_80], xmm0
0x18004e566  movaps  xmm1, [rbp+130h+var_170]
0x18004e56a  movaps  [rbp+130h+var_70], xmm1
0x18004e571  movaps  xmm0, [rbp+130h+var_160]
0x18004e575  movaps  [rbp+130h+var_60], xmm0
0x18004e57c  movaps  xmm1, [rbp+130h+var_150]
0x18004e580  movaps  xmmword ptr [rbp+0E0h], xmm1
0x18004e587  movaps  xmm0, [rbp+130h+var_140]
0x18004e58b  movaps  [rbp+130h+var_48+8], xmm0
0x18004e592  movaps  xmm1, [rbp+130h+var_130]
0x18004e596  movaps  [rbp+130h+var_38+8], xmm1
0x18004e59d  movsd   xmm0, [rbp+130h+var_120]
0x18004e5a2  movsd   [rbp+130h+var_20], xmm0
0x18004e5aa  mov     eax, [rbp+130h+var_118]
0x18004e5ad  mov     [rbp+130h+var_18], eax
0x18004e5b3  movss   xmm0, dword ptr [rsp+230h+var_210]
0x18004e5b9  comiss  xmm0, xmm2
0x18004e5bc  jbe     loc_18004E85F
0x18004e5c2  mov     ecx, 1
0x18004e5c7  mov     eax, ecx
0x18004e5c9  xchg    eax, [rbx]
0x18004e5cb  test    eax, eax
0x18004e5cd  jz      short loc_18004E604
0x18004e5cf  nop
0x18004e5d0  mov     eax, [rbx]
0x18004e5d2  test    eax, eax
0x18004e5d4  jz      short loc_18004E5F9
0x18004e5d6  mov     eax, ecx
0x18004e5d8  test    ecx, ecx
0x18004e5da  jz      short loc_18004E5F1
0x18004e5dc  nop     dword ptr [rax+00h]
0x18004e5e0  pause
0x18004e5e2  sub     eax, 1
0x18004e5e5  jnz     short loc_18004E5E0
0x18004e5e7  cmp     ecx, 40h ; '@'
0x18004e5ea  jl      short loc_18004E5F1
0x18004e5ec  lea     ecx, [rax+40h]
0x18004e5ef  jmp     short loc_18004E5F3
0x18004e5f1  add     ecx, ecx
0x18004e5f3  mov     eax, [rbx]
0x18004e5f5  test    eax, eax
0x18004e5f7  jnz     short loc_18004E5D6
0x18004e5f9  mov     eax, 1
0x18004e5fe  xchg    eax, [rbx]
0x18004e600  test    eax, eax
0x18004e602  jnz     short loc_18004E5D0
0x18004e604  mov     r8d, 7Ch ; '|'; Size
0x18004e60a  lea     rdx, [rbp+130h+Buf2]; Buf2
0x18004e611  lea     rcx, [rbx+4]; Buf1
0x18004e615  call    memcmp_0
0x18004e61a  test    eax, eax
0x18004e61c  setz    cl
0x18004e61f  test    cl, cl
0x18004e621  jz      short loc_18004E673
0x18004e623  movaps  xmm0, [rsp+230h+var_210]
0x18004e628  movups  xmmword ptr [rbx+4], xmm0
0x18004e62c  movaps  xmm1, [rsp+230h+var_200]
0x18004e631  movups  xmmword ptr [rbx+14h], xmm1
0x18004e635  movaps  xmm0, [rsp+230h+var_1F0]
0x18004e63a  movups  xmmword ptr [rbx+24h], xmm0
0x18004e63e  movaps  xmm1, [rsp+230h+var_1E0]
0x18004e643  movups  xmmword ptr [rbx+34h], xmm1
0x18004e647  movaps  xmm0, [rsp+230h+var_1D0]
0x18004e64c  movups  xmmword ptr [rbx+44h], xmm0
0x18004e650  movaps  xmm1, [rsp+230h+var_1C0]
0x18004e655  movups  xmmword ptr [rbx+54h], xmm1
0x18004e659  movaps  xmm0, [rbp+130h+var_1B0]
0x18004e65d  movups  xmmword ptr [rbx+64h], xmm0
0x18004e661  movsd   xmm1, [rbp+130h+var_1A0]
0x18004e666  movsd   qword ptr [rbx+74h], xmm1
0x18004e66b  mov     eax, [rbp+130h+var_198]
0x18004e66e  mov     [rbx+7Ch], eax
0x18004e671  jmp     short loc_18004E6D6
0x18004e673  movups  xmm0, xmmword ptr [rbx+4]
0x18004e677  movaps  [rbp+130h+Buf2], xmm0
0x18004e67e  movups  xmm1, xmmword ptr [rbx+14h]
0x18004e682  movaps  [rbp+130h+var_80], xmm1
0x18004e689  movups  xmm0, xmmword ptr [rbx+24h]
0x18004e68d  movaps  [rbp+130h+var_70], xmm0
0x18004e694  movups  xmm1, xmmword ptr [rbx+34h]
0x18004e698  movaps  [rbp+130h+var_60], xmm1
0x18004e69f  movups  xmm0, xmmword ptr [rbx+44h]
0x18004e6a3  movaps  xmmword ptr [rbp+0E0h], xmm0
0x18004e6aa  movups  xmm1, xmmword ptr [rbx+54h]
0x18004e6ae  movaps  [rbp+130h+var_48+8], xmm1
0x18004e6b5  movups  xmm0, xmmword ptr [rbx+64h]
0x18004e6b9  movaps  [rbp+130h+var_38+8], xmm0
0x18004e6c0  movsd   xmm1, qword ptr [rbx+74h]
0x18004e6c5  movsd   [rbp+130h+var_20], xmm1
0x18004e6cd  mov     eax, [rbx+7Ch]
0x18004e6d0  mov     [rbp+130h+var_18], eax
0x18004e6d6  xor     eax, eax
0x18004e6d8  xchg    eax, [rbx]
0x18004e6da  test    cl, cl
0x18004e6dc  jnz     loc_18004E7F6
0x18004e6e2  mov     ecx, 1
0x18004e6e7  mov     eax, ecx
0x18004e6e9  xchg    eax, [rbx]
0x18004e6eb  test    eax, eax
0x18004e6ed  jz      short loc_18004E724
0x18004e6ef  nop
0x18004e6f0  mov     eax, [rbx]
0x18004e6f2  test    eax, eax
0x18004e6f4  jz      short loc_18004E719
0x18004e6f6  mov     eax, ecx
0x18004e6f8  test    ecx, ecx
0x18004e6fa  jz      short loc_18004E711
0x18004e6fc  nop     dword ptr [rax+00h]
0x18004e700  pause
0x18004e702  sub     eax, 1
0x18004e705  jnz     short loc_18004E700
0x18004e707  cmp     ecx, 40h ; '@'
0x18004e70a  jl      short loc_18004E711
0x18004e70c  lea     ecx, [rax+40h]
0x18004e70f  jmp     short loc_18004E713
0x18004e711  add     ecx, ecx
0x18004e713  mov     eax, [rbx]
0x18004e715  test    eax, eax
0x18004e717  jnz     short loc_18004E6F6
0x18004e719  mov     eax, 1
0x18004e71e  xchg    eax, [rbx]
0x18004e720  test    eax, eax
0x18004e722  jnz     short loc_18004E6F0
0x18004e724  movups  xmm0, xmmword ptr [rbx+4]
0x18004e728  movaps  [rbp+130h+var_110], xmm0
0x18004e72c  movups  xmm1, xmmword ptr [rbx+14h]
0x18004e730  movaps  [rbp+130h+var_100], xmm1
0x18004e734  movups  xmm0, xmmword ptr [rbx+24h]
0x18004e738  movaps  [rbp+130h+var_F0], xmm0
0x18004e73c  movups  xmm1, xmmword ptr [rbx+34h]
0x18004e740  movaps  [rbp+130h+var_E0], xmm1
0x18004e744  movups  xmm0, xmmword ptr [rbx+44h]
0x18004e748  movaps  [rbp+130h+var_D0], xmm0
0x18004e74c  movups  xmm1, xmmword ptr [rbx+54h]
0x18004e750  movaps  [rbp+130h+var_C0], xmm1
0x18004e754  movups  xmm0, xmmword ptr [rbx+64h]
0x18004e758  movaps  [rbp+130h+var_B0], xmm0
0x18004e75f  movsd   xmm1, qword ptr [rbx+74h]
0x18004e764  movsd   [rbp+130h+var_A0], xmm1
0x18004e76c  mov     eax, [rbx+7Ch]
0x18004e76f  mov     [rbp+130h+var_98], eax
0x18004e775  xor     eax, eax
0x18004e777  xchg    eax, [rbx]
0x18004e779  movaps  xmm2, [rbp+130h+var_110]
0x18004e77d  movaps  [rbp+130h+Buf2], xmm2
0x18004e784  movaps  xmm0, [rbp+130h+var_100]
0x18004e788  movaps  [rbp+130h+var_80], xmm0
0x18004e78f  movaps  xmm1, [rbp+130h+var_F0]
0x18004e793  movaps  [rbp+130h+var_70], xmm1
0x18004e79a  movaps  xmm0, [rbp+130h+var_E0]
0x18004e79e  movaps  [rbp+130h+var_60], xmm0
0x18004e7a5  movaps  xmm1, [rbp+130h+var_D0]
0x18004e7a9  movaps  xmmword ptr [rbp+0E0h], xmm1
0x18004e7b0  movaps  xmm0, [rbp+130h+var_C0]
0x18004e7b4  movaps  [rbp+130h+var_48+8], xmm0
0x18004e7bb  movaps  xmm1, [rbp+130h+var_B0]
0x18004e7c2  movaps  [rbp+130h+var_38+8], xmm1
0x18004e7c9  movsd   xmm0, [rbp+130h+var_A0]
0x18004e7d1  movsd   [rbp+130h+var_20], xmm0
0x18004e7d9  mov     eax, [rbp+130h+var_98]
0x18004e7df  mov     [rbp+130h+var_18], eax
0x18004e7e5  movss   xmm0, dword ptr [rsp+230h+var_210]
0x18004e7eb  comiss  xmm0, xmm2
0x18004e7ee  ja      loc_18004E5C2
0x18004e7f4  jmp     short loc_18004E85F
0x18004e7f6  movaps  xmm0, [rbp+130h+Buf2]
0x18004e7fd  movaps  [rsp+230h+var_210], xmm0
0x18004e802  movaps  xmm1, [rbp+130h+var_80]
0x18004e809  movaps  [rsp+230h+var_200], xmm1
0x18004e80e  movaps  xmm0, [rbp+130h+var_70]
0x18004e815  movaps  [rsp+230h+var_1F0], xmm0
0x18004e81a  movaps  xmm1, [rbp+130h+var_60]
0x18004e821  movaps  [rsp+230h+var_1E0], xmm1
0x18004e826  movaps  xmm0, xmmword ptr [rbp+0E0h]
0x18004e82d  movaps  [rsp+230h+var_1D0], xmm0
0x18004e832  movaps  xmm1, [rbp+130h+var_48+8]
0x18004e839  movaps  [rsp+230h+var_1C0], xmm1
0x18004e83e  movaps  xmm0, [rbp+130h+var_38+8]
0x18004e845  movaps  [rbp+130h+var_1B0], xmm0
0x18004e849  movsd   xmm1, [rbp+130h+var_20]
0x18004e851  movsd   [rbp+130h+var_1A0], xmm1
0x18004e856  mov     eax, [rbp+130h+var_18]
0x18004e85c  mov     [rbp+130h+var_198], eax
0x18004e85f  sub     rbx, 0FFFFFFFFFFFFFF80h
0x18004e863  sub     rsi, 1
0x18004e867  jnz     loc_18004E4C0
0x18004e86d  mov     rcx, [rbp+130h+var_10]
0x18004e874  xor     rcx, rsp; StackCookie
0x18004e877  call    __security_check_cookie
0x18004e87c  lea     r11, [rsp+230h+var_s0]
0x18004e884  mov     rbx, [r11+18h]
0x18004e888  mov     rsi, [r11+20h]
0x18004e88c  mov     rdi, [r11+28h]
0x18004e890  mov     rsp, r11
0x18004e893  pop     rbp
0x18004e894  retn
```
