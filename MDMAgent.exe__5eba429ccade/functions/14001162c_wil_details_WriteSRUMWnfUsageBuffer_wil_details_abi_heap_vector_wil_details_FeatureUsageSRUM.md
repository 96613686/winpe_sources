# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x14001162c`
- end: `0x1400117f6`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1400089c0`

## callees

- `0x140002930`
- `0x14000349c`
- `0x14001162c`
- `0x140011d00`
- `0x140011d78`
- `0x1400185e0`

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
0x14001162c  push    rbp
0x14001162e  push    rbx
0x14001162f  push    rsi
0x140011630  push    rdi
0x140011631  push    r12
0x140011633  push    r14
0x140011635  lea     rbp, [rsp-0F68h]
0x14001163d  mov     eax, 1068h
0x140011642  call    _alloca_probe
0x140011647  sub     rsp, rax
0x14001164a  mov     rax, cs:__security_cookie
0x140011651  xor     rax, rsp
0x140011654  mov     [rbp+0F90h+var_40], rax
0x14001165b  mov     rax, [rcx+8]
0x14001165f  xor     ebx, ebx
0x140011661  sub     rax, [rcx]
0x140011664  xor     edi, edi
0x140011666  mov     r14, rcx
0x140011669  cmp     rax, 0Ch
0x14001166d  jb      loc_1400117D0
0x140011673  xor     esi, esi
0x140011675  mov     r12, 0AAAAAAAAAAAAAAABh
0x14001167f  xor     edx, edx; Val
0x140011681  lea     rcx, [rsp+1090h+var_1040]; void *
0x140011686  mov     r8d, 1000h; Size
0x14001168c  call    memset_0
0x140011691  lea     rax, [rsp+1090h+var_1050]
0x140011696  mov     [rsp+1090h+var_1050], 1000h
0x14001169e  mov     [rsp+1090h+var_1068], rax
0x1400116a3  lea     r9, [rsp+1090h+var_104C]
0x1400116a8  lea     rax, [rsp+1090h+var_1040]
0x1400116ad  mov     [rsp+1090h+var_104C], 0
0x1400116b5  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1400116bc  mov     [rsp+1090h+var_1070], rax
0x1400116c1  call    wil_details_NtQueryWnfStateData
0x1400116c6  mov     ebx, eax
0x1400116c8  test    eax, eax
0x1400116ca  jnz     loc_1400117B9
0x1400116d0  mov     r9d, [rsp+1090h+var_1050]
0x1400116d5  mov     rax, r12
0x1400116d8  mul     r9
0x1400116db  shr     rdx, 3
0x1400116df  lea     rcx, [rdx+rdx*2]
0x1400116e3  shl     rcx, 2
0x1400116e7  cmp     r9, rcx
0x1400116ea  jz      short loc_1400116F4
0x1400116ec  xor     r9d, r9d
0x1400116ef  mov     [rsp+1090h+var_1050], r9d
0x1400116f4  mov     r8, [r14]
0x1400116f7  mov     rax, r12
0x1400116fa  mov     ecx, r9d
0x1400116fd  mul     rcx
0x140011700  mov     rcx, [r14+8]
0x140011704  mov     rax, r12
0x140011707  mov     r11, rdx
0x14001170a  sub     rcx, r8
0x14001170d  mul     rcx
0x140011710  shr     r11, 3
0x140011714  shr     rdx, 3
0x140011718  lea     rax, [rdx+rdx*2]
0x14001171c  lea     rdi, [r8+rax*4]
0x140011720  jmp     short loc_14001178E
0x140011722  mov     eax, r11d
0x140011725  lea     r10, [rsp+1090h+var_1040]
0x14001172a  lea     rcx, [rax+rax*2]
0x14001172e  lea     r10, [r10+rcx*4]
0x140011732  cmp     rdx, r10
0x140011735  jz      short loc_14001175D
0x140011737  mov     eax, [r8]
0x14001173a  cmp     [rdx], eax
0x14001173c  jnz     short loc_140011749
0x14001173e  movzx   eax, word ptr [r8+4]
0x140011743  cmp     [rdx+4], ax
0x140011747  jz      short loc_14001174F
0x140011749  add     rdx, 0Ch
0x14001174d  jmp     short loc_140011732
0x14001174f  mov     eax, [r8+8]
0x140011753  add     [rdx+8], eax
0x140011756  mov     r9d, [rsp+1090h+var_1050]
0x14001175b  jmp     short loc_14001178A
0x14001175d  mov     eax, r9d
0x140011760  add     rax, 0Ch
0x140011764  cmp     rax, 1000h
0x14001176a  ja      short loc_14001178A
0x14001176c  movsd   xmm0, qword ptr [r8]
0x140011771  add     r9d, 0Ch
0x140011775  movsd   qword ptr [r10], xmm0
0x14001177a  inc     r11d
0x14001177d  mov     eax, [r8+8]
0x140011781  mov     [r10+8], eax
0x140011785  mov     [rsp+1090h+var_1050], r9d
0x14001178a  add     r8, 0Ch
0x14001178e  lea     rdx, [rsp+1090h+var_1040]
0x140011793  cmp     r8, rdi
0x140011796  jnz     short loc_140011722
0x140011798  mov     eax, [rsp+1090h+var_104C]
0x14001179c  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1400117a3  mov     [rsp+1090h+var_1060], 1
0x1400117ab  mov     r8d, r9d
0x1400117ae  mov     dword ptr [rsp+1090h+var_1068], eax
0x1400117b2  call    wil_details_NtUpdateWnfStateData
0x1400117b7  mov     edi, eax
0x1400117b9  cmp     edi, 0C0000001h
0x1400117bf  jnz     short loc_1400117D0
0x1400117c1  inc     esi
0x1400117c3  cmp     esi, 64h ; 'd'
0x1400117c6  jge     short loc_1400117D0
0x1400117c8  test    ebx, ebx
0x1400117ca  jz      loc_14001167F
0x1400117d0  test    ebx, ebx
0x1400117d2  cmovz   ebx, edi
0x1400117d5  mov     eax, ebx
0x1400117d7  mov     rcx, [rbp+0F90h+var_40]
0x1400117de  xor     rcx, rsp; StackCookie
0x1400117e1  call    __security_check_cookie
0x1400117e6  add     rsp, 1068h
0x1400117ed  pop     r14
0x1400117ef  pop     r12
0x1400117f1  pop     rdi
0x1400117f2  pop     rsi
0x1400117f3  pop     rbx
0x1400117f4  pop     rbp
0x1400117f5  retn
```
