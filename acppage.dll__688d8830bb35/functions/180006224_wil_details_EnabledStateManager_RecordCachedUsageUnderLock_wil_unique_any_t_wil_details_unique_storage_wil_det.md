# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x180006224`
- end: `0x1800063d9`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `437`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180005dfc`
- `0x180008c70`
- `0x180008cd0`

## callees

- `0x180006224`
- `0x180008024`
- `0x180016280`
- `0x180017010`

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
0x180006224  push    rbx
0x180006226  push    rbp
0x180006227  push    rsi
0x180006228  push    rdi
0x180006229  push    r14
0x18000622b  push    r15
0x18000622d  sub     rsp, 78h
0x180006231  mov     rax, cs:__security_cookie
0x180006238  xor     rax, rsp
0x18000623b  mov     [rsp+0A8h+var_48], rax
0x180006240  mov     rdi, [rcx+28h]
0x180006244  mov     rsi, rcx
0x180006247  mov     rbx, [rcx+20h]
0x18000624b  mov     rax, rdi
0x18000624e  sub     rax, rbx
0x180006251  cmp     rax, 10h
0x180006255  jb      loc_1800063BF
0x18000625b  mov     ebp, 1
0x180006260  mov     r15d, 1FFh
0x180006266  lea     r14d, [rbp+1]
0x18000626a  cmp     rbx, rdi
0x18000626d  jz      loc_18000638D
0x180006273  mov     r8, [rbx+8]
0x180006277  mov     r10d, [rbx]
0x18000627a  prefetchw byte ptr [r8]
0x18000627e  mov     eax, [r8]
0x180006281  mov     ecx, eax
0x180006283  and     ecx, 0FFC0401Eh
0x180006289  lock cmpxchg [r8], ecx
0x18000628e  jnz     short loc_180006281
0x180006290  mov     r9d, eax
0x180006293  mov     ecx, eax
0x180006295  shr     r9d, 1
0x180006298  and     r9d, 0Fh
0x18000629c  jz      short loc_1800062BB
0x18000629e  prefetchw byte ptr [r8+4]
0x1800062a3  mov     eax, [r8+4]
0x1800062a7  mov     edx, eax
0x1800062a9  or      edx, r9d
0x1800062ac  lock cmpxchg [r8+4], edx
0x1800062b2  jnz     short loc_1800062A7
0x1800062b4  not     eax
0x1800062b6  and     eax, r9d
0x1800062b9  jmp     short loc_1800062BE
0x1800062bb  mov     eax, r9d
0x1800062be  test    bpl, al
0x1800062c1  jz      short loc_1800062D7
0x1800062c3  mov     [rsp+0A8h+var_78], r10d
0x1800062c8  lea     rdx, [rsp+0A8h+var_70]
0x1800062cd  mov     [rsp+0A8h+var_74], 10002h
0x1800062d5  jmp     short loc_1800062DC
0x1800062d7  lea     rdx, [rsp+0A8h+var_78]
0x1800062dc  test    r14b, al
0x1800062df  jz      short loc_1800062EF
0x1800062e1  mov     [rdx], r10d
0x1800062e4  mov     dword ptr [rdx+4], 10006h
0x1800062eb  add     rdx, 8
0x1800062ef  test    al, 4
0x1800062f1  jz      short loc_180006301
0x1800062f3  mov     [rdx], r10d
0x1800062f6  mov     dword ptr [rdx+4], 10003h
0x1800062fd  add     rdx, 8
0x180006301  cmp     eax, 8
0x180006304  jb      short loc_180006314
0x180006306  mov     [rdx], r10d
0x180006309  mov     dword ptr [rdx+4], 10007h
0x180006310  add     rdx, 8
0x180006314  mov     r8d, ecx
0x180006317  shr     r8d, 5
0x18000631b  test    r15d, r8d
0x18000631e  jz      short loc_180006340
0x180006320  and     r8w, r15w; unsigned __int64
0x180006324  mov     [rdx], r10d
0x180006327  mov     eax, ecx
0x180006329  mov     [rdx+6], r8w
0x18000632e  shr     eax, 0Eh
0x180006331  and     ax, bp
0x180006334  shl     ax, 2
0x180006338  mov     [rdx+4], ax
0x18000633c  add     rdx, 8
0x180006340  mov     eax, ecx
0x180006342  shr     eax, 0Fh
0x180006345  test    al, 7Fh
0x180006347  jz      short loc_180006369
0x180006349  shr     ecx, 16h
0x18000634c  and     ax, 7Fh
0x180006350  and     cx, bp
0x180006353  mov     [rdx], r10d
0x180006356  shl     cx, 2
0x18000635a  add     cx, bp
0x18000635d  mov     [rdx+6], ax
0x180006361  mov     [rdx+4], cx
0x180006365  add     rdx, 8
0x180006369  lea     rax, [rsp+0A8h+var_78]
0x18000636e  sub     rdx, rax
0x180006371  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x180006375  test    rdx, rdx
0x180006378  jle     short loc_180006384
0x18000637a  lea     rcx, [rsp+0A8h+var_78]; this
0x18000637f  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x180006384  add     rbx, 10h
0x180006388  jmp     loc_18000626A
0x18000638d  mov     rax, [rsi+20h]
0x180006391  mov     [rsi+28h], rax
0x180006395  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000639c  test    rax, rax
0x18000639f  jnz     short loc_1800063AD
0x1800063a1  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x1800063a8  test    rax, rax
0x1800063ab  jz      short loc_1800063BF
0x1800063ad  xor     r9d, r9d
0x1800063b0  xor     r8d, r8d
0x1800063b3  mov     edx, 0FEh
0x1800063b8  xor     ecx, ecx
0x1800063ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063bf  mov     rcx, [rsp+0A8h+var_48]
0x1800063c4  xor     rcx, rsp; StackCookie
0x1800063c7  call    __security_check_cookie
0x1800063cc  add     rsp, 78h
0x1800063d0  pop     r15
0x1800063d2  pop     r14
0x1800063d4  pop     rdi
0x1800063d5  pop     rsi
0x1800063d6  pop     rbp
0x1800063d7  pop     rbx
0x1800063d8  retn
```
