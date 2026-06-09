# Windows::AutoComPtr<IClassFactory>::GetInitPointer(void)

- ea: `0x140007630`
- end: `0x14000764d`
- name: `?GetInitPointer@?$AutoComPtr@UIClassFactory@@@Windows@@QEAAPEAPEAUIClassFactory@@XZ`
- size: `29`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `15`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140007770`
- `0x140009b2c`
- `0x14000d23c`
- `0x1400108cc`
- `0x140010d00`
- `0x140011810`
- `0x140012b70`
- `0x1400145e4`
- `0x140014d60`
- `0x140015b90`
- `0x14001a16c`
- `0x14001a4c0`
- `0x14001a7e4`
- `0x14001acbc`
- `0x14001afa4`

## callees

- `0x140007630`
- `0x1400076ec`

## pseudocode

```c
_QWORD *__fastcall Windows::AutoComPtr<IClassFactory>::GetInitPointer(_QWORD *a1)
{
  if ( *a1 )
    INTERNAL_ERROR_ACTION(-1073741595);
  return a1;
}

```

## disassembly

```asm
0x140007630  sub     rsp, 28h
0x140007634  cmp     qword ptr [rcx], 0
0x140007638  jnz     short loc_140007642
0x14000763a  mov     rax, rcx
0x14000763d  add     rsp, 28h
0x140007641  retn
0x140007642  mov     ecx, 0C00000E5h; int
0x140007647  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
