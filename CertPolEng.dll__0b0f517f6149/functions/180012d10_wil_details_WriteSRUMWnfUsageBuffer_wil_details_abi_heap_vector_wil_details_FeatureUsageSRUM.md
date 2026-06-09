# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180012d10`
- end: `0x180012eda`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18000ee00`

## callees

- `0x180012d10`
- `0x1800130cc`
- `0x180013144`
- `0x18001a342`
- `0x18001a380`
- `0x18001a440`

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
0x180012d10  push    rbp
0x180012d12  push    rbx
0x180012d13  push    rsi
0x180012d14  push    rdi
0x180012d15  push    r12
0x180012d17  push    r14
0x180012d19  lea     rbp, [rsp-0F68h]
0x180012d21  mov     eax, 1068h
0x180012d26  call    _alloca_probe
0x180012d2b  sub     rsp, rax
0x180012d2e  mov     rax, cs:__security_cookie
0x180012d35  xor     rax, rsp
0x180012d38  mov     [rbp+0F90h+var_40], rax
0x180012d3f  mov     rax, [rcx+8]
0x180012d43  xor     ebx, ebx
0x180012d45  sub     rax, [rcx]
0x180012d48  xor     edi, edi
0x180012d4a  mov     r14, rcx
0x180012d4d  cmp     rax, 0Ch
0x180012d51  jb      loc_180012EB4
0x180012d57  xor     esi, esi
0x180012d59  mov     r12, 0AAAAAAAAAAAAAAABh
0x180012d63  xor     edx, edx; Val
0x180012d65  lea     rcx, [rsp+1090h+var_1040]; void *
0x180012d6a  mov     r8d, 1000h; Size
0x180012d70  call    memset_0
0x180012d75  lea     rax, [rsp+1090h+var_1050]
0x180012d7a  mov     [rsp+1090h+var_1050], 1000h
0x180012d82  mov     [rsp+1090h+var_1068], rax
0x180012d87  lea     r9, [rsp+1090h+var_104C]
0x180012d8c  lea     rax, [rsp+1090h+var_1040]
0x180012d91  mov     [rsp+1090h+var_104C], 0
0x180012d99  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180012da0  mov     [rsp+1090h+var_1070], rax
0x180012da5  call    wil_details_NtQueryWnfStateData
0x180012daa  mov     ebx, eax
0x180012dac  test    eax, eax
0x180012dae  jnz     loc_180012E9D
0x180012db4  mov     r9d, [rsp+1090h+var_1050]
0x180012db9  mov     rax, r12
0x180012dbc  mul     r9
0x180012dbf  shr     rdx, 3
0x180012dc3  lea     rcx, [rdx+rdx*2]
0x180012dc7  shl     rcx, 2
0x180012dcb  cmp     r9, rcx
0x180012dce  jz      short loc_180012DD8
0x180012dd0  xor     r9d, r9d
0x180012dd3  mov     [rsp+1090h+var_1050], r9d
0x180012dd8  mov     r8, [r14]
0x180012ddb  mov     rax, r12
0x180012dde  mov     ecx, r9d
0x180012de1  mul     rcx
0x180012de4  mov     rcx, [r14+8]
0x180012de8  mov     rax, r12
0x180012deb  mov     r11, rdx
0x180012dee  sub     rcx, r8
0x180012df1  mul     rcx
0x180012df4  shr     r11, 3
0x180012df8  shr     rdx, 3
0x180012dfc  lea     rax, [rdx+rdx*2]
0x180012e00  lea     rdi, [r8+rax*4]
0x180012e04  jmp     short loc_180012E72
0x180012e06  mov     eax, r11d
0x180012e09  lea     r10, [rsp+1090h+var_1040]
0x180012e0e  lea     rcx, [rax+rax*2]
0x180012e12  lea     r10, [r10+rcx*4]
0x180012e16  cmp     rdx, r10
0x180012e19  jz      short loc_180012E41
0x180012e1b  mov     eax, [r8]
0x180012e1e  cmp     [rdx], eax
0x180012e20  jnz     short loc_180012E2D
0x180012e22  movzx   eax, word ptr [r8+4]
0x180012e27  cmp     [rdx+4], ax
0x180012e2b  jz      short loc_180012E33
0x180012e2d  add     rdx, 0Ch
0x180012e31  jmp     short loc_180012E16
0x180012e33  mov     eax, [r8+8]
0x180012e37  add     [rdx+8], eax
0x180012e3a  mov     r9d, [rsp+1090h+var_1050]
0x180012e3f  jmp     short loc_180012E6E
0x180012e41  mov     eax, r9d
0x180012e44  add     rax, 0Ch
0x180012e48  cmp     rax, 1000h
0x180012e4e  ja      short loc_180012E6E
0x180012e50  movsd   xmm0, qword ptr [r8]
0x180012e55  add     r9d, 0Ch
0x180012e59  movsd   qword ptr [r10], xmm0
0x180012e5e  inc     r11d
0x180012e61  mov     eax, [r8+8]
0x180012e65  mov     [r10+8], eax
0x180012e69  mov     [rsp+1090h+var_1050], r9d
0x180012e6e  add     r8, 0Ch
0x180012e72  lea     rdx, [rsp+1090h+var_1040]
0x180012e77  cmp     r8, rdi
0x180012e7a  jnz     short loc_180012E06
0x180012e7c  mov     eax, [rsp+1090h+var_104C]
0x180012e80  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180012e87  mov     [rsp+1090h+var_1060], 1
0x180012e8f  mov     r8d, r9d
0x180012e92  mov     dword ptr [rsp+1090h+var_1068], eax
0x180012e96  call    wil_details_NtUpdateWnfStateData
0x180012e9b  mov     edi, eax
0x180012e9d  cmp     edi, 0C0000001h
0x180012ea3  jnz     short loc_180012EB4
0x180012ea5  inc     esi
0x180012ea7  cmp     esi, 64h ; 'd'
0x180012eaa  jge     short loc_180012EB4
0x180012eac  test    ebx, ebx
0x180012eae  jz      loc_180012D63
0x180012eb4  test    ebx, ebx
0x180012eb6  cmovz   ebx, edi
0x180012eb9  mov     eax, ebx
0x180012ebb  mov     rcx, [rbp+0F90h+var_40]
0x180012ec2  xor     rcx, rsp; StackCookie
0x180012ec5  call    __security_check_cookie
0x180012eca  add     rsp, 1068h
0x180012ed1  pop     r14
0x180012ed3  pop     r12
0x180012ed5  pop     rdi
0x180012ed6  pop     rsi
0x180012ed7  pop     rbx
0x180012ed8  pop     rbp
0x180012ed9  retn
```
