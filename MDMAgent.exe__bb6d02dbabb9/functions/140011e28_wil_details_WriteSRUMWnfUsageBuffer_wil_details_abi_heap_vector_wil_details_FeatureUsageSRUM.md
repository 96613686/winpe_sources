# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x140011e28`
- end: `0x140011ff3`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `459`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140008db0`

## callees

- `0x1400029c0`
- `0x14000353c`
- `0x140011e28`
- `0x14001251c`
- `0x140012594`
- `0x140019340`

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
0x140011e28  push    rbp
0x140011e2a  push    rbx
0x140011e2b  push    rsi
0x140011e2c  push    rdi
0x140011e2d  push    r12
0x140011e2f  push    r14
0x140011e31  lea     rbp, [rsp-0F68h]
0x140011e39  mov     eax, 1068h
0x140011e3e  call    _alloca_probe
0x140011e43  sub     rsp, rax
0x140011e46  mov     rax, cs:__security_cookie
0x140011e4d  xor     rax, rsp
0x140011e50  mov     [rbp+0F90h+var_40], rax
0x140011e57  mov     rax, [rcx+8]
0x140011e5b  xor     ebx, ebx
0x140011e5d  sub     rax, [rcx]
0x140011e60  xor     edi, edi
0x140011e62  mov     r14, rcx
0x140011e65  cmp     rax, 0Ch
0x140011e69  jb      loc_140011FCC
0x140011e6f  xor     esi, esi
0x140011e71  mov     r12, 0AAAAAAAAAAAAAAABh
0x140011e7b  xor     edx, edx; Val
0x140011e7d  lea     rcx, [rsp+1090h+var_1040]; void *
0x140011e82  mov     r8d, 1000h; Size
0x140011e88  call    memset_0
0x140011e8d  lea     rax, [rsp+1090h+var_1050]
0x140011e92  mov     [rsp+1090h+var_1050], 1000h
0x140011e9a  mov     [rsp+1090h+var_1068], rax
0x140011e9f  lea     r9, [rsp+1090h+var_104C]
0x140011ea4  lea     rax, [rsp+1090h+var_1040]
0x140011ea9  mov     [rsp+1090h+var_104C], 0
0x140011eb1  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x140011eb8  mov     [rsp+1090h+var_1070], rax
0x140011ebd  call    wil_details_NtQueryWnfStateData
0x140011ec2  mov     ebx, eax
0x140011ec4  test    eax, eax
0x140011ec6  jnz     loc_140011FB5
0x140011ecc  mov     r9d, [rsp+1090h+var_1050]
0x140011ed1  mov     rax, r12
0x140011ed4  mul     r9
0x140011ed7  shr     rdx, 3
0x140011edb  lea     rcx, [rdx+rdx*2]
0x140011edf  shl     rcx, 2
0x140011ee3  cmp     r9, rcx
0x140011ee6  jz      short loc_140011EF0
0x140011ee8  xor     r9d, r9d
0x140011eeb  mov     [rsp+1090h+var_1050], r9d
0x140011ef0  mov     r8, [r14]
0x140011ef3  mov     rax, r12
0x140011ef6  mov     ecx, r9d
0x140011ef9  mul     rcx
0x140011efc  mov     rcx, [r14+8]
0x140011f00  mov     rax, r12
0x140011f03  mov     r11, rdx
0x140011f06  sub     rcx, r8
0x140011f09  mul     rcx
0x140011f0c  shr     r11, 3
0x140011f10  shr     rdx, 3
0x140011f14  lea     rax, [rdx+rdx*2]
0x140011f18  lea     rdi, [r8+rax*4]
0x140011f1c  jmp     short loc_140011F8A
0x140011f1e  mov     eax, r11d
0x140011f21  lea     r10, [rsp+1090h+var_1040]
0x140011f26  lea     rcx, [rax+rax*2]
0x140011f2a  lea     r10, [r10+rcx*4]
0x140011f2e  cmp     rdx, r10
0x140011f31  jz      short loc_140011F59
0x140011f33  mov     eax, [r8]
0x140011f36  cmp     [rdx], eax
0x140011f38  jnz     short loc_140011F45
0x140011f3a  movzx   eax, word ptr [r8+4]
0x140011f3f  cmp     [rdx+4], ax
0x140011f43  jz      short loc_140011F4B
0x140011f45  add     rdx, 0Ch
0x140011f49  jmp     short loc_140011F2E
0x140011f4b  mov     eax, [r8+8]
0x140011f4f  add     [rdx+8], eax
0x140011f52  mov     r9d, [rsp+1090h+var_1050]
0x140011f57  jmp     short loc_140011F86
0x140011f59  mov     eax, r9d
0x140011f5c  add     rax, 0Ch
0x140011f60  cmp     rax, 1000h
0x140011f66  ja      short loc_140011F86
0x140011f68  movsd   xmm0, qword ptr [r8]
0x140011f6d  add     r9d, 0Ch
0x140011f71  movsd   qword ptr [r10], xmm0
0x140011f76  inc     r11d
0x140011f79  mov     eax, [r8+8]
0x140011f7d  mov     [r10+8], eax
0x140011f81  mov     [rsp+1090h+var_1050], r9d
0x140011f86  add     r8, 0Ch
0x140011f8a  lea     rdx, [rsp+1090h+var_1040]
0x140011f8f  cmp     r8, rdi
0x140011f92  jnz     short loc_140011F1E
0x140011f94  mov     eax, [rsp+1090h+var_104C]
0x140011f98  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x140011f9f  mov     [rsp+1090h+var_1060], 1
0x140011fa7  mov     r8d, r9d
0x140011faa  mov     dword ptr [rsp+1090h+var_1068], eax
0x140011fae  call    wil_details_NtUpdateWnfStateData
0x140011fb3  mov     edi, eax
0x140011fb5  cmp     edi, 0C0000001h
0x140011fbb  jnz     short loc_140011FCC
0x140011fbd  inc     esi
0x140011fbf  cmp     esi, 64h ; 'd'
0x140011fc2  jge     short loc_140011FCC
0x140011fc4  test    ebx, ebx
0x140011fc6  jz      loc_140011E7B
0x140011fcc  test    ebx, ebx
0x140011fce  cmovz   ebx, edi
0x140011fd1  mov     eax, ebx
0x140011fd3  mov     rcx, [rbp+0F90h+var_40]
0x140011fda  xor     rcx, rsp; StackCookie
0x140011fdd  call    __security_check_cookie
0x140011fe2  add     rsp, 1068h
0x140011fe9  pop     r14
0x140011feb  pop     r12
0x140011fed  pop     rdi
0x140011fee  pop     rsi
0x140011fef  pop     rbx
0x140011ff0  pop     rbp
0x140011ff1  retn
```
