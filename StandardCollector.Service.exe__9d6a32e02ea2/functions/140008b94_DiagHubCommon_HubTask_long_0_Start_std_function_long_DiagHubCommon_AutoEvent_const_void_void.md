# DiagHubCommon::HubTask<long,0>::Start(std::function<long (DiagHubCommon::AutoEvent const &,void *)>,void *)

- ea: `0x140008b94`
- end: `0x140008ca7`
- name: `?Start@?$HubTask@J$0A@@DiagHubCommon@@QEAAJV?$function@$$A6AJAEBVAutoEvent@DiagHubCommon@@PEAX@Z@std@@PEAX@Z`
- size: `275`
- prototype: `__int64 __fastcall(_QWORD *lpParameter, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x140007f38`

## callees

- `0x140008b94`
- `0x140008ca8`
- `0x1400137e0`
- `0x140014c70`

## import_xrefs

- `KERNEL32!CreateThread` at `0x140008c1e`
- `KERNEL32!CreateThread` at `0x140008c1e`
- `KERNEL32!GetLastError` at `0x140008c29`
- `KERNEL32!GetLastError` at `0x140008c29`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DiagHubCommon::HubTask<long,0>::Start(_QWORD *lpParameter, __int64 a2)
{
  __int64 v2; // rbx
  __int64 v4; // rcx
  HANDLE v6; // rax
  __int64 v7; // rdx
  signed int LastError; // eax
  __int64 v9; // rdx
  unsigned int v10; // edi
  __int64 v11; // rcx
  __int64 v12; // rcx
  DWORD ThreadId; // [rsp+38h] [rbp-20h] BYREF

  v2 = a2;
  if ( lpParameter[1] )
  {
    v4 = *(_QWORD *)(a2 + 56);
    if ( v4 )
    {
      LOBYTE(a2) = v4 != a2;
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 32LL))(v4, a2);
      *(_QWORD *)(v2 + 56) = 0;
    }
    return 2147942405LL;
  }
  else
  {
    std::function<long (DiagHubCommon::AutoEvent const &,void *)>::operator=((__int64)(lpParameter + 2), a2);
    lpParameter[10] = 0;
    v6 = CreateThread(0, 0, DiagHubCommon::HubTask<long,0>::ThreadMain, lpParameter, 0, &ThreadId);
    if ( v6 )
    {
      lpParameter[1] = v6;
      v12 = *(_QWORD *)(v2 + 56);
      if ( v12 )
      {
        LOBYTE(v7) = v12 != v2;
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v12 + 32LL))(v12, v7);
        *(_QWORD *)(v2 + 56) = 0;
      }
      return 0;
    }
    else
    {
      LastError = GetLastError();
      v10 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v10 = LastError;
      v11 = *(_QWORD *)(v2 + 56);
      if ( v11 )
      {
        LOBYTE(v9) = v11 != v2;
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v11 + 32LL))(v11, v9);
        *(_QWORD *)(v2 + 56) = 0;
      }
      return v10;
    }
  }
}

```

## disassembly

```asm
0x140008b94  mov     [rsp+arg_10], rbx
0x140008b99  push    rdi
0x140008b9a  sub     rsp, 50h
0x140008b9e  mov     rax, cs:__security_cookie
0x140008ba5  xor     rax, rsp
0x140008ba8  mov     [rsp+58h+var_18], rax
0x140008bad  mov     rbx, rdx
0x140008bb0  mov     rdi, rcx
0x140008bb3  mov     [rsp+58h+var_28], rdx
0x140008bb8  cmp     qword ptr [rcx+8], 0
0x140008bbd  jz      short loc_140008BED
0x140008bbf  mov     rcx, [rdx+38h]
0x140008bc3  test    rcx, rcx
0x140008bc6  jz      short loc_140008BE3
0x140008bc8  cmp     rcx, rdx
0x140008bcb  setnz   dl
0x140008bce  mov     rax, [rcx]
0x140008bd1  mov     rax, [rax+20h]
0x140008bd5  call    cs:__guard_dispatch_icall_fptr
0x140008bdb  mov     qword ptr [rbx+38h], 0
0x140008be3  mov     eax, 80070005h
0x140008be8  jmp     loc_140008C8F
0x140008bed  add     rcx, 10h
0x140008bf1  call    ??4?$function@$$A6AJAEBVAutoEvent@DiagHubCommon@@PEAX@Z@std@@QEAAAEAV01@AEBV01@@Z; std::function<long (DiagHubCommon::AutoEvent const &,void *)>::operator=(std::function<long (DiagHubCommon::AutoEvent const &,void *)> const &)
0x140008bf6  mov     qword ptr [rdi+50h], 0
0x140008bfe  lea     rax, [rsp+58h+ThreadId]
0x140008c03  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x140008c08  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x140008c10  mov     r9, rdi; lpParameter
0x140008c13  lea     r8, ?ThreadMain@?$HubTask@J$0A@@DiagHubCommon@@CAKPEAX@Z; lpStartAddress
0x140008c1a  xor     edx, edx; dwStackSize
0x140008c1c  xor     ecx, ecx; lpThreadAttributes
0x140008c1e  call    cs:__imp_CreateThread
0x140008c24  test    rax, rax
0x140008c27  jnz     short loc_140008C65
0x140008c29  call    cs:__imp_GetLastError
0x140008c2f  movzx   edi, ax
0x140008c32  or      edi, 80070000h
0x140008c38  test    eax, eax
0x140008c3a  cmovle  edi, eax
0x140008c3d  mov     rcx, [rbx+38h]
0x140008c41  test    rcx, rcx
0x140008c44  jz      short loc_140008C61
0x140008c46  cmp     rcx, rbx
0x140008c49  setnz   dl
0x140008c4c  mov     r8, [rcx]
0x140008c4f  mov     rax, [r8+20h]
0x140008c53  call    cs:__guard_dispatch_icall_fptr
0x140008c59  mov     qword ptr [rbx+38h], 0
0x140008c61  mov     eax, edi
0x140008c63  jmp     short loc_140008C8F
0x140008c65  mov     [rdi+8], rax
0x140008c69  mov     rcx, [rbx+38h]
0x140008c6d  test    rcx, rcx
0x140008c70  jz      short loc_140008C8D
0x140008c72  cmp     rcx, rbx
0x140008c75  setnz   dl
0x140008c78  mov     rax, [rcx]
0x140008c7b  mov     rax, [rax+20h]
0x140008c7f  call    cs:__guard_dispatch_icall_fptr
0x140008c85  mov     qword ptr [rbx+38h], 0
0x140008c8d  xor     eax, eax
0x140008c8f  mov     rcx, [rsp+58h+var_18]
0x140008c94  xor     rcx, rsp; StackCookie
0x140008c97  call    __security_check_cookie
0x140008c9c  mov     rbx, [rsp+58h+arg_10]
0x140008ca1  add     rsp, 50h
0x140008ca5  pop     rdi
0x140008ca6  retn
```
