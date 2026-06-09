# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(void)

- ea: `0x180004650`
- end: `0x18000487f`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXXZ`
- size: `559`
- prototype: `void __fastcall(int **this)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004b90`
- `0x180008420`
- `0x18001fba0`

## callees

- `0x180004650`
- `0x1800181b0`
- `0x18001cdf0`

## pseudocode

```c
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
0x180004650  mov     [rsp+arg_8], rbx
0x180004655  mov     [rsp+arg_10], rbp
0x18000465a  mov     [rsp+arg_18], rsi
0x18000465f  push    rdi
0x180004660  push    r12
0x180004662  push    r13
0x180004664  push    r14
0x180004666  push    r15
0x180004668  sub     rsp, 70h
0x18000466c  mov     rax, cs:__security_cookie
0x180004673  xor     rax, rsp
0x180004676  mov     [rsp+98h+var_30], rax
0x18000467b  mov     r14, rcx
0x18000467e  mov     [rsp+98h+var_68], rcx
0x180004683  mov     rbx, [rcx+30h]
0x180004687  mov     rbp, [rcx+38h]
0x18000468b  mov     rax, rbp
0x18000468e  sub     rax, rbx
0x180004691  cmp     rax, 10h
0x180004695  jb      loc_180004854
0x18000469b  cmp     rbx, rbp
0x18000469e  jz      loc_180004820
0x1800046a4  mov     r11d, 3
0x1800046aa  mov     r12d, 1FFh
0x1800046b0  mov     r9, [rbx+8]
0x1800046b4  mov     r10d, [rbx]
0x1800046b7  prefetchw byte ptr [r9]
0x1800046bb  mov     eax, [r9]
0x1800046be  xchg    ax, ax
0x1800046c0  mov     ecx, eax
0x1800046c2  and     ecx, 0FFC0401Eh
0x1800046c8  lock cmpxchg [r9], ecx
0x1800046cd  jnz     short loc_1800046C0
0x1800046cf  mov     edx, eax
0x1800046d1  mov     ecx, eax
0x1800046d3  shr     ecx, 1
0x1800046d5  and     ecx, 0Fh
0x1800046d8  jz      short loc_180004702
0x1800046da  prefetchw byte ptr [r9+4]
0x1800046df  mov     eax, [r9+4]
0x1800046e3  nop     dword ptr [rax+00h]
0x1800046e7  nop     word ptr [rax+rax+00000000h]
0x1800046f0  mov     r8d, eax
0x1800046f3  or      r8d, ecx
0x1800046f6  lock cmpxchg [r9+4], r8d
0x1800046fc  jnz     short loc_1800046F0
0x1800046fe  not     eax
0x180004700  and     ecx, eax
0x180004702  lea     rdi, [rsp+98h+var_60]
0x180004707  test    cl, 1
0x18000470a  jz      short loc_18000471E
0x18000470c  mov     [rsp+98h+var_60], r10d
0x180004711  mov     [rsp+98h+var_5C], 10002h
0x180004719  lea     rdi, [rsp+98h+var_58]
0x18000471e  test    cl, 2
0x180004721  jz      short loc_180004731
0x180004723  mov     [rdi], r10d
0x180004726  mov     dword ptr [rdi+4], 10006h
0x18000472d  add     rdi, 8
0x180004731  test    cl, 4
0x180004734  jz      short loc_180004744
0x180004736  mov     [rdi], r10d
0x180004739  mov     dword ptr [rdi+4], 10003h
0x180004740  add     rdi, 8
0x180004744  cmp     ecx, 8
0x180004747  jb      short loc_180004757
0x180004749  mov     [rdi], r10d
0x18000474c  mov     dword ptr [rdi+4], 10007h
0x180004753  add     rdi, 8
0x180004757  mov     ecx, edx
0x180004759  shr     ecx, 5
0x18000475c  test    r12d, ecx
0x18000475f  jz      short loc_180004781
0x180004761  mov     [rdi], r10d
0x180004764  mov     eax, edx
0x180004766  shr     eax, 0Eh
0x180004769  and     ax, 1
0x18000476d  shl     ax, 2
0x180004771  mov     [rdi+4], ax
0x180004775  and     cx, r12w
0x180004779  mov     [rdi+6], cx
0x18000477d  add     rdi, 8
0x180004781  mov     eax, edx
0x180004783  shr     eax, 0Fh
0x180004786  test    al, 7Fh
0x180004788  jz      short loc_1800047AC
0x18000478a  mov     [rdi], r10d
0x18000478d  shr     edx, 16h
0x180004790  and     dx, 1
0x180004794  shl     dx, 2
0x180004798  or      dx, 1
0x18000479c  mov     [rdi+4], dx
0x1800047a0  and     ax, 7Fh
0x1800047a4  mov     [rdi+6], ax
0x1800047a8  add     rdi, 8
0x1800047ac  lea     rax, [rsp+98h+var_60]
0x1800047b1  sub     rdi, rax
0x1800047b4  sar     rdi, 3
0x1800047b8  test    rdi, rdi
0x1800047bb  jle     short loc_18000480E
0x1800047bd  xor     esi, esi
0x1800047bf  test    rdi, rdi
0x1800047c2  jz      short loc_18000480E
0x1800047c4  nop     dword ptr [rax+00h]
0x1800047c8  nop     dword ptr [rax+rax+00000000h]
0x1800047d0  movzx   r8d, word ptr [rsp+rsi*8+98h+var_5C+2]
0x1800047d6  movzx   edx, word ptr [rsp+rsi*8+98h+var_5C]
0x1800047db  mov     ecx, [rsp+rsi*8+98h+var_60]
0x1800047df  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x1800047e6  test    rax, rax
0x1800047e9  jnz     short loc_1800047F7
0x1800047eb  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x1800047f2  test    rax, rax
0x1800047f5  jz      short loc_180004800
0x1800047f7  xor     r9d, r9d
0x1800047fa  call    cs:__guard_dispatch_icall_fptr
0x180004800  inc     rsi
0x180004803  cmp     rsi, rdi
0x180004806  jb      short loc_1800047D0
0x180004808  mov     r11d, 3
0x18000480e  add     rbx, 10h
0x180004812  cmp     rbx, rbp
0x180004815  jnz     loc_1800046B0
0x18000481b  mov     r14, [rsp+98h+var_68]
0x180004820  mov     rax, [r14+30h]
0x180004824  mov     [r14+38h], rax
0x180004828  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000482f  test    rax, rax
0x180004832  jnz     short loc_180004840
0x180004834  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000483b  test    rax, rax
0x18000483e  jz      short loc_180004854
0x180004840  xor     r9d, r9d
0x180004843  xor     r8d, r8d
0x180004846  mov     edx, 0FEh
0x18000484b  xor     ecx, ecx
0x18000484d  call    cs:__guard_dispatch_icall_fptr
0x180004853  nop
0x180004854  mov     rcx, [rsp+98h+var_30]
0x180004859  xor     rcx, rsp; StackCookie
0x18000485c  call    __security_check_cookie
0x180004861  lea     r11, [rsp+98h+var_28]
0x180004866  mov     rbx, [r11+38h]
0x18000486a  mov     rbp, [r11+40h]
0x18000486e  mov     rsi, [r11+48h]
0x180004872  mov     rsp, r11
0x180004875  pop     r15
0x180004877  pop     r14
0x180004879  pop     r13
0x18000487b  pop     r12
0x18000487d  pop     rdi
0x18000487e  retn
```
