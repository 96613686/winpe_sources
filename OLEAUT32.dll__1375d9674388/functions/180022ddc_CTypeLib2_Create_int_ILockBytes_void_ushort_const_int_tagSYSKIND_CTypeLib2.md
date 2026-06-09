# CTypeLib2::Create(int,ILockBytes *,void *,ushort const *,int,tagSYSKIND,CTypeLib2 * *)

- ea: `0x180022ddc`
- end: `0x18002301b`
- name: `?Create@CTypeLib2@@SAJHPEAUILockBytes@@PEAXPEBGHW4tagSYSKIND@@PEAPEAV1@@Z`
- size: `575`
- prototype: `static int(int, struct ILockBytes *, void *, const unsigned __int16 *, int, enum tagSYSKIND, struct CTypeLib2 **)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x1800234fc`
- `0x180043680`

## callees

- `0x180001a70`
- `0x1800024f4`
- `0x18000a830`
- `0x18000f900`
- `0x180010100`
- `0x180022ddc`
- `0x180023024`
- `0x180023250`
- `0x1800233ec`
- `0x1800238a8`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022f9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022f9b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180022edb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180022edb`

## pseudocode

```c
__int64 __fastcall CTypeLib2::Create(
        int a1,
        struct ILockBytes *a2,
        void *a3,
        const unsigned __int16 *a4,
        int a5,
        enum tagSYSKIND a6,
        struct CTypeLib2 **a7)
{
  unsigned __int64 v7; // rax
  CTypeLib2 *v13; // rax
  CTypeLib2 *v14; // rax
  CTypeLib2 *v15; // rbx
  int v16; // eax
  unsigned int v17; // edx
  signed int inited; // edi
  _WORD *v19; // rdi
  const unsigned __int16 *v20; // rax
  signed int LastError; // eax

  v7 = -1;
  do
    ++v7;
  while ( a4[v7] );
  if ( v7 >= 0x104 )
    return 2147942487LL;
  v13 = (CTypeLib2 *)MemAlloc(688);
  if ( !v13 )
    return 2147942414LL;
  v14 = CTypeLib2::CTypeLib2(v13);
  v15 = v14;
  if ( !v14 )
    return 2147942414LL;
  *((_DWORD *)v14 + 124) = 1;
  if ( a2 )
    ((void (__fastcall *)(struct ILockBytes *))a2->lpVtbl->AddRef)(a2);
  *((_QWORD *)v15 + 65) = 0;
  *((_QWORD *)v15 + 64) = a3;
  *((_QWORD *)v15 + 60) = a2;
  *((_QWORD *)v15 + 63) = 0;
  *((_DWORD *)v15 + 122) = -1;
  *((_DWORD *)v15 + 123) = -1;
  *((_QWORD *)v15 + 59) = 0;
  *((_QWORD *)v15 + 70) = 0;
  *((_QWORD *)v15 + 67) = 0;
  *((_DWORD *)v15 + 104) = 0;
  *((_QWORD *)v15 + 68) = 0;
  *((_QWORD *)v15 + 69) = 0;
  *((_QWORD *)v15 + 73) = 0;
  *((_QWORD *)v15 + 74) = 0;
  *((_QWORD *)v15 + 75) = 0;
  if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)v15 + 608), 0) )
    goto LABEL_10;
  LastError = GetLastError();
  inited = LastError;
  if ( LastError > 0 )
    inited = (unsigned __int16)LastError | 0x80070000;
  *((_OWORD *)v15 + 38) = 0;
  *((_OWORD *)v15 + 39) = 0;
  *((_QWORD *)v15 + 80) = 0;
  if ( inited >= 0 )
  {
LABEL_10:
    v16 = *((_DWORD *)v15 + 132);
    if ( a1 )
    {
      *((_DWORD *)v15 + 132) = v16 & 0xFFFFFFFE;
      inited = CTypeLib2::InitNew(v15, a6);
      if ( inited < 0 )
        goto LABEL_21;
      v19 = (_WORD *)((char *)v15 + 404);
    }
    else
    {
      *((_DWORD *)v15 + 132) = v16 | 1;
      inited = CTypeLib2::ReadExisting(v15, a6);
      if ( inited < 0 )
        goto LABEL_21;
      CTypeLib2::CheckForBad64BitLayout(v15, a6);
      v19 = (_WORD *)((char *)v15 + 404);
      if ( (*((_WORD *)v15 + 202) & 3) != *((_DWORD *)v15 + 169) )
        CTypeLib2::MarkAllForReLayout(v15);
    }
    v20 = SysAllocString(a4);
    *((_QWORD *)v15 + 65) = v20;
    v17 = (unsigned int)v20;
    if ( v20 )
    {
      *v19 ^= (*v19 ^ (8 * a5)) & 8;
      if ( !a1 || (inited = OLE_TYPEMGR::TypeLibLoaded(g_poletmgr, v20, a5, (struct ITypeLib *)v15, a6), inited >= 0) )
      {
        *a7 = v15;
        return 0;
      }
    }
    else
    {
      inited = -2147024882;
    }
  }
