# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x18000108c`
- end: `0x1800011c8`
- name: `??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@43@Z`
- size: `316`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _QWORD *, _QWORD *, _QWORD *, __int64, __int64, _QWORD *)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x1800072f0`
- `0x18000881c`
- `0x18000b414`
- `0x18000b994`
- `0x18000dad0`
- `0x18000e070`
- `0x18000f570`

## callees

- `0x18000108c`
- `0x1800011d0`
- `0x180001e20`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        _QWORD *a6,
        _QWORD *a7,
        __int64 a8,
        __int64 a9,
        _QWORD *a10)
{
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax

  v10 = -1;
  if ( *a10 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *(_BYTE *)(*a10 + v11) );
  }
  if ( *a7 )
  {
    v12 = -1;
    do
      ++v12;
    while ( *(_BYTE *)(*a7 + v12) );
  }
  if ( *a6 )
  {
    v13 = -1;
    do
      ++v13;
    while ( *(_BYTE *)(*a6 + v13) );
  }
  if ( *a5 )
  {
    do
      ++v10;
    while ( *(_BYTE *)(*a5 + v10) );
  }
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001D000, a2, 0);
}

```

## disassembly

```asm
0x18000108c  push    rbp
0x18000108e  lea     rbp, [rsp-27h]
0x180001093  sub     rsp, 0C0h
0x18000109a  mov     rax, cs:__security_cookie
0x1800010a1  xor     rax, rsp
0x1800010a4  mov     [rbp+27h+var_10], rax
0x1800010a8  mov     rax, [rbp+27h+arg_48]
0x1800010ac  lea     r11, qword_1800150F8
0x1800010b3  mov     r10, rdx
0x1800010b6  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800010ba  xor     r9d, r9d
0x1800010bd  mov     r8d, 1
0x1800010c3  mov     rdx, [rax]
0x1800010c6  test    rdx, rdx
0x1800010c9  jz      short loc_1800010DB
0x1800010cb  mov     rax, rcx
0x1800010ce  inc     rax
0x1800010d1  cmp     [rdx+rax], r9b
0x1800010d5  jnz     short loc_1800010CE
0x1800010d7  inc     eax
0x1800010d9  jmp     short loc_1800010E1
0x1800010db  mov     rdx, r11
0x1800010de  mov     eax, r8d
0x1800010e1  mov     [rbp+27h+var_18], eax
0x1800010e4  mov     rax, [rbp+27h+arg_40]
0x1800010e8  mov     [rbp+27h+var_30], rax
0x1800010ec  mov     rax, [rbp+27h+arg_38]
0x1800010f0  mov     [rbp+27h+var_40], rax
0x1800010f4  mov     rax, [rbp+27h+arg_30]
0x1800010f8  mov     [rbp+27h+var_20], rdx
0x1800010fc  mov     [rbp+27h+var_14], r9d
0x180001100  mov     [rbp+27h+var_28], 4
0x180001108  mov     rdx, [rax]
0x18000110b  mov     [rbp+27h+var_38], 4
0x180001113  test    rdx, rdx
0x180001116  jz      short loc_180001128
0x180001118  mov     rax, rcx
0x18000111b  inc     rax
0x18000111e  cmp     [rdx+rax], r9b
0x180001122  jnz     short loc_18000111B
0x180001124  inc     eax
0x180001126  jmp     short loc_18000112E
0x180001128  mov     rdx, r11
0x18000112b  mov     eax, r8d
0x18000112e  mov     [rbp+27h+var_48], eax
0x180001131  mov     rax, [rbp+27h+arg_28]
0x180001135  mov     [rbp+27h+var_50], rdx
0x180001139  mov     [rbp+27h+var_44], r9d
0x18000113d  mov     rdx, [rax]
0x180001140  test    rdx, rdx
0x180001143  jz      short loc_180001155
0x180001145  mov     rax, rcx
0x180001148  inc     rax
0x18000114b  cmp     [rdx+rax], r9b
0x18000114f  jnz     short loc_180001148
0x180001151  inc     eax
0x180001153  jmp     short loc_18000115B
0x180001155  mov     rdx, r11
0x180001158  mov     eax, r8d
0x18000115b  mov     [rbp+27h+var_58], eax
0x18000115e  mov     rax, [rbp+27h+arg_20]
0x180001162  mov     [rbp+27h+var_60], rdx
0x180001166  mov     [rbp+27h+var_54], r9d
0x18000116a  mov     rdx, [rax]
0x18000116d  test    rdx, rdx
0x180001170  jz      short loc_180001181
0x180001172  inc     rcx
0x180001175  cmp     [rdx+rcx], r9b
0x180001179  jnz     short loc_180001172
0x18000117b  lea     r8d, [rcx+1]
0x18000117f  jmp     short loc_180001184
0x180001181  mov     rdx, r11
0x180001184  lea     rax, [rbp+27h+var_90]
0x180001188  mov     [rbp+27h+var_70], rdx
0x18000118c  mov     [rbp+27h+var_68], r8d
0x180001190  lea     rcx, dword_18001D000
0x180001197  mov     [rsp+0C0h+var_98], rax
0x18000119c  xor     r8d, r8d
0x18000119f  mov     rdx, r10
0x1800011a2  mov     [rsp+0C0h+var_A0], 8
0x1800011aa  mov     [rbp+27h+var_64], r9d
0x1800011ae  call    _tlgWriteTransfer_EventWriteTransfer
0x1800011b3  mov     rcx, [rbp+27h+var_10]
0x1800011b7  xor     rcx, rsp; StackCookie
0x1800011ba  call    __security_check_cookie
0x1800011bf  add     rsp, 0C0h
0x1800011c6  pop     rbp
0x1800011c7  retn
```
