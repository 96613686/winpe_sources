# tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)

- ea: `0x1400190b8`
- end: `0x1400191b7`
- name: `?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `255`
- prototype: `void __fastcall(__int64, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x140008ecc`
- `0x140010be0`

## callees

- `0x140003620`
- `0x1400190b8`
- `0x140019650`
- `0x14001c3a4`
- `0x14001f010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140019129`
- `KERNEL32!GetProcAddress` at `0x140019129`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140019194`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140019194`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,0>::complete_helper(__int64 a1, unsigned int a2)
{
  bool v2; // zf
  unsigned int v3; // edi
  FARPROC ProcAddress; // rax
  unsigned int v6; // esi
  __int64 v7; // rbp
  HMODULE KernelBaseModuleHandle; // rax
  int v9; // edx
  __int128 v10; // [rsp+30h] [rbp-58h] BYREF
  LPVOID pv[2]; // [rsp+40h] [rbp-48h]
  __int128 v12; // [rsp+50h] [rbp-38h]

  v2 = *(_DWORD *)(a1 + 232) == 0;
  v10 = 0;
  v3 = a2;
  *(_OWORD *)pv = 0;
  v12 = 0;
  if ( !v2 )
    v3 = a2 | 8;
  ProcAddress = (FARPROC)`TestQueryData'::`2'::s_pfnTestQueryData;
  v6 = *(_DWORD *)(a1 + 184);
  v7 = *(_QWORD *)(a1 + 240);
  *(_QWORD *)(a1 + 240) = 0;
  if ( ProcAddress
    || (KernelBaseModuleHandle = (HMODULE)tip_details_GetKernelBaseModuleHandle(),
        ProcAddress = GetProcAddress(KernelBaseModuleHandle, "TestQueryData"),
        (`TestQueryData'::`2'::s_pfnTestQueryData = (__int64)ProcAddress) != 0) )
  {
    if ( ((unsigned int (__fastcall *)(__int64, _QWORD, _QWORD, __int128 *))ProcAddress)(v7, v3, v6, &v10) )
    {
      v9 = (int)pv[0];
      *(_DWORD *)(a1 + 64) |= HIDWORD(pv[0]);
      if ( !pv[1] )
        *(_DWORD *)(a1 + 184) = v9;
      tip2::details::shared_data<0,0,0>::evaluate_and_report(a1, v12);
    }
  }
  else
  {
    v10 = 0;
    *(_OWORD *)pv = 0;
    v12 = 0;
  }
  CoTaskMemFree(pv[1]);
}

```

## disassembly

```asm
0x1400190b8  mov     [rsp+arg_10], rbx
0x1400190bd  push    rbp
0x1400190be  push    rsi
0x1400190bf  push    rdi
0x1400190c0  sub     rsp, 70h
0x1400190c4  mov     rax, cs:__security_cookie
0x1400190cb  xor     rax, rsp
0x1400190ce  mov     [rsp+88h+var_28], rax
0x1400190d3  cmp     dword ptr [rcx+0E8h], 0
0x1400190da  xorps   xmm0, xmm0
0x1400190dd  movups  [rsp+88h+var_58], xmm0
0x1400190e2  mov     edi, edx
0x1400190e4  mov     rbx, rcx
0x1400190e7  movups  xmmword ptr [rsp+88h+pv], xmm0
0x1400190ec  movups  [rsp+88h+var_38], xmm0
0x1400190f1  jbe     short loc_1400190F6
0x1400190f3  or      edi, 8
0x1400190f6  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x1400190fd  mov     esi, [rcx+0B8h]
0x140019103  mov     rbp, [rcx+0F0h]
0x14001910a  mov     qword ptr [rcx+0F0h], 0
0x140019115  test    rax, rax
0x140019118  jnz     short loc_14001914F
0x14001911a  call    tip_details_GetKernelBaseModuleHandle
0x14001911f  mov     rcx, rax; hModule
0x140019122  lea     rdx, aTestquerydata; "TestQueryData"
0x140019129  call    cs:__imp_GetProcAddress
0x14001912f  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x140019136  test    rax, rax
0x140019139  jnz     short loc_14001914F
0x14001913b  xorps   xmm0, xmm0
0x14001913e  movups  [rsp+88h+var_58], xmm0
0x140019143  movups  xmmword ptr [rsp+88h+pv], xmm0
0x140019148  movups  [rsp+88h+var_38], xmm0
0x14001914d  jmp     short loc_14001918F
0x14001914f  lea     r9, [rsp+88h+var_58]
0x140019154  mov     r8d, esi
0x140019157  mov     edx, edi
0x140019159  mov     rcx, rbp
0x14001915c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019161  test    eax, eax
0x140019163  jz      short loc_14001918F
0x140019165  mov     rdx, [rsp+88h+pv]
0x14001916a  mov     rax, rdx
0x14001916d  shr     rax, 20h
0x140019171  or      [rbx+40h], eax
0x140019174  cmp     [rsp+88h+pv+8], 0
0x14001917a  jnz     short loc_140019182
0x14001917c  mov     [rbx+0B8h], edx
0x140019182  mov     rdx, qword ptr [rsp+88h+var_38]
0x140019187  mov     rcx, rbx
0x14001918a  call    ?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)
0x14001918f  mov     rcx, [rsp+88h+pv+8]; pv
0x140019194  call    cs:__imp_CoTaskMemFree
0x14001919a  mov     rcx, [rsp+88h+var_28]
0x14001919f  xor     rcx, rsp; StackCookie
0x1400191a2  call    __security_check_cookie
0x1400191a7  mov     rbx, [rsp+88h+arg_10]
0x1400191af  add     rsp, 70h
0x1400191b3  pop     rdi
0x1400191b4  pop     rsi
0x1400191b5  pop     rbp
0x1400191b6  retn
```
