# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180011568`
- end: `0x180011732`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800075d0`

## callees

- `0x180001720`
- `0x1800021b8`
- `0x180011568`
- `0x1800118a0`
- `0x180011918`
- `0x1800142b0`

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
0x180011568  push    rbp
0x18001156a  push    rbx
0x18001156b  push    rsi
0x18001156c  push    rdi
0x18001156d  push    r12
0x18001156f  push    r14
0x180011571  lea     rbp, [rsp-0F68h]
0x180011579  mov     eax, 1068h
0x18001157e  call    _alloca_probe
0x180011583  sub     rsp, rax
0x180011586  mov     rax, cs:__security_cookie
0x18001158d  xor     rax, rsp
0x180011590  mov     [rbp+0F90h+var_40], rax
0x180011597  mov     rax, [rcx+8]
0x18001159b  xor     ebx, ebx
0x18001159d  sub     rax, [rcx]
0x1800115a0  xor     edi, edi
0x1800115a2  mov     r14, rcx
0x1800115a5  cmp     rax, 0Ch
0x1800115a9  jb      loc_18001170C
0x1800115af  xor     esi, esi
0x1800115b1  mov     r12, 0AAAAAAAAAAAAAAABh
0x1800115bb  xor     edx, edx; Val
0x1800115bd  lea     rcx, [rsp+1090h+var_1040]; void *
0x1800115c2  mov     r8d, 1000h; Size
0x1800115c8  call    memset_0
0x1800115cd  lea     rax, [rsp+1090h+var_1050]
0x1800115d2  mov     [rsp+1090h+var_1050], 1000h
0x1800115da  mov     [rsp+1090h+var_1068], rax
0x1800115df  lea     r9, [rsp+1090h+var_104C]
0x1800115e4  lea     rax, [rsp+1090h+var_1040]
0x1800115e9  mov     [rsp+1090h+var_104C], 0
0x1800115f1  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1800115f8  mov     [rsp+1090h+var_1070], rax
0x1800115fd  call    wil_details_NtQueryWnfStateData
0x180011602  mov     ebx, eax
0x180011604  test    eax, eax
0x180011606  jnz     loc_1800116F5
0x18001160c  mov     r9d, [rsp+1090h+var_1050]
0x180011611  mov     rax, r12
0x180011614  mul     r9
0x180011617  shr     rdx, 3
0x18001161b  lea     rcx, [rdx+rdx*2]
0x18001161f  shl     rcx, 2
0x180011623  cmp     r9, rcx
0x180011626  jz      short loc_180011630
0x180011628  xor     r9d, r9d
0x18001162b  mov     [rsp+1090h+var_1050], r9d
0x180011630  mov     r8, [r14]
0x180011633  mov     rax, r12
0x180011636  mov     ecx, r9d
0x180011639  mul     rcx
0x18001163c  mov     rcx, [r14+8]
0x180011640  mov     rax, r12
0x180011643  mov     r11, rdx
0x180011646  sub     rcx, r8
0x180011649  mul     rcx
0x18001164c  shr     r11, 3
0x180011650  shr     rdx, 3
0x180011654  lea     rax, [rdx+rdx*2]
0x180011658  lea     rdi, [r8+rax*4]
0x18001165c  jmp     short loc_1800116CA
0x18001165e  mov     eax, r11d
0x180011661  lea     r10, [rsp+1090h+var_1040]
0x180011666  lea     rcx, [rax+rax*2]
0x18001166a  lea     r10, [r10+rcx*4]
0x18001166e  cmp     rdx, r10
0x180011671  jz      short loc_180011699
0x180011673  mov     eax, [r8]
0x180011676  cmp     [rdx], eax
0x180011678  jnz     short loc_180011685
0x18001167a  movzx   eax, word ptr [r8+4]
0x18001167f  cmp     [rdx+4], ax
0x180011683  jz      short loc_18001168B
0x180011685  add     rdx, 0Ch
0x180011689  jmp     short loc_18001166E
0x18001168b  mov     eax, [r8+8]
0x18001168f  add     [rdx+8], eax
0x180011692  mov     r9d, [rsp+1090h+var_1050]
0x180011697  jmp     short loc_1800116C6
0x180011699  mov     eax, r9d
0x18001169c  add     rax, 0Ch
0x1800116a0  cmp     rax, 1000h
0x1800116a6  ja      short loc_1800116C6
0x1800116a8  movsd   xmm0, qword ptr [r8]
0x1800116ad  add     r9d, 0Ch
0x1800116b1  movsd   qword ptr [r10], xmm0
0x1800116b6  inc     r11d
0x1800116b9  mov     eax, [r8+8]
0x1800116bd  mov     [r10+8], eax
0x1800116c1  mov     [rsp+1090h+var_1050], r9d
0x1800116c6  add     r8, 0Ch
0x1800116ca  lea     rdx, [rsp+1090h+var_1040]
0x1800116cf  cmp     r8, rdi
0x1800116d2  jnz     short loc_18001165E
0x1800116d4  mov     eax, [rsp+1090h+var_104C]
0x1800116d8  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1800116df  mov     [rsp+1090h+var_1060], 1
0x1800116e7  mov     r8d, r9d
0x1800116ea  mov     dword ptr [rsp+1090h+var_1068], eax
0x1800116ee  call    wil_details_NtUpdateWnfStateData
0x1800116f3  mov     edi, eax
0x1800116f5  cmp     edi, 0C0000001h
0x1800116fb  jnz     short loc_18001170C
0x1800116fd  inc     esi
0x1800116ff  cmp     esi, 64h ; 'd'
0x180011702  jge     short loc_18001170C
0x180011704  test    ebx, ebx
0x180011706  jz      loc_1800115BB
0x18001170c  test    ebx, ebx
0x18001170e  cmovz   ebx, edi
0x180011711  mov     eax, ebx
0x180011713  mov     rcx, [rbp+0F90h+var_40]
0x18001171a  xor     rcx, rsp; StackCookie
0x18001171d  call    __security_check_cookie
0x180011722  add     rsp, 1068h
0x180011729  pop     r14
0x18001172b  pop     r12
0x18001172d  pop     rdi
0x18001172e  pop     rsi
0x18001172f  pop     rbx
0x180011730  pop     rbp
0x180011731  retn
```
