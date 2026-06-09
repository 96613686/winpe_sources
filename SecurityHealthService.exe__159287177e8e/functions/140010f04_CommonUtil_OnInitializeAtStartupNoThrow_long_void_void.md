# CommonUtil::OnInitializeAtStartupNoThrow(long (*)(void *),void *)

- ea: `0x140010f04`
- end: `0x140010f62`
- name: `?OnInitializeAtStartupNoThrow@CommonUtil@@YAJP6AJPEAX@Z0@Z`
- size: `94`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, int (*)(void *), void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400102a0`
- `0x140011c80`

## callees

- `0x140003640`
- `0x140010f04`
- `0x140013010`

## pseudocode

```c
__int64 __fastcall CommonUtil::OnInitializeAtStartupNoThrow(CommonUtil *this, int (*a2)(void *), void *a3)
{
  int v3; // ebx

  v3 = ((__int64 (__fastcall *)(int (*)(void *)))this)(a2);
  if ( v3 >= 0 )
    return 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_40931461d12536ea8f2e1fda7d29c7b2_Traceguids, (unsigned int)v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140010f04  push    rbx
0x140010f06  sub     rsp, 30h
0x140010f0a  mov     rax, rcx
0x140010f0d  mov     rcx, rdx
0x140010f10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010f15  mov     ebx, eax
0x140010f17  jmp     short loc_140010F1D
0x140010f19  mov     ebx, [rsp+38h+arg_0]
0x140010f1d  test    ebx, ebx
0x140010f1f  js      short loc_140010F29
0x140010f21  xor     eax, eax
0x140010f23  jmp     short loc_140010F5C
0x140010f25  mov     ebx, [rsp+38h+arg_0]
0x140010f29  lea     rax, WPP_GLOBAL_Control
0x140010f30  mov     rcx, cs:WPP_GLOBAL_Control
0x140010f37  cmp     rcx, rax
0x140010f3a  jz      short loc_140010F5A
0x140010f3c  test    byte ptr [rcx+1Ch], 1
0x140010f40  jz      short loc_140010F5A
0x140010f42  mov     edx, 0Ah
0x140010f47  mov     r9d, ebx
0x140010f4a  lea     r8, WPP_40931461d12536ea8f2e1fda7d29c7b2_Traceguids
0x140010f51  mov     rcx, [rcx+10h]
0x140010f55  call    WPP_SF_d
0x140010f5a  mov     eax, ebx
0x140010f5c  add     rsp, 30h
0x140010f60  pop     rbx
0x140010f61  retn
```
