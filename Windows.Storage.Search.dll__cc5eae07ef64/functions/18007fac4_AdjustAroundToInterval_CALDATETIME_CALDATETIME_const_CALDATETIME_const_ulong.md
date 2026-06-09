# _AdjustAroundToInterval(CALDATETIME *,CALDATETIME const *,CALDATETIME const *,ulong)

- ea: `0x18007fac4`
- end: `0x18007fc50`
- name: `?_AdjustAroundToInterval@@YAXPEAUCALDATETIME@@PEBU1@1K@Z`
- size: `396`
- prototype: `void __fastcall(struct CALDATETIME *, const struct CALDATETIME *, const struct CALDATETIME *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800801f8`

## callees

- `0x180071dc0`
- `0x18007fac4`

## import_xrefs

- `api-ms-win-core-kernel32-private-l1-1-0!CompareCalendarDates` at `0x18007faff`
- `api-ms-win-core-kernel32-private-l1-1-0!CompareCalendarDates` at `0x18007fb22`
- `api-ms-win-core-kernel32-private-l1-1-0!CompareCalendarDates` at `0x18007fbcd`
- `api-ms-win-core-kernel32-private-l1-1-0!CompareCalendarDates` at `0x18007faff`
- `api-ms-win-core-kernel32-private-l1-1-0!CompareCalendarDates` at `0x18007fb22`
- `api-ms-win-core-kernel32-private-l1-1-0!CompareCalendarDates` at `0x18007fbcd`
- `api-ms-win-core-calendar-l1-1-0!AdjustCalendarDate` at `0x18007fb9b`
- `api-ms-win-core-calendar-l1-1-0!AdjustCalendarDate` at `0x18007fc13`
- `api-ms-win-core-calendar-l1-1-0!AdjustCalendarDate` at `0x18007fb9b`
- `api-ms-win-core-calendar-l1-1-0!AdjustCalendarDate` at `0x18007fc13`
- `api-ms-win-core-calendar-l1-1-0!GetCalendarSupportedDateRange` at `0x18007fb65`
- `api-ms-win-core-calendar-l1-1-0!GetCalendarSupportedDateRange` at `0x18007fb65`

## pseudocode

```c
void __fastcall _AdjustAroundToInterval(
        struct CALDATETIME *a1,
        const struct CALDATETIME *a2,
        const struct CALDATETIME *a3,
        unsigned int a4)
{
  __int128 v8; // xmm1
  __int64 v9; // xmm0_8
  __int64 v10; // xmm0_8
  __int128 v11; // xmm1
  int v12; // [rsp+20h] [rbp-60h] BYREF
  __int128 v13; // [rsp+28h] [rbp-58h] BYREF
  __int128 v14; // [rsp+38h] [rbp-48h]
  __int64 v15; // [rsp+48h] [rbp-38h]
  __int128 v16; // [rsp+50h] [rbp-30h] BYREF
  __int128 v17; // [rsp+60h] [rbp-20h]
  __int64 v18; // [rsp+70h] [rbp-10h]

  v12 = 0;
  if ( a2 && (unsigned int)CompareCalendarDates(a1, a2, &v12) && v12 < 0
    || a3 && (unsigned int)CompareCalendarDates(a3, a1, &v12) && v12 < 0 )
  {
    v15 = 0;
    v18 = 0;
    v13 = 0;
    v14 = 0;
    v16 = 0;
    v17 = 0;
    if ( (unsigned int)GetCalendarSupportedDateRange(a4, &v13, &v16) )
    {
      if ( !a3 )
      {
        *(_OWORD *)a1 = *(_OWORD *)a2;
        *((_OWORD *)a1 + 1) = *((_OWORD *)a2 + 1);
        *((_QWORD *)a1 + 4) = *((_QWORD *)a2 + 4);
        if ( (unsigned int)AdjustCalendarDate(a1, 1, 2) )
          return;
        v11 = v17;
        *(_OWORD *)a1 = v16;
        v10 = v18;
        *((_OWORD *)a1 + 1) = v11;
        goto LABEL_17;
      }
      *(_OWORD *)a1 = *(_OWORD *)a3;
      *((_OWORD *)a1 + 1) = *((_OWORD *)a3 + 1);
      *((_QWORD *)a1 + 4) = *((_QWORD *)a3 + 4);
      if ( !(unsigned int)AdjustCalendarDate(a1, 2, 0xFFFFFFFFLL) )
      {
        v8 = v14;
        *(_OWORD *)a1 = v13;
        v9 = v15;
        *((_OWORD *)a1 + 1) = v8;
        *((_QWORD *)a1 + 4) = v9;
      }
      if ( a2 && (unsigned int)CompareCalendarDates(a2, a1, &v12) && v12 > 0 )
      {
        *(_OWORD *)a1 = *(_OWORD *)a2;
        *((_OWORD *)a1 + 1) = *((_OWORD *)a2 + 1);
        v10 = *((_QWORD *)a2 + 4);
LABEL_17:
        *((_QWORD *)a1 + 4) = v10;
      }
    }
  }
}

```

## disassembly

