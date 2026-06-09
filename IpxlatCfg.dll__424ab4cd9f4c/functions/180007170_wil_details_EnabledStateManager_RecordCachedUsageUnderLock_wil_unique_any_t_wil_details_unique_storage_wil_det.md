# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x180007170`
- end: `0x180007327`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `439`
- prototype: `__int64 (__fastcall *__fastcall(__int64))(_QWORD, __int64, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180006cdc`
- `0x18000a4a0`
- `0x18000a500`

## callees

- `0x180001d40`
- `0x180007170`
- `0x180009924`
- `0x180019010`

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
0x180007170  push    rbx
0x180007172  push    rbp
0x180007173  push    rsi
0x180007174  push    rdi
0x180007175  push    r14
0x180007177  push    r15
0x180007179  sub     rsp, 78h
0x18000717d  mov     rax, cs:__security_cookie
0x180007184  xor     rax, rsp
0x180007187  mov     [rsp+0A8h+var_48], rax
0x18000718c  mov     rsi, rcx
0x18000718f  mov     rbx, [rcx+20h]
0x180007193  mov     rdi, [rcx+28h]
0x180007197  mov     rax, rdi
0x18000719a  sub     rax, rbx
0x18000719d  cmp     rax, 10h
0x1800071a1  jb      loc_18000730D
0x1800071a7  mov     ebp, 1
0x1800071ac  lea     r14d, [rbp+1]
0x1800071b0  mov     r15d, 1FFh
0x1800071b6  cmp     rbx, rdi
0x1800071b9  jz      loc_1800072DA
0x1800071bf  mov     r8, [rbx+8]
0x1800071c3  mov     r10d, [rbx]
0x1800071c6  prefetchw byte ptr [r8]
0x1800071ca  mov     eax, [r8]
0x1800071cd  mov     ecx, eax
0x1800071cf  and     ecx, 0FFC0401Eh
0x1800071d5  lock cmpxchg [r8], ecx
0x1800071da  jnz     short loc_1800071CD
0x1800071dc  mov     ecx, eax
0x1800071de  mov     r9d, eax
0x1800071e1  shr     r9d, 1
0x1800071e4  and     r9d, 0Fh
0x1800071e8  jz      short loc_180007207
0x1800071ea  prefetchw byte ptr [r8+4]
0x1800071ef  mov     eax, [r8+4]
0x1800071f3  mov     edx, eax
0x1800071f5  or      edx, r9d
0x1800071f8  lock cmpxchg [r8+4], edx
0x1800071fe  jnz     short loc_1800071F3
0x180007200  not     eax
0x180007202  and     eax, r9d
0x180007205  jmp     short loc_18000720A
0x180007207  mov     eax, r9d
0x18000720a  test    bpl, al
0x18000720d  jz      short loc_180007223
0x18000720f  mov     [rsp+0A8h+var_78], r10d
0x180007214  mov     [rsp+0A8h+var_74], 10002h
0x18000721c  lea     rdx, [rsp+0A8h+var_70]
0x180007221  jmp     short loc_180007228
0x180007223  lea     rdx, [rsp+0A8h+var_78]
0x180007228  test    r14b, al
0x18000722b  jz      short loc_18000723B
0x18000722d  mov     [rdx], r10d
0x180007230  mov     dword ptr [rdx+4], 10006h
0x180007237  add     rdx, 8
0x18000723b  test    al, 4
0x18000723d  jz      short loc_18000724D
0x18000723f  mov     [rdx], r10d
0x180007242  mov     dword ptr [rdx+4], 10003h
0x180007249  add     rdx, 8
0x18000724d  cmp     eax, 8
0x180007250  jb      short loc_180007260
0x180007252  mov     [rdx], r10d
0x180007255  mov     dword ptr [rdx+4], 10007h
0x18000725c  add     rdx, 8
0x180007260  mov     r8d, ecx
0x180007263  shr     r8d, 5
0x180007267  test    r15d, r8d
0x18000726a  jz      short loc_18000728C
0x18000726c  mov     [rdx], r10d
0x18000726f  mov     eax, ecx
0x180007271  shr     eax, 0Eh
0x180007274  and     ax, bp
0x180007277  shl     ax, 2
0x18000727b  mov     [rdx+4], ax
0x18000727f  and     r8w, r15w; unsigned __int64
0x180007283  mov     [rdx+6], r8w
0x180007288  add     rdx, 8
0x18000728c  mov     eax, ecx
0x18000728e  shr     eax, 0Fh
0x180007291  test    al, 7Fh
0x180007293  jz      short loc_1800072B5
0x180007295  mov     [rdx], r10d
0x180007298  shr     ecx, 16h
0x18000729b  and     cx, bp
0x18000729e  shl     cx, 2
0x1800072a2  add     cx, bp
0x1800072a5  mov     [rdx+4], cx
0x1800072a9  and     ax, 7Fh
0x1800072ad  mov     [rdx+6], ax
0x1800072b1  add     rdx, 8
0x1800072b5  lea     rax, [rsp+0A8h+var_78]
0x1800072ba  sub     rdx, rax
0x1800072bd  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x1800072c1  test    rdx, rdx
0x1800072c4  jle     short loc_1800072D1
0x1800072c6  lea     rcx, [rsp+0A8h+var_78]; this
0x1800072cb  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x1800072d0  nop
0x1800072d1  add     rbx, 10h
0x1800072d5  jmp     loc_1800071B6
0x1800072da  mov     rax, [rsi+20h]
0x1800072de  mov     [rsi+28h], rax
0x1800072e2  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x1800072e9  test    rax, rax
0x1800072ec  jnz     short loc_1800072FA
0x1800072ee  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x1800072f5  test    rax, rax
0x1800072f8  jz      short loc_18000730D
0x1800072fa  xor     r9d, r9d
0x1800072fd  xor     r8d, r8d
0x180007300  mov     edx, 0FEh
0x180007305  xor     ecx, ecx
0x180007307  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000730c  nop
0x18000730d  mov     rcx, [rsp+0A8h+var_48]
0x180007312  xor     rcx, rsp; StackCookie
0x180007315  call    __security_check_cookie
0x18000731a  add     rsp, 78h
0x18000731e  pop     r15
0x180007320  pop     r14
0x180007322  pop     rdi
0x180007323  pop     rsi
0x180007324  pop     rbp
0x180007325  pop     rbx
0x180007326  retn
```
