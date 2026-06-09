# CompletableIrp::~CompletableIrp(void)

- ea: `0x1400366ac`
- end: `0x1400366e2`
- name: `??1CompletableIrp@@QEAA@XZ`
- size: `54`
- prototype: `void __fastcall(CompletableIrp *__hidden this)`
- caller_count: `19`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140037a8c`
- `0x14005a840`
- `0x140078fb8`
- `0x14007d500`
- `0x140080150`
- `0x140086b38`
- `0x140086cc4`
- `0x14008706c`
- `0x140087310`
- `0x140087bb0`
- `0x140087df4`
- `0x140088038`
- `0x1400882c4`
- `0x140088510`
- `0x1400887cc`
- `0x140088964`
- `0x140088afc`
- `0x140088dc0`
- `0x140088f60`

## callees

- `0x1400366ac`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400366d0`
- `ntoskrnl!IofCompleteRequest` at `0x1400366d0`

## pseudocode

```c
void __fastcall CompletableIrp::~CompletableIrp(CompletableIrp *this)
{
  __int64 v1; // rdx

  v1 = *((_QWORD *)this + 2);
  if ( v1 )
  {
    *(_QWORD *)(v1 + 56) = *((_QWORD *)this + 1);
    *(_DWORD *)(*((_QWORD *)this + 2) + 48LL) = *(_DWORD *)this;
    IofCompleteRequest(*((PIRP *)this + 2), 0);
  }
}

```

## disassembly

```asm
0x1400366ac  sub     rsp, 28h
0x1400366b0  mov     rdx, [rcx+10h]
0x1400366b4  test    rdx, rdx
0x1400366b7  jz      short loc_1400366DC
0x1400366b9  mov     rax, [rcx+8]
0x1400366bd  mov     [rdx+38h], rax
0x1400366c1  mov     rdx, [rcx+10h]
0x1400366c5  mov     eax, [rcx]
0x1400366c7  mov     [rdx+30h], eax
0x1400366ca  xor     edx, edx; PriorityBoost
0x1400366cc  mov     rcx, [rcx+10h]; Irp
0x1400366d0  call    cs:__imp_IofCompleteRequest
0x1400366d7  nop     dword ptr [rax+rax+00h]
0x1400366dc  add     rsp, 28h
0x1400366e0  retn
```
