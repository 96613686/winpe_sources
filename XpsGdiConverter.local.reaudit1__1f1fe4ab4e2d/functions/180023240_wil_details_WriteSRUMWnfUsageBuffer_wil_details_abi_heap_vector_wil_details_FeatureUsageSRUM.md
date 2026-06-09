# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180023240`
- end: `0x180023415`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `469`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18001b8b0`

## callees

- `0x180008830`
- `0x1800093c4`
- `0x180023240`
- `0x180023b4c`
- `0x180023bc4`
- `0x180047170`

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
0x180023240  push    rbp
0x180023242  push    rbx
0x180023243  push    rsi
0x180023244  push    rdi
0x180023245  push    r12
0x180023247  push    r14
0x180023249  lea     rbp, [rsp-0F68h]
0x180023251  mov     eax, 1068h
0x180023256  call    _alloca_probe
0x18002325b  sub     rsp, rax
0x18002325e  mov     rax, cs:__security_cookie
0x180023265  xor     rax, rsp
0x180023268  mov     [rbp+0F90h+var_40], rax
0x18002326f  mov     rax, [rcx+8]
0x180023273  xor     ebx, ebx
0x180023275  sub     rax, [rcx]
0x180023278  xor     edi, edi
0x18002327a  mov     r14, rcx
0x18002327d  cmp     rax, 0Ch
0x180023281  jb      loc_1800233E1
0x180023287  xor     esi, esi
0x180023289  mov     r12, 0AAAAAAAAAAAAAAABh
0x180023293  xor     edx, edx; Val
0x180023295  lea     rcx, [rsp+1090h+var_1040]; void *
0x18002329a  mov     r8d, 1000h; Size
0x1800232a0  call    memset_0
0x1800232a5  lea     rax, [rsp+1090h+var_1050]
0x1800232aa  mov     [rsp+1090h+var_1050], 1000h
0x1800232b2  mov     [rsp+1090h+var_1068], rax
0x1800232b7  lea     r9, [rsp+1090h+var_104C]
0x1800232bc  lea     rax, [rsp+1090h+var_1040]
0x1800232c1  mov     [rsp+1090h+var_104C], 0
0x1800232c9  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1800232d0  mov     [rsp+1090h+var_1070], rax
0x1800232d5  call    wil_details_NtQueryWnfStateData
0x1800232da  mov     ebx, eax
0x1800232dc  test    eax, eax
0x1800232de  jnz     loc_1800233CA
0x1800232e4  mov     r9d, [rsp+1090h+var_1050]
0x1800232e9  mov     rax, r12
0x1800232ec  mul     r9
0x1800232ef  shr     rdx, 3
0x1800232f3  lea     rcx, [rdx+rdx*2]
0x1800232f7  shl     rcx, 2
0x1800232fb  cmp     r9, rcx
0x1800232fe  jz      short loc_180023308
0x180023300  xor     r9d, r9d
0x180023303  mov     [rsp+1090h+var_1050], r9d
0x180023308  mov     r8, [r14]
0x18002330b  mov     rax, r12
0x18002330e  mov     ecx, r9d
0x180023311  mul     rcx
0x180023314  mov     rcx, [r14+8]
0x180023318  mov     rax, r12
0x18002331b  mov     r10, rdx
0x18002331e  sub     rcx, r8
0x180023321  mul     rcx
0x180023324  shr     r10, 3
0x180023328  shr     rdx, 3
0x18002332c  lea     rax, [rdx+rdx*2]
0x180023330  lea     rdi, [r8+rax*4]
0x180023334  jmp     short loc_18002339F
0x180023336  mov     eax, r10d
0x180023339  lea     rcx, [rax+rax*2]
0x18002333d  lea     rdx, [rdx+rcx*4]
0x180023341  lea     rax, [rsp+1090h+var_1040]
0x180023346  cmp     rax, rdx
0x180023349  jz      short loc_180023370
0x18002334b  mov     r11d, [r8]
0x18002334e  lea     rcx, [rsp+1090h+var_1040]
0x180023353  cmp     [rcx], r11d
0x180023356  jnz     short loc_180023367
0x180023358  movzx   eax, word ptr [r8+4]
0x18002335d  cmp     [rcx+4], ax
0x180023361  jz      loc_180023407
0x180023367  add     rcx, 0Ch
0x18002336b  cmp     rcx, rdx
0x18002336e  jnz     short loc_180023353
0x180023370  mov     eax, r9d
0x180023373  add     rax, 0Ch
0x180023377  cmp     rax, 1000h
0x18002337d  ja      short loc_18002339B
0x18002337f  movsd   xmm0, qword ptr [r8]
0x180023384  add     r9d, 0Ch
0x180023388  movsd   qword ptr [rdx], xmm0
0x18002338c  inc     r10d
0x18002338f  mov     eax, [r8+8]
0x180023393  mov     [rdx+8], eax
0x180023396  mov     [rsp+1090h+var_1050], r9d
0x18002339b  add     r8, 0Ch
0x18002339f  lea     rdx, [rsp+1090h+var_1040]
0x1800233a4  cmp     r8, rdi
0x1800233a7  jnz     short loc_180023336
0x1800233a9  mov     eax, [rsp+1090h+var_104C]
0x1800233ad  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1800233b4  mov     [rsp+1090h+var_1060], 1
0x1800233bc  mov     r8d, r9d
0x1800233bf  mov     dword ptr [rsp+1090h+var_1068], eax
0x1800233c3  call    wil_details_NtUpdateWnfStateData
0x1800233c8  mov     edi, eax
0x1800233ca  cmp     edi, 0C0000001h
0x1800233d0  jnz     short loc_1800233E1
0x1800233d2  inc     esi
0x1800233d4  cmp     esi, 64h ; 'd'
0x1800233d7  jge     short loc_1800233E1
0x1800233d9  test    ebx, ebx
0x1800233db  jz      loc_180023293
0x1800233e1  test    ebx, ebx
0x1800233e3  cmovz   ebx, edi
0x1800233e6  mov     eax, ebx
0x1800233e8  mov     rcx, [rbp+0F90h+var_40]
0x1800233ef  xor     rcx, rsp; StackCookie
0x1800233f2  call    __security_check_cookie
0x1800233f7  add     rsp, 1068h
0x1800233fe  pop     r14
0x180023400  pop     r12
0x180023402  pop     rdi
0x180023403  pop     rsi
0x180023404  pop     rbx
0x180023405  pop     rbp
0x180023406  retn
0x180023407  mov     eax, [r8+8]
0x18002340b  add     [rcx+8], eax
0x18002340e  mov     r9d, [rsp+1090h+var_1050]
0x180023413  jmp     short loc_18002339B
```
