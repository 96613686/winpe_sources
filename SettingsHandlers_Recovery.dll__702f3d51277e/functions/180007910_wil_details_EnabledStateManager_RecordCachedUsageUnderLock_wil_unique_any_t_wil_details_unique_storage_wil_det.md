# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x180007910`
- end: `0x180007ac7`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `439`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800073fc`
- `0x18000eef0`
- `0x18000ef50`

## callees

- `0x180002350`
- `0x180007910`
- `0x18000a1f4`
- `0x18002b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 (__fastcall *__fastcall wil::details::EnabledStateManager::RecordCachedUsageUnderLock(
        __int64 a1))(_QWORD, __int64, _QWORD, _QWORD)
{
  int *v2; // rbx
  int *v3; // rdi
  __int64 (__fastcall *result)(_QWORD, __int64, _QWORD, _QWORD); // rax
  __int64 v5; // r8
  int v6; // r10d
  unsigned __int32 v7; // ecx
  unsigned __int32 v8; // eax
  char *v9; // rdx
  unsigned __int64 v10; // r8
  __int64 v11; // rdx
  _DWORD v12[2]; // [rsp+30h] [rbp-78h] BYREF
  char v13; // [rsp+38h] [rbp-70h] BYREF

  v2 = *(int **)(a1 + 32);
  v3 = *(int **)(a1 + 40);
  result = (__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))((char *)v3 - (char *)v2);
  if ( (unsigned __int64)((char *)v3 - (char *)v2) >= 0x10 )
  {
    while ( v2 != v3 )
    {
      v5 = *((_QWORD *)v2 + 1);
      v6 = *v2;
      _m_prefetchw((const void *)v5);
      v7 = _InterlockedAnd((volatile signed __int32 *)v5, 0xFFC0401E);
      if ( ((v7 >> 1) & 0xF) != 0 )
      {
        _m_prefetchw((const void *)(v5 + 4));
        v8 = (v7 >> 1) & 0xF & ~_InterlockedOr((volatile signed __int32 *)(v5 + 4), (v7 >> 1) & 0xF);
      }
      else
      {
        v8 = 0;
      }
      if ( (v8 & 1) != 0 )
      {
        v12[0] = v6;
        v12[1] = 65538;
        v9 = &v13;
      }
      else
      {
        v9 = (char *)v12;
      }
      if ( (v8 & 2) != 0 )
      {
        *(_DWORD *)v9 = v6;
        *((_DWORD *)v9 + 1) = 65542;
        v9 += 8;
      }
      if ( (v8 & 4) != 0 )
      {
        *(_DWORD *)v9 = v6;
        *((_DWORD *)v9 + 1) = 65539;
        v9 += 8;
      }
      if ( v8 >= 8 )
      {
        *(_DWORD *)v9 = v6;
        *((_DWORD *)v9 + 1) = 65543;
        v9 += 8;
      }
      v10 = v7 >> 5;
      if ( (v10 & 0x1FF) != 0 )
      {
        *(_DWORD *)v9 = v6;
        *((_WORD *)v9 + 2) = 4 * ((v7 >> 14) & 1);
        LOWORD(v10) = v10 & 0x1FF;
        *((_WORD *)v9 + 3) = v10;
        v9 += 8;
      }
      if ( ((v7 >> 15) & 0x7F) != 0 )
      {
        *(_DWORD *)v9 = v6;
        *((_WORD *)v9 + 2) = 4 * ((v7 >> 22) & 1) + 1;
        *((_WORD *)v9 + 3) = (v7 >> 15) & 0x7F;
        v9 += 8;
      }
      v11 = (v9 - (char *)v12) >> 3;
      if ( v11 > 0 )
        wil::details::WilApi_RecordFeatureUsageReports(
          (wil::details *)v12,
          (struct __WIL_RTL_FEATURE_USAGE_DATA *)v11,
          v10);
      v2 += 4;
    }
    *(_QWORD *)(a1 + 40) = *(_QWORD *)(a1 + 32);
    result = (__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage )
      return (__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))result(0, 254, 0, 0);
    result = (__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage;
    if ( g_wil_details_apiRecordFeatureUsage )
      return (__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))result(0, 254, 0, 0);
  }
  return result;
}

