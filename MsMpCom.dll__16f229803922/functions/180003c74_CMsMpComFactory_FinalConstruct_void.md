# CMsMpComFactory::FinalConstruct(void)

- ea: `0x180003c74`
- end: `0x180003ccc`
- name: `?FinalConstruct@CMsMpComFactory@@QEAAJXZ`
- size: `88`
- prototype: `__int64 __fastcall(CMsMpComFactory *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003514`
- `0x180003668`

## callees

- `0x180003c74`
- `0x18000a010`

## import_xrefs

- `mpclient!MpConfigUninitialize` at `0x180003c84`
- `mpclient!MpConfigUninitialize` at `0x180003c84`
- `mpclient!MpConfigInitialize` at `0x180003c92`
- `mpclient!MpConfigInitialize` at `0x180003c92`
- `mpclient!MpUtilsExportFunctions` at `0x180003ca4`
- `mpclient!MpUtilsExportFunctions` at `0x180003ca4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMsMpComFactory::FinalConstruct(CMsMpComFactory *this)
{
  __int64 result; // rax
  __int64 v3; // rax

  if ( *((_QWORD *)this + 9) )
  {
    MpConfigUninitialize();
    *((_QWORD *)this + 9) = 0;
  }
  result = MpConfigInitialize();
  if ( (int)result >= 0 )
  {
    *((_QWORD *)this + 9) = 305419896;
    v3 = MpUtilsExportFunctions();
    result = (*(__int64 (__fastcall **)(__int64, char *))(v3 + 80))(16, (char *)this + 80);
    if ( (int)result >= 0 )
    {
      *((_BYTE *)this + 96) = 0;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180003c74  push    rbx
0x180003c76  sub     rsp, 20h
0x180003c7a  cmp     qword ptr [rcx+48h], 0
0x180003c7f  mov     rbx, rcx
0x180003c82  jz      short loc_180003C92
0x180003c84  call    cs:__imp_MpConfigUninitialize
0x180003c8a  mov     qword ptr [rbx+48h], 0
0x180003c92  call    cs:__imp_MpConfigInitialize
0x180003c98  test    eax, eax
0x180003c9a  js      short loc_180003CC6
0x180003c9c  mov     qword ptr [rbx+48h], 12345678h
0x180003ca4  call    cs:__imp_MpUtilsExportFunctions
0x180003caa  lea     rdx, [rbx+50h]
0x180003cae  mov     ecx, 10h
0x180003cb3  mov     rax, [rax+50h]
0x180003cb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cbc  test    eax, eax
0x180003cbe  js      short loc_180003CC6
0x180003cc0  mov     byte ptr [rbx+60h], 0
0x180003cc4  xor     eax, eax
0x180003cc6  add     rsp, 20h
0x180003cca  pop     rbx
0x180003ccb  retn
```
