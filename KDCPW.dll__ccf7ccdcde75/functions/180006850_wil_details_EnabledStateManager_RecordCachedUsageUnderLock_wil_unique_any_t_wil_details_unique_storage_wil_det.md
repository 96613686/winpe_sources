# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x180006850`
- end: `0x180006a05`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `437`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800025b0`
- `0x1800026f0`
- `0x18000624c`

## callees

- `0x180001630`
- `0x180006850`
- `0x180008c14`
- `0x18000d010`

## pseudocode

```c
__int64 (__fastcall *__fastcall wil::details::EnabledStateManager::RecordCachedUsageUnderLock(
        __int64 a1))(_QWORD, __int64, _QWORD, _QWORD)
{
  int *v1; // rdi
  int *v3; // rbx
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

  v1 = *(int **)(a1 + 40);
  v3 = *(int **)(a1 + 32);
  result = (__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))((char *)v1 - (char *)v3);
  if ( (unsigned __int64)((char *)v1 - (char *)v3) >= 0x10 )
  {
    while ( v3 != v1 )
    {
      v5 = *((_QWORD *)v3 + 1);
      v6 = *v3;
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
        v9 = &v13;
        v12[1] = 65538;
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
        LOWORD(v10) = v10 & 0x1FF;
        *(_DWORD *)v9 = v6;
        *((_WORD *)v9 + 3) = v10;
        *((_WORD *)v9 + 2) = 4 * ((v7 >> 14) & 1);
        v9 += 8;
      }
      if ( ((v7 >> 15) & 0x7F) != 0 )
      {
        *(_DWORD *)v9 = v6;
        *((_WORD *)v9 + 3) = (v7 >> 15) & 0x7F;
        *((_WORD *)v9 + 2) = 4 * ((v7 >> 22) & 1) + 1;
        v9 += 8;
      }
      v11 = (v9 - (char *)v12) >> 3;
      if ( v11 > 0 )
        wil::details::WilApi_RecordFeatureUsageReports(
          (wil::details *)v12,
          (struct __WIL_RTL_FEATURE_USAGE_DATA *)v11,
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
0x180006850  push    rbx
0x180006852  push    rbp
0x180006853  push    rsi
0x180006854  push    rdi
0x180006855  push    r14
0x180006857  push    r15
0x180006859  sub     rsp, 78h
0x18000685d  mov     rax, cs:__security_cookie
0x180006864  xor     rax, rsp
0x180006867  mov     [rsp+0A8h+var_48], rax
0x18000686c  mov     rdi, [rcx+28h]
0x180006870  mov     rsi, rcx
0x180006873  mov     rbx, [rcx+20h]
0x180006877  mov     rax, rdi
0x18000687a  sub     rax, rbx
0x18000687d  cmp     rax, 10h
0x180006881  jb      loc_1800069EB
0x180006887  mov     ebp, 1
0x18000688c  mov     r15d, 1FFh
0x180006892  lea     r14d, [rbp+1]
0x180006896  cmp     rbx, rdi
0x180006899  jz      loc_1800069B9
0x18000689f  mov     r8, [rbx+8]
0x1800068a3  mov     r10d, [rbx]
0x1800068a6  prefetchw byte ptr [r8]
0x1800068aa  mov     eax, [r8]
0x1800068ad  mov     ecx, eax
0x1800068af  and     ecx, 0FFC0401Eh
0x1800068b5  lock cmpxchg [r8], ecx
0x1800068ba  jnz     short loc_1800068AD
0x1800068bc  mov     r9d, eax
0x1800068bf  mov     ecx, eax
0x1800068c1  shr     r9d, 1
0x1800068c4  and     r9d, 0Fh
0x1800068c8  jz      short loc_1800068E7
0x1800068ca  prefetchw byte ptr [r8+4]
0x1800068cf  mov     eax, [r8+4]
0x1800068d3  mov     edx, eax
0x1800068d5  or      edx, r9d
0x1800068d8  lock cmpxchg [r8+4], edx
0x1800068de  jnz     short loc_1800068D3
0x1800068e0  not     eax
0x1800068e2  and     eax, r9d
0x1800068e5  jmp     short loc_1800068EA
0x1800068e7  mov     eax, r9d
0x1800068ea  test    bpl, al
0x1800068ed  jz      short loc_180006903
0x1800068ef  mov     [rsp+0A8h+var_78], r10d
0x1800068f4  lea     rdx, [rsp+0A8h+var_70]
0x1800068f9  mov     [rsp+0A8h+var_74], 10002h
0x180006901  jmp     short loc_180006908
0x180006903  lea     rdx, [rsp+0A8h+var_78]
0x180006908  test    r14b, al
0x18000690b  jz      short loc_18000691B
0x18000690d  mov     [rdx], r10d
0x180006910  mov     dword ptr [rdx+4], 10006h
0x180006917  add     rdx, 8
0x18000691b  test    al, 4
0x18000691d  jz      short loc_18000692D
0x18000691f  mov     [rdx], r10d
0x180006922  mov     dword ptr [rdx+4], 10003h
0x180006929  add     rdx, 8
0x18000692d  cmp     eax, 8
0x180006930  jb      short loc_180006940
0x180006932  mov     [rdx], r10d
0x180006935  mov     dword ptr [rdx+4], 10007h
0x18000693c  add     rdx, 8
0x180006940  mov     r8d, ecx
0x180006943  shr     r8d, 5
0x180006947  test    r15d, r8d
0x18000694a  jz      short loc_18000696C
0x18000694c  and     r8w, r15w; unsigned __int64
0x180006950  mov     [rdx], r10d
0x180006953  mov     eax, ecx
0x180006955  mov     [rdx+6], r8w
0x18000695a  shr     eax, 0Eh
0x18000695d  and     ax, bp
0x180006960  shl     ax, 2
0x180006964  mov     [rdx+4], ax
0x180006968  add     rdx, 8
0x18000696c  mov     eax, ecx
0x18000696e  shr     eax, 0Fh
0x180006971  test    al, 7Fh
0x180006973  jz      short loc_180006995
0x180006975  shr     ecx, 16h
0x180006978  and     ax, 7Fh
0x18000697c  and     cx, bp
0x18000697f  mov     [rdx], r10d
0x180006982  shl     cx, 2
0x180006986  add     cx, bp
0x180006989  mov     [rdx+6], ax
0x18000698d  mov     [rdx+4], cx
0x180006991  add     rdx, 8
0x180006995  lea     rax, [rsp+0A8h+var_78]
0x18000699a  sub     rdx, rax
0x18000699d  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x1800069a1  test    rdx, rdx
0x1800069a4  jle     short loc_1800069B0
0x1800069a6  lea     rcx, [rsp+0A8h+var_78]; this
0x1800069ab  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x1800069b0  add     rbx, 10h
0x1800069b4  jmp     loc_180006896
0x1800069b9  mov     rax, [rsi+20h]
0x1800069bd  mov     [rsi+28h], rax
0x1800069c1  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x1800069c8  test    rax, rax
0x1800069cb  jnz     short loc_1800069D9
0x1800069cd  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x1800069d4  test    rax, rax
0x1800069d7  jz      short loc_1800069EB
0x1800069d9  xor     r9d, r9d
0x1800069dc  xor     r8d, r8d
0x1800069df  mov     edx, 0FEh
0x1800069e4  xor     ecx, ecx
0x1800069e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069eb  mov     rcx, [rsp+0A8h+var_48]
0x1800069f0  xor     rcx, rsp; StackCookie
0x1800069f3  call    __security_check_cookie
0x1800069f8  add     rsp, 78h
0x1800069fc  pop     r15
0x1800069fe  pop     r14
0x180006a00  pop     rdi
0x180006a01  pop     rsi
0x180006a02  pop     rbp
0x180006a03  pop     rbx
0x180006a04  retn
```
