# Microsoft::Windows::Performance::CEventTraceRelogger::ProcessTraces(void)

- ea: `0x180002fa0`
- end: `0x180003022`
- name: `?ProcessTraces@CEventTraceRelogger@Performance@Windows@Microsoft@@UEAAJXZ`
- size: `130`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CEventTraceRelogger *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002fa0`
- `0x180003024`
- `0x1800055d8`
- `0x180027910`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x180002ff9`
- `KERNEL32!GetCurrentThread` at `0x180002ff9`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CEventTraceRelogger::ProcessTraces(
        Microsoft::Windows::Performance::CEventTraceRelogger *this)
{
  int v3; // r8d
  unsigned int v4; // ebx
  HANDLE CurrentThread; // rax
  void (__fastcall *v6[2])(HANDLE, _QWORD, _DWORD *, __int64); // [rsp+30h] [rbp-28h] BYREF
  int v7; // [rsp+40h] [rbp-18h]
  int v8; // [rsp+60h] [rbp+8h] BYREF

  if ( *((_DWORD *)this + 4) != 1 )
    return 2147947423LL;
  Microsoft::Windows::Performance::CEventTraceRelogger::CMemoryPriority<1>::CMemoryPriority<1>((__int64)v6);
  v3 = Microsoft::Windows::Performance::CEventTraceRelogger::InternalProcessTraces(this);
  if ( v3 < 0 )
    *((_DWORD *)this + 4) = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 3) + 104LL))(
         *((_QWORD *)this + 3),
         (unsigned int)v3);
  if ( v6[0] )
  {
    v8 = v7;
    CurrentThread = GetCurrentThread();
    v6[0](CurrentThread, 0, &v8, 4);
  }
  return v4;
}

```

## disassembly

```asm
0x180002fa0  push    rbx
0x180002fa2  sub     rsp, 50h
0x180002fa6  cmp     dword ptr [rcx+10h], 1
0x180002faa  mov     rbx, rcx
0x180002fad  jz      short loc_180002FB6
0x180002faf  mov     eax, 8007139Fh
0x180002fb4  jmp     short loc_18000301C
0x180002fb6  lea     rcx, [rsp+58h+var_28]
0x180002fbb  call    ??0?$CMemoryPriority@$00@CEventTraceRelogger@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CEventTraceRelogger::CMemoryPriority<1>::CMemoryPriority<1>(void)
0x180002fc0  mov     rcx, rbx; this
0x180002fc3  call    ?InternalProcessTraces@CEventTraceRelogger@Performance@Windows@Microsoft@@AEAAJXZ; Microsoft::Windows::Performance::CEventTraceRelogger::InternalProcessTraces(void)
0x180002fc8  mov     r8d, eax
0x180002fcb  test    eax, eax
0x180002fcd  jns     short loc_180002FD3
0x180002fcf  and     dword ptr [rbx+10h], 0
0x180002fd3  mov     rcx, [rbx+18h]
0x180002fd7  mov     rdx, [rcx]
0x180002fda  mov     rax, [rdx+68h]
0x180002fde  mov     edx, r8d
0x180002fe1  call    cs:__guard_dispatch_icall_fptr
0x180002fe7  cmp     [rsp+58h+var_28], 0
0x180002fed  mov     ebx, eax
0x180002fef  jz      short loc_18000301A
0x180002ff1  mov     ecx, [rsp+58h+var_18]
0x180002ff5  mov     [rsp+58h+arg_0], ecx
0x180002ff9  call    cs:__imp_GetCurrentThread
0x180002fff  mov     r9d, 4
0x180003005  lea     r8, [rsp+58h+arg_0]
0x18000300a  mov     rcx, rax
0x18000300d  xor     edx, edx
0x18000300f  mov     rax, [rsp+58h+var_28]
0x180003014  call    cs:__guard_dispatch_icall_fptr
0x18000301a  mov     eax, ebx
0x18000301c  add     rsp, 50h
0x180003020  pop     rbx
0x180003021  retn
```
