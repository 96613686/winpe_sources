# RtdspBuildKeyString

- ea: `0x180004090`
- end: `0x18000447e`
- name: `RtdspBuildKeyString`
- size: `1006`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003f78`

## callees

- `0x180004090`
- `0x180004484`

## import_xrefs

- `RPCRT4!UuidToStringW` at `0x1800040e2`
- `RPCRT4!UuidToStringW` at `0x1800040e2`
- `RPCRT4!RpcStringFreeW` at `0x180004202`
- `RPCRT4!RpcStringFreeW` at `0x180004202`

## string_xrefs

- `0x180004135`: `Software\Microsoft\Windows\CurrentVersion\NetworkServiceTriggers\Triggers\`

## pseudocode

```c
__int64 __fastcall RtdspBuildKeyString(__int64 a1, const wchar_t *a2, _WORD *a3, size_t a4, _QWORD *a5)
{
  RPC_STATUS v8; // eax
  int v9; // r13d
  unsigned __int64 v10; // rax
  __int64 v11; // rax
  const wchar_t *v12; // rdx
  __int64 v13; // rcx
  size_t v14; // r8
  _WORD *v15; // r9
  __int64 v16; // r10
  size_t v17; // rdx
  wchar_t *v18; // rcx
  size_t v20; // r10
  wchar_t *v21; // rbx
  size_t v22; // rcx
  STRSAFE_LPWSTR v23; // rax
  size_t v24; // rbp
  size_t v25; // r11
  wchar_t *v26; // r15
  wchar_t *v27; // r14
  const wchar_t *v28; // rcx
  size_t v29; // r8
  wchar_t *v30; // rdx
  __int64 v31; // r9
  __int64 v32; // rax
  STRSAFE_LPWSTR v33; // rcx
  DWORD v34; // [rsp+28h] [rbp-60h]
  DWORD v35; // [rsp+28h] [rbp-60h]
  STRSAFE_LPWSTR ppszDestEnd; // [rsp+30h] [rbp-58h] BYREF
  __int64 v37; // [rsp+38h] [rbp-50h]
  STRSAFE_LPWSTR v38; // [rsp+40h] [rbp-48h] BYREF
  size_t cchDest; // [rsp+90h] [rbp+8h] BYREF
  _WORD *v40; // [rsp+A0h] [rbp+18h]
  RPC_WSTR String; // [rsp+A8h] [rbp+20h] BYREF

  v40 = a3;
  cchDest = a4;
  ppszDestEnd = 0;
  v38 = 0;
  String = 0;
  v8 = UuidToStringW(&RPC_INTERFACE_EVENT_GUID, &String);
  v9 = v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
    goto LABEL_17;
  }
  v10 = 113;
  if ( a2 )
  {
    v11 = -1;
    do
      ++v11;
    while ( a2[v11] );
    v10 = v11 + 114;
  }
  if ( v10 >= a4 )
  {
    if ( a5 )
      *a5 = v10 + 1;
    v9 = -2147024774;
    goto LABEL_17;
  }
  if ( !a4 )
  {
    v9 = -2147024809;
    goto LABEL_17;
  }
  if ( a4 > 0x7FFFFFFF )
  {
    v9 = -2147024809;
    *a3 = 0;
    goto LABEL_17;
  }
  v12 = L"Software\\Microsoft\\Windows\\CurrentVersion\\NetworkServiceTriggers\\Triggers\\";
  v37 = 2147483646;
  v13 = 2147483646;
  v14 = a4;
  v15 = a3;
  v9 = 0;
  v16 = 0;
  do
  {
    if ( !v13 || !*v12 )
    {
      *v15 = 0;
      v17 = a4 - v16;
      v18 = &a3[v16];
      goto LABEL_16;
    }
    *v15++ = *v12++;
    --v13;
    ++v16;
    --v14;
  }
  while ( v14 );
  *(v15 - 1) = 0;
  v9 = -2147024774;
  v17 = a4 & 0x7FFFFFFFFFFFFFFFLL;
  if ( (a4 & 0x7FFFFFFFFFFFFFFFLL) != 0 )
  {
    v18 = a3;
    *a3 = 0;
  }
  else
  {
    v17 = a4 - (v16 - 1);
    v18 = &a3[v16 - 1];
  }
