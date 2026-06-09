# win_musl::FiberThread::ThreadProc(win_mp_lib::null_type)

- ea: `0x18004f730`
- end: `0x18004f8cc`
- name: `?ThreadProc@FiberThread@win_musl@@AEAAXVnull_type@win_mp_lib@@@Z`
- size: `412`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800016b0`
- `0x18004f730`
- `0x18004f8d4`
- `0x18004f8f0`
- `0x18007a324`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f8b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f8b4`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18004f74f`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18004f74f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18004f7c4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18004f7c4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004f778`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004f861`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004f778`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004f861`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004f797`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004f797`
- `api-ms-win-core-fibers-l2-1-0!SwitchToFiber` at `0x18004f7fa`
- `api-ms-win-core-fibers-l2-1-0!SwitchToFiber` at `0x18004f7fa`
- `api-ms-win-core-fibers-l2-1-0!ConvertThreadToFiber` at `0x18004f761`
- `api-ms-win-core-fibers-l2-1-0!ConvertThreadToFiber` at `0x18004f761`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall win_musl::FiberThread::ThreadProc(__int64 a1)
{
  HRESULT v2; // eax
  int v3; // edi
  LPVOID v4; // rax
  win_musl::CriticalSection *v5; // rbx
  __int64 v6; // r14
  win_musl::FiberBase *v7; // rbx
  __m128i v8; // xmm6
  unsigned __int64 v9; // xmm0_8
  DWORD LastError; // eax
  __m128i v11; // [rsp+30h] [rbp-48h] BYREF

  v2 = CoInitializeEx(0, 0);
  v3 = -2147221008;
  if ( v2 != -2147221008 )
    v3 = v2;
  v4 = ConvertThreadToFiber(0);
  *(_QWORD *)(a1 + 16) = v4;
  if ( !v4 )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1;
    *(_DWORD *)(a1 + 24) = LastError;
  }
  SetEvent(*(HANDLE *)(a1 + 72));
  while ( 1 )
  {
    WaitForSingleObject(*(HANDLE *)(a1 + 88), 0xFFFFFFFF);
    v5 = (win_musl::CriticalSection *)(*(_QWORD *)(a1 + 8) + 16LL);
    win_musl::CriticalSection::Enter(v5);
    if ( *(_BYTE *)(a1 + 28) )
      break;
    if ( v5 )
      win_musl::CriticalSection::Leave(v5);
    v6 = *(_QWORD *)(a1 + 32);
    *(_QWORD *)(a1 + 32) = 0;
    *(_QWORD *)(v6 + 64) = a1;
    SwitchToFiber(*(LPVOID *)(v6 + 32));
    v7 = *(win_musl::FiberBase **)(a1 + 40);
    if ( v7 && dword_1801C4F30 != -1 )
    {
      *(_QWORD *)(a1 + 40) = 0;
      win_musl::FiberBase::ClearFiberState(v7);
      (*(void (__fastcall **)(win_musl::FiberBase *))(*(_QWORD *)v7 + 16LL))(v7);
    }
    if ( *(_QWORD *)(a1 + 48) )
    {
      if ( *(_QWORD *)(a1 + 56) )
      {
        if ( dword_1801C4F30 != -1 )
        {
          v8 = *(__m128i *)(a1 + 48);
          *(_QWORD *)(a1 + 48) = 0;
          *(_QWORD *)(a1 + 56) = 0;
          v11 = v8;
          v9 = _mm_srli_si128(v8, 8).m128i_u64[0];
          SetEvent(*(HANDLE *)(v9 + 16));
          if ( v8.m128i_i64[0] )
          {
            if ( v9 )
              win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v11);
          }
        }
      }
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  if ( v5 )
    win_musl::CriticalSection::Leave(v5);
  if ( v3 >= 0 )
    CoUninitialize();
}

```

## disassembly

