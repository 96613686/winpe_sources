# Microsoft::CoreUI::Dispatch::Win32EventLoopBridge::FinallyOnAfterWait(void)

- ea: `0x1800669a0`
- end: `0x1800669ed`
- name: `?FinallyOnAfterWait@Win32EventLoopBridge@Dispatch@CoreUI@Microsoft@@UEAAXXZ`
- size: `77`
- prototype: `void __fastcall(Microsoft::CoreUI::Dispatch::Win32EventLoopBridge *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000ec10`
- `0x1800669a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800669d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800669d3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800669de`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800669de`

## pseudocode

```c
void __fastcall Microsoft::CoreUI::Dispatch::Win32EventLoopBridge::FinallyOnAfterWait(
        Microsoft::CoreUI::Dispatch::Win32EventLoopBridge *this)
{
  System::Object *v1; // rbx
  int v2; // edi
  HANDLE CurrentThread; // rax

  v1 = (System::Object *)*((_QWORD *)this + 5);
  if ( v1 )
    ++*((_DWORD *)v1 + 4);
  v2 = *((_DWORD *)v1 + 29);
  if ( v2 != 0x7FFFFFFF )
  {
    CurrentThread = GetCurrentThread();
    SetThreadPriority(CurrentThread, v2);
    *((_DWORD *)v1 + 29) = 0x7FFFFFFF;
  }
  System::Object::ReleaseNotFrozen$(v1);
}

```

## disassembly

```asm
0x1800669a0  mov     [rsp+arg_0], rbx
0x1800669a5  push    rdi
0x1800669a6  sub     rsp, 20h
0x1800669aa  mov     rbx, [rcx+28h]
0x1800669ae  test    rbx, rbx
0x1800669b1  jz      short loc_1800669B6
0x1800669b3  inc     dword ptr [rbx+10h]
0x1800669b6  mov     edi, [rbx+74h]
0x1800669b9  cmp     edi, 7FFFFFFFh
0x1800669bf  jnz     short loc_1800669D3
0x1800669c1  mov     rcx, rbx; this
0x1800669c4  mov     rbx, [rsp+28h+arg_0]
0x1800669c9  add     rsp, 20h
0x1800669cd  pop     rdi
0x1800669ce  jmp     ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x1800669d3  call    cs:__imp_GetCurrentThread
0x1800669d9  mov     rcx, rax; hThread
0x1800669dc  mov     edx, edi; nPriority
0x1800669de  call    cs:__imp_SetThreadPriority
0x1800669e4  mov     dword ptr [rbx+74h], 7FFFFFFFh
0x1800669eb  jmp     short loc_1800669C1
```
