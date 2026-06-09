# SwitchOrSleep(int &)

- ea: `0x1400053b8`
- end: `0x1400053dc`
- name: `?SwitchOrSleep@@YAXAEAH@Z`
- size: `36`
- prototype: `void __fastcall(DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400053dc`

## callees

- `0x1400053b8`

## import_xrefs

- `KERNEL32!SwitchToThread` at `0x1400053c1`
- `KERNEL32!SwitchToThread` at `0x1400053c1`
- `KERNEL32!Sleep` at `0x1400053cd`
- `KERNEL32!Sleep` at `0x1400053cd`

## pseudocode

```c
void __fastcall SwitchOrSleep(DWORD *a1)
{
  if ( !SwitchToThread() )
  {
    Sleep(*a1);
    *a1 ^= 1u;
  }
}

```

## disassembly

```asm
0x1400053b8  push    rbx
0x1400053ba  sub     rsp, 20h
0x1400053be  mov     rbx, rcx
0x1400053c1  call    cs:__imp_SwitchToThread
0x1400053c7  test    eax, eax
0x1400053c9  jnz     short loc_1400053D6
0x1400053cb  mov     ecx, [rbx]; dwMilliseconds
0x1400053cd  call    cs:__imp_Sleep
0x1400053d3  xor     dword ptr [rbx], 1
0x1400053d6  add     rsp, 20h
0x1400053da  pop     rbx
0x1400053db  retn
```
