# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x140007818`
- end: `0x1400079ed`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `469`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140002170`

## callees

- `0x1400014c0`
- `0x14000209c`
- `0x140007818`
- `0x140007af0`
- `0x140007b68`
- `0x140008750`

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
        v9 = v7 / 0xC;
        v10 = *a1 + 12 * ((a1[1] - *a1) / 0xCuLL);
        while ( v8 != v10 )
        {
          v11 = &v17[3 * v9];
          if ( v17 == v11 )
          {
LABEL_12:
            if ( (unsigned __int64)v7 + 12 <= 0x1000 )
            {
              v7 += 12;
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
0x140007818  push    rbp
0x14000781a  push    rbx
0x14000781b  push    rsi
0x14000781c  push    rdi
0x14000781d  push    r12
0x14000781f  push    r14
0x140007821  lea     rbp, [rsp-0F68h]
0x140007829  mov     eax, 1068h
0x14000782e  call    _alloca_probe
0x140007833  sub     rsp, rax
0x140007836  mov     rax, cs:__security_cookie
0x14000783d  xor     rax, rsp
0x140007840  mov     [rbp+0F90h+var_40], rax
0x140007847  mov     rax, [rcx+8]
0x14000784b  xor     ebx, ebx
0x14000784d  sub     rax, [rcx]
0x140007850  xor     edi, edi
0x140007852  mov     r14, rcx
0x140007855  cmp     rax, 0Ch
0x140007859  jb      loc_1400079B9
0x14000785f  xor     esi, esi
0x140007861  mov     r12, 0AAAAAAAAAAAAAAABh
0x14000786b  xor     edx, edx; Val
0x14000786d  lea     rcx, [rsp+1090h+var_1040]; void *
0x140007872  mov     r8d, 1000h; Size
0x140007878  call    memset_0
0x14000787d  lea     rax, [rsp+1090h+var_1050]
0x140007882  mov     [rsp+1090h+var_1050], 1000h
0x14000788a  mov     [rsp+1090h+var_1068], rax
0x14000788f  lea     r9, [rsp+1090h+var_104C]
0x140007894  lea     rax, [rsp+1090h+var_1040]
0x140007899  mov     [rsp+1090h+var_104C], 0
0x1400078a1  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1400078a8  mov     [rsp+1090h+var_1070], rax
0x1400078ad  call    wil_details_NtQueryWnfStateData
0x1400078b2  mov     ebx, eax
0x1400078b4  test    eax, eax
0x1400078b6  jnz     loc_1400079A2
0x1400078bc  mov     r9d, [rsp+1090h+var_1050]
0x1400078c1  mov     rax, r12
0x1400078c4  mul     r9
0x1400078c7  shr     rdx, 3
0x1400078cb  lea     rcx, [rdx+rdx*2]
0x1400078cf  shl     rcx, 2
0x1400078d3  cmp     r9, rcx
0x1400078d6  jz      short loc_1400078E0
0x1400078d8  xor     r9d, r9d
0x1400078db  mov     [rsp+1090h+var_1050], r9d
0x1400078e0  mov     r8, [r14]
0x1400078e3  mov     rax, r12
0x1400078e6  mov     ecx, r9d
0x1400078e9  mul     rcx
0x1400078ec  mov     rcx, [r14+8]
0x1400078f0  mov     rax, r12
0x1400078f3  mov     r10, rdx
0x1400078f6  sub     rcx, r8
0x1400078f9  mul     rcx
0x1400078fc  shr     r10, 3
0x140007900  shr     rdx, 3
0x140007904  lea     rax, [rdx+rdx*2]
0x140007908  lea     rdi, [r8+rax*4]
0x14000790c  jmp     short loc_140007977
0x14000790e  mov     eax, r10d
0x140007911  lea     rcx, [rax+rax*2]
0x140007915  lea     rdx, [rdx+rcx*4]
0x140007919  lea     rax, [rsp+1090h+var_1040]
0x14000791e  cmp     rax, rdx
0x140007921  jz      short loc_140007948
0x140007923  mov     r11d, [r8]
0x140007926  lea     rcx, [rsp+1090h+var_1040]
0x14000792b  cmp     [rcx], r11d
0x14000792e  jnz     short loc_14000793F
0x140007930  movzx   eax, word ptr [r8+4]
0x140007935  cmp     [rcx+4], ax
0x140007939  jz      loc_1400079DF
0x14000793f  add     rcx, 0Ch
0x140007943  cmp     rcx, rdx
0x140007946  jnz     short loc_14000792B
0x140007948  mov     eax, r9d
0x14000794b  add     rax, 0Ch
0x14000794f  cmp     rax, 1000h
0x140007955  ja      short loc_140007973
0x140007957  movsd   xmm0, qword ptr [r8]
0x14000795c  add     r9d, 0Ch
0x140007960  movsd   qword ptr [rdx], xmm0
0x140007964  inc     r10d
0x140007967  mov     eax, [r8+8]
0x14000796b  mov     [rdx+8], eax
0x14000796e  mov     [rsp+1090h+var_1050], r9d
0x140007973  add     r8, 0Ch
0x140007977  lea     rdx, [rsp+1090h+var_1040]
0x14000797c  cmp     r8, rdi
0x14000797f  jnz     short loc_14000790E
0x140007981  mov     eax, [rsp+1090h+var_104C]
0x140007985  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000798c  mov     [rsp+1090h+var_1060], 1
0x140007994  mov     r8d, r9d
0x140007997  mov     dword ptr [rsp+1090h+var_1068], eax
0x14000799b  call    wil_details_NtUpdateWnfStateData
0x1400079a0  mov     edi, eax
0x1400079a2  cmp     edi, 0C0000001h
0x1400079a8  jnz     short loc_1400079B9
0x1400079aa  inc     esi
0x1400079ac  cmp     esi, 64h ; 'd'
0x1400079af  jge     short loc_1400079B9
0x1400079b1  test    ebx, ebx
0x1400079b3  jz      loc_14000786B
0x1400079b9  test    ebx, ebx
0x1400079bb  cmovz   ebx, edi
0x1400079be  mov     eax, ebx
0x1400079c0  mov     rcx, [rbp+0F90h+var_40]
0x1400079c7  xor     rcx, rsp; StackCookie
0x1400079ca  call    __security_check_cookie
0x1400079cf  add     rsp, 1068h
0x1400079d6  pop     r14
0x1400079d8  pop     r12
0x1400079da  pop     rdi
0x1400079db  pop     rsi
0x1400079dc  pop     rbx
0x1400079dd  pop     rbp
0x1400079de  retn
0x1400079df  mov     eax, [r8+8]
0x1400079e3  add     [rcx+8], eax
0x1400079e6  mov     r9d, [rsp+1090h+var_1050]
0x1400079eb  jmp     short loc_140007973
```
