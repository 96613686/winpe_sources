# `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<bool> *>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vector deleting destructor'(uint)

- ea: `0x18000b6e0`
- end: `0x18000b75f`
- name: `??_ECompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@_N@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@_N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@UEAAPEAXI@Z`
- size: `127`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800049f4`
- `0x18000b6e0`
- `0x180012114`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b6f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b6f8`

## string_xrefs

- `0x18000b74d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<bool> *>'::`2'::CompletionDelegate::`vector deleting destructor'(
        _QWORD *Block,
        char a2)
{
  void *v4; // rcx
  const char *v5; // r9
  __int64 v6; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = (void *)Block[7];
  if ( v4 && !CloseHandle(v4) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v5);
  *((_DWORD *)Block + 11) = -1073741823;
  v6 = Block[4];
  if ( v6 )
  {
    Block[4] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x18000b6e0  mov     [rsp+arg_0], rbx
0x18000b6e5  push    rdi
0x18000b6e6  sub     rsp, 20h
0x18000b6ea  mov     edi, edx
0x18000b6ec  mov     rbx, rcx
0x18000b6ef  mov     rcx, [rcx+38h]; hObject
0x18000b6f3  test    rcx, rcx
0x18000b6f6  jz      short loc_18000B707
0x18000b6f8  call    cs:__imp_CloseHandle
0x18000b6fe  mov     rcx, [rsp+28h]; this
0x18000b703  test    eax, eax
0x18000b705  jz      short loc_18000B74D
0x18000b707  mov     dword ptr [rbx+2Ch], 0C0000001h
0x18000b70e  mov     rcx, [rbx+20h]
0x18000b712  test    rcx, rcx
0x18000b715  jz      short loc_18000B72C
0x18000b717  mov     qword ptr [rbx+20h], 0
0x18000b71f  mov     rax, [rcx]
0x18000b722  mov     rax, [rax+10h]
0x18000b726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b72b  nop
0x18000b72c  test    dil, 1
0x18000b730  jz      short loc_18000B73F
0x18000b732  mov     edx, 40h ; '@'
0x18000b737  mov     rcx, rbx; Block
0x18000b73a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b73f  mov     rax, rbx
0x18000b742  mov     rbx, [rsp+28h+arg_0]
0x18000b747  add     rsp, 20h
0x18000b74b  pop     rdi
0x18000b74c  retn
0x18000b74d  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b754  mov     edx, 0A0Bh; void *
0x18000b759  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
