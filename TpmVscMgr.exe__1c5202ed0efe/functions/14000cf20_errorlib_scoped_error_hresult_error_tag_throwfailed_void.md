# errorlib::scoped_error<hresult_error::tag>::throwfailed(void)

- ea: `0x14000cf20`
- end: `0x14000cf54`
- name: `?throwfailed@?$scoped_error@Utag@hresult_error@@@errorlib@@QEBAXXZ`
- size: `52`
- prototype: `void __fastcall(int *)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x140006164`
- `0x140006298`
- `0x140008784`
- `0x140009434`
- `0x1400098b0`
- `0x14000ded8`
- `0x14000f54c`

## callees

- `0x140002462`
- `0x140007c8c`
- `0x14000cf20`

## pseudocode

```c
void __fastcall errorlib::scoped_error<hresult_error::tag>::throwfailed(int *a1)
{
  bool v1; // sf
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  v1 = *a1 < 0;
  a1[1] = 3;
  if ( v1 )
  {
    errorlib::specific_error_exception<hresult_error::tag>::specific_error_exception<hresult_error::tag>(
      pExceptionObject,
      a1);
    throw (errorlib::specific_error_exception<hresult_error::tag> *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x14000cf20  sub     rsp, 48h
0x14000cf24  cmp     dword ptr [rcx], 0
0x14000cf27  mov     dword ptr [rcx+4], 3
0x14000cf2e  jl      short loc_14000CF35
0x14000cf30  add     rsp, 48h
0x14000cf34  retn
0x14000cf35  mov     rdx, rcx
0x14000cf38  lea     rcx, [rsp+48h+pExceptionObject]
0x14000cf3d  call    ??0?$specific_error_exception@Utag@hresult_error@@@errorlib@@QEAA@AEBV?$scoped_error@Utag@hresult_error@@@1@@Z; errorlib::specific_error_exception<hresult_error::tag>::specific_error_exception<hresult_error::tag>(errorlib::scoped_error<hresult_error::tag> const &)
0x14000cf42  lea     rdx, _TI4?AV?$specific_error_exception@Utag@hresult_error@@@errorlib@@; pThrowInfo
0x14000cf49  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x14000cf4e  call    _CxxThrowException_0
```
