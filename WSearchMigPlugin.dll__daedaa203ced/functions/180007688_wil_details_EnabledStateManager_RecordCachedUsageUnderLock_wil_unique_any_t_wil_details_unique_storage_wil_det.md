# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x180007688`
- end: `0x180007848`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `448`
- prototype: `__int64 (__fastcall *__fastcall(__int64))(_QWORD, __int64, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800071a4`
- `0x18000c260`
- `0x18000c2c0`

## callees

- `0x1800026f0`
- `0x180007688`
- `0x180009c64`
- `0x180018010`

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
  _DWORD v12[2]; // [rsp+38h] [rbp-70h] BYREF
  char v13; // [rsp+40h] [rbp-68h] BYREF

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
0x180007688  push    rbx
0x18000768a  push    rbp
0x18000768b  push    rsi
0x18000768c  push    rdi
0x18000768d  push    r14
0x18000768f  push    r15
0x180007691  sub     rsp, 78h
0x180007695  mov     [rsp+0A8h+var_78], 0FFFFFFFFFFFFFFFEh
0x18000769e  mov     rax, cs:__security_cookie
0x1800076a5  xor     rax, rsp
0x1800076a8  mov     [rsp+0A8h+var_40], rax
0x1800076ad  mov     rsi, rcx
0x1800076b0  mov     rbx, [rcx+20h]
0x1800076b4  mov     rdi, [rcx+28h]
0x1800076b8  mov     rax, rdi
0x1800076bb  sub     rax, rbx
0x1800076be  cmp     rax, 10h
0x1800076c2  jb      loc_18000782E
0x1800076c8  mov     ebp, 1
0x1800076cd  lea     r14d, [rbp+1]
0x1800076d1  mov     r15d, 1FFh
0x1800076d7  cmp     rbx, rdi
0x1800076da  jz      loc_1800077FB
0x1800076e0  mov     r8, [rbx+8]
0x1800076e4  mov     r10d, [rbx]
0x1800076e7  prefetchw byte ptr [r8]
0x1800076eb  mov     eax, [r8]
0x1800076ee  mov     ecx, eax
0x1800076f0  and     ecx, 0FFC0401Eh
0x1800076f6  lock cmpxchg [r8], ecx
0x1800076fb  jnz     short loc_1800076EE
0x1800076fd  mov     ecx, eax
0x1800076ff  mov     r9d, eax
0x180007702  shr     r9d, 1
0x180007705  and     r9d, 0Fh
0x180007709  jz      short loc_180007728
0x18000770b  prefetchw byte ptr [r8+4]
0x180007710  mov     eax, [r8+4]
0x180007714  mov     edx, eax
0x180007716  or      edx, r9d
0x180007719  lock cmpxchg [r8+4], edx
0x18000771f  jnz     short loc_180007714
0x180007721  not     eax
0x180007723  and     eax, r9d
0x180007726  jmp     short loc_18000772B
0x180007728  mov     eax, r9d
0x18000772b  test    bpl, al
0x18000772e  jz      short loc_180007744
0x180007730  mov     [rsp+0A8h+var_70], r10d
0x180007735  mov     [rsp+0A8h+var_6C], 10002h
0x18000773d  lea     rdx, [rsp+0A8h+var_68]
0x180007742  jmp     short loc_180007749
0x180007744  lea     rdx, [rsp+0A8h+var_70]
0x180007749  test    r14b, al
0x18000774c  jz      short loc_18000775C
0x18000774e  mov     [rdx], r10d
0x180007751  mov     dword ptr [rdx+4], 10006h
0x180007758  add     rdx, 8
0x18000775c  test    al, 4
0x18000775e  jz      short loc_18000776E
0x180007760  mov     [rdx], r10d
0x180007763  mov     dword ptr [rdx+4], 10003h
0x18000776a  add     rdx, 8
0x18000776e  cmp     eax, 8
0x180007771  jb      short loc_180007781
0x180007773  mov     [rdx], r10d
0x180007776  mov     dword ptr [rdx+4], 10007h
0x18000777d  add     rdx, 8
0x180007781  mov     r8d, ecx
0x180007784  shr     r8d, 5
0x180007788  test    r15d, r8d
0x18000778b  jz      short loc_1800077AD
0x18000778d  mov     [rdx], r10d
0x180007790  mov     eax, ecx
0x180007792  shr     eax, 0Eh
0x180007795  and     ax, bp
0x180007798  shl     ax, 2
0x18000779c  mov     [rdx+4], ax
0x1800077a0  and     r8w, r15w; unsigned __int64
0x1800077a4  mov     [rdx+6], r8w
0x1800077a9  add     rdx, 8
0x1800077ad  mov     eax, ecx
0x1800077af  shr     eax, 0Fh
0x1800077b2  test    al, 7Fh
0x1800077b4  jz      short loc_1800077D6
0x1800077b6  mov     [rdx], r10d
0x1800077b9  shr     ecx, 16h
0x1800077bc  and     cx, bp
0x1800077bf  shl     cx, 2
0x1800077c3  add     cx, bp
0x1800077c6  mov     [rdx+4], cx
0x1800077ca  and     ax, 7Fh
0x1800077ce  mov     [rdx+6], ax
0x1800077d2  add     rdx, 8
0x1800077d6  lea     rax, [rsp+0A8h+var_70]
0x1800077db  sub     rdx, rax
0x1800077de  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x1800077e2  test    rdx, rdx
0x1800077e5  jle     short loc_1800077F2
0x1800077e7  lea     rcx, [rsp+0A8h+var_70]; this
0x1800077ec  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x1800077f1  nop
0x1800077f2  add     rbx, 10h
0x1800077f6  jmp     loc_1800076D7
0x1800077fb  mov     rax, [rsi+20h]
0x1800077ff  mov     [rsi+28h], rax
0x180007803  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000780a  test    rax, rax
0x18000780d  jnz     short loc_18000781B
0x18000780f  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180007816  test    rax, rax
0x180007819  jz      short loc_18000782E
0x18000781b  xor     r9d, r9d
0x18000781e  xor     r8d, r8d
0x180007821  mov     edx, 0FEh
0x180007826  xor     ecx, ecx
0x180007828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000782d  nop
0x18000782e  mov     rcx, [rsp+0A8h+var_40]
0x180007833  xor     rcx, rsp; StackCookie
0x180007836  call    __security_check_cookie
0x18000783b  add     rsp, 78h
0x18000783f  pop     r15
0x180007841  pop     r14
0x180007843  pop     rdi
0x180007844  pop     rsi
0x180007845  pop     rbp
0x180007846  pop     rbx
0x180007847  retn
```
