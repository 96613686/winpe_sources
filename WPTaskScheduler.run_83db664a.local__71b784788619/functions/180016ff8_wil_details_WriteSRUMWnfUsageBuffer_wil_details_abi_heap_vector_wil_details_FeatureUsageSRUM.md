# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180016ff8`
- end: `0x1800171cd`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `469`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800107d0`

## callees

- `0x180016ff8`
- `0x180017904`
- `0x18001797c`
- `0x180020c02`
- `0x180020c30`
- `0x180020cf0`

## pseudocode

```c
__int64 __fastcall wil_details_WriteSRUMWnfUsageBuffer(__int64 *a1)
{
  unsigned int WnfStateData; // ebx
  unsigned int updated; // edi
  int v4; // esi
  int v5; // edx
  int v6; // r8d
  __int64 v7; // r9
  __int64 v8; // r8
  unsigned int v9; // r10d
  unsigned __int64 v10; // rdi
  _DWORD *v11; // rdx
  _DWORD *v12; // rcx
  int v14; // [rsp+20h] [rbp-E0h]
  unsigned int v15; // [rsp+40h] [rbp-C0h] BYREF
  int v16; // [rsp+44h] [rbp-BCh] BYREF
  _DWORD v17[1024]; // [rsp+50h] [rbp-B0h] BYREF

  WnfStateData = 0;
  updated = 0;
  if ( (unsigned __int64)(a1[1] - *a1) >= 0xC )
  {
    v4 = 0;
    do
    {
      memset_0(v17, 0, sizeof(v17));
      v15 = 4096;
      v16 = 0;
      WnfStateData = wil_details_NtQueryWnfStateData(
                       (unsigned int)&__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM,
                       v5,
                       v6,
                       (unsigned int)&v16,
                       (__int64)v17,
                       (__int64)&v15);
      if ( !WnfStateData )
      {
        v7 = v15;
        if ( v15 != 12 * (v15 / 0xCuLL) )
        {
          v7 = 0;
          v15 = 0;
        }
        v8 = *a1;
        v9 = (unsigned int)v7 / 0xC;
        v10 = *a1 + 12 * ((a1[1] - *a1) / 0xCuLL);
        while ( v8 != v10 )
        {
          v11 = &v17[3 * v9];
          if ( v17 == v11 )
          {
LABEL_12:
            if ( (unsigned __int64)(unsigned int)v7 + 12 <= 0x1000 )
            {
              v7 = (unsigned int)(v7 + 12);
              *(_QWORD *)v11 = *(_QWORD *)v8;
              ++v9;
              v11[2] = *(_DWORD *)(v8 + 8);
              v15 = v7;
            }
          }
          else
          {
            v12 = v17;
            while ( *v12 != *(_DWORD *)v8 || *((_WORD *)v12 + 2) != *(_WORD *)(v8 + 4) )
            {
              v12 += 3;
              if ( v12 == v11 )
                goto LABEL_12;
            }
            v12[2] += *(_DWORD *)(v8 + 8);
            v7 = v15;
          }
          v8 += 12;
        }
        updated = wil_details_NtUpdateWnfStateData(
                    (__int64)&__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM,
                    (__int64)v17,
                    v7,
                    v7,
                    v14,
                    v16,
                    1);
      }
      if ( updated != -1073741823 )
        break;
      if ( ++v4 >= 100 )
        break;
    }
    while ( !WnfStateData );
  }
  if ( !WnfStateData )
    return updated;
  return WnfStateData;
}