```asm
0x18007fac4  push    rbp
0x18007fac6  push    rbx
0x18007fac7  push    rsi
0x18007fac8  push    rdi
0x18007fac9  push    r14
0x18007facb  mov     rbp, rsp
0x18007face  sub     rsp, 80h
0x18007fad5  mov     rax, cs:__security_cookie
0x18007fadc  xor     rax, rsp
0x18007fadf  mov     [rbp+var_8], rax
0x18007fae3  mov     [rbp+var_60], 0
0x18007faea  mov     r14d, r9d
0x18007faed  mov     rsi, r8
0x18007faf0  mov     rdi, rdx
0x18007faf3  mov     rbx, rcx
0x18007faf6  test    rdx, rdx
0x18007faf9  jz      short loc_18007FB0F
0x18007fafb  lea     r8, [rbp+var_60]
0x18007faff  call    cs:__imp_CompareCalendarDates
0x18007fb05  test    eax, eax
0x18007fb07  jz      short loc_18007FB0F
0x18007fb09  cmp     [rbp+var_60], 0
0x18007fb0d  jl      short loc_18007FB3A
0x18007fb0f  test    rsi, rsi
0x18007fb12  jz      loc_18007FC36
0x18007fb18  lea     r8, [rbp+var_60]
0x18007fb1c  mov     rdx, rbx
0x18007fb1f  mov     rcx, rsi
0x18007fb22  call    cs:__imp_CompareCalendarDates
0x18007fb28  test    eax, eax
0x18007fb2a  jz      loc_18007FC36
0x18007fb30  cmp     [rbp+var_60], 0
0x18007fb34  jge     loc_18007FC36
0x18007fb3a  xorps   xmm0, xmm0
0x18007fb3d  lea     r8, [rbp+var_30]
0x18007fb41  xor     eax, eax
0x18007fb43  lea     rdx, [rbp+var_58]
0x18007fb47  xorps   xmm1, xmm1
0x18007fb4a  mov     [rbp+var_38], rax
0x18007fb4e  mov     ecx, r14d
0x18007fb51  mov     [rbp+var_10], rax
0x18007fb55  movups  [rbp+var_58], xmm0
0x18007fb59  movups  [rbp+var_48], xmm0
0x18007fb5d  movups  [rbp+var_30], xmm1
0x18007fb61  movups  [rbp+var_20], xmm1
0x18007fb65  call    cs:__imp_GetCalendarSupportedDateRange
0x18007fb6b  test    eax, eax
0x18007fb6d  jz      loc_18007FC36
0x18007fb73  mov     rcx, rbx
0x18007fb76  test    rsi, rsi
0x18007fb79  jz      short loc_18007FBF2
0x18007fb7b  movups  xmm0, xmmword ptr [rsi]
0x18007fb7e  or      r8d, 0FFFFFFFFh
0x18007fb82  movups  xmmword ptr [rbx], xmm0
0x18007fb85  movups  xmm1, xmmword ptr [rsi+10h]
0x18007fb89  lea     edx, [r8+3]
0x18007fb8d  movups  xmmword ptr [rbx+10h], xmm1
0x18007fb91  movsd   xmm0, qword ptr [rsi+20h]
0x18007fb96  movsd   qword ptr [rbx+20h], xmm0
0x18007fb9b  call    cs:__imp_AdjustCalendarDate
0x18007fba1  test    eax, eax
0x18007fba3  jnz     short loc_18007FBBE
0x18007fba5  movups  xmm0, [rbp+var_58]
0x18007fba9  movups  xmm1, [rbp+var_48]
0x18007fbad  movups  xmmword ptr [rbx], xmm0
0x18007fbb0  movsd   xmm0, [rbp+var_38]
0x18007fbb5  movups  xmmword ptr [rbx+10h], xmm1
0x18007fbb9  movsd   qword ptr [rbx+20h], xmm0
0x18007fbbe  test    rdi, rdi
0x18007fbc1  jz      short loc_18007FC36
0x18007fbc3  lea     r8, [rbp+var_60]
0x18007fbc7  mov     rdx, rbx
0x18007fbca  mov     rcx, rdi
0x18007fbcd  call    cs:__imp_CompareCalendarDates
0x18007fbd3  test    eax, eax
0x18007fbd5  jz      short loc_18007FC36
0x18007fbd7  cmp     [rbp+var_60], 0
0x18007fbdb  jle     short loc_18007FC36
0x18007fbdd  movups  xmm0, xmmword ptr [rdi]
0x18007fbe0  movups  xmmword ptr [rbx], xmm0
0x18007fbe3  movups  xmm1, xmmword ptr [rdi+10h]
0x18007fbe7  movups  xmmword ptr [rbx+10h], xmm1
0x18007fbeb  movsd   xmm0, qword ptr [rdi+20h]
0x18007fbf0  jmp     short loc_18007FC31
0x18007fbf2  movups  xmm0, xmmword ptr [rdi]
0x18007fbf5  mov     edx, 1
0x18007fbfa  movups  xmmword ptr [rbx], xmm0
0x18007fbfd  movups  xmm1, xmmword ptr [rdi+10h]
0x18007fc01  lea     r8d, [rdx+1]
0x18007fc05  movups  xmmword ptr [rbx+10h], xmm1
0x18007fc09  movsd   xmm0, qword ptr [rdi+20h]
0x18007fc0e  movsd   qword ptr [rbx+20h], xmm0
0x18007fc13  call    cs:__imp_AdjustCalendarDate
0x18007fc19  test    eax, eax
0x18007fc1b  jnz     short loc_18007FC36
0x18007fc1d  movups  xmm0, [rbp+var_30]
0x18007fc21  movups  xmm1, [rbp+var_20]
0x18007fc25  movups  xmmword ptr [rbx], xmm0
0x18007fc28  movsd   xmm0, [rbp+var_10]
0x18007fc2d  movups  xmmword ptr [rbx+10h], xmm1
0x18007fc31  movsd   qword ptr [rbx+20h], xmm0
0x18007fc36  mov     rcx, [rbp+var_8]
0x18007fc3a  xor     rcx, rsp; StackCookie
0x18007fc3d  call    __security_check_cookie
0x18007fc42  add     rsp, 80h
0x18007fc49  pop     r14
0x18007fc4b  pop     rdi
0x18007fc4c  pop     rsi
0x18007fc4d  pop     rbx
0x18007fc4e  pop     rbp
0x18007fc4f  retn
```
