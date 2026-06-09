# ATL::AtlCallTermFunc(ATL::_ATL_MODULE70 *)

- ea: `0x18000b3b0`
- end: `0x18000b41d`
- name: `?AtlCallTermFunc@ATL@@YAXPEAU_ATL_MODULE70@1@@Z`
- size: `109`
- prototype: `void __fastcall(struct ATL::_ATL_MODULE70 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180001ff8`
- `0x180002070`

## callees

- `0x180006b74`
- `0x18000b3b0`
- `0x18000c010`

## import_xrefs

- `KERNEL32!RaiseException` at `0x18000b3d5`
- `KERNEL32!RaiseException` at `0x18000b3d5`

## pseudocode

```c
void __fastcall ATL::AtlCallTermFunc(struct ATL::_ATL_MODULE70 *a1)
{
  _QWORD *v2; // rsi
  _QWORD *v3; // rbx

  if ( !a1 )
  {
    RaiseException(0xC0000005, 1u, 0, 0);
    __debugbreak();
  }
  v2 = (_QWORD *)*((_QWORD *)a1 + 1);
  if ( v2 )
  {
    do
    {
      ((void (__fastcall *)(_QWORD))*v2)(v2[1]);
      v3 = (_QWORD *)v2[2];
      operator delete(v2);
      v2 = v3;
    }
    while ( v3 );
  }
  *((_QWORD *)a1 + 1) = 0;
}

```

## disassembly

```asm
0x18000b3b0  mov     [rsp+arg_0], rbx
0x18000b3b5  mov     [rsp+arg_8], rsi
0x18000b3ba  push    rdi
0x18000b3bb  sub     rsp, 20h
0x18000b3bf  mov     rdi, rcx
0x18000b3c2  test    rcx, rcx
0x18000b3c5  jnz     short loc_18000B3DC
0x18000b3c7  lea     edx, [rcx+1]; dwExceptionFlags
0x18000b3ca  xor     r9d, r9d; lpArguments
0x18000b3cd  mov     ecx, 0C0000005h; dwExceptionCode
0x18000b3d2  xor     r8d, r8d; nNumberOfArguments
0x18000b3d5  call    cs:__imp_RaiseException
0x18000b3db  int     3; Trap to Debugger
0x18000b3dc  mov     rsi, [rcx+8]
0x18000b3e0  test    rsi, rsi
0x18000b3e3  jz      short loc_18000B405
0x18000b3e5  mov     rcx, [rsi+8]
0x18000b3e9  mov     rax, [rsi]
0x18000b3ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3f1  mov     rbx, [rsi+10h]
0x18000b3f5  mov     rcx, rsi; Block
0x18000b3f8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b3fd  mov     rsi, rbx
0x18000b400  test    rbx, rbx
0x18000b403  jnz     short loc_18000B3E5
0x18000b405  mov     rbx, [rsp+28h+arg_0]
0x18000b40a  mov     rsi, [rsp+28h+arg_8]
0x18000b40f  mov     qword ptr [rdi+8], 0
0x18000b417  add     rsp, 20h
0x18000b41b  pop     rdi
0x18000b41c  retn
```
