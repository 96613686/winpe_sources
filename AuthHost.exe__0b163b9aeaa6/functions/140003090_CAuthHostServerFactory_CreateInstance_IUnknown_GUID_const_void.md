# CAuthHostServerFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x140003090`
- end: `0x140003200`
- name: `?CreateInstance@CAuthHostServerFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `368`
- prototype: `__int64 __fastcall(CAuthHostServerFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140002c70`
- `0x14000300c`
- `0x140003090`
- `0x140003a44`
- `0x140012d10`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400031de`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400031de`

## pseudocode

```c
__int64 __fastcall CAuthHostServerFactory::CreateInstance(
        CAuthHostServerFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  CAuthHostServer *v8; // rcx
  unsigned int v9; // edi
  int v10; // eax
  _QWORD *v11; // rcx
  __int64 v12; // r8
  CAuthHostServer *v13; // [rsp+38h] [rbp+10h] BYREF

  *a4 = 0;
  if ( a2 )
    return 2147746064LL;
  if ( !_InterlockedExchange((volatile __int32 *)this + 6, 1) )
  {
    v13 = 0;
    Common::GlobalHeap::Alloc((ReservedForLocalUse *)0x30, (void **)&v13);
    v8 = v13;
    if ( v13 )
      v8 = CAuthHostServer::CAuthHostServer(v13);
    *((_QWORD *)this + 1) = v8;
    if ( v8 )
    {
      v10 = (**(__int64 (__fastcall ***)(CAuthHostServer *, const struct _GUID *, void **))v8)(v8, a3, a4);
      v11 = (_QWORD *)*((_QWORD *)this + 1);
      v9 = v10;
      if ( v10 >= 0 )
      {
        v11[3] = *((_QWORD *)this + 2);
        return v9;
      }
      (*(void (__fastcall **)(_QWORD *))(*v11 + 16LL))(v11);
      *((_QWORD *)this + 1) = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
      {
        WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 7), 13, v12, a3);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, &WPP_7c4350cd6e3a3fa521c812ffbe82d600_Traceguids);
      }
      v9 = -2147024882;
    }
    SetEvent(*((HANDLE *)this + 2));
    return v9;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, &WPP_7c4350cd6e3a3fa521c812ffbe82d600_Traceguids);
  }
  return 2147746294LL;
}

```

## disassembly

```asm
0x140003090  mov     [rsp+arg_0], rbx
0x140003095  mov     [rsp+arg_10], rsi
0x14000309a  push    rdi
0x14000309b  sub     rsp, 20h
0x14000309f  mov     qword ptr [r9], 0
0x1400030a6  mov     rdi, r9
0x1400030a9  mov     rsi, r8
0x1400030ac  mov     rbx, rcx
0x1400030af  test    rdx, rdx
0x1400030b2  jz      short loc_1400030BE
0x1400030b4  mov     eax, 80040110h
0x1400030b9  jmp     loc_1400031F0
0x1400030be  mov     eax, 1
0x1400030c3  xchg    eax, [rcx+18h]
0x1400030c6  test    eax, eax
0x1400030c8  jz      short loc_140003108
0x1400030ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400030d1  lea     rax, WPP_GLOBAL_Control
0x1400030d8  cmp     rcx, rax
0x1400030db  jz      short loc_1400030FE
0x1400030dd  test    byte ptr [rcx+44h], 10h
0x1400030e1  jz      short loc_1400030FE
0x1400030e3  cmp     byte ptr [rcx+41h], 2
0x1400030e7  jb      short loc_1400030FE
0x1400030e9  mov     rcx, [rcx+38h]
0x1400030ed  lea     r8, WPP_7c4350cd6e3a3fa521c812ffbe82d600_Traceguids
0x1400030f4  mov     edx, 0Bh
0x1400030f9  call    WPP_SF_
0x1400030fe  mov     eax, 800401F6h
0x140003103  jmp     loc_1400031F0
0x140003108  lea     rdx, [rsp+28h+arg_8]; void **
0x14000310d  mov     [rsp+28h+arg_8], 0
0x140003116  mov     ecx, 30h ; '0'; unsigned __int64
0x14000311b  call    ?Alloc@GlobalHeap@Common@@SAJ_KPEAPEAX@Z; Common::GlobalHeap::Alloc(unsigned __int64,void * *)
0x140003120  mov     rcx, [rsp+28h+arg_8]; this
0x140003125  mov     [rsp+28h+arg_8], rcx
0x14000312a  test    rcx, rcx
0x14000312d  jz      short loc_140003137
0x14000312f  call    ??0CAuthHostServer@@QEAA@XZ; CAuthHostServer::CAuthHostServer(void)
0x140003134  mov     rcx, rax
0x140003137  mov     [rbx+8], rcx
0x14000313b  test    rcx, rcx
0x14000313e  jnz     short loc_14000317B
0x140003140  mov     rcx, cs:WPP_GLOBAL_Control
0x140003147  lea     rax, WPP_GLOBAL_Control
0x14000314e  cmp     rcx, rax
0x140003151  jz      short loc_140003174
0x140003153  test    byte ptr [rcx+44h], 10h
0x140003157  jz      short loc_140003174
0x140003159  cmp     byte ptr [rcx+41h], 2
0x14000315d  jb      short loc_140003174
0x14000315f  mov     rcx, [rcx+38h]
0x140003163  lea     r8, WPP_7c4350cd6e3a3fa521c812ffbe82d600_Traceguids
0x14000316a  mov     edx, 0Ch
0x14000316f  call    WPP_SF_
0x140003174  mov     edi, 8007000Eh
0x140003179  jmp     short loc_1400031DA
0x14000317b  mov     rax, [rcx]
0x14000317e  mov     r8, rdi
0x140003181  mov     rdx, rsi
0x140003184  mov     rax, [rax]
0x140003187  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000318c  mov     rcx, [rbx+8]
0x140003190  mov     edi, eax
0x140003192  test    eax, eax
0x140003194  jns     short loc_1400031E6
0x140003196  mov     rdx, [rcx]
0x140003199  mov     rax, [rdx+10h]
0x14000319d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400031a2  mov     qword ptr [rbx+8], 0
0x1400031aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400031b1  lea     rax, WPP_GLOBAL_Control
0x1400031b8  cmp     rcx, rax
0x1400031bb  jz      short loc_1400031DA
0x1400031bd  test    byte ptr [rcx+44h], 10h
0x1400031c1  jz      short loc_1400031DA
0x1400031c3  cmp     byte ptr [rcx+41h], 2
0x1400031c7  jb      short loc_1400031DA
0x1400031c9  mov     rcx, [rcx+38h]
0x1400031cd  mov     edx, 0Dh
0x1400031d2  mov     r9, rsi
0x1400031d5  call    WPP_SF__guid_
0x1400031da  mov     rcx, [rbx+10h]; hEvent
0x1400031de  call    cs:__imp_SetEvent
0x1400031e4  jmp     short loc_1400031EE
0x1400031e6  mov     rax, [rbx+10h]
0x1400031ea  mov     [rcx+18h], rax
0x1400031ee  mov     eax, edi
0x1400031f0  mov     rbx, [rsp+28h+arg_0]
0x1400031f5  mov     rsi, [rsp+28h+arg_10]
0x1400031fa  add     rsp, 20h
0x1400031fe  pop     rdi
0x1400031ff  retn
```
