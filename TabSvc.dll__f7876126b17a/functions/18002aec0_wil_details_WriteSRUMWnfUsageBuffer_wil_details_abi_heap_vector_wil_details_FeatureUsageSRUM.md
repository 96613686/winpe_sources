# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18002aec0`
- end: `0x18002b08a`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18001d0f0`

## callees

- `0x18001bbe0`
- `0x18001c684`
- `0x18002aec0`
- `0x18002ba4c`
- `0x18002bac4`
- `0x18002fae0`

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
0x18002aec0  push    rbp
0x18002aec2  push    rbx
0x18002aec3  push    rsi
0x18002aec4  push    rdi
0x18002aec5  push    r12
0x18002aec7  push    r14
0x18002aec9  lea     rbp, [rsp-0F68h]
0x18002aed1  mov     eax, 1068h
0x18002aed6  call    _alloca_probe
0x18002aedb  sub     rsp, rax
0x18002aede  mov     rax, cs:__security_cookie
0x18002aee5  xor     rax, rsp
0x18002aee8  mov     [rbp+0F90h+var_40], rax
0x18002aeef  mov     rax, [rcx+8]
0x18002aef3  xor     ebx, ebx
0x18002aef5  sub     rax, [rcx]
0x18002aef8  xor     edi, edi
0x18002aefa  mov     r14, rcx
0x18002aefd  cmp     rax, 0Ch
0x18002af01  jb      loc_18002B064
0x18002af07  xor     esi, esi
0x18002af09  mov     r12, 0AAAAAAAAAAAAAAABh
0x18002af13  xor     edx, edx; Val
0x18002af15  lea     rcx, [rsp+1090h+var_1040]; void *
0x18002af1a  mov     r8d, 1000h; Size
0x18002af20  call    memset_0
0x18002af25  lea     rax, [rsp+1090h+var_1050]
0x18002af2a  mov     [rsp+1090h+var_1050], 1000h
0x18002af32  mov     [rsp+1090h+var_1068], rax
0x18002af37  lea     r9, [rsp+1090h+var_104C]
0x18002af3c  lea     rax, [rsp+1090h+var_1040]
0x18002af41  mov     [rsp+1090h+var_104C], 0
0x18002af49  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18002af50  mov     [rsp+1090h+var_1070], rax
0x18002af55  call    wil_details_NtQueryWnfStateData
0x18002af5a  mov     ebx, eax
0x18002af5c  test    eax, eax
0x18002af5e  jnz     loc_18002B04D
0x18002af64  mov     r9d, [rsp+1090h+var_1050]
0x18002af69  mov     rax, r12
0x18002af6c  mul     r9
0x18002af6f  shr     rdx, 3
0x18002af73  lea     rcx, [rdx+rdx*2]
0x18002af77  shl     rcx, 2
0x18002af7b  cmp     r9, rcx
0x18002af7e  jz      short loc_18002AF88
0x18002af80  xor     r9d, r9d
0x18002af83  mov     [rsp+1090h+var_1050], r9d
0x18002af88  mov     r8, [r14]
0x18002af8b  mov     rax, r12
0x18002af8e  mov     ecx, r9d
0x18002af91  mul     rcx
0x18002af94  mov     rcx, [r14+8]
0x18002af98  mov     rax, r12
0x18002af9b  mov     r11, rdx
0x18002af9e  sub     rcx, r8
0x18002afa1  mul     rcx
0x18002afa4  shr     r11, 3
0x18002afa8  shr     rdx, 3
0x18002afac  lea     rax, [rdx+rdx*2]
0x18002afb0  lea     rdi, [r8+rax*4]
0x18002afb4  jmp     short loc_18002B022
0x18002afb6  mov     eax, r11d
0x18002afb9  lea     r10, [rsp+1090h+var_1040]
0x18002afbe  lea     rcx, [rax+rax*2]
0x18002afc2  lea     r10, [r10+rcx*4]
0x18002afc6  cmp     rdx, r10
0x18002afc9  jz      short loc_18002AFF1
0x18002afcb  mov     eax, [r8]
0x18002afce  cmp     [rdx], eax
0x18002afd0  jnz     short loc_18002AFDD
0x18002afd2  movzx   eax, word ptr [r8+4]
0x18002afd7  cmp     [rdx+4], ax
0x18002afdb  jz      short loc_18002AFE3
0x18002afdd  add     rdx, 0Ch
0x18002afe1  jmp     short loc_18002AFC6
0x18002afe3  mov     eax, [r8+8]
0x18002afe7  add     [rdx+8], eax
0x18002afea  mov     r9d, [rsp+1090h+var_1050]
0x18002afef  jmp     short loc_18002B01E
0x18002aff1  mov     eax, r9d
0x18002aff4  add     rax, 0Ch
0x18002aff8  cmp     rax, 1000h
0x18002affe  ja      short loc_18002B01E
0x18002b000  movsd   xmm0, qword ptr [r8]
0x18002b005  add     r9d, 0Ch
0x18002b009  movsd   qword ptr [r10], xmm0
0x18002b00e  inc     r11d
0x18002b011  mov     eax, [r8+8]
0x18002b015  mov     [r10+8], eax
0x18002b019  mov     [rsp+1090h+var_1050], r9d
0x18002b01e  add     r8, 0Ch
0x18002b022  lea     rdx, [rsp+1090h+var_1040]
0x18002b027  cmp     r8, rdi
0x18002b02a  jnz     short loc_18002AFB6
0x18002b02c  mov     eax, [rsp+1090h+var_104C]
0x18002b030  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18002b037  mov     [rsp+1090h+var_1060], 1
0x18002b03f  mov     r8d, r9d
0x18002b042  mov     dword ptr [rsp+1090h+var_1068], eax
0x18002b046  call    wil_details_NtUpdateWnfStateData
0x18002b04b  mov     edi, eax
0x18002b04d  cmp     edi, 0C0000001h
0x18002b053  jnz     short loc_18002B064
0x18002b055  inc     esi
0x18002b057  cmp     esi, 64h ; 'd'
0x18002b05a  jge     short loc_18002B064
0x18002b05c  test    ebx, ebx
0x18002b05e  jz      loc_18002AF13
0x18002b064  test    ebx, ebx
0x18002b066  cmovz   ebx, edi
0x18002b069  mov     eax, ebx
0x18002b06b  mov     rcx, [rbp+0F90h+var_40]
0x18002b072  xor     rcx, rsp; StackCookie
0x18002b075  call    __security_check_cookie
0x18002b07a  add     rsp, 1068h
0x18002b081  pop     r14
0x18002b083  pop     r12
0x18002b085  pop     rdi
0x18002b086  pop     rsi
0x18002b087  pop     rbx
0x18002b088  pop     rbp
0x18002b089  retn
```
