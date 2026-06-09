# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x180008514`
- end: `0x1800086cb`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `439`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180007ea4`

## callees

- `0x180008514`
- `0x18000adc4`
- `0x18000f5f0`
- `0x180011010`

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
0x180008514  push    rbx
0x180008516  push    rbp
0x180008517  push    rsi
0x180008518  push    rdi
0x180008519  push    r14
0x18000851b  push    r15
0x18000851d  sub     rsp, 78h
0x180008521  mov     rax, cs:__security_cookie
0x180008528  xor     rax, rsp
0x18000852b  mov     [rsp+0A8h+var_48], rax
0x180008530  mov     rsi, rcx
0x180008533  mov     rbx, [rcx+20h]
0x180008537  mov     rdi, [rcx+28h]
0x18000853b  mov     rax, rdi
0x18000853e  sub     rax, rbx
0x180008541  cmp     rax, 10h
0x180008545  jb      loc_1800086B1
0x18000854b  mov     ebp, 1
0x180008550  lea     r14d, [rbp+1]
0x180008554  mov     r15d, 1FFh
0x18000855a  cmp     rbx, rdi
0x18000855d  jz      loc_18000867E
0x180008563  mov     r8, [rbx+8]
0x180008567  mov     r10d, [rbx]
0x18000856a  prefetchw byte ptr [r8]
0x18000856e  mov     eax, [r8]
0x180008571  mov     ecx, eax
0x180008573  and     ecx, 0FFC0401Eh
0x180008579  lock cmpxchg [r8], ecx
0x18000857e  jnz     short loc_180008571
0x180008580  mov     ecx, eax
0x180008582  mov     r9d, eax
0x180008585  shr     r9d, 1
0x180008588  and     r9d, 0Fh
0x18000858c  jz      short loc_1800085AB
0x18000858e  prefetchw byte ptr [r8+4]
0x180008593  mov     eax, [r8+4]
0x180008597  mov     edx, eax
0x180008599  or      edx, r9d
0x18000859c  lock cmpxchg [r8+4], edx
0x1800085a2  jnz     short loc_180008597
0x1800085a4  not     eax
0x1800085a6  and     eax, r9d
0x1800085a9  jmp     short loc_1800085AE
0x1800085ab  mov     eax, r9d
0x1800085ae  test    bpl, al
0x1800085b1  jz      short loc_1800085C7
0x1800085b3  mov     [rsp+0A8h+var_78], r10d
0x1800085b8  mov     [rsp+0A8h+var_74], 10002h
0x1800085c0  lea     rdx, [rsp+0A8h+var_70]
0x1800085c5  jmp     short loc_1800085CC
0x1800085c7  lea     rdx, [rsp+0A8h+var_78]
0x1800085cc  test    r14b, al
0x1800085cf  jz      short loc_1800085DF
0x1800085d1  mov     [rdx], r10d
0x1800085d4  mov     dword ptr [rdx+4], 10006h
0x1800085db  add     rdx, 8
0x1800085df  test    al, 4
0x1800085e1  jz      short loc_1800085F1
0x1800085e3  mov     [rdx], r10d
0x1800085e6  mov     dword ptr [rdx+4], 10003h
0x1800085ed  add     rdx, 8
0x1800085f1  cmp     eax, 8
0x1800085f4  jb      short loc_180008604
0x1800085f6  mov     [rdx], r10d
0x1800085f9  mov     dword ptr [rdx+4], 10007h
0x180008600  add     rdx, 8
0x180008604  mov     r8d, ecx
0x180008607  shr     r8d, 5
0x18000860b  test    r15d, r8d
0x18000860e  jz      short loc_180008630
0x180008610  mov     [rdx], r10d
0x180008613  mov     eax, ecx
0x180008615  shr     eax, 0Eh
0x180008618  and     ax, bp
0x18000861b  shl     ax, 2
0x18000861f  mov     [rdx+4], ax
0x180008623  and     r8w, r15w; unsigned __int64
0x180008627  mov     [rdx+6], r8w
0x18000862c  add     rdx, 8
0x180008630  mov     eax, ecx
0x180008632  shr     eax, 0Fh
0x180008635  test    al, 7Fh
0x180008637  jz      short loc_180008659
0x180008639  mov     [rdx], r10d
0x18000863c  shr     ecx, 16h
0x18000863f  and     cx, bp
0x180008642  shl     cx, 2
0x180008646  add     cx, bp
0x180008649  mov     [rdx+4], cx
0x18000864d  and     ax, 7Fh
0x180008651  mov     [rdx+6], ax
0x180008655  add     rdx, 8
0x180008659  lea     rax, [rsp+0A8h+var_78]
0x18000865e  sub     rdx, rax
0x180008661  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x180008665  test    rdx, rdx
0x180008668  jle     short loc_180008675
0x18000866a  lea     rcx, [rsp+0A8h+var_78]; this
0x18000866f  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x180008674  nop
0x180008675  add     rbx, 10h
0x180008679  jmp     loc_18000855A
0x18000867e  mov     rax, [rsi+20h]
0x180008682  mov     [rsi+28h], rax
0x180008686  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000868d  test    rax, rax
0x180008690  jnz     short loc_18000869E
0x180008692  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180008699  test    rax, rax
0x18000869c  jz      short loc_1800086B1
0x18000869e  xor     r9d, r9d
0x1800086a1  xor     r8d, r8d
0x1800086a4  mov     edx, 0FEh
0x1800086a9  xor     ecx, ecx
0x1800086ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086b0  nop
0x1800086b1  mov     rcx, [rsp+0A8h+var_48]
0x1800086b6  xor     rcx, rsp; StackCookie
0x1800086b9  call    __security_check_cookie
0x1800086be  add     rsp, 78h
0x1800086c2  pop     r15
0x1800086c4  pop     r14
0x1800086c6  pop     rdi
0x1800086c7  pop     rsi
0x1800086c8  pop     rbp
0x1800086c9  pop     rbx
0x1800086ca  retn
```
