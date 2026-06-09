# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x18000c8d8`
- end: `0x18000ca8d`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `437`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000a5f0`
- `0x18000a650`
- `0x18000c6a4`

## callees

- `0x180001630`
- `0x18000c8d8`
- `0x18000cdd4`
- `0x18001b010`

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
0x18000c8d8  push    rbx
0x18000c8da  push    rbp
0x18000c8db  push    rsi
0x18000c8dc  push    rdi
0x18000c8dd  push    r14
0x18000c8df  push    r15
0x18000c8e1  sub     rsp, 78h
0x18000c8e5  mov     rax, cs:__security_cookie
0x18000c8ec  xor     rax, rsp
0x18000c8ef  mov     [rsp+0A8h+var_48], rax
0x18000c8f4  mov     rdi, [rcx+28h]
0x18000c8f8  mov     rsi, rcx
0x18000c8fb  mov     rbx, [rcx+20h]
0x18000c8ff  mov     rax, rdi
0x18000c902  sub     rax, rbx
0x18000c905  cmp     rax, 10h
0x18000c909  jb      loc_18000CA73
0x18000c90f  mov     ebp, 1
0x18000c914  mov     r15d, 1FFh
0x18000c91a  lea     r14d, [rbp+1]
0x18000c91e  cmp     rbx, rdi
0x18000c921  jz      loc_18000CA41
0x18000c927  mov     r8, [rbx+8]
0x18000c92b  mov     r10d, [rbx]
0x18000c92e  prefetchw byte ptr [r8]
0x18000c932  mov     eax, [r8]
0x18000c935  mov     ecx, eax
0x18000c937  and     ecx, 0FFC0401Eh
0x18000c93d  lock cmpxchg [r8], ecx
0x18000c942  jnz     short loc_18000C935
0x18000c944  mov     r9d, eax
0x18000c947  mov     ecx, eax
0x18000c949  shr     r9d, 1
0x18000c94c  and     r9d, 0Fh
0x18000c950  jz      short loc_18000C96F
0x18000c952  prefetchw byte ptr [r8+4]
0x18000c957  mov     eax, [r8+4]
0x18000c95b  mov     edx, eax
0x18000c95d  or      edx, r9d
0x18000c960  lock cmpxchg [r8+4], edx
0x18000c966  jnz     short loc_18000C95B
0x18000c968  not     eax
0x18000c96a  and     eax, r9d
0x18000c96d  jmp     short loc_18000C972
0x18000c96f  mov     eax, r9d
0x18000c972  test    bpl, al
0x18000c975  jz      short loc_18000C98B
0x18000c977  mov     [rsp+0A8h+var_78], r10d
0x18000c97c  lea     rdx, [rsp+0A8h+var_70]
0x18000c981  mov     [rsp+0A8h+var_74], 10002h
0x18000c989  jmp     short loc_18000C990
0x18000c98b  lea     rdx, [rsp+0A8h+var_78]
0x18000c990  test    r14b, al
0x18000c993  jz      short loc_18000C9A3
0x18000c995  mov     [rdx], r10d
0x18000c998  mov     dword ptr [rdx+4], 10006h
0x18000c99f  add     rdx, 8
0x18000c9a3  test    al, 4
0x18000c9a5  jz      short loc_18000C9B5
0x18000c9a7  mov     [rdx], r10d
0x18000c9aa  mov     dword ptr [rdx+4], 10003h
0x18000c9b1  add     rdx, 8
0x18000c9b5  cmp     eax, 8
0x18000c9b8  jb      short loc_18000C9C8
0x18000c9ba  mov     [rdx], r10d
0x18000c9bd  mov     dword ptr [rdx+4], 10007h
0x18000c9c4  add     rdx, 8
0x18000c9c8  mov     r8d, ecx
0x18000c9cb  shr     r8d, 5
0x18000c9cf  test    r15d, r8d
0x18000c9d2  jz      short loc_18000C9F4
0x18000c9d4  and     r8w, r15w; unsigned __int64
0x18000c9d8  mov     [rdx], r10d
0x18000c9db  mov     eax, ecx
0x18000c9dd  mov     [rdx+6], r8w
0x18000c9e2  shr     eax, 0Eh
0x18000c9e5  and     ax, bp
0x18000c9e8  shl     ax, 2
0x18000c9ec  mov     [rdx+4], ax
0x18000c9f0  add     rdx, 8
0x18000c9f4  mov     eax, ecx
0x18000c9f6  shr     eax, 0Fh
0x18000c9f9  test    al, 7Fh
0x18000c9fb  jz      short loc_18000CA1D
0x18000c9fd  shr     ecx, 16h
0x18000ca00  and     ax, 7Fh
0x18000ca04  and     cx, bp
0x18000ca07  mov     [rdx], r10d
0x18000ca0a  shl     cx, 2
0x18000ca0e  add     cx, bp
0x18000ca11  mov     [rdx+6], ax
0x18000ca15  mov     [rdx+4], cx
0x18000ca19  add     rdx, 8
0x18000ca1d  lea     rax, [rsp+0A8h+var_78]
0x18000ca22  sub     rdx, rax
0x18000ca25  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x18000ca29  test    rdx, rdx
0x18000ca2c  jle     short loc_18000CA38
0x18000ca2e  lea     rcx, [rsp+0A8h+var_78]; this
0x18000ca33  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x18000ca38  add     rbx, 10h
0x18000ca3c  jmp     loc_18000C91E
0x18000ca41  mov     rax, [rsi+20h]
0x18000ca45  mov     [rsi+28h], rax
0x18000ca49  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000ca50  test    rax, rax
0x18000ca53  jnz     short loc_18000CA61
0x18000ca55  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000ca5c  test    rax, rax
0x18000ca5f  jz      short loc_18000CA73
0x18000ca61  xor     r9d, r9d
0x18000ca64  xor     r8d, r8d
0x18000ca67  mov     edx, 0FEh
0x18000ca6c  xor     ecx, ecx
0x18000ca6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca73  mov     rcx, [rsp+0A8h+var_48]
0x18000ca78  xor     rcx, rsp; StackCookie
0x18000ca7b  call    __security_check_cookie
0x18000ca80  add     rsp, 78h
0x18000ca84  pop     r15
0x18000ca86  pop     r14
0x18000ca88  pop     rdi
0x18000ca89  pop     rsi
0x18000ca8a  pop     rbp
0x18000ca8b  pop     rbx
0x18000ca8c  retn
```
