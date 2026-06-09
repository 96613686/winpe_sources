# CrmpActivityContextStart(_CRMP_ACTIVITY_CONTEXT *,_CRMP_REGISTRATION_CONTEXT *,_CRM_ACTIVITY_ID,_ACTIVITY_COORDINATOR_RESOURCE_CONDITIONS *,ushort *,ulong *,void (*)(void *,void *,_CRM_NOTIFICATION_TYPE,void *,void *),void *)

- ea: `0x1800043b0`
- end: `0x180004545`
- name: `?CrmpActivityContextStart@@YAJPEAU_CRMP_ACTIVITY_CONTEXT@@PEAU_CRMP_REGISTRATION_CONTEXT@@W4_CRM_ACTIVITY_ID@@PEAU_ACTIVITY_COORDINATOR_RESOURCE_CONDITIONS@@PEAGPEAKP6AXPEAX6W4_CRM_NOTIFICATION_TYPE@@66@Z6@Z`
- size: `405`
- prototype: `int __fastcall(__int64, __int64, unsigned int, __int64, __int64, _DWORD *, __int64, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800041e0`
- `0x1800042d0`

## callees

- `0x1800043b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800043e9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800043e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004523`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000452d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004535`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004523`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000452d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004535`
- `RPCRT4!NdrClientCall3` at `0x180004457`
- `RPCRT4!NdrClientCall3` at `0x180004457`
- `RPCRT4!RpcExceptionFilter` at `0x18001b13e`
- `RPCRT4!RpcExceptionFilter` at `0x18001b13e`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000446a`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000446a`
- `ext-ms-win-resourcemanager-crm-private-ext-l1-1-0!CrmpInProcActivityAllocate` at `0x180004507`
- `ext-ms-win-resourcemanager-crm-private-ext-l1-1-0!CrmpInProcActivityAllocate` at `0x180004507`

## pseudocode

```c
int __fastcall CrmpActivityContextStart(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        _DWORD *a6,
        __int64 a7,
        __int64 a8)
{
  HANDLE EventW; // rax
  __int64 v13; // rdx
  __int64 v14; // rcx
  _DWORD *v15; // r15
  CLIENT_CALL_RETURN v16; // rax
  __int64 v18; // [rsp+58h] [rbp-40h] BYREF
  CLIENT_CALL_RETURN v19; // [rsp+60h] [rbp-38h]

  v18 = -1;
  EventW = CreateEventW(0, 0, 0, 0);
  *(_QWORD *)(a1 + 64) = EventW;
  if ( EventW )
  {
    v13 = *(_QWORD *)(a2 + 16);
    if ( v13 )
    {
      v15 = a6;
      LODWORD(v16.Pointer) = CrmpInProcActivityAllocate(&v18, v13, a3, a4, a5, a1 + 40, a6);
    }
    else
    {
      v14 = *(_QWORD *)(a2 + 8);
      v19.Simple = 0;
      v15 = a6;
      v16.Pointer = NdrClientCall3(
                      (MIDL_STUBLESS_PROXY_INFO *)&stru_18001DC50,
                      2u,
                      0,
                      &v18,
                      v14,
                      a3,
                      a4,
                      a5,
                      a1 + 40,
                      a6).Pointer;
      v19.Pointer = v16.Pointer;
    }
    if ( SLODWORD(v16.Simple) >= 0 )
    {
      *(_QWORD *)(a1 + 16) = a2;
      *(_DWORD *)a1 = a3;
      *(_QWORD *)(a1 + 24) = a7;
      *(_QWORD *)(a1 + 32) = a8;
      *(_QWORD *)(a1 + 8) = v18;
      if ( v15 )
      {
        *(_DWORD *)(a1 + 56) = *v15;
        LODWORD(v16.Pointer) = 0;
      }
      else
      {
        *(_DWORD *)(a1 + 56) = -1;
        LODWORD(v16.Pointer) = 0;
      }
    }
  }
  else if ( (int)GetLastError() > 0 )
  {
    LODWORD(v16.Pointer) = (unsigned __int16)GetLastError() | 0xC0070000;
  }
  else
  {
    LODWORD(v16.Pointer) = GetLastError();
  }
  return (int)v16.Pointer;
}

