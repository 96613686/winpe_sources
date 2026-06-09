# ATL::CComPtr<IBackgroundCopyJob>::Release(void)

- ea: `0x18001c328`
- end: `0x18001c350`
- name: `?Release@?$CComPtr@UIBackgroundCopyJob@@@ATL@@QEAAXXZ`
- size: `40`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001b05c`
- `0x18001cab8`

## callees

- `0x18001c328`
- `0x180021010`

## pseudocode

```c
_QWORD *__fastcall ATL::CComPtr<IBackgroundCopyJob>::Release(_QWORD *a1)
{
  _QWORD *result; // rax
  __int64 v2; // rcx

  result = a1;
  v2 = *a1;
  if ( v2 )
  {
    *result = 0;
    return (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  return result;
}

```

## disassembly

```asm
0x18001c328  sub     rsp, 28h
0x18001c32c  mov     rax, rcx
0x18001c32f  mov     rcx, [rcx]
0x18001c332  test    rcx, rcx
0x18001c335  jz      short loc_18001C34A
0x18001c337  mov     qword ptr [rax], 0
0x18001c33e  mov     rax, [rcx]
0x18001c341  mov     rax, [rax+10h]
0x18001c345  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c34a  add     rsp, 28h
0x18001c34e  retn
```
