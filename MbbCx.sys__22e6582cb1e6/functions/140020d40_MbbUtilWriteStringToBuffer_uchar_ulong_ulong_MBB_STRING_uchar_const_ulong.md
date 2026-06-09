# MbbUtilWriteStringToBuffer(uchar *,ulong,ulong,_MBB_STRING *,uchar const *,ulong)

- ea: `0x140020d40`
- end: `0x140020d9d`
- name: `?MbbUtilWriteStringToBuffer@@YAKPEAEKKPEAU_MBB_STRING@@PEBEK@Z`
- size: `93`
- prototype: `unsigned int __fastcall(unsigned __int8 *, unsigned int, unsigned int, struct _MBB_STRING *, const unsigned __int8 *Src, size_t Size)`
- caller_count: `21`
- callee_count: `2`
- tags: ``

## callers

- `0x1400142f0`
- `0x1400153a0`
- `0x140015560`
- `0x140015e10`
- `0x14001cd78`
- `0x14001d05c`
- `0x14001d38c`
- `0x14001d45c`
- `0x14001d530`
- `0x14001d5f8`
- `0x14001f834`
- `0x1400219b0`
- `0x140021d8c`
- `0x140022030`
- `0x140022470`
- `0x140022d98`
- `0x140022f4c`
- `0x1400235d8`
- `0x140023a7c`
- `0x140023bb4`
- `0x140023ce4`

## callees

- `0x140020d40`
- `0x140048040`

## pseudocode

```c
size_t __fastcall MbbUtilWriteStringToBuffer(
        unsigned __int8 *a1,
        unsigned int a2,
        int a3,
        struct _MBB_STRING *a4,
        const unsigned __int8 *Src,
        size_t Size)
{
  __int64 v6; // rax
  unsigned int v7; // ebx

  v6 = (a3 + 3) & 0xFFFFFFFC;
  v7 = (a3 + 3) & 0xFFFFFFFC;
  if ( v6 + (unsigned __int64)(unsigned int)Size > a2 )
  {
    __debugbreak();
  }
  else
  {
    *(_DWORD *)a4 = 0;
    *((_DWORD *)a4 + 1) = Size;
    if ( (_DWORD)Size )
    {
      *(_DWORD *)a4 = v6;
      memmove(&a1[(unsigned int)v6], Src, (unsigned int)Size);
      return ((_DWORD)Size + v7 + 3) & 0xFFFFFFFC;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x140020d40  mov     [rsp+arg_0], rbx
0x140020d45  push    rdi
0x140020d46  sub     rsp, 20h
0x140020d4a  mov     edi, dword ptr [rsp+28h+Size]
0x140020d4e  lea     eax, [r8+3]
0x140020d52  and     eax, 0FFFFFFFCh
0x140020d55  mov     r8d, edi; Size
0x140020d58  mov     ebx, eax
0x140020d5a  lea     r10, [rax+rdi]
0x140020d5e  mov     eax, edx
0x140020d60  cmp     r10, rax
0x140020d63  ja      short loc_140020D8E
0x140020d65  mov     dword ptr [r9], 0
0x140020d6c  mov     [r9+4], edi
0x140020d70  test    edi, edi
0x140020d72  jz      short loc_140020D8F
0x140020d74  mov     rdx, [rsp+28h+Src]; Src
0x140020d79  add     rcx, rbx; void *
0x140020d7c  mov     [r9], ebx
0x140020d7f  call    memmove
0x140020d84  add     ebx, 3
0x140020d87  add     ebx, edi
0x140020d89  and     ebx, 0FFFFFFFCh
0x140020d8c  jmp     short loc_140020D8F
0x140020d8e  int     3; Trap to Debugger
0x140020d8f  mov     eax, ebx
0x140020d91  mov     rbx, [rsp+28h+arg_0]
0x140020d96  add     rsp, 20h
0x140020d9a  pop     rdi
0x140020d9b  retn
```
