# asg::Sqlite::TransactionGuard__asg::Sqlite::DbTransaction::AcquireTransactionGuard_::_2_::_lambda_1___::_TransactionGuard__asg::Sqlite::DbTransaction::AcquireTransactionGuard_::_2_::_lambda_1___

- ea: `0x18017efe0`
- end: `0x18017f155`
- name: `asg::Sqlite::TransactionGuard__asg::Sqlite::DbTransaction::AcquireTransactionGuard_::_2_::_lambda_1___::_TransactionGuard__asg::Sqlite::DbTransaction::AcquireTransactionGuard_::_2_::_lambda_1___`
- size: `373`
- prototype: ``
- caller_count: `12`
- callee_count: `9`
- tags: ``

## callers

- `0x18017fa90`
- `0x18017ff20`
- `0x180180080`
- `0x180180bd0`
- `0x180180ee0`
- `0x180181140`
- `0x180181790`
- `0x180251c90`
- `0x180251ce0`
- `0x180251d00`
- `0x180251dd0`
- `0x180251de0`

## callees

- `0x180007e60`
- `0x18001db40`
- `0x18007b3e0`
- `0x18017efe0`
- `0x1801d2ae0`
- `0x1801d2b20`
- `0x1801d2dc0`
- `0x1801d2e10`
- `0x1801d3160`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18017f043`
- `KERNEL32!GetCurrentThreadId` at `0x18017f043`

## string_xrefs

- `0x18017f095`: `DbTransaction guard ended on different thread!`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall asg::Sqlite::TransactionGuard__asg::Sqlite::DbTransaction::AcquireTransactionGuard_::_2_::_lambda_1___::_TransactionGuard__asg::Sqlite::DbTransaction::AcquireTransactionGuard_::_2_::_lambda_1___(
        __int64 a1)
{
  __int64 v2; // rsi
  __int64 v3; // rbx
  DWORD CurrentThreadId; // ebx
  __int64 v5; // rax
  int result; // eax
  volatile signed __int32 *v7; // rbx
  __int128 v8; // [rsp+20h] [rbp-68h] BYREF
  __int128 v9; // [rsp+30h] [rbp-58h]
  char v10; // [rsp+40h] [rbp-48h]
  _OWORD v11[2]; // [rsp+60h] [rbp-28h] BYREF

  v2 = *(_QWORD *)(a1 + 16);
  if ( Mtx_lock((_Mtx_t)(v2 + 24)) )
    std::_Throw_Cpp_error(5);
  if ( *(_DWORD *)(v2 + 100) == 0x7FFFFFFF )
  {
    *(_DWORD *)(v2 + 100) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  --*(_DWORD *)(*(_QWORD *)(a1 + 16) + 176LL);
  v3 = *(_QWORD *)(*(_QWORD *)(a1 + 16) + 192LL);
  if ( v3 )
  {
    asg::IsFeatureEnabled<wil::Feature<__WilFeatureTraits_Feature_56532199>>();
    if ( !*(_BYTE *)(v3 + 256) )
    {
      CurrentThreadId = GetCurrentThreadId();
      if ( Thrd_id() != CurrentThreadId )
      {
        *(_QWORD *)&v8 = 0x150000006CLL;
        *((_QWORD *)&v8 + 1) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\libSqliteWrapper\\DbTransaction.cpp";
        *(_QWORD *)&v9 = "auto __cdecl asg::Sqlite::DbTransaction::AcquireTransactionGuard::<lambda_1>::operator ()(void) noexcept const";
        BYTE8(v9) = 1;
        v11[0] = v8;
        v11[1] = v9;
        asg::details::_asg_Log<std::integral_constant<bool,0>>(
          &v8,
          v11,
          4,
          L"DbTransaction guard ended on different thread!");
        if ( v10 )
          asg::SemanticPipelines::RegionId::~RegionId((asg::SemanticPipelines::RegionId *)&v8);
      }
    }
  }
  v5 = *(_QWORD *)(a1 + 16);
  if ( !*(_DWORD *)(v5 + 176) )
  {
    *(_BYTE *)(v5 + 184) = 0;
    Cnd_broadcast((_Cnd_t)(*(_QWORD *)(a1 + 16) + 104LL));
  }
  result = Mtx_unlock((_Mtx_t)(v2 + 24));
  v7 = *(volatile signed __int32 **)(a1 + 8);
  if ( v7 )
  {
    result = _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF);
    if ( result == 1 )
    {
      result = (**(__int64 (__fastcall ***)(volatile signed __int32 *))v7)(v7);
      if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
        return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18017efe0  mov     [rsp+arg_0], rbx
0x18017efe5  mov     [rsp+arg_8], rsi
0x18017efea  push    rdi
0x18017efeb  sub     rsp, 80h
0x18017eff2  mov     rdi, rcx
0x18017eff5  mov     rsi, [rcx+10h]
0x18017eff9  lea     rcx, [rsi+18h]; _Mtx_t
0x18017effd  call    _Mtx_lock
0x18017f002  test    eax, eax
0x18017f004  jnz     loc_18017F14A
0x18017f00a  cmp     dword ptr [rsi+64h], 7FFFFFFFh
0x18017f011  jz      loc_18017F138
0x18017f017  mov     rax, [rdi+10h]
0x18017f01b  dec     dword ptr [rax+0B0h]
0x18017f021  mov     rax, [rdi+10h]
0x18017f025  mov     rbx, [rax+0C0h]
0x18017f02c  test    rbx, rbx
0x18017f02f  jz      loc_18017F0C2
0x18017f035  call    ??$IsFeatureEnabled@V?$Feature@U__WilFeatureTraits_Feature_56532199@@@wil@@@asg@@YA_NXZ; asg::IsFeatureEnabled<wil::Feature<__WilFeatureTraits_Feature_56532199>>(void)
0x18017f03a  cmp     byte ptr [rbx+100h], 0
0x18017f041  jnz     short loc_18017F0C2
0x18017f043  call    cs:__imp_GetCurrentThreadId
0x18017f049  mov     ebx, eax
0x18017f04b  call    _Thrd_id
0x18017f050  cmp     eax, ebx
0x18017f052  jz      short loc_18017F0C2
0x18017f054  mov     dword ptr [rsp+88h+var_68], 6Ch ; 'l'
0x18017f05c  mov     dword ptr [rsp+88h+var_68+4], 15h
0x18017f064  lea     rax, aCW1SSrcSemanti_18; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18017f06b  mov     qword ptr [rsp+88h+var_68+8], rax
0x18017f070  lea     rax, aAutoCdeclAsgSq; "auto __cdecl asg::Sqlite::DbTransaction"...
0x18017f077  mov     qword ptr [rsp+88h+var_58], rax
0x18017f07c  mov     byte ptr [rsp+88h+var_58+8], 1
0x18017f081  movups  xmm0, [rsp+88h+var_68]
0x18017f086  movaps  [rsp+88h+var_28], xmm0
0x18017f08b  movups  xmm1, [rsp+88h+var_58]
0x18017f090  movaps  [rsp+88h+var_18], xmm1
0x18017f095  lea     r9, aDbtransactionG; "DbTransaction guard ended on different "...
0x18017f09c  mov     r8d, 4
0x18017f0a2  lea     rdx, [rsp+88h+var_28]
0x18017f0a7  lea     rcx, [rsp+88h+var_68]
0x18017f0ac  call    ??$_asg_Log@U?$integral_constant@_N$0A@@std@@@details@asg@@YA?AULogStringView@1@V?$optional@Usource_location@std@@@std@@W4LogLevel@1@PEB_SZZ; asg::details::_asg_Log<std::integral_constant<bool,0>>(std::optional<std::source_location>,asg::LogLevel,char16_t const *,...)
0x18017f0b1  cmp     [rsp+88h+var_48], 0
0x18017f0b6  jz      short loc_18017F0C2
0x18017f0b8  lea     rcx, [rsp+88h+var_68]; this
0x18017f0bd  call    ??1RegionId@SemanticPipelines@asg@@QEAA@XZ; asg::SemanticPipelines::RegionId::~RegionId(void)
0x18017f0c2  mov     rax, [rdi+10h]
0x18017f0c6  cmp     dword ptr [rax+0B0h], 0
0x18017f0cd  jnz     short loc_18017F0E3
0x18017f0cf  mov     byte ptr [rax+0B8h], 0
0x18017f0d6  mov     rcx, [rdi+10h]
0x18017f0da  add     rcx, 68h ; 'h'; _Cnd_t
0x18017f0de  call    _Cnd_broadcast
0x18017f0e3  lea     rcx, [rsi+18h]; _Mtx_t
0x18017f0e7  call    _Mtx_unlock
0x18017f0ec  nop
0x18017f0ed  mov     rbx, [rdi+8]
0x18017f0f1  test    rbx, rbx
0x18017f0f4  jz      short loc_18017F123
0x18017f0f6  mov     edi, 0FFFFFFFFh
0x18017f0fb  mov     eax, edi
0x18017f0fd  lock xadd [rbx+8], eax
0x18017f102  cmp     eax, 1
0x18017f105  jnz     short loc_18017F123
0x18017f107  mov     rax, [rbx]
0x18017f10a  mov     rcx, rbx
0x18017f10d  call    qword ptr [rax]
0x18017f10f  lock xadd [rbx+0Ch], edi
0x18017f114  cmp     edi, 1
0x18017f117  jnz     short loc_18017F123
0x18017f119  mov     rax, [rbx]
0x18017f11c  mov     rcx, rbx
0x18017f11f  call    qword ptr [rax+8]
0x18017f122  nop
0x18017f123  lea     r11, [rsp+88h+var_8]
0x18017f12b  mov     rbx, [r11+10h]
0x18017f12f  mov     rsi, [r11+18h]
0x18017f133  mov     rsp, r11
0x18017f136  pop     rdi
0x18017f137  retn
0x18017f138  mov     dword ptr [rsi+64h], 7FFFFFFEh
0x18017f13f  mov     ecx, 6; int
0x18017f144  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18017f14a  mov     ecx, 5; int
0x18017f14f  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
