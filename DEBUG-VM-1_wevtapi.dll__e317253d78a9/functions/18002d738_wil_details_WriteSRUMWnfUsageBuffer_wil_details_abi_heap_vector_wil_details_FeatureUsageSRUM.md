# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18002d738`
- end: `0x18002d902`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180029370`

## callees

- `0x1800249f0`
- `0x1800254b4`
- `0x18002d738`
- `0x18002dafc`
- `0x18002db74`
- `0x180038f60`

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
0x18002d738  push    rbp
0x18002d73a  push    rbx
0x18002d73b  push    rsi
0x18002d73c  push    rdi
0x18002d73d  push    r12
0x18002d73f  push    r14
0x18002d741  lea     rbp, [rsp-0F68h]
0x18002d749  mov     eax, 1068h
0x18002d74e  call    _alloca_probe
0x18002d753  sub     rsp, rax
0x18002d756  mov     rax, cs:__security_cookie
0x18002d75d  xor     rax, rsp
0x18002d760  mov     [rbp+0F90h+var_40], rax
0x18002d767  mov     rax, [rcx+8]
0x18002d76b  xor     ebx, ebx
0x18002d76d  sub     rax, [rcx]
0x18002d770  xor     edi, edi
0x18002d772  mov     r14, rcx
0x18002d775  cmp     rax, 0Ch
0x18002d779  jb      loc_18002D8DC
0x18002d77f  xor     esi, esi
0x18002d781  mov     r12, 0AAAAAAAAAAAAAAABh
0x18002d78b  xor     edx, edx; Val
0x18002d78d  lea     rcx, [rsp+1090h+var_1040]; void *
0x18002d792  mov     r8d, 1000h; Size
0x18002d798  call    memset_0
0x18002d79d  lea     rax, [rsp+1090h+var_1050]
0x18002d7a2  mov     [rsp+1090h+var_1050], 1000h
0x18002d7aa  mov     [rsp+1090h+var_1068], rax
0x18002d7af  lea     r9, [rsp+1090h+var_104C]
0x18002d7b4  lea     rax, [rsp+1090h+var_1040]
0x18002d7b9  mov     [rsp+1090h+var_104C], 0
0x18002d7c1  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18002d7c8  mov     [rsp+1090h+var_1070], rax
0x18002d7cd  call    wil_details_NtQueryWnfStateData
0x18002d7d2  mov     ebx, eax
0x18002d7d4  test    eax, eax
0x18002d7d6  jnz     loc_18002D8C5
0x18002d7dc  mov     r9d, [rsp+1090h+var_1050]
0x18002d7e1  mov     rax, r12
0x18002d7e4  mul     r9
0x18002d7e7  shr     rdx, 3
0x18002d7eb  lea     rcx, [rdx+rdx*2]
0x18002d7ef  shl     rcx, 2
0x18002d7f3  cmp     r9, rcx
0x18002d7f6  jz      short loc_18002D800
0x18002d7f8  xor     r9d, r9d
0x18002d7fb  mov     [rsp+1090h+var_1050], r9d
0x18002d800  mov     r8, [r14]
0x18002d803  mov     rax, r12
0x18002d806  mov     ecx, r9d
0x18002d809  mul     rcx
0x18002d80c  mov     rcx, [r14+8]
0x18002d810  mov     rax, r12
0x18002d813  mov     r11, rdx
0x18002d816  sub     rcx, r8
0x18002d819  mul     rcx
0x18002d81c  shr     r11, 3
0x18002d820  shr     rdx, 3
0x18002d824  lea     rax, [rdx+rdx*2]
0x18002d828  lea     rdi, [r8+rax*4]
0x18002d82c  jmp     short loc_18002D89A
0x18002d82e  mov     eax, r11d
0x18002d831  lea     r10, [rsp+1090h+var_1040]
0x18002d836  lea     rcx, [rax+rax*2]
0x18002d83a  lea     r10, [r10+rcx*4]
0x18002d83e  cmp     rdx, r10
0x18002d841  jz      short loc_18002D869
0x18002d843  mov     eax, [r8]
0x18002d846  cmp     [rdx], eax
0x18002d848  jnz     short loc_18002D855
0x18002d84a  movzx   eax, word ptr [r8+4]
0x18002d84f  cmp     [rdx+4], ax
0x18002d853  jz      short loc_18002D85B
0x18002d855  add     rdx, 0Ch
0x18002d859  jmp     short loc_18002D83E
0x18002d85b  mov     eax, [r8+8]
0x18002d85f  add     [rdx+8], eax
0x18002d862  mov     r9d, [rsp+1090h+var_1050]
0x18002d867  jmp     short loc_18002D896
0x18002d869  mov     eax, r9d
0x18002d86c  add     rax, 0Ch
0x18002d870  cmp     rax, 1000h
0x18002d876  ja      short loc_18002D896
0x18002d878  movsd   xmm0, qword ptr [r8]
0x18002d87d  add     r9d, 0Ch
0x18002d881  movsd   qword ptr [r10], xmm0
0x18002d886  inc     r11d
0x18002d889  mov     eax, [r8+8]
0x18002d88d  mov     [r10+8], eax
0x18002d891  mov     [rsp+1090h+var_1050], r9d
0x18002d896  add     r8, 0Ch
0x18002d89a  lea     rdx, [rsp+1090h+var_1040]
0x18002d89f  cmp     r8, rdi
0x18002d8a2  jnz     short loc_18002D82E
0x18002d8a4  mov     eax, [rsp+1090h+var_104C]
0x18002d8a8  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18002d8af  mov     [rsp+1090h+var_1060], 1
0x18002d8b7  mov     r8d, r9d
0x18002d8ba  mov     dword ptr [rsp+1090h+var_1068], eax
0x18002d8be  call    wil_details_NtUpdateWnfStateData
0x18002d8c3  mov     edi, eax
0x18002d8c5  cmp     edi, 0C0000001h
0x18002d8cb  jnz     short loc_18002D8DC
0x18002d8cd  inc     esi
0x18002d8cf  cmp     esi, 64h ; 'd'
0x18002d8d2  jge     short loc_18002D8DC
0x18002d8d4  test    ebx, ebx
0x18002d8d6  jz      loc_18002D78B
0x18002d8dc  test    ebx, ebx
0x18002d8de  cmovz   ebx, edi
0x18002d8e1  mov     eax, ebx
0x18002d8e3  mov     rcx, [rbp+0F90h+var_40]
0x18002d8ea  xor     rcx, rsp; StackCookie
0x18002d8ed  call    __security_check_cookie
0x18002d8f2  add     rsp, 1068h
0x18002d8f9  pop     r14
0x18002d8fb  pop     r12
0x18002d8fd  pop     rdi
0x18002d8fe  pop     rsi
0x18002d8ff  pop     rbx
0x18002d900  pop     rbp
0x18002d901  retn
```
