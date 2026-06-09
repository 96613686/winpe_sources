# WindowsPerformanceRecorder::Impl::ConvertToFullPath(ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>> &,ushort const *)

- ea: `0x18004bca4`
- end: `0x18004bd18`
- name: `?ConvertToFullPath@Impl@WindowsPerformanceRecorder@@YAJAEAV?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@PEBG@Z`
- size: `116`
- prototype: `__int64 __fastcall(__int64, const wchar_t *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18004b7f8`
- `0x18005b310`

## callees

- `0x1800138c0`
- `0x18001c458`
- `0x18004bca4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wfullpath` at `0x18004bccc`
- `api-ms-win-crt-private-l1-1-0!_o__wfullpath` at `0x18004bccc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004bce1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004bcfd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004bce1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004bcfd`

## pseudocode

```c
__int64 __fastcall WindowsPerformanceRecorder::Impl::ConvertToFullPath(__int64 a1, const wchar_t *a2)
{
  wchar_t *v4; // rax
  wchar_t *v5; // rbx
  __int64 result; // rax
  ATL::CAtlException *v7; // [rsp+28h] [rbp-10h] BYREF

  ATL::CSimpleStringT<unsigned short,0>::Empty(a1);
  v4 = _wfullpath(0, a2, 0);
  v5 = v4;
  if ( v4 )
  {
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      ATL::CSimpleStringT<unsigned short,0>::SetString(a1, v4);
      free(v5);
      result = 0;
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', &v7) )
      {
        result = *(unsigned int *)v7;
        __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18004BD08);
      }
    }
  }
  else
  {
    free(0);
    return 2147500037LL;
  }
  return result;
}

```

## disassembly

```asm
0x18004bca4  push    rdi
0x18004bca6  sub     rsp, 30h
0x18004bcaa  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18004bcb3  mov     [rsp+38h+arg_8], rbx
0x18004bcb8  mov     rbx, rdx
0x18004bcbb  mov     rdi, rcx
0x18004bcbe  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x18004bcc3  nop
0x18004bcc4  xor     r8d, r8d; BufferCount
0x18004bcc7  mov     rdx, rbx; Path
0x18004bcca  xor     ecx, ecx; Buffer
0x18004bccc  call    cs:__imp__wfullpath
0x18004bcd2  mov     rbx, rax
0x18004bcd5  mov     [rsp+38h+arg_0], rax
0x18004bcda  test    rax, rax
0x18004bcdd  jnz     short loc_18004BCEE
0x18004bcdf  xor     ecx, ecx; Block
0x18004bce1  call    cs:__imp_free
0x18004bce7  mov     eax, 80004005h
0x18004bcec  jmp     short loc_18004BD0C
0x18004bcee  mov     rdx, rbx
0x18004bcf1  mov     rcx, rdi
0x18004bcf4  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18004bcf9  nop
0x18004bcfa  mov     rcx, rbx; Block
0x18004bcfd  call    cs:__imp_free
0x18004bd03  nop
0x18004bd04  xor     eax, eax
0x18004bd06  jmp     short loc_18004BD0C
0x18004bd08  mov     eax, dword ptr [rsp+38h+arg_0]
0x18004bd0c  mov     rbx, [rsp+38h+arg_8]
0x18004bd11  add     rsp, 30h
0x18004bd15  pop     rdi
0x18004bd16  retn
```
