# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x14000b0c8`
- end: `0x14000b27f`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `439`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400069e0`
- `0x140006c20`
- `0x14000a930`

## callees

- `0x14000b0c8`
- `0x14000d324`
- `0x14000e1c0`
- `0x14000f010`

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
0x14000b0c8  push    rbx
0x14000b0ca  push    rbp
0x14000b0cb  push    rsi
0x14000b0cc  push    rdi
0x14000b0cd  push    r14
0x14000b0cf  push    r15
0x14000b0d1  sub     rsp, 78h
0x14000b0d5  mov     rax, cs:__security_cookie
0x14000b0dc  xor     rax, rsp
0x14000b0df  mov     [rsp+0A8h+var_48], rax
0x14000b0e4  mov     rsi, rcx
0x14000b0e7  mov     rbx, [rcx+20h]
0x14000b0eb  mov     rdi, [rcx+28h]
0x14000b0ef  mov     rax, rdi
0x14000b0f2  sub     rax, rbx
0x14000b0f5  cmp     rax, 10h
0x14000b0f9  jb      loc_14000B265
0x14000b0ff  mov     ebp, 1
0x14000b104  lea     r14d, [rbp+1]
0x14000b108  mov     r15d, 1FFh
0x14000b10e  cmp     rbx, rdi
0x14000b111  jz      loc_14000B232
0x14000b117  mov     r8, [rbx+8]
0x14000b11b  mov     r10d, [rbx]
0x14000b11e  prefetchw byte ptr [r8]
0x14000b122  mov     eax, [r8]
0x14000b125  mov     ecx, eax
0x14000b127  and     ecx, 0FFC0401Eh
0x14000b12d  lock cmpxchg [r8], ecx
0x14000b132  jnz     short loc_14000B125
0x14000b134  mov     ecx, eax
0x14000b136  mov     r9d, eax
0x14000b139  shr     r9d, 1
0x14000b13c  and     r9d, 0Fh
0x14000b140  jz      short loc_14000B15F
0x14000b142  prefetchw byte ptr [r8+4]
0x14000b147  mov     eax, [r8+4]
0x14000b14b  mov     edx, eax
0x14000b14d  or      edx, r9d
0x14000b150  lock cmpxchg [r8+4], edx
0x14000b156  jnz     short loc_14000B14B
0x14000b158  not     eax
0x14000b15a  and     eax, r9d
0x14000b15d  jmp     short loc_14000B162
0x14000b15f  mov     eax, r9d
0x14000b162  test    bpl, al
0x14000b165  jz      short loc_14000B17B
0x14000b167  mov     [rsp+0A8h+var_78], r10d
0x14000b16c  mov     [rsp+0A8h+var_74], 10002h
0x14000b174  lea     rdx, [rsp+0A8h+var_70]
0x14000b179  jmp     short loc_14000B180
0x14000b17b  lea     rdx, [rsp+0A8h+var_78]
0x14000b180  test    r14b, al
0x14000b183  jz      short loc_14000B193
0x14000b185  mov     [rdx], r10d
0x14000b188  mov     dword ptr [rdx+4], 10006h
0x14000b18f  add     rdx, 8
0x14000b193  test    al, 4
0x14000b195  jz      short loc_14000B1A5
0x14000b197  mov     [rdx], r10d
0x14000b19a  mov     dword ptr [rdx+4], 10003h
0x14000b1a1  add     rdx, 8
0x14000b1a5  cmp     eax, 8
0x14000b1a8  jb      short loc_14000B1B8
0x14000b1aa  mov     [rdx], r10d
0x14000b1ad  mov     dword ptr [rdx+4], 10007h
0x14000b1b4  add     rdx, 8
0x14000b1b8  mov     r8d, ecx
0x14000b1bb  shr     r8d, 5
0x14000b1bf  test    r15d, r8d
0x14000b1c2  jz      short loc_14000B1E4
0x14000b1c4  mov     [rdx], r10d
0x14000b1c7  mov     eax, ecx
0x14000b1c9  shr     eax, 0Eh
0x14000b1cc  and     ax, bp
0x14000b1cf  shl     ax, 2
0x14000b1d3  mov     [rdx+4], ax
0x14000b1d7  and     r8w, r15w; unsigned __int64
0x14000b1db  mov     [rdx+6], r8w
0x14000b1e0  add     rdx, 8
0x14000b1e4  mov     eax, ecx
0x14000b1e6  shr     eax, 0Fh
0x14000b1e9  test    al, 7Fh
0x14000b1eb  jz      short loc_14000B20D
0x14000b1ed  mov     [rdx], r10d
0x14000b1f0  shr     ecx, 16h
0x14000b1f3  and     cx, bp
0x14000b1f6  shl     cx, 2
0x14000b1fa  add     cx, bp
0x14000b1fd  mov     [rdx+4], cx
0x14000b201  and     ax, 7Fh
0x14000b205  mov     [rdx+6], ax
0x14000b209  add     rdx, 8
0x14000b20d  lea     rax, [rsp+0A8h+var_78]
0x14000b212  sub     rdx, rax
0x14000b215  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x14000b219  test    rdx, rdx
0x14000b21c  jle     short loc_14000B229
0x14000b21e  lea     rcx, [rsp+0A8h+var_78]; this
0x14000b223  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x14000b228  nop
0x14000b229  add     rbx, 10h
0x14000b22d  jmp     loc_14000B10E
0x14000b232  mov     rax, [rsi+20h]
0x14000b236  mov     [rsi+28h], rax
0x14000b23a  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x14000b241  test    rax, rax
0x14000b244  jnz     short loc_14000B252
0x14000b246  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x14000b24d  test    rax, rax
0x14000b250  jz      short loc_14000B265
0x14000b252  xor     r9d, r9d
0x14000b255  xor     r8d, r8d
0x14000b258  mov     edx, 0FEh
0x14000b25d  xor     ecx, ecx
0x14000b25f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b264  nop
0x14000b265  mov     rcx, [rsp+0A8h+var_48]
0x14000b26a  xor     rcx, rsp; StackCookie
0x14000b26d  call    __security_check_cookie
0x14000b272  add     rsp, 78h
0x14000b276  pop     r15
0x14000b278  pop     r14
0x14000b27a  pop     rdi
0x14000b27b  pop     rsi
0x14000b27c  pop     rbp
0x14000b27d  pop     rbx
0x14000b27e  retn
```
