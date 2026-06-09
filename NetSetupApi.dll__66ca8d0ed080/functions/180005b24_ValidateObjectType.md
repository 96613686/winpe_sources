# ValidateObjectType

- ea: `0x180005b24`
- end: `0x180005bcd`
- name: `ValidateObjectType`
- size: `169`
- prototype: `__int64 __fastcall(int)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x18000da04`
- `0x18000db4c`
- `0x18000de90`
- `0x18000e424`
- `0x18000e70c`

## callees

- `0x180005b24`
- `0x180006608`
- `0x18000895c`
- `0x18000d18c`

## pseudocode

```c
__int64 __fastcall ValidateObjectType(int a1)
{
  __int64 v1; // r9
  bool v2; // zf
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  __int64 result; // rax
  _BYTE pExceptionObject[216]; // [rsp+20h] [rbp-D8h] BYREF

  v1 = (unsigned int)a1;
  if ( a1 > 7 )
  {
    v3 = a1 - 8;
    if ( !v3 )
      return result;
    v4 = v3 - 1;
    if ( !v4 )
      return result;
    v5 = v4 - 2;
    if ( !v5 )
      return result;
    v6 = v5 - 1;
    if ( !v6 )
      return result;
    v2 = v6 == 1;
  }
  else
  {
    if ( a1 == 7 || a1 == 1 || a1 == 2 || a1 == 3 || a1 == 4 || a1 == 5 )
      return result;
    v2 = a1 == 6;
  }
  if ( !v2 )
  {
    result = (unsigned __int16)v1;
    if ( (unsigned __int16)v1 != 10 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_b3b320b7595b350a842d079d8560ec21_Traceguids, v1);
      HResultException::HResultException((HResultException *)pExceptionObject, -2147024809);
      throw (HResultException *)pExceptionObject;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180005b24  sub     rsp, 0F8h
0x180005b2b  mov     r9d, ecx
0x180005b2e  cmp     ecx, 7
0x180005b31  jg      short loc_180005B55
0x180005b33  jz      short loc_180005B7B
0x180005b35  mov     edx, ecx
0x180005b37  sub     edx, 1
0x180005b3a  jz      short loc_180005B7B
0x180005b3c  sub     edx, 1
0x180005b3f  jz      short loc_180005B7B
0x180005b41  sub     edx, 1
0x180005b44  jz      short loc_180005B7B
0x180005b46  sub     edx, 1
0x180005b49  jz      short loc_180005B7B
0x180005b4b  sub     edx, 1
0x180005b4e  jz      short loc_180005B7B
0x180005b50  cmp     edx, 1
0x180005b53  jmp     short loc_180005B6C
0x180005b55  sub     ecx, 8
0x180005b58  jz      short loc_180005B7B
0x180005b5a  sub     ecx, 1
0x180005b5d  jz      short loc_180005B7B
0x180005b5f  sub     ecx, 2
0x180005b62  jz      short loc_180005B7B
0x180005b64  sub     ecx, 1
0x180005b67  jz      short loc_180005B7B
0x180005b69  cmp     ecx, 1
0x180005b6c  jz      short loc_180005B7B
0x180005b6e  movzx   eax, r9w
0x180005b72  mov     edx, 0Ah
0x180005b77  cmp     eax, edx
0x180005b79  jnz     short loc_180005B83
0x180005b7b  add     rsp, 0F8h
0x180005b82  retn
0x180005b83  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b8a  lea     rax, WPP_GLOBAL_Control
0x180005b91  cmp     rcx, rax
0x180005b94  jz      short loc_180005BAC
0x180005b96  cmp     byte ptr [rcx+19h], 2
0x180005b9a  jb      short loc_180005BAC
0x180005b9c  mov     rcx, [rcx+10h]
0x180005ba0  lea     r8, WPP_b3b320b7595b350a842d079d8560ec21_Traceguids
0x180005ba7  call    WPP_SF_d
0x180005bac  mov     edx, 80070057h; int
0x180005bb1  lea     rcx, [rsp+0F8h+pExceptionObject]; this
0x180005bb6  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180005bbb  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180005bc2  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x180005bc7  call    _CxxThrowException_0
```
