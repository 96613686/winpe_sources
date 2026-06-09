# BfFillOutEcpFields

- ea: `0x140011d18`
- end: `0x140011de7`
- name: `BfFillOutEcpFields`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140011fb4`

## callees

- `0x14000f66c`
- `0x14000f6a4`
- `0x14000f6e0`

## import_xrefs

- `ntoskrnl!PsGetProcessId` at `0x140011d3f`
- `ntoskrnl!PsGetProcessId` at `0x140011d3f`
- `ntoskrnl!PsGetProcessSessionId` at `0x140011d5d`
- `ntoskrnl!PsGetProcessSessionId` at `0x140011d5d`
- `ntoskrnl!PsGetCurrentProcess` at `0x140011d30`
- `ntoskrnl!PsGetCurrentProcess` at `0x140011d4e`
- `ntoskrnl!PsGetCurrentProcess` at `0x140011d30`
- `ntoskrnl!PsGetCurrentProcess` at `0x140011d4e`

## pseudocode

```c
__int64 __fastcall BfFillOutEcpFields(__int64 a1, __int64 a2, __int64 a3)
{
  struct _KPROCESS *CurrentProcess; // rax
  __int64 v7; // rax
  __int64 result; // rax

  CurrentProcess = (struct _KPROCESS *)PsGetCurrentProcess();
  *(_DWORD *)(a1 + 24) = (unsigned int)PsGetProcessId(CurrentProcess);
  v7 = PsGetCurrentProcess();
  *(_DWORD *)(a1 + 28) = PsGetProcessSessionId(v7);
  *(_QWORD *)(a1 + 32) = RtlReadULong64FromUser(a2 + 712);
  *(_DWORD *)(a1 + 40) = RtlReadULongFromUser(a2 + 1960);
  *(_DWORD *)(a1 + 44) = RtlReadULongFromUser(a2 + 1964);
  *(_DWORD *)(a1 + 48) = RtlReadULongFromUser(a2 + 296);
  *(_BYTE *)(a1 + 52) = RtlReadUCharFromUser(a2 + 1968);
  *(_BYTE *)(a1 + 56) = RtlReadUCharFromUser(a3 + 640);
  result = RtlReadUCharFromUser(a3 + 641);
  *(_BYTE *)(a1 + 57) = result;
  return result;
}

```

## disassembly

```asm
0x140011d18  mov     [rsp+arg_0], rbx
0x140011d1d  mov     [rsp+arg_8], rsi
0x140011d22  push    rdi
0x140011d23  sub     rsp, 20h
0x140011d27  mov     rdi, r8
0x140011d2a  mov     rbx, rdx
0x140011d2d  mov     rsi, rcx
0x140011d30  call    cs:__imp_PsGetCurrentProcess
0x140011d37  nop     dword ptr [rax+rax+00h]
0x140011d3c  mov     rcx, rax; Process
0x140011d3f  call    cs:__imp_PsGetProcessId
0x140011d46  nop     dword ptr [rax+rax+00h]
0x140011d4b  mov     [rsi+18h], eax
0x140011d4e  call    cs:__imp_PsGetCurrentProcess
0x140011d55  nop     dword ptr [rax+rax+00h]
0x140011d5a  mov     rcx, rax
0x140011d5d  call    cs:__imp_PsGetProcessSessionId
0x140011d64  nop     dword ptr [rax+rax+00h]
0x140011d69  lea     rcx, [rbx+2C8h]
0x140011d70  mov     [rsi+1Ch], eax
0x140011d73  call    RtlReadULong64FromUser
0x140011d78  lea     rcx, [rbx+7A8h]
0x140011d7f  mov     [rsi+20h], rax
0x140011d83  call    RtlReadULongFromUser
0x140011d88  lea     rcx, [rbx+7ACh]
0x140011d8f  mov     [rsi+28h], eax
0x140011d92  call    RtlReadULongFromUser
0x140011d97  lea     rcx, [rbx+128h]
0x140011d9e  mov     [rsi+2Ch], eax
0x140011da1  call    RtlReadULongFromUser
0x140011da6  lea     rcx, [rbx+7B0h]
0x140011dad  mov     [rsi+30h], eax
0x140011db0  call    RtlReadUCharFromUser
0x140011db5  lea     rcx, [rdi+280h]
0x140011dbc  mov     [rsi+34h], al
0x140011dbf  call    RtlReadUCharFromUser
0x140011dc4  lea     rcx, [rdi+281h]
0x140011dcb  mov     [rsi+38h], al
0x140011dce  call    RtlReadUCharFromUser
0x140011dd3  mov     rbx, [rsp+28h+arg_0]
0x140011dd8  mov     [rsi+39h], al
0x140011ddb  mov     rsi, [rsp+28h+arg_8]
0x140011de0  add     rsp, 20h
0x140011de4  pop     rdi
0x140011de5  retn
```
