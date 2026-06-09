# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x180019ba8`
- end: `0x180019d5f`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `439`
- prototype: `__int64 (__fastcall *__fastcall(__int64))(_QWORD, __int64, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000ac00`
- `0x18000ae40`
- `0x18001947c`

## callees

- `0x180003520`
- `0x180019ba8`
- `0x18001d080`
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
0x180019ba8  push    rbx
0x180019baa  push    rbp
0x180019bab  push    rsi
0x180019bac  push    rdi
0x180019bad  push    r14
0x180019baf  push    r15
0x180019bb1  sub     rsp, 78h
0x180019bb5  mov     rax, cs:__security_cookie
0x180019bbc  xor     rax, rsp
0x180019bbf  mov     [rsp+0A8h+var_48], rax
0x180019bc4  mov     rsi, rcx
0x180019bc7  mov     rbx, [rcx+20h]
0x180019bcb  mov     rdi, [rcx+28h]
0x180019bcf  mov     rax, rdi
0x180019bd2  sub     rax, rbx
0x180019bd5  cmp     rax, 10h
0x180019bd9  jb      loc_180019D45
0x180019bdf  mov     ebp, 1
0x180019be4  lea     r14d, [rbp+1]
0x180019be8  mov     r15d, 1FFh
0x180019bee  cmp     rbx, rdi
0x180019bf1  jz      loc_180019D12
0x180019bf7  mov     r8, [rbx+8]
0x180019bfb  mov     r10d, [rbx]
0x180019bfe  prefetchw byte ptr [r8]
0x180019c02  mov     eax, [r8]
0x180019c05  mov     ecx, eax
0x180019c07  and     ecx, 0FFC0401Eh
0x180019c0d  lock cmpxchg [r8], ecx
0x180019c12  jnz     short loc_180019C05
0x180019c14  mov     ecx, eax
0x180019c16  mov     r9d, eax
0x180019c19  shr     r9d, 1
0x180019c1c  and     r9d, 0Fh
0x180019c20  jz      short loc_180019C3F
0x180019c22  prefetchw byte ptr [r8+4]
0x180019c27  mov     eax, [r8+4]
0x180019c2b  mov     edx, eax
0x180019c2d  or      edx, r9d
0x180019c30  lock cmpxchg [r8+4], edx
0x180019c36  jnz     short loc_180019C2B
0x180019c38  not     eax
0x180019c3a  and     eax, r9d
0x180019c3d  jmp     short loc_180019C42
0x180019c3f  mov     eax, r9d
0x180019c42  test    bpl, al
0x180019c45  jz      short loc_180019C5B
0x180019c47  mov     [rsp+0A8h+var_78], r10d
0x180019c4c  mov     [rsp+0A8h+var_74], 10002h
0x180019c54  lea     rdx, [rsp+0A8h+var_70]
0x180019c59  jmp     short loc_180019C60
0x180019c5b  lea     rdx, [rsp+0A8h+var_78]
0x180019c60  test    r14b, al
0x180019c63  jz      short loc_180019C73
0x180019c65  mov     [rdx], r10d
0x180019c68  mov     dword ptr [rdx+4], 10006h
0x180019c6f  add     rdx, 8
0x180019c73  test    al, 4
0x180019c75  jz      short loc_180019C85
0x180019c77  mov     [rdx], r10d
0x180019c7a  mov     dword ptr [rdx+4], 10003h
0x180019c81  add     rdx, 8
0x180019c85  cmp     eax, 8
0x180019c88  jb      short loc_180019C98
0x180019c8a  mov     [rdx], r10d
0x180019c8d  mov     dword ptr [rdx+4], 10007h
0x180019c94  add     rdx, 8
0x180019c98  mov     r8d, ecx
0x180019c9b  shr     r8d, 5
0x180019c9f  test    r15d, r8d
0x180019ca2  jz      short loc_180019CC4
0x180019ca4  mov     [rdx], r10d
0x180019ca7  mov     eax, ecx
0x180019ca9  shr     eax, 0Eh
0x180019cac  and     ax, bp
0x180019caf  shl     ax, 2
0x180019cb3  mov     [rdx+4], ax
0x180019cb7  and     r8w, r15w; unsigned __int64
0x180019cbb  mov     [rdx+6], r8w
0x180019cc0  add     rdx, 8
0x180019cc4  mov     eax, ecx
0x180019cc6  shr     eax, 0Fh
0x180019cc9  test    al, 7Fh
0x180019ccb  jz      short loc_180019CED
0x180019ccd  mov     [rdx], r10d
0x180019cd0  shr     ecx, 16h
0x180019cd3  and     cx, bp
0x180019cd6  shl     cx, 2
0x180019cda  add     cx, bp
0x180019cdd  mov     [rdx+4], cx
0x180019ce1  and     ax, 7Fh
0x180019ce5  mov     [rdx+6], ax
0x180019ce9  add     rdx, 8
0x180019ced  lea     rax, [rsp+0A8h+var_78]
0x180019cf2  sub     rdx, rax
0x180019cf5  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x180019cf9  test    rdx, rdx
0x180019cfc  jle     short loc_180019D09
0x180019cfe  lea     rcx, [rsp+0A8h+var_78]; this
0x180019d03  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x180019d08  nop
0x180019d09  add     rbx, 10h
0x180019d0d  jmp     loc_180019BEE
0x180019d12  mov     rax, [rsi+20h]
0x180019d16  mov     [rsi+28h], rax
0x180019d1a  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180019d21  test    rax, rax
0x180019d24  jnz     short loc_180019D32
0x180019d26  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180019d2d  test    rax, rax
0x180019d30  jz      short loc_180019D45
0x180019d32  xor     r9d, r9d
0x180019d35  xor     r8d, r8d
0x180019d38  mov     edx, 0FEh
0x180019d3d  xor     ecx, ecx
0x180019d3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d44  nop
0x180019d45  mov     rcx, [rsp+0A8h+var_48]
0x180019d4a  xor     rcx, rsp; StackCookie
0x180019d4d  call    __security_check_cookie
0x180019d52  add     rsp, 78h
0x180019d56  pop     r15
0x180019d58  pop     r14
0x180019d5a  pop     rdi
0x180019d5b  pop     rsi
0x180019d5c  pop     rbp
0x180019d5d  pop     rbx
0x180019d5e  retn
```
