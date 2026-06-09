# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x1800208ac`
- end: `0x180020a63`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `439`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001bb30`
- `0x18001bb90`
- `0x18002032c`

## callees

- `0x180004180`
- `0x1800208ac`
- `0x18002107c`
- `0x180032010`

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
0x1800208ac  push    rbx
0x1800208ae  push    rbp
0x1800208af  push    rsi
0x1800208b0  push    rdi
0x1800208b1  push    r14
0x1800208b3  push    r15
0x1800208b5  sub     rsp, 78h
0x1800208b9  mov     rax, cs:__security_cookie
0x1800208c0  xor     rax, rsp
0x1800208c3  mov     [rsp+0A8h+var_48], rax
0x1800208c8  mov     rsi, rcx
0x1800208cb  mov     rbx, [rcx+20h]
0x1800208cf  mov     rdi, [rcx+28h]
0x1800208d3  mov     rax, rdi
0x1800208d6  sub     rax, rbx
0x1800208d9  cmp     rax, 10h
0x1800208dd  jb      loc_180020A49
0x1800208e3  mov     ebp, 1
0x1800208e8  lea     r14d, [rbp+1]
0x1800208ec  mov     r15d, 1FFh
0x1800208f2  cmp     rbx, rdi
0x1800208f5  jz      loc_180020A16
0x1800208fb  mov     r8, [rbx+8]
0x1800208ff  mov     r10d, [rbx]
0x180020902  prefetchw byte ptr [r8]
0x180020906  mov     eax, [r8]
0x180020909  mov     ecx, eax
0x18002090b  and     ecx, 0FFC0401Eh
0x180020911  lock cmpxchg [r8], ecx
0x180020916  jnz     short loc_180020909
0x180020918  mov     ecx, eax
0x18002091a  mov     r9d, eax
0x18002091d  shr     r9d, 1
0x180020920  and     r9d, 0Fh
0x180020924  jz      short loc_180020943
0x180020926  prefetchw byte ptr [r8+4]
0x18002092b  mov     eax, [r8+4]
0x18002092f  mov     edx, eax
0x180020931  or      edx, r9d
0x180020934  lock cmpxchg [r8+4], edx
0x18002093a  jnz     short loc_18002092F
0x18002093c  not     eax
0x18002093e  and     eax, r9d
0x180020941  jmp     short loc_180020946
0x180020943  mov     eax, r9d
0x180020946  test    bpl, al
0x180020949  jz      short loc_18002095F
0x18002094b  mov     [rsp+0A8h+var_78], r10d
0x180020950  mov     [rsp+0A8h+var_74], 10002h
0x180020958  lea     rdx, [rsp+0A8h+var_70]
0x18002095d  jmp     short loc_180020964
0x18002095f  lea     rdx, [rsp+0A8h+var_78]
0x180020964  test    r14b, al
0x180020967  jz      short loc_180020977
0x180020969  mov     [rdx], r10d
0x18002096c  mov     dword ptr [rdx+4], 10006h
0x180020973  add     rdx, 8
0x180020977  test    al, 4
0x180020979  jz      short loc_180020989
0x18002097b  mov     [rdx], r10d
0x18002097e  mov     dword ptr [rdx+4], 10003h
0x180020985  add     rdx, 8
0x180020989  cmp     eax, 8
0x18002098c  jb      short loc_18002099C
0x18002098e  mov     [rdx], r10d
0x180020991  mov     dword ptr [rdx+4], 10007h
0x180020998  add     rdx, 8
0x18002099c  mov     r8d, ecx
0x18002099f  shr     r8d, 5
0x1800209a3  test    r15d, r8d
0x1800209a6  jz      short loc_1800209C8
0x1800209a8  mov     [rdx], r10d
0x1800209ab  mov     eax, ecx
0x1800209ad  shr     eax, 0Eh
0x1800209b0  and     ax, bp
0x1800209b3  shl     ax, 2
0x1800209b7  mov     [rdx+4], ax
0x1800209bb  and     r8w, r15w; unsigned __int64
0x1800209bf  mov     [rdx+6], r8w
0x1800209c4  add     rdx, 8
0x1800209c8  mov     eax, ecx
0x1800209ca  shr     eax, 0Fh
0x1800209cd  test    al, 7Fh
0x1800209cf  jz      short loc_1800209F1
0x1800209d1  mov     [rdx], r10d
0x1800209d4  shr     ecx, 16h
0x1800209d7  and     cx, bp
0x1800209da  shl     cx, 2
0x1800209de  add     cx, bp
0x1800209e1  mov     [rdx+4], cx
0x1800209e5  and     ax, 7Fh
0x1800209e9  mov     [rdx+6], ax
0x1800209ed  add     rdx, 8
0x1800209f1  lea     rax, [rsp+0A8h+var_78]
0x1800209f6  sub     rdx, rax
0x1800209f9  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x1800209fd  test    rdx, rdx
0x180020a00  jle     short loc_180020A0D
0x180020a02  lea     rcx, [rsp+0A8h+var_78]; this
0x180020a07  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x180020a0c  nop
0x180020a0d  add     rbx, 10h
0x180020a11  jmp     loc_1800208F2
0x180020a16  mov     rax, [rsi+20h]
0x180020a1a  mov     [rsi+28h], rax
0x180020a1e  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180020a25  test    rax, rax
0x180020a28  jnz     short loc_180020A36
0x180020a2a  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180020a31  test    rax, rax
0x180020a34  jz      short loc_180020A49
0x180020a36  xor     r9d, r9d
0x180020a39  xor     r8d, r8d
0x180020a3c  mov     edx, 0FEh
0x180020a41  xor     ecx, ecx
0x180020a43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a48  nop
0x180020a49  mov     rcx, [rsp+0A8h+var_48]
0x180020a4e  xor     rcx, rsp; StackCookie
0x180020a51  call    __security_check_cookie
0x180020a56  add     rsp, 78h
0x180020a5a  pop     r15
0x180020a5c  pop     r14
0x180020a5e  pop     rdi
0x180020a5f  pop     rsi
0x180020a60  pop     rbp
0x180020a61  pop     rbx
0x180020a62  retn
```
