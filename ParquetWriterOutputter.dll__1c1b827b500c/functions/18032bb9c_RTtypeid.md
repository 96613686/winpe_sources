# __RTtypeid

- ea: `0x18032bb9c`
- end: `0x18032bc4a`
- name: `__RTtypeid`
- size: `174`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180096630`

## callees

- `0x18032b080`
- `0x18032b9ec`
- `0x18032ba1c`
- `0x18032bb9c`

## import_xrefs

- `KERNEL32!RtlPcToFileHeader` at `0x18032bbbb`
- `KERNEL32!RtlPcToFileHeader` at `0x18032bbbb`

## string_xrefs

- `0x18032bc27`: `Access violation - no RTTI data!`
- `0x18032bbe1`: `Attempted a typeid of nullptr pointer!`
- `0x18032bc04`: `Bad read pointer - no RTTI data!`

## pseudocode

```c
char *__fastcall _RTtypeid(_QWORD *a1)
{
  int *v1; // rbx
  char *v2; // rcx
  char *result; // rax
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF
  PVOID BaseOfImage; // [rsp+50h] [rbp+8h] BYREF

  if ( !a1 )
  {
    std::bad_typeid::__construct_from_string_literal(pExceptionObject, "Attempted a typeid of nullptr pointer!");
    throw (std::bad_typeid *)pExceptionObject;
  }
  v1 = *(int **)(*a1 - 8LL);
  if ( *v1 )
  {
    v2 = (char *)v1 - v1[5];
  }
  else
  {
    v2 = (char *)RtlPcToFileHeader(v1, &BaseOfImage);
    BaseOfImage = v2;
  }
  result = &v2[v1[3]];
  if ( !result )
  {
    std::__non_rtti_object::__construct_from_string_literal(pExceptionObject, "Bad read pointer - no RTTI data!");
    throw (std::__non_rtti_object *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x18032bb9c  push    rbx
0x18032bb9e  sub     rsp, 40h
0x18032bba2  test    rcx, rcx
0x18032bba5  jz      short loc_18032BBE1
0x18032bba7  mov     rax, [rcx]
0x18032bbaa  mov     rbx, [rax-8]
0x18032bbae  mov     rcx, rbx; PcValue
0x18032bbb1  cmp     dword ptr [rbx], 0
0x18032bbb4  jnz     short loc_18032BBCB
0x18032bbb6  lea     rdx, [rsp+48h+BaseOfImage]; BaseOfImage
0x18032bbbb  call    cs:__imp_RtlPcToFileHeader
0x18032bbc1  mov     rcx, rax
0x18032bbc4  mov     [rsp+48h+BaseOfImage], rax
0x18032bbc9  jmp     short loc_18032BBD2
0x18032bbcb  movsxd  rax, dword ptr [rbx+14h]
0x18032bbcf  sub     rcx, rax
0x18032bbd2  movsxd  rax, dword ptr [rbx+0Ch]
0x18032bbd6  add     rax, rcx
0x18032bbd9  jz      short loc_18032BC04
0x18032bbdb  add     rsp, 40h
0x18032bbdf  pop     rbx
0x18032bbe0  retn
0x18032bbe1  lea     rdx, aAttemptedAType
0x18032bbe8  lea     rcx, [rsp+48h+pExceptionObject]
0x18032bbed  call    ?__construct_from_string_literal@bad_typeid@std@@SA?AV12@QEBD@Z
0x18032bbf2  lea     rdx, _TI2?AVbad_typeid@std@@; pThrowInfo
0x18032bbf9  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18032bbfe  call    _CxxThrowException
0x18032bc04  lea     rdx, aBadReadPointer
0x18032bc0b  lea     rcx, [rsp+48h+pExceptionObject]
0x18032bc10  call    ?__construct_from_string_literal@__non_rtti_object@std@@SA?AV12@QEBD@Z
0x18032bc15  lea     rdx, _TI3?AV__non_rtti_object@std@@; pThrowInfo
0x18032bc1c  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18032bc21  call    _CxxThrowException
0x18032bc27  lea     rdx, aAccessViolatio
0x18032bc2e  lea     rcx, [rsp+48h+pExceptionObject]
0x18032bc33  call    ?__construct_from_string_literal@__non_rtti_object@std@@SA?AV12@QEBD@Z
0x18032bc38  lea     rdx, _TI3?AV__non_rtti_object@std@@; pThrowInfo
0x18032bc3f  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18032bc44  call    _CxxThrowException
0x18036a990  push    rbp
0x18036a992  sub     rsp, 20h
0x18036a996  mov     rbp, rdx
0x18036a999  mov     rax, [rcx]
0x18036a99c  xor     ecx, ecx
0x18036a99e  cmp     dword ptr [rax], 0C0000005h
0x18036a9a4  setz    cl
0x18036a9a7  mov     eax, ecx
0x18036a9a9  add     rsp, 20h
0x18036a9ad  pop     rbp
0x18036a9ae  retn
```
