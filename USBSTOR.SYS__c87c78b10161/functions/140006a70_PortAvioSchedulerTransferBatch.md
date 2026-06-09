# PortAvioSchedulerTransferBatch

- ea: `0x140006a70`
- end: `0x140006fe3`
- name: `PortAvioSchedulerTransferBatch`
- size: `1395`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1400036f0`
- `0x140006910`

## callees

- `0x140006a70`
- `0x140008288`
- `0x14000acd0`
- `0x14000ae10`
- `0x1400105e8`
- `0x140010664`
- `0x140013714`

## pseudocode

```c
__int64 __fastcall PortAvioSchedulerTransferBatch(__int64 a1, _QWORD *a2, _QWORD *m)
{
  unsigned int v4; // r15d
  __int64 *v5; // rdi
  unsigned int i; // esi
  int v7; // eax
  unsigned int v8; // esi
  unsigned int v9; // ebp
  int j; // edi
  __int64 v11; // r10
  unsigned int k; // ebx
  _QWORD *v13; // r11
  __int64 v14; // rcx
  _QWORD *v15; // rax
  __int64 v16; // rax
  int v17; // ecx
  _QWORD *n; // rax
  _QWORD *v19; // rcx
  unsigned __int64 v20; // rax
  unsigned __int64 v21; // rcx
  unsigned __int64 v22; // r9
  __int64 v23; // rax
  __int64 *v24; // rbx
  unsigned int ii; // esi
  unsigned int v26; // ebx
  unsigned int v27; // ebx
  _QWORD *v29; // rax
  _QWORD *v30; // rax
  unsigned int v31; // r11d
  unsigned int v32; // ebp
  _QWORD *v33; // rax
  unsigned int v34; // r11d
  int v35; // r9d
  unsigned int v36; // r11d
  unsigned int v37; // ebp
  _QWORD *v38; // rax
  unsigned int v39; // r11d

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_((__int64)WPP_GLOBAL_Control->AttachedDevice, 0xAu, (__int64)WPP_256a4584ee4438b757ec1546b7dd7507_Traceguids);
  if ( *(_DWORD *)(a1 + 4) )
  {
    v4 = *(_DWORD *)a1;
    if ( *(_DWORD *)a1 )
    {
      v5 = *(__int64 **)(a1 + 16);
      for ( i = 0; v5 != (__int64 *)(a1 + 16); v5 = (__int64 *)*v5 )
      {
        if ( i >= v4 )
          break;
        v31 = *((_DWORD *)v5 + 4);
        if ( v31 >= v4 - i )
          v31 = v4 - i;
        v32 = 0;
        if ( v31 )
        {
          do
          {
            v33 = PortListRemoveNextRequest((__int64)(v5 + 3));
            if ( !v33 )
              break;
            PortListInsertRequest(a1 + 32, v33);
            ++i;
            ++v32;
          }
          while ( v32 < v34 );
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_qDD(WPP_GLOBAL_Control->AttachedDevice, a2, m, v5, v32, *((_DWORD *)v5 + 12));
      }
      v4 -= i;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_d(
          (__int64)WPP_GLOBAL_Control->AttachedDevice,
          0xCu,
          (__int64)WPP_256a4584ee4438b757ec1546b7dd7507_Traceguids,
          i);
      if ( v4 )
      {
        if ( *(_DWORD *)(a1 + 12) < 0x64u )
          goto LABEL_14;
        v7 = TransferStarvedRequests(a1, v4);
        v4 -= v7;
        if ( v7 )
          *(_DWORD *)(a1 + 12) = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_d(
            (__int64)WPP_GLOBAL_Control->AttachedDevice,
            0xDu,
            (__int64)WPP_256a4584ee4438b757ec1546b7dd7507_Traceguids,
            v7);
        if ( v4 )
        {
LABEL_14:
          v8 = 0;
          v9 = v4;
          for ( j = 3; j > 0; --j )
          {
            a2 = (_QWORD *)(a1 + 32);
            v11 = a1 + 56LL * (unsigned int)(j - 1) + 88;
            for ( k = 0; *(_QWORD *)v11 != v11 && k < v9; ++k )
            {
              v13 = *(_QWORD **)(v11 + 16);
              *(_QWORD *)(v11 + 16) = *v13;
              *(_QWORD *)(v11 + 40) = v13[2] + 1LL;
              v14 = *v13;
              if ( *(_QWORD **)(*v13 + 8LL) != v13 )
                goto LABEL_54;
              v15 = (_QWORD *)v13[1];
              if ( (_QWORD *)*v15 != v13 )
                goto LABEL_54;
              *v15 = v14;
              *(_QWORD *)(v14 + 8) = v15;
              v16 = *(_QWORD *)(v11 + 32);
              --*(_DWORD *)(v11 + 24);
              if ( v16 )
                --*(_DWORD *)(v16 + 4);
              if ( *(_QWORD *)(v11 + 16) == v11 )
                *(_QWORD *)(v11 + 16) = *(_QWORD *)v11;
              v17 = *(_DWORD *)(a1 + 80);
              if ( v17 )
              {
                if ( v17 == 2 )
                {
                  for ( m = (_QWORD *)*a2; m != a2; m = (_QWORD *)*m )
                  {
                    v35 = 0;
                    while ( *((_DWORD *)v13 + (unsigned int)(1 - v35) + 4) == *((_DWORD *)m + (unsigned int)(1 - v35)
                                                                                            + 4) )
                    {
                      if ( (unsigned int)++v35 >= 2 )
                      {
                        if ( v35 == 2 )
                          goto LABEL_84;
                        break;
                      }
                    }
                    if ( *((_DWORD *)v13 + (unsigned int)(1 - v35) + 4) <= *((_DWORD *)m + (unsigned int)(1 - v35) + 4) )
                      break;
LABEL_84:
                    ;
                  }
                  v30 = (_QWORD *)m[1];
                  if ( (_QWORD *)*v30 != m )
LABEL_54:
                    __fastfail(3u);
                  *v13 = m;
                  v13[1] = v30;
                  *v30 = v13;
                  m[1] = v13;
                  *(_QWORD *)(a1 + 48) = *(_QWORD *)(a1 + 32);
                }
                else
                {
                  v29 = *(_QWORD **)(a1 + 40);
                  if ( (_QWORD *)*v29 != a2 )
                    goto LABEL_54;
                  *v13 = a2;
                  v13[1] = v29;
                  *v29 = v13;
                  *(_QWORD *)(a1 + 40) = v13;
                  *(_QWORD *)(a1 + 48) = *(_QWORD *)(a1 + 32);
                }
              }
              else
              {
                for ( n = (_QWORD *)*a2; n != a2; n = (_QWORD *)*n )
                {
                  if ( v13[2] < n[2] )
                    break;
                }
                v19 = (_QWORD *)n[1];
                if ( (_QWORD *)*v19 != n )
                  goto LABEL_54;
                *v13 = n;
                v13[1] = v19;
                *v19 = v13;
                n[1] = v13;
                m = *(_QWORD **)(a1 + 48);
                if ( m == a2 )
                {
                  *(_QWORD *)(a1 + 48) = *(_QWORD *)(a1 + 32);
                }
                else
                {
                  v20 = *(_QWORD *)(a1 + 72);
                  v21 = v13[2];
                  if ( v21 >= v20 )
                  {
                    v22 = m[2];
                    if ( v21 < v22 || v22 < v20 )
                      *(_QWORD *)(a1 + 48) = v13;
                  }
                }
              }
              v23 = *(_QWORD *)(a1 + 64);
              ++*(_DWORD *)(a1 + 56);
              if ( v23 )
                ++*(_DWORD *)(v23 + 4);
            }
            v8 += k;
            if ( v8 >= v4 )
              break;
            v9 -= k;
          }
          v4 -= v8;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            WPP_SF_d(
              (__int64)WPP_GLOBAL_Control->AttachedDevice,
              0xEu,
              (__int64)WPP_256a4584ee4438b757ec1546b7dd7507_Traceguids,
              v8);
          }
          if ( v4 )
          {
            v24 = *(__int64 **)(a1 + 16);
            for ( ii = 0; v24 != (__int64 *)(a1 + 16); v24 = (__int64 *)*v24 )
            {
              if ( ii >= v4 )
                break;
              v36 = *((_DWORD *)v24 + 4);
              if ( v36 >= v4 - ii )
                v36 = v4 - ii;
              v37 = 0;
              if ( v36 )
              {
                do
                {
                  v38 = PortListRemoveNextRequest((__int64)(v24 + 3));
                  if ( !v38 )
                    break;
                  PortListInsertRequest(a1 + 32, v38);
                  ++ii;
                  ++v37;
                }
                while ( v37 < v39 );
              }
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
              {
                WPP_SF_qDD(WPP_GLOBAL_Control->AttachedDevice, a2, m, v24, v37, *((_DWORD *)v24 + 12));
              }
            }
            v4 -= ii;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              WPP_SF_d(
                (__int64)WPP_GLOBAL_Control->AttachedDevice,
                0xFu,
                (__int64)WPP_256a4584ee4438b757ec1546b7dd7507_Traceguids,
                ii);
            }
          }
        }
      }
    }
    v26 = *(_DWORD *)a1;
    *(_DWORD *)(a1 + 12) += *(_DWORD *)a1 - v4;
    v27 = v26 - v4;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x10u,
        (__int64)WPP_256a4584ee4438b757ec1546b7dd7507_Traceguids,
        v27);
    return v27;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0xBu,
        (__int64)WPP_256a4584ee4438b757ec1546b7dd7507_Traceguids,
        0);
    return 0;
  }
}