```

## disassembly

```asm
0x180016ff8  push    rbp
0x180016ffa  push    rbx
0x180016ffb  push    rsi
0x180016ffc  push    rdi
0x180016ffd  push    r12
0x180016fff  push    r14
0x180017001  lea     rbp, [rsp-0F68h]
0x180017009  mov     eax, 1068h
0x18001700e  call    _alloca_probe
0x180017013  sub     rsp, rax
0x180017016  mov     rax, cs:__security_cookie
0x18001701d  xor     rax, rsp
0x180017020  mov     [rbp+0F90h+var_40], rax
0x180017027  mov     rax, [rcx+8]
0x18001702b  xor     ebx, ebx
0x18001702d  sub     rax, [rcx]
0x180017030  xor     edi, edi
0x180017032  mov     r14, rcx
0x180017035  cmp     rax, 0Ch
0x180017039  jb      loc_180017199
0x18001703f  xor     esi, esi
0x180017041  mov     r12, 0AAAAAAAAAAAAAAABh
0x18001704b  xor     edx, edx; Val
0x18001704d  lea     rcx, [rsp+1090h+var_1040]; void *
0x180017052  mov     r8d, 1000h; Size
0x180017058  call    memset_0
0x18001705d  lea     rax, [rsp+1090h+var_1050]
0x180017062  mov     [rsp+1090h+var_1050], 1000h
0x18001706a  mov     [rsp+1090h+var_1068], rax
0x18001706f  lea     r9, [rsp+1090h+var_104C]
0x180017074  lea     rax, [rsp+1090h+var_1040]
0x180017079  mov     [rsp+1090h+var_104C], 0
0x180017081  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180017088  mov     [rsp+1090h+var_1070], rax
0x18001708d  call    wil_details_NtQueryWnfStateData
0x180017092  mov     ebx, eax
0x180017094  test    eax, eax
0x180017096  jnz     loc_180017182
0x18001709c  mov     r9d, [rsp+1090h+var_1050]
0x1800170a1  mov     rax, r12
0x1800170a4  mul     r9
0x1800170a7  shr     rdx, 3
0x1800170ab  lea     rcx, [rdx+rdx*2]
0x1800170af  shl     rcx, 2
0x1800170b3  cmp     r9, rcx
0x1800170b6  jz      short loc_1800170C0
0x1800170b8  xor     r9d, r9d
0x1800170bb  mov     [rsp+1090h+var_1050], r9d
0x1800170c0  mov     r8, [r14]
0x1800170c3  mov     rax, r12
0x1800170c6  mov     ecx, r9d
0x1800170c9  mul     rcx
0x1800170cc  mov     rcx, [r14+8]
0x1800170d0  mov     rax, r12
0x1800170d3  mov     r10, rdx
0x1800170d6  sub     rcx, r8
0x1800170d9  mul     rcx
0x1800170dc  shr     r10, 3
0x1800170e0  shr     rdx, 3
0x1800170e4  lea     rax, [rdx+rdx*2]
0x1800170e8  lea     rdi, [r8+rax*4]
0x1800170ec  jmp     short loc_180017157
0x1800170ee  mov     eax, r10d
0x1800170f1  lea     rcx, [rax+rax*2]
0x1800170f5  lea     rdx, [rdx+rcx*4]
0x1800170f9  lea     rax, [rsp+1090h+var_1040]
0x1800170fe  cmp     rax, rdx
0x180017101  jz      short loc_180017128
0x180017103  mov     r11d, [r8]
0x180017106  lea     rcx, [rsp+1090h+var_1040]
0x18001710b  cmp     [rcx], r11d
0x18001710e  jnz     short loc_18001711F
0x180017110  movzx   eax, word ptr [r8+4]
0x180017115  cmp     [rcx+4], ax
0x180017119  jz      loc_1800171BF
0x18001711f  add     rcx, 0Ch
0x180017123  cmp     rcx, rdx
0x180017126  jnz     short loc_18001710B
0x180017128  mov     eax, r9d
0x18001712b  add     rax, 0Ch
0x18001712f  cmp     rax, 1000h
0x180017135  ja      short loc_180017153
0x180017137  movsd   xmm0, qword ptr [r8]
0x18001713c  add     r9d, 0Ch
0x180017140  movsd   qword ptr [rdx], xmm0
0x180017144  inc     r10d
0x180017147  mov     eax, [r8+8]
0x18001714b  mov     [rdx+8], eax
0x18001714e  mov     [rsp+1090h+var_1050], r9d
0x180017153  add     r8, 0Ch
0x180017157  lea     rdx, [rsp+1090h+var_1040]
0x18001715c  cmp     r8, rdi
0x18001715f  jnz     short loc_1800170EE
0x180017161  mov     eax, [rsp+1090h+var_104C]
0x180017165  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18001716c  mov     [rsp+1090h+var_1060], 1
0x180017174  mov     r8d, r9d
0x180017177  mov     dword ptr [rsp+1090h+var_1068], eax
0x18001717b  call    wil_details_NtUpdateWnfStateData
0x180017180  mov     edi, eax
0x180017182  cmp     edi, 0C0000001h
0x180017188  jnz     short loc_180017199
0x18001718a  inc     esi
0x18001718c  cmp     esi, 64h ; 'd'
0x18001718f  jge     short loc_180017199
0x180017191  test    ebx, ebx
0x180017193  jz      loc_18001704B
0x180017199  test    ebx, ebx
0x18001719b  cmovz   ebx, edi
0x18001719e  mov     eax, ebx
0x1800171a0  mov     rcx, [rbp+0F90h+var_40]
0x1800171a7  xor     rcx, rsp; StackCookie
0x1800171aa  call    __security_check_cookie
0x1800171af  add     rsp, 1068h
0x1800171b6  pop     r14
0x1800171b8  pop     r12
0x1800171ba  pop     rdi
0x1800171bb  pop     rsi
0x1800171bc  pop     rbx
0x1800171bd  pop     rbp
0x1800171be  retn
0x1800171bf  mov     eax, [r8+8]
0x1800171c3  add     [rcx+8], eax
0x1800171c6  mov     r9d, [rsp+1090h+var_1050]
0x1800171cb  jmp     short loc_180017153
```
