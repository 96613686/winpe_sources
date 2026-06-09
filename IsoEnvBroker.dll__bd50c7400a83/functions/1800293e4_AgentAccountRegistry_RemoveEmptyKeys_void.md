# AgentAccountRegistry::RemoveEmptyKeys(void)

- ea: `0x1800293e4`
- end: `0x180029563`
- name: `?RemoveEmptyKeys@AgentAccountRegistry@@QEAAXXZ`
- size: `383`
- prototype: `void __fastcall(AgentAccountRegistry *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180023170`
- `0x180056060`

## callees

- `0x1800029cc`
- `0x1800075e4`
- `0x180011e18`
- `0x1800208d4`
- `0x1800293e4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800293fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800293fe`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180029446`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180029446`

## string_xrefs

- `0x18002954e`: `onecoreuap\windows\core\isoenvbroker\inc\checked_srwlock.h`
- `0x180029465`: `Failed to delete reg key for human user %s: %#x`

## pseudocode

```c
void __fastcall AgentAccountRegistry::RemoveEmptyKeys(AgentAccountRegistry *this)
{
  int v1; // ebx
  const char *v2; // r9
  __int64 v3; // rax
  _QWORD *v4; // rbx
  const WCHAR **v5; // rsi
  const WCHAR *v6; // rdx
  unsigned int v7; // eax
  const WCHAR *v8; // r8
  const WCHAR *v9; // r8
  unsigned __int64 v10; // rdx
  __int64 v11; // rcx
  unsigned __int64 v12; // r9
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rax
  _QWORD *v17; // rdi
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = dword_1800B9160;
  if ( v1 != GetCurrentThreadId() )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x15D,
      (int)"onecoreuap\\windows\\core\\isoenvbroker\\inc\\checked_srwlock.h",
      v2);
  v3 = qword_1800B9470;
  v4 = *(_QWORD **)qword_1800B9470;
  while ( v4 != (_QWORD *)v3 )
  {
    if ( *(_QWORD *)(v4[6] + 120LL) )
    {
      v4 = (_QWORD *)*v4;
    }
    else
    {
      v5 = (const WCHAR **)(v4 + 2);
      v6 = (const WCHAR *)(v4 + 2);
      if ( v4[5] > 7u )
        v6 = *v5;
      v7 = RegDeleteKeyW(g_agentAccountRegistry, v6);
      if ( (v7 & 0xFFFFFFFD) != 0 )
      {
        if ( v4[5] <= 7u )
          v8 = (const WCHAR *)(v4 + 2);
        else
          v8 = *v5;
        Log(2u, L"Failed to delete reg key for human user %s: %#x", v8, v7);
      }
      v9 = (const WCHAR *)(v4 + 2);
      if ( v4[5] > 7u )
        v9 = *v5;
      v10 = 0;
      v11 = 0xCBF29CE484222325uLL;
      v12 = 2LL * v4[4];
      if ( v12 )
      {
        do
        {
          v13 = *((unsigned __int8 *)v9 + v10++);
          v11 = 0x100000001B3LL * (v13 ^ v11);
        }
        while ( v10 < v12 );
      }
      v14 = xmmword_1800B9480;
      v15 = 2 * (qword_1800B9498 & v11);
      if ( *(_QWORD **)(xmmword_1800B9480 + 8 * v15 + 8) == v4 )
      {
        if ( *(_QWORD **)(xmmword_1800B9480 + 8 * v15) == v4 )
        {
          v16 = qword_1800B9470;
          *(_QWORD *)(xmmword_1800B9480 + 8 * v15) = qword_1800B9470;
        }
        else
        {
          v16 = v4[1];
        }
        *(_QWORD *)(v14 + 8 * v15 + 8) = v16;
      }
      else if ( *(_QWORD **)(xmmword_1800B9480 + 8 * v15) == v4 )
      {
        *(_QWORD *)(xmmword_1800B9480 + 8 * v15) = *v4;
      }
      v17 = (_QWORD *)*v4;
      --qword_1800B9478;
      *(_QWORD *)v4[1] = v17;
      v17[1] = v4[1];
      std::pair<std::wstring const,std::unique_ptr<OwningUserRegistry>>::~pair<std::wstring const,std::unique_ptr<OwningUserRegistry>>((__int64)(v4 + 2));
      operator delete(v4, (const struct std::nothrow_t *)0x38);
      v3 = qword_1800B9470;
      v4 = v17;
    }
  }
}

```

## disassembly

