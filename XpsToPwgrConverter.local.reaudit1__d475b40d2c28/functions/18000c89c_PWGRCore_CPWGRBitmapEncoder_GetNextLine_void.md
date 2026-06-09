# PWGRCore::CPWGRBitmapEncoder::_GetNextLine(void)

- ea: `0x18000c89c`
- end: `0x18000c95f`
- name: `?_GetNextLine@CPWGRBitmapEncoder@PWGRCore@@AEAA_NXZ`
- size: `195`
- prototype: `bool __fastcall(PWGRCore::CPWGRBitmapEncoder *__hidden this)`
- caller_count: `6`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ae2c`
- `0x18000aef4`
- `0x18000afcc`
- `0x18000b094`
- `0x18000b170`
- `0x18000c514`

## callees

- `0x1800021a0`
- `0x18000a0ac`
- `0x18000c89c`
- `0x18000d8f8`
- `0x18000d93c`

## pseudocode

```c
char __fastcall PWGRCore::CPWGRBitmapEncoder::_GetNextLine(PWGRCore::CPWGRBitmapEncoder *this)
{
  __int64 v1; // rbx
  char v3; // cl
  __int64 v4; // rdx
  _DWORD *v5; // rdi
  int v6; // eax
  _BYTE pExceptionObject[64]; // [rsp+30h] [rbp-48h] BYREF

  v1 = *((_QWORD *)this + 7);
  if ( *(_DWORD *)(v1 + 68) > *(_DWORD *)(v1 + 36) )
  {
    v5 = (_DWORD *)(v1 + 40);
    if ( *(_DWORD *)(v1 + 40) == *(_DWORD *)(v1 + 60) )
      PWGRCore::CPWGRBitmapWrapper::_GetNextImageBand(*((PWGRCore::CPWGRBitmapWrapper **)this + 7));
    *((_QWORD *)this + 5) = *(_QWORD *)(v1 + 48);
    v4 = *(unsigned int *)(v1 + 56);
    *(_QWORD *)(v1 + 48) += v4;
    if ( *v5 == -1 || (++*v5, v6 = *(_DWORD *)(v1 + 36), v6 == -1) )
      RenderCommon::SafeIntExceptionHandler<PrintCore::WindowsError>::SafeIntOnOverflow();
    v3 = 0;
    *(_DWORD *)(v1 + 36) = v6 + 1;
  }
  else
  {
    v3 = 1;
    *((_QWORD *)this + 5) = 0;
    LODWORD(v4) = 0;
  }
  if ( (_DWORD)v4 != *((_DWORD *)this + 8) && (_DWORD)v4 )
  {
    PrintCore::WindowsError::WindowsError(
      (PrintCore::WindowsError *)pExceptionObject,
      -2147467259,
      "Wrong buffer size",
      "onecoreuap\\printscan\\print\\drivers\\renderlibrary\\pwgraster\\pwgrcore\\pwgrbitmapencoder.cpp",
      0x8Bu);
    throw (PrintCore::WindowsError *)pExceptionObject;
  }
  return v3;
}

```

## disassembly

```asm
0x18000c89c  mov     [rsp+arg_0], rbx
0x18000c8a1  mov     [rsp+arg_8], rsi
0x18000c8a6  push    rdi
0x18000c8a7  sub     rsp, 70h
0x18000c8ab  mov     rbx, [rcx+38h]
0x18000c8af  mov     rsi, rcx
0x18000c8b2  mov     eax, [rbx+24h]
0x18000c8b5  cmp     [rbx+44h], eax
0x18000c8b8  ja      short loc_18000C8C8
0x18000c8ba  mov     cl, 1
0x18000c8bc  mov     qword ptr [rsi+28h], 0
0x18000c8c4  xor     edx, edx
0x18000c8c6  jmp     short loc_18000C905
0x18000c8c8  mov     eax, [rbx+3Ch]
0x18000c8cb  lea     rdi, [rbx+28h]
0x18000c8cf  cmp     [rdi], eax
0x18000c8d1  jnz     short loc_18000C8DB
0x18000c8d3  mov     rcx, rbx; this
0x18000c8d6  call    ?_GetNextImageBand@CPWGRBitmapWrapper@PWGRCore@@AEAAXXZ; PWGRCore::CPWGRBitmapWrapper::_GetNextImageBand(void)
0x18000c8db  mov     rax, [rbx+30h]
0x18000c8df  or      ecx, 0FFFFFFFFh
0x18000c8e2  mov     [rsi+28h], rax
0x18000c8e6  mov     edx, [rbx+38h]
0x18000c8e9  add     [rbx+30h], rdx
0x18000c8ed  mov     eax, [rdi]
0x18000c8ef  cmp     eax, ecx
0x18000c8f1  jz      short loc_18000C959
0x18000c8f3  inc     eax
0x18000c8f5  mov     [rdi], eax
0x18000c8f7  mov     eax, [rbx+24h]
0x18000c8fa  cmp     eax, ecx
0x18000c8fc  jz      short loc_18000C959
0x18000c8fe  xor     cl, cl
0x18000c900  inc     eax
0x18000c902  mov     [rbx+24h], eax
0x18000c905  cmp     edx, [rsi+20h]
0x18000c908  jz      short loc_18000C90E
0x18000c90a  test    edx, edx
0x18000c90c  jnz     short loc_18000C922
0x18000c90e  lea     r11, [rsp+78h+var_8]
0x18000c913  mov     al, cl
0x18000c915  mov     rbx, [r11+10h]
0x18000c919  mov     rsi, [r11+18h]
0x18000c91d  mov     rsp, r11
0x18000c920  pop     rdi
0x18000c921  retn
0x18000c922  lea     r9, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\drivers\\"...
0x18000c929  mov     [rsp+78h+var_58], 8Bh; unsigned int
0x18000c931  lea     r8, aWrongBufferSiz; "Wrong buffer size"
0x18000c938  mov     edx, 80004005h; int
0x18000c93d  lea     rcx, [rsp+78h+pExceptionObject]; this
0x18000c942  call    ??0WindowsError@PrintCore@@QEAA@JPEBD0I@Z; PrintCore::WindowsError::WindowsError(long,char const *,char const *,uint)
0x18000c947  lea     rdx, _TI2?AVWindowsError@PrintCore@@; pThrowInfo
0x18000c94e  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18000c953  call    _CxxThrowException_0
0x18000c959  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VWindowsError@PrintCore@@@RenderCommon@@SAXXZ; RenderCommon::SafeIntExceptionHandler<PrintCore::WindowsError>::SafeIntOnOverflow(void)
```
