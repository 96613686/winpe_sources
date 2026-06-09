# CSingleSideReducer::AddLines(MglPoint<double> const *,uint,unsigned __int64 const *)

- ea: `0x100437d40`
- end: `0x100437f07`
- name: `?AddLines@CSingleSideReducer@@UEAAJPEBU?$MglPoint@N@@IPEB_K@Z`
- size: `455`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x100401210`
- `0x100437d40`

## pseudocode

```c
__int64 __fastcall CSingleSideReducer::AddLines(__int64 a1, const void *a2, unsigned int a3, const void *a4)
{
  __int64 v5; // rsi
  __int64 result; // rax
  int v9; // edi
  int v10; // eax
  __int64 v11; // r9
  int v12; // eax
  int v13; // ecx
  __int64 v14; // rbp
  __int64 v15; // r13
  unsigned int v16; // r8d
  __int64 v17; // rcx
  __int64 v18; // rax

  v5 = a3;
  result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 48) + 40LL))(a1 + 48);
  if ( (int)result < 0 )
  {
LABEL_14:
    _mm_lfence();
    return result;
  }
  if ( !*(_BYTE *)(a1 + 104) )
  {
    if ( !*(_BYTE *)(a1 + 106) )
    {
      _mm_lfence();
      return (*(__int64 (__fastcall **)(_QWORD, const void *, _QWORD, const void *))(**(_QWORD **)(a1 + 40) + 40LL))(
               *(_QWORD *)(a1 + 40),
               a2,
               (unsigned int)v5,
               a4);
    }
    goto LABEL_14;
  }
  _mm_lfence();
  v9 = 0;
  v10 = 0;
  if ( *(_DWORD *)(a1 + 132) )
  {
    _mm_lfence();
    v10 = *(_DWORD *)(a1 + 132) - 1;
  }
  v11 = *(_QWORD *)(*(_QWORD *)(a1 + 136)
                  + 8LL
                  * ((unsigned int)(v10 * *(_DWORD *)(a1 + 148) + *(_DWORD *)(a1 + 144) - 1)
                   / *(_DWORD *)(a1 + 148)))
      + 72LL * ((unsigned int)(v10 * *(_DWORD *)(a1 + 148) + *(_DWORD *)(a1 + 144) - 1) % *(_DWORD *)(a1 + 148));
  v12 = *(_DWORD *)(v11 + 20);
  v13 = v12 - 1;
  if ( !v12 )
    v13 = 0;
  v14 = *(_QWORD *)(*(_QWORD *)(v11 + 24)
                  + 8LL
                  * ((unsigned int)(*(_DWORD *)(v11 + 36) * v13 - 1 + *(_DWORD *)(v11 + 32))
                   / *(_DWORD *)(v11 + 36)))
      + 56LL * ((unsigned int)(*(_DWORD *)(v11 + 36) * v13 - 1 + *(_DWORD *)(v11 + 32)) % *(_DWORD *)(v11 + 36));
  v15 = (unsigned int)(*(_DWORD *)(a1 + 192) - *(_DWORD *)(a1 + 156));
  memcpy_s((void *const)(*(_QWORD *)(v14 + 32) + 16LL * *(unsigned int *)(v14 + 48)), 16 * v15, a2, 16 * v5);
  if ( a4 )
  {
    _mm_lfence();
    memcpy_s((void *const)(*(_QWORD *)(v14 + 40) + 8LL * *(unsigned int *)(v14 + 48)), 8 * v15, a4, 8 * v5);
  }
  *(_DWORD *)(v14 + 48) += v5;
  _mm_lfence();
  if ( *(_DWORD *)(a1 + 132) )
  {
    _mm_lfence();
    v9 = *(_DWORD *)(a1 + 132) - 1;
  }
  v16 = *(_DWORD *)(a1 + 148);
  v17 = 9LL * ((v9 * v16 + *(_DWORD *)(a1 + 144) - 1) % v16);
  v18 = *(_QWORD *)(*(_QWORD *)(a1 + 136) + 8LL * ((v9 * v16 + *(_DWORD *)(a1 + 144) - 1) / v16));
  *(_DWORD *)(v18 + 8 * v17 + 8) += v5;
  *(_DWORD *)(a1 + 156) += v5;
  return 0;
}

