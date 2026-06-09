# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000ef98`
- end: `0x18000f162`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18000a480`

## callees

- `0x180004c70`
- `0x1800056e0`
- `0x18000ef98`
- `0x18000f3f4`
- `0x18000f46c`
- `0x1800135e0`

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
0x18000ef98  push    rbp
0x18000ef9a  push    rbx
0x18000ef9b  push    rsi
0x18000ef9c  push    rdi
0x18000ef9d  push    r12
0x18000ef9f  push    r14
0x18000efa1  lea     rbp, [rsp-0F68h]
0x18000efa9  mov     eax, 1068h
0x18000efae  call    _alloca_probe
0x18000efb3  sub     rsp, rax
0x18000efb6  mov     rax, cs:__security_cookie
0x18000efbd  xor     rax, rsp
0x18000efc0  mov     [rbp+0F90h+var_40], rax
0x18000efc7  mov     rax, [rcx+8]
0x18000efcb  xor     ebx, ebx
0x18000efcd  sub     rax, [rcx]
0x18000efd0  xor     edi, edi
0x18000efd2  mov     r14, rcx
0x18000efd5  cmp     rax, 0Ch
0x18000efd9  jb      loc_18000F13C
0x18000efdf  xor     esi, esi
0x18000efe1  mov     r12, 0AAAAAAAAAAAAAAABh
0x18000efeb  xor     edx, edx; Val
0x18000efed  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000eff2  mov     r8d, 1000h; Size
0x18000eff8  call    memset_0
0x18000effd  lea     rax, [rsp+1090h+var_1050]
0x18000f002  mov     [rsp+1090h+var_1050], 1000h
0x18000f00a  mov     [rsp+1090h+var_1068], rax
0x18000f00f  lea     r9, [rsp+1090h+var_104C]
0x18000f014  lea     rax, [rsp+1090h+var_1040]
0x18000f019  mov     [rsp+1090h+var_104C], 0
0x18000f021  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000f028  mov     [rsp+1090h+var_1070], rax
0x18000f02d  call    wil_details_NtQueryWnfStateData
0x18000f032  mov     ebx, eax
0x18000f034  test    eax, eax
0x18000f036  jnz     loc_18000F125
0x18000f03c  mov     r9d, [rsp+1090h+var_1050]
0x18000f041  mov     rax, r12
0x18000f044  mul     r9
0x18000f047  shr     rdx, 3
0x18000f04b  lea     rcx, [rdx+rdx*2]
0x18000f04f  shl     rcx, 2
0x18000f053  cmp     r9, rcx
0x18000f056  jz      short loc_18000F060
0x18000f058  xor     r9d, r9d
0x18000f05b  mov     [rsp+1090h+var_1050], r9d
0x18000f060  mov     r8, [r14]
0x18000f063  mov     rax, r12
0x18000f066  mov     ecx, r9d
0x18000f069  mul     rcx
0x18000f06c  mov     rcx, [r14+8]
0x18000f070  mov     rax, r12
0x18000f073  mov     r11, rdx
0x18000f076  sub     rcx, r8
0x18000f079  mul     rcx
0x18000f07c  shr     r11, 3
0x18000f080  shr     rdx, 3
0x18000f084  lea     rax, [rdx+rdx*2]
0x18000f088  lea     rdi, [r8+rax*4]
0x18000f08c  jmp     short loc_18000F0FA
0x18000f08e  mov     eax, r11d
0x18000f091  lea     r10, [rsp+1090h+var_1040]
0x18000f096  lea     rcx, [rax+rax*2]
0x18000f09a  lea     r10, [r10+rcx*4]
0x18000f09e  cmp     rdx, r10
0x18000f0a1  jz      short loc_18000F0C9
0x18000f0a3  mov     eax, [r8]
0x18000f0a6  cmp     [rdx], eax
0x18000f0a8  jnz     short loc_18000F0B5
0x18000f0aa  movzx   eax, word ptr [r8+4]
0x18000f0af  cmp     [rdx+4], ax
0x18000f0b3  jz      short loc_18000F0BB
0x18000f0b5  add     rdx, 0Ch
0x18000f0b9  jmp     short loc_18000F09E
0x18000f0bb  mov     eax, [r8+8]
0x18000f0bf  add     [rdx+8], eax
0x18000f0c2  mov     r9d, [rsp+1090h+var_1050]
0x18000f0c7  jmp     short loc_18000F0F6
0x18000f0c9  mov     eax, r9d
0x18000f0cc  add     rax, 0Ch
0x18000f0d0  cmp     rax, 1000h
0x18000f0d6  ja      short loc_18000F0F6
0x18000f0d8  movsd   xmm0, qword ptr [r8]
0x18000f0dd  add     r9d, 0Ch
0x18000f0e1  movsd   qword ptr [r10], xmm0
0x18000f0e6  inc     r11d
0x18000f0e9  mov     eax, [r8+8]
0x18000f0ed  mov     [r10+8], eax
0x18000f0f1  mov     [rsp+1090h+var_1050], r9d
0x18000f0f6  add     r8, 0Ch
0x18000f0fa  lea     rdx, [rsp+1090h+var_1040]
0x18000f0ff  cmp     r8, rdi
0x18000f102  jnz     short loc_18000F08E
0x18000f104  mov     eax, [rsp+1090h+var_104C]
0x18000f108  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000f10f  mov     [rsp+1090h+var_1060], 1
0x18000f117  mov     r8d, r9d
0x18000f11a  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000f11e  call    wil_details_NtUpdateWnfStateData
0x18000f123  mov     edi, eax
0x18000f125  cmp     edi, 0C0000001h
0x18000f12b  jnz     short loc_18000F13C
0x18000f12d  inc     esi
0x18000f12f  cmp     esi, 64h ; 'd'
0x18000f132  jge     short loc_18000F13C
0x18000f134  test    ebx, ebx
0x18000f136  jz      loc_18000EFEB
0x18000f13c  test    ebx, ebx
0x18000f13e  cmovz   ebx, edi
0x18000f141  mov     eax, ebx
0x18000f143  mov     rcx, [rbp+0F90h+var_40]
0x18000f14a  xor     rcx, rsp; StackCookie
0x18000f14d  call    __security_check_cookie
0x18000f152  add     rsp, 1068h
0x18000f159  pop     r14
0x18000f15b  pop     r12
0x18000f15d  pop     rdi
0x18000f15e  pop     rsi
0x18000f15f  pop     rbx
0x18000f160  pop     rbp
0x18000f161  retn
```
