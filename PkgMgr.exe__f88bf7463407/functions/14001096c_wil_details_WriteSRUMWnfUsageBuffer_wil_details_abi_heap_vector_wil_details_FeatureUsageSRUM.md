# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x14001096c`
- end: `0x140010b36`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x14000e1f0`

## callees

- `0x140002360`
- `0x140002d98`
- `0x14001096c`
- `0x140012120`
- `0x140012198`
- `0x140029b70`

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
0x14001096c  push    rbp
0x14001096e  push    rbx
0x14001096f  push    rsi
0x140010970  push    rdi
0x140010971  push    r12
0x140010973  push    r14
0x140010975  lea     rbp, [rsp-0F68h]
0x14001097d  mov     eax, 1068h
0x140010982  call    _alloca_probe
0x140010987  sub     rsp, rax
0x14001098a  mov     rax, cs:__security_cookie
0x140010991  xor     rax, rsp
0x140010994  mov     [rbp+0F90h+var_40], rax
0x14001099b  mov     rax, [rcx+8]
0x14001099f  xor     ebx, ebx
0x1400109a1  sub     rax, [rcx]
0x1400109a4  xor     edi, edi
0x1400109a6  mov     r14, rcx
0x1400109a9  cmp     rax, 0Ch
0x1400109ad  jb      loc_140010B10
0x1400109b3  xor     esi, esi
0x1400109b5  mov     r12, 0AAAAAAAAAAAAAAABh
0x1400109bf  xor     edx, edx; Val
0x1400109c1  lea     rcx, [rsp+1090h+var_1040]; void *
0x1400109c6  mov     r8d, 1000h; Size
0x1400109cc  call    memset_0
0x1400109d1  lea     rax, [rsp+1090h+var_1050]
0x1400109d6  mov     [rsp+1090h+var_1050], 1000h
0x1400109de  mov     [rsp+1090h+var_1068], rax
0x1400109e3  lea     r9, [rsp+1090h+var_104C]
0x1400109e8  lea     rax, [rsp+1090h+var_1040]
0x1400109ed  mov     [rsp+1090h+var_104C], 0
0x1400109f5  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1400109fc  mov     [rsp+1090h+var_1070], rax
0x140010a01  call    wil_details_NtQueryWnfStateData
0x140010a06  mov     ebx, eax
0x140010a08  test    eax, eax
0x140010a0a  jnz     loc_140010AF9
0x140010a10  mov     r9d, [rsp+1090h+var_1050]
0x140010a15  mov     rax, r12
0x140010a18  mul     r9
0x140010a1b  shr     rdx, 3
0x140010a1f  lea     rcx, [rdx+rdx*2]
0x140010a23  shl     rcx, 2
0x140010a27  cmp     r9, rcx
0x140010a2a  jz      short loc_140010A34
0x140010a2c  xor     r9d, r9d
0x140010a2f  mov     [rsp+1090h+var_1050], r9d
0x140010a34  mov     r8, [r14]
0x140010a37  mov     rax, r12
0x140010a3a  mov     ecx, r9d
0x140010a3d  mul     rcx
0x140010a40  mov     rcx, [r14+8]
0x140010a44  mov     rax, r12
0x140010a47  mov     r11, rdx
0x140010a4a  sub     rcx, r8
0x140010a4d  mul     rcx
0x140010a50  shr     r11, 3
0x140010a54  shr     rdx, 3
0x140010a58  lea     rax, [rdx+rdx*2]
0x140010a5c  lea     rdi, [r8+rax*4]
0x140010a60  jmp     short loc_140010ACE
0x140010a62  mov     eax, r11d
0x140010a65  lea     r10, [rsp+1090h+var_1040]
0x140010a6a  lea     rcx, [rax+rax*2]
0x140010a6e  lea     r10, [r10+rcx*4]
0x140010a72  cmp     rdx, r10
0x140010a75  jz      short loc_140010A9D
0x140010a77  mov     eax, [r8]
0x140010a7a  cmp     [rdx], eax
0x140010a7c  jnz     short loc_140010A89
0x140010a7e  movzx   eax, word ptr [r8+4]
0x140010a83  cmp     [rdx+4], ax
0x140010a87  jz      short loc_140010A8F
0x140010a89  add     rdx, 0Ch
0x140010a8d  jmp     short loc_140010A72
0x140010a8f  mov     eax, [r8+8]
0x140010a93  add     [rdx+8], eax
0x140010a96  mov     r9d, [rsp+1090h+var_1050]
0x140010a9b  jmp     short loc_140010ACA
0x140010a9d  mov     eax, r9d
0x140010aa0  add     rax, 0Ch
0x140010aa4  cmp     rax, 1000h
0x140010aaa  ja      short loc_140010ACA
0x140010aac  movsd   xmm0, qword ptr [r8]
0x140010ab1  add     r9d, 0Ch
0x140010ab5  movsd   qword ptr [r10], xmm0
0x140010aba  inc     r11d
0x140010abd  mov     eax, [r8+8]
0x140010ac1  mov     [r10+8], eax
0x140010ac5  mov     [rsp+1090h+var_1050], r9d
0x140010aca  add     r8, 0Ch
0x140010ace  lea     rdx, [rsp+1090h+var_1040]
0x140010ad3  cmp     r8, rdi
0x140010ad6  jnz     short loc_140010A62
0x140010ad8  mov     eax, [rsp+1090h+var_104C]
0x140010adc  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x140010ae3  mov     [rsp+1090h+var_1060], 1
0x140010aeb  mov     r8d, r9d
0x140010aee  mov     dword ptr [rsp+1090h+var_1068], eax
0x140010af2  call    wil_details_NtUpdateWnfStateData
0x140010af7  mov     edi, eax
0x140010af9  cmp     edi, 0C0000001h
0x140010aff  jnz     short loc_140010B10
0x140010b01  inc     esi
0x140010b03  cmp     esi, 64h ; 'd'
0x140010b06  jge     short loc_140010B10
0x140010b08  test    ebx, ebx
0x140010b0a  jz      loc_1400109BF
0x140010b10  test    ebx, ebx
0x140010b12  cmovz   ebx, edi
0x140010b15  mov     eax, ebx
0x140010b17  mov     rcx, [rbp+0F90h+var_40]
0x140010b1e  xor     rcx, rsp; StackCookie
0x140010b21  call    __security_check_cookie
0x140010b26  add     rsp, 1068h
0x140010b2d  pop     r14
0x140010b2f  pop     r12
0x140010b31  pop     rdi
0x140010b32  pop     rsi
0x140010b33  pop     rbx
0x140010b34  pop     rbp
0x140010b35  retn
```
