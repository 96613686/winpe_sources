# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x18000c604`
- end: `0x18000c7bb`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `439`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000a440`
- `0x18000a4a0`
- `0x18000c3f8`

## callees

- `0x180001ef0`
- `0x18000c604`
- `0x18000dcb8`
- `0x18000f010`

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
0x18000c604  push    rbx
0x18000c606  push    rbp
0x18000c607  push    rsi
0x18000c608  push    rdi
0x18000c609  push    r14
0x18000c60b  push    r15
0x18000c60d  sub     rsp, 78h
0x18000c611  mov     rax, cs:__security_cookie
0x18000c618  xor     rax, rsp
0x18000c61b  mov     [rsp+0A8h+var_48], rax
0x18000c620  mov     rsi, rcx
0x18000c623  mov     rbx, [rcx+20h]
0x18000c627  mov     rdi, [rcx+28h]
0x18000c62b  mov     rax, rdi
0x18000c62e  sub     rax, rbx
0x18000c631  cmp     rax, 10h
0x18000c635  jb      loc_18000C7A1
0x18000c63b  mov     ebp, 1
0x18000c640  lea     r14d, [rbp+1]
0x18000c644  mov     r15d, 1FFh
0x18000c64a  cmp     rbx, rdi
0x18000c64d  jz      loc_18000C76E
0x18000c653  mov     r8, [rbx+8]
0x18000c657  mov     r10d, [rbx]
0x18000c65a  prefetchw byte ptr [r8]
0x18000c65e  mov     eax, [r8]
0x18000c661  mov     ecx, eax
0x18000c663  and     ecx, 0FFC0401Eh
0x18000c669  lock cmpxchg [r8], ecx
0x18000c66e  jnz     short loc_18000C661
0x18000c670  mov     ecx, eax
0x18000c672  mov     r9d, eax
0x18000c675  shr     r9d, 1
0x18000c678  and     r9d, 0Fh
0x18000c67c  jz      short loc_18000C69B
0x18000c67e  prefetchw byte ptr [r8+4]
0x18000c683  mov     eax, [r8+4]
0x18000c687  mov     edx, eax
0x18000c689  or      edx, r9d
0x18000c68c  lock cmpxchg [r8+4], edx
0x18000c692  jnz     short loc_18000C687
0x18000c694  not     eax
0x18000c696  and     eax, r9d
0x18000c699  jmp     short loc_18000C69E
0x18000c69b  mov     eax, r9d
0x18000c69e  test    bpl, al
0x18000c6a1  jz      short loc_18000C6B7
0x18000c6a3  mov     [rsp+0A8h+var_78], r10d
0x18000c6a8  mov     [rsp+0A8h+var_74], 10002h
0x18000c6b0  lea     rdx, [rsp+0A8h+var_70]
0x18000c6b5  jmp     short loc_18000C6BC
0x18000c6b7  lea     rdx, [rsp+0A8h+var_78]
0x18000c6bc  test    r14b, al
0x18000c6bf  jz      short loc_18000C6CF
0x18000c6c1  mov     [rdx], r10d
0x18000c6c4  mov     dword ptr [rdx+4], 10006h
0x18000c6cb  add     rdx, 8
0x18000c6cf  test    al, 4
0x18000c6d1  jz      short loc_18000C6E1
0x18000c6d3  mov     [rdx], r10d
0x18000c6d6  mov     dword ptr [rdx+4], 10003h
0x18000c6dd  add     rdx, 8
0x18000c6e1  cmp     eax, 8
0x18000c6e4  jb      short loc_18000C6F4
0x18000c6e6  mov     [rdx], r10d
0x18000c6e9  mov     dword ptr [rdx+4], 10007h
0x18000c6f0  add     rdx, 8
0x18000c6f4  mov     r8d, ecx
0x18000c6f7  shr     r8d, 5
0x18000c6fb  test    r15d, r8d
0x18000c6fe  jz      short loc_18000C720
0x18000c700  mov     [rdx], r10d
0x18000c703  mov     eax, ecx
0x18000c705  shr     eax, 0Eh
0x18000c708  and     ax, bp
0x18000c70b  shl     ax, 2
0x18000c70f  mov     [rdx+4], ax
0x18000c713  and     r8w, r15w; unsigned __int64
0x18000c717  mov     [rdx+6], r8w
0x18000c71c  add     rdx, 8
0x18000c720  mov     eax, ecx
0x18000c722  shr     eax, 0Fh
0x18000c725  test    al, 7Fh
0x18000c727  jz      short loc_18000C749
0x18000c729  mov     [rdx], r10d
0x18000c72c  shr     ecx, 16h
0x18000c72f  and     cx, bp
0x18000c732  shl     cx, 2
0x18000c736  add     cx, bp
0x18000c739  mov     [rdx+4], cx
0x18000c73d  and     ax, 7Fh
0x18000c741  mov     [rdx+6], ax
0x18000c745  add     rdx, 8
0x18000c749  lea     rax, [rsp+0A8h+var_78]
0x18000c74e  sub     rdx, rax
0x18000c751  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x18000c755  test    rdx, rdx
0x18000c758  jle     short loc_18000C765
0x18000c75a  lea     rcx, [rsp+0A8h+var_78]; this
0x18000c75f  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x18000c764  nop
0x18000c765  add     rbx, 10h
0x18000c769  jmp     loc_18000C64A
0x18000c76e  mov     rax, [rsi+20h]
0x18000c772  mov     [rsi+28h], rax
0x18000c776  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000c77d  test    rax, rax
0x18000c780  jnz     short loc_18000C78E
0x18000c782  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000c789  test    rax, rax
0x18000c78c  jz      short loc_18000C7A1
0x18000c78e  xor     r9d, r9d
0x18000c791  xor     r8d, r8d
0x18000c794  mov     edx, 0FEh
0x18000c799  xor     ecx, ecx
0x18000c79b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7a0  nop
0x18000c7a1  mov     rcx, [rsp+0A8h+var_48]
0x18000c7a6  xor     rcx, rsp; StackCookie
0x18000c7a9  call    __security_check_cookie
0x18000c7ae  add     rsp, 78h
0x18000c7b2  pop     r15
0x18000c7b4  pop     r14
0x18000c7b6  pop     rdi
0x18000c7b7  pop     rsi
0x18000c7b8  pop     rbp
0x18000c7b9  pop     rbx
0x18000c7ba  retn
```
