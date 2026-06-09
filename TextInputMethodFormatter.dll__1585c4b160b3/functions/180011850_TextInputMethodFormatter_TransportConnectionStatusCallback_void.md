# TextInputMethodFormatter::TransportConnectionStatusCallback(void *)

- ea: `0x180011850`
- end: `0x1800118cf`
- name: `?TransportConnectionStatusCallback@TextInputMethodFormatter@@CAJPEAX@Z`
- size: `127`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callees

- `0x18000271c`
- `0x18000df34`
- `0x180011850`
- `0x180012030`
- `0x180012050`

## string_xrefs

- `0x18001188c`: `mincore\textinput\dev\virtualization\textinputmethodformatter\dll\textinputmethodformatter.cpp`
- `0x1800118a6`: `mincore\textinput\dev\virtualization\textinputmethodformatter\dll\textinputmethodformatter.cpp`
- `0x1800118bd`: `mincore\textinput\dev\virtualization\textinputmethodformatter\dll\textinputmethodformatter.cpp`

## pseudocode

```c
__int64 __fastcall TextInputMethodFormatter::TransportConnectionStatusCallback(
        _DWORD *Block,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  __int64 v5; // rcx
  int v6; // eax
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !Block )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF9,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\textinputmethodformatter\\dll\\textinputmethodformatter.cpp",
      a4);
  v5 = *(_QWORD *)Block;
  if ( !v5 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xFA,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\textinputmethodformatter\\dll\\textinputmethodformatter.cpp",
      a4);
  v6 = TextInputMethodFormatter::OnTransportConnectionStatusChangedImpl(v5, Block[2]);
  if ( v6 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0xFC,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\textinputmethodformatter\\dll\\textinputmethodformatter.cpp",
      (const char *)(unsigned int)v6,
      v8);
  operator delete(Block);
  return 0;
}

```

## disassembly

```asm
0x180011850  push    rbx; int
0x180011852  sub     rsp, 20h
0x180011856  mov     rbx, rcx
0x180011859  test    rcx, rcx
0x18001185c  jz      short loc_1800118A1
0x18001185e  mov     rcx, [rcx]
0x180011861  test    rcx, rcx
0x180011864  jz      short loc_1800118B8
0x180011866  mov     edx, [rbx+8]
0x180011869  call    ?OnTransportConnectionStatusChangedImpl@TextInputMethodFormatter@@AEAAJW4TransportConnectionStatus@@@Z; TextInputMethodFormatter::OnTransportConnectionStatusChangedImpl(TransportConnectionStatus)
0x18001186e  test    eax, eax
0x180011870  js      short loc_180011887
0x180011872  mov     edx, 10h
0x180011877  mov     rcx, rbx; Block
0x18001187a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001187f  xor     eax, eax
0x180011881  add     rsp, 20h
0x180011885  pop     rbx
0x180011886  retn
0x180011887  mov     rcx, [rsp+28h]; this
0x18001188c  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\virtualization"...
0x180011893  mov     r9d, eax; char *
0x180011896  mov     edx, 0FCh; void *
0x18001189b  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800118a1  mov     rcx, [rsp+28h]; this
0x1800118a6  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\virtualization"...
0x1800118ad  mov     edx, 0F9h; void *
0x1800118b2  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800118b8  mov     rcx, [rsp+28h]; this
0x1800118bd  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\virtualization"...
0x1800118c4  mov     edx, 0FAh; void *
0x1800118c9  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
