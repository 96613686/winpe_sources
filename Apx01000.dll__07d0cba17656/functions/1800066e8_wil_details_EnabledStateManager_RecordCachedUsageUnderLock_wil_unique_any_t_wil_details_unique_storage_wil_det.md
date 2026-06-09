# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x1800066e8`
- end: `0x18000689f`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `439`
- prototype: `__int64 (__fastcall *__fastcall(__int64))(_QWORD, __int64, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000629c`
- `0x18000a5f0`
- `0x18000a650`

## callees

- `0x180001d30`
- `0x1800066e8`
- `0x180008d34`
- `0x18002a010`

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
0x1800066e8  push    rbx
0x1800066ea  push    rbp
0x1800066eb  push    rsi
0x1800066ec  push    rdi
0x1800066ed  push    r14
0x1800066ef  push    r15
0x1800066f1  sub     rsp, 78h
0x1800066f5  mov     rax, cs:__security_cookie
0x1800066fc  xor     rax, rsp
0x1800066ff  mov     [rsp+0A8h+var_48], rax
0x180006704  mov     rsi, rcx
0x180006707  mov     rbx, [rcx+20h]
0x18000670b  mov     rdi, [rcx+28h]
0x18000670f  mov     rax, rdi
0x180006712  sub     rax, rbx
0x180006715  cmp     rax, 10h
0x180006719  jb      loc_180006885
0x18000671f  mov     ebp, 1
0x180006724  lea     r14d, [rbp+1]
0x180006728  mov     r15d, 1FFh
0x18000672e  cmp     rbx, rdi
0x180006731  jz      loc_180006852
0x180006737  mov     r8, [rbx+8]
0x18000673b  mov     r10d, [rbx]
0x18000673e  prefetchw byte ptr [r8]
0x180006742  mov     eax, [r8]
0x180006745  mov     ecx, eax
0x180006747  and     ecx, 0FFC0401Eh
0x18000674d  lock cmpxchg [r8], ecx
0x180006752  jnz     short loc_180006745
0x180006754  mov     ecx, eax
0x180006756  mov     r9d, eax
0x180006759  shr     r9d, 1
0x18000675c  and     r9d, 0Fh
0x180006760  jz      short loc_18000677F
0x180006762  prefetchw byte ptr [r8+4]
0x180006767  mov     eax, [r8+4]
0x18000676b  mov     edx, eax
0x18000676d  or      edx, r9d
0x180006770  lock cmpxchg [r8+4], edx
0x180006776  jnz     short loc_18000676B
0x180006778  not     eax
0x18000677a  and     eax, r9d
0x18000677d  jmp     short loc_180006782
0x18000677f  mov     eax, r9d
0x180006782  test    bpl, al
0x180006785  jz      short loc_18000679B
0x180006787  mov     [rsp+0A8h+var_78], r10d
0x18000678c  mov     [rsp+0A8h+var_74], 10002h
0x180006794  lea     rdx, [rsp+0A8h+var_70]
0x180006799  jmp     short loc_1800067A0
0x18000679b  lea     rdx, [rsp+0A8h+var_78]
0x1800067a0  test    r14b, al
0x1800067a3  jz      short loc_1800067B3
0x1800067a5  mov     [rdx], r10d
0x1800067a8  mov     dword ptr [rdx+4], 10006h
0x1800067af  add     rdx, 8
0x1800067b3  test    al, 4
0x1800067b5  jz      short loc_1800067C5
0x1800067b7  mov     [rdx], r10d
0x1800067ba  mov     dword ptr [rdx+4], 10003h
0x1800067c1  add     rdx, 8
0x1800067c5  cmp     eax, 8
0x1800067c8  jb      short loc_1800067D8
0x1800067ca  mov     [rdx], r10d
0x1800067cd  mov     dword ptr [rdx+4], 10007h
0x1800067d4  add     rdx, 8
0x1800067d8  mov     r8d, ecx
0x1800067db  shr     r8d, 5
0x1800067df  test    r15d, r8d
0x1800067e2  jz      short loc_180006804
0x1800067e4  mov     [rdx], r10d
0x1800067e7  mov     eax, ecx
0x1800067e9  shr     eax, 0Eh
0x1800067ec  and     ax, bp
0x1800067ef  shl     ax, 2
0x1800067f3  mov     [rdx+4], ax
0x1800067f7  and     r8w, r15w; unsigned __int64
0x1800067fb  mov     [rdx+6], r8w
0x180006800  add     rdx, 8
0x180006804  mov     eax, ecx
0x180006806  shr     eax, 0Fh
0x180006809  test    al, 7Fh
0x18000680b  jz      short loc_18000682D
0x18000680d  mov     [rdx], r10d
0x180006810  shr     ecx, 16h
0x180006813  and     cx, bp
0x180006816  shl     cx, 2
0x18000681a  add     cx, bp
0x18000681d  mov     [rdx+4], cx
0x180006821  and     ax, 7Fh
0x180006825  mov     [rdx+6], ax
0x180006829  add     rdx, 8
0x18000682d  lea     rax, [rsp+0A8h+var_78]
0x180006832  sub     rdx, rax
0x180006835  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x180006839  test    rdx, rdx
0x18000683c  jle     short loc_180006849
0x18000683e  lea     rcx, [rsp+0A8h+var_78]; this
0x180006843  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x180006848  nop
0x180006849  add     rbx, 10h
0x18000684d  jmp     loc_18000672E
0x180006852  mov     rax, [rsi+20h]
0x180006856  mov     [rsi+28h], rax
0x18000685a  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180006861  test    rax, rax
0x180006864  jnz     short loc_180006872
0x180006866  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000686d  test    rax, rax
0x180006870  jz      short loc_180006885
0x180006872  xor     r9d, r9d
0x180006875  xor     r8d, r8d
0x180006878  mov     edx, 0FEh
0x18000687d  xor     ecx, ecx
0x18000687f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006884  nop
0x180006885  mov     rcx, [rsp+0A8h+var_48]
0x18000688a  xor     rcx, rsp; StackCookie
0x18000688d  call    __security_check_cookie
0x180006892  add     rsp, 78h
0x180006896  pop     r15
0x180006898  pop     r14
0x18000689a  pop     rdi
0x18000689b  pop     rsi
0x18000689c  pop     rbp
0x18000689d  pop     rbx
0x18000689e  retn
```
