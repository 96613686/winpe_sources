# VsmmVaGpaCorepCommitFinalize

- ea: `0x1400ede88`
- end: `0x1400ee1ed`
- name: `VsmmVaGpaCorepCommitFinalize`
- size: `869`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400ed88c`

## callees

- `0x1400e8bc8`
- `0x1400ede88`
- `0x1400ee400`
- `0x1400ee420`
- `0x1400ef36c`

## import_xrefs

- `ntoskrnl!RtlRbInsertNodeEx` at `0x1400edf5b`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x1400edff1`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x1400edf5b`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x1400edff1`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400ee0cc`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400ee127`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400ee0cc`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400ee127`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ee0f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ee0f9`
- `winhvr!WinHvUncommitGpaPages` at `0x1400ee073`
- `winhvr!WinHvUncommitGpaPages` at `0x1400ee073`

## pseudocode

```c
void __fastcall VsmmVaGpaCorepCommitFinalize(__int64 a1, _QWORD **a2, _QWORD **a3)
{
  _QWORD **v3; // r15
  _QWORD *v6; // rax
  _QWORD *v7; // rcx
  _QWORD *v8; // rbp
  unsigned __int64 v9; // rbx
  int v10; // esi
  unsigned __int64 v11; // rax
  __int64 v12; // rbp
  __int64 v13; // rdi
  unsigned __int64 v14; // rbx
  int v15; // esi
  unsigned __int64 v16; // rax
  _QWORD *v17; // rax
  _QWORD *v18; // rcx
  _QWORD *v19; // rbx
  __int64 v20; // rcx
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  _QWORD *v23; // rax
  __int64 v24; // rdi
  int v25; // eax
  __int64 v26; // rsi
  __int64 v27; // rcx
  __int64 v28; // rax
  __int64 v29; // [rsp+80h] [rbp+18h] BYREF

  v3 = a3;
  if ( a3 )
  {
    while ( 1 )
    {
      v6 = *v3;
      if ( *v3 == v3 )
        goto LABEL_31;
      if ( (_QWORD **)v6[1] != v3 || (v7 = (_QWORD *)*v6, *(_QWORD **)(*v6 + 8LL) != v6) )
LABEL_61:
        __fastfail(3u);
      *v3 = v7;
      v8 = v6 - 5;
      v7[1] = v3;
      v6[1] = 0;
      *v6 = 0;
      v9 = *(_QWORD *)(a1 + 10824);
      if ( (*(_BYTE *)(a1 + 10832) & 1) != 0 && v9 )
        v9 ^= a1 + 10824;
      LOBYTE(a3) = 0;
      v10 = *(_BYTE *)(a1 + 10832) & 1;
      if ( !v9 )
        goto LABEL_16;
      while ( 1 )
      {
        if ( (int)VsmmVaGpaCorepGpnCompareFunctionByPage(v8 + 7, v9, a3) >= 0 )
        {
          v11 = *(_QWORD *)(v9 + 8);
          if ( v10 )
          {
            if ( !v11 )
            {
LABEL_15:
              LOBYTE(a3) = 1;
              goto LABEL_16;
            }
            v11 ^= v9;
          }
          if ( !v11 )
            goto LABEL_15;
          goto LABEL_10;
        }
        v11 = *(_QWORD *)v9;
        if ( v10 )
          break;
LABEL_12:
        if ( !v11 )
          goto LABEL_46;
LABEL_10:
        v9 = v11;
      }
      if ( v11 )
        break;
LABEL_46:
      LOBYTE(a3) = 0;
LABEL_16:
      RtlRbInsertNodeEx(a1 + 10824, v9, a3, v8);
      if ( (v8[12] & 4) != 0 )
        ++*(_QWORD *)(a1 + 10856);
      v12 = v8[10];
      if ( *(_QWORD *)(v12 + 16) == -1 )
      {
        v13 = *(_QWORD *)(v12 + 24) + 64LL;
        v14 = *(_QWORD *)v13;
        if ( (*(_BYTE *)(*(_QWORD *)(v12 + 24) + 72LL) & 1) != 0 )
        {
          if ( v14 )
            v14 ^= v13;
        }
        LOBYTE(a3) = 0;
        v15 = *(_BYTE *)(*(_QWORD *)(v12 + 24) + 72LL) & 1;
        if ( v14 )
        {
          while ( 1 )
          {
            if ( (int)VsmmVaGpaCorepVpnCompareFunctionByPage(v12 + 32, v14, a3) < 0 )
            {
              v16 = *(_QWORD *)v14;
              if ( v15 )
              {
                if ( !v16 )
                {
LABEL_48:
                  LOBYTE(a3) = 0;
                  break;
                }
                v16 ^= v14;
              }
              if ( !v16 )
                goto LABEL_48;
            }
            else
            {
              v16 = *(_QWORD *)(v14 + 8);
              if ( v15 )
              {
                if ( !v16 )
                {
LABEL_29:
                  LOBYTE(a3) = 1;
                  break;
                }
                v16 ^= v14;
              }
              if ( !v16 )
                goto LABEL_29;
            }
            v14 = v16;
          }
        }
        RtlRbInsertNodeEx(v13, v14, a3, v12);
      }
    }
    v11 ^= v9;
    goto LABEL_12;
  }
LABEL_31:
  if ( a2 )
  {
    while ( 1 )
    {
      v17 = *a2;
      if ( *a2 == a2 )
        return;
      if ( (_QWORD **)v17[1] != a2 )
        goto LABEL_61;
      v18 = (_QWORD *)*v17;
      if ( *(_QWORD **)(*v17 + 8LL) != v17 )
        goto LABEL_61;
      *a2 = v18;
      v19 = v17 - 5;
      v18[1] = a2;
      v17[1] = 0;
      *v17 = 0;
      v20 = *(_QWORD *)(a1 + 648);
      v29 = 0;
      WinHvUncommitGpaPages(v20, v17[2], v17[3] - v17[2] + 1LL, &v29);
      v21 = v19 + 3;
      v22 = v19[3];
      if ( *(_QWORD **)(v22 + 8) != v19 + 3 )
        goto LABEL_61;
      v23 = (_QWORD *)v19[4];
      if ( (_QWORD *)*v23 != v21 )
        goto LABEL_61;
      v24 = v19[10];
      *v23 = v22;
      *(_QWORD *)(v22 + 8) = v23;
      *v21 = 0;
      v19[4] = 0;
      v19[10] = 0;
      --*(_DWORD *)(v24 + 64);
      RtlRbRemoveNode(a1 + 10824, v19);
      v25 = *((_DWORD *)v19 + 24);
      v19[2] = -1;
      if ( (v25 & 4) != 0 )
        --*(_QWORD *)(a1 + 10856);
      if ( !*(_DWORD *)(v24 + 64) )
        break;
LABEL_40:
      ExFreePoolWithTag(v19, 0x6D4D6456u);
    }
    RtlRbRemoveNode(*(_QWORD *)(v24 + 24) + 64LL, v24);
    v26 = *(_QWORD *)(v24 + 24);
    *(_QWORD *)(v24 + 16) = -1;
    VsmmVaGpaCorepFreeRanges(v27, v24);
    v28 = *(_QWORD *)(v26 + 64);
    if ( (*(_BYTE *)(v26 + 72) & 1) != 0 )
    {
      if ( !v28 )
      {
LABEL_44:
        VsmmVaGpaCorepProcessContextTeardown(a1, v26);
        goto LABEL_40;
      }
      v28 ^= v26 + 64;
    }
    if ( v28 )
      goto LABEL_40;
    goto LABEL_44;
  }
}

