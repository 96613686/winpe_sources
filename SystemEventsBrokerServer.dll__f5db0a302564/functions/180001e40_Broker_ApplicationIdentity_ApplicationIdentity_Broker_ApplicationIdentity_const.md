# Broker::ApplicationIdentity::ApplicationIdentity(Broker::ApplicationIdentity const &)

- ea: `0x180001e40`
- end: `0x180001ee1`
- name: `??0ApplicationIdentity@Broker@@QEAA@AEBU01@@Z`
- size: `161`
- prototype: `Broker::ApplicationIdentity *__fastcall(Broker::ApplicationIdentity *this, const struct Broker::ApplicationIdentity *)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800026d0`
- `0x180007880`
- `0x18001aa38`
- `0x18001b008`

## callees

- `0x180001e40`
- `0x1800085c0`
- `0x18001a540`

## pseudocode

```c
Broker::ApplicationIdentity *__fastcall Broker::ApplicationIdentity::ApplicationIdentity(
        Broker::ApplicationIdentity *this,
        const struct Broker::ApplicationIdentity *a2)
{
  _QWORD *v4; // rdx
  _QWORD *v5; // rdx

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  std::vector<unsigned char>::_Construct_n<unsigned char * const &,unsigned char * const &>(
    this,
    *((_QWORD *)a2 + 1) - *(_QWORD *)a2,
    a2);
  v4 = (_QWORD *)((char *)a2 + 24);
  *(_OWORD *)((char *)this + 24) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  if ( *((_QWORD *)a2 + 6) > 7u )
    v4 = (_QWORD *)*v4;
  std::wstring::_Construct<2,unsigned short const *>((char *)this + 24, v4, *((_QWORD *)a2 + 5));
  v5 = (_QWORD *)((char *)a2 + 56);
  *(_OWORD *)((char *)this + 56) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  if ( *((_QWORD *)a2 + 10) > 7u )
    v5 = (_QWORD *)*v5;
  std::wstring::_Construct<2,unsigned short const *>((char *)this + 56, v5, *((_QWORD *)a2 + 9));
  return this;
}

```

## disassembly

```asm
0x180001e40  mov     [rsp+arg_8], rbx
0x180001e45  mov     [rsp+arg_10], rsi
0x180001e4a  mov     [rsp+arg_0], rcx
0x180001e4f  push    rdi
0x180001e50  sub     rsp, 20h
0x180001e54  mov     rdi, rdx
0x180001e57  mov     rbx, rcx
0x180001e5a  xor     esi, esi
0x180001e5c  mov     [rcx], rsi
0x180001e5f  mov     [rcx+8], rsi
0x180001e63  mov     [rcx+10h], rsi
0x180001e67  lea     r9, [rdx+8]
0x180001e6b  mov     rdx, [r9]
0x180001e6e  sub     rdx, [rdi]
0x180001e71  mov     r8, rdi
0x180001e74  call    ??$_Construct_n@AEBQEAEAEBQEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBQEAE1@Z; std::vector<uchar>::_Construct_n<uchar * const &,uchar * const &>(unsigned __int64,uchar * const &,uchar * const &)
0x180001e79  nop
0x180001e7a  lea     rcx, [rbx+18h]
0x180001e7e  lea     rdx, [rdi+18h]
0x180001e82  xorps   xmm0, xmm0
0x180001e85  movups  xmmword ptr [rcx], xmm0
0x180001e88  mov     [rcx+10h], rsi
0x180001e8c  mov     [rcx+18h], rsi
0x180001e90  mov     r8, [rdx+10h]
0x180001e94  cmp     qword ptr [rdx+18h], 7
0x180001e99  jbe     short loc_180001E9E
0x180001e9b  mov     rdx, [rdx]
0x180001e9e  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x180001ea3  nop
0x180001ea4  lea     rcx, [rbx+38h]
0x180001ea8  lea     rdx, [rdi+38h]
0x180001eac  xorps   xmm0, xmm0
0x180001eaf  movups  xmmword ptr [rcx], xmm0
0x180001eb2  mov     [rcx+10h], rsi
0x180001eb6  mov     [rcx+18h], rsi
0x180001eba  mov     r8, [rdx+10h]
0x180001ebe  cmp     qword ptr [rdx+18h], 7
0x180001ec3  jbe     short loc_180001EC8
0x180001ec5  mov     rdx, [rdx]
0x180001ec8  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x180001ecd  nop
0x180001ece  mov     rax, rbx
0x180001ed1  mov     rbx, [rsp+28h+arg_8]
0x180001ed6  mov     rsi, [rsp+28h+arg_10]
0x180001edb  add     rsp, 20h
0x180001edf  pop     rdi
0x180001ee0  retn
```
