# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x14000c174`
- end: `0x14000c32b`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `439`
- prototype: `__int64 (__fastcall *__fastcall(__int64))(_QWORD, __int64, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000bd34`

## callees

- `0x14000c174`
- `0x14000e6c4`
- `0x140011e10`
- `0x140013010`

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
0x14000c174  push    rbx
0x14000c176  push    rbp
0x14000c177  push    rsi
0x14000c178  push    rdi
0x14000c179  push    r14
0x14000c17b  push    r15
0x14000c17d  sub     rsp, 78h
0x14000c181  mov     rax, cs:__security_cookie
0x14000c188  xor     rax, rsp
0x14000c18b  mov     [rsp+0A8h+var_48], rax
0x14000c190  mov     rsi, rcx
0x14000c193  mov     rbx, [rcx+20h]
0x14000c197  mov     rdi, [rcx+28h]
0x14000c19b  mov     rax, rdi
0x14000c19e  sub     rax, rbx
0x14000c1a1  cmp     rax, 10h
0x14000c1a5  jb      loc_14000C311
0x14000c1ab  mov     ebp, 1
0x14000c1b0  lea     r14d, [rbp+1]
0x14000c1b4  mov     r15d, 1FFh
0x14000c1ba  cmp     rbx, rdi
0x14000c1bd  jz      loc_14000C2DE
0x14000c1c3  mov     r8, [rbx+8]
0x14000c1c7  mov     r10d, [rbx]
0x14000c1ca  prefetchw byte ptr [r8]
0x14000c1ce  mov     eax, [r8]
0x14000c1d1  mov     ecx, eax
0x14000c1d3  and     ecx, 0FFC0401Eh
0x14000c1d9  lock cmpxchg [r8], ecx
0x14000c1de  jnz     short loc_14000C1D1
0x14000c1e0  mov     ecx, eax
0x14000c1e2  mov     r9d, eax
0x14000c1e5  shr     r9d, 1
0x14000c1e8  and     r9d, 0Fh
0x14000c1ec  jz      short loc_14000C20B
0x14000c1ee  prefetchw byte ptr [r8+4]
0x14000c1f3  mov     eax, [r8+4]
0x14000c1f7  mov     edx, eax
0x14000c1f9  or      edx, r9d
0x14000c1fc  lock cmpxchg [r8+4], edx
0x14000c202  jnz     short loc_14000C1F7
0x14000c204  not     eax
0x14000c206  and     eax, r9d
0x14000c209  jmp     short loc_14000C20E
0x14000c20b  mov     eax, r9d
0x14000c20e  test    bpl, al
0x14000c211  jz      short loc_14000C227
0x14000c213  mov     [rsp+0A8h+var_78], r10d
0x14000c218  mov     [rsp+0A8h+var_74], 10002h
0x14000c220  lea     rdx, [rsp+0A8h+var_70]
0x14000c225  jmp     short loc_14000C22C
0x14000c227  lea     rdx, [rsp+0A8h+var_78]
0x14000c22c  test    r14b, al
0x14000c22f  jz      short loc_14000C23F
0x14000c231  mov     [rdx], r10d
0x14000c234  mov     dword ptr [rdx+4], 10006h
0x14000c23b  add     rdx, 8
0x14000c23f  test    al, 4
0x14000c241  jz      short loc_14000C251
0x14000c243  mov     [rdx], r10d
0x14000c246  mov     dword ptr [rdx+4], 10003h
0x14000c24d  add     rdx, 8
0x14000c251  cmp     eax, 8
0x14000c254  jb      short loc_14000C264
0x14000c256  mov     [rdx], r10d
0x14000c259  mov     dword ptr [rdx+4], 10007h
0x14000c260  add     rdx, 8
0x14000c264  mov     r8d, ecx
0x14000c267  shr     r8d, 5
0x14000c26b  test    r15d, r8d
0x14000c26e  jz      short loc_14000C290
0x14000c270  mov     [rdx], r10d
0x14000c273  mov     eax, ecx
0x14000c275  shr     eax, 0Eh
0x14000c278  and     ax, bp
0x14000c27b  shl     ax, 2
0x14000c27f  mov     [rdx+4], ax
0x14000c283  and     r8w, r15w; unsigned __int64
0x14000c287  mov     [rdx+6], r8w
0x14000c28c  add     rdx, 8
0x14000c290  mov     eax, ecx
0x14000c292  shr     eax, 0Fh
0x14000c295  test    al, 7Fh
0x14000c297  jz      short loc_14000C2B9
0x14000c299  mov     [rdx], r10d
0x14000c29c  shr     ecx, 16h
0x14000c29f  and     cx, bp
0x14000c2a2  shl     cx, 2
0x14000c2a6  add     cx, bp
0x14000c2a9  mov     [rdx+4], cx
0x14000c2ad  and     ax, 7Fh
0x14000c2b1  mov     [rdx+6], ax
0x14000c2b5  add     rdx, 8
0x14000c2b9  lea     rax, [rsp+0A8h+var_78]
0x14000c2be  sub     rdx, rax
0x14000c2c1  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x14000c2c5  test    rdx, rdx
0x14000c2c8  jle     short loc_14000C2D5
0x14000c2ca  lea     rcx, [rsp+0A8h+var_78]; this
0x14000c2cf  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x14000c2d4  nop
0x14000c2d5  add     rbx, 10h
0x14000c2d9  jmp     loc_14000C1BA
0x14000c2de  mov     rax, [rsi+20h]
0x14000c2e2  mov     [rsi+28h], rax
0x14000c2e6  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x14000c2ed  test    rax, rax
0x14000c2f0  jnz     short loc_14000C2FE
0x14000c2f2  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x14000c2f9  test    rax, rax
0x14000c2fc  jz      short loc_14000C311
0x14000c2fe  xor     r9d, r9d
0x14000c301  xor     r8d, r8d
0x14000c304  mov     edx, 0FEh
0x14000c309  xor     ecx, ecx
0x14000c30b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c310  nop
0x14000c311  mov     rcx, [rsp+0A8h+var_48]
0x14000c316  xor     rcx, rsp; StackCookie
0x14000c319  call    __security_check_cookie
0x14000c31e  add     rsp, 78h
0x14000c322  pop     r15
0x14000c324  pop     r14
0x14000c326  pop     rdi
0x14000c327  pop     rsi
0x14000c328  pop     rbp
0x14000c329  pop     rbx
0x14000c32a  retn
```
