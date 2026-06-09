# CSyncChange_CreateInstance(ChangeGroup *,IdParameters *,uchar const *,uchar const *,_SYNC_VERSION const *,_SYNC_VERSION const *,uchar const *,ulong,ulong,int,int,ISyncKnowledge *,IForgottenKnowledge *,ISyncKnowledge *,ISyncFilterInfo *,CSyncChange * *)

- ea: `0x180055cec`
- end: `0x180055ed0`
- name: `?CSyncChange_CreateInstance@@YAJPEAVChangeGroup@@PEAVIdParameters@@PEBE2PEBU_SYNC_VERSION@@32KKHHPEAUISyncKnowledge@@PEAUIForgottenKnowledge@@4PEAUISyncFilterInfo@@PEAPEAVCSyncChange@@@Z`
- size: `484`
- prototype: `__int64 __fastcall(struct ChangeGroup *, struct IdParameters *, const unsigned __int8 *, const unsigned __int8 *, const struct _SYNC_VERSION *, const struct _SYNC_VERSION *, unsigned __int8 *, unsigned int, unsigned int, int, int, struct ISyncKnowledge *, struct IForgottenKnowledge *, struct ISyncKnowledge *, struct ISyncFilterInfo *, struct CSyncChange **)`
- caller_count: `5`
- callee_count: `7`
- tags: ``

## callers

- `0x180028398`
- `0x18003c0d8`
- `0x18004c4c4`
- `0x18006d9c8`
- `0x18006e66c`

## callees

- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x1800553ac`
- `0x180055cec`
- `0x180059370`
- `0x180094010`

## string_xrefs

- `0x180055d2f`: `CSyncChange_CreateInstance`
- `0x180055e9e`: `CSyncChange_CreateInstance`

## pseudocode

```c
__int64 __fastcall CSyncChange_CreateInstance(
        struct ChangeGroup *a1,
        struct IdParameters *a2,
        const unsigned __int8 *a3,
        const unsigned __int8 *a4,
        const struct _SYNC_VERSION *a5,
        const struct _SYNC_VERSION *a6,
        unsigned __int8 *a7,
        unsigned int a8,
        unsigned int a9,
        int a10,
        int a11,
        struct ISyncKnowledge *a12,
        struct IForgottenKnowledge *a13,
        struct ISyncKnowledge *a14,
        struct ISyncFilterInfo *a15,
        struct CSyncChange **a16)
{
  PVOID *v20; // rcx
  int v21; // edi
  CSyncChange *v22; // rax
  CSyncChange *v23; // rax
  struct CSyncChange *v24; // rbx

