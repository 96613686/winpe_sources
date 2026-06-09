# Microsoft::CoreUI::Dispatch::EventLoop::get_IsRunningOnOtherThread(void)

- ea: `0x180026a10`
- end: `0x180026a60`
- name: `?get_IsRunningOnOtherThread@EventLoop@Dispatch@CoreUI@Microsoft@@QEAA_NXZ`
- size: `80`
- prototype: `bool __fastcall(Microsoft::CoreUI::Dispatch::EventLoop *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180026628`
- `0x180026914`

## callees

- `0x180026a10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026a2e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026a4d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026a2e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026a4d`

## pseudocode

```c
bool __fastcall Microsoft::CoreUI::Dispatch::EventLoop::get_IsRunningOnOtherThread(
        Microsoft::CoreUI::Dispatch::EventLoop *this)
{
  __int64 v2; // rdi
  bool result; // al
  __int64 v4; // rbx

  result = 0;
  if ( *((_DWORD *)this + 16) || *((_DWORD *)this + 18) )
  {
    v2 = *((_QWORD *)this + 6);
    if ( GetCurrentThreadId() != *(_DWORD *)(v2 + 176) )
    {
      v4 = *((_QWORD *)this + 7);
      if ( GetCurrentThreadId() != *(_DWORD *)(v4 + 64) )
        return 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180026a10  push    rbx
0x180026a12  sub     rsp, 20h
0x180026a16  cmp     dword ptr [rcx+40h], 0
0x180026a1a  mov     rbx, rcx
0x180026a1d  jnz     short loc_180026A25
0x180026a1f  cmp     dword ptr [rcx+48h], 0
0x180026a23  jz      short loc_180026A41
0x180026a25  mov     [rsp+28h+arg_0], rdi
0x180026a2a  mov     rdi, [rcx+30h]
0x180026a2e  call    cs:__imp_GetCurrentThreadId
0x180026a34  cmp     eax, [rdi+0B0h]
0x180026a3a  mov     rdi, [rsp+28h+arg_0]
0x180026a3f  jnz     short loc_180026A49
0x180026a41  xor     al, al
0x180026a43  add     rsp, 20h
0x180026a47  pop     rbx
0x180026a48  retn
0x180026a49  mov     rbx, [rbx+38h]
0x180026a4d  call    cs:__imp_GetCurrentThreadId
0x180026a53  cmp     eax, [rbx+40h]
0x180026a56  jz      short loc_180026A41
0x180026a58  mov     al, 1
0x180026a5a  add     rsp, 20h
0x180026a5e  pop     rbx
0x180026a5f  retn
```
