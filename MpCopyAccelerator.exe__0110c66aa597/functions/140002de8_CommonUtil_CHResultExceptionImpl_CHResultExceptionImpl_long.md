# CommonUtil::CHResultExceptionImpl::CHResultExceptionImpl(long)

- ea: `0x140002de8`
- end: `0x140002e26`
- name: `??0CHResultExceptionImpl@CommonUtil@@QEAA@J@Z`
- size: `62`
- prototype: `__int64 __fastcall(CommonUtil::CHResultExceptionImpl *__hidden this, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140002e74`

## callees

- `0x140002f34`

## pseudocode

```c
CommonUtil::CHResultExceptionImpl *__fastcall CommonUtil::CHResultExceptionImpl::CHResultExceptionImpl(
        CommonUtil::CHResultExceptionImpl *this,
        int a2)
{
  *(_OWORD *)((char *)this + 8) = 0;
  *((_DWORD *)this + 10) = a2;
  *(_QWORD *)this = &CommonUtil::CHResultExceptionImpl::`vftable';
  StringCchPrintfA((char *)this + 24, 0xEu, "hr=0x%08X", a2);
  return this;
}

```

## disassembly

```asm
0x140002de8  push    rbx
0x140002dea  sub     rsp, 20h
0x140002dee  xorps   xmm0, xmm0
0x140002df1  lea     rax, ??_7CHResultExceptionImpl@CommonUtil@@6B@; const CommonUtil::CHResultExceptionImpl::`vftable'
0x140002df8  movups  xmmword ptr [rcx+8], xmm0
0x140002dfc  mov     [rcx+28h], edx
0x140002dff  lea     r8, aHr0x08x; "hr=0x%08X"
0x140002e06  mov     [rcx], rax
0x140002e09  mov     rbx, rcx
0x140002e0c  mov     r9d, edx
0x140002e0f  add     rcx, 18h; Buffer
0x140002e13  mov     edx, 0Eh; unsigned __int64
0x140002e18  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x140002e1d  mov     rax, rbx
0x140002e20  add     rsp, 20h
0x140002e24  pop     rbx
0x140002e25  retn
```
