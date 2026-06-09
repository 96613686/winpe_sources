# CommonUtil::OnInitializeAtStartupNoThrow(long (*)(void *),void *)

- ea: `0x140004b3c`
- end: `0x140004b9e`
- name: `?OnInitializeAtStartupNoThrow@CommonUtil@@YAJP6AJPEAX@Z0@Z`
- size: `98`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, int (*)(void *), void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400055a0`
- `0x14001cd60`

## callees

- `0x140004b3c`
- `0x14001da70`
- `0x140024c40`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall CommonUtil::OnInitializeAtStartupNoThrow(CommonUtil *this, int (*a2)(void *), void *a3)
{
  int v3; // ebx

  v3 = ((__int64 (__fastcall *)(int (*)(void *)))this)(a2);
  if ( v3 >= 0 )
    return 0;
  _mm_lfence();
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_39b0cd1a9f7c3025f2f0b0bfda0a4dc5_Traceguids, (unsigned int)v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140004b3c  push    rbx
0x140004b3e  sub     rsp, 30h
0x140004b42  mov     rax, rcx
0x140004b45  mov     rcx, rdx
0x140004b48  call    cs:__guard_dispatch_icall_fptr
0x140004b4e  mov     ebx, eax
0x140004b50  jmp     short loc_140004B56
0x140004b52  mov     ebx, [rsp+38h+arg_0]
0x140004b56  test    ebx, ebx
0x140004b58  js      short loc_140004B62
0x140004b5a  xor     eax, eax
0x140004b5c  jmp     short loc_140004B98
0x140004b5e  mov     ebx, [rsp+38h+arg_0]
0x140004b62  lfence
0x140004b65  lea     rax, WPP_GLOBAL_Control
0x140004b6c  mov     rcx, cs:WPP_GLOBAL_Control
0x140004b73  cmp     rcx, rax
0x140004b76  jz      short loc_140004B96
0x140004b78  test    byte ptr [rcx+1Ch], 1
0x140004b7c  jz      short loc_140004B96
0x140004b7e  mov     edx, 0Ah
0x140004b83  mov     r9d, ebx
0x140004b86  lea     r8, WPP_39b0cd1a9f7c3025f2f0b0bfda0a4dc5_Traceguids
0x140004b8d  mov     rcx, [rcx+10h]
0x140004b91  call    WPP_SF_d
0x140004b96  mov     eax, ebx
0x140004b98  add     rsp, 30h
0x140004b9c  pop     rbx
0x140004b9d  retn
```
