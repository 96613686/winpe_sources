# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x18000d64c`
- end: `0x18000d81a`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `462`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000d214`
- `0x180018410`
- `0x180018470`

## callees

- `0x180002880`
- `0x18000d64c`
- `0x1800101a8`
- `0x18002c010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 (__fastcall *__fastcall wil::details::EnabledStateManager::RecordCachedUsageUnderLock(
        __int64 a1))(_QWORD, __int64, _QWORD, _QWORD)
{
  int *v2; // rsi
  int *v3; // rbx
  __int64 (__fastcall *result)(_QWORD, __int64, _QWORD, _QWORD); // rax
  __int64 v5; // r9
  int v6; // r10d
  unsigned __int32 v7; // edx
  unsigned int v8; // ecx
  char *v9; // r8
  signed __int64 v10; // r8
  _DWORD v11[2]; // [rsp+30h] [rbp-58h] BYREF
  char v12; // [rsp+38h] [rbp-50h] BYREF

  v2 = *(int **)(a1 + 40);
  v3 = *(int **)(a1 + 32);
  result = (__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))((char *)v2 - (char *)v3);
  if ( (unsigned __int64)((char *)v2 - (char *)v3) >= 0x10 )
  {
    while ( v3 != v2 )
    {
      v5 = *((_QWORD *)v3 + 1);
      v6 = *v3;
      _m_prefetchw((const void *)v5);
      v7 = _InterlockedAnd((volatile signed __int32 *)v5, 0xFFC0401E);
      v8 = (v7 >> 1) & 0xF;
      if ( v8 )
      {
        _m_prefetchw((const void *)(v5 + 4));
        v8 &= ~_InterlockedOr((volatile signed __int32 *)(v5 + 4), v8);
      }
      v9 = (char *)v11;
      if ( (v8 & 1) != 0 )
      {
        v11[0] = v6;
        v11[1] = 65538;
        v9 = &v12;
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
      if ( ((v7 >> 5) & 0x1FF) != 0 )
      {
        *(_DWORD *)v9 = v6;
        *((_WORD *)v9 + 2) = 4 * ((v7 >> 14) & 1);
        *((_WORD *)v9 + 3) = (v7 >> 5) & 0x1FF;
        v9 += 8;
      }
      if ( ((v7 >> 15) & 0x7F) != 0 )
      {
        *(_DWORD *)v9 = v6;
        *((_WORD *)v9 + 2) = 4 * ((v7 >> 22) & 1) + 1;
        *((_WORD *)v9 + 3) = (v7 >> 15) & 0x7F;
        v9 += 8;
      }
      v10 = (v9 - (char *)v11) >> 3;
      if ( v10 > 0 )
        wil::details::WilApi_RecordFeatureUsageReports(
          (wil::details *)v11,
          (struct __WIL_RTL_FEATURE_USAGE_DATA *)v10,
          v10);
      v3 += 4;
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
0x18000d64c  mov     [rsp+arg_8], rbx
0x18000d651  mov     [rsp+arg_10], rbp
0x18000d656  mov     [rsp+arg_18], rsi
0x18000d65b  push    rdi
0x18000d65c  push    r14
0x18000d65e  push    r15
0x18000d660  sub     rsp, 70h
0x18000d664  mov     rax, cs:__security_cookie
0x18000d66b  xor     rax, rsp
0x18000d66e  mov     [rsp+88h+var_28], rax
0x18000d673  mov     rdi, rcx
0x18000d676  mov     rsi, [rcx+28h]
0x18000d67a  mov     rbx, [rcx+20h]
0x18000d67e  mov     rax, rsi
0x18000d681  sub     rax, rbx
0x18000d684  cmp     rax, 10h
0x18000d688  jb      loc_18000D7F2
0x18000d68e  mov     ebp, 1
0x18000d693  lea     r14d, [rbp+1]
0x18000d697  mov     r15d, 1FFh
0x18000d69d  cmp     rbx, rsi
0x18000d6a0  jz      loc_18000D7BF
0x18000d6a6  mov     r9, [rbx+8]
0x18000d6aa  mov     r10d, [rbx]
0x18000d6ad  prefetchw byte ptr [r9]
0x18000d6b1  mov     eax, [r9]
0x18000d6b4  mov     ecx, eax
0x18000d6b6  and     ecx, 0FFC0401Eh
0x18000d6bc  lock cmpxchg [r9], ecx
0x18000d6c1  jnz     short loc_18000D6B4
0x18000d6c3  mov     edx, eax
0x18000d6c5  mov     ecx, eax
0x18000d6c7  shr     ecx, 1
0x18000d6c9  and     ecx, 0Fh
0x18000d6cc  jz      short loc_18000D6E9
0x18000d6ce  prefetchw byte ptr [r9+4]
0x18000d6d3  mov     eax, [r9+4]
0x18000d6d7  mov     r8d, eax
0x18000d6da  or      r8d, ecx
0x18000d6dd  lock cmpxchg [r9+4], r8d
0x18000d6e3  jnz     short loc_18000D6D7
0x18000d6e5  not     eax
0x18000d6e7  and     ecx, eax
0x18000d6e9  lea     r8, [rsp+88h+var_58]
0x18000d6ee  test    bpl, cl
0x18000d6f1  jz      short loc_18000D705
0x18000d6f3  mov     [rsp+88h+var_58], r10d
0x18000d6f8  mov     [rsp+88h+var_54], 10002h
0x18000d700  lea     r8, [rsp+88h+var_50]
0x18000d705  test    r14b, cl
0x18000d708  jz      short loc_18000D719
0x18000d70a  mov     [r8], r10d
0x18000d70d  mov     dword ptr [r8+4], 10006h
0x18000d715  add     r8, 8
0x18000d719  test    cl, 4
0x18000d71c  jz      short loc_18000D72D
0x18000d71e  mov     [r8], r10d
0x18000d721  mov     dword ptr [r8+4], 10003h
0x18000d729  add     r8, 8
0x18000d72d  cmp     ecx, 8
0x18000d730  jb      short loc_18000D741
0x18000d732  mov     [r8], r10d
0x18000d735  mov     dword ptr [r8+4], 10007h
0x18000d73d  add     r8, 8
0x18000d741  mov     ecx, edx
0x18000d743  shr     ecx, 5
0x18000d746  test    r15d, ecx
0x18000d749  jz      short loc_18000D76C
0x18000d74b  mov     [r8], r10d
0x18000d74e  mov     eax, edx
0x18000d750  shr     eax, 0Eh
0x18000d753  and     ax, bp
0x18000d756  shl     ax, 2
0x18000d75a  mov     [r8+4], ax
0x18000d75f  and     cx, r15w
0x18000d763  mov     [r8+6], cx
0x18000d768  add     r8, 8
0x18000d76c  mov     eax, edx
0x18000d76e  shr     eax, 0Fh
0x18000d771  test    al, 7Fh
0x18000d773  jz      short loc_18000D797
0x18000d775  mov     [r8], r10d
0x18000d778  shr     edx, 16h
0x18000d77b  and     dx, bp
0x18000d77e  shl     dx, 2
0x18000d782  add     dx, bp
0x18000d785  mov     [r8+4], dx
0x18000d78a  and     ax, 7Fh
0x18000d78e  mov     [r8+6], ax
0x18000d793  add     r8, 8
0x18000d797  lea     rax, [rsp+88h+var_58]
0x18000d79c  sub     r8, rax
0x18000d79f  sar     r8, 3; unsigned __int64
0x18000d7a3  test    r8, r8
0x18000d7a6  jle     short loc_18000D7B6
0x18000d7a8  mov     rdx, r8; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x18000d7ab  lea     rcx, [rsp+88h+var_58]; this
0x18000d7b0  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x18000d7b5  nop
0x18000d7b6  add     rbx, 10h
0x18000d7ba  jmp     loc_18000D69D
0x18000d7bf  mov     rax, [rdi+20h]
0x18000d7c3  mov     [rdi+28h], rax
0x18000d7c7  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000d7ce  test    rax, rax
0x18000d7d1  jnz     short loc_18000D7DF
0x18000d7d3  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000d7da  test    rax, rax
0x18000d7dd  jz      short loc_18000D7F2
0x18000d7df  xor     r9d, r9d
0x18000d7e2  xor     r8d, r8d
0x18000d7e5  mov     edx, 0FEh
0x18000d7ea  xor     ecx, ecx
0x18000d7ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7f1  nop
0x18000d7f2  mov     rcx, [rsp+88h+var_28]
0x18000d7f7  xor     rcx, rsp; StackCookie
0x18000d7fa  call    __security_check_cookie
0x18000d7ff  lea     r11, [rsp+88h+var_18]
0x18000d804  mov     rbx, [r11+28h]
0x18000d808  mov     rbp, [r11+30h]
0x18000d80c  mov     rsi, [r11+38h]
0x18000d810  mov     rsp, r11
0x18000d813  pop     r15
0x18000d815  pop     r14
0x18000d817  pop     rdi
0x18000d818  retn
```
