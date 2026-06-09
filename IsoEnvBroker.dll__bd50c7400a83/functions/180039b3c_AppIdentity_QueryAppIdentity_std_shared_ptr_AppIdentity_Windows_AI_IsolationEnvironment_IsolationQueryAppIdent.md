# AppIdentity::QueryAppIdentity(std::shared_ptr<AppIdentity> &,Windows::AI::IsolationEnvironment::IsolationQueryAppIdentityStatus *)

- ea: `0x180039b3c`
- end: `0x180039caf`
- name: `?QueryAppIdentity@AppIdentity@@SAJAEAV?$shared_ptr@VAppIdentity@@@std@@PEAW4IsolationQueryAppIdentityStatus@IsolationEnvironment@AI@Windows@@@Z`
- size: `371`
- prototype: `__int64 __fastcall(__int64, int *)`
- caller_count: `7`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800238a0`
- `0x180023fb0`
- `0x180025a90`
- `0x1800274e0`
- `0x180028120`
- `0x180028ac0`
- `0x180029ad0`

## callees

- `0x180013230`
- `0x1800366b4`
- `0x180036f34`
- `0x180038494`
- `0x180039b3c`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039c0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039c94`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039c0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039c94`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180039bc1`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180039bc1`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180039b6b`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180039b6b`

## string_xrefs

- `0x180039b9e`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\appidentity.cpp`
- `0x180039beb`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\appidentity.cpp`
- `0x180039be4`: `[QueryAppIdentity] OpenProcess failed for PID %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AppIdentity::QueryAppIdentity(__int64 a1, int *a2)
{
  RPC_STATUS v4; // eax
  unsigned int v5; // ebx
  char *v7; // rbx
  unsigned int LastErrorMsg; // edi
  int v9; // esi
  volatile signed __int32 *v10; // rdi
  char *v11; // [rsp+20h] [rbp-30h]
  char *v12; // [rsp+28h] [rbp-28h]
  __int128 v13; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  unsigned int Pid; // [rsp+80h] [rbp+30h] BYREF
  int v16; // [rsp+88h] [rbp+38h]

  v16 = 1;
  Pid = 0;
  v4 = I_RpcBindingInqLocalClientPID(0, &Pid);
  if ( v4 < 1 )
    v5 = v4;
  else
    v5 = (unsigned __int16)v4 | 0x80010000;
  if ( (v5 & 0x80000000) == 0 )
  {
    v7 = (char *)OpenProcess(0x400u, 0, Pid);
    if ( ((unsigned __int64)(v7 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      v13 = 0;
      v9 = AppIdentity::EnumerateParentProcesses((char *)Pid);
      if ( v9 >= 0 )
      {
        std::shared_ptr<AppIdentity>::operator=(a1, &v13);
        if ( a2 )
          *a2 = v16;
      }
      v10 = (volatile signed __int32 *)*((_QWORD *)&v13 + 1);
      if ( *((_QWORD *)&v13 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v13 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
          if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
        }
      }
      CloseHandle(v7);
      return (unsigned int)v9;
    }
    else
    {
      LODWORD(v11) = Pid;
      LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                       retaddr,
                       (void *)0x1ED,
                       (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\appidentity.cpp",
                       "[QueryAppIdentity] OpenProcess failed for PID %d",
                       v11);
      if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v7);
      return LastErrorMsg;
    }
  }
  else
  {
    LODWORD(v12) = v4;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x1E6,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\appidentity.cpp",
      (const char *)v5,
      (int)"I_RpcBindingInqLocalClientPID failed with status %#x",
      v12);
    return v5;
  }
}

