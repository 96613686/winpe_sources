# ServiceEtwThreadHelper::Initialize(void)

- ea: `0x18000f634`
- end: `0x18000f71a`
- name: `?Initialize@ServiceEtwThreadHelper@@QEAAXXZ`
- size: `230`
- prototype: `void __fastcall(ServiceEtwThreadHelper *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180011630`

## callees

- `0x180003ebc`
- `0x180004cbc`
- `0x18000da1c`
- `0x18000e720`
- `0x18000e760`
- `0x18000e8b0`
- `0x18000f634`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000f713`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000f713`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18000f699`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18000f699`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ServiceEtwThreadHelper::Initialize(ServiceEtwThreadHelper *this)
{
  _lambda_eba06b9dd6f59ed029562cd91b3a862a_ *v2; // rbx
  _QWORD *v3; // rax
  _OWORD *v4; // rax
  __int128 v5; // xmm1
  __int128 v6; // [rsp+30h] [rbp-10h] BYREF
  void *v7; // [rsp+50h] [rbp+10h] BYREF
  char v8; // [rsp+58h] [rbp+18h] BYREF

  if ( !*((_BYTE *)this + 8) )
  {
    *((_BYTE *)this + 8) = 1;
    v2 = _lambda_eba06b9dd6f59ed029562cd91b3a862a_::_lambda_eba06b9dd6f59ed029562cd91b3a862a_(
           (_lambda_eba06b9dd6f59ed029562cd91b3a862a_ *)&v8,
           this);
    v3 = operator new(8u);
    *v3 = *(_QWORD *)v2;
    v7 = v3;
    *(_QWORD *)&v6 = _o__beginthreadex(
                       0,
                       0,
                       std::thread::_Invoke<std::tuple<_lambda_eba06b9dd6f59ed029562cd91b3a862a_>,0>,
                       v3,
                       0,
                       (char *)&v6 + 8);
    if ( !(_QWORD)v6 )
    {
      DWORD2(v6) = 0;
      std::_Throw_Cpp_error(6);
      JUMPOUT(0x18000F719LL);
    }
    v7 = 0;
    std::unique_ptr<std::tuple<_lambda_eba06b9dd6f59ed029562cd91b3a862a_>>::~unique_ptr<std::tuple<_lambda_eba06b9dd6f59ed029562cd91b3a862a_>>(&v7);
    v4 = operator new(0x10u);
    v5 = v6;
    v6 = 0;
    *v4 = v5;
    v7 = v4;
    std::unique_ptr<std::thread>::operator=<std::default_delete<std::thread>,0>((__int64 *)this, (__int64 *)&v7);
    std::unique_ptr<std::thread>::~unique_ptr<std::thread>(&v7);
    std::thread::~thread((std::thread *)&v6);
  }
}

```

## disassembly

```asm
0x18000f634  mov     [rsp-8+arg_10], rbx
0x18000f639  mov     [rsp-8+arg_18], rdi
0x18000f63e  push    rbp
0x18000f63f  mov     rbp, rsp
0x18000f642  sub     rsp, 40h
0x18000f646  mov     rdi, rcx
0x18000f649  cmp     byte ptr [rcx+8], 0
0x18000f64d  jnz     loc_18000F6F7
0x18000f653  mov     byte ptr [rcx+8], 1
0x18000f657  mov     rdx, rcx; struct ServiceEtwThreadHelper *
0x18000f65a  lea     rcx, [rbp+arg_8]; this
0x18000f65e  call    ??0_lambda_eba06b9dd6f59ed029562cd91b3a862a_@@QEAA@PEAVServiceEtwThreadHelper@@@Z; _lambda_eba06b9dd6f59ed029562cd91b3a862a_::_lambda_eba06b9dd6f59ed029562cd91b3a862a_(ServiceEtwThreadHelper *)
0x18000f663  mov     rbx, rax
0x18000f666  mov     ecx, 8; Size
0x18000f66b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f670  mov     rcx, [rbx]
0x18000f673  mov     [rax], rcx
0x18000f676  mov     [rbp+arg_0], rax
0x18000f67a  lea     rcx, [rbp+var_10+8]
0x18000f67e  mov     [rsp+40h+var_18], rcx
0x18000f683  mov     [rsp+40h+var_20], 0
0x18000f68b  mov     r9, rax
0x18000f68e  lea     r8, ??$_Invoke@V?$tuple@V_lambda_eba06b9dd6f59ed029562cd91b3a862a_@@@std@@$0A@@thread@std@@CAIPEAX@Z; std::thread::_Invoke<std::tuple<_lambda_eba06b9dd6f59ed029562cd91b3a862a_>,0>(void *)
0x18000f695  xor     edx, edx
0x18000f697  xor     ecx, ecx
0x18000f699  call    cs:__imp__o__beginthreadex
0x18000f69f  mov     qword ptr [rbp+var_10], rax
0x18000f6a3  test    rax, rax
0x18000f6a6  jz      short loc_18000F707
0x18000f6a8  mov     [rbp+arg_0], 0
0x18000f6b0  lea     rcx, [rbp+arg_0]
0x18000f6b4  call    ??1?$unique_ptr@V?$tuple@V_lambda_eba06b9dd6f59ed029562cd91b3a862a_@@@std@@U?$default_delete@V?$tuple@V_lambda_eba06b9dd6f59ed029562cd91b3a862a_@@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::tuple<_lambda_eba06b9dd6f59ed029562cd91b3a862a_>>::~unique_ptr<std::tuple<_lambda_eba06b9dd6f59ed029562cd91b3a862a_>>(void)
0x18000f6b9  nop
0x18000f6ba  mov     ecx, 10h; Size
0x18000f6bf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f6c4  xorps   xmm0, xmm0
0x18000f6c7  movaps  xmm1, [rbp+var_10]
0x18000f6cb  movdqa  [rbp+var_10], xmm0
0x18000f6d0  movdqu  xmmword ptr [rax], xmm1
0x18000f6d4  mov     [rbp+arg_0], rax
0x18000f6d8  lea     rdx, [rbp+arg_0]
0x18000f6dc  mov     rcx, rdi
0x18000f6df  call    ??$?4U?$default_delete@Vthread@std@@@std@@$0A@@?$unique_ptr@Vthread@std@@U?$default_delete@Vthread@std@@@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<std::thread>::operator=<std::default_delete<std::thread>,0>(std::unique_ptr<std::thread> &&)
0x18000f6e4  lea     rcx, [rbp+arg_0]
0x18000f6e8  call    ??1?$unique_ptr@Vthread@std@@U?$default_delete@Vthread@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::thread>::~unique_ptr<std::thread>(void)
0x18000f6ed  nop
0x18000f6ee  lea     rcx, [rbp+var_10]; this
0x18000f6f2  call    ??1thread@std@@QEAA@XZ; std::thread::~thread(void)
0x18000f6f7  mov     rbx, [rsp+40h+arg_10]
0x18000f6fc  mov     rdi, [rsp+40h+arg_18]
0x18000f701  add     rsp, 40h
0x18000f705  pop     rbp
0x18000f706  retn
0x18000f707  mov     dword ptr [rbp+var_10+8], 0
0x18000f70e  mov     ecx, 6
0x18000f713  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
