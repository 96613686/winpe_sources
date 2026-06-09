# asg::Sqlite::DbTransaction::AcquireTransactionGuard

- ea: `0x18017f6c0`
- end: `0x18017f885`
- name: `asg::Sqlite::DbTransaction::AcquireTransactionGuard`
- size: `453`
- prototype: `__int64 __fastcall(asg::Sqlite::DbTransaction *this)`
- caller_count: `7`
- callee_count: `8`
- tags: ``

## callers

- `0x18017fa90`
- `0x18017ff20`
- `0x180180080`
- `0x180180bd0`
- `0x180180ee0`
- `0x180181140`
- `0x180181790`

## callees

- `0x1800040f0`
- `0x18001db40`
- `0x18017f6c0`
- `0x1801818c0`
- `0x1801d2ae0`
- `0x1801d2b20`
- `0x1801d2dc0`
- `0x1801f97e0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18017f71d`
- `KERNEL32!GetCurrentThreadId` at `0x18017f71d`

## string_xrefs

- `0x18017f845`: `Transaction owner thread ID is populated when it should be empty!`
- `0x18017f822`: `Read/Write DBTransaction is not safe to access from multiple threads!`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall asg::Sqlite::DbTransaction::AcquireTransactionGuard(asg::Sqlite::DbTransaction *this, _QWORD *a2)
{
  DWORD CurrentThreadId; // r14d
  char v5; // cl
  __int64 v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rax
  volatile signed __int32 *v9; // rbx
  _BYTE pExceptionObject[48]; // [rsp+38h] [rbp-30h] BYREF
  __int64 v12; // [rsp+70h] [rbp+8h]

  asg::IsFeatureEnabled<wil::Feature<__WilFeatureTraits_Feature_56532199>>();
  if ( Mtx_lock((asg::Sqlite::DbTransaction *)((char *)this + 24)) )
    std::_Throw_Cpp_error(5);
  if ( *((_DWORD *)this + 25) == 0x7FFFFFFF )
  {
    *((_DWORD *)this + 25) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  asg::Sqlite::DbTransaction::VerifyState(this);
  CurrentThreadId = GetCurrentThreadId();
  v5 = *((_BYTE *)this + 184);
  if ( *((_DWORD *)this + 44) )
  {
    if ( !v5 || *((_DWORD *)this + 45) != CurrentThreadId )
    {
      v6 = *((_QWORD *)this + 24);
      if ( v6 )
      {
        asg::IsFeatureEnabled<wil::Feature<__WilFeatureTraits_Feature_56532199>>();
        if ( !*(_BYTE *)(v6 + 256) )
        {
          std::logic_error::logic_error(
            (std::logic_error *)pExceptionObject,
            "Read/Write DBTransaction is not safe to access from multiple threads!");
          throw (std::logic_error *)pExceptionObject;
        }
      }
    }
  }
  else if ( v5 )
  {
    std::logic_error::logic_error(
      (std::logic_error *)pExceptionObject,
      "Transaction owner thread ID is populated when it should be empty!");
    throw (std::logic_error *)pExceptionObject;
  }
  LODWORD(v12) = CurrentThreadId;
  BYTE4(v12) = 1;
  *(_QWORD *)((char *)this + 180) = v12;
  ++*((_DWORD *)this + 44);
  v7 = *((_QWORD *)this + 25);
  if ( v7 )
    _InterlockedIncrement((volatile signed __int32 *)(v7 + 8));
  v8 = *((_QWORD *)this + 24);
  v9 = (volatile signed __int32 *)*((_QWORD *)this + 25);
  *a2 = 0;
  a2[1] = 0;
  if ( v9 )
  {
    _InterlockedIncrement(v9 + 2);
    *a2 = v8;
    a2[1] = v9;
    a2[2] = this;
    if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
      if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    }
  }
  else
  {
    *a2 = v8;
    a2[1] = 0;
    a2[2] = this;
  }
  Mtx_unlock((asg::Sqlite::DbTransaction *)((char *)this + 24));
  return a2;
}

