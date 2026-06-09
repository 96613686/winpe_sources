# VidTraceActivityInitialize

- ea: `0x140024850`
- end: `0x1400248b2`
- name: `VidTraceActivityInitialize`
- size: `98`
- prototype: ``
- caller_count: `31`
- callee_count: `1`
- tags: ``

## callers

- `0x14007b454`
- `0x14007b71c`
- `0x14007baa4`
- `0x14007c150`
- `0x14007c600`
- `0x14007c964`
- `0x14007ccc8`
- `0x14007d0d4`
- `0x14007d498`
- `0x14007d9ac`
- `0x14007dd70`
- `0x14007e080`
- `0x14007e478`
- `0x14007e890`
- `0x14007ed04`
- `0x14007f0c8`
- `0x14007f3d8`
- `0x14007f7b0`
- `0x14007fbc0`
- `0x14007ff98`
- `0x140080370`
- `0x140080764`
- `0x140080b74`
- `0x140080f84`
- `0x1400812d4`
- `0x140081620`
- `0x140081af0`
- `0x140081e2c`
- `0x140082300`
- `0x140089b94`
- `0x14008a2f0`

## callees

- `0x140021e00`

## import_xrefs

- `ntoskrnl!EtwActivityIdControl` at `0x140024871`
- `ntoskrnl!EtwActivityIdControl` at `0x140024886`
- `ntoskrnl!EtwActivityIdControl` at `0x140024871`
- `ntoskrnl!EtwActivityIdControl` at `0x140024886`
- `ntoskrnl!IoSetActivityIdThread` at `0x140024896`
- `ntoskrnl!IoSetActivityIdThread` at `0x140024896`

## pseudocode

```c
__int64 __fastcall VidTraceActivityInitialize(GUID *a1)
{
  __int64 result; // rax

  memset(a1, 0, 0x50u);
  EtwActivityIdControl(5u, a1 + 1);
  EtwActivityIdControl(1u, a1 + 2);
  result = IoSetActivityIdThread(&a1[2]);
  *(_QWORD *)a1->Data4 = result;
  return result;
}

```

## disassembly

```asm
0x140024850  mov     [rsp+arg_0], rbx
0x140024855  push    rdi
0x140024856  sub     rsp, 20h
0x14002485a  xor     edx, edx; Val
0x14002485c  mov     rdi, rcx
0x14002485f  lea     r8d, [rdx+50h]; Size
0x140024863  call    memset
0x140024868  lea     rdx, [rdi+10h]; ActivityId
0x14002486c  mov     ecx, 5; ControlCode
0x140024871  call    cs:__imp_EtwActivityIdControl
0x140024878  nop     dword ptr [rax+rax+00h]
0x14002487d  lea     rdx, [rdi+20h]; ActivityId
0x140024881  mov     ecx, 1; ControlCode
0x140024886  call    cs:__imp_EtwActivityIdControl
0x14002488d  nop     dword ptr [rax+rax+00h]
0x140024892  lea     rcx, [rdi+20h]
0x140024896  call    cs:__imp_IoSetActivityIdThread
0x14002489d  nop     dword ptr [rax+rax+00h]
0x1400248a2  mov     rbx, [rsp+28h+arg_0]
0x1400248a7  mov     [rdi+8], rax
0x1400248ab  add     rsp, 20h
0x1400248af  pop     rdi
0x1400248b0  retn
```
