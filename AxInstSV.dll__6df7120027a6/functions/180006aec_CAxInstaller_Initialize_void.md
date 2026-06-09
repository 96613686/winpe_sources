# CAxInstaller::Initialize(void)

- ea: `0x180006aec`
- end: `0x180006c5d`
- name: `?Initialize@CAxInstaller@@QEAAJXZ`
- size: `369`
- prototype: `__int64 __fastcall(CAxInstaller *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180006c70`

## callees

- `0x1800017c0`
- `0x180005328`
- `0x1800053e4`
- `0x180006918`
- `0x180006aec`
- `0x18000725c`
- `0x180011fe8`
- `0x1800120ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006c35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006c35`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006c2b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006c2b`

## pseudocode

```c
__int64 __fastcall CAxInstaller::Initialize(CAxInstaller *this)
{
  CAxInstaller *v1; // r14
  CAxisUrlCache **v2; // rsi
  CAxisUrlCache *v3; // rbx
  int Folder; // ebx
  unsigned int v5; // r8d
  CAxInstaller *v6; // rcx
  signed int LastError; // eax
  ATL::CAtlException *v9; // [rsp+30h] [rbp-38h] BYREF
  CAxInstaller *ReturnLength; // [rsp+70h] [rbp+8h] BYREF
  CAxisUrlCache *v11; // [rsp+78h] [rbp+10h]
  CAxisUrlCache **v12; // [rsp+80h] [rbp+18h]

  ReturnLength = this;
  v1 = this;
  AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 8u, 4u, L"Initialize called");
  v2 = (CAxisUrlCache **)((char *)v1 + 696);
  v12 = (CAxisUrlCache **)((char *)v1 + 696);
  if ( !*((_QWORD *)v1 + 87) )
  {
    v3 = (CAxisUrlCache *)operator new(0x80u, (const struct std::nothrow_t *)&std::nothrow);
    v11 = v3;
    if ( v3 )
    {
      if ( __eh34_try(-1, 0) )
      {
        __eh34_scope_strut(0);
        *(_QWORD *)v3 = &CAxisUrlCache::`vftable';
        *((_QWORD *)v3 + 1) = 0;
        *((_QWORD *)v3 + 2) = 0;
        std::_Tree<std::_Tmap_traits<ATL::CComBSTR,CAxISUrlEntry *,AxISCaseInsensitiveLessThan,std::allocator<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>,0>>::_Alloc_sentinel_and_proxy();
      }
      if ( __eh34_catch(0) )
      {
        if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', &v9) )
        {
          LODWORD(v11) = *(_DWORD *)v9;
          __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_180006B8D);
          Folder = (int)v11;
          if ( (int)v11 < 0 )
            return (unsigned int)Folder;
          v1 = ReturnLength;
          v2 = v12;
          goto LABEL_8;
        }
        if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
        {
          Folder = -2147024882;
          __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180006B84);
          return (unsigned int)Folder;
        }
      }
    }
    else
    {
      v3 = 0;
    }
    *v2 = v3;
    if ( !v3 )
      return (unsigned int)-2147024882;
LABEL_8:
    Folder = CAxisUrlCache::Initialize(*v2);
    if ( Folder < 0 )
      return (unsigned int)Folder;
  }
  if ( PathName )
  {
    Folder = Utils::CreateFolder(&PathName);
    if ( Folder >= 0 )
    {
      Folder = ((__int64 (__fastcall *)(const unsigned __int16 *, unsigned __int16 *, unsigned int))Utils::CreateTempFolder)(
                 &PathName,
                 (unsigned __int16 *)v1 + 36,
                 v5);
      if ( Folder >= 0 )
      {
        Folder = ((int (__stdcall *)(CAxInstaller *, void **))CAxInstaller::GetClientsToken)(v6, (void **)v1 + 85);
        if ( Folder >= 0 )
        {
          Folder = 0;
          LODWORD(ReturnLength) = 4;
          if ( !GetTokenInformation(*((HANDLE *)v1 + 85), TokenSessionId, (char *)v1 + 668, 4u, (PDWORD)&ReturnLength) )
          {
            LastError = GetLastError();
            Folder = LastError;
            if ( LastError > 0 )
              return (unsigned __int16)LastError | 0x80070000;
          }
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return (unsigned int)Folder;
}

```

## disassembly

```asm
0x180006aec  mov     [rsp+arg_0], rcx
0x180006af1  push    rbx
0x180006af2  push    rsi
0x180006af3  push    rdi
0x180006af4  push    r14
0x180006af6  sub     rsp, 48h
0x180006afa  mov     r14, rcx
0x180006afd  lea     r9, aInitializeCall; "Initialize called"
0x180006b04  mov     edx, 8; unsigned int
0x180006b09  lea     r8d, [rdx-4]; unsigned __int8
0x180006b0d  lea     rcx, qword_180021AD8; this
0x180006b14  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x180006b19  lea     rsi, [r14+2B8h]
0x180006b20  mov     [rsp+68h+arg_10], rsi
0x180006b28  xor     edi, edi
0x180006b2a  cmp     [rsi], rdi
0x180006b2d  jnz     loc_180006BBA
0x180006b33  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006b3a  mov     ecx, 80h; unsigned __int64
0x180006b3f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180006b44  mov     rbx, rax
0x180006b47  mov     [rsp+68h+arg_8], rax
0x180006b4c  test    rax, rax
0x180006b4f  jz      short loc_180006B6D
0x180006b51  lea     rax, ??_7CAxisUrlCache@@6B@; const CAxisUrlCache::`vftable'
0x180006b58  mov     [rbx], rax
0x180006b5b  lea     rcx, [rbx+8]
0x180006b5f  mov     [rcx], rdi
0x180006b62  mov     [rcx+8], rdi
0x180006b66  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@PEAVCAxISUrlEntry@@UAxISCaseInsensitiveLessThan@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@@std@@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<ATL::CComBSTR,CAxISUrlEntry *,AxISCaseInsensitiveLessThan,std::allocator<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>,0>>::_Alloc_sentinel_and_proxy(void)
0x180006b6b  jmp     short loc_180006B70
0x180006b6d  mov     rbx, rdi
0x180006b70  mov     [rsi], rbx
0x180006b73  test    rbx, rbx
0x180006b76  jnz     short loc_180006B82
0x180006b78  mov     ebx, 8007000Eh
0x180006b7d  jmp     loc_180006C51
0x180006b82  jmp     short loc_180006BA8
0x180006b84  mov     ebx, dword ptr [rsp+68h+arg_8]
0x180006b88  jmp     loc_180006C51
0x180006b8d  mov     ebx, dword ptr [rsp+68h+arg_8]
0x180006b91  xor     edi, edi
0x180006b93  test    ebx, ebx
0x180006b95  js      loc_180006C51
0x180006b9b  mov     r14, [rsp+68h+arg_0]
0x180006ba0  mov     rsi, [rsp+68h+arg_10]
0x180006ba8  mov     rcx, [rsi]; this
0x180006bab  call    ?Initialize@CAxisUrlCache@@QEAAJXZ; CAxisUrlCache::Initialize(void)
0x180006bb0  mov     ebx, eax
0x180006bb2  test    eax, eax
0x180006bb4  js      loc_180006C51
0x180006bba  cmp     di, cs:PathName
0x180006bc1  jz      loc_180006C4C
0x180006bc7  lea     rcx, PathName; lpPathName
0x180006bce  call    ?CreateFolder@Utils@@SAJPEAG@Z; Utils::CreateFolder(ushort *)
0x180006bd3  mov     ebx, eax
0x180006bd5  test    eax, eax
0x180006bd7  js      short loc_180006C51
0x180006bd9  lea     rdx, [r14+48h]; unsigned __int16 *
0x180006bdd  lea     rcx, PathName; unsigned __int16 *
0x180006be4  call    ?CreateTempFolder@Utils@@SAJPEBGPEAGK@Z; Utils::CreateTempFolder(ushort const *,ushort *,ulong)
0x180006be9  mov     ebx, eax
0x180006beb  test    eax, eax
0x180006bed  js      short loc_180006C51
0x180006bef  lea     rsi, [r14+2A8h]
0x180006bf6  mov     rdx, rsi; void **
0x180006bf9  call    ?GetClientsToken@CAxInstaller@@AEAAJPEAPEAX@Z; CAxInstaller::GetClientsToken(void * *)
0x180006bfe  mov     ebx, eax
0x180006c00  test    eax, eax
0x180006c02  js      short loc_180006C51
0x180006c04  mov     ebx, edi
0x180006c06  mov     dword ptr [rsp+68h+arg_0], 4
0x180006c0e  lea     r8, [r14+29Ch]; TokenInformation
0x180006c15  lea     rax, [rsp+68h+arg_0]
0x180006c1a  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x180006c1f  mov     edx, 0Ch; TokenInformationClass
0x180006c24  lea     r9d, [rdx-8]; TokenInformationLength
0x180006c28  mov     rcx, [rsi]; TokenHandle
0x180006c2b  call    cs:__imp_GetTokenInformation
0x180006c31  test    eax, eax
0x180006c33  jnz     short loc_180006C51
0x180006c35  call    cs:__imp_GetLastError
0x180006c3b  mov     ebx, eax
0x180006c3d  test    eax, eax
0x180006c3f  jle     short loc_180006C51
0x180006c41  movzx   ebx, ax
0x180006c44  or      ebx, 80070000h
0x180006c4a  jmp     short loc_180006C51
0x180006c4c  mov     ebx, 80004005h
0x180006c51  mov     eax, ebx
0x180006c53  add     rsp, 48h
0x180006c57  pop     r14
0x180006c59  pop     rdi
0x180006c5a  pop     rsi
0x180006c5b  pop     rbx
0x180006c5c  retn
```
