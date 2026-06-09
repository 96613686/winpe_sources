# PrintCore::CaptureAndConvertExceptionToHR__lambda_67289b3a95168f935d9fdc73d090b16b___

- ea: `0x18000e964`
- end: `0x18000e9fa`
- name: `PrintCore::CaptureAndConvertExceptionToHR__lambda_67289b3a95168f935d9fdc73d090b16b___`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000fd10`

## callees

- `0x18000e964`
- `0x180010050`
- `0x180010290`

## string_xrefs

- `0x18000e99c`: `onecoreuap\printscan\print\drivers\renderlibrary\pclm\lib\pclmwriter.cpp`

## pseudocode

```c
__int64 __fastcall PrintCore::CaptureAndConvertExceptionToHR__lambda_67289b3a95168f935d9fdc73d090b16b___(__int64 a1)
{
  __int64 v3; // r9
  __int64 v4; // r8
  __int64 v5; // rdx
  void (__fastcall *v6)(_QWORD, __int64, __int64, __int64); // rax
  unsigned int v7; // [rsp+20h] [rbp-28h]
  PrintCore::WindowsError *v8; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v9; // [rsp+50h] [rbp+8h]

  v9 = 0;
  if ( !*(_QWORD *)a1 || *(float *)(a1 + 8) == 0.0 || *(float *)(a1 + 12) == 0.0 )
  {
    try
    {
      PrintCore::ThrowIfError(
        (PrintCore *)0x80070057LL,
        (int)"Unspecified.",
        "onecoreuap\\printscan\\print\\drivers\\renderlibrary\\pclm\\lib\\pclmwriter.cpp",
        (const char *)0x48,
        v7);
    }
    catch ( std::bad_alloc )
    {
      return (unsigned int)-2147024882;
    }
    catch ( std::out_of_range )
    {
      return (unsigned int)-2147023728;
    }
    catch ( std::invalid_argument )
    {
      return (unsigned int)-2147024809;
    }
    catch ( std::range_error )
    {
      return (unsigned int)-2147483637;
    }
    catch ( PrintCore::WindowsError *v8 )
    {
      v9 = *((_DWORD *)v8 + 6);
      v3 = *((unsigned int *)v8 + 12);
      v4 = *((_QWORD *)v8 + 5);
      v5 = *((_QWORD *)v8 + 4);
      v6 = (void (__fastcall *)(_QWORD, __int64, __int64, __int64))_InterlockedCompareExchange64(
                                                                     (volatile signed __int64 *)&PrintCore::WindowsErrorLogger::s_pCallback,
                                                                     0,
                                                                     0);
      if ( v6 )
        v6(v9, v5, v4, v3);
      return v9;
    }
    catch ( ... )
    {
      return (unsigned int)-2147418113;
    }
  }
  PCLmWriter::PCLmWriter::_HandlePCLmPage(
    *(PCLmWriter::PCLmWriter **)(a1 + 16),
    *(struct IPageBitmapProvider **)a1,
    *(float *)(a1 + 8) * 72.0,
    *(float *)(a1 + 12) * 72.0,
    *(const char **)(a1 + 24));
  return v9;
}

```

## disassembly

```asm
0x18000e964  push    rbx
0x18000e966  sub     rsp, 40h
0x18000e96a  mov     rbx, rcx
0x18000e96d  mov     [rsp+48h+arg_0], 0
0x18000e975  cmp     qword ptr [rcx], 0
0x18000e979  jz      short loc_18000E996
0x18000e97b  movss   xmm0, dword ptr [rcx+8]
0x18000e980  xorps   xmm1, xmm1
0x18000e983  ucomiss xmm0, xmm1
0x18000e986  jp      short loc_18000E98A
0x18000e988  jz      short loc_18000E996
0x18000e98a  movss   xmm0, dword ptr [rcx+0Ch]
0x18000e98f  ucomiss xmm0, xmm1
0x18000e992  jp      short loc_18000E9B4
0x18000e994  jnz     short loc_18000E9B4
0x18000e996  mov     r9d, 48h ; 'H'; char *
0x18000e99c  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\drivers\\"...
0x18000e9a3  lea     rdx, aUnspecified; "Unspecified."
0x18000e9aa  mov     ecx, 80070057h; this
0x18000e9af  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x18000e9b4  movss   xmm3, dword ptr [rbx+0Ch]
0x18000e9b9  mulss   xmm3, cs:__real@42900000; float
0x18000e9c1  movss   xmm2, dword ptr [rbx+8]
0x18000e9c6  mulss   xmm2, cs:__real@42900000; float
0x18000e9ce  mov     rax, [rbx+18h]
0x18000e9d2  mov     qword ptr [rsp+48h+var_28], rax; char *
0x18000e9d7  mov     rdx, [rbx]; struct IPageBitmapProvider *
0x18000e9da  mov     rcx, [rbx+10h]; this
0x18000e9de  call    ?_HandlePCLmPage@PCLmWriter@1@AEAAXPEAUIPageBitmapProvider@@MMPEBD@Z; PCLmWriter::PCLmWriter::_HandlePCLmPage(IPageBitmapProvider *,float,float,char const *)
0x18000e9e3  nop
0x18000e9e4  jmp     short loc_18000E9F0
0x18000e9e6  jmp     short loc_18000E9F0
0x18000e9e8  jmp     short loc_18000E9F0
0x18000e9ea  jmp     short loc_18000E9F0
0x18000e9ec  jmp     short loc_18000E9F0
0x18000e9ee  jmp     short $+2
0x18000e9f0  mov     eax, [rsp+48h+arg_0]
0x18000e9f4  add     rsp, 40h
0x18000e9f8  pop     rbx
0x18000e9f9  retn
```
