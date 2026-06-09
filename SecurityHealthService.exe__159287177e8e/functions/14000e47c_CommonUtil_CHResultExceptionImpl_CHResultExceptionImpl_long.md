# CommonUtil::CHResultExceptionImpl::CHResultExceptionImpl(long)

- ea: `0x14000e47c`
- end: `0x14000e4ba`
- name: `??0CHResultExceptionImpl@CommonUtil@@QEAA@J@Z`
- size: `62`
- prototype: `CommonUtil::CHResultExceptionImpl *__fastcall(CommonUtil::CHResultExceptionImpl *this, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000e508`

## callees

- `0x14000e5e4`

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
0x14000e47c  push    rbx
0x14000e47e  sub     rsp, 20h
0x14000e482  xorps   xmm0, xmm0
0x14000e485  lea     rax, ??_7CHResultExceptionImpl@CommonUtil@@6B@; const CommonUtil::CHResultExceptionImpl::`vftable'
0x14000e48c  movups  xmmword ptr [rcx+8], xmm0
0x14000e490  mov     [rcx+28h], edx
0x14000e493  lea     r8, aHr0x08x; "hr=0x%08X"
0x14000e49a  mov     [rcx], rax
0x14000e49d  mov     rbx, rcx
0x14000e4a0  mov     r9d, edx
0x14000e4a3  add     rcx, 18h; char *
0x14000e4a7  mov     edx, 0Eh; unsigned __int64
0x14000e4ac  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x14000e4b1  mov     rax, rbx
0x14000e4b4  add     rsp, 20h
0x14000e4b8  pop     rbx
0x14000e4b9  retn
```
