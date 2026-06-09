# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x14001bd0c`
- end: `0x14001bed6`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140004520`

## callees

- `0x140003620`
- `0x1400042c4`
- `0x14001bd0c`
- `0x14001cc5c`
- `0x14001ccd4`
- `0x14001e000`

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
0x14001bd0c  push    rbp
0x14001bd0e  push    rbx
0x14001bd0f  push    rsi
0x14001bd10  push    rdi
0x14001bd11  push    r12
0x14001bd13  push    r14
0x14001bd15  lea     rbp, [rsp-0F68h]
0x14001bd1d  mov     eax, 1068h
0x14001bd22  call    _alloca_probe
0x14001bd27  sub     rsp, rax
0x14001bd2a  mov     rax, cs:__security_cookie
0x14001bd31  xor     rax, rsp
0x14001bd34  mov     [rbp+0F90h+var_40], rax
0x14001bd3b  mov     rax, [rcx+8]
0x14001bd3f  xor     ebx, ebx
0x14001bd41  sub     rax, [rcx]
0x14001bd44  xor     edi, edi
0x14001bd46  mov     r14, rcx
0x14001bd49  cmp     rax, 0Ch
0x14001bd4d  jb      loc_14001BEB0
0x14001bd53  xor     esi, esi
0x14001bd55  mov     r12, 0AAAAAAAAAAAAAAABh
0x14001bd5f  xor     edx, edx; Val
0x14001bd61  lea     rcx, [rsp+1090h+var_1040]; void *
0x14001bd66  mov     r8d, 1000h; Size
0x14001bd6c  call    memset_0
0x14001bd71  lea     rax, [rsp+1090h+var_1050]
0x14001bd76  mov     [rsp+1090h+var_1050], 1000h
0x14001bd7e  mov     [rsp+1090h+var_1068], rax
0x14001bd83  lea     r9, [rsp+1090h+var_104C]
0x14001bd88  lea     rax, [rsp+1090h+var_1040]
0x14001bd8d  mov     [rsp+1090h+var_104C], 0
0x14001bd95  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14001bd9c  mov     [rsp+1090h+var_1070], rax
0x14001bda1  call    wil_details_NtQueryWnfStateData
0x14001bda6  mov     ebx, eax
0x14001bda8  test    eax, eax
0x14001bdaa  jnz     loc_14001BE99
0x14001bdb0  mov     r9d, [rsp+1090h+var_1050]
0x14001bdb5  mov     rax, r12
0x14001bdb8  mul     r9
0x14001bdbb  shr     rdx, 3
0x14001bdbf  lea     rcx, [rdx+rdx*2]
0x14001bdc3  shl     rcx, 2
0x14001bdc7  cmp     r9, rcx
0x14001bdca  jz      short loc_14001BDD4
0x14001bdcc  xor     r9d, r9d
0x14001bdcf  mov     [rsp+1090h+var_1050], r9d
0x14001bdd4  mov     r8, [r14]
0x14001bdd7  mov     rax, r12
0x14001bdda  mov     ecx, r9d
0x14001bddd  mul     rcx
0x14001bde0  mov     rcx, [r14+8]
0x14001bde4  mov     rax, r12
0x14001bde7  mov     r11, rdx
0x14001bdea  sub     rcx, r8
0x14001bded  mul     rcx
0x14001bdf0  shr     r11, 3
0x14001bdf4  shr     rdx, 3
0x14001bdf8  lea     rax, [rdx+rdx*2]
0x14001bdfc  lea     rdi, [r8+rax*4]
0x14001be00  jmp     short loc_14001BE6E
0x14001be02  mov     eax, r11d
0x14001be05  lea     r10, [rsp+1090h+var_1040]
0x14001be0a  lea     rcx, [rax+rax*2]
0x14001be0e  lea     r10, [r10+rcx*4]
0x14001be12  cmp     rdx, r10
0x14001be15  jz      short loc_14001BE3D
0x14001be17  mov     eax, [r8]
0x14001be1a  cmp     [rdx], eax
0x14001be1c  jnz     short loc_14001BE29
0x14001be1e  movzx   eax, word ptr [r8+4]
0x14001be23  cmp     [rdx+4], ax
0x14001be27  jz      short loc_14001BE2F
0x14001be29  add     rdx, 0Ch
0x14001be2d  jmp     short loc_14001BE12
0x14001be2f  mov     eax, [r8+8]
0x14001be33  add     [rdx+8], eax
0x14001be36  mov     r9d, [rsp+1090h+var_1050]
0x14001be3b  jmp     short loc_14001BE6A
0x14001be3d  mov     eax, r9d
0x14001be40  add     rax, 0Ch
0x14001be44  cmp     rax, 1000h
0x14001be4a  ja      short loc_14001BE6A
0x14001be4c  movsd   xmm0, qword ptr [r8]
0x14001be51  add     r9d, 0Ch
0x14001be55  movsd   qword ptr [r10], xmm0
0x14001be5a  inc     r11d
0x14001be5d  mov     eax, [r8+8]
0x14001be61  mov     [r10+8], eax
0x14001be65  mov     [rsp+1090h+var_1050], r9d
0x14001be6a  add     r8, 0Ch
0x14001be6e  lea     rdx, [rsp+1090h+var_1040]
0x14001be73  cmp     r8, rdi
0x14001be76  jnz     short loc_14001BE02
0x14001be78  mov     eax, [rsp+1090h+var_104C]
0x14001be7c  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14001be83  mov     [rsp+1090h+var_1060], 1
0x14001be8b  mov     r8d, r9d
0x14001be8e  mov     dword ptr [rsp+1090h+var_1068], eax
0x14001be92  call    wil_details_NtUpdateWnfStateData
0x14001be97  mov     edi, eax
0x14001be99  cmp     edi, 0C0000001h
0x14001be9f  jnz     short loc_14001BEB0
0x14001bea1  inc     esi
0x14001bea3  cmp     esi, 64h ; 'd'
0x14001bea6  jge     short loc_14001BEB0
0x14001bea8  test    ebx, ebx
0x14001beaa  jz      loc_14001BD5F
0x14001beb0  test    ebx, ebx
0x14001beb2  cmovz   ebx, edi
0x14001beb5  mov     eax, ebx
0x14001beb7  mov     rcx, [rbp+0F90h+var_40]
0x14001bebe  xor     rcx, rsp; StackCookie
0x14001bec1  call    __security_check_cookie
0x14001bec6  add     rsp, 1068h
0x14001becd  pop     r14
0x14001becf  pop     r12
0x14001bed1  pop     rdi
0x14001bed2  pop     rsi
0x14001bed3  pop     rbx
0x14001bed4  pop     rbp
0x14001bed5  retn
```
