# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18001edf4`
- end: `0x18001efbe`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180009400`

## callees

- `0x180002380`
- `0x1800032dc`
- `0x18001edf4`
- `0x18002102c`
- `0x1800210a4`
- `0x1800227b0`

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
0x18001edf4  push    rbp
0x18001edf6  push    rbx
0x18001edf7  push    rsi
0x18001edf8  push    rdi
0x18001edf9  push    r12
0x18001edfb  push    r14
0x18001edfd  lea     rbp, [rsp-0F68h]
0x18001ee05  mov     eax, 1068h
0x18001ee0a  call    _alloca_probe
0x18001ee0f  sub     rsp, rax
0x18001ee12  mov     rax, cs:__security_cookie
0x18001ee19  xor     rax, rsp
0x18001ee1c  mov     [rbp+0F90h+var_40], rax
0x18001ee23  mov     rax, [rcx+8]
0x18001ee27  xor     ebx, ebx
0x18001ee29  sub     rax, [rcx]
0x18001ee2c  xor     edi, edi
0x18001ee2e  mov     r14, rcx
0x18001ee31  cmp     rax, 0Ch
0x18001ee35  jb      loc_18001EF98
0x18001ee3b  xor     esi, esi
0x18001ee3d  mov     r12, 0AAAAAAAAAAAAAAABh
0x18001ee47  xor     edx, edx; Val
0x18001ee49  lea     rcx, [rsp+1090h+var_1040]; void *
0x18001ee4e  mov     r8d, 1000h; Size
0x18001ee54  call    memset_0
0x18001ee59  lea     rax, [rsp+1090h+var_1050]
0x18001ee5e  mov     [rsp+1090h+var_1050], 1000h
0x18001ee66  mov     [rsp+1090h+var_1068], rax
0x18001ee6b  lea     r9, [rsp+1090h+var_104C]
0x18001ee70  lea     rax, [rsp+1090h+var_1040]
0x18001ee75  mov     [rsp+1090h+var_104C], 0
0x18001ee7d  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18001ee84  mov     [rsp+1090h+var_1070], rax
0x18001ee89  call    wil_details_NtQueryWnfStateData
0x18001ee8e  mov     ebx, eax
0x18001ee90  test    eax, eax
0x18001ee92  jnz     loc_18001EF81
0x18001ee98  mov     r9d, [rsp+1090h+var_1050]
0x18001ee9d  mov     rax, r12
0x18001eea0  mul     r9
0x18001eea3  shr     rdx, 3
0x18001eea7  lea     rcx, [rdx+rdx*2]
0x18001eeab  shl     rcx, 2
0x18001eeaf  cmp     r9, rcx
0x18001eeb2  jz      short loc_18001EEBC
0x18001eeb4  xor     r9d, r9d
0x18001eeb7  mov     [rsp+1090h+var_1050], r9d
0x18001eebc  mov     r8, [r14]
0x18001eebf  mov     rax, r12
0x18001eec2  mov     ecx, r9d
0x18001eec5  mul     rcx
0x18001eec8  mov     rcx, [r14+8]
0x18001eecc  mov     rax, r12
0x18001eecf  mov     r11, rdx
0x18001eed2  sub     rcx, r8
0x18001eed5  mul     rcx
0x18001eed8  shr     r11, 3
0x18001eedc  shr     rdx, 3
0x18001eee0  lea     rax, [rdx+rdx*2]
0x18001eee4  lea     rdi, [r8+rax*4]
0x18001eee8  jmp     short loc_18001EF56
0x18001eeea  mov     eax, r11d
0x18001eeed  lea     r10, [rsp+1090h+var_1040]
0x18001eef2  lea     rcx, [rax+rax*2]
0x18001eef6  lea     r10, [r10+rcx*4]
0x18001eefa  cmp     rdx, r10
0x18001eefd  jz      short loc_18001EF25
0x18001eeff  mov     eax, [r8]
0x18001ef02  cmp     [rdx], eax
0x18001ef04  jnz     short loc_18001EF11
0x18001ef06  movzx   eax, word ptr [r8+4]
0x18001ef0b  cmp     [rdx+4], ax
0x18001ef0f  jz      short loc_18001EF17
0x18001ef11  add     rdx, 0Ch
0x18001ef15  jmp     short loc_18001EEFA
0x18001ef17  mov     eax, [r8+8]
0x18001ef1b  add     [rdx+8], eax
0x18001ef1e  mov     r9d, [rsp+1090h+var_1050]
0x18001ef23  jmp     short loc_18001EF52
0x18001ef25  mov     eax, r9d
0x18001ef28  add     rax, 0Ch
0x18001ef2c  cmp     rax, 1000h
0x18001ef32  ja      short loc_18001EF52
0x18001ef34  movsd   xmm0, qword ptr [r8]
0x18001ef39  add     r9d, 0Ch
0x18001ef3d  movsd   qword ptr [r10], xmm0
0x18001ef42  inc     r11d
0x18001ef45  mov     eax, [r8+8]
0x18001ef49  mov     [r10+8], eax
0x18001ef4d  mov     [rsp+1090h+var_1050], r9d
0x18001ef52  add     r8, 0Ch
0x18001ef56  lea     rdx, [rsp+1090h+var_1040]
0x18001ef5b  cmp     r8, rdi
0x18001ef5e  jnz     short loc_18001EEEA
0x18001ef60  mov     eax, [rsp+1090h+var_104C]
0x18001ef64  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18001ef6b  mov     [rsp+1090h+var_1060], 1
0x18001ef73  mov     r8d, r9d
0x18001ef76  mov     dword ptr [rsp+1090h+var_1068], eax
0x18001ef7a  call    wil_details_NtUpdateWnfStateData
0x18001ef7f  mov     edi, eax
0x18001ef81  cmp     edi, 0C0000001h
0x18001ef87  jnz     short loc_18001EF98
0x18001ef89  inc     esi
0x18001ef8b  cmp     esi, 64h ; 'd'
0x18001ef8e  jge     short loc_18001EF98
0x18001ef90  test    ebx, ebx
0x18001ef92  jz      loc_18001EE47
0x18001ef98  test    ebx, ebx
0x18001ef9a  cmovz   ebx, edi
0x18001ef9d  mov     eax, ebx
0x18001ef9f  mov     rcx, [rbp+0F90h+var_40]
0x18001efa6  xor     rcx, rsp; StackCookie
0x18001efa9  call    __security_check_cookie
0x18001efae  add     rsp, 1068h
0x18001efb5  pop     r14
0x18001efb7  pop     r12
0x18001efb9  pop     rdi
0x18001efba  pop     rsi
0x18001efbb  pop     rbx
0x18001efbc  pop     rbp
0x18001efbd  retn
```
