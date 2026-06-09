# WindowsMidiServicesInternal::UmpBufferIterator::GetCurrentMessageWord(uchar)

- ea: `0x18000e090`
- end: `0x18000e18a`
- name: `?GetCurrentMessageWord@UmpBufferIterator@WindowsMidiServicesInternal@@QEBAIE@Z`
- size: `250`
- prototype: `__int64 __fastcall(WindowsMidiServicesInternal::UmpBufferIterator *this, unsigned __int8)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180010650`

## callees

- `0x180003a50`
- `0x18000cfa4`
- `0x18000de04`
- `0x18000e090`

## pseudocode

```c
__int64 __fastcall WindowsMidiServicesInternal::UmpBufferIterator::GetCurrentMessageWord(
        WindowsMidiServicesInternal::UmpBufferIterator *this,
        unsigned __int8 a2)
{
  unsigned __int64 v2; // rdi
  __int64 v4; // rsi
  __int64 v5; // rdi
  unsigned int v6; // ecx
  unsigned int v7; // ecx
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned __int8 v12; // al
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  v2 = *((_QWORD *)this + 2);
  v4 = a2;
  if ( *(_QWORD *)this >= v2 )
  {
    std::runtime_error::runtime_error((std::runtime_error *)pExceptionObject, "Invalid UMP. Past end of buffer.");
    throw (std::runtime_error *)pExceptionObject;
  }
  v5 = (__int64)(v2 - *(_QWORD *)this) >> 2;
  if ( (unsigned int)v5 < WindowsMidiServicesInternal::UmpBufferIterator::CurrentMessageWordCount(this) )
    goto LABEL_24;
  v6 = **(_DWORD **)this >> 28;
  if ( v6 <= 8 )
  {
    if ( v6 != 8 )
    {
      if ( !v6 || (v7 = v6 - 1) == 0 || (v8 = v7 - 1) == 0 )
      {
LABEL_12:
        v12 = 1;
        goto LABEL_22;
      }
      v9 = v8 - 1;
      if ( v9 )
      {
        v10 = v9 - 1;
        if ( v10 )
        {
          v11 = v10 - 1;
          if ( v11 )
          {
            if ( v11 - 1 > 1 )
              goto LABEL_24;
            goto LABEL_12;
          }
          goto LABEL_19;
        }
      }
    }
    goto LABEL_21;
  }
  v13 = v6 - 9;
  if ( v13 )
  {
    v14 = v13 - 1;
    if ( v14 )
    {
      v15 = v14 - 1;
      if ( !v15 || (v16 = v15 - 1) == 0 )
      {
        v12 = 3;
        goto LABEL_22;
      }
      v17 = v16 - 1;
      if ( !v17 || v17 - 1 <= 1 )
      {
LABEL_19:
        v12 = 4;
        goto LABEL_22;
      }
LABEL_24:
      std::runtime_error::runtime_error(
        (std::runtime_error *)pExceptionObject,
        "Word index out of range for this message.");
      throw (std::runtime_error *)pExceptionObject;
    }
  }
LABEL_21:
  v12 = 2;
LABEL_22:
  if ( (unsigned __int8)v4 >= v12 )
    goto LABEL_24;
  return *(unsigned int *)(*(_QWORD *)this + 4 * v4);
}

```

## disassembly

```asm
0x18000e090  mov     [rsp+arg_0], rbx
0x18000e095  mov     [rsp+arg_8], rsi
0x18000e09a  push    rdi
0x18000e09b  sub     rsp, 40h
0x18000e09f  mov     rdi, [rcx+10h]
0x18000e0a3  mov     rbx, rcx
0x18000e0a6  movzx   esi, dl
0x18000e0a9  cmp     [rcx], rdi
0x18000e0ac  jnb     loc_18000E167
0x18000e0b2  sub     rdi, [rcx]
0x18000e0b5  sar     rdi, 2
0x18000e0b9  call    ?CurrentMessageWordCount@UmpBufferIterator@WindowsMidiServicesInternal@@QEBAEXZ; WindowsMidiServicesInternal::UmpBufferIterator::CurrentMessageWordCount(void)
0x18000e0be  movzx   eax, al
0x18000e0c1  cmp     edi, eax
0x18000e0c3  jb      short loc_18000E144
0x18000e0c5  mov     rdx, [rbx]
0x18000e0c8  mov     ecx, [rdx]
0x18000e0ca  shr     ecx, 1Ch
0x18000e0cd  cmp     ecx, 8
0x18000e0d0  ja      short loc_18000E0FF
0x18000e0d2  jz      short loc_18000E12A
0x18000e0d4  test    ecx, ecx
0x18000e0d6  jz      short loc_18000E0FB
0x18000e0d8  sub     ecx, 1
0x18000e0db  jz      short loc_18000E0FB
0x18000e0dd  sub     ecx, 1
0x18000e0e0  jz      short loc_18000E0FB
0x18000e0e2  sub     ecx, 1
0x18000e0e5  jz      short loc_18000E12A
0x18000e0e7  sub     ecx, 1
0x18000e0ea  jz      short loc_18000E12A
0x18000e0ec  sub     ecx, 1
0x18000e0ef  jz      short loc_18000E122
0x18000e0f1  sub     ecx, 1
0x18000e0f4  jz      short loc_18000E0FB
0x18000e0f6  cmp     ecx, 1
0x18000e0f9  jnz     short loc_18000E144
0x18000e0fb  mov     al, 1
0x18000e0fd  jmp     short loc_18000E12C
0x18000e0ff  sub     ecx, 9
0x18000e102  jz      short loc_18000E12A
0x18000e104  sub     ecx, 1
0x18000e107  jz      short loc_18000E12A
0x18000e109  sub     ecx, 1
0x18000e10c  jz      short loc_18000E126
0x18000e10e  sub     ecx, 1
0x18000e111  jz      short loc_18000E126
0x18000e113  sub     ecx, 1
0x18000e116  jz      short loc_18000E122
0x18000e118  sub     ecx, 1
0x18000e11b  jz      short loc_18000E122
0x18000e11d  cmp     ecx, 1
0x18000e120  jnz     short loc_18000E144
0x18000e122  mov     al, 4
0x18000e124  jmp     short loc_18000E12C
0x18000e126  mov     al, 3
0x18000e128  jmp     short loc_18000E12C
0x18000e12a  mov     al, 2
0x18000e12c  cmp     sil, al
0x18000e12f  jnb     short loc_18000E144
0x18000e131  mov     eax, [rdx+rsi*4]
0x18000e134  mov     rsi, [rsp+48h+arg_8]
0x18000e139  mov     rbx, [rsp+48h+arg_0]
0x18000e13e  add     rsp, 40h
0x18000e142  pop     rdi
0x18000e143  retn
0x18000e144  lea     rdx, aWordIndexOutOf; "Word index out of range for this messag"...
0x18000e14b  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000e150  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18000e155  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18000e15c  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000e161  call    _CxxThrowException_0
0x18000e167  lea     rdx, aInvalidUmpPast; "Invalid UMP. Past end of buffer."
0x18000e16e  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000e173  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18000e178  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18000e17f  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000e184  call    _CxxThrowException_0
```
