# SetInboxATAutoStart(INBOXAT,int)

- ea: `0x14000c8b4`
- end: `0x14000cb49`
- name: `?SetInboxATAutoStart@@YAJW4INBOXAT@@H@Z`
- size: `661`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000b250`

## callees

- `0x140001e44`
- `0x140004890`
- `0x140006a78`
- `0x140009384`
- `0x14000bd60`
- `0x14000bdf4`
- `0x14000c68c`
- `0x14000c8b4`
- `0x14000cb50`
- `0x14000cfd0`
- `0x14000f810`
- `0x1400100d8`
- `0x1400113b0`
- `0x1400116c4`
- `0x140017010`

## string_xrefs

- `0x14000c917`: `enduser\ezap\easeofaccess\atmanager\atlist.cpp`
- `0x14000c9e2`: `enduser\ezap\easeofaccess\atmanager\atlist.cpp`

## pseudocode

```c
__int64 __fastcall SetInboxATAutoStart(__int64 a1, int a2)
{
  int NameOfInboxAT; // eax
  unsigned int v4; // ebx
  unsigned __int16 *v5; // rdx
  int v7; // eax
  unsigned __int16 *v8; // rdi
  const wchar_t **v9; // rbx
  int v10; // r14d
  __int64 v11; // rdx
  __int64 v12; // r14
  unsigned __int16 *v13; // rax
  int v14; // edx
  int v15; // ecx
  int v16; // [rsp+20h] [rbp-E0h]
  _BYTE v17[352]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]
  unsigned __int16 *v19; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v20; // [rsp+1C8h] [rbp+C8h] BYREF

  v19 = (unsigned __int16 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  NameOfInboxAT = anonymous_namespace_::GetNameOfInboxAT(3, &v19);
  v4 = NameOfInboxAT;
  if ( NameOfInboxAT < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x34D,
      (unsigned int)"enduser\\ezap\\easeofaccess\\atmanager\\atlist.cpp",
      (const char *)(unsigned int)NameOfInboxAT,
      v16);
    v5 = v19 - 12;
    if ( _InterlockedDecrement((volatile signed __int32 *)v19 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v5 + 8LL))(*(_QWORD *)v5);
    return v4;
  }
  v7 = IsInteractiveUser();
  v8 = v19;
  if ( v7 )
  {
    v9 = (const wchar_t **)Accommodation::Open(v19);
    if ( !v9 )
    {
      if ( _InterlockedDecrement((volatile signed __int32 *)v8 - 2) <= 0 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v8 - 3) + 8LL))(*((_QWORD *)v8 - 3));
      return 2147500037LL;
    }
    ATManager::ATManager((ATManager *)v17, 1);
    if ( a2 )
    {
      v10 = StartList::Add((StartList *)v17, v9);
      if ( v10 < 0 )
      {
        v11 = 858;
LABEL_13:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v11,
          (unsigned int)"enduser\\ezap\\easeofaccess\\atmanager\\atlist.cpp",
          (const char *)(unsigned int)v10,
          (int)v9);
        ATManager::~ATManager((ATManager *)v17);
        Accommodation::~Accommodation((Accommodation *)v9);
        operator delete(v9);
        if ( _InterlockedDecrement((volatile signed __int32 *)v8 - 2) <= 0 )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v8 - 3) + 8LL))(*((_QWORD *)v8 - 3));
        return (unsigned int)v10;
      }
      v20 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v20, L"narrator");
      v12 = v20;
      if ( !v20 )
        ATL::AtlThrowImpl(-2147467259);
      v13 = v8;
      do
      {
        v14 = *(unsigned __int16 *)((char *)v13 + v20 - (_QWORD)v8);
        v15 = *v13 - v14;
        if ( v15 )
          break;
        ++v13;
      }
      while ( v14 );
      if ( !v15 )
        StartList::SetNarratorAfterSigninResetCompleted();
      if ( _InterlockedDecrement((volatile signed __int32 *)(v12 - 24 + 16)) <= 0 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v12 - 24) + 8LL))(*(_QWORD *)(v12 - 24));
    }
    else
    {
      v10 = StartList::Remove((StartList *)v17, (struct Accommodation *)v9);
      if ( v10 < 0 )
      {
        v11 = 872;
        goto LABEL_13;
      }
    }
    ATManager::~ATManager((ATManager *)v17);
    Accommodation::~Accommodation((Accommodation *)v9);
    operator delete(v9);
  }
  if ( _InterlockedDecrement((volatile signed __int32 *)v8 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v8 - 3) + 8LL))(*((_QWORD *)v8 - 3));
  return 0;
}

