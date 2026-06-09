# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x140012cc8`
- end: `0x140012e92`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140007d60`

## callees

- `0x140012cc8`
- `0x14001398c`
- `0x140013a04`
- `0x14001a8aa`
- `0x14001a8d0`
- `0x14001a960`

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
0x140012cc8  push    rbp
0x140012cca  push    rbx
0x140012ccb  push    rsi
0x140012ccc  push    rdi
0x140012ccd  push    r12
0x140012ccf  push    r14
0x140012cd1  lea     rbp, [rsp-0F68h]
0x140012cd9  mov     eax, 1068h
0x140012cde  call    _alloca_probe
0x140012ce3  sub     rsp, rax
0x140012ce6  mov     rax, cs:__security_cookie
0x140012ced  xor     rax, rsp
0x140012cf0  mov     [rbp+0F90h+var_40], rax
0x140012cf7  mov     rax, [rcx+8]
0x140012cfb  xor     ebx, ebx
0x140012cfd  sub     rax, [rcx]
0x140012d00  xor     edi, edi
0x140012d02  mov     r14, rcx
0x140012d05  cmp     rax, 0Ch
0x140012d09  jb      loc_140012E6C
0x140012d0f  xor     esi, esi
0x140012d11  mov     r12, 0AAAAAAAAAAAAAAABh
0x140012d1b  xor     edx, edx; Val
0x140012d1d  lea     rcx, [rsp+1090h+var_1040]; void *
0x140012d22  mov     r8d, 1000h; Size
0x140012d28  call    memset_0
0x140012d2d  lea     rax, [rsp+1090h+var_1050]
0x140012d32  mov     [rsp+1090h+var_1050], 1000h
0x140012d3a  mov     [rsp+1090h+var_1068], rax
0x140012d3f  lea     r9, [rsp+1090h+var_104C]
0x140012d44  lea     rax, [rsp+1090h+var_1040]
0x140012d49  mov     [rsp+1090h+var_104C], 0
0x140012d51  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x140012d58  mov     [rsp+1090h+var_1070], rax
0x140012d5d  call    wil_details_NtQueryWnfStateData
0x140012d62  mov     ebx, eax
0x140012d64  test    eax, eax
0x140012d66  jnz     loc_140012E55
0x140012d6c  mov     r9d, [rsp+1090h+var_1050]
0x140012d71  mov     rax, r12
0x140012d74  mul     r9
0x140012d77  shr     rdx, 3
0x140012d7b  lea     rcx, [rdx+rdx*2]
0x140012d7f  shl     rcx, 2
0x140012d83  cmp     r9, rcx
0x140012d86  jz      short loc_140012D90
0x140012d88  xor     r9d, r9d
0x140012d8b  mov     [rsp+1090h+var_1050], r9d
0x140012d90  mov     r8, [r14]
0x140012d93  mov     rax, r12
0x140012d96  mov     ecx, r9d
0x140012d99  mul     rcx
0x140012d9c  mov     rcx, [r14+8]
0x140012da0  mov     rax, r12
0x140012da3  mov     r11, rdx
0x140012da6  sub     rcx, r8
0x140012da9  mul     rcx
0x140012dac  shr     r11, 3
0x140012db0  shr     rdx, 3
0x140012db4  lea     rax, [rdx+rdx*2]
0x140012db8  lea     rdi, [r8+rax*4]
0x140012dbc  jmp     short loc_140012E2A
0x140012dbe  mov     eax, r11d
0x140012dc1  lea     r10, [rsp+1090h+var_1040]
0x140012dc6  lea     rcx, [rax+rax*2]
0x140012dca  lea     r10, [r10+rcx*4]
0x140012dce  cmp     rdx, r10
0x140012dd1  jz      short loc_140012DF9
0x140012dd3  mov     eax, [r8]
0x140012dd6  cmp     [rdx], eax
0x140012dd8  jnz     short loc_140012DE5
0x140012dda  movzx   eax, word ptr [r8+4]
0x140012ddf  cmp     [rdx+4], ax
0x140012de3  jz      short loc_140012DEB
0x140012de5  add     rdx, 0Ch
0x140012de9  jmp     short loc_140012DCE
0x140012deb  mov     eax, [r8+8]
0x140012def  add     [rdx+8], eax
0x140012df2  mov     r9d, [rsp+1090h+var_1050]
0x140012df7  jmp     short loc_140012E26
0x140012df9  mov     eax, r9d
0x140012dfc  add     rax, 0Ch
0x140012e00  cmp     rax, 1000h
0x140012e06  ja      short loc_140012E26
0x140012e08  movsd   xmm0, qword ptr [r8]
0x140012e0d  add     r9d, 0Ch
0x140012e11  movsd   qword ptr [r10], xmm0
0x140012e16  inc     r11d
0x140012e19  mov     eax, [r8+8]
0x140012e1d  mov     [r10+8], eax
0x140012e21  mov     [rsp+1090h+var_1050], r9d
0x140012e26  add     r8, 0Ch
0x140012e2a  lea     rdx, [rsp+1090h+var_1040]
0x140012e2f  cmp     r8, rdi
0x140012e32  jnz     short loc_140012DBE
0x140012e34  mov     eax, [rsp+1090h+var_104C]
0x140012e38  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x140012e3f  mov     [rsp+1090h+var_1060], 1
0x140012e47  mov     r8d, r9d
0x140012e4a  mov     dword ptr [rsp+1090h+var_1068], eax
0x140012e4e  call    wil_details_NtUpdateWnfStateData
0x140012e53  mov     edi, eax
0x140012e55  cmp     edi, 0C0000001h
0x140012e5b  jnz     short loc_140012E6C
0x140012e5d  inc     esi
0x140012e5f  cmp     esi, 64h ; 'd'
0x140012e62  jge     short loc_140012E6C
0x140012e64  test    ebx, ebx
0x140012e66  jz      loc_140012D1B
0x140012e6c  test    ebx, ebx
0x140012e6e  cmovz   ebx, edi
0x140012e71  mov     eax, ebx
0x140012e73  mov     rcx, [rbp+0F90h+var_40]
0x140012e7a  xor     rcx, rsp; StackCookie
0x140012e7d  call    __security_check_cookie
0x140012e82  add     rsp, 1068h
0x140012e89  pop     r14
0x140012e8b  pop     r12
0x140012e8d  pop     rdi
0x140012e8e  pop     rsi
0x140012e8f  pop     rbx
0x140012e90  pop     rbp
0x140012e91  retn
```
