# AppReadiness::Tasks::AppxPreRegister::Add(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x180026610`
- end: `0x1800266f1`
- name: `?Add@AppxPreRegister@Tasks@AppReadiness@@AEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@5@@Z`
- size: `225`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003db20`

## callees

- `0x1800148b0`
- `0x180026610`
- `0x180026954`
- `0x18002c3d0`
- `0x18004a3bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800266e2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800266e2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180026662`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180026662`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall AppReadiness::Tasks::AppxPreRegister::Add(__int64 a1, __int64 a2, __int64 *a3)
{
  __int64 v5; // rcx
  __int64 v6; // rdi
  __int64 v7; // rbp
  const WCHAR *v8; // r8
  const WCHAR *v9; // rcx
  __int64 v10; // rdx
  PSRWLOCK SRWLock; // [rsp+60h] [rbp+8h] BYREF

  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, a1 + 56);
  v6 = *a3;
  v7 = a3[1];
  while ( v6 != v7 )
  {
    if ( *(_QWORD *)(v6 + 24) <= 7u )
      v8 = (const WCHAR *)v6;
    else
      v8 = *(const WCHAR **)v6;
    v9 = (const WCHAR *)a2;
    if ( *(_QWORD *)(a2 + 24) > 7u )
      v9 = *(const WCHAR **)a2;
    if ( CompareStringOrdinal(v9, -1, v8, -1, 1) == 2 )
      break;
    v6 += 32;
  }
  v10 = a3[1];
  if ( v6 == v10 )
  {
    if ( v10 == a3[2] )
    {
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(a3, v10, a2);
    }
    else
    {
      std::_Default_allocator_traits<std::allocator<std::wstring>>::construct<std::wstring,std::wstring const &>(
        v5,
        v10,
        a2);
      a3[1] += 32;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_fb225c8d27f6327f6fb2058d73d6f2b1_Traceguids);
  }
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
}

```

## disassembly

```asm
0x180026610  push    rbx
0x180026612  push    rbp
0x180026613  push    rsi
0x180026614  push    rdi
0x180026615  sub     rsp, 38h
0x180026619  mov     rsi, r8
0x18002661c  mov     rbx, rdx
0x18002661f  lea     rdx, [rcx+38h]
0x180026623  lea     rcx, [rsp+58h+SRWLock]
0x180026628  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18002662d  nop
0x18002662e  mov     rdi, [rsi]
0x180026631  mov     rbp, [rsi+8]
0x180026635  jmp     short loc_180026671
0x180026637  cmp     qword ptr [rdi+18h], 7
0x18002663c  jbe     short loc_180026643
0x18002663e  mov     r8, [rdi]
0x180026641  jmp     short loc_180026646
0x180026643  mov     r8, rdi; lpString2
0x180026646  mov     rcx, rbx
0x180026649  cmp     qword ptr [rbx+18h], 7
0x18002664e  jbe     short loc_180026653
0x180026650  mov     rcx, [rbx]; lpString1
0x180026653  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x18002665b  or      r9d, 0FFFFFFFFh; cchCount2
0x18002665f  or      edx, r9d; cchCount1
0x180026662  call    cs:__imp_CompareStringOrdinal
0x180026668  cmp     eax, 2
0x18002666b  jz      short loc_180026676
0x18002666d  add     rdi, 20h ; ' '
0x180026671  cmp     rdi, rbp
0x180026674  jnz     short loc_180026637
0x180026676  mov     rdx, [rsi+8]
0x18002667a  cmp     rdi, rdx
0x18002667d  jnz     short loc_1800266D8
0x18002667f  mov     r8, rbx
0x180026682  cmp     rdx, [rsi+10h]
0x180026686  jz      short loc_180026694
0x180026688  call    ??$construct@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@?$_Default_allocator_traits@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@SAXAEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV31@@Z; std::_Default_allocator_traits<std::allocator<std::wstring>>::construct<std::wstring,std::wstring const &>(std::allocator<std::wstring> &,std::wstring * const,std::wstring const &)
0x18002668d  add     qword ptr [rsi+8], 20h ; ' '
0x180026692  jmp     short loc_18002669C
0x180026694  mov     rcx, rsi
0x180026697  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x18002669c  lea     rax, WPP_GLOBAL_Control
0x1800266a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800266aa  cmp     rcx, rax
0x1800266ad  jz      short loc_1800266D8
0x1800266af  test    byte ptr [rcx+1Ch], 4
0x1800266b3  jz      short loc_1800266D8
0x1800266b5  cmp     qword ptr [rbx+18h], 7
0x1800266ba  jbe     short loc_1800266BF
0x1800266bc  mov     rbx, [rbx]
0x1800266bf  mov     edx, 0Ah
0x1800266c4  mov     r9, rbx
0x1800266c7  lea     r8, WPP_fb225c8d27f6327f6fb2058d73d6f2b1_Traceguids
0x1800266ce  mov     rcx, [rcx+10h]
0x1800266d2  call    WPP_SF_S
0x1800266d7  nop
0x1800266d8  mov     rcx, [rsp+58h+SRWLock]; SRWLock
0x1800266dd  test    rcx, rcx
0x1800266e0  jz      short loc_1800266E8
0x1800266e2  call    cs:__imp_ReleaseSRWLockExclusive
0x1800266e8  add     rsp, 38h
0x1800266ec  pop     rdi
0x1800266ed  pop     rsi
0x1800266ee  pop     rbp
0x1800266ef  pop     rbx
0x1800266f0  retn
```
