# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x1800075d4`
- end: `0x18000778b`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `439`
- prototype: `__int64 (__fastcall *__fastcall(__int64))(_QWORD, __int64, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180002350`
- `0x180002490`
- `0x180007190`

## callees

- `0x1800075d4`
- `0x18000a340`
- `0x1800107c0`
- `0x180012010`

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
0x1800075d4  push    rbx
0x1800075d6  push    rbp
0x1800075d7  push    rsi
0x1800075d8  push    rdi
0x1800075d9  push    r14
0x1800075db  push    r15
0x1800075dd  sub     rsp, 78h
0x1800075e1  mov     rax, cs:__security_cookie
0x1800075e8  xor     rax, rsp
0x1800075eb  mov     [rsp+0A8h+var_48], rax
0x1800075f0  mov     rsi, rcx
0x1800075f3  mov     rbx, [rcx+20h]
0x1800075f7  mov     rdi, [rcx+28h]
0x1800075fb  mov     rax, rdi
0x1800075fe  sub     rax, rbx
0x180007601  cmp     rax, 10h
0x180007605  jb      loc_180007771
0x18000760b  mov     ebp, 1
0x180007610  lea     r14d, [rbp+1]
0x180007614  mov     r15d, 1FFh
0x18000761a  cmp     rbx, rdi
0x18000761d  jz      loc_18000773E
0x180007623  mov     r8, [rbx+8]
0x180007627  mov     r10d, [rbx]
0x18000762a  prefetchw byte ptr [r8]
0x18000762e  mov     eax, [r8]
0x180007631  mov     ecx, eax
0x180007633  and     ecx, 0FFC0401Eh
0x180007639  lock cmpxchg [r8], ecx
0x18000763e  jnz     short loc_180007631
0x180007640  mov     ecx, eax
0x180007642  mov     r9d, eax
0x180007645  shr     r9d, 1
0x180007648  and     r9d, 0Fh
0x18000764c  jz      short loc_18000766B
0x18000764e  prefetchw byte ptr [r8+4]
0x180007653  mov     eax, [r8+4]
0x180007657  mov     edx, eax
0x180007659  or      edx, r9d
0x18000765c  lock cmpxchg [r8+4], edx
0x180007662  jnz     short loc_180007657
0x180007664  not     eax
0x180007666  and     eax, r9d
0x180007669  jmp     short loc_18000766E
0x18000766b  mov     eax, r9d
0x18000766e  test    bpl, al
0x180007671  jz      short loc_180007687
0x180007673  mov     [rsp+0A8h+var_78], r10d
0x180007678  mov     [rsp+0A8h+var_74], 10002h
0x180007680  lea     rdx, [rsp+0A8h+var_70]
0x180007685  jmp     short loc_18000768C
0x180007687  lea     rdx, [rsp+0A8h+var_78]
0x18000768c  test    r14b, al
0x18000768f  jz      short loc_18000769F
0x180007691  mov     [rdx], r10d
0x180007694  mov     dword ptr [rdx+4], 10006h
0x18000769b  add     rdx, 8
0x18000769f  test    al, 4
0x1800076a1  jz      short loc_1800076B1
0x1800076a3  mov     [rdx], r10d
0x1800076a6  mov     dword ptr [rdx+4], 10003h
0x1800076ad  add     rdx, 8
0x1800076b1  cmp     eax, 8
0x1800076b4  jb      short loc_1800076C4
0x1800076b6  mov     [rdx], r10d
0x1800076b9  mov     dword ptr [rdx+4], 10007h
0x1800076c0  add     rdx, 8
0x1800076c4  mov     r8d, ecx
0x1800076c7  shr     r8d, 5
0x1800076cb  test    r15d, r8d
0x1800076ce  jz      short loc_1800076F0
0x1800076d0  mov     [rdx], r10d
0x1800076d3  mov     eax, ecx
0x1800076d5  shr     eax, 0Eh
0x1800076d8  and     ax, bp
0x1800076db  shl     ax, 2
0x1800076df  mov     [rdx+4], ax
0x1800076e3  and     r8w, r15w; unsigned __int64
0x1800076e7  mov     [rdx+6], r8w
0x1800076ec  add     rdx, 8
0x1800076f0  mov     eax, ecx
0x1800076f2  shr     eax, 0Fh
0x1800076f5  test    al, 7Fh
0x1800076f7  jz      short loc_180007719
0x1800076f9  mov     [rdx], r10d
0x1800076fc  shr     ecx, 16h
0x1800076ff  and     cx, bp
0x180007702  shl     cx, 2
0x180007706  add     cx, bp
0x180007709  mov     [rdx+4], cx
0x18000770d  and     ax, 7Fh
0x180007711  mov     [rdx+6], ax
0x180007715  add     rdx, 8
0x180007719  lea     rax, [rsp+0A8h+var_78]
0x18000771e  sub     rdx, rax
0x180007721  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x180007725  test    rdx, rdx
0x180007728  jle     short loc_180007735
0x18000772a  lea     rcx, [rsp+0A8h+var_78]; this
0x18000772f  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x180007734  nop
0x180007735  add     rbx, 10h
0x180007739  jmp     loc_18000761A
0x18000773e  mov     rax, [rsi+20h]
0x180007742  mov     [rsi+28h], rax
0x180007746  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000774d  test    rax, rax
0x180007750  jnz     short loc_18000775E
0x180007752  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180007759  test    rax, rax
0x18000775c  jz      short loc_180007771
0x18000775e  xor     r9d, r9d
0x180007761  xor     r8d, r8d
0x180007764  mov     edx, 0FEh
0x180007769  xor     ecx, ecx
0x18000776b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007770  nop
0x180007771  mov     rcx, [rsp+0A8h+var_48]
0x180007776  xor     rcx, rsp; StackCookie
0x180007779  call    __security_check_cookie
0x18000777e  add     rsp, 78h
0x180007782  pop     r15
0x180007784  pop     r14
0x180007786  pop     rdi
0x180007787  pop     rsi
0x180007788  pop     rbp
0x180007789  pop     rbx
0x18000778a  retn
```
