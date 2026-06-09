# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x1800144f4`
- end: `0x1800146be`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18000f9a0`

## callees

- `0x18000eb70`
- `0x18000f4dc`
- `0x1800144f4`
- `0x180014a9c`
- `0x180014b14`
- `0x180028390`

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
0x1800144f4  push    rbp
0x1800144f6  push    rbx
0x1800144f7  push    rsi
0x1800144f8  push    rdi
0x1800144f9  push    r12
0x1800144fb  push    r14
0x1800144fd  lea     rbp, [rsp-0F68h]
0x180014505  mov     eax, 1068h
0x18001450a  call    _alloca_probe
0x18001450f  sub     rsp, rax
0x180014512  mov     rax, cs:__security_cookie
0x180014519  xor     rax, rsp
0x18001451c  mov     [rbp+0F90h+var_40], rax
0x180014523  mov     rax, [rcx+8]
0x180014527  xor     ebx, ebx
0x180014529  sub     rax, [rcx]
0x18001452c  xor     edi, edi
0x18001452e  mov     r14, rcx
0x180014531  cmp     rax, 0Ch
0x180014535  jb      loc_180014698
0x18001453b  xor     esi, esi
0x18001453d  mov     r12, 0AAAAAAAAAAAAAAABh
0x180014547  xor     edx, edx; Val
0x180014549  lea     rcx, [rsp+1090h+var_1040]; void *
0x18001454e  mov     r8d, 1000h; Size
0x180014554  call    memset_0
0x180014559  lea     rax, [rsp+1090h+var_1050]
0x18001455e  mov     [rsp+1090h+var_1050], 1000h
0x180014566  mov     [rsp+1090h+var_1068], rax
0x18001456b  lea     r9, [rsp+1090h+var_104C]
0x180014570  lea     rax, [rsp+1090h+var_1040]
0x180014575  mov     [rsp+1090h+var_104C], 0
0x18001457d  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180014584  mov     [rsp+1090h+var_1070], rax
0x180014589  call    wil_details_NtQueryWnfStateData
0x18001458e  mov     ebx, eax
0x180014590  test    eax, eax
0x180014592  jnz     loc_180014681
0x180014598  mov     r9d, [rsp+1090h+var_1050]
0x18001459d  mov     rax, r12
0x1800145a0  mul     r9
0x1800145a3  shr     rdx, 3
0x1800145a7  lea     rcx, [rdx+rdx*2]
0x1800145ab  shl     rcx, 2
0x1800145af  cmp     r9, rcx
0x1800145b2  jz      short loc_1800145BC
0x1800145b4  xor     r9d, r9d
0x1800145b7  mov     [rsp+1090h+var_1050], r9d
0x1800145bc  mov     r8, [r14]
0x1800145bf  mov     rax, r12
0x1800145c2  mov     ecx, r9d
0x1800145c5  mul     rcx
0x1800145c8  mov     rcx, [r14+8]
0x1800145cc  mov     rax, r12
0x1800145cf  mov     r11, rdx
0x1800145d2  sub     rcx, r8
0x1800145d5  mul     rcx
0x1800145d8  shr     r11, 3
0x1800145dc  shr     rdx, 3
0x1800145e0  lea     rax, [rdx+rdx*2]
0x1800145e4  lea     rdi, [r8+rax*4]
0x1800145e8  jmp     short loc_180014656
0x1800145ea  mov     eax, r11d
0x1800145ed  lea     r10, [rsp+1090h+var_1040]
0x1800145f2  lea     rcx, [rax+rax*2]
0x1800145f6  lea     r10, [r10+rcx*4]
0x1800145fa  cmp     rdx, r10
0x1800145fd  jz      short loc_180014625
0x1800145ff  mov     eax, [r8]
0x180014602  cmp     [rdx], eax
0x180014604  jnz     short loc_180014611
0x180014606  movzx   eax, word ptr [r8+4]
0x18001460b  cmp     [rdx+4], ax
0x18001460f  jz      short loc_180014617
0x180014611  add     rdx, 0Ch
0x180014615  jmp     short loc_1800145FA
0x180014617  mov     eax, [r8+8]
0x18001461b  add     [rdx+8], eax
0x18001461e  mov     r9d, [rsp+1090h+var_1050]
0x180014623  jmp     short loc_180014652
0x180014625  mov     eax, r9d
0x180014628  add     rax, 0Ch
0x18001462c  cmp     rax, 1000h
0x180014632  ja      short loc_180014652
0x180014634  movsd   xmm0, qword ptr [r8]
0x180014639  add     r9d, 0Ch
0x18001463d  movsd   qword ptr [r10], xmm0
0x180014642  inc     r11d
0x180014645  mov     eax, [r8+8]
0x180014649  mov     [r10+8], eax
0x18001464d  mov     [rsp+1090h+var_1050], r9d
0x180014652  add     r8, 0Ch
0x180014656  lea     rdx, [rsp+1090h+var_1040]
0x18001465b  cmp     r8, rdi
0x18001465e  jnz     short loc_1800145EA
0x180014660  mov     eax, [rsp+1090h+var_104C]
0x180014664  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18001466b  mov     [rsp+1090h+var_1060], 1
0x180014673  mov     r8d, r9d
0x180014676  mov     dword ptr [rsp+1090h+var_1068], eax
0x18001467a  call    wil_details_NtUpdateWnfStateData
0x18001467f  mov     edi, eax
0x180014681  cmp     edi, 0C0000001h
0x180014687  jnz     short loc_180014698
0x180014689  inc     esi
0x18001468b  cmp     esi, 64h ; 'd'
0x18001468e  jge     short loc_180014698
0x180014690  test    ebx, ebx
0x180014692  jz      loc_180014547
0x180014698  test    ebx, ebx
0x18001469a  cmovz   ebx, edi
0x18001469d  mov     eax, ebx
0x18001469f  mov     rcx, [rbp+0F90h+var_40]
0x1800146a6  xor     rcx, rsp; StackCookie
0x1800146a9  call    __security_check_cookie
0x1800146ae  add     rsp, 1068h
0x1800146b5  pop     r14
0x1800146b7  pop     r12
0x1800146b9  pop     rdi
0x1800146ba  pop     rsi
0x1800146bb  pop     rbx
0x1800146bc  pop     rbp
0x1800146bd  retn
```
