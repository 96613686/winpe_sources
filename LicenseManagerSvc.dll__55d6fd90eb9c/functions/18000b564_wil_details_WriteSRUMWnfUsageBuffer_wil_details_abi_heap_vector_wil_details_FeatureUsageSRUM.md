# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000b564`
- end: `0x18000b739`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `469`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180007c30`

## callees

- `0x1800033d0`
- `0x180004184`
- `0x18000b564`
- `0x18000bcec`
- `0x18000bd64`
- `0x1800173f0`

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
0x18000b564  push    rbp
0x18000b566  push    rbx
0x18000b567  push    rsi
0x18000b568  push    rdi
0x18000b569  push    r12
0x18000b56b  push    r14
0x18000b56d  lea     rbp, [rsp-0F68h]
0x18000b575  mov     eax, 1068h
0x18000b57a  call    _alloca_probe
0x18000b57f  sub     rsp, rax
0x18000b582  mov     rax, cs:__security_cookie
0x18000b589  xor     rax, rsp
0x18000b58c  mov     [rbp+0F90h+var_40], rax
0x18000b593  mov     rax, [rcx+8]
0x18000b597  xor     ebx, ebx
0x18000b599  sub     rax, [rcx]
0x18000b59c  xor     edi, edi
0x18000b59e  mov     r14, rcx
0x18000b5a1  cmp     rax, 0Ch
0x18000b5a5  jb      loc_18000B705
0x18000b5ab  xor     esi, esi
0x18000b5ad  mov     r12, 0AAAAAAAAAAAAAAABh
0x18000b5b7  xor     edx, edx; Val
0x18000b5b9  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000b5be  mov     r8d, 1000h; Size
0x18000b5c4  call    memset_0
0x18000b5c9  lea     rax, [rsp+1090h+var_1050]
0x18000b5ce  mov     [rsp+1090h+var_1050], 1000h
0x18000b5d6  mov     [rsp+1090h+var_1068], rax
0x18000b5db  lea     r9, [rsp+1090h+var_104C]
0x18000b5e0  lea     rax, [rsp+1090h+var_1040]
0x18000b5e5  mov     [rsp+1090h+var_104C], 0
0x18000b5ed  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000b5f4  mov     [rsp+1090h+var_1070], rax
0x18000b5f9  call    wil_details_NtQueryWnfStateData
0x18000b5fe  mov     ebx, eax
0x18000b600  test    eax, eax
0x18000b602  jnz     loc_18000B6EE
0x18000b608  mov     r9d, [rsp+1090h+var_1050]
0x18000b60d  mov     rax, r12
0x18000b610  mul     r9
0x18000b613  shr     rdx, 3
0x18000b617  lea     rcx, [rdx+rdx*2]
0x18000b61b  shl     rcx, 2
0x18000b61f  cmp     r9, rcx
0x18000b622  jz      short loc_18000B62C
0x18000b624  xor     r9d, r9d
0x18000b627  mov     [rsp+1090h+var_1050], r9d
0x18000b62c  mov     r8, [r14]
0x18000b62f  mov     rax, r12
0x18000b632  mov     ecx, r9d
0x18000b635  mul     rcx
0x18000b638  mov     rcx, [r14+8]
0x18000b63c  mov     rax, r12
0x18000b63f  mov     r10, rdx
0x18000b642  sub     rcx, r8
0x18000b645  mul     rcx
0x18000b648  shr     r10, 3
0x18000b64c  shr     rdx, 3
0x18000b650  lea     rax, [rdx+rdx*2]
0x18000b654  lea     rdi, [r8+rax*4]
0x18000b658  jmp     short loc_18000B6C3
0x18000b65a  mov     eax, r10d
0x18000b65d  lea     rcx, [rax+rax*2]
0x18000b661  lea     rdx, [rdx+rcx*4]
0x18000b665  lea     rax, [rsp+1090h+var_1040]
0x18000b66a  cmp     rax, rdx
0x18000b66d  jz      short loc_18000B694
0x18000b66f  mov     r11d, [r8]
0x18000b672  lea     rcx, [rsp+1090h+var_1040]
0x18000b677  cmp     [rcx], r11d
0x18000b67a  jnz     short loc_18000B68B
0x18000b67c  movzx   eax, word ptr [r8+4]
0x18000b681  cmp     [rcx+4], ax
0x18000b685  jz      loc_18000B72B
0x18000b68b  add     rcx, 0Ch
0x18000b68f  cmp     rcx, rdx
0x18000b692  jnz     short loc_18000B677
0x18000b694  mov     eax, r9d
0x18000b697  add     rax, 0Ch
0x18000b69b  cmp     rax, 1000h
0x18000b6a1  ja      short loc_18000B6BF
0x18000b6a3  movsd   xmm0, qword ptr [r8]
0x18000b6a8  add     r9d, 0Ch
0x18000b6ac  movsd   qword ptr [rdx], xmm0
0x18000b6b0  inc     r10d
0x18000b6b3  mov     eax, [r8+8]
0x18000b6b7  mov     [rdx+8], eax
0x18000b6ba  mov     [rsp+1090h+var_1050], r9d
0x18000b6bf  add     r8, 0Ch
0x18000b6c3  lea     rdx, [rsp+1090h+var_1040]
0x18000b6c8  cmp     r8, rdi
0x18000b6cb  jnz     short loc_18000B65A
0x18000b6cd  mov     eax, [rsp+1090h+var_104C]
0x18000b6d1  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000b6d8  mov     [rsp+1090h+var_1060], 1
0x18000b6e0  mov     r8d, r9d
0x18000b6e3  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000b6e7  call    wil_details_NtUpdateWnfStateData
0x18000b6ec  mov     edi, eax
0x18000b6ee  cmp     edi, 0C0000001h
0x18000b6f4  jnz     short loc_18000B705
0x18000b6f6  inc     esi
0x18000b6f8  cmp     esi, 64h ; 'd'
0x18000b6fb  jge     short loc_18000B705
0x18000b6fd  test    ebx, ebx
0x18000b6ff  jz      loc_18000B5B7
0x18000b705  test    ebx, ebx
0x18000b707  cmovz   ebx, edi
0x18000b70a  mov     eax, ebx
0x18000b70c  mov     rcx, [rbp+0F90h+var_40]
0x18000b713  xor     rcx, rsp; StackCookie
0x18000b716  call    __security_check_cookie
0x18000b71b  add     rsp, 1068h
0x18000b722  pop     r14
0x18000b724  pop     r12
0x18000b726  pop     rdi
0x18000b727  pop     rsi
0x18000b728  pop     rbx
0x18000b729  pop     rbp
0x18000b72a  retn
0x18000b72b  mov     eax, [r8+8]
0x18000b72f  add     [rcx+8], eax
0x18000b732  mov     r9d, [rsp+1090h+var_1050]
0x18000b737  jmp     short loc_18000B6BF
```
