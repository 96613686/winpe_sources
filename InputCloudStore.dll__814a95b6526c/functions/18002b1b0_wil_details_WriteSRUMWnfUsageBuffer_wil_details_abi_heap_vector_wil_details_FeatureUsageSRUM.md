# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18002b1b0`
- end: `0x18002b37a`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800288e0`

## callees

- `0x180003560`
- `0x180003fd4`
- `0x18002b1b0`
- `0x18002b5ec`
- `0x18002b664`
- `0x18002e660`

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
0x18002b1b0  push    rbp
0x18002b1b2  push    rbx
0x18002b1b3  push    rsi
0x18002b1b4  push    rdi
0x18002b1b5  push    r12
0x18002b1b7  push    r14
0x18002b1b9  lea     rbp, [rsp-0F68h]
0x18002b1c1  mov     eax, 1068h
0x18002b1c6  call    _alloca_probe
0x18002b1cb  sub     rsp, rax
0x18002b1ce  mov     rax, cs:__security_cookie
0x18002b1d5  xor     rax, rsp
0x18002b1d8  mov     [rbp+0F90h+var_40], rax
0x18002b1df  mov     rax, [rcx+8]
0x18002b1e3  xor     ebx, ebx
0x18002b1e5  sub     rax, [rcx]
0x18002b1e8  xor     edi, edi
0x18002b1ea  mov     r14, rcx
0x18002b1ed  cmp     rax, 0Ch
0x18002b1f1  jb      loc_18002B354
0x18002b1f7  xor     esi, esi
0x18002b1f9  mov     r12, 0AAAAAAAAAAAAAAABh
0x18002b203  xor     edx, edx; Val
0x18002b205  lea     rcx, [rsp+1090h+var_1040]; void *
0x18002b20a  mov     r8d, 1000h; Size
0x18002b210  call    memset_0
0x18002b215  lea     rax, [rsp+1090h+var_1050]
0x18002b21a  mov     [rsp+1090h+var_1050], 1000h
0x18002b222  mov     [rsp+1090h+var_1068], rax
0x18002b227  lea     r9, [rsp+1090h+var_104C]
0x18002b22c  lea     rax, [rsp+1090h+var_1040]
0x18002b231  mov     [rsp+1090h+var_104C], 0
0x18002b239  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18002b240  mov     [rsp+1090h+var_1070], rax
0x18002b245  call    wil_details_NtQueryWnfStateData
0x18002b24a  mov     ebx, eax
0x18002b24c  test    eax, eax
0x18002b24e  jnz     loc_18002B33D
0x18002b254  mov     r9d, [rsp+1090h+var_1050]
0x18002b259  mov     rax, r12
0x18002b25c  mul     r9
0x18002b25f  shr     rdx, 3
0x18002b263  lea     rcx, [rdx+rdx*2]
0x18002b267  shl     rcx, 2
0x18002b26b  cmp     r9, rcx
0x18002b26e  jz      short loc_18002B278
0x18002b270  xor     r9d, r9d
0x18002b273  mov     [rsp+1090h+var_1050], r9d
0x18002b278  mov     r8, [r14]
0x18002b27b  mov     rax, r12
0x18002b27e  mov     ecx, r9d
0x18002b281  mul     rcx
0x18002b284  mov     rcx, [r14+8]
0x18002b288  mov     rax, r12
0x18002b28b  mov     r11, rdx
0x18002b28e  sub     rcx, r8
0x18002b291  mul     rcx
0x18002b294  shr     r11, 3
0x18002b298  shr     rdx, 3
0x18002b29c  lea     rax, [rdx+rdx*2]
0x18002b2a0  lea     rdi, [r8+rax*4]
0x18002b2a4  jmp     short loc_18002B312
0x18002b2a6  mov     eax, r11d
0x18002b2a9  lea     r10, [rsp+1090h+var_1040]
0x18002b2ae  lea     rcx, [rax+rax*2]
0x18002b2b2  lea     r10, [r10+rcx*4]
0x18002b2b6  cmp     rdx, r10
0x18002b2b9  jz      short loc_18002B2E1
0x18002b2bb  mov     eax, [r8]
0x18002b2be  cmp     [rdx], eax
0x18002b2c0  jnz     short loc_18002B2CD
0x18002b2c2  movzx   eax, word ptr [r8+4]
0x18002b2c7  cmp     [rdx+4], ax
0x18002b2cb  jz      short loc_18002B2D3
0x18002b2cd  add     rdx, 0Ch
0x18002b2d1  jmp     short loc_18002B2B6
0x18002b2d3  mov     eax, [r8+8]
0x18002b2d7  add     [rdx+8], eax
0x18002b2da  mov     r9d, [rsp+1090h+var_1050]
0x18002b2df  jmp     short loc_18002B30E
0x18002b2e1  mov     eax, r9d
0x18002b2e4  add     rax, 0Ch
0x18002b2e8  cmp     rax, 1000h
0x18002b2ee  ja      short loc_18002B30E
0x18002b2f0  movsd   xmm0, qword ptr [r8]
0x18002b2f5  add     r9d, 0Ch
0x18002b2f9  movsd   qword ptr [r10], xmm0
0x18002b2fe  inc     r11d
0x18002b301  mov     eax, [r8+8]
0x18002b305  mov     [r10+8], eax
0x18002b309  mov     [rsp+1090h+var_1050], r9d
0x18002b30e  add     r8, 0Ch
0x18002b312  lea     rdx, [rsp+1090h+var_1040]
0x18002b317  cmp     r8, rdi
0x18002b31a  jnz     short loc_18002B2A6
0x18002b31c  mov     eax, [rsp+1090h+var_104C]
0x18002b320  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18002b327  mov     [rsp+1090h+var_1060], 1
0x18002b32f  mov     r8d, r9d
0x18002b332  mov     dword ptr [rsp+1090h+var_1068], eax
0x18002b336  call    wil_details_NtUpdateWnfStateData
0x18002b33b  mov     edi, eax
0x18002b33d  cmp     edi, 0C0000001h
0x18002b343  jnz     short loc_18002B354
0x18002b345  inc     esi
0x18002b347  cmp     esi, 64h ; 'd'
0x18002b34a  jge     short loc_18002B354
0x18002b34c  test    ebx, ebx
0x18002b34e  jz      loc_18002B203
0x18002b354  test    ebx, ebx
0x18002b356  cmovz   ebx, edi
0x18002b359  mov     eax, ebx
0x18002b35b  mov     rcx, [rbp+0F90h+var_40]
0x18002b362  xor     rcx, rsp; StackCookie
0x18002b365  call    __security_check_cookie
0x18002b36a  add     rsp, 1068h
0x18002b371  pop     r14
0x18002b373  pop     r12
0x18002b375  pop     rdi
0x18002b376  pop     rsi
0x18002b377  pop     rbx
0x18002b378  pop     rbp
0x18002b379  retn
```
