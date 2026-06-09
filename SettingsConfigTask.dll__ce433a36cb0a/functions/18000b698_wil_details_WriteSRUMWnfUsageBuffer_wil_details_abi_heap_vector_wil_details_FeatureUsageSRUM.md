# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000b698`
- end: `0x18000b862`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180003550`

## callees

- `0x1800021d0`
- `0x180002c18`
- `0x18000b698`
- `0x18000bf44`
- `0x18000bfbc`
- `0x180021f10`

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
  unsigned int v9; // r11d
  unsigned __int64 v10; // rdi
  _DWORD *v11; // r10
  _DWORD *v12; // rdx
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
        while ( 1 )
        {
          v12 = v17;
          if ( v8 == v10 )
            break;
          v11 = &v17[3 * v9];
          while ( v12 != v11 )
          {
            if ( *v12 == *(_DWORD *)v8 && *((_WORD *)v12 + 2) == *(_WORD *)(v8 + 4) )
            {
              v12[2] += *(_DWORD *)(v8 + 8);
              v7 = v15;
              goto LABEL_15;
            }
            v12 += 3;
          }
          if ( (unsigned __int64)(unsigned int)v7 + 12 <= 0x1000 )
          {
            v7 = (unsigned int)(v7 + 12);
            *(_QWORD *)v11 = *(_QWORD *)v8;
            ++v9;
            v11[2] = *(_DWORD *)(v8 + 8);
            v15 = v7;
          }
LABEL_15:
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
0x18000b698  push    rbp
0x18000b69a  push    rbx
0x18000b69b  push    rsi
0x18000b69c  push    rdi
0x18000b69d  push    r12
0x18000b69f  push    r14
0x18000b6a1  lea     rbp, [rsp-0F68h]
0x18000b6a9  mov     eax, 1068h
0x18000b6ae  call    _alloca_probe
0x18000b6b3  sub     rsp, rax
0x18000b6b6  mov     rax, cs:__security_cookie
0x18000b6bd  xor     rax, rsp
0x18000b6c0  mov     [rbp+0F90h+var_40], rax
0x18000b6c7  mov     rax, [rcx+8]
0x18000b6cb  xor     ebx, ebx
0x18000b6cd  sub     rax, [rcx]
0x18000b6d0  xor     edi, edi
0x18000b6d2  mov     r14, rcx
0x18000b6d5  cmp     rax, 0Ch
0x18000b6d9  jb      loc_18000B83C
0x18000b6df  xor     esi, esi
0x18000b6e1  mov     r12, 0AAAAAAAAAAAAAAABh
0x18000b6eb  xor     edx, edx; Val
0x18000b6ed  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000b6f2  mov     r8d, 1000h; Size
0x18000b6f8  call    memset_0
0x18000b6fd  lea     rax, [rsp+1090h+var_1050]
0x18000b702  mov     [rsp+1090h+var_1050], 1000h
0x18000b70a  mov     [rsp+1090h+var_1068], rax
0x18000b70f  lea     r9, [rsp+1090h+var_104C]
0x18000b714  lea     rax, [rsp+1090h+var_1040]
0x18000b719  mov     [rsp+1090h+var_104C], 0
0x18000b721  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000b728  mov     [rsp+1090h+var_1070], rax
0x18000b72d  call    wil_details_NtQueryWnfStateData
0x18000b732  mov     ebx, eax
0x18000b734  test    eax, eax
0x18000b736  jnz     loc_18000B825
0x18000b73c  mov     r9d, [rsp+1090h+var_1050]
0x18000b741  mov     rax, r12
0x18000b744  mul     r9
0x18000b747  shr     rdx, 3
0x18000b74b  lea     rcx, [rdx+rdx*2]
0x18000b74f  shl     rcx, 2
0x18000b753  cmp     r9, rcx
0x18000b756  jz      short loc_18000B760
0x18000b758  xor     r9d, r9d
0x18000b75b  mov     [rsp+1090h+var_1050], r9d
0x18000b760  mov     r8, [r14]
0x18000b763  mov     rax, r12
0x18000b766  mov     ecx, r9d
0x18000b769  mul     rcx
0x18000b76c  mov     rcx, [r14+8]
0x18000b770  mov     rax, r12
0x18000b773  mov     r11, rdx
0x18000b776  sub     rcx, r8
0x18000b779  mul     rcx
0x18000b77c  shr     r11, 3
0x18000b780  shr     rdx, 3
0x18000b784  lea     rax, [rdx+rdx*2]
0x18000b788  lea     rdi, [r8+rax*4]
0x18000b78c  jmp     short loc_18000B7FA
0x18000b78e  mov     eax, r11d
0x18000b791  lea     r10, [rsp+1090h+var_1040]
0x18000b796  lea     rcx, [rax+rax*2]
0x18000b79a  lea     r10, [r10+rcx*4]
0x18000b79e  cmp     rdx, r10
0x18000b7a1  jz      short loc_18000B7C9
0x18000b7a3  mov     eax, [r8]
0x18000b7a6  cmp     [rdx], eax
0x18000b7a8  jnz     short loc_18000B7B5
0x18000b7aa  movzx   eax, word ptr [r8+4]
0x18000b7af  cmp     [rdx+4], ax
0x18000b7b3  jz      short loc_18000B7BB
0x18000b7b5  add     rdx, 0Ch
0x18000b7b9  jmp     short loc_18000B79E
0x18000b7bb  mov     eax, [r8+8]
0x18000b7bf  add     [rdx+8], eax
0x18000b7c2  mov     r9d, [rsp+1090h+var_1050]
0x18000b7c7  jmp     short loc_18000B7F6
0x18000b7c9  mov     eax, r9d
0x18000b7cc  add     rax, 0Ch
0x18000b7d0  cmp     rax, 1000h
0x18000b7d6  ja      short loc_18000B7F6
0x18000b7d8  movsd   xmm0, qword ptr [r8]
0x18000b7dd  add     r9d, 0Ch
0x18000b7e1  movsd   qword ptr [r10], xmm0
0x18000b7e6  inc     r11d
0x18000b7e9  mov     eax, [r8+8]
0x18000b7ed  mov     [r10+8], eax
0x18000b7f1  mov     [rsp+1090h+var_1050], r9d
0x18000b7f6  add     r8, 0Ch
0x18000b7fa  lea     rdx, [rsp+1090h+var_1040]
0x18000b7ff  cmp     r8, rdi
0x18000b802  jnz     short loc_18000B78E
0x18000b804  mov     eax, [rsp+1090h+var_104C]
0x18000b808  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000b80f  mov     [rsp+1090h+var_1060], 1
0x18000b817  mov     r8d, r9d
0x18000b81a  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000b81e  call    wil_details_NtUpdateWnfStateData
0x18000b823  mov     edi, eax
0x18000b825  cmp     edi, 0C0000001h
0x18000b82b  jnz     short loc_18000B83C
0x18000b82d  inc     esi
0x18000b82f  cmp     esi, 64h ; 'd'
0x18000b832  jge     short loc_18000B83C
0x18000b834  test    ebx, ebx
0x18000b836  jz      loc_18000B6EB
0x18000b83c  test    ebx, ebx
0x18000b83e  cmovz   ebx, edi
0x18000b841  mov     eax, ebx
0x18000b843  mov     rcx, [rbp+0F90h+var_40]
0x18000b84a  xor     rcx, rsp; StackCookie
0x18000b84d  call    __security_check_cookie
0x18000b852  add     rsp, 1068h
0x18000b859  pop     r14
0x18000b85b  pop     r12
0x18000b85d  pop     rdi
0x18000b85e  pop     rsi
0x18000b85f  pop     rbx
0x18000b860  pop     rbp
0x18000b861  retn
```
