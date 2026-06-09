# AuthHostWebInstance::GetSecurityId(IUri *,uchar *,ulong *)

- ea: `0x140010470`
- end: `0x140010476`
- name: `?GetSecurityId@AuthHostWebInstance@@UEAAJPEAUIUri@@PEAEPEAK@Z`
- size: `6`
- prototype: `__int64 __fastcall(AuthHostWebInstance *__hidden this, struct IUri *, unsigned __int8 *, unsigned int *)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1400053e0`

## pseudocode

```c
__int64 __fastcall AuthHostWebInstance::GetSecurityId(
        AuthHostWebInstance *this,
        struct IUri *a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  return 2148270097LL;
}

```

## disassembly

```asm
0x140010470  mov     eax, 800C0011h
0x140010475  retn
```
