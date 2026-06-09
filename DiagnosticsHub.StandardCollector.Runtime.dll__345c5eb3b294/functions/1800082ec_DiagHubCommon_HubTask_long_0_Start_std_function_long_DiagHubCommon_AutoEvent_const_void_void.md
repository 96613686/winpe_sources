# DiagHubCommon::HubTask<long,0>::Start(std::function<long (DiagHubCommon::AutoEvent const &,void *)>,void *)

- ea: `0x1800082ec`
- end: `0x180008408`
- name: `?Start@?$HubTask@J$0A@@DiagHubCommon@@QEAAJV?$function@$$A6AJAEBVAutoEvent@DiagHubCommon@@PEAX@Z@std@@PEAX@Z`
- size: `284`
- prototype: `__int64 __fastcall(LPVOID lpParameter)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004d10`
- `0x18002824c`
- `0x18002ba5c`

## callees

- `0x1800082ec`
- `0x180008ab4`
- `0x180049b50`
- `0x18004b640`

## import_xrefs

- `KERNEL32!CreateThread` at `0x18000837a`
- `KERNEL32!CreateThread` at `0x18000837a`
- `KERNEL32!GetLastError` at `0x180008385`
- `KERNEL32!GetLastError` at `0x180008385`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DiagHubCommon::HubTask<long,0>::Start(_QWORD *lpParameter, __int64 a2, __int64 a3)
{
  __int64 v4; // rbx
  __int64 v6; // rcx
  HANDLE v8; // rax
  __int64 v9; // rdx
  signed int LastError; // eax
  __int64 v11; // rdx
  unsigned int v12; // edi
  __int64 v13; // rcx
  __int64 v14; // rcx
  DWORD ThreadId; // [rsp+38h] [rbp-20h] BYREF

  v4 = a2;
  if ( lpParameter[1] )
  {
    v6 = *(_QWORD *)(a2 + 56);
    if ( v6 )
    {
      LOBYTE(a2) = v6 != a2;
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 32LL))(v6, a2);
      *(_QWORD *)(v4 + 56) = 0;
    }
    return 2147942405LL;
  }
  else
  {
    std::function<long (DiagHubCommon::AutoEvent const &,void *)>::operator=(lpParameter + 2);
    lpParameter[10] = a3;
    v8 = CreateThread(0, 0, DiagHubCommon::HubTask<long,0>::ThreadMain, lpParameter, 0, &ThreadId);
    if ( v8 )
    {
      lpParameter[1] = v8;
      v14 = *(_QWORD *)(v4 + 56);
      if ( v14 )
      {
        LOBYTE(v9) = v14 != v4;
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v14 + 32LL))(v14, v9);
        *(_QWORD *)(v4 + 56) = 0;
      }
      return 0;
    }
    else
    {
      LastError = GetLastError();
      v12 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v12 = LastError;
      v13 = *(_QWORD *)(v4 + 56);
      if ( v13 )
      {
        LOBYTE(v11) = v13 != v4;
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v13 + 32LL))(v13, v11);
        *(_QWORD *)(v4 + 56) = 0;
      }
      return v12;
    }
  }
}

```

## disassembly

```asm
0x1800082ec  mov     [rsp+arg_10], rbx
0x1800082f1  mov     [rsp+arg_18], rsi
0x1800082f6  push    rdi
0x1800082f7  sub     rsp, 50h
0x1800082fb  mov     rax, cs:__security_cookie
0x180008302  xor     rax, rsp
0x180008305  mov     [rsp+58h+var_18], rax
0x18000830a  mov     rsi, r8
0x18000830d  mov     rbx, rdx
0x180008310  mov     rdi, rcx
0x180008313  mov     [rsp+58h+var_28], rdx
0x180008318  cmp     qword ptr [rcx+8], 0
0x18000831d  jz      short loc_18000834D
0x18000831f  mov     rcx, [rdx+38h]
0x180008323  test    rcx, rcx
0x180008326  jz      short loc_180008343
0x180008328  cmp     rcx, rdx
0x18000832b  setnz   dl
0x18000832e  mov     rax, [rcx]
0x180008331  mov     rax, [rax+20h]
0x180008335  call    cs:__guard_dispatch_icall_fptr
0x18000833b  mov     qword ptr [rbx+38h], 0
0x180008343  mov     eax, 80070005h
0x180008348  jmp     loc_1800083EB
0x18000834d  add     rcx, 10h
0x180008351  call    ??4?$function@$$A6AJAEBVAutoEvent@DiagHubCommon@@PEAX@Z@std@@QEAAAEAV01@AEBV01@@Z; std::function<long (DiagHubCommon::AutoEvent const &,void *)>::operator=(std::function<long (DiagHubCommon::AutoEvent const &,void *)> const &)
0x180008356  mov     [rdi+50h], rsi
0x18000835a  lea     rax, [rsp+58h+ThreadId]
0x18000835f  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x180008364  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x18000836c  mov     r9, rdi; lpParameter
0x18000836f  lea     r8, ?ThreadMain@?$HubTask@J$0A@@DiagHubCommon@@CAKPEAX@Z; lpStartAddress
0x180008376  xor     edx, edx; dwStackSize
0x180008378  xor     ecx, ecx; lpThreadAttributes
0x18000837a  call    cs:__imp_CreateThread
0x180008380  test    rax, rax
0x180008383  jnz     short loc_1800083C1
0x180008385  call    cs:__imp_GetLastError
0x18000838b  movzx   edi, ax
0x18000838e  or      edi, 80070000h
0x180008394  test    eax, eax
0x180008396  cmovle  edi, eax
0x180008399  mov     rcx, [rbx+38h]
0x18000839d  test    rcx, rcx
0x1800083a0  jz      short loc_1800083BD
0x1800083a2  cmp     rcx, rbx
0x1800083a5  setnz   dl
0x1800083a8  mov     r8, [rcx]
0x1800083ab  mov     rax, [r8+20h]
0x1800083af  call    cs:__guard_dispatch_icall_fptr
0x1800083b5  mov     qword ptr [rbx+38h], 0
0x1800083bd  mov     eax, edi
0x1800083bf  jmp     short loc_1800083EB
0x1800083c1  mov     [rdi+8], rax
0x1800083c5  mov     rcx, [rbx+38h]
0x1800083c9  test    rcx, rcx
0x1800083cc  jz      short loc_1800083E9
0x1800083ce  cmp     rcx, rbx
0x1800083d1  setnz   dl
0x1800083d4  mov     rax, [rcx]
0x1800083d7  mov     rax, [rax+20h]
0x1800083db  call    cs:__guard_dispatch_icall_fptr
0x1800083e1  mov     qword ptr [rbx+38h], 0
0x1800083e9  xor     eax, eax
0x1800083eb  mov     rcx, [rsp+58h+var_18]
0x1800083f0  xor     rcx, rsp; StackCookie
0x1800083f3  call    __security_check_cookie
0x1800083f8  mov     rbx, [rsp+58h+arg_10]
0x1800083fd  mov     rsi, [rsp+58h+arg_18]
0x180008402  add     rsp, 50h
0x180008406  pop     rdi
0x180008407  retn
```
