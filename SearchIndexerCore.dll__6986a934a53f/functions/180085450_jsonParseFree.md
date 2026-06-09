# jsonParseFree

- ea: `0x180085450`
- end: `0x180085483`
- name: `jsonParseFree`
- size: `51`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `11`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800825d0`
- `0x180082c80`
- `0x180082cc4`
- `0x180083b70`
- `0x180084384`
- `0x18008548c`
- `0x180085740`
- `0x1800857f0`
- `0x180085a70`
- `0x180087790`
- `0x180087a80`

## callees

- `0x180041d10`
- `0x180085450`
- `0x1800856dc`

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
0x180085450  test    rcx, rcx
0x180085453  jz      short locret_180085482
0x180085455  push    rbx
0x180085456  sub     rsp, 20h
0x18008545a  mov     eax, [rcx+24h]
0x18008545d  mov     rbx, rcx
0x180085460  cmp     eax, 1
0x180085463  jbe     short loc_18008546C
0x180085465  dec     eax
0x180085467  mov     [rcx+24h], eax
0x18008546a  jmp     short loc_18008547D
0x18008546c  call    jsonParseReset
0x180085471  mov     rcx, [rbx+18h]
0x180085475  mov     rdx, rbx
0x180085478  call    sqlite3DbFree
0x18008547d  add     rsp, 20h
0x180085481  pop     rbx
0x180085482  retn
```
