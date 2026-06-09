# _anonymous_namespace_::CancelThread

- ea: `0x1800214b4`
- end: `0x18002153a`
- name: `_anonymous_namespace_::CancelThread`
- size: `134`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180021770`

## callees

- `0x1800214b4`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002152e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002152e`
- `KERNEL32!QueueUserAPC` at `0x18002151f`
- `KERNEL32!QueueUserAPC` at `0x18002151f`
- `KERNEL32!OpenThread` at `0x180021504`
- `KERNEL32!OpenThread` at `0x180021504`
- `USER32!PostThreadMessageW` at `0x1800214f6`
- `USER32!PostThreadMessageW` at `0x1800214f6`

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
    LODWORD(v3) = QueueUserAPC((PAPCFUNC)Com::Module::Initialize, v3, 0);
    if ( v4 != (void *)-1LL )
      LODWORD(v3) = CloseHandle(v4);
  }
  return (int)v3;
}

```

## disassembly

```asm
0x1800214b4  push    rbx
0x1800214b6  sub     rsp, 20h
0x1800214ba  mov     [rsp+28h+arg_0], 0
0x1800214c2  mov     rbx, rcx
0x1800214c5  mov     byte ptr [rsp+28h+arg_0], 1
0x1800214ca  mov     eax, [rsp+28h+arg_0]
0x1800214ce  xchg    eax, [rcx+0Ch]
0x1800214d1  mov     rcx, [rcx+48h]
0x1800214d5  test    rcx, rcx
0x1800214d8  jz      short loc_1800214E6
0x1800214da  mov     rax, [rcx]
0x1800214dd  mov     rax, [rax+10h]
0x1800214e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800214e6  cmp     byte ptr [rbx+9], 0
0x1800214ea  jz      short loc_1800214FC
0x1800214ec  mov     ecx, [rbx]; idThread
0x1800214ee  xor     r9d, r9d; lParam
0x1800214f1  xor     r8d, r8d; wParam
0x1800214f4  xor     edx, edx; Msg
0x1800214f6  call    cs:__imp_PostThreadMessageW
0x1800214fc  mov     r8d, [rbx]; dwThreadId
0x1800214ff  xor     edx, edx; bInheritHandle
0x180021501  lea     ecx, [rdx+10h]; dwDesiredAccess
0x180021504  call    cs:__imp_OpenThread
0x18002150a  mov     rbx, rax
0x18002150d  test    rax, rax
0x180021510  jz      short loc_180021534
0x180021512  xor     r8d, r8d; dwData
0x180021515  lea     rcx, ?Initialize@Module@Com@@MEAAXXZ; pfnAPC
0x18002151c  mov     rdx, rax; hThread
0x18002151f  call    cs:__imp_QueueUserAPC
0x180021525  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180021529  jz      short loc_180021534
0x18002152b  mov     rcx, rbx; hObject
0x18002152e  call    cs:__imp_CloseHandle
0x180021534  add     rsp, 20h
0x180021538  pop     rbx
0x180021539  retn
```
