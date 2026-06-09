# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000ae0c`
- end: `0x18000afe1`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `469`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180007830`

## callees

- `0x1800036a0`
- `0x180004054`
- `0x18000ae0c`
- `0x18000b174`
- `0x18000b1ec`
- `0x18001b3e0`

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
0x18000ae0c  push    rbp
0x18000ae0e  push    rbx
0x18000ae0f  push    rsi
0x18000ae10  push    rdi
0x18000ae11  push    r12
0x18000ae13  push    r14
0x18000ae15  lea     rbp, [rsp-0F68h]
0x18000ae1d  mov     eax, 1068h
0x18000ae22  call    _alloca_probe
0x18000ae27  sub     rsp, rax
0x18000ae2a  mov     rax, cs:__security_cookie
0x18000ae31  xor     rax, rsp
0x18000ae34  mov     [rbp+0F90h+var_40], rax
0x18000ae3b  mov     rax, [rcx+8]
0x18000ae3f  xor     ebx, ebx
0x18000ae41  sub     rax, [rcx]
0x18000ae44  xor     edi, edi
0x18000ae46  mov     r14, rcx
0x18000ae49  cmp     rax, 0Ch
0x18000ae4d  jb      loc_18000AFAD
0x18000ae53  xor     esi, esi
0x18000ae55  mov     r12, 0AAAAAAAAAAAAAAABh
0x18000ae5f  xor     edx, edx; Val
0x18000ae61  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000ae66  mov     r8d, 1000h; Size
0x18000ae6c  call    memset_0
0x18000ae71  lea     rax, [rsp+1090h+var_1050]
0x18000ae76  mov     [rsp+1090h+var_1050], 1000h
0x18000ae7e  mov     [rsp+1090h+var_1068], rax
0x18000ae83  lea     r9, [rsp+1090h+var_104C]
0x18000ae88  lea     rax, [rsp+1090h+var_1040]
0x18000ae8d  mov     [rsp+1090h+var_104C], 0
0x18000ae95  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000ae9c  mov     [rsp+1090h+var_1070], rax
0x18000aea1  call    wil_details_NtQueryWnfStateData
0x18000aea6  mov     ebx, eax
0x18000aea8  test    eax, eax
0x18000aeaa  jnz     loc_18000AF96
0x18000aeb0  mov     r9d, [rsp+1090h+var_1050]
0x18000aeb5  mov     rax, r12
0x18000aeb8  mul     r9
0x18000aebb  shr     rdx, 3
0x18000aebf  lea     rcx, [rdx+rdx*2]
0x18000aec3  shl     rcx, 2
0x18000aec7  cmp     r9, rcx
0x18000aeca  jz      short loc_18000AED4
0x18000aecc  xor     r9d, r9d
0x18000aecf  mov     [rsp+1090h+var_1050], r9d
0x18000aed4  mov     r8, [r14]
0x18000aed7  mov     rax, r12
0x18000aeda  mov     ecx, r9d
0x18000aedd  mul     rcx
0x18000aee0  mov     rcx, [r14+8]
0x18000aee4  mov     rax, r12
0x18000aee7  mov     r10, rdx
0x18000aeea  sub     rcx, r8
0x18000aeed  mul     rcx
0x18000aef0  shr     r10, 3
0x18000aef4  shr     rdx, 3
0x18000aef8  lea     rax, [rdx+rdx*2]
0x18000aefc  lea     rdi, [r8+rax*4]
0x18000af00  jmp     short loc_18000AF6B
0x18000af02  mov     eax, r10d
0x18000af05  lea     rcx, [rax+rax*2]
0x18000af09  lea     rdx, [rdx+rcx*4]
0x18000af0d  lea     rax, [rsp+1090h+var_1040]
0x18000af12  cmp     rax, rdx
0x18000af15  jz      short loc_18000AF3C
0x18000af17  mov     r11d, [r8]
0x18000af1a  lea     rcx, [rsp+1090h+var_1040]
0x18000af1f  cmp     [rcx], r11d
0x18000af22  jnz     short loc_18000AF33
0x18000af24  movzx   eax, word ptr [r8+4]
0x18000af29  cmp     [rcx+4], ax
0x18000af2d  jz      loc_18000AFD3
0x18000af33  add     rcx, 0Ch
0x18000af37  cmp     rcx, rdx
0x18000af3a  jnz     short loc_18000AF1F
0x18000af3c  mov     eax, r9d
0x18000af3f  add     rax, 0Ch
0x18000af43  cmp     rax, 1000h
0x18000af49  ja      short loc_18000AF67
0x18000af4b  movsd   xmm0, qword ptr [r8]
0x18000af50  add     r9d, 0Ch
0x18000af54  movsd   qword ptr [rdx], xmm0
0x18000af58  inc     r10d
0x18000af5b  mov     eax, [r8+8]
0x18000af5f  mov     [rdx+8], eax
0x18000af62  mov     [rsp+1090h+var_1050], r9d
0x18000af67  add     r8, 0Ch
0x18000af6b  lea     rdx, [rsp+1090h+var_1040]
0x18000af70  cmp     r8, rdi
0x18000af73  jnz     short loc_18000AF02
0x18000af75  mov     eax, [rsp+1090h+var_104C]
0x18000af79  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000af80  mov     [rsp+1090h+var_1060], 1
0x18000af88  mov     r8d, r9d
0x18000af8b  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000af8f  call    wil_details_NtUpdateWnfStateData
0x18000af94  mov     edi, eax
0x18000af96  cmp     edi, 0C0000001h
0x18000af9c  jnz     short loc_18000AFAD
0x18000af9e  inc     esi
0x18000afa0  cmp     esi, 64h ; 'd'
0x18000afa3  jge     short loc_18000AFAD
0x18000afa5  test    ebx, ebx
0x18000afa7  jz      loc_18000AE5F
0x18000afad  test    ebx, ebx
0x18000afaf  cmovz   ebx, edi
0x18000afb2  mov     eax, ebx
0x18000afb4  mov     rcx, [rbp+0F90h+var_40]
0x18000afbb  xor     rcx, rsp; StackCookie
0x18000afbe  call    __security_check_cookie
0x18000afc3  add     rsp, 1068h
0x18000afca  pop     r14
0x18000afcc  pop     r12
0x18000afce  pop     rdi
0x18000afcf  pop     rsi
0x18000afd0  pop     rbx
0x18000afd1  pop     rbp
0x18000afd2  retn
0x18000afd3  mov     eax, [r8+8]
0x18000afd7  add     [rcx+8], eax
0x18000afda  mov     r9d, [rsp+1090h+var_1050]
0x18000afdf  jmp     short loc_18000AF67
```
