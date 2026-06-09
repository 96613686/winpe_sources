# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x140006208`
- end: `0x1400063bf`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `439`
- prototype: `__int64 (__fastcall *__fastcall(__int64))(_QWORD, __int64, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140005dbc`
- `0x140009410`
- `0x140009470`

## callees

- `0x1400016f0`
- `0x140006208`
- `0x140008854`
- `0x14000c010`

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
0x140006208  push    rbx
0x14000620a  push    rbp
0x14000620b  push    rsi
0x14000620c  push    rdi
0x14000620d  push    r14
0x14000620f  push    r15
0x140006211  sub     rsp, 78h
0x140006215  mov     rax, cs:__security_cookie
0x14000621c  xor     rax, rsp
0x14000621f  mov     [rsp+0A8h+var_48], rax
0x140006224  mov     rsi, rcx
0x140006227  mov     rbx, [rcx+20h]
0x14000622b  mov     rdi, [rcx+28h]
0x14000622f  mov     rax, rdi
0x140006232  sub     rax, rbx
0x140006235  cmp     rax, 10h
0x140006239  jb      loc_1400063A5
0x14000623f  mov     ebp, 1
0x140006244  lea     r14d, [rbp+1]
0x140006248  mov     r15d, 1FFh
0x14000624e  cmp     rbx, rdi
0x140006251  jz      loc_140006372
0x140006257  mov     r8, [rbx+8]
0x14000625b  mov     r10d, [rbx]
0x14000625e  prefetchw byte ptr [r8]
0x140006262  mov     eax, [r8]
0x140006265  mov     ecx, eax
0x140006267  and     ecx, 0FFC0401Eh
0x14000626d  lock cmpxchg [r8], ecx
0x140006272  jnz     short loc_140006265
0x140006274  mov     ecx, eax
0x140006276  mov     r9d, eax
0x140006279  shr     r9d, 1
0x14000627c  and     r9d, 0Fh
0x140006280  jz      short loc_14000629F
0x140006282  prefetchw byte ptr [r8+4]
0x140006287  mov     eax, [r8+4]
0x14000628b  mov     edx, eax
0x14000628d  or      edx, r9d
0x140006290  lock cmpxchg [r8+4], edx
0x140006296  jnz     short loc_14000628B
0x140006298  not     eax
0x14000629a  and     eax, r9d
0x14000629d  jmp     short loc_1400062A2
0x14000629f  mov     eax, r9d
0x1400062a2  test    bpl, al
0x1400062a5  jz      short loc_1400062BB
0x1400062a7  mov     [rsp+0A8h+var_78], r10d
0x1400062ac  mov     [rsp+0A8h+var_74], 10002h
0x1400062b4  lea     rdx, [rsp+0A8h+var_70]
0x1400062b9  jmp     short loc_1400062C0
0x1400062bb  lea     rdx, [rsp+0A8h+var_78]
0x1400062c0  test    r14b, al
0x1400062c3  jz      short loc_1400062D3
0x1400062c5  mov     [rdx], r10d
0x1400062c8  mov     dword ptr [rdx+4], 10006h
0x1400062cf  add     rdx, 8
0x1400062d3  test    al, 4
0x1400062d5  jz      short loc_1400062E5
0x1400062d7  mov     [rdx], r10d
0x1400062da  mov     dword ptr [rdx+4], 10003h
0x1400062e1  add     rdx, 8
0x1400062e5  cmp     eax, 8
0x1400062e8  jb      short loc_1400062F8
0x1400062ea  mov     [rdx], r10d
0x1400062ed  mov     dword ptr [rdx+4], 10007h
0x1400062f4  add     rdx, 8
0x1400062f8  mov     r8d, ecx
0x1400062fb  shr     r8d, 5
0x1400062ff  test    r15d, r8d
0x140006302  jz      short loc_140006324
0x140006304  mov     [rdx], r10d
0x140006307  mov     eax, ecx
0x140006309  shr     eax, 0Eh
0x14000630c  and     ax, bp
0x14000630f  shl     ax, 2
0x140006313  mov     [rdx+4], ax
0x140006317  and     r8w, r15w; unsigned __int64
0x14000631b  mov     [rdx+6], r8w
0x140006320  add     rdx, 8
0x140006324  mov     eax, ecx
0x140006326  shr     eax, 0Fh
0x140006329  test    al, 7Fh
0x14000632b  jz      short loc_14000634D
0x14000632d  mov     [rdx], r10d
0x140006330  shr     ecx, 16h
0x140006333  and     cx, bp
0x140006336  shl     cx, 2
0x14000633a  add     cx, bp
0x14000633d  mov     [rdx+4], cx
0x140006341  and     ax, 7Fh
0x140006345  mov     [rdx+6], ax
0x140006349  add     rdx, 8
0x14000634d  lea     rax, [rsp+0A8h+var_78]
0x140006352  sub     rdx, rax
0x140006355  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x140006359  test    rdx, rdx
0x14000635c  jle     short loc_140006369
0x14000635e  lea     rcx, [rsp+0A8h+var_78]; this
0x140006363  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x140006368  nop
0x140006369  add     rbx, 10h
0x14000636d  jmp     loc_14000624E
0x140006372  mov     rax, [rsi+20h]
0x140006376  mov     [rsi+28h], rax
0x14000637a  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x140006381  test    rax, rax
0x140006384  jnz     short loc_140006392
0x140006386  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x14000638d  test    rax, rax
0x140006390  jz      short loc_1400063A5
0x140006392  xor     r9d, r9d
0x140006395  xor     r8d, r8d
0x140006398  mov     edx, 0FEh
0x14000639d  xor     ecx, ecx
0x14000639f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400063a4  nop
0x1400063a5  mov     rcx, [rsp+0A8h+var_48]
0x1400063aa  xor     rcx, rsp; StackCookie
0x1400063ad  call    __security_check_cookie
0x1400063b2  add     rsp, 78h
0x1400063b6  pop     r15
0x1400063b8  pop     r14
0x1400063ba  pop     rdi
0x1400063bb  pop     rsi
0x1400063bc  pop     rbp
0x1400063bd  pop     rbx
0x1400063be  retn
```
