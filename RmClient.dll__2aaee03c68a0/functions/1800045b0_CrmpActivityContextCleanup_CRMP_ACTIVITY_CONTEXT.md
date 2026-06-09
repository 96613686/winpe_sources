# CrmpActivityContextCleanup(_CRMP_ACTIVITY_CONTEXT *)

- ea: `0x1800045b0`
- end: `0x180004639`
- name: `?CrmpActivityContextCleanup@@YAXPEAU_CRMP_ACTIVITY_CONTEXT@@@Z`
- size: `137`
- prototype: `void __fastcall(struct _CRMP_ACTIVITY_CONTEXT *)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800041e0`
- `0x1800042d0`
- `0x180004570`

## callees

- `0x1800045b0`
- `0x180004640`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800045d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800045d0`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180004631`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180004631`
- `RPCRT4!NdrClientCall3` at `0x18000460d`
- `RPCRT4!NdrClientCall3` at `0x18000460d`
- `RPCRT4!RpcExceptionFilter` at `0x18001b16e`
- `RPCRT4!RpcExceptionFilter` at `0x18001b16e`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000461c`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000461c`
- `ext-ms-win-resourcemanager-crm-private-ext-l1-1-0!CrmpInProcActivityFree` at `0x180004629`
- `ext-ms-win-resourcemanager-crm-private-ext-l1-1-0!CrmpInProcActivityFree` at `0x180004629`

## pseudocode

```c
void __fastcall CrmpActivityContextCleanup(struct _CRMP_ACTIVITY_CONTEXT *a1)
{
  void *v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rax

  CrmpActivityWindowClosedReasonUnsubscribe(a1);
  if ( *((_QWORD *)a1 + 6) )
    RtlUnsubscribeWnfNotificationWaitForCompletion();
  v2 = (void *)*((_QWORD *)a1 + 8);
  if ( v2 )
    CloseHandle(v2);
  v3 = *((_QWORD *)a1 + 1);
  if ( v3 != -1 )
  {
    v4 = *((_QWORD *)a1 + 2);
    if ( *(_QWORD *)(v4 + 16) )
      CrmpInProcActivityFree();
    else
      NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18001DC50, 4u, 0, v3, *(_QWORD *)(v4 + 8));
  }
}

```

## disassembly

```asm
0x1800045b0  push    rbx
0x1800045b2  sub     rsp, 30h
0x1800045b6  mov     rbx, rcx
0x1800045b9  call    ?CrmpActivityWindowClosedReasonUnsubscribe@@YAXPEAU_CRMP_ACTIVITY_CONTEXT@@@Z; CrmpActivityWindowClosedReasonUnsubscribe(_CRMP_ACTIVITY_CONTEXT *)
0x1800045be  mov     rcx, [rbx+30h]
0x1800045c2  test    rcx, rcx
0x1800045c5  jnz     short loc_180004631
0x1800045c7  mov     rcx, [rbx+40h]; hObject
0x1800045cb  test    rcx, rcx
0x1800045ce  jz      short loc_1800045D6
0x1800045d0  call    cs:__imp_CloseHandle
0x1800045d6  mov     rcx, [rbx+8]
0x1800045da  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800045de  jz      short loc_180004623
0x1800045e0  mov     rax, [rbx+10h]
0x1800045e4  mov     rdx, [rax+10h]
0x1800045e8  test    rdx, rdx
0x1800045eb  jnz     short loc_180004629
0x1800045ed  mov     rax, [rax+8]
0x1800045f1  mov     [rsp+38h+arg_0], rdx
0x1800045f6  mov     [rsp+38h+var_18], rax
0x1800045fb  mov     r9, rcx
0x1800045fe  xor     r8d, r8d; pReturnValue
0x180004601  mov     edx, 4; nProcNum
0x180004606  lea     rcx, stru_18001DC50; pProxyInfo
0x18000460d  call    cs:__imp_NdrClientCall3
0x180004613  mov     [rsp+38h+arg_0], rax
0x180004618  jmp     short loc_180004623
0x18000461a  mov     ecx, eax; Status
0x18000461c  call    cs:__imp_I_RpcMapWin32Status
0x180004622  nop
0x180004623  add     rsp, 30h
0x180004627  pop     rbx
0x180004628  retn
0x180004629  call    cs:__imp_CrmpInProcActivityFree
0x18000462f  jmp     short loc_180004623
0x180004631  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180004637  jmp     short loc_1800045C7
0x18001b160  push    rbp
0x18001b162  sub     rsp, 30h
0x18001b166  mov     rbp, rdx
0x18001b169  mov     rcx, [rcx]
0x18001b16c  mov     ecx, [rcx]; ExceptionCode
0x18001b16e  call    cs:__imp_RpcExceptionFilter
0x18001b174  nop
0x18001b175  add     rsp, 30h
0x18001b179  pop     rbp
0x18001b17a  retn
```