```

## disassembly

```asm
0x180039b3c  mov     [rsp-18h+arg_0], rbx
0x180039b41  mov     [rsp-18h+arg_8], rsi
0x180039b46  push    rbp
0x180039b47  push    rdi
0x180039b48  push    r14
0x180039b4a  mov     rbp, rsp
0x180039b4d  sub     rsp, 50h
0x180039b51  mov     rdi, rdx
0x180039b54  mov     r14, rcx
0x180039b57  mov     [rbp+arg_18], 1
0x180039b5e  mov     [rbp+Pid], 0
0x180039b65  lea     rdx, [rbp+Pid]; Pid
0x180039b69  xor     ecx, ecx; Binding
0x180039b6b  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180039b71  cmp     eax, 1
0x180039b74  jl      short loc_180039B81
0x180039b76  movzx   ebx, ax
0x180039b79  or      ebx, 80010000h
0x180039b7f  jmp     short loc_180039B83
0x180039b81  mov     ebx, eax
0x180039b83  test    ebx, ebx
0x180039b85  jns     short loc_180039BB6
0x180039b87  mov     rcx, [rbp+18h]; this
0x180039b8b  mov     dword ptr [rsp+50h+var_28], eax; char *
0x180039b8f  lea     rax, aIRpcbindinginq; "I_RpcBindingInqLocalClientPID failed wi"...
0x180039b96  mov     [rsp+50h+var_30], rax; int
0x180039b9b  mov     r9d, ebx; char *
0x180039b9e  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180039ba5  mov     edx, 1E6h; void *
0x180039baa  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180039baf  mov     eax, ebx
0x180039bb1  jmp     loc_180039C9C
0x180039bb6  mov     r8d, [rbp+Pid]; dwProcessId
0x180039bba  xor     edx, edx; bInheritHandle
0x180039bbc  mov     ecx, 400h; dwDesiredAccess
0x180039bc1  call    cs:__imp_OpenProcess
0x180039bc7  mov     rbx, rax
0x180039bca  mov     [rbp+var_20], rax
0x180039bce  inc     rax
0x180039bd1  test    rax, 0FFFFFFFFFFFFFFFEh
0x180039bd7  jnz     short loc_180039C18
0x180039bd9  mov     eax, [rbp+Pid]
0x180039bdc  mov     rcx, [rbp+18h]; this
0x180039be0  mov     dword ptr [rsp+50h+var_30], eax; char *
0x180039be4  lea     r9, aQueryappidenti_2; "[QueryAppIdentity] OpenProcess failed f"...
0x180039beb  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180039bf2  mov     edx, 1EDh; void *
0x180039bf7  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x180039bfc  mov     edi, eax
0x180039bfe  lea     rcx, [rbx-1]
0x180039c02  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180039c06  ja      short loc_180039C11
0x180039c08  mov     rcx, rbx; hObject
0x180039c0b  call    cs:__imp_CloseHandle
0x180039c11  mov     eax, edi
0x180039c13  jmp     loc_180039C9C
0x180039c18  xorps   xmm0, xmm0
0x180039c1b  movdqu  [rbp+var_18], xmm0
0x180039c20  lea     r8, [rbp+var_18]
0x180039c24  lea     rdx, [rbp+arg_18]
0x180039c28  mov     ecx, [rbp+Pid]; char *
0x180039c2b  call    ?EnumerateParentProcesses@AppIdentity@@CAJKAEAW4IsolationQueryAppIdentityStatus@IsolationEnvironment@AI@Windows@@AEAV?$shared_ptr@VAppIdentity@@@std@@@Z; AppIdentity::EnumerateParentProcesses(ulong,Windows::AI::IsolationEnvironment::IsolationQueryAppIdentityStatus &,std::shared_ptr<AppIdentity> &)
0x180039c30  mov     esi, eax
0x180039c32  test    eax, eax
0x180039c34  js      short loc_180039C4C
0x180039c36  lea     rdx, [rbp+var_18]
0x180039c3a  mov     rcx, r14
0x180039c3d  call    ??4?$shared_ptr@VAppIdentity@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<AppIdentity>::operator=(std::shared_ptr<AppIdentity> &&)
0x180039c42  test    rdi, rdi
0x180039c45  jz      short loc_180039C4C
0x180039c47  mov     ecx, [rbp+arg_18]
0x180039c4a  mov     [rdi], ecx
0x180039c4c  mov     rdi, qword ptr [rbp+var_18+8]
0x180039c50  test    rdi, rdi
0x180039c53  jz      short loc_180039C91
0x180039c55  or      r14d, 0FFFFFFFFh
0x180039c59  mov     eax, r14d
0x180039c5c  lock xadd [rdi+8], eax
0x180039c61  add     eax, r14d
0x180039c64  jnz     short loc_180039C91
0x180039c66  mov     rax, [rdi]
0x180039c69  mov     rcx, rdi
0x180039c6c  mov     rax, [rax]
0x180039c6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039c74  mov     eax, r14d
0x180039c77  lock xadd [rdi+0Ch], eax
0x180039c7c  add     eax, r14d
0x180039c7f  jnz     short loc_180039C91
0x180039c81  mov     rax, [rdi]
0x180039c84  mov     rcx, rdi
0x180039c87  mov     rax, [rax+8]
0x180039c8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039c90  nop
0x180039c91  mov     rcx, rbx; hObject
0x180039c94  call    cs:__imp_CloseHandle
0x180039c9a  mov     eax, esi
0x180039c9c  mov     rbx, [rsp+50h+arg_0]
0x180039ca1  mov     rsi, [rsp+50h+arg_8]
0x180039ca6  add     rsp, 50h
0x180039caa  pop     r14
0x180039cac  pop     rdi
0x180039cad  pop     rbp
0x180039cae  retn
```
