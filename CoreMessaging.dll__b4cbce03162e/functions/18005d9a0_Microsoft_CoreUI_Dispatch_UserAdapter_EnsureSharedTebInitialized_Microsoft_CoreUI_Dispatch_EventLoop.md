# Microsoft::CoreUI::Dispatch::UserAdapter::EnsureSharedTebInitialized(Microsoft::CoreUI::Dispatch::EventLoop *)

- ea: `0x18005d9a0`
- end: `0x18005da83`
- name: `?EnsureSharedTebInitialized@UserAdapter@Dispatch@CoreUI@Microsoft@@SAXPEAVEventLoop@234@@Z`
- size: `227`
- prototype: `void __fastcall(struct Microsoft::CoreUI::Dispatch::EventLoop *)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180013ca0`
- `0x18005cd50`

## callees

- `0x18003773c`
- `0x18005c92c`
- `0x18005d9a0`
- `0x1800a1ae8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18005da01`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18005da01`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsGUIThread` at `0x18005da4c`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsGUIThread` at `0x18005da4c`

## pseudocode

```c
void __fastcall Microsoft::CoreUI::Dispatch::UserAdapter::EnsureSharedTebInitialized(
        struct Microsoft::CoreUI::Dispatch::EventLoop *a1)
{
  struct _TEB *v1; // rbx
  __int64 SpareUlong0; // rax
  _QWORD *v4; // rbx
  __int64 v5; // rax
  struct _TEB *v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rax
  const char *v9; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = NtCurrentTeb();
  SpareUlong0 = (int)v1->SpareUlong0;
  if ( (int)SpareUlong0 < 0 )
    v1 = (struct _TEB *)((char *)v1 + SpareUlong0);
  v4 = (_QWORD *)v1->Win32ClientInfo[61];
  if ( !v4 )
  {
    v5 = Cn::Engine::Heap::ProcessAllocate(a1, 48);
    v6 = NtCurrentTeb();
    v4 = (_QWORD *)v5;
    v7 = (int)v6->SpareUlong0;
    if ( (int)v7 < 0 )
      v6 = (struct _TEB *)((char *)v6 + v7);
    v6->Win32ClientInfo[61] = (SIZE_T)v4;
    *(_QWORD *)(*((_QWORD *)TlsGetValue(Cn::Context::s_tlsStorage) + 6) + 64LL) = v4;
  }
  if ( !*v4 )
    *v4 = &Microsoft::CoreUI::Dispatch::UserAdapter::OnGuiThreadInitCallback;
  v8 = v4[3];
  if ( v8 && *(_DWORD *)v8 >= 2u )
  {
    if ( (*(_BYTE *)(v8 + 16) & 1) != 0 )
      *((_BYTE *)a1 + 32) = 1;
    Microsoft::CoreUI::Dispatch::UserAdapter::SetTlsFlags(2);
    if ( !IsGUIThread(1) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x318,
        (unsigned int)"mincore\\coreui\\dev\\system\\Dispatch\\minwin\\UserAdapterN.cpp",
        v9);
  }
}

```

## disassembly

```asm
0x18005d9a0  mov     [rsp+arg_0], rbx
0x18005d9a5  push    rdi
0x18005d9a6  sub     rsp, 20h
0x18005d9aa  mov     rbx, gs:30h
0x18005d9b3  mov     rdi, rcx
0x18005d9b6  movsxd  rax, dword ptr [rbx+180Ch]
0x18005d9bd  test    eax, eax
0x18005d9bf  js      loc_18005DA6D
0x18005d9c5  mov     rbx, [rbx+9E8h]
0x18005d9cc  test    rbx, rbx
0x18005d9cf  jnz     short loc_18005DA0F
0x18005d9d1  lea     edx, [rbx+30h]
0x18005d9d4  call    ?ProcessAllocate@Heap@Engine@Cn@@SAPEAXUAllocType@23@_K@Z; Cn::Engine::Heap::ProcessAllocate(Cn::Engine::AllocType,unsigned __int64)
0x18005d9d9  mov     rcx, gs:30h
0x18005d9e2  mov     rbx, rax
0x18005d9e5  movsxd  rax, dword ptr [rcx+180Ch]
0x18005d9ec  test    eax, eax
0x18005d9ee  js      loc_18005DA75
0x18005d9f4  mov     [rcx+9E8h], rbx
0x18005d9fb  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18005da01  call    cs:__imp_TlsGetValue
0x18005da07  mov     rcx, [rax+30h]
0x18005da0b  mov     [rcx+40h], rbx
0x18005da0f  cmp     qword ptr [rbx], 0
0x18005da13  jnz     short loc_18005DA1F
0x18005da15  lea     rax, ?OnGuiThreadInitCallback@UserAdapter@Dispatch@CoreUI@Microsoft@@SAXW4tagCoreMessagingNotification@@IPEAX@Z; Microsoft::CoreUI::Dispatch::UserAdapter::OnGuiThreadInitCallback(tagCoreMessagingNotification,uint,void *)
0x18005da1c  mov     [rbx], rax
0x18005da1f  mov     rax, [rbx+18h]
0x18005da23  test    rax, rax
0x18005da26  jnz     short loc_18005DA33
0x18005da28  mov     rbx, [rsp+28h+arg_0]
0x18005da2d  add     rsp, 20h
0x18005da31  pop     rdi
0x18005da32  retn
0x18005da33  mov     ecx, 2
0x18005da38  cmp     [rax], ecx
0x18005da3a  jb      short loc_18005DA28
0x18005da3c  test    byte ptr [rax+10h], 1
0x18005da40  jnz     short loc_18005DA7D
0x18005da42  call    ?SetTlsFlags@UserAdapter@Dispatch@CoreUI@Microsoft@@CAXW4UserAdapter$TlsFlags@234@@Z; Microsoft::CoreUI::Dispatch::UserAdapter::SetTlsFlags(Microsoft::CoreUI::Dispatch::UserAdapter$TlsFlags)
0x18005da47  mov     ecx, 1; bConvert
0x18005da4c  call    cs:__imp_IsGUIThread
0x18005da52  test    eax, eax
0x18005da54  jnz     short loc_18005DA28
0x18005da56  mov     rcx, [rsp+28h]; this
0x18005da5b  lea     r8, aMincoreCoreuiD_0; "mincore\\coreui\\dev\\system\\Dispatch"...
0x18005da62  mov     edx, 318h; void *
0x18005da67  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18005da6d  add     rbx, rax
0x18005da70  jmp     loc_18005D9C5
0x18005da75  add     rcx, rax
0x18005da78  jmp     loc_18005D9F4
0x18005da7d  mov     byte ptr [rdi+20h], 1
0x18005da81  jmp     short loc_18005DA42
```
