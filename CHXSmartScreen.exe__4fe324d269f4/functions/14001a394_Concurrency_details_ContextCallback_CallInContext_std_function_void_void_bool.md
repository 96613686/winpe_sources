# Concurrency::details::_ContextCallback::_CallInContext(std::function<void (void)>,bool)

- ea: `0x14001a394`
- end: `0x14001a4b3`
- name: `?_CallInContext@_ContextCallback@details@Concurrency@@QEBAXV?$function@$$A6AXXZ@std@@_N@Z`
- size: `287`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400163d0`
- `0x14001c004`

## callees

- `0x140001710`
- `0x140003330`
- `0x1400088b4`
- `0x14001a394`
- `0x140031960`
- `0x140035010`

## import_xrefs

- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x14001a489`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x14001a489`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Concurrency::details::_ContextCallback::_CallInContext(__int64 *a1, __int64 a2, char a3)
{
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 result; // rax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 pExceptionObject; // [rsp+40h] [rbp-38h] BYREF
  __int64 Exception; // [rsp+48h] [rbp-30h]
  _QWORD v12[3]; // [rsp+50h] [rbp-28h] BYREF

  v12[2] = a2;
  v5 = *a1;
  if ( v5 )
  {
    v12[0] = 0;
    v12[1] = a2;
    result = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall *)(struct tagComCallData *), _QWORD *, GUID *, int, _QWORD))(*(_QWORD *)v5 + 24LL))(
               v5,
               Concurrency::details::_ContextCallback::_Bridge,
               v12,
               &IID_ICallbackWithNoReentrancyToApplicationSTA,
               5,
               0);
    if ( (int)result < 0
      && (!a3 || (_DWORD)result != -2147023174 && (_DWORD)result != -2147417848 && (_DWORD)result != -1996357631) )
    {
      Exception = Platform::Exception::CreateException((unsigned int)result);
      pExceptionObject = __abi_winrt_ptr_ctor(Exception);
      throw (Platform::Exception **)&pExceptionObject;
    }
  }
  else
  {
    v6 = *(_QWORD *)(a2 + 24);
    if ( !v6 )
      std::_Xbad_function_call();
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  v9 = *(_QWORD *)(a2 + 24);
  if ( v9 )
  {
    LOBYTE(v8) = v9 != a2;
    result = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 32LL))(v9, v8);
    *(_QWORD *)(a2 + 24) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14001a394  mov     [rsp+arg_10], rbx
0x14001a399  push    rdi
0x14001a39a  sub     rsp, 70h
0x14001a39e  mov     rax, cs:__security_cookie
0x14001a3a5  xor     rax, rsp
0x14001a3a8  mov     [rsp+78h+var_10], rax
0x14001a3ad  mov     dil, r8b
0x14001a3b0  mov     rbx, rdx
0x14001a3b3  mov     [rsp+78h+var_18], rdx
0x14001a3b8  mov     rcx, [rcx]
0x14001a3bb  test    rcx, rcx
0x14001a3be  jnz     short loc_14001A418
0x14001a3c0  mov     rcx, [rdx+18h]
0x14001a3c4  test    rcx, rcx
0x14001a3c7  jz      loc_14001A481
0x14001a3cd  mov     rax, [rcx]
0x14001a3d0  mov     rax, [rax+10h]
0x14001a3d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a3d9  nop
0x14001a3da  mov     rcx, [rbx+18h]
0x14001a3de  test    rcx, rcx
0x14001a3e1  jz      short loc_14001A3FD
0x14001a3e3  mov     rax, [rcx]
0x14001a3e6  cmp     rcx, rbx
0x14001a3e9  setnz   dl
0x14001a3ec  mov     rax, [rax+20h]
0x14001a3f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a3f5  mov     qword ptr [rbx+18h], 0
0x14001a3fd  mov     rcx, [rsp+78h+var_10]
0x14001a402  xor     rcx, rsp; StackCookie
0x14001a405  call    __security_check_cookie
0x14001a40a  mov     rbx, [rsp+78h+arg_10]
0x14001a412  add     rsp, 70h
0x14001a416  pop     rdi
0x14001a417  retn
0x14001a418  mov     [rsp+78h+var_28], 0
0x14001a421  mov     [rsp+78h+var_20], rbx
0x14001a426  mov     rax, [rcx]
0x14001a429  mov     [rsp+78h+var_50], 0
0x14001a432  mov     [rsp+78h+var_58], 5
0x14001a43a  lea     r9, IID_ICallbackWithNoReentrancyToApplicationSTA
0x14001a441  lea     r8, [rsp+78h+var_28]
0x14001a446  lea     rdx, ?_Bridge@_ContextCallback@details@Concurrency@@CAJPEAUtagComCallData@@@Z; Concurrency::details::_ContextCallback::_Bridge(tagComCallData *)
0x14001a44d  mov     rax, [rax+18h]
0x14001a451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a456  test    eax, eax
0x14001a458  jns     short loc_14001A3DA
0x14001a45a  test    dil, dil
0x14001a45d  jz      short loc_14001A487
0x14001a45f  cmp     eax, 800706BAh
0x14001a464  jz      loc_14001A3DA
0x14001a46a  cmp     eax, 80010108h
0x14001a46f  jz      loc_14001A3DA
0x14001a475  cmp     eax, 89020001h
0x14001a47a  jnz     short loc_14001A487
0x14001a47c  jmp     loc_14001A3DA
0x14001a481  call    ?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x14001a487  mov     ecx, eax
0x14001a489  call    cs:__imp_?CreateException@Exception@Platform@@SAPE$AAV12@H@Z; Platform::Exception::CreateException(int)
0x14001a48f  mov     [rsp+78h+var_30], rax
0x14001a494  mov     rcx, rax
0x14001a497  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x14001a49c  mov     [rsp+78h+pExceptionObject], rax
0x14001a4a1  lea     rdx, _TI9PE$AAVException@Platform@@; pThrowInfo
0x14001a4a8  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x14001a4ad  call    _CxxThrowException_0
```
