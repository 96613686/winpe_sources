# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x14000bcec`
- end: `0x14000beb6`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140006aa0`

## callees

- `0x140005530`
- `0x1400061b8`
- `0x14000bcec`
- `0x14000c15c`
- `0x14000c1d4`
- `0x14000fc30`

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
0x14000bcec  push    rbp
0x14000bcee  push    rbx
0x14000bcef  push    rsi
0x14000bcf0  push    rdi
0x14000bcf1  push    r12
0x14000bcf3  push    r14
0x14000bcf5  lea     rbp, [rsp-0F68h]
0x14000bcfd  mov     eax, 1068h
0x14000bd02  call    _alloca_probe
0x14000bd07  sub     rsp, rax
0x14000bd0a  mov     rax, cs:__security_cookie
0x14000bd11  xor     rax, rsp
0x14000bd14  mov     [rbp+0F90h+var_40], rax
0x14000bd1b  mov     rax, [rcx+8]
0x14000bd1f  xor     ebx, ebx
0x14000bd21  sub     rax, [rcx]
0x14000bd24  xor     edi, edi
0x14000bd26  mov     r14, rcx
0x14000bd29  cmp     rax, 0Ch
0x14000bd2d  jb      loc_14000BE90
0x14000bd33  xor     esi, esi
0x14000bd35  mov     r12, 0AAAAAAAAAAAAAAABh
0x14000bd3f  xor     edx, edx; Val
0x14000bd41  lea     rcx, [rsp+1090h+var_1040]; void *
0x14000bd46  mov     r8d, 1000h; Size
0x14000bd4c  call    memset_0
0x14000bd51  lea     rax, [rsp+1090h+var_1050]
0x14000bd56  mov     [rsp+1090h+var_1050], 1000h
0x14000bd5e  mov     [rsp+1090h+var_1068], rax
0x14000bd63  lea     r9, [rsp+1090h+var_104C]
0x14000bd68  lea     rax, [rsp+1090h+var_1040]
0x14000bd6d  mov     [rsp+1090h+var_104C], 0
0x14000bd75  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000bd7c  mov     [rsp+1090h+var_1070], rax
0x14000bd81  call    wil_details_NtQueryWnfStateData
0x14000bd86  mov     ebx, eax
0x14000bd88  test    eax, eax
0x14000bd8a  jnz     loc_14000BE79
0x14000bd90  mov     r9d, [rsp+1090h+var_1050]
0x14000bd95  mov     rax, r12
0x14000bd98  mul     r9
0x14000bd9b  shr     rdx, 3
0x14000bd9f  lea     rcx, [rdx+rdx*2]
0x14000bda3  shl     rcx, 2
0x14000bda7  cmp     r9, rcx
0x14000bdaa  jz      short loc_14000BDB4
0x14000bdac  xor     r9d, r9d
0x14000bdaf  mov     [rsp+1090h+var_1050], r9d
0x14000bdb4  mov     r8, [r14]
0x14000bdb7  mov     rax, r12
0x14000bdba  mov     ecx, r9d
0x14000bdbd  mul     rcx
0x14000bdc0  mov     rcx, [r14+8]
0x14000bdc4  mov     rax, r12
0x14000bdc7  mov     r11, rdx
0x14000bdca  sub     rcx, r8
0x14000bdcd  mul     rcx
0x14000bdd0  shr     r11, 3
0x14000bdd4  shr     rdx, 3
0x14000bdd8  lea     rax, [rdx+rdx*2]
0x14000bddc  lea     rdi, [r8+rax*4]
0x14000bde0  jmp     short loc_14000BE4E
0x14000bde2  mov     eax, r11d
0x14000bde5  lea     r10, [rsp+1090h+var_1040]
0x14000bdea  lea     rcx, [rax+rax*2]
0x14000bdee  lea     r10, [r10+rcx*4]
0x14000bdf2  cmp     rdx, r10
0x14000bdf5  jz      short loc_14000BE1D
0x14000bdf7  mov     eax, [r8]
0x14000bdfa  cmp     [rdx], eax
0x14000bdfc  jnz     short loc_14000BE09
0x14000bdfe  movzx   eax, word ptr [r8+4]
0x14000be03  cmp     [rdx+4], ax
0x14000be07  jz      short loc_14000BE0F
0x14000be09  add     rdx, 0Ch
0x14000be0d  jmp     short loc_14000BDF2
0x14000be0f  mov     eax, [r8+8]
0x14000be13  add     [rdx+8], eax
0x14000be16  mov     r9d, [rsp+1090h+var_1050]
0x14000be1b  jmp     short loc_14000BE4A
0x14000be1d  mov     eax, r9d
0x14000be20  add     rax, 0Ch
0x14000be24  cmp     rax, 1000h
0x14000be2a  ja      short loc_14000BE4A
0x14000be2c  movsd   xmm0, qword ptr [r8]
0x14000be31  add     r9d, 0Ch
0x14000be35  movsd   qword ptr [r10], xmm0
0x14000be3a  inc     r11d
0x14000be3d  mov     eax, [r8+8]
0x14000be41  mov     [r10+8], eax
0x14000be45  mov     [rsp+1090h+var_1050], r9d
0x14000be4a  add     r8, 0Ch
0x14000be4e  lea     rdx, [rsp+1090h+var_1040]
0x14000be53  cmp     r8, rdi
0x14000be56  jnz     short loc_14000BDE2
0x14000be58  mov     eax, [rsp+1090h+var_104C]
0x14000be5c  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000be63  mov     [rsp+1090h+var_1060], 1
0x14000be6b  mov     r8d, r9d
0x14000be6e  mov     dword ptr [rsp+1090h+var_1068], eax
0x14000be72  call    wil_details_NtUpdateWnfStateData
0x14000be77  mov     edi, eax
0x14000be79  cmp     edi, 0C0000001h
0x14000be7f  jnz     short loc_14000BE90
0x14000be81  inc     esi
0x14000be83  cmp     esi, 64h ; 'd'
0x14000be86  jge     short loc_14000BE90
0x14000be88  test    ebx, ebx
0x14000be8a  jz      loc_14000BD3F
0x14000be90  test    ebx, ebx
0x14000be92  cmovz   ebx, edi
0x14000be95  mov     eax, ebx
0x14000be97  mov     rcx, [rbp+0F90h+var_40]
0x14000be9e  xor     rcx, rsp; StackCookie
0x14000bea1  call    __security_check_cookie
0x14000bea6  add     rsp, 1068h
0x14000bead  pop     r14
0x14000beaf  pop     r12
0x14000beb1  pop     rdi
0x14000beb2  pop     rsi
0x14000beb3  pop     rbx
0x14000beb4  pop     rbp
0x14000beb5  retn
```
