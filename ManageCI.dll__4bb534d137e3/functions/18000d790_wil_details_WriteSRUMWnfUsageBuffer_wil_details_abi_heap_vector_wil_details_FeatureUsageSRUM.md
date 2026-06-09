# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000d790`
- end: `0x18000d965`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `469`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180009a60`

## callees

- `0x180002a90`
- `0x180003888`
- `0x18000d790`
- `0x18000dac4`
- `0x18000db3c`
- `0x180029780`

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
0x18000d790  push    rbp
0x18000d792  push    rbx
0x18000d793  push    rsi
0x18000d794  push    rdi
0x18000d795  push    r12
0x18000d797  push    r14
0x18000d799  lea     rbp, [rsp-0F68h]
0x18000d7a1  mov     eax, 1068h
0x18000d7a6  call    _alloca_probe
0x18000d7ab  sub     rsp, rax
0x18000d7ae  mov     rax, cs:__security_cookie
0x18000d7b5  xor     rax, rsp
0x18000d7b8  mov     [rbp+0F90h+var_40], rax
0x18000d7bf  mov     rax, [rcx+8]
0x18000d7c3  xor     ebx, ebx
0x18000d7c5  sub     rax, [rcx]
0x18000d7c8  xor     edi, edi
0x18000d7ca  mov     r14, rcx
0x18000d7cd  cmp     rax, 0Ch
0x18000d7d1  jb      loc_18000D931
0x18000d7d7  xor     esi, esi
0x18000d7d9  mov     r12, 0AAAAAAAAAAAAAAABh
0x18000d7e3  xor     edx, edx; Val
0x18000d7e5  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000d7ea  mov     r8d, 1000h; Size
0x18000d7f0  call    memset_0
0x18000d7f5  lea     rax, [rsp+1090h+var_1050]
0x18000d7fa  mov     [rsp+1090h+var_1050], 1000h
0x18000d802  mov     [rsp+1090h+var_1068], rax
0x18000d807  lea     r9, [rsp+1090h+var_104C]
0x18000d80c  lea     rax, [rsp+1090h+var_1040]
0x18000d811  mov     [rsp+1090h+var_104C], 0
0x18000d819  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000d820  mov     [rsp+1090h+var_1070], rax
0x18000d825  call    wil_details_NtQueryWnfStateData
0x18000d82a  mov     ebx, eax
0x18000d82c  test    eax, eax
0x18000d82e  jnz     loc_18000D91A
0x18000d834  mov     r9d, [rsp+1090h+var_1050]
0x18000d839  mov     rax, r12
0x18000d83c  mul     r9
0x18000d83f  shr     rdx, 3
0x18000d843  lea     rcx, [rdx+rdx*2]
0x18000d847  shl     rcx, 2
0x18000d84b  cmp     r9, rcx
0x18000d84e  jz      short loc_18000D858
0x18000d850  xor     r9d, r9d
0x18000d853  mov     [rsp+1090h+var_1050], r9d
0x18000d858  mov     r8, [r14]
0x18000d85b  mov     rax, r12
0x18000d85e  mov     ecx, r9d
0x18000d861  mul     rcx
0x18000d864  mov     rcx, [r14+8]
0x18000d868  mov     rax, r12
0x18000d86b  mov     r10, rdx
0x18000d86e  sub     rcx, r8
0x18000d871  mul     rcx
0x18000d874  shr     r10, 3
0x18000d878  shr     rdx, 3
0x18000d87c  lea     rax, [rdx+rdx*2]
0x18000d880  lea     rdi, [r8+rax*4]
0x18000d884  jmp     short loc_18000D8EF
0x18000d886  mov     eax, r10d
0x18000d889  lea     rcx, [rax+rax*2]
0x18000d88d  lea     rdx, [rdx+rcx*4]
0x18000d891  lea     rax, [rsp+1090h+var_1040]
0x18000d896  cmp     rax, rdx
0x18000d899  jz      short loc_18000D8C0
0x18000d89b  mov     r11d, [r8]
0x18000d89e  lea     rcx, [rsp+1090h+var_1040]
0x18000d8a3  cmp     [rcx], r11d
0x18000d8a6  jnz     short loc_18000D8B7
0x18000d8a8  movzx   eax, word ptr [r8+4]
0x18000d8ad  cmp     [rcx+4], ax
0x18000d8b1  jz      loc_18000D957
0x18000d8b7  add     rcx, 0Ch
0x18000d8bb  cmp     rcx, rdx
0x18000d8be  jnz     short loc_18000D8A3
0x18000d8c0  mov     eax, r9d
0x18000d8c3  add     rax, 0Ch
0x18000d8c7  cmp     rax, 1000h
0x18000d8cd  ja      short loc_18000D8EB
0x18000d8cf  movsd   xmm0, qword ptr [r8]
0x18000d8d4  add     r9d, 0Ch
0x18000d8d8  movsd   qword ptr [rdx], xmm0
0x18000d8dc  inc     r10d
0x18000d8df  mov     eax, [r8+8]
0x18000d8e3  mov     [rdx+8], eax
0x18000d8e6  mov     [rsp+1090h+var_1050], r9d
0x18000d8eb  add     r8, 0Ch
0x18000d8ef  lea     rdx, [rsp+1090h+var_1040]
0x18000d8f4  cmp     r8, rdi
0x18000d8f7  jnz     short loc_18000D886
0x18000d8f9  mov     eax, [rsp+1090h+var_104C]
0x18000d8fd  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000d904  mov     [rsp+1090h+var_1060], 1
0x18000d90c  mov     r8d, r9d
0x18000d90f  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000d913  call    wil_details_NtUpdateWnfStateData
0x18000d918  mov     edi, eax
0x18000d91a  cmp     edi, 0C0000001h
0x18000d920  jnz     short loc_18000D931
0x18000d922  inc     esi
0x18000d924  cmp     esi, 64h ; 'd'
0x18000d927  jge     short loc_18000D931
0x18000d929  test    ebx, ebx
0x18000d92b  jz      loc_18000D7E3
0x18000d931  test    ebx, ebx
0x18000d933  cmovz   ebx, edi
0x18000d936  mov     eax, ebx
0x18000d938  mov     rcx, [rbp+0F90h+var_40]
0x18000d93f  xor     rcx, rsp; StackCookie
0x18000d942  call    __security_check_cookie
0x18000d947  add     rsp, 1068h
0x18000d94e  pop     r14
0x18000d950  pop     r12
0x18000d952  pop     rdi
0x18000d953  pop     rsi
0x18000d954  pop     rbx
0x18000d955  pop     rbp
0x18000d956  retn
0x18000d957  mov     eax, [r8+8]
0x18000d95b  add     [rcx+8], eax
0x18000d95e  mov     r9d, [rsp+1090h+var_1050]
0x18000d963  jmp     short loc_18000D8EB
```
