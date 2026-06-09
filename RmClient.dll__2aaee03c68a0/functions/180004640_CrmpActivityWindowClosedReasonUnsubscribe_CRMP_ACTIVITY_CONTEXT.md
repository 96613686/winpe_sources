# CrmpActivityWindowClosedReasonUnsubscribe(_CRMP_ACTIVITY_CONTEXT *)

- ea: `0x180004640`
- end: `0x1800046de`
- name: `?CrmpActivityWindowClosedReasonUnsubscribe@@YAXPEAU_CRMP_ACTIVITY_CONTEXT@@@Z`
- size: `158`
- prototype: `void __fastcall(struct _CRMP_ACTIVITY_CONTEXT *)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003dd0`
- `0x1800045b0`
- `0x180010384`

## callees

- `0x180004640`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180004656`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180004656`
- `RPCRT4!NdrClientCall3` at `0x1800046b1`
- `RPCRT4!NdrClientCall3` at `0x1800046b1`
- `RPCRT4!RpcExceptionFilter` at `0x18001b19e`
- `RPCRT4!RpcExceptionFilter` at `0x18001b19e`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800046c0`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800046c0`
- `ext-ms-win-resourcemanager-crm-private-ext-l1-1-0!CrmpInProcActivityWindowClosedReasonUnsubscribe` at `0x1800046d6`
- `ext-ms-win-resourcemanager-crm-private-ext-l1-1-0!CrmpInProcActivityWindowClosedReasonUnsubscribe` at `0x1800046d6`

## pseudocode

```c
void __fastcall CrmpActivityWindowClosedReasonUnsubscribe(struct _CRMP_ACTIVITY_CONTEXT *a1)
{
  __int64 v2; // rax

  if ( *((_QWORD *)a1 + 12) )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    *((_QWORD *)a1 + 12) = 0;
  }
  if ( *((_DWORD *)a1 + 22) || *((_DWORD *)a1 + 23) )
  {
    v2 = *((_QWORD *)a1 + 2);
    if ( *(_QWORD *)(v2 + 16) )
      CrmpInProcActivityWindowClosedReasonUnsubscribe(*((_QWORD *)a1 + 1));
    else
      NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18001DC50, 9u, 0, *((_QWORD *)a1 + 1), *(_QWORD *)(v2 + 8));
    *((_QWORD *)a1 + 11) = 0;
  }
}

```

## disassembly

```asm
0x180004640  mov     [rsp+arg_10], rbx
0x180004645  push    rdi
0x180004646  sub     rsp, 30h
0x18000464a  mov     rbx, rcx
0x18000464d  mov     rcx, [rcx+60h]
0x180004651  test    rcx, rcx
0x180004654  jz      short loc_180004664
0x180004656  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18000465c  mov     qword ptr [rbx+60h], 0
0x180004664  lea     rdi, [rbx+58h]
0x180004668  mov     [rsp+38h+arg_8], rdi
0x18000466d  cmp     dword ptr [rdi], 0
0x180004670  jnz     short loc_180004683
0x180004672  cmp     dword ptr [rbx+5Ch], 0
0x180004676  jnz     short loc_180004683
0x180004678  mov     rbx, [rsp+38h+arg_10]
0x18000467d  add     rsp, 30h
0x180004681  pop     rdi
0x180004682  retn
0x180004683  mov     rax, [rbx+10h]
0x180004687  mov     rdx, [rax+10h]
0x18000468b  test    rdx, rdx
0x18000468e  jnz     short loc_1800046D2
0x180004690  mov     rax, [rax+8]
0x180004694  mov     [rsp+38h+arg_0], rdx
0x180004699  mov     [rsp+38h+var_18], rax
0x18000469e  mov     r9, [rbx+8]
0x1800046a2  xor     r8d, r8d; pReturnValue
0x1800046a5  mov     edx, 9; nProcNum
0x1800046aa  lea     rcx, stru_18001DC50; pProxyInfo
0x1800046b1  call    cs:__imp_NdrClientCall3
0x1800046b7  mov     [rsp+38h+arg_0], rax
0x1800046bc  jmp     short loc_1800046CB
0x1800046be  mov     ecx, eax; Status
0x1800046c0  call    cs:__imp_I_RpcMapWin32Status
0x1800046c6  mov     rdi, [rsp+38h+arg_8]
0x1800046cb  xor     eax, eax
0x1800046cd  mov     [rdi], rax
0x1800046d0  jmp     short loc_180004678
0x1800046d2  mov     rcx, [rbx+8]
0x1800046d6  call    cs:__imp_CrmpInProcActivityWindowClosedReasonUnsubscribe
0x1800046dc  jmp     short loc_1800046CB
0x18001b190  push    rbp
0x18001b192  sub     rsp, 30h
0x18001b196  mov     rbp, rdx
0x18001b199  mov     rcx, [rcx]
0x18001b19c  mov     ecx, [rcx]; ExceptionCode
0x18001b19e  call    cs:__imp_RpcExceptionFilter
0x18001b1a4  nop
0x18001b1a5  add     rsp, 30h
0x18001b1a9  pop     rbp
0x18001b1aa  retn
```