LABEL_21:
  CTypeLib2::`scalar deleting destructor'(v15, v17);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180022ddc  push    rbx
0x180022dde  push    rbp
0x180022ddf  push    rsi
0x180022de0  push    rdi
0x180022de1  push    r14
0x180022de3  push    r15
0x180022de5  sub     rsp, 38h
0x180022de9  or      rax, 0FFFFFFFFFFFFFFFFh
0x180022ded  mov     rbp, r9
0x180022df0  xor     r15d, r15d
0x180022df3  mov     rsi, r8
0x180022df6  mov     rdi, rdx
0x180022df9  mov     r14d, ecx
0x180022dfc  inc     rax
0x180022dff  cmp     [r9+rax*2], r15w
0x180022e04  jnz     short loc_180022DFC
0x180022e06  cmp     rax, 104h
0x180022e0c  jb      short loc_180022E20
0x180022e0e  mov     eax, 80070057h
0x180022e13  add     rsp, 38h
0x180022e17  pop     r15
0x180022e19  pop     r14
0x180022e1b  pop     rdi
0x180022e1c  pop     rsi
0x180022e1d  pop     rbp
0x180022e1e  pop     rbx
0x180022e1f  retn
0x180022e20  mov     ecx, 2B0h
0x180022e25  call    MemAlloc
0x180022e2a  test    rax, rax
0x180022e2d  jz      loc_180022F87
0x180022e33  mov     rcx, rax; this
0x180022e36  call    ??0CTypeLib2@@QEAA@XZ; CTypeLib2::CTypeLib2(void)
0x180022e3b  mov     rbx, rax
0x180022e3e  test    rax, rax
0x180022e41  jz      loc_180022F87
0x180022e47  mov     dword ptr [rax+1F0h], 1
0x180022e51  test    rdi, rdi
0x180022e54  jz      short loc_180022E65
0x180022e56  mov     rcx, [rdi]
0x180022e59  mov     rax, [rcx+8]
0x180022e5d  mov     rcx, rdi
0x180022e60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e65  or      eax, 0FFFFFFFFh
0x180022e68  mov     [rbx+208h], r15
0x180022e6f  mov     [rbx+200h], rsi
0x180022e76  xor     edx, edx; dwSpinCount
0x180022e78  lea     rsi, [rbx+260h]
0x180022e7f  mov     [rbx+1E0h], rdi
0x180022e86  mov     rcx, rsi; lpCriticalSection
0x180022e89  mov     [rbx+1F8h], r15
0x180022e90  mov     [rbx+1E8h], eax
0x180022e96  mov     [rbx+1ECh], eax
0x180022e9c  mov     [rbx+1D8h], r15
0x180022ea3  mov     [rbx+230h], r15
0x180022eaa  mov     [rbx+218h], r15
0x180022eb1  mov     [rbx+1A0h], r15d
0x180022eb8  mov     [rbx+220h], r15
0x180022ebf  mov     [rbx+228h], r15
0x180022ec6  mov     [rbx+248h], r15
0x180022ecd  mov     [rbx+250h], r15
0x180022ed4  mov     [rbx+258h], r15
0x180022edb  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180022ee1  test    eax, eax
0x180022ee3  jz      loc_180022F9B
0x180022ee9  mov     esi, [rsp+68h+arg_28]
0x180022ef0  mov     edx, esi; enum tagSYSKIND
0x180022ef2  mov     eax, [rbx+210h]
0x180022ef8  mov     rcx, rbx; this
0x180022efb  test    r14d, r14d
0x180022efe  jnz     loc_180022FF4
0x180022f04  or      eax, 1
0x180022f07  mov     [rbx+210h], eax
0x180022f0d  call    ?ReadExisting@CTypeLib2@@QEAAJW4tagSYSKIND@@@Z; CTypeLib2::ReadExisting(tagSYSKIND)
0x180022f12  mov     edi, eax
0x180022f14  test    eax, eax
0x180022f16  js      loc_180022FBF
0x180022f1c  mov     edx, esi; enum tagSYSKIND
0x180022f1e  mov     rcx, rbx; this
0x180022f21  call    ?CheckForBad64BitLayout@CTypeLib2@@AEAAJW4tagSYSKIND@@@Z; CTypeLib2::CheckForBad64BitLayout(tagSYSKIND)
0x180022f26  lea     rdi, [rbx+194h]
0x180022f2d  movzx   eax, word ptr [rdi]
0x180022f30  and     eax, 3
0x180022f33  cmp     eax, [rbx+2A4h]
0x180022f39  jnz     short loc_180022F91
0x180022f3b  mov     rcx, rbp; psz
0x180022f3e  call    SysAllocString
0x180022f43  mov     [rbx+208h], rax
0x180022f4a  mov     rdx, rax; unsigned __int16 *
0x180022f4d  test    rax, rax
0x180022f50  jz      loc_180023014
0x180022f56  mov     r8d, [rsp+68h+arg_20]; int
0x180022f5e  movzx   eax, r8w
0x180022f62  shl     ax, 3
0x180022f66  xor     ax, [rdi]
0x180022f69  and     ax, 8
0x180022f6d  xor     [rdi], ax
0x180022f70  test    r14d, r14d
0x180022f73  jnz     short loc_180022FCE
0x180022f75  mov     rax, [rsp+68h+arg_30]
0x180022f7d  mov     [rax], rbx
0x180022f80  xor     eax, eax
0x180022f82  jmp     loc_180022E13
0x180022f87  mov     eax, 8007000Eh
0x180022f8c  jmp     loc_180022E13
0x180022f91  mov     rcx, rbx; this
0x180022f94  call    ?MarkAllForReLayout@CTypeLib2@@AEAAXXZ; CTypeLib2::MarkAllForReLayout(void)
0x180022f99  jmp     short loc_180022F3B
0x180022f9b  call    cs:__imp_GetLastError
0x180022fa1  mov     edi, eax
0x180022fa3  test    eax, eax
0x180022fa5  jg      short loc_180022FE9
0x180022fa7  xorps   xmm0, xmm0
0x180022faa  xor     eax, eax
0x180022fac  movups  xmmword ptr [rsi], xmm0
0x180022faf  movups  xmmword ptr [rsi+10h], xmm0
0x180022fb3  mov     [rsi+20h], rax
0x180022fb7  test    edi, edi
0x180022fb9  jns     loc_180022EE9
0x180022fbf  mov     rcx, rbx; this
0x180022fc2  call    ??_GCTypeLib2@@QEAAPEAXI@Z; CTypeLib2::`scalar deleting destructor'(uint)
0x180022fc7  mov     eax, edi
0x180022fc9  jmp     loc_180022E13
0x180022fce  mov     rcx, cs:?g_poletmgr@@3PEAVOLE_TYPEMGR@@EA; this
0x180022fd5  mov     r9, rbx; struct ITypeLib *
0x180022fd8  mov     [rsp+68h+var_48], esi; enum tagSYSKIND
0x180022fdc  call    ?TypeLibLoaded@OLE_TYPEMGR@@QEAAJPEBGHPEAUITypeLib@@W4tagSYSKIND@@@Z; OLE_TYPEMGR::TypeLibLoaded(ushort const *,int,ITypeLib *,tagSYSKIND)
0x180022fe1  mov     edi, eax
0x180022fe3  test    eax, eax
0x180022fe5  jns     short loc_180022F75
0x180022fe7  jmp     short loc_180022FBF
0x180022fe9  movzx   edi, ax
0x180022fec  or      edi, 80070000h
0x180022ff2  jmp     short loc_180022FA7
0x180022ff4  and     eax, 0FFFFFFFEh
0x180022ff7  mov     [rbx+210h], eax
0x180022ffd  call    ?InitNew@CTypeLib2@@QEAAJW4tagSYSKIND@@@Z; CTypeLib2::InitNew(tagSYSKIND)
0x180023002  mov     edi, eax
0x180023004  test    eax, eax
0x180023006  js      short loc_180022FBF
0x180023008  lea     rdi, [rbx+194h]
0x18002300f  jmp     loc_180022F3B
0x180023014  mov     edi, 8007000Eh
0x180023019  jmp     short loc_180022FBF
```