```asm
0x1800293e4  mov     [rsp+arg_0], rbx
0x1800293e9  mov     [rsp+arg_8], rsi
0x1800293ee  push    rdi
0x1800293ef  sub     rsp, 20h
0x1800293f3  mov     ebx, cs:dword_1800B9160
0x1800293f9  mov     rdi, [rsp+28h]
0x1800293fe  call    cs:__imp_GetCurrentThreadId
0x180029404  cmp     ebx, eax
0x180029406  jnz     loc_18002954E
0x18002940c  mov     rax, cs:qword_1800B9470
0x180029413  mov     rbx, [rax]
0x180029416  cmp     rbx, rax
0x180029419  jz      loc_18002953E
0x18002941f  mov     rcx, [rbx+30h]
0x180029423  cmp     qword ptr [rcx+78h], 0
0x180029428  jnz     loc_180029536
0x18002942e  lea     rsi, [rbx+10h]
0x180029432  cmp     qword ptr [rsi+18h], 7
0x180029437  mov     rdx, rsi
0x18002943a  jbe     short loc_18002943F
0x18002943c  mov     rdx, [rsi]; lpSubKey
0x18002943f  mov     rcx, cs:?g_agentAccountRegistry@@3VAgentAccountRegistry@@A; hKey
0x180029446  call    cs:__imp_RegDeleteKeyW
0x18002944c  test    eax, 0FFFFFFFDh
0x180029451  jz      short loc_180029476
0x180029453  cmp     qword ptr [rsi+18h], 7
0x180029458  jbe     short loc_18002945F
0x18002945a  mov     r8, [rsi]
0x18002945d  jmp     short loc_180029462
0x18002945f  mov     r8, rsi
0x180029462  mov     r9d, eax
0x180029465  lea     rdx, aFailedToDelete_2; "Failed to delete reg key for human user"...
0x18002946c  mov     ecx, 2; unsigned __int8
0x180029471  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180029476  cmp     qword ptr [rsi+18h], 7
0x18002947b  mov     r8, rsi
0x18002947e  mov     r9, [rsi+10h]
0x180029482  jbe     short loc_180029487
0x180029484  mov     r8, [rsi]
0x180029487  xor     edx, edx
0x180029489  mov     rcx, 0CBF29CE484222325h
0x180029493  add     r9, r9
0x180029496  jz      short loc_1800294B6
0x180029498  movzx   eax, byte ptr [r8+rdx]
0x18002949d  mov     r10, 100000001B3h
0x1800294a7  xor     rcx, rax
0x1800294aa  inc     rdx
0x1800294ad  imul    rcx, r10
0x1800294b1  cmp     rdx, r9
0x1800294b4  jb      short loc_180029498
0x1800294b6  and     rcx, cs:qword_1800B9498
0x1800294bd  mov     rdx, qword ptr cs:xmmword_1800B9480
0x1800294c4  add     rcx, rcx
0x1800294c7  cmp     [rdx+rcx*8+8], rbx
0x1800294cc  jnz     short loc_1800294EC
0x1800294ce  cmp     [rdx+rcx*8], rbx
0x1800294d2  jnz     short loc_1800294E1
0x1800294d4  mov     rax, cs:qword_1800B9470
0x1800294db  mov     [rdx+rcx*8], rax
0x1800294df  jmp     short loc_1800294E5
0x1800294e1  mov     rax, [rbx+8]
0x1800294e5  mov     [rdx+rcx*8+8], rax
0x1800294ea  jmp     short loc_1800294F9
0x1800294ec  cmp     [rdx+rcx*8], rbx
0x1800294f0  jnz     short loc_1800294F9
0x1800294f2  mov     rax, [rbx]
0x1800294f5  mov     [rdx+rcx*8], rax
0x1800294f9  mov     rdi, [rbx]
0x1800294fc  mov     rcx, rsi
0x1800294ff  dec     cs:qword_1800B9478
0x180029506  mov     rax, [rbx+8]
0x18002950a  mov     [rax], rdi
0x18002950d  mov     rax, [rbx+8]
0x180029511  mov     [rdi+8], rax
0x180029515  call    ??1?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@VOwningUserRegistry@@U?$default_delete@VOwningUserRegistry@@@std@@@2@@std@@QEAA@XZ; std::pair<std::wstring const,std::unique_ptr<OwningUserRegistry>>::~pair<std::wstring const,std::unique_ptr<OwningUserRegistry>>(void)
0x18002951a  mov     edx, 38h ; '8'; struct std::nothrow_t *
0x18002951f  mov     rcx, rbx; void *
0x180029522  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180029527  mov     rax, cs:qword_1800B9470
0x18002952e  mov     rbx, rdi
0x180029531  jmp     loc_180029416
0x180029536  mov     rbx, [rbx]
0x180029539  jmp     loc_180029416
0x18002953e  mov     rbx, [rsp+28h+arg_0]
0x180029543  mov     rsi, [rsp+28h+arg_8]
0x180029548  add     rsp, 20h
0x18002954c  pop     rdi
0x18002954d  retn
0x18002954e  lea     r8, aOnecoreuapWind_13; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180029555  mov     edx, 15Dh; void *
0x18002955a  mov     rcx, rdi; this
0x18002955d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
