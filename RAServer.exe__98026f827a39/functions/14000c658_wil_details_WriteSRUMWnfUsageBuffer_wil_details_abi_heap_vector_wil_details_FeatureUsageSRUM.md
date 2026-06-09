# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x14000c658`
- end: `0x14000c822`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140002590`

## callees

- `0x1400022d3`
- `0x14000c658`
- `0x14000c8b8`
- `0x14000c930`
- `0x140015aa0`
- `0x140015b60`

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
0x14000c658  push    rbp
0x14000c65a  push    rbx
0x14000c65b  push    rsi
0x14000c65c  push    rdi
0x14000c65d  push    r12
0x14000c65f  push    r14
0x14000c661  lea     rbp, [rsp-0F68h]
0x14000c669  mov     eax, 1068h
0x14000c66e  call    _alloca_probe
0x14000c673  sub     rsp, rax
0x14000c676  mov     rax, cs:__security_cookie
0x14000c67d  xor     rax, rsp
0x14000c680  mov     [rbp+0F90h+var_40], rax
0x14000c687  mov     rax, [rcx+8]
0x14000c68b  xor     ebx, ebx
0x14000c68d  sub     rax, [rcx]
0x14000c690  xor     edi, edi
0x14000c692  mov     r14, rcx
0x14000c695  cmp     rax, 0Ch
0x14000c699  jb      loc_14000C7FC
0x14000c69f  xor     esi, esi
0x14000c6a1  mov     r12, 0AAAAAAAAAAAAAAABh
0x14000c6ab  xor     edx, edx; Val
0x14000c6ad  lea     rcx, [rsp+1090h+var_1040]; void *
0x14000c6b2  mov     r8d, 1000h; Size
0x14000c6b8  call    memset_0
0x14000c6bd  lea     rax, [rsp+1090h+var_1050]
0x14000c6c2  mov     [rsp+1090h+var_1050], 1000h
0x14000c6ca  mov     [rsp+1090h+var_1068], rax
0x14000c6cf  lea     r9, [rsp+1090h+var_104C]
0x14000c6d4  lea     rax, [rsp+1090h+var_1040]
0x14000c6d9  mov     [rsp+1090h+var_104C], 0
0x14000c6e1  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000c6e8  mov     [rsp+1090h+var_1070], rax
0x14000c6ed  call    wil_details_NtQueryWnfStateData
0x14000c6f2  mov     ebx, eax
0x14000c6f4  test    eax, eax
0x14000c6f6  jnz     loc_14000C7E5
0x14000c6fc  mov     r9d, [rsp+1090h+var_1050]
0x14000c701  mov     rax, r12
0x14000c704  mul     r9
0x14000c707  shr     rdx, 3
0x14000c70b  lea     rcx, [rdx+rdx*2]
0x14000c70f  shl     rcx, 2
0x14000c713  cmp     r9, rcx
0x14000c716  jz      short loc_14000C720
0x14000c718  xor     r9d, r9d
0x14000c71b  mov     [rsp+1090h+var_1050], r9d
0x14000c720  mov     r8, [r14]
0x14000c723  mov     rax, r12
0x14000c726  mov     ecx, r9d
0x14000c729  mul     rcx
0x14000c72c  mov     rcx, [r14+8]
0x14000c730  mov     rax, r12
0x14000c733  mov     r11, rdx
0x14000c736  sub     rcx, r8
0x14000c739  mul     rcx
0x14000c73c  shr     r11, 3
0x14000c740  shr     rdx, 3
0x14000c744  lea     rax, [rdx+rdx*2]
0x14000c748  lea     rdi, [r8+rax*4]
0x14000c74c  jmp     short loc_14000C7BA
0x14000c74e  mov     eax, r11d
0x14000c751  lea     r10, [rsp+1090h+var_1040]
0x14000c756  lea     rcx, [rax+rax*2]
0x14000c75a  lea     r10, [r10+rcx*4]
0x14000c75e  cmp     rdx, r10
0x14000c761  jz      short loc_14000C789
0x14000c763  mov     eax, [r8]
0x14000c766  cmp     [rdx], eax
0x14000c768  jnz     short loc_14000C775
0x14000c76a  movzx   eax, word ptr [r8+4]
0x14000c76f  cmp     [rdx+4], ax
0x14000c773  jz      short loc_14000C77B
0x14000c775  add     rdx, 0Ch
0x14000c779  jmp     short loc_14000C75E
0x14000c77b  mov     eax, [r8+8]
0x14000c77f  add     [rdx+8], eax
0x14000c782  mov     r9d, [rsp+1090h+var_1050]
0x14000c787  jmp     short loc_14000C7B6
0x14000c789  mov     eax, r9d
0x14000c78c  add     rax, 0Ch
0x14000c790  cmp     rax, 1000h
0x14000c796  ja      short loc_14000C7B6
0x14000c798  movsd   xmm0, qword ptr [r8]
0x14000c79d  add     r9d, 0Ch
0x14000c7a1  movsd   qword ptr [r10], xmm0
0x14000c7a6  inc     r11d
0x14000c7a9  mov     eax, [r8+8]
0x14000c7ad  mov     [r10+8], eax
0x14000c7b1  mov     [rsp+1090h+var_1050], r9d
0x14000c7b6  add     r8, 0Ch
0x14000c7ba  lea     rdx, [rsp+1090h+var_1040]
0x14000c7bf  cmp     r8, rdi
0x14000c7c2  jnz     short loc_14000C74E
0x14000c7c4  mov     eax, [rsp+1090h+var_104C]
0x14000c7c8  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000c7cf  mov     [rsp+1090h+var_1060], 1
0x14000c7d7  mov     r8d, r9d
0x14000c7da  mov     dword ptr [rsp+1090h+var_1068], eax
0x14000c7de  call    wil_details_NtUpdateWnfStateData
0x14000c7e3  mov     edi, eax
0x14000c7e5  cmp     edi, 0C0000001h
0x14000c7eb  jnz     short loc_14000C7FC
0x14000c7ed  inc     esi
0x14000c7ef  cmp     esi, 64h ; 'd'
0x14000c7f2  jge     short loc_14000C7FC
0x14000c7f4  test    ebx, ebx
0x14000c7f6  jz      loc_14000C6AB
0x14000c7fc  test    ebx, ebx
0x14000c7fe  cmovz   ebx, edi
0x14000c801  mov     eax, ebx
0x14000c803  mov     rcx, [rbp+0F90h+var_40]
0x14000c80a  xor     rcx, rsp; StackCookie
0x14000c80d  call    __security_check_cookie
0x14000c812  add     rsp, 1068h
0x14000c819  pop     r14
0x14000c81b  pop     r12
0x14000c81d  pop     rdi
0x14000c81e  pop     rsi
0x14000c81f  pop     rbx
0x14000c820  pop     rbp
0x14000c821  retn
```
