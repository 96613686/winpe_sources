# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x18000cfb0`
- end: `0x18000d167`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `439`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000cb64`
- `0x180017750`
- `0x1800177b0`

## callees

- `0x1800028f0`
- `0x18000cfb0`
- `0x18000f8e4`
- `0x18002a010`

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
0x18000cfb0  push    rbx
0x18000cfb2  push    rbp
0x18000cfb3  push    rsi
0x18000cfb4  push    rdi
0x18000cfb5  push    r14
0x18000cfb7  push    r15
0x18000cfb9  sub     rsp, 78h
0x18000cfbd  mov     rax, cs:__security_cookie
0x18000cfc4  xor     rax, rsp
0x18000cfc7  mov     [rsp+0A8h+var_48], rax
0x18000cfcc  mov     rsi, rcx
0x18000cfcf  mov     rbx, [rcx+20h]
0x18000cfd3  mov     rdi, [rcx+28h]
0x18000cfd7  mov     rax, rdi
0x18000cfda  sub     rax, rbx
0x18000cfdd  cmp     rax, 10h
0x18000cfe1  jb      loc_18000D14D
0x18000cfe7  mov     ebp, 1
0x18000cfec  lea     r14d, [rbp+1]
0x18000cff0  mov     r15d, 1FFh
0x18000cff6  cmp     rbx, rdi
0x18000cff9  jz      loc_18000D11A
0x18000cfff  mov     r8, [rbx+8]
0x18000d003  mov     r10d, [rbx]
0x18000d006  prefetchw byte ptr [r8]
0x18000d00a  mov     eax, [r8]
0x18000d00d  mov     ecx, eax
0x18000d00f  and     ecx, 0FFC0401Eh
0x18000d015  lock cmpxchg [r8], ecx
0x18000d01a  jnz     short loc_18000D00D
0x18000d01c  mov     ecx, eax
0x18000d01e  mov     r9d, eax
0x18000d021  shr     r9d, 1
0x18000d024  and     r9d, 0Fh
0x18000d028  jz      short loc_18000D047
0x18000d02a  prefetchw byte ptr [r8+4]
0x18000d02f  mov     eax, [r8+4]
0x18000d033  mov     edx, eax
0x18000d035  or      edx, r9d
0x18000d038  lock cmpxchg [r8+4], edx
0x18000d03e  jnz     short loc_18000D033
0x18000d040  not     eax
0x18000d042  and     eax, r9d
0x18000d045  jmp     short loc_18000D04A
0x18000d047  mov     eax, r9d
0x18000d04a  test    bpl, al
0x18000d04d  jz      short loc_18000D063
0x18000d04f  mov     [rsp+0A8h+var_78], r10d
0x18000d054  mov     [rsp+0A8h+var_74], 10002h
0x18000d05c  lea     rdx, [rsp+0A8h+var_70]
0x18000d061  jmp     short loc_18000D068
0x18000d063  lea     rdx, [rsp+0A8h+var_78]
0x18000d068  test    r14b, al
0x18000d06b  jz      short loc_18000D07B
0x18000d06d  mov     [rdx], r10d
0x18000d070  mov     dword ptr [rdx+4], 10006h
0x18000d077  add     rdx, 8
0x18000d07b  test    al, 4
0x18000d07d  jz      short loc_18000D08D
0x18000d07f  mov     [rdx], r10d
0x18000d082  mov     dword ptr [rdx+4], 10003h
0x18000d089  add     rdx, 8
0x18000d08d  cmp     eax, 8
0x18000d090  jb      short loc_18000D0A0
0x18000d092  mov     [rdx], r10d
0x18000d095  mov     dword ptr [rdx+4], 10007h
0x18000d09c  add     rdx, 8
0x18000d0a0  mov     r8d, ecx
0x18000d0a3  shr     r8d, 5
0x18000d0a7  test    r15d, r8d
0x18000d0aa  jz      short loc_18000D0CC
0x18000d0ac  mov     [rdx], r10d
0x18000d0af  mov     eax, ecx
0x18000d0b1  shr     eax, 0Eh
0x18000d0b4  and     ax, bp
0x18000d0b7  shl     ax, 2
0x18000d0bb  mov     [rdx+4], ax
0x18000d0bf  and     r8w, r15w; unsigned __int64
0x18000d0c3  mov     [rdx+6], r8w
0x18000d0c8  add     rdx, 8
0x18000d0cc  mov     eax, ecx
0x18000d0ce  shr     eax, 0Fh
0x18000d0d1  test    al, 7Fh
0x18000d0d3  jz      short loc_18000D0F5
0x18000d0d5  mov     [rdx], r10d
0x18000d0d8  shr     ecx, 16h
0x18000d0db  and     cx, bp
0x18000d0de  shl     cx, 2
0x18000d0e2  add     cx, bp
0x18000d0e5  mov     [rdx+4], cx
0x18000d0e9  and     ax, 7Fh
0x18000d0ed  mov     [rdx+6], ax
0x18000d0f1  add     rdx, 8
0x18000d0f5  lea     rax, [rsp+0A8h+var_78]
0x18000d0fa  sub     rdx, rax
0x18000d0fd  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x18000d101  test    rdx, rdx
0x18000d104  jle     short loc_18000D111
0x18000d106  lea     rcx, [rsp+0A8h+var_78]; this
0x18000d10b  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x18000d110  nop
0x18000d111  add     rbx, 10h
0x18000d115  jmp     loc_18000CFF6
0x18000d11a  mov     rax, [rsi+20h]
0x18000d11e  mov     [rsi+28h], rax
0x18000d122  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000d129  test    rax, rax
0x18000d12c  jnz     short loc_18000D13A
0x18000d12e  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000d135  test    rax, rax
0x18000d138  jz      short loc_18000D14D
0x18000d13a  xor     r9d, r9d
0x18000d13d  xor     r8d, r8d
0x18000d140  mov     edx, 0FEh
0x18000d145  xor     ecx, ecx
0x18000d147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d14c  nop
0x18000d14d  mov     rcx, [rsp+0A8h+var_48]
0x18000d152  xor     rcx, rsp; StackCookie
0x18000d155  call    __security_check_cookie
0x18000d15a  add     rsp, 78h
0x18000d15e  pop     r15
0x18000d160  pop     r14
0x18000d162  pop     rdi
0x18000d163  pop     rsi
0x18000d164  pop     rbp
0x18000d165  pop     rbx
0x18000d166  retn
```
