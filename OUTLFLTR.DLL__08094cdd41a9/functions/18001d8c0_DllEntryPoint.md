# DllEntryPoint

- ea: `0x18001d8c0`
- end: `0x18001d91c`
- name: `DllEntryPoint`
- size: `92`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180019120`
- `0x18001d8c0`
- `0x180088880`
- `0x18008d070`

## pseudocode

```c
BOOL __stdcall DllEntryPoint(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  int v7; // ebx

  if ( fdwReason == 1 && (int)sub_180019120() < 0 )
  {
    sub_18008D070();
    return 0;
  }
  else
  {
    v7 = sub_180088880(hinstDLL, fdwReason, lpReserved);
    if ( !fdwReason )
      sub_18008D070();
    return v7;
  }
}

```

## disassembly

```asm
0x18001d8c0  mov     [rsp+arg_0], rbx
0x18001d8c5  mov     [rsp+arg_8], rsi
0x18001d8ca  push    rdi
0x18001d8cb  sub     rsp, 20h
0x18001d8cf  cmp     edx, 1
0x18001d8d2  mov     rbx, r8
0x18001d8d5  mov     rsi, rcx
0x18001d8d8  mov     edi, edx
0x18001d8da  jnz     short loc_18001D8EE
0x18001d8dc  call    sub_180019120
0x18001d8e1  test    eax, eax
0x18001d8e3  jns     short loc_18001D8EE
0x18001d8e5  call    sub_18008D070
0x18001d8ea  xor     eax, eax
0x18001d8ec  jmp     short loc_18001D90C
0x18001d8ee  mov     rcx, rsi
0x18001d8f1  mov     rax, cs:off_1800637A0
0x18001d8f8  mov     r8, rbx
0x18001d8fb  mov     edx, edi
0x18001d8fd  call    rax ; sub_180088880
0x18001d8ff  test    edi, edi
0x18001d901  mov     ebx, eax
0x18001d903  jnz     short loc_18001D90A
0x18001d905  call    sub_18008D070
0x18001d90a  mov     eax, ebx
0x18001d90c  mov     rsi, [rsp+28h+arg_8]
0x18001d911  mov     rbx, [rsp+28h+arg_0]
0x18001d916  add     rsp, 20h
0x18001d91a  pop     rdi
0x18001d91b  retn
```
