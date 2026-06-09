# WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::_GenerateActionArguments(WindowsInternal::ApplicationModel::Calls::IncomingToastAction,uint const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)

- ea: `0x180013e70`
- end: `0x180013eaf`
- name: `?_GenerateActionArguments@IncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@MEAAJW4IncomingToastAction@234@AEBIPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `63`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int *, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180004a0c`
- `0x180011e68`
- `0x180013e70`

## pseudocode

```c
__int64 __fastcall WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::_GenerateActionArguments(
        __int64 a1,
        unsigned int a2,
        unsigned int *a3,
        __int64 a4)
{
  int v4; // eax
  __int64 v5; // r8
  unsigned int v6; // ebx

  v4 = tlx::append_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
         a4,
         L"%u.%u",
         a2,
         *a3);
  v6 = v4;
  if ( v4 >= 0 )
    return 0;
  Log_HREvent_1((unsigned int)v4, 1, v5, 852);
  return v6;
}

```

## disassembly

```asm
0x180013e70  push    rbx
0x180013e72  sub     rsp, 30h
0x180013e76  mov     rcx, r9
0x180013e79  mov     r9d, [r8]
0x180013e7c  mov     r8d, edx
0x180013e7f  lea     rdx, aUU; "%u.%u"
0x180013e86  call    ??$append_sprintf@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGZZ; tlx::append_sprintf<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,...)
0x180013e8b  mov     ebx, eax
0x180013e8d  test    eax, eax
0x180013e8f  jns     short loc_180013EA7
0x180013e91  mov     edx, 1
0x180013e96  mov     r9d, 354h
0x180013e9c  mov     ecx, eax
0x180013e9e  call    Log_HREvent_1
0x180013ea3  mov     eax, ebx
0x180013ea5  jmp     short loc_180013EA9
0x180013ea7  xor     eax, eax
0x180013ea9  add     rsp, 30h
0x180013ead  pop     rbx
0x180013eae  retn
```
