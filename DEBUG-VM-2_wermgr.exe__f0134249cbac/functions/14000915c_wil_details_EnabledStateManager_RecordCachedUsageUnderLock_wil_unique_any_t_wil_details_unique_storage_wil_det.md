# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x14000915c`
- end: `0x140009313`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `439`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140003950`
- `0x1400039b0`
- `0x140008f4c`

## callees

- `0x140003200`
- `0x14000915c`
- `0x14000d684`
- `0x14001e010`

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
0x14000915c  push    rbx
0x14000915e  push    rbp
0x14000915f  push    rsi
0x140009160  push    rdi
0x140009161  push    r14
0x140009163  push    r15
0x140009165  sub     rsp, 78h
0x140009169  mov     rax, cs:__security_cookie
0x140009170  xor     rax, rsp
0x140009173  mov     [rsp+0A8h+var_48], rax
0x140009178  mov     rsi, rcx
0x14000917b  mov     rbx, [rcx+20h]
0x14000917f  mov     rdi, [rcx+28h]
0x140009183  mov     rax, rdi
0x140009186  sub     rax, rbx
0x140009189  cmp     rax, 10h
0x14000918d  jb      loc_1400092F9
0x140009193  mov     ebp, 1
0x140009198  lea     r14d, [rbp+1]
0x14000919c  mov     r15d, 1FFh
0x1400091a2  cmp     rbx, rdi
0x1400091a5  jz      loc_1400092C6
0x1400091ab  mov     r8, [rbx+8]
0x1400091af  mov     r10d, [rbx]
0x1400091b2  prefetchw byte ptr [r8]
0x1400091b6  mov     eax, [r8]
0x1400091b9  mov     ecx, eax
0x1400091bb  and     ecx, 0FFC0401Eh
0x1400091c1  lock cmpxchg [r8], ecx
0x1400091c6  jnz     short loc_1400091B9
0x1400091c8  mov     ecx, eax
0x1400091ca  mov     r9d, eax
0x1400091cd  shr     r9d, 1
0x1400091d0  and     r9d, 0Fh
0x1400091d4  jz      short loc_1400091F3
0x1400091d6  prefetchw byte ptr [r8+4]
0x1400091db  mov     eax, [r8+4]
0x1400091df  mov     edx, eax
0x1400091e1  or      edx, r9d
0x1400091e4  lock cmpxchg [r8+4], edx
0x1400091ea  jnz     short loc_1400091DF
0x1400091ec  not     eax
0x1400091ee  and     eax, r9d
0x1400091f1  jmp     short loc_1400091F6
0x1400091f3  mov     eax, r9d
0x1400091f6  test    bpl, al
0x1400091f9  jz      short loc_14000920F
0x1400091fb  mov     [rsp+0A8h+var_78], r10d
0x140009200  mov     [rsp+0A8h+var_74], 10002h
0x140009208  lea     rdx, [rsp+0A8h+var_70]
0x14000920d  jmp     short loc_140009214
0x14000920f  lea     rdx, [rsp+0A8h+var_78]
0x140009214  test    r14b, al
0x140009217  jz      short loc_140009227
0x140009219  mov     [rdx], r10d
0x14000921c  mov     dword ptr [rdx+4], 10006h
0x140009223  add     rdx, 8
0x140009227  test    al, 4
0x140009229  jz      short loc_140009239
0x14000922b  mov     [rdx], r10d
0x14000922e  mov     dword ptr [rdx+4], 10003h
0x140009235  add     rdx, 8
0x140009239  cmp     eax, 8
0x14000923c  jb      short loc_14000924C
0x14000923e  mov     [rdx], r10d
0x140009241  mov     dword ptr [rdx+4], 10007h
0x140009248  add     rdx, 8
0x14000924c  mov     r8d, ecx
0x14000924f  shr     r8d, 5
0x140009253  test    r15d, r8d
0x140009256  jz      short loc_140009278
0x140009258  mov     [rdx], r10d
0x14000925b  mov     eax, ecx
0x14000925d  shr     eax, 0Eh
0x140009260  and     ax, bp
0x140009263  shl     ax, 2
0x140009267  mov     [rdx+4], ax
0x14000926b  and     r8w, r15w; unsigned __int64
0x14000926f  mov     [rdx+6], r8w
0x140009274  add     rdx, 8
0x140009278  mov     eax, ecx
0x14000927a  shr     eax, 0Fh
0x14000927d  test    al, 7Fh
0x14000927f  jz      short loc_1400092A1
0x140009281  mov     [rdx], r10d
0x140009284  shr     ecx, 16h
0x140009287  and     cx, bp
0x14000928a  shl     cx, 2
0x14000928e  add     cx, bp
0x140009291  mov     [rdx+4], cx
0x140009295  and     ax, 7Fh
0x140009299  mov     [rdx+6], ax
0x14000929d  add     rdx, 8
0x1400092a1  lea     rax, [rsp+0A8h+var_78]
0x1400092a6  sub     rdx, rax
0x1400092a9  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x1400092ad  test    rdx, rdx
0x1400092b0  jle     short loc_1400092BD
0x1400092b2  lea     rcx, [rsp+0A8h+var_78]; this
0x1400092b7  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x1400092bc  nop
0x1400092bd  add     rbx, 10h
0x1400092c1  jmp     loc_1400091A2
0x1400092c6  mov     rax, [rsi+20h]
0x1400092ca  mov     [rsi+28h], rax
0x1400092ce  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x1400092d5  test    rax, rax
0x1400092d8  jnz     short loc_1400092E6
0x1400092da  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x1400092e1  test    rax, rax
0x1400092e4  jz      short loc_1400092F9
0x1400092e6  xor     r9d, r9d
0x1400092e9  xor     r8d, r8d
0x1400092ec  mov     edx, 0FEh
0x1400092f1  xor     ecx, ecx
0x1400092f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400092f8  nop
0x1400092f9  mov     rcx, [rsp+0A8h+var_48]
0x1400092fe  xor     rcx, rsp; StackCookie
0x140009301  call    __security_check_cookie
0x140009306  add     rsp, 78h
0x14000930a  pop     r15
0x14000930c  pop     r14
0x14000930e  pop     rdi
0x14000930f  pop     rsi
0x140009310  pop     rbp
0x140009311  pop     rbx
0x140009312  retn
```