```

## disassembly

```asm
0x18017f6c0  mov     [rsp+arg_8], rbx
0x18017f6c5  mov     [rsp+arg_10], rbp
0x18017f6ca  push    rsi
0x18017f6cb  push    rdi
0x18017f6cc  push    r14
0x18017f6ce  sub     rsp, 50h
0x18017f6d2  mov     rdi, rdx
0x18017f6d5  mov     rsi, rcx
0x18017f6d8  call    ??$IsFeatureEnabled@V?$Feature@U__WilFeatureTraits_Feature_56532199@@@wil@@@asg@@YA_NXZ; asg::IsFeatureEnabled<wil::Feature<__WilFeatureTraits_Feature_56532199>>(void)
0x18017f6dd  xorps   xmm0, xmm0
0x18017f6e0  movups  [rsp+68h+var_40], xmm0
0x18017f6e5  lea     rbp, [rsi+18h]
0x18017f6e9  mov     qword ptr [rsp+68h+var_40], rbp
0x18017f6ee  mov     byte ptr [rsp+68h+var_40+8], 0
0x18017f6f3  mov     rcx, rbp; _Mtx_t
0x18017f6f6  call    _Mtx_lock
0x18017f6fb  test    eax, eax
0x18017f6fd  jnz     loc_18017F868
0x18017f703  cmp     dword ptr [rbp+4Ch], 7FFFFFFFh
0x18017f70a  jz      loc_18017F873
0x18017f710  mov     byte ptr [rsp+68h+var_40+8], 1
0x18017f715  mov     rcx, rsi; this
0x18017f718  call    ?VerifyState@DbTransaction@Sqlite@asg@@AEBAXXZ; asg::Sqlite::DbTransaction::VerifyState(void)
0x18017f71d  call    cs:__imp_GetCurrentThreadId
0x18017f723  mov     r14d, eax
0x18017f726  movzx   ecx, byte ptr [rsi+0B8h]
0x18017f72d  cmp     dword ptr [rsi+0B0h], 0
0x18017f734  jnz     short loc_18017F740
0x18017f736  test    cl, cl
0x18017f738  jnz     loc_18017F845
0x18017f73e  jmp     short loc_18017F76B
0x18017f740  test    cl, cl
0x18017f742  jz      short loc_18017F74D
0x18017f744  cmp     [rsi+0B4h], r14d
0x18017f74b  jz      short loc_18017F76B
0x18017f74d  mov     rbx, [rsi+0C0h]
0x18017f754  test    rbx, rbx
0x18017f757  jz      short loc_18017F76B
0x18017f759  call    ??$IsFeatureEnabled@V?$Feature@U__WilFeatureTraits_Feature_56532199@@@wil@@@asg@@YA_NXZ; asg::IsFeatureEnabled<wil::Feature<__WilFeatureTraits_Feature_56532199>>(void)
0x18017f75e  cmp     byte ptr [rbx+100h], 0
0x18017f765  jz      loc_18017F822
0x18017f76b  mov     dword ptr [rsp+68h+arg_0], r14d
0x18017f770  mov     byte ptr [rsp+68h+arg_0+4], 1
0x18017f775  mov     rax, [rsp+68h+arg_0]
0x18017f77a  mov     [rsi+0B4h], rax
0x18017f781  inc     dword ptr [rsi+0B0h]
0x18017f787  mov     rax, [rsi+0C8h]
0x18017f78e  test    rax, rax
0x18017f791  jz      short loc_18017F797
0x18017f793  lock inc dword ptr [rax+8]
0x18017f797  mov     rax, [rsi+0C0h]
0x18017f79e  mov     rbx, [rsi+0C8h]
0x18017f7a5  mov     qword ptr [rdi], 0
0x18017f7ac  mov     qword ptr [rdi+8], 0
0x18017f7b4  test    rbx, rbx
0x18017f7b7  jz      short loc_18017F7F6
0x18017f7b9  lock inc dword ptr [rbx+8]
0x18017f7bd  mov     [rdi], rax
0x18017f7c0  mov     [rdi+8], rbx
0x18017f7c4  mov     [rdi+10h], rsi
0x18017f7c8  mov     esi, 0FFFFFFFFh
0x18017f7cd  mov     eax, esi
0x18017f7cf  lock xadd [rbx+8], eax
0x18017f7d4  cmp     eax, 1
0x18017f7d7  jnz     short loc_18017F801
0x18017f7d9  mov     rax, [rbx]
0x18017f7dc  mov     rcx, rbx
0x18017f7df  call    qword ptr [rax]
0x18017f7e1  lock xadd [rbx+0Ch], esi
0x18017f7e6  cmp     esi, 1
0x18017f7e9  jnz     short loc_18017F801
0x18017f7eb  mov     rax, [rbx]
0x18017f7ee  mov     rcx, rbx
0x18017f7f1  call    qword ptr [rax+8]
0x18017f7f4  jmp     short loc_18017F801
0x18017f7f6  mov     [rdi], rax
0x18017f7f9  mov     [rdi+8], rbx
0x18017f7fd  mov     [rdi+10h], rsi
0x18017f801  mov     rcx, rbp; _Mtx_t
0x18017f804  call    _Mtx_unlock
0x18017f809  mov     rax, rdi
0x18017f80c  mov     rbx, [rsp+68h+arg_8]
0x18017f811  mov     rbp, [rsp+68h+arg_10]
0x18017f819  add     rsp, 50h
0x18017f81d  pop     r14
0x18017f81f  pop     rdi
0x18017f820  pop     rsi
0x18017f821  retn
0x18017f822  lea     rdx, aReadWriteDbtra; "Read/Write DBTransaction is not safe to"...
0x18017f829  lea     rcx, [rsp+68h+pExceptionObject]; this
0x18017f82e  call    ??0logic_error@std@@QEAA@PEBD@Z; std::logic_error::logic_error(char const *)
0x18017f833  lea     rdx, _TI2?AVlogic_error@std@@; pThrowInfo
0x18017f83a  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18017f83f  call    _CxxThrowException
0x18017f845  lea     rdx, aTransactionOwn; "Transaction owner thread ID is populate"...
0x18017f84c  lea     rcx, [rsp+68h+pExceptionObject]; this
0x18017f851  call    ??0logic_error@std@@QEAA@PEBD@Z; std::logic_error::logic_error(char const *)
0x18017f856  lea     rdx, _TI2?AVlogic_error@std@@; pThrowInfo
0x18017f85d  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18017f862  call    _CxxThrowException
0x18017f868  mov     ecx, 5; int
0x18017f86d  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18017f873  mov     dword ptr [rbp+4Ch], 7FFFFFFEh
0x18017f87a  mov     ecx, 6; int
0x18017f87f  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
