# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x14000ed68`
- end: `0x14000ef32`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140003ea0`

## callees

- `0x140002f40`
- `0x140003ab8`
- `0x14000ed68`
- `0x14000f0f0`
- `0x14000f168`
- `0x140018460`

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
0x14000ed68  push    rbp
0x14000ed6a  push    rbx
0x14000ed6b  push    rsi
0x14000ed6c  push    rdi
0x14000ed6d  push    r12
0x14000ed6f  push    r14
0x14000ed71  lea     rbp, [rsp-0F68h]
0x14000ed79  mov     eax, 1068h
0x14000ed7e  call    _alloca_probe
0x14000ed83  sub     rsp, rax
0x14000ed86  mov     rax, cs:__security_cookie
0x14000ed8d  xor     rax, rsp
0x14000ed90  mov     [rbp+0F90h+var_40], rax
0x14000ed97  mov     rax, [rcx+8]
0x14000ed9b  xor     ebx, ebx
0x14000ed9d  sub     rax, [rcx]
0x14000eda0  xor     edi, edi
0x14000eda2  mov     r14, rcx
0x14000eda5  cmp     rax, 0Ch
0x14000eda9  jb      loc_14000EF0C
0x14000edaf  xor     esi, esi
0x14000edb1  mov     r12, 0AAAAAAAAAAAAAAABh
0x14000edbb  xor     edx, edx; Val
0x14000edbd  lea     rcx, [rsp+1090h+var_1040]; void *
0x14000edc2  mov     r8d, 1000h; Size
0x14000edc8  call    memset_0
0x14000edcd  lea     rax, [rsp+1090h+var_1050]
0x14000edd2  mov     [rsp+1090h+var_1050], 1000h
0x14000edda  mov     [rsp+1090h+var_1068], rax
0x14000eddf  lea     r9, [rsp+1090h+var_104C]
0x14000ede4  lea     rax, [rsp+1090h+var_1040]
0x14000ede9  mov     [rsp+1090h+var_104C], 0
0x14000edf1  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000edf8  mov     [rsp+1090h+var_1070], rax
0x14000edfd  call    wil_details_NtQueryWnfStateData
0x14000ee02  mov     ebx, eax
0x14000ee04  test    eax, eax
0x14000ee06  jnz     loc_14000EEF5
0x14000ee0c  mov     r9d, [rsp+1090h+var_1050]
0x14000ee11  mov     rax, r12
0x14000ee14  mul     r9
0x14000ee17  shr     rdx, 3
0x14000ee1b  lea     rcx, [rdx+rdx*2]
0x14000ee1f  shl     rcx, 2
0x14000ee23  cmp     r9, rcx
0x14000ee26  jz      short loc_14000EE30
0x14000ee28  xor     r9d, r9d
0x14000ee2b  mov     [rsp+1090h+var_1050], r9d
0x14000ee30  mov     r8, [r14]
0x14000ee33  mov     rax, r12
0x14000ee36  mov     ecx, r9d
0x14000ee39  mul     rcx
0x14000ee3c  mov     rcx, [r14+8]
0x14000ee40  mov     rax, r12
0x14000ee43  mov     r11, rdx
0x14000ee46  sub     rcx, r8
0x14000ee49  mul     rcx
0x14000ee4c  shr     r11, 3
0x14000ee50  shr     rdx, 3
0x14000ee54  lea     rax, [rdx+rdx*2]
0x14000ee58  lea     rdi, [r8+rax*4]
0x14000ee5c  jmp     short loc_14000EECA
0x14000ee5e  mov     eax, r11d
0x14000ee61  lea     r10, [rsp+1090h+var_1040]
0x14000ee66  lea     rcx, [rax+rax*2]
0x14000ee6a  lea     r10, [r10+rcx*4]
0x14000ee6e  cmp     rdx, r10
0x14000ee71  jz      short loc_14000EE99
0x14000ee73  mov     eax, [r8]
0x14000ee76  cmp     [rdx], eax
0x14000ee78  jnz     short loc_14000EE85
0x14000ee7a  movzx   eax, word ptr [r8+4]
0x14000ee7f  cmp     [rdx+4], ax
0x14000ee83  jz      short loc_14000EE8B
0x14000ee85  add     rdx, 0Ch
0x14000ee89  jmp     short loc_14000EE6E
0x14000ee8b  mov     eax, [r8+8]
0x14000ee8f  add     [rdx+8], eax
0x14000ee92  mov     r9d, [rsp+1090h+var_1050]
0x14000ee97  jmp     short loc_14000EEC6
0x14000ee99  mov     eax, r9d
0x14000ee9c  add     rax, 0Ch
0x14000eea0  cmp     rax, 1000h
0x14000eea6  ja      short loc_14000EEC6
0x14000eea8  movsd   xmm0, qword ptr [r8]
0x14000eead  add     r9d, 0Ch
0x14000eeb1  movsd   qword ptr [r10], xmm0
0x14000eeb6  inc     r11d
0x14000eeb9  mov     eax, [r8+8]
0x14000eebd  mov     [r10+8], eax
0x14000eec1  mov     [rsp+1090h+var_1050], r9d
0x14000eec6  add     r8, 0Ch
0x14000eeca  lea     rdx, [rsp+1090h+var_1040]
0x14000eecf  cmp     r8, rdi
0x14000eed2  jnz     short loc_14000EE5E
0x14000eed4  mov     eax, [rsp+1090h+var_104C]
0x14000eed8  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000eedf  mov     [rsp+1090h+var_1060], 1
0x14000eee7  mov     r8d, r9d
0x14000eeea  mov     dword ptr [rsp+1090h+var_1068], eax
0x14000eeee  call    wil_details_NtUpdateWnfStateData
0x14000eef3  mov     edi, eax
0x14000eef5  cmp     edi, 0C0000001h
0x14000eefb  jnz     short loc_14000EF0C
0x14000eefd  inc     esi
0x14000eeff  cmp     esi, 64h ; 'd'
0x14000ef02  jge     short loc_14000EF0C
0x14000ef04  test    ebx, ebx
0x14000ef06  jz      loc_14000EDBB
0x14000ef0c  test    ebx, ebx
0x14000ef0e  cmovz   ebx, edi
0x14000ef11  mov     eax, ebx
0x14000ef13  mov     rcx, [rbp+0F90h+var_40]
0x14000ef1a  xor     rcx, rsp; StackCookie
0x14000ef1d  call    __security_check_cookie
0x14000ef22  add     rsp, 1068h
0x14000ef29  pop     r14
0x14000ef2b  pop     r12
0x14000ef2d  pop     rdi
0x14000ef2e  pop     rsi
0x14000ef2f  pop     rbx
0x14000ef30  pop     rbp
0x14000ef31  retn
```
