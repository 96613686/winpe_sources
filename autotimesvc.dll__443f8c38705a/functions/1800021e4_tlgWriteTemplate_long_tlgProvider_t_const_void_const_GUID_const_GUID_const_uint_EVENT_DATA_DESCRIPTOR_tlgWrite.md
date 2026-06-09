# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1800021e4`
- end: `0x1800022a5`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `193`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _QWORD *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e440`
- `0x18000e550`
- `0x18000e6f8`
- `0x18000ee3c`

## callees

- `0x180001054`
- `0x1800021e4`
- `0x180002a70`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
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
0x1800021e4  mov     r11, rsp
0x1800021e7  sub     rsp, 98h
0x1800021ee  mov     rax, cs:__security_cookie
0x1800021f5  xor     rax, rsp
0x1800021f8  mov     [rsp+98h+var_18], rax
0x180002200  mov     rax, [rsp+98h+arg_30]
0x180002208  xor     r8d, r8d
0x18000220b  mov     [r11-28h], rax
0x18000220f  mov     rax, [rsp+98h+arg_28]
0x180002217  mov     [r11-38h], rax
0x18000221b  mov     rax, [rsp+98h+arg_20]
0x180002223  mov     qword ptr [r11-20h], 4
0x18000222b  mov     qword ptr [r11-30h], 1
0x180002233  mov     rcx, [rax]
0x180002236  test    rcx, rcx
0x180002239  jz      short loc_180002252
0x18000223b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000223f  inc     rax
0x180002242  cmp     [rcx+rax*2], r8w
0x180002247  jnz     short loc_18000223F
0x180002249  lea     eax, ds:2[rax*2]
0x180002250  jmp     short loc_18000225E
0x180002252  lea     rcx, dword_1800150AC
0x180002259  mov     eax, 2
0x18000225e  mov     [rsp+98h+var_40], eax
0x180002262  xor     r9d, r9d
0x180002265  lea     rax, [rsp+98h+var_68]
0x18000226a  mov     [rsp+98h+var_48], rcx
0x18000226f  mov     [rsp+98h+var_70], rax
0x180002274  lea     rcx, dword_18001C010
0x18000227b  mov     [rsp+98h+var_78], 5
0x180002283  mov     [rsp+98h+var_3C], r8d
0x180002288  call    _tlgWriteTransfer_EventWriteTransfer
0x18000228d  mov     rcx, [rsp+98h+var_18]
0x180002295  xor     rcx, rsp; StackCookie
0x180002298  call    __security_check_cookie
0x18000229d  add     rsp, 98h
0x1800022a4  retn
```
