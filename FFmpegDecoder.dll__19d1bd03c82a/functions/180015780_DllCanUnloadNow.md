# DllCanUnloadNow

- ea: `0x180015780`
- end: `0x18001583c`
- name: `DllCanUnloadNow`
- size: `188`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180015780`
- `0x180017bd0`
- `0x18001cddd`
- `0x18001d160`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  PSLIST_ENTRY v1; // r8
  struct _SLIST_ENTRY *Next; // rsi
  struct _SLIST_ENTRY *v3; // r9
  __int128 v4; // rt0
  unsigned __int8 v5; // tt

  if ( dword_18002FF20 )
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
0x180015780  mov     [rsp+arg_0], rbx
0x180015785  mov     [rsp+arg_8], rsi
0x18001578a  push    rdi
0x18001578b  sub     rsp, 40h
0x18001578f  mov     rax, cs:__security_cookie
0x180015796  xor     rax, rsp
0x180015799  mov     [rsp+48h+var_18], rax
0x18001579e  mov     eax, cs:dword_18002FF20
0x1800157a4  test    eax, eax
0x1800157a6  jz      short loc_1800157AF
0x1800157a8  mov     edi, 1
0x1800157ad  jmp     short loc_18001581D
0x1800157af  lea     rcx, ListHead; ListHead
0x1800157b6  call    InterlockedFlushSList
0x1800157bb  mov     r8, rax
0x1800157be  test    rax, rax
0x1800157c1  jz      short loc_18001581B
0x1800157c3  mov     edi, 1
0x1800157c8  mov     rsi, [r8]
0x1800157cb  mov     r9, [r8-10h]
0x1800157cf  test    r9, r9
0x1800157d2  jz      short loc_180015813
0x1800157d4  xor     ecx, ecx
0x1800157d6  mov     [rsp+48h+var_28], r9
0x1800157db  xor     ebx, ebx
0x1800157dd  mov     [rsp+48h+var_20], 0
0x1800157e6  xor     edx, edx
0x1800157e8  mov     rax, r9
0x1800157eb  lock cmpxchg16b xmmword ptr [r8-10h]
0x1800157f1  mov     [rsp+48h+var_28], rax
0x1800157f6  setz    al
0x1800157f9  mov     [rsp+48h+var_20], rdx
0x1800157fe  cmp     al, dil
0x180015801  jnz     short loc_180015813
0x180015803  mov     rax, [r9]
0x180015806  mov     rcx, r9
0x180015809  mov     rax, [rax+10h]
0x18001580d  call    cs:__guard_dispatch_icall_fptr
0x180015813  mov     r8, rsi
0x180015816  test    rsi, rsi
0x180015819  jnz     short loc_1800157C8
0x18001581b  xor     edi, edi
0x18001581d  mov     eax, edi
0x18001581f  mov     rcx, [rsp+48h+var_18]
0x180015824  xor     rcx, rsp; StackCookie
0x180015827  call    __security_check_cookie
0x18001582c  mov     rbx, [rsp+48h+arg_0]
0x180015831  mov     rsi, [rsp+48h+arg_8]
0x180015836  add     rsp, 40h
0x18001583a  pop     rdi
0x18001583b  retn
```
