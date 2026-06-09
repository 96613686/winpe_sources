# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)

- ea: `0x18000108c`
- end: `0x18000117d`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@34AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `241`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, _QWORD *, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180002d8c`
- `0x18000308c`

## callees

- `0x18000108c`
- `0x180001244`
- `0x180001730`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        _QWORD *a6,
        __int64 a7,
        _QWORD *a8)
{
  __int64 v8; // rcx
  __int64 v9; // rax

  v8 = -1;
  if ( *a8 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *(_BYTE *)(*a8 + v9) );
  }
  if ( *a6 )
  {
    do
      ++v8;
    while ( *(_BYTE *)(*a6 + v8) );
  }
  return tlgWriteTransfer_EventWriteTransfer(&dword_180007000, a2, 0);
}

```

## disassembly

```asm
0x18000108c  push    rbp
0x18000108e  lea     rbp, [rsp-2Fh]
0x180001093  sub     rsp, 0B0h
0x18000109a  mov     rax, cs:__security_cookie
0x1800010a1  xor     rax, rsp
0x1800010a4  mov     [rbp+2Fh+var_10], rax
0x1800010a8  mov     rax, [rbp+2Fh+arg_40]
0x1800010ac  xor     r9d, r9d
0x1800010af  mov     [rbp+2Fh+var_20], rax
0x1800010b3  mov     r10, rdx
0x1800010b6  mov     rax, [rbp+2Fh+arg_38]
0x1800010ba  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800010be  mov     [rbp+2Fh+var_18], 8
0x1800010c6  lea     r8d, [r9+1]
0x1800010ca  mov     rdx, [rax]
0x1800010cd  test    rdx, rdx
0x1800010d0  jz      short loc_1800010E2
0x1800010d2  mov     rax, rcx
0x1800010d5  inc     rax
0x1800010d8  cmp     [rdx+rax], r9b
0x1800010dc  jnz     short loc_1800010D5
0x1800010de  inc     eax
0x1800010e0  jmp     short loc_1800010EC
0x1800010e2  lea     rdx, word_18000563E
0x1800010e9  mov     eax, r8d
0x1800010ec  mov     [rbp+2Fh+var_28], eax
0x1800010ef  mov     rax, [rbp+2Fh+arg_30]
0x1800010f3  mov     [rbp+2Fh+var_40], rax
0x1800010f7  mov     rax, [rbp+2Fh+arg_28]
0x1800010fb  mov     [rbp+2Fh+var_30], rdx
0x1800010ff  mov     [rbp+2Fh+var_24], r9d
0x180001103  mov     [rbp+2Fh+var_38], 4
0x18000110b  mov     rdx, [rax]
0x18000110e  test    rdx, rdx
0x180001111  jz      short loc_180001122
0x180001113  inc     rcx
0x180001116  cmp     [rdx+rcx], r9b
0x18000111a  jnz     short loc_180001113
0x18000111c  lea     r8d, [rcx+1]
0x180001120  jmp     short loc_180001129
0x180001122  lea     rdx, word_18000563E
0x180001129  mov     rax, [rbp+2Fh+arg_20]
0x18000112d  lea     rcx, dword_180007000
0x180001134  mov     [rbp+2Fh+var_60], rax
0x180001138  lea     rax, [rbp+2Fh+var_80]
0x18000113c  mov     [rbp+2Fh+var_50], rdx
0x180001140  mov     rdx, r10
0x180001143  mov     [rbp+2Fh+var_48], r8d
0x180001147  xor     r8d, r8d
0x18000114a  mov     [rsp+0B0h+var_88], rax
0x18000114f  mov     [rsp+0B0h+var_90], 7
0x180001157  mov     [rbp+2Fh+var_44], r9d
0x18000115b  mov     [rbp+2Fh+var_58], 4
0x180001163  call    _tlgWriteTransfer_EventWriteTransfer
0x180001168  mov     rcx, [rbp+2Fh+var_10]
0x18000116c  xor     rcx, rsp; StackCookie
0x18000116f  call    __security_check_cookie
0x180001174  add     rsp, 0B0h
0x18000117b  pop     rbp
0x18000117c  retn
```
