# tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)

- ea: `0x18000adb0`
- end: `0x18000aec0`
- name: `?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `272`
- prototype: `void __fastcall(__int64, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180007410`
- `0x180009e10`

## callees

- `0x18000adb0`
- `0x18000b7c0`
- `0x1800181b0`
- `0x18001cdf0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000ae30`
- `KERNEL32!GetProcAddress` at `0x18000ae30`
- `KERNEL32!GetModuleHandleW` at `0x18000ae19`
- `KERNEL32!GetModuleHandleW` at `0x18000ae19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ae9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ae9c`

## string_xrefs

- `0x18000ae12`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall tip2::details::shared_data<0,0,0>::complete_helper(__int64 a1, unsigned int a2)
{
  unsigned int v4; // esi
  __int64 v5; // rbp
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v8; // edx
  __int128 v9; // [rsp+30h] [rbp-58h] BYREF
  LPVOID pv[2]; // [rsp+40h] [rbp-48h]
  __int128 v11; // [rsp+50h] [rbp-38h]

  v9 = 0;
  *(_OWORD *)pv = 0;
  v11 = 0;
  v4 = *(_DWORD *)(a1 + 184);
  v5 = *(_QWORD *)(a1 + 232);
  *(_QWORD *)(a1 + 232) = 0;
  ProcAddress = (FARPROC)`TestQueryData'::`2'::s_pfnTestQueryData;
  if ( `TestQueryData'::`2'::s_pfnTestQueryData )
    goto LABEL_13;
  ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
  if ( !g_tip_details_kernelbaseModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
    g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "TestQueryData");
  `TestQueryData'::`2'::s_pfnTestQueryData = (__int64)ProcAddress;
  if ( ProcAddress )
  {
LABEL_13:
    if ( ((unsigned int (__fastcall *)(__int64, _QWORD, _QWORD, __int128 *))ProcAddress)(v5, a2, v4, &v9) )
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
0x18000adb0  mov     [rsp+arg_10], rbx
0x18000adb5  push    rbp
0x18000adb6  push    rsi
0x18000adb7  push    rdi
0x18000adb8  sub     rsp, 70h
0x18000adbc  mov     rax, cs:__security_cookie
0x18000adc3  xor     rax, rsp
0x18000adc6  mov     [rsp+88h+var_28], rax
0x18000adcb  mov     edi, edx
0x18000adcd  mov     rbx, rcx
0x18000add0  xorps   xmm0, xmm0
0x18000add3  movups  [rsp+88h+var_58], xmm0
0x18000add8  movups  xmmword ptr [rsp+88h+pv], xmm0
0x18000addd  movups  [rsp+88h+var_38], xmm0
0x18000ade2  mov     esi, [rcx+0B8h]
0x18000ade8  mov     rbp, [rcx+0E8h]
0x18000adef  mov     qword ptr [rcx+0E8h], 0
0x18000adfa  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x18000ae01  test    rax, rax
0x18000ae04  jnz     short loc_18000AE56
0x18000ae06  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18000ae0d  test    rax, rax
0x18000ae10  jnz     short loc_18000AE26
0x18000ae12  lea     rcx, ModuleName; "kernelbase.dll"
0x18000ae19  call    cs:__imp_GetModuleHandleW
0x18000ae1f  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18000ae26  lea     rdx, aTestquerydata; "TestQueryData"
0x18000ae2d  mov     rcx, rax; hModule
0x18000ae30  call    cs:__imp_GetProcAddress
0x18000ae36  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x18000ae3d  test    rax, rax
0x18000ae40  jnz     short loc_18000AE56
0x18000ae42  xorps   xmm0, xmm0
0x18000ae45  movups  [rsp+88h+var_58], xmm0
0x18000ae4a  movups  xmmword ptr [rsp+88h+pv], xmm0
0x18000ae4f  movups  [rsp+88h+var_38], xmm0
0x18000ae54  jmp     short loc_18000AE97
0x18000ae56  lea     r9, [rsp+88h+var_58]
0x18000ae5b  mov     r8d, esi
0x18000ae5e  mov     edx, edi
0x18000ae60  mov     rcx, rbp
0x18000ae63  call    cs:__guard_dispatch_icall_fptr
0x18000ae69  test    eax, eax
0x18000ae6b  jz      short loc_18000AE97
0x18000ae6d  mov     rdx, [rsp+88h+pv]
0x18000ae72  mov     rax, rdx
0x18000ae75  shr     rax, 20h
0x18000ae79  or      [rbx+40h], eax
0x18000ae7c  cmp     [rsp+88h+pv+8], 0
0x18000ae82  jnz     short loc_18000AE8A
0x18000ae84  mov     [rbx+0B8h], edx
0x18000ae8a  mov     rdx, qword ptr [rsp+88h+var_38]
0x18000ae8f  mov     rcx, rbx
0x18000ae92  call    ?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)
0x18000ae97  mov     rcx, [rsp+88h+pv+8]; pv
0x18000ae9c  call    cs:__imp_CoTaskMemFree
0x18000aea2  nop
0x18000aea3  mov     rcx, [rsp+88h+var_28]
0x18000aea8  xor     rcx, rsp; StackCookie
0x18000aeab  call    __security_check_cookie
0x18000aeb0  mov     rbx, [rsp+88h+arg_10]
0x18000aeb8  add     rsp, 70h
0x18000aebc  pop     rdi
0x18000aebd  pop     rsi
0x18000aebe  pop     rbp
0x18000aebf  retn
```
