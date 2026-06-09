# CSyncChangeUnitWrapper_CreateInstance(IdParameters *,ISyncChangeUnit *,CSyncChangeWrapper *,int,CSyncChangeUnitWrapper * *)

- ea: `0x180071bc8`
- end: `0x180071d08`
- name: `?CSyncChangeUnitWrapper_CreateInstance@@YAJPEAVIdParameters@@PEAUISyncChangeUnit@@PEAVCSyncChangeWrapper@@HPEAPEAVCSyncChangeUnitWrapper@@@Z`
- size: `320`
- prototype: `__int64 __fastcall(struct IdParameters *, struct ISyncChangeUnit *, struct CSyncChangeWrapper *, int, struct CSyncChangeUnitWrapper **)`
- caller_count: `5`
- callee_count: `7`
- tags: ``

## callers

- `0x18003a294`
- `0x180043374`
- `0x18006659c`
- `0x1800678a0`
- `0x180071d10`

## callees

- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x18007198c`
- `0x180071bc8`
- `0x1800725bc`
- `0x180094010`

## string_xrefs

- `0x180071c06`: `CSyncChangeUnitWrapper_CreateInstance`
- `0x180071cdb`: `CSyncChangeUnitWrapper_CreateInstance`

## pseudocode

```c
__int64 __fastcall CSyncChangeUnitWrapper_CreateInstance(
        struct IdParameters *a1,
        struct ISyncChangeUnit *a2,
        struct CSyncChangeWrapper *a3,
        int a4,
        struct CSyncChangeUnitWrapper **a5)
{
  PVOID *v9; // rcx
  int v10; // ebx
  CSyncChangeUnitWrapper *v11; // rax
  CSyncChangeUnitWrapper *v12; // rax
  struct CSyncChangeUnitWrapper *v13; // rdi

  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      60,
      WPP_e2efb66d97a1346b7c1308d867b5aff5_Traceguids,
      "CSyncChangeUnitWrapper_CreateInstance");
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  v10 = -2147467261;
  if ( a1 && a2 && a5 )
  {
    v11 = (CSyncChangeUnitWrapper *)SeAlloc(0x78u);
    if ( v11 )
    {
      v12 = CSyncChangeUnitWrapper::CSyncChangeUnitWrapper(v11, a1);
      *a5 = 0;
      v13 = v12;
      v10 = -2147024882;
      if ( v12 )
      {
        v10 = CSyncChangeUnitWrapper::Init(v12, a2, a3, a4);
        if ( v10 >= 0 )
        {
          v10 = 0;
          (*(void (__fastcall **)(struct CSyncChangeUnitWrapper *))(*(_QWORD *)v13 + 8LL))(v13);
          *a5 = v13;
        }
        (*(void (__fastcall **)(struct CSyncChangeUnitWrapper *))(*(_QWORD *)v13 + 16LL))(v13);
      }
    }
    else
    {
      *a5 = 0;
      v10 = -2147024882;
    }
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 8) != 0 && *((_BYTE *)v9 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v9[2],
      61,
      (unsigned int)WPP_e2efb66d97a1346b7c1308d867b5aff5_Traceguids,
      (unsigned int)"CSyncChangeUnitWrapper_CreateInstance",
      v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180071bc8  push    rbx
0x180071bca  push    rbp
0x180071bcb  push    rsi
0x180071bcc  push    rdi
0x180071bcd  push    r12
0x180071bcf  push    r14
0x180071bd1  push    r15
0x180071bd3  sub     rsp, 30h
0x180071bd7  mov     r14d, r9d
0x180071bda  mov     r15, r8
0x180071bdd  mov     rbp, rdx
0x180071be0  mov     rdi, rcx
0x180071be3  mov     rcx, cs:WPP_GLOBAL_Control
0x180071bea  lea     r12, WPP_GLOBAL_Control
0x180071bf1  cmp     rcx, r12
0x180071bf4  jz      short loc_180071C25
0x180071bf6  test    byte ptr [rcx+1Ch], 8
0x180071bfa  jz      short loc_180071C25
0x180071bfc  cmp     byte ptr [rcx+19h], 5
0x180071c00  jb      short loc_180071C25
0x180071c02  mov     rcx, [rcx+10h]
0x180071c06  lea     r9, aCsyncchangeuni_21; "CSyncChangeUnitWrapper_CreateInstance"
0x180071c0d  mov     edx, 3Ch ; '<'
0x180071c12  lea     r8, WPP_e2efb66d97a1346b7c1308d867b5aff5_Traceguids
0x180071c19  call    WPP_SF_s
0x180071c1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180071c25  mov     ebx, 80004003h
0x180071c2a  test    rdi, rdi
0x180071c2d  jz      loc_180071CC6
0x180071c33  test    rbp, rbp
0x180071c36  jz      loc_180071CC6
0x180071c3c  mov     rsi, [rsp+68h+arg_20]
0x180071c44  test    rsi, rsi
0x180071c47  jz      short loc_180071CC6
0x180071c49  mov     ecx, 78h ; 'x'; unsigned __int64
0x180071c4e  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x180071c53  test    rax, rax
0x180071c56  jz      short loc_180071CB3
0x180071c58  mov     rdx, rdi; struct IdParameters *
0x180071c5b  mov     rcx, rax; this
0x180071c5e  call    ??0CSyncChangeUnitWrapper@@QEAA@PEAVIdParameters@@@Z; CSyncChangeUnitWrapper::CSyncChangeUnitWrapper(IdParameters *)
0x180071c63  mov     qword ptr [rsi], 0
0x180071c6a  mov     rdi, rax
0x180071c6d  mov     ebx, 8007000Eh
0x180071c72  test    rax, rax
0x180071c75  jz      short loc_180071CBF
0x180071c77  mov     r9d, r14d; int
0x180071c7a  mov     r8, r15; struct CSyncChangeWrapper *
0x180071c7d  mov     rdx, rbp; struct ISyncChangeUnit *
0x180071c80  mov     rcx, rax; this
0x180071c83  call    ?Init@CSyncChangeUnitWrapper@@QEAAJPEAUISyncChangeUnit@@PEAVCSyncChangeWrapper@@H@Z; CSyncChangeUnitWrapper::Init(ISyncChangeUnit *,CSyncChangeWrapper *,int)
0x180071c88  mov     ebx, eax
0x180071c8a  test    eax, eax
0x180071c8c  js      short loc_180071CA2
0x180071c8e  mov     rax, [rdi]
0x180071c91  xor     ebx, ebx
0x180071c93  mov     rcx, rdi
0x180071c96  mov     rax, [rax+8]
0x180071c9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071c9f  mov     [rsi], rdi
0x180071ca2  mov     rax, [rdi]
0x180071ca5  mov     rcx, rdi
0x180071ca8  mov     rax, [rax+10h]
0x180071cac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071cb1  jmp     short loc_180071CBF
0x180071cb3  mov     qword ptr [rsi], 0
0x180071cba  mov     ebx, 8007000Eh
0x180071cbf  mov     rcx, cs:WPP_GLOBAL_Control
0x180071cc6  cmp     rcx, r12
0x180071cc9  jz      short loc_180071CF7
0x180071ccb  test    byte ptr [rcx+1Ch], 8
0x180071ccf  jz      short loc_180071CF7
0x180071cd1  cmp     byte ptr [rcx+19h], 5
0x180071cd5  jb      short loc_180071CF7
0x180071cd7  mov     rcx, [rcx+10h]
0x180071cdb  lea     r9, aCsyncchangeuni_21; "CSyncChangeUnitWrapper_CreateInstance"
0x180071ce2  mov     edx, 3Dh ; '='
0x180071ce7  mov     [rsp+68h+var_48], ebx
0x180071ceb  lea     r8, WPP_e2efb66d97a1346b7c1308d867b5aff5_Traceguids
0x180071cf2  call    WPP_SF_sD
0x180071cf7  mov     eax, ebx
0x180071cf9  add     rsp, 30h
0x180071cfd  pop     r15
0x180071cff  pop     r14
0x180071d01  pop     r12
0x180071d03  pop     rdi
0x180071d04  pop     rsi
0x180071d05  pop     rbp
0x180071d06  pop     rbx
0x180071d07  retn
```