```

## disassembly

```asm
0x14000c8b4  mov     [rsp-8+arg_0], rbx
0x14000c8b9  mov     [rsp-8+arg_8], rsi
0x14000c8be  push    rbp
0x14000c8bf  push    rdi
0x14000c8c0  push    r14
0x14000c8c2  lea     rbp, [rsp-90h]
0x14000c8ca  sub     rsp, 190h
0x14000c8d1  mov     r14d, edx
0x14000c8d4  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000c8db  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000c8e2  mov     rax, [rax+18h]
0x14000c8e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c8eb  add     rax, 18h
0x14000c8ef  mov     [rbp+0A0h+arg_10], rax
0x14000c8f6  lea     rdx, [rbp+0A0h+arg_10]
0x14000c8fd  mov     ecx, 3
0x14000c902  call    _anonymous_namespace___GetNameOfInboxAT
0x14000c907  mov     ebx, eax
0x14000c909  test    eax, eax
0x14000c90b  jns     short loc_14000C95A
0x14000c90d  mov     rcx, [rbp+0A8h]; this
0x14000c914  mov     r9d, eax; char *
0x14000c917  lea     r8, aEnduserEzapEas_0; "enduser\\ezap\\easeofaccess\\atmanager"...
0x14000c91e  mov     edx, 34Dh; void *
0x14000c923  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c928  nop
0x14000c929  mov     rdx, [rbp+0A0h+arg_10]
0x14000c930  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000c934  or      esi, 0FFFFFFFFh
0x14000c937  mov     eax, esi
0x14000c939  lock xadd [rdx+10h], eax
0x14000c93e  add     eax, esi
0x14000c940  test    eax, eax
0x14000c942  jg      short loc_14000C953
0x14000c944  mov     rcx, [rdx]
0x14000c947  mov     rax, [rcx]
0x14000c94a  mov     rax, [rax+8]
0x14000c94e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c953  mov     eax, ebx
0x14000c955  jmp     loc_14000CB0F
0x14000c95a  call    ?IsInteractiveUser@@YAHXZ; IsInteractiveUser(void)
0x14000c95f  or      esi, 0FFFFFFFFh
0x14000c962  mov     rdi, [rbp+0A0h+arg_10]
0x14000c969  test    eax, eax
0x14000c96b  jz      loc_14000CAED
0x14000c971  mov     rcx, rdi; unsigned __int16 *
0x14000c974  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x14000c979  mov     rbx, rax
0x14000c97c  mov     qword ptr [rsp+1A0h+var_180], rax; int
0x14000c981  test    rax, rax
0x14000c984  jnz     short loc_14000C9B0
0x14000c986  lea     rdx, [rdi-18h]
0x14000c98a  mov     eax, esi
0x14000c98c  lock xadd [rdx+10h], eax
0x14000c991  add     eax, esi
0x14000c993  test    eax, eax
0x14000c995  jg      short loc_14000C9A6
0x14000c997  mov     rcx, [rdx]
0x14000c99a  mov     rax, [rcx]
0x14000c99d  mov     rax, [rax+8]
0x14000c9a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c9a6  mov     eax, 80004005h
0x14000c9ab  jmp     loc_14000CB0F
0x14000c9b0  mov     edx, 1; int
0x14000c9b5  lea     rcx, [rsp+1A0h+var_170]; this
0x14000c9ba  call    ??0ATManager@@QEAA@H@Z; ATManager::ATManager(int)
0x14000c9bf  nop
0x14000c9c0  mov     rdx, rbx; struct Accommodation *
0x14000c9c3  lea     rcx, [rsp+1A0h+var_170]; this
0x14000c9c8  test    r14d, r14d
0x14000c9cb  jz      loc_14000CB27
0x14000c9d1  call    ?Add@StartList@@QEAAJPEAVAccommodation@@@Z; StartList::Add(Accommodation *)
0x14000c9d6  mov     r14d, eax
0x14000c9d9  test    eax, eax
0x14000c9db  jns     short loc_14000CA3D
0x14000c9dd  mov     edx, 35Ah; void *
0x14000c9e2  lea     r8, aEnduserEzapEas_0; "enduser\\ezap\\easeofaccess\\atmanager"...
0x14000c9e9  mov     r9d, r14d; char *
0x14000c9ec  mov     rcx, [rbp+0A8h]; this
0x14000c9f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c9f8  nop
0x14000c9f9  lea     rcx, [rsp+1A0h+var_170]; this
0x14000c9fe  call    ??1ATManager@@QEAA@XZ; ATManager::~ATManager(void)
0x14000ca03  nop
0x14000ca04  mov     rcx, rbx; this
0x14000ca07  call    ??1Accommodation@@QEAA@XZ; Accommodation::~Accommodation(void)
0x14000ca0c  mov     rcx, rbx; Block
0x14000ca0f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000ca14  nop
0x14000ca15  lea     rdx, [rdi-18h]
0x14000ca19  mov     eax, esi
0x14000ca1b  lock xadd [rdx+10h], eax
0x14000ca20  add     eax, esi
0x14000ca22  test    eax, eax
0x14000ca24  jg      short loc_14000CA35
0x14000ca26  mov     rcx, [rdx]
0x14000ca29  mov     rax, [rcx]
0x14000ca2c  mov     rax, [rax+8]
0x14000ca30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ca35  mov     eax, r14d
0x14000ca38  jmp     loc_14000CB0F
0x14000ca3d  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000ca44  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000ca4b  mov     rax, [rax+18h]
0x14000ca4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ca54  add     rax, 18h
0x14000ca58  mov     [rbp+0A0h+arg_18], rax
0x14000ca5f  mov     r8d, 8
0x14000ca65  lea     rdx, aNarrator; "narrator"
0x14000ca6c  lea     rcx, [rbp+0A0h+arg_18]
0x14000ca73  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14000ca78  nop
0x14000ca79  mov     r14, [rbp+0A0h+arg_18]
0x14000ca80  test    r14, r14
0x14000ca83  jz      loc_14000CB3E
0x14000ca89  mov     rax, rdi
0x14000ca8c  mov     r8, r14
0x14000ca8f  sub     r8, rdi
0x14000ca92  movzx   ecx, word ptr [rax]
0x14000ca95  movzx   edx, word ptr [rax+r8]
0x14000ca9a  sub     ecx, edx
0x14000ca9c  jnz     short loc_14000CAA6
0x14000ca9e  add     rax, 2
0x14000caa2  test    edx, edx
0x14000caa4  jnz     short loc_14000CA92
0x14000caa6  test    ecx, ecx
0x14000caa8  jnz     short loc_14000CAB0
0x14000caaa  call    ?SetNarratorAfterSigninResetCompleted@StartList@@SAXXZ; StartList::SetNarratorAfterSigninResetCompleted(void)
0x14000caaf  nop
0x14000cab0  lea     rdx, [r14-18h]
0x14000cab4  mov     eax, esi
0x14000cab6  lock xadd [rdx+10h], eax
0x14000cabb  add     eax, esi
0x14000cabd  test    eax, eax
0x14000cabf  jg      short loc_14000CAD1
0x14000cac1  mov     rcx, [rdx]
0x14000cac4  mov     rax, [rcx]
0x14000cac7  mov     rax, [rax+8]
0x14000cacb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cad0  nop
0x14000cad1  lea     rcx, [rsp+1A0h+var_170]; this
0x14000cad6  call    ??1ATManager@@QEAA@XZ; ATManager::~ATManager(void)
0x14000cadb  nop
0x14000cadc  mov     rcx, rbx; this
0x14000cadf  call    ??1Accommodation@@QEAA@XZ; Accommodation::~Accommodation(void)
0x14000cae4  mov     rcx, rbx; Block
0x14000cae7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000caec  nop
0x14000caed  lea     rdx, [rdi-18h]
0x14000caf1  mov     eax, esi
0x14000caf3  lock xadd [rdx+10h], eax
0x14000caf8  add     eax, esi
0x14000cafa  test    eax, eax
0x14000cafc  jg      short loc_14000CB0D
0x14000cafe  mov     rcx, [rdx]
0x14000cb01  mov     rax, [rcx]
0x14000cb04  mov     rax, [rax+8]
0x14000cb08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cb0d  xor     eax, eax
0x14000cb0f  lea     r11, [rsp+1A0h+var_10]
0x14000cb17  mov     rbx, [r11+20h]
0x14000cb1b  mov     rsi, [r11+28h]
0x14000cb1f  mov     rsp, r11
0x14000cb22  pop     r14
0x14000cb24  pop     rdi
0x14000cb25  pop     rbp
0x14000cb26  retn
0x14000cb27  call    ?Remove@StartList@@QEAAJPEAVAccommodation@@@Z; StartList::Remove(Accommodation *)
0x14000cb2c  nop
0x14000cb2d  mov     r14d, eax
0x14000cb30  test    eax, eax
0x14000cb32  jns     short loc_14000CAD1
0x14000cb34  mov     edx, 368h
0x14000cb39  jmp     loc_14000C9E2
0x14000cb3e  mov     ecx, 80004005h; int
0x14000cb43  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
