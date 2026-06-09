# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x140007314`
- end: `0x1400074de`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140003440`

## callees

- `0x140002910`
- `0x1400032d0`
- `0x140007314`
- `0x140007730`
- `0x1400077a8`
- `0x1400078d0`

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
0x140007314  push    rbp
0x140007316  push    rbx
0x140007317  push    rsi
0x140007318  push    rdi
0x140007319  push    r12
0x14000731b  push    r14
0x14000731d  lea     rbp, [rsp-0F68h]
0x140007325  mov     eax, 1068h
0x14000732a  call    _alloca_probe
0x14000732f  sub     rsp, rax
0x140007332  mov     rax, cs:__security_cookie
0x140007339  xor     rax, rsp
0x14000733c  mov     [rbp+0F90h+var_40], rax
0x140007343  mov     rax, [rcx+8]
0x140007347  xor     ebx, ebx
0x140007349  sub     rax, [rcx]
0x14000734c  xor     edi, edi
0x14000734e  mov     r14, rcx
0x140007351  cmp     rax, 0Ch
0x140007355  jb      loc_1400074B8
0x14000735b  xor     esi, esi
0x14000735d  mov     r12, 0AAAAAAAAAAAAAAABh
0x140007367  xor     edx, edx; Val
0x140007369  lea     rcx, [rsp+1090h+var_1040]; void *
0x14000736e  mov     r8d, 1000h; Size
0x140007374  call    memset_0
0x140007379  lea     rax, [rsp+1090h+var_1050]
0x14000737e  mov     [rsp+1090h+var_1050], 1000h
0x140007386  mov     [rsp+1090h+var_1068], rax
0x14000738b  lea     r9, [rsp+1090h+var_104C]
0x140007390  lea     rax, [rsp+1090h+var_1040]
0x140007395  mov     [rsp+1090h+var_104C], 0
0x14000739d  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1400073a4  mov     [rsp+1090h+var_1070], rax
0x1400073a9  call    wil_details_NtQueryWnfStateData
0x1400073ae  mov     ebx, eax
0x1400073b0  test    eax, eax
0x1400073b2  jnz     loc_1400074A1
0x1400073b8  mov     r9d, [rsp+1090h+var_1050]
0x1400073bd  mov     rax, r12
0x1400073c0  mul     r9
0x1400073c3  shr     rdx, 3
0x1400073c7  lea     rcx, [rdx+rdx*2]
0x1400073cb  shl     rcx, 2
0x1400073cf  cmp     r9, rcx
0x1400073d2  jz      short loc_1400073DC
0x1400073d4  xor     r9d, r9d
0x1400073d7  mov     [rsp+1090h+var_1050], r9d
0x1400073dc  mov     r8, [r14]
0x1400073df  mov     rax, r12
0x1400073e2  mov     ecx, r9d
0x1400073e5  mul     rcx
0x1400073e8  mov     rcx, [r14+8]
0x1400073ec  mov     rax, r12
0x1400073ef  mov     r11, rdx
0x1400073f2  sub     rcx, r8
0x1400073f5  mul     rcx
0x1400073f8  shr     r11, 3
0x1400073fc  shr     rdx, 3
0x140007400  lea     rax, [rdx+rdx*2]
0x140007404  lea     rdi, [r8+rax*4]
0x140007408  jmp     short loc_140007476
0x14000740a  mov     eax, r11d
0x14000740d  lea     r10, [rsp+1090h+var_1040]
0x140007412  lea     rcx, [rax+rax*2]
0x140007416  lea     r10, [r10+rcx*4]
0x14000741a  cmp     rdx, r10
0x14000741d  jz      short loc_140007445
0x14000741f  mov     eax, [r8]
0x140007422  cmp     [rdx], eax
0x140007424  jnz     short loc_140007431
0x140007426  movzx   eax, word ptr [r8+4]
0x14000742b  cmp     [rdx+4], ax
0x14000742f  jz      short loc_140007437
0x140007431  add     rdx, 0Ch
0x140007435  jmp     short loc_14000741A
0x140007437  mov     eax, [r8+8]
0x14000743b  add     [rdx+8], eax
0x14000743e  mov     r9d, [rsp+1090h+var_1050]
0x140007443  jmp     short loc_140007472
0x140007445  mov     eax, r9d
0x140007448  add     rax, 0Ch
0x14000744c  cmp     rax, 1000h
0x140007452  ja      short loc_140007472
0x140007454  movsd   xmm0, qword ptr [r8]
0x140007459  add     r9d, 0Ch
0x14000745d  movsd   qword ptr [r10], xmm0
0x140007462  inc     r11d
0x140007465  mov     eax, [r8+8]
0x140007469  mov     [r10+8], eax
0x14000746d  mov     [rsp+1090h+var_1050], r9d
0x140007472  add     r8, 0Ch
0x140007476  lea     rdx, [rsp+1090h+var_1040]
0x14000747b  cmp     r8, rdi
0x14000747e  jnz     short loc_14000740A
0x140007480  mov     eax, [rsp+1090h+var_104C]
0x140007484  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000748b  mov     [rsp+1090h+var_1060], 1
0x140007493  mov     r8d, r9d
0x140007496  mov     dword ptr [rsp+1090h+var_1068], eax
0x14000749a  call    wil_details_NtUpdateWnfStateData
0x14000749f  mov     edi, eax
0x1400074a1  cmp     edi, 0C0000001h
0x1400074a7  jnz     short loc_1400074B8
0x1400074a9  inc     esi
0x1400074ab  cmp     esi, 64h ; 'd'
0x1400074ae  jge     short loc_1400074B8
0x1400074b0  test    ebx, ebx
0x1400074b2  jz      loc_140007367
0x1400074b8  test    ebx, ebx
0x1400074ba  cmovz   ebx, edi
0x1400074bd  mov     eax, ebx
0x1400074bf  mov     rcx, [rbp+0F90h+var_40]
0x1400074c6  xor     rcx, rsp; StackCookie
0x1400074c9  call    __security_check_cookie
0x1400074ce  add     rsp, 1068h
0x1400074d5  pop     r14
0x1400074d7  pop     r12
0x1400074d9  pop     rdi
0x1400074da  pop     rsi
0x1400074db  pop     rbx
0x1400074dc  pop     rbp
0x1400074dd  retn
```
