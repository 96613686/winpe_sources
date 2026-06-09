# sub_18002CCBC

- ea: `0x18002ccbc`
- end: `0x18002cd0c`
- name: `sub_18002CCBC`
- size: `80`
- prototype: `void __fastcall(char *lpMem)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180025160`

## callees

- `0x180023610`
- `0x18002ccbc`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18002cce5`
- `KERNEL32!DeleteCriticalSection` at `0x18002cce5`

## pseudocode

```c
void __fastcall sub_18002CCBC(char *lpMem)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  struct _RTL_CRITICAL_SECTION *v3; // rdi

  if ( lpMem )
  {
    v1 = (struct _RTL_CRITICAL_SECTION *)(lpMem + 4608);
    v3 = (struct _RTL_CRITICAL_SECTION *)lpMem;
    do
    {
      DeleteCriticalSection(v3);
      v3 = (struct _RTL_CRITICAL_SECTION *)((char *)v3 + 72);
    }
    while ( v3 != v1 );
    sub_180023610(lpMem);
  }
}

```

## disassembly

```asm
0x18002ccbc  test    rcx, rcx
0x18002ccbf  jz      short locret_18002CD0B
0x18002ccc1  mov     [rsp+arg_0], rbx
0x18002ccc6  mov     [rsp+arg_8], rsi
0x18002cccb  push    rdi
0x18002cccc  sub     rsp, 20h
0x18002ccd0  lea     rsi, [rcx+1200h]
0x18002ccd7  mov     rbx, rcx
0x18002ccda  mov     rdi, rcx
0x18002ccdd  cmp     rcx, rsi
0x18002cce0  jz      short loc_18002CCF4
0x18002cce2  mov     rcx, rdi; lpCriticalSection
0x18002cce5  call    cs:__imp_DeleteCriticalSection
0x18002cceb  add     rdi, 48h ; 'H'
0x18002ccef  cmp     rdi, rsi
0x18002ccf2  jnz     short loc_18002CCE2
0x18002ccf4  mov     rcx, rbx; lpMem
0x18002ccf7  call    sub_180023610
0x18002ccfc  mov     rbx, [rsp+28h+arg_0]
0x18002cd01  mov     rsi, [rsp+28h+arg_8]
0x18002cd06  add     rsp, 20h
0x18002cd0a  pop     rdi
0x18002cd0b  retn
```
