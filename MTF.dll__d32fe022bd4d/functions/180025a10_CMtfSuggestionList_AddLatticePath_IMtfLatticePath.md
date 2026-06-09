# CMtfSuggestionList::AddLatticePath(IMtfLatticePath *)

- ea: `0x180025a10`
- end: `0x180025a96`
- name: `?AddLatticePath@CMtfSuggestionList@@UEAAJPEAUIMtfLatticePath@@@Z`
- size: `134`
- prototype: `__int64 __fastcall(CMtfSuggestionList *__hidden this, struct IMtfLatticePath *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180025a10`
- `0x18002b6c4`
- `0x18002f010`

## pseudocode

```c
__int64 __fastcall CMtfSuggestionList::AddLatticePath(CMtfSuggestionList *this, __int64 (***a2)(void))
{
  int v3; // ebx
  __int64 v4; // rcx
  __int64 result; // rax
  __int64 v6; // [rsp+38h] [rbp+10h] BYREF

  v6 = 0;
  try
  {
    v3 = (**a2)();
    if ( v3 >= 0 )
    {
      std::vector<IMtfSuggestionListElement *>::push_back((char *)this + 16, &v6);
      v4 = 0;
      v6 = 0;
    }
    else
    {
      MEMORY[0] = 0;
      v4 = v6;
    }
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    result = (unsigned int)v3;
  }
  catch ( ... )
  {
    return 2147500037LL;
  }
  return result;
}

```

## disassembly

```asm
0x180025a10  mov     [rsp+arg_0], rbx
0x180025a15  push    rdi
0x180025a16  sub     rsp, 20h
0x180025a1a  mov     r9, rdx
0x180025a1d  mov     rdi, rcx
0x180025a20  mov     [rsp+28h+arg_8], 0
0x180025a29  mov     rax, [rdx]
0x180025a2c  lea     r8, [rsp+28h+arg_8]
0x180025a31  lea     rdx, _GUID_5f445657_746b_468a_9ebb_ae80a72c4f7a
0x180025a38  mov     rcx, r9
0x180025a3b  mov     rax, [rax]
0x180025a3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a43  mov     ebx, eax
0x180025a45  test    eax, eax
0x180025a47  jns     short loc_180025A5B
0x180025a49  mov     dword ptr ds:0, 0
0x180025a54  mov     rcx, [rsp+28h+arg_8]
0x180025a59  jmp     short loc_180025A70
0x180025a5b  lea     rcx, [rdi+10h]
0x180025a5f  lea     rdx, [rsp+28h+arg_8]
0x180025a64  call    ?push_back@?$vector@PEAUIMtfSuggestionListElement@@V?$allocator@PEAUIMtfSuggestionListElement@@@std@@@std@@QEAAXAEBQEAUIMtfSuggestionListElement@@@Z; std::vector<IMtfSuggestionListElement *>::push_back(IMtfSuggestionListElement * const &)
0x180025a69  xor     ecx, ecx
0x180025a6b  mov     [rsp+28h+arg_8], rcx
0x180025a70  test    rcx, rcx
0x180025a73  jz      short loc_180025A81
0x180025a75  mov     rax, [rcx]
0x180025a78  mov     rax, [rax+10h]
0x180025a7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a81  mov     eax, ebx
0x180025a83  jmp     short loc_180025A8A
0x180025a85  mov     eax, 80004005h
0x180025a8a  mov     rbx, [rsp+28h+arg_0]
0x180025a8f  add     rsp, 20h
0x180025a93  pop     rdi
0x180025a94  retn
```
