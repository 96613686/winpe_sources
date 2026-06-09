# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000b188`
- end: `0x18000b352`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180002c90`

## callees

- `0x180001ed0`
- `0x180002878`
- `0x18000b188`
- `0x18000bafc`
- `0x18000bb74`
- `0x180010010`

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
0x18000b188  push    rbp
0x18000b18a  push    rbx
0x18000b18b  push    rsi
0x18000b18c  push    rdi
0x18000b18d  push    r12
0x18000b18f  push    r14
0x18000b191  lea     rbp, [rsp-0F68h]
0x18000b199  mov     eax, 1068h
0x18000b19e  call    _alloca_probe
0x18000b1a3  sub     rsp, rax
0x18000b1a6  mov     rax, cs:__security_cookie
0x18000b1ad  xor     rax, rsp
0x18000b1b0  mov     [rbp+0F90h+var_40], rax
0x18000b1b7  mov     rax, [rcx+8]
0x18000b1bb  xor     ebx, ebx
0x18000b1bd  sub     rax, [rcx]
0x18000b1c0  xor     edi, edi
0x18000b1c2  mov     r14, rcx
0x18000b1c5  cmp     rax, 0Ch
0x18000b1c9  jb      loc_18000B32C
0x18000b1cf  xor     esi, esi
0x18000b1d1  mov     r12, 0AAAAAAAAAAAAAAABh
0x18000b1db  xor     edx, edx; Val
0x18000b1dd  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000b1e2  mov     r8d, 1000h; Size
0x18000b1e8  call    memset_0
0x18000b1ed  lea     rax, [rsp+1090h+var_1050]
0x18000b1f2  mov     [rsp+1090h+var_1050], 1000h
0x18000b1fa  mov     [rsp+1090h+var_1068], rax
0x18000b1ff  lea     r9, [rsp+1090h+var_104C]
0x18000b204  lea     rax, [rsp+1090h+var_1040]
0x18000b209  mov     [rsp+1090h+var_104C], 0
0x18000b211  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000b218  mov     [rsp+1090h+var_1070], rax
0x18000b21d  call    wil_details_NtQueryWnfStateData
0x18000b222  mov     ebx, eax
0x18000b224  test    eax, eax
0x18000b226  jnz     loc_18000B315
0x18000b22c  mov     r9d, [rsp+1090h+var_1050]
0x18000b231  mov     rax, r12
0x18000b234  mul     r9
0x18000b237  shr     rdx, 3
0x18000b23b  lea     rcx, [rdx+rdx*2]
0x18000b23f  shl     rcx, 2
0x18000b243  cmp     r9, rcx
0x18000b246  jz      short loc_18000B250
0x18000b248  xor     r9d, r9d
0x18000b24b  mov     [rsp+1090h+var_1050], r9d
0x18000b250  mov     r8, [r14]
0x18000b253  mov     rax, r12
0x18000b256  mov     ecx, r9d
0x18000b259  mul     rcx
0x18000b25c  mov     rcx, [r14+8]
0x18000b260  mov     rax, r12
0x18000b263  mov     r11, rdx
0x18000b266  sub     rcx, r8
0x18000b269  mul     rcx
0x18000b26c  shr     r11, 3
0x18000b270  shr     rdx, 3
0x18000b274  lea     rax, [rdx+rdx*2]
0x18000b278  lea     rdi, [r8+rax*4]
0x18000b27c  jmp     short loc_18000B2EA
0x18000b27e  mov     eax, r11d
0x18000b281  lea     r10, [rsp+1090h+var_1040]
0x18000b286  lea     rcx, [rax+rax*2]
0x18000b28a  lea     r10, [r10+rcx*4]
0x18000b28e  cmp     rdx, r10
0x18000b291  jz      short loc_18000B2B9
0x18000b293  mov     eax, [r8]
0x18000b296  cmp     [rdx], eax
0x18000b298  jnz     short loc_18000B2A5
0x18000b29a  movzx   eax, word ptr [r8+4]
0x18000b29f  cmp     [rdx+4], ax
0x18000b2a3  jz      short loc_18000B2AB
0x18000b2a5  add     rdx, 0Ch
0x18000b2a9  jmp     short loc_18000B28E
0x18000b2ab  mov     eax, [r8+8]
0x18000b2af  add     [rdx+8], eax
0x18000b2b2  mov     r9d, [rsp+1090h+var_1050]
0x18000b2b7  jmp     short loc_18000B2E6
0x18000b2b9  mov     eax, r9d
0x18000b2bc  add     rax, 0Ch
0x18000b2c0  cmp     rax, 1000h
0x18000b2c6  ja      short loc_18000B2E6
0x18000b2c8  movsd   xmm0, qword ptr [r8]
0x18000b2cd  add     r9d, 0Ch
0x18000b2d1  movsd   qword ptr [r10], xmm0
0x18000b2d6  inc     r11d
0x18000b2d9  mov     eax, [r8+8]
0x18000b2dd  mov     [r10+8], eax
0x18000b2e1  mov     [rsp+1090h+var_1050], r9d
0x18000b2e6  add     r8, 0Ch
0x18000b2ea  lea     rdx, [rsp+1090h+var_1040]
0x18000b2ef  cmp     r8, rdi
0x18000b2f2  jnz     short loc_18000B27E
0x18000b2f4  mov     eax, [rsp+1090h+var_104C]
0x18000b2f8  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000b2ff  mov     [rsp+1090h+var_1060], 1
0x18000b307  mov     r8d, r9d
0x18000b30a  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000b30e  call    wil_details_NtUpdateWnfStateData
0x18000b313  mov     edi, eax
0x18000b315  cmp     edi, 0C0000001h
0x18000b31b  jnz     short loc_18000B32C
0x18000b31d  inc     esi
0x18000b31f  cmp     esi, 64h ; 'd'
0x18000b322  jge     short loc_18000B32C
0x18000b324  test    ebx, ebx
0x18000b326  jz      loc_18000B1DB
0x18000b32c  test    ebx, ebx
0x18000b32e  cmovz   ebx, edi
0x18000b331  mov     eax, ebx
0x18000b333  mov     rcx, [rbp+0F90h+var_40]
0x18000b33a  xor     rcx, rsp; StackCookie
0x18000b33d  call    __security_check_cookie
0x18000b342  add     rsp, 1068h
0x18000b349  pop     r14
0x18000b34b  pop     r12
0x18000b34d  pop     rdi
0x18000b34e  pop     rsi
0x18000b34f  pop     rbx
0x18000b350  pop     rbp
0x18000b351  retn
```
