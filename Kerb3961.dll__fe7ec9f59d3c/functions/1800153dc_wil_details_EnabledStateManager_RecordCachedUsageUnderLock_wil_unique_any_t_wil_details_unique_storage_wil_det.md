# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x1800153dc`
- end: `0x180015591`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `437`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000fa50`
- `0x18000fbc0`
- `0x180014cf0`

## callees

- `0x180001d40`
- `0x1800153dc`
- `0x180017d44`
- `0x18001e010`

## pseudocode

```c
__int64 (__fastcall *__fastcall wil::details::EnabledStateManager::RecordCachedUsageUnderLock(
        __int64 a1))(_QWORD, __int64, _QWORD, _QWORD)
{
  int *v1; // rdi
  int *v3; // rbx
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

  v1 = *(int **)(a1 + 40);
  v3 = *(int **)(a1 + 32);
  result = (__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))((char *)v1 - (char *)v3);
  if ( (unsigned __int64)((char *)v1 - (char *)v3) >= 0x10 )
  {
    while ( v3 != v1 )
    {
      v5 = *((_QWORD *)v3 + 1);
      v6 = *v3;
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
        v9 = &v13;
        v12[1] = 65538;
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
        LOWORD(v10) = v10 & 0x1FF;
        *(_DWORD *)v9 = v6;
        *((_WORD *)v9 + 3) = v10;
        *((_WORD *)v9 + 2) = 4 * ((v7 >> 14) & 1);
        v9 += 8;
      }
      if ( ((v7 >> 15) & 0x7F) != 0 )
      {
        *(_DWORD *)v9 = v6;
        *((_WORD *)v9 + 3) = (v7 >> 15) & 0x7F;
        *((_WORD *)v9 + 2) = 4 * ((v7 >> 22) & 1) + 1;
        v9 += 8;
      }
      v11 = (v9 - (char *)v12) >> 3;
      if ( v11 > 0 )
        wil::details::WilApi_RecordFeatureUsageReports(
          (wil::details *)v12,
          (struct __WIL_RTL_FEATURE_USAGE_DATA *)v11,
          v10);
      v3 += 4;
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
0x1800153dc  push    rbx
0x1800153de  push    rbp
0x1800153df  push    rsi
0x1800153e0  push    rdi
0x1800153e1  push    r14
0x1800153e3  push    r15
0x1800153e5  sub     rsp, 78h
0x1800153e9  mov     rax, cs:__security_cookie
0x1800153f0  xor     rax, rsp
0x1800153f3  mov     [rsp+0A8h+var_48], rax
0x1800153f8  mov     rdi, [rcx+28h]
0x1800153fc  mov     rsi, rcx
0x1800153ff  mov     rbx, [rcx+20h]
0x180015403  mov     rax, rdi
0x180015406  sub     rax, rbx
0x180015409  cmp     rax, 10h
0x18001540d  jb      loc_180015577
0x180015413  mov     ebp, 1
0x180015418  mov     r15d, 1FFh
0x18001541e  lea     r14d, [rbp+1]
0x180015422  cmp     rbx, rdi
0x180015425  jz      loc_180015545
0x18001542b  mov     r8, [rbx+8]
0x18001542f  mov     r10d, [rbx]
0x180015432  prefetchw byte ptr [r8]
0x180015436  mov     eax, [r8]
0x180015439  mov     ecx, eax
0x18001543b  and     ecx, 0FFC0401Eh
0x180015441  lock cmpxchg [r8], ecx
0x180015446  jnz     short loc_180015439
0x180015448  mov     r9d, eax
0x18001544b  mov     ecx, eax
0x18001544d  shr     r9d, 1
0x180015450  and     r9d, 0Fh
0x180015454  jz      short loc_180015473
0x180015456  prefetchw byte ptr [r8+4]
0x18001545b  mov     eax, [r8+4]
0x18001545f  mov     edx, eax
0x180015461  or      edx, r9d
0x180015464  lock cmpxchg [r8+4], edx
0x18001546a  jnz     short loc_18001545F
0x18001546c  not     eax
0x18001546e  and     eax, r9d
0x180015471  jmp     short loc_180015476
0x180015473  mov     eax, r9d
0x180015476  test    bpl, al
0x180015479  jz      short loc_18001548F
0x18001547b  mov     [rsp+0A8h+var_78], r10d
0x180015480  lea     rdx, [rsp+0A8h+var_70]
0x180015485  mov     [rsp+0A8h+var_74], 10002h
0x18001548d  jmp     short loc_180015494
0x18001548f  lea     rdx, [rsp+0A8h+var_78]
0x180015494  test    r14b, al
0x180015497  jz      short loc_1800154A7
0x180015499  mov     [rdx], r10d
0x18001549c  mov     dword ptr [rdx+4], 10006h
0x1800154a3  add     rdx, 8
0x1800154a7  test    al, 4
0x1800154a9  jz      short loc_1800154B9
0x1800154ab  mov     [rdx], r10d
0x1800154ae  mov     dword ptr [rdx+4], 10003h
0x1800154b5  add     rdx, 8
0x1800154b9  cmp     eax, 8
0x1800154bc  jb      short loc_1800154CC
0x1800154be  mov     [rdx], r10d
0x1800154c1  mov     dword ptr [rdx+4], 10007h
0x1800154c8  add     rdx, 8
0x1800154cc  mov     r8d, ecx
0x1800154cf  shr     r8d, 5
0x1800154d3  test    r15d, r8d
0x1800154d6  jz      short loc_1800154F8
0x1800154d8  and     r8w, r15w; unsigned __int64
0x1800154dc  mov     [rdx], r10d
0x1800154df  mov     eax, ecx
0x1800154e1  mov     [rdx+6], r8w
0x1800154e6  shr     eax, 0Eh
0x1800154e9  and     ax, bp
0x1800154ec  shl     ax, 2
0x1800154f0  mov     [rdx+4], ax
0x1800154f4  add     rdx, 8
0x1800154f8  mov     eax, ecx
0x1800154fa  shr     eax, 0Fh
0x1800154fd  test    al, 7Fh
0x1800154ff  jz      short loc_180015521
0x180015501  shr     ecx, 16h
0x180015504  and     ax, 7Fh
0x180015508  and     cx, bp
0x18001550b  mov     [rdx], r10d
0x18001550e  shl     cx, 2
0x180015512  add     cx, bp
0x180015515  mov     [rdx+6], ax
0x180015519  mov     [rdx+4], cx
0x18001551d  add     rdx, 8
0x180015521  lea     rax, [rsp+0A8h+var_78]
0x180015526  sub     rdx, rax
0x180015529  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x18001552d  test    rdx, rdx
0x180015530  jle     short loc_18001553C
0x180015532  lea     rcx, [rsp+0A8h+var_78]; this
0x180015537  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x18001553c  add     rbx, 10h
0x180015540  jmp     loc_180015422
0x180015545  mov     rax, [rsi+20h]
0x180015549  mov     [rsi+28h], rax
0x18001554d  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180015554  test    rax, rax
0x180015557  jnz     short loc_180015565
0x180015559  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180015560  test    rax, rax
0x180015563  jz      short loc_180015577
0x180015565  xor     r9d, r9d
0x180015568  xor     r8d, r8d
0x18001556b  mov     edx, 0FEh
0x180015570  xor     ecx, ecx
0x180015572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015577  mov     rcx, [rsp+0A8h+var_48]
0x18001557c  xor     rcx, rsp; StackCookie
0x18001557f  call    __security_check_cookie
0x180015584  add     rsp, 78h
0x180015588  pop     r15
0x18001558a  pop     r14
0x18001558c  pop     rdi
0x18001558d  pop     rsi
0x18001558e  pop     rbp
0x18001558f  pop     rbx
0x180015590  retn
```
