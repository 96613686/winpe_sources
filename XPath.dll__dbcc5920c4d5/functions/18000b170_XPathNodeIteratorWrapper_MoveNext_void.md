# XPathNodeIteratorWrapper::MoveNext(void)

- ea: `0x18000b170`
- end: `0x18000b1f3`
- name: `?MoveNext@XPathNodeIteratorWrapper@@UEAAJXZ`
- size: `131`
- prototype: `__int64 __fastcall(XPathNodeIteratorWrapper *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800020b4`
- `0x18000b170`
- `0x18000e5ac`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall XPathNodeIteratorWrapper::MoveNext(XPathNodeIteratorWrapper *this)
{
  __int64 result; // rax
  __int64 v3; // rcx
  int valid; // ebx
  struct IXPathNavigator *v5; // [rsp+30h] [rbp+8h] BYREF

  result = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 48LL))(*((_QWORD *)this + 3));
  if ( (int)result >= 0 && (_DWORD)result != 1 )
  {
    v3 = *((_QWORD *)this + 3);
    v5 = 0;
    valid = (*(__int64 (__fastcall **)(__int64, struct IXPathNavigator **))(*(_QWORD *)v3 + 32LL))(v3, &v5);
    if ( valid < 0
      || (valid = XPathNavigatorInternal::InitializeAsValidPosition(
                    (XPathNodeIteratorWrapper *)((char *)this + 32),
                    (struct IUnknown *)v5),
          valid < 0) )
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v5);
      return (unsigned int)valid;
    }
    else
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v5);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000b170  mov     [rsp+arg_8], rbx
0x18000b175  push    rdi
0x18000b176  sub     rsp, 20h
0x18000b17a  mov     rdi, rcx
0x18000b17d  mov     rcx, [rcx+18h]
0x18000b181  mov     rax, [rcx]
0x18000b184  mov     rax, [rax+30h]
0x18000b188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b18d  test    eax, eax
0x18000b18f  js      short loc_18000B1E8
0x18000b191  cmp     eax, 1
0x18000b194  jz      short loc_18000B1E8
0x18000b196  mov     rcx, [rdi+18h]
0x18000b19a  lea     rdx, [rsp+28h+arg_0]
0x18000b19f  mov     [rsp+28h+arg_0], 0
0x18000b1a8  mov     rax, [rcx]
0x18000b1ab  mov     rax, [rax+20h]
0x18000b1af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1b4  mov     ebx, eax
0x18000b1b6  test    eax, eax
0x18000b1b8  jns     short loc_18000B1C8
0x18000b1ba  lea     rcx, [rsp+28h+arg_0]
0x18000b1bf  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000b1c4  mov     eax, ebx
0x18000b1c6  jmp     short loc_18000B1E8
0x18000b1c8  mov     rdx, [rsp+28h+arg_0]; struct IXPathNavigator *
0x18000b1cd  lea     rcx, [rdi+20h]; this
0x18000b1d1  call    ?InitializeAsValidPosition@XPathNavigatorInternal@@QEAAJPEAUIXPathNavigator@@@Z; XPathNavigatorInternal::InitializeAsValidPosition(IXPathNavigator *)
0x18000b1d6  lea     rcx, [rsp+28h+arg_0]
0x18000b1db  mov     ebx, eax
0x18000b1dd  test    eax, eax
0x18000b1df  js      short loc_18000B1BF
0x18000b1e1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000b1e6  xor     eax, eax
0x18000b1e8  mov     rbx, [rsp+28h+arg_8]
0x18000b1ed  add     rsp, 20h
0x18000b1f1  pop     rdi
0x18000b1f2  retn
```
