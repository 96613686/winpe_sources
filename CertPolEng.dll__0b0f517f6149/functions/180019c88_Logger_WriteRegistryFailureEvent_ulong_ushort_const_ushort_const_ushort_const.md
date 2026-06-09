# Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *,ushort const *)

- ea: `0x180019c88`
- end: `0x180019cba`
- name: `?WriteRegistryFailureEvent@Logger@@SAJKPEBG00@Z`
- size: `50`
- prototype: `int __fastcall(unsigned int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180019024`

## callees

- `0x18000aa90`

## pseudocode

```c
int __fastcall Logger::WriteRegistryFailureEvent(
        unsigned int a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  const wchar_t *v4; // rax

  v4 = L"<NULL>";
  if ( a4 )
    v4 = a4;
  return Logger::WriteRegistryFailureEventEx(a1, L"RegGetValueW", L"%s@%s", a3, v4);
}

```

## disassembly

```asm
0x180019c88  sub     rsp, 38h
0x180019c8c  test    r9, r9
0x180019c8f  lea     rax, aNull_2; "<NULL>"
0x180019c96  lea     rdx, aReggetvaluew; "RegGetValueW"
0x180019c9d  cmovnz  rax, r9
0x180019ca1  mov     r9, r8
0x180019ca4  lea     r8, aSS; "%s@%s"
0x180019cab  mov     [rsp+38h+var_18], rax
0x180019cb0  call    ?WriteRegistryFailureEventEx@Logger@@SAJKPEBG0ZZ; Logger::WriteRegistryFailureEventEx(ulong,ushort const *,ushort const *,...)
0x180019cb5  add     rsp, 38h
0x180019cb9  retn
```
