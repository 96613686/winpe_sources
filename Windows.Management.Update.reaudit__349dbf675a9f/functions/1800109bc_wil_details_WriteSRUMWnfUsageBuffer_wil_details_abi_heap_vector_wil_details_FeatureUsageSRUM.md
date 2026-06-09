# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x1800109bc`
- end: `0x180010ba9`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `493`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180008f30`

## callees

- `0x180002880`
- `0x1800035cc`
- `0x1800109bc`
- `0x180010e64`
- `0x180010f0c`
- `0x180028a60`

## pseudocode

```c
__int64 __fastcall wil_details_WriteSRUMWnfUsageBuffer(__int64 *a1)
{
  unsigned int WnfStateData; // ebx
  unsigned int updated; // edi
  int v4; // esi
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // r8
  unsigned int v9; // r10d
  unsigned __int64 v10; // rdi
  _DWORD *v11; // rdx
  _DWORD *v12; // rcx
  int v14; // [rsp+20h] [rbp-E0h]
  unsigned int v15; // [rsp+40h] [rbp-C0h] BYREF
  int v16[3]; // [rsp+44h] [rbp-BCh] BYREF
  _DWORD v17[1024]; // [rsp+50h] [rbp-B0h] BYREF

  WnfStateData = 0;
  updated = 0;
  if ( (unsigned __int64)(a1[1] - *a1) >= 0xC )
  {
    v4 = 0;
    do
    {
      memset_0(v17, 0, sizeof(v17));
      v16[0] = 0;
      v15 = 4096;
      WnfStateData = wil_details_NtQueryWnfStateData(
                       (__int64)&__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM,
                       v5,
                       v6,
                       (__int64)v16,
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
          v12 = v17;
          if ( v17 == v11 )
          {
LABEL_11:
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
            while ( *v12 != *(_DWORD *)v8 || *((_WORD *)v12 + 2) != *(_WORD *)(v8 + 4) )
            {
              v12 += 3;
              if ( v12 == v11 )
                goto LABEL_11;
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
                    v16[0],
                    1);
      }
      ++v4;
    }
    while ( updated == -1073741823 && v4 < 100 && !WnfStateData );
  }
  if ( !WnfStateData )
    return updated;
  return WnfStateData;
}

```

## disassembly

```asm
0x1800109bc  mov     rax, rsp
0x1800109bf  mov     [rax+8], rbx
0x1800109c3  mov     [rax+10h], rsi
0x1800109c7  mov     [rax+18h], rdi
0x1800109cb  push    rbp
0x1800109cc  push    r12
0x1800109ce  push    r14
0x1800109d0  lea     rbp, [rax-0F78h]
0x1800109d7  mov     eax, 1060h
0x1800109dc  call    _alloca_probe
0x1800109e1  sub     rsp, rax
0x1800109e4  mov     rax, cs:__security_cookie
0x1800109eb  xor     rax, rsp
0x1800109ee  mov     [rbp+0F70h+var_20], rax
0x1800109f5  mov     rax, [rcx+8]
0x1800109f9  xor     ebx, ebx
0x1800109fb  sub     rax, [rcx]
0x1800109fe  xor     edi, edi
0x180010a00  mov     r14, rcx
0x180010a03  cmp     rax, 0Ch
0x180010a07  jb      loc_180010B64
0x180010a0d  xor     esi, esi
0x180010a0f  mov     r12, 0AAAAAAAAAAAAAAABh
0x180010a19  xor     edx, edx; Val
0x180010a1b  lea     rcx, [rsp+1070h+var_1020]; void *
0x180010a20  mov     r8d, 1000h; Size
0x180010a26  call    memset_0
0x180010a2b  and     [rsp+1070h+var_102C], 0
0x180010a30  lea     rax, [rsp+1070h+var_1030]
0x180010a35  mov     qword ptr [rsp+1070h+var_1048], rax
0x180010a3a  lea     r9, [rsp+1070h+var_102C]
0x180010a3f  lea     rax, [rsp+1070h+var_1020]
0x180010a44  mov     [rsp+1070h+var_1030], 1000h
0x180010a4c  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180010a53  mov     [rsp+1070h+var_1050], rax
0x180010a58  call    wil_details_NtQueryWnfStateData
0x180010a5d  mov     ebx, eax
0x180010a5f  test    eax, eax
0x180010a61  jnz     loc_180010B4D
0x180010a67  mov     r9d, [rsp+1070h+var_1030]
0x180010a6c  mov     rax, r12
0x180010a6f  mul     r9
0x180010a72  shr     rdx, 3
0x180010a76  lea     rcx, [rdx+rdx*2]
0x180010a7a  shl     rcx, 2
0x180010a7e  cmp     r9, rcx
0x180010a81  jz      short loc_180010A8B
0x180010a83  xor     r9d, r9d
0x180010a86  mov     [rsp+1070h+var_1030], r9d
0x180010a8b  mov     r8, [r14]
0x180010a8e  mov     rax, r12
0x180010a91  mov     ecx, r9d
0x180010a94  mul     rcx
0x180010a97  mov     rcx, [r14+8]
0x180010a9b  mov     rax, r12
0x180010a9e  mov     r10, rdx
0x180010aa1  sub     rcx, r8
0x180010aa4  mul     rcx
0x180010aa7  shr     r10, 3
0x180010aab  shr     rdx, 3
0x180010aaf  lea     rax, [rdx+rdx*2]
0x180010ab3  lea     rdi, [r8+rax*4]
0x180010ab7  jmp     short loc_180010B22
0x180010ab9  mov     eax, r10d
0x180010abc  lea     rcx, [rax+rax*2]
0x180010ac0  lea     rdx, [rdx+rcx*4]
0x180010ac4  lea     rax, [rsp+1070h+var_1020]
0x180010ac9  lea     rcx, [rsp+1070h+var_1020]
0x180010ace  cmp     rax, rdx
0x180010ad1  jz      short loc_180010AF3
0x180010ad3  mov     r11d, [r8]
0x180010ad6  cmp     [rcx], r11d
0x180010ad9  jnz     short loc_180010AEA
0x180010adb  movzx   eax, word ptr [r8+4]
0x180010ae0  cmp     [rcx+4], ax
0x180010ae4  jz      loc_180010B98
0x180010aea  add     rcx, 0Ch
0x180010aee  cmp     rcx, rdx
0x180010af1  jnz     short loc_180010AD6
0x180010af3  mov     eax, r9d
0x180010af6  add     rax, 0Ch
0x180010afa  cmp     rax, 1000h
0x180010b00  ja      short loc_180010B1E
0x180010b02  movsd   xmm0, qword ptr [r8]
0x180010b07  add     r9d, 0Ch
0x180010b0b  movsd   qword ptr [rdx], xmm0
0x180010b0f  inc     r10d
0x180010b12  mov     eax, [r8+8]
0x180010b16  mov     [rdx+8], eax
0x180010b19  mov     [rsp+1070h+var_1030], r9d
0x180010b1e  add     r8, 0Ch
0x180010b22  lea     rdx, [rsp+1070h+var_1020]
0x180010b27  cmp     r8, rdi
0x180010b2a  jnz     short loc_180010AB9
0x180010b2c  mov     eax, [rsp+1070h+var_102C]
0x180010b30  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180010b37  mov     [rsp+1070h+var_1040], 1
0x180010b3f  mov     r8d, r9d
0x180010b42  mov     [rsp+1070h+var_1048], eax
0x180010b46  call    wil_details_NtUpdateWnfStateData
0x180010b4b  mov     edi, eax
0x180010b4d  inc     esi
0x180010b4f  cmp     edi, 0C0000001h
0x180010b55  jnz     short loc_180010B64
0x180010b57  cmp     esi, 64h ; 'd'
0x180010b5a  jge     short loc_180010B64
0x180010b5c  test    ebx, ebx
0x180010b5e  jz      loc_180010A19
0x180010b64  test    ebx, ebx
0x180010b66  cmovz   ebx, edi
0x180010b69  mov     eax, ebx
0x180010b6b  mov     rcx, [rbp+0F70h+var_20]
0x180010b72  xor     rcx, rsp; StackCookie
0x180010b75  call    __security_check_cookie
0x180010b7a  lea     r11, [rsp+1070h+var_10]
0x180010b82  mov     rbx, [r11+20h]
0x180010b86  mov     rsi, [r11+28h]
0x180010b8a  mov     rdi, [r11+30h]
0x180010b8e  mov     rsp, r11
0x180010b91  pop     r14
0x180010b93  pop     r12
0x180010b95  pop     rbp
0x180010b96  retn
0x180010b98  mov     eax, [r8+8]
0x180010b9c  add     [rcx+8], eax
0x180010b9f  mov     r9d, [rsp+1070h+var_1030]
0x180010ba4  jmp     loc_180010B1E
```
