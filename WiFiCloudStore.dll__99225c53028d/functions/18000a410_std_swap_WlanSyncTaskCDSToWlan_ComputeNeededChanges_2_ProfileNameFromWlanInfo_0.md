# std::swap__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameFromWlanInfo_0_

- ea: `0x18000a410`
- end: `0x18000a5a1`
- name: `std::swap__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameFromWlanInfo_0_`
- size: `401`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b868`
- `0x18003b0b0`

## callees

- `0x180007f90`
- `0x1800097f4`
- `0x18000a410`
- `0x180025308`
- `0x18002a030`

## pseudocode

```c
__int64 __fastcall std::swap__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameFromWlanInfo_0_(
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // rdx
  __int64 v5; // rbx
  char v6; // r14
  int v7; // r15d
  __int128 v8; // xmm6
  unsigned __int64 v9; // rdx
  unsigned __int64 v10; // rdx
  __int64 v11; // xmm0_8
  int v12; // eax
  __m128i si128; // xmm0
  __int16 v15; // [rsp+20h] [rbp-60h] BYREF
  __int64 v16; // [rsp+22h] [rbp-5Eh]
  int v17; // [rsp+2Ah] [rbp-56h]
  __int16 v18; // [rsp+2Eh] [rbp-52h]
  __m128i v19; // [rsp+30h] [rbp-50h]
  __int64 v20; // [rsp+40h] [rbp-40h]
  __int128 v21; // [rsp+48h] [rbp-38h]
  char v22; // [rsp+58h] [rbp-28h]
  int v23; // [rsp+5Ch] [rbp-24h]

  std::wstring::wstring((__int64)&v15, a1);
  v5 = *(_QWORD *)(v4 + 32);
  v6 = *(_BYTE *)(v4 + 56);
  v7 = *(_DWORD *)(v4 + 60);
  v20 = v5;
  v22 = v6;
  v23 = v7;
  v8 = *(_OWORD *)(v4 + 40);
  v21 = v8;
  if ( v4 != a2 )
  {
    v9 = *(_QWORD *)(v4 + 24);
    if ( v9 > 7 )
      std::_Deallocate<16>(*(void **)a1, 2 * v9 + 2);
    *(_QWORD *)(a1 + 16) = 0;
    *(_WORD *)a1 = 0;
    *(_QWORD *)(a1 + 24) = 7;
    *(_OWORD *)a1 = *(_OWORD *)a2;
    *(_OWORD *)(a1 + 16) = *(_OWORD *)(a2 + 16);
    *(_QWORD *)(a2 + 16) = 0;
    *(_QWORD *)(a2 + 24) = 7;
    *(_WORD *)a2 = 0;
  }
  *(_QWORD *)(a1 + 32) = *(_QWORD *)(a2 + 32);
  *(_OWORD *)(a1 + 40) = *(_OWORD *)(a2 + 40);
  *(_BYTE *)(a1 + 56) = *(_BYTE *)(a2 + 56);
  *(_DWORD *)(a1 + 60) = *(_DWORD *)(a2 + 60);
  if ( (__int16 *)a2 != &v15 )
  {
    v10 = *(_QWORD *)(a2 + 24);
    if ( v10 > 7 )
      std::_Deallocate<16>(*(void **)a2, 2 * v10 + 2);
    v11 = v16;
    *(_WORD *)a2 = v15;
    v12 = v17;
    *(_QWORD *)(a2 + 16) = 0;
    *(_QWORD *)(a2 + 2) = v11;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    *(_DWORD *)(a2 + 10) = v12;
    *(_WORD *)(a2 + 14) = v18;
    *(__m128i *)(a2 + 16) = v19;
    v15 = 0;
    v19 = si128;
  }
  *(_QWORD *)(a2 + 32) = v5;
  *(_OWORD *)(a2 + 40) = v8;
  *(_BYTE *)(a2 + 56) = v6;
  *(_DWORD *)(a2 + 60) = v7;
  return std::wstring::~wstring((__int64)&v15);
}

