# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x14000b03c`
- end: `0x14000b206`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1400060f0`

## callees

- `0x1400023e0`
- `0x140002de4`
- `0x14000b03c`
- `0x14000b49c`
- `0x14000b514`
- `0x14002a8e0`

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
0x14000b03c  push    rbp
0x14000b03e  push    rbx
0x14000b03f  push    rsi
0x14000b040  push    rdi
0x14000b041  push    r12
0x14000b043  push    r14
0x14000b045  lea     rbp, [rsp-0F68h]
0x14000b04d  mov     eax, 1068h
0x14000b052  call    _alloca_probe
0x14000b057  sub     rsp, rax
0x14000b05a  mov     rax, cs:__security_cookie
0x14000b061  xor     rax, rsp
0x14000b064  mov     [rbp+0F90h+var_40], rax
0x14000b06b  mov     rax, [rcx+8]
0x14000b06f  xor     ebx, ebx
0x14000b071  sub     rax, [rcx]
0x14000b074  xor     edi, edi
0x14000b076  mov     r14, rcx
0x14000b079  cmp     rax, 0Ch
0x14000b07d  jb      loc_14000B1E0
0x14000b083  xor     esi, esi
0x14000b085  mov     r12, 0AAAAAAAAAAAAAAABh
0x14000b08f  xor     edx, edx; Val
0x14000b091  lea     rcx, [rsp+1090h+var_1040]; void *
0x14000b096  mov     r8d, 1000h; Size
0x14000b09c  call    memset_0
0x14000b0a1  lea     rax, [rsp+1090h+var_1050]
0x14000b0a6  mov     [rsp+1090h+var_1050], 1000h
0x14000b0ae  mov     [rsp+1090h+var_1068], rax
0x14000b0b3  lea     r9, [rsp+1090h+var_104C]
0x14000b0b8  lea     rax, [rsp+1090h+var_1040]
0x14000b0bd  mov     [rsp+1090h+var_104C], 0
0x14000b0c5  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000b0cc  mov     [rsp+1090h+var_1070], rax
0x14000b0d1  call    wil_details_NtQueryWnfStateData
0x14000b0d6  mov     ebx, eax
0x14000b0d8  test    eax, eax
0x14000b0da  jnz     loc_14000B1C9
0x14000b0e0  mov     r9d, [rsp+1090h+var_1050]
0x14000b0e5  mov     rax, r12
0x14000b0e8  mul     r9
0x14000b0eb  shr     rdx, 3
0x14000b0ef  lea     rcx, [rdx+rdx*2]
0x14000b0f3  shl     rcx, 2
0x14000b0f7  cmp     r9, rcx
0x14000b0fa  jz      short loc_14000B104
0x14000b0fc  xor     r9d, r9d
0x14000b0ff  mov     [rsp+1090h+var_1050], r9d
0x14000b104  mov     r8, [r14]
0x14000b107  mov     rax, r12
0x14000b10a  mov     ecx, r9d
0x14000b10d  mul     rcx
0x14000b110  mov     rcx, [r14+8]
0x14000b114  mov     rax, r12
0x14000b117  mov     r11, rdx
0x14000b11a  sub     rcx, r8
0x14000b11d  mul     rcx
0x14000b120  shr     r11, 3
0x14000b124  shr     rdx, 3
0x14000b128  lea     rax, [rdx+rdx*2]
0x14000b12c  lea     rdi, [r8+rax*4]
0x14000b130  jmp     short loc_14000B19E
0x14000b132  mov     eax, r11d
0x14000b135  lea     r10, [rsp+1090h+var_1040]
0x14000b13a  lea     rcx, [rax+rax*2]
0x14000b13e  lea     r10, [r10+rcx*4]
0x14000b142  cmp     rdx, r10
0x14000b145  jz      short loc_14000B16D
0x14000b147  mov     eax, [r8]
0x14000b14a  cmp     [rdx], eax
0x14000b14c  jnz     short loc_14000B159
0x14000b14e  movzx   eax, word ptr [r8+4]
0x14000b153  cmp     [rdx+4], ax
0x14000b157  jz      short loc_14000B15F
0x14000b159  add     rdx, 0Ch
0x14000b15d  jmp     short loc_14000B142
0x14000b15f  mov     eax, [r8+8]
0x14000b163  add     [rdx+8], eax
0x14000b166  mov     r9d, [rsp+1090h+var_1050]
0x14000b16b  jmp     short loc_14000B19A
0x14000b16d  mov     eax, r9d
0x14000b170  add     rax, 0Ch
0x14000b174  cmp     rax, 1000h
0x14000b17a  ja      short loc_14000B19A
0x14000b17c  movsd   xmm0, qword ptr [r8]
0x14000b181  add     r9d, 0Ch
0x14000b185  movsd   qword ptr [r10], xmm0
0x14000b18a  inc     r11d
0x14000b18d  mov     eax, [r8+8]
0x14000b191  mov     [r10+8], eax
0x14000b195  mov     [rsp+1090h+var_1050], r9d
0x14000b19a  add     r8, 0Ch
0x14000b19e  lea     rdx, [rsp+1090h+var_1040]
0x14000b1a3  cmp     r8, rdi
0x14000b1a6  jnz     short loc_14000B132
0x14000b1a8  mov     eax, [rsp+1090h+var_104C]
0x14000b1ac  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000b1b3  mov     [rsp+1090h+var_1060], 1
0x14000b1bb  mov     r8d, r9d
0x14000b1be  mov     dword ptr [rsp+1090h+var_1068], eax
0x14000b1c2  call    wil_details_NtUpdateWnfStateData
0x14000b1c7  mov     edi, eax
0x14000b1c9  cmp     edi, 0C0000001h
0x14000b1cf  jnz     short loc_14000B1E0
0x14000b1d1  inc     esi
0x14000b1d3  cmp     esi, 64h ; 'd'
0x14000b1d6  jge     short loc_14000B1E0
0x14000b1d8  test    ebx, ebx
0x14000b1da  jz      loc_14000B08F
0x14000b1e0  test    ebx, ebx
0x14000b1e2  cmovz   ebx, edi
0x14000b1e5  mov     eax, ebx
0x14000b1e7  mov     rcx, [rbp+0F90h+var_40]
0x14000b1ee  xor     rcx, rsp; StackCookie
0x14000b1f1  call    __security_check_cookie
0x14000b1f6  add     rsp, 1068h
0x14000b1fd  pop     r14
0x14000b1ff  pop     r12
0x14000b201  pop     rdi
0x14000b202  pop     rsi
0x14000b203  pop     rbx
0x14000b204  pop     rbp
0x14000b205  retn
```
