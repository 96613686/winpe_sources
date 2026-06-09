# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x140009754`
- end: `0x14000991e`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1400037a0`

## callees

- `0x140001caf`
- `0x140009754`
- `0x140009c0c`
- `0x140009c84`
- `0x14001edc0`
- `0x14001ee50`

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
0x140009754  push    rbp
0x140009756  push    rbx
0x140009757  push    rsi
0x140009758  push    rdi
0x140009759  push    r12
0x14000975b  push    r14
0x14000975d  lea     rbp, [rsp-0F68h]
0x140009765  mov     eax, 1068h
0x14000976a  call    _alloca_probe
0x14000976f  sub     rsp, rax
0x140009772  mov     rax, cs:__security_cookie
0x140009779  xor     rax, rsp
0x14000977c  mov     [rbp+0F90h+var_40], rax
0x140009783  mov     rax, [rcx+8]
0x140009787  xor     ebx, ebx
0x140009789  sub     rax, [rcx]
0x14000978c  xor     edi, edi
0x14000978e  mov     r14, rcx
0x140009791  cmp     rax, 0Ch
0x140009795  jb      loc_1400098F8
0x14000979b  xor     esi, esi
0x14000979d  mov     r12, 0AAAAAAAAAAAAAAABh
0x1400097a7  xor     edx, edx; Val
0x1400097a9  lea     rcx, [rsp+1090h+var_1040]; void *
0x1400097ae  mov     r8d, 1000h; Size
0x1400097b4  call    memset_0
0x1400097b9  lea     rax, [rsp+1090h+var_1050]
0x1400097be  mov     [rsp+1090h+var_1050], 1000h
0x1400097c6  mov     [rsp+1090h+var_1068], rax
0x1400097cb  lea     r9, [rsp+1090h+var_104C]
0x1400097d0  lea     rax, [rsp+1090h+var_1040]
0x1400097d5  mov     [rsp+1090h+var_104C], 0
0x1400097dd  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1400097e4  mov     [rsp+1090h+var_1070], rax
0x1400097e9  call    wil_details_NtQueryWnfStateData
0x1400097ee  mov     ebx, eax
0x1400097f0  test    eax, eax
0x1400097f2  jnz     loc_1400098E1
0x1400097f8  mov     r9d, [rsp+1090h+var_1050]
0x1400097fd  mov     rax, r12
0x140009800  mul     r9
0x140009803  shr     rdx, 3
0x140009807  lea     rcx, [rdx+rdx*2]
0x14000980b  shl     rcx, 2
0x14000980f  cmp     r9, rcx
0x140009812  jz      short loc_14000981C
0x140009814  xor     r9d, r9d
0x140009817  mov     [rsp+1090h+var_1050], r9d
0x14000981c  mov     r8, [r14]
0x14000981f  mov     rax, r12
0x140009822  mov     ecx, r9d
0x140009825  mul     rcx
0x140009828  mov     rcx, [r14+8]
0x14000982c  mov     rax, r12
0x14000982f  mov     r11, rdx
0x140009832  sub     rcx, r8
0x140009835  mul     rcx
0x140009838  shr     r11, 3
0x14000983c  shr     rdx, 3
0x140009840  lea     rax, [rdx+rdx*2]
0x140009844  lea     rdi, [r8+rax*4]
0x140009848  jmp     short loc_1400098B6
0x14000984a  mov     eax, r11d
0x14000984d  lea     r10, [rsp+1090h+var_1040]
0x140009852  lea     rcx, [rax+rax*2]
0x140009856  lea     r10, [r10+rcx*4]
0x14000985a  cmp     rdx, r10
0x14000985d  jz      short loc_140009885
0x14000985f  mov     eax, [r8]
0x140009862  cmp     [rdx], eax
0x140009864  jnz     short loc_140009871
0x140009866  movzx   eax, word ptr [r8+4]
0x14000986b  cmp     [rdx+4], ax
0x14000986f  jz      short loc_140009877
0x140009871  add     rdx, 0Ch
0x140009875  jmp     short loc_14000985A
0x140009877  mov     eax, [r8+8]
0x14000987b  add     [rdx+8], eax
0x14000987e  mov     r9d, [rsp+1090h+var_1050]
0x140009883  jmp     short loc_1400098B2
0x140009885  mov     eax, r9d
0x140009888  add     rax, 0Ch
0x14000988c  cmp     rax, 1000h
0x140009892  ja      short loc_1400098B2
0x140009894  movsd   xmm0, qword ptr [r8]
0x140009899  add     r9d, 0Ch
0x14000989d  movsd   qword ptr [r10], xmm0
0x1400098a2  inc     r11d
0x1400098a5  mov     eax, [r8+8]
0x1400098a9  mov     [r10+8], eax
0x1400098ad  mov     [rsp+1090h+var_1050], r9d
0x1400098b2  add     r8, 0Ch
0x1400098b6  lea     rdx, [rsp+1090h+var_1040]
0x1400098bb  cmp     r8, rdi
0x1400098be  jnz     short loc_14000984A
0x1400098c0  mov     eax, [rsp+1090h+var_104C]
0x1400098c4  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1400098cb  mov     [rsp+1090h+var_1060], 1
0x1400098d3  mov     r8d, r9d
0x1400098d6  mov     dword ptr [rsp+1090h+var_1068], eax
0x1400098da  call    wil_details_NtUpdateWnfStateData
0x1400098df  mov     edi, eax
0x1400098e1  cmp     edi, 0C0000001h
0x1400098e7  jnz     short loc_1400098F8
0x1400098e9  inc     esi
0x1400098eb  cmp     esi, 64h ; 'd'
0x1400098ee  jge     short loc_1400098F8
0x1400098f0  test    ebx, ebx
0x1400098f2  jz      loc_1400097A7
0x1400098f8  test    ebx, ebx
0x1400098fa  cmovz   ebx, edi
0x1400098fd  mov     eax, ebx
0x1400098ff  mov     rcx, [rbp+0F90h+var_40]
0x140009906  xor     rcx, rsp; StackCookie
0x140009909  call    __security_check_cookie
0x14000990e  add     rsp, 1068h
0x140009915  pop     r14
0x140009917  pop     r12
0x140009919  pop     rdi
0x14000991a  pop     rsi
0x14000991b  pop     rbx
0x14000991c  pop     rbp
0x14000991d  retn
```
