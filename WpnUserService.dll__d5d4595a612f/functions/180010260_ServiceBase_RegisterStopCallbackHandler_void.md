# ServiceBase::_RegisterStopCallbackHandler(void)

- ea: `0x180010260`
- end: `0x1800102ab`
- name: `?_RegisterStopCallbackHandler@ServiceBase@@MEAAJXZ`
- size: `75`
- prototype: `__int64 __fastcall(ServiceBase *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180010260`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall ServiceBase::_RegisterStopCallbackHandler(ServiceBase *this)
{
  __int64 result; // rax

  result = (*(__int64 (__fastcall **)(char *, char *, _QWORD, __int64 (__fastcall *)(), ServiceBase *, int))(*((_QWORD *)this + 22) + 192LL))(
             (char *)this + 88,
             (char *)this + 8,
             *((_QWORD *)this + 10),
             StopCallback,
             this,
             8);
  if ( (int)result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180010260  sub     rsp, 48h
0x180010264  mov     rax, [rcx+0B0h]
0x18001026b  lea     rdx, [rcx+8]
0x18001026f  mov     r8, rcx
0x180010272  mov     [rsp+48h+var_20], 8
0x18001027a  mov     [rsp+48h+var_28], r8
0x18001027f  lea     r9, StopCallback
0x180010286  add     rcx, 58h ; 'X'
0x18001028a  mov     rax, [rax+0C0h]
0x180010291  mov     r8, [r8+50h]
0x180010295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001029a  test    eax, eax
0x18001029c  jle     short loc_1800102A6
0x18001029e  movzx   eax, ax
0x1800102a1  or      eax, 80070000h
0x1800102a6  add     rsp, 48h
0x1800102aa  retn
```
