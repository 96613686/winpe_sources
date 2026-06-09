# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x18002c5c4`
- end: `0x18002c77b`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `439`
- prototype: `__int64 (__fastcall *__fastcall(__int64))(_QWORD, __int64, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180026d30`
- `0x180026f50`
- `0x18002be60`

## callees

- `0x18002c5c4`
- `0x18002f834`
- `0x1800350e0`
- `0x180037010`

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
0x18002c5c4  push    rbx
0x18002c5c6  push    rbp
0x18002c5c7  push    rsi
0x18002c5c8  push    rdi
0x18002c5c9  push    r14
0x18002c5cb  push    r15
0x18002c5cd  sub     rsp, 78h
0x18002c5d1  mov     rax, cs:__security_cookie
0x18002c5d8  xor     rax, rsp
0x18002c5db  mov     [rsp+0A8h+var_48], rax
0x18002c5e0  mov     rsi, rcx
0x18002c5e3  mov     rbx, [rcx+20h]
0x18002c5e7  mov     rdi, [rcx+28h]
0x18002c5eb  mov     rax, rdi
0x18002c5ee  sub     rax, rbx
0x18002c5f1  cmp     rax, 10h
0x18002c5f5  jb      loc_18002C761
0x18002c5fb  mov     ebp, 1
0x18002c600  lea     r14d, [rbp+1]
0x18002c604  mov     r15d, 1FFh
0x18002c60a  cmp     rbx, rdi
0x18002c60d  jz      loc_18002C72E
0x18002c613  mov     r8, [rbx+8]
0x18002c617  mov     r10d, [rbx]
0x18002c61a  prefetchw byte ptr [r8]
0x18002c61e  mov     eax, [r8]
0x18002c621  mov     ecx, eax
0x18002c623  and     ecx, 0FFC0401Eh
0x18002c629  lock cmpxchg [r8], ecx
0x18002c62e  jnz     short loc_18002C621
0x18002c630  mov     ecx, eax
0x18002c632  mov     r9d, eax
0x18002c635  shr     r9d, 1
0x18002c638  and     r9d, 0Fh
0x18002c63c  jz      short loc_18002C65B
0x18002c63e  prefetchw byte ptr [r8+4]
0x18002c643  mov     eax, [r8+4]
0x18002c647  mov     edx, eax
0x18002c649  or      edx, r9d
0x18002c64c  lock cmpxchg [r8+4], edx
0x18002c652  jnz     short loc_18002C647
0x18002c654  not     eax
0x18002c656  and     eax, r9d
0x18002c659  jmp     short loc_18002C65E
0x18002c65b  mov     eax, r9d
0x18002c65e  test    bpl, al
0x18002c661  jz      short loc_18002C677
0x18002c663  mov     [rsp+0A8h+var_78], r10d
0x18002c668  mov     [rsp+0A8h+var_74], 10002h
0x18002c670  lea     rdx, [rsp+0A8h+var_70]
0x18002c675  jmp     short loc_18002C67C
0x18002c677  lea     rdx, [rsp+0A8h+var_78]
0x18002c67c  test    r14b, al
0x18002c67f  jz      short loc_18002C68F
0x18002c681  mov     [rdx], r10d
0x18002c684  mov     dword ptr [rdx+4], 10006h
0x18002c68b  add     rdx, 8
0x18002c68f  test    al, 4
0x18002c691  jz      short loc_18002C6A1
0x18002c693  mov     [rdx], r10d
0x18002c696  mov     dword ptr [rdx+4], 10003h
0x18002c69d  add     rdx, 8
0x18002c6a1  cmp     eax, 8
0x18002c6a4  jb      short loc_18002C6B4
0x18002c6a6  mov     [rdx], r10d
0x18002c6a9  mov     dword ptr [rdx+4], 10007h
0x18002c6b0  add     rdx, 8
0x18002c6b4  mov     r8d, ecx
0x18002c6b7  shr     r8d, 5
0x18002c6bb  test    r15d, r8d
0x18002c6be  jz      short loc_18002C6E0
0x18002c6c0  mov     [rdx], r10d
0x18002c6c3  mov     eax, ecx
0x18002c6c5  shr     eax, 0Eh
0x18002c6c8  and     ax, bp
0x18002c6cb  shl     ax, 2
0x18002c6cf  mov     [rdx+4], ax
0x18002c6d3  and     r8w, r15w; unsigned __int64
0x18002c6d7  mov     [rdx+6], r8w
0x18002c6dc  add     rdx, 8
0x18002c6e0  mov     eax, ecx
0x18002c6e2  shr     eax, 0Fh
0x18002c6e5  test    al, 7Fh
0x18002c6e7  jz      short loc_18002C709
0x18002c6e9  mov     [rdx], r10d
0x18002c6ec  shr     ecx, 16h
0x18002c6ef  and     cx, bp
0x18002c6f2  shl     cx, 2
0x18002c6f6  add     cx, bp
0x18002c6f9  mov     [rdx+4], cx
0x18002c6fd  and     ax, 7Fh
0x18002c701  mov     [rdx+6], ax
0x18002c705  add     rdx, 8
0x18002c709  lea     rax, [rsp+0A8h+var_78]
0x18002c70e  sub     rdx, rax
0x18002c711  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x18002c715  test    rdx, rdx
0x18002c718  jle     short loc_18002C725
0x18002c71a  lea     rcx, [rsp+0A8h+var_78]; this
0x18002c71f  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x18002c724  nop
0x18002c725  add     rbx, 10h
0x18002c729  jmp     loc_18002C60A
0x18002c72e  mov     rax, [rsi+20h]
0x18002c732  mov     [rsi+28h], rax
0x18002c736  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18002c73d  test    rax, rax
0x18002c740  jnz     short loc_18002C74E
0x18002c742  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18002c749  test    rax, rax
0x18002c74c  jz      short loc_18002C761
0x18002c74e  xor     r9d, r9d
0x18002c751  xor     r8d, r8d
0x18002c754  mov     edx, 0FEh
0x18002c759  xor     ecx, ecx
0x18002c75b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c760  nop
0x18002c761  mov     rcx, [rsp+0A8h+var_48]
0x18002c766  xor     rcx, rsp; StackCookie
0x18002c769  call    __security_check_cookie
0x18002c76e  add     rsp, 78h
0x18002c772  pop     r15
0x18002c774  pop     r14
0x18002c776  pop     rdi
0x18002c777  pop     rsi
0x18002c778  pop     rbp
0x18002c779  pop     rbx
0x18002c77a  retn
```
