# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMapsBrokerAsyncOperation>::QueryInterface(_GUID const &,void * *)

- ea: `0x180007cf0`
- end: `0x180007d64`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIMapsBrokerAsyncOperation@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `116`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180007cf0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMapsBrokerAsyncOperation>::QueryInterface(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  unsigned int v3; // ebx
  int v4; // eax

  v3 = 0;
  *a3 = 0;
  if ( *a2 )
  {
    if ( *a2 != -1119134625
      || a2[1] != *(_DWORD *)&GUID_bd4b5c5f_2fda_4f70_9304_22275c0fe19d.Data2
      || a2[2] != *(_DWORD *)GUID_bd4b5c5f_2fda_4f70_9304_22275c0fe19d.Data4 )
    {
      return (unsigned int)-2147467262;
    }
    v4 = *(_DWORD *)&GUID_bd4b5c5f_2fda_4f70_9304_22275c0fe19d.Data4[4];
  }
  else
  {
    if ( a2[1] != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data2
      || a2[2] != *(_DWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4 )
    {
      return (unsigned int)-2147467262;
    }
    v4 = *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data4[4];
  }
  if ( a2[3] != v4 )
    return (unsigned int)-2147467262;
  *a3 = a1;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  return v3;
}

```

## disassembly

```asm
0x180007cf0  push    rbx
0x180007cf2  sub     rsp, 20h
0x180007cf6  xor     ebx, ebx
0x180007cf8  mov     [r8], rbx
0x180007cfb  cmp     [rdx], ebx
0x180007cfd  jnz     short loc_180007D31
0x180007cff  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x180007d05  cmp     [rdx+4], eax
0x180007d08  jnz     short loc_180007D57
0x180007d0a  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x180007d10  cmp     [rdx+8], eax
0x180007d13  jnz     short loc_180007D57
0x180007d15  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x180007d1b  cmp     [rdx+0Ch], eax
0x180007d1e  jnz     short loc_180007D57
0x180007d20  mov     [r8], rcx
0x180007d23  mov     rax, [rcx]
0x180007d26  mov     rax, [rax+8]
0x180007d2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d2f  jmp     short loc_180007D5C
0x180007d31  cmp     dword ptr [rdx], 0BD4B5C5Fh
0x180007d37  jnz     short loc_180007D57
0x180007d39  mov     eax, dword ptr cs:_GUID_bd4b5c5f_2fda_4f70_9304_22275c0fe19d.Data2
0x180007d3f  cmp     [rdx+4], eax
0x180007d42  jnz     short loc_180007D57
0x180007d44  mov     eax, dword ptr cs:_GUID_bd4b5c5f_2fda_4f70_9304_22275c0fe19d.Data4
0x180007d4a  cmp     [rdx+8], eax
0x180007d4d  jnz     short loc_180007D57
0x180007d4f  mov     eax, dword ptr cs:_GUID_bd4b5c5f_2fda_4f70_9304_22275c0fe19d.Data4+4
0x180007d55  jmp     short loc_180007D1B
0x180007d57  mov     ebx, 80004002h
0x180007d5c  mov     eax, ebx
0x180007d5e  add     rsp, 20h
0x180007d62  pop     rbx
0x180007d63  retn
```
