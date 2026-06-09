# Microsoft::Bluetooth::Foundation::Details::DedicatedThreadRequestDispatcher::IoThread(void)

- ea: `0x18001d1f0`
- end: `0x18001d309`
- name: `?IoThread@DedicatedThreadRequestDispatcher@Details@Foundation@Bluetooth@Microsoft@@AEAAXXZ`
- size: `281`
- prototype: `void __fastcall(Microsoft::Bluetooth::Foundation::Details::DedicatedThreadRequestDispatcher *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18001c6d0`
- `0x18001d1f0`
- `0x18001d310`
- `0x18001daa0`
- `0x18001f3d4`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18001d272`
- `ntdll!RtlNtStatusToDosError` at `0x18001d272`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d210`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d210`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18001d21b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18001d21b`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatusEx` at `0x18001d2de`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatusEx` at `0x18001d2de`

## pseudocode

```c
void __fastcall Microsoft::Bluetooth::Foundation::Details::DedicatedThreadRequestDispatcher::IoThread(
        Microsoft::Bluetooth::Foundation::Details::DedicatedThreadRequestDispatcher *this)
{
  int v1; // edi
  HANDLE CurrentThread; // rax
  void *v4; // rdx
  unsigned int v5; // r8d
  const char *v6; // r9
  ULONG v7; // eax
  char v8; // bp
  ULONG v9; // esi
  __int64 v10; // rdi
  NTSTATUS *v11; // rcx
  ULONG v12; // eax
  void *v13; // rcx
  void *v14; // rdx
  unsigned int v15; // r8d
  const char *v16; // r9
  const struct Microsoft::Bluetooth::Foundation::DeviceIoTarget::OnRequestCompletedPassKey *dwMilliseconds; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  ULONG ulNumEntriesRemoved; // [rsp+50h] [rbp+8h] BYREF

  v1 = *((_DWORD *)this + 4);
  if ( v1 )
  {
    CurrentThread = GetCurrentThread();
    if ( !SetThreadPriority(CurrentThread, v1) )
      wil::details::in1diag3::_Log_GetLastError(retaddr, v4, v5, v6);
  }
  while ( 1 )
  {
    v13 = (void *)*((_QWORD *)this + 4);
    ulNumEntriesRemoved = 0;
    if ( !GetQueuedCompletionStatusEx(v13, (LPOVERLAPPED_ENTRY)this + 2, 0x10u, &ulNumEntriesRemoved, 0xFFFFFFFF, 0) )
      break;
    v7 = ulNumEntriesRemoved;
    v8 = 0;
    v9 = 0;
    if ( ulNumEntriesRemoved )
    {
      do
      {
        v10 = 32 * (v9 + 2LL);
        if ( *(_QWORD *)((char *)this + v10) == 348450623 )
        {
          v8 = 1;
        }
        else
        {
          v11 = *(NTSTATUS **)((char *)this + v10 + 8);
          if ( v11 )
          {
            if ( *(_QWORD *)((char *)this + v10) == 3348278312LL )
            {
              v12 = RtlNtStatusToDosError(*v11);
              Microsoft::Bluetooth::Foundation::DeviceIoTarget::OnRequestCompleted(
                *((Microsoft::Bluetooth::Foundation::DeviceIoTarget **)this + 1),
                (struct Microsoft::Bluetooth::Foundation::Details::IoTargetRequest *)((*(_QWORD *)((char *)this + v10 + 8)
                                                                                     - 8LL)
                                                                                    & -(__int64)(*(_QWORD *)((char *)this + v10 + 8) != 0)),
                v12,
                *(_DWORD *)((char *)this + v10 + 24),
                dwMilliseconds);
              Microsoft::Bluetooth::Foundation::Details::CountdownEvent::Decrement((Microsoft::Bluetooth::Foundation::Details::DedicatedThreadRequestDispatcher *)((char *)this + 56));
              v7 = ulNumEntriesRemoved;
            }
          }
        }
        ++v9;
      }
      while ( v9 < v7 );
      if ( v8 )
        return;
    }
  }
  wil::details::in1diag3::Log_GetLastError(retaddr, v14, v15, v16);
}

```

## disassembly

