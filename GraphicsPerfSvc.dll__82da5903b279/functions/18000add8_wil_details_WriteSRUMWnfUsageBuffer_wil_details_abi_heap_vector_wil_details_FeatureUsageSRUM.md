# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000add8`
- end: `0x18000afa2`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180004c30`

## callees

- `0x180003ab0`
- `0x1800047f0`
- `0x18000add8`
- `0x18000b24c`
- `0x18000b2c4`
- `0x18002f0d0`

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
0x18000add8  push    rbp
0x18000adda  push    rbx
0x18000addb  push    rsi
0x18000addc  push    rdi
0x18000addd  push    r12
0x18000addf  push    r14
0x18000ade1  lea     rbp, [rsp-0F68h]
0x18000ade9  mov     eax, 1068h
0x18000adee  call    _alloca_probe
0x18000adf3  sub     rsp, rax
0x18000adf6  mov     rax, cs:__security_cookie
0x18000adfd  xor     rax, rsp
0x18000ae00  mov     [rbp+0F90h+var_40], rax
0x18000ae07  mov     rax, [rcx+8]
0x18000ae0b  xor     ebx, ebx
0x18000ae0d  sub     rax, [rcx]
0x18000ae10  xor     edi, edi
0x18000ae12  mov     r14, rcx
0x18000ae15  cmp     rax, 0Ch
0x18000ae19  jb      loc_18000AF7C
0x18000ae1f  xor     esi, esi
0x18000ae21  mov     r12, 0AAAAAAAAAAAAAAABh
0x18000ae2b  xor     edx, edx; Val
0x18000ae2d  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000ae32  mov     r8d, 1000h; Size
0x18000ae38  call    memset_0
0x18000ae3d  lea     rax, [rsp+1090h+var_1050]
0x18000ae42  mov     [rsp+1090h+var_1050], 1000h
0x18000ae4a  mov     [rsp+1090h+var_1068], rax
0x18000ae4f  lea     r9, [rsp+1090h+var_104C]
0x18000ae54  lea     rax, [rsp+1090h+var_1040]
0x18000ae59  mov     [rsp+1090h+var_104C], 0
0x18000ae61  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000ae68  mov     [rsp+1090h+var_1070], rax
0x18000ae6d  call    wil_details_NtQueryWnfStateData
0x18000ae72  mov     ebx, eax
0x18000ae74  test    eax, eax
0x18000ae76  jnz     loc_18000AF65
0x18000ae7c  mov     r9d, [rsp+1090h+var_1050]
0x18000ae81  mov     rax, r12
0x18000ae84  mul     r9
0x18000ae87  shr     rdx, 3
0x18000ae8b  lea     rcx, [rdx+rdx*2]
0x18000ae8f  shl     rcx, 2
0x18000ae93  cmp     r9, rcx
0x18000ae96  jz      short loc_18000AEA0
0x18000ae98  xor     r9d, r9d
0x18000ae9b  mov     [rsp+1090h+var_1050], r9d
0x18000aea0  mov     r8, [r14]
0x18000aea3  mov     rax, r12
0x18000aea6  mov     ecx, r9d
0x18000aea9  mul     rcx
0x18000aeac  mov     rcx, [r14+8]
0x18000aeb0  mov     rax, r12
0x18000aeb3  mov     r11, rdx
0x18000aeb6  sub     rcx, r8
0x18000aeb9  mul     rcx
0x18000aebc  shr     r11, 3
0x18000aec0  shr     rdx, 3
0x18000aec4  lea     rax, [rdx+rdx*2]
0x18000aec8  lea     rdi, [r8+rax*4]
0x18000aecc  jmp     short loc_18000AF3A
0x18000aece  mov     eax, r11d
0x18000aed1  lea     r10, [rsp+1090h+var_1040]
0x18000aed6  lea     rcx, [rax+rax*2]
0x18000aeda  lea     r10, [r10+rcx*4]
0x18000aede  cmp     rdx, r10
0x18000aee1  jz      short loc_18000AF09
0x18000aee3  mov     eax, [r8]
0x18000aee6  cmp     [rdx], eax
0x18000aee8  jnz     short loc_18000AEF5
0x18000aeea  movzx   eax, word ptr [r8+4]
0x18000aeef  cmp     [rdx+4], ax
0x18000aef3  jz      short loc_18000AEFB
0x18000aef5  add     rdx, 0Ch
0x18000aef9  jmp     short loc_18000AEDE
0x18000aefb  mov     eax, [r8+8]
0x18000aeff  add     [rdx+8], eax
0x18000af02  mov     r9d, [rsp+1090h+var_1050]
0x18000af07  jmp     short loc_18000AF36
0x18000af09  mov     eax, r9d
0x18000af0c  add     rax, 0Ch
0x18000af10  cmp     rax, 1000h
0x18000af16  ja      short loc_18000AF36
0x18000af18  movsd   xmm0, qword ptr [r8]
0x18000af1d  add     r9d, 0Ch
0x18000af21  movsd   qword ptr [r10], xmm0
0x18000af26  inc     r11d
0x18000af29  mov     eax, [r8+8]
0x18000af2d  mov     [r10+8], eax
0x18000af31  mov     [rsp+1090h+var_1050], r9d
0x18000af36  add     r8, 0Ch
0x18000af3a  lea     rdx, [rsp+1090h+var_1040]
0x18000af3f  cmp     r8, rdi
0x18000af42  jnz     short loc_18000AECE
0x18000af44  mov     eax, [rsp+1090h+var_104C]
0x18000af48  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000af4f  mov     [rsp+1090h+var_1060], 1
0x18000af57  mov     r8d, r9d
0x18000af5a  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000af5e  call    wil_details_NtUpdateWnfStateData
0x18000af63  mov     edi, eax
0x18000af65  cmp     edi, 0C0000001h
0x18000af6b  jnz     short loc_18000AF7C
0x18000af6d  inc     esi
0x18000af6f  cmp     esi, 64h ; 'd'
0x18000af72  jge     short loc_18000AF7C
0x18000af74  test    ebx, ebx
0x18000af76  jz      loc_18000AE2B
0x18000af7c  test    ebx, ebx
0x18000af7e  cmovz   ebx, edi
0x18000af81  mov     eax, ebx
0x18000af83  mov     rcx, [rbp+0F90h+var_40]
0x18000af8a  xor     rcx, rsp; StackCookie
0x18000af8d  call    __security_check_cookie
0x18000af92  add     rsp, 1068h
0x18000af99  pop     r14
0x18000af9b  pop     r12
0x18000af9d  pop     rdi
0x18000af9e  pop     rsi
0x18000af9f  pop     rbx
0x18000afa0  pop     rbp
0x18000afa1  retn
```
