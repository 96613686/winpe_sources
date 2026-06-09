# TextInputMethodFormatter::DataReceivedCallback(void *)

- ea: `0x18000a540`
- end: `0x18000a5d2`
- name: `?DataReceivedCallback@TextInputMethodFormatter@@CAJPEAX@Z`
- size: `146`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callees

- `0x18000271c`
- `0x18000428c`
- `0x18000a540`
- `0x18000a5d8`
- `0x180012030`
- `0x180012050`

## string_xrefs

- `0x18000a58f`: `mincore\textinput\dev\virtualization\textinputmethodformatter\dll\textinputmethodformatter.cpp`
- `0x18000a5a9`: `mincore\textinput\dev\virtualization\textinputmethodformatter\dll\textinputmethodformatter.cpp`
- `0x18000a5c0`: `mincore\textinput\dev\virtualization\textinputmethodformatter\dll\textinputmethodformatter.cpp`

## pseudocode

```c
__int64 __fastcall TextInputMethodFormatter::DataReceivedCallback(char *Block, __int64 a2, __int64 a3, const char *a4)
{
  TextInputMethodFormatter *v5; // rcx
  int v6; // eax
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !Block )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x28F,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\textinputmethodformatter\\dll\\textinputmethodformatter.cpp",
      a4);
  v5 = *(TextInputMethodFormatter **)Block;
  if ( !v5 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x290,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\textinputmethodformatter\\dll\\textinputmethodformatter.cpp",
      a4);
  v6 = TextInputMethodFormatter::DataReceivedImpl(v5);
  if ( v6 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x292,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\textinputmethodformatter\\dll\\textinputmethodformatter.cpp",
      (const char *)(unsigned int)v6,
      v8);
  std::vector<char>::~vector<char>(Block + 16);
  operator delete(Block);
  return 0;
}

```

## disassembly

```asm
0x18000a540  mov     [rsp+arg_0], rbx
0x18000a545  push    rdi; int
0x18000a546  sub     rsp, 20h
0x18000a54a  mov     rbx, rcx
0x18000a54d  test    rcx, rcx
0x18000a550  jz      short loc_18000A5A4
0x18000a552  mov     rcx, [rcx]; this
0x18000a555  test    rcx, rcx
0x18000a558  jz      short loc_18000A5BB
0x18000a55a  lea     r8, [rbx+10h]
0x18000a55e  call    ?DataReceivedImpl@TextInputMethodFormatter@@AEAAJIAEAV?$vector@DV?$allocator@D@std@@@std@@@Z; TextInputMethodFormatter::DataReceivedImpl(uint,std::vector<char> &)
0x18000a563  test    eax, eax
0x18000a565  js      short loc_18000A58A
0x18000a567  lea     rcx, [rbx+10h]
0x18000a56b  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x18000a570  mov     edx, 28h ; '('
0x18000a575  mov     rcx, rbx; Block
0x18000a578  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a57d  mov     rbx, [rsp+28h+arg_0]
0x18000a582  xor     eax, eax
0x18000a584  add     rsp, 20h
0x18000a588  pop     rdi
0x18000a589  retn
0x18000a58a  mov     rcx, [rsp+28h]; this
0x18000a58f  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\virtualization"...
0x18000a596  mov     r9d, eax; char *
0x18000a599  mov     edx, 292h; void *
0x18000a59e  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18000a5a4  mov     rcx, [rsp+28h]; this
0x18000a5a9  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\virtualization"...
0x18000a5b0  mov     edx, 28Fh; void *
0x18000a5b5  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000a5bb  mov     rcx, [rsp+28h]; this
0x18000a5c0  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\virtualization"...
0x18000a5c7  mov     edx, 290h; void *
0x18000a5cc  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
