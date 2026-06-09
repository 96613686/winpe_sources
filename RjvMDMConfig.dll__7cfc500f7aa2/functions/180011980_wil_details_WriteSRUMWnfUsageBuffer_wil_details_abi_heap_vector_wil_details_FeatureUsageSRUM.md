# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180011980`
- end: `0x180011b4b`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `459`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180006610`

## callees

- `0x180001c60`
- `0x1800026d8`
- `0x180011980`
- `0x1800126bc`
- `0x180012734`
- `0x18001cf10`

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
0x180011980  push    rbp
0x180011982  push    rbx
0x180011983  push    rsi
0x180011984  push    rdi
0x180011985  push    r12
0x180011987  push    r14
0x180011989  lea     rbp, [rsp-0F68h]
0x180011991  mov     eax, 1068h
0x180011996  call    _alloca_probe
0x18001199b  sub     rsp, rax
0x18001199e  mov     rax, cs:__security_cookie
0x1800119a5  xor     rax, rsp
0x1800119a8  mov     [rbp+0F90h+var_40], rax
0x1800119af  mov     rax, [rcx+8]
0x1800119b3  xor     ebx, ebx
0x1800119b5  sub     rax, [rcx]
0x1800119b8  xor     edi, edi
0x1800119ba  mov     r14, rcx
0x1800119bd  cmp     rax, 0Ch
0x1800119c1  jb      loc_180011B24
0x1800119c7  xor     esi, esi
0x1800119c9  mov     r12, 0AAAAAAAAAAAAAAABh
0x1800119d3  xor     edx, edx; Val
0x1800119d5  lea     rcx, [rsp+1090h+var_1040]; void *
0x1800119da  mov     r8d, 1000h; Size
0x1800119e0  call    memset_0
0x1800119e5  lea     rax, [rsp+1090h+var_1050]
0x1800119ea  mov     [rsp+1090h+var_1050], 1000h
0x1800119f2  mov     [rsp+1090h+var_1068], rax
0x1800119f7  lea     r9, [rsp+1090h+var_104C]
0x1800119fc  lea     rax, [rsp+1090h+var_1040]
0x180011a01  mov     [rsp+1090h+var_104C], 0
0x180011a09  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180011a10  mov     [rsp+1090h+var_1070], rax
0x180011a15  call    wil_details_NtQueryWnfStateData
0x180011a1a  mov     ebx, eax
0x180011a1c  test    eax, eax
0x180011a1e  jnz     loc_180011B0D
0x180011a24  mov     r9d, [rsp+1090h+var_1050]
0x180011a29  mov     rax, r12
0x180011a2c  mul     r9
0x180011a2f  shr     rdx, 3
0x180011a33  lea     rcx, [rdx+rdx*2]
0x180011a37  shl     rcx, 2
0x180011a3b  cmp     r9, rcx
0x180011a3e  jz      short loc_180011A48
0x180011a40  xor     r9d, r9d
0x180011a43  mov     [rsp+1090h+var_1050], r9d
0x180011a48  mov     r8, [r14]
0x180011a4b  mov     rax, r12
0x180011a4e  mov     ecx, r9d
0x180011a51  mul     rcx
0x180011a54  mov     rcx, [r14+8]
0x180011a58  mov     rax, r12
0x180011a5b  mov     r11, rdx
0x180011a5e  sub     rcx, r8
0x180011a61  mul     rcx
0x180011a64  shr     r11, 3
0x180011a68  shr     rdx, 3
0x180011a6c  lea     rax, [rdx+rdx*2]
0x180011a70  lea     rdi, [r8+rax*4]
0x180011a74  jmp     short loc_180011AE2
0x180011a76  mov     eax, r11d
0x180011a79  lea     r10, [rsp+1090h+var_1040]
0x180011a7e  lea     rcx, [rax+rax*2]
0x180011a82  lea     r10, [r10+rcx*4]
0x180011a86  cmp     rdx, r10
0x180011a89  jz      short loc_180011AB1
0x180011a8b  mov     eax, [r8]
0x180011a8e  cmp     [rdx], eax
0x180011a90  jnz     short loc_180011A9D
0x180011a92  movzx   eax, word ptr [r8+4]
0x180011a97  cmp     [rdx+4], ax
0x180011a9b  jz      short loc_180011AA3
0x180011a9d  add     rdx, 0Ch
0x180011aa1  jmp     short loc_180011A86
0x180011aa3  mov     eax, [r8+8]
0x180011aa7  add     [rdx+8], eax
0x180011aaa  mov     r9d, [rsp+1090h+var_1050]
0x180011aaf  jmp     short loc_180011ADE
0x180011ab1  mov     eax, r9d
0x180011ab4  add     rax, 0Ch
0x180011ab8  cmp     rax, 1000h
0x180011abe  ja      short loc_180011ADE
0x180011ac0  movsd   xmm0, qword ptr [r8]
0x180011ac5  add     r9d, 0Ch
0x180011ac9  movsd   qword ptr [r10], xmm0
0x180011ace  inc     r11d
0x180011ad1  mov     eax, [r8+8]
0x180011ad5  mov     [r10+8], eax
0x180011ad9  mov     [rsp+1090h+var_1050], r9d
0x180011ade  add     r8, 0Ch
0x180011ae2  lea     rdx, [rsp+1090h+var_1040]
0x180011ae7  cmp     r8, rdi
0x180011aea  jnz     short loc_180011A76
0x180011aec  mov     eax, [rsp+1090h+var_104C]
0x180011af0  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180011af7  mov     [rsp+1090h+var_1060], 1
0x180011aff  mov     r8d, r9d
0x180011b02  mov     dword ptr [rsp+1090h+var_1068], eax
0x180011b06  call    wil_details_NtUpdateWnfStateData
0x180011b0b  mov     edi, eax
0x180011b0d  cmp     edi, 0C0000001h
0x180011b13  jnz     short loc_180011B24
0x180011b15  inc     esi
0x180011b17  cmp     esi, 64h ; 'd'
0x180011b1a  jge     short loc_180011B24
0x180011b1c  test    ebx, ebx
0x180011b1e  jz      loc_1800119D3
0x180011b24  test    ebx, ebx
0x180011b26  cmovz   ebx, edi
0x180011b29  mov     eax, ebx
0x180011b2b  mov     rcx, [rbp+0F90h+var_40]
0x180011b32  xor     rcx, rsp; StackCookie
0x180011b35  call    __security_check_cookie
0x180011b3a  add     rsp, 1068h
0x180011b41  pop     r14
0x180011b43  pop     r12
0x180011b45  pop     rdi
0x180011b46  pop     rsi
0x180011b47  pop     rbx
0x180011b48  pop     rbp
0x180011b49  retn
```
