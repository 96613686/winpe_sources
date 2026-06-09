# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(void)

- ea: `0x18000f670`
- end: `0x18000f89f`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXXZ`
- size: `559`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000f620`
- `0x18000f8a0`
- `0x1800419a0`

## callees

- `0x18000f670`
- `0x180034ef0`
- `0x18003bed0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::EnabledStateManager::RecordCachedUsageUnderLock(int **this)
{
  wil::details::EnabledStateManager *v1; // r14
  int *v2; // rbx
  int *v3; // rbp
  unsigned __int32 *v4; // r9
  int v5; // r10d
  unsigned __int32 v6; // eax
  unsigned __int32 v7; // ett
  unsigned __int32 v8; // edx
  unsigned int v9; // ecx
  int *v10; // rdi
  unsigned __int32 v11; // eax
  __int64 v12; // rdi
  unsigned __int64 i; // rsi
  void (__fastcall *v14)(_QWORD, _QWORD, _QWORD, _QWORD); // rax
  void (__fastcall *v15)(_QWORD, __int64, _QWORD, _QWORD); // rax
  int v17; // [rsp+38h] [rbp-60h] BYREF
  int v18; // [rsp+3Ch] [rbp-5Ch]
  char v19; // [rsp+40h] [rbp-58h] BYREF

  v1 = (wil::details::EnabledStateManager *)this;
  v2 = this[6];
  v3 = this[7];
  if ( (unsigned __int64)((char *)v3 - (char *)v2) >= 0x10 )
  {
    if ( v2 != v3 )
    {
      do
      {
        v4 = (unsigned __int32 *)*((_QWORD *)v2 + 1);
        v5 = *v2;
        _m_prefetchw(v4);
        v6 = *v4;
        do
        {
          v7 = v6;
          v6 = _InterlockedCompareExchange((volatile signed __int32 *)v4, v6 & 0xFFC0401E, v6);
        }
        while ( v7 != v6 );
        v8 = v6;
        v9 = (v6 >> 1) & 0xF;
        if ( v9 )
        {
          _m_prefetchw(v4 + 1);
          v9 &= ~_InterlockedOr((volatile signed __int32 *)v4 + 1, v9);
        }
        v10 = &v17;
        if ( (v9 & 1) != 0 )
        {
          v17 = v5;
          v18 = 65538;
          v10 = (int *)&v19;
        }
        if ( (v9 & 2) != 0 )
        {
          *v10 = v5;
          v10[1] = 65542;
          v10 += 2;
        }
        if ( (v9 & 4) != 0 )
        {
          *v10 = v5;
          v10[1] = 65539;
          v10 += 2;
        }
        if ( v9 >= 8 )
        {
          *v10 = v5;
          v10[1] = 65543;
          v10 += 2;
        }
        if ( ((v6 >> 5) & 0x1FF) != 0 )
        {
          *v10 = v5;
          *((_WORD *)v10 + 2) = 4 * ((v6 >> 14) & 1);
          *((_WORD *)v10 + 3) = (v6 >> 5) & 0x1FF;
          v10 += 2;
        }
        v11 = v6 >> 15;
        if ( ((v8 >> 15) & 0x7F) != 0 )
        {
          *v10 = v5;
          *((_WORD *)v10 + 2) = (4 * ((v8 >> 22) & 1)) | 1;
          *((_WORD *)v10 + 3) = v11 & 0x7F;
          v10 += 2;
        }
        v12 = ((char *)v10 - (char *)&v17) >> 3;
        if ( v12 > 0 )
        {
          for ( i = 0; i < v12; ++i )
          {
            v14 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
            if ( !g_wil_details_internalRecordFeatureUsage )
            {
              v14 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage;
              if ( !g_wil_details_apiRecordFeatureUsage )
                continue;
            }
            v14(
              (unsigned int)*(&v17 + 2 * i),
              *((unsigned __int16 *)&v18 + 4 * i),
              *((unsigned __int16 *)&v18 + 4 * i + 1),
              0);
          }
        }
        v2 += 4;
      }
      while ( v2 != v3 );
      v1 = (wil::details::EnabledStateManager *)this;
    }
    *((_QWORD *)v1 + 7) = *((_QWORD *)v1 + 6);
    v15 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v15 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v15(0, 254, 0, 0);
    }
  }
}

```

