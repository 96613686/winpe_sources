# sub_1800EEDF0

- ea: `0x1800eedf0`
- end: `0x1800ef092`
- name: `sub_1800EEDF0`
- size: `674`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x18009904c`
- `0x180099098`
- `0x1800994a0`
- `0x1800ad3e0`
- `0x1800eedf0`
- `0x1800ef0d0`
- `0x1800f79a0`
- `0x18020c9f0`
- `0x18020cab0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800eee3a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800eee3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ef059`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ef059`

## pseudocode

```c
__int64 __fastcall sub_1800EEDF0(__int64 a1, unsigned int a2, __int64 a3)
{
  int v4; // edi
  DWORD TickCount; // eax
  __int64 v8; // rcx
  unsigned int i; // esi
  __int64 v10; // rax
  __int64 result; // rax
  unsigned int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rdi
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rdi
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  _BYTE *v23; // rax
  unsigned int v24; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v26[4096]; // [rsp+40h] [rbp-C0h] BYREF
  char v27; // [rsp+1040h] [rbp+F40h]
  _BYTE v28[24]; // [rsp+1050h] [rbp+F50h] BYREF

  v4 = 0;
  pv = 0;
  TickCount = GetTickCount();
  v8 = 0;
  v27 = 0;
  do
  {
    TickCount = ((int)(214013 * TickCount + 2531011) >> 16) & 0x7FFF;
    v26[v8++] = TickCount;
  }
  while ( v8 != 4096 );
  for ( i = 0; i < *(_DWORD *)(a1 + 48); ++i )
  {
    if ( pv )
      break;
    v10 = *(_QWORD *)(a1 + 40);
    v24 = 0;
    result = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)(v10 + 8LL * i) + 24LL))(
               *(_QWORD *)(v10 + 8LL * i),
               &v24);
    v4 = result;
    if ( (int)result < 0 )
      return result;
    v12 = v24;
    if ( a2 < v24 )
    {
      v13 = *(_QWORD *)(*(_QWORD *)(a1 + 40) + 8LL * i);
      result = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *, LPVOID *))(*(_QWORD *)v13 + 40LL))(
                 v13,
                 a2,
                 a3,
                 qword_18021EA20,
                 &pv);
      v4 = result;
      if ( (int)result < 0 )
        return result;
      v12 = v24;
    }
    a2 -= v12;
  }
  if ( !*(_QWORD *)(a1 + 80) )
  {
    v14 = sub_18009904C(16);
    *(_QWORD *)(a1 + 80) = v14;
    v15 = v14;
    if ( v14 )
    {
      memcpy(v26, qword_18021EA90, sizeof(v26));
      v27 = 1;
      if ( (int)sub_1800EF0D0(v26, v28) < 0 )
      {
        j__o_free(v15);
        *(_QWORD *)(a1 + 80) = 0;
        v15 = 0;
      }
      v4 = sub_1800F79A0(v16, v28, pv, v15);
      if ( v4 < 0 )
      {
        v17 = *(_QWORD *)(a1 + 80);
        if ( v17 )
        {
          j__o_free(v17);
          *(_QWORD *)(a1 + 80) = 0;
        }
      }
      goto LABEL_25;
    }
    return 2147942414LL;
  }
  if ( !*(_QWORD *)(a1 + 88) )
  {
    v18 = sub_18009904C(16);
    *(_QWORD *)(a1 + 88) = v18;
    v19 = v18;
    if ( v18 )
    {
      memcpy(v26, qword_18021EA90, sizeof(v26));
      v27 = 1;
      if ( (int)sub_1800EF0D0(v26, v28) < 0 )
      {
        j__o_free(v19);
        *(_QWORD *)(a1 + 88) = 0;
        v19 = 0;
      }
      v4 = sub_1800F79A0(v20, v28, pv, v19);
      if ( v4 < 0 )
      {
        v21 = *(_QWORD *)(a1 + 88);
        if ( v21 )
        {
          j__o_free(v21);
          *(_QWORD *)(a1 + 88) = 0;
        }
      }
      goto LABEL_25;
    }
    return 2147942414LL;
  }
LABEL_25:
  v22 = 20;
  v23 = v28;
  do
  {
    *v23++ = 0;
    --v22;
  }
  while ( v22 );
  if ( pv )
    CoTaskMemFree(pv);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800eedf0  mov     [rsp-8+arg_18], rbx
0x1800eedf5  push    rbp
0x1800eedf6  push    rsi
0x1800eedf7  push    rdi
0x1800eedf8  push    r12
0x1800eedfa  push    r13
0x1800eedfc  push    r14
0x1800eedfe  push    r15
0x1800eee00  lea     rbp, [rsp-0F70h]
0x1800eee08  mov     eax, 1070h
0x1800eee0d  call    __alloca_probe
0x1800eee12  sub     rsp, rax
0x1800eee15  mov     rax, cs:__security_cookie
0x1800eee1c  xor     rax, rsp
0x1800eee1f  mov     [rbp+0FA0h+var_38], rax
0x1800eee26  xor     r13d, r13d
0x1800eee29  mov     r12, r8
0x1800eee2c  mov     edi, r13d
0x1800eee2f  mov     [rsp+10A0h+pv], r13
0x1800eee34  mov     r14d, edx
0x1800eee37  mov     rbx, rcx
0x1800eee3a  call    cs:GetTickCount
0x1800eee41  nop     dword ptr [rax+rax+00h]
0x1800eee46  mov     ecx, r13d
0x1800eee49  mov     [rbp+0FA0h+var_60], r13b
0x1800eee50  imul    eax, 343FDh
0x1800eee56  add     eax, 269EC3h
0x1800eee5b  sar     eax, 10h
0x1800eee5e  and     eax, 7FFFh
0x1800eee63  mov     [rsp+rcx+10A0h+var_1060], al
0x1800eee67  inc     rcx
0x1800eee6a  cmp     rcx, 1000h
0x1800eee71  jnz     short loc_1800EEE50
0x1800eee73  mov     esi, r13d
0x1800eee76  cmp     [rbx+30h], r13d
0x1800eee7a  jbe     loc_1800EEF00
0x1800eee80  cmp     [rsp+10A0h+pv], r13
0x1800eee85  jnz     short loc_1800EEF00
0x1800eee87  mov     rax, [rbx+28h]
0x1800eee8b  lea     rdx, [rsp+10A0h+var_1070]
0x1800eee90  mov     [rsp+10A0h+var_1070], r13d
0x1800eee95  mov     r15d, esi
0x1800eee98  mov     rcx, [rax+r15*8]
0x1800eee9c  mov     rax, [rcx]
0x1800eee9f  mov     rax, [rax+18h]
0x1800eeea3  call    cs:__guard_dispatch_icall_fptr
0x1800eeea9  mov     edi, eax
0x1800eeeab  test    eax, eax
0x1800eeead  js      loc_1800EF067
0x1800eeeb3  mov     eax, [rsp+10A0h+var_1070]
0x1800eeeb7  cmp     r14d, eax
0x1800eeeba  jnb     short loc_1800EEEF6
0x1800eeebc  mov     rax, [rbx+28h]
0x1800eeec0  lea     rdx, [rsp+10A0h+pv]
0x1800eeec5  mov     [rsp+10A0h+var_1080], rdx
0x1800eeeca  lea     r9, qword_18021EA20
0x1800eeed1  mov     r8, r12
0x1800eeed4  mov     edx, r14d
0x1800eeed7  mov     rcx, [rax+r15*8]
0x1800eeedb  mov     rax, [rcx]
0x1800eeede  mov     rax, [rax+28h]
0x1800eeee2  call    cs:__guard_dispatch_icall_fptr
0x1800eeee8  mov     edi, eax
0x1800eeeea  test    eax, eax
0x1800eeeec  js      loc_1800EF067
0x1800eeef2  mov     eax, [rsp+10A0h+var_1070]
0x1800eeef6  sub     r14d, eax
0x1800eeef9  inc     esi
0x1800eeefb  cmp     esi, [rbx+30h]
0x1800eeefe  jb      short loc_1800EEE80
0x1800eef00  cmp     [rbx+50h], r13
0x1800eef04  jnz     loc_1800EEF9F
0x1800eef0a  mov     ecx, 10h
0x1800eef0f  call    sub_18009904C
0x1800eef14  mov     [rbx+50h], rax
0x1800eef18  mov     rdi, rax
0x1800eef1b  test    rax, rax
0x1800eef1e  jz      loc_1800EEFBF
0x1800eef24  mov     r8d, 1000h; Size
0x1800eef2a  lea     rdx, qword_18021EA90; Src
0x1800eef31  lea     rcx, [rsp+10A0h+var_1060]; void *
0x1800eef36  call    memcpy
0x1800eef3b  lea     rdx, [rbp+0FA0h+var_50]
0x1800eef42  mov     [rbp+0FA0h+var_60], 1
0x1800eef49  lea     rcx, [rsp+10A0h+var_1060]
0x1800eef4e  call    sub_1800EF0D0
0x1800eef53  test    eax, eax
0x1800eef55  jns     short loc_1800EEF66
0x1800eef57  mov     rcx, rdi
0x1800eef5a  call    j__o_free
0x1800eef5f  mov     [rbx+50h], r13
0x1800eef63  mov     rdi, r13
0x1800eef66  mov     r8, [rsp+10A0h+pv]
0x1800eef6b  lea     rdx, [rbp+0FA0h+var_50]
0x1800eef72  mov     r9, rdi
0x1800eef75  call    sub_1800F79A0
0x1800eef7a  mov     edi, eax
0x1800eef7c  test    eax, eax
0x1800eef7e  jns     loc_1800EF037
0x1800eef84  mov     rcx, [rbx+50h]
0x1800eef88  test    rcx, rcx
0x1800eef8b  jz      loc_1800EF037
0x1800eef91  call    j__o_free
0x1800eef96  mov     [rbx+50h], r13
0x1800eef9a  jmp     loc_1800EF037
0x1800eef9f  cmp     [rbx+58h], r13
0x1800eefa3  jnz     loc_1800EF037
0x1800eefa9  mov     ecx, 10h
0x1800eefae  call    sub_18009904C
0x1800eefb3  mov     [rbx+58h], rax
0x1800eefb7  mov     rdi, rax
0x1800eefba  test    rax, rax
0x1800eefbd  jnz     short loc_1800EEFC9
0x1800eefbf  mov     eax, 8007000Eh
0x1800eefc4  jmp     loc_1800EF067
0x1800eefc9  mov     r8d, 1000h; Size
0x1800eefcf  lea     rdx, qword_18021EA90; Src
0x1800eefd6  lea     rcx, [rsp+10A0h+var_1060]; void *
0x1800eefdb  call    memcpy
0x1800eefe0  lea     rdx, [rbp+0FA0h+var_50]
0x1800eefe7  mov     [rbp+0FA0h+var_60], 1
0x1800eefee  lea     rcx, [rsp+10A0h+var_1060]
0x1800eeff3  call    sub_1800EF0D0
0x1800eeff8  test    eax, eax
0x1800eeffa  jns     short loc_1800EF00B
0x1800eeffc  mov     rcx, rdi
0x1800eefff  call    j__o_free
0x1800ef004  mov     [rbx+58h], r13
0x1800ef008  mov     rdi, r13
0x1800ef00b  mov     r8, [rsp+10A0h+pv]
0x1800ef010  lea     rdx, [rbp+0FA0h+var_50]
0x1800ef017  mov     r9, rdi
0x1800ef01a  call    sub_1800F79A0
0x1800ef01f  mov     edi, eax
0x1800ef021  test    eax, eax
0x1800ef023  jns     short loc_1800EF037
0x1800ef025  mov     rcx, [rbx+58h]
0x1800ef029  test    rcx, rcx
0x1800ef02c  jz      short loc_1800EF037
0x1800ef02e  call    j__o_free
0x1800ef033  mov     [rbx+58h], r13
0x1800ef037  mov     ecx, 14h
0x1800ef03c  lea     rax, [rbp+0FA0h+var_50]
0x1800ef043  mov     [rax], r13b
0x1800ef046  inc     rax
0x1800ef049  sub     rcx, 1
0x1800ef04d  jnz     short loc_1800EF043
0x1800ef04f  mov     rcx, [rsp+10A0h+pv]; pv
0x1800ef054  test    rcx, rcx
0x1800ef057  jz      short loc_1800EF065
0x1800ef059  call    cs:CoTaskMemFree
0x1800ef060  nop     dword ptr [rax+rax+00h]
0x1800ef065  mov     eax, edi
0x1800ef067  mov     rcx, [rbp+0FA0h+var_38]
0x1800ef06e  xor     rcx, rsp; StackCookie
0x1800ef071  call    __security_check_cookie
0x1800ef076  mov     rbx, [rsp+10A0h+arg_18]
0x1800ef07e  add     rsp, 1070h
0x1800ef085  pop     r15
0x1800ef087  pop     r14
0x1800ef089  pop     r13
0x1800ef08b  pop     r12
0x1800ef08d  pop     rdi
0x1800ef08e  pop     rsi
0x1800ef08f  pop     rbp
0x1800ef090  retn
```
