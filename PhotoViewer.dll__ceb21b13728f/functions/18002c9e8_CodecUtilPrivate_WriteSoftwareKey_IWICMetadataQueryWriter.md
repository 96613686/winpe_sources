# CodecUtilPrivate::WriteSoftwareKey(IWICMetadataQueryWriter *)

- ea: `0x18002c9e8`
- end: `0x18002cbba`
- name: `?WriteSoftwareKey@CodecUtilPrivate@@YAXPEAUIWICMetadataQueryWriter@@@Z`
- size: `466`
- prototype: `void __fastcall(CodecUtilPrivate *__hidden this, struct IWICMetadataQueryWriter *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800796e8`

## callees

- `0x180004908`
- `0x180004e88`
- `0x180026724`
- `0x1800271ec`
- `0x18002c9b8`
- `0x18002c9e8`
- `0x18002ddc0`
- `0x18002ea00`
- `0x180080010`

## import_xrefs

- `VERSION!GetFileVersionInfoW` at `0x18002caa4`
- `VERSION!GetFileVersionInfoW` at `0x18002caa4`
- `VERSION!VerQueryValueW` at `0x18002cacf`
- `VERSION!VerQueryValueW` at `0x18002cacf`
- `VERSION!GetFileVersionInfoSizeW` at `0x18002ca6c`
- `VERSION!GetFileVersionInfoSizeW` at `0x18002ca6c`
- `PhotoBase!?Delete@BasePrivate@@YAXPEAX@Z` at `0x18002cb5c`
- `PhotoBase!?Delete@BasePrivate@@YAXPEAX@Z` at `0x18002cb5c`
- `PhotoBase!?New@BasePrivate@@YAPEAX_K_N@Z` at `0x18002ca88`
- `PhotoBase!?New@BasePrivate@@YAPEAX_K_N@Z` at `0x18002ca88`
- `PhotoBase!?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ` at `0x18002ca24`
- `PhotoBase!?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ` at `0x18002cae9`
- `PhotoBase!?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ` at `0x18002ca24`
- `PhotoBase!?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ` at `0x18002cae9`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18002ca08`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18002cade`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18002cba6`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18002ca08`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18002cade`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18002cba6`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x18002ca78`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x18002caae`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x18002ca78`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x18002caae`

## string_xrefs

- `0x18002ca65`: `PhotoBase.dll`
- `0x18002ca9d`: `PhotoBase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall CodecUtilPrivate::WriteSoftwareKey(CodecUtilPrivate *this, struct IWICMetadataQueryWriter *a2)
{
  __int64 BaseStringManager; // rax
  DWORD FileVersionInfoSizeW; // eax
  unsigned __int64 v5; // rdx
  Base *v6; // rcx
  bool v7; // r8
  DWORD v8; // ebx
  void *v9; // rdi
  Base *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  unsigned __int16 *v13; // rbx
  __int64 v14; // rax
  void *v15; // rdx
  int v16; // eax
  int v17; // edx
  LPVOID lpBuffer[2]; // [rsp+30h] [rbp-38h] BYREF
  _QWORD v19[5]; // [rsp+40h] [rbp-28h] BYREF
  DWORD dwHandle; // [rsp+A0h] [rbp+38h] BYREF
  unsigned int puLen; // [rsp+A8h] [rbp+40h] BYREF
  unsigned __int16 *v22; // [rsp+B0h] [rbp+48h] BYREF
  __int64 v23; // [rsp+B8h] [rbp+50h] BYREF

  if ( !this )
  {
    Base::Throw((Base *)0x80004003LL, (_DWORD)a2);
    __debugbreak();
  }
  if ( !word_1800A4770 )
  {
    BaseStringManager = Base::String::GetBaseStringManager(this, a2);
    ATL::CSimpleStringT<unsigned short,0>::CSimpleStringT<unsigned short,0>(&v22, BaseStringManager);
    if ( !(unsigned __int8)ATL::CStringT<unsigned short,StrTraitBase<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
                             &v22,
                             L"Microsoft Windows Photo Viewer ") )
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v22, L"Microsoft Windows Photo Viewer ");
    dwHandle = 0;
    FileVersionInfoSizeW = GetFileVersionInfoSizeW(L"PhotoBase.dll", &dwHandle);
    v8 = FileVersionInfoSizeW;
    if ( !FileVersionInfoSizeW )
    {
      Base::ThrowLastError(v6);
      __debugbreak();
    }
    LOBYTE(v5) = 1;
    v9 = BasePrivate::New((BasePrivate *)FileVersionInfoSizeW, v5, v7);
    lpBuffer[1] = v9;
    if ( !GetFileVersionInfoW(L"PhotoBase.dll", 0, v8, v9) )
    {
      Base::ThrowLastError(v10);
      __debugbreak();
    }
    lpBuffer[0] = 0;
    puLen = 0;
    if ( !VerQueryValueW(v9, L"\\", lpBuffer, &puLen) )
    {
      Base::Throw((Base *)0x80004005LL, v11);
      __debugbreak();
    }
    v13 = (unsigned __int16 *)lpBuffer[0];
    v14 = Base::String::GetBaseStringManager(v12, v11);
    ATL::CSimpleStringT<unsigned short,0>::CSimpleStringT<unsigned short,0>(&v23, v14);
    ATL::CStringT<unsigned short,StrTraitBase<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      &v23,
      L"%d.%d.%d.%d",
      v13[9],
      v13[8],
      v13[11],
      v13[10]);
    ATL::CSimpleStringT<unsigned short,0>::Append(&v22, v23, *(unsigned int *)(v23 - 16));
    StringCchCopyW(&word_1800A4770, 0x50u, v22);
    Base::String::~String((Base::String *)&v23);
    if ( v9 )
      BasePrivate::Delete((BasePrivate *)v9, v15);
    Base::String::~String((Base::String *)&v22);
  }
  v19[0] = 31;
  v19[2] = 0;
  v19[1] = &word_1800A4770;
  v16 = (*(__int64 (__fastcall **)(CodecUtilPrivate *, const wchar_t *, _QWORD *))(*(_QWORD *)this + 56LL))(
          this,
          L"System.ApplicationName",
          v19);
  if ( v16 < 0 )
  {
    Base::Throw((Base *)(unsigned int)v16, v17);
    __debugbreak();
  }
}

```

