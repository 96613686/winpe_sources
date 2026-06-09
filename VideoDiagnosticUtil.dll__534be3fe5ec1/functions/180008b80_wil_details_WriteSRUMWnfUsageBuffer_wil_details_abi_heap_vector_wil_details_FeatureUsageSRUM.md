# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180008b80`
- end: `0x180008d56`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `470`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800022e0`

## callees

- `0x180008b80`
- `0x180008d5c`
- `0x180008e04`
- `0x18000967e`
- `0x1800096b0`
- `0x180009740`

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
0x180008b80  push    rbp
0x180008b82  push    rbx
0x180008b83  push    rsi
0x180008b84  push    rdi
0x180008b85  push    r12
0x180008b87  push    r14
0x180008b89  lea     rbp, [rsp-0F68h]
0x180008b91  mov     eax, 1068h
0x180008b96  call    _alloca_probe
0x180008b9b  sub     rsp, rax
0x180008b9e  mov     rax, cs:__security_cookie
0x180008ba5  xor     rax, rsp
0x180008ba8  mov     [rbp+0F90h+var_40], rax
0x180008baf  mov     rax, [rcx+8]
0x180008bb3  xor     ebx, ebx
0x180008bb5  sub     rax, [rcx]
0x180008bb8  xor     edi, edi
0x180008bba  mov     r14, rcx
0x180008bbd  cmp     rax, 0Ch
0x180008bc1  jb      loc_180008D21
0x180008bc7  xor     esi, esi
0x180008bc9  mov     r12, 0AAAAAAAAAAAAAAABh
0x180008bd3  xor     edx, edx; Val
0x180008bd5  lea     rcx, [rsp+1090h+var_1040]; void *
0x180008bda  mov     r8d, 1000h; Size
0x180008be0  call    memset_0
0x180008be5  lea     rax, [rsp+1090h+var_1050]
0x180008bea  mov     [rsp+1090h+var_1050], 1000h
0x180008bf2  mov     [rsp+1090h+var_1068], rax
0x180008bf7  lea     r9, [rsp+1090h+var_104C]
0x180008bfc  lea     rax, [rsp+1090h+var_1040]
0x180008c01  mov     [rsp+1090h+var_104C], 0
0x180008c09  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180008c10  mov     [rsp+1090h+var_1070], rax
0x180008c15  call    wil_details_NtQueryWnfStateData
0x180008c1a  mov     ebx, eax
0x180008c1c  test    eax, eax
0x180008c1e  jnz     loc_180008D0A
0x180008c24  mov     r9d, [rsp+1090h+var_1050]
0x180008c29  mov     rax, r12
0x180008c2c  mul     r9
0x180008c2f  shr     rdx, 3
0x180008c33  lea     rcx, [rdx+rdx*2]
0x180008c37  shl     rcx, 2
0x180008c3b  cmp     r9, rcx
0x180008c3e  jz      short loc_180008C48
0x180008c40  xor     r9d, r9d
0x180008c43  mov     [rsp+1090h+var_1050], r9d
0x180008c48  mov     r8, [r14]
0x180008c4b  mov     rax, r12
0x180008c4e  mov     ecx, r9d
0x180008c51  mul     rcx
0x180008c54  mov     rcx, [r14+8]
0x180008c58  mov     rax, r12
0x180008c5b  mov     r10, rdx
0x180008c5e  sub     rcx, r8
0x180008c61  mul     rcx
0x180008c64  shr     r10, 3
0x180008c68  shr     rdx, 3
0x180008c6c  lea     rax, [rdx+rdx*2]
0x180008c70  lea     rdi, [r8+rax*4]
0x180008c74  jmp     short loc_180008CDF
0x180008c76  mov     eax, r10d
0x180008c79  lea     rcx, [rax+rax*2]
0x180008c7d  lea     rdx, [rdx+rcx*4]
0x180008c81  lea     rax, [rsp+1090h+var_1040]
0x180008c86  cmp     rax, rdx
0x180008c89  jz      short loc_180008CB0
0x180008c8b  mov     r11d, [r8]
0x180008c8e  lea     rcx, [rsp+1090h+var_1040]
0x180008c93  cmp     [rcx], r11d
0x180008c96  jnz     short loc_180008CA7
0x180008c98  movzx   eax, word ptr [r8+4]
0x180008c9d  cmp     [rcx+4], ax
0x180008ca1  jz      loc_180008D48
0x180008ca7  add     rcx, 0Ch
0x180008cab  cmp     rcx, rdx
0x180008cae  jnz     short loc_180008C93
0x180008cb0  mov     eax, r9d
0x180008cb3  add     rax, 0Ch
0x180008cb7  cmp     rax, 1000h
0x180008cbd  ja      short loc_180008CDB
0x180008cbf  movsd   xmm0, qword ptr [r8]
0x180008cc4  add     r9d, 0Ch
0x180008cc8  movsd   qword ptr [rdx], xmm0
0x180008ccc  inc     r10d
0x180008ccf  mov     eax, [r8+8]
0x180008cd3  mov     [rdx+8], eax
0x180008cd6  mov     [rsp+1090h+var_1050], r9d
0x180008cdb  add     r8, 0Ch
0x180008cdf  lea     rdx, [rsp+1090h+var_1040]
0x180008ce4  cmp     r8, rdi
0x180008ce7  jnz     short loc_180008C76
0x180008ce9  mov     eax, [rsp+1090h+var_104C]
0x180008ced  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180008cf4  mov     [rsp+1090h+var_1060], 1
0x180008cfc  mov     r8d, r9d
0x180008cff  mov     dword ptr [rsp+1090h+var_1068], eax
0x180008d03  call    wil_details_NtUpdateWnfStateData
0x180008d08  mov     edi, eax
0x180008d0a  cmp     edi, 0C0000001h
0x180008d10  jnz     short loc_180008D21
0x180008d12  inc     esi
0x180008d14  cmp     esi, 64h ; 'd'
0x180008d17  jge     short loc_180008D21
0x180008d19  test    ebx, ebx
0x180008d1b  jz      loc_180008BD3
0x180008d21  test    ebx, ebx
0x180008d23  cmovz   ebx, edi
0x180008d26  mov     eax, ebx
0x180008d28  mov     rcx, [rbp+0F90h+var_40]
0x180008d2f  xor     rcx, rsp; StackCookie
0x180008d32  call    __security_check_cookie
0x180008d37  add     rsp, 1068h
0x180008d3e  pop     r14
0x180008d40  pop     r12
0x180008d42  pop     rdi
0x180008d43  pop     rsi
0x180008d44  pop     rbx
0x180008d45  pop     rbp
0x180008d46  retn
0x180008d48  mov     eax, [r8+8]
0x180008d4c  add     [rcx+8], eax
0x180008d4f  mov     r9d, [rsp+1090h+var_1050]
0x180008d54  jmp     short loc_180008CDB
```
