# DialogBlockingService::OnSessionUserChanged(ulong,ulong,unsigned __int64)

- ea: `0x180006248`
- end: `0x180006276`
- name: `?OnSessionUserChanged@DialogBlockingService@@QEAAXKK_K@Z`
- size: `46`
- prototype: `void __fastcall(Windows::Internal::DialogBlocking::ServiceSessions **this, int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180005b00`

## callees

- `0x180006248`
- `0x18000a538`
- `0x18000a65c`

## pseudocode

```c
void __fastcall DialogBlockingService::OnSessionUserChanged(
        Windows::Internal::DialogBlocking::ServiceSessions **this,
        int a2,
        unsigned int a3)
{
  int v3; // edx

  try
  {
    v3 = a2 - 5;
    if ( v3 )
    {
      if ( v3 == 1 )
        Windows::Internal::DialogBlocking::ServiceSessions::logoffUser(this[7], a3);
    }
    else
    {
      Windows::Internal::DialogBlocking::ServiceSessions::logonUser(this[7], a3);
    }
  }
  catch ( ... )
  {
  }
}

```

## disassembly

```asm
0x180006248  sub     rsp, 28h
0x18000624c  sub     edx, 5
0x18000624f  jz      short loc_180006264
0x180006251  cmp     edx, 1
0x180006254  jnz     short loc_180006271
0x180006256  mov     edx, r8d; unsigned int
0x180006259  mov     rcx, [rcx+38h]; this
0x18000625d  call    ?logoffUser@ServiceSessions@DialogBlocking@Internal@Windows@@QEAAXK@Z; Windows::Internal::DialogBlocking::ServiceSessions::logoffUser(ulong)
0x180006262  jmp     short loc_180006271
0x180006264  mov     edx, r8d; unsigned int
0x180006267  mov     rcx, [rcx+38h]; this
0x18000626b  call    ?logonUser@ServiceSessions@DialogBlocking@Internal@Windows@@QEAAXK@Z; Windows::Internal::DialogBlocking::ServiceSessions::logonUser(ulong)
0x180006270  nop
0x180006271  add     rsp, 28h
0x180006275  retn
```
