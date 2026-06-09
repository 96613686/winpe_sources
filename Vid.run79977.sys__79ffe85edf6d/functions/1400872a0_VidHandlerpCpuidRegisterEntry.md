# VidHandlerpCpuidRegisterEntry

- ea: `0x1400872a0`
- end: `0x14008735d`
- name: `VidHandlerpCpuidRegisterEntry`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x14008693c`

## callees

- `0x140021c60`
- `0x140074df4`
- `0x1400872a0`

## import_xrefs

- `ntoskrnl!RtlRbRemoveNode` at `0x140087334`
- `ntoskrnl!RtlRbRemoveNode` at `0x140087334`
- `winhvr!WinHvInstallIntercept` at `0x140087307`
- `winhvr!WinHvInstallIntercept` at `0x140087307`

## pseudocode

```c
__int64 __fastcall VidHandlerpCpuidRegisterEntry(__int64 a1, __int64 a2)
{
  int v2; // ebx
  __int64 v3; // rbp
  int v6; // ebx
  __int64 v7; // rcx
  __int64 v9; // [rsp+20h] [rbp-38h] BYREF
  int v10; // [rsp+28h] [rbp-30h]

  v2 = *(_DWORD *)(a2 + 116);
  v3 = a1 + 3456;
  v10 = 0;
  v9 = 0;
  if ( (unsigned __int8)VidHandlerTableInsert(a1 + 3456) )
  {
    v7 = *(_QWORD *)(a1 + 648);
    LODWORD(v9) = 2;
    v10 = v2;
    v6 = WinHvInstallIntercept(v7, 4, &v9);
    if ( v6 < 0 )
      RtlRbRemoveNode(v3, a2 + 160);
    else
      _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(a1 + 1528) + 496LL));
  }
  else
  {
    return (unsigned int)-1070137343;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400872a0  mov     [rsp+arg_10], rbx
0x1400872a5  push    rbp
0x1400872a6  push    rsi
0x1400872a7  push    rdi
0x1400872a8  sub     rsp, 40h
0x1400872ac  mov     rax, cs:__security_cookie
0x1400872b3  xor     rax, rsp
0x1400872b6  mov     [rsp+58h+var_28], rax
0x1400872bb  mov     ebx, [rdx+74h]
0x1400872be  lea     rbp, [rcx+0D80h]
0x1400872c5  xor     eax, eax
0x1400872c7  mov     rdi, rcx
0x1400872ca  mov     qword ptr [rsp+58h+var_34], rax
0x1400872cf  mov     rcx, rbp
0x1400872d2  mov     [rsp+20h], rax
0x1400872d7  mov     rsi, rdx
0x1400872da  call    VidHandlerTableInsert
0x1400872df  test    al, al
0x1400872e1  jnz     short loc_1400872EA
0x1400872e3  mov     ebx, 0C0370001h
0x1400872e8  jmp     short loc_140087340
0x1400872ea  mov     rcx, [rdi+288h]
0x1400872f1  lea     r8, [rsp+58h+var_38]
0x1400872f6  mov     edx, 4
0x1400872fb  mov     [rsp+58h+var_38], 2
0x140087303  mov     [rsp+58h+var_34+4], ebx
0x140087307  call    cs:__imp_WinHvInstallIntercept
0x14008730e  nop     dword ptr [rax+rax+00h]
0x140087313  mov     ebx, eax
0x140087315  test    eax, eax
0x140087317  js      short loc_14008732A
0x140087319  mov     rcx, [rdi+5F8h]
0x140087320  lock inc qword ptr [rcx+1F0h]
0x140087328  jmp     short loc_140087340
0x14008732a  lea     rdx, [rsi+0A0h]
0x140087331  mov     rcx, rbp
0x140087334  call    cs:__imp_RtlRbRemoveNode
0x14008733b  nop     dword ptr [rax+rax+00h]
0x140087340  mov     eax, ebx
0x140087342  mov     rcx, [rsp+58h+var_28]
0x140087347  xor     rcx, rsp; StackCookie
0x14008734a  call    __security_check_cookie
0x14008734f  mov     rbx, [rsp+58h+arg_10]
0x140087354  add     rsp, 40h
0x140087358  pop     rdi
0x140087359  pop     rsi
0x14008735a  pop     rbp
0x14008735b  retn
```
