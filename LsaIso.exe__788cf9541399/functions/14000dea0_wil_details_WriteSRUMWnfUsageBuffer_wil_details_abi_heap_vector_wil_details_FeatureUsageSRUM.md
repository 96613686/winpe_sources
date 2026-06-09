# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x14000dea0`
- end: `0x14000e06a`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140006d80`

## callees

- `0x14000dea0`
- `0x1400122a0`
- `0x140012318`
- `0x140038cd2`
- `0x140038d10`
- `0x140038dd0`

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
0x14000dea0  push    rbp
0x14000dea2  push    rbx
0x14000dea3  push    rsi
0x14000dea4  push    rdi
0x14000dea5  push    r12
0x14000dea7  push    r14
0x14000dea9  lea     rbp, [rsp-0F68h]
0x14000deb1  mov     eax, 1068h
0x14000deb6  call    _alloca_probe
0x14000debb  sub     rsp, rax
0x14000debe  mov     rax, cs:__security_cookie
0x14000dec5  xor     rax, rsp
0x14000dec8  mov     [rbp+0F90h+var_40], rax
0x14000decf  mov     rax, [rcx+8]
0x14000ded3  xor     ebx, ebx
0x14000ded5  sub     rax, [rcx]
0x14000ded8  xor     edi, edi
0x14000deda  mov     r14, rcx
0x14000dedd  cmp     rax, 0Ch
0x14000dee1  jb      loc_14000E044
0x14000dee7  xor     esi, esi
0x14000dee9  mov     r12, 0AAAAAAAAAAAAAAABh
0x14000def3  xor     edx, edx; Val
0x14000def5  lea     rcx, [rsp+1090h+var_1040]; void *
0x14000defa  mov     r8d, 1000h; Size
0x14000df00  call    memset_0
0x14000df05  lea     rax, [rsp+1090h+var_1050]
0x14000df0a  mov     [rsp+1090h+var_1050], 1000h
0x14000df12  mov     [rsp+1090h+var_1068], rax
0x14000df17  lea     r9, [rsp+1090h+var_104C]
0x14000df1c  lea     rax, [rsp+1090h+var_1040]
0x14000df21  mov     [rsp+1090h+var_104C], 0
0x14000df29  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000df30  mov     [rsp+1090h+var_1070], rax
0x14000df35  call    wil_details_NtQueryWnfStateData
0x14000df3a  mov     ebx, eax
0x14000df3c  test    eax, eax
0x14000df3e  jnz     loc_14000E02D
0x14000df44  mov     r9d, [rsp+1090h+var_1050]
0x14000df49  mov     rax, r12
0x14000df4c  mul     r9
0x14000df4f  shr     rdx, 3
0x14000df53  lea     rcx, [rdx+rdx*2]
0x14000df57  shl     rcx, 2
0x14000df5b  cmp     r9, rcx
0x14000df5e  jz      short loc_14000DF68
0x14000df60  xor     r9d, r9d
0x14000df63  mov     [rsp+1090h+var_1050], r9d
0x14000df68  mov     r8, [r14]
0x14000df6b  mov     rax, r12
0x14000df6e  mov     ecx, r9d
0x14000df71  mul     rcx
0x14000df74  mov     rcx, [r14+8]
0x14000df78  mov     rax, r12
0x14000df7b  mov     r11, rdx
0x14000df7e  sub     rcx, r8
0x14000df81  mul     rcx
0x14000df84  shr     r11, 3
0x14000df88  shr     rdx, 3
0x14000df8c  lea     rax, [rdx+rdx*2]
0x14000df90  lea     rdi, [r8+rax*4]
0x14000df94  jmp     short loc_14000E002
0x14000df96  mov     eax, r11d
0x14000df99  lea     r10, [rsp+1090h+var_1040]
0x14000df9e  lea     rcx, [rax+rax*2]
0x14000dfa2  lea     r10, [r10+rcx*4]
0x14000dfa6  cmp     rdx, r10
0x14000dfa9  jz      short loc_14000DFD1
0x14000dfab  mov     eax, [r8]
0x14000dfae  cmp     [rdx], eax
0x14000dfb0  jnz     short loc_14000DFBD
0x14000dfb2  movzx   eax, word ptr [r8+4]
0x14000dfb7  cmp     [rdx+4], ax
0x14000dfbb  jz      short loc_14000DFC3
0x14000dfbd  add     rdx, 0Ch
0x14000dfc1  jmp     short loc_14000DFA6
0x14000dfc3  mov     eax, [r8+8]
0x14000dfc7  add     [rdx+8], eax
0x14000dfca  mov     r9d, [rsp+1090h+var_1050]
0x14000dfcf  jmp     short loc_14000DFFE
0x14000dfd1  mov     eax, r9d
0x14000dfd4  add     rax, 0Ch
0x14000dfd8  cmp     rax, 1000h
0x14000dfde  ja      short loc_14000DFFE
0x14000dfe0  movsd   xmm0, qword ptr [r8]
0x14000dfe5  add     r9d, 0Ch
0x14000dfe9  movsd   qword ptr [r10], xmm0
0x14000dfee  inc     r11d
0x14000dff1  mov     eax, [r8+8]
0x14000dff5  mov     [r10+8], eax
0x14000dff9  mov     [rsp+1090h+var_1050], r9d
0x14000dffe  add     r8, 0Ch
0x14000e002  lea     rdx, [rsp+1090h+var_1040]
0x14000e007  cmp     r8, rdi
0x14000e00a  jnz     short loc_14000DF96
0x14000e00c  mov     eax, [rsp+1090h+var_104C]
0x14000e010  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000e017  mov     [rsp+1090h+var_1060], 1
0x14000e01f  mov     r8d, r9d
0x14000e022  mov     dword ptr [rsp+1090h+var_1068], eax
0x14000e026  call    wil_details_NtUpdateWnfStateData
0x14000e02b  mov     edi, eax
0x14000e02d  cmp     edi, 0C0000001h
0x14000e033  jnz     short loc_14000E044
0x14000e035  inc     esi
0x14000e037  cmp     esi, 64h ; 'd'
0x14000e03a  jge     short loc_14000E044
0x14000e03c  test    ebx, ebx
0x14000e03e  jz      loc_14000DEF3
0x14000e044  test    ebx, ebx
0x14000e046  cmovz   ebx, edi
0x14000e049  mov     eax, ebx
0x14000e04b  mov     rcx, [rbp+0F90h+var_40]
0x14000e052  xor     rcx, rsp; StackCookie
0x14000e055  call    __security_check_cookie
0x14000e05a  add     rsp, 1068h
0x14000e061  pop     r14
0x14000e063  pop     r12
0x14000e065  pop     rdi
0x14000e066  pop     rsi
0x14000e067  pop     rbx
0x14000e068  pop     rbp
0x14000e069  retn
```
