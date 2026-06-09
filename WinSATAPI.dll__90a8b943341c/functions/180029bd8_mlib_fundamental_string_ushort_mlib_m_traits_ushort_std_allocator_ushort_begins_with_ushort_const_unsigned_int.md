# mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::begins_with(ushort const *,unsigned __int64)

- ea: `0x180029bd8`
- end: `0x180029cad`
- name: `?begins_with@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA_NPEBG_K@Z`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800248f0`

## callees

- `0x180003640`
- `0x18000e4c0`
- `0x18001153c`
- `0x180012bf3`
- `0x180029bd8`
- `0x18002fb50`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180029c78`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180029c78`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::begins_with(
        __int64 a1,
        const WCHAR *a2)
{
  __int64 v4; // rdx
  int cchCount2; // eax
  _BYTE pExceptionObject[24]; // [rsp+38h] [rbp-50h] BYREF
  __int64 v8; // [rsp+50h] [rbp-38h] BYREF

  if ( !a2 )
  {
    v4 = mlib::_msrse_(&v8);
    std::out_of_range::out_of_range(pExceptionObject, v4);
    throw (std::invalid_argument *)pExceptionObject;
  }
  if ( !**(_QWORD **)a1 || !*a2 )
    return 0;
  cchCount2 = mlib::m_traits<unsigned short>::CStrlen(a2, 0x10000);
  return CompareStringW(0x400u, 0x1000u, *(PCNZWCH *)(*(_QWORD *)a1 + 24LL), cchCount2, a2, cchCount2) == 2;
}

```

## disassembly

```asm
0x180029bd8  mov     r11, rsp
0x180029bdb  push    rdi
0x180029bdc  sub     rsp, 80h
0x180029be3  mov     qword ptr [r11-58h], 0FFFFFFFFFFFFFFFEh
0x180029beb  mov     [r11+18h], rbx
0x180029bef  mov     rax, cs:__security_cookie
0x180029bf6  xor     rax, rsp
0x180029bf9  mov     [rsp+88h+var_18], rax
0x180029bfe  mov     rbx, rdx
0x180029c01  mov     rdi, rcx
0x180029c04  xor     ecx, ecx
0x180029c06  test    rdx, rdx
0x180029c09  jnz     short loc_180029C41
0x180029c0b  mov     r9d, 16A0h
0x180029c11  lea     rdx, aStrIsNull; "str is null"
0x180029c18  lea     rcx, [r11-38h]; void *
0x180029c1c  call    ?_msrse_@mlib@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD0H@Z; mlib::_msrse_(char const *,char const *,int)
0x180029c21  nop
0x180029c22  mov     rdx, rax
0x180029c25  lea     rcx, [rsp+88h+pExceptionObject]
0x180029c2a  call    ??0out_of_range@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::out_of_range::out_of_range(std::string const &)
0x180029c2f  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x180029c36  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180029c3b  call    _CxxThrowException_0
0x180029c41  mov     rax, [rdi]
0x180029c44  cmp     [rax], rcx
0x180029c47  jz      short loc_180029C8C
0x180029c49  cmp     [rdx], cx
0x180029c4c  jz      short loc_180029C8C
0x180029c4e  mov     edx, 10000h
0x180029c53  mov     rcx, rbx
0x180029c56  call    ?CStrlen@?$m_traits@G@mlib@@SA_KPEBG_K@Z; mlib::m_traits<ushort>::CStrlen(ushort const *,unsigned __int64)
0x180029c5b  mov     rcx, [rdi]
0x180029c5e  mov     [rsp+88h+cchCount2], eax; cchCount2
0x180029c62  mov     [rsp+88h+lpString2], rbx; lpString2
0x180029c67  mov     r9d, eax; cchCount1
0x180029c6a  mov     r8, [rcx+18h]; lpString1
0x180029c6e  mov     edx, 1000h; dwCmpFlags
0x180029c73  mov     ecx, 400h; Locale
0x180029c78  call    cs:__imp_CompareStringW
0x180029c7f  nop     dword ptr [rax+rax+00h]
0x180029c84  cmp     eax, 2
0x180029c87  setz    al
0x180029c8a  jmp     short loc_180029C8E
0x180029c8c  xor     al, al
0x180029c8e  mov     rcx, [rsp+88h+var_18]
0x180029c93  xor     rcx, rsp; StackCookie
0x180029c96  call    __security_check_cookie
0x180029c9b  mov     rbx, [rsp+88h+arg_10]
0x180029ca3  add     rsp, 80h
0x180029caa  pop     rdi
0x180029cab  retn
```
