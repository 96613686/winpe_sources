# Microsoft::WRL::Details::MakeAndInitialize<WindowsInternal::Shell::UnifiedTile::PackagedUnifiedTileIdentifier,WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier,HSTRING__ * &,HSTRING__ * &>(WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier * *,HSTRING__ * &,HSTRING__ * &)

- ea: `0x1800301cc`
- end: `0x18003042c`
- name: `??$MakeAndInitialize@VPackagedUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@UIUnifiedTileIdentifier@234@AEAPEAUHSTRING__@@AEAPEAU6@@Details@WRL@Microsoft@@YAJPEAPEAUIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@AEAPEAUHSTRING__@@1@Z`
- size: `608`
- prototype: ``
- caller_count: `7`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18002ff00`
- `0x1800301a0`
- `0x180050a70`
- `0x180158a40`
- `0x180181b00`
- `0x1801d4b98`
- `0x1802fb848`

## callees

- `0x1800177e4`
- `0x180018850`
- `0x18001aca4`
- `0x1800301cc`
- `0x180030684`
- `0x1800307d0`
- `0x180030e28`
- `0x18020be0c`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180030248`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180030248`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800302aa`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800303b9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800302aa`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800303b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800302cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800303cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800302cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800303cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003022d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003027e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003022d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003027e`

## string_xrefs

- `0x180030368`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtileidentifier.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<WindowsInternal::Shell::UnifiedTile::PackagedUnifiedTileIdentifier,WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier,HSTRING__ * &,HSTRING__ * &>(
        __int64 *a1,
        HSTRING *a2,
        HSTRING *a3)
{
  WindowsInternal::Shell::UnifiedTile::PackagedUnifiedTileIdentifier *v5; // rax
  __int64 v6; // r14
  HSTRING v7; // r15
  _DWORD *v8; // r13
  const wchar_t *StringRawBuffer; // rax
  const wchar_t *v10; // rbp
  wchar_t *v11; // rax
  const WCHAR *v12; // rdi
  const WCHAR *v13; // rax
  const WCHAR *v14; // r12
  bool v15; // al
  _QWORD *v16; // rsi
  _DWORD *v17; // r15
  HSTRING v18; // rcx
  int SerializedIdentifier; // eax
  unsigned int v20; // esi
  int v21; // edi
  __int64 v23; // rdx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-68h]
  __int64 v25; // [rsp+40h] [rbp-48h] BYREF
  _QWORD v26[8]; // [rsp+48h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  UINT32 length; // [rsp+A8h] [rbp+20h] BYREF

  *a1 = 0;
  v5 = (WindowsInternal::Shell::UnifiedTile::PackagedUnifiedTileIdentifier *)operator new(
                                                                               0x80u,
                                                                               (const struct std::nothrow_t *)std::nothrow);
  if ( !v5 )
    return 2147942414LL;
  v6 = WindowsInternal::Shell::UnifiedTile::PackagedUnifiedTileIdentifier::PackagedUnifiedTileIdentifier(v5);
  v25 = v6;
  v26[0] = 0;
  v7 = *a3;
  v8 = (_DWORD *)(v6 + 108);
  StringRawBuffer = WindowsGetStringRawBuffer(*a2, (UINT32 *)(v6 + 108));
  v10 = StringRawBuffer;
  if ( !*(_DWORD *)(v6 + 108)
    || (v11 = wcschr(StringRawBuffer, 0x21u),
        (v12 = (const WCHAR *)((unsigned __int64)(v11 + 1) & -(__int64)(v11 != 0))) == 0)
    || !*v12 )
  {
    v20 = -2147024809;
    goto LABEL_16;
  }
  length = 0;
  v13 = WindowsGetStringRawBuffer(v7, &length);
  v14 = v13;
  v15 = !length
     || CompareStringOrdinal(v12, -1, v13, -1, 1) == 2
     || CompareStringOrdinal(L"PrimaryBaseTile", -1, v14, -1, 1) == 2;
  v16 = (_QWORD *)(v6 + 72);
  v17 = (_DWORD *)(v6 + 104);
  v18 = *(HSTRING *)(v6 + 72);
  if ( !v15 )
  {
    WindowsDeleteString(v18);
    *v16 = 0;
    SerializedIdentifier = WindowsInternal::Shell::UnifiedTile::CreateSerializedIdentifier(
                             1,
                             (_DWORD)v10,
                             *v8,
                             (_DWORD)v14,
                             length,
                             v6 + 72,
                             v6 + 104,
                             v6 + 116);
    v20 = SerializedIdentifier;
    if ( SerializedIdentifier >= 0 )
    {
      v21 = *v17 + v12 - v10;
      goto LABEL_11;
    }
    v23 = 238;
    goto LABEL_15;
  }
  WindowsDeleteString(v18);
  *v16 = 0;
  SerializedIdentifier = WindowsInternal::Shell::UnifiedTile::CreateSerializedIdentifier(
                           1,
                           (_DWORD)v10,
                           *v8,
                           0,
                           0,
                           v6 + 72,
                           v6 + 104,
                           0);
  v20 = SerializedIdentifier;
  if ( SerializedIdentifier < 0 )
  {
    v23 = 223;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtileidentifier.cpp",
      (const char *)(unsigned int)SerializedIdentifier,
      bIgnoreCase);
LABEL_16:
    Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::PackagedUnifiedTileIdentifier>::InternalRelease(&v25);
    Microsoft::WRL::Details::MakeAllocator<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CuratedTileGroup>::~MakeAllocator<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CuratedTileGroup>(v26);
    return v20;
  }
  v21 = *v17 + v12 - v10;
  *(_DWORD *)(v6 + 116) = v21;
