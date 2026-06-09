# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(void)

- ea: `0x140003e98`
- end: `0x140004069`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXXZ`
- size: `465`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x140003ca4`
- `0x1400042d0`
- `0x140004b10`
- `0x1400102c0`

## callees

- `0x140003c48`
- `0x140003e98`
- `0x14000a390`
- `0x14000f4d0`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::details::EnabledStateManager *this)
{
  int *v2; // rbx
  int *v3; // rsi
  __int64 v4; // r9
  int v5; // r10d
  unsigned __int32 v6; // edx
  unsigned int v7; // ecx
  char *v8; // r8
  signed __int64 v9; // r8
  void (__fastcall *v10)(_QWORD, __int64, _QWORD, _QWORD); // rax
  _DWORD v11[2]; // [rsp+30h] [rbp-58h] BYREF
  char v12; // [rsp+38h] [rbp-50h] BYREF

  v2 = (int *)*((_QWORD *)this + 6);
  v3 = (int *)*((_QWORD *)this + 7);
  if ( (unsigned __int64)((char *)v3 - (char *)v2) >= 0x10 )
  {
    for ( ; v2 != v3; v2 += 4 )
    {
      v4 = *((_QWORD *)v2 + 1);
      v5 = *v2;
      _m_prefetchw((const void *)v4);
      v6 = _InterlockedAnd((volatile signed __int32 *)v4, 0xFFC0401E);
      v7 = (v6 >> 1) & 0xF;
      if ( v7 )
      {
        _m_prefetchw((const void *)(v4 + 4));
        v7 &= ~_InterlockedOr((volatile signed __int32 *)(v4 + 4), v7);
      }
      v8 = (char *)v11;
      if ( (v7 & 1) != 0 )
      {
        v11[0] = v5;
        v11[1] = 65538;
        v8 = &v12;
      }
      if ( (v7 & 2) != 0 )
      {
        *(_DWORD *)v8 = v5;
        *((_DWORD *)v8 + 1) = 65542;
        v8 += 8;
      }
      if ( (v7 & 4) != 0 )
      {
        *(_DWORD *)v8 = v5;
        *((_DWORD *)v8 + 1) = 65539;
        v8 += 8;
      }
      if ( v7 >= 8 )
      {
        *(_DWORD *)v8 = v5;
        *((_DWORD *)v8 + 1) = 65543;
        v8 += 8;
      }
      if ( ((v6 >> 5) & 0x1FF) != 0 )
      {
        *(_DWORD *)v8 = v5;
        *((_WORD *)v8 + 2) = 4 * ((v6 >> 14) & 1);
        *((_WORD *)v8 + 3) = (v6 >> 5) & 0x1FF;
        v8 += 8;
      }
      if ( ((v6 >> 15) & 0x7F) != 0 )
      {
        *(_DWORD *)v8 = v5;
        *((_WORD *)v8 + 2) = (4 * ((v6 >> 22) & 1)) | 1;
        *((_WORD *)v8 + 3) = (v6 >> 15) & 0x7F;
        v8 += 8;
      }
      v9 = (v8 - (char *)v11) >> 3;
      if ( v9 > 0 )
        wil::details::WilApi_RecordFeatureUsageReports(
          (wil::details *)v11,
          (struct __WIL_RTL_FEATURE_USAGE_DATA *)v9,
          v9);
    }
    *((_QWORD *)this + 7) = *((_QWORD *)this + 6);
    v10 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v10 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v10(0, 254, 0, 0);
    }
  }
}

