# clntudp_destroy

- ea: `0x14000e930`
- end: `0x14000e9b2`
- name: `clntudp_destroy`
- size: `130`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000e930`
- `0x140019010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x14000e949`
- `KERNEL32!EnterCriticalSection` at `0x14000e949`
- `KERNEL32!GlobalFree` at `0x14000e981`
- `KERNEL32!GlobalFree` at `0x14000e981`
- `KERNEL32!GlobalFree` at `0x14000e9ab`
- `KERNEL32!LeaveCriticalSection` at `0x14000e98a`
- `KERNEL32!LeaveCriticalSection` at `0x14000e98a`
- `KERNEL32!DeleteCriticalSection` at `0x14000e993`
- `KERNEL32!DeleteCriticalSection` at `0x14000e993`
- `WS2_32!__imp_closesocket` at `0x14000e95c`
- `WS2_32!__imp_closesocket` at `0x14000e95c`

## pseudocode

```c
HGLOBAL __fastcall clntudp_destroy(__int64 a1)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  SOCKET *v3; // rbx
  void (__fastcall *v4)(SOCKET *); // rax

  v1 = (struct _RTL_CRITICAL_SECTION *)(a1 + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
  v3 = *(SOCKET **)(a1 + 16);
  if ( *v3 != -1 )
    closesocket(*v3);
  v4 = *(void (__fastcall **)(SOCKET *))(v3[23] + 56);
  if ( v4 )
    v4(v3 + 22);
  GlobalFree(v3);
  LeaveCriticalSection(v1);
  DeleteCriticalSection(v1);
  return GlobalFree((HGLOBAL)a1);
}

```

## disassembly

```asm
0x14000e930  mov     [rsp+arg_0], rbx
0x14000e935  mov     [rsp+arg_8], rsi
0x14000e93a  push    rdi
0x14000e93b  sub     rsp, 20h
0x14000e93f  lea     rsi, [rcx+18h]
0x14000e943  mov     rdi, rcx
0x14000e946  mov     rcx, rsi; lpCriticalSection
0x14000e949  call    cs:__imp_EnterCriticalSection
0x14000e94f  mov     rbx, [rdi+10h]
0x14000e953  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x14000e957  jz      short loc_14000E962
0x14000e959  mov     rcx, [rbx]; s
0x14000e95c  call    cs:__imp_closesocket
0x14000e962  mov     rax, [rbx+0B8h]
0x14000e969  mov     rax, [rax+38h]
0x14000e96d  test    rax, rax
0x14000e970  jz      short loc_14000E97E
0x14000e972  lea     rcx, [rbx+0B0h]
0x14000e979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e97e  mov     rcx, rbx; hMem
0x14000e981  call    cs:__imp_GlobalFree
0x14000e987  mov     rcx, rsi; lpCriticalSection
0x14000e98a  call    cs:__imp_LeaveCriticalSection
0x14000e990  mov     rcx, rsi; lpCriticalSection
0x14000e993  call    cs:__imp_DeleteCriticalSection
0x14000e999  mov     rcx, rdi
0x14000e99c  mov     rbx, [rsp+28h+arg_0]
0x14000e9a1  mov     rsi, [rsp+28h+arg_8]
0x14000e9a6  add     rsp, 20h
0x14000e9aa  pop     rdi
0x14000e9ab  jmp     cs:__imp_GlobalFree
```