```asm
0x18004f730  push    rbx
0x18004f732  push    rsi
0x18004f733  push    rdi
0x18004f734  push    r14
0x18004f736  sub     rsp, 58h
0x18004f73a  mov     [rsp+78h+var_58], 0FFFFFFFFFFFFFFFEh
0x18004f743  movaps  [rsp+78h+var_38], xmm6
0x18004f748  mov     rsi, rcx
0x18004f74b  xor     edx, edx; dwCoInit
0x18004f74d  xor     ecx, ecx; pvReserved
0x18004f74f  call    cs:__imp_CoInitializeEx
0x18004f755  mov     edi, 800401F0h
0x18004f75a  cmp     eax, edi
0x18004f75c  cmovnz  edi, eax
0x18004f75f  xor     ecx, ecx; lpParameter
0x18004f761  call    cs:__imp_ConvertThreadToFiber
0x18004f767  mov     [rsi+10h], rax
0x18004f76b  test    rax, rax
0x18004f76e  jz      loc_18004F8B4
0x18004f774  mov     rcx, [rsi+48h]; hEvent
0x18004f778  call    cs:__imp_SetEvent
0x18004f77e  jmp     short loc_18004F790
0x18004f780  mov     rax, [r14]
0x18004f783  mov     rcx, r14
0x18004f786  mov     rax, [rax+10h]
0x18004f78a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f78f  nop
0x18004f790  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18004f793  mov     rcx, [rsi+58h]; hHandle
0x18004f797  call    cs:__imp_WaitForSingleObject
0x18004f79d  mov     rbx, [rsi+8]
0x18004f7a1  add     rbx, 10h
0x18004f7a5  mov     rcx, rbx; this
0x18004f7a8  call    ?Enter@CriticalSection@win_musl@@QEAAXXZ; win_musl::CriticalSection::Enter(void)
0x18004f7ad  cmp     byte ptr [rsi+1Ch], 0
0x18004f7b1  jz      short loc_18004F7D9
0x18004f7b3  test    rbx, rbx
0x18004f7b6  jz      short loc_18004F7C0
0x18004f7b8  mov     rcx, rbx; this
0x18004f7bb  call    ?Leave@CriticalSection@win_musl@@QEAAXXZ; win_musl::CriticalSection::Leave(void)
0x18004f7c0  test    edi, edi
0x18004f7c2  js      short loc_18004F7CA
0x18004f7c4  call    cs:__imp_CoUninitialize
0x18004f7ca  movaps  xmm6, [rsp+78h+var_38]
0x18004f7cf  add     rsp, 58h
0x18004f7d3  pop     r14
0x18004f7d5  pop     rdi
0x18004f7d6  pop     rsi
0x18004f7d7  pop     rbx
0x18004f7d8  retn
0x18004f7d9  test    rbx, rbx
0x18004f7dc  jz      short loc_18004F7E6
0x18004f7de  mov     rcx, rbx; this
0x18004f7e1  call    ?Leave@CriticalSection@win_musl@@QEAAXXZ; win_musl::CriticalSection::Leave(void)
0x18004f7e6  mov     r14, [rsi+20h]
0x18004f7ea  mov     qword ptr [rsi+20h], 0
0x18004f7f2  mov     [r14+40h], rsi
0x18004f7f6  mov     rcx, [r14+20h]; lpFiber
0x18004f7fa  call    cs:__imp_SwitchToFiber
0x18004f800  mov     rbx, [rsi+28h]
0x18004f804  test    rbx, rbx
0x18004f807  jz      short loc_18004F812
0x18004f809  cmp     cs:dword_1801C4F30, 0FFFFFFFFh
0x18004f810  jnz     short loc_18004F88E
0x18004f812  cmp     qword ptr [rsi+30h], 0
0x18004f817  jz      loc_18004F780
0x18004f81d  cmp     qword ptr [rsi+38h], 0
0x18004f822  jz      loc_18004F780
0x18004f828  cmp     cs:dword_1801C4F30, 0FFFFFFFFh
0x18004f82f  jz      loc_18004F780
0x18004f835  movups  xmm6, xmmword ptr [rsi+30h]
0x18004f839  mov     qword ptr [rsi+30h], 0
0x18004f841  mov     qword ptr [rsi+38h], 0
0x18004f849  movdqa  [rsp+78h+var_48], xmm6
0x18004f84f  movdqa  xmm0, xmm6
0x18004f853  psrldq  xmm0, 8
0x18004f858  movq    rbx, xmm0
0x18004f85d  mov     rcx, [rbx+10h]; hEvent
0x18004f861  call    cs:__imp_SetEvent
0x18004f867  nop
0x18004f868  movq    rax, xmm6
0x18004f86d  test    rax, rax
0x18004f870  jz      loc_18004F780
0x18004f876  test    rbx, rbx
0x18004f879  jz      loc_18004F780
0x18004f87f  lea     rcx, [rsp+78h+var_48]
0x18004f884  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x18004f889  jmp     loc_18004F780
0x18004f88e  mov     qword ptr [rsi+28h], 0
0x18004f896  mov     rcx, rbx; this
0x18004f899  call    ?ClearFiberState@FiberBase@win_musl@@IEAAXXZ; win_musl::FiberBase::ClearFiberState(void)
0x18004f89e  nop
0x18004f89f  mov     rax, [rbx]
0x18004f8a2  mov     rcx, rbx
0x18004f8a5  mov     rax, [rax+10h]
0x18004f8a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f8ae  nop
0x18004f8af  jmp     loc_18004F812
0x18004f8b4  call    cs:__imp_GetLastError
0x18004f8ba  mov     ecx, 1
0x18004f8bf  test    eax, eax
0x18004f8c1  cmovz   eax, ecx
0x18004f8c4  mov     [rsi+18h], eax
0x18004f8c7  jmp     loc_18004F774
```
