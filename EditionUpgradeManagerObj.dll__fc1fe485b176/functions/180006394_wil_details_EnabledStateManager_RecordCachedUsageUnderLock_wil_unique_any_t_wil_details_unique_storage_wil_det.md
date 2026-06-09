# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x180006394`
- end: `0x180006549`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `437`
- prototype: `__int64 (__fastcall *__fastcall(__int64))(_QWORD, __int64, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180005f4c`
- `0x180008dc0`
- `0x180008e20`

## callees

- `0x180001ac0`
- `0x180006394`
- `0x180008454`
- `0x180023010`

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
0x180006394  push    rbx
0x180006396  push    rbp
0x180006397  push    rsi
0x180006398  push    rdi
0x180006399  push    r14
0x18000639b  push    r15
0x18000639d  sub     rsp, 78h
0x1800063a1  mov     rax, cs:__security_cookie
0x1800063a8  xor     rax, rsp
0x1800063ab  mov     [rsp+0A8h+var_48], rax
0x1800063b0  mov     rdi, [rcx+28h]
0x1800063b4  mov     rsi, rcx
0x1800063b7  mov     rbx, [rcx+20h]
0x1800063bb  mov     rax, rdi
0x1800063be  sub     rax, rbx
0x1800063c1  cmp     rax, 10h
0x1800063c5  jb      loc_18000652F
0x1800063cb  mov     ebp, 1
0x1800063d0  mov     r15d, 1FFh
0x1800063d6  lea     r14d, [rbp+1]
0x1800063da  cmp     rbx, rdi
0x1800063dd  jz      loc_1800064FD
0x1800063e3  mov     r8, [rbx+8]
0x1800063e7  mov     r10d, [rbx]
0x1800063ea  prefetchw byte ptr [r8]
0x1800063ee  mov     eax, [r8]
0x1800063f1  mov     ecx, eax
0x1800063f3  and     ecx, 0FFC0401Eh
0x1800063f9  lock cmpxchg [r8], ecx
0x1800063fe  jnz     short loc_1800063F1
0x180006400  mov     r9d, eax
0x180006403  mov     ecx, eax
0x180006405  shr     r9d, 1
0x180006408  and     r9d, 0Fh
0x18000640c  jz      short loc_18000642B
0x18000640e  prefetchw byte ptr [r8+4]
0x180006413  mov     eax, [r8+4]
0x180006417  mov     edx, eax
0x180006419  or      edx, r9d
0x18000641c  lock cmpxchg [r8+4], edx
0x180006422  jnz     short loc_180006417
0x180006424  not     eax
0x180006426  and     eax, r9d
0x180006429  jmp     short loc_18000642E
0x18000642b  mov     eax, r9d
0x18000642e  test    bpl, al
0x180006431  jz      short loc_180006447
0x180006433  mov     [rsp+0A8h+var_78], r10d
0x180006438  lea     rdx, [rsp+0A8h+var_70]
0x18000643d  mov     [rsp+0A8h+var_74], 10002h
0x180006445  jmp     short loc_18000644C
0x180006447  lea     rdx, [rsp+0A8h+var_78]
0x18000644c  test    r14b, al
0x18000644f  jz      short loc_18000645F
0x180006451  mov     [rdx], r10d
0x180006454  mov     dword ptr [rdx+4], 10006h
0x18000645b  add     rdx, 8
0x18000645f  test    al, 4
0x180006461  jz      short loc_180006471
0x180006463  mov     [rdx], r10d
0x180006466  mov     dword ptr [rdx+4], 10003h
0x18000646d  add     rdx, 8
0x180006471  cmp     eax, 8
0x180006474  jb      short loc_180006484
0x180006476  mov     [rdx], r10d
0x180006479  mov     dword ptr [rdx+4], 10007h
0x180006480  add     rdx, 8
0x180006484  mov     r8d, ecx
0x180006487  shr     r8d, 5
0x18000648b  test    r15d, r8d
0x18000648e  jz      short loc_1800064B0
0x180006490  and     r8w, r15w; unsigned __int64
0x180006494  mov     [rdx], r10d
0x180006497  mov     eax, ecx
0x180006499  mov     [rdx+6], r8w
0x18000649e  shr     eax, 0Eh
0x1800064a1  and     ax, bp
0x1800064a4  shl     ax, 2
0x1800064a8  mov     [rdx+4], ax
0x1800064ac  add     rdx, 8
0x1800064b0  mov     eax, ecx
0x1800064b2  shr     eax, 0Fh
0x1800064b5  test    al, 7Fh
0x1800064b7  jz      short loc_1800064D9
0x1800064b9  shr     ecx, 16h
0x1800064bc  and     ax, 7Fh
0x1800064c0  and     cx, bp
0x1800064c3  mov     [rdx], r10d
0x1800064c6  shl     cx, 2
0x1800064ca  add     cx, bp
0x1800064cd  mov     [rdx+6], ax
0x1800064d1  mov     [rdx+4], cx
0x1800064d5  add     rdx, 8
0x1800064d9  lea     rax, [rsp+0A8h+var_78]
0x1800064de  sub     rdx, rax
0x1800064e1  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x1800064e5  test    rdx, rdx
0x1800064e8  jle     short loc_1800064F4
0x1800064ea  lea     rcx, [rsp+0A8h+var_78]; this
0x1800064ef  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x1800064f4  add     rbx, 10h
0x1800064f8  jmp     loc_1800063DA
0x1800064fd  mov     rax, [rsi+20h]
0x180006501  mov     [rsi+28h], rax
0x180006505  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000650c  test    rax, rax
0x18000650f  jnz     short loc_18000651D
0x180006511  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180006518  test    rax, rax
0x18000651b  jz      short loc_18000652F
0x18000651d  xor     r9d, r9d
0x180006520  xor     r8d, r8d
0x180006523  mov     edx, 0FEh
0x180006528  xor     ecx, ecx
0x18000652a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000652f  mov     rcx, [rsp+0A8h+var_48]
0x180006534  xor     rcx, rsp; StackCookie
0x180006537  call    __security_check_cookie
0x18000653c  add     rsp, 78h
0x180006540  pop     r15
0x180006542  pop     r14
0x180006544  pop     rdi
0x180006545  pop     rsi
0x180006546  pop     rbp
0x180006547  pop     rbx
0x180006548  retn
```
