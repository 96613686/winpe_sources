# Pal::RandomAccessStreamWin32::RandomAccessStreamWin32(void *)

- ea: `0x180010944`
- end: `0x1800109e0`
- name: `??0RandomAccessStreamWin32@Pal@@QEAA@PEAX@Z`
- size: `156`
- prototype: `Pal::RandomAccessStreamWin32 *__fastcall(Pal::RandomAccessStreamWin32 *this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d81c`

## callees

- `0x180009988`
- `0x18001b15c`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!BindIoCompletionCallback` at `0x1800109c6`
- `api-ms-win-core-kernel32-legacy-l1-1-0!BindIoCompletionCallback` at `0x1800109c6`

## pseudocode

```c
Pal::RandomAccessStreamWin32 *__fastcall Pal::RandomAccessStreamWin32::RandomAccessStreamWin32(
        Pal::RandomAccessStreamWin32 *this,
        void *a2)
{
  _DWORD *v5; // [rsp+40h] [rbp+18h]

  *(_QWORD *)this = &Pal::RandomAccessStreamWin32::`vftable';
  v5 = operator new(0x18u);
  *(_OWORD *)v5 = 0;
  v5[2] = 1;
  v5[3] = 1;
  *(_QWORD *)v5 = &std::_Ref_count_obj2<Pal::FileHandle>::`vftable';
  *((_QWORD *)v5 + 2) = a2;
  *((_QWORD *)this + 1) = v5 + 4;
  *((_QWORD *)this + 2) = v5;
  *((_QWORD *)this + 3) = 0;
  Pal::UntypedAsyncOperationCancelList::UntypedAsyncOperationCancelList((Pal::RandomAccessStreamWin32 *)((char *)this + 32));
  *((_BYTE *)this + 136) = 0;
  BindIoCompletionCallback(a2, Pal::RandomAccessStreamWin32::FileIoCompletionRoutine, 0);
  return this;
}

```

## disassembly

```asm
0x180010944  mov     [rsp+arg_8], rbx
0x180010949  mov     [rsp+arg_18], rsi
0x18001094e  mov     [rsp+arg_0], rcx
0x180010953  push    rdi
0x180010954  sub     rsp, 20h
0x180010958  mov     rdi, rdx
0x18001095b  mov     rsi, rcx
0x18001095e  lea     rax, ??_7RandomAccessStreamWin32@Pal@@6B@; const Pal::RandomAccessStreamWin32::`vftable'
0x180010965  mov     [rcx], rax
0x180010968  mov     ecx, 18h; Size
0x18001096d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010972  mov     [rsp+28h+arg_10], rax
0x180010977  xorps   xmm0, xmm0
0x18001097a  movups  xmmword ptr [rax], xmm0
0x18001097d  mov     ecx, 1
0x180010982  mov     [rax+8], ecx
0x180010985  mov     [rax+0Ch], ecx
0x180010988  lea     rcx, ??_7?$_Ref_count_obj2@VFileHandle@Pal@@@std@@6B@; const std::_Ref_count_obj2<Pal::FileHandle>::`vftable'
0x18001098f  mov     [rax], rcx
0x180010992  lea     rcx, [rax+10h]
0x180010996  mov     [rcx], rdi
0x180010999  mov     [rsi+8], rcx
0x18001099d  mov     [rsi+10h], rax
0x1800109a1  mov     qword ptr [rsi+18h], 0
0x1800109a9  lea     rcx, [rsi+20h]; this
0x1800109ad  call    ??0UntypedAsyncOperationCancelList@Pal@@QEAA@XZ; Pal::UntypedAsyncOperationCancelList::UntypedAsyncOperationCancelList(void)
0x1800109b2  mov     byte ptr [rsi+88h], 0
0x1800109b9  xor     r8d, r8d; Flags
0x1800109bc  lea     rdx, ?FileIoCompletionRoutine@RandomAccessStreamWin32@Pal@@CAXKKPEAU_OVERLAPPED@@@Z; Function
0x1800109c3  mov     rcx, rdi; FileHandle
0x1800109c6  call    cs:__imp_BindIoCompletionCallback
0x1800109cc  nop
0x1800109cd  mov     rax, rsi
0x1800109d0  mov     rbx, [rsp+28h+arg_8]
0x1800109d5  mov     rsi, [rsp+28h+arg_18]
0x1800109da  add     rsp, 20h
0x1800109de  pop     rdi
0x1800109df  retn
```