LABEL_11:
  *(_DWORD *)(v6 + 112) = v21;
  *a1 = v6;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
  if ( v6 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier,WindowsInternal::Shell::UnifiedTile::IPackagedUnifiedTileIdentifier,Microsoft::WRL::FtmBase>::Release(v6);
  return 0;
}

```

## disassembly

```asm
0x1800301cc  mov     [rsp+arg_8], rbx
0x1800301d1  mov     [rsp+arg_0], rcx
0x1800301d6  push    rbp
0x1800301d7  push    rsi
0x1800301d8  push    rdi
0x1800301d9  push    r12
0x1800301db  push    r13
0x1800301dd  push    r14
0x1800301df  push    r15
0x1800301e1  sub     rsp, 50h
0x1800301e5  mov     rdi, r8
0x1800301e8  mov     rsi, rdx
0x1800301eb  xor     r12d, r12d
0x1800301ee  mov     [rcx], r12
0x1800301f1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800301f8  mov     ecx, 80h; unsigned __int64
0x1800301fd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180030202  test    rax, rax
0x180030205  jz      loc_18003039E
0x18003020b  mov     rcx, rax; this
0x18003020e  call    ??0PackagedUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@QEAA@XZ; WindowsInternal::Shell::UnifiedTile::PackagedUnifiedTileIdentifier::PackagedUnifiedTileIdentifier(void)
0x180030213  mov     r14, rax
0x180030216  mov     [rsp+88h+var_48], rax
0x18003021b  mov     [rsp+88h+var_40], r12
0x180030220  mov     r15, [rdi]
0x180030223  lea     r13, [rax+6Ch]
0x180030227  mov     rdx, r13; length
0x18003022a  mov     rcx, [rsi]; string
0x18003022d  call    cs:__imp_WindowsGetStringRawBuffer
0x180030233  mov     rbp, rax
0x180030236  cmp     [r13+0], r12d
0x18003023a  jz      loc_180030397
0x180030240  lea     edx, [r12+21h]; Ch
0x180030245  mov     rcx, rax; Str
0x180030248  call    cs:__imp_wcschr
0x18003024e  lea     rdx, [rax+2]
0x180030252  neg     rax
0x180030255  sbb     rdi, rdi
0x180030258  and     rdi, rdx
0x18003025b  jz      loc_180030397
0x180030261  cmp     [rdi], r12w
0x180030265  jz      loc_180030397
0x18003026b  mov     [rsp+88h+length], r12d
0x180030273  lea     rdx, [rsp+88h+length]; length
0x18003027b  mov     rcx, r15; string
0x18003027e  call    cs:__imp_WindowsGetStringRawBuffer
0x180030284  mov     r12, rax
0x180030287  mov     esi, 1
0x18003028c  cmp     [rsp+88h+length], 0
0x180030294  jz      short loc_1800302B9
0x180030296  mov     [rsp+88h+bIgnoreCase], esi; bIgnoreCase
0x18003029a  or      r15d, 0FFFFFFFFh
0x18003029e  mov     r9d, r15d; cchCount2
0x1800302a1  mov     r8, rax; lpString2
0x1800302a4  mov     edx, r15d; cchCount1
0x1800302a7  mov     rcx, rdi; lpString1
0x1800302aa  call    cs:__imp_CompareStringOrdinal
0x1800302b0  cmp     eax, 2
0x1800302b3  jnz     loc_1800303A5
0x1800302b9  mov     al, sil
0x1800302bc  lea     rsi, [r14+48h]
0x1800302c0  lea     r15, [r14+68h]
0x1800302c4  mov     rcx, [rsi]; string
0x1800302c7  test    al, al
0x1800302c9  jz      loc_1800303CF
0x1800302cf  call    cs:__imp_WindowsDeleteString
0x1800302d5  mov     qword ptr [rsi], 0
0x1800302dc  mov     [rsp+88h+var_50], 0
0x1800302e5  mov     [rsp+88h+var_58], r15
0x1800302ea  mov     [rsp+88h+var_60], rsi
0x1800302ef  mov     [rsp+88h+bIgnoreCase], 0; int
0x1800302f7  xor     r9d, r9d
0x1800302fa  mov     r8d, [r13+0]
0x1800302fe  mov     rdx, rbp
0x180030301  lea     ecx, [r9+1]
0x180030305  call    WindowsInternal__Shell__UnifiedTile__CreateSerializedIdentifier
0x18003030a  mov     esi, eax
0x18003030c  test    eax, eax
0x18003030e  js      short loc_180030363
0x180030310  sub     rdi, rbp
0x180030313  sar     rdi, 1
0x180030316  add     edi, [r15]
0x180030319  mov     [r14+74h], edi
0x18003031d  mov     [r14+70h], edi
0x180030321  mov     rax, [rsp+88h+arg_0]
0x180030329  mov     [rax], r14
0x18003032c  mov     rax, [r14]
0x18003032f  mov     rcx, r14
0x180030332  mov     rax, [rax+8]
0x180030336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003033b  nop
0x18003033c  test    r14, r14
0x18003033f  jz      short loc_180030349
0x180030341  mov     rcx, r14
0x180030344  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@UIPackagedUnifiedTileIdentifier@567@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier,WindowsInternal::Shell::UnifiedTile::IPackagedUnifiedTileIdentifier,Microsoft::WRL::FtmBase>::Release(void)
0x180030349  xor     eax, eax
0x18003034b  mov     rbx, [rsp+88h+arg_8]
0x180030353  add     rsp, 50h
0x180030357  pop     r15
0x180030359  pop     r14
0x18003035b  pop     r13
0x18003035d  pop     r12
0x18003035f  pop     rdi
0x180030360  pop     rsi
0x180030361  pop     rbp
0x180030362  retn
0x180030363  mov     edx, 0DFh; void *
0x180030368  lea     r8, aShellcommonShe_227; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x18003036f  mov     r9d, eax; char *
0x180030372  mov     rcx, [rsp+88h]; this
0x18003037a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003037f  lea     rcx, [rsp+88h+var_48]
0x180030384  call    ?InternalRelease@?$ComPtr@VPackagedUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::PackagedUnifiedTileIdentifier>::InternalRelease(void)
0x180030389  lea     rcx, [rsp+88h+var_40]
0x18003038e  call    ??1?$MakeAllocator@VCuratedTileGroup@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CuratedTileGroup>::~MakeAllocator<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CuratedTileGroup>(void)
0x180030393  mov     eax, esi
0x180030395  jmp     short loc_18003034B
0x180030397  mov     esi, 80070057h
0x18003039c  jmp     short loc_18003037F
0x18003039e  mov     eax, 8007000Eh
0x1800303a3  jmp     short loc_18003034B
0x1800303a5  mov     [rsp+88h+bIgnoreCase], esi; bIgnoreCase
0x1800303a9  mov     r9d, r15d; cchCount2
0x1800303ac  mov     r8, r12; lpString2
0x1800303af  mov     edx, r15d; cchCount1
0x1800303b2  lea     rcx, aPrimarybasetil; "PrimaryBaseTile"
0x1800303b9  call    cs:__imp_CompareStringOrdinal
0x1800303bf  cmp     eax, 2
0x1800303c2  jz      loc_1800302B9
0x1800303c8  xor     al, al
0x1800303ca  jmp     loc_1800302BC
0x1800303cf  call    cs:__imp_WindowsDeleteString
0x1800303d5  mov     qword ptr [rsi], 0
0x1800303dc  mov     ecx, [rsp+88h+length]
0x1800303e3  lea     rax, [r14+74h]
0x1800303e7  mov     [rsp+88h+var_50], rax
0x1800303ec  mov     [rsp+88h+var_58], r15
0x1800303f1  mov     [rsp+88h+var_60], rsi
0x1800303f6  mov     [rsp+88h+bIgnoreCase], ecx
0x1800303fa  mov     r9, r12
0x1800303fd  mov     r8d, [r13+0]
0x180030401  mov     rdx, rbp
0x180030404  mov     ecx, 1
0x180030409  call    WindowsInternal__Shell__UnifiedTile__CreateSerializedIdentifier
0x18003040e  mov     esi, eax
0x180030410  test    eax, eax
0x180030412  jns     short loc_18003041E
0x180030414  mov     edx, 0EEh
0x180030419  jmp     loc_180030368
0x18003041e  sub     rdi, rbp
0x180030421  sar     rdi, 1
0x180030424  add     edi, [r15]
0x180030427  jmp     loc_18003031D
```
