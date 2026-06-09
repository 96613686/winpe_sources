# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18001e1b0`
- end: `0x18001e385`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `469`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18001bcf0`

## callees

- `0x18001e1b0`
- `0x18001e3ec`
- `0x18001e464`
- `0x180022792`
- `0x1800227c0`
- `0x180022880`

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
0x18001e1b0  push    rbp
0x18001e1b2  push    rbx
0x18001e1b3  push    rsi
0x18001e1b4  push    rdi
0x18001e1b5  push    r12
0x18001e1b7  push    r14
0x18001e1b9  lea     rbp, [rsp-0F68h]
0x18001e1c1  mov     eax, 1068h
0x18001e1c6  call    _alloca_probe
0x18001e1cb  sub     rsp, rax
0x18001e1ce  mov     rax, cs:__security_cookie
0x18001e1d5  xor     rax, rsp
0x18001e1d8  mov     [rbp+0F90h+var_40], rax
0x18001e1df  mov     rax, [rcx+8]
0x18001e1e3  xor     ebx, ebx
0x18001e1e5  sub     rax, [rcx]
0x18001e1e8  xor     edi, edi
0x18001e1ea  mov     r14, rcx
0x18001e1ed  cmp     rax, 0Ch
0x18001e1f1  jb      loc_18001E351
0x18001e1f7  xor     esi, esi
0x18001e1f9  mov     r12, 0AAAAAAAAAAAAAAABh
0x18001e203  xor     edx, edx; Val
0x18001e205  lea     rcx, [rsp+1090h+var_1040]; void *
0x18001e20a  mov     r8d, 1000h; Size
0x18001e210  call    memset_0
0x18001e215  lea     rax, [rsp+1090h+var_1050]
0x18001e21a  mov     [rsp+1090h+var_1050], 1000h
0x18001e222  mov     [rsp+1090h+var_1068], rax
0x18001e227  lea     r9, [rsp+1090h+var_104C]
0x18001e22c  lea     rax, [rsp+1090h+var_1040]
0x18001e231  mov     [rsp+1090h+var_104C], 0
0x18001e239  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18001e240  mov     [rsp+1090h+var_1070], rax
0x18001e245  call    wil_details_NtQueryWnfStateData
0x18001e24a  mov     ebx, eax
0x18001e24c  test    eax, eax
0x18001e24e  jnz     loc_18001E33A
0x18001e254  mov     r9d, [rsp+1090h+var_1050]
0x18001e259  mov     rax, r12
0x18001e25c  mul     r9
0x18001e25f  shr     rdx, 3
0x18001e263  lea     rcx, [rdx+rdx*2]
0x18001e267  shl     rcx, 2
0x18001e26b  cmp     r9, rcx
0x18001e26e  jz      short loc_18001E278
0x18001e270  xor     r9d, r9d
0x18001e273  mov     [rsp+1090h+var_1050], r9d
0x18001e278  mov     r8, [r14]
0x18001e27b  mov     rax, r12
0x18001e27e  mov     ecx, r9d
0x18001e281  mul     rcx
0x18001e284  mov     rcx, [r14+8]
0x18001e288  mov     rax, r12
0x18001e28b  mov     r10, rdx
0x18001e28e  sub     rcx, r8
0x18001e291  mul     rcx
0x18001e294  shr     r10, 3
0x18001e298  shr     rdx, 3
0x18001e29c  lea     rax, [rdx+rdx*2]
0x18001e2a0  lea     rdi, [r8+rax*4]
0x18001e2a4  jmp     short loc_18001E30F
0x18001e2a6  mov     eax, r10d
0x18001e2a9  lea     rcx, [rax+rax*2]
0x18001e2ad  lea     rdx, [rdx+rcx*4]
0x18001e2b1  lea     rax, [rsp+1090h+var_1040]
0x18001e2b6  cmp     rax, rdx
0x18001e2b9  jz      short loc_18001E2E0
0x18001e2bb  mov     r11d, [r8]
0x18001e2be  lea     rcx, [rsp+1090h+var_1040]
0x18001e2c3  cmp     [rcx], r11d
0x18001e2c6  jnz     short loc_18001E2D7
0x18001e2c8  movzx   eax, word ptr [r8+4]
0x18001e2cd  cmp     [rcx+4], ax
0x18001e2d1  jz      loc_18001E377
0x18001e2d7  add     rcx, 0Ch
0x18001e2db  cmp     rcx, rdx
0x18001e2de  jnz     short loc_18001E2C3
0x18001e2e0  mov     eax, r9d
0x18001e2e3  add     rax, 0Ch
0x18001e2e7  cmp     rax, 1000h
0x18001e2ed  ja      short loc_18001E30B
0x18001e2ef  movsd   xmm0, qword ptr [r8]
0x18001e2f4  add     r9d, 0Ch
0x18001e2f8  movsd   qword ptr [rdx], xmm0
0x18001e2fc  inc     r10d
0x18001e2ff  mov     eax, [r8+8]
0x18001e303  mov     [rdx+8], eax
0x18001e306  mov     [rsp+1090h+var_1050], r9d
0x18001e30b  add     r8, 0Ch
0x18001e30f  lea     rdx, [rsp+1090h+var_1040]
0x18001e314  cmp     r8, rdi
0x18001e317  jnz     short loc_18001E2A6
0x18001e319  mov     eax, [rsp+1090h+var_104C]
0x18001e31d  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18001e324  mov     [rsp+1090h+var_1060], 1
0x18001e32c  mov     r8d, r9d
0x18001e32f  mov     dword ptr [rsp+1090h+var_1068], eax
0x18001e333  call    wil_details_NtUpdateWnfStateData
0x18001e338  mov     edi, eax
0x18001e33a  cmp     edi, 0C0000001h
0x18001e340  jnz     short loc_18001E351
0x18001e342  inc     esi
0x18001e344  cmp     esi, 64h ; 'd'
0x18001e347  jge     short loc_18001E351
0x18001e349  test    ebx, ebx
0x18001e34b  jz      loc_18001E203
0x18001e351  test    ebx, ebx
0x18001e353  cmovz   ebx, edi
0x18001e356  mov     eax, ebx
0x18001e358  mov     rcx, [rbp+0F90h+var_40]
0x18001e35f  xor     rcx, rsp; StackCookie
0x18001e362  call    __security_check_cookie
0x18001e367  add     rsp, 1068h
0x18001e36e  pop     r14
0x18001e370  pop     r12
0x18001e372  pop     rdi
0x18001e373  pop     rsi
0x18001e374  pop     rbx
0x18001e375  pop     rbp
0x18001e376  retn
0x18001e377  mov     eax, [r8+8]
0x18001e37b  add     [rcx+8], eax
0x18001e37e  mov     r9d, [rsp+1090h+var_1050]
0x18001e383  jmp     short loc_18001E30B
```