```

## disassembly

```asm
0x18000a410  mov     [rsp-28h+arg_10], rbx
0x18000a415  mov     [rsp-28h+arg_18], rsi
0x18000a41a  push    rbp
0x18000a41b  push    rdi
0x18000a41c  push    r12
0x18000a41e  push    r14
0x18000a420  push    r15
0x18000a422  mov     rbp, rsp
0x18000a425  sub     rsp, 80h
0x18000a42c  movaps  [rsp+80h+var_10], xmm6
0x18000a431  mov     rax, cs:__security_cookie
0x18000a438  xor     rax, rsp
0x18000a43b  mov     [rbp+var_20], rax
0x18000a43f  mov     rdi, rdx
0x18000a442  mov     rsi, rcx
0x18000a445  mov     rdx, rcx
0x18000a448  lea     rcx, [rbp+var_60]
0x18000a44c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18000a451  mov     rbx, [rdx+20h]
0x18000a455  mov     r12d, 7
0x18000a45b  mov     r14b, [rdx+38h]
0x18000a45f  mov     r15d, [rdx+3Ch]
0x18000a463  mov     [rbp+var_40], rbx
0x18000a467  mov     [rbp+var_28], r14b
0x18000a46b  mov     [rbp+var_24], r15d
0x18000a46f  movups  xmm6, xmmword ptr [rdx+28h]
0x18000a473  movups  [rbp+var_38], xmm6
0x18000a477  cmp     rdx, rdi
0x18000a47a  jz      short loc_18000A4B3
0x18000a47c  mov     rdx, [rdx+18h]
0x18000a480  cmp     rdx, r12
0x18000a483  ja      loc_18000A577
0x18000a489  mov     qword ptr [rsi+10h], 0
0x18000a491  xor     eax, eax
0x18000a493  mov     [rsi], ax
0x18000a496  mov     [rsi+18h], r12
0x18000a49a  movups  xmm0, xmmword ptr [rdi]
0x18000a49d  movups  xmmword ptr [rsi], xmm0
0x18000a4a0  movups  xmm1, xmmword ptr [rdi+10h]
0x18000a4a4  movups  xmmword ptr [rsi+10h], xmm1
0x18000a4a8  mov     [rdi+10h], rax
0x18000a4ac  mov     [rdi+18h], r12
0x18000a4b0  mov     [rdi], ax
0x18000a4b3  mov     rax, [rdi+20h]
0x18000a4b7  mov     [rsi+20h], rax
0x18000a4bb  movups  xmm0, xmmword ptr [rdi+28h]
0x18000a4bf  movdqu  xmmword ptr [rsi+28h], xmm0
0x18000a4c4  mov     al, [rdi+38h]
0x18000a4c7  mov     [rsi+38h], al
0x18000a4ca  mov     eax, [rdi+3Ch]
0x18000a4cd  mov     [rsi+3Ch], eax
0x18000a4d0  lea     rax, [rbp+var_60]
0x18000a4d4  cmp     rdi, rax
0x18000a4d7  jz      short loc_18000A530
0x18000a4d9  mov     rdx, [rdi+18h]
0x18000a4dd  cmp     rdx, r12
0x18000a4e0  ja      loc_18000A58C
0x18000a4e6  movzx   eax, [rbp+var_60]
0x18000a4ea  movsd   xmm0, [rbp+var_5E]
0x18000a4ef  mov     [rdi], ax
0x18000a4f2  mov     eax, [rbp+var_56]
0x18000a4f5  mov     qword ptr [rdi+10h], 0
0x18000a4fd  movsd   qword ptr [rdi+2], xmm0
0x18000a502  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18000a50a  mov     [rdi+0Ah], eax
0x18000a50d  movzx   eax, [rbp+var_52]
0x18000a511  mov     [rdi+0Eh], ax
0x18000a515  mov     rax, qword ptr [rbp+var_50]
0x18000a519  mov     [rdi+10h], rax
0x18000a51d  mov     rax, qword ptr [rbp+var_50+8]
0x18000a521  mov     [rdi+18h], rax
0x18000a525  xor     eax, eax
0x18000a527  mov     [rbp+var_60], ax
0x18000a52b  movdqa  [rbp+var_50], xmm0
0x18000a530  lea     rcx, [rbp+var_60]
0x18000a534  mov     [rdi+20h], rbx
0x18000a538  movdqu  xmmword ptr [rdi+28h], xmm6
0x18000a53d  mov     [rdi+38h], r14b
0x18000a541  mov     [rdi+3Ch], r15d
0x18000a545  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000a54a  mov     rcx, [rbp+var_20]
0x18000a54e  xor     rcx, rsp; StackCookie
0x18000a551  call    __security_check_cookie
0x18000a556  lea     r11, [rsp+80h+var_s0]
0x18000a55e  mov     rbx, [r11+40h]
0x18000a562  mov     rsi, [r11+48h]
0x18000a566  movaps  xmm6, [rsp+80h+var_10]
0x18000a56b  mov     rsp, r11
0x18000a56e  pop     r15
0x18000a570  pop     r14
0x18000a572  pop     r12
0x18000a574  pop     rdi
0x18000a575  pop     rbp
0x18000a576  retn
0x18000a577  mov     rcx, [rsi]
0x18000a57a  lea     rdx, ds:2[rdx*2]
0x18000a582  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000a587  jmp     loc_18000A489
0x18000a58c  mov     rcx, [rdi]
0x18000a58f  lea     rdx, ds:2[rdx*2]
0x18000a597  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000a59c  jmp     loc_18000A4E6
```
