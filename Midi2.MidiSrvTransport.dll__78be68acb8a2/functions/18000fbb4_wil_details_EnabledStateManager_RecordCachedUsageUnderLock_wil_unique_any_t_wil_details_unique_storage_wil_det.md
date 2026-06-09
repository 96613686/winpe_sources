# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x18000fbb4`
- end: `0x18000fd6b`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `439`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000cc80`
- `0x18000cce0`
- `0x18000f8e8`

## callees

- `0x180002470`
- `0x18000fbb4`
- `0x18001115c`
- `0x180015010`

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
0x18000fbb4  push    rbx
0x18000fbb6  push    rbp
0x18000fbb7  push    rsi
0x18000fbb8  push    rdi
0x18000fbb9  push    r14
0x18000fbbb  push    r15
0x18000fbbd  sub     rsp, 78h
0x18000fbc1  mov     rax, cs:__security_cookie
0x18000fbc8  xor     rax, rsp
0x18000fbcb  mov     [rsp+0A8h+var_48], rax
0x18000fbd0  mov     rsi, rcx
0x18000fbd3  mov     rbx, [rcx+20h]
0x18000fbd7  mov     rdi, [rcx+28h]
0x18000fbdb  mov     rax, rdi
0x18000fbde  sub     rax, rbx
0x18000fbe1  cmp     rax, 10h
0x18000fbe5  jb      loc_18000FD51
0x18000fbeb  mov     ebp, 1
0x18000fbf0  lea     r14d, [rbp+1]
0x18000fbf4  mov     r15d, 1FFh
0x18000fbfa  cmp     rbx, rdi
0x18000fbfd  jz      loc_18000FD1E
0x18000fc03  mov     r8, [rbx+8]
0x18000fc07  mov     r10d, [rbx]
0x18000fc0a  prefetchw byte ptr [r8]
0x18000fc0e  mov     eax, [r8]
0x18000fc11  mov     ecx, eax
0x18000fc13  and     ecx, 0FFC0401Eh
0x18000fc19  lock cmpxchg [r8], ecx
0x18000fc1e  jnz     short loc_18000FC11
0x18000fc20  mov     ecx, eax
0x18000fc22  mov     r9d, eax
0x18000fc25  shr     r9d, 1
0x18000fc28  and     r9d, 0Fh
0x18000fc2c  jz      short loc_18000FC4B
0x18000fc2e  prefetchw byte ptr [r8+4]
0x18000fc33  mov     eax, [r8+4]
0x18000fc37  mov     edx, eax
0x18000fc39  or      edx, r9d
0x18000fc3c  lock cmpxchg [r8+4], edx
0x18000fc42  jnz     short loc_18000FC37
0x18000fc44  not     eax
0x18000fc46  and     eax, r9d
0x18000fc49  jmp     short loc_18000FC4E
0x18000fc4b  mov     eax, r9d
0x18000fc4e  test    bpl, al
0x18000fc51  jz      short loc_18000FC67
0x18000fc53  mov     [rsp+0A8h+var_78], r10d
0x18000fc58  mov     [rsp+0A8h+var_74], 10002h
0x18000fc60  lea     rdx, [rsp+0A8h+var_70]
0x18000fc65  jmp     short loc_18000FC6C
0x18000fc67  lea     rdx, [rsp+0A8h+var_78]
0x18000fc6c  test    r14b, al
0x18000fc6f  jz      short loc_18000FC7F
0x18000fc71  mov     [rdx], r10d
0x18000fc74  mov     dword ptr [rdx+4], 10006h
0x18000fc7b  add     rdx, 8
0x18000fc7f  test    al, 4
0x18000fc81  jz      short loc_18000FC91
0x18000fc83  mov     [rdx], r10d
0x18000fc86  mov     dword ptr [rdx+4], 10003h
0x18000fc8d  add     rdx, 8
0x18000fc91  cmp     eax, 8
0x18000fc94  jb      short loc_18000FCA4
0x18000fc96  mov     [rdx], r10d
0x18000fc99  mov     dword ptr [rdx+4], 10007h
0x18000fca0  add     rdx, 8
0x18000fca4  mov     r8d, ecx
0x18000fca7  shr     r8d, 5
0x18000fcab  test    r15d, r8d
0x18000fcae  jz      short loc_18000FCD0
0x18000fcb0  mov     [rdx], r10d
0x18000fcb3  mov     eax, ecx
0x18000fcb5  shr     eax, 0Eh
0x18000fcb8  and     ax, bp
0x18000fcbb  shl     ax, 2
0x18000fcbf  mov     [rdx+4], ax
0x18000fcc3  and     r8w, r15w; unsigned __int64
0x18000fcc7  mov     [rdx+6], r8w
0x18000fccc  add     rdx, 8
0x18000fcd0  mov     eax, ecx
0x18000fcd2  shr     eax, 0Fh
0x18000fcd5  test    al, 7Fh
0x18000fcd7  jz      short loc_18000FCF9
0x18000fcd9  mov     [rdx], r10d
0x18000fcdc  shr     ecx, 16h
0x18000fcdf  and     cx, bp
0x18000fce2  shl     cx, 2
0x18000fce6  add     cx, bp
0x18000fce9  mov     [rdx+4], cx
0x18000fced  and     ax, 7Fh
0x18000fcf1  mov     [rdx+6], ax
0x18000fcf5  add     rdx, 8
0x18000fcf9  lea     rax, [rsp+0A8h+var_78]
0x18000fcfe  sub     rdx, rax
0x18000fd01  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x18000fd05  test    rdx, rdx
0x18000fd08  jle     short loc_18000FD15
0x18000fd0a  lea     rcx, [rsp+0A8h+var_78]; this
0x18000fd0f  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x18000fd14  nop
0x18000fd15  add     rbx, 10h
0x18000fd19  jmp     loc_18000FBFA
0x18000fd1e  mov     rax, [rsi+20h]
0x18000fd22  mov     [rsi+28h], rax
0x18000fd26  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000fd2d  test    rax, rax
0x18000fd30  jnz     short loc_18000FD3E
0x18000fd32  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000fd39  test    rax, rax
0x18000fd3c  jz      short loc_18000FD51
0x18000fd3e  xor     r9d, r9d
0x18000fd41  xor     r8d, r8d
0x18000fd44  mov     edx, 0FEh
0x18000fd49  xor     ecx, ecx
0x18000fd4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd50  nop
0x18000fd51  mov     rcx, [rsp+0A8h+var_48]
0x18000fd56  xor     rcx, rsp; StackCookie
0x18000fd59  call    __security_check_cookie
0x18000fd5e  add     rsp, 78h
0x18000fd62  pop     r15
0x18000fd64  pop     r14
0x18000fd66  pop     rdi
0x18000fd67  pop     rsi
0x18000fd68  pop     rbp
0x18000fd69  pop     rbx
0x18000fd6a  retn
```
