# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IPopupCommand>::QueryInterface(_GUID const &,void * *)

- ea: `0x140007fe0`
- end: `0x140008054`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIPopupCommand@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `116`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140007fe0`
- `0x14000a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IPopupCommand>::QueryInterface(
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
    if ( *a2 != 1146277385
      || a2[1] != *(_DWORD *)&GUID_4452ce09_0488_4ca7_a896_c4f140907549.Data2
      || a2[2] != *(_DWORD *)GUID_4452ce09_0488_4ca7_a896_c4f140907549.Data4 )
    {
      return (unsigned int)-2147467262;
    }
    v4 = *(_DWORD *)&GUID_4452ce09_0488_4ca7_a896_c4f140907549.Data4[4];
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
0x140007fe0  push    rbx
0x140007fe2  sub     rsp, 20h
0x140007fe6  xor     ebx, ebx
0x140007fe8  mov     [r8], rbx
0x140007feb  cmp     [rdx], ebx
0x140007fed  jnz     short loc_140008021
0x140007fef  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x140007ff5  cmp     [rdx+4], eax
0x140007ff8  jnz     short loc_140008047
0x140007ffa  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x140008000  cmp     [rdx+8], eax
0x140008003  jnz     short loc_140008047
0x140008005  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x14000800b  cmp     [rdx+0Ch], eax
0x14000800e  jnz     short loc_140008047
0x140008010  mov     [r8], rcx
0x140008013  mov     rax, [rcx]
0x140008016  mov     rax, [rax+8]
0x14000801a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000801f  jmp     short loc_14000804C
0x140008021  cmp     dword ptr [rdx], 4452CE09h
0x140008027  jnz     short loc_140008047
0x140008029  mov     eax, dword ptr cs:_GUID_4452ce09_0488_4ca7_a896_c4f140907549.Data2
0x14000802f  cmp     [rdx+4], eax
0x140008032  jnz     short loc_140008047
0x140008034  mov     eax, dword ptr cs:_GUID_4452ce09_0488_4ca7_a896_c4f140907549.Data4
0x14000803a  cmp     [rdx+8], eax
0x14000803d  jnz     short loc_140008047
0x14000803f  mov     eax, dword ptr cs:_GUID_4452ce09_0488_4ca7_a896_c4f140907549.Data4+4
0x140008045  jmp     short loc_14000800B
0x140008047  mov     ebx, 80004002h
0x14000804c  mov     eax, ebx
0x14000804e  add     rsp, 20h
0x140008052  pop     rbx
0x140008053  retn
```
