# ??$_Start@P8ThreadManager@@EAAX$$QEAV?$unique_ptr@USpecializationData@@U?$default_delete@USpecializationData@@@std@@@std@@@ZPEAV1@$$T@thread@std@@AEAAX$$QEAP8ThreadManager@@EAAX$$QEAV?$unique_ptr@USpecializationData@@U?$default_delete@USpecializationData@@@std@@@1@@Z$$QEAPEAV2@$$QEA$$T@Z

- ea: `0x18000a2a8`
- end: `0x18000a359`
- name: `??$_Start@P8ThreadManager@@EAAX$$QEAV?$unique_ptr@USpecializationData@@U?$default_delete@USpecializationData@@@std@@@std@@@ZPEAV1@$$T@thread@std@@AEAAX$$QEAP8ThreadManager@@EAAX$$QEAV?$unique_ptr@USpecializationData@@U?$default_delete@USpecializationData@@@std@@@1@@Z$$QEAPEAV2@$$QEA$$T@Z`
- size: `177`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180010284`
- `0x18001475c`

## callees

- `0x180002b20`
- `0x180002b88`
- `0x18000a2a8`
- `0x18000dccc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18000a30f`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18000a30f`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000a352`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000a352`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::thread::_Start<void (ThreadManager::*)(std::unique_ptr<SpecializationData> &&),ThreadManager *,std::nullptr_t>(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3,
        _QWORD *a4)
{
  _QWORD *v8; // rax
  __int64 v9; // rax
  __int64 v11; // [rsp+30h] [rbp-38h] BYREF

  v8 = operator new(0x18u);
  *v8 = *a4;
  v8[1] = *a3;
  v8[2] = *a2;
  v9 = _o__beginthreadex(
         0,
         0,
         std::thread::_Invoke<std::tuple<void (ThreadManager::*)(std::unique_ptr<SpecializationData> &&),ThreadManager *,std::nullptr_t>,0,1,2>,
         v8,
         0,
         a1 + 8,
         v8);
  *(_QWORD *)a1 = v9;
  if ( !v9 )
  {
    *(_DWORD *)(a1 + 8) = 0;
    std::_Throw_Cpp_error(6);
    JUMPOUT(0x18000A358LL);
  }
  v11 = 0;
  return Microsoft::WRL::Details::MakeAllocator<Windows::Storage::Streams::CBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_,Windows::Storage::Streams::DefaultMarshaler>>::~MakeAllocator<Windows::Storage::Streams::CBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_,Windows::Storage::Streams::DefaultMarshaler>>(&v11);
}

```

## disassembly

```asm
0x18000a2a8  push    rbx
0x18000a2aa  push    rsi
0x18000a2ab  push    rdi
0x18000a2ac  push    r14
0x18000a2ae  sub     rsp, 48h
0x18000a2b2  mov     rax, cs:__security_cookie
0x18000a2b9  xor     rax, rsp
0x18000a2bc  mov     [rsp+68h+var_30], rax
0x18000a2c1  mov     rbx, r9
0x18000a2c4  mov     rdi, r8
0x18000a2c7  mov     rsi, rdx
0x18000a2ca  mov     r14, rcx
0x18000a2cd  mov     ecx, 18h; Size
0x18000a2d2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a2d7  mov     r9, [rbx]
0x18000a2da  mov     [rax], r9
0x18000a2dd  mov     r8, [rdi]
0x18000a2e0  mov     [rax+8], r8
0x18000a2e4  mov     rcx, [rsi]
0x18000a2e7  mov     [rax+10h], rcx
0x18000a2eb  mov     [rsp+68h+var_38], rax
0x18000a2f0  lea     rbx, [r14+8]
0x18000a2f4  mov     [rsp+68h+var_40], rbx
0x18000a2f9  mov     [rsp+68h+var_48], 0
0x18000a301  mov     r9, rax
0x18000a304  lea     r8, ??$_Invoke@V?$tuple@P8ThreadManager@@EAAX$$QEAV?$unique_ptr@USpecializationData@@U?$default_delete@USpecializationData@@@std@@@std@@@ZPEAV1@$$T@std@@$0A@$00$01@thread@std@@CAIPEAX@Z; std::thread::_Invoke<std::tuple<void (ThreadManager::*)(std::unique_ptr<SpecializationData> &&),ThreadManager *,std::nullptr_t>,0,1,2>(void *)
0x18000a30b  xor     edx, edx
0x18000a30d  xor     ecx, ecx
0x18000a30f  call    cs:__imp__o__beginthreadex
0x18000a315  mov     [r14], rax
0x18000a318  test    rax, rax
0x18000a31b  jz      short loc_18000A347
0x18000a31d  mov     [rsp+68h+var_38], 0
0x18000a326  lea     rcx, [rsp+68h+var_38]
0x18000a32b  call    ??1?$MakeAllocator@V?$CBuffer@V_lambda_8fcabb03306c9f8765c03020018d7da6_@@UDefaultMarshaler@Streams@Storage@Windows@@@Streams@Storage@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Storage::Streams::CBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_,Windows::Storage::Streams::DefaultMarshaler>>::~MakeAllocator<Windows::Storage::Streams::CBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_,Windows::Storage::Streams::DefaultMarshaler>>(void)
0x18000a330  mov     rcx, [rsp+68h+var_30]
0x18000a335  xor     rcx, rsp; StackCookie
0x18000a338  call    __security_check_cookie
0x18000a33d  add     rsp, 48h
0x18000a341  pop     r14
0x18000a343  pop     rdi
0x18000a344  pop     rsi
0x18000a345  pop     rbx
0x18000a346  retn
0x18000a347  mov     dword ptr [rbx], 0
0x18000a34d  mov     ecx, 6
0x18000a352  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