```

## disassembly

```asm
0x180007910  push    rbx
0x180007912  push    rbp
0x180007913  push    rsi
0x180007914  push    rdi
0x180007915  push    r14
0x180007917  push    r15
0x180007919  sub     rsp, 78h
0x18000791d  mov     rax, cs:__security_cookie
0x180007924  xor     rax, rsp
0x180007927  mov     [rsp+0A8h+var_48], rax
0x18000792c  mov     rsi, rcx
0x18000792f  mov     rbx, [rcx+20h]
0x180007933  mov     rdi, [rcx+28h]
0x180007937  mov     rax, rdi
0x18000793a  sub     rax, rbx
0x18000793d  cmp     rax, 10h
0x180007941  jb      loc_180007AAD
0x180007947  mov     ebp, 1
0x18000794c  lea     r14d, [rbp+1]
0x180007950  mov     r15d, 1FFh
0x180007956  cmp     rbx, rdi
0x180007959  jz      loc_180007A7A
0x18000795f  mov     r8, [rbx+8]
0x180007963  mov     r10d, [rbx]
0x180007966  prefetchw byte ptr [r8]
0x18000796a  mov     eax, [r8]
0x18000796d  mov     ecx, eax
0x18000796f  and     ecx, 0FFC0401Eh
0x180007975  lock cmpxchg [r8], ecx
0x18000797a  jnz     short loc_18000796D
0x18000797c  mov     ecx, eax
0x18000797e  mov     r9d, eax
0x180007981  shr     r9d, 1
0x180007984  and     r9d, 0Fh
0x180007988  jz      short loc_1800079A7
0x18000798a  prefetchw byte ptr [r8+4]
0x18000798f  mov     eax, [r8+4]
0x180007993  mov     edx, eax
0x180007995  or      edx, r9d
0x180007998  lock cmpxchg [r8+4], edx
0x18000799e  jnz     short loc_180007993
0x1800079a0  not     eax
0x1800079a2  and     eax, r9d
0x1800079a5  jmp     short loc_1800079AA
0x1800079a7  mov     eax, r9d
0x1800079aa  test    bpl, al
0x1800079ad  jz      short loc_1800079C3
0x1800079af  mov     [rsp+0A8h+var_78], r10d
0x1800079b4  mov     [rsp+0A8h+var_74], 10002h
0x1800079bc  lea     rdx, [rsp+0A8h+var_70]
0x1800079c1  jmp     short loc_1800079C8
0x1800079c3  lea     rdx, [rsp+0A8h+var_78]
0x1800079c8  test    r14b, al
0x1800079cb  jz      short loc_1800079DB
0x1800079cd  mov     [rdx], r10d
0x1800079d0  mov     dword ptr [rdx+4], 10006h
0x1800079d7  add     rdx, 8
0x1800079db  test    al, 4
0x1800079dd  jz      short loc_1800079ED
0x1800079df  mov     [rdx], r10d
0x1800079e2  mov     dword ptr [rdx+4], 10003h
0x1800079e9  add     rdx, 8
0x1800079ed  cmp     eax, 8
0x1800079f0  jb      short loc_180007A00
0x1800079f2  mov     [rdx], r10d
0x1800079f5  mov     dword ptr [rdx+4], 10007h
0x1800079fc  add     rdx, 8
0x180007a00  mov     r8d, ecx
0x180007a03  shr     r8d, 5
0x180007a07  test    r15d, r8d
0x180007a0a  jz      short loc_180007A2C
0x180007a0c  mov     [rdx], r10d
0x180007a0f  mov     eax, ecx
0x180007a11  shr     eax, 0Eh
0x180007a14  and     ax, bp
0x180007a17  shl     ax, 2
0x180007a1b  mov     [rdx+4], ax
0x180007a1f  and     r8w, r15w; unsigned __int64
0x180007a23  mov     [rdx+6], r8w
0x180007a28  add     rdx, 8
0x180007a2c  mov     eax, ecx
0x180007a2e  shr     eax, 0Fh
0x180007a31  test    al, 7Fh
0x180007a33  jz      short loc_180007A55
0x180007a35  mov     [rdx], r10d
0x180007a38  shr     ecx, 16h
0x180007a3b  and     cx, bp
0x180007a3e  shl     cx, 2
0x180007a42  add     cx, bp
0x180007a45  mov     [rdx+4], cx
0x180007a49  and     ax, 7Fh
0x180007a4d  mov     [rdx+6], ax
0x180007a51  add     rdx, 8
0x180007a55  lea     rax, [rsp+0A8h+var_78]
0x180007a5a  sub     rdx, rax
0x180007a5d  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x180007a61  test    rdx, rdx
0x180007a64  jle     short loc_180007A71
0x180007a66  lea     rcx, [rsp+0A8h+var_78]; this
0x180007a6b  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x180007a70  nop
0x180007a71  add     rbx, 10h
0x180007a75  jmp     loc_180007956
0x180007a7a  mov     rax, [rsi+20h]
0x180007a7e  mov     [rsi+28h], rax
0x180007a82  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180007a89  test    rax, rax
0x180007a8c  jnz     short loc_180007A9A
0x180007a8e  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180007a95  test    rax, rax
0x180007a98  jz      short loc_180007AAD
0x180007a9a  xor     r9d, r9d
0x180007a9d  xor     r8d, r8d
0x180007aa0  mov     edx, 0FEh
0x180007aa5  xor     ecx, ecx
0x180007aa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007aac  nop
0x180007aad  mov     rcx, [rsp+0A8h+var_48]
0x180007ab2  xor     rcx, rsp; StackCookie
0x180007ab5  call    __security_check_cookie
0x180007aba  add     rsp, 78h
0x180007abe  pop     r15
0x180007ac0  pop     r14
0x180007ac2  pop     rdi
0x180007ac3  pop     rsi
0x180007ac4  pop     rbp
0x180007ac5  pop     rbx
0x180007ac6  retn
```
