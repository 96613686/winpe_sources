# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x14000cf50`
- end: `0x14000d11a`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x14000a080`

## callees

- `0x140008c80`
- `0x140009640`
- `0x14000cf50`
- `0x14000d33c`
- `0x14000d3b4`
- `0x14000f260`

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
0x14000cf50  push    rbp
0x14000cf52  push    rbx
0x14000cf53  push    rsi
0x14000cf54  push    rdi
0x14000cf55  push    r12
0x14000cf57  push    r14
0x14000cf59  lea     rbp, [rsp-0F68h]
0x14000cf61  mov     eax, 1068h
0x14000cf66  call    _alloca_probe
0x14000cf6b  sub     rsp, rax
0x14000cf6e  mov     rax, cs:__security_cookie
0x14000cf75  xor     rax, rsp
0x14000cf78  mov     [rbp+0F90h+var_40], rax
0x14000cf7f  mov     rax, [rcx+8]
0x14000cf83  xor     ebx, ebx
0x14000cf85  sub     rax, [rcx]
0x14000cf88  xor     edi, edi
0x14000cf8a  mov     r14, rcx
0x14000cf8d  cmp     rax, 0Ch
0x14000cf91  jb      loc_14000D0F4
0x14000cf97  xor     esi, esi
0x14000cf99  mov     r12, 0AAAAAAAAAAAAAAABh
0x14000cfa3  xor     edx, edx; Val
0x14000cfa5  lea     rcx, [rsp+1090h+var_1040]; void *
0x14000cfaa  mov     r8d, 1000h; Size
0x14000cfb0  call    memset_0
0x14000cfb5  lea     rax, [rsp+1090h+var_1050]
0x14000cfba  mov     [rsp+1090h+var_1050], 1000h
0x14000cfc2  mov     [rsp+1090h+var_1068], rax
0x14000cfc7  lea     r9, [rsp+1090h+var_104C]
0x14000cfcc  lea     rax, [rsp+1090h+var_1040]
0x14000cfd1  mov     [rsp+1090h+var_104C], 0
0x14000cfd9  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000cfe0  mov     [rsp+1090h+var_1070], rax
0x14000cfe5  call    wil_details_NtQueryWnfStateData
0x14000cfea  mov     ebx, eax
0x14000cfec  test    eax, eax
0x14000cfee  jnz     loc_14000D0DD
0x14000cff4  mov     r9d, [rsp+1090h+var_1050]
0x14000cff9  mov     rax, r12
0x14000cffc  mul     r9
0x14000cfff  shr     rdx, 3
0x14000d003  lea     rcx, [rdx+rdx*2]
0x14000d007  shl     rcx, 2
0x14000d00b  cmp     r9, rcx
0x14000d00e  jz      short loc_14000D018
0x14000d010  xor     r9d, r9d
0x14000d013  mov     [rsp+1090h+var_1050], r9d
0x14000d018  mov     r8, [r14]
0x14000d01b  mov     rax, r12
0x14000d01e  mov     ecx, r9d
0x14000d021  mul     rcx
0x14000d024  mov     rcx, [r14+8]
0x14000d028  mov     rax, r12
0x14000d02b  mov     r11, rdx
0x14000d02e  sub     rcx, r8
0x14000d031  mul     rcx
0x14000d034  shr     r11, 3
0x14000d038  shr     rdx, 3
0x14000d03c  lea     rax, [rdx+rdx*2]
0x14000d040  lea     rdi, [r8+rax*4]
0x14000d044  jmp     short loc_14000D0B2
0x14000d046  mov     eax, r11d
0x14000d049  lea     r10, [rsp+1090h+var_1040]
0x14000d04e  lea     rcx, [rax+rax*2]
0x14000d052  lea     r10, [r10+rcx*4]
0x14000d056  cmp     rdx, r10
0x14000d059  jz      short loc_14000D081
0x14000d05b  mov     eax, [r8]
0x14000d05e  cmp     [rdx], eax
0x14000d060  jnz     short loc_14000D06D
0x14000d062  movzx   eax, word ptr [r8+4]
0x14000d067  cmp     [rdx+4], ax
0x14000d06b  jz      short loc_14000D073
0x14000d06d  add     rdx, 0Ch
0x14000d071  jmp     short loc_14000D056
0x14000d073  mov     eax, [r8+8]
0x14000d077  add     [rdx+8], eax
0x14000d07a  mov     r9d, [rsp+1090h+var_1050]
0x14000d07f  jmp     short loc_14000D0AE
0x14000d081  mov     eax, r9d
0x14000d084  add     rax, 0Ch
0x14000d088  cmp     rax, 1000h
0x14000d08e  ja      short loc_14000D0AE
0x14000d090  movsd   xmm0, qword ptr [r8]
0x14000d095  add     r9d, 0Ch
0x14000d099  movsd   qword ptr [r10], xmm0
0x14000d09e  inc     r11d
0x14000d0a1  mov     eax, [r8+8]
0x14000d0a5  mov     [r10+8], eax
0x14000d0a9  mov     [rsp+1090h+var_1050], r9d
0x14000d0ae  add     r8, 0Ch
0x14000d0b2  lea     rdx, [rsp+1090h+var_1040]
0x14000d0b7  cmp     r8, rdi
0x14000d0ba  jnz     short loc_14000D046
0x14000d0bc  mov     eax, [rsp+1090h+var_104C]
0x14000d0c0  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000d0c7  mov     [rsp+1090h+var_1060], 1
0x14000d0cf  mov     r8d, r9d
0x14000d0d2  mov     dword ptr [rsp+1090h+var_1068], eax
0x14000d0d6  call    wil_details_NtUpdateWnfStateData
0x14000d0db  mov     edi, eax
0x14000d0dd  cmp     edi, 0C0000001h
0x14000d0e3  jnz     short loc_14000D0F4
0x14000d0e5  inc     esi
0x14000d0e7  cmp     esi, 64h ; 'd'
0x14000d0ea  jge     short loc_14000D0F4
0x14000d0ec  test    ebx, ebx
0x14000d0ee  jz      loc_14000CFA3
0x14000d0f4  test    ebx, ebx
0x14000d0f6  cmovz   ebx, edi
0x14000d0f9  mov     eax, ebx
0x14000d0fb  mov     rcx, [rbp+0F90h+var_40]
0x14000d102  xor     rcx, rsp; StackCookie
0x14000d105  call    __security_check_cookie
0x14000d10a  add     rsp, 1068h
0x14000d111  pop     r14
0x14000d113  pop     r12
0x14000d115  pop     rdi
0x14000d116  pop     rsi
0x14000d117  pop     rbx
0x14000d118  pop     rbp
0x14000d119  retn
```
