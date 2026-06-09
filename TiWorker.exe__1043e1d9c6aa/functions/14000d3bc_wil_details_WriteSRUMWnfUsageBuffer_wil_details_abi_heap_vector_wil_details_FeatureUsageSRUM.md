# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x14000d3bc`
- end: `0x14000d586`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140009ab0`

## callees

- `0x140002310`
- `0x140002cf8`
- `0x14000d3bc`
- `0x14000d668`
- `0x14000d6e0`
- `0x14002ac80`

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
0x14000d3bc  push    rbp
0x14000d3be  push    rbx
0x14000d3bf  push    rsi
0x14000d3c0  push    rdi
0x14000d3c1  push    r12
0x14000d3c3  push    r14
0x14000d3c5  lea     rbp, [rsp-0F68h]
0x14000d3cd  mov     eax, 1068h
0x14000d3d2  call    _alloca_probe
0x14000d3d7  sub     rsp, rax
0x14000d3da  mov     rax, cs:__security_cookie
0x14000d3e1  xor     rax, rsp
0x14000d3e4  mov     [rbp+0F90h+var_40], rax
0x14000d3eb  mov     rax, [rcx+8]
0x14000d3ef  xor     ebx, ebx
0x14000d3f1  sub     rax, [rcx]
0x14000d3f4  xor     edi, edi
0x14000d3f6  mov     r14, rcx
0x14000d3f9  cmp     rax, 0Ch
0x14000d3fd  jb      loc_14000D560
0x14000d403  xor     esi, esi
0x14000d405  mov     r12, 0AAAAAAAAAAAAAAABh
0x14000d40f  xor     edx, edx; Val
0x14000d411  lea     rcx, [rsp+1090h+var_1040]; void *
0x14000d416  mov     r8d, 1000h; Size
0x14000d41c  call    memset_0
0x14000d421  lea     rax, [rsp+1090h+var_1050]
0x14000d426  mov     [rsp+1090h+var_1050], 1000h
0x14000d42e  mov     [rsp+1090h+var_1068], rax
0x14000d433  lea     r9, [rsp+1090h+var_104C]
0x14000d438  lea     rax, [rsp+1090h+var_1040]
0x14000d43d  mov     [rsp+1090h+var_104C], 0
0x14000d445  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000d44c  mov     [rsp+1090h+var_1070], rax
0x14000d451  call    wil_details_NtQueryWnfStateData
0x14000d456  mov     ebx, eax
0x14000d458  test    eax, eax
0x14000d45a  jnz     loc_14000D549
0x14000d460  mov     r9d, [rsp+1090h+var_1050]
0x14000d465  mov     rax, r12
0x14000d468  mul     r9
0x14000d46b  shr     rdx, 3
0x14000d46f  lea     rcx, [rdx+rdx*2]
0x14000d473  shl     rcx, 2
0x14000d477  cmp     r9, rcx
0x14000d47a  jz      short loc_14000D484
0x14000d47c  xor     r9d, r9d
0x14000d47f  mov     [rsp+1090h+var_1050], r9d
0x14000d484  mov     r8, [r14]
0x14000d487  mov     rax, r12
0x14000d48a  mov     ecx, r9d
0x14000d48d  mul     rcx
0x14000d490  mov     rcx, [r14+8]
0x14000d494  mov     rax, r12
0x14000d497  mov     r11, rdx
0x14000d49a  sub     rcx, r8
0x14000d49d  mul     rcx
0x14000d4a0  shr     r11, 3
0x14000d4a4  shr     rdx, 3
0x14000d4a8  lea     rax, [rdx+rdx*2]
0x14000d4ac  lea     rdi, [r8+rax*4]
0x14000d4b0  jmp     short loc_14000D51E
0x14000d4b2  mov     eax, r11d
0x14000d4b5  lea     r10, [rsp+1090h+var_1040]
0x14000d4ba  lea     rcx, [rax+rax*2]
0x14000d4be  lea     r10, [r10+rcx*4]
0x14000d4c2  cmp     rdx, r10
0x14000d4c5  jz      short loc_14000D4ED
0x14000d4c7  mov     eax, [r8]
0x14000d4ca  cmp     [rdx], eax
0x14000d4cc  jnz     short loc_14000D4D9
0x14000d4ce  movzx   eax, word ptr [r8+4]
0x14000d4d3  cmp     [rdx+4], ax
0x14000d4d7  jz      short loc_14000D4DF
0x14000d4d9  add     rdx, 0Ch
0x14000d4dd  jmp     short loc_14000D4C2
0x14000d4df  mov     eax, [r8+8]
0x14000d4e3  add     [rdx+8], eax
0x14000d4e6  mov     r9d, [rsp+1090h+var_1050]
0x14000d4eb  jmp     short loc_14000D51A
0x14000d4ed  mov     eax, r9d
0x14000d4f0  add     rax, 0Ch
0x14000d4f4  cmp     rax, 1000h
0x14000d4fa  ja      short loc_14000D51A
0x14000d4fc  movsd   xmm0, qword ptr [r8]
0x14000d501  add     r9d, 0Ch
0x14000d505  movsd   qword ptr [r10], xmm0
0x14000d50a  inc     r11d
0x14000d50d  mov     eax, [r8+8]
0x14000d511  mov     [r10+8], eax
0x14000d515  mov     [rsp+1090h+var_1050], r9d
0x14000d51a  add     r8, 0Ch
0x14000d51e  lea     rdx, [rsp+1090h+var_1040]
0x14000d523  cmp     r8, rdi
0x14000d526  jnz     short loc_14000D4B2
0x14000d528  mov     eax, [rsp+1090h+var_104C]
0x14000d52c  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000d533  mov     [rsp+1090h+var_1060], 1
0x14000d53b  mov     r8d, r9d
0x14000d53e  mov     dword ptr [rsp+1090h+var_1068], eax
0x14000d542  call    wil_details_NtUpdateWnfStateData
0x14000d547  mov     edi, eax
0x14000d549  cmp     edi, 0C0000001h
0x14000d54f  jnz     short loc_14000D560
0x14000d551  inc     esi
0x14000d553  cmp     esi, 64h ; 'd'
0x14000d556  jge     short loc_14000D560
0x14000d558  test    ebx, ebx
0x14000d55a  jz      loc_14000D40F
0x14000d560  test    ebx, ebx
0x14000d562  cmovz   ebx, edi
0x14000d565  mov     eax, ebx
0x14000d567  mov     rcx, [rbp+0F90h+var_40]
0x14000d56e  xor     rcx, rsp; StackCookie
0x14000d571  call    __security_check_cookie
0x14000d576  add     rsp, 1068h
0x14000d57d  pop     r14
0x14000d57f  pop     r12
0x14000d581  pop     rdi
0x14000d582  pop     rsi
0x14000d583  pop     rbx
0x14000d584  pop     rbp
0x14000d585  retn
```
