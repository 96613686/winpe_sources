# VidHandlerpCpuidUnregisterEntry

- ea: `0x140087364`
- end: `0x1400873e0`
- name: `VidHandlerpCpuidUnregisterEntry`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x140074c30`

## callees

- `0x140021c60`

## import_xrefs

- `ntoskrnl!RtlRbRemoveNode` at `0x1400873bb`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400873bb`
- `winhvr!WinHvInstallIntercept` at `0x1400873a1`
- `winhvr!WinHvInstallIntercept` at `0x1400873a1`

## pseudocode

```c
__int64 __fastcall VidHandlerpCpuidUnregisterEntry(__int64 a1, __int64 a2)
{
  int v2; // eax
  __int64 v6; // [rsp+20h] [rbp-28h] BYREF
  int v7; // [rsp+28h] [rbp-20h]

  v2 = *(_DWORD *)(a2 + 116);
  v6 = 2;
  v7 = v2;
  WinHvInstallIntercept(*(_QWORD *)(a1 + 648), 0, &v6);
  return RtlRbRemoveNode(a1 + 3456, a2 + 160);
}

```

## disassembly

```asm
0x140087364  mov     [rsp+arg_10], rbx
0x140087369  push    rdi
0x14008736a  sub     rsp, 40h
0x14008736e  mov     rax, cs:__security_cookie
0x140087375  xor     rax, rsp
0x140087378  mov     [rsp+48h+var_18], rax
0x14008737d  mov     eax, [rdx+74h]
0x140087380  lea     r8, [rsp+48h+var_28]
0x140087385  mov     rdi, rdx
0x140087388  mov     [rsp+48h+var_28], 2
0x140087391  mov     rbx, rcx
0x140087394  mov     [rsp+48h+var_20], eax
0x140087398  mov     rcx, [rcx+288h]
0x14008739f  xor     edx, edx
0x1400873a1  call    cs:__imp_WinHvInstallIntercept
0x1400873a8  nop     dword ptr [rax+rax+00h]
0x1400873ad  lea     rdx, [rdi+0A0h]
0x1400873b4  lea     rcx, [rbx+0D80h]
0x1400873bb  call    cs:__imp_RtlRbRemoveNode
0x1400873c2  nop     dword ptr [rax+rax+00h]
0x1400873c7  mov     rcx, [rsp+48h+var_18]
0x1400873cc  xor     rcx, rsp; StackCookie
0x1400873cf  call    __security_check_cookie
0x1400873d4  mov     rbx, [rsp+48h+arg_10]
0x1400873d9  add     rsp, 40h
0x1400873dd  pop     rdi
0x1400873de  retn
```
