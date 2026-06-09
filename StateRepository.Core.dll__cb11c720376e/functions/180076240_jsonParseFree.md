# jsonParseFree

- ea: `0x180076240`
- end: `0x180076273`
- name: `jsonParseFree`
- size: `51`
- prototype: `void __fastcall(__int64)`
- caller_count: `11`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180073360`
- `0x180073a10`
- `0x180073a54`
- `0x180074920`
- `0x180075144`
- `0x18007627c`
- `0x180076530`
- `0x1800765e0`
- `0x180076860`
- `0x180078580`
- `0x180078870`

## callees

- `0x18000a9e0`
- `0x180076240`
- `0x1800764cc`

## pseudocode

```c
void __fastcall jsonParseFree(__int64 a1)
{
  unsigned int v1; // eax

  if ( a1 )
  {
    v1 = *(_DWORD *)(a1 + 36);
    if ( v1 <= 1 )
    {
      jsonParseReset(a1);
      sqlite3DbFree(*(_QWORD *)(a1 + 24), a1);
    }
    else
    {
      *(_DWORD *)(a1 + 36) = v1 - 1;
    }
  }
}

```

## disassembly

```asm
0x180076240  test    rcx, rcx
0x180076243  jz      short locret_180076272
0x180076245  push    rbx
0x180076246  sub     rsp, 20h
0x18007624a  mov     eax, [rcx+24h]
0x18007624d  mov     rbx, rcx
0x180076250  cmp     eax, 1
0x180076253  jbe     short loc_18007625C
0x180076255  dec     eax
0x180076257  mov     [rcx+24h], eax
0x18007625a  jmp     short loc_18007626D
0x18007625c  call    jsonParseReset
0x180076261  mov     rcx, [rbx+18h]
0x180076265  mov     rdx, rbx
0x180076268  call    sqlite3DbFree
0x18007626d  add     rsp, 20h
0x180076271  pop     rbx
0x180076272  retn
```
