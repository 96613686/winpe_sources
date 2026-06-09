# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x1800090f8`
- end: `0x1800092c2`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800029f0`

## callees

- `0x180001e00`
- `0x180002858`
- `0x1800090f8`
- `0x18000943c`
- `0x1800094b4`
- `0x1800096e0`

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
0x1800090f8  push    rbp
0x1800090fa  push    rbx
0x1800090fb  push    rsi
0x1800090fc  push    rdi
0x1800090fd  push    r12
0x1800090ff  push    r14
0x180009101  lea     rbp, [rsp-0F68h]
0x180009109  mov     eax, 1068h
0x18000910e  call    _alloca_probe
0x180009113  sub     rsp, rax
0x180009116  mov     rax, cs:__security_cookie
0x18000911d  xor     rax, rsp
0x180009120  mov     [rbp+0F90h+var_40], rax
0x180009127  mov     rax, [rcx+8]
0x18000912b  xor     ebx, ebx
0x18000912d  sub     rax, [rcx]
0x180009130  xor     edi, edi
0x180009132  mov     r14, rcx
0x180009135  cmp     rax, 0Ch
0x180009139  jb      loc_18000929C
0x18000913f  xor     esi, esi
0x180009141  mov     r12, 0AAAAAAAAAAAAAAABh
0x18000914b  xor     edx, edx; Val
0x18000914d  lea     rcx, [rsp+1090h+var_1040]; void *
0x180009152  mov     r8d, 1000h; Size
0x180009158  call    memset_0
0x18000915d  lea     rax, [rsp+1090h+var_1050]
0x180009162  mov     [rsp+1090h+var_1050], 1000h
0x18000916a  mov     [rsp+1090h+var_1068], rax
0x18000916f  lea     r9, [rsp+1090h+var_104C]
0x180009174  lea     rax, [rsp+1090h+var_1040]
0x180009179  mov     [rsp+1090h+var_104C], 0
0x180009181  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180009188  mov     [rsp+1090h+var_1070], rax
0x18000918d  call    wil_details_NtQueryWnfStateData
0x180009192  mov     ebx, eax
0x180009194  test    eax, eax
0x180009196  jnz     loc_180009285
0x18000919c  mov     r9d, [rsp+1090h+var_1050]
0x1800091a1  mov     rax, r12
0x1800091a4  mul     r9
0x1800091a7  shr     rdx, 3
0x1800091ab  lea     rcx, [rdx+rdx*2]
0x1800091af  shl     rcx, 2
0x1800091b3  cmp     r9, rcx
0x1800091b6  jz      short loc_1800091C0
0x1800091b8  xor     r9d, r9d
0x1800091bb  mov     [rsp+1090h+var_1050], r9d
0x1800091c0  mov     r8, [r14]
0x1800091c3  mov     rax, r12
0x1800091c6  mov     ecx, r9d
0x1800091c9  mul     rcx
0x1800091cc  mov     rcx, [r14+8]
0x1800091d0  mov     rax, r12
0x1800091d3  mov     r11, rdx
0x1800091d6  sub     rcx, r8
0x1800091d9  mul     rcx
0x1800091dc  shr     r11, 3
0x1800091e0  shr     rdx, 3
0x1800091e4  lea     rax, [rdx+rdx*2]
0x1800091e8  lea     rdi, [r8+rax*4]
0x1800091ec  jmp     short loc_18000925A
0x1800091ee  mov     eax, r11d
0x1800091f1  lea     r10, [rsp+1090h+var_1040]
0x1800091f6  lea     rcx, [rax+rax*2]
0x1800091fa  lea     r10, [r10+rcx*4]
0x1800091fe  cmp     rdx, r10
0x180009201  jz      short loc_180009229
0x180009203  mov     eax, [r8]
0x180009206  cmp     [rdx], eax
0x180009208  jnz     short loc_180009215
0x18000920a  movzx   eax, word ptr [r8+4]
0x18000920f  cmp     [rdx+4], ax
0x180009213  jz      short loc_18000921B
0x180009215  add     rdx, 0Ch
0x180009219  jmp     short loc_1800091FE
0x18000921b  mov     eax, [r8+8]
0x18000921f  add     [rdx+8], eax
0x180009222  mov     r9d, [rsp+1090h+var_1050]
0x180009227  jmp     short loc_180009256
0x180009229  mov     eax, r9d
0x18000922c  add     rax, 0Ch
0x180009230  cmp     rax, 1000h
0x180009236  ja      short loc_180009256
0x180009238  movsd   xmm0, qword ptr [r8]
0x18000923d  add     r9d, 0Ch
0x180009241  movsd   qword ptr [r10], xmm0
0x180009246  inc     r11d
0x180009249  mov     eax, [r8+8]
0x18000924d  mov     [r10+8], eax
0x180009251  mov     [rsp+1090h+var_1050], r9d
0x180009256  add     r8, 0Ch
0x18000925a  lea     rdx, [rsp+1090h+var_1040]
0x18000925f  cmp     r8, rdi
0x180009262  jnz     short loc_1800091EE
0x180009264  mov     eax, [rsp+1090h+var_104C]
0x180009268  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000926f  mov     [rsp+1090h+var_1060], 1
0x180009277  mov     r8d, r9d
0x18000927a  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000927e  call    wil_details_NtUpdateWnfStateData
0x180009283  mov     edi, eax
0x180009285  cmp     edi, 0C0000001h
0x18000928b  jnz     short loc_18000929C
0x18000928d  inc     esi
0x18000928f  cmp     esi, 64h ; 'd'
0x180009292  jge     short loc_18000929C
0x180009294  test    ebx, ebx
0x180009296  jz      loc_18000914B
0x18000929c  test    ebx, ebx
0x18000929e  cmovz   ebx, edi
0x1800092a1  mov     eax, ebx
0x1800092a3  mov     rcx, [rbp+0F90h+var_40]
0x1800092aa  xor     rcx, rsp; StackCookie
0x1800092ad  call    __security_check_cookie
0x1800092b2  add     rsp, 1068h
0x1800092b9  pop     r14
0x1800092bb  pop     r12
0x1800092bd  pop     rdi
0x1800092be  pop     rsi
0x1800092bf  pop     rbx
0x1800092c0  pop     rbp
0x1800092c1  retn
```
