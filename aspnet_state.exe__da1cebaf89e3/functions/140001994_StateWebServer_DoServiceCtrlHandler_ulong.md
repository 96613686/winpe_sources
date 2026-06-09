# StateWebServer::DoServiceCtrlHandler(ulong)

- ea: `0x140001994`
- end: `0x140001a1f`
- name: `?DoServiceCtrlHandler@StateWebServer@@AEAAXK@Z`
- size: `139`
- prototype: `void __fastcall(StateWebServer *this, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x140001ce0`

## callees

- `0x140001994`
- `0x140004f90`
- `0x1400052d0`
- `0x140005374`

## import_xrefs

- `KERNEL32!SetEvent` at `0x140001a09`
- `KERNEL32!SetEvent` at `0x140001a09`

## pseudocode

```c
void __fastcall StateWebServer::DoServiceCtrlHandler(StateWebServer *this, int a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rdi
  _QWORD *v6; // rax

  if ( !*((_BYTE *)this + 73) )
  {
    if ( ((a2 - 1) & 0xFFFFFFFB) == 0 )
      *((_BYTE *)this + 73) = 1;
    v4 = MemAllocClear(0x18u);
    v5 = v4;
    if ( v4 )
    {
      *(_OWORD *)v4 = 0;
      v4[2] = 0;
      *((_DWORD *)v4 + 4) = a2;
      CReadWriteSpinLock::AcquireWriterLock((StateWebServer *)((char *)this + 112));
      v6 = (_QWORD *)*((_QWORD *)this + 13);
      *v5 = (char *)this + 96;
      v5[1] = v6;
      *v6 = v5;
      *((_QWORD *)this + 13) = v5;
      CReadWriteSpinLock::ReleaseWriterLock((StateWebServer *)((char *)this + 112));
      SetEvent(*((HANDLE *)this + 8));
    }
  }
}

```

## disassembly

```asm
0x140001994  mov     [rsp+arg_0], rbx
0x140001999  mov     [rsp+arg_8], rsi
0x14000199e  push    rdi
0x14000199f  sub     rsp, 20h
0x1400019a3  cmp     byte ptr [rcx+49h], 0
0x1400019a7  mov     ebx, edx
0x1400019a9  mov     rsi, rcx
0x1400019ac  jnz     short loc_140001A0F
0x1400019ae  lea     eax, [rdx-1]
0x1400019b1  test    eax, 0FFFFFFFBh
0x1400019b6  jnz     short loc_1400019BC
0x1400019b8  mov     byte ptr [rcx+49h], 1
0x1400019bc  mov     ecx, 18h; unsigned __int64
0x1400019c1  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x1400019c6  mov     rdi, rax
0x1400019c9  test    rax, rax
0x1400019cc  jz      short loc_140001A0F
0x1400019ce  xorps   xmm0, xmm0
0x1400019d1  lea     rcx, [rsi+70h]; this
0x1400019d5  movups  xmmword ptr [rdi], xmm0
0x1400019d8  xor     eax, eax
0x1400019da  mov     [rdi+10h], rax
0x1400019de  mov     [rdi+10h], ebx
0x1400019e1  call    ?AcquireWriterLock@CReadWriteSpinLock@@QEAAXXZ; CReadWriteSpinLock::AcquireWriterLock(void)
0x1400019e6  lea     rdx, [rsi+60h]
0x1400019ea  mov     rax, [rdx+8]
0x1400019ee  lea     rcx, [rsi+70h]; this
0x1400019f2  mov     [rdi], rdx
0x1400019f5  mov     [rdi+8], rax
0x1400019f9  mov     [rax], rdi
0x1400019fc  mov     [rdx+8], rdi
0x140001a00  call    ?ReleaseWriterLock@CReadWriteSpinLock@@QEAAXXZ; CReadWriteSpinLock::ReleaseWriterLock(void)
0x140001a05  mov     rcx, [rsi+40h]; hEvent
0x140001a09  call    cs:__imp_SetEvent
0x140001a0f  mov     rbx, [rsp+28h+arg_0]
0x140001a14  mov     rsi, [rsp+28h+arg_8]
0x140001a19  add     rsp, 20h
0x140001a1d  pop     rdi
0x140001a1e  retn
```