```

## disassembly

```asm
0x140006a70  push    r12
0x140006a72  push    r13
0x140006a74  sub     rsp, 48h
0x140006a78  mov     r12, rcx
0x140006a7b  mov     rcx, cs:WPP_GLOBAL_Control
0x140006a82  lea     r13, WPP_GLOBAL_Control
0x140006a89  cmp     rcx, r13
0x140006a8c  jnz     loc_140006CFD
0x140006a92  cmp     dword ptr [r12+4], 0
0x140006a98  jz      loc_140006D8B
0x140006a9e  mov     [rsp+58h+arg_0], rbx
0x140006aa3  mov     [rsp+58h+arg_8], rbp
0x140006aa8  mov     [rsp+58h+arg_10], rsi
0x140006aad  mov     [rsp+58h+var_18], rdi
0x140006ab2  mov     [rsp+58h+var_20], r14
0x140006ab7  mov     [rsp+58h+var_28], r15
0x140006abc  mov     r15d, [r12]
0x140006ac0  test    r15d, r15d
0x140006ac3  jz      loc_140006CB6
0x140006ac9  mov     rdi, [r12+10h]
0x140006ace  lea     rbx, [r12+10h]
0x140006ad3  xor     esi, esi
0x140006ad5  cmp     rdi, rbx
0x140006ad8  jnz     loc_140006E5B
0x140006ade  sub     r15d, esi
0x140006ae1  mov     rcx, cs:WPP_GLOBAL_Control
0x140006ae8  cmp     rcx, r13
0x140006aeb  jz      short loc_140006AF8
0x140006aed  mov     eax, [rcx+2Ch]
0x140006af0  test    al, 1
0x140006af2  jnz     loc_140006ED6
0x140006af8  test    r15d, r15d
0x140006afb  jz      loc_140006CB6
0x140006b01  cmp     dword ptr [r12+0Ch], 64h ; 'd'
0x140006b07  jb      short loc_140006B40
0x140006b09  mov     edx, r15d
0x140006b0c  mov     rcx, r12
0x140006b0f  call    TransferStarvedRequests
0x140006b14  sub     r15d, eax
0x140006b17  mov     r9d, eax
0x140006b1a  test    eax, eax
0x140006b1c  jz      short loc_140006B27
0x140006b1e  mov     dword ptr [r12+0Ch], 0
0x140006b27  mov     rcx, cs:WPP_GLOBAL_Control
0x140006b2e  cmp     rcx, r13
0x140006b31  jnz     loc_140006DA7
0x140006b37  test    r15d, r15d
0x140006b3a  jz      loc_140006CB6
0x140006b40  xor     esi, esi
0x140006b42  mov     ebp, r15d
0x140006b45  mov     edi, 3
0x140006b4a  nop     word ptr [rax+rax+00h]
0x140006b50  test    edi, edi
0x140006b52  jle     loc_140006C6F
0x140006b58  lea     ecx, [rdi-1]
0x140006b5b  imul    r10, rcx, 38h ; '8'
0x140006b5f  lea     rdx, [r12+20h]
0x140006b64  add     r10, 58h ; 'X'
0x140006b68  add     r10, r12
0x140006b6b  xor     ebx, ebx
0x140006b6d  cmp     [r10], r10
0x140006b70  jz      loc_140006C5F
0x140006b76  cmp     ebx, ebp
0x140006b78  jnb     loc_140006C5F
0x140006b7e  mov     r11, [r10+10h]
0x140006b82  mov     rax, [r11]
0x140006b85  mov     [r10+10h], rax
0x140006b89  mov     rax, [r11+10h]
0x140006b8d  inc     rax
0x140006b90  mov     [r10+28h], rax
0x140006b94  mov     rcx, [r11]
0x140006b97  cmp     [rcx+8], r11
0x140006b9b  jnz     loc_140006D7B
0x140006ba1  mov     rax, [r11+8]
0x140006ba5  cmp     [rax], r11
0x140006ba8  jnz     loc_140006D7B
0x140006bae  mov     [rax], rcx
0x140006bb1  mov     [rcx+8], rax
0x140006bb5  mov     rax, [r10+20h]
0x140006bb9  dec     dword ptr [r10+18h]
0x140006bbd  test    rax, rax
0x140006bc0  jz      short loc_140006BC5
0x140006bc2  dec     dword ptr [rax+4]
0x140006bc5  cmp     [r10+10h], r10
0x140006bc9  jnz     short loc_140006BD2
0x140006bcb  mov     rax, [r10]
0x140006bce  mov     [r10+10h], rax
0x140006bd2  mov     ecx, [rdx+30h]
0x140006bd5  test    ecx, ecx
0x140006bd7  jnz     loc_140006EF3
0x140006bdd  mov     rax, [rdx]
0x140006be0  cmp     rax, rdx
0x140006be3  jz      short loc_140006BFE
0x140006be5  mov     rcx, [r11+10h]
0x140006be9  nop     dword ptr [rax+00000000h]
0x140006bf0  cmp     rcx, [rax+10h]
0x140006bf4  jb      short loc_140006BFE
0x140006bf6  mov     rax, [rax]
0x140006bf9  cmp     rax, rdx
0x140006bfc  jnz     short loc_140006BF0
0x140006bfe  mov     rcx, [rax+8]
0x140006c02  cmp     [rcx], rax
0x140006c05  jnz     loc_140006D7B
0x140006c0b  mov     [r11], rax
0x140006c0e  mov     [r11+8], rcx
0x140006c12  mov     [rcx], r11
0x140006c15  mov     [rax+8], r11
0x140006c19  mov     r8, [rdx+10h]
0x140006c1d  cmp     r8, rdx
0x140006c20  jz      loc_140006D6F
0x140006c26  mov     rax, [rdx+28h]
0x140006c2a  mov     rcx, [r11+10h]
0x140006c2e  cmp     rcx, rax
0x140006c31  jb      short loc_140006C49
0x140006c33  mov     r9, [r8+10h]
0x140006c37  cmp     rcx, r9
0x140006c3a  jb      loc_140006D82
0x140006c40  cmp     r9, rax
0x140006c43  jb      loc_140006D82
0x140006c49  mov     rax, [rdx+20h]
0x140006c4d  inc     dword ptr [rdx+18h]
0x140006c50  test    rax, rax
0x140006c53  jz      short loc_140006C58
0x140006c55  inc     dword ptr [rax+4]
0x140006c58  inc     ebx
0x140006c5a  jmp     loc_140006B6D
0x140006c5f  add     esi, ebx
0x140006c61  cmp     esi, r15d
0x140006c64  jnb     short loc_140006C6F
0x140006c66  sub     ebp, ebx
0x140006c68  dec     edi
0x140006c6a  jmp     loc_140006B50
0x140006c6f  sub     r15d, esi
0x140006c72  mov     rcx, cs:WPP_GLOBAL_Control
0x140006c79  cmp     rcx, r13
0x140006c7c  jnz     loc_140006D22
0x140006c82  test    r15d, r15d
0x140006c85  jz      short loc_140006CB6
0x140006c87  mov     rbx, [r12+10h]
0x140006c8c  lea     rdi, [r12+10h]
0x140006c91  xor     esi, esi
0x140006c93  cmp     rbx, rdi
0x140006c96  jnz     loc_140006F68
0x140006c9c  sub     r15d, esi
0x140006c9f  mov     rcx, cs:WPP_GLOBAL_Control
0x140006ca6  cmp     rcx, r13
0x140006ca9  jz      short loc_140006CB6
0x140006cab  mov     eax, [rcx+2Ch]
0x140006cae  test    al, 1
0x140006cb0  jnz     loc_140006DCC
0x140006cb6  mov     ebx, [r12]
0x140006cba  mov     eax, ebx
0x140006cbc  sub     eax, r15d
0x140006cbf  add     [r12+0Ch], eax
0x140006cc4  sub     ebx, r15d
0x140006cc7  mov     rcx, cs:WPP_GLOBAL_Control
0x140006cce  cmp     rcx, r13
0x140006cd1  jnz     short loc_140006D4A
0x140006cd3  mov     r14, [rsp+58h+var_20]
0x140006cd8  mov     eax, ebx
0x140006cda  mov     rbx, [rsp+58h+arg_0]
0x140006cdf  mov     rdi, [rsp+58h+var_18]
0x140006ce4  mov     rsi, [rsp+58h+arg_10]
0x140006ce9  mov     rbp, [rsp+58h+arg_8]
0x140006cee  mov     r15, [rsp+58h+var_28]
0x140006cf3  add     rsp, 48h
0x140006cf7  pop     r13
0x140006cf9  pop     r12
0x140006cfb  retn
0x140006cfd  mov     eax, [rcx+2Ch]
0x140006d00  test    al, 1
0x140006d02  jz      loc_140006A92
0x140006d08  mov     rcx, [rcx+18h]
0x140006d0c  lea     r8, WPP_256a4584ee4438b757ec1546b7dd7507_Traceguids
0x140006d13  mov     edx, 0Ah
0x140006d18  call    WPP_SF_
0x140006d1d  jmp     loc_140006A92
0x140006d22  mov     eax, [rcx+2Ch]
0x140006d25  test    al, 1
0x140006d27  jz      loc_140006C82
0x140006d2d  mov     rcx, [rcx+18h]
0x140006d31  lea     r8, WPP_256a4584ee4438b757ec1546b7dd7507_Traceguids
0x140006d38  mov     edx, 0Eh
0x140006d3d  mov     r9d, esi
0x140006d40  call    WPP_SF_d
0x140006d45  jmp     loc_140006C82
0x140006d4a  mov     edx, [rcx+2Ch]
0x140006d4d  test    dl, 1
0x140006d50  jz      short loc_140006CD3
0x140006d52  mov     rcx, [rcx+18h]
0x140006d56  lea     r8, WPP_256a4584ee4438b757ec1546b7dd7507_Traceguids
0x140006d5d  mov     edx, 10h
0x140006d62  mov     r9d, ebx
0x140006d65  call    WPP_SF_d
0x140006d6a  jmp     loc_140006CD3
0x140006d6f  mov     rax, [rdx]
0x140006d72  mov     [rdx+10h], rax
0x140006d76  jmp     loc_140006C49
0x140006d7b  mov     ecx, 3
0x140006d80  int     29h; Win8: RtlFailFast(ecx)
0x140006d82  mov     [rdx+10h], r11
0x140006d86  jmp     loc_140006C49
0x140006d8b  mov     rcx, cs:WPP_GLOBAL_Control
0x140006d92  cmp     rcx, r13
0x140006d95  jnz     loc_140006E33
0x140006d9b  xor     eax, eax
0x140006d9d  add     rsp, 48h
0x140006da1  pop     r13
0x140006da3  pop     r12
0x140006da5  retn
0x140006da7  mov     eax, [rcx+2Ch]
0x140006daa  test    al, 1
0x140006dac  jz      loc_140006B37
0x140006db2  mov     rcx, [rcx+18h]
0x140006db6  lea     r8, WPP_256a4584ee4438b757ec1546b7dd7507_Traceguids
0x140006dbd  mov     edx, 0Dh
0x140006dc2  call    WPP_SF_d
0x140006dc7  jmp     loc_140006B37
0x140006dcc  mov     rcx, [rcx+18h]
0x140006dd0  lea     r8, WPP_256a4584ee4438b757ec1546b7dd7507_Traceguids
0x140006dd7  mov     edx, 0Fh
0x140006ddc  mov     r9d, esi
0x140006ddf  call    WPP_SF_d
0x140006de4  jmp     loc_140006CB6
0x140006de9  mov     rax, [rdx+8]
0x140006ded  cmp     [rax], rdx
0x140006df0  jnz     short loc_140006D7B
0x140006df2  mov     [r11], rdx
0x140006df5  mov     [r11+8], rax
0x140006df9  mov     [rax], r11
0x140006dfc  mov     [rdx+8], r11
0x140006e00  mov     rax, [rdx]
0x140006e03  mov     [rdx+10h], rax
0x140006e07  jmp     loc_140006C49
0x140006e0c  mov     rax, [r8+8]
0x140006e10  cmp     [rax], r8
0x140006e13  jnz     loc_140006D7B
0x140006e19  mov     [r11], r8
0x140006e1c  mov     [r11+8], rax
0x140006e20  mov     [rax], r11
0x140006e23  mov     [r8+8], r11
0x140006e27  mov     rax, [rdx]
0x140006e2a  mov     [rdx+10h], rax
0x140006e2e  jmp     loc_140006C49
0x140006e33  mov     eax, [rcx+2Ch]
0x140006e36  test    al, 1
0x140006e38  jz      loc_140006D9B
0x140006e3e  mov     rcx, [rcx+18h]
0x140006e42  lea     r8, WPP_256a4584ee4438b757ec1546b7dd7507_Traceguids
0x140006e49  mov     edx, 0Bh
0x140006e4e  xor     r9d, r9d
0x140006e51  call    WPP_SF_d
0x140006e56  jmp     loc_140006D9B
0x140006e5b  cmp     esi, r15d
0x140006e5e  jnb     loc_140006ADE
0x140006e64  mov     r11d, [rdi+10h]
0x140006e68  mov     eax, r15d
0x140006e6b  sub     eax, esi
0x140006e6d  cmp     r11d, eax
0x140006e70  cmovnb  r11d, eax
0x140006e74  xor     ebp, ebp
0x140006e76  test    r11d, r11d
0x140006e79  jz      short loc_140006E9F
0x140006e7b  lea     rcx, [rdi+18h]
0x140006e7f  call    PortListRemoveNextRequest
0x140006e84  test    rax, rax
0x140006e87  jz      short loc_140006E9F
0x140006e89  lea     rcx, [r12+20h]
0x140006e8e  mov     rdx, rax
0x140006e91  call    PortListInsertRequest
0x140006e96  inc     esi
0x140006e98  inc     ebp
0x140006e9a  cmp     ebp, r11d
0x140006e9d  jb      short loc_140006E7B
0x140006e9f  mov     rcx, cs:WPP_GLOBAL_Control
0x140006ea6  cmp     rcx, r13
0x140006ea9  jz      short loc_140006EC9
0x140006eab  mov     eax, [rcx+2Ch]
0x140006eae  test    al, 1
0x140006eb0  jz      short loc_140006EC9
0x140006eb2  mov     eax, [rdi+30h]
0x140006eb5  mov     r9, rdi
0x140006eb8  mov     rcx, [rcx+18h]
0x140006ebc  mov     [rsp+58h+var_30], eax
0x140006ec0  mov     [rsp+58h+var_38], ebp
0x140006ec4  call    WPP_SF_qDD
0x140006ec9  mov     rdi, [rdi]
0x140006ecc  cmp     rdi, rbx
0x140006ecf  jnz     short loc_140006E5B
0x140006ed1  jmp     loc_140006ADE
0x140006ed6  mov     rcx, [rcx+18h]
0x140006eda  lea     r8, WPP_256a4584ee4438b757ec1546b7dd7507_Traceguids
0x140006ee1  mov     edx, 0Ch
0x140006ee6  mov     r9d, esi
0x140006ee9  call    WPP_SF_d
0x140006eee  jmp     loc_140006AF8
0x140006ef3  sub     ecx, 1
0x140006ef6  jz      loc_140006DE9
0x140006efc  cmp     ecx, 1
0x140006eff  jnz     loc_140006DE9
  ... truncated ...
```
