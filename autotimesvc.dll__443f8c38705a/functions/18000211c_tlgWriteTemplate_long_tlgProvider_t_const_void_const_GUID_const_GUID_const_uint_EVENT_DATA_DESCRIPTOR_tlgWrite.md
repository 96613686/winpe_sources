# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &)

- ea: `0x18000211c`
- end: `0x1800021dd`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$00@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$00@@4@Z`
- size: `193`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e440`

## callees

- `0x180001054`
- `0x18000211c`
- `0x180002a70`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(
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
0x18000211c  mov     r11, rsp
0x18000211f  sub     rsp, 98h
0x180002126  mov     rax, cs:__security_cookie
0x18000212d  xor     rax, rsp
0x180002130  mov     [rsp+98h+var_18], rax
0x180002138  mov     rax, [rsp+98h+arg_30]
0x180002140  xor     r8d, r8d
0x180002143  mov     [r11-28h], rax
0x180002147  mov     rax, [rsp+98h+arg_28]
0x18000214f  mov     [r11-38h], rax
0x180002153  mov     rax, [rsp+98h+arg_20]
0x18000215b  mov     qword ptr [r11-20h], 1
0x180002163  mov     qword ptr [r11-30h], 1
0x18000216b  mov     rcx, [rax]
0x18000216e  test    rcx, rcx
0x180002171  jz      short loc_18000218A
0x180002173  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002177  inc     rax
0x18000217a  cmp     [rcx+rax*2], r8w
0x18000217f  jnz     short loc_180002177
0x180002181  lea     eax, ds:2[rax*2]
0x180002188  jmp     short loc_180002196
0x18000218a  lea     rcx, dword_1800150AC
0x180002191  mov     eax, 2
0x180002196  mov     [rsp+98h+var_40], eax
0x18000219a  xor     r9d, r9d
0x18000219d  lea     rax, [rsp+98h+var_68]
0x1800021a2  mov     [rsp+98h+var_48], rcx
0x1800021a7  mov     [rsp+98h+var_70], rax
0x1800021ac  lea     rcx, dword_18001C010
0x1800021b3  mov     [rsp+98h+var_78], 5
0x1800021bb  mov     [rsp+98h+var_3C], r8d
0x1800021c0  call    _tlgWriteTransfer_EventWriteTransfer
0x1800021c5  mov     rcx, [rsp+98h+var_18]
0x1800021cd  xor     rcx, rsp; StackCookie
0x1800021d0  call    __security_check_cookie
0x1800021d5  add     rsp, 98h
0x1800021dc  retn
```