```

## disassembly

```asm
0x1400ede88  push    rbx
0x1400ede8a  push    rbp
0x1400ede8b  push    rsi
0x1400ede8c  push    rdi
0x1400ede8d  push    r12
0x1400ede8f  push    r13
0x1400ede91  push    r14
0x1400ede93  push    r15
0x1400ede95  sub     rsp, 28h
0x1400ede99  mov     r15, r8
0x1400ede9c  mov     r13, rdx
0x1400ede9f  mov     r14, rcx
0x1400edea2  test    r8, r8
0x1400edea5  jz      loc_1400EE002
0x1400edeab  mov     rax, [r15]
0x1400edeae  cmp     rax, r15
0x1400edeb1  jz      loc_1400EE002
0x1400edeb7  cmp     [rax+8], r15
0x1400edebb  jnz     loc_1400EE1E6
0x1400edec1  mov     rcx, [rax]
0x1400edec4  cmp     [rcx+8], rax
0x1400edec8  jnz     loc_1400EE1E6
0x1400edece  mov     [r15], rcx
0x1400eded1  lea     rbp, [rax-28h]
0x1400eded5  mov     [rcx+8], r15
0x1400eded9  lea     rdi, [r14+2A48h]
0x1400edee0  mov     qword ptr [rbp+30h], 0
0x1400edee8  mov     qword ptr [rax], 0
0x1400edeef  test    byte ptr [r14+2A50h], 1
0x1400edef7  mov     rbx, [rdi]
0x1400edefa  jnz     loc_1400EE180
0x1400edf00  movzx   esi, byte ptr [rdi+8]
0x1400edf04  xor     r8b, r8b
0x1400edf07  and     esi, 1
0x1400edf0a  test    rbx, rbx
0x1400edf0d  jz      short loc_1400EDF52
0x1400edf0f  mov     rdx, rbx
0x1400edf12  lea     rcx, [rbp+38h]
0x1400edf16  call    VsmmVaGpaCorepGpnCompareFunctionByPage
0x1400edf1b  test    eax, eax
0x1400edf1d  js      short loc_1400EDF31
0x1400edf1f  mov     rax, [rbx+8]
0x1400edf23  test    esi, esi
0x1400edf25  jnz     short loc_1400EDF46
0x1400edf27  test    rax, rax
0x1400edf2a  jz      short loc_1400EDF4F
0x1400edf2c  mov     rbx, rax
0x1400edf2f  jmp     short loc_1400EDF0F
0x1400edf31  mov     rax, [rbx]
0x1400edf34  test    esi, esi
0x1400edf36  jnz     loc_1400EE166
0x1400edf3c  test    rax, rax
0x1400edf3f  jnz     short loc_1400EDF2C
0x1400edf41  jmp     loc_1400EE16B
0x1400edf46  test    rax, rax
0x1400edf49  jnz     loc_1400EE1AE
0x1400edf4f  mov     r8b, 1
0x1400edf52  mov     r9, rbp
0x1400edf55  mov     rdx, rbx
0x1400edf58  mov     rcx, rdi
0x1400edf5b  call    cs:__imp_RtlRbInsertNodeEx
0x1400edf62  nop     dword ptr [rax+rax+00h]
0x1400edf67  mov     eax, [rbp+60h]
0x1400edf6a  test    al, 4
0x1400edf6c  jnz     loc_1400EE1BE
0x1400edf72  mov     rbp, [rbp+50h]
0x1400edf76  cmp     qword ptr [rbp+10h], 0FFFFFFFFFFFFFFFFh
0x1400edf7b  jnz     loc_1400EDEAB
0x1400edf81  mov     rdi, [rbp+18h]
0x1400edf85  add     rdi, 40h ; '@'
0x1400edf89  test    byte ptr [rdi+8], 1
0x1400edf8d  mov     rbx, [rdi]
0x1400edf90  jnz     loc_1400EE18A
0x1400edf96  movzx   esi, byte ptr [rdi+8]
0x1400edf9a  xor     r8b, r8b
0x1400edf9d  and     esi, 1
0x1400edfa0  test    rbx, rbx
0x1400edfa3  jz      short loc_1400EDFE8
0x1400edfa5  mov     rdx, rbx
0x1400edfa8  lea     rcx, [rbp+20h]
0x1400edfac  call    VsmmVaGpaCorepVpnCompareFunctionByPage
0x1400edfb1  test    eax, eax
0x1400edfb3  js      short loc_1400EDFC7
0x1400edfb5  mov     rax, [rbx+8]
0x1400edfb9  test    esi, esi
0x1400edfbb  jnz     short loc_1400EDFDC
0x1400edfbd  test    rax, rax
0x1400edfc0  jz      short loc_1400EDFE5
0x1400edfc2  mov     rbx, rax
0x1400edfc5  jmp     short loc_1400EDFA5
0x1400edfc7  mov     rax, [rbx]
0x1400edfca  test    esi, esi
0x1400edfcc  jnz     loc_1400EE173
0x1400edfd2  test    rax, rax
0x1400edfd5  jnz     short loc_1400EDFC2
0x1400edfd7  jmp     loc_1400EE178
0x1400edfdc  test    rax, rax
0x1400edfdf  jnz     loc_1400EE1CA
0x1400edfe5  mov     r8b, 1
0x1400edfe8  mov     r9, rbp
0x1400edfeb  mov     rdx, rbx
0x1400edfee  mov     rcx, rdi
0x1400edff1  call    cs:__imp_RtlRbInsertNodeEx
0x1400edff8  nop     dword ptr [rax+rax+00h]
0x1400edffd  jmp     loc_1400EDEAB
0x1400ee002  test    r13, r13
0x1400ee005  jz      loc_1400EE10A
0x1400ee00b  mov     rax, [r13+0]
0x1400ee00f  cmp     rax, r13
0x1400ee012  jz      loc_1400EE10A
0x1400ee018  cmp     [rax+8], r13
0x1400ee01c  jnz     loc_1400EE1E6
0x1400ee022  mov     rcx, [rax]
0x1400ee025  cmp     [rcx+8], rax
0x1400ee029  jnz     loc_1400EE1E6
0x1400ee02f  mov     [r13+0], rcx
0x1400ee033  lea     rbx, [rax-28h]
0x1400ee037  mov     [rcx+8], r13
0x1400ee03b  lea     r9, [rsp+68h+arg_10]
0x1400ee043  mov     qword ptr [rbx+30h], 0
0x1400ee04b  mov     qword ptr [rax], 0
0x1400ee052  mov     rcx, [r14+288h]
0x1400ee059  mov     [rsp+68h+arg_10], 0
0x1400ee065  mov     rdx, [rbx+38h]
0x1400ee069  mov     r8, [rbx+40h]
0x1400ee06d  sub     r8, rdx
0x1400ee070  inc     r8
0x1400ee073  call    cs:__imp_WinHvUncommitGpaPages
0x1400ee07a  nop     dword ptr [rax+rax+00h]
0x1400ee07f  lea     rcx, [rbx+18h]
0x1400ee083  mov     rdx, [rcx]
0x1400ee086  cmp     [rdx+8], rcx
0x1400ee08a  jnz     loc_1400EE1E6
0x1400ee090  mov     rax, [rbx+20h]
0x1400ee094  cmp     [rax], rcx
0x1400ee097  jnz     loc_1400EE1E6
0x1400ee09d  mov     rdi, [rbx+50h]
0x1400ee0a1  mov     [rax], rdx
0x1400ee0a4  mov     [rdx+8], rax
0x1400ee0a8  mov     rdx, rbx
0x1400ee0ab  mov     qword ptr [rcx], 0
0x1400ee0b2  lea     rcx, [r14+2A48h]
0x1400ee0b9  mov     qword ptr [rbx+20h], 0
0x1400ee0c1  mov     qword ptr [rbx+50h], 0
0x1400ee0c9  dec     dword ptr [rdi+40h]
0x1400ee0cc  call    cs:__imp_RtlRbRemoveNode
0x1400ee0d3  nop     dword ptr [rax+rax+00h]
0x1400ee0d8  mov     eax, [rbx+60h]
0x1400ee0db  mov     qword ptr [rbx+10h], 0FFFFFFFFFFFFFFFFh
0x1400ee0e3  test    al, 4
0x1400ee0e5  jnz     loc_1400EE1DA
0x1400ee0eb  cmp     dword ptr [rdi+40h], 0
0x1400ee0ef  jz      short loc_1400EE11C
0x1400ee0f1  mov     edx, 6D4D6456h; Tag
0x1400ee0f6  mov     rcx, rbx; P
0x1400ee0f9  call    cs:__imp_ExFreePoolWithTag
0x1400ee100  nop     dword ptr [rax+rax+00h]
0x1400ee105  jmp     loc_1400EE00B
0x1400ee10a  add     rsp, 28h
0x1400ee10e  pop     r15
0x1400ee110  pop     r14
0x1400ee112  pop     r13
0x1400ee114  pop     r12
0x1400ee116  pop     rdi
0x1400ee117  pop     rsi
0x1400ee118  pop     rbp
0x1400ee119  pop     rbx
0x1400ee11a  retn
0x1400ee11c  mov     rcx, [rdi+18h]
0x1400ee120  mov     rdx, rdi
0x1400ee123  add     rcx, 40h ; '@'
0x1400ee127  call    cs:__imp_RtlRbRemoveNode
0x1400ee12e  nop     dword ptr [rax+rax+00h]
0x1400ee133  mov     rsi, [rdi+18h]
0x1400ee137  mov     rdx, rdi
0x1400ee13a  mov     qword ptr [rdi+10h], 0FFFFFFFFFFFFFFFFh
0x1400ee142  call    VsmmVaGpaCorepFreeRanges
0x1400ee147  test    byte ptr [rsi+48h], 1
0x1400ee14b  lea     rcx, [rsi+40h]
0x1400ee14f  mov     rax, [rcx]
0x1400ee152  jnz     short loc_1400EE1A4
0x1400ee154  test    rax, rax
0x1400ee157  jnz     short loc_1400EE0F1
0x1400ee159  mov     rdx, rsi
0x1400ee15c  mov     rcx, r14
0x1400ee15f  call    VsmmVaGpaCorepProcessContextTeardown
0x1400ee164  jmp     short loc_1400EE0F1
0x1400ee166  test    rax, rax
0x1400ee169  jnz     short loc_1400EE1B6
0x1400ee16b  xor     r8b, r8b
0x1400ee16e  jmp     loc_1400EDF52
0x1400ee173  test    rax, rax
0x1400ee176  jnz     short loc_1400EE1D2
0x1400ee178  xor     r8b, r8b
0x1400ee17b  jmp     loc_1400EDFE8
0x1400ee180  test    rbx, rbx
0x1400ee183  jnz     short loc_1400EE197
0x1400ee185  jmp     loc_1400EDF00
0x1400ee18a  test    rbx, rbx
0x1400ee18d  jz      short loc_1400EE19F
0x1400ee18f  xor     rbx, rdi
0x1400ee192  jmp     loc_1400EDF96
0x1400ee197  xor     rbx, rdi
0x1400ee19a  jmp     loc_1400EDF00
0x1400ee19f  jmp     loc_1400EDF96
0x1400ee1a4  test    rax, rax
0x1400ee1a7  jz      short loc_1400EE159
0x1400ee1a9  xor     rax, rcx
0x1400ee1ac  jmp     short loc_1400EE154
0x1400ee1ae  xor     rax, rbx
0x1400ee1b1  jmp     loc_1400EDF27
0x1400ee1b6  xor     rax, rbx
0x1400ee1b9  jmp     loc_1400EDF3C
0x1400ee1be  inc     qword ptr [r14+2A68h]
0x1400ee1c5  jmp     loc_1400EDF72
0x1400ee1ca  xor     rax, rbx
0x1400ee1cd  jmp     loc_1400EDFBD
0x1400ee1d2  xor     rax, rbx
0x1400ee1d5  jmp     loc_1400EDFD2
0x1400ee1da  dec     qword ptr [r14+2A68h]
0x1400ee1e1  jmp     loc_1400EE0EB
0x1400ee1e6  mov     ecx, 3
0x1400ee1eb  int     29h; Win8: RtlFailFast(ecx)
```
