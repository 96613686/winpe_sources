# DllCanUnloadNow

- ea: `0x180026390`
- end: `0x18002644c`
- name: `DllCanUnloadNow`
- size: `188`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180026390`
- `0x180027d10`
- `0x18002cc9d`
- `0x18002d040`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  PSLIST_ENTRY v1; // r8
  struct _SLIST_ENTRY *Next; // rsi
  struct _SLIST_ENTRY *v3; // r9
  __int128 v4; // rt0
  unsigned __int8 v5; // tt

  if ( dword_180045268 )
    return 1;
  v1 = InterlockedFlushSList(&ListHead);
  if ( v1 )
  {
    do
    {
      Next = v1->Next;
      v3 = v1[-1].Next;
      if ( v3 )
      {
        v4 = (unsigned __int64)v1[-1].Next;
        v5 = _InterlockedCompareExchange128((volatile signed __int64 *)&v1[-1], 0, 0, (signed __int64 *)&v4);
        if ( v5 != 0 )
          ((void (__fastcall *)(struct _SLIST_ENTRY *))v3->Next[1].Next)(v3);
      }
      v1 = Next;
    }
    while ( Next );
  }
  return 0;
}

```

## disassembly

```asm
0x180026390  mov     [rsp+arg_0], rbx
0x180026395  mov     [rsp+arg_8], rsi
0x18002639a  push    rdi
0x18002639b  sub     rsp, 40h
0x18002639f  mov     rax, cs:__security_cookie
0x1800263a6  xor     rax, rsp
0x1800263a9  mov     [rsp+48h+var_18], rax
0x1800263ae  mov     eax, cs:dword_180045268
0x1800263b4  test    eax, eax
0x1800263b6  jz      short loc_1800263BF
0x1800263b8  mov     edi, 1
0x1800263bd  jmp     short loc_18002642D
0x1800263bf  lea     rcx, ListHead; ListHead
0x1800263c6  call    InterlockedFlushSList
0x1800263cb  mov     r8, rax
0x1800263ce  test    rax, rax
0x1800263d1  jz      short loc_18002642B
0x1800263d3  mov     edi, 1
0x1800263d8  mov     rsi, [r8]
0x1800263db  mov     r9, [r8-10h]
0x1800263df  test    r9, r9
0x1800263e2  jz      short loc_180026423
0x1800263e4  xor     ecx, ecx
0x1800263e6  mov     [rsp+48h+var_28], r9
0x1800263eb  xor     ebx, ebx
0x1800263ed  mov     [rsp+48h+var_20], 0
0x1800263f6  xor     edx, edx
0x1800263f8  mov     rax, r9
0x1800263fb  lock cmpxchg16b xmmword ptr [r8-10h]
0x180026401  mov     [rsp+48h+var_28], rax
0x180026406  setz    al
0x180026409  mov     [rsp+48h+var_20], rdx
0x18002640e  cmp     al, dil
0x180026411  jnz     short loc_180026423
0x180026413  mov     rax, [r9]
0x180026416  mov     rcx, r9
0x180026419  mov     rax, [rax+10h]
0x18002641d  call    cs:__guard_dispatch_icall_fptr
0x180026423  mov     r8, rsi
0x180026426  test    rsi, rsi
0x180026429  jnz     short loc_1800263D8
0x18002642b  xor     edi, edi
0x18002642d  mov     eax, edi
0x18002642f  mov     rcx, [rsp+48h+var_18]
0x180026434  xor     rcx, rsp; StackCookie
0x180026437  call    __security_check_cookie
0x18002643c  mov     rbx, [rsp+48h+arg_0]
0x180026441  mov     rsi, [rsp+48h+arg_8]
0x180026446  add     rsp, 40h
0x18002644a  pop     rdi
0x18002644b  retn
```
