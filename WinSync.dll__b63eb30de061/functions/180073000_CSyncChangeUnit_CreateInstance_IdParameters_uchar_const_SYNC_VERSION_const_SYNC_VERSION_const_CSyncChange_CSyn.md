# CSyncChangeUnit_CreateInstance(IdParameters *,uchar const *,_SYNC_VERSION const *,_SYNC_VERSION const *,CSyncChange *,CSyncChangeUnit * *)

- ea: `0x180073000`
- end: `0x1800731b4`
- name: `?CSyncChangeUnit_CreateInstance@@YAJPEAVIdParameters@@PEBEPEBU_SYNC_VERSION@@2PEAVCSyncChange@@PEAPEAVCSyncChangeUnit@@@Z`
- size: `436`
- prototype: `__int64 __fastcall(struct IdParameters *, const unsigned __int8 *, const struct _SYNC_VERSION *, const struct _SYNC_VERSION *, struct CSyncChange *, struct CSyncChangeUnit **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18005555c`

## callees

- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x180073000`
- `0x180073500`
- `0x180094010`

## string_xrefs

- `0x18007303e`: `CSyncChangeUnit_CreateInstance`
- `0x180073187`: `CSyncChangeUnit_CreateInstance`

## pseudocode

```c
__int64 __fastcall CSyncChangeUnit_CreateInstance(
        struct IdParameters *a1,
        const unsigned __int8 *a2,
        const struct _SYNC_VERSION *a3,
        const struct _SYNC_VERSION *a4,
        struct CSyncChange *a5,
        struct CSyncChangeUnit **a6)
{
  PVOID *v10; // rcx
  int v11; // edi
  _QWORD *v12; // rbx

  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      25,
      WPP_d0fec225714f3fab65a0ae3a2a7d44d3_Traceguids,
      "CSyncChangeUnit_CreateInstance");
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  v11 = -2147467261;
  if ( a1 && a6 )
  {
    v12 = SeAlloc(0x48u);
    if ( v12 )
    {
      v12[2] = 0;
      *v12 = &CSyncChangeUnit::`vftable';
      *((_DWORD *)v12 + 2) = 1;
      v12[7] = 0;
      v12[8] = a1;
      _InterlockedIncrement(&g_cRefThisDll);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          WPP_d0fec225714f3fab65a0ae3a2a7d44d3_Traceguids,
          "CSyncChangeUnit::CSyncChangeUnit");
      }
      _InterlockedIncrement((volatile signed __int32 *)(v12[8] + 48LL));
      *a6 = 0;
      v11 = CSyncChangeUnit::Init((CSyncChangeUnit *)v12, a2, a3, a4, a5);
      if ( v11 >= 0 )
      {
        v11 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v12 + 8LL))(v12);
        *a6 = (struct CSyncChangeUnit *)v12;
      }
      (*(void (__fastcall **)(_QWORD *))(*v12 + 16LL))(v12);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    else
    {
      v10 = (PVOID *)WPP_GLOBAL_Control;
      v11 = -2147024882;
      *a6 = 0;
    }
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x20) != 0 && *((_BYTE *)v10 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v10[2],
      26,
      (unsigned int)WPP_d0fec225714f3fab65a0ae3a2a7d44d3_Traceguids,
      (unsigned int)"CSyncChangeUnit_CreateInstance",
      v11);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180073000  push    rbx
0x180073002  push    rbp
0x180073003  push    rsi
0x180073004  push    rdi
0x180073005  push    r12
0x180073007  push    r14
0x180073009  push    r15
0x18007300b  sub     rsp, 30h
0x18007300f  mov     r14, r9
0x180073012  mov     r15, r8
0x180073015  mov     r12, rdx
0x180073018  mov     rbp, rcx
0x18007301b  mov     rcx, cs:WPP_GLOBAL_Control
0x180073022  lea     rax, WPP_GLOBAL_Control
0x180073029  cmp     rcx, rax
0x18007302c  jz      short loc_18007305D
0x18007302e  test    byte ptr [rcx+1Ch], 20h
0x180073032  jz      short loc_18007305D
0x180073034  cmp     byte ptr [rcx+19h], 5
0x180073038  jb      short loc_18007305D
0x18007303a  mov     rcx, [rcx+10h]
0x18007303e  lea     r9, aCsyncchangeuni_30; "CSyncChangeUnit_CreateInstance"
0x180073045  mov     edx, 19h
0x18007304a  lea     r8, WPP_d0fec225714f3fab65a0ae3a2a7d44d3_Traceguids
0x180073051  call    WPP_SF_s
0x180073056  mov     rcx, cs:WPP_GLOBAL_Control
0x18007305d  mov     edi, 80004003h
0x180073062  test    rbp, rbp
0x180073065  jz      loc_18007316B
0x18007306b  mov     rsi, [rsp+68h+arg_28]
0x180073073  test    rsi, rsi
0x180073076  jz      loc_18007316B
0x18007307c  mov     ecx, 48h ; 'H'; unsigned __int64
0x180073081  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x180073086  mov     rbx, rax
0x180073089  test    rax, rax
0x18007308c  jz      loc_180073158
0x180073092  lea     rax, ??_7CSyncChangeUnit@@6B@; const CSyncChangeUnit::`vftable'
0x180073099  mov     qword ptr [rbx+10h], 0
0x1800730a1  mov     [rbx], rax
0x1800730a4  mov     dword ptr [rbx+8], 1
0x1800730ab  mov     qword ptr [rbx+38h], 0
0x1800730b3  mov     [rbx+40h], rbp
0x1800730b7  lock inc cs:?g_cRefThisDll@@3JC; long volatile g_cRefThisDll
0x1800730be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800730c5  lea     rbp, WPP_GLOBAL_Control
0x1800730cc  cmp     rcx, rbp
0x1800730cf  jz      short loc_1800730F9
0x1800730d1  test    byte ptr [rcx+1Ch], 20h
0x1800730d5  jz      short loc_1800730F9
0x1800730d7  cmp     byte ptr [rcx+19h], 5
0x1800730db  jb      short loc_1800730F9
0x1800730dd  mov     rcx, [rcx+10h]
0x1800730e1  lea     r9, aCsyncchangeuni_28; "CSyncChangeUnit::CSyncChangeUnit"
0x1800730e8  mov     edx, 0Ah
0x1800730ed  lea     r8, WPP_d0fec225714f3fab65a0ae3a2a7d44d3_Traceguids
0x1800730f4  call    WPP_SF_s
0x1800730f9  mov     rax, [rbx+40h]
0x1800730fd  lock inc dword ptr [rax+30h]
0x180073101  mov     rax, [rsp+68h+arg_20]
0x180073109  mov     r9, r14; struct _SYNC_VERSION *
0x18007310c  mov     r8, r15; struct _SYNC_VERSION *
0x18007310f  mov     [rsp+68h+var_48], rax; struct CSyncChange *
0x180073114  mov     rdx, r12; unsigned __int8 *
0x180073117  mov     qword ptr [rsi], 0
0x18007311e  mov     rcx, rbx; this
0x180073121  call    ?Init@CSyncChangeUnit@@QEAAJPEBEPEBU_SYNC_VERSION@@1PEAVCSyncChange@@@Z; CSyncChangeUnit::Init(uchar const *,_SYNC_VERSION const *,_SYNC_VERSION const *,CSyncChange *)
0x180073126  mov     edi, eax
0x180073128  test    eax, eax
0x18007312a  js      short loc_180073140
0x18007312c  mov     rax, [rbx]
0x18007312f  xor     edi, edi
0x180073131  mov     rcx, rbx
0x180073134  mov     rax, [rax+8]
0x180073138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007313d  mov     [rsi], rbx
0x180073140  mov     rax, [rbx]
0x180073143  mov     rcx, rbx
0x180073146  mov     rax, [rax+10h]
0x18007314a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007314f  mov     rcx, cs:WPP_GLOBAL_Control
0x180073156  jmp     short loc_180073172
0x180073158  mov     rcx, cs:WPP_GLOBAL_Control
0x18007315f  mov     edi, 8007000Eh
0x180073164  mov     qword ptr [rsi], 0
0x18007316b  lea     rbp, WPP_GLOBAL_Control
0x180073172  cmp     rcx, rbp
0x180073175  jz      short loc_1800731A3
0x180073177  test    byte ptr [rcx+1Ch], 20h
0x18007317b  jz      short loc_1800731A3
0x18007317d  cmp     byte ptr [rcx+19h], 5
0x180073181  jb      short loc_1800731A3
0x180073183  mov     rcx, [rcx+10h]
0x180073187  lea     r9, aCsyncchangeuni_30; "CSyncChangeUnit_CreateInstance"
0x18007318e  mov     edx, 1Ah
0x180073193  mov     dword ptr [rsp+68h+var_48], edi
0x180073197  lea     r8, WPP_d0fec225714f3fab65a0ae3a2a7d44d3_Traceguids
0x18007319e  call    WPP_SF_sD
0x1800731a3  mov     eax, edi
0x1800731a5  add     rsp, 30h
0x1800731a9  pop     r15
0x1800731ab  pop     r14
0x1800731ad  pop     r12
0x1800731af  pop     rdi
0x1800731b0  pop     rsi
0x1800731b1  pop     rbp
0x1800731b2  pop     rbx
0x1800731b3  retn
```
