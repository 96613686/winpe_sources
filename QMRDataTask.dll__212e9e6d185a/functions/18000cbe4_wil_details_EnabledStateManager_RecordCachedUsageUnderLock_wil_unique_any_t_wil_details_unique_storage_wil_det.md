# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x18000cbe4`
- end: `0x18000cd9b`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `439`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180004580`
- `0x1800046c0`
- `0x18000c1bc`

## callees

- `0x18000cbe4`
- `0x180011104`
- `0x180014310`
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
0x18000cbe4  push    rbx
0x18000cbe6  push    rbp
0x18000cbe7  push    rsi
0x18000cbe8  push    rdi
0x18000cbe9  push    r14
0x18000cbeb  push    r15
0x18000cbed  sub     rsp, 78h
0x18000cbf1  mov     rax, cs:__security_cookie
0x18000cbf8  xor     rax, rsp
0x18000cbfb  mov     [rsp+0A8h+var_48], rax
0x18000cc00  mov     rsi, rcx
0x18000cc03  mov     rbx, [rcx+20h]
0x18000cc07  mov     rdi, [rcx+28h]
0x18000cc0b  mov     rax, rdi
0x18000cc0e  sub     rax, rbx
0x18000cc11  cmp     rax, 10h
0x18000cc15  jb      loc_18000CD81
0x18000cc1b  mov     ebp, 1
0x18000cc20  lea     r14d, [rbp+1]
0x18000cc24  mov     r15d, 1FFh
0x18000cc2a  cmp     rbx, rdi
0x18000cc2d  jz      loc_18000CD4E
0x18000cc33  mov     r8, [rbx+8]
0x18000cc37  mov     r10d, [rbx]
0x18000cc3a  prefetchw byte ptr [r8]
0x18000cc3e  mov     eax, [r8]
0x18000cc41  mov     ecx, eax
0x18000cc43  and     ecx, 0FFC0401Eh
0x18000cc49  lock cmpxchg [r8], ecx
0x18000cc4e  jnz     short loc_18000CC41
0x18000cc50  mov     ecx, eax
0x18000cc52  mov     r9d, eax
0x18000cc55  shr     r9d, 1
0x18000cc58  and     r9d, 0Fh
0x18000cc5c  jz      short loc_18000CC7B
0x18000cc5e  prefetchw byte ptr [r8+4]
0x18000cc63  mov     eax, [r8+4]
0x18000cc67  mov     edx, eax
0x18000cc69  or      edx, r9d
0x18000cc6c  lock cmpxchg [r8+4], edx
0x18000cc72  jnz     short loc_18000CC67
0x18000cc74  not     eax
0x18000cc76  and     eax, r9d
0x18000cc79  jmp     short loc_18000CC7E
0x18000cc7b  mov     eax, r9d
0x18000cc7e  test    bpl, al
0x18000cc81  jz      short loc_18000CC97
0x18000cc83  mov     [rsp+0A8h+var_78], r10d
0x18000cc88  mov     [rsp+0A8h+var_74], 10002h
0x18000cc90  lea     rdx, [rsp+0A8h+var_70]
0x18000cc95  jmp     short loc_18000CC9C
0x18000cc97  lea     rdx, [rsp+0A8h+var_78]
0x18000cc9c  test    r14b, al
0x18000cc9f  jz      short loc_18000CCAF
0x18000cca1  mov     [rdx], r10d
0x18000cca4  mov     dword ptr [rdx+4], 10006h
0x18000ccab  add     rdx, 8
0x18000ccaf  test    al, 4
0x18000ccb1  jz      short loc_18000CCC1
0x18000ccb3  mov     [rdx], r10d
0x18000ccb6  mov     dword ptr [rdx+4], 10003h
0x18000ccbd  add     rdx, 8
0x18000ccc1  cmp     eax, 8
0x18000ccc4  jb      short loc_18000CCD4
0x18000ccc6  mov     [rdx], r10d
0x18000ccc9  mov     dword ptr [rdx+4], 10007h
0x18000ccd0  add     rdx, 8
0x18000ccd4  mov     r8d, ecx
0x18000ccd7  shr     r8d, 5
0x18000ccdb  test    r15d, r8d
0x18000ccde  jz      short loc_18000CD00
0x18000cce0  mov     [rdx], r10d
0x18000cce3  mov     eax, ecx
0x18000cce5  shr     eax, 0Eh
0x18000cce8  and     ax, bp
0x18000cceb  shl     ax, 2
0x18000ccef  mov     [rdx+4], ax
0x18000ccf3  and     r8w, r15w; unsigned __int64
0x18000ccf7  mov     [rdx+6], r8w
0x18000ccfc  add     rdx, 8
0x18000cd00  mov     eax, ecx
0x18000cd02  shr     eax, 0Fh
0x18000cd05  test    al, 7Fh
0x18000cd07  jz      short loc_18000CD29
0x18000cd09  mov     [rdx], r10d
0x18000cd0c  shr     ecx, 16h
0x18000cd0f  and     cx, bp
0x18000cd12  shl     cx, 2
0x18000cd16  add     cx, bp
0x18000cd19  mov     [rdx+4], cx
0x18000cd1d  and     ax, 7Fh
0x18000cd21  mov     [rdx+6], ax
0x18000cd25  add     rdx, 8
0x18000cd29  lea     rax, [rsp+0A8h+var_78]
0x18000cd2e  sub     rdx, rax
0x18000cd31  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x18000cd35  test    rdx, rdx
0x18000cd38  jle     short loc_18000CD45
0x18000cd3a  lea     rcx, [rsp+0A8h+var_78]; this
0x18000cd3f  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x18000cd44  nop
0x18000cd45  add     rbx, 10h
0x18000cd49  jmp     loc_18000CC2A
0x18000cd4e  mov     rax, [rsi+20h]
0x18000cd52  mov     [rsi+28h], rax
0x18000cd56  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000cd5d  test    rax, rax
0x18000cd60  jnz     short loc_18000CD6E
0x18000cd62  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000cd69  test    rax, rax
0x18000cd6c  jz      short loc_18000CD81
0x18000cd6e  xor     r9d, r9d
0x18000cd71  xor     r8d, r8d
0x18000cd74  mov     edx, 0FEh
0x18000cd79  xor     ecx, ecx
0x18000cd7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd80  nop
0x18000cd81  mov     rcx, [rsp+0A8h+var_48]
0x18000cd86  xor     rcx, rsp; StackCookie
0x18000cd89  call    __security_check_cookie
0x18000cd8e  add     rsp, 78h
0x18000cd92  pop     r15
0x18000cd94  pop     r14
0x18000cd96  pop     rdi
0x18000cd97  pop     rsi
0x18000cd98  pop     rbp
0x18000cd99  pop     rbx
0x18000cd9a  retn
```
