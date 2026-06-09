# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180008fc4`
- end: `0x18000918e`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180006940`

## callees

- `0x180008fc4`
- `0x18000cff8`
- `0x18000d070`
- `0x18000d2ce`
- `0x18000d300`
- `0x18000d390`

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
0x180008fc4  push    rbp
0x180008fc6  push    rbx
0x180008fc7  push    rsi
0x180008fc8  push    rdi
0x180008fc9  push    r12
0x180008fcb  push    r14
0x180008fcd  lea     rbp, [rsp-0F68h]
0x180008fd5  mov     eax, 1068h
0x180008fda  call    _alloca_probe
0x180008fdf  sub     rsp, rax
0x180008fe2  mov     rax, cs:__security_cookie
0x180008fe9  xor     rax, rsp
0x180008fec  mov     [rbp+0F90h+var_40], rax
0x180008ff3  mov     rax, [rcx+8]
0x180008ff7  xor     ebx, ebx
0x180008ff9  sub     rax, [rcx]
0x180008ffc  xor     edi, edi
0x180008ffe  mov     r14, rcx
0x180009001  cmp     rax, 0Ch
0x180009005  jb      loc_180009168
0x18000900b  xor     esi, esi
0x18000900d  mov     r12, 0AAAAAAAAAAAAAAABh
0x180009017  xor     edx, edx; Val
0x180009019  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000901e  mov     r8d, 1000h; Size
0x180009024  call    memset_0
0x180009029  lea     rax, [rsp+1090h+var_1050]
0x18000902e  mov     [rsp+1090h+var_1050], 1000h
0x180009036  mov     [rsp+1090h+var_1068], rax
0x18000903b  lea     r9, [rsp+1090h+var_104C]
0x180009040  lea     rax, [rsp+1090h+var_1040]
0x180009045  mov     [rsp+1090h+var_104C], 0
0x18000904d  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180009054  mov     [rsp+1090h+var_1070], rax
0x180009059  call    wil_details_NtQueryWnfStateData
0x18000905e  mov     ebx, eax
0x180009060  test    eax, eax
0x180009062  jnz     loc_180009151
0x180009068  mov     r9d, [rsp+1090h+var_1050]
0x18000906d  mov     rax, r12
0x180009070  mul     r9
0x180009073  shr     rdx, 3
0x180009077  lea     rcx, [rdx+rdx*2]
0x18000907b  shl     rcx, 2
0x18000907f  cmp     r9, rcx
0x180009082  jz      short loc_18000908C
0x180009084  xor     r9d, r9d
0x180009087  mov     [rsp+1090h+var_1050], r9d
0x18000908c  mov     r8, [r14]
0x18000908f  mov     rax, r12
0x180009092  mov     ecx, r9d
0x180009095  mul     rcx
0x180009098  mov     rcx, [r14+8]
0x18000909c  mov     rax, r12
0x18000909f  mov     r11, rdx
0x1800090a2  sub     rcx, r8
0x1800090a5  mul     rcx
0x1800090a8  shr     r11, 3
0x1800090ac  shr     rdx, 3
0x1800090b0  lea     rax, [rdx+rdx*2]
0x1800090b4  lea     rdi, [r8+rax*4]
0x1800090b8  jmp     short loc_180009126
0x1800090ba  mov     eax, r11d
0x1800090bd  lea     r10, [rsp+1090h+var_1040]
0x1800090c2  lea     rcx, [rax+rax*2]
0x1800090c6  lea     r10, [r10+rcx*4]
0x1800090ca  cmp     rdx, r10
0x1800090cd  jz      short loc_1800090F5
0x1800090cf  mov     eax, [r8]
0x1800090d2  cmp     [rdx], eax
0x1800090d4  jnz     short loc_1800090E1
0x1800090d6  movzx   eax, word ptr [r8+4]
0x1800090db  cmp     [rdx+4], ax
0x1800090df  jz      short loc_1800090E7
0x1800090e1  add     rdx, 0Ch
0x1800090e5  jmp     short loc_1800090CA
0x1800090e7  mov     eax, [r8+8]
0x1800090eb  add     [rdx+8], eax
0x1800090ee  mov     r9d, [rsp+1090h+var_1050]
0x1800090f3  jmp     short loc_180009122
0x1800090f5  mov     eax, r9d
0x1800090f8  add     rax, 0Ch
0x1800090fc  cmp     rax, 1000h
0x180009102  ja      short loc_180009122
0x180009104  movsd   xmm0, qword ptr [r8]
0x180009109  add     r9d, 0Ch
0x18000910d  movsd   qword ptr [r10], xmm0
0x180009112  inc     r11d
0x180009115  mov     eax, [r8+8]
0x180009119  mov     [r10+8], eax
0x18000911d  mov     [rsp+1090h+var_1050], r9d
0x180009122  add     r8, 0Ch
0x180009126  lea     rdx, [rsp+1090h+var_1040]
0x18000912b  cmp     r8, rdi
0x18000912e  jnz     short loc_1800090BA
0x180009130  mov     eax, [rsp+1090h+var_104C]
0x180009134  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000913b  mov     [rsp+1090h+var_1060], 1
0x180009143  mov     r8d, r9d
0x180009146  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000914a  call    wil_details_NtUpdateWnfStateData
0x18000914f  mov     edi, eax
0x180009151  cmp     edi, 0C0000001h
0x180009157  jnz     short loc_180009168
0x180009159  inc     esi
0x18000915b  cmp     esi, 64h ; 'd'
0x18000915e  jge     short loc_180009168
0x180009160  test    ebx, ebx
0x180009162  jz      loc_180009017
0x180009168  test    ebx, ebx
0x18000916a  cmovz   ebx, edi
0x18000916d  mov     eax, ebx
0x18000916f  mov     rcx, [rbp+0F90h+var_40]
0x180009176  xor     rcx, rsp; StackCookie
0x180009179  call    __security_check_cookie
0x18000917e  add     rsp, 1068h
0x180009185  pop     r14
0x180009187  pop     r12
0x180009189  pop     rdi
0x18000918a  pop     rsi
0x18000918b  pop     rbx
0x18000918c  pop     rbp
0x18000918d  retn
```
