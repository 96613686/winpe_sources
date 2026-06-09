# WindowsMidiServicesInternal::UmpBufferIterator::CurrentMessageWordCount(void)

- ea: `0x18000aad4`
- end: `0x18000ab71`
- name: `?CurrentMessageWordCount@UmpBufferIterator@WindowsMidiServicesInternal@@QEBAEXZ`
- size: `157`
- prototype: `unsigned __int8 __fastcall(WindowsMidiServicesInternal::UmpBufferIterator *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000caf0`

## callees

- `0x180002964`
- `0x18000a890`
- `0x18000aad4`

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
0x18000aad4  sub     rsp, 48h
0x18000aad8  mov     rax, [rcx]
0x18000aadb  cmp     rax, [rcx+10h]
0x18000aadf  jnb     short loc_18000AB4E
0x18000aae1  mov     ecx, [rax]
0x18000aae3  shr     ecx, 1Ch
0x18000aae6  cmp     ecx, 8
0x18000aae9  ja      short loc_18000AB1B
0x18000aaeb  jz      short loc_18000AB4A
0x18000aaed  test    ecx, ecx
0x18000aaef  jz      short loc_18000AB14
0x18000aaf1  sub     ecx, 1
0x18000aaf4  jz      short loc_18000AB14
0x18000aaf6  sub     ecx, 1
0x18000aaf9  jz      short loc_18000AB14
0x18000aafb  sub     ecx, 1
0x18000aafe  jz      short loc_18000AB4A
0x18000ab00  sub     ecx, 1
0x18000ab03  jz      short loc_18000AB4A
0x18000ab05  sub     ecx, 1
0x18000ab08  jz      short loc_18000AB42
0x18000ab0a  sub     ecx, 1
0x18000ab0d  jz      short loc_18000AB14
0x18000ab0f  cmp     ecx, 1
0x18000ab12  jnz     short loc_18000AB3E
0x18000ab14  mov     al, 1
0x18000ab16  add     rsp, 48h
0x18000ab1a  retn
0x18000ab1b  sub     ecx, 9
0x18000ab1e  jz      short loc_18000AB4A
0x18000ab20  sub     ecx, 1
0x18000ab23  jz      short loc_18000AB4A
0x18000ab25  sub     ecx, 1
0x18000ab28  jz      short loc_18000AB46
0x18000ab2a  sub     ecx, 1
0x18000ab2d  jz      short loc_18000AB46
0x18000ab2f  sub     ecx, 1
0x18000ab32  jz      short loc_18000AB42
0x18000ab34  sub     ecx, 1
0x18000ab37  jz      short loc_18000AB42
0x18000ab39  cmp     ecx, 1
0x18000ab3c  jz      short loc_18000AB42
0x18000ab3e  xor     al, al
0x18000ab40  jmp     short loc_18000AB16
0x18000ab42  mov     al, 4
0x18000ab44  jmp     short loc_18000AB16
0x18000ab46  mov     al, 3
0x18000ab48  jmp     short loc_18000AB16
0x18000ab4a  mov     al, 2
0x18000ab4c  jmp     short loc_18000AB16
0x18000ab4e  lea     rdx, aInvalidUmpPast; "Invalid UMP. Past end of buffer."
0x18000ab55  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000ab5a  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18000ab5f  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18000ab66  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000ab6b  call    _CxxThrowException_0
```
