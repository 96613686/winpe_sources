# ConnectionPointContainer::Remove(ulong)

- ea: `0x1800033b0`
- end: `0x180003543`
- name: `?Remove@ConnectionPointContainer@@QEAAXK@Z`
- size: `403`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18001be3c`
- `0x18001ff50`

## callees

- `0x1800033b0`
- `0x180003550`
- `0x180003c70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800033f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003538`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800033f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003538`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800033d0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800033d0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ConnectionPointContainer::Remove(LPCRITICAL_SECTION lpCriticalSection, unsigned int a2)
{
  std::_Ref_count_base *i; // rsi
  _DWORD **OwningThread; // rcx
  _DWORD **v6; // rdi
  _DWORD *v7; // rbp
  __int64 v8; // rdi
  __int64 v9; // rcx
  __int64 v10; // rdx
  _DWORD *v11; // rax
  _QWORD *v12; // r15
  _QWORD *v13; // r14
  std::_Ref_count_base *v14; // rcx
  _DWORD *v15; // rax
  _DWORD *v16; // rcx
  std::_Ref_count_base *v17; // rax

  i = 0;
  EnterCriticalSection(lpCriticalSection);
  OwningThread = (_DWORD **)lpCriticalSection[1].OwningThread;
  v6 = *(_DWORD ***)&lpCriticalSection[1].LockCount;
  if ( v6 == OwningThread )
  {
    v7 = 0;
  }
  else
  {
    while ( **v6 != a2 )
    {
      v6 += 2;
      if ( v6 == OwningThread )
      {
        v8 = ((__int64)lpCriticalSection[1].OwningThread - *(_QWORD *)&lpCriticalSection[1].LockCount) >> 4;
        LeaveCriticalSection(lpCriticalSection);
        goto LABEL_9;
      }
    }
    v11 = v6[1];
    if ( v11 )
      _InterlockedIncrement(v11 + 2);
    v12 = lpCriticalSection[1].OwningThread;
    v13 = v6 + 2;
    v7 = *v6;
    for ( i = (std::_Ref_count_base *)v6[1]; v13 != v12; v13 += 2 )
    {
      v15 = (_DWORD *)*v13;
      v16 = (_DWORD *)v13[1];
      *v13 = 0;
      v13[1] = 0;
      *v6 = v15;
      v17 = (std::_Ref_count_base *)v6[1];
      v6[1] = v16;
      if ( v17 )
        std::_Ref_count_base::_Decref(v17);
      v6 += 2;
    }
    v14 = (std::_Ref_count_base *)*((_QWORD *)lpCriticalSection[1].OwningThread - 1);
    if ( v14 )
      std::_Ref_count_base::_Decref(v14);
    lpCriticalSection[1].OwningThread = (char *)lpCriticalSection[1].OwningThread - 16;
  }
  v8 = ((__int64)lpCriticalSection[1].OwningThread - *(_QWORD *)&lpCriticalSection[1].LockCount) >> 4;
  LeaveCriticalSection(lpCriticalSection);
  if ( v7 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
      goto LABEL_6;
    v10 = 11;
  }
  else
  {
LABEL_9:
    v9 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
      goto LABEL_6;
    v10 = 12;
  }
  WPP_SF_Dd(*(_QWORD *)(v9 + 16), v10, WPP_2ce43deefc5a38284e7a25a8a4237130_Traceguids, a2, v8);
LABEL_6:
  if ( i )
    std::_Ref_count_base::_Decref(i);
}

