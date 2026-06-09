# CommonUtil::CHResultExceptionImpl::CHResultExceptionImpl(long)

- ea: `0x180007b60`
- end: `0x180007ba7`
- name: `??0CHResultExceptionImpl@CommonUtil@@QEAA@J@Z`
- size: `71`
- prototype: `__int64 __fastcall(CommonUtil::CHResultExceptionImpl *__hidden this, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007c10`

## callees

- `0x180001c78`
- `0x180007ce4`

## pseudocode

```c
CommonUtil::CHResultExceptionImpl *__fastcall CommonUtil::CHResultExceptionImpl::CHResultExceptionImpl(
        CommonUtil::CHResultExceptionImpl *this,
        int a2)
{
  exception::exception(this);
  *((_DWORD *)this + 10) = a2;
  *(_QWORD *)this = &CommonUtil::CHResultExceptionImpl::`vftable';
  StringCchPrintfA((char *)this + 24, 0xEu, "hr=0x%08X", a2);
  return this;
}

```

## disassembly

```asm
0x180007b60  mov     [rsp+arg_0], rbx
0x180007b65  push    rdi
0x180007b66  sub     rsp, 20h
0x180007b6a  mov     ebx, edx
0x180007b6c  mov     rdi, rcx
0x180007b6f  call    ??0exception@@QEAA@XZ_0; exception::exception(void)
0x180007b74  lea     rax, ??_7CHResultExceptionImpl@CommonUtil@@6B@; const CommonUtil::CHResultExceptionImpl::`vftable'
0x180007b7b  mov     [rdi+28h], ebx
0x180007b7e  lea     rcx, [rdi+18h]; char *
0x180007b82  mov     [rdi], rax
0x180007b85  mov     r9d, ebx
0x180007b88  lea     r8, aHr0x08x; "hr=0x%08X"
0x180007b8f  mov     edx, 0Eh; unsigned __int64
0x180007b94  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180007b99  mov     rbx, [rsp+28h+arg_0]
0x180007b9e  mov     rax, rdi
0x180007ba1  add     rsp, 20h
0x180007ba5  pop     rdi
0x180007ba6  retn
```
