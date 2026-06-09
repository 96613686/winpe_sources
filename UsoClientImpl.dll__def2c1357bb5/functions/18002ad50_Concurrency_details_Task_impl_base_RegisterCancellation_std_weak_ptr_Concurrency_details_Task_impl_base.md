# Concurrency::details::_Task_impl_base::_RegisterCancellation(std::weak_ptr<Concurrency::details::_Task_impl_base>)

- ea: `0x18002ad50`
- end: `0x18002b02e`
- name: `?_RegisterCancellation@_Task_impl_base@details@Concurrency@@QEAAXV?$weak_ptr@U_Task_impl_base@details@Concurrency@@@std@@@Z`
- size: `734`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002b034`

## callees

- `0x18002ad50`
- `0x180036d78`
- `0x180036ed8`
- `0x180056524`
- `0x18005c5e0`
- `0x18005c660`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002af0a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002af8d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002af0a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002af8d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002af1e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002af1e`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18002af97`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18002af97`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Concurrency::details::_Task_impl_base::_RegisterCancellation(__int64 a1, __int64 *a2)
{
  volatile signed __int32 *v4; // rsi
  __int64 v5; // rbx
  char *v6; // rdi
  __int64 v7; // rbp
  char v8; // r12
  char **v9; // rax
  bool v10; // zf
  DWORD CurrentThreadId; // ebx
  signed __int32 v12; // eax
  volatile signed __int32 *v13; // rcx

  v4 = (volatile signed __int32 *)a2[1];
  if ( v4 )
  {
    v5 = *a2;
    _InterlockedIncrement(v4 + 3);
  }
  else
  {
    v4 = 0;
    v5 = 0;
  }
  v6 = (char *)operator new(0xD0u);
  memset(v6, 0, 0xD0u);
  *(_QWORD *)v6 = &Concurrency::details::_RefCounter::`vftable';
  *((_DWORD *)v6 + 2) = 1;
  *((_DWORD *)v6 + 4) = 3;
  *((_QWORD *)v6 + 3) = 0;
  *((_QWORD *)v6 + 4) = 0;
  *(_OWORD *)(v6 + 40) = 0;
  *(_OWORD *)(v6 + 56) = 0;
  *(_OWORD *)(v6 + 72) = 0;
  *((_QWORD *)v6 + 11) = 0;
  *((_QWORD *)v6 + 12) = 2;
  *(_OWORD *)(v6 + 120) = 0;
  *(_OWORD *)(v6 + 136) = 0;
  *(_OWORD *)(v6 + 152) = 0;
  *(_OWORD *)(v6 + 104) = 0;
  *((_DWORD *)v6 + 42) = -1;
  *((_DWORD *)v6 + 43) = 0;
  v6[176] = 0;
  *((_QWORD *)v6 + 23) = 0;
  *(_QWORD *)v6 = &___7___CancellationTokenCallback_V_lambda_1___1___RegisterCancellation__Task_impl_base_details_Concurrency__QEAAXV__weak_ptr_U_Task_impl_base_details_Concurrency___std___Z__details_Concurrency__6B_;
  *((_QWORD *)v6 + 24) = 0;
  *((_QWORD *)v6 + 25) = 0;
  if ( v4 )
  {
    *((_QWORD *)v6 + 24) = v5;
    *((_QWORD *)v6 + 25) = v4;
    _InterlockedIncrement(v4 + 3);
  }
  *(_QWORD *)(a1 + 128) = v6;
  v7 = *(_QWORD *)(a1 + 120);
  _InterlockedExchange((volatile __int32 *)v6 + 4, 0);
  _InterlockedIncrement((volatile signed __int32 *)v6 + 2);
  *((_QWORD *)v6 + 23) = v7;
  v8 = 1;
  if ( *(_DWORD *)(v7 + 16) )
    goto LABEL_18;
  if ( (unsigned int)mtx_do_lock(v7 + 24) )
    goto LABEL_38;
  if ( *(_DWORD *)(v7 + 100) == 0x7FFFFFFF )
  {
    *(_DWORD *)(v7 + 100) = 2147483646;
    goto LABEL_37;
  }
  if ( !*(_DWORD *)(v7 + 16) )
  {
    v8 = 0;
    v9 = (char **)operator new(0x10u);
    *v9 = v6;
    v9[1] = 0;
    if ( *(_QWORD *)(v7 + 104) )
      *(_QWORD *)(*(_QWORD *)(v7 + 112) + 8LL) = v9;
    else
      *(_QWORD *)(v7 + 104) = v9;
    *(_QWORD *)(v7 + 112) = v9;
  }
  v10 = (*(_DWORD *)(v7 + 100))-- == 1;
  if ( v10 )
  {
    *(_DWORD *)(v7 + 96) = -1;
    ReleaseSRWLockExclusive((PSRWLOCK)(v7 + 40));
  }
  if ( v8 )
  {
LABEL_18:
    CurrentThreadId = GetCurrentThreadId();
    if ( _InterlockedCompareExchange((volatile signed __int32 *)v6 + 4, CurrentThreadId, 0) )
      goto LABEL_27;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6);
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)v6 + 4, 3, CurrentThreadId);
    if ( CurrentThreadId != v12 )
      CurrentThreadId = v12;
    if ( CurrentThreadId != 2 )
    {
LABEL_27:
      if ( !_InterlockedDecrement((volatile signed __int32 *)v6 + 2) )
        (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))(v6);
      goto LABEL_29;
    }
    if ( !(unsigned int)mtx_do_lock(v6 + 96) )
    {
      if ( *((_DWORD *)v6 + 43) == 0x7FFFFFFF )
      {
        *((_DWORD *)v6 + 43) = 2147483646;
LABEL_37:
        std::_Throw_Cpp_error(6);
      }
      v6[176] = 1;
      v10 = (*((_DWORD *)v6 + 43))-- == 1;
      if ( v10 )
      {
        *((_DWORD *)v6 + 42) = -1;
        ReleaseSRWLockExclusive((PSRWLOCK)v6 + 14);
      }
      WakeAllConditionVariable((PCONDITION_VARIABLE)v6 + 4);
      goto LABEL_27;
    }
LABEL_38:
    std::_Throw_Cpp_error(5);
  }
LABEL_29:
  if ( v4 && !_InterlockedDecrement(v4 + 3) )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
  v13 = (volatile signed __int32 *)a2[1];
  if ( v13 )
  {
    if ( !_InterlockedDecrement(v13 + 3) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
  }
}

```

## disassembly

```asm
0x18002ad50  mov     rax, rsp
0x18002ad53  mov     [rax+18h], rbx
0x18002ad57  push    rbp
0x18002ad58  push    rsi
0x18002ad59  push    rdi
0x18002ad5a  push    r12
0x18002ad5c  push    r13
0x18002ad5e  push    r14
0x18002ad60  push    r15
0x18002ad62  sub     rsp, 40h
0x18002ad66  mov     r15, rdx
0x18002ad69  mov     rbp, rcx
0x18002ad6c  mov     [rax-40h], rdx
0x18002ad70  xorps   xmm1, xmm1
0x18002ad73  movdqu  xmmword ptr [rax-50h], xmm1
0x18002ad78  mov     rsi, [rdx+8]
0x18002ad7c  xor     r12d, r12d
0x18002ad7f  test    rsi, rsi
0x18002ad82  jz      short loc_18002AD95
0x18002ad84  mov     rbx, [rdx]
0x18002ad87  mov     [rax-50h], rbx
0x18002ad8b  mov     [rax-48h], rsi
0x18002ad8f  lock inc dword ptr [rsi+0Ch]
0x18002ad93  jmp     short loc_18002AD9F
0x18002ad95  mov     rsi, [rsp+78h+var_48]
0x18002ad9a  mov     rbx, [rsp+78h+var_50]
0x18002ad9f  mov     r14d, 0D0h
0x18002ada5  mov     ecx, r14d; Size
0x18002ada8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002adad  mov     rdi, rax
0x18002adb0  mov     [rsp+78h+var_58], rax
0x18002adb5  mov     r8d, r14d; Size
0x18002adb8  xor     edx, edx; Val
0x18002adba  mov     rcx, rax; void *
0x18002adbd  call    memset
0x18002adc2  lea     rax, ??_7_RefCounter@details@Concurrency@@6B@; const Concurrency::details::_RefCounter::`vftable'
0x18002adc9  mov     [rdi], rax
0x18002adcc  mov     dword ptr [rdi+8], 1
0x18002add3  mov     dword ptr [rdi+10h], 3
0x18002adda  mov     [rdi+18h], r12
0x18002adde  mov     [rdi+20h], r12
0x18002ade2  xorps   xmm0, xmm0
0x18002ade5  xor     eax, eax
0x18002ade7  movups  xmmword ptr [rdi+28h], xmm0
0x18002adeb  movups  xmmword ptr [rdi+38h], xmm0
0x18002adef  movups  xmmword ptr [rdi+48h], xmm0
0x18002adf3  mov     [rdi+58h], rax
0x18002adf7  mov     qword ptr [rdi+60h], 2
0x18002adff  movups  xmmword ptr [rdi+78h], xmm0
0x18002ae03  movups  xmmword ptr [rdi+88h], xmm0
0x18002ae0a  movups  xmmword ptr [rdi+98h], xmm0
0x18002ae11  movdqu  xmmword ptr [rdi+68h], xmm0
0x18002ae16  mov     dword ptr [rdi+0A8h], 0FFFFFFFFh
0x18002ae20  mov     [rdi+0ACh], r12d
0x18002ae27  mov     [rdi+0B0h], r12b
0x18002ae2e  mov     [rdi+0B8h], r12
0x18002ae35  lea     rax, ??_7?$_CancellationTokenCallback@V_lambda_1_@?1??_RegisterCancellation@_Task_impl_base@details@Concurrency@@QEAAXV?$weak_ptr@U_Task_impl_base@details@Concurrency@@@std@@@Z@@details@Concurrency@@6B@; const Concurrency::details::_CancellationTokenCallback<`Concurrency::details::_Task_impl_base::_RegisterCancellation(std::weak_ptr<Concurrency::details::_Task_impl_base>)'::`2'::_lambda_1_>::`vftable'
0x18002ae3c  mov     [rdi], rax
0x18002ae3f  mov     [rdi+0C0h], r12
0x18002ae46  mov     [rdi+0C8h], r12
0x18002ae4d  test    rsi, rsi
0x18002ae50  jz      short loc_18002AE64
0x18002ae52  mov     [rdi+0C0h], rbx
0x18002ae59  mov     [rdi+0C8h], rsi
0x18002ae60  lock inc dword ptr [rsi+0Ch]
0x18002ae64  mov     [rbp+80h], rdi
0x18002ae6b  mov     rbp, [rbp+78h]
0x18002ae6f  mov     eax, r12d
0x18002ae72  xchg    eax, [rdi+10h]
0x18002ae75  lock inc dword ptr [rdi+8]
0x18002ae79  mov     [rdi+0B8h], rbp
0x18002ae80  mov     r12b, 1
0x18002ae83  mov     eax, [rbp+10h]
0x18002ae86  nop
0x18002ae87  test    eax, eax
0x18002ae89  jnz     loc_18002AF1B
0x18002ae8f  lea     rbx, [rbp+18h]
0x18002ae93  mov     [rsp+78h+var_58], rbx
0x18002ae98  mov     rcx, rbx
0x18002ae9b  call    mtx_do_lock
0x18002aea0  test    eax, eax
0x18002aea2  jnz     loc_18002B023
0x18002aea8  mov     eax, [rbx+4Ch]
0x18002aeab  cmp     eax, 7FFFFFFFh
0x18002aeb0  jnz     short loc_18002AEBC
0x18002aeb2  dec     eax
0x18002aeb4  mov     [rbx+4Ch], eax
0x18002aeb7  jmp     loc_18002B018
0x18002aebc  mov     eax, [rbp+10h]
0x18002aebf  nop
0x18002aec0  test    eax, eax
0x18002aec2  jnz     short loc_18002AEFB
0x18002aec4  xor     r12b, r12b
0x18002aec7  lea     ecx, [rax+10h]; Size
0x18002aeca  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002aecf  mov     rcx, rax
0x18002aed2  mov     [rsp+78h+var_58], rax
0x18002aed7  mov     [rax], rdi
0x18002aeda  mov     qword ptr [rax+8], 0
0x18002aee2  cmp     qword ptr [rbp+68h], 0
0x18002aee7  jnz     short loc_18002AEEF
0x18002aee9  mov     [rbp+68h], rax
0x18002aeed  jmp     short loc_18002AEF7
0x18002aeef  mov     rax, [rbp+70h]
0x18002aef3  mov     [rax+8], rcx
0x18002aef7  mov     [rbp+70h], rcx
0x18002aefb  or      ebp, 0FFFFFFFFh
0x18002aefe  add     [rbx+4Ch], ebp
0x18002af01  jnz     short loc_18002AF10
0x18002af03  mov     [rbx+48h], ebp
0x18002af06  lea     rcx, [rbx+10h]; SRWLock
0x18002af0a  call    cs:__imp_ReleaseSRWLockExclusive
0x18002af10  test    r12b, r12b
0x18002af13  jz      loc_18002AFB8
0x18002af19  jmp     short loc_18002AF1E
0x18002af1b  or      ebp, 0FFFFFFFFh
0x18002af1e  call    cs:__imp_GetCurrentThreadId
0x18002af24  mov     ebx, eax
0x18002af26  xor     eax, eax
0x18002af28  lock cmpxchg [rdi+10h], ebx
0x18002af2d  jnz     short loc_18002AF9D
0x18002af2f  mov     rcx, [rdi]
0x18002af32  mov     rax, [rcx+10h]
0x18002af36  mov     rcx, rdi
0x18002af39  call    _guard_dispatch_icall
0x18002af3e  mov     eax, ebx
0x18002af40  mov     ecx, 3
0x18002af45  lock cmpxchg [rdi+10h], ecx
0x18002af4a  cmovnz  ebx, eax
0x18002af4d  cmp     ebx, 2
0x18002af50  jnz     short loc_18002AF9D
0x18002af52  lea     rcx, [rdi+60h]
0x18002af56  call    mtx_do_lock
0x18002af5b  test    eax, eax
0x18002af5d  jnz     loc_18002B023
0x18002af63  mov     eax, [rdi+0ACh]
0x18002af69  cmp     eax, 7FFFFFFFh
0x18002af6e  jz      loc_18002B010
0x18002af74  mov     byte ptr [rdi+0B0h], 1
0x18002af7b  add     [rdi+0ACh], ebp
0x18002af81  jnz     short loc_18002AF93
0x18002af83  mov     [rdi+0A8h], ebp
0x18002af89  lea     rcx, [rdi+70h]; SRWLock
0x18002af8d  call    cs:__imp_ReleaseSRWLockExclusive
0x18002af93  lea     rcx, [rdi+20h]; ConditionVariable
0x18002af97  call    cs:__imp_WakeAllConditionVariable
0x18002af9d  mov     eax, ebp
0x18002af9f  lock xadd [rdi+8], eax
0x18002afa4  add     eax, ebp
0x18002afa6  jnz     short loc_18002AFB8
0x18002afa8  mov     rax, [rdi]
0x18002afab  mov     rcx, rdi
0x18002afae  mov     rax, [rax+8]
0x18002afb2  call    _guard_dispatch_icall
0x18002afb7  nop
0x18002afb8  test    rsi, rsi
0x18002afbb  jz      short loc_18002AFD8
0x18002afbd  mov     eax, ebp
0x18002afbf  lock xadd [rsi+0Ch], eax
0x18002afc4  add     eax, ebp
0x18002afc6  jnz     short loc_18002AFD8
0x18002afc8  mov     rax, [rsi]
0x18002afcb  mov     rcx, rsi
0x18002afce  mov     rax, [rax+8]
0x18002afd2  call    _guard_dispatch_icall
0x18002afd7  nop
0x18002afd8  mov     rcx, [r15+8]
0x18002afdc  test    rcx, rcx
0x18002afdf  jz      short loc_18002AFF8
0x18002afe1  mov     eax, ebp
0x18002afe3  lock xadd [rcx+0Ch], eax
0x18002afe8  add     eax, ebp
0x18002afea  jnz     short loc_18002AFF8
0x18002afec  mov     rax, [rcx]
0x18002afef  mov     rax, [rax+8]
0x18002aff3  call    _guard_dispatch_icall
0x18002aff8  mov     rbx, [rsp+78h+arg_10]
0x18002b000  add     rsp, 40h
0x18002b004  pop     r15
0x18002b006  pop     r14
0x18002b008  pop     r13
0x18002b00a  pop     r12
0x18002b00c  pop     rdi
0x18002b00d  pop     rsi
0x18002b00e  pop     rbp
0x18002b00f  retn
0x18002b010  dec     eax
0x18002b012  mov     [rdi+0ACh], eax
0x18002b018  mov     ecx, 6; int
0x18002b01d  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18002b023  mov     ecx, 5; int
0x18002b028  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
