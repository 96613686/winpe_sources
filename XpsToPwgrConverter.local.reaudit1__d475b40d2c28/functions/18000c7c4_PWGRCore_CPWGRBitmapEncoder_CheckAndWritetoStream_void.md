# PWGRCore::CPWGRBitmapEncoder::_CheckAndWritetoStream(void)

- ea: `0x18000c7c4`
- end: `0x18000c855`
- name: `?_CheckAndWritetoStream@CPWGRBitmapEncoder@PWGRCore@@AEAAXXZ`
- size: `145`
- prototype: `void __fastcall(PWGRCore::CPWGRBitmapEncoder *__hidden this)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

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
- `0x18000c7c4`
- `0x18000c9a8`
- `0x180011010`

## string_xrefs

- `0x18000c830`: `Failed to write to ouput Stream`

## pseudocode

```c
void __fastcall PWGRCore::CPWGRBitmapEncoder::_CheckAndWritetoStream(PWGRCore::CPWGRBitmapEncoder *this)
{
  __int64 *v1; // rbx
  __int64 v2; // r8
  __int64 v3; // rcx
  __int64 v4; // rdx
  int v5; // eax
  _BYTE pExceptionObject[72]; // [rsp+30h] [rbp-48h] BYREF
  int v7; // [rsp+80h] [rbp+8h] BYREF

  v1 = (__int64 *)((char *)this + 8);
  v2 = *((_QWORD *)this + 2) - *((_QWORD *)this + 1);
  if ( *((_QWORD *)this + 3) - *((_QWORD *)this + 1) < (unsigned __int64)(v2 + 4096) && v2 )
  {
    v3 = *(_QWORD *)this;
    v4 = *v1;
    v7 = 0;
    v5 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, int *))(*(_QWORD *)v3 + 32LL))(v3, v4, v2, &v7);
    if ( v5 < 0 )
    {
      PrintCore::WindowsError::WindowsError(
        (PrintCore::WindowsError *)pExceptionObject,
        v5,
        "Failed to write to ouput Stream",
        "onecoreuap\\printscan\\print\\drivers\\renderlibrary\\pwgraster\\pwgrcore\\pwgrbitmapencoder.cpp",
        0x6Fu);
      throw (PrintCore::WindowsError *)pExceptionObject;
    }
    std::vector<unsigned char>::resize(v1);
  }
}

```

## disassembly

```asm
0x18000c7c4  mov     r11, rsp
0x18000c7c7  push    rbx
0x18000c7c8  sub     rsp, 70h
0x18000c7cc  lea     rbx, [rcx+8]
0x18000c7d0  mov     r8, [rbx+8]
0x18000c7d4  sub     r8, [rbx]
0x18000c7d7  mov     r9, [rbx+10h]
0x18000c7db  sub     r9, [rbx]
0x18000c7de  lea     rax, [r8+1000h]
0x18000c7e5  cmp     r9, rax
0x18000c7e8  jnb     short loc_18000C81B
0x18000c7ea  test    r8, r8
0x18000c7ed  jz      short loc_18000C81B
0x18000c7ef  mov     rcx, [rcx]
0x18000c7f2  lea     r9, [r11+8]
0x18000c7f6  mov     rdx, [rbx]
0x18000c7f9  mov     dword ptr [r11+8], 0
0x18000c801  mov     rax, [rcx]
0x18000c804  mov     rax, [rax+20h]
0x18000c808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c80d  test    eax, eax
0x18000c80f  js      short loc_18000C821
0x18000c811  xor     edx, edx
0x18000c813  mov     rcx, rbx
0x18000c816  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x18000c81b  add     rsp, 70h
0x18000c81f  pop     rbx
0x18000c820  retn
0x18000c821  lea     r9, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\drivers\\"...
0x18000c828  mov     [rsp+78h+var_58], 6Fh ; 'o'; unsigned int
0x18000c830  lea     r8, aFailedToWriteT; "Failed to write to ouput Stream"
0x18000c837  mov     edx, eax; int
0x18000c839  lea     rcx, [rsp+78h+pExceptionObject]; this
0x18000c83e  call    ??0WindowsError@PrintCore@@QEAA@JPEBD0I@Z; PrintCore::WindowsError::WindowsError(long,char const *,char const *,uint)
0x18000c843  lea     rdx, _TI2?AVWindowsError@PrintCore@@; pThrowInfo
0x18000c84a  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18000c84f  call    _CxxThrowException_0
```
