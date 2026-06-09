# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x1800099bc`
- end: `0x180009b92`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `470`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800020d0`

## callees

- `0x1800099bc`
- `0x18000ae30`
- `0x18000aed8`
- `0x18003d4ca`
- `0x18003d510`
- `0x18003d5a0`

## pseudocode

```c
__int64 __fastcall wil_details_WriteSRUMWnfUsageBuffer(__int64 *a1)
{
  unsigned int WnfStateData; // ebx
  unsigned int updated; // edi
  int v4; // esi
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // r8
  unsigned int v9; // r10d
  unsigned __int64 v10; // rdi
  _DWORD *v11; // rdx
  _DWORD *v12; // rcx
  int v14; // [rsp+20h] [rbp-E0h]
  unsigned int v15; // [rsp+40h] [rbp-C0h] BYREF
  int v16[3]; // [rsp+44h] [rbp-BCh] BYREF
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
      v16[0] = 0;
      WnfStateData = wil_details_NtQueryWnfStateData(
                       (__int64)&__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM,
                       v5,
                       v6,
                       (__int64)v16,
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
                    v16[0],
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
0x1800099bc  push    rbp
0x1800099be  push    rbx
0x1800099bf  push    rsi
0x1800099c0  push    rdi
0x1800099c1  push    r12
0x1800099c3  push    r14
0x1800099c5  lea     rbp, [rsp-0F68h]
0x1800099cd  mov     eax, 1068h
0x1800099d2  call    _alloca_probe
0x1800099d7  sub     rsp, rax
0x1800099da  mov     rax, cs:__security_cookie
0x1800099e1  xor     rax, rsp
0x1800099e4  mov     [rbp+0F90h+var_40], rax
0x1800099eb  mov     rax, [rcx+8]
0x1800099ef  xor     ebx, ebx
0x1800099f1  sub     rax, [rcx]
0x1800099f4  xor     edi, edi
0x1800099f6  mov     r14, rcx
0x1800099f9  cmp     rax, 0Ch
0x1800099fd  jb      loc_180009B5D
0x180009a03  xor     esi, esi
0x180009a05  mov     r12, 0AAAAAAAAAAAAAAABh
0x180009a0f  xor     edx, edx; Val
0x180009a11  lea     rcx, [rsp+1090h+var_1040]; void *
0x180009a16  mov     r8d, 1000h; Size
0x180009a1c  call    memset_0
0x180009a21  lea     rax, [rsp+1090h+var_1050]
0x180009a26  mov     [rsp+1090h+var_1050], 1000h
0x180009a2e  mov     [rsp+1090h+var_1068], rax
0x180009a33  lea     r9, [rsp+1090h+var_104C]
0x180009a38  lea     rax, [rsp+1090h+var_1040]
0x180009a3d  mov     [rsp+1090h+var_104C], 0
0x180009a45  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180009a4c  mov     [rsp+1090h+var_1070], rax
0x180009a51  call    wil_details_NtQueryWnfStateData
0x180009a56  mov     ebx, eax
0x180009a58  test    eax, eax
0x180009a5a  jnz     loc_180009B46
0x180009a60  mov     r9d, [rsp+1090h+var_1050]
0x180009a65  mov     rax, r12
0x180009a68  mul     r9
0x180009a6b  shr     rdx, 3
0x180009a6f  lea     rcx, [rdx+rdx*2]
0x180009a73  shl     rcx, 2
0x180009a77  cmp     r9, rcx
0x180009a7a  jz      short loc_180009A84
0x180009a7c  xor     r9d, r9d
0x180009a7f  mov     [rsp+1090h+var_1050], r9d
0x180009a84  mov     r8, [r14]
0x180009a87  mov     rax, r12
0x180009a8a  mov     ecx, r9d
0x180009a8d  mul     rcx
0x180009a90  mov     rcx, [r14+8]
0x180009a94  mov     rax, r12
0x180009a97  mov     r10, rdx
0x180009a9a  sub     rcx, r8
0x180009a9d  mul     rcx
0x180009aa0  shr     r10, 3
0x180009aa4  shr     rdx, 3
0x180009aa8  lea     rax, [rdx+rdx*2]
0x180009aac  lea     rdi, [r8+rax*4]
0x180009ab0  jmp     short loc_180009B1B
0x180009ab2  mov     eax, r10d
0x180009ab5  lea     rcx, [rax+rax*2]
0x180009ab9  lea     rdx, [rdx+rcx*4]
0x180009abd  lea     rax, [rsp+1090h+var_1040]
0x180009ac2  cmp     rax, rdx
0x180009ac5  jz      short loc_180009AEC
0x180009ac7  mov     r11d, [r8]
0x180009aca  lea     rcx, [rsp+1090h+var_1040]
0x180009acf  cmp     [rcx], r11d
0x180009ad2  jnz     short loc_180009AE3
0x180009ad4  movzx   eax, word ptr [r8+4]
0x180009ad9  cmp     [rcx+4], ax
0x180009add  jz      loc_180009B84
0x180009ae3  add     rcx, 0Ch
0x180009ae7  cmp     rcx, rdx
0x180009aea  jnz     short loc_180009ACF
0x180009aec  mov     eax, r9d
0x180009aef  add     rax, 0Ch
0x180009af3  cmp     rax, 1000h
0x180009af9  ja      short loc_180009B17
0x180009afb  movsd   xmm0, qword ptr [r8]
0x180009b00  add     r9d, 0Ch
0x180009b04  movsd   qword ptr [rdx], xmm0
0x180009b08  inc     r10d
0x180009b0b  mov     eax, [r8+8]
0x180009b0f  mov     [rdx+8], eax
0x180009b12  mov     [rsp+1090h+var_1050], r9d
0x180009b17  add     r8, 0Ch
0x180009b1b  lea     rdx, [rsp+1090h+var_1040]
0x180009b20  cmp     r8, rdi
0x180009b23  jnz     short loc_180009AB2
0x180009b25  mov     eax, [rsp+1090h+var_104C]
0x180009b29  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180009b30  mov     [rsp+1090h+var_1060], 1
0x180009b38  mov     r8d, r9d
0x180009b3b  mov     dword ptr [rsp+1090h+var_1068], eax
0x180009b3f  call    wil_details_NtUpdateWnfStateData
0x180009b44  mov     edi, eax
0x180009b46  cmp     edi, 0C0000001h
0x180009b4c  jnz     short loc_180009B5D
0x180009b4e  inc     esi
0x180009b50  cmp     esi, 64h ; 'd'
0x180009b53  jge     short loc_180009B5D
0x180009b55  test    ebx, ebx
0x180009b57  jz      loc_180009A0F
0x180009b5d  test    ebx, ebx
0x180009b5f  cmovz   ebx, edi
0x180009b62  mov     eax, ebx
0x180009b64  mov     rcx, [rbp+0F90h+var_40]
0x180009b6b  xor     rcx, rsp; StackCookie
0x180009b6e  call    __security_check_cookie
0x180009b73  add     rsp, 1068h
0x180009b7a  pop     r14
0x180009b7c  pop     r12
0x180009b7e  pop     rdi
0x180009b7f  pop     rsi
0x180009b80  pop     rbx
0x180009b81  pop     rbp
0x180009b82  retn
0x180009b84  mov     eax, [r8+8]
0x180009b88  add     [rcx+8], eax
0x180009b8b  mov     r9d, [rsp+1090h+var_1050]
0x180009b90  jmp     short loc_180009B17
```