  v20 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      93,
      WPP_898ee27924ee3465bbd2231b74e1faae_Traceguids,
      "CSyncChange_CreateInstance");
    v20 = (PVOID *)WPP_GLOBAL_Control;
  }
  v21 = -2147467261;
  if ( a2 && a16 && a5 && a6 )
  {
    *a16 = 0;
    v21 = -2147024882;
    v22 = (CSyncChange *)SeAlloc(0x110u);
    if ( v22 )
    {
      v23 = CSyncChange::CSyncChange(v22, a2);
      v24 = v23;
      if ( v23 )
      {
        v21 = CSyncChange::Init(v23, a3, a4, a5, a5, a6, a7, a8, a9, a10, a11, a1, a12, a13, a14, a15);
        if ( v21 >= 0 )
        {
          v21 = 0;
          (*(void (__fastcall **)(struct CSyncChange *))(*(_QWORD *)v24 + 8LL))(v24);
          *a16 = v24;
        }
        (*(void (__fastcall **)(struct CSyncChange *))(*(_QWORD *)v24 + 16LL))(v24);
      }
    }
    v20 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 0x20) != 0 && *((_BYTE *)v20 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v20[2],
      94,
      (unsigned int)WPP_898ee27924ee3465bbd2231b74e1faae_Traceguids,
      (unsigned int)"CSyncChange_CreateInstance",
      v21);
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x180055cec  push    rbx
0x180055cee  push    rbp
0x180055cef  push    rsi
0x180055cf0  push    rdi
0x180055cf1  push    r12
0x180055cf3  push    r13
0x180055cf5  push    r14
0x180055cf7  push    r15
0x180055cf9  sub     rsp, 88h
0x180055d00  mov     r15, r9
0x180055d03  mov     r12, r8
0x180055d06  mov     rbx, rdx
0x180055d09  mov     r13, rcx
0x180055d0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180055d13  lea     rax, WPP_GLOBAL_Control
0x180055d1a  cmp     rcx, rax
0x180055d1d  jz      short loc_180055D4E
0x180055d1f  test    byte ptr [rcx+1Ch], 20h
0x180055d23  jz      short loc_180055D4E
0x180055d25  cmp     byte ptr [rcx+19h], 5
0x180055d29  jb      short loc_180055D4E
0x180055d2b  mov     rcx, [rcx+10h]
0x180055d2f  lea     r9, aCsyncchangeCre; "CSyncChange_CreateInstance"
0x180055d36  mov     edx, 5Dh ; ']'
0x180055d3b  lea     r8, WPP_898ee27924ee3465bbd2231b74e1faae_Traceguids
0x180055d42  call    WPP_SF_s
0x180055d47  mov     rcx, cs:WPP_GLOBAL_Control
0x180055d4e  mov     edi, 80004003h
0x180055d53  test    rbx, rbx
0x180055d56  jz      loc_180055E82
0x180055d5c  mov     rsi, [rsp+0C8h+arg_78]
0x180055d64  test    rsi, rsi
0x180055d67  jz      loc_180055E82
0x180055d6d  mov     rbp, [rsp+0C8h+arg_20]
0x180055d75  test    rbp, rbp
0x180055d78  jz      loc_180055E82
0x180055d7e  mov     r14, [rsp+0C8h+arg_28]
0x180055d86  test    r14, r14
0x180055d89  jz      loc_180055E82
0x180055d8f  mov     ecx, 110h; unsigned __int64
0x180055d94  mov     qword ptr [rsi], 0
0x180055d9b  mov     edi, 8007000Eh
0x180055da0  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x180055da5  test    rax, rax
0x180055da8  jz      loc_180055E7B
0x180055dae  mov     rdx, rbx; struct IdParameters *
0x180055db1  mov     rcx, rax; this
0x180055db4  call    ??0CSyncChange@@QEAA@PEAVIdParameters@@@Z; CSyncChange::CSyncChange(IdParameters *)
0x180055db9  mov     rbx, rax
0x180055dbc  test    rax, rax
0x180055dbf  jz      loc_180055E7B
0x180055dc5  mov     rax, [rsp+0C8h+arg_70]
0x180055dcd  mov     r9, rbp; struct _SYNC_VERSION *
0x180055dd0  mov     [rsp+0C8h+var_50], rax; struct ISyncFilterInfo *
0x180055dd5  mov     r8, r15; unsigned __int8 *
0x180055dd8  mov     rax, [rsp+0C8h+arg_68]
0x180055de0  mov     rdx, r12; unsigned __int8 *
0x180055de3  mov     [rsp+0C8h+var_58], rax; struct ISyncKnowledge *
0x180055de8  mov     rcx, rbx; this
0x180055deb  mov     rax, [rsp+0C8h+arg_60]
0x180055df3  mov     [rsp+0C8h+var_60], rax; struct IForgottenKnowledge *
0x180055df8  mov     rax, [rsp+0C8h+arg_58]
0x180055e00  mov     [rsp+0C8h+var_68], rax; struct ISyncKnowledge *
0x180055e05  mov     eax, [rsp+0C8h+arg_50]
0x180055e0c  mov     [rsp+0C8h+var_70], r13; struct ChangeGroup *
0x180055e11  mov     [rsp+0C8h+var_78], eax; int
0x180055e15  mov     eax, [rsp+0C8h+arg_48]
0x180055e1c  mov     [rsp+0C8h+var_80], eax; int
0x180055e20  mov     eax, [rsp+0C8h+arg_40]
0x180055e27  mov     [rsp+0C8h+var_88], eax; unsigned int
0x180055e2b  mov     eax, [rsp+0C8h+arg_38]
0x180055e32  mov     [rsp+0C8h+var_90], eax; unsigned int
0x180055e36  mov     rax, [rsp+0C8h+arg_30]
0x180055e3e  mov     [rsp+0C8h+var_98], rax; unsigned __int8 *
0x180055e43  mov     [rsp+0C8h+var_A0], r14; struct _SYNC_VERSION *
0x180055e48  mov     [rsp+0C8h+var_A8], rbp; struct _SYNC_VERSION *
0x180055e4d  call    ?Init@CSyncChange@@QEAAJPEBE0PEBU_SYNC_VERSION@@110KKHHPEAVChangeGroup@@PEAUISyncKnowledge@@PEAUIForgottenKnowledge@@3PEAUISyncFilterInfo@@@Z; CSyncChange::Init(uchar const *,uchar const *,_SYNC_VERSION const *,_SYNC_VERSION const *,_SYNC_VERSION const *,uchar const *,ulong,ulong,int,int,ChangeGroup *,ISyncKnowledge *,IForgottenKnowledge *,ISyncKnowledge *,ISyncFilterInfo *)
0x180055e52  mov     edi, eax
0x180055e54  test    eax, eax
0x180055e56  js      short loc_180055E6C
0x180055e58  mov     rax, [rbx]
0x180055e5b  xor     edi, edi
0x180055e5d  mov     rcx, rbx
0x180055e60  mov     rax, [rax+8]
0x180055e64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055e69  mov     [rsi], rbx
0x180055e6c  mov     rax, [rbx]
0x180055e6f  mov     rcx, rbx
0x180055e72  mov     rax, [rax+10h]
0x180055e76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055e7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180055e82  lea     rax, WPP_GLOBAL_Control
0x180055e89  cmp     rcx, rax
0x180055e8c  jz      short loc_180055EBA
0x180055e8e  test    byte ptr [rcx+1Ch], 20h
0x180055e92  jz      short loc_180055EBA
0x180055e94  cmp     byte ptr [rcx+19h], 5
0x180055e98  jb      short loc_180055EBA
0x180055e9a  mov     rcx, [rcx+10h]
0x180055e9e  lea     r9, aCsyncchangeCre; "CSyncChange_CreateInstance"
0x180055ea5  mov     edx, 5Eh ; '^'
0x180055eaa  mov     dword ptr [rsp+0C8h+var_A8], edi
0x180055eae  lea     r8, WPP_898ee27924ee3465bbd2231b74e1faae_Traceguids
0x180055eb5  call    WPP_SF_sD
0x180055eba  mov     eax, edi
0x180055ebc  add     rsp, 88h
0x180055ec3  pop     r15
0x180055ec5  pop     r14
0x180055ec7  pop     r13
0x180055ec9  pop     r12
0x180055ecb  pop     rdi
0x180055ecc  pop     rsi
0x180055ecd  pop     rbp
0x180055ece  pop     rbx
0x180055ecf  retn
```
