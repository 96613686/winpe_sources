# clnttcp_destroy

- ea: `0x14000dc10`
- end: `0x14000dc92`
- name: `clnttcp_destroy`
- size: `130`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000dc10`
- `0x140019010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x14000dc29`
- `KERNEL32!EnterCriticalSection` at `0x14000dc29`
- `KERNEL32!GlobalFree` at `0x14000dc61`
- `KERNEL32!GlobalFree` at `0x14000dc61`
- `KERNEL32!GlobalFree` at `0x14000dc8b`
- `KERNEL32!LeaveCriticalSection` at `0x14000dc6a`
- `KERNEL32!LeaveCriticalSection` at `0x14000dc6a`
- `KERNEL32!DeleteCriticalSection` at `0x14000dc73`
- `KERNEL32!DeleteCriticalSection` at `0x14000dc73`
- `WS2_32!__imp_closesocket` at `0x14000dc3c`
- `WS2_32!__imp_closesocket` at `0x14000dc3c`

## pseudocode

```c
HGLOBAL __fastcall clnttcp_destroy(__int64 a1)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  SOCKET *v3; // rbx
  void (__fastcall *v4)(SOCKET *); // rax

  v1 = (struct _RTL_CRITICAL_SECTION *)(a1 + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
  v3 = *(SOCKET **)(a1 + 16);
  if ( *v3 != -1 )
    closesocket(*v3);
  v4 = *(void (__fastcall **)(SOCKET *))(v3[26] + 56);
  if ( v4 )
    v4(v3 + 25);
  GlobalFree(v3);
  LeaveCriticalSection(v1);
  DeleteCriticalSection(v1);
  return GlobalFree((HGLOBAL)a1);
}

```

## disassembly

```asm
0x14000dc10  mov     [rsp+arg_0], rbx
0x14000dc15  mov     [rsp+arg_8], rsi
0x14000dc1a  push    rdi
0x14000dc1b  sub     rsp, 20h
0x14000dc1f  lea     rsi, [rcx+18h]
0x14000dc23  mov     rdi, rcx
0x14000dc26  mov     rcx, rsi; lpCriticalSection
0x14000dc29  call    cs:__imp_EnterCriticalSection
0x14000dc2f  mov     rbx, [rdi+10h]
0x14000dc33  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x14000dc37  jz      short loc_14000DC42
0x14000dc39  mov     rcx, [rbx]; s
0x14000dc3c  call    cs:__imp_closesocket
0x14000dc42  mov     rax, [rbx+0D0h]
0x14000dc49  mov     rax, [rax+38h]
0x14000dc4d  test    rax, rax
0x14000dc50  jz      short loc_14000DC5E
0x14000dc52  lea     rcx, [rbx+0C8h]
0x14000dc59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dc5e  mov     rcx, rbx; hMem
0x14000dc61  call    cs:__imp_GlobalFree
0x14000dc67  mov     rcx, rsi; lpCriticalSection
0x14000dc6a  call    cs:__imp_LeaveCriticalSection
0x14000dc70  mov     rcx, rsi; lpCriticalSection
0x14000dc73  call    cs:__imp_DeleteCriticalSection
0x14000dc79  mov     rcx, rdi
0x14000dc7c  mov     rbx, [rsp+28h+arg_0]
0x14000dc81  mov     rsi, [rsp+28h+arg_8]
0x14000dc86  add     rsp, 20h
0x14000dc8a  pop     rdi
0x14000dc8b  jmp     cs:__imp_GlobalFree
```
