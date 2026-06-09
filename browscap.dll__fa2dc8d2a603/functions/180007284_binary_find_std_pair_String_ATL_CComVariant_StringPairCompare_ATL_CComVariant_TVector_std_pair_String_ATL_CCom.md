# binary_find<std::pair<String,ATL::CComVariant>,StringPairCompare<ATL::CComVariant>>(TVector<std::pair<String,ATL::CComVariant>> &,std::pair<String,ATL::CComVariant> const &,StringPairCompare<ATL::CComVariant> &)

- ea: `0x180007284`
- end: `0x18000734f`
- name: `??$binary_find@U?$pair@VString@@VCComVariant@ATL@@@std@@U?$StringPairCompare@VCComVariant@ATL@@@@@@YAPEAU?$pair@VString@@VCComVariant@ATL@@@std@@AEAV?$TVector@U?$pair@VString@@VCComVariant@ATL@@@std@@@@AEBU01@AEAU?$StringPairCompare@VCComVariant@ATL@@@@@Z`
- size: `203`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007570`
- `0x18000888c`

## callees

- `0x180007284`

## pseudocode

```c
__int64 __fastcall binary_find<std::pair<String,ATL::CComVariant>,StringPairCompare<ATL::CComVariant>>(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // r9
  __int64 v4; // rdx
  unsigned __int64 v5; // r8
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r10
  unsigned __int8 *v8; // r11
  int v9; // ecx
  int v10; // eax
  unsigned __int64 v11; // rdx
  unsigned __int8 *v12; // rdx
  __int64 v13; // r8
  int v14; // ecx
  int v15; // eax

  v2 = *(_QWORD *)(a1 + 8);
  v4 = (*(_QWORD *)(a1 + 16) - v2) / 40;
  if ( v4 )
  {
    v5 = v4 - 1;
    v6 = (unsigned __int64)(v4 - 1) >> 1;
    if ( v5 )
    {
      v7 = 0;
      do
      {
        v8 = *(unsigned __int8 **)(*(_QWORD *)a2 + 32LL);
        do
        {
          v9 = v8[*(_QWORD *)(*(_QWORD *)(v2 + 40 * v6) + 32LL) - *(_QWORD *)(*(_QWORD *)a2 + 32LL)];
          v10 = *v8 - v9;
          if ( v10 )
            break;
          ++v8;
        }
        while ( v9 );
        if ( v10 <= 0 )
        {
          if ( v10 >= 0 )
            break;
          v5 = v6;
          v11 = v7 + v6;
        }
        else
        {
          v7 = v6 + 1;
          v11 = v6 + 1 + v5;
        }
        v6 = v11 >> 1;
      }
      while ( v5 != v7 );
    }
    v2 += 40 * v6;
    v12 = *(unsigned __int8 **)(*(_QWORD *)a2 + 32LL);
    v13 = *(_QWORD *)(*(_QWORD *)v2 + 32LL) - (_QWORD)v12;
    do
    {
      v14 = v12[v13];
      v15 = *v12 - v14;
      if ( v15 )
        break;
      ++v12;
    }
    while ( v14 );
    if ( v15 > 0 )
      v2 += 40;
  }
  return v2;
}

```

## disassembly

```asm
0x180007284  push    rbx
0x180007286  push    rsi
0x180007287  push    rdi
0x180007288  mov     r9, [rcx+8]
0x18000728c  mov     rdi, rdx
0x18000728f  mov     r8, [rcx+10h]
0x180007293  mov     rax, 6666666666666667h
0x18000729d  sub     r8, r9
0x1800072a0  imul    r8
0x1800072a3  sar     rdx, 4
0x1800072a7  mov     rax, rdx
0x1800072aa  shr     rax, 3Fh
0x1800072ae  add     rdx, rax
0x1800072b1  jz      loc_180007348
0x1800072b7  lea     r8, [rdx-1]
0x1800072bb  mov     rdx, r8
0x1800072be  shr     rdx, 1
0x1800072c1  test    r8, r8
0x1800072c4  jz      short loc_180007314
0x1800072c6  mov     rax, [rdi]
0x1800072c9  xor     r10d, r10d
0x1800072cc  mov     rsi, [rax+20h]
0x1800072d0  lea     rax, [rdx+rdx*4]
0x1800072d4  mov     r11, rsi
0x1800072d7  mov     rcx, [r9+rax*8]
0x1800072db  mov     rbx, [rcx+20h]
0x1800072df  sub     rbx, rsi
0x1800072e2  movzx   eax, byte ptr [r11]
0x1800072e6  movzx   ecx, byte ptr [r11+rbx]
0x1800072eb  sub     eax, ecx
0x1800072ed  jnz     short loc_1800072F6
0x1800072ef  inc     r11
0x1800072f2  test    ecx, ecx
0x1800072f4  jnz     short loc_1800072E2
0x1800072f6  test    eax, eax
0x1800072f8  jle     short loc_180007304
0x1800072fa  lea     r10, [rdx+1]
0x1800072fe  lea     rdx, [r10+r8]
0x180007302  jmp     short loc_18000730C
0x180007304  jns     short loc_180007314
0x180007306  mov     r8, rdx
0x180007309  add     rdx, r10
0x18000730c  shr     rdx, 1
0x18000730f  cmp     r8, r10
0x180007312  jnz     short loc_1800072D0
0x180007314  lea     rax, [rdx+rdx*4]
0x180007318  lea     r9, [r9+rax*8]
0x18000731c  mov     rax, [rdi]
0x18000731f  mov     rcx, [r9]
0x180007322  mov     rdx, [rax+20h]
0x180007326  mov     r8, [rcx+20h]
0x18000732a  sub     r8, rdx
0x18000732d  movzx   eax, byte ptr [rdx]
0x180007330  movzx   ecx, byte ptr [rdx+r8]
0x180007335  sub     eax, ecx
0x180007337  jnz     short loc_180007340
0x180007339  inc     rdx
0x18000733c  test    ecx, ecx
0x18000733e  jnz     short loc_18000732D
0x180007340  test    eax, eax
0x180007342  jle     short loc_180007348
0x180007344  add     r9, 28h ; '('
0x180007348  mov     rax, r9
0x18000734b  pop     rdi
0x18000734c  pop     rsi
0x18000734d  pop     rbx
0x18000734e  retn
```
