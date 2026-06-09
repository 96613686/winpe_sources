# __security_check_cookie(x)

- ea: `0x40cb60`
- end: `0x40cb70`
- name: `@__security_check_cookie@4`
- size: `16`
- prototype: `void __fastcall(uintptr_t StackCookie)`
- caller_count: `39`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x402737`
- `0x4027bb`
- `0x40285e`
- `0x402918`
- `0x403291`
- `0x40373b`
- `0x404214`
- `0x4044ae`
- `0x40494e`
- `0x404c02`
- `0x405304`
- `0x4067aa`
- `0x406bda`
- `0x406e8a`
- `0x406f2f`
- `0x406fdc`
- `0x40723a`
- `0x4072e3`
- `0x4076da`
- `0x407a3f`
- `0x407c3c`
- `0x407ca8`
- `0x407d14`
- `0x407eab`
- `0x407fd4`
- `0x408235`
- `0x408fe0`
- `0x409212`
- `0x409551`
- `0x409933`
- `0x40a256`
- `0x40a422`
- `0x40aec9`
- `0x40b08b`
- `0x40c09d`
- `0x40c146`
- `0x40c3ba`
- `0x40de00`
- `0x40ea20`

## callees

- `0x40cb60`
- `0x40cbdb`

## pseudocode

```c
void __fastcall __security_check_cookie(uintptr_t StackCookie)
{
  if ( StackCookie != __security_cookie )
    __report_gsfailure();
}

```

## disassembly

```asm
0x40cb60  cmp     ecx, ___security_cookie
0x40cb66  jnz     short loc_40CB6B
0x40cb68  retn    0
0x40cb6b  jmp     ___report_gsfailure
```