## disassembly

```asm
0x18000f670  mov     [rsp+arg_8], rbx
0x18000f675  mov     [rsp+arg_10], rbp
0x18000f67a  mov     [rsp+arg_18], rsi
0x18000f67f  push    rdi
0x18000f680  push    r12
0x18000f682  push    r13
0x18000f684  push    r14
0x18000f686  push    r15
0x18000f688  sub     rsp, 70h
0x18000f68c  mov     rax, cs:__security_cookie
0x18000f693  xor     rax, rsp
0x18000f696  mov     [rsp+98h+var_30], rax
0x18000f69b  mov     r14, rcx
0x18000f69e  mov     [rsp+98h+var_68], rcx
0x18000f6a3  mov     rbx, [rcx+30h]
0x18000f6a7  mov     rbp, [rcx+38h]
0x18000f6ab  mov     rax, rbp
0x18000f6ae  sub     rax, rbx
0x18000f6b1  cmp     rax, 10h
0x18000f6b5  jb      loc_18000F874
0x18000f6bb  cmp     rbx, rbp
0x18000f6be  jz      loc_18000F840
0x18000f6c4  mov     r11d, 3
0x18000f6ca  mov     r12d, 1FFh
0x18000f6d0  mov     r9, [rbx+8]
0x18000f6d4  mov     r10d, [rbx]
0x18000f6d7  prefetchw byte ptr [r9]
0x18000f6db  mov     eax, [r9]
0x18000f6de  xchg    ax, ax
0x18000f6e0  mov     ecx, eax
0x18000f6e2  and     ecx, 0FFC0401Eh
0x18000f6e8  lock cmpxchg [r9], ecx
0x18000f6ed  jnz     short loc_18000F6E0
0x18000f6ef  mov     edx, eax
0x18000f6f1  mov     ecx, eax
0x18000f6f3  shr     ecx, 1
0x18000f6f5  and     ecx, 0Fh
0x18000f6f8  jz      short loc_18000F722
0x18000f6fa  prefetchw byte ptr [r9+4]
0x18000f6ff  mov     eax, [r9+4]
0x18000f703  nop     dword ptr [rax+00h]
0x18000f707  nop     word ptr [rax+rax+00000000h]
0x18000f710  mov     r8d, eax
0x18000f713  or      r8d, ecx
0x18000f716  lock cmpxchg [r9+4], r8d
0x18000f71c  jnz     short loc_18000F710
0x18000f71e  not     eax
0x18000f720  and     ecx, eax
0x18000f722  lea     rdi, [rsp+98h+var_60]
0x18000f727  test    cl, 1
0x18000f72a  jz      short loc_18000F73E
0x18000f72c  mov     [rsp+98h+var_60], r10d
0x18000f731  mov     [rsp+98h+var_5C], 10002h
0x18000f739  lea     rdi, [rsp+98h+var_58]
0x18000f73e  test    cl, 2
0x18000f741  jz      short loc_18000F751
0x18000f743  mov     [rdi], r10d
0x18000f746  mov     dword ptr [rdi+4], 10006h
0x18000f74d  add     rdi, 8
0x18000f751  test    cl, 4
0x18000f754  jz      short loc_18000F764
0x18000f756  mov     [rdi], r10d
0x18000f759  mov     dword ptr [rdi+4], 10003h
0x18000f760  add     rdi, 8
0x18000f764  cmp     ecx, 8
0x18000f767  jb      short loc_18000F777
0x18000f769  mov     [rdi], r10d
0x18000f76c  mov     dword ptr [rdi+4], 10007h
0x18000f773  add     rdi, 8
0x18000f777  mov     ecx, edx
0x18000f779  shr     ecx, 5
0x18000f77c  test    r12d, ecx
0x18000f77f  jz      short loc_18000F7A1
0x18000f781  mov     [rdi], r10d
0x18000f784  mov     eax, edx
0x18000f786  shr     eax, 0Eh
0x18000f789  and     ax, 1
0x18000f78d  shl     ax, 2
0x18000f791  mov     [rdi+4], ax
0x18000f795  and     cx, r12w
0x18000f799  mov     [rdi+6], cx
0x18000f79d  add     rdi, 8
0x18000f7a1  mov     eax, edx
0x18000f7a3  shr     eax, 0Fh
0x18000f7a6  test    al, 7Fh
0x18000f7a8  jz      short loc_18000F7CC
0x18000f7aa  mov     [rdi], r10d
0x18000f7ad  shr     edx, 16h
0x18000f7b0  and     dx, 1
0x18000f7b4  shl     dx, 2
0x18000f7b8  or      dx, 1
0x18000f7bc  mov     [rdi+4], dx
0x18000f7c0  and     ax, 7Fh
0x18000f7c4  mov     [rdi+6], ax
0x18000f7c8  add     rdi, 8
0x18000f7cc  lea     rax, [rsp+98h+var_60]
0x18000f7d1  sub     rdi, rax
0x18000f7d4  sar     rdi, 3
0x18000f7d8  test    rdi, rdi
0x18000f7db  jle     short loc_18000F82E
0x18000f7dd  xor     esi, esi
0x18000f7df  test    rdi, rdi
0x18000f7e2  jz      short loc_18000F82E
0x18000f7e4  nop     dword ptr [rax+00h]
0x18000f7e8  nop     dword ptr [rax+rax+00000000h]
0x18000f7f0  movzx   r8d, word ptr [rsp+rsi*8+98h+var_5C+2]
0x18000f7f6  movzx   edx, word ptr [rsp+rsi*8+98h+var_5C]
0x18000f7fb  mov     ecx, [rsp+rsi*8+98h+var_60]
0x18000f7ff  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000f806  test    rax, rax
0x18000f809  jnz     short loc_18000F817
0x18000f80b  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000f812  test    rax, rax
0x18000f815  jz      short loc_18000F820
0x18000f817  xor     r9d, r9d
0x18000f81a  call    cs:__guard_dispatch_icall_fptr
0x18000f820  inc     rsi
0x18000f823  cmp     rsi, rdi
0x18000f826  jb      short loc_18000F7F0
0x18000f828  mov     r11d, 3
0x18000f82e  add     rbx, 10h
0x18000f832  cmp     rbx, rbp
0x18000f835  jnz     loc_18000F6D0
0x18000f83b  mov     r14, [rsp+98h+var_68]
0x18000f840  mov     rax, [r14+30h]
0x18000f844  mov     [r14+38h], rax
0x18000f848  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000f84f  test    rax, rax
0x18000f852  jnz     short loc_18000F860
0x18000f854  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000f85b  test    rax, rax
0x18000f85e  jz      short loc_18000F874
0x18000f860  xor     r9d, r9d
0x18000f863  xor     r8d, r8d
0x18000f866  mov     edx, 0FEh
0x18000f86b  xor     ecx, ecx
0x18000f86d  call    cs:__guard_dispatch_icall_fptr
0x18000f873  nop
0x18000f874  mov     rcx, [rsp+98h+var_30]
0x18000f879  xor     rcx, rsp; StackCookie
0x18000f87c  call    __security_check_cookie
0x18000f881  lea     r11, [rsp+98h+var_28]
0x18000f886  mov     rbx, [r11+38h]
0x18000f88a  mov     rbp, [r11+40h]
0x18000f88e  mov     rsi, [r11+48h]
0x18000f892  mov     rsp, r11
0x18000f895  pop     r15
0x18000f897  pop     r14
0x18000f899  pop     r13
0x18000f89b  pop     r12
0x18000f89d  pop     rdi
0x18000f89e  retn
```
