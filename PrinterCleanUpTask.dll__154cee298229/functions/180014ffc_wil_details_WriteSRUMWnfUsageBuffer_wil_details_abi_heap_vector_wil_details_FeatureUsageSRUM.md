# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180014ffc`
- end: `0x1800151c6`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180010830`

## callees

- `0x180002020`
- `0x180002b78`
- `0x180014ffc`
- `0x1800156e8`
- `0x180015760`
- `0x180015f10`

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
0x180014ffc  push    rbp
0x180014ffe  push    rbx
0x180014fff  push    rsi
0x180015000  push    rdi
0x180015001  push    r12
0x180015003  push    r14
0x180015005  lea     rbp, [rsp-0F68h]
0x18001500d  mov     eax, 1068h
0x180015012  call    _alloca_probe
0x180015017  sub     rsp, rax
0x18001501a  mov     rax, cs:__security_cookie
0x180015021  xor     rax, rsp
0x180015024  mov     [rbp+0F90h+var_40], rax
0x18001502b  mov     rax, [rcx+8]
0x18001502f  xor     ebx, ebx
0x180015031  sub     rax, [rcx]
0x180015034  xor     edi, edi
0x180015036  mov     r14, rcx
0x180015039  cmp     rax, 0Ch
0x18001503d  jb      loc_1800151A0
0x180015043  xor     esi, esi
0x180015045  mov     r12, 0AAAAAAAAAAAAAAABh
0x18001504f  xor     edx, edx; Val
0x180015051  lea     rcx, [rsp+1090h+var_1040]; void *
0x180015056  mov     r8d, 1000h; Size
0x18001505c  call    memset_0
0x180015061  lea     rax, [rsp+1090h+var_1050]
0x180015066  mov     [rsp+1090h+var_1050], 1000h
0x18001506e  mov     [rsp+1090h+var_1068], rax
0x180015073  lea     r9, [rsp+1090h+var_104C]
0x180015078  lea     rax, [rsp+1090h+var_1040]
0x18001507d  mov     [rsp+1090h+var_104C], 0
0x180015085  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18001508c  mov     [rsp+1090h+var_1070], rax
0x180015091  call    wil_details_NtQueryWnfStateData
0x180015096  mov     ebx, eax
0x180015098  test    eax, eax
0x18001509a  jnz     loc_180015189
0x1800150a0  mov     r9d, [rsp+1090h+var_1050]
0x1800150a5  mov     rax, r12
0x1800150a8  mul     r9
0x1800150ab  shr     rdx, 3
0x1800150af  lea     rcx, [rdx+rdx*2]
0x1800150b3  shl     rcx, 2
0x1800150b7  cmp     r9, rcx
0x1800150ba  jz      short loc_1800150C4
0x1800150bc  xor     r9d, r9d
0x1800150bf  mov     [rsp+1090h+var_1050], r9d
0x1800150c4  mov     r8, [r14]
0x1800150c7  mov     rax, r12
0x1800150ca  mov     ecx, r9d
0x1800150cd  mul     rcx
0x1800150d0  mov     rcx, [r14+8]
0x1800150d4  mov     rax, r12
0x1800150d7  mov     r11, rdx
0x1800150da  sub     rcx, r8
0x1800150dd  mul     rcx
0x1800150e0  shr     r11, 3
0x1800150e4  shr     rdx, 3
0x1800150e8  lea     rax, [rdx+rdx*2]
0x1800150ec  lea     rdi, [r8+rax*4]
0x1800150f0  jmp     short loc_18001515E
0x1800150f2  mov     eax, r11d
0x1800150f5  lea     r10, [rsp+1090h+var_1040]
0x1800150fa  lea     rcx, [rax+rax*2]
0x1800150fe  lea     r10, [r10+rcx*4]
0x180015102  cmp     rdx, r10
0x180015105  jz      short loc_18001512D
0x180015107  mov     eax, [r8]
0x18001510a  cmp     [rdx], eax
0x18001510c  jnz     short loc_180015119
0x18001510e  movzx   eax, word ptr [r8+4]
0x180015113  cmp     [rdx+4], ax
0x180015117  jz      short loc_18001511F
0x180015119  add     rdx, 0Ch
0x18001511d  jmp     short loc_180015102
0x18001511f  mov     eax, [r8+8]
0x180015123  add     [rdx+8], eax
0x180015126  mov     r9d, [rsp+1090h+var_1050]
0x18001512b  jmp     short loc_18001515A
0x18001512d  mov     eax, r9d
0x180015130  add     rax, 0Ch
0x180015134  cmp     rax, 1000h
0x18001513a  ja      short loc_18001515A
0x18001513c  movsd   xmm0, qword ptr [r8]
0x180015141  add     r9d, 0Ch
0x180015145  movsd   qword ptr [r10], xmm0
0x18001514a  inc     r11d
0x18001514d  mov     eax, [r8+8]
0x180015151  mov     [r10+8], eax
0x180015155  mov     [rsp+1090h+var_1050], r9d
0x18001515a  add     r8, 0Ch
0x18001515e  lea     rdx, [rsp+1090h+var_1040]
0x180015163  cmp     r8, rdi
0x180015166  jnz     short loc_1800150F2
0x180015168  mov     eax, [rsp+1090h+var_104C]
0x18001516c  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180015173  mov     [rsp+1090h+var_1060], 1
0x18001517b  mov     r8d, r9d
0x18001517e  mov     dword ptr [rsp+1090h+var_1068], eax
0x180015182  call    wil_details_NtUpdateWnfStateData
0x180015187  mov     edi, eax
0x180015189  cmp     edi, 0C0000001h
0x18001518f  jnz     short loc_1800151A0
0x180015191  inc     esi
0x180015193  cmp     esi, 64h ; 'd'
0x180015196  jge     short loc_1800151A0
0x180015198  test    ebx, ebx
0x18001519a  jz      loc_18001504F
0x1800151a0  test    ebx, ebx
0x1800151a2  cmovz   ebx, edi
0x1800151a5  mov     eax, ebx
0x1800151a7  mov     rcx, [rbp+0F90h+var_40]
0x1800151ae  xor     rcx, rsp; StackCookie
0x1800151b1  call    __security_check_cookie
0x1800151b6  add     rsp, 1068h
0x1800151bd  pop     r14
0x1800151bf  pop     r12
0x1800151c1  pop     rdi
0x1800151c2  pop     rsi
0x1800151c3  pop     rbx
0x1800151c4  pop     rbp
0x1800151c5  retn
```
