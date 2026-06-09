# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x18000f9e0`
- end: `0x18000fb97`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `439`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000c410`
- `0x18000c470`
- `0x18000f7d4`

## callees

- `0x1800033d0`
- `0x18000f9e0`
- `0x18000ffd0`
- `0x180013010`

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
0x18000f9e0  push    rbx
0x18000f9e2  push    rbp
0x18000f9e3  push    rsi
0x18000f9e4  push    rdi
0x18000f9e5  push    r14
0x18000f9e7  push    r15
0x18000f9e9  sub     rsp, 78h
0x18000f9ed  mov     rax, cs:__security_cookie
0x18000f9f4  xor     rax, rsp
0x18000f9f7  mov     [rsp+0A8h+var_48], rax
0x18000f9fc  mov     rsi, rcx
0x18000f9ff  mov     rbx, [rcx+20h]
0x18000fa03  mov     rdi, [rcx+28h]
0x18000fa07  mov     rax, rdi
0x18000fa0a  sub     rax, rbx
0x18000fa0d  cmp     rax, 10h
0x18000fa11  jb      loc_18000FB7D
0x18000fa17  mov     ebp, 1
0x18000fa1c  lea     r14d, [rbp+1]
0x18000fa20  mov     r15d, 1FFh
0x18000fa26  cmp     rbx, rdi
0x18000fa29  jz      loc_18000FB4A
0x18000fa2f  mov     r8, [rbx+8]
0x18000fa33  mov     r10d, [rbx]
0x18000fa36  prefetchw byte ptr [r8]
0x18000fa3a  mov     eax, [r8]
0x18000fa3d  mov     ecx, eax
0x18000fa3f  and     ecx, 0FFC0401Eh
0x18000fa45  lock cmpxchg [r8], ecx
0x18000fa4a  jnz     short loc_18000FA3D
0x18000fa4c  mov     ecx, eax
0x18000fa4e  mov     r9d, eax
0x18000fa51  shr     r9d, 1
0x18000fa54  and     r9d, 0Fh
0x18000fa58  jz      short loc_18000FA77
0x18000fa5a  prefetchw byte ptr [r8+4]
0x18000fa5f  mov     eax, [r8+4]
0x18000fa63  mov     edx, eax
0x18000fa65  or      edx, r9d
0x18000fa68  lock cmpxchg [r8+4], edx
0x18000fa6e  jnz     short loc_18000FA63
0x18000fa70  not     eax
0x18000fa72  and     eax, r9d
0x18000fa75  jmp     short loc_18000FA7A
0x18000fa77  mov     eax, r9d
0x18000fa7a  test    bpl, al
0x18000fa7d  jz      short loc_18000FA93
0x18000fa7f  mov     [rsp+0A8h+var_78], r10d
0x18000fa84  mov     [rsp+0A8h+var_74], 10002h
0x18000fa8c  lea     rdx, [rsp+0A8h+var_70]
0x18000fa91  jmp     short loc_18000FA98
0x18000fa93  lea     rdx, [rsp+0A8h+var_78]
0x18000fa98  test    r14b, al
0x18000fa9b  jz      short loc_18000FAAB
0x18000fa9d  mov     [rdx], r10d
0x18000faa0  mov     dword ptr [rdx+4], 10006h
0x18000faa7  add     rdx, 8
0x18000faab  test    al, 4
0x18000faad  jz      short loc_18000FABD
0x18000faaf  mov     [rdx], r10d
0x18000fab2  mov     dword ptr [rdx+4], 10003h
0x18000fab9  add     rdx, 8
0x18000fabd  cmp     eax, 8
0x18000fac0  jb      short loc_18000FAD0
0x18000fac2  mov     [rdx], r10d
0x18000fac5  mov     dword ptr [rdx+4], 10007h
0x18000facc  add     rdx, 8
0x18000fad0  mov     r8d, ecx
0x18000fad3  shr     r8d, 5
0x18000fad7  test    r15d, r8d
0x18000fada  jz      short loc_18000FAFC
0x18000fadc  mov     [rdx], r10d
0x18000fadf  mov     eax, ecx
0x18000fae1  shr     eax, 0Eh
0x18000fae4  and     ax, bp
0x18000fae7  shl     ax, 2
0x18000faeb  mov     [rdx+4], ax
0x18000faef  and     r8w, r15w; unsigned __int64
0x18000faf3  mov     [rdx+6], r8w
0x18000faf8  add     rdx, 8
0x18000fafc  mov     eax, ecx
0x18000fafe  shr     eax, 0Fh
0x18000fb01  test    al, 7Fh
0x18000fb03  jz      short loc_18000FB25
0x18000fb05  mov     [rdx], r10d
0x18000fb08  shr     ecx, 16h
0x18000fb0b  and     cx, bp
0x18000fb0e  shl     cx, 2
0x18000fb12  add     cx, bp
0x18000fb15  mov     [rdx+4], cx
0x18000fb19  and     ax, 7Fh
0x18000fb1d  mov     [rdx+6], ax
0x18000fb21  add     rdx, 8
0x18000fb25  lea     rax, [rsp+0A8h+var_78]
0x18000fb2a  sub     rdx, rax
0x18000fb2d  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x18000fb31  test    rdx, rdx
0x18000fb34  jle     short loc_18000FB41
0x18000fb36  lea     rcx, [rsp+0A8h+var_78]; this
0x18000fb3b  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x18000fb40  nop
0x18000fb41  add     rbx, 10h
0x18000fb45  jmp     loc_18000FA26
0x18000fb4a  mov     rax, [rsi+20h]
0x18000fb4e  mov     [rsi+28h], rax
0x18000fb52  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000fb59  test    rax, rax
0x18000fb5c  jnz     short loc_18000FB6A
0x18000fb5e  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000fb65  test    rax, rax
0x18000fb68  jz      short loc_18000FB7D
0x18000fb6a  xor     r9d, r9d
0x18000fb6d  xor     r8d, r8d
0x18000fb70  mov     edx, 0FEh
0x18000fb75  xor     ecx, ecx
0x18000fb77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb7c  nop
0x18000fb7d  mov     rcx, [rsp+0A8h+var_48]
0x18000fb82  xor     rcx, rsp; StackCookie
0x18000fb85  call    __security_check_cookie
0x18000fb8a  add     rsp, 78h
0x18000fb8e  pop     r15
0x18000fb90  pop     r14
0x18000fb92  pop     rdi
0x18000fb93  pop     rsi
0x18000fb94  pop     rbp
0x18000fb95  pop     rbx
0x18000fb96  retn
```
