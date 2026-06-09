# SafeRelease<IMFMediaType>(IMFMediaType * *)

- ea: `0x180001f8c`
- end: `0x180001fb6`
- name: `??$SafeRelease@UIMFMediaType@@@@YAXPEAPEAUIMFMediaType@@@Z`
- size: `42`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180001fbc`
- `0x180002180`
- `0x180002440`
- `0x180002b14`
- `0x180003080`
- `0x180003190`

## callees

- `0x180001f8c`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall SafeRelease<IMFMediaType>(__int64 *a1)
{
  __int64 v2; // rcx
  __int64 result; // rax

  v2 = *a1;
  if ( v2 )
  {
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180001f8c  push    rbx
0x180001f8e  sub     rsp, 20h
0x180001f92  mov     rbx, rcx
0x180001f95  mov     rcx, [rcx]
0x180001f98  test    rcx, rcx
0x180001f9b  jz      short loc_180001FB0
0x180001f9d  mov     rax, [rcx]
0x180001fa0  mov     rax, [rax+10h]
0x180001fa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fa9  mov     qword ptr [rbx], 0
0x180001fb0  add     rsp, 20h
0x180001fb4  pop     rbx
0x180001fb5  retn
```