## disassembly

```asm
0x18002c9e8  push    rbp
0x18002c9ea  push    rbx
0x18002c9eb  push    rsi
0x18002c9ec  push    rdi
0x18002c9ed  push    r14
0x18002c9ef  push    r15
0x18002c9f1  mov     rbp, rsp
0x18002c9f4  sub     rsp, 68h
0x18002c9f8  mov     rsi, rcx
0x18002c9fb  xor     r14d, r14d
0x18002c9fe  test    rcx, rcx
0x18002ca01  jnz     short loc_18002CA0F
0x18002ca03  mov     ecx, 80004003h
0x18002ca08  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18002ca0e  int     3; Trap to Debugger
0x18002ca0f  lea     r15, word_1800A4770
0x18002ca16  cmp     cs:word_1800A4770, r14w
0x18002ca1e  jnz     loc_18002CB6C
0x18002ca24  call    cs:__imp_?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ; Base::String::GetBaseStringManager(void)
0x18002ca2a  nop
0x18002ca2b  mov     rdx, rax
0x18002ca2e  lea     rcx, [rbp+arg_10]
0x18002ca32  call    ??0?$CSimpleStringT@G$0A@@ATL@@QEAA@PEAUIAtlStringMgr@1@@Z; ATL::CSimpleStringT<ushort,0>::CSimpleStringT<ushort,0>(ATL::IAtlStringMgr *)
0x18002ca37  nop
0x18002ca38  lea     rdx, aMicrosoftWindo_0; "Microsoft Windows Photo Viewer "
0x18002ca3f  lea     rcx, [rbp+arg_10]
0x18002ca43  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitBase@GV?$ChTraitsCRT@G@ATL@@@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,StrTraitBase<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x18002ca48  test    al, al
0x18002ca4a  jnz     short loc_18002CA5D
0x18002ca4c  lea     rdx, aMicrosoftWindo_0; "Microsoft Windows Photo Viewer "
0x18002ca53  lea     rcx, [rbp+arg_10]
0x18002ca57  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18002ca5c  nop
0x18002ca5d  mov     [rbp+dwHandle], r14d
0x18002ca61  lea     rdx, [rbp+dwHandle]; lpdwHandle
0x18002ca65  lea     rcx, tstrFilename; "PhotoBase.dll"
0x18002ca6c  call    cs:__imp_GetFileVersionInfoSizeW
0x18002ca72  mov     ebx, eax
0x18002ca74  test    eax, eax
0x18002ca76  jnz     short loc_18002CA7F
0x18002ca78  call    cs:__imp_?ThrowLastError@Base@@YAXXZ; Base::ThrowLastError(void)
0x18002ca7e  int     3; Trap to Debugger
0x18002ca7f  mov     [rbp+var_30], r14
0x18002ca83  mov     rcx, rbx
0x18002ca86  mov     dl, 1
0x18002ca88  call    cs:__imp_?New@BasePrivate@@YAPEAX_K_N@Z; BasePrivate::New(unsigned __int64,bool)
0x18002ca8e  mov     rdi, rax
0x18002ca91  mov     [rbp+var_30], rax
0x18002ca95  mov     r9, rax; lpData
0x18002ca98  mov     r8d, ebx; dwLen
0x18002ca9b  xor     edx, edx; dwHandle
0x18002ca9d  lea     rcx, tstrFilename; "PhotoBase.dll"
0x18002caa4  call    cs:__imp_GetFileVersionInfoW
0x18002caaa  test    eax, eax
0x18002caac  jnz     short loc_18002CAB5
0x18002caae  call    cs:__imp_?ThrowLastError@Base@@YAXXZ; Base::ThrowLastError(void)
0x18002cab4  int     3; Trap to Debugger
0x18002cab5  mov     [rbp+lpBuffer], r14
0x18002cab9  mov     [rbp+puLen], r14d
0x18002cabd  lea     r9, [rbp+puLen]; puLen
0x18002cac1  lea     r8, [rbp+lpBuffer]; lplpBuffer
0x18002cac5  lea     rdx, SubBlock; "\\"
0x18002cacc  mov     rcx, rdi; pBlock
0x18002cacf  call    cs:__imp_VerQueryValueW
0x18002cad5  test    eax, eax
0x18002cad7  jnz     short loc_18002CAE5
0x18002cad9  mov     ecx, 80004005h
0x18002cade  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18002cae4  int     3; Trap to Debugger
0x18002cae5  mov     rbx, [rbp+lpBuffer]
0x18002cae9  call    cs:__imp_?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ; Base::String::GetBaseStringManager(void)
0x18002caef  nop
0x18002caf0  mov     rdx, rax
0x18002caf3  lea     rcx, [rbp+arg_18]
0x18002caf7  call    ??0?$CSimpleStringT@G$0A@@ATL@@QEAA@PEAUIAtlStringMgr@1@@Z; ATL::CSimpleStringT<ushort,0>::CSimpleStringT<ushort,0>(ATL::IAtlStringMgr *)
0x18002cafc  nop
0x18002cafd  movzx   eax, word ptr [rbx+14h]
0x18002cb01  movzx   ecx, word ptr [rbx+16h]
0x18002cb05  movzx   r9d, word ptr [rbx+10h]
0x18002cb0a  movzx   r8d, word ptr [rbx+12h]
0x18002cb0f  mov     [rsp+68h+var_40], eax
0x18002cb13  mov     [rsp+68h+var_48], ecx
0x18002cb17  lea     rdx, aDDDD; "%d.%d.%d.%d"
0x18002cb1e  lea     rcx, [rbp+arg_18]
0x18002cb22  call    ?Format@?$CStringT@GV?$StrTraitBase@GV?$ChTraitsCRT@G@ATL@@@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,StrTraitBase<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18002cb27  mov     rdx, [rbp+arg_18]
0x18002cb2b  mov     r8d, [rdx-10h]
0x18002cb2f  lea     rcx, [rbp+arg_10]
0x18002cb33  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18002cb38  mov     r8, [rbp+arg_10]; unsigned __int16 *
0x18002cb3c  mov     edx, 50h ; 'P'; unsigned __int64
0x18002cb41  mov     rcx, r15; unsigned __int16 *
0x18002cb44  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002cb49  nop
0x18002cb4a  lea     rcx, [rbp+arg_18]; this
0x18002cb4e  call    ??1String@Base@@QEAA@XZ; Base::String::~String(void)
0x18002cb53  nop
0x18002cb54  test    rdi, rdi
0x18002cb57  jz      short loc_18002CB63
0x18002cb59  mov     rcx, rdi
0x18002cb5c  call    cs:__imp_?Delete@BasePrivate@@YAXPEAX@Z; BasePrivate::Delete(void *)
0x18002cb62  nop
0x18002cb63  lea     rcx, [rbp+arg_10]; this
0x18002cb67  call    ??1String@Base@@QEAA@XZ; Base::String::~String(void)
0x18002cb6c  xorps   xmm0, xmm0
0x18002cb6f  xor     eax, eax
0x18002cb71  movups  [rbp+var_28], xmm0
0x18002cb75  mov     [rbp+var_18], rax
0x18002cb79  mov     eax, 1Fh
0x18002cb7e  mov     word ptr [rbp+var_28], ax
0x18002cb82  mov     qword ptr [rbp+var_28+8], r15
0x18002cb86  mov     rax, [rsi]
0x18002cb89  lea     r8, [rbp+var_28]
0x18002cb8d  lea     rdx, aSystemApplicat; "System.ApplicationName"
0x18002cb94  mov     rcx, rsi
0x18002cb97  mov     rax, [rax+38h]
0x18002cb9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cba0  test    eax, eax
0x18002cba2  jns     short loc_18002CBAD
0x18002cba4  mov     ecx, eax
0x18002cba6  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18002cbac  int     3; Trap to Debugger
0x18002cbad  add     rsp, 68h
0x18002cbb1  pop     r15
0x18002cbb3  pop     r14
0x18002cbb5  pop     rdi
0x18002cbb6  pop     rsi
0x18002cbb7  pop     rbx
0x18002cbb8  pop     rbp
0x18002cbb9  retn
```
