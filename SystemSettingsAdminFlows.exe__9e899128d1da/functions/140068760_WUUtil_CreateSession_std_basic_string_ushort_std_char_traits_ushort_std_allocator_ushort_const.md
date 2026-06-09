# WUUtil::CreateSession(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x140068760`
- end: `0x140068815`
- name: `?CreateSession@WUUtil@@YA?AV?$CComPtr@UIUpdateSession@@@ATL@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14004255c`

## callees

- `0x140029eb8`
- `0x14004158c`
- `0x1400430c0`
- `0x140068760`
- `0x14007d010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1400687a2`
- `ole32!CoCreateInstance` at `0x1400687a2`
- `OLEAUT32!__imp_SysAllocString` at `0x1400687f7`
- `OLEAUT32!__imp_SysAllocString` at `0x1400687f7`
- `OLEAUT32!__imp_SysFreeString` at `0x1400687e0`
- `OLEAUT32!__imp_SysFreeString` at `0x1400687e0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPVOID *__fastcall WUUtil::CreateSession(LPVOID *a1, __int64 a2)
{
  HRESULT Instance; // eax
  const OLECHAR *v5; // rax
  OLECHAR *v6; // rbx
  int v7; // eax

  *a1 = 0;
  Instance = CoCreateInstance(
               &GUID_4cb43d7f_7eee_4906_8698_60da1c38f2fe,
               0,
               1u,
               &GUID_816858a4_260d_4260_933a_2585f1abc76b,
               a1);
  THROW_HR_IF_FAILED(Instance);
  v5 = (const OLECHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  if ( v5 )
  {
    v6 = SysAllocString(v5);
    if ( !v6 )
      ATL::AtlThrowImpl(-2147024882);
  }
  else
  {
    v6 = 0;
  }
  v7 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *))(*(_QWORD *)*a1 + 64LL))(*a1, v6);
  THROW_HR_IF_FAILED(v7);
  SysFreeString(v6);
  return a1;
}

```

## disassembly

```asm
0x140068760  mov     rax, rsp
0x140068763  mov     [rax+18h], rbx
0x140068767  mov     [rax+8], rcx
0x14006876b  push    rdi
0x14006876c  sub     rsp, 40h
0x140068770  mov     rbx, rdx
0x140068773  mov     rdi, rcx
0x140068776  mov     dword ptr [rax-18h], 0
0x14006877d  mov     qword ptr [rcx], 0
0x140068784  mov     r8d, 1; dwClsContext
0x14006878a  mov     [rax-18h], r8d
0x14006878e  mov     [rax-28h], rcx
0x140068792  lea     r9, _GUID_816858a4_260d_4260_933a_2585f1abc76b; riid
0x140068799  xor     edx, edx; pUnkOuter
0x14006879b  lea     rcx, _GUID_4cb43d7f_7eee_4906_8698_60da1c38f2fe; rclsid
0x1400687a2  call    cs:__imp_CoCreateInstance
0x1400687a8  mov     ecx, eax; int
0x1400687aa  call    ?THROW_HR_IF_FAILED@@YAXJ@Z; THROW_HR_IF_FAILED(long)
0x1400687af  mov     rcx, rbx
0x1400687b2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1400687b7  test    rax, rax
0x1400687ba  jnz     short loc_1400687F4
0x1400687bc  xor     ebx, ebx
0x1400687be  mov     [rsp+48h+arg_8], rbx
0x1400687c3  mov     rcx, [rdi]
0x1400687c6  mov     rax, [rcx]
0x1400687c9  mov     rdx, rbx
0x1400687cc  mov     rax, [rax+40h]
0x1400687d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400687d5  mov     ecx, eax; int
0x1400687d7  call    ?THROW_HR_IF_FAILED@@YAXJ@Z; THROW_HR_IF_FAILED(long)
0x1400687dc  nop
0x1400687dd  mov     rcx, rbx; bstrString
0x1400687e0  call    cs:__imp_SysFreeString
0x1400687e6  mov     rax, rdi
0x1400687e9  mov     rbx, [rsp+48h+arg_10]
0x1400687ee  add     rsp, 40h
0x1400687f2  pop     rdi
0x1400687f3  retn
0x1400687f4  mov     rcx, rax; psz
0x1400687f7  call    cs:__imp_SysAllocString
0x1400687fd  mov     rbx, rax
0x140068800  mov     [rsp+48h+arg_8], rax
0x140068805  test    rax, rax
0x140068808  jnz     short loc_1400687C3
0x14006880a  mov     ecx, 8007000Eh; int
0x14006880f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