```

## disassembly

```asm
0x1800043b0  mov     [rsp+arg_10], r8d
0x1800043b5  mov     [rsp+arg_8], rdx
0x1800043ba  mov     [rsp+arg_0], rcx
0x1800043bf  push    rbx
0x1800043c0  push    rsi
0x1800043c1  push    rdi
0x1800043c2  push    r14
0x1800043c4  push    r15
0x1800043c6  sub     rsp, 70h
0x1800043ca  mov     r14, r9
0x1800043cd  mov     esi, r8d
0x1800043d0  mov     rdi, rdx
0x1800043d3  mov     rbx, rcx
0x1800043d6  mov     [rsp+98h+var_40], 0FFFFFFFFFFFFFFFFh
0x1800043df  xor     r9d, r9d; lpName
0x1800043e2  xor     r8d, r8d; bInitialState
0x1800043e5  xor     edx, edx; bManualReset
0x1800043e7  xor     ecx, ecx; lpEventAttributes
0x1800043e9  call    cs:__imp_CreateEventW
0x1800043ef  mov     [rbx+40h], rax
0x1800043f3  test    rax, rax
0x1800043f6  jz      loc_180004523
0x1800043fc  mov     rdx, [rdi+10h]
0x180004400  test    rdx, rdx
0x180004403  jnz     loc_1800044D9
0x180004409  mov     rcx, [rdi+8]
0x18000440d  mov     [rsp+98h+var_38], rdx
0x180004412  lea     rax, [rbx+28h]
0x180004416  mov     r15, [rsp+98h+arg_28]
0x18000441e  mov     [rsp+98h+var_50], r15
0x180004423  mov     [rsp+98h+var_58], rax
0x180004428  mov     rax, [rsp+98h+arg_20]
0x180004430  mov     [rsp+98h+var_60], rax
0x180004435  mov     [rsp+98h+var_68], r14
0x18000443a  mov     dword ptr [rsp+98h+var_70], esi
0x18000443e  mov     [rsp+98h+var_78], rcx
0x180004443  lea     r9, [rsp+98h+var_40]
0x180004448  xor     r8d, r8d; pReturnValue
0x18000444b  mov     edx, 2; nProcNum
0x180004450  lea     rcx, stru_18001DC50; pProxyInfo
0x180004457  call    cs:__imp_NdrClientCall3
0x18000445d  mov     [rsp+98h+var_38], rax
0x180004462  mov     [rsp+98h+var_48], eax
0x180004466  jmp     short loc_180004493
0x180004468  mov     ecx, eax; Status
0x18000446a  call    cs:__imp_I_RpcMapWin32Status
0x180004470  mov     [rsp+98h+var_48], eax
0x180004474  mov     r15, [rsp+98h+arg_28]
0x18000447c  mov     esi, [rsp+98h+arg_10]
0x180004483  mov     rdi, [rsp+98h+arg_8]
0x18000448b  mov     rbx, [rsp+98h+arg_0]
0x180004493  test    eax, eax
0x180004495  js      short loc_1800044CD
0x180004497  mov     [rbx+10h], rdi
0x18000449b  mov     [rbx], esi
0x18000449d  mov     rax, [rsp+98h+arg_30]
0x1800044a5  mov     [rbx+18h], rax
0x1800044a9  mov     rax, [rsp+98h+arg_38]
0x1800044b1  mov     [rbx+20h], rax
0x1800044b5  mov     rax, [rsp+98h+var_40]
0x1800044ba  mov     [rbx+8], rax
0x1800044be  test    r15, r15
0x1800044c1  jnz     short loc_18000450F
0x1800044c3  mov     eax, 0FFFFFFFFh
0x1800044c8  mov     [rbx+38h], eax
0x1800044cb  xor     eax, eax
0x1800044cd  add     rsp, 70h
0x1800044d1  pop     r15
0x1800044d3  pop     r14
0x1800044d5  pop     rdi
0x1800044d6  pop     rsi
0x1800044d7  pop     rbx
0x1800044d8  retn
0x1800044d9  lea     rax, [rbx+28h]
0x1800044dd  mov     r15, [rsp+98h+arg_28]
0x1800044e5  mov     [rsp+98h+var_68], r15
0x1800044ea  mov     [rsp+98h+var_70], rax
0x1800044ef  mov     rax, [rsp+98h+arg_20]
0x1800044f7  mov     [rsp+98h+var_78], rax
0x1800044fc  mov     r9, r14
0x1800044ff  mov     r8d, esi
0x180004502  lea     rcx, [rsp+98h+var_40]
0x180004507  call    cs:__imp_CrmpInProcActivityAllocate
0x18000450d  jmp     short loc_180004493
0x18000450f  mov     eax, [r15]
0x180004512  mov     [rbx+38h], eax
0x180004515  xor     eax, eax
0x180004517  add     rsp, 70h
0x18000451b  pop     r15
0x18000451d  pop     r14
0x18000451f  pop     rdi
0x180004520  pop     rsi
0x180004521  pop     rbx
0x180004522  retn
0x180004523  call    cs:__imp_GetLastError
0x180004529  test    eax, eax
0x18000452b  jg      short loc_180004535
0x18000452d  call    cs:__imp_GetLastError
0x180004533  jmp     short loc_1800044CD
0x180004535  call    cs:__imp_GetLastError
0x18000453b  movzx   eax, ax
0x18000453e  or      eax, 0C0070000h
0x180004543  jmp     short loc_1800044CD
0x18001b130  push    rbp
0x18001b132  sub     rsp, 50h
0x18001b136  mov     rbp, rdx
0x18001b139  mov     rcx, [rcx]
0x18001b13c  mov     ecx, [rcx]; ExceptionCode
0x18001b13e  call    cs:__imp_RpcExceptionFilter
0x18001b144  nop
0x18001b145  add     rsp, 50h
0x18001b149  pop     rbp
0x18001b14a  retn
```
