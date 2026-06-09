# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x180014398`
- end: `0x18001454f`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `439`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800106a0`
- `0x180010840`
- `0x180013dd4`

## callees

- `0x180014398`
- `0x180016094`
- `0x180019760`
- `0x18001b010`

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
0x180014398  push    rbx
0x18001439a  push    rbp
0x18001439b  push    rsi
0x18001439c  push    rdi
0x18001439d  push    r14
0x18001439f  push    r15
0x1800143a1  sub     rsp, 78h
0x1800143a5  mov     rax, cs:__security_cookie
0x1800143ac  xor     rax, rsp
0x1800143af  mov     [rsp+0A8h+var_48], rax
0x1800143b4  mov     rsi, rcx
0x1800143b7  mov     rbx, [rcx+20h]
0x1800143bb  mov     rdi, [rcx+28h]
0x1800143bf  mov     rax, rdi
0x1800143c2  sub     rax, rbx
0x1800143c5  cmp     rax, 10h
0x1800143c9  jb      loc_180014535
0x1800143cf  mov     ebp, 1
0x1800143d4  lea     r14d, [rbp+1]
0x1800143d8  mov     r15d, 1FFh
0x1800143de  cmp     rbx, rdi
0x1800143e1  jz      loc_180014502
0x1800143e7  mov     r8, [rbx+8]
0x1800143eb  mov     r10d, [rbx]
0x1800143ee  prefetchw byte ptr [r8]
0x1800143f2  mov     eax, [r8]
0x1800143f5  mov     ecx, eax
0x1800143f7  and     ecx, 0FFC0401Eh
0x1800143fd  lock cmpxchg [r8], ecx
0x180014402  jnz     short loc_1800143F5
0x180014404  mov     ecx, eax
0x180014406  mov     r9d, eax
0x180014409  shr     r9d, 1
0x18001440c  and     r9d, 0Fh
0x180014410  jz      short loc_18001442F
0x180014412  prefetchw byte ptr [r8+4]
0x180014417  mov     eax, [r8+4]
0x18001441b  mov     edx, eax
0x18001441d  or      edx, r9d
0x180014420  lock cmpxchg [r8+4], edx
0x180014426  jnz     short loc_18001441B
0x180014428  not     eax
0x18001442a  and     eax, r9d
0x18001442d  jmp     short loc_180014432
0x18001442f  mov     eax, r9d
0x180014432  test    bpl, al
0x180014435  jz      short loc_18001444B
0x180014437  mov     [rsp+0A8h+var_78], r10d
0x18001443c  mov     [rsp+0A8h+var_74], 10002h
0x180014444  lea     rdx, [rsp+0A8h+var_70]
0x180014449  jmp     short loc_180014450
0x18001444b  lea     rdx, [rsp+0A8h+var_78]
0x180014450  test    r14b, al
0x180014453  jz      short loc_180014463
0x180014455  mov     [rdx], r10d
0x180014458  mov     dword ptr [rdx+4], 10006h
0x18001445f  add     rdx, 8
0x180014463  test    al, 4
0x180014465  jz      short loc_180014475
0x180014467  mov     [rdx], r10d
0x18001446a  mov     dword ptr [rdx+4], 10003h
0x180014471  add     rdx, 8
0x180014475  cmp     eax, 8
0x180014478  jb      short loc_180014488
0x18001447a  mov     [rdx], r10d
0x18001447d  mov     dword ptr [rdx+4], 10007h
0x180014484  add     rdx, 8
0x180014488  mov     r8d, ecx
0x18001448b  shr     r8d, 5
0x18001448f  test    r15d, r8d
0x180014492  jz      short loc_1800144B4
0x180014494  mov     [rdx], r10d
0x180014497  mov     eax, ecx
0x180014499  shr     eax, 0Eh
0x18001449c  and     ax, bp
0x18001449f  shl     ax, 2
0x1800144a3  mov     [rdx+4], ax
0x1800144a7  and     r8w, r15w; unsigned __int64
0x1800144ab  mov     [rdx+6], r8w
0x1800144b0  add     rdx, 8
0x1800144b4  mov     eax, ecx
0x1800144b6  shr     eax, 0Fh
0x1800144b9  test    al, 7Fh
0x1800144bb  jz      short loc_1800144DD
0x1800144bd  mov     [rdx], r10d
0x1800144c0  shr     ecx, 16h
0x1800144c3  and     cx, bp
0x1800144c6  shl     cx, 2
0x1800144ca  add     cx, bp
0x1800144cd  mov     [rdx+4], cx
0x1800144d1  and     ax, 7Fh
0x1800144d5  mov     [rdx+6], ax
0x1800144d9  add     rdx, 8
0x1800144dd  lea     rax, [rsp+0A8h+var_78]
0x1800144e2  sub     rdx, rax
0x1800144e5  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x1800144e9  test    rdx, rdx
0x1800144ec  jle     short loc_1800144F9
0x1800144ee  lea     rcx, [rsp+0A8h+var_78]; this
0x1800144f3  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x1800144f8  nop
0x1800144f9  add     rbx, 10h
0x1800144fd  jmp     loc_1800143DE
0x180014502  mov     rax, [rsi+20h]
0x180014506  mov     [rsi+28h], rax
0x18001450a  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180014511  test    rax, rax
0x180014514  jnz     short loc_180014522
0x180014516  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18001451d  test    rax, rax
0x180014520  jz      short loc_180014535
0x180014522  xor     r9d, r9d
0x180014525  xor     r8d, r8d
0x180014528  mov     edx, 0FEh
0x18001452d  xor     ecx, ecx
0x18001452f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014534  nop
0x180014535  mov     rcx, [rsp+0A8h+var_48]
0x18001453a  xor     rcx, rsp; StackCookie
0x18001453d  call    __security_check_cookie
0x180014542  add     rsp, 78h
0x180014546  pop     r15
0x180014548  pop     r14
0x18001454a  pop     rdi
0x18001454b  pop     rsi
0x18001454c  pop     rbp
0x18001454d  pop     rbx
0x18001454e  retn
```
