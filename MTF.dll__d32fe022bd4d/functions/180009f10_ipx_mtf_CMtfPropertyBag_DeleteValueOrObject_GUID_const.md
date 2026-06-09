# ipx::mtf::CMtfPropertyBag::DeleteValueOrObject(_GUID const &)

- ea: `0x180009f10`
- end: `0x180009fa4`
- name: `?DeleteValueOrObject@CMtfPropertyBag@mtf@ipx@@UEAAJAEBU_GUID@@@Z`
- size: `148`
- prototype: `int(ipx::mtf::CMtfPropertyBag *__hidden this, const struct _GUID *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180009f10`
- `0x18000aa6c`
- `0x18000da18`
- `0x18000e0a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009f46`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009f46`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009f85`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009f85`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ipx::mtf::CMtfPropertyBag::DeleteValueOrObject(RTL_SRWLOCK *this, const struct _GUID *a2)
{
  __int64 result; // rax
  const char *v4; // r9
  unsigned int v5; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned __int16 v7; // [rsp+40h] [rbp+18h] BYREF
  RTL_SRWLOCK *v8; // [rsp+48h] [rbp+20h]

  v7 = 0;
  try
  {
    result = ipx::mtf::GuidMapper::MapGuidToWord(a2, &v7);
    v5 = result;
    if ( (int)result >= 0 )
    {
      AcquireSRWLockExclusive(this + 3);
      v8 = this + 3;
      if ( !std::_Tree<std::_Tmap_traits<unsigned short,ipx::mtf::CMtfPropertyBag::FlatData,std::less<unsigned short>,std::allocator<std::pair<unsigned short const,ipx::mtf::CMtfPropertyBag::FlatData>>,0>>::erase(
              &this[4],
              &v7)
        && !std::_Tree<std::_Tmap_traits<unsigned short,RefPtr<IUnknown>,std::less<unsigned short>,std::allocator<std::pair<unsigned short const,RefPtr<IUnknown>>>,0>>::erase(
              &this[6],
              &v7) )
      {
        v5 = -2143288319;
      }
      if ( this != (RTL_SRWLOCK *)-24LL )
        ReleaseSRWLockExclusive(this + 3);
      result = v5;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1A8,
                           (unsigned int)"mincore\\textinput\\dev\\mtf\\predictionengine\\containers\\propertybag.cpp",
                           v4);
  }
  return result;
}

```

## disassembly

```asm
0x180009f10  mov     [rsp+arg_0], rbx
0x180009f15  mov     [rsp+arg_8], rsi
0x180009f1a  push    rdi
0x180009f1b  sub     rsp, 20h
0x180009f1f  mov     r8, rdx
0x180009f22  mov     rsi, rcx
0x180009f25  xor     eax, eax
0x180009f27  mov     [rsp+28h+arg_10], ax
0x180009f2c  lea     rdx, [rsp+28h+arg_10]; unsigned __int16 *
0x180009f31  mov     rcx, r8; struct _GUID *
0x180009f34  call    ?MapGuidToWord@GuidMapper@mtf@ipx@@SAJAEBU_GUID@@PEAG@Z; ipx::mtf::GuidMapper::MapGuidToWord(_GUID const &,ushort *)
0x180009f39  mov     ebx, eax
0x180009f3b  test    eax, eax
0x180009f3d  js      short loc_180009F93
0x180009f3f  lea     rdi, [rsi+18h]
0x180009f43  mov     rcx, rdi; SRWLock
0x180009f46  call    cs:__imp_AcquireSRWLockExclusive
0x180009f4c  mov     [rsp+28h+arg_18], rdi
0x180009f51  lea     rcx, [rsi+20h]
0x180009f55  lea     rdx, [rsp+28h+arg_10]
0x180009f5a  call    ?erase@?$_Tree@V?$_Tmap_traits@GVFlatData@CMtfPropertyBag@mtf@ipx@@U?$less@G@std@@V?$allocator@U?$pair@$$CBGVFlatData@CMtfPropertyBag@mtf@ipx@@@std@@@6@$0A@@std@@@std@@QEAA_KAEBG@Z; std::_Tree<std::_Tmap_traits<ushort,ipx::mtf::CMtfPropertyBag::FlatData,std::less<ushort>,std::allocator<std::pair<ushort const,ipx::mtf::CMtfPropertyBag::FlatData>>,0>>::erase(ushort const &)
0x180009f5f  test    rax, rax
0x180009f62  jnz     short loc_180009F7D
0x180009f64  lea     rcx, [rsi+30h]
0x180009f68  lea     rdx, [rsp+28h+arg_10]
0x180009f6d  call    ?erase@?$_Tree@V?$_Tmap_traits@GV?$RefPtr@UIUnknown@@@@U?$less@G@std@@V?$allocator@U?$pair@$$CBGV?$RefPtr@UIUnknown@@@@@std@@@3@$0A@@std@@@std@@QEAA_KAEBG@Z; std::_Tree<std::_Tmap_traits<ushort,RefPtr<IUnknown>,std::less<ushort>,std::allocator<std::pair<ushort const,RefPtr<IUnknown>>>,0>>::erase(ushort const &)
0x180009f72  mov     ecx, 80400401h
0x180009f77  test    rax, rax
0x180009f7a  cmovz   ebx, ecx
0x180009f7d  test    rdi, rdi
0x180009f80  jz      short loc_180009F8B
0x180009f82  mov     rcx, rdi; SRWLock
0x180009f85  call    cs:__imp_ReleaseSRWLockExclusive
0x180009f8b  mov     eax, ebx
0x180009f8d  jmp     short loc_180009F93
0x180009f8f  mov     eax, dword ptr [rsp+28h+arg_10]
0x180009f93  mov     rbx, [rsp+28h+arg_0]
0x180009f98  mov     rsi, [rsp+28h+arg_8]
0x180009f9d  add     rsp, 20h
0x180009fa1  pop     rdi
0x180009fa2  retn
```