```

## disassembly

```asm
0x1800033b0  mov     rax, rsp
0x1800033b3  push    rsi
0x1800033b4  sub     rsp, 60h
0x1800033b8  mov     [rax+18h], rbx
0x1800033bc  xor     esi, esi
0x1800033be  mov     [rax+20h], rbp
0x1800033c2  mov     rbx, rcx
0x1800033c5  mov     [rax-10h], rdi
0x1800033c9  mov     [rax-18h], r12
0x1800033cd  mov     r12d, edx
0x1800033d0  call    cs:__imp_EnterCriticalSection
0x1800033d6  mov     rcx, [rbx+38h]
0x1800033da  mov     rdi, [rbx+30h]
0x1800033de  cmp     rdi, rcx
0x1800033e1  jnz     loc_180003515
0x1800033e7  xor     ebp, ebp
0x1800033e9  mov     rdi, [rbx+38h]
0x1800033ed  mov     rcx, rbx; lpCriticalSection
0x1800033f0  sub     rdi, [rbx+30h]
0x1800033f4  sar     rdi, 4
0x1800033f8  call    cs:__imp_LeaveCriticalSection
0x1800033fe  test    rbp, rbp
0x180003401  jz      short loc_180003449
0x180003403  mov     rcx, cs:WPP_GLOBAL_Control
0x18000340a  lea     rax, WPP_GLOBAL_Control
0x180003411  cmp     rcx, rax
0x180003414  jz      short loc_18000341C
0x180003416  test    byte ptr [rcx+1Ch], 4
0x18000341a  jnz     short loc_180003469
0x18000341c  mov     r12, [rsp+68h+var_18]
0x180003421  mov     rdi, [rsp+68h+var_10]
0x180003426  mov     rbp, [rsp+68h+arg_18]
0x18000342e  mov     rbx, [rsp+68h+arg_10]
0x180003436  test    rsi, rsi
0x180003439  jz      short loc_180003443
0x18000343b  mov     rcx, rsi; this
0x18000343e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180003443  add     rsp, 60h
0x180003447  pop     rsi
0x180003448  retn
0x180003449  mov     rcx, cs:WPP_GLOBAL_Control
0x180003450  lea     rax, WPP_GLOBAL_Control
0x180003457  cmp     rcx, rax
0x18000345a  jz      short loc_18000341C
0x18000345c  test    byte ptr [rcx+1Ch], 4
0x180003460  jz      short loc_18000341C
0x180003462  mov     edx, 0Ch
0x180003467  jmp     short loc_18000346E
0x180003469  mov     edx, 0Bh
0x18000346e  mov     rcx, [rcx+10h]
0x180003472  lea     r8, WPP_2ce43deefc5a38284e7a25a8a4237130_Traceguids
0x180003479  mov     r9d, r12d
0x18000347c  mov     [rsp+68h+var_48], edi
0x180003480  call    WPP_SF_Dd
0x180003485  jmp     short loc_18000341C
0x180003487  mov     rax, [rdi+8]
0x18000348b  mov     [rsp+68h+var_20], r14
0x180003490  mov     [rsp+68h+var_28], r15
0x180003495  test    rax, rax
0x180003498  jz      short loc_18000349E
0x18000349a  lock inc dword ptr [rax+8]
0x18000349e  mov     r15, [rbx+38h]
0x1800034a2  lea     r14, [rdi+10h]
0x1800034a6  mov     rbp, [rdi]
0x1800034a9  mov     rsi, [rdi+8]
0x1800034ad  cmp     r14, r15
0x1800034b0  jnz     short loc_1800034D8
0x1800034b2  mov     rax, [rbx+38h]
0x1800034b6  mov     r15, [rsp+68h+var_28]
0x1800034bb  mov     r14, [rsp+68h+var_20]
0x1800034c0  mov     rcx, [rax-8]; this
0x1800034c4  test    rcx, rcx
0x1800034c7  jz      short loc_1800034CE
0x1800034c9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800034ce  add     qword ptr [rbx+38h], 0FFFFFFFFFFFFFFF0h
0x1800034d3  jmp     loc_1800033E9
0x1800034d8  mov     rax, [r14]
0x1800034db  mov     rcx, [r14+8]
0x1800034df  mov     qword ptr [r14], 0
0x1800034e6  mov     qword ptr [r14+8], 0
0x1800034ee  mov     [rdi], rax
0x1800034f1  mov     rax, [rdi+8]
0x1800034f5  mov     [rdi+8], rcx
0x1800034f9  test    rax, rax
0x1800034fc  jz      short loc_180003506
0x1800034fe  mov     rcx, rax; this
0x180003501  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180003506  add     rdi, 10h
0x18000350a  add     r14, 10h
0x18000350e  cmp     r14, r15
0x180003511  jnz     short loc_1800034D8
0x180003513  jmp     short loc_1800034B2
0x180003515  mov     rax, [rdi]
0x180003518  cmp     [rax], r12d
0x18000351b  jz      loc_180003487
0x180003521  add     rdi, 10h
0x180003525  cmp     rdi, rcx
0x180003528  jnz     short loc_180003515
0x18000352a  mov     rdi, rcx
0x18000352d  mov     rcx, rbx; lpCriticalSection
0x180003530  sub     rdi, [rbx+30h]
0x180003534  sar     rdi, 4
0x180003538  call    cs:__imp_LeaveCriticalSection
0x18000353e  jmp     loc_180003449
```