```asm
0x18001d1f0  mov     [rsp+arg_8], rbx
0x18001d1f5  mov     [rsp+arg_10], rbp
0x18001d1fa  push    rsi
0x18001d1fb  push    rdi
0x18001d1fc  push    r14
0x18001d1fe  sub     rsp, 30h
0x18001d202  mov     edi, [rcx+10h]
0x18001d205  mov     rbx, rcx
0x18001d208  test    edi, edi
0x18001d20a  jz      loc_18001D2B3
0x18001d210  call    cs:__imp_GetCurrentThread
0x18001d216  mov     rcx, rax; hThread
0x18001d219  mov     edx, edi; nPriority
0x18001d21b  call    cs:__imp_SetThreadPriority
0x18001d221  test    eax, eax
0x18001d223  jnz     loc_18001D2B3
0x18001d229  mov     rcx, [rsp+48h]; this
0x18001d22e  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18001d233  jmp     short loc_18001D2B3
0x18001d235  mov     eax, [rsp+48h+ulNumEntriesRemoved]
0x18001d239  xor     bpl, bpl
0x18001d23c  xor     esi, esi
0x18001d23e  test    eax, eax
0x18001d240  jz      short loc_18001D2B3
0x18001d242  mov     edi, esi
0x18001d244  add     rdi, 2
0x18001d248  shl     rdi, 5
0x18001d24c  cmp     qword ptr [rdi+rbx], 14C4EF3Fh
0x18001d254  jnz     short loc_18001D25B
0x18001d256  mov     bpl, 1
0x18001d259  jmp     short loc_18001D2A8
0x18001d25b  mov     rcx, [rdi+rbx+8]
0x18001d260  test    rcx, rcx
0x18001d263  jz      short loc_18001D2A8
0x18001d265  mov     edx, 0C792AC28h
0x18001d26a  cmp     [rdi+rbx], rdx
0x18001d26e  jnz     short loc_18001D2A8
0x18001d270  mov     ecx, [rcx]; Status
0x18001d272  call    cs:__imp_RtlNtStatusToDosError
0x18001d278  mov     rcx, [rdi+rbx+8]
0x18001d27d  mov     r9d, [rdi+rbx+18h]; unsigned int
0x18001d282  lea     r8, [rcx-8]
0x18001d286  neg     rcx
0x18001d289  mov     rcx, [rbx+8]; this
0x18001d28d  sbb     rdx, rdx
0x18001d290  and     rdx, r8; struct Microsoft::Bluetooth::Foundation::Details::IoTargetRequest *
0x18001d293  mov     r8d, eax; unsigned int
0x18001d296  call    ?OnRequestCompleted@DeviceIoTarget@Foundation@Bluetooth@Microsoft@@QEAAXAEAVIoTargetRequest@Details@234@IIAEBUOnRequestCompletedPassKey@1234@@Z; Microsoft::Bluetooth::Foundation::DeviceIoTarget::OnRequestCompleted(Microsoft::Bluetooth::Foundation::Details::IoTargetRequest &,uint,uint,Microsoft::Bluetooth::Foundation::DeviceIoTarget::OnRequestCompletedPassKey const &)
0x18001d29b  lea     rcx, [rbx+38h]; this
0x18001d29f  call    ?Decrement@CountdownEvent@Details@Foundation@Bluetooth@Microsoft@@QEAAXXZ; Microsoft::Bluetooth::Foundation::Details::CountdownEvent::Decrement(void)
0x18001d2a4  mov     eax, [rsp+48h+ulNumEntriesRemoved]
0x18001d2a8  inc     esi
0x18001d2aa  cmp     esi, eax
0x18001d2ac  jb      short loc_18001D242
0x18001d2ae  test    bpl, bpl
0x18001d2b1  jnz     short loc_18001D2F6
0x18001d2b3  mov     rcx, [rbx+20h]; CompletionPort
0x18001d2b7  lea     r9, [rsp+48h+ulNumEntriesRemoved]; ulNumEntriesRemoved
0x18001d2bc  mov     [rsp+48h+fAlertable], 0; fAlertable
0x18001d2c4  lea     rdx, [rbx+40h]; lpCompletionPortEntries
0x18001d2c8  mov     r8d, 10h; ulCount
0x18001d2ce  mov     dword ptr [rsp+48h+dwMilliseconds], 0FFFFFFFFh; struct Microsoft::Bluetooth::Foundation::DeviceIoTarget::OnRequestCompletedPassKey *
0x18001d2d6  mov     [rsp+48h+ulNumEntriesRemoved], 0
0x18001d2de  call    cs:__imp_GetQueuedCompletionStatusEx
0x18001d2e4  test    eax, eax
0x18001d2e6  jnz     loc_18001D235
0x18001d2ec  mov     rcx, [rsp+48h]; this
0x18001d2f1  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x18001d2f6  mov     rbx, [rsp+48h+arg_8]
0x18001d2fb  mov     rbp, [rsp+48h+arg_10]
0x18001d300  add     rsp, 30h
0x18001d304  pop     r14
0x18001d306  pop     rdi
0x18001d307  pop     rsi
0x18001d308  retn
```
