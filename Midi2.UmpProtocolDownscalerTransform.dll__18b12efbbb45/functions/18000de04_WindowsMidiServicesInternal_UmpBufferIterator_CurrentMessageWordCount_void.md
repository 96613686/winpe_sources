# WindowsMidiServicesInternal::UmpBufferIterator::CurrentMessageWordCount(void)

- ea: `0x18000de04`
- end: `0x18000dea1`
- name: `?CurrentMessageWordCount@UmpBufferIterator@WindowsMidiServicesInternal@@QEBAEXZ`
- size: `157`
- prototype: `unsigned __int8 __fastcall(WindowsMidiServicesInternal::UmpBufferIterator *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000dcc4`
- `0x18000e090`
- `0x180010650`

## callees

- `0x180003a50`
- `0x18000cfa4`
- `0x18000de04`

## pseudocode

```c
unsigned __int8 __fastcall WindowsMidiServicesInternal::UmpBufferIterator::CurrentMessageWordCount(
        WindowsMidiServicesInternal::UmpBufferIterator *this)
{
  unsigned int v1; // ecx
  unsigned int v2; // ecx
  unsigned int v3; // ecx
  unsigned int v4; // ecx
  unsigned int v5; // ecx
  unsigned int v6; // ecx
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  if ( *(_QWORD *)this >= *((_QWORD *)this + 2) )
  {
    std::runtime_error::runtime_error((std::runtime_error *)pExceptionObject, "Invalid UMP. Past end of buffer.");
    throw (std::runtime_error *)pExceptionObject;
  }
  v1 = **(_DWORD **)this >> 28;
  if ( v1 <= 8 )
  {
    if ( v1 != 8 )
    {
      if ( !v1 )
        return 1;
      v2 = v1 - 1;
      if ( !v2 )
        return 1;
      v3 = v2 - 1;
      if ( !v3 )
        return 1;
      v4 = v3 - 1;
      if ( v4 )
      {
        v5 = v4 - 1;
        if ( v5 )
        {
          v6 = v5 - 1;
          if ( v6 )
            return v6 - 1 <= 1;
          return 4;
        }
      }
    }
    return 2;
  }
  v8 = v1 - 9;
  if ( !v8 )
    return 2;
  v9 = v8 - 1;
  if ( !v9 )
    return 2;
  v10 = v9 - 1;
  if ( v10 )
  {
    v11 = v10 - 1;
    if ( v11 )
    {
      v12 = v11 - 1;
      if ( v12 && v12 - 1 >= 2 )
        return 0;
      return 4;
    }
  }
  return 3;
}

```

## disassembly

```asm
0x18000de04  sub     rsp, 48h
0x18000de08  mov     rax, [rcx]
0x18000de0b  cmp     rax, [rcx+10h]
0x18000de0f  jnb     short loc_18000DE7E
0x18000de11  mov     ecx, [rax]
0x18000de13  shr     ecx, 1Ch
0x18000de16  cmp     ecx, 8
0x18000de19  ja      short loc_18000DE4B
0x18000de1b  jz      short loc_18000DE7A
0x18000de1d  test    ecx, ecx
0x18000de1f  jz      short loc_18000DE44
0x18000de21  sub     ecx, 1
0x18000de24  jz      short loc_18000DE44
0x18000de26  sub     ecx, 1
0x18000de29  jz      short loc_18000DE44
0x18000de2b  sub     ecx, 1
0x18000de2e  jz      short loc_18000DE7A
0x18000de30  sub     ecx, 1
0x18000de33  jz      short loc_18000DE7A
0x18000de35  sub     ecx, 1
0x18000de38  jz      short loc_18000DE72
0x18000de3a  sub     ecx, 1
0x18000de3d  jz      short loc_18000DE44
0x18000de3f  cmp     ecx, 1
0x18000de42  jnz     short loc_18000DE6E
0x18000de44  mov     al, 1
0x18000de46  add     rsp, 48h
0x18000de4a  retn
0x18000de4b  sub     ecx, 9
0x18000de4e  jz      short loc_18000DE7A
0x18000de50  sub     ecx, 1
0x18000de53  jz      short loc_18000DE7A
0x18000de55  sub     ecx, 1
0x18000de58  jz      short loc_18000DE76
0x18000de5a  sub     ecx, 1
0x18000de5d  jz      short loc_18000DE76
0x18000de5f  sub     ecx, 1
0x18000de62  jz      short loc_18000DE72
0x18000de64  sub     ecx, 1
0x18000de67  jz      short loc_18000DE72
0x18000de69  cmp     ecx, 1
0x18000de6c  jz      short loc_18000DE72
0x18000de6e  xor     al, al
0x18000de70  jmp     short loc_18000DE46
0x18000de72  mov     al, 4
0x18000de74  jmp     short loc_18000DE46
0x18000de76  mov     al, 3
0x18000de78  jmp     short loc_18000DE46
0x18000de7a  mov     al, 2
0x18000de7c  jmp     short loc_18000DE46
0x18000de7e  lea     rdx, aInvalidUmpPast; "Invalid UMP. Past end of buffer."
0x18000de85  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000de8a  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18000de8f  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18000de96  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000de9b  call    _CxxThrowException_0
```
