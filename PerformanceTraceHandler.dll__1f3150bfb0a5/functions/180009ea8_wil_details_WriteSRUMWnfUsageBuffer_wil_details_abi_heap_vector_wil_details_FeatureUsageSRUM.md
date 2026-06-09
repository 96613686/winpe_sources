# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180009ea8`
- end: `0x18000a072`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180003970`

## callees

- `0x180002c00`
- `0x180003710`
- `0x180009ea8`
- `0x18000a33c`
- `0x18000a3b4`
- `0x18001a540`

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
0x180009ea8  push    rbp
0x180009eaa  push    rbx
0x180009eab  push    rsi
0x180009eac  push    rdi
0x180009ead  push    r12
0x180009eaf  push    r14
0x180009eb1  lea     rbp, [rsp-0F68h]
0x180009eb9  mov     eax, 1068h
0x180009ebe  call    _alloca_probe
0x180009ec3  sub     rsp, rax
0x180009ec6  mov     rax, cs:__security_cookie
0x180009ecd  xor     rax, rsp
0x180009ed0  mov     [rbp+0F90h+var_40], rax
0x180009ed7  mov     rax, [rcx+8]
0x180009edb  xor     ebx, ebx
0x180009edd  sub     rax, [rcx]
0x180009ee0  xor     edi, edi
0x180009ee2  mov     r14, rcx
0x180009ee5  cmp     rax, 0Ch
0x180009ee9  jb      loc_18000A04C
0x180009eef  xor     esi, esi
0x180009ef1  mov     r12, 0AAAAAAAAAAAAAAABh
0x180009efb  xor     edx, edx; Val
0x180009efd  lea     rcx, [rsp+1090h+var_1040]; void *
0x180009f02  mov     r8d, 1000h; Size
0x180009f08  call    memset_0
0x180009f0d  lea     rax, [rsp+1090h+var_1050]
0x180009f12  mov     [rsp+1090h+var_1050], 1000h
0x180009f1a  mov     [rsp+1090h+var_1068], rax
0x180009f1f  lea     r9, [rsp+1090h+var_104C]
0x180009f24  lea     rax, [rsp+1090h+var_1040]
0x180009f29  mov     [rsp+1090h+var_104C], 0
0x180009f31  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180009f38  mov     [rsp+1090h+var_1070], rax
0x180009f3d  call    wil_details_NtQueryWnfStateData
0x180009f42  mov     ebx, eax
0x180009f44  test    eax, eax
0x180009f46  jnz     loc_18000A035
0x180009f4c  mov     r9d, [rsp+1090h+var_1050]
0x180009f51  mov     rax, r12
0x180009f54  mul     r9
0x180009f57  shr     rdx, 3
0x180009f5b  lea     rcx, [rdx+rdx*2]
0x180009f5f  shl     rcx, 2
0x180009f63  cmp     r9, rcx
0x180009f66  jz      short loc_180009F70
0x180009f68  xor     r9d, r9d
0x180009f6b  mov     [rsp+1090h+var_1050], r9d
0x180009f70  mov     r8, [r14]
0x180009f73  mov     rax, r12
0x180009f76  mov     ecx, r9d
0x180009f79  mul     rcx
0x180009f7c  mov     rcx, [r14+8]
0x180009f80  mov     rax, r12
0x180009f83  mov     r11, rdx
0x180009f86  sub     rcx, r8
0x180009f89  mul     rcx
0x180009f8c  shr     r11, 3
0x180009f90  shr     rdx, 3
0x180009f94  lea     rax, [rdx+rdx*2]
0x180009f98  lea     rdi, [r8+rax*4]
0x180009f9c  jmp     short loc_18000A00A
0x180009f9e  mov     eax, r11d
0x180009fa1  lea     r10, [rsp+1090h+var_1040]
0x180009fa6  lea     rcx, [rax+rax*2]
0x180009faa  lea     r10, [r10+rcx*4]
0x180009fae  cmp     rdx, r10
0x180009fb1  jz      short loc_180009FD9
0x180009fb3  mov     eax, [r8]
0x180009fb6  cmp     [rdx], eax
0x180009fb8  jnz     short loc_180009FC5
0x180009fba  movzx   eax, word ptr [r8+4]
0x180009fbf  cmp     [rdx+4], ax
0x180009fc3  jz      short loc_180009FCB
0x180009fc5  add     rdx, 0Ch
0x180009fc9  jmp     short loc_180009FAE
0x180009fcb  mov     eax, [r8+8]
0x180009fcf  add     [rdx+8], eax
0x180009fd2  mov     r9d, [rsp+1090h+var_1050]
0x180009fd7  jmp     short loc_18000A006
0x180009fd9  mov     eax, r9d
0x180009fdc  add     rax, 0Ch
0x180009fe0  cmp     rax, 1000h
0x180009fe6  ja      short loc_18000A006
0x180009fe8  movsd   xmm0, qword ptr [r8]
0x180009fed  add     r9d, 0Ch
0x180009ff1  movsd   qword ptr [r10], xmm0
0x180009ff6  inc     r11d
0x180009ff9  mov     eax, [r8+8]
0x180009ffd  mov     [r10+8], eax
0x18000a001  mov     [rsp+1090h+var_1050], r9d
0x18000a006  add     r8, 0Ch
0x18000a00a  lea     rdx, [rsp+1090h+var_1040]
0x18000a00f  cmp     r8, rdi
0x18000a012  jnz     short loc_180009F9E
0x18000a014  mov     eax, [rsp+1090h+var_104C]
0x18000a018  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000a01f  mov     [rsp+1090h+var_1060], 1
0x18000a027  mov     r8d, r9d
0x18000a02a  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000a02e  call    wil_details_NtUpdateWnfStateData
0x18000a033  mov     edi, eax
0x18000a035  cmp     edi, 0C0000001h
0x18000a03b  jnz     short loc_18000A04C
0x18000a03d  inc     esi
0x18000a03f  cmp     esi, 64h ; 'd'
0x18000a042  jge     short loc_18000A04C
0x18000a044  test    ebx, ebx
0x18000a046  jz      loc_180009EFB
0x18000a04c  test    ebx, ebx
0x18000a04e  cmovz   ebx, edi
0x18000a051  mov     eax, ebx
0x18000a053  mov     rcx, [rbp+0F90h+var_40]
0x18000a05a  xor     rcx, rsp; StackCookie
0x18000a05d  call    __security_check_cookie
0x18000a062  add     rsp, 1068h
0x18000a069  pop     r14
0x18000a06b  pop     r12
0x18000a06d  pop     rdi
0x18000a06e  pop     rsi
0x18000a06f  pop     rbx
0x18000a070  pop     rbp
0x18000a071  retn
```
