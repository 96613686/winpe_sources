# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180016afc`
- end: `0x180016cd2`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `470`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180010020`

## callees

- `0x180016afc`
- `0x180016e88`
- `0x180016f30`
- `0x18001899e`
- `0x1800189d0`
- `0x180018a60`

## pseudocode

```c
__int64 __fastcall wil_details_WriteSRUMWnfUsageBuffer(__int64 *a1)
{
  unsigned int WnfStateData; // ebx
  unsigned int updated; // edi
  int v4; // esi
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // r8
  unsigned int v9; // r10d
  unsigned __int64 v10; // rdi
  _DWORD *v11; // rdx
  _DWORD *v12; // rcx
  int v14; // [rsp+20h] [rbp-E0h]
  unsigned int v15; // [rsp+40h] [rbp-C0h] BYREF
  int v16[3]; // [rsp+44h] [rbp-BCh] BYREF
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
      v16[0] = 0;
      WnfStateData = wil_details_NtQueryWnfStateData(
                       (__int64)&__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM,
                       v5,
                       v6,
                       (__int64)v16,
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
                    v16[0],
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
0x180016afc  push    rbp
0x180016afe  push    rbx
0x180016aff  push    rsi
0x180016b00  push    rdi
0x180016b01  push    r12
0x180016b03  push    r14
0x180016b05  lea     rbp, [rsp-0F68h]
0x180016b0d  mov     eax, 1068h
0x180016b12  call    _alloca_probe
0x180016b17  sub     rsp, rax
0x180016b1a  mov     rax, cs:__security_cookie
0x180016b21  xor     rax, rsp
0x180016b24  mov     [rbp+0F90h+var_40], rax
0x180016b2b  mov     rax, [rcx+8]
0x180016b2f  xor     ebx, ebx
0x180016b31  sub     rax, [rcx]
0x180016b34  xor     edi, edi
0x180016b36  mov     r14, rcx
0x180016b39  cmp     rax, 0Ch
0x180016b3d  jb      loc_180016C9D
0x180016b43  xor     esi, esi
0x180016b45  mov     r12, 0AAAAAAAAAAAAAAABh
0x180016b4f  xor     edx, edx; Val
0x180016b51  lea     rcx, [rsp+1090h+var_1040]; void *
0x180016b56  mov     r8d, 1000h; Size
0x180016b5c  call    memset_0
0x180016b61  lea     rax, [rsp+1090h+var_1050]
0x180016b66  mov     [rsp+1090h+var_1050], 1000h
0x180016b6e  mov     [rsp+1090h+var_1068], rax
0x180016b73  lea     r9, [rsp+1090h+var_104C]
0x180016b78  lea     rax, [rsp+1090h+var_1040]
0x180016b7d  mov     [rsp+1090h+var_104C], 0
0x180016b85  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180016b8c  mov     [rsp+1090h+var_1070], rax
0x180016b91  call    wil_details_NtQueryWnfStateData
0x180016b96  mov     ebx, eax
0x180016b98  test    eax, eax
0x180016b9a  jnz     loc_180016C86
0x180016ba0  mov     r9d, [rsp+1090h+var_1050]
0x180016ba5  mov     rax, r12
0x180016ba8  mul     r9
0x180016bab  shr     rdx, 3
0x180016baf  lea     rcx, [rdx+rdx*2]
0x180016bb3  shl     rcx, 2
0x180016bb7  cmp     r9, rcx
0x180016bba  jz      short loc_180016BC4
0x180016bbc  xor     r9d, r9d
0x180016bbf  mov     [rsp+1090h+var_1050], r9d
0x180016bc4  mov     r8, [r14]
0x180016bc7  mov     rax, r12
0x180016bca  mov     ecx, r9d
0x180016bcd  mul     rcx
0x180016bd0  mov     rcx, [r14+8]
0x180016bd4  mov     rax, r12
0x180016bd7  mov     r10, rdx
0x180016bda  sub     rcx, r8
0x180016bdd  mul     rcx
0x180016be0  shr     r10, 3
0x180016be4  shr     rdx, 3
0x180016be8  lea     rax, [rdx+rdx*2]
0x180016bec  lea     rdi, [r8+rax*4]
0x180016bf0  jmp     short loc_180016C5B
0x180016bf2  mov     eax, r10d
0x180016bf5  lea     rcx, [rax+rax*2]
0x180016bf9  lea     rdx, [rdx+rcx*4]
0x180016bfd  lea     rax, [rsp+1090h+var_1040]
0x180016c02  cmp     rax, rdx
0x180016c05  jz      short loc_180016C2C
0x180016c07  mov     r11d, [r8]
0x180016c0a  lea     rcx, [rsp+1090h+var_1040]
0x180016c0f  cmp     [rcx], r11d
0x180016c12  jnz     short loc_180016C23
0x180016c14  movzx   eax, word ptr [r8+4]
0x180016c19  cmp     [rcx+4], ax
0x180016c1d  jz      loc_180016CC4
0x180016c23  add     rcx, 0Ch
0x180016c27  cmp     rcx, rdx
0x180016c2a  jnz     short loc_180016C0F
0x180016c2c  mov     eax, r9d
0x180016c2f  add     rax, 0Ch
0x180016c33  cmp     rax, 1000h
0x180016c39  ja      short loc_180016C57
0x180016c3b  movsd   xmm0, qword ptr [r8]
0x180016c40  add     r9d, 0Ch
0x180016c44  movsd   qword ptr [rdx], xmm0
0x180016c48  inc     r10d
0x180016c4b  mov     eax, [r8+8]
0x180016c4f  mov     [rdx+8], eax
0x180016c52  mov     [rsp+1090h+var_1050], r9d
0x180016c57  add     r8, 0Ch
0x180016c5b  lea     rdx, [rsp+1090h+var_1040]
0x180016c60  cmp     r8, rdi
0x180016c63  jnz     short loc_180016BF2
0x180016c65  mov     eax, [rsp+1090h+var_104C]
0x180016c69  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180016c70  mov     [rsp+1090h+var_1060], 1
0x180016c78  mov     r8d, r9d
0x180016c7b  mov     dword ptr [rsp+1090h+var_1068], eax
0x180016c7f  call    wil_details_NtUpdateWnfStateData
0x180016c84  mov     edi, eax
0x180016c86  cmp     edi, 0C0000001h
0x180016c8c  jnz     short loc_180016C9D
0x180016c8e  inc     esi
0x180016c90  cmp     esi, 64h ; 'd'
0x180016c93  jge     short loc_180016C9D
0x180016c95  test    ebx, ebx
0x180016c97  jz      loc_180016B4F
0x180016c9d  test    ebx, ebx
0x180016c9f  cmovz   ebx, edi
0x180016ca2  mov     eax, ebx
0x180016ca4  mov     rcx, [rbp+0F90h+var_40]
0x180016cab  xor     rcx, rsp; StackCookie
0x180016cae  call    __security_check_cookie
0x180016cb3  add     rsp, 1068h
0x180016cba  pop     r14
0x180016cbc  pop     r12
0x180016cbe  pop     rdi
0x180016cbf  pop     rsi
0x180016cc0  pop     rbx
0x180016cc1  pop     rbp
0x180016cc2  retn
0x180016cc4  mov     eax, [r8+8]
0x180016cc8  add     [rcx+8], eax
0x180016ccb  mov     r9d, [rsp+1090h+var_1050]
0x180016cd0  jmp     short loc_180016C57
```
