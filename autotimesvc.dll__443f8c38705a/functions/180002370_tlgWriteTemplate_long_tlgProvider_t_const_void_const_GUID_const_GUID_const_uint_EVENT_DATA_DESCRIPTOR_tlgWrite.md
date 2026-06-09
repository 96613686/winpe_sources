# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperPtrSize>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperPtrSize const &)

- ea: `0x180002370`
- end: `0x180002437`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$00@@U_tlgWrapperPtrSize@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$00@@AEBU_tlgWrapperPtrSize@@@Z`
- size: `199`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e6f8`

## callees

- `0x180001054`
- `0x180002370`
- `0x180002a70`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperPtrSize>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5)
{
  __int64 v5; // rax

  if ( *a5 )
  {
    v5 = -1;
    do
      ++v5;
    while ( *(_WORD *)(*a5 + 2 * v5) );
  }
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001C010, a2, 0, 0);
}

```

## disassembly

```asm
0x180002370  mov     r11, rsp
0x180002373  sub     rsp, 98h
0x18000237a  mov     rax, cs:__security_cookie
0x180002381  xor     rax, rsp
0x180002384  mov     [rsp+98h+var_18], rax
0x18000238c  mov     rcx, [rsp+98h+arg_30]
0x180002394  xor     r8d, r8d
0x180002397  mov     rax, [rcx]
0x18000239a  mov     [r11-28h], rax
0x18000239e  mov     eax, [rcx+8]
0x1800023a1  mov     [rsp+98h+var_20], eax
0x1800023a5  mov     rax, [rsp+98h+arg_28]
0x1800023ad  mov     [r11-38h], rax
0x1800023b1  mov     rax, [rsp+98h+arg_20]
0x1800023b9  mov     [r11-1Ch], r8d
0x1800023bd  mov     qword ptr [r11-30h], 1
0x1800023c5  mov     rcx, [rax]
0x1800023c8  test    rcx, rcx
0x1800023cb  jz      short loc_1800023E4
0x1800023cd  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800023d1  inc     rax
0x1800023d4  cmp     [rcx+rax*2], r8w
0x1800023d9  jnz     short loc_1800023D1
0x1800023db  lea     eax, ds:2[rax*2]
0x1800023e2  jmp     short loc_1800023F0
0x1800023e4  lea     rcx, dword_1800150AC
0x1800023eb  mov     eax, 2
0x1800023f0  mov     [rsp+98h+var_40], eax
0x1800023f4  xor     r9d, r9d
0x1800023f7  lea     rax, [rsp+98h+var_68]
0x1800023fc  mov     [rsp+98h+var_48], rcx
0x180002401  mov     [rsp+98h+var_70], rax
0x180002406  lea     rcx, dword_18001C010
0x18000240d  mov     [rsp+98h+var_78], 5
0x180002415  mov     [rsp+98h+var_3C], r8d
0x18000241a  call    _tlgWriteTransfer_EventWriteTransfer
0x18000241f  mov     rcx, [rsp+98h+var_18]
0x180002427  xor     rcx, rsp; StackCookie
0x18000242a  call    __security_check_cookie
0x18000242f  add     rsp, 98h
0x180002436  retn
```
