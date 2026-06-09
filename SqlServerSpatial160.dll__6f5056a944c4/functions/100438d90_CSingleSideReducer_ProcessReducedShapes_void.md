# CSingleSideReducer::ProcessReducedShapes(void)

- ea: `0x100438d90`
- end: `0x100438fb9`
- name: `?ProcessReducedShapes@CSingleSideReducer@@AEAAJXZ`
- size: `553`
- prototype: `__int64 __fastcall(CSingleSideReducer *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x100437850`

## callees

- `0x100438d90`

## pseudocode

```c
__int64 __fastcall CSingleSideReducer::ProcessReducedShapes(CSingleSideReducer *this)
{
  unsigned int v2; // r8d
  unsigned int i; // r15d
  int v4; // eax
  unsigned int v5; // r9d
  int v6; // ecx
  __int64 v7; // r14
  __int64 result; // rax
  unsigned int j; // ebp
  int v10; // eax
  unsigned int v11; // r8d
  int v12; // ecx
  __int64 v13; // rax
  __int64 v14; // r8
  __int64 v15; // rdi
  __int64 v16; // rbx
  unsigned int v17; // edx
  unsigned int v18; // r8d
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int128 v21; // xmm1
  __int64 v22; // r9
  __int64 v23; // rcx
  _QWORD *v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // r9
  __int64 v27; // r8
  __int64 v28; // r9
  __int64 v29; // rdx

  v2 = 0;
  for ( i = 0; ; ++i )
  {
    v4 = *((_DWORD *)this + 33);
    v5 = *((_DWORD *)this + 37);
    v6 = v4 - 1;
    if ( !v4 )
      v6 = 0;
    if ( i >= *((_DWORD *)this + 36) + v5 * v6 )
      break;
    v7 = *(_QWORD *)(*((_QWORD *)this + 17) + 8LL * (i / v5)) + 72LL * (i % v5);
    if ( !*(_BYTE *)v7 )
    {
      result = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 5) + 8LL))(*((_QWORD *)this + 5), 4);
      if ( (int)result < 0 )
        goto LABEL_29;
      for ( j = 0; ; ++j )
      {
        v10 = *(_DWORD *)(v7 + 20);
        v11 = *(_DWORD *)(v7 + 36);
        v12 = v10 - 1;
        if ( !v10 )
          v12 = 0;
        if ( j >= *(_DWORD *)(v7 + 32) + v11 * v12 )
          break;
        v13 = j / v11;
        v14 = j % v11;
        v15 = 56 * v14;
        v16 = *(_QWORD *)(*(_QWORD *)(v7 + 24) + 8 * v13);
        if ( !*(_BYTE *)(v16 + 56 * v14 + 1) )
        {
          if ( *(_BYTE *)(v16 + 56 * v14) == (j != 0) )
          {
            v17 = *(_DWORD *)(v16 + v15 + 48);
            v18 = 0;
            if ( (v17 & 0xFFFFFFFE) != 0 )
            {
              do
              {
                v19 = *(_QWORD *)(v16 + v15 + 32);
                v20 = 2LL * (v17 - v18 - 1);
                v21 = *(_OWORD *)(v19 + 16LL * v18);
                *(_OWORD *)(v19 + 16LL * v18) = *(_OWORD *)(v19 + 8 * v20);
                *(_OWORD *)(v19 + 8 * v20) = v21;
                v22 = *(_QWORD *)(v16 + v15 + 40);
                if ( v22 )
                {
                  v23 = *(_QWORD *)(v22 + 8LL * v18);
                  v24 = (_QWORD *)(v22 + 8LL * (*(_DWORD *)(v16 + v15 + 48) - v18 - 1));
                  *(_QWORD *)(v22 + 8LL * v18) = *v24;
                  *v24 = v23;
                }
                v17 = *(_DWORD *)(v16 + v15 + 48);
                ++v18;
              }
              while ( v18 < v17 >> 1 );
            }
          }
          v25 = *(unsigned int *)(v16 + v15 + 48);
          v26 = *((_BYTE *)this + 16) ? *(_QWORD *)(v16 + v15 + 40) + 8LL * (unsigned int)(v25 - 1) : 0LL;
          v27 = 16LL * (unsigned int)(v25 - 1);
          LOBYTE(v25) = 1;
          result = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64))(**((_QWORD **)this + 5) + 32LL))(
                     *((_QWORD *)this + 5),
                     v25,
                     *(_QWORD *)(v16 + v15 + 32) + v27,
                     v26);
          if ( (int)result < 0 )
            goto LABEL_29;
          v28 = *((_BYTE *)this + 16) ? *(_QWORD *)(v16 + v15 + 40) : 0LL;
          result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(**((_QWORD **)this + 5) + 40LL))(
                     *((_QWORD *)this + 5),
                     *(_QWORD *)(v16 + v15 + 32),
                     *(unsigned int *)(v16 + v15 + 48),
                     v28);
          if ( (int)result < 0 )
            goto LABEL_29;
          LOBYTE(v29) = 1;
          result = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 5) + 56LL))(
                     *((_QWORD *)this + 5),
                     v29);
          if ( (int)result < 0 )
            goto LABEL_29;
        }
      }
      result = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 5) + 16LL))(*((_QWORD *)this + 5), 4);
      v2 = result;
      if ( (int)result < 0 )
      {
LABEL_29:
        _mm_lfence();
        return result;
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x100438d90  mov     [rsp+arg_0], rbx
0x100438d95  mov     [rsp+arg_8], rbp
0x100438d9a  mov     [rsp+arg_10], rsi
0x100438d9f  mov     [rsp+arg_18], rdi
0x100438da4  push    r12
0x100438da6  push    r14
0x100438da8  push    r15
0x100438daa  sub     rsp, 20h
0x100438dae  xor     r12d, r12d
0x100438db1  mov     rsi, rcx
0x100438db4  mov     r8d, r12d
0x100438db7  mov     r15d, r12d
0x100438dba  nop     word ptr [rax+rax+00h]
0x100438dc0  mov     eax, [rsi+84h]
0x100438dc6  test    eax, eax
0x100438dc8  mov     r9d, [rsi+94h]
0x100438dcf  lea     ecx, [rax-1]
0x100438dd2  cmovz   ecx, r12d
0x100438dd6  imul    ecx, r9d
0x100438dda  add     ecx, [rsi+90h]
0x100438de0  cmp     r15d, ecx
0x100438de3  jnb     loc_100438F97
0x100438de9  xor     edx, edx
0x100438deb  mov     eax, r15d
0x100438dee  div     r9d
0x100438df1  mov     ecx, edx
0x100438df3  mov     edx, eax
0x100438df5  mov     rax, [rsi+88h]
0x100438dfc  lea     rcx, [rcx+rcx*8]
0x100438e00  mov     rax, [rax+rdx*8]
0x100438e04  cmp     [rax+rcx*8], r12b
0x100438e08  lea     r14, [rax+rcx*8]
0x100438e0c  jnz     loc_100438F8A
0x100438e12  mov     rcx, [rsi+28h]
0x100438e16  xor     r8d, r8d
0x100438e19  mov     rax, [rcx]
0x100438e1c  lea     edx, [r8+4]
0x100438e20  call    qword ptr [rax+8]
0x100438e23  test    eax, eax
0x100438e25  js      loc_100438F92
0x100438e2b  mov     ebp, r12d
0x100438e2e  xchg    ax, ax
0x100438e30  mov     eax, [r14+14h]
0x100438e34  test    eax, eax
0x100438e36  mov     r8d, [r14+24h]
0x100438e3a  lea     ecx, [rax-1]
0x100438e3d  cmovz   ecx, r12d
0x100438e41  imul    ecx, r8d
0x100438e45  add     ecx, [r14+20h]
0x100438e49  cmp     ebp, ecx
0x100438e4b  jnb     loc_100438F74
0x100438e51  mov     rbx, [r14+18h]
0x100438e55  xor     edx, edx
0x100438e57  mov     eax, ebp
0x100438e59  div     r8d
0x100438e5c  mov     r8d, edx
0x100438e5f  imul    rdi, r8, 38h ; '8'
0x100438e63  mov     rbx, [rbx+rax*8]
0x100438e67  cmp     [rbx+rdi+1], r12b
0x100438e6c  jnz     loc_100438F6D
0x100438e72  movzx   eax, byte ptr [rbx+rdi]
0x100438e76  test    ebp, ebp
0x100438e78  mov     ecx, r12d
0x100438e7b  setnz   cl
0x100438e7e  cmp     eax, ecx
0x100438e80  jnz     short loc_100438EFC
0x100438e82  mov     edx, [rbx+rdi+30h]
0x100438e86  mov     r8d, r12d
0x100438e89  test    edx, 0FFFFFFFEh
0x100438e8f  jbe     short loc_100438EFC
0x100438e91  nop     dword ptr [rax+00h]
0x100438e95  nop     word ptr [rax+rax+00000000h]
0x100438ea0  mov     rcx, [rbx+rdi+20h]
0x100438ea5  sub     edx, r8d
0x100438ea8  dec     edx
0x100438eaa  mov     eax, r8d
0x100438ead  add     rdx, rdx
0x100438eb0  mov     r10d, r8d
0x100438eb3  add     rax, rax
0x100438eb6  movups  xmm0, xmmword ptr [rcx+rdx*8]
0x100438eba  movups  xmm1, xmmword ptr [rcx+rax*8]
0x100438ebe  movups  xmmword ptr [rcx+rax*8], xmm0
0x100438ec2  movups  xmmword ptr [rcx+rdx*8], xmm1
0x100438ec6  mov     r9, [rbx+rdi+28h]
0x100438ecb  test    r9, r9
0x100438ece  jz      short loc_100438EEC
0x100438ed0  mov     eax, [rbx+rdi+30h]
0x100438ed4  mov     rcx, [r9+r10*8]
0x100438ed8  sub     eax, r8d
0x100438edb  dec     eax
0x100438edd  lea     rdx, [r9+rax*8]
0x100438ee1  mov     rax, [r9+rax*8]
0x100438ee5  mov     [r9+r10*8], rax
0x100438ee9  mov     [rdx], rcx
0x100438eec  mov     edx, [rbx+rdi+30h]
0x100438ef0  inc     r8d
0x100438ef3  mov     eax, edx
0x100438ef5  shr     eax, 1
0x100438ef7  cmp     r8d, eax
0x100438efa  jb      short loc_100438EA0
0x100438efc  mov     edx, [rbx+rdi+30h]
0x100438f00  cmp     [rsi+10h], r12b
0x100438f04  jz      short loc_100438F14
0x100438f06  mov     rax, [rbx+rdi+28h]
0x100438f0b  lea     ecx, [rdx-1]
0x100438f0e  lea     r9, [rax+rcx*8]
0x100438f12  jmp     short loc_100438F17
0x100438f14  mov     r9, r12
0x100438f17  mov     rcx, [rsi+28h]
0x100438f1b  lea     r8d, [rdx-1]
0x100438f1f  shl     r8, 4
0x100438f23  mov     dl, 1
0x100438f25  add     r8, [rbx+rdi+20h]
0x100438f2a  mov     r10, [rcx]
0x100438f2d  call    qword ptr [r10+20h]
0x100438f31  test    eax, eax
0x100438f33  js      short loc_100438F92
0x100438f35  cmp     [rsi+10h], r12b
0x100438f39  jz      short loc_100438F42
0x100438f3b  mov     r9, [rbx+rdi+28h]
0x100438f40  jmp     short loc_100438F45
0x100438f42  mov     r9, r12
0x100438f45  mov     rcx, [rsi+28h]
0x100438f49  mov     r8d, [rbx+rdi+30h]
0x100438f4e  mov     rdx, [rbx+rdi+20h]
0x100438f53  mov     rax, [rcx]
0x100438f56  call    qword ptr [rax+28h]
0x100438f59  test    eax, eax
0x100438f5b  js      short loc_100438F92
0x100438f5d  mov     rcx, [rsi+28h]
0x100438f61  mov     dl, 1
0x100438f63  mov     rax, [rcx]
0x100438f66  call    qword ptr [rax+38h]
0x100438f69  test    eax, eax
0x100438f6b  js      short loc_100438F92
0x100438f6d  inc     ebp
0x100438f6f  jmp     loc_100438E30
0x100438f74  mov     rcx, [rsi+28h]
0x100438f78  mov     edx, 4
0x100438f7d  mov     rax, [rcx]
0x100438f80  call    qword ptr [rax+10h]
0x100438f83  mov     r8d, eax
0x100438f86  test    eax, eax
0x100438f88  js      short loc_100438F92
0x100438f8a  inc     r15d
0x100438f8d  jmp     loc_100438DC0
0x100438f92  lfence
0x100438f95  jmp     short loc_100438F9A
0x100438f97  mov     eax, r8d
0x100438f9a  mov     rbx, [rsp+38h+arg_0]
0x100438f9f  mov     rbp, [rsp+38h+arg_8]
0x100438fa4  mov     rsi, [rsp+38h+arg_10]
0x100438fa9  mov     rdi, [rsp+38h+arg_18]
0x100438fae  add     rsp, 20h
0x100438fb2  pop     r15
0x100438fb4  pop     r14
0x100438fb6  pop     r12
0x100438fb8  retn
```
