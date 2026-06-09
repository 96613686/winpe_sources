# CAMThread::InitialThreadProc(void *)

- ea: `0x1800071a0`
- end: `0x1800071db`
- name: `?InitialThreadProc@CAMThread@@SAKPEAX@Z`
- size: `59`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800070c4`
- `0x1800071a0`
- `0x180034010`

## import_xrefs

- `ole32!CoUninitialize` at `0x1800071c8`
- `ole32!CoUninitialize` at `0x1800071c8`

## pseudocode

```c
__int64 __fastcall CAMThread::InitialThreadProc(__int64 (__fastcall ***lpThreadParameter)(_QWORD))
{
  int v2; // edi
  unsigned int v3; // ebx

  v2 = CAMThread::CoInitializeHelper();
  v3 = (**lpThreadParameter)(lpThreadParameter);
  if ( v2 >= 0 )
    CoUninitialize();
  return v3;
}

```

## disassembly

```asm
0x1800071a0  mov     [rsp+arg_0], rbx
0x1800071a5  push    rdi
0x1800071a6  sub     rsp, 20h
0x1800071aa  mov     rbx, rcx
0x1800071ad  call    ?CoInitializeHelper@CAMThread@@SAJXZ; CAMThread::CoInitializeHelper(void)
0x1800071b2  mov     rdx, [rbx]
0x1800071b5  mov     edi, eax
0x1800071b7  mov     rcx, rbx
0x1800071ba  mov     rax, [rdx]
0x1800071bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071c2  mov     ebx, eax
0x1800071c4  test    edi, edi
0x1800071c6  js      short loc_1800071CE
0x1800071c8  call    cs:__imp_CoUninitialize
0x1800071ce  mov     eax, ebx
0x1800071d0  mov     rbx, [rsp+28h+arg_0]
0x1800071d5  add     rsp, 20h
0x1800071d9  pop     rdi
0x1800071da  retn
```
