# ServiceMain(ulong,ushort * *)

- ea: `0x180006d10`
- end: `0x180006d3a`
- name: `?ServiceMain@@YAXKPEAPEAG@Z`
- size: `42`
- prototype: `void __fastcall(int, const wchar_t **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x1800068b0`
- `0x180006d10`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180006d26`
- `msvcrt!_wcsicmp` at `0x180006d26`

## pseudocode

```c
void __fastcall ServiceMain(int a1, const wchar_t **a2)
{
  if ( a1 == 1 && !_wcsicmp(*a2, L"apphostsvc") )
    AppHostServiceMain();
}

```

## disassembly

```asm
0x180006d10  sub     rsp, 28h
0x180006d14  mov     rax, rdx
0x180006d17  cmp     ecx, 1
0x180006d1a  jnz     short loc_180006D35
0x180006d1c  mov     rcx, [rax]; String1
0x180006d1f  lea     rdx, aApphostsvc_1; "apphostsvc"
0x180006d26  call    cs:__imp__wcsicmp
0x180006d2c  test    eax, eax
0x180006d2e  jnz     short loc_180006D35
0x180006d30  call    ?AppHostServiceMain@@YAXXZ; AppHostServiceMain(void)
0x180006d35  add     rsp, 28h
0x180006d39  retn
```
