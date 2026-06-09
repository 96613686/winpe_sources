# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x180005984`
- end: `0x180005b39`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `437`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000555c`

## callees

- `0x180005984`
- `0x1800079c4`
- `0x18000c560`
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
0x180005984  push    rbx
0x180005986  push    rbp
0x180005987  push    rsi
0x180005988  push    rdi
0x180005989  push    r14
0x18000598b  push    r15
0x18000598d  sub     rsp, 78h
0x180005991  mov     rax, cs:__security_cookie
0x180005998  xor     rax, rsp
0x18000599b  mov     [rsp+0A8h+var_48], rax
0x1800059a0  mov     rdi, [rcx+28h]
0x1800059a4  mov     rsi, rcx
0x1800059a7  mov     rbx, [rcx+20h]
0x1800059ab  mov     rax, rdi
0x1800059ae  sub     rax, rbx
0x1800059b1  cmp     rax, 10h
0x1800059b5  jb      loc_180005B1F
0x1800059bb  mov     ebp, 1
0x1800059c0  mov     r15d, 1FFh
0x1800059c6  lea     r14d, [rbp+1]
0x1800059ca  cmp     rbx, rdi
0x1800059cd  jz      loc_180005AED
0x1800059d3  mov     r8, [rbx+8]
0x1800059d7  mov     r10d, [rbx]
0x1800059da  prefetchw byte ptr [r8]
0x1800059de  mov     eax, [r8]
0x1800059e1  mov     ecx, eax
0x1800059e3  and     ecx, 0FFC0401Eh
0x1800059e9  lock cmpxchg [r8], ecx
0x1800059ee  jnz     short loc_1800059E1
0x1800059f0  mov     r9d, eax
0x1800059f3  mov     ecx, eax
0x1800059f5  shr     r9d, 1
0x1800059f8  and     r9d, 0Fh
0x1800059fc  jz      short loc_180005A1B
0x1800059fe  prefetchw byte ptr [r8+4]
0x180005a03  mov     eax, [r8+4]
0x180005a07  mov     edx, eax
0x180005a09  or      edx, r9d
0x180005a0c  lock cmpxchg [r8+4], edx
0x180005a12  jnz     short loc_180005A07
0x180005a14  not     eax
0x180005a16  and     eax, r9d
0x180005a19  jmp     short loc_180005A1E
0x180005a1b  mov     eax, r9d
0x180005a1e  test    bpl, al
0x180005a21  jz      short loc_180005A37
0x180005a23  mov     [rsp+0A8h+var_78], r10d
0x180005a28  lea     rdx, [rsp+0A8h+var_70]
0x180005a2d  mov     [rsp+0A8h+var_74], 10002h
0x180005a35  jmp     short loc_180005A3C
0x180005a37  lea     rdx, [rsp+0A8h+var_78]
0x180005a3c  test    r14b, al
0x180005a3f  jz      short loc_180005A4F
0x180005a41  mov     [rdx], r10d
0x180005a44  mov     dword ptr [rdx+4], 10006h
0x180005a4b  add     rdx, 8
0x180005a4f  test    al, 4
0x180005a51  jz      short loc_180005A61
0x180005a53  mov     [rdx], r10d
0x180005a56  mov     dword ptr [rdx+4], 10003h
0x180005a5d  add     rdx, 8
0x180005a61  cmp     eax, 8
0x180005a64  jb      short loc_180005A74
0x180005a66  mov     [rdx], r10d
0x180005a69  mov     dword ptr [rdx+4], 10007h
0x180005a70  add     rdx, 8
0x180005a74  mov     r8d, ecx
0x180005a77  shr     r8d, 5
0x180005a7b  test    r15d, r8d
0x180005a7e  jz      short loc_180005AA0
0x180005a80  and     r8w, r15w; unsigned __int64
0x180005a84  mov     [rdx], r10d
0x180005a87  mov     eax, ecx
0x180005a89  mov     [rdx+6], r8w
0x180005a8e  shr     eax, 0Eh
0x180005a91  and     ax, bp
0x180005a94  shl     ax, 2
0x180005a98  mov     [rdx+4], ax
0x180005a9c  add     rdx, 8
0x180005aa0  mov     eax, ecx
0x180005aa2  shr     eax, 0Fh
0x180005aa5  test    al, 7Fh
0x180005aa7  jz      short loc_180005AC9
0x180005aa9  shr     ecx, 16h
0x180005aac  and     ax, 7Fh
0x180005ab0  and     cx, bp
0x180005ab3  mov     [rdx], r10d
0x180005ab6  shl     cx, 2
0x180005aba  add     cx, bp
0x180005abd  mov     [rdx+6], ax
0x180005ac1  mov     [rdx+4], cx
0x180005ac5  add     rdx, 8
0x180005ac9  lea     rax, [rsp+0A8h+var_78]
0x180005ace  sub     rdx, rax
0x180005ad1  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x180005ad5  test    rdx, rdx
0x180005ad8  jle     short loc_180005AE4
0x180005ada  lea     rcx, [rsp+0A8h+var_78]; this
0x180005adf  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x180005ae4  add     rbx, 10h
0x180005ae8  jmp     loc_1800059CA
0x180005aed  mov     rax, [rsi+20h]
0x180005af1  mov     [rsi+28h], rax
0x180005af5  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180005afc  test    rax, rax
0x180005aff  jnz     short loc_180005B0D
0x180005b01  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180005b08  test    rax, rax
0x180005b0b  jz      short loc_180005B1F
0x180005b0d  xor     r9d, r9d
0x180005b10  xor     r8d, r8d
0x180005b13  mov     edx, 0FEh
0x180005b18  xor     ecx, ecx
0x180005b1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b1f  mov     rcx, [rsp+0A8h+var_48]
0x180005b24  xor     rcx, rsp; StackCookie
0x180005b27  call    __security_check_cookie
0x180005b2c  add     rsp, 78h
0x180005b30  pop     r15
0x180005b32  pop     r14
0x180005b34  pop     rdi
0x180005b35  pop     rsi
0x180005b36  pop     rbp
0x180005b37  pop     rbx
0x180005b38  retn
```