```

## disassembly

```asm
0x140003e98  mov     [rsp+arg_8], rbx
0x140003e9d  mov     [rsp+arg_10], rbp
0x140003ea2  mov     [rsp+arg_18], rsi
0x140003ea7  push    rdi
0x140003ea8  push    r14
0x140003eaa  push    r15
0x140003eac  sub     rsp, 70h
0x140003eb0  mov     rax, cs:__security_cookie
0x140003eb7  xor     rax, rsp
0x140003eba  mov     [rsp+88h+var_28], rax
0x140003ebf  mov     rdi, rcx
0x140003ec2  mov     rbx, [rcx+30h]
0x140003ec6  mov     rsi, [rcx+38h]
0x140003eca  mov     rax, rsi
0x140003ecd  sub     rax, rbx
0x140003ed0  cmp     rax, 10h
0x140003ed4  jb      loc_140004042
0x140003eda  cmp     rbx, rsi
0x140003edd  jz      loc_14000400F
0x140003ee3  mov     ebp, 1
0x140003ee8  lea     r14d, [rbp+1]
0x140003eec  mov     r15d, 1FFh
0x140003ef2  mov     r9, [rbx+8]
0x140003ef6  mov     r10d, [rbx]
0x140003ef9  prefetchw byte ptr [r9]
0x140003efd  mov     eax, [r9]
0x140003f00  mov     ecx, eax
0x140003f02  and     ecx, 0FFC0401Eh
0x140003f08  lock cmpxchg [r9], ecx
0x140003f0d  jnz     short loc_140003F00
0x140003f0f  mov     edx, eax
0x140003f11  mov     ecx, eax
0x140003f13  shr     ecx, 1
0x140003f15  and     ecx, 0Fh
0x140003f18  jz      short loc_140003F35
0x140003f1a  prefetchw byte ptr [r9+4]
0x140003f1f  mov     eax, [r9+4]
0x140003f23  mov     r8d, eax
0x140003f26  or      r8d, ecx
0x140003f29  lock cmpxchg [r9+4], r8d
0x140003f2f  jnz     short loc_140003F23
0x140003f31  not     eax
0x140003f33  and     ecx, eax
0x140003f35  lea     r8, [rsp+88h+var_58]
0x140003f3a  test    bpl, cl
0x140003f3d  jz      short loc_140003F51
0x140003f3f  mov     [rsp+88h+var_58], r10d
0x140003f44  mov     [rsp+88h+var_54], 10002h
0x140003f4c  lea     r8, [rsp+88h+var_50]
0x140003f51  test    r14b, cl
0x140003f54  jz      short loc_140003F65
0x140003f56  mov     [r8], r10d
0x140003f59  mov     dword ptr [r8+4], 10006h
0x140003f61  add     r8, 8
0x140003f65  test    cl, 4
0x140003f68  jz      short loc_140003F79
0x140003f6a  mov     [r8], r10d
0x140003f6d  mov     dword ptr [r8+4], 10003h
0x140003f75  add     r8, 8
0x140003f79  cmp     ecx, 8
0x140003f7c  jb      short loc_140003F8D
0x140003f7e  mov     [r8], r10d
0x140003f81  mov     dword ptr [r8+4], 10007h
0x140003f89  add     r8, 8
0x140003f8d  mov     ecx, edx
0x140003f8f  shr     ecx, 5
0x140003f92  test    r15d, ecx
0x140003f95  jz      short loc_140003FB8
0x140003f97  mov     [r8], r10d
0x140003f9a  mov     eax, edx
0x140003f9c  shr     eax, 0Eh
0x140003f9f  and     ax, bp
0x140003fa2  shl     ax, 2
0x140003fa6  mov     [r8+4], ax
0x140003fab  and     cx, r15w
0x140003faf  mov     [r8+6], cx
0x140003fb4  add     r8, 8
0x140003fb8  mov     eax, edx
0x140003fba  shr     eax, 0Fh
0x140003fbd  test    al, 7Fh
0x140003fbf  jz      short loc_140003FE3
0x140003fc1  mov     [r8], r10d
0x140003fc4  shr     edx, 16h
0x140003fc7  and     dx, bp
0x140003fca  shl     dx, 2
0x140003fce  or      dx, bp
0x140003fd1  mov     [r8+4], dx
0x140003fd6  and     ax, 7Fh
0x140003fda  mov     [r8+6], ax
0x140003fdf  add     r8, 8
0x140003fe3  lea     rax, [rsp+88h+var_58]
0x140003fe8  sub     r8, rax
0x140003feb  sar     r8, 3; unsigned __int64
0x140003fef  test    r8, r8
0x140003ff2  jle     short loc_140004002
0x140003ff4  mov     rdx, r8; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x140003ff7  lea     rcx, [rsp+88h+var_58]; this
0x140003ffc  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x140004001  nop
0x140004002  add     rbx, 10h
0x140004006  cmp     rbx, rsi
0x140004009  jnz     loc_140003EF2
0x14000400f  mov     rax, [rdi+30h]
0x140004013  mov     [rdi+38h], rax
0x140004017  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x14000401e  test    rax, rax
0x140004021  jnz     short loc_14000402F
0x140004023  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x14000402a  test    rax, rax
0x14000402d  jz      short loc_140004042
0x14000402f  xor     r9d, r9d
0x140004032  xor     r8d, r8d
0x140004035  mov     edx, 0FEh
0x14000403a  xor     ecx, ecx
0x14000403c  call    _guard_dispatch_icall
0x140004041  nop
0x140004042  mov     rcx, [rsp+88h+var_28]
0x140004047  xor     rcx, rsp; StackCookie
0x14000404a  call    __security_check_cookie
0x14000404f  lea     r11, [rsp+88h+var_18]
0x140004054  mov     rbx, [r11+28h]
0x140004058  mov     rbp, [r11+30h]
0x14000405c  mov     rsi, [r11+38h]
0x140004060  mov     rsp, r11
0x140004063  pop     r15
0x140004065  pop     r14
0x140004067  pop     rdi
0x140004068  retn
```
