# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x140008440`
- end: `0x1400085f7`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `439`
- prototype: `__int64 (__fastcall *__fastcall(__int64))(_QWORD, __int64, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400021e0`
- `0x140002320`
- `0x140007dd0`

## callees

- `0x1400016a0`
- `0x140008440`
- `0x14000b284`
- `0x140012010`

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
0x140008440  push    rbx
0x140008442  push    rbp
0x140008443  push    rsi
0x140008444  push    rdi
0x140008445  push    r14
0x140008447  push    r15
0x140008449  sub     rsp, 78h
0x14000844d  mov     rax, cs:__security_cookie
0x140008454  xor     rax, rsp
0x140008457  mov     [rsp+0A8h+var_48], rax
0x14000845c  mov     rsi, rcx
0x14000845f  mov     rbx, [rcx+20h]
0x140008463  mov     rdi, [rcx+28h]
0x140008467  mov     rax, rdi
0x14000846a  sub     rax, rbx
0x14000846d  cmp     rax, 10h
0x140008471  jb      loc_1400085DD
0x140008477  mov     ebp, 1
0x14000847c  lea     r14d, [rbp+1]
0x140008480  mov     r15d, 1FFh
0x140008486  cmp     rbx, rdi
0x140008489  jz      loc_1400085AA
0x14000848f  mov     r8, [rbx+8]
0x140008493  mov     r10d, [rbx]
0x140008496  prefetchw byte ptr [r8]
0x14000849a  mov     eax, [r8]
0x14000849d  mov     ecx, eax
0x14000849f  and     ecx, 0FFC0401Eh
0x1400084a5  lock cmpxchg [r8], ecx
0x1400084aa  jnz     short loc_14000849D
0x1400084ac  mov     ecx, eax
0x1400084ae  mov     r9d, eax
0x1400084b1  shr     r9d, 1
0x1400084b4  and     r9d, 0Fh
0x1400084b8  jz      short loc_1400084D7
0x1400084ba  prefetchw byte ptr [r8+4]
0x1400084bf  mov     eax, [r8+4]
0x1400084c3  mov     edx, eax
0x1400084c5  or      edx, r9d
0x1400084c8  lock cmpxchg [r8+4], edx
0x1400084ce  jnz     short loc_1400084C3
0x1400084d0  not     eax
0x1400084d2  and     eax, r9d
0x1400084d5  jmp     short loc_1400084DA
0x1400084d7  mov     eax, r9d
0x1400084da  test    bpl, al
0x1400084dd  jz      short loc_1400084F3
0x1400084df  mov     [rsp+0A8h+var_78], r10d
0x1400084e4  mov     [rsp+0A8h+var_74], 10002h
0x1400084ec  lea     rdx, [rsp+0A8h+var_70]
0x1400084f1  jmp     short loc_1400084F8
0x1400084f3  lea     rdx, [rsp+0A8h+var_78]
0x1400084f8  test    r14b, al
0x1400084fb  jz      short loc_14000850B
0x1400084fd  mov     [rdx], r10d
0x140008500  mov     dword ptr [rdx+4], 10006h
0x140008507  add     rdx, 8
0x14000850b  test    al, 4
0x14000850d  jz      short loc_14000851D
0x14000850f  mov     [rdx], r10d
0x140008512  mov     dword ptr [rdx+4], 10003h
0x140008519  add     rdx, 8
0x14000851d  cmp     eax, 8
0x140008520  jb      short loc_140008530
0x140008522  mov     [rdx], r10d
0x140008525  mov     dword ptr [rdx+4], 10007h
0x14000852c  add     rdx, 8
0x140008530  mov     r8d, ecx
0x140008533  shr     r8d, 5
0x140008537  test    r15d, r8d
0x14000853a  jz      short loc_14000855C
0x14000853c  mov     [rdx], r10d
0x14000853f  mov     eax, ecx
0x140008541  shr     eax, 0Eh
0x140008544  and     ax, bp
0x140008547  shl     ax, 2
0x14000854b  mov     [rdx+4], ax
0x14000854f  and     r8w, r15w; unsigned __int64
0x140008553  mov     [rdx+6], r8w
0x140008558  add     rdx, 8
0x14000855c  mov     eax, ecx
0x14000855e  shr     eax, 0Fh
0x140008561  test    al, 7Fh
0x140008563  jz      short loc_140008585
0x140008565  mov     [rdx], r10d
0x140008568  shr     ecx, 16h
0x14000856b  and     cx, bp
0x14000856e  shl     cx, 2
0x140008572  add     cx, bp
0x140008575  mov     [rdx+4], cx
0x140008579  and     ax, 7Fh
0x14000857d  mov     [rdx+6], ax
0x140008581  add     rdx, 8
0x140008585  lea     rax, [rsp+0A8h+var_78]
0x14000858a  sub     rdx, rax
0x14000858d  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x140008591  test    rdx, rdx
0x140008594  jle     short loc_1400085A1
0x140008596  lea     rcx, [rsp+0A8h+var_78]; this
0x14000859b  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x1400085a0  nop
0x1400085a1  add     rbx, 10h
0x1400085a5  jmp     loc_140008486
0x1400085aa  mov     rax, [rsi+20h]
0x1400085ae  mov     [rsi+28h], rax
0x1400085b2  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x1400085b9  test    rax, rax
0x1400085bc  jnz     short loc_1400085CA
0x1400085be  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x1400085c5  test    rax, rax
0x1400085c8  jz      short loc_1400085DD
0x1400085ca  xor     r9d, r9d
0x1400085cd  xor     r8d, r8d
0x1400085d0  mov     edx, 0FEh
0x1400085d5  xor     ecx, ecx
0x1400085d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400085dc  nop
0x1400085dd  mov     rcx, [rsp+0A8h+var_48]
0x1400085e2  xor     rcx, rsp; StackCookie
0x1400085e5  call    __security_check_cookie
0x1400085ea  add     rsp, 78h
0x1400085ee  pop     r15
0x1400085f0  pop     r14
0x1400085f2  pop     rdi
0x1400085f3  pop     rsi
0x1400085f4  pop     rbp
0x1400085f5  pop     rbx
0x1400085f6  retn
```
