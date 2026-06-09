# Microsoft::CoreUI::Dispatch::UserAdapter::OnUserQueueReportsEmpty(void)

- ea: `0x1800158ac`
- end: `0x180015906`
- name: `?OnUserQueueReportsEmpty@UserAdapter@Dispatch@CoreUI@Microsoft@@AEAA_NXZ`
- size: `90`
- prototype: `bool __fastcall(Microsoft::CoreUI::Dispatch::UserAdapter *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800155ac`

## callees

- `0x180008354`
- `0x1800158ac`

## import_xrefs

- `ext-ms-win-rtcore-ntuser-integration-l1-1-0!__imp_GetQueueStatusReadonly` at `0x1800158be`
- `ext-ms-win-rtcore-ntuser-integration-l1-1-0!__imp_GetQueueStatusReadonly` at `0x1800158be`

## pseudocode

```c
char __fastcall Microsoft::CoreUI::Dispatch::UserAdapter::OnUserQueueReportsEmpty(
        Microsoft::CoreUI::Dispatch::UserAdapter *this)
{
  char v2; // bl
  int v3; // edx

  if ( (GetQueueStatusReadonly(8) & 0x80000) != 0 )
    return 1;
  v2 = 0;
  v3 = *(_DWORD *)(*((_QWORD *)this + 5) + 24LL);
  *((_BYTE *)this + 80) = (v3 & 8) != 0;
  if ( (v3 & 8) != 0 )
    Microsoft::CoreUI::Dispatch::UserAdapter::DrainCoreMessagingQueue((__int64)this, 3, 0);
  return v2;
}

```

## disassembly

```asm
0x1800158ac  mov     [rsp+arg_0], rbx
0x1800158b1  push    rdi
0x1800158b2  sub     rsp, 20h
0x1800158b6  mov     rdi, rcx
0x1800158b9  mov     ecx, 8
0x1800158be  call    cs:__imp_GetQueueStatusReadonly
0x1800158c4  shr     eax, 10h
0x1800158c7  test    al, 8
0x1800158c9  jnz     short loc_180015902
0x1800158cb  mov     rcx, [rdi+28h]
0x1800158cf  xor     bl, bl
0x1800158d1  mov     edx, [rcx+18h]
0x1800158d4  bt      edx, 3
0x1800158d8  setb    cl
0x1800158db  mov     [rdi+50h], cl
0x1800158de  bt      edx, 3
0x1800158e2  jb      short loc_1800158F1
0x1800158e4  mov     al, bl
0x1800158e6  mov     rbx, [rsp+28h+arg_0]
0x1800158eb  add     rsp, 20h
0x1800158ef  pop     rdi
0x1800158f0  retn
0x1800158f1  xor     r8d, r8d
0x1800158f4  mov     rcx, rdi
0x1800158f7  lea     edx, [r8+3]
0x1800158fb  call    ?DrainCoreMessagingQueue@UserAdapter@Dispatch@CoreUI@Microsoft@@AEAAXW4UserAdapter$UserPriority@234@PEAPEAX@Z; Microsoft::CoreUI::Dispatch::UserAdapter::DrainCoreMessagingQueue(Microsoft::CoreUI::Dispatch::UserAdapter$UserPriority,void * *)
0x180015900  jmp     short loc_1800158E4
0x180015902  mov     bl, 1
0x180015904  jmp     short loc_1800158E4
```
