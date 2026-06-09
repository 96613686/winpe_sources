# AhcpCacheEnumEntryClearForReboot

- ea: `0x140028b90`
- end: `0x140028bf5`
- name: `AhcpCacheEnumEntryClearForReboot`
- size: `101`
- prototype: `__int64 __fastcall(bool *, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140028850`
- `0x140028b90`
- `0x14003e364`

## string_xrefs

- `0x140028bb3`: `AhcpCacheEntryFilterForReboot failed [%x]`
- `0x140028bc4`: `AhcpCacheEnumEntryClearForReboot`

## pseudocode

```c
__int64 __fastcall AhcpCacheEnumEntryClearForReboot(bool *a1, __int64 a2, __int64 a3)
{
  int v5; // eax
  unsigned int v6; // ebx

  v5 = AhcpCacheEntryFilterForReboot(a3);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v6 = 0;
    *a1 = *(_DWORD *)(a3 + 16) == 0;
  }
  else
  {
    AslLogCallPrintf(1, "AhcpCacheEnumEntryClearForReboot", 559, "AhcpCacheEntryFilterForReboot failed [%x]", v5);
  }
  return v6;
}

```

## disassembly

```asm
0x140028b90  mov     [rsp+arg_0], rbx
0x140028b95  mov     [rsp+arg_8], rsi
0x140028b9a  push    rdi
0x140028b9b  sub     rsp, 30h
0x140028b9f  mov     rsi, rcx
0x140028ba2  mov     rdi, r8
0x140028ba5  mov     rcx, r8
0x140028ba8  call    AhcpCacheEntryFilterForReboot
0x140028bad  mov     ebx, eax
0x140028baf  test    eax, eax
0x140028bb1  jns     short loc_140028BD7
0x140028bb3  lea     r9, aAhcpcacheentry_3; "AhcpCacheEntryFilterForReboot failed [%"...
0x140028bba  mov     [rsp+38h+var_18], eax
0x140028bbe  mov     r8d, 22Fh
0x140028bc4  lea     rdx, aAhcpcacheenume; "AhcpCacheEnumEntryClearForReboot"
0x140028bcb  mov     ecx, 1
0x140028bd0  call    AslLogCallPrintf
0x140028bd5  jmp     short loc_140028BE2
0x140028bd7  cmp     dword ptr [rdi+10h], 0
0x140028bdb  setz    al
0x140028bde  xor     ebx, ebx
0x140028be0  mov     [rsi], al
0x140028be2  mov     rsi, [rsp+38h+arg_8]
0x140028be7  mov     eax, ebx
0x140028be9  mov     rbx, [rsp+38h+arg_0]
0x140028bee  add     rsp, 30h
0x140028bf2  pop     rdi
0x140028bf3  retn
```
