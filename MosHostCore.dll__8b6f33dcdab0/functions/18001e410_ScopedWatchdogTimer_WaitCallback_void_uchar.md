# ScopedWatchdogTimer::WaitCallback(void *,uchar)

- ea: `0x18001e410`
- end: `0x18001e44d`
- name: `?WaitCallback@ScopedWatchdogTimer@@SAXPEAXE@Z`
- size: `61`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001e410`
- `0x180025010`

## import_xrefs

- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18001e439`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18001e439`

## string_xrefs

- `0x18001e41c`: `ScopedWatchdogTimer - operation in thread 0x%08x timed out`

## pseudocode

```c
void __fastcall ScopedWatchdogTimer::WaitCallback(void (**a1)(void), char a2)
{
  if ( a2 )
  {
    ZTraceHelperNoThis(
      0,
      "ScopedWatchdogTimer::WaitCallback",
      22,
      "ScopedWatchdogTimer - operation in thread 0x%08x timed out",
      *((_DWORD *)a1 + 2));
    (*a1)();
  }
}

```

## disassembly

```asm
0x18001e410  test    dl, dl
0x18001e412  jz      short locret_18001E44C
0x18001e414  push    rbx
0x18001e415  sub     rsp, 30h
0x18001e419  mov     eax, [rcx+8]
0x18001e41c  lea     r9, aScopedwatchdog_0; "ScopedWatchdogTimer - operation in thre"...
0x18001e423  mov     rbx, rcx
0x18001e426  mov     [rsp+38h+var_18], eax
0x18001e42a  xor     ecx, ecx
0x18001e42c  lea     rdx, aScopedwatchdog_1; "ScopedWatchdogTimer::WaitCallback"
0x18001e433  mov     r8d, 16h
0x18001e439  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x18001e43f  mov     rax, [rbx]
0x18001e442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e447  add     rsp, 30h
0x18001e44b  pop     rbx
0x18001e44c  retn
```
