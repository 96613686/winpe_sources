# tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)

- ea: `0x14002afd0`
- end: `0x14002b0d0`
- name: `?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `256`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x14002bd04`
- `0x140033858`

## callees

- `0x140005f30`
- `0x14002afd0`
- `0x14002b5b8`
- `0x14002e090`
- `0x14007d010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14002b041`
- `KERNEL32!GetProcAddress` at `0x14002b041`
- `ole32!CoTaskMemFree` at `0x14002b0ac`
- `ole32!CoTaskMemFree` at `0x14002b0ac`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,0>::complete_helper(__int64 a1, unsigned int a2)
{
  unsigned int v2; // edi
  unsigned int v4; // esi
  __int64 v5; // rbp
  FARPROC ProcAddress; // rax
  HMODULE KernelBaseModuleHandle; // rax
  int v8; // edx
  __int128 v9; // [rsp+30h] [rbp-58h] BYREF
  LPVOID pv[2]; // [rsp+40h] [rbp-48h]
  __int128 v11; // [rsp+50h] [rbp-38h]

  v2 = a2;
  v9 = 0;
  *(_OWORD *)pv = 0;
  v11 = 0;
  if ( *(_DWORD *)(a1 + 232) )
    v2 = a2 | 8;
  v4 = *(_DWORD *)(a1 + 184);
  v5 = *(_QWORD *)(a1 + 240);
  *(_QWORD *)(a1 + 240) = 0;
  ProcAddress = (FARPROC)`TestQueryData'::`2'::s_pfnTestQueryData;
  if ( `TestQueryData'::`2'::s_pfnTestQueryData
    || (KernelBaseModuleHandle = (HMODULE)tip_details_GetKernelBaseModuleHandle(),
        ProcAddress = GetProcAddress(KernelBaseModuleHandle, "TestQueryData"),
        (`TestQueryData'::`2'::s_pfnTestQueryData = (__int64)ProcAddress) != 0) )
  {
    if ( ((unsigned int (__fastcall *)(__int64, _QWORD, _QWORD, __int128 *))ProcAddress)(v5, v2, v4, &v9) )
    {
      v8 = (int)pv[0];
      *(_DWORD *)(a1 + 64) |= HIDWORD(pv[0]);
      if ( !pv[1] )
        *(_DWORD *)(a1 + 184) = v8;
      tip2::details::shared_data<0,0,0>::evaluate_and_report(a1, v11);
    }
  }
  else
  {
    v9 = 0;
    *(_OWORD *)pv = 0;
    v11 = 0;
  }
  CoTaskMemFree(pv[1]);
}

```

## disassembly

```asm
0x14002afd0  mov     [rsp+arg_10], rbx
0x14002afd5  push    rbp
0x14002afd6  push    rsi
0x14002afd7  push    rdi
0x14002afd8  sub     rsp, 70h
0x14002afdc  mov     rax, cs:__security_cookie
0x14002afe3  xor     rax, rsp
0x14002afe6  mov     [rsp+88h+var_28], rax
0x14002afeb  mov     edi, edx
0x14002afed  mov     rbx, rcx
0x14002aff0  xorps   xmm0, xmm0
0x14002aff3  movups  [rsp+88h+var_58], xmm0
0x14002aff8  movups  xmmword ptr [rsp+88h+pv], xmm0
0x14002affd  movups  [rsp+88h+var_38], xmm0
0x14002b002  cmp     dword ptr [rcx+0E8h], 0
0x14002b009  jbe     short loc_14002B00E
0x14002b00b  or      edi, 8
0x14002b00e  mov     esi, [rcx+0B8h]
0x14002b014  mov     rbp, [rcx+0F0h]
0x14002b01b  mov     qword ptr [rcx+0F0h], 0
0x14002b026  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x14002b02d  test    rax, rax
0x14002b030  jnz     short loc_14002B067
0x14002b032  call    tip_details_GetKernelBaseModuleHandle
0x14002b037  mov     rcx, rax; hModule
0x14002b03a  lea     rdx, aTestquerydata; "TestQueryData"
0x14002b041  call    cs:__imp_GetProcAddress
0x14002b047  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x14002b04e  test    rax, rax
0x14002b051  jnz     short loc_14002B067
0x14002b053  xorps   xmm0, xmm0
0x14002b056  movups  [rsp+88h+var_58], xmm0
0x14002b05b  movups  xmmword ptr [rsp+88h+pv], xmm0
0x14002b060  movups  [rsp+88h+var_38], xmm0
0x14002b065  jmp     short loc_14002B0A7
0x14002b067  lea     r9, [rsp+88h+var_58]
0x14002b06c  mov     r8d, esi
0x14002b06f  mov     edx, edi
0x14002b071  mov     rcx, rbp
0x14002b074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b079  test    eax, eax
0x14002b07b  jz      short loc_14002B0A7
0x14002b07d  mov     rdx, [rsp+88h+pv]
0x14002b082  mov     rax, rdx
0x14002b085  shr     rax, 20h
0x14002b089  or      [rbx+40h], eax
0x14002b08c  cmp     [rsp+88h+pv+8], 0
0x14002b092  jnz     short loc_14002B09A
0x14002b094  mov     [rbx+0B8h], edx
0x14002b09a  mov     rdx, qword ptr [rsp+88h+var_38]
0x14002b09f  mov     rcx, rbx
0x14002b0a2  call    ?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)
0x14002b0a7  mov     rcx, [rsp+88h+pv+8]; pv
0x14002b0ac  call    cs:__imp_CoTaskMemFree
0x14002b0b2  nop
0x14002b0b3  mov     rcx, [rsp+88h+var_28]
0x14002b0b8  xor     rcx, rsp; StackCookie
0x14002b0bb  call    __security_check_cookie
0x14002b0c0  mov     rbx, [rsp+88h+arg_10]
0x14002b0c8  add     rsp, 70h
0x14002b0cc  pop     rdi
0x14002b0cd  pop     rsi
0x14002b0ce  pop     rbp
0x14002b0cf  retn
```
