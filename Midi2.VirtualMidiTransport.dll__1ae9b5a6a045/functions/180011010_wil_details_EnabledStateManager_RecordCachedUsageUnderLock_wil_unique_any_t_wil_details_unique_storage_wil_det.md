# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x180011010`
- end: `0x1800111c7`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `439`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000ca20`
- `0x18000ca80`
- `0x180010e04`

## callees

- `0x1800038f0`
- `0x180011010`
- `0x18001198c`
- `0x180021010`

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
0x180011010  push    rbx
0x180011012  push    rbp
0x180011013  push    rsi
0x180011014  push    rdi
0x180011015  push    r14
0x180011017  push    r15
0x180011019  sub     rsp, 78h
0x18001101d  mov     rax, cs:__security_cookie
0x180011024  xor     rax, rsp
0x180011027  mov     [rsp+0A8h+var_48], rax
0x18001102c  mov     rsi, rcx
0x18001102f  mov     rbx, [rcx+20h]
0x180011033  mov     rdi, [rcx+28h]
0x180011037  mov     rax, rdi
0x18001103a  sub     rax, rbx
0x18001103d  cmp     rax, 10h
0x180011041  jb      loc_1800111AD
0x180011047  mov     ebp, 1
0x18001104c  lea     r14d, [rbp+1]
0x180011050  mov     r15d, 1FFh
0x180011056  cmp     rbx, rdi
0x180011059  jz      loc_18001117A
0x18001105f  mov     r8, [rbx+8]
0x180011063  mov     r10d, [rbx]
0x180011066  prefetchw byte ptr [r8]
0x18001106a  mov     eax, [r8]
0x18001106d  mov     ecx, eax
0x18001106f  and     ecx, 0FFC0401Eh
0x180011075  lock cmpxchg [r8], ecx
0x18001107a  jnz     short loc_18001106D
0x18001107c  mov     ecx, eax
0x18001107e  mov     r9d, eax
0x180011081  shr     r9d, 1
0x180011084  and     r9d, 0Fh
0x180011088  jz      short loc_1800110A7
0x18001108a  prefetchw byte ptr [r8+4]
0x18001108f  mov     eax, [r8+4]
0x180011093  mov     edx, eax
0x180011095  or      edx, r9d
0x180011098  lock cmpxchg [r8+4], edx
0x18001109e  jnz     short loc_180011093
0x1800110a0  not     eax
0x1800110a2  and     eax, r9d
0x1800110a5  jmp     short loc_1800110AA
0x1800110a7  mov     eax, r9d
0x1800110aa  test    bpl, al
0x1800110ad  jz      short loc_1800110C3
0x1800110af  mov     [rsp+0A8h+var_78], r10d
0x1800110b4  mov     [rsp+0A8h+var_74], 10002h
0x1800110bc  lea     rdx, [rsp+0A8h+var_70]
0x1800110c1  jmp     short loc_1800110C8
0x1800110c3  lea     rdx, [rsp+0A8h+var_78]
0x1800110c8  test    r14b, al
0x1800110cb  jz      short loc_1800110DB
0x1800110cd  mov     [rdx], r10d
0x1800110d0  mov     dword ptr [rdx+4], 10006h
0x1800110d7  add     rdx, 8
0x1800110db  test    al, 4
0x1800110dd  jz      short loc_1800110ED
0x1800110df  mov     [rdx], r10d
0x1800110e2  mov     dword ptr [rdx+4], 10003h
0x1800110e9  add     rdx, 8
0x1800110ed  cmp     eax, 8
0x1800110f0  jb      short loc_180011100
0x1800110f2  mov     [rdx], r10d
0x1800110f5  mov     dword ptr [rdx+4], 10007h
0x1800110fc  add     rdx, 8
0x180011100  mov     r8d, ecx
0x180011103  shr     r8d, 5
0x180011107  test    r15d, r8d
0x18001110a  jz      short loc_18001112C
0x18001110c  mov     [rdx], r10d
0x18001110f  mov     eax, ecx
0x180011111  shr     eax, 0Eh
0x180011114  and     ax, bp
0x180011117  shl     ax, 2
0x18001111b  mov     [rdx+4], ax
0x18001111f  and     r8w, r15w; unsigned __int64
0x180011123  mov     [rdx+6], r8w
0x180011128  add     rdx, 8
0x18001112c  mov     eax, ecx
0x18001112e  shr     eax, 0Fh
0x180011131  test    al, 7Fh
0x180011133  jz      short loc_180011155
0x180011135  mov     [rdx], r10d
0x180011138  shr     ecx, 16h
0x18001113b  and     cx, bp
0x18001113e  shl     cx, 2
0x180011142  add     cx, bp
0x180011145  mov     [rdx+4], cx
0x180011149  and     ax, 7Fh
0x18001114d  mov     [rdx+6], ax
0x180011151  add     rdx, 8
0x180011155  lea     rax, [rsp+0A8h+var_78]
0x18001115a  sub     rdx, rax
0x18001115d  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x180011161  test    rdx, rdx
0x180011164  jle     short loc_180011171
0x180011166  lea     rcx, [rsp+0A8h+var_78]; this
0x18001116b  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x180011170  nop
0x180011171  add     rbx, 10h
0x180011175  jmp     loc_180011056
0x18001117a  mov     rax, [rsi+20h]
0x18001117e  mov     [rsi+28h], rax
0x180011182  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180011189  test    rax, rax
0x18001118c  jnz     short loc_18001119A
0x18001118e  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180011195  test    rax, rax
0x180011198  jz      short loc_1800111AD
0x18001119a  xor     r9d, r9d
0x18001119d  xor     r8d, r8d
0x1800111a0  mov     edx, 0FEh
0x1800111a5  xor     ecx, ecx
0x1800111a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800111ac  nop
0x1800111ad  mov     rcx, [rsp+0A8h+var_48]
0x1800111b2  xor     rcx, rsp; StackCookie
0x1800111b5  call    __security_check_cookie
0x1800111ba  add     rsp, 78h
0x1800111be  pop     r15
0x1800111c0  pop     r14
0x1800111c2  pop     rdi
0x1800111c3  pop     rsi
0x1800111c4  pop     rbp
0x1800111c5  pop     rbx
0x1800111c6  retn
```