```

## disassembly

```asm
0x100437d40  push    rbx
0x100437d42  push    rsi
0x100437d43  push    r14
0x100437d45  push    r15
0x100437d47  sub     rsp, 28h
0x100437d4b  mov     rax, [rcx+30h]
0x100437d4f  mov     rbx, rcx
0x100437d52  add     rcx, 30h ; '0'
0x100437d56  mov     esi, r8d
0x100437d59  mov     r14, r9
0x100437d5c  mov     r15, rdx
0x100437d5f  call    qword ptr [rax+28h]
0x100437d62  test    eax, eax
0x100437d64  js      loc_100437EF9
0x100437d6a  cmp     byte ptr [rbx+68h], 0
0x100437d6e  jnz     short loc_100437D9B
0x100437d70  cmp     byte ptr [rbx+6Ah], 0
0x100437d74  jnz     loc_100437EF9
0x100437d7a  lfence
0x100437d7d  mov     rcx, [rbx+28h]
0x100437d81  mov     r9, r14
0x100437d84  mov     r8d, esi
0x100437d87  mov     rdx, r15
0x100437d8a  mov     rax, [rcx]
0x100437d8d  add     rsp, 28h
0x100437d91  pop     r15
0x100437d93  pop     r14
0x100437d95  pop     rsi
0x100437d96  pop     rbx
0x100437d97  jmp     qword ptr [rax+28h]
0x100437d9b  mov     [rsp+48h+arg_0], rbp
0x100437da0  mov     [rsp+48h+arg_8], rdi
0x100437da5  mov     [rsp+48h+arg_10], r12
0x100437daa  mov     [rsp+48h+var_28], r13
0x100437daf  lfence
0x100437db2  xor     edi, edi
0x100437db4  mov     eax, edi
0x100437db6  cmp     [rbx+84h], eax
0x100437dbc  jbe     short loc_100437DC9
0x100437dbe  lfence
0x100437dc1  mov     eax, [rbx+84h]
0x100437dc7  dec     eax
0x100437dc9  mov     r8d, [rbx+94h]
0x100437dd0  xor     edx, edx
0x100437dd2  mov     ecx, r8d
0x100437dd5  imul    ecx, eax
0x100437dd8  mov     eax, [rbx+90h]
0x100437dde  dec     eax
0x100437de0  add     eax, ecx
0x100437de2  div     r8d
0x100437de5  mov     ecx, edx
0x100437de7  mov     edx, eax
0x100437de9  mov     rax, [rbx+88h]
0x100437df0  lea     rcx, [rcx+rcx*8]
0x100437df4  mov     rax, [rax+rdx*8]
0x100437df8  lea     r9, [rax+rcx*8]
0x100437dfc  mov     eax, [rax+rcx*8+14h]
0x100437e00  test    eax, eax
0x100437e02  lea     ecx, [rax-1]
0x100437e05  mov     eax, [r9+20h]
0x100437e09  cmovz   ecx, edi
0x100437e0c  xor     edx, edx
0x100437e0e  imul    ecx, [r9+24h]
0x100437e13  dec     ecx
0x100437e15  add     eax, ecx
0x100437e17  div     dword ptr [r9+24h]
0x100437e1b  mov     ecx, eax
0x100437e1d  mov     rax, [r9+18h]
0x100437e21  mov     r9, rsi
0x100437e24  mov     r8d, edx
0x100437e27  imul    rbp, r8, 38h ; '8'
0x100437e2b  shl     r9, 4; SourceSize
0x100437e2f  mov     r8, r15; Source
0x100437e32  add     rbp, [rax+rcx*8]
0x100437e36  mov     eax, [rbx+0C0h]
0x100437e3c  sub     eax, [rbx+9Ch]
0x100437e42  mov     edx, eax
0x100437e44  mov     ecx, [rbp+30h]
0x100437e47  shl     rcx, 4
0x100437e4b  add     rcx, [rbp+20h]; Destination
0x100437e4f  shl     rdx, 4; DestinationSize
0x100437e53  mov     r13d, eax
0x100437e56  call    memcpy_s
0x100437e5b  test    r14, r14
0x100437e5e  jz      short loc_100437E86
0x100437e60  lfence
0x100437e63  mov     ecx, [rbp+30h]
0x100437e66  lea     r9, ds:0[rsi*8]; SourceSize
0x100437e6e  mov     rax, [rbp+28h]
0x100437e72  lea     rdx, ds:0[r13*8]; DestinationSize
0x100437e7a  mov     r8, r14; Source
0x100437e7d  lea     rcx, [rax+rcx*8]; Destination
0x100437e81  call    memcpy_s
0x100437e86  add     [rbp+30h], esi
0x100437e89  lfence
0x100437e8c  mov     r13, [rsp+48h+var_28]
0x100437e91  mov     r12, [rsp+48h+arg_10]
0x100437e96  mov     rbp, [rsp+48h+arg_0]
0x100437e9b  cmp     [rbx+84h], edi
0x100437ea1  jbe     short loc_100437EAE
0x100437ea3  lfence
0x100437ea6  mov     edi, [rbx+84h]
0x100437eac  dec     edi
0x100437eae  mov     r8d, [rbx+94h]
0x100437eb5  xor     edx, edx
0x100437eb7  mov     eax, [rbx+90h]
0x100437ebd  mov     ecx, r8d
0x100437ec0  imul    ecx, edi
0x100437ec3  dec     eax
0x100437ec5  mov     rdi, [rsp+48h+arg_8]
0x100437eca  add     eax, ecx
0x100437ecc  div     r8d
0x100437ecf  mov     ecx, edx
0x100437ed1  mov     edx, eax
0x100437ed3  mov     rax, [rbx+88h]
0x100437eda  lea     rcx, [rcx+rcx*8]
0x100437ede  mov     rax, [rax+rdx*8]
0x100437ee2  add     [rax+rcx*8+8], esi
0x100437ee6  add     [rbx+9Ch], esi
0x100437eec  xor     eax, eax
0x100437eee  add     rsp, 28h
0x100437ef2  pop     r15
0x100437ef4  pop     r14
0x100437ef6  pop     rsi
0x100437ef7  pop     rbx
0x100437ef8  retn
0x100437ef9  lfence
0x100437efc  add     rsp, 28h
0x100437f00  pop     r15
0x100437f02  pop     r14
0x100437f04  pop     rsi
0x100437f05  pop     rbx
0x100437f06  retn
```
