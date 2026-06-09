# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x18000a5d0`
- end: `0x18000a787`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `439`
- prototype: `__int64 (__fastcall *__fastcall(__int64))(_QWORD, __int64, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180002f80`
- `0x180003140`
- `0x180009d70`

## callees

- `0x180002300`
- `0x18000a5d0`
- `0x18000dd84`
- `0x180012010`

## pseudocode

```c
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
0x18000a5d0  push    rbx
0x18000a5d2  push    rbp
0x18000a5d3  push    rsi
0x18000a5d4  push    rdi
0x18000a5d5  push    r14
0x18000a5d7  push    r15
0x18000a5d9  sub     rsp, 78h
0x18000a5dd  mov     rax, cs:__security_cookie
0x18000a5e4  xor     rax, rsp
0x18000a5e7  mov     [rsp+0A8h+var_48], rax
0x18000a5ec  mov     rsi, rcx
0x18000a5ef  mov     rbx, [rcx+20h]
0x18000a5f3  mov     rdi, [rcx+28h]
0x18000a5f7  mov     rax, rdi
0x18000a5fa  sub     rax, rbx
0x18000a5fd  cmp     rax, 10h
0x18000a601  jb      loc_18000A76D
0x18000a607  mov     ebp, 1
0x18000a60c  lea     r14d, [rbp+1]
0x18000a610  mov     r15d, 1FFh
0x18000a616  cmp     rbx, rdi
0x18000a619  jz      loc_18000A73A
0x18000a61f  mov     r8, [rbx+8]
0x18000a623  mov     r10d, [rbx]
0x18000a626  prefetchw byte ptr [r8]
0x18000a62a  mov     eax, [r8]
0x18000a62d  mov     ecx, eax
0x18000a62f  and     ecx, 0FFC0401Eh
0x18000a635  lock cmpxchg [r8], ecx
0x18000a63a  jnz     short loc_18000A62D
0x18000a63c  mov     ecx, eax
0x18000a63e  mov     r9d, eax
0x18000a641  shr     r9d, 1
0x18000a644  and     r9d, 0Fh
0x18000a648  jz      short loc_18000A667
0x18000a64a  prefetchw byte ptr [r8+4]
0x18000a64f  mov     eax, [r8+4]
0x18000a653  mov     edx, eax
0x18000a655  or      edx, r9d
0x18000a658  lock cmpxchg [r8+4], edx
0x18000a65e  jnz     short loc_18000A653
0x18000a660  not     eax
0x18000a662  and     eax, r9d
0x18000a665  jmp     short loc_18000A66A
0x18000a667  mov     eax, r9d
0x18000a66a  test    bpl, al
0x18000a66d  jz      short loc_18000A683
0x18000a66f  mov     [rsp+0A8h+var_78], r10d
0x18000a674  mov     [rsp+0A8h+var_74], 10002h
0x18000a67c  lea     rdx, [rsp+0A8h+var_70]
0x18000a681  jmp     short loc_18000A688
0x18000a683  lea     rdx, [rsp+0A8h+var_78]
0x18000a688  test    r14b, al
0x18000a68b  jz      short loc_18000A69B
0x18000a68d  mov     [rdx], r10d
0x18000a690  mov     dword ptr [rdx+4], 10006h
0x18000a697  add     rdx, 8
0x18000a69b  test    al, 4
0x18000a69d  jz      short loc_18000A6AD
0x18000a69f  mov     [rdx], r10d
0x18000a6a2  mov     dword ptr [rdx+4], 10003h
0x18000a6a9  add     rdx, 8
0x18000a6ad  cmp     eax, 8
0x18000a6b0  jb      short loc_18000A6C0
0x18000a6b2  mov     [rdx], r10d
0x18000a6b5  mov     dword ptr [rdx+4], 10007h
0x18000a6bc  add     rdx, 8
0x18000a6c0  mov     r8d, ecx
0x18000a6c3  shr     r8d, 5
0x18000a6c7  test    r15d, r8d
0x18000a6ca  jz      short loc_18000A6EC
0x18000a6cc  mov     [rdx], r10d
0x18000a6cf  mov     eax, ecx
0x18000a6d1  shr     eax, 0Eh
0x18000a6d4  and     ax, bp
0x18000a6d7  shl     ax, 2
0x18000a6db  mov     [rdx+4], ax
0x18000a6df  and     r8w, r15w; unsigned __int64
0x18000a6e3  mov     [rdx+6], r8w
0x18000a6e8  add     rdx, 8
0x18000a6ec  mov     eax, ecx
0x18000a6ee  shr     eax, 0Fh
0x18000a6f1  test    al, 7Fh
0x18000a6f3  jz      short loc_18000A715
0x18000a6f5  mov     [rdx], r10d
0x18000a6f8  shr     ecx, 16h
0x18000a6fb  and     cx, bp
0x18000a6fe  shl     cx, 2
0x18000a702  add     cx, bp
0x18000a705  mov     [rdx+4], cx
0x18000a709  and     ax, 7Fh
0x18000a70d  mov     [rdx+6], ax
0x18000a711  add     rdx, 8
0x18000a715  lea     rax, [rsp+0A8h+var_78]
0x18000a71a  sub     rdx, rax
0x18000a71d  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x18000a721  test    rdx, rdx
0x18000a724  jle     short loc_18000A731
0x18000a726  lea     rcx, [rsp+0A8h+var_78]; this
0x18000a72b  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x18000a730  nop
0x18000a731  add     rbx, 10h
0x18000a735  jmp     loc_18000A616
0x18000a73a  mov     rax, [rsi+20h]
0x18000a73e  mov     [rsi+28h], rax
0x18000a742  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000a749  test    rax, rax
0x18000a74c  jnz     short loc_18000A75A
0x18000a74e  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000a755  test    rax, rax
0x18000a758  jz      short loc_18000A76D
0x18000a75a  xor     r9d, r9d
0x18000a75d  xor     r8d, r8d
0x18000a760  mov     edx, 0FEh
0x18000a765  xor     ecx, ecx
0x18000a767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a76c  nop
0x18000a76d  mov     rcx, [rsp+0A8h+var_48]
0x18000a772  xor     rcx, rsp; StackCookie
0x18000a775  call    __security_check_cookie
0x18000a77a  add     rsp, 78h
0x18000a77e  pop     r15
0x18000a780  pop     r14
0x18000a782  pop     rdi
0x18000a783  pop     rsi
0x18000a784  pop     rbp
0x18000a785  pop     rbx
0x18000a786  retn
```
