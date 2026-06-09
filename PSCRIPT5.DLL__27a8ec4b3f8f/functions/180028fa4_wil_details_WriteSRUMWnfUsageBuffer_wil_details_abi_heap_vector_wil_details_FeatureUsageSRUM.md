# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180028fa4`
- end: `0x18002917a`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `470`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800232c0`

## callees

- `0x180001f20`
- `0x180002938`
- `0x180028fa4`
- `0x18002986c`
- `0x180029914`
- `0x18005e040`

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
      v15 = 4096;
      v16[0] = 0;
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
                    v16[0],
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
0x180028fa4  push    rbp
0x180028fa6  push    rbx
0x180028fa7  push    rsi
0x180028fa8  push    rdi
0x180028fa9  push    r12
0x180028fab  push    r14
0x180028fad  lea     rbp, [rsp-0F68h]
0x180028fb5  mov     eax, 1068h
0x180028fba  call    _alloca_probe
0x180028fbf  sub     rsp, rax
0x180028fc2  mov     rax, cs:__security_cookie
0x180028fc9  xor     rax, rsp
0x180028fcc  mov     [rbp+0F90h+var_40], rax
0x180028fd3  mov     rax, [rcx+8]
0x180028fd7  xor     ebx, ebx
0x180028fd9  sub     rax, [rcx]
0x180028fdc  xor     edi, edi
0x180028fde  mov     r14, rcx
0x180028fe1  cmp     rax, 0Ch
0x180028fe5  jb      loc_180029145
0x180028feb  xor     esi, esi
0x180028fed  mov     r12, 0AAAAAAAAAAAAAAABh
0x180028ff7  xor     edx, edx; Val
0x180028ff9  lea     rcx, [rsp+1090h+var_1040]; void *
0x180028ffe  mov     r8d, 1000h; Size
0x180029004  call    memset_0
0x180029009  lea     rax, [rsp+1090h+var_1050]
0x18002900e  mov     [rsp+1090h+var_1050], 1000h
0x180029016  mov     [rsp+1090h+var_1068], rax
0x18002901b  lea     r9, [rsp+1090h+var_104C]
0x180029020  lea     rax, [rsp+1090h+var_1040]
0x180029025  mov     [rsp+1090h+var_104C], 0
0x18002902d  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180029034  mov     [rsp+1090h+var_1070], rax
0x180029039  call    wil_details_NtQueryWnfStateData
0x18002903e  mov     ebx, eax
0x180029040  test    eax, eax
0x180029042  jnz     loc_18002912E
0x180029048  mov     r9d, [rsp+1090h+var_1050]
0x18002904d  mov     rax, r12
0x180029050  mul     r9
0x180029053  shr     rdx, 3
0x180029057  lea     rcx, [rdx+rdx*2]
0x18002905b  shl     rcx, 2
0x18002905f  cmp     r9, rcx
0x180029062  jz      short loc_18002906C
0x180029064  xor     r9d, r9d
0x180029067  mov     [rsp+1090h+var_1050], r9d
0x18002906c  mov     r8, [r14]
0x18002906f  mov     rax, r12
0x180029072  mov     ecx, r9d
0x180029075  mul     rcx
0x180029078  mov     rcx, [r14+8]
0x18002907c  mov     rax, r12
0x18002907f  mov     r10, rdx
0x180029082  sub     rcx, r8
0x180029085  mul     rcx
0x180029088  shr     r10, 3
0x18002908c  shr     rdx, 3
0x180029090  lea     rax, [rdx+rdx*2]
0x180029094  lea     rdi, [r8+rax*4]
0x180029098  jmp     short loc_180029103
0x18002909a  mov     eax, r10d
0x18002909d  lea     rcx, [rax+rax*2]
0x1800290a1  lea     rdx, [rdx+rcx*4]
0x1800290a5  lea     rax, [rsp+1090h+var_1040]
0x1800290aa  cmp     rax, rdx
0x1800290ad  jz      short loc_1800290D4
0x1800290af  mov     r11d, [r8]
0x1800290b2  lea     rcx, [rsp+1090h+var_1040]
0x1800290b7  cmp     [rcx], r11d
0x1800290ba  jnz     short loc_1800290CB
0x1800290bc  movzx   eax, word ptr [r8+4]
0x1800290c1  cmp     [rcx+4], ax
0x1800290c5  jz      loc_18002916C
0x1800290cb  add     rcx, 0Ch
0x1800290cf  cmp     rcx, rdx
0x1800290d2  jnz     short loc_1800290B7
0x1800290d4  mov     eax, r9d
0x1800290d7  add     rax, 0Ch
0x1800290db  cmp     rax, 1000h
0x1800290e1  ja      short loc_1800290FF
0x1800290e3  movsd   xmm0, qword ptr [r8]
0x1800290e8  add     r9d, 0Ch
0x1800290ec  movsd   qword ptr [rdx], xmm0
0x1800290f0  inc     r10d
0x1800290f3  mov     eax, [r8+8]
0x1800290f7  mov     [rdx+8], eax
0x1800290fa  mov     [rsp+1090h+var_1050], r9d
0x1800290ff  add     r8, 0Ch
0x180029103  lea     rdx, [rsp+1090h+var_1040]
0x180029108  cmp     r8, rdi
0x18002910b  jnz     short loc_18002909A
0x18002910d  mov     eax, [rsp+1090h+var_104C]
0x180029111  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180029118  mov     [rsp+1090h+var_1060], 1
0x180029120  mov     r8d, r9d
0x180029123  mov     dword ptr [rsp+1090h+var_1068], eax
0x180029127  call    wil_details_NtUpdateWnfStateData
0x18002912c  mov     edi, eax
0x18002912e  cmp     edi, 0C0000001h
0x180029134  jnz     short loc_180029145
0x180029136  inc     esi
0x180029138  cmp     esi, 64h ; 'd'
0x18002913b  jge     short loc_180029145
0x18002913d  test    ebx, ebx
0x18002913f  jz      loc_180028FF7
0x180029145  test    ebx, ebx
0x180029147  cmovz   ebx, edi
0x18002914a  mov     eax, ebx
0x18002914c  mov     rcx, [rbp+0F90h+var_40]
0x180029153  xor     rcx, rsp; StackCookie
0x180029156  call    __security_check_cookie
0x18002915b  add     rsp, 1068h
0x180029162  pop     r14
0x180029164  pop     r12
0x180029166  pop     rdi
0x180029167  pop     rsi
0x180029168  pop     rbx
0x180029169  pop     rbp
0x18002916a  retn
0x18002916c  mov     eax, [r8+8]
0x180029170  add     [rcx+8], eax
0x180029173  mov     r9d, [rsp+1090h+var_1050]
0x180029178  jmp     short loc_1800290FF
```
