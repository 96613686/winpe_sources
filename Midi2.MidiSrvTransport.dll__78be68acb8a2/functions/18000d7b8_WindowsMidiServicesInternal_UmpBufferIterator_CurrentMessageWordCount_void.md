# WindowsMidiServicesInternal::UmpBufferIterator::CurrentMessageWordCount(void)

- ea: `0x18000d7b8`
- end: `0x18000d84e`
- name: `?CurrentMessageWordCount@UmpBufferIterator@WindowsMidiServicesInternal@@QEBAEXZ`
- size: `150`
- prototype: `unsigned __int8 __fastcall(WindowsMidiServicesInternal::UmpBufferIterator *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180010094`

## callees

- `0x180003004`
- `0x18000d0a4`
- `0x18000d7b8`

## pseudocode

```c
unsigned __int8 __fastcall WindowsMidiServicesInternal::UmpBufferIterator::CurrentMessageWordCount(
        WindowsMidiServicesInternal::UmpBufferIterator *this,
        const char *a2)
{
  unsigned int v2; // ecx
  unsigned int v3; // ecx
  unsigned int v4; // ecx
  unsigned int v5; // ecx
  unsigned int v6; // ecx
  unsigned int v7; // ecx
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  if ( *(_QWORD *)this >= *((_QWORD *)this + 2) )
  {
    std::runtime_error::runtime_error((std::runtime_error *)pExceptionObject, a2);
    throw (std::runtime_error *)pExceptionObject;
  }
  v2 = **(_DWORD **)this >> 28;
  if ( v2 <= 8 )
  {
    if ( v2 != 8 )
    {
      if ( !v2 )
        return 1;
      v3 = v2 - 1;
      if ( !v3 )
        return 1;
      v4 = v3 - 1;
      if ( !v4 )
        return 1;
      v5 = v4 - 1;
      if ( v5 )
      {
        v6 = v5 - 1;
        if ( v6 )
        {
          v7 = v6 - 1;
          if ( v7 )
            return v7 - 1 <= 1;
          return 4;
        }
      }
    }
    return 2;
  }
  v9 = v2 - 9;
  if ( !v9 )
    return 2;
  v10 = v9 - 1;
  if ( !v10 )
    return 2;
  v11 = v10 - 1;
  if ( v11 )
  {
    v12 = v11 - 1;
    if ( v12 )
    {
      v13 = v12 - 1;
      if ( v13 && v13 - 1 >= 2 )
        return 0;
      return 4;
    }
  }
  return 3;
}

```

## disassembly

```asm
0x18000d7b8  sub     rsp, 48h
0x18000d7bc  mov     rax, [rcx]
0x18000d7bf  cmp     rax, [rcx+10h]
0x18000d7c3  jnb     short loc_18000D832
0x18000d7c5  mov     ecx, [rax]
0x18000d7c7  shr     ecx, 1Ch
0x18000d7ca  cmp     ecx, 8
0x18000d7cd  ja      short loc_18000D7FF
0x18000d7cf  jz      short loc_18000D82E
0x18000d7d1  test    ecx, ecx
0x18000d7d3  jz      short loc_18000D7F8
0x18000d7d5  sub     ecx, 1
0x18000d7d8  jz      short loc_18000D7F8
0x18000d7da  sub     ecx, 1
0x18000d7dd  jz      short loc_18000D7F8
0x18000d7df  sub     ecx, 1
0x18000d7e2  jz      short loc_18000D82E
0x18000d7e4  sub     ecx, 1
0x18000d7e7  jz      short loc_18000D82E
0x18000d7e9  sub     ecx, 1
0x18000d7ec  jz      short loc_18000D826
0x18000d7ee  sub     ecx, 1
0x18000d7f1  jz      short loc_18000D7F8
0x18000d7f3  cmp     ecx, 1
0x18000d7f6  jnz     short loc_18000D822
0x18000d7f8  mov     al, 1
0x18000d7fa  add     rsp, 48h
0x18000d7fe  retn
0x18000d7ff  sub     ecx, 9
0x18000d802  jz      short loc_18000D82E
0x18000d804  sub     ecx, 1
0x18000d807  jz      short loc_18000D82E
0x18000d809  sub     ecx, 1
0x18000d80c  jz      short loc_18000D82A
0x18000d80e  sub     ecx, 1
0x18000d811  jz      short loc_18000D82A
0x18000d813  sub     ecx, 1
0x18000d816  jz      short loc_18000D826
0x18000d818  sub     ecx, 1
0x18000d81b  jz      short loc_18000D826
0x18000d81d  cmp     ecx, 1
0x18000d820  jz      short loc_18000D826
0x18000d822  xor     al, al
0x18000d824  jmp     short loc_18000D7FA
0x18000d826  mov     al, 4
0x18000d828  jmp     short loc_18000D7FA
0x18000d82a  mov     al, 3
0x18000d82c  jmp     short loc_18000D7FA
0x18000d82e  mov     al, 2
0x18000d830  jmp     short loc_18000D7FA
0x18000d832  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000d837  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18000d83c  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18000d843  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000d848  call    _CxxThrowException_0
```