LABEL_16:
  ppszDestEnd = v18;
  cchDest = v17;
  if ( v9 >= 0 )
  {
    v9 = StringCchCatExW(v18, v17, String, &ppszDestEnd, &cchDest, v34);
    if ( v9 >= 0 )
    {
      if ( a2 )
      {
        v20 = cchDest;
        if ( cchDest - 1 > 0x7FFFFFFE )
        {
LABEL_51:
          v9 = -2147024809;
          goto LABEL_17;
        }
        v21 = ppszDestEnd;
        v22 = cchDest;
        v23 = ppszDestEnd;
        do
        {
          if ( !*v23 )
            break;
          ++v23;
          --v22;
        }
        while ( v22 );
        v9 = -2147024809;
        if ( v22 )
        {
          v24 = cchDest - v22;
          v25 = v22;
          v26 = &ppszDestEnd[cchDest - v22];
          v9 = 0;
          v27 = v26;
          if ( v22 <= 1 )
          {
            if ( asc_18000E508[0] )
            {
              if ( ppszDestEnd )
LABEL_32:
                v9 = -2147024774;
              else
                v9 = -2147024809;
              if ( (v20 & 0x7FFFFFFFFFFFFFFFLL) != 0 )
              {
                v27 = &v21[v24];
                v25 = (v20 & 0x7FFFFFFFFFFFFFFFLL) - v24;
                *v26 = 0;
              }
              if ( v9 != -2147024774 )
                goto LABEL_42;
            }
          }
          else
          {
            v28 = L"\\";
            v29 = v25;
            v30 = &ppszDestEnd[v24];
            v31 = 0;
            v32 = 2147483646;
            while ( v32 && *v28 )
            {
              *v30++ = *v28++;
              v32 = v37 - 1;
              ++v31;
              --v37;
              if ( !--v29 )
              {
                *(v30 - 1) = 0;
                v27 = &v26[v31 - 1];
                v25 -= v31 - 1;
                goto LABEL_32;
              }
            }
            v27 = &v26[v31];
            *v30 = 0;
            v25 -= v31;
          }
          v21 = v27;
          cchDest = v25;
          v20 = v25;
LABEL_42:
          if ( v9 >= 0 )
          {
            v9 = StringCchCatExW(v21, v20, a2, &v38, &cchDest, v35);
            if ( v9 >= 0 )
            {
              v33 = v38;
              if ( v38 - v40 > a4 )
                v33 = &v40[a4];
              while ( v21 != v33 )
              {
                if ( *v21 == 1 )
                  goto LABEL_51;
                if ( *v21 == 92 )
                  *v21 = 1;
                ++v21;
              }
            }
          }
        }
      }
    }
  }
LABEL_17:
  if ( String )
    RpcStringFreeW(&String);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180004090  mov     rax, rsp
