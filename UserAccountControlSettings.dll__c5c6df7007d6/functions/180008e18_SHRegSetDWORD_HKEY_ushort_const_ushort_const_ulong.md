# SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)

- ea: `0x180008e18`
- end: `0x180008e41`
- name: `?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z`
- size: `41`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180008e50`

## callees

- `0x180008e18`
- `0x180008fec`

## pseudocode

```c
__int64 __fastcall SHRegSetDWORD(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3, __int64 a4)
{
  __int64 result; // rax
  int v5; // [rsp+68h] [rbp+20h] BYREF

  v5 = a4;
  result = _RegSetKeyValueWithSDDL(a1, a2, a3, a4, (BYTE *)&v5);
  if ( (int)result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180008e18  mov     [rsp+arg_18], r9d
0x180008e1d  sub     rsp, 48h
0x180008e21  lea     rax, [rsp+48h+arg_18]
0x180008e26  mov     [rsp+48h+var_28], rax; void *
0x180008e2b  call    ?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEBG1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z; _RegSetKeyValueWithSDDL(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)
0x180008e30  test    eax, eax
0x180008e32  jle     short loc_180008E3C
0x180008e34  movzx   eax, ax
0x180008e37  or      eax, 80070000h
0x180008e3c  add     rsp, 48h
0x180008e40  retn
```
