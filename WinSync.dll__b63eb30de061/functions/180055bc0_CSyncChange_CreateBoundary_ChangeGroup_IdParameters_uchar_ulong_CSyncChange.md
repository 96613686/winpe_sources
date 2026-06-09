# CSyncChange_CreateBoundary(ChangeGroup *,IdParameters *,uchar *,ulong,CSyncChange * *)

- ea: `0x180055bc0`
- end: `0x180055ce5`
- name: `?CSyncChange_CreateBoundary@@YAJPEAVChangeGroup@@PEAVIdParameters@@PEAEKPEAPEAVCSyncChange@@@Z`
- size: `293`
- prototype: `__int64 __fastcall(struct ChangeGroup *, struct IdParameters *, unsigned __int8 *, unsigned int, struct CSyncChange **)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18004c3b0`
- `0x1800540a0`

## callees

- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x1800553ac`
- `0x180055bc0`
- `0x18005969c`
- `0x180094010`

## string_xrefs

- `0x180055bfe`: `CSyncChange_CreateBoundary`
- `0x180055cb8`: `CSyncChange_CreateBoundary`

## pseudocode

```c
__int64 __fastcall CSyncChange_CreateBoundary(
        struct ChangeGroup *a1,
        struct IdParameters *a2,
        unsigned __int8 *a3,
        unsigned int a4,
        struct CSyncChange **a5)
{
  PVOID *v9; // rcx
  int inited; // ebx
  CSyncChange *v11; // rax
  CSyncChange *v12; // rax
  struct IdParameters *v13; // r8
  struct CSyncChange *v14; // rdi

  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      95,
      WPP_898ee27924ee3465bbd2231b74e1faae_Traceguids,
      "CSyncChange_CreateBoundary");
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  inited = -2147467261;
  if ( a2 && a5 && a3 )
  {
    inited = -2147024882;
    v11 = (CSyncChange *)SeAlloc(0x110u);
    if ( v11 )
    {
      v12 = CSyncChange::CSyncChange(v11, a2);
      v14 = v12;
      if ( v12 )
      {
        inited = CSyncChange::Init_Boundary(v12, a1, v13, a3, a4);
        if ( inited >= 0 )
        {
          inited = 0;
          (*(void (__fastcall **)(struct CSyncChange *))(*(_QWORD *)v14 + 8LL))(v14);
          *a5 = v14;
        }
        (*(void (__fastcall **)(struct CSyncChange *))(*(_QWORD *)v14 + 16LL))(v14);
      }
    }
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x20) != 0 && *((_BYTE *)v9 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v9[2],
      96,
      (unsigned int)WPP_898ee27924ee3465bbd2231b74e1faae_Traceguids,
      (unsigned int)"CSyncChange_CreateBoundary",
      inited);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180055bc0  push    rbx
0x180055bc2  push    rbp
0x180055bc3  push    rsi
0x180055bc4  push    rdi
0x180055bc5  push    r12
0x180055bc7  push    r14
0x180055bc9  push    r15
0x180055bcb  sub     rsp, 30h
0x180055bcf  mov     r14d, r9d
0x180055bd2  mov     rbp, r8
0x180055bd5  mov     rdi, rdx
0x180055bd8  mov     r15, rcx
0x180055bdb  mov     rcx, cs:WPP_GLOBAL_Control
0x180055be2  lea     r12, WPP_GLOBAL_Control
0x180055be9  cmp     rcx, r12
0x180055bec  jz      short loc_180055C1D
0x180055bee  test    byte ptr [rcx+1Ch], 20h
0x180055bf2  jz      short loc_180055C1D
0x180055bf4  cmp     byte ptr [rcx+19h], 5
0x180055bf8  jb      short loc_180055C1D
0x180055bfa  mov     rcx, [rcx+10h]
0x180055bfe  lea     r9, aCsyncchangeCre_0; "CSyncChange_CreateBoundary"
0x180055c05  mov     edx, 5Fh ; '_'
0x180055c0a  lea     r8, WPP_898ee27924ee3465bbd2231b74e1faae_Traceguids
0x180055c11  call    WPP_SF_s
0x180055c16  mov     rcx, cs:WPP_GLOBAL_Control
0x180055c1d  mov     ebx, 80004003h
0x180055c22  test    rdi, rdi
0x180055c25  jz      short loc_180055CA3
0x180055c27  mov     rsi, [rsp+68h+arg_20]
0x180055c2f  test    rsi, rsi
0x180055c32  jz      short loc_180055CA3
0x180055c34  test    rbp, rbp
0x180055c37  jz      short loc_180055CA3
0x180055c39  mov     ecx, 110h; unsigned __int64
0x180055c3e  mov     ebx, 8007000Eh
0x180055c43  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x180055c48  test    rax, rax
0x180055c4b  jz      short loc_180055C9C
0x180055c4d  mov     rdx, rdi; struct IdParameters *
0x180055c50  mov     rcx, rax; this
0x180055c53  call    ??0CSyncChange@@QEAA@PEAVIdParameters@@@Z; CSyncChange::CSyncChange(IdParameters *)
0x180055c58  mov     rdi, rax
0x180055c5b  test    rax, rax
0x180055c5e  jz      short loc_180055C9C
0x180055c60  mov     r9, rbp; unsigned __int8 *
0x180055c63  mov     [rsp+68h+var_48], r14d; unsigned int
0x180055c68  mov     rdx, r15; struct ChangeGroup *
0x180055c6b  mov     rcx, rax; this
0x180055c6e  call    ?Init_Boundary@CSyncChange@@QEAAJPEAVChangeGroup@@PEAVIdParameters@@PEAEK@Z; CSyncChange::Init_Boundary(ChangeGroup *,IdParameters *,uchar *,ulong)
0x180055c73  mov     ebx, eax
0x180055c75  test    eax, eax
0x180055c77  js      short loc_180055C8D
0x180055c79  mov     rax, [rdi]
0x180055c7c  xor     ebx, ebx
0x180055c7e  mov     rcx, rdi
0x180055c81  mov     rax, [rax+8]
0x180055c85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055c8a  mov     [rsi], rdi
0x180055c8d  mov     rax, [rdi]
0x180055c90  mov     rcx, rdi
0x180055c93  mov     rax, [rax+10h]
0x180055c97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055c9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180055ca3  cmp     rcx, r12
0x180055ca6  jz      short loc_180055CD4
0x180055ca8  test    byte ptr [rcx+1Ch], 20h
0x180055cac  jz      short loc_180055CD4
0x180055cae  cmp     byte ptr [rcx+19h], 5
0x180055cb2  jb      short loc_180055CD4
0x180055cb4  mov     rcx, [rcx+10h]
0x180055cb8  lea     r9, aCsyncchangeCre_0; "CSyncChange_CreateBoundary"
0x180055cbf  mov     edx, 60h ; '`'
0x180055cc4  mov     [rsp+68h+var_48], ebx
0x180055cc8  lea     r8, WPP_898ee27924ee3465bbd2231b74e1faae_Traceguids
0x180055ccf  call    WPP_SF_sD
0x180055cd4  mov     eax, ebx
0x180055cd6  add     rsp, 30h
0x180055cda  pop     r15
0x180055cdc  pop     r14
0x180055cde  pop     r12
0x180055ce0  pop     rdi
0x180055ce1  pop     rsi
0x180055ce2  pop     rbp
0x180055ce3  pop     rbx
0x180055ce4  retn
```
