# ValidateBufferAndCount

- ea: `0x180004a20`
- end: `0x180004a87`
- name: `ValidateBufferAndCount`
- size: `103`
- prototype: `void __fastcall(__int64, int)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x18000da04`
- `0x18000dcc8`
- `0x18000de90`
- `0x18000e70c`

## callees

- `0x180004a20`
- `0x180006608`
- `0x18000895c`
- `0x18000cab4`

## pseudocode

```c
void __fastcall ValidateBufferAndCount(__int64 a1, int a2)
{
  _BYTE pExceptionObject[216]; // [rsp+20h] [rbp-D8h] BYREF

  if ( !a1 && a2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_b3b320b7595b350a842d079d8560ec21_Traceguids);
    HResultException::HResultException((HResultException *)pExceptionObject, -2147024809);
    throw (HResultException *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x180004a20  sub     rsp, 0F8h
0x180004a27  test    rcx, rcx
0x180004a2a  jnz     short loc_180004A30
0x180004a2c  test    edx, edx
0x180004a2e  jnz     short loc_180004A38
0x180004a30  add     rsp, 0F8h
0x180004a37  retn
0x180004a38  mov     rcx, cs:WPP_GLOBAL_Control
0x180004a3f  lea     rax, WPP_GLOBAL_Control
0x180004a46  cmp     rcx, rax
0x180004a49  jz      short loc_180004A66
0x180004a4b  cmp     byte ptr [rcx+19h], 2
0x180004a4f  jb      short loc_180004A66
0x180004a51  mov     rcx, [rcx+10h]
0x180004a55  lea     r8, WPP_b3b320b7595b350a842d079d8560ec21_Traceguids
0x180004a5c  mov     edx, 0Ch
0x180004a61  call    WPP_SF_
0x180004a66  mov     edx, 80070057h; int
0x180004a6b  lea     rcx, [rsp+0F8h+pExceptionObject]; this
0x180004a70  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180004a75  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180004a7c  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x180004a81  call    _CxxThrowException_0
```
