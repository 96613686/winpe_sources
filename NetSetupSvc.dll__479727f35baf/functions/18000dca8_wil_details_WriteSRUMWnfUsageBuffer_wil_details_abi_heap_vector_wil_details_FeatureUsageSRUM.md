# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000dca8`
- end: `0x18000de7d`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `469`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180007b10`

## callees

- `0x1800027c0`
- `0x1800032d8`
- `0x18000dca8`
- `0x18000e5ec`
- `0x18000e664`
- `0x18002e290`

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
0x18000dca8  push    rbp
0x18000dcaa  push    rbx
0x18000dcab  push    rsi
0x18000dcac  push    rdi
0x18000dcad  push    r12
0x18000dcaf  push    r14
0x18000dcb1  lea     rbp, [rsp-0F68h]
0x18000dcb9  mov     eax, 1068h
0x18000dcbe  call    _alloca_probe
0x18000dcc3  sub     rsp, rax
0x18000dcc6  mov     rax, cs:__security_cookie
0x18000dccd  xor     rax, rsp
0x18000dcd0  mov     [rbp+0F90h+var_40], rax
0x18000dcd7  mov     rax, [rcx+8]
0x18000dcdb  xor     ebx, ebx
0x18000dcdd  sub     rax, [rcx]
0x18000dce0  xor     edi, edi
0x18000dce2  mov     r14, rcx
0x18000dce5  cmp     rax, 0Ch
0x18000dce9  jb      loc_18000DE49
0x18000dcef  xor     esi, esi
0x18000dcf1  mov     r12, 0AAAAAAAAAAAAAAABh
0x18000dcfb  xor     edx, edx; Val
0x18000dcfd  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000dd02  mov     r8d, 1000h; Size
0x18000dd08  call    memset_0
0x18000dd0d  lea     rax, [rsp+1090h+var_1050]
0x18000dd12  mov     [rsp+1090h+var_1050], 1000h
0x18000dd1a  mov     [rsp+1090h+var_1068], rax
0x18000dd1f  lea     r9, [rsp+1090h+var_104C]
0x18000dd24  lea     rax, [rsp+1090h+var_1040]
0x18000dd29  mov     [rsp+1090h+var_104C], 0
0x18000dd31  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000dd38  mov     [rsp+1090h+var_1070], rax
0x18000dd3d  call    wil_details_NtQueryWnfStateData
0x18000dd42  mov     ebx, eax
0x18000dd44  test    eax, eax
0x18000dd46  jnz     loc_18000DE32
0x18000dd4c  mov     r9d, [rsp+1090h+var_1050]
0x18000dd51  mov     rax, r12
0x18000dd54  mul     r9
0x18000dd57  shr     rdx, 3
0x18000dd5b  lea     rcx, [rdx+rdx*2]
0x18000dd5f  shl     rcx, 2
0x18000dd63  cmp     r9, rcx
0x18000dd66  jz      short loc_18000DD70
0x18000dd68  xor     r9d, r9d
0x18000dd6b  mov     [rsp+1090h+var_1050], r9d
0x18000dd70  mov     r8, [r14]
0x18000dd73  mov     rax, r12
0x18000dd76  mov     ecx, r9d
0x18000dd79  mul     rcx
0x18000dd7c  mov     rcx, [r14+8]
0x18000dd80  mov     rax, r12
0x18000dd83  mov     r10, rdx
0x18000dd86  sub     rcx, r8
0x18000dd89  mul     rcx
0x18000dd8c  shr     r10, 3
0x18000dd90  shr     rdx, 3
0x18000dd94  lea     rax, [rdx+rdx*2]
0x18000dd98  lea     rdi, [r8+rax*4]
0x18000dd9c  jmp     short loc_18000DE07
0x18000dd9e  mov     eax, r10d
0x18000dda1  lea     rcx, [rax+rax*2]
0x18000dda5  lea     rdx, [rdx+rcx*4]
0x18000dda9  lea     rax, [rsp+1090h+var_1040]
0x18000ddae  cmp     rax, rdx
0x18000ddb1  jz      short loc_18000DDD8
0x18000ddb3  mov     r11d, [r8]
0x18000ddb6  lea     rcx, [rsp+1090h+var_1040]
0x18000ddbb  cmp     [rcx], r11d
0x18000ddbe  jnz     short loc_18000DDCF
0x18000ddc0  movzx   eax, word ptr [r8+4]
0x18000ddc5  cmp     [rcx+4], ax
0x18000ddc9  jz      loc_18000DE6F
0x18000ddcf  add     rcx, 0Ch
0x18000ddd3  cmp     rcx, rdx
0x18000ddd6  jnz     short loc_18000DDBB
0x18000ddd8  mov     eax, r9d
0x18000dddb  add     rax, 0Ch
0x18000dddf  cmp     rax, 1000h
0x18000dde5  ja      short loc_18000DE03
0x18000dde7  movsd   xmm0, qword ptr [r8]
0x18000ddec  add     r9d, 0Ch
0x18000ddf0  movsd   qword ptr [rdx], xmm0
0x18000ddf4  inc     r10d
0x18000ddf7  mov     eax, [r8+8]
0x18000ddfb  mov     [rdx+8], eax
0x18000ddfe  mov     [rsp+1090h+var_1050], r9d
0x18000de03  add     r8, 0Ch
0x18000de07  lea     rdx, [rsp+1090h+var_1040]
0x18000de0c  cmp     r8, rdi
0x18000de0f  jnz     short loc_18000DD9E
0x18000de11  mov     eax, [rsp+1090h+var_104C]
0x18000de15  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000de1c  mov     [rsp+1090h+var_1060], 1
0x18000de24  mov     r8d, r9d
0x18000de27  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000de2b  call    wil_details_NtUpdateWnfStateData
0x18000de30  mov     edi, eax
0x18000de32  cmp     edi, 0C0000001h
0x18000de38  jnz     short loc_18000DE49
0x18000de3a  inc     esi
0x18000de3c  cmp     esi, 64h ; 'd'
0x18000de3f  jge     short loc_18000DE49
0x18000de41  test    ebx, ebx
0x18000de43  jz      loc_18000DCFB
0x18000de49  test    ebx, ebx
0x18000de4b  cmovz   ebx, edi
0x18000de4e  mov     eax, ebx
0x18000de50  mov     rcx, [rbp+0F90h+var_40]
0x18000de57  xor     rcx, rsp; StackCookie
0x18000de5a  call    __security_check_cookie
0x18000de5f  add     rsp, 1068h
0x18000de66  pop     r14
0x18000de68  pop     r12
0x18000de6a  pop     rdi
0x18000de6b  pop     rsi
0x18000de6c  pop     rbx
0x18000de6d  pop     rbp
0x18000de6e  retn
0x18000de6f  mov     eax, [r8+8]
0x18000de73  add     [rcx+8], eax
0x18000de76  mov     r9d, [rsp+1090h+var_1050]
0x18000de7b  jmp     short loc_18000DE03
```
