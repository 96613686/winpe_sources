# SdbpGetPathSystem

- ea: `0x14002d790`
- end: `0x14002d827`
- name: `SdbpGetPathSystem`
- size: `151`
- prototype: `__int64 __fastcall(NTSTRSAFE_PWSTR pszDest, size_t cchDest, NTSTRSAFE_PCWSTR)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x14002d790`
- `0x14002d830`
- `0x140032c14`
- `0x14003e364`

## string_xrefs

- `0x14002d806`: `SdbpGetPathSystem`
- `0x14002d7f9`: `AslEnvGetSystem32DirPathBuf failed [%x]`

## pseudocode

```c
__int64 __fastcall SdbpGetPathSystem(NTSTRSAFE_PWSTR pszDest, size_t cchDest, NTSTRSAFE_PCWSTR a3, __int64 a4)
{
  int ProcessHostGuestArchitectures; // eax
  unsigned int v8; // ebx
  const char *v9; // r9
  __int64 v10; // r8
  __int64 v12; // [rsp+20h] [rbp-48h]
  __int16 v13[2]; // [rsp+30h] [rbp-38h] BYREF
  __int16 v14; // [rsp+34h] [rbp-34h] BYREF

  v14 = 0;
  v13[0] = 0;
  ProcessHostGuestArchitectures = SdbpGetProcessHostGuestArchitectures(&v14, v13, a4);
  v8 = ProcessHostGuestArchitectures;
  if ( ProcessHostGuestArchitectures < 0 )
  {
    v9 = "SdbpGetProcessHostGuestArchitectures failed [%x]";
    v10 = 1054;
LABEL_5:
    LODWORD(v12) = ProcessHostGuestArchitectures;
    AslLogCallPrintf(1, "SdbpGetPathSystem", v10, v9, v12);
    return v8;
  }
  ProcessHostGuestArchitectures = AslEnvGetSystem32DirPathBuf(pszDest, cchDest, a3, v14, v13);
  v8 = ProcessHostGuestArchitectures;
  if ( ProcessHostGuestArchitectures < 0 )
  {
    v9 = "AslEnvGetSystem32DirPathBuf failed [%x]";
    v10 = 1060;
    goto LABEL_5;
  }
  return v8;
}

```

## disassembly

```asm
0x14002d790  push    rbx
0x14002d792  push    rbp
0x14002d793  push    rsi
0x14002d794  push    rdi
0x14002d795  sub     rsp, 48h
0x14002d799  xor     eax, eax
0x14002d79b  mov     rdi, r8
0x14002d79e  mov     rsi, rdx
0x14002d7a1  mov     [rsp+68h+var_38+4], ax
0x14002d7a6  mov     rbp, rcx
0x14002d7a9  mov     [rsp+68h+var_38], ax
0x14002d7ae  mov     r8, r9
0x14002d7b1  lea     rdx, [rsp+68h+var_38]
0x14002d7b6  lea     rcx, [rsp+68h+var_38+4]
0x14002d7bb  call    SdbpGetProcessHostGuestArchitectures
0x14002d7c0  mov     ebx, eax
0x14002d7c2  test    eax, eax
0x14002d7c4  jns     short loc_14002D7D5
0x14002d7c6  lea     r9, aSdbpgetprocess; "SdbpGetProcessHostGuestArchitectures fa"...
0x14002d7cd  mov     r8d, 41Eh
0x14002d7d3  jmp     short loc_14002D806
0x14002d7d5  movzx   r9d, [rsp+68h+var_38+4]
0x14002d7db  lea     rax, [rsp+68h+var_38]
0x14002d7e0  mov     r8, rdi; NTSTRSAFE_PCWSTR
0x14002d7e3  mov     [rsp+68h+var_48], rax; __int64
0x14002d7e8  mov     rdx, rsi; cchDest
0x14002d7eb  mov     rcx, rbp; pszDest
0x14002d7ee  call    AslEnvGetSystem32DirPathBuf
0x14002d7f3  mov     ebx, eax
0x14002d7f5  test    eax, eax
0x14002d7f7  jns     short loc_14002D81B
0x14002d7f9  lea     r9, aAslenvgetsyste_0; "AslEnvGetSystem32DirPathBuf failed [%x]"
0x14002d800  mov     r8d, 424h
0x14002d806  lea     rdx, aSdbpgetpathsys; "SdbpGetPathSystem"
0x14002d80d  mov     dword ptr [rsp+68h+var_48], eax
0x14002d811  mov     ecx, 1
0x14002d816  call    AslLogCallPrintf
0x14002d81b  mov     eax, ebx
0x14002d81d  add     rsp, 48h
0x14002d821  pop     rdi
0x14002d822  pop     rsi
0x14002d823  pop     rbp
0x14002d824  pop     rbx
0x14002d825  retn
```
