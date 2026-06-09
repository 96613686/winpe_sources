# _anonymous_namespace_::CancelThread

- ea: `0x18003a0b4`
- end: `0x18003a13a`
- name: `_anonymous_namespace_::CancelThread`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003a140`
- `0x18003a9f4`

## callees

- `0x18003a0b4`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!QueueUserAPC` at `0x18003a11f`
- `api-ms-win-core-processthreads-l1-1-0!QueueUserAPC` at `0x18003a11f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18003a104`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18003a104`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a12e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a12e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostThreadMessageW` at `0x18003a0f6`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostThreadMessageW` at `0x18003a0f6`

## pseudocode

```c
int __fastcall anonymous_namespace_::CancelThread(__int64 a1)
{
  __int64 v2; // rcx
  HANDLE v3; // rax
  void *v4; // rbx

  _InterlockedExchange((volatile __int32 *)(a1 + 12), 1);
  v2 = *(_QWORD *)(a1 + 72);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  if ( *(_BYTE *)(a1 + 9) )
    PostThreadMessageW(*(_DWORD *)a1, 0, 0, 0);
  v3 = OpenThread(0x10u, 0, *(_DWORD *)a1);
  v4 = v3;
  if ( v3 )
  {
    LODWORD(v3) = QueueUserAPC(Com::Module::Initialize, v3, 0);
    if ( v4 != (void *)-1LL )
      LODWORD(v3) = CloseHandle(v4);
  }
  return (int)v3;
}

```

## disassembly

```asm
0x18003a0b4  push    rbx
0x18003a0b6  sub     rsp, 20h
0x18003a0ba  mov     [rsp+28h+arg_0], 0
0x18003a0c2  mov     rbx, rcx
0x18003a0c5  mov     byte ptr [rsp+28h+arg_0], 1
0x18003a0ca  mov     eax, [rsp+28h+arg_0]
0x18003a0ce  xchg    eax, [rcx+0Ch]
0x18003a0d1  mov     rcx, [rcx+48h]
0x18003a0d5  test    rcx, rcx
0x18003a0d8  jz      short loc_18003A0E6
0x18003a0da  mov     rax, [rcx]
0x18003a0dd  mov     rax, [rax+10h]
0x18003a0e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a0e6  cmp     byte ptr [rbx+9], 0
0x18003a0ea  jz      short loc_18003A0FC
0x18003a0ec  mov     ecx, [rbx]; idThread
0x18003a0ee  xor     r9d, r9d; lParam
0x18003a0f1  xor     r8d, r8d; wParam
0x18003a0f4  xor     edx, edx; Msg
0x18003a0f6  call    cs:__imp_PostThreadMessageW
0x18003a0fc  mov     r8d, [rbx]; dwThreadId
0x18003a0ff  xor     edx, edx; bInheritHandle
0x18003a101  lea     ecx, [rdx+10h]; dwDesiredAccess
0x18003a104  call    cs:__imp_OpenThread
0x18003a10a  mov     rbx, rax
0x18003a10d  test    rax, rax
0x18003a110  jz      short loc_18003A134
0x18003a112  xor     r8d, r8d; dwData
0x18003a115  lea     rcx, ?Initialize@Module@Com@@MEAAXXZ; pfnAPC
0x18003a11c  mov     rdx, rax; hThread
0x18003a11f  call    cs:__imp_QueueUserAPC
0x18003a125  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18003a129  jz      short loc_18003A134
0x18003a12b  mov     rcx, rbx; hObject
0x18003a12e  call    cs:__imp_CloseHandle
0x18003a134  add     rsp, 20h
0x18003a138  pop     rbx
0x18003a139  retn
```
