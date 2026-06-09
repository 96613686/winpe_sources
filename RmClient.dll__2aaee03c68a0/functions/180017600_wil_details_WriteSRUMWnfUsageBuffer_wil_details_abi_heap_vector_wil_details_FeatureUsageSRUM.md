# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180017600`
- end: `0x1800177ca`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180015b70`

## callees

- `0x180013004`
- `0x180017600`
- `0x180017a58`
- `0x18001ae8e`
- `0x18001aec0`
- `0x18001af50`

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
0x180017600  push    rbp
0x180017602  push    rbx
0x180017603  push    rsi
0x180017604  push    rdi
0x180017605  push    r12
0x180017607  push    r14
0x180017609  lea     rbp, [rsp-0F68h]
0x180017611  mov     eax, 1068h
0x180017616  call    _alloca_probe
0x18001761b  sub     rsp, rax
0x18001761e  mov     rax, cs:__security_cookie
0x180017625  xor     rax, rsp
0x180017628  mov     [rbp+0F90h+var_40], rax
0x18001762f  mov     rax, [rcx+8]
0x180017633  xor     ebx, ebx
0x180017635  sub     rax, [rcx]
0x180017638  xor     edi, edi
0x18001763a  mov     r14, rcx
0x18001763d  cmp     rax, 0Ch
0x180017641  jb      loc_1800177A4
0x180017647  xor     esi, esi
0x180017649  mov     r12, 0AAAAAAAAAAAAAAABh
0x180017653  xor     edx, edx; Val
0x180017655  lea     rcx, [rsp+1090h+var_1040]; void *
0x18001765a  mov     r8d, 1000h; Size
0x180017660  call    memset_0
0x180017665  lea     rax, [rsp+1090h+var_1050]
0x18001766a  mov     [rsp+1090h+var_1050], 1000h
0x180017672  mov     [rsp+1090h+var_1068], rax
0x180017677  lea     r9, [rsp+1090h+var_104C]
0x18001767c  lea     rax, [rsp+1090h+var_1040]
0x180017681  mov     [rsp+1090h+var_104C], 0
0x180017689  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180017690  mov     [rsp+1090h+var_1070], rax
0x180017695  call    wil_details_NtQueryWnfStateData
0x18001769a  mov     ebx, eax
0x18001769c  test    eax, eax
0x18001769e  jnz     loc_18001778D
0x1800176a4  mov     r9d, [rsp+1090h+var_1050]
0x1800176a9  mov     rax, r12
0x1800176ac  mul     r9
0x1800176af  shr     rdx, 3
0x1800176b3  lea     rcx, [rdx+rdx*2]
0x1800176b7  shl     rcx, 2
0x1800176bb  cmp     r9, rcx
0x1800176be  jz      short loc_1800176C8
0x1800176c0  xor     r9d, r9d
0x1800176c3  mov     [rsp+1090h+var_1050], r9d
0x1800176c8  mov     r8, [r14]
0x1800176cb  mov     rax, r12
0x1800176ce  mov     ecx, r9d
0x1800176d1  mul     rcx
0x1800176d4  mov     rcx, [r14+8]
0x1800176d8  mov     rax, r12
0x1800176db  mov     r11, rdx
0x1800176de  sub     rcx, r8
0x1800176e1  mul     rcx
0x1800176e4  shr     r11, 3
0x1800176e8  shr     rdx, 3
0x1800176ec  lea     rax, [rdx+rdx*2]
0x1800176f0  lea     rdi, [r8+rax*4]
0x1800176f4  jmp     short loc_180017762
0x1800176f6  mov     eax, r11d
0x1800176f9  lea     r10, [rsp+1090h+var_1040]
0x1800176fe  lea     rcx, [rax+rax*2]
0x180017702  lea     r10, [r10+rcx*4]
0x180017706  cmp     rdx, r10
0x180017709  jz      short loc_180017731
0x18001770b  mov     eax, [r8]
0x18001770e  cmp     [rdx], eax
0x180017710  jnz     short loc_18001771D
0x180017712  movzx   eax, word ptr [r8+4]
0x180017717  cmp     [rdx+4], ax
0x18001771b  jz      short loc_180017723
0x18001771d  add     rdx, 0Ch
0x180017721  jmp     short loc_180017706
0x180017723  mov     eax, [r8+8]
0x180017727  add     [rdx+8], eax
0x18001772a  mov     r9d, [rsp+1090h+var_1050]
0x18001772f  jmp     short loc_18001775E
0x180017731  mov     eax, r9d
0x180017734  add     rax, 0Ch
0x180017738  cmp     rax, 1000h
0x18001773e  ja      short loc_18001775E
0x180017740  movsd   xmm0, qword ptr [r8]
0x180017745  add     r9d, 0Ch
0x180017749  movsd   qword ptr [r10], xmm0
0x18001774e  inc     r11d
0x180017751  mov     eax, [r8+8]
0x180017755  mov     [r10+8], eax
0x180017759  mov     [rsp+1090h+var_1050], r9d
0x18001775e  add     r8, 0Ch
0x180017762  lea     rdx, [rsp+1090h+var_1040]
0x180017767  cmp     r8, rdi
0x18001776a  jnz     short loc_1800176F6
0x18001776c  mov     eax, [rsp+1090h+var_104C]
0x180017770  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180017777  mov     [rsp+1090h+var_1060], 1
0x18001777f  mov     r8d, r9d
0x180017782  mov     dword ptr [rsp+1090h+var_1068], eax
0x180017786  call    wil_details_NtUpdateWnfStateData
0x18001778b  mov     edi, eax
0x18001778d  cmp     edi, 0C0000001h
0x180017793  jnz     short loc_1800177A4
0x180017795  inc     esi
0x180017797  cmp     esi, 64h ; 'd'
0x18001779a  jge     short loc_1800177A4
0x18001779c  test    ebx, ebx
0x18001779e  jz      loc_180017653
0x1800177a4  test    ebx, ebx
0x1800177a6  cmovz   ebx, edi
0x1800177a9  mov     eax, ebx
0x1800177ab  mov     rcx, [rbp+0F90h+var_40]
0x1800177b2  xor     rcx, rsp; StackCookie
0x1800177b5  call    __security_check_cookie
0x1800177ba  add     rsp, 1068h
0x1800177c1  pop     r14
0x1800177c3  pop     r12
0x1800177c5  pop     rdi
0x1800177c6  pop     rsi
0x1800177c7  pop     rbx
0x1800177c8  pop     rbp
0x1800177c9  retn
```