0x180004093  mov     [rax+18h], r8
0x180004097  mov     [rax+8], rcx
0x18000409b  push    r13
0x18000409d  sub     rsp, 80h
0x1800040a4  mov     [rax+10h], rbx
0x1800040a8  lea     rcx, RPC_INTERFACE_EVENT_GUID; Uuid
0x1800040af  mov     [rax-10h], rbp
0x1800040b3  xor     ebp, ebp
0x1800040b5  mov     [rax-18h], rsi
0x1800040b9  mov     [rax-20h], rdi
0x1800040bd  mov     rdi, rdx
0x1800040c0  mov     [rax-28h], r12
0x1800040c4  lea     rdx, [rax+20h]; StringUuid
0x1800040c8  mov     [rax-30h], r14
0x1800040cc  mov     r12, r9
0x1800040cf  mov     r14, r8
0x1800040d2  mov     [rax+8], r9
0x1800040d6  mov     [rax-58h], rbp
0x1800040da  mov     [rax-48h], rbp
0x1800040de  mov     [rax+20h], rbp
0x1800040e2  call    cs:__imp_UuidToStringW
0x1800040e8  mov     r13d, eax
0x1800040eb  test    eax, eax
0x1800040ed  jnz     loc_180004418
0x1800040f3  mov     eax, 71h ; 'q'
0x1800040f8  test    rdi, rdi
0x1800040fb  jz      short loc_180004111
0x1800040fd  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180004104  inc     rax
0x180004107  cmp     [rdi+rax*2], bp
0x18000410b  jnz     short loc_180004104
0x18000410d  add     rax, 72h ; 'r'
0x180004111  cmp     rax, r12
0x180004114  jnb     loc_18000432B
0x18000411a  test    r12, r12
0x18000411d  jz      loc_180004400
0x180004123  cmp     r12, 7FFFFFFFh
0x18000412a  ja      loc_18000442E
0x180004130  mov     ebx, 7FFFFFFEh
0x180004135  lea     rdx, RTDS_TRIGGER_KEY; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000413c  mov     [rsp+88h+var_50], rbx
0x180004141  mov     ecx, ebx
0x180004143  mov     r8, r12
0x180004146  mov     r9, r14
0x180004149  mov     r13d, ebp
0x18000414c  mov     r10, rbp
0x18000414f  nop
0x180004150  test    rcx, rcx
0x180004153  jz      short loc_1800041A4
0x180004155  movzx   eax, word ptr [rdx]
0x180004158  test    ax, ax
0x18000415b  jz      short loc_18000419F
0x18000415d  mov     [r9], ax
0x180004161  add     rdx, 2
0x180004165  add     r9, 2
0x180004169  dec     rcx
0x18000416c  inc     r10
0x18000416f  sub     r8, 1
0x180004173  jnz     short loc_180004150
0x180004175  mov     rsi, 7FFFFFFFFFFFFFFFh
0x18000417f  mov     [r9-2], bp
0x180004184  mov     rdx, r12
0x180004187  mov     r13d, 8007007Ah
0x18000418d  and     rdx, rsi
0x180004190  jbe     loc_180004436
0x180004196  mov     rcx, r14
0x180004199  mov     [r14], bp
0x18000419d  jmp     short loc_1800041BC
0x18000419f  test    r8, r8
0x1800041a2  jz      short loc_180004175
0x1800041a4  mov     rdx, r12
0x1800041a7  mov     [r9], bp
0x1800041ab  sub     rdx, r10; cchDest
0x1800041ae  lea     rcx, [r14+r10*2]; pszDest
0x1800041b2  mov     rsi, 7FFFFFFFFFFFFFFFh
0x1800041bc  mov     [rsp+88h+ppszDestEnd], rcx
0x1800041c1  mov     [rsp+88h+cchDest], rdx
0x1800041c9  test    r13d, r13d
0x1800041cc  jns     short loc_180004215
0x1800041ce  cmp     [rsp+88h+String], 0
0x1800041d7  mov     r14, [rsp+88h+var_30]
0x1800041dc  mov     r12, [rsp+88h+var_28]
0x1800041e1  mov     rdi, [rsp+88h+var_20]
0x1800041e6  mov     rsi, [rsp+88h+var_18]
0x1800041eb  mov     rbp, [rsp+88h+var_10]
0x1800041f0  mov     rbx, [rsp+88h+arg_8]
0x1800041f8  jz      short loc_180004208
0x1800041fa  lea     rcx, [rsp+88h+String]; String
0x180004202  call    cs:__imp_RpcStringFreeW
0x180004208  mov     eax, r13d
0x18000420b  add     rsp, 80h
0x180004212  pop     r13
0x180004214  retn
0x180004215  mov     r8, [rsp+88h+String]; pszSrc
0x18000421d  lea     rax, [rsp+88h+cchDest]
0x180004225  lea     r9, [rsp+88h+ppszDestEnd]; ppszDestEnd
0x18000422a  mov     [rsp+88h+pcchRemaining], rax; pcchRemaining
0x18000422f  call    StringCchCatExW
0x180004234  mov     r13d, eax
0x180004237  test    eax, eax
0x180004239  js      short loc_1800041CE
0x18000423b  test    rdi, rdi
0x18000423e  jz      short loc_1800041CE
0x180004240  mov     r10, [rsp+88h+cchDest]
0x180004248  lea     rax, [r10-1]
0x18000424c  cmp     rax, rbx
0x18000424f  ja      loc_1800043E2
0x180004255  mov     rbx, [rsp+88h+ppszDestEnd]
0x18000425a  mov     rcx, r10
0x18000425d  mov     rax, rbx
0x180004260  cmp     [rax], bp
0x180004263  jnz     loc_1800043ED
0x180004269  test    rcx, rcx
0x18000426c  mov     r13d, 80070057h
0x180004272  cmovnz  r13d, ebp
0x180004276  jz      loc_1800041CE
0x18000427c  mov     rbp, r10
0x18000427f  sub     rbp, rcx
0x180004282  test    rcx, rcx
0x180004285  jz      loc_1800041CE
0x18000428b  mov     r11, r10
0x18000428e  mov     [rsp+88h+var_38], r15
0x180004293  sub     r11, rbp
0x180004296  lea     r15, [rbx+rbp*2]
0x18000429a  xor     r13d, r13d
0x18000429d  mov     r14, r15
0x1800042a0  cmp     r11, 1
0x1800042a4  jbe     loc_180004449
0x1800042aa  lea     rcx, asc_18000E508; "\\"
0x1800042b1  mov     r8, r11
0x1800042b4  mov     rdx, r15
0x1800042b7  xor     r9d, r9d
0x1800042ba  mov     eax, 7FFFFFFEh
0x1800042bf  nop
0x1800042c0  test    rax, rax
0x1800042c3  jz      loc_18000434E
0x1800042c9  movzx   eax, word ptr [rcx]
0x1800042cc  test    ax, ax
0x1800042cf  jz      short loc_180004349
0x1800042d1  mov     [rdx], ax
0x1800042d4  add     rcx, 2
0x1800042d8  mov     rax, [rsp+88h+var_50]
0x1800042dd  add     rdx, 2
0x1800042e1  dec     rax
0x1800042e4  inc     r9
0x1800042e7  mov     [rsp+88h+var_50], rax
0x1800042ec  sub     r8, 1
0x1800042f0  jnz     short loc_1800042C0
0x1800042f2  lea     rcx, [r9-1]
0x1800042f6  xor     eax, eax
0x1800042f8  mov     [rdx-2], ax
0x1800042fc  lea     r14, [r15+rcx*2]
0x180004300  sub     r11, rcx
0x180004303  mov     r13d, 8007007Ah
0x180004309  mov     rax, r10
0x18000430c  and     rax, rsi
0x18000430f  jbe     short loc_180004320
0x180004311  mov     r11, rax
0x180004314  mov     r14, r15
0x180004317  sub     r11, rbp
0x18000431a  xor     eax, eax
0x18000431c  mov     [r15], ax
0x180004320  cmp     r13d, 8007007Ah
0x180004327  jnz     short loc_180004368
0x180004329  jmp     short loc_18000435A
0x18000432b  mov     rcx, [rsp+88h+arg_20]
0x180004333  test    rcx, rcx
0x180004336  jz      short loc_18000433E
0x180004338  inc     rax
0x18000433b  mov     [rcx], rax
0x18000433e  mov     r13d, 8007007Ah
0x180004344  jmp     loc_1800041CE
0x180004349  test    r8, r8
0x18000434c  jz      short loc_1800042F2
0x18000434e  xor     eax, eax
0x180004350  lea     r14, [r15+r9*2]
0x180004354  mov     [rdx], ax
0x180004357  sub     r11, r9
0x18000435a  mov     rbx, r14
0x18000435d  mov     [rsp+88h+cchDest], r11
0x180004365  mov     r10, r11
0x180004368  mov     r15, [rsp+88h+var_38]
0x18000436d  test    r13d, r13d
0x180004370  js      loc_1800041CE
0x180004376  lea     rax, [rsp+88h+cchDest]
0x18000437e  mov     r8, rdi; pszSrc
0x180004381  lea     r9, [rsp+88h+var_48]; ppszDestEnd
0x180004386  mov     [rsp+88h+pcchRemaining], rax; pcchRemaining
0x18000438b  mov     rdx, r10; cchDest
0x18000438e  mov     rcx, rbx; pszDest
0x180004391  call    StringCchCatExW
0x180004396  mov     r13d, eax
0x180004399  test    eax, eax
0x18000439b  js      loc_1800041CE
0x1800043a1  mov     rcx, [rsp+88h+var_48]
0x1800043a6  mov     rdx, [rsp+88h+arg_10]
0x1800043ae  mov     rax, rcx
0x1800043b1  sub     rax, rdx
0x1800043b4  sar     rax, 1
0x1800043b7  cmp     rax, r12
0x1800043ba  ja      loc_18000446B
0x1800043c0  cmp     rbx, rcx
0x1800043c3  jz      loc_1800041CE
0x1800043c9  movzx   eax, word ptr [rbx]
0x1800043cc  cmp     ax, 1
0x1800043d0  jz      short loc_1800043E2
0x1800043d2  cmp     ax, 5Ch ; '\'
0x1800043d6  jz      loc_180004474
0x1800043dc  add     rbx, 2
0x1800043e0  jmp     short loc_1800043C0
0x1800043e2  mov     r13d, 80070057h
0x1800043e8  jmp     loc_1800041CE
0x1800043ed  add     rax, 2
0x1800043f1  sub     rcx, 1
0x1800043f5  jnz     loc_180004260
0x1800043fb  jmp     loc_180004269
0x180004400  mov     r13d, 80070057h
0x180004406  test    r12, r12
0x180004409  jz      loc_1800041CE
0x18000440f  mov     [r14], bp
0x180004413  jmp     loc_1800041CE
0x180004418  jle     loc_1800041CE
0x18000441e  movzx   r13d, ax
0x180004422  or      r13d, 80070000h
0x180004429  jmp     loc_1800041CE
0x18000442e  mov     r13d, 80070057h
0x180004434  jmp     short loc_18000440F
0x180004436  lea     rax, [r10-1]
0x18000443a  mov     rdx, r12
0x18000443d  sub     rdx, rax
0x180004440  lea     rcx, [r14+rax*2]
0x180004444  jmp     loc_1800041BC
0x180004449  cmp     word ptr cs:asc_18000E508, r13w; "\\"
0x180004451  jz      loc_18000435A
0x180004457  test    rbx, rbx
0x18000445a  jnz     loc_180004303
0x180004460  mov     r13d, 80070057h
0x180004466  jmp     loc_180004309
0x18000446b  lea     rcx, [rdx+r12*2]
0x18000446f  jmp     loc_1800043C0
0x180004474  mov     word ptr [rbx], 1
0x180004479  jmp     loc_1800043DC
```
