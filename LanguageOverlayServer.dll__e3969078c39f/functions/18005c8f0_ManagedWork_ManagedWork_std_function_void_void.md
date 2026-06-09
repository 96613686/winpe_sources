# ManagedWork::ManagedWork(std::function<void (void)> &&)

- ea: `0x18005c8f0`
- end: `0x18005ca5d`
- name: `??0ManagedWork@@QEAA@$$QEAV?$function@$$A6AXXZ@std@@@Z`
- size: `365`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180043a60`
- `0x18005a7dc`

## callees

- `0x180005db4`
- `0x180011334`
- `0x18005c8f0`
- `0x18006a010`

## import_xrefs

- `combase!__imp_CoAddRefSharedService` at `0x18005c96f`
- `combase!__imp_CoAddRefSharedService` at `0x18005c96f`
- `msvcp_win!_Mtx_unlock` at `0x18005c979`
- `msvcp_win!_Mtx_unlock` at `0x18005c979`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18005c938`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18005c953`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18005c938`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18005c953`
- `msvcp_win!_Mtx_lock` at `0x18005c929`
- `msvcp_win!_Mtx_lock` at `0x18005c929`

## string_xrefs

- `0x18005ca4b`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageoverlayservicemodule.cpp`

## pseudocode

```c
__int64 __fastcall ManagedWork::ManagedWork(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Details *v4; // rbx
  char *v5; // rsi
  unsigned int v6; // ebx
  _DWORD *v7; // rsi
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  unsigned int v12; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *(_QWORD *)a1 = &IManagedWork::`vftable';
  v4 = _service;
  v5 = (char *)_service + 16;
  if ( _Mtx_lock((Microsoft::WRL::Details *)((char *)_service + 16)) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( *((_DWORD *)v5 + 19) == 0x7FFFFFFF )
  {
    *((_DWORD *)v5 + 19) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  if ( ((*((_DWORD *)v4 + 31) - 1) & 0xFFFFFFFD) == 0 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x7F,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageoverlayservicemodule.cpp",
      (const char *)0x45B,
      v12);
  v6 = *((_DWORD *)v4 + 30);
  CoAddRefSharedService(v6);
  _Mtx_unlock((_Mtx_t)v5);
  *(_DWORD *)(a1 + 8) = v6;
  *(_QWORD *)a1 = &ManagedWork::`vftable';
  v7 = operator new(0x60u);
  *(_OWORD *)v7 = 0;
  v7[2] = 1;
  v7[3] = 1;
  *(_QWORD *)v7 = &std::_Ref_count_obj2<ManagedWorkExecutionContext>::`vftable';
  *((_QWORD *)v7 + 2) = &ManagedWorkExecutionContext::`vftable';
  *((_BYTE *)v7 + 24) = 0;
  *((_QWORD *)v7 + 11) = 0;
  v8 = *(_QWORD *)(a2 + 56);
  if ( v8 )
  {
    if ( v8 != a2 )
    {
      *((_QWORD *)v7 + 11) = v8;
      goto LABEL_11;
    }
    *((_QWORD *)v7 + 11) = (*(__int64 (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v8 + 8LL))(v8, v7 + 8);
    v10 = *(_QWORD *)(a2 + 56);
    if ( v10 )
    {
      LOBYTE(v9) = v10 != a2;
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v10 + 32LL))(v10, v9);
LABEL_11:
      *(_QWORD *)(a2 + 56) = 0;
    }
  }
  *(_QWORD *)(a1 + 16) = v7 + 4;
  *(_QWORD *)(a1 + 24) = v7;
  return a1;
}

```

## disassembly

```asm
0x18005c8f0  mov     r11, rsp
0x18005c8f3  mov     [r11+10h], rbx
0x18005c8f7  mov     [r11+20h], rbp
0x18005c8fb  mov     [r11+8], rcx
0x18005c8ff  push    rsi
0x18005c900  push    rdi
0x18005c901  push    r14; unsigned int
0x18005c903  sub     rsp, 20h
0x18005c907  mov     rbp, rdx
0x18005c90a  mov     rdi, rcx
0x18005c90d  lea     rax, ??_7IManagedWork@@6B@; const IManagedWork::`vftable'
0x18005c914  mov     [rcx], rax
0x18005c917  mov     rbx, cs:?_service@@3AEAVLanguageOverlayServiceModule@@EA; LanguageOverlayServiceModule & _service
0x18005c91e  lea     rsi, [rbx+10h]
0x18005c922  mov     [r11+18h], rsi
0x18005c926  mov     rcx, rsi; _Mtx_t
0x18005c929  call    cs:__imp__Mtx_lock
0x18005c92f  test    eax, eax
0x18005c931  jz      short loc_18005C93F
0x18005c933  mov     ecx, 5
0x18005c938  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18005c93e  int     3; Trap to Debugger
0x18005c93f  mov     eax, [rsi+4Ch]
0x18005c942  cmp     eax, 7FFFFFFFh
0x18005c947  jnz     short loc_18005C95A
0x18005c949  dec     eax
0x18005c94b  mov     [rsi+4Ch], eax
0x18005c94e  mov     ecx, 6
0x18005c953  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18005c959  nop
0x18005c95a  mov     eax, [rbx+7Ch]
0x18005c95d  dec     eax
0x18005c95f  test    eax, 0FFFFFFFDh
0x18005c964  jz      loc_18005CA40
0x18005c96a  mov     ebx, [rbx+78h]
0x18005c96d  mov     ecx, ebx
0x18005c96f  call    cs:__imp_CoAddRefSharedService
0x18005c975  nop
0x18005c976  mov     rcx, rsi; _Mtx_t
0x18005c979  call    cs:__imp__Mtx_unlock
0x18005c97f  mov     [rdi+8], ebx
0x18005c982  lea     rax, ??_7ManagedWork@@6B@; const ManagedWork::`vftable'
0x18005c989  mov     [rdi], rax
0x18005c98c  mov     ecx, 60h ; '`'; Size
0x18005c991  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005c996  mov     rsi, rax
0x18005c999  mov     [rsp+38h+arg_0], rax
0x18005c99e  xorps   xmm0, xmm0
0x18005c9a1  movups  xmmword ptr [rax], xmm0
0x18005c9a4  mov     dword ptr [rax+8], 1
0x18005c9ab  mov     dword ptr [rax+0Ch], 1
0x18005c9b2  lea     rax, ??_7?$_Ref_count_obj2@VManagedWorkExecutionContext@@@std@@6B@; const std::_Ref_count_obj2<ManagedWorkExecutionContext>::`vftable'
0x18005c9b9  mov     [rsi], rax
0x18005c9bc  lea     r14, [rsi+10h]
0x18005c9c0  lea     rax, ??_7ManagedWorkExecutionContext@@6B@; const ManagedWorkExecutionContext::`vftable'
0x18005c9c7  mov     [r14], rax
0x18005c9ca  mov     byte ptr [r14+8], 0
0x18005c9cf  mov     qword ptr [r14+48h], 0
0x18005c9d7  mov     rcx, [rbp+38h]
0x18005c9db  test    rcx, rcx
0x18005c9de  jz      short loc_18005CA22
0x18005c9e0  cmp     rcx, rbp
0x18005c9e3  jnz     short loc_18005CA16
0x18005c9e5  mov     rax, [rcx]
0x18005c9e8  lea     rdx, [r14+10h]
0x18005c9ec  mov     rax, [rax+8]
0x18005c9f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c9f5  mov     [r14+48h], rax
0x18005c9f9  mov     rcx, [rbp+38h]
0x18005c9fd  test    rcx, rcx
0x18005ca00  jz      short loc_18005CA22
0x18005ca02  mov     rax, [rcx]
0x18005ca05  cmp     rcx, rbp
0x18005ca08  setnz   dl
0x18005ca0b  mov     rax, [rax+20h]
0x18005ca0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ca14  jmp     short loc_18005CA1A
0x18005ca16  mov     [r14+48h], rcx
0x18005ca1a  mov     qword ptr [rbp+38h], 0
0x18005ca22  mov     [rdi+10h], r14
0x18005ca26  mov     [rdi+18h], rsi
0x18005ca2a  mov     rax, rdi
0x18005ca2d  mov     rbx, [rsp+38h+arg_8]
0x18005ca32  mov     rbp, [rsp+38h+arg_18]
0x18005ca37  add     rsp, 20h
0x18005ca3b  pop     r14
0x18005ca3d  pop     rdi
0x18005ca3e  pop     rsi
0x18005ca3f  retn
0x18005ca40  mov     rcx, [rsp+38h]; this
0x18005ca45  mov     r9d, 45Bh; char *
0x18005ca4b  lea     r8, aOnecoreBaseLan_5; "onecore\\base\\languageoverlay\\service"...
0x18005ca52  mov     edx, 7Fh; void *
0x18005ca57  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
