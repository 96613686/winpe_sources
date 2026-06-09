# CSyncSession_CreateInstance(IdParameters *,ISyncProvider *,ISyncProvider *,_GUID const &,void * *)

- ea: `0x18002dcac`
- end: `0x18002ddb7`
- name: `?CSyncSession_CreateInstance@@YAJPEAVIdParameters@@PEAUISyncProvider@@1AEBU_GUID@@PEAPEAX@Z`
- size: `267`
- prototype: `__int64 __fastcall(struct IdParameters *, struct ISyncProvider *, struct ISyncProvider *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18002c600`

## callees

- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x18002d3e8`
- `0x18002dcac`
- `0x18002f664`
- `0x180094010`

## string_xrefs

- `0x18002dce5`: `CSyncSession_CreateInstance`
- `0x18002dd8c`: `CSyncSession_CreateInstance`

## pseudocode

```c
__int64 __fastcall CSyncSession_CreateInstance(
        struct IdParameters *a1,
        struct ISyncProvider *a2,
        struct ISyncProvider *a3,
        const struct _GUID *a4,
        void **a5)
{
  int v8; // ebx
  CSyncSession *v9; // rax
  CSyncSession *v10; // rax
  CSyncSession *v11; // rdi

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      87,
      WPP_24b986413345305da18a80c41c45e189_Traceguids,
      "CSyncSession_CreateInstance");
  }
  v8 = -2147024882;
  *a5 = 0;
  v9 = (CSyncSession *)SeAlloc(0xC8u);
  if ( v9 )
  {
    v10 = CSyncSession::CSyncSession(v9, a1);
    v11 = v10;
    if ( v10 )
    {
      v8 = CSyncSession::Init(v10, a2, a3);
      if ( v8 >= 0 )
        v8 = (**(__int64 (__fastcall ***)(CSyncSession *, GUID *, void **))v11)(
               v11,
               &GUID_e1456ec0_914e_4f84_95b0_ce8576dfc515,
               a5);
      (*(void (__fastcall **)(CSyncSession *))(*(_QWORD *)v11 + 16LL))(v11);
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      88,
      (unsigned int)WPP_24b986413345305da18a80c41c45e189_Traceguids,
      (unsigned int)"CSyncSession_CreateInstance",
      v8);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002dcac  push    rbx
0x18002dcae  push    rbp
0x18002dcaf  push    rsi
0x18002dcb0  push    rdi
0x18002dcb1  push    r14
0x18002dcb3  push    r15
0x18002dcb5  sub     rsp, 38h
0x18002dcb9  mov     rbp, r8
0x18002dcbc  mov     r14, rdx
0x18002dcbf  mov     rdi, rcx
0x18002dcc2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dcc9  lea     r15, WPP_GLOBAL_Control
0x18002dcd0  cmp     rcx, r15
0x18002dcd3  jz      short loc_18002DCFD
0x18002dcd5  test    byte ptr [rcx+1Ch], 4
0x18002dcd9  jz      short loc_18002DCFD
0x18002dcdb  cmp     byte ptr [rcx+19h], 5
0x18002dcdf  jb      short loc_18002DCFD
0x18002dce1  mov     rcx, [rcx+10h]
0x18002dce5  lea     r9, aCsyncsessionCr; "CSyncSession_CreateInstance"
0x18002dcec  mov     edx, 57h ; 'W'
0x18002dcf1  lea     r8, WPP_24b986413345305da18a80c41c45e189_Traceguids
0x18002dcf8  call    WPP_SF_s
0x18002dcfd  mov     rsi, [rsp+68h+arg_20]
0x18002dd05  mov     ecx, 0C8h; unsigned __int64
0x18002dd0a  mov     ebx, 8007000Eh
0x18002dd0f  mov     qword ptr [rsi], 0
0x18002dd16  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x18002dd1b  test    rax, rax
0x18002dd1e  jz      short loc_18002DD70
0x18002dd20  mov     rdx, rdi; struct IdParameters *
0x18002dd23  mov     rcx, rax; this
0x18002dd26  call    ??0CSyncSession@@QEAA@PEAVIdParameters@@@Z; CSyncSession::CSyncSession(IdParameters *)
0x18002dd2b  mov     rdi, rax
0x18002dd2e  test    rax, rax
0x18002dd31  jz      short loc_18002DD70
0x18002dd33  mov     r8, rbp; struct ISyncProvider *
0x18002dd36  mov     rdx, r14; struct ISyncProvider *
0x18002dd39  mov     rcx, rax; this
0x18002dd3c  call    ?Init@CSyncSession@@QEAAJPEAUISyncProvider@@0@Z; CSyncSession::Init(ISyncProvider *,ISyncProvider *)
0x18002dd41  mov     ebx, eax
0x18002dd43  test    eax, eax
0x18002dd45  js      short loc_18002DD61
0x18002dd47  mov     rax, [rdi]
0x18002dd4a  lea     rdx, _GUID_e1456ec0_914e_4f84_95b0_ce8576dfc515
0x18002dd51  mov     r8, rsi
0x18002dd54  mov     rcx, rdi
0x18002dd57  mov     rax, [rax]
0x18002dd5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dd5f  mov     ebx, eax
0x18002dd61  mov     rax, [rdi]
0x18002dd64  mov     rcx, rdi
0x18002dd67  mov     rax, [rax+10h]
0x18002dd6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dd70  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dd77  cmp     rcx, r15
0x18002dd7a  jz      short loc_18002DDA8
0x18002dd7c  test    byte ptr [rcx+1Ch], 4
0x18002dd80  jz      short loc_18002DDA8
0x18002dd82  cmp     byte ptr [rcx+19h], 5
0x18002dd86  jb      short loc_18002DDA8
0x18002dd88  mov     rcx, [rcx+10h]
0x18002dd8c  lea     r9, aCsyncsessionCr; "CSyncSession_CreateInstance"
0x18002dd93  mov     edx, 58h ; 'X'
0x18002dd98  mov     [rsp+68h+var_48], ebx
0x18002dd9c  lea     r8, WPP_24b986413345305da18a80c41c45e189_Traceguids
0x18002dda3  call    WPP_SF_sD
0x18002dda8  mov     eax, ebx
0x18002ddaa  add     rsp, 38h
0x18002ddae  pop     r15
0x18002ddb0  pop     r14
0x18002ddb2  pop     rdi
0x18002ddb3  pop     rsi
0x18002ddb4  pop     rbp
0x18002ddb5  pop     rbx
0x18002ddb6  retn
```
