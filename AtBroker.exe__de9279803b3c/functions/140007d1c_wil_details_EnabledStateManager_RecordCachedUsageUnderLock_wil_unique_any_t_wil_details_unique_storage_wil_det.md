# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x140007d1c`
- end: `0x140007ed1`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `437`
- prototype: `__int64 (__fastcall *__fastcall(__int64))(_QWORD, __int64, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140002a70`
- `0x140002c10`
- `0x14000766c`

## callees

- `0x140007d1c`
- `0x14000a4c4`
- `0x140015b00`
- `0x140017010`

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
0x140007d1c  push    rbx
0x140007d1e  push    rbp
0x140007d1f  push    rsi
0x140007d20  push    rdi
0x140007d21  push    r14
0x140007d23  push    r15
0x140007d25  sub     rsp, 78h
0x140007d29  mov     rax, cs:__security_cookie
0x140007d30  xor     rax, rsp
0x140007d33  mov     [rsp+0A8h+var_48], rax
0x140007d38  mov     rdi, [rcx+28h]
0x140007d3c  mov     rsi, rcx
0x140007d3f  mov     rbx, [rcx+20h]
0x140007d43  mov     rax, rdi
0x140007d46  sub     rax, rbx
0x140007d49  cmp     rax, 10h
0x140007d4d  jb      loc_140007EB7
0x140007d53  mov     ebp, 1
0x140007d58  mov     r15d, 1FFh
0x140007d5e  lea     r14d, [rbp+1]
0x140007d62  cmp     rbx, rdi
0x140007d65  jz      loc_140007E85
0x140007d6b  mov     r8, [rbx+8]
0x140007d6f  mov     r10d, [rbx]
0x140007d72  prefetchw byte ptr [r8]
0x140007d76  mov     eax, [r8]
0x140007d79  mov     ecx, eax
0x140007d7b  and     ecx, 0FFC0401Eh
0x140007d81  lock cmpxchg [r8], ecx
0x140007d86  jnz     short loc_140007D79
0x140007d88  mov     r9d, eax
0x140007d8b  mov     ecx, eax
0x140007d8d  shr     r9d, 1
0x140007d90  and     r9d, 0Fh
0x140007d94  jz      short loc_140007DB3
0x140007d96  prefetchw byte ptr [r8+4]
0x140007d9b  mov     eax, [r8+4]
0x140007d9f  mov     edx, eax
0x140007da1  or      edx, r9d
0x140007da4  lock cmpxchg [r8+4], edx
0x140007daa  jnz     short loc_140007D9F
0x140007dac  not     eax
0x140007dae  and     eax, r9d
0x140007db1  jmp     short loc_140007DB6
0x140007db3  mov     eax, r9d
0x140007db6  test    bpl, al
0x140007db9  jz      short loc_140007DCF
0x140007dbb  mov     [rsp+0A8h+var_78], r10d
0x140007dc0  lea     rdx, [rsp+0A8h+var_70]
0x140007dc5  mov     [rsp+0A8h+var_74], 10002h
0x140007dcd  jmp     short loc_140007DD4
0x140007dcf  lea     rdx, [rsp+0A8h+var_78]
0x140007dd4  test    r14b, al
0x140007dd7  jz      short loc_140007DE7
0x140007dd9  mov     [rdx], r10d
0x140007ddc  mov     dword ptr [rdx+4], 10006h
0x140007de3  add     rdx, 8
0x140007de7  test    al, 4
0x140007de9  jz      short loc_140007DF9
0x140007deb  mov     [rdx], r10d
0x140007dee  mov     dword ptr [rdx+4], 10003h
0x140007df5  add     rdx, 8
0x140007df9  cmp     eax, 8
0x140007dfc  jb      short loc_140007E0C
0x140007dfe  mov     [rdx], r10d
0x140007e01  mov     dword ptr [rdx+4], 10007h
0x140007e08  add     rdx, 8
0x140007e0c  mov     r8d, ecx
0x140007e0f  shr     r8d, 5
0x140007e13  test    r15d, r8d
0x140007e16  jz      short loc_140007E38
0x140007e18  and     r8w, r15w; unsigned __int64
0x140007e1c  mov     [rdx], r10d
0x140007e1f  mov     eax, ecx
0x140007e21  mov     [rdx+6], r8w
0x140007e26  shr     eax, 0Eh
0x140007e29  and     ax, bp
0x140007e2c  shl     ax, 2
0x140007e30  mov     [rdx+4], ax
0x140007e34  add     rdx, 8
0x140007e38  mov     eax, ecx
0x140007e3a  shr     eax, 0Fh
0x140007e3d  test    al, 7Fh
0x140007e3f  jz      short loc_140007E61
0x140007e41  shr     ecx, 16h
0x140007e44  and     ax, 7Fh
0x140007e48  and     cx, bp
0x140007e4b  mov     [rdx], r10d
0x140007e4e  shl     cx, 2
0x140007e52  add     cx, bp
0x140007e55  mov     [rdx+6], ax
0x140007e59  mov     [rdx+4], cx
0x140007e5d  add     rdx, 8
0x140007e61  lea     rax, [rsp+0A8h+var_78]
0x140007e66  sub     rdx, rax
0x140007e69  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x140007e6d  test    rdx, rdx
0x140007e70  jle     short loc_140007E7C
0x140007e72  lea     rcx, [rsp+0A8h+var_78]; this
0x140007e77  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x140007e7c  add     rbx, 10h
0x140007e80  jmp     loc_140007D62
0x140007e85  mov     rax, [rsi+20h]
0x140007e89  mov     [rsi+28h], rax
0x140007e8d  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x140007e94  test    rax, rax
0x140007e97  jnz     short loc_140007EA5
0x140007e99  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x140007ea0  test    rax, rax
0x140007ea3  jz      short loc_140007EB7
0x140007ea5  xor     r9d, r9d
0x140007ea8  xor     r8d, r8d
0x140007eab  mov     edx, 0FEh
0x140007eb0  xor     ecx, ecx
0x140007eb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007eb7  mov     rcx, [rsp+0A8h+var_48]
0x140007ebc  xor     rcx, rsp; StackCookie
0x140007ebf  call    __security_check_cookie
0x140007ec4  add     rsp, 78h
0x140007ec8  pop     r15
0x140007eca  pop     r14
0x140007ecc  pop     rdi
0x140007ecd  pop     rsi
0x140007ece  pop     rbp
0x140007ecf  pop     rbx
0x140007ed0  retn
```
