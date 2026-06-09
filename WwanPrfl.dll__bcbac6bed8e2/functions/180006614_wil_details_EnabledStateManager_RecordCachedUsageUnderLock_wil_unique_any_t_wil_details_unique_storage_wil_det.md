# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x180006614`
- end: `0x1800067cb`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `439`
- prototype: `__int64 (__fastcall *__fastcall(__int64))(_QWORD, __int64, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800023c0`
- `0x180002530`
- `0x18000600c`

## callees

- `0x180001670`
- `0x180006614`
- `0x180008ed4`
- `0x180014010`

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
0x180006614  push    rbx
0x180006616  push    rbp
0x180006617  push    rsi
0x180006618  push    rdi
0x180006619  push    r14
0x18000661b  push    r15
0x18000661d  sub     rsp, 78h
0x180006621  mov     rax, cs:__security_cookie
0x180006628  xor     rax, rsp
0x18000662b  mov     [rsp+0A8h+var_48], rax
0x180006630  mov     rsi, rcx
0x180006633  mov     rbx, [rcx+20h]
0x180006637  mov     rdi, [rcx+28h]
0x18000663b  mov     rax, rdi
0x18000663e  sub     rax, rbx
0x180006641  cmp     rax, 10h
0x180006645  jb      loc_1800067B1
0x18000664b  mov     ebp, 1
0x180006650  lea     r14d, [rbp+1]
0x180006654  mov     r15d, 1FFh
0x18000665a  cmp     rbx, rdi
0x18000665d  jz      loc_18000677E
0x180006663  mov     r8, [rbx+8]
0x180006667  mov     r10d, [rbx]
0x18000666a  prefetchw byte ptr [r8]
0x18000666e  mov     eax, [r8]
0x180006671  mov     ecx, eax
0x180006673  and     ecx, 0FFC0401Eh
0x180006679  lock cmpxchg [r8], ecx
0x18000667e  jnz     short loc_180006671
0x180006680  mov     ecx, eax
0x180006682  mov     r9d, eax
0x180006685  shr     r9d, 1
0x180006688  and     r9d, 0Fh
0x18000668c  jz      short loc_1800066AB
0x18000668e  prefetchw byte ptr [r8+4]
0x180006693  mov     eax, [r8+4]
0x180006697  mov     edx, eax
0x180006699  or      edx, r9d
0x18000669c  lock cmpxchg [r8+4], edx
0x1800066a2  jnz     short loc_180006697
0x1800066a4  not     eax
0x1800066a6  and     eax, r9d
0x1800066a9  jmp     short loc_1800066AE
0x1800066ab  mov     eax, r9d
0x1800066ae  test    bpl, al
0x1800066b1  jz      short loc_1800066C7
0x1800066b3  mov     [rsp+0A8h+var_78], r10d
0x1800066b8  mov     [rsp+0A8h+var_74], 10002h
0x1800066c0  lea     rdx, [rsp+0A8h+var_70]
0x1800066c5  jmp     short loc_1800066CC
0x1800066c7  lea     rdx, [rsp+0A8h+var_78]
0x1800066cc  test    r14b, al
0x1800066cf  jz      short loc_1800066DF
0x1800066d1  mov     [rdx], r10d
0x1800066d4  mov     dword ptr [rdx+4], 10006h
0x1800066db  add     rdx, 8
0x1800066df  test    al, 4
0x1800066e1  jz      short loc_1800066F1
0x1800066e3  mov     [rdx], r10d
0x1800066e6  mov     dword ptr [rdx+4], 10003h
0x1800066ed  add     rdx, 8
0x1800066f1  cmp     eax, 8
0x1800066f4  jb      short loc_180006704
0x1800066f6  mov     [rdx], r10d
0x1800066f9  mov     dword ptr [rdx+4], 10007h
0x180006700  add     rdx, 8
0x180006704  mov     r8d, ecx
0x180006707  shr     r8d, 5
0x18000670b  test    r15d, r8d
0x18000670e  jz      short loc_180006730
0x180006710  mov     [rdx], r10d
0x180006713  mov     eax, ecx
0x180006715  shr     eax, 0Eh
0x180006718  and     ax, bp
0x18000671b  shl     ax, 2
0x18000671f  mov     [rdx+4], ax
0x180006723  and     r8w, r15w; unsigned __int64
0x180006727  mov     [rdx+6], r8w
0x18000672c  add     rdx, 8
0x180006730  mov     eax, ecx
0x180006732  shr     eax, 0Fh
0x180006735  test    al, 7Fh
0x180006737  jz      short loc_180006759
0x180006739  mov     [rdx], r10d
0x18000673c  shr     ecx, 16h
0x18000673f  and     cx, bp
0x180006742  shl     cx, 2
0x180006746  add     cx, bp
0x180006749  mov     [rdx+4], cx
0x18000674d  and     ax, 7Fh
0x180006751  mov     [rdx+6], ax
0x180006755  add     rdx, 8
0x180006759  lea     rax, [rsp+0A8h+var_78]
0x18000675e  sub     rdx, rax
0x180006761  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x180006765  test    rdx, rdx
0x180006768  jle     short loc_180006775
0x18000676a  lea     rcx, [rsp+0A8h+var_78]; this
0x18000676f  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x180006774  nop
0x180006775  add     rbx, 10h
0x180006779  jmp     loc_18000665A
0x18000677e  mov     rax, [rsi+20h]
0x180006782  mov     [rsi+28h], rax
0x180006786  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000678d  test    rax, rax
0x180006790  jnz     short loc_18000679E
0x180006792  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180006799  test    rax, rax
0x18000679c  jz      short loc_1800067B1
0x18000679e  xor     r9d, r9d
0x1800067a1  xor     r8d, r8d
0x1800067a4  mov     edx, 0FEh
0x1800067a9  xor     ecx, ecx
0x1800067ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067b0  nop
0x1800067b1  mov     rcx, [rsp+0A8h+var_48]
0x1800067b6  xor     rcx, rsp; StackCookie
0x1800067b9  call    __security_check_cookie
0x1800067be  add     rsp, 78h
0x1800067c2  pop     r15
0x1800067c4  pop     r14
0x1800067c6  pop     rdi
0x1800067c7  pop     rsi
0x1800067c8  pop     rbp
0x1800067c9  pop     rbx
0x1800067ca  retn
```
