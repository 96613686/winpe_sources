# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x18005bde0`
- end: `0x18005bfaf`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `463`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004abb0`
- `0x18005bc34`

## callees

- `0x18004d320`
- `0x18005bde0`
- `0x18005c990`
- `0x1800960c0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 (__fastcall *__fastcall wil::details::EnabledStateManager::RecordCachedUsageUnderLock(
        __int64 a1))(_QWORD, __int64, _QWORD, _QWORD)
{
  int *v2; // rbx
  int *v3; // rdi
  __int64 (__fastcall *result)(_QWORD, __int64, _QWORD, _QWORD); // rax
  unsigned __int32 *v5; // r8
  int v6; // r10d
  unsigned __int32 v7; // eax
  unsigned __int32 v8; // ett
  unsigned __int32 v9; // ecx
  unsigned __int32 v10; // eax
  char *v11; // rdx
  unsigned __int64 v12; // r8
  __int64 v13; // rdx
  _DWORD v14[2]; // [rsp+30h] [rbp-88h] BYREF
  char v15; // [rsp+38h] [rbp-80h] BYREF

  v2 = *(int **)(a1 + 32);
  v3 = *(int **)(a1 + 40);
  result = (__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))((char *)v3 - (char *)v2);
  if ( (unsigned __int64)((char *)v3 - (char *)v2) >= 0x10 )
  {
    while ( v2 != v3 )
    {
      v5 = (unsigned __int32 *)*((_QWORD *)v2 + 1);
      v6 = *v2;
      _m_prefetchw(v5);
      v7 = *v5;
      do
      {
        v8 = v7;
        v7 = _InterlockedCompareExchange((volatile signed __int32 *)v5, v7 & 0xFFC0401E, v7);
      }
      while ( v8 != v7 );
      v9 = v7;
      if ( ((v7 >> 1) & 0xF) != 0 )
      {
        _m_prefetchw(v5 + 1);
        v10 = (v7 >> 1) & 0xF & ~_InterlockedOr((volatile signed __int32 *)v5 + 1, (v7 >> 1) & 0xF);
      }
      else
      {
        v10 = 0;
      }
      if ( (v10 & 1) != 0 )
      {
        v14[0] = v6;
        v14[1] = 65538;
        v11 = &v15;
      }
      else
      {
        v11 = (char *)v14;
      }
      if ( (v10 & 2) != 0 )
      {
        *(_DWORD *)v11 = v6;
        *((_DWORD *)v11 + 1) = 65542;
        v11 += 8;
      }
      if ( (v10 & 4) != 0 )
      {
        *(_DWORD *)v11 = v6;
        *((_DWORD *)v11 + 1) = 65539;
        v11 += 8;
      }
      if ( v10 >= 8 )
      {
        *(_DWORD *)v11 = v6;
        *((_DWORD *)v11 + 1) = 65543;
        v11 += 8;
      }
      v12 = v9 >> 5;
      if ( (v12 & 0x1FF) != 0 )
      {
        *(_DWORD *)v11 = v6;
        *((_WORD *)v11 + 2) = 4 * ((v9 >> 14) & 1);
        LOWORD(v12) = v12 & 0x1FF;
        *((_WORD *)v11 + 3) = v12;
        v11 += 8;
      }
      if ( ((v9 >> 15) & 0x7F) != 0 )
      {
        *(_DWORD *)v11 = v6;
        *((_WORD *)v11 + 2) = 4 * ((v9 >> 22) & 1) + 1;
        *((_WORD *)v11 + 3) = (v9 >> 15) & 0x7F;
        v11 += 8;
      }
      v13 = (v11 - (char *)v14) >> 3;
      if ( v13 > 0 )
        wil::details::WilApi_RecordFeatureUsageReports(
          (wil::details *)v14,
          (struct __WIL_RTL_FEATURE_USAGE_DATA *)v13,
          v12);
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
0x18005bde0  push    rbx
0x18005bde2  push    rbp
0x18005bde3  push    rsi
0x18005bde4  push    rdi
0x18005bde5  push    r12
0x18005bde7  push    r13
0x18005bde9  push    r14
0x18005bdeb  push    r15
0x18005bded  sub     rsp, 78h
0x18005bdf1  mov     rax, cs:__security_cookie
0x18005bdf8  xor     rax, rsp
0x18005bdfb  mov     [rsp+0B8h+var_58], rax
0x18005be00  mov     rsi, rcx
0x18005be03  mov     rbx, [rcx+20h]
0x18005be07  mov     rdi, [rcx+28h]
0x18005be0b  mov     rax, rdi
0x18005be0e  sub     rax, rbx
0x18005be11  cmp     rax, 10h
0x18005be15  jb      loc_18005BF90
0x18005be1b  mov     r11d, 3
0x18005be21  mov     r14d, 1FFh
0x18005be27  cmp     rbx, rdi
0x18005be2a  jz      loc_18005BF5C
0x18005be30  mov     r8, [rbx+8]
0x18005be34  mov     r10d, [rbx]
0x18005be37  prefetchw byte ptr [r8]
0x18005be3b  mov     eax, [r8]
0x18005be3e  xchg    ax, ax
0x18005be40  mov     ecx, eax
0x18005be42  and     ecx, 0FFC0401Eh
0x18005be48  lock cmpxchg [r8], ecx
0x18005be4d  jnz     short loc_18005BE40
0x18005be4f  mov     ecx, eax
0x18005be51  mov     r9d, eax
0x18005be54  shr     r9d, 1
0x18005be57  and     r9d, 0Fh
0x18005be5b  jz      short loc_18005BE84
0x18005be5d  prefetchw byte ptr [r8+4]
0x18005be62  mov     eax, [r8+4]
0x18005be66  nop     word ptr [rax+rax+00000000h]
0x18005be70  mov     edx, eax
0x18005be72  or      edx, r9d
0x18005be75  lock cmpxchg [r8+4], edx
0x18005be7b  jnz     short loc_18005BE70
0x18005be7d  not     eax
0x18005be7f  and     eax, r9d
0x18005be82  jmp     short loc_18005BE87
0x18005be84  mov     eax, r9d
0x18005be87  test    al, 1
0x18005be89  jz      short loc_18005BE9F
0x18005be8b  mov     [rsp+0B8h+var_88], r10d
0x18005be90  mov     [rsp+0B8h+var_84], 10002h
0x18005be98  lea     rdx, [rsp+0B8h+var_80]
0x18005be9d  jmp     short loc_18005BEA4
0x18005be9f  lea     rdx, [rsp+0B8h+var_88]
0x18005bea4  test    al, 2
0x18005bea6  jz      short loc_18005BEB6
0x18005bea8  mov     [rdx], r10d
0x18005beab  mov     dword ptr [rdx+4], 10006h
0x18005beb2  add     rdx, 8
0x18005beb6  test    al, 4
0x18005beb8  jz      short loc_18005BEC8
0x18005beba  mov     [rdx], r10d
0x18005bebd  mov     dword ptr [rdx+4], 10003h
0x18005bec4  add     rdx, 8
0x18005bec8  cmp     eax, 8
0x18005becb  jb      short loc_18005BEDB
0x18005becd  mov     [rdx], r10d
0x18005bed0  mov     dword ptr [rdx+4], 10007h
0x18005bed7  add     rdx, 8
0x18005bedb  mov     r8d, ecx
0x18005bede  shr     r8d, 5
0x18005bee2  test    r14d, r8d
0x18005bee5  jz      short loc_18005BF08
0x18005bee7  mov     [rdx], r10d
0x18005beea  mov     eax, ecx
0x18005beec  shr     eax, 0Eh
0x18005beef  and     ax, 1
0x18005bef3  shl     ax, 2
0x18005bef7  mov     [rdx+4], ax
0x18005befb  and     r8w, r14w; unsigned __int64
0x18005beff  mov     [rdx+6], r8w
0x18005bf04  add     rdx, 8
0x18005bf08  mov     eax, ecx
0x18005bf0a  shr     eax, 0Fh
0x18005bf0d  test    al, 7Fh
0x18005bf0f  jz      short loc_18005BF32
0x18005bf11  mov     [rdx], r10d
0x18005bf14  shr     ecx, 16h
0x18005bf17  and     cx, 1
0x18005bf1b  shl     cx, 2
0x18005bf1f  inc     cx
0x18005bf22  mov     [rdx+4], cx
0x18005bf26  and     ax, 7Fh
0x18005bf2a  mov     [rdx+6], ax
0x18005bf2e  add     rdx, 8
0x18005bf32  lea     rax, [rsp+0B8h+var_88]
0x18005bf37  sub     rdx, rax
0x18005bf3a  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x18005bf3e  test    rdx, rdx
0x18005bf41  jle     short loc_18005BF53
0x18005bf43  lea     rcx, [rsp+0B8h+var_88]; this
0x18005bf48  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x18005bf4d  mov     r11d, 3
0x18005bf53  add     rbx, 10h
0x18005bf57  jmp     loc_18005BE27
0x18005bf5c  mov     rax, [rsi+20h]
0x18005bf60  mov     [rsi+28h], rax
0x18005bf64  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18005bf6b  test    rax, rax
0x18005bf6e  jnz     short loc_18005BF7C
0x18005bf70  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18005bf77  test    rax, rax
0x18005bf7a  jz      short loc_18005BF90
0x18005bf7c  xor     r9d, r9d
0x18005bf7f  xor     r8d, r8d
0x18005bf82  mov     edx, 0FEh
0x18005bf87  xor     ecx, ecx
0x18005bf89  call    cs:__guard_dispatch_icall_fptr
0x18005bf8f  nop
0x18005bf90  mov     rcx, [rsp+0B8h+var_58]
0x18005bf95  xor     rcx, rsp; StackCookie
0x18005bf98  call    __security_check_cookie
0x18005bf9d  add     rsp, 78h
0x18005bfa1  pop     r15
0x18005bfa3  pop     r14
0x18005bfa5  pop     r13
0x18005bfa7  pop     r12
0x18005bfa9  pop     rdi
0x18005bfaa  pop     rsi
0x18005bfab  pop     rbp
0x18005bfac  pop     rbx
0x18005bfad  retn
```
