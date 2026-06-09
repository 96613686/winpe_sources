# InvasivePtr<AppHostConfigPathNavigator>::Reset(void)

- ea: `0x1800039ec`
- end: `0x180003a13`
- name: `?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ`
- size: `39`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `24`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800021c8`
- `0x180002544`
- `0x180002600`
- `0x180002700`
- `0x1800033d0`
- `0x18000446c`
- `0x180004840`
- `0x180004900`
- `0x180004980`
- `0x1800052d0`
- `0x180005dc8`
- `0x180005e90`
- `0x180005f10`
- `0x1800062a0`
- `0x180006a88`
- `0x180006b50`
- `0x180006bd0`
- `0x180006f70`
- `0x180009018`
- `0x1800090e0`
- `0x180009160`
- `0x180009460`
- `0x18000cc48`
- `0x18000d6bc`

## callees

- `0x18000299c`
- `0x1800039ec`

## pseudocode

```c
__int64 __fastcall InvasivePtr<AppHostConfigPathNavigator>::Reset(__int64 *a1)
{
  __int64 v2; // rcx
  __int64 result; // rax

  v2 = *a1;
  if ( v2 )
  {
    result = InvasivePtrObject::Dereference((InvasivePtrObject *)(v2 + 16));
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800039ec  push    rbx
0x1800039ee  sub     rsp, 20h
0x1800039f2  mov     rbx, rcx
0x1800039f5  mov     rcx, [rcx]
0x1800039f8  test    rcx, rcx
0x1800039fb  jz      short loc_180003A0D
0x1800039fd  add     rcx, 10h; this
0x180003a01  call    ?Dereference@InvasivePtrObject@@QEAAJXZ; InvasivePtrObject::Dereference(void)
0x180003a06  mov     qword ptr [rbx], 0
0x180003a0d  add     rsp, 20h
0x180003a11  pop     rbx
0x180003a12  retn
```
