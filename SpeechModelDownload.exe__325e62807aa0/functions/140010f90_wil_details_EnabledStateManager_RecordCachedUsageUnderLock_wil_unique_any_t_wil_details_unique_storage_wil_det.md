# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x140010f90`
- end: `0x140011147`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `439`
- prototype: `__int64 (__fastcall *__fastcall(__int64))(_QWORD, __int64, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140010414`

## callees

- `0x140002600`
- `0x140010f90`
- `0x140013034`
- `0x14001d010`

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
0x140010f90  push    rbx
0x140010f92  push    rbp
0x140010f93  push    rsi
0x140010f94  push    rdi
0x140010f95  push    r14
0x140010f97  push    r15
0x140010f99  sub     rsp, 78h
0x140010f9d  mov     rax, cs:__security_cookie
0x140010fa4  xor     rax, rsp
0x140010fa7  mov     [rsp+0A8h+var_48], rax
0x140010fac  mov     rsi, rcx
0x140010faf  mov     rbx, [rcx+20h]
0x140010fb3  mov     rdi, [rcx+28h]
0x140010fb7  mov     rax, rdi
0x140010fba  sub     rax, rbx
0x140010fbd  cmp     rax, 10h
0x140010fc1  jb      loc_14001112D
0x140010fc7  mov     ebp, 1
0x140010fcc  lea     r14d, [rbp+1]
0x140010fd0  mov     r15d, 1FFh
0x140010fd6  cmp     rbx, rdi
0x140010fd9  jz      loc_1400110FA
0x140010fdf  mov     r8, [rbx+8]
0x140010fe3  mov     r10d, [rbx]
0x140010fe6  prefetchw byte ptr [r8]
0x140010fea  mov     eax, [r8]
0x140010fed  mov     ecx, eax
0x140010fef  and     ecx, 0FFC0401Eh
0x140010ff5  lock cmpxchg [r8], ecx
0x140010ffa  jnz     short loc_140010FED
0x140010ffc  mov     ecx, eax
0x140010ffe  mov     r9d, eax
0x140011001  shr     r9d, 1
0x140011004  and     r9d, 0Fh
0x140011008  jz      short loc_140011027
0x14001100a  prefetchw byte ptr [r8+4]
0x14001100f  mov     eax, [r8+4]
0x140011013  mov     edx, eax
0x140011015  or      edx, r9d
0x140011018  lock cmpxchg [r8+4], edx
0x14001101e  jnz     short loc_140011013
0x140011020  not     eax
0x140011022  and     eax, r9d
0x140011025  jmp     short loc_14001102A
0x140011027  mov     eax, r9d
0x14001102a  test    bpl, al
0x14001102d  jz      short loc_140011043
0x14001102f  mov     [rsp+0A8h+var_78], r10d
0x140011034  mov     [rsp+0A8h+var_74], 10002h
0x14001103c  lea     rdx, [rsp+0A8h+var_70]
0x140011041  jmp     short loc_140011048
0x140011043  lea     rdx, [rsp+0A8h+var_78]
0x140011048  test    r14b, al
0x14001104b  jz      short loc_14001105B
0x14001104d  mov     [rdx], r10d
0x140011050  mov     dword ptr [rdx+4], 10006h
0x140011057  add     rdx, 8
0x14001105b  test    al, 4
0x14001105d  jz      short loc_14001106D
0x14001105f  mov     [rdx], r10d
0x140011062  mov     dword ptr [rdx+4], 10003h
0x140011069  add     rdx, 8
0x14001106d  cmp     eax, 8
0x140011070  jb      short loc_140011080
0x140011072  mov     [rdx], r10d
0x140011075  mov     dword ptr [rdx+4], 10007h
0x14001107c  add     rdx, 8
0x140011080  mov     r8d, ecx
0x140011083  shr     r8d, 5
0x140011087  test    r15d, r8d
0x14001108a  jz      short loc_1400110AC
0x14001108c  mov     [rdx], r10d
0x14001108f  mov     eax, ecx
0x140011091  shr     eax, 0Eh
0x140011094  and     ax, bp
0x140011097  shl     ax, 2
0x14001109b  mov     [rdx+4], ax
0x14001109f  and     r8w, r15w; unsigned __int64
0x1400110a3  mov     [rdx+6], r8w
0x1400110a8  add     rdx, 8
0x1400110ac  mov     eax, ecx
0x1400110ae  shr     eax, 0Fh
0x1400110b1  test    al, 7Fh
0x1400110b3  jz      short loc_1400110D5
0x1400110b5  mov     [rdx], r10d
0x1400110b8  shr     ecx, 16h
0x1400110bb  and     cx, bp
0x1400110be  shl     cx, 2
0x1400110c2  add     cx, bp
0x1400110c5  mov     [rdx+4], cx
0x1400110c9  and     ax, 7Fh
0x1400110cd  mov     [rdx+6], ax
0x1400110d1  add     rdx, 8
0x1400110d5  lea     rax, [rsp+0A8h+var_78]
0x1400110da  sub     rdx, rax
0x1400110dd  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x1400110e1  test    rdx, rdx
0x1400110e4  jle     short loc_1400110F1
0x1400110e6  lea     rcx, [rsp+0A8h+var_78]; this
0x1400110eb  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x1400110f0  nop
0x1400110f1  add     rbx, 10h
0x1400110f5  jmp     loc_140010FD6
0x1400110fa  mov     rax, [rsi+20h]
0x1400110fe  mov     [rsi+28h], rax
0x140011102  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x140011109  test    rax, rax
0x14001110c  jnz     short loc_14001111A
0x14001110e  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x140011115  test    rax, rax
0x140011118  jz      short loc_14001112D
0x14001111a  xor     r9d, r9d
0x14001111d  xor     r8d, r8d
0x140011120  mov     edx, 0FEh
0x140011125  xor     ecx, ecx
0x140011127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001112c  nop
0x14001112d  mov     rcx, [rsp+0A8h+var_48]
0x140011132  xor     rcx, rsp; StackCookie
0x140011135  call    __security_check_cookie
0x14001113a  add     rsp, 78h
0x14001113e  pop     r15
0x140011140  pop     r14
0x140011142  pop     rdi
0x140011143  pop     rsi
0x140011144  pop     rbp
0x140011145  pop     rbx
0x140011146  retn
```
