# CommonUtil::UtilWinRpcGetClientPid(ulong *,void *)

- ea: `0x140003f6c`
- end: `0x140004031`
- name: `?UtilWinRpcGetClientPid@CommonUtil@@YAJPEAKPEAX@Z`
- size: `197`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, unsigned int *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14001e654`

## callees

- `0x140002584`
- `0x140003f6c`
- `0x140005c20`
- `0x14001da70`
- `0x140024c40`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilWinRpcGetClientPid(CommonUtil *this, unsigned int *a2, void *a3)
{
  bool v3; // zf
  __int64 (__fastcall *v7)(unsigned int *, int *); // rax
  int v8; // ebx
  unsigned int v9; // ebx
  int v10; // [rsp+20h] [rbp-18h] BYREF

  v3 = dword_14003C120 == 0;
  *(_DWORD *)this = 0;
  if ( v3 )
    return 2147500033LL;
  if ( a2 == (unsigned int *)-1LL )
    return 2147942487LL;
  v7 = (__int64 (__fastcall *)(unsigned int *, int *))MpDecodeVoidPointer(qword_14003C118, a2, a3);
  v10 = 0;
  v8 = v7(a2, &v10);
  if ( v8 )
  {
    v9 = v8 | 0x80010000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_5d796bf5d6913099feb0f367352bb89a_Traceguids, v9);
    return v9;
  }
  else
  {
    *(_DWORD *)this = v10;
    return 0;
  }
}

```

## disassembly

```asm
0x140003f6c  mov     [rsp+arg_10], rbx
0x140003f71  push    rdi
0x140003f72  sub     rsp, 30h
0x140003f76  mov     rax, cs:__security_cookie
0x140003f7d  xor     rax, rsp
0x140003f80  mov     [rsp+38h+var_10], rax
0x140003f85  cmp     cs:dword_14003C120, 0
0x140003f8c  mov     rbx, rdx
0x140003f8f  mov     rdi, rcx
0x140003f92  mov     dword ptr [rcx], 0
0x140003f98  jnz     short loc_140003FA1
0x140003f9a  mov     eax, 80004001h
0x140003f9f  jmp     short loc_140004019
0x140003fa1  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140003fa5  jnz     short loc_140003FAE
0x140003fa7  mov     eax, 80070057h
0x140003fac  jmp     short loc_140004019
0x140003fae  mov     rcx, cs:qword_14003C118
0x140003fb5  call    MpDecodeVoidPointer
0x140003fba  lea     rdx, [rsp+38h+var_18]
0x140003fbf  mov     [rsp+38h+var_18], 0
0x140003fc7  mov     rcx, rbx
0x140003fca  call    cs:__guard_dispatch_icall_fptr
0x140003fd0  mov     ebx, eax
0x140003fd2  test    eax, eax
0x140003fd4  jz      short loc_140004011
0x140003fd6  or      ebx, 80010000h
0x140003fdc  mov     rcx, cs:WPP_GLOBAL_Control
0x140003fe3  lea     rax, WPP_GLOBAL_Control
0x140003fea  cmp     rcx, rax
0x140003fed  jz      short loc_14000400D
0x140003fef  test    byte ptr [rcx+1Ch], 1
0x140003ff3  jz      short loc_14000400D
0x140003ff5  mov     rcx, [rcx+10h]
0x140003ff9  lea     r8, WPP_5d796bf5d6913099feb0f367352bb89a_Traceguids
0x140004000  mov     edx, 0Bh
0x140004005  mov     r9d, ebx
0x140004008  call    WPP_SF_d
0x14000400d  mov     eax, ebx
0x14000400f  jmp     short loc_140004019
0x140004011  mov     eax, [rsp+38h+var_18]
0x140004015  mov     [rdi], eax
0x140004017  xor     eax, eax
0x140004019  mov     rcx, [rsp+38h+var_10]
0x14000401e  xor     rcx, rsp; StackCookie
0x140004021  call    __security_check_cookie
0x140004026  mov     rbx, [rsp+38h+arg_10]
0x14000402b  add     rsp, 30h
0x14000402f  pop     rdi
0x140004030  retn
```
