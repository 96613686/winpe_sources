# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x140010158`
- end: `0x14001030d`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `437`
- prototype: `__int64 (__fastcall *__fastcall(__int64))(_QWORD, __int64, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400056d0`
- `0x140005810`
- `0x14000fb7c`

## callees

- `0x140010158`
- `0x140011bd4`
- `0x1400134a0`
- `0x140014010`

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
0x140010158  push    rbx
0x14001015a  push    rbp
0x14001015b  push    rsi
0x14001015c  push    rdi
0x14001015d  push    r14
0x14001015f  push    r15
0x140010161  sub     rsp, 78h
0x140010165  mov     rax, cs:__security_cookie
0x14001016c  xor     rax, rsp
0x14001016f  mov     [rsp+0A8h+var_48], rax
0x140010174  mov     rdi, [rcx+28h]
0x140010178  mov     rsi, rcx
0x14001017b  mov     rbx, [rcx+20h]
0x14001017f  mov     rax, rdi
0x140010182  sub     rax, rbx
0x140010185  cmp     rax, 10h
0x140010189  jb      loc_1400102F3
0x14001018f  mov     ebp, 1
0x140010194  mov     r15d, 1FFh
0x14001019a  lea     r14d, [rbp+1]
0x14001019e  cmp     rbx, rdi
0x1400101a1  jz      loc_1400102C1
0x1400101a7  mov     r8, [rbx+8]
0x1400101ab  mov     r10d, [rbx]
0x1400101ae  prefetchw byte ptr [r8]
0x1400101b2  mov     eax, [r8]
0x1400101b5  mov     ecx, eax
0x1400101b7  and     ecx, 0FFC0401Eh
0x1400101bd  lock cmpxchg [r8], ecx
0x1400101c2  jnz     short loc_1400101B5
0x1400101c4  mov     r9d, eax
0x1400101c7  mov     ecx, eax
0x1400101c9  shr     r9d, 1
0x1400101cc  and     r9d, 0Fh
0x1400101d0  jz      short loc_1400101EF
0x1400101d2  prefetchw byte ptr [r8+4]
0x1400101d7  mov     eax, [r8+4]
0x1400101db  mov     edx, eax
0x1400101dd  or      edx, r9d
0x1400101e0  lock cmpxchg [r8+4], edx
0x1400101e6  jnz     short loc_1400101DB
0x1400101e8  not     eax
0x1400101ea  and     eax, r9d
0x1400101ed  jmp     short loc_1400101F2
0x1400101ef  mov     eax, r9d
0x1400101f2  test    bpl, al
0x1400101f5  jz      short loc_14001020B
0x1400101f7  mov     [rsp+0A8h+var_78], r10d
0x1400101fc  lea     rdx, [rsp+0A8h+var_70]
0x140010201  mov     [rsp+0A8h+var_74], 10002h
0x140010209  jmp     short loc_140010210
0x14001020b  lea     rdx, [rsp+0A8h+var_78]
0x140010210  test    r14b, al
0x140010213  jz      short loc_140010223
0x140010215  mov     [rdx], r10d
0x140010218  mov     dword ptr [rdx+4], 10006h
0x14001021f  add     rdx, 8
0x140010223  test    al, 4
0x140010225  jz      short loc_140010235
0x140010227  mov     [rdx], r10d
0x14001022a  mov     dword ptr [rdx+4], 10003h
0x140010231  add     rdx, 8
0x140010235  cmp     eax, 8
0x140010238  jb      short loc_140010248
0x14001023a  mov     [rdx], r10d
0x14001023d  mov     dword ptr [rdx+4], 10007h
0x140010244  add     rdx, 8
0x140010248  mov     r8d, ecx
0x14001024b  shr     r8d, 5
0x14001024f  test    r15d, r8d
0x140010252  jz      short loc_140010274
0x140010254  and     r8w, r15w; unsigned __int64
0x140010258  mov     [rdx], r10d
0x14001025b  mov     eax, ecx
0x14001025d  mov     [rdx+6], r8w
0x140010262  shr     eax, 0Eh
0x140010265  and     ax, bp
0x140010268  shl     ax, 2
0x14001026c  mov     [rdx+4], ax
0x140010270  add     rdx, 8
0x140010274  mov     eax, ecx
0x140010276  shr     eax, 0Fh
0x140010279  test    al, 7Fh
0x14001027b  jz      short loc_14001029D
0x14001027d  shr     ecx, 16h
0x140010280  and     ax, 7Fh
0x140010284  and     cx, bp
0x140010287  mov     [rdx], r10d
0x14001028a  shl     cx, 2
0x14001028e  add     cx, bp
0x140010291  mov     [rdx+6], ax
0x140010295  mov     [rdx+4], cx
0x140010299  add     rdx, 8
0x14001029d  lea     rax, [rsp+0A8h+var_78]
0x1400102a2  sub     rdx, rax
0x1400102a5  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x1400102a9  test    rdx, rdx
0x1400102ac  jle     short loc_1400102B8
0x1400102ae  lea     rcx, [rsp+0A8h+var_78]; this
0x1400102b3  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x1400102b8  add     rbx, 10h
0x1400102bc  jmp     loc_14001019E
0x1400102c1  mov     rax, [rsi+20h]
0x1400102c5  mov     [rsi+28h], rax
0x1400102c9  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x1400102d0  test    rax, rax
0x1400102d3  jnz     short loc_1400102E1
0x1400102d5  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x1400102dc  test    rax, rax
0x1400102df  jz      short loc_1400102F3
0x1400102e1  xor     r9d, r9d
0x1400102e4  xor     r8d, r8d
0x1400102e7  mov     edx, 0FEh
0x1400102ec  xor     ecx, ecx
0x1400102ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400102f3  mov     rcx, [rsp+0A8h+var_48]
0x1400102f8  xor     rcx, rsp; StackCookie
0x1400102fb  call    __security_check_cookie
0x140010300  add     rsp, 78h
0x140010304  pop     r15
0x140010306  pop     r14
0x140010308  pop     rdi
0x140010309  pop     rsi
0x14001030a  pop     rbp
0x14001030b  pop     rbx
0x14001030c  retn
```
