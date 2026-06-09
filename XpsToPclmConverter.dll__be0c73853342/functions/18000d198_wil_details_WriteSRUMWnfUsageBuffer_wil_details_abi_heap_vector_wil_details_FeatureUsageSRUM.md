# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000d198`
- end: `0x18000d36d`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `469`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180007800`

## callees

- `0x1800015f0`
- `0x180002148`
- `0x18000d198`
- `0x18000d464`
- `0x18000d4dc`
- `0x18001cbf0`

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
0x18000d198  push    rbp
0x18000d19a  push    rbx
0x18000d19b  push    rsi
0x18000d19c  push    rdi
0x18000d19d  push    r12
0x18000d19f  push    r14
0x18000d1a1  lea     rbp, [rsp-0F68h]
0x18000d1a9  mov     eax, 1068h
0x18000d1ae  call    _alloca_probe
0x18000d1b3  sub     rsp, rax
0x18000d1b6  mov     rax, cs:__security_cookie
0x18000d1bd  xor     rax, rsp
0x18000d1c0  mov     [rbp+0F90h+var_40], rax
0x18000d1c7  mov     rax, [rcx+8]
0x18000d1cb  xor     ebx, ebx
0x18000d1cd  sub     rax, [rcx]
0x18000d1d0  xor     edi, edi
0x18000d1d2  mov     r14, rcx
0x18000d1d5  cmp     rax, 0Ch
0x18000d1d9  jb      loc_18000D339
0x18000d1df  xor     esi, esi
0x18000d1e1  mov     r12, 0AAAAAAAAAAAAAAABh
0x18000d1eb  xor     edx, edx; Val
0x18000d1ed  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000d1f2  mov     r8d, 1000h; Size
0x18000d1f8  call    memset_0
0x18000d1fd  lea     rax, [rsp+1090h+var_1050]
0x18000d202  mov     [rsp+1090h+var_1050], 1000h
0x18000d20a  mov     [rsp+1090h+var_1068], rax
0x18000d20f  lea     r9, [rsp+1090h+var_104C]
0x18000d214  lea     rax, [rsp+1090h+var_1040]
0x18000d219  mov     [rsp+1090h+var_104C], 0
0x18000d221  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000d228  mov     [rsp+1090h+var_1070], rax
0x18000d22d  call    wil_details_NtQueryWnfStateData
0x18000d232  mov     ebx, eax
0x18000d234  test    eax, eax
0x18000d236  jnz     loc_18000D322
0x18000d23c  mov     r9d, [rsp+1090h+var_1050]
0x18000d241  mov     rax, r12
0x18000d244  mul     r9
0x18000d247  shr     rdx, 3
0x18000d24b  lea     rcx, [rdx+rdx*2]
0x18000d24f  shl     rcx, 2
0x18000d253  cmp     r9, rcx
0x18000d256  jz      short loc_18000D260
0x18000d258  xor     r9d, r9d
0x18000d25b  mov     [rsp+1090h+var_1050], r9d
0x18000d260  mov     r8, [r14]
0x18000d263  mov     rax, r12
0x18000d266  mov     ecx, r9d
0x18000d269  mul     rcx
0x18000d26c  mov     rcx, [r14+8]
0x18000d270  mov     rax, r12
0x18000d273  mov     r10, rdx
0x18000d276  sub     rcx, r8
0x18000d279  mul     rcx
0x18000d27c  shr     r10, 3
0x18000d280  shr     rdx, 3
0x18000d284  lea     rax, [rdx+rdx*2]
0x18000d288  lea     rdi, [r8+rax*4]
0x18000d28c  jmp     short loc_18000D2F7
0x18000d28e  mov     eax, r10d
0x18000d291  lea     rcx, [rax+rax*2]
0x18000d295  lea     rdx, [rdx+rcx*4]
0x18000d299  lea     rax, [rsp+1090h+var_1040]
0x18000d29e  cmp     rax, rdx
0x18000d2a1  jz      short loc_18000D2C8
0x18000d2a3  mov     r11d, [r8]
0x18000d2a6  lea     rcx, [rsp+1090h+var_1040]
0x18000d2ab  cmp     [rcx], r11d
0x18000d2ae  jnz     short loc_18000D2BF
0x18000d2b0  movzx   eax, word ptr [r8+4]
0x18000d2b5  cmp     [rcx+4], ax
0x18000d2b9  jz      loc_18000D35F
0x18000d2bf  add     rcx, 0Ch
0x18000d2c3  cmp     rcx, rdx
0x18000d2c6  jnz     short loc_18000D2AB
0x18000d2c8  mov     eax, r9d
0x18000d2cb  add     rax, 0Ch
0x18000d2cf  cmp     rax, 1000h
0x18000d2d5  ja      short loc_18000D2F3
0x18000d2d7  movsd   xmm0, qword ptr [r8]
0x18000d2dc  add     r9d, 0Ch
0x18000d2e0  movsd   qword ptr [rdx], xmm0
0x18000d2e4  inc     r10d
0x18000d2e7  mov     eax, [r8+8]
0x18000d2eb  mov     [rdx+8], eax
0x18000d2ee  mov     [rsp+1090h+var_1050], r9d
0x18000d2f3  add     r8, 0Ch
0x18000d2f7  lea     rdx, [rsp+1090h+var_1040]
0x18000d2fc  cmp     r8, rdi
0x18000d2ff  jnz     short loc_18000D28E
0x18000d301  mov     eax, [rsp+1090h+var_104C]
0x18000d305  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000d30c  mov     [rsp+1090h+var_1060], 1
0x18000d314  mov     r8d, r9d
0x18000d317  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000d31b  call    wil_details_NtUpdateWnfStateData
0x18000d320  mov     edi, eax
0x18000d322  cmp     edi, 0C0000001h
0x18000d328  jnz     short loc_18000D339
0x18000d32a  inc     esi
0x18000d32c  cmp     esi, 64h ; 'd'
0x18000d32f  jge     short loc_18000D339
0x18000d331  test    ebx, ebx
0x18000d333  jz      loc_18000D1EB
0x18000d339  test    ebx, ebx
0x18000d33b  cmovz   ebx, edi
0x18000d33e  mov     eax, ebx
0x18000d340  mov     rcx, [rbp+0F90h+var_40]
0x18000d347  xor     rcx, rsp; StackCookie
0x18000d34a  call    __security_check_cookie
0x18000d34f  add     rsp, 1068h
0x18000d356  pop     r14
0x18000d358  pop     r12
0x18000d35a  pop     rdi
0x18000d35b  pop     rsi
0x18000d35c  pop     rbx
0x18000d35d  pop     rbp
0x18000d35e  retn
0x18000d35f  mov     eax, [r8+8]
0x18000d363  add     [rcx+8], eax
0x18000d366  mov     r9d, [rsp+1090h+var_1050]
0x18000d36b  jmp     short loc_18000D2F3
```
