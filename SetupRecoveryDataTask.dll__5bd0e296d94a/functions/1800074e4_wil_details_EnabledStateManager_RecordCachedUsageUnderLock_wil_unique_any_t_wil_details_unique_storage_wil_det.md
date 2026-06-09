# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x1800074e4`
- end: `0x18000769b`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `439`
- prototype: `__int64 (__fastcall *__fastcall(__int64))(_QWORD, __int64, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180002140`
- `0x180002280`
- `0x1800070a0`

## callees

- `0x1800074e4`
- `0x18000a060`
- `0x18000c610`
- `0x18000d010`

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
0x1800074e4  push    rbx
0x1800074e6  push    rbp
0x1800074e7  push    rsi
0x1800074e8  push    rdi
0x1800074e9  push    r14
0x1800074eb  push    r15
0x1800074ed  sub     rsp, 78h
0x1800074f1  mov     rax, cs:__security_cookie
0x1800074f8  xor     rax, rsp
0x1800074fb  mov     [rsp+0A8h+var_48], rax
0x180007500  mov     rsi, rcx
0x180007503  mov     rbx, [rcx+20h]
0x180007507  mov     rdi, [rcx+28h]
0x18000750b  mov     rax, rdi
0x18000750e  sub     rax, rbx
0x180007511  cmp     rax, 10h
0x180007515  jb      loc_180007681
0x18000751b  mov     ebp, 1
0x180007520  lea     r14d, [rbp+1]
0x180007524  mov     r15d, 1FFh
0x18000752a  cmp     rbx, rdi
0x18000752d  jz      loc_18000764E
0x180007533  mov     r8, [rbx+8]
0x180007537  mov     r10d, [rbx]
0x18000753a  prefetchw byte ptr [r8]
0x18000753e  mov     eax, [r8]
0x180007541  mov     ecx, eax
0x180007543  and     ecx, 0FFC0401Eh
0x180007549  lock cmpxchg [r8], ecx
0x18000754e  jnz     short loc_180007541
0x180007550  mov     ecx, eax
0x180007552  mov     r9d, eax
0x180007555  shr     r9d, 1
0x180007558  and     r9d, 0Fh
0x18000755c  jz      short loc_18000757B
0x18000755e  prefetchw byte ptr [r8+4]
0x180007563  mov     eax, [r8+4]
0x180007567  mov     edx, eax
0x180007569  or      edx, r9d
0x18000756c  lock cmpxchg [r8+4], edx
0x180007572  jnz     short loc_180007567
0x180007574  not     eax
0x180007576  and     eax, r9d
0x180007579  jmp     short loc_18000757E
0x18000757b  mov     eax, r9d
0x18000757e  test    bpl, al
0x180007581  jz      short loc_180007597
0x180007583  mov     [rsp+0A8h+var_78], r10d
0x180007588  mov     [rsp+0A8h+var_74], 10002h
0x180007590  lea     rdx, [rsp+0A8h+var_70]
0x180007595  jmp     short loc_18000759C
0x180007597  lea     rdx, [rsp+0A8h+var_78]
0x18000759c  test    r14b, al
0x18000759f  jz      short loc_1800075AF
0x1800075a1  mov     [rdx], r10d
0x1800075a4  mov     dword ptr [rdx+4], 10006h
0x1800075ab  add     rdx, 8
0x1800075af  test    al, 4
0x1800075b1  jz      short loc_1800075C1
0x1800075b3  mov     [rdx], r10d
0x1800075b6  mov     dword ptr [rdx+4], 10003h
0x1800075bd  add     rdx, 8
0x1800075c1  cmp     eax, 8
0x1800075c4  jb      short loc_1800075D4
0x1800075c6  mov     [rdx], r10d
0x1800075c9  mov     dword ptr [rdx+4], 10007h
0x1800075d0  add     rdx, 8
0x1800075d4  mov     r8d, ecx
0x1800075d7  shr     r8d, 5
0x1800075db  test    r15d, r8d
0x1800075de  jz      short loc_180007600
0x1800075e0  mov     [rdx], r10d
0x1800075e3  mov     eax, ecx
0x1800075e5  shr     eax, 0Eh
0x1800075e8  and     ax, bp
0x1800075eb  shl     ax, 2
0x1800075ef  mov     [rdx+4], ax
0x1800075f3  and     r8w, r15w; unsigned __int64
0x1800075f7  mov     [rdx+6], r8w
0x1800075fc  add     rdx, 8
0x180007600  mov     eax, ecx
0x180007602  shr     eax, 0Fh
0x180007605  test    al, 7Fh
0x180007607  jz      short loc_180007629
0x180007609  mov     [rdx], r10d
0x18000760c  shr     ecx, 16h
0x18000760f  and     cx, bp
0x180007612  shl     cx, 2
0x180007616  add     cx, bp
0x180007619  mov     [rdx+4], cx
0x18000761d  and     ax, 7Fh
0x180007621  mov     [rdx+6], ax
0x180007625  add     rdx, 8
0x180007629  lea     rax, [rsp+0A8h+var_78]
0x18000762e  sub     rdx, rax
0x180007631  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x180007635  test    rdx, rdx
0x180007638  jle     short loc_180007645
0x18000763a  lea     rcx, [rsp+0A8h+var_78]; this
0x18000763f  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x180007644  nop
0x180007645  add     rbx, 10h
0x180007649  jmp     loc_18000752A
0x18000764e  mov     rax, [rsi+20h]
0x180007652  mov     [rsi+28h], rax
0x180007656  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000765d  test    rax, rax
0x180007660  jnz     short loc_18000766E
0x180007662  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180007669  test    rax, rax
0x18000766c  jz      short loc_180007681
0x18000766e  xor     r9d, r9d
0x180007671  xor     r8d, r8d
0x180007674  mov     edx, 0FEh
0x180007679  xor     ecx, ecx
0x18000767b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007680  nop
0x180007681  mov     rcx, [rsp+0A8h+var_48]
0x180007686  xor     rcx, rsp; StackCookie
0x180007689  call    __security_check_cookie
0x18000768e  add     rsp, 78h
0x180007692  pop     r15
0x180007694  pop     r14
0x180007696  pop     rdi
0x180007697  pop     rsi
0x180007698  pop     rbp
0x180007699  pop     rbx
0x18000769a  retn
```
