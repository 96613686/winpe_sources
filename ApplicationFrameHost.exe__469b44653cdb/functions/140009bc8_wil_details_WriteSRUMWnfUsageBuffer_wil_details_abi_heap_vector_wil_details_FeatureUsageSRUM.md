# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x140009bc8`
- end: `0x140009d92`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1400041a0`

## callees

- `0x1400031b0`
- `0x140003de8`
- `0x140009bc8`
- `0x140009e88`
- `0x140009f00`
- `0x14000a3b0`

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
0x140009bc8  push    rbp
0x140009bca  push    rbx
0x140009bcb  push    rsi
0x140009bcc  push    rdi
0x140009bcd  push    r12
0x140009bcf  push    r14
0x140009bd1  lea     rbp, [rsp-0F68h]
0x140009bd9  mov     eax, 1068h
0x140009bde  call    _alloca_probe
0x140009be3  sub     rsp, rax
0x140009be6  mov     rax, cs:__security_cookie
0x140009bed  xor     rax, rsp
0x140009bf0  mov     [rbp+0F90h+var_40], rax
0x140009bf7  mov     rax, [rcx+8]
0x140009bfb  xor     ebx, ebx
0x140009bfd  sub     rax, [rcx]
0x140009c00  xor     edi, edi
0x140009c02  mov     r14, rcx
0x140009c05  cmp     rax, 0Ch
0x140009c09  jb      loc_140009D6C
0x140009c0f  xor     esi, esi
0x140009c11  mov     r12, 0AAAAAAAAAAAAAAABh
0x140009c1b  xor     edx, edx; Val
0x140009c1d  lea     rcx, [rsp+1090h+var_1040]; void *
0x140009c22  mov     r8d, 1000h; Size
0x140009c28  call    memset_0
0x140009c2d  lea     rax, [rsp+1090h+var_1050]
0x140009c32  mov     [rsp+1090h+var_1050], 1000h
0x140009c3a  mov     [rsp+1090h+var_1068], rax
0x140009c3f  lea     r9, [rsp+1090h+var_104C]
0x140009c44  lea     rax, [rsp+1090h+var_1040]
0x140009c49  mov     [rsp+1090h+var_104C], 0
0x140009c51  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x140009c58  mov     [rsp+1090h+var_1070], rax
0x140009c5d  call    wil_details_NtQueryWnfStateData
0x140009c62  mov     ebx, eax
0x140009c64  test    eax, eax
0x140009c66  jnz     loc_140009D55
0x140009c6c  mov     r9d, [rsp+1090h+var_1050]
0x140009c71  mov     rax, r12
0x140009c74  mul     r9
0x140009c77  shr     rdx, 3
0x140009c7b  lea     rcx, [rdx+rdx*2]
0x140009c7f  shl     rcx, 2
0x140009c83  cmp     r9, rcx
0x140009c86  jz      short loc_140009C90
0x140009c88  xor     r9d, r9d
0x140009c8b  mov     [rsp+1090h+var_1050], r9d
0x140009c90  mov     r8, [r14]
0x140009c93  mov     rax, r12
0x140009c96  mov     ecx, r9d
0x140009c99  mul     rcx
0x140009c9c  mov     rcx, [r14+8]
0x140009ca0  mov     rax, r12
0x140009ca3  mov     r11, rdx
0x140009ca6  sub     rcx, r8
0x140009ca9  mul     rcx
0x140009cac  shr     r11, 3
0x140009cb0  shr     rdx, 3
0x140009cb4  lea     rax, [rdx+rdx*2]
0x140009cb8  lea     rdi, [r8+rax*4]
0x140009cbc  jmp     short loc_140009D2A
0x140009cbe  mov     eax, r11d
0x140009cc1  lea     r10, [rsp+1090h+var_1040]
0x140009cc6  lea     rcx, [rax+rax*2]
0x140009cca  lea     r10, [r10+rcx*4]
0x140009cce  cmp     rdx, r10
0x140009cd1  jz      short loc_140009CF9
0x140009cd3  mov     eax, [r8]
0x140009cd6  cmp     [rdx], eax
0x140009cd8  jnz     short loc_140009CE5
0x140009cda  movzx   eax, word ptr [r8+4]
0x140009cdf  cmp     [rdx+4], ax
0x140009ce3  jz      short loc_140009CEB
0x140009ce5  add     rdx, 0Ch
0x140009ce9  jmp     short loc_140009CCE
0x140009ceb  mov     eax, [r8+8]
0x140009cef  add     [rdx+8], eax
0x140009cf2  mov     r9d, [rsp+1090h+var_1050]
0x140009cf7  jmp     short loc_140009D26
0x140009cf9  mov     eax, r9d
0x140009cfc  add     rax, 0Ch
0x140009d00  cmp     rax, 1000h
0x140009d06  ja      short loc_140009D26
0x140009d08  movsd   xmm0, qword ptr [r8]
0x140009d0d  add     r9d, 0Ch
0x140009d11  movsd   qword ptr [r10], xmm0
0x140009d16  inc     r11d
0x140009d19  mov     eax, [r8+8]
0x140009d1d  mov     [r10+8], eax
0x140009d21  mov     [rsp+1090h+var_1050], r9d
0x140009d26  add     r8, 0Ch
0x140009d2a  lea     rdx, [rsp+1090h+var_1040]
0x140009d2f  cmp     r8, rdi
0x140009d32  jnz     short loc_140009CBE
0x140009d34  mov     eax, [rsp+1090h+var_104C]
0x140009d38  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x140009d3f  mov     [rsp+1090h+var_1060], 1
0x140009d47  mov     r8d, r9d
0x140009d4a  mov     dword ptr [rsp+1090h+var_1068], eax
0x140009d4e  call    wil_details_NtUpdateWnfStateData
0x140009d53  mov     edi, eax
0x140009d55  cmp     edi, 0C0000001h
0x140009d5b  jnz     short loc_140009D6C
0x140009d5d  inc     esi
0x140009d5f  cmp     esi, 64h ; 'd'
0x140009d62  jge     short loc_140009D6C
0x140009d64  test    ebx, ebx
0x140009d66  jz      loc_140009C1B
0x140009d6c  test    ebx, ebx
0x140009d6e  cmovz   ebx, edi
0x140009d71  mov     eax, ebx
0x140009d73  mov     rcx, [rbp+0F90h+var_40]
0x140009d7a  xor     rcx, rsp; StackCookie
0x140009d7d  call    __security_check_cookie
0x140009d82  add     rsp, 1068h
0x140009d89  pop     r14
0x140009d8b  pop     r12
0x140009d8d  pop     rdi
0x140009d8e  pop     rsi
0x140009d8f  pop     rbx
0x140009d90  pop     rbp
0x140009d91  retn
```
