# InvasivePtr<ConfigLocationsTree>::Reset(void)

- ea: `0x180003a1c`
- end: `0x180003a3f`
- name: `?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ`
- size: `35`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `23`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800020f0`
- `0x1800021d4`
- `0x18000280c`
- `0x1800033d0`
- `0x180004320`
- `0x18000442c`
- `0x1800044ac`
- `0x180004c04`
- `0x1800052d0`
- `0x180005bfc`
- `0x180005fdc`
- `0x1800062a0`
- `0x1800069e4`
- `0x180006cf4`
- `0x180006f70`
- `0x180007718`
- `0x180007f94`
- `0x180008190`
- `0x180008f80`
- `0x1800092a0`
- `0x180009460`
- `0x180009b74`
- `0x18001082c`

## callees

- `0x18000299c`
- `0x180003a1c`

## pseudocode

```c
__int64 __fastcall InvasivePtr<ConfigLocationsTree>::Reset(InvasivePtrObject **a1)
{
  InvasivePtrObject *v2; // rcx
  __int64 result; // rax

  v2 = *a1;
  if ( v2 )
  {
    result = InvasivePtrObject::Dereference(v2);
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180003a1c  push    rbx
0x180003a1e  sub     rsp, 20h
0x180003a22  mov     rbx, rcx
0x180003a25  mov     rcx, [rcx]; this
0x180003a28  test    rcx, rcx
0x180003a2b  jz      short loc_180003A39
0x180003a2d  call    ?Dereference@InvasivePtrObject@@QEAAJXZ; InvasivePtrObject::Dereference(void)
0x180003a32  mov     qword ptr [rbx], 0
0x180003a39  add     rsp, 20h
0x180003a3d  pop     rbx
0x180003a3e  retn
```
