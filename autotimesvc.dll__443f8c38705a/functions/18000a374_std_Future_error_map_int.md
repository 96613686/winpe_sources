# std::_Future_error_map(int)

- ea: `0x18000a374`
- end: `0x18000a3ab`
- name: `?_Future_error_map@std@@YAPEBDH@Z`
- size: `55`
- prototype: `const char *__fastcall(int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a980`
- `0x18000acc0`

## callees

- `0x18000a374`

## string_xrefs

- `0x18000a39b`: `future already retrieved`
- `0x18000a393`: `promise already satisfied`

## pseudocode

```c
const char *__fastcall std::_Future_error_map(int a1)
{
  int v1; // ecx
  int v2; // ecx
  int v3; // ecx

  v1 = a1 - 1;
  if ( !v1 )
    return "broken promise";
  v2 = v1 - 1;
  if ( !v2 )
    return "future already retrieved";
  v3 = v2 - 1;
  if ( !v3 )
    return "promise already satisfied";
  if ( v3 == 1 )
    return "no state";
  return 0;
}

```

## disassembly

```asm
0x18000a374  sub     ecx, 1
0x18000a377  jz      short loc_18000A3A3
0x18000a379  sub     ecx, 1
0x18000a37c  jz      short loc_18000A39B
0x18000a37e  sub     ecx, 1
0x18000a381  jz      short loc_18000A393
0x18000a383  cmp     ecx, 1
0x18000a386  jz      short loc_18000A38B
0x18000a388  xor     eax, eax
0x18000a38a  retn
0x18000a38b  lea     rax, aNoState; "no state"
0x18000a392  retn
0x18000a393  lea     rax, aPromiseAlready; "promise already satisfied"
0x18000a39a  retn
0x18000a39b  lea     rax, aFutureAlreadyR; "future already retrieved"
0x18000a3a2  retn
0x18000a3a3  lea     rax, aBrokenPromise; "broken promise"
0x18000a3aa  retn
```
