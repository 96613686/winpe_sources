# TvkrImplWrapper::SendKeyToHost(uint,CKeyPressInfo &)

- ea: `0x180010910`
- end: `0x1800109a8`
- name: `?SendKeyToHost@TvkrImplWrapper@@UEAAJIAEAVCKeyPressInfo@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(TvkrImplWrapper *__hidden this, unsigned int, struct CKeyPressInfo *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x18000428c`
- `0x180006a14`
- `0x180010910`
- `0x180014c9c`
- `0x180058010`

## import_xrefs

- `CoreMessaging!MsgBlobCreateShared` at `0x180010946`
- `CoreMessaging!MsgBlobCreateShared` at `0x180010946`
- `CoreMessaging!MsgRelease` at `0x180010989`
- `CoreMessaging!MsgRelease` at `0x180010989`

## string_xrefs

- `0x180010971`: `mincore\textinput\dev\virtualization\textinputmethodformatter\dll\textinputmethodformatter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TvkrImplWrapper::SendKeyToHost(TvkrImplWrapper *this, unsigned int a2, struct CKeyPressInfo *a3)
{
  int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  unsigned int v9; // ebx
  __int64 v11; // [rsp+20h] [rbp-28h] BYREF
  int v12; // [rsp+28h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v14; // [rsp+50h] [rbp+8h] BYREF

  CKeyPressInfo::Serialize(a3, &v11);
  v14 = 0;
  MsgBlobCreateShared(v11, (unsigned int)(v12 - v11), &v14);
  v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 4) + 32LL))(
         *((_QWORD *)this + 4),
         a2,
         v14);
  v9 = v5;
  if ( v5 >= 0 )
  {
    MsgRelease(v14, v6, v7, v8);
    v9 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x68,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\textinputmethodformatter\\dll\\textinputmethodformatter.cpp",
      (const char *)(unsigned int)v5,
      v11);
  }
  std::vector<char>::~vector<char>(&v11);
  return v9;
}

```

## disassembly

```asm
0x180010910  mov     [rsp+arg_8], rbx
0x180010915  push    rdi
0x180010916  sub     rsp, 40h
0x18001091a  mov     edi, edx
0x18001091c  mov     rbx, rcx
0x18001091f  lea     rdx, [rsp+48h+var_28]
0x180010924  mov     rcx, r8
0x180010927  call    ?Serialize@CKeyPressInfo@@QEAA?AV?$vector@EV?$allocator@E@std@@@std@@XZ; CKeyPressInfo::Serialize(void)
0x18001092c  nop
0x18001092d  mov     [rsp+48h+arg_0], 0
0x180010936  mov     edx, [rsp+48h+var_20]
0x18001093a  mov     rcx, [rsp+48h+var_28]
0x18001093f  sub     edx, ecx
0x180010941  lea     r8, [rsp+48h+arg_0]
0x180010946  call    cs:__imp_MsgBlobCreateShared
0x18001094c  mov     rcx, [rbx+20h]
0x180010950  mov     rax, [rcx]
0x180010953  mov     r8, [rsp+48h+arg_0]
0x180010958  mov     edx, edi
0x18001095a  mov     rax, [rax+20h]
0x18001095e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010963  mov     ebx, eax
0x180010965  test    eax, eax
0x180010967  jns     short loc_180010984
0x180010969  mov     rcx, [rsp+48h]; this
0x18001096e  mov     r9d, eax; char *
0x180010971  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\virtualization"...
0x180010978  mov     edx, 68h ; 'h'; void *
0x18001097d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010982  jmp     short loc_180010991
0x180010984  mov     rcx, [rsp+48h+arg_0]
0x180010989  call    cs:__imp_MsgRelease
0x18001098f  xor     ebx, ebx
0x180010991  lea     rcx, [rsp+48h+var_28]
0x180010996  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x18001099b  mov     eax, ebx
0x18001099d  mov     rbx, [rsp+48h+arg_8]
0x1800109a2  add     rsp, 40h
0x1800109a6  pop     rdi
0x1800109a7  retn
```
