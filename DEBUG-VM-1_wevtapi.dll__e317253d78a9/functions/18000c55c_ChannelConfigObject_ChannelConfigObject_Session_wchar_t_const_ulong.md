# ChannelConfigObject::ChannelConfigObject(Session *,wchar_t const *,ulong)

- ea: `0x18000c55c`
- end: `0x18000c6bf`
- name: `??0ChannelConfigObject@@QEAA@PEAVSession@@PEB_WK@Z`
- size: `355`
- prototype: `ChannelConfigObject *__fastcall(ChannelConfigObject *__hidden this, struct Session *, const wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001a98c`

## callees

- `0x1800017cc`
- `0x18000c374`
- `0x18000c55c`
- `0x180023548`
- `0x180038fb4`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000c626`
- `RPCRT4!NdrClientCall3` at `0x18000c626`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
ChannelConfigObject *__fastcall ChannelConfigObject::ChannelConfigObject(
        ChannelConfigObject *this,
        struct Session *a2,
        const wchar_t *a3,
        int a4)
{
  char *v7; // r14
  __int64 v8; // rax
  unsigned int Pointer; // ebx
  _QWORD v11[2]; // [rsp+40h] [rbp-40h] BYREF
  _QWORD pExceptionObject[3]; // [rsp+50h] [rbp-30h] BYREF
  unsigned int v13; // [rsp+68h] [rbp-18h]
  __int64 v14; // [rsp+6Ch] [rbp-14h]
  char v15; // [rsp+74h] [rbp-Ch]

  *(_QWORD *)this = &wmi::RefBase::`vftable';
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 6) = 0;
  *((_WORD *)this + 14) = 10;
  *((_BYTE *)this + 30) = 1;
  v7 = (char *)this + 32;
  *((_OWORD *)this + 2) = 0;
  *(_QWORD *)this = &ChannelConfigObject::`vftable';
  *((_QWORD *)this + 6) = a2;
  if ( a2 )
    _InterlockedIncrement((volatile signed __int32 *)a2 + 2);
  v8 = -1;
  do
    ++v8;
  while ( a3[v8] );
  v11[0] = a3;
  v11[1] = v8;
  MakeOrThrowOOM((char *)this + 56, v11);
  utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>((_QWORD *)this + 11);
  *((_DWORD *)this + 28) = a4;
  *((_BYTE *)this + 116) = 0;
  Pointer = (unsigned int)NdrClientCall3(
                            (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                            0x14u,
                            0,
                            *((_QWORD *)a2 + 9),
                            *((_QWORD *)this + 7),
                            a4,
                            v7).Pointer;
  if ( Pointer )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_970b3d70c99a3bbc832a1e51198c3047_Traceguids, Pointer);
    }
    pExceptionObject[0] = &word_18004024A;
    pExceptionObject[1] = 0;
    pExceptionObject[2] = 0;
    v13 = Pointer;
    v14 = -1;
    v15 = 0;
    throw (EvtException *)pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x18000c55c  mov     [rsp-28h+arg_8], rbx
0x18000c561  mov     [rsp-28h+arg_10], rsi
0x18000c566  mov     [rsp-28h+arg_0], rcx
0x18000c56b  push    rbp
0x18000c56c  push    rdi
0x18000c56d  push    r12
0x18000c56f  push    r14
0x18000c571  push    r15
0x18000c573  mov     rbp, rsp
0x18000c576  sub     rsp, 80h
0x18000c57d  mov     r15d, r9d
0x18000c580  mov     rsi, rdx
0x18000c583  mov     rdi, rcx
0x18000c586  lea     rax, ??_7RefBase@wmi@@6B@; const wmi::RefBase::`vftable'
0x18000c58d  mov     [rcx], rax
0x18000c590  xor     r12d, r12d
0x18000c593  mov     [rcx+8], r12d
0x18000c597  mov     [rcx+10h], r12
0x18000c59b  mov     [rcx+18h], r12d
0x18000c59f  mov     word ptr [rcx+1Ch], 0Ah
0x18000c5a5  mov     byte ptr [rcx+1Eh], 1
0x18000c5a9  lea     r14, [rcx+20h]
0x18000c5ad  xorps   xmm0, xmm0
0x18000c5b0  movups  xmmword ptr [r14], xmm0
0x18000c5b4  lea     rax, ??_7ChannelConfigObject@@6B@; const ChannelConfigObject::`vftable'
0x18000c5bb  mov     [rcx], rax
0x18000c5be  mov     [rcx+30h], rdx
0x18000c5c2  test    rdx, rdx
0x18000c5c5  jz      short loc_18000C5CB
0x18000c5c7  lock inc dword ptr [rdx+8]
0x18000c5cb  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c5cf  inc     rax
0x18000c5d2  cmp     [r8+rax*2], r12w
0x18000c5d7  jnz     short loc_18000C5CF
0x18000c5d9  mov     [rbp+var_40], r8
0x18000c5dd  mov     [rbp+var_38], rax
0x18000c5e1  lea     rdx, [rbp+var_40]
0x18000c5e5  add     rcx, 38h ; '8'
0x18000c5e9  call    ?MakeOrThrowOOM@@YA?AV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@2@@Z; MakeOrThrowOOM(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18000c5ee  nop
0x18000c5ef  lea     rcx, [rdi+58h]
0x18000c5f3  call    ??0?$vector@UTmplInstInfo@BinXmlReader@@V?$allocator@UTmplInstInfo@BinXmlReader@@@utl@@@utl@@QEAA@XZ; utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(void)
0x18000c5f8  nop
0x18000c5f9  mov     [rdi+70h], r15d
0x18000c5fd  mov     [rdi+74h], r12b
0x18000c601  mov     [rsp+80h+var_50], r14
0x18000c606  mov     [rsp+80h+var_58], r15d
0x18000c60b  mov     rax, [rdi+38h]
0x18000c60f  mov     [rsp+80h+var_60], rax
0x18000c614  mov     r9, [rsi+48h]
0x18000c618  xor     r8d, r8d; pReturnValue
0x18000c61b  lea     edx, [r8+14h]; nProcNum
0x18000c61f  lea     rcx, pProxyInfo; pProxyInfo
0x18000c626  call    cs:__imp_NdrClientCall3
0x18000c62c  mov     rbx, rax
0x18000c62f  test    eax, eax
0x18000c631  jnz     short loc_18000C652
0x18000c633  mov     rax, rdi
0x18000c636  lea     r11, [rsp+80h+var_s0]
0x18000c63e  mov     rbx, [r11+38h]
0x18000c642  mov     rsi, [r11+40h]
0x18000c646  mov     rsp, r11
0x18000c649  pop     r15
0x18000c64b  pop     r14
0x18000c64d  pop     r12
0x18000c64f  pop     rdi
0x18000c650  pop     rbp
0x18000c651  retn
0x18000c652  lea     rax, WPP_GLOBAL_Control
0x18000c659  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c660  cmp     rcx, rax
0x18000c663  jz      short loc_18000C68C
0x18000c665  test    dword ptr [rcx+1Ch], 40000h
0x18000c66c  jz      short loc_18000C68C
0x18000c66e  cmp     byte ptr [rcx+19h], 2
0x18000c672  jb      short loc_18000C68C
0x18000c674  mov     edx, 0Ah
0x18000c679  mov     r9d, ebx
0x18000c67c  lea     r8, WPP_970b3d70c99a3bbc832a1e51198c3047_Traceguids
0x18000c683  mov     rcx, [rcx+10h]
0x18000c687  call    WPP_SF_D
0x18000c68c  lea     rax, word_18004024A
0x18000c693  mov     [rbp+pExceptionObject], rax
0x18000c697  mov     [rbp+var_28], r12
0x18000c69b  mov     [rbp+var_20], r12
0x18000c69f  mov     [rbp+var_18], ebx
0x18000c6a2  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x18000c6aa  mov     [rbp+var_C], r12b
0x18000c6ae  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18000c6b5  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000c6b9  call    _CxxThrowException_0
```
