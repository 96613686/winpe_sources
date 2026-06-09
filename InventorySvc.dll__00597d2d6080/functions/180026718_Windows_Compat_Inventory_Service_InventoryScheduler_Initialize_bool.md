# Windows::Compat::Inventory::Service::InventoryScheduler::Initialize(bool)

- ea: `0x180026718`
- end: `0x180026811`
- name: `?Initialize@InventoryScheduler@Service@Inventory@Compat@Windows@@AEAAX_N@Z`
- size: `249`
- prototype: `void __fastcall(Windows::Compat::Inventory::Service::InventoryScheduler *__hidden this, bool)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001ff40`
- `0x1800294d0`

## callees

- `0x180002c40`
- `0x180009060`
- `0x180011334`
- `0x1800152d0`
- `0x180026718`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800267f3`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800267f3`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1800267a4`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1800267a4`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18002678b`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18002678b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180026732`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180026732`

## string_xrefs

- `0x1800267b8`: `Windows::Compat::Inventory::Service::InventoryScheduler::Initialize`
- `0x1800267ab`: `Already initialized. Continuing.`
- `0x1800267ff`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::Compat::Inventory::Service::InventoryScheduler::Initialize(HANDLE *this, char a2)
{
  DWORD v3; // eax
  const char *v4; // r9
  HANDLE **v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rcx
  int v8; // ecx
  int v9; // eax
  _DWORD v10[4]; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( !a2 )
  {
    v3 = WaitForSingleObjectEx(this[4], 0, 0);
    if ( v3 == 258 )
    {
      AslLogCallPrintf(
        3,
        "Windows::Compat::Inventory::Service::InventoryScheduler::Initialize",
        88,
        "Already initialized. Continuing.");
      return;
    }
    if ( v3 )
LABEL_12:
      wil::details::in1diag3::FailFast_Unexpected(
        retaddr,
        (void *)0xB0F,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        v4);
  }
  if ( *((_DWORD *)this + 22) )
    std::thread::join((std::thread *)(this + 10));
  v5 = (HANDLE **)operator new(8u);
  *v5 = this;
  v6 = _o__beginthreadex(
         0,
         0,
         std::thread::_Invoke_std::tuple__lambda_7e541e4d92ddeef83ac68a335929177d____0_,
         v5,
         0,
         v10);
  if ( !v6 )
  {
    v10[0] = 0;
    std::_Throw_Cpp_error(6);
    goto LABEL_12;
  }
  if ( *((_DWORD *)this + 22) )
  {
    _o_terminate(v7, v6);
    __debugbreak();
  }
  v8 = v10[0];
  v9 = v10[1];
  this[10] = (HANDLE)v6;
  *((_DWORD *)this + 22) = v8;
  *((_DWORD *)this + 23) = v9;
}

```

## disassembly

```asm
0x180026718  mov     [rsp+arg_0], rbx
0x18002671d  push    rdi
0x18002671e  sub     rsp, 40h
0x180026722  mov     rdi, rcx
0x180026725  test    dl, dl
0x180026727  jnz     short loc_180026747
0x180026729  xor     r8d, r8d; bAlertable
0x18002672c  xor     edx, edx; dwMilliseconds
0x18002672e  mov     rcx, [rcx+20h]; hHandle
0x180026732  call    cs:__imp_WaitForSingleObjectEx
0x180026738  cmp     eax, 102h
0x18002673d  jz      short loc_1800267AB
0x18002673f  test    eax, eax
0x180026741  jnz     loc_1800267FA
0x180026747  lea     rbx, [rdi+50h]
0x18002674b  cmp     dword ptr [rdi+58h], 0
0x18002674f  jz      short loc_180026759
0x180026751  mov     rcx, rbx; this
0x180026754  call    ?join@thread@std@@QEAAXXZ; std::thread::join(void)
0x180026759  mov     ecx, 8; Size
0x18002675e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026763  mov     [rax], rdi
0x180026766  mov     [rsp+48h+arg_10], rax
0x18002676b  lea     rcx, [rsp+48h+var_10]
0x180026770  mov     [rsp+48h+var_20], rcx
0x180026775  mov     [rsp+48h+var_28], 0
0x18002677d  mov     r9, rax
0x180026780  lea     r8, std__thread___Invoke_std__tuple__lambda_7e541e4d92ddeef83ac68a335929177d____0_
0x180026787  xor     edx, edx
0x180026789  xor     ecx, ecx
0x18002678b  call    cs:__imp__o__beginthreadex
0x180026791  mov     rdx, rax
0x180026794  mov     [rsp+48h+var_18], rax
0x180026799  test    rax, rax
0x18002679c  jz      short loc_1800267E6
0x18002679e  cmp     dword ptr [rbx+8], 0
0x1800267a2  jz      short loc_1800267D3
0x1800267a4  call    cs:__imp__o_terminate
0x1800267aa  int     3; Trap to Debugger
0x1800267ab  lea     r9, aAlreadyInitial_0; "Already initialized. Continuing."
0x1800267b2  mov     r8d, 58h ; 'X'
0x1800267b8  lea     rdx, aWindowsCompatI_8; "Windows::Compat::Inventory::Service::In"...
0x1800267bf  lea     ecx, [r8-55h]
0x1800267c3  call    AslLogCallPrintf
0x1800267c8  mov     rbx, [rsp+48h+arg_0]
0x1800267cd  add     rsp, 40h
0x1800267d1  pop     rdi
0x1800267d2  retn
0x1800267d3  mov     ecx, [rsp+48h+var_10]
0x1800267d7  mov     eax, [rsp+48h+var_C]
0x1800267db  mov     [rbx], rdx
0x1800267de  mov     [rbx+8], ecx
0x1800267e1  mov     [rbx+0Ch], eax
0x1800267e4  jmp     short loc_1800267C8
0x1800267e6  mov     [rsp+48h+var_10], 0
0x1800267ee  mov     ecx, 6
0x1800267f3  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800267f9  nop
0x1800267fa  mov     rcx, [rsp+48h]; this
0x1800267ff  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180026806  mov     edx, 0B0Fh; void *
0x18002680b  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
```
