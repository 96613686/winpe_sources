# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000a388`
- end: `0x18000a552`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180003e30`

## callees

- `0x1800020c0`
- `0x180002b28`
- `0x18000a388`
- `0x18000a7dc`
- `0x18000a854`
- `0x1800164c0`

## pseudocode

```c
__int64 __fastcall wil_details_WriteSRUMWnfUsageBuffer(__int64 *a1)
{
  unsigned int WnfStateData; // ebx
  unsigned int updated; // edi
  int v4; // esi
  int v5; // edx
  int v6; // r8d
  unsigned int v7; // r9d
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
        v9 = v7 / 0xC;
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
          if ( (unsigned __int64)v7 + 12 <= 0x1000 )
          {
            v7 += 12;
            *(_QWORD *)v11 = *(_QWORD *)v8;
            ++v9;
            v11[2] = *(_DWORD *)(v8 + 8);
            v15 = v7;
          }
LABEL_15:
          v8 += 12;
        }
        updated = wil_details_NtUpdateWnfStateData(
                    (unsigned int)&__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM,
                    (unsigned int)v17,
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
0x18000a388  push    rbp
0x18000a38a  push    rbx
0x18000a38b  push    rsi
0x18000a38c  push    rdi
0x18000a38d  push    r12
0x18000a38f  push    r14
0x18000a391  lea     rbp, [rsp-0F68h]
0x18000a399  mov     eax, 1068h
0x18000a39e  call    _alloca_probe
0x18000a3a3  sub     rsp, rax
0x18000a3a6  mov     rax, cs:__security_cookie
0x18000a3ad  xor     rax, rsp
0x18000a3b0  mov     [rbp+0F90h+var_40], rax
0x18000a3b7  mov     rax, [rcx+8]
0x18000a3bb  xor     ebx, ebx
0x18000a3bd  sub     rax, [rcx]
0x18000a3c0  xor     edi, edi
0x18000a3c2  mov     r14, rcx
0x18000a3c5  cmp     rax, 0Ch
0x18000a3c9  jb      loc_18000A52C
0x18000a3cf  xor     esi, esi
0x18000a3d1  mov     r12, 0AAAAAAAAAAAAAAABh
0x18000a3db  xor     edx, edx; Val
0x18000a3dd  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000a3e2  mov     r8d, 1000h; Size
0x18000a3e8  call    memset_0
0x18000a3ed  lea     rax, [rsp+1090h+var_1050]
0x18000a3f2  mov     [rsp+1090h+var_1050], 1000h
0x18000a3fa  mov     [rsp+1090h+var_1068], rax
0x18000a3ff  lea     r9, [rsp+1090h+var_104C]
0x18000a404  lea     rax, [rsp+1090h+var_1040]
0x18000a409  mov     [rsp+1090h+var_104C], 0
0x18000a411  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000a418  mov     [rsp+1090h+var_1070], rax
0x18000a41d  call    wil_details_NtQueryWnfStateData
0x18000a422  mov     ebx, eax
0x18000a424  test    eax, eax
0x18000a426  jnz     loc_18000A515
0x18000a42c  mov     r9d, [rsp+1090h+var_1050]
0x18000a431  mov     rax, r12
0x18000a434  mul     r9
0x18000a437  shr     rdx, 3
0x18000a43b  lea     rcx, [rdx+rdx*2]
0x18000a43f  shl     rcx, 2
0x18000a443  cmp     r9, rcx
0x18000a446  jz      short loc_18000A450
0x18000a448  xor     r9d, r9d
0x18000a44b  mov     [rsp+1090h+var_1050], r9d
0x18000a450  mov     r8, [r14]
0x18000a453  mov     rax, r12
0x18000a456  mov     ecx, r9d
0x18000a459  mul     rcx
0x18000a45c  mov     rcx, [r14+8]
0x18000a460  mov     rax, r12
0x18000a463  mov     r11, rdx
0x18000a466  sub     rcx, r8
0x18000a469  mul     rcx
0x18000a46c  shr     r11, 3
0x18000a470  shr     rdx, 3
0x18000a474  lea     rax, [rdx+rdx*2]
0x18000a478  lea     rdi, [r8+rax*4]
0x18000a47c  jmp     short loc_18000A4EA
0x18000a47e  mov     eax, r11d
0x18000a481  lea     r10, [rsp+1090h+var_1040]
0x18000a486  lea     rcx, [rax+rax*2]
0x18000a48a  lea     r10, [r10+rcx*4]
0x18000a48e  cmp     rdx, r10
0x18000a491  jz      short loc_18000A4B9
0x18000a493  mov     eax, [r8]
0x18000a496  cmp     [rdx], eax
0x18000a498  jnz     short loc_18000A4A5
0x18000a49a  movzx   eax, word ptr [r8+4]
0x18000a49f  cmp     [rdx+4], ax
0x18000a4a3  jz      short loc_18000A4AB
0x18000a4a5  add     rdx, 0Ch
0x18000a4a9  jmp     short loc_18000A48E
0x18000a4ab  mov     eax, [r8+8]
0x18000a4af  add     [rdx+8], eax
0x18000a4b2  mov     r9d, [rsp+1090h+var_1050]
0x18000a4b7  jmp     short loc_18000A4E6
0x18000a4b9  mov     eax, r9d
0x18000a4bc  add     rax, 0Ch
0x18000a4c0  cmp     rax, 1000h
0x18000a4c6  ja      short loc_18000A4E6
0x18000a4c8  movsd   xmm0, qword ptr [r8]
0x18000a4cd  add     r9d, 0Ch
0x18000a4d1  movsd   qword ptr [r10], xmm0
0x18000a4d6  inc     r11d
0x18000a4d9  mov     eax, [r8+8]
0x18000a4dd  mov     [r10+8], eax
0x18000a4e1  mov     [rsp+1090h+var_1050], r9d
0x18000a4e6  add     r8, 0Ch
0x18000a4ea  lea     rdx, [rsp+1090h+var_1040]
0x18000a4ef  cmp     r8, rdi
0x18000a4f2  jnz     short loc_18000A47E
0x18000a4f4  mov     eax, [rsp+1090h+var_104C]
0x18000a4f8  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000a4ff  mov     [rsp+1090h+var_1060], 1
0x18000a507  mov     r8d, r9d
0x18000a50a  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000a50e  call    wil_details_NtUpdateWnfStateData
0x18000a513  mov     edi, eax
0x18000a515  cmp     edi, 0C0000001h
0x18000a51b  jnz     short loc_18000A52C
0x18000a51d  inc     esi
0x18000a51f  cmp     esi, 64h ; 'd'
0x18000a522  jge     short loc_18000A52C
0x18000a524  test    ebx, ebx
0x18000a526  jz      loc_18000A3DB
0x18000a52c  test    ebx, ebx
0x18000a52e  cmovz   ebx, edi
0x18000a531  mov     eax, ebx
0x18000a533  mov     rcx, [rbp+0F90h+var_40]
0x18000a53a  xor     rcx, rsp; StackCookie
0x18000a53d  call    __security_check_cookie
0x18000a542  add     rsp, 1068h
0x18000a549  pop     r14
0x18000a54b  pop     r12
0x18000a54d  pop     rdi
0x18000a54e  pop     rsi
0x18000a54f  pop     rbx
0x18000a550  pop     rbp
0x18000a551  retn
```
