# std::thread::_Start<void (ThreadManager::*)(std::unique_ptr<SpecializationData,std::default_delete<SpecializationData>> &&),ThreadManager *,std::unique_ptr<SpecializationData,std::default_delete<SpecializationData>>>(void (ThreadManager::*&&)(std::unique_ptr<SpecializationData,std::default_delete<SpecializationData>> &&),ThreadManager * &&,std::unique_ptr<SpecializationData,std::default_delete<SpecializationData>> &&)

- ea: `0x18000a360`
- end: `0x18000a41f`
- name: `??$_Start@P8ThreadManager@@EAAX$$QEAV?$unique_ptr@USpecializationData@@U?$default_delete@USpecializationData@@@std@@@std@@@ZPEAV1@V23@@thread@std@@AEAAX$$QEAP8ThreadManager@@EAAX$$QEAV?$unique_ptr@USpecializationData@@U?$default_delete@USpecializationData@@@std@@@1@@Z$$QEAPEAV2@0@Z`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000f8dc`

## callees

- `0x180002b20`
- `0x180002b88`
- `0x18000a360`
- `0x18000e15c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18000a3d1`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18000a3d1`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000a418`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000a418`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::thread::_Start<void (ThreadManager::*)(std::unique_ptr<SpecializationData> &&),ThreadManager *,std::unique_ptr<SpecializationData>>(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3,
        __int64 *a4)
{
  _QWORD *v8; // rax
  __int64 v9; // r10
  __int64 v10; // rax
  __int64 v12; // [rsp+30h] [rbp-28h] BYREF

  v8 = operator new(0x18u);
  v9 = *a4;
  *a4 = 0;
  *v8 = v9;
  v8[1] = *a3;
  v8[2] = *a2;
  v10 = _o__beginthreadex(
          0,
          0,
          std::thread::_Invoke<std::tuple<void (ThreadManager::*)(std::unique_ptr<SpecializationData> &&),ThreadManager *,std::unique_ptr<SpecializationData>>,0,1,2>,
          v8,
          0,
          a1 + 8,
          v8);
  *(_QWORD *)a1 = v10;
  if ( !v10 )
  {
    *(_DWORD *)(a1 + 8) = 0;
    std::_Throw_Cpp_error(6);
    JUMPOUT(0x18000A41ELL);
  }
  v12 = 0;
  return std::unique_ptr<std::tuple<void (ThreadManager::*)(std::unique_ptr<SpecializationData> &&),ThreadManager *,std::unique_ptr<SpecializationData>>>::~unique_ptr<std::tuple<void (ThreadManager::*)(std::unique_ptr<SpecializationData> &&),ThreadManager *,std::unique_ptr<SpecializationData>>>(&v12);
}

```

## disassembly

```asm
0x18000a360  mov     [rsp+arg_8], rbx
0x18000a365  push    rsi
0x18000a366  push    rdi
0x18000a367  push    r14
0x18000a369  sub     rsp, 40h
0x18000a36d  mov     rax, cs:__security_cookie
0x18000a374  xor     rax, rsp
0x18000a377  mov     [rsp+58h+var_20], rax
0x18000a37c  mov     rbx, r9
0x18000a37f  mov     rdi, r8
0x18000a382  mov     rsi, rdx
0x18000a385  mov     r14, rcx
0x18000a388  mov     ecx, 18h; Size
0x18000a38d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a392  mov     r10, [rbx]
0x18000a395  mov     qword ptr [rbx], 0
0x18000a39c  mov     [rax], r10
0x18000a39f  mov     rdx, [rdi]
0x18000a3a2  mov     [rax+8], rdx
0x18000a3a6  mov     rcx, [rsi]
0x18000a3a9  mov     [rax+10h], rcx
0x18000a3ad  mov     [rsp+58h+var_28], rax
0x18000a3b2  lea     rbx, [r14+8]
0x18000a3b6  mov     [rsp+58h+var_30], rbx
0x18000a3bb  mov     [rsp+58h+var_38], 0
0x18000a3c3  mov     r9, rax
0x18000a3c6  lea     r8, ??$_Invoke@V?$tuple@P8ThreadManager@@EAAX$$QEAV?$unique_ptr@USpecializationData@@U?$default_delete@USpecializationData@@@std@@@std@@@ZPEAV1@V23@@std@@$0A@$00$01@thread@std@@CAIPEAX@Z; std::thread::_Invoke<std::tuple<void (ThreadManager::*)(std::unique_ptr<SpecializationData> &&),ThreadManager *,std::unique_ptr<SpecializationData>>,0,1,2>(void *)
0x18000a3cd  xor     edx, edx
0x18000a3cf  xor     ecx, ecx
0x18000a3d1  call    cs:__imp__o__beginthreadex
0x18000a3d7  mov     [r14], rax
0x18000a3da  test    rax, rax
0x18000a3dd  jz      short loc_18000A40D
0x18000a3df  mov     [rsp+58h+var_28], 0
0x18000a3e8  lea     rcx, [rsp+58h+var_28]
0x18000a3ed  call    ??1?$unique_ptr@V?$tuple@P8ThreadManager@@EAAX$$QEAV?$unique_ptr@USpecializationData@@U?$default_delete@USpecializationData@@@std@@@std@@@ZPEAV1@V23@@std@@U?$default_delete@V?$tuple@P8ThreadManager@@EAAX$$QEAV?$unique_ptr@USpecializationData@@U?$default_delete@USpecializationData@@@std@@@std@@@ZPEAV1@V23@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::tuple<void (ThreadManager::*)(std::unique_ptr<SpecializationData> &&),ThreadManager *,std::unique_ptr<SpecializationData>>>::~unique_ptr<std::tuple<void (ThreadManager::*)(std::unique_ptr<SpecializationData> &&),ThreadManager *,std::unique_ptr<SpecializationData>>>(void)
0x18000a3f2  mov     rcx, [rsp+58h+var_20]
0x18000a3f7  xor     rcx, rsp; StackCookie
0x18000a3fa  call    __security_check_cookie
0x18000a3ff  mov     rbx, [rsp+58h+arg_8]
0x18000a404  add     rsp, 40h
0x18000a408  pop     r14
0x18000a40a  pop     rdi
0x18000a40b  pop     rsi
0x18000a40c  retn
0x18000a40d  mov     dword ptr [rbx], 0
0x18000a413  mov     ecx, 6
0x18000a418  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
