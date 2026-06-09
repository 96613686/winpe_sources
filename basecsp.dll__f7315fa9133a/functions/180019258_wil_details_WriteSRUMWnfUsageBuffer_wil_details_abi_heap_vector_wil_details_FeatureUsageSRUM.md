# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180019258`
- end: `0x180019422`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18000a880`

## callees

- `0x18000a772`
- `0x180019258`
- `0x180019ee0`
- `0x180019f58`
- `0x18002cfa0`
- `0x18002d060`

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
0x180019258  push    rbp
0x18001925a  push    rbx
0x18001925b  push    rsi
0x18001925c  push    rdi
0x18001925d  push    r12
0x18001925f  push    r14
0x180019261  lea     rbp, [rsp-0F68h]
0x180019269  mov     eax, 1068h
0x18001926e  call    _alloca_probe
0x180019273  sub     rsp, rax
0x180019276  mov     rax, cs:__security_cookie
0x18001927d  xor     rax, rsp
0x180019280  mov     [rbp+0F90h+var_40], rax
0x180019287  mov     rax, [rcx+8]
0x18001928b  xor     ebx, ebx
0x18001928d  sub     rax, [rcx]
0x180019290  xor     edi, edi
0x180019292  mov     r14, rcx
0x180019295  cmp     rax, 0Ch
0x180019299  jb      loc_1800193FC
0x18001929f  xor     esi, esi
0x1800192a1  mov     r12, 0AAAAAAAAAAAAAAABh
0x1800192ab  xor     edx, edx; Val
0x1800192ad  lea     rcx, [rsp+1090h+var_1040]; void *
0x1800192b2  mov     r8d, 1000h; Size
0x1800192b8  call    memset_0
0x1800192bd  lea     rax, [rsp+1090h+var_1050]
0x1800192c2  mov     [rsp+1090h+var_1050], 1000h
0x1800192ca  mov     [rsp+1090h+var_1068], rax
0x1800192cf  lea     r9, [rsp+1090h+var_104C]
0x1800192d4  lea     rax, [rsp+1090h+var_1040]
0x1800192d9  mov     [rsp+1090h+var_104C], 0
0x1800192e1  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1800192e8  mov     [rsp+1090h+var_1070], rax
0x1800192ed  call    wil_details_NtQueryWnfStateData
0x1800192f2  mov     ebx, eax
0x1800192f4  test    eax, eax
0x1800192f6  jnz     loc_1800193E5
0x1800192fc  mov     r9d, [rsp+1090h+var_1050]
0x180019301  mov     rax, r12
0x180019304  mul     r9
0x180019307  shr     rdx, 3
0x18001930b  lea     rcx, [rdx+rdx*2]
0x18001930f  shl     rcx, 2
0x180019313  cmp     r9, rcx
0x180019316  jz      short loc_180019320
0x180019318  xor     r9d, r9d
0x18001931b  mov     [rsp+1090h+var_1050], r9d
0x180019320  mov     r8, [r14]
0x180019323  mov     rax, r12
0x180019326  mov     ecx, r9d
0x180019329  mul     rcx
0x18001932c  mov     rcx, [r14+8]
0x180019330  mov     rax, r12
0x180019333  mov     r11, rdx
0x180019336  sub     rcx, r8
0x180019339  mul     rcx
0x18001933c  shr     r11, 3
0x180019340  shr     rdx, 3
0x180019344  lea     rax, [rdx+rdx*2]
0x180019348  lea     rdi, [r8+rax*4]
0x18001934c  jmp     short loc_1800193BA
0x18001934e  mov     eax, r11d
0x180019351  lea     r10, [rsp+1090h+var_1040]
0x180019356  lea     rcx, [rax+rax*2]
0x18001935a  lea     r10, [r10+rcx*4]
0x18001935e  cmp     rdx, r10
0x180019361  jz      short loc_180019389
0x180019363  mov     eax, [r8]
0x180019366  cmp     [rdx], eax
0x180019368  jnz     short loc_180019375
0x18001936a  movzx   eax, word ptr [r8+4]
0x18001936f  cmp     [rdx+4], ax
0x180019373  jz      short loc_18001937B
0x180019375  add     rdx, 0Ch
0x180019379  jmp     short loc_18001935E
0x18001937b  mov     eax, [r8+8]
0x18001937f  add     [rdx+8], eax
0x180019382  mov     r9d, [rsp+1090h+var_1050]
0x180019387  jmp     short loc_1800193B6
0x180019389  mov     eax, r9d
0x18001938c  add     rax, 0Ch
0x180019390  cmp     rax, 1000h
0x180019396  ja      short loc_1800193B6
0x180019398  movsd   xmm0, qword ptr [r8]
0x18001939d  add     r9d, 0Ch
0x1800193a1  movsd   qword ptr [r10], xmm0
0x1800193a6  inc     r11d
0x1800193a9  mov     eax, [r8+8]
0x1800193ad  mov     [r10+8], eax
0x1800193b1  mov     [rsp+1090h+var_1050], r9d
0x1800193b6  add     r8, 0Ch
0x1800193ba  lea     rdx, [rsp+1090h+var_1040]
0x1800193bf  cmp     r8, rdi
0x1800193c2  jnz     short loc_18001934E
0x1800193c4  mov     eax, [rsp+1090h+var_104C]
0x1800193c8  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1800193cf  mov     [rsp+1090h+var_1060], 1
0x1800193d7  mov     r8d, r9d
0x1800193da  mov     dword ptr [rsp+1090h+var_1068], eax
0x1800193de  call    wil_details_NtUpdateWnfStateData
0x1800193e3  mov     edi, eax
0x1800193e5  cmp     edi, 0C0000001h
0x1800193eb  jnz     short loc_1800193FC
0x1800193ed  inc     esi
0x1800193ef  cmp     esi, 64h ; 'd'
0x1800193f2  jge     short loc_1800193FC
0x1800193f4  test    ebx, ebx
0x1800193f6  jz      loc_1800192AB
0x1800193fc  test    ebx, ebx
0x1800193fe  cmovz   ebx, edi
0x180019401  mov     eax, ebx
0x180019403  mov     rcx, [rbp+0F90h+var_40]
0x18001940a  xor     rcx, rsp; StackCookie
0x18001940d  call    __security_check_cookie
0x180019412  add     rsp, 1068h
0x180019419  pop     r14
0x18001941b  pop     r12
0x18001941d  pop     rdi
0x18001941e  pop     rsi
0x18001941f  pop     rbx
0x180019420  pop     rbp
0x180019421  retn
```
