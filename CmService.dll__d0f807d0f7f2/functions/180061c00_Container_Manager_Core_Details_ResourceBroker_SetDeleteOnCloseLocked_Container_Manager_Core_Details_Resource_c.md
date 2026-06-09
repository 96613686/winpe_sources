# Container::Manager::Core::Details::ResourceBroker::SetDeleteOnCloseLocked(Container::Manager::Core::Details::Resource const &,bool,bool,Csl::SrwLock::ReleaseOnScopeExit<0> &,void *)

- ea: `0x180061c00`
- end: `0x180062024`
- name: `?SetDeleteOnCloseLocked@ResourceBroker@Details@Core@Manager@Container@@AEAAJAEBVResource@2345@_N1AEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@PEAX@Z`
- size: `1060`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180061ae4`
- `0x18006202c`

## callees

- `0x18000a10c`
- `0x18000da88`
- `0x18000dad8`
- `0x180016718`
- `0x1800335b8`
- `0x18003ed4c`
- `0x18005ce8c`
- `0x180061c00`
- `0x180087b80`
- `0x1800cc220`
- `0x1800e1f94`
- `0x1800ea808`
- `0x1800eeea0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180061d25`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180061e87`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180061d25`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180061e87`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180061d7d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180061dc2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180061e0b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180061e47`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180061ebf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180061f97`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180061d7d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180061dc2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180061e0b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180061e47`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180061ebf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180061f97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180061e93`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180061e93`

## string_xrefs

- `0x180061fb6`: `onecore\base\gendrv\silos\clem\core\lib\ResourceBroker.h`
- `0x180061fcd`: `onecore\base\gendrv\silos\clem\core\lib\ResourceBroker.h`
- `0x180061fe4`: `onecore\base\gendrv\silos\clem\core\lib\ResourceBroker.h`
- `0x180061ffb`: `onecore\base\gendrv\silos\clem\core\lib\ResourceBroker.h`
- `0x180062012`: `onecore\base\gendrv\silos\clem\core\lib\ResourceBroker.h`
- `0x180061c76`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x180061de8`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x180061e6c`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x180061f7a`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`

## pseudocode

```c
int __fastcall Container::Manager::Core::Details::ResourceBroker::SetDeleteOnCloseLocked(
        __int64 a1,
        __int64 a2,
        bool a3,
        char a4,
        char *a5,
        void *a6)
{
  const char *v10; // r9
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v14; // rbx
  __int64 v15; // rdi
  int v16; // ebx
  __int64 v17; // rdx
  __int64 v18; // rdi
  RTL_SRWLOCK *v19; // rbx
  int v20; // edx
  int v21; // eax
  unsigned int v22; // edi
  __int64 v23; // rdx
  int v24; // eax
  __int64 v25; // rcx
  int v26; // eax
  __int64 v27; // rcx
  unsigned int v28[2]; // [rsp+20h] [rbp-38h] BYREF
  char v29; // [rsp+28h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( Container::Manager::Core::Details::Resource::IsDeleteOnClose((Container::Manager::Core::Details::Resource *)a2) == a3 )
    return 0;
  if ( a4 )
  {
    if ( a3 )
    {
LABEL_18:
      switch ( *(_DWORD *)(a2 + 16) )
      {
        case 1:
          if ( !*(_BYTE *)(a2 + 40) )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x5D,
              (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\ResourceBroker.h",
              v10);
          v16 = Container::Manager::Core::Details::ContainerStorage::SetDeleteOnClose(
                  *(Container::Manager::Core::Details::ContainerStorage **)(a2 + 32),
                  a3,
                  a6);
          if ( v16 < 0 )
          {
            v17 = 6277;
            goto LABEL_58;
          }
          break;
        case 2:
          if ( !*(_BYTE *)(a2 + 56) )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x56,
              (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\ResourceBroker.h",
              v10);
          v16 = Container::Manager::Core::Details::Layer::SetDeleteOnClose(
                  *(Container::Manager::Core::Details::Layer **)(a2 + 48),
                  a3,
                  a6);
          if ( v16 < 0 )
          {
            v17 = 6285;
            goto LABEL_58;
          }
          break;
        case 3:
          if ( !*(_BYTE *)(a2 + 72) )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x64,
              (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\ResourceBroker.h",
              v10);
          v16 = Container::Manager::Core::Details::Snapshot::SetDeleteOnClose(*(PSRWLOCK *)(a2 + 64), a3, a6);
          if ( v16 < 0 )
          {
            v17 = 6293;
            goto LABEL_58;
          }
          break;
        case 4:
          if ( !*(_BYTE *)(a2 + 88) )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x6B,
              (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\ResourceBroker.h",
              v10);
          Container::Manager::Core::Details::Zygote::SetDeleteOnClose(*(PSRWLOCK *)(a2 + 80), a3);
          break;
        case 5:
          if ( !*(_BYTE *)(a2 + 104) )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x72,
              (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\ResourceBroker.h",
              v10);
          v18 = *(_QWORD *)(a2 + 96);
          v19 = (RTL_SRWLOCK *)(v18 + 128);
          AcquireSRWLockExclusive((PSRWLOCK)(v18 + 128));
          v20 = *(_DWORD *)(v18 + 140);
          if ( a3 )
          {
            v21 = Container::Manager::Core::Details::BaseImage::SetFlagsLocked(v18, v20 | 1u, a6);
            v22 = v21;
            if ( v21 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x30E,
                (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\baseimage.cpp",
                (const char *)(unsigned int)v21,
                v28[0]);
              if ( v19 )
                ReleaseSRWLockExclusive(v19);
              v23 = 645;
LABEL_34:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v23,
                (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\baseimage.cpp",
                (const char *)v22,
                v28[0]);
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x18A7,
                (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
                (const char *)v22,
                v28[0]);
              return v22;
            }
          }
          else
          {
            v24 = Container::Manager::Core::Details::BaseImage::SetFlagsLocked(v18, v20 & 0xFFFFFFFE, a6);
            v22 = v24;
            if ( v24 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x321,
                (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\baseimage.cpp",
                (const char *)(unsigned int)v24,
                v28[0]);
              if ( v19 )
                ReleaseSRWLockExclusive(v19);
              v23 = 650;
              goto LABEL_34;
            }
          }
          if ( v19 )
            ReleaseSRWLockExclusive(v19);
          break;
        default:
          v16 = -2147467259;
          v17 = 6318;
LABEL_58:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v17,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
            (const char *)(unsigned int)v16,
            v28[0]);
          return v16;
      }
      if ( *(_DWORD *)(a2 + 16) != 4 && !a6 )
      {
        v25 = *(_QWORD *)a5;
        if ( *(_QWORD *)a5 )
        {
          *(_DWORD *)(v25 + 8) = 0;
          ReleaseSRWLockExclusive((PSRWLOCK)v25);
          *(_QWORD *)a5 = 0;
        }
        v26 = Csl::RegistryKey::Flush((Csl::RegistryKey *)(a1 + 8));
        if ( v26 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x18C6,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
            (const char *)(unsigned int)v26,
            v28[0]);
        AcquireSRWLockExclusive((PSRWLOCK)(a1 + 16));
        *(_DWORD *)(a1 + 24) = GetCurrentThreadId();
        if ( a5 == &v29 )
        {
          *(_DWORD *)(a1 + 24) = 0;
          ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 16));
        }
        else
        {
          v27 = *(_QWORD *)a5;
          if ( *(_QWORD *)a5 )
          {
            *(_DWORD *)(v27 + 8) = 0;
            ReleaseSRWLockExclusive((PSRWLOCK)v27);
          }
          *(_QWORD *)a5 = a1 + 16;
        }
      }
      return 0;
    }
  }
  else
  {
    if ( a3 )
    {
      v11 = *(_QWORD *)(a2 + 232);
      *(_QWORD *)v28 = v11;
      while ( v11 != a2 + 216 )
      {
        if ( !Container::Manager::Core::Details::Resource::IsDeleteOnClose(*(Container::Manager::Core::Details::Resource **)(v11 + 24)) )
        {
          v12 = 6242;
          return wil::details::in1diag3::Return_Win32(
                   retaddr,
                   (void *)v12,
                   (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
                   (const char *)0x1724,
                   v28[0]);
        }
        utl::_TreeConstIt<Container::Manager::Core::Details::Resource *>::operator++(v28);
        v11 = *(_QWORD *)v28;
      }
      goto LABEL_18;
    }
    v14 = *(_QWORD *)(a2 + 192);
    v15 = *(_QWORD *)(a2 + 200);
    while ( v14 != v15 )
    {
      if ( Container::Manager::Core::Details::Resource::IsDeleteOnClose(*(Container::Manager::Core::Details::Resource **)(*(_QWORD *)v14 + 40LL)) )
      {
        v12 = 6254;
        return wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)v12,
                 (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
                 (const char *)0x1724,
                 v28[0]);
      }
      v14 += 8;
    }
  }
  if ( !*(_BYTE *)(a2 + 256) )
    goto LABEL_18;
  v12 = 6267;
  return wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v12,
           (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
           (const char *)0x1724,
           v28[0]);
}

```

## disassembly

```asm
0x180061c00  push    rbx
0x180061c02  push    rbp
0x180061c03  push    rsi
0x180061c04  push    rdi
0x180061c05  push    r15
0x180061c07  sub     rsp, 30h
0x180061c0b  mov     r15, rcx
0x180061c0e  mov     bl, r9b
0x180061c11  mov     rcx, rdx; this
0x180061c14  mov     bpl, r8b
0x180061c17  mov     rsi, rdx
0x180061c1a  call    ?IsDeleteOnClose@Resource@Details@Core@Manager@Container@@AEBA_NXZ; Container::Manager::Core::Details::Resource::IsDeleteOnClose(void)
0x180061c1f  cmp     al, bpl
0x180061c22  jz      loc_180061FA3
0x180061c28  test    bl, bl
0x180061c2a  jnz     loc_180061CBD
0x180061c30  test    bpl, bpl
0x180061c33  jz      short loc_180061C8D
0x180061c35  lea     rbx, [rsi+0D8h]
0x180061c3c  mov     rcx, [rbx+10h]
0x180061c40  mov     qword ptr [rsp+58h+var_38], rcx; int
0x180061c45  cmp     rcx, rbx
0x180061c48  jz      loc_180061CD2
0x180061c4e  mov     rcx, [rcx+18h]; this
0x180061c52  call    ?IsDeleteOnClose@Resource@Details@Core@Manager@Container@@AEBA_NXZ; Container::Manager::Core::Details::Resource::IsDeleteOnClose(void)
0x180061c57  test    al, al
0x180061c59  jz      short loc_180061C6C
0x180061c5b  lea     rcx, [rsp+58h+var_38]
0x180061c60  call    ??E?$_TreeConstIt@PEAVResource@Details@Core@Manager@Container@@@utl@@QEAAAEAV01@XZ; utl::_TreeConstIt<Container::Manager::Core::Details::Resource *>::operator++(void)
0x180061c65  mov     rcx, qword ptr [rsp+58h+var_38]
0x180061c6a  jmp     short loc_180061C45
0x180061c6c  mov     edx, 1862h; void *
0x180061c71  mov     rcx, [rsp+58h]; this
0x180061c76  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180061c7d  mov     r9d, 1724h; char *
0x180061c83  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180061c88  jmp     loc_180061FA5
0x180061c8d  mov     rbx, [rsi+0C0h]
0x180061c94  mov     rdi, [rsi+0C8h]
0x180061c9b  cmp     rbx, rdi
0x180061c9e  jz      short loc_180061CC2
0x180061ca0  mov     rcx, [rbx]
0x180061ca3  mov     rcx, [rcx+28h]; this
0x180061ca7  call    ?IsDeleteOnClose@Resource@Details@Core@Manager@Container@@AEBA_NXZ; Container::Manager::Core::Details::Resource::IsDeleteOnClose(void)
0x180061cac  test    al, al
0x180061cae  jnz     short loc_180061CB6
0x180061cb0  add     rbx, 8
0x180061cb4  jmp     short loc_180061C9B
0x180061cb6  mov     edx, 186Eh
0x180061cbb  jmp     short loc_180061C71
0x180061cbd  test    bpl, bpl
0x180061cc0  jnz     short loc_180061CD2
0x180061cc2  cmp     byte ptr [rsi+100h], 0
0x180061cc9  jz      short loc_180061CD2
0x180061ccb  mov     edx, 187Bh
0x180061cd0  jmp     short loc_180061C71
0x180061cd2  mov     ecx, [rsi+10h]
0x180061cd5  sub     ecx, 1
0x180061cd8  jz      loc_180061F4C
0x180061cde  sub     ecx, 1
0x180061ce1  jz      loc_180061F1D
0x180061ce7  sub     ecx, 1
0x180061cea  jz      loc_180061EEE
0x180061cf0  sub     ecx, 1
0x180061cf3  jz      loc_180061ED3
0x180061cf9  cmp     ecx, 1
0x180061cfc  jz      short loc_180061D0D
0x180061cfe  mov     ebx, 80004005h
0x180061d03  mov     edx, 18AEh
0x180061d08  jmp     loc_180061F75
0x180061d0d  cmp     byte ptr [rsi+68h], 0
0x180061d11  jz      loc_180061FC8
0x180061d17  mov     rdi, [rsi+60h]
0x180061d1b  lea     rbx, [rdi+80h]
0x180061d22  mov     rcx, rbx; SRWLock
0x180061d25  call    cs:__imp_AcquireSRWLockExclusive
0x180061d2c  nop     dword ptr [rax+rax+00h]
0x180061d31  mov     edx, [rdi+8Ch]
0x180061d37  mov     rcx, rdi
0x180061d3a  mov     r8, [rsp+58h+arg_28]
0x180061d42  test    bpl, bpl
0x180061d45  jz      short loc_180061D90
0x180061d47  or      edx, 1
0x180061d4a  call    ?SetFlagsLocked@BaseImage@Details@Core@Manager@Container@@AEAAJW4BaseImageFlags@2345@PEAX@Z; Container::Manager::Core::Details::BaseImage::SetFlagsLocked(Container::Manager::Core::Details::BaseImageFlags,void *)
0x180061d4f  mov     edi, eax
0x180061d51  test    eax, eax
0x180061d53  jns     loc_180061E03
0x180061d59  mov     rcx, [rsp+58h]; this
0x180061d5e  lea     rsi, aOnecoreBaseGen_31; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180061d65  mov     r8, rsi; unsigned int
0x180061d68  mov     r9d, eax; char *
0x180061d6b  mov     edx, 30Eh; void *
0x180061d70  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180061d75  test    rbx, rbx
0x180061d78  jz      short loc_180061D89
0x180061d7a  mov     rcx, rbx; SRWLock
0x180061d7d  call    cs:__imp_ReleaseSRWLockExclusive
0x180061d84  nop     dword ptr [rax+rax+00h]
0x180061d89  mov     edx, 285h
0x180061d8e  jmp     short loc_180061DD3
0x180061d90  and     edx, 0FFFFFFFEh
0x180061d93  call    ?SetFlagsLocked@BaseImage@Details@Core@Manager@Container@@AEAAJW4BaseImageFlags@2345@PEAX@Z; Container::Manager::Core::Details::BaseImage::SetFlagsLocked(Container::Manager::Core::Details::BaseImageFlags,void *)
0x180061d98  mov     edi, eax
0x180061d9a  test    eax, eax
0x180061d9c  jns     short loc_180061E03
0x180061d9e  mov     rcx, [rsp+58h]; this
0x180061da3  lea     rsi, aOnecoreBaseGen_31; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180061daa  mov     r8, rsi; unsigned int
0x180061dad  mov     r9d, eax; char *
0x180061db0  mov     edx, 321h; void *
0x180061db5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180061dba  test    rbx, rbx
0x180061dbd  jz      short loc_180061DCE
0x180061dbf  mov     rcx, rbx; SRWLock
0x180061dc2  call    cs:__imp_ReleaseSRWLockExclusive
0x180061dc9  nop     dword ptr [rax+rax+00h]
0x180061dce  mov     edx, 28Ah; void *
0x180061dd3  mov     rcx, [rsp+58h]; this
0x180061dd8  mov     r9d, edi; char *
0x180061ddb  mov     r8, rsi; unsigned int
0x180061dde  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180061de3  mov     rcx, [rsp+58h]; this
0x180061de8  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180061def  mov     r9d, edi; char *
0x180061df2  mov     edx, 18A7h; void *
0x180061df7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180061dfc  mov     eax, edi
0x180061dfe  jmp     loc_180061FA5
0x180061e03  test    rbx, rbx
0x180061e06  jz      short loc_180061E17
0x180061e08  mov     rcx, rbx; SRWLock
0x180061e0b  call    cs:__imp_ReleaseSRWLockExclusive
0x180061e12  nop     dword ptr [rax+rax+00h]
0x180061e17  cmp     dword ptr [rsi+10h], 4
0x180061e1b  jz      loc_180061FA3
0x180061e21  cmp     [rsp+58h+arg_28], 0
0x180061e2a  jnz     loc_180061FA3
0x180061e30  mov     rbx, [rsp+58h+arg_20]
0x180061e38  mov     rcx, [rbx]; SRWLock
0x180061e3b  test    rcx, rcx
0x180061e3e  jz      short loc_180061E5A
0x180061e40  mov     dword ptr [rcx+8], 0
0x180061e47  call    cs:__imp_ReleaseSRWLockExclusive
0x180061e4e  nop     dword ptr [rax+rax+00h]
0x180061e53  mov     qword ptr [rbx], 0
0x180061e5a  lea     rcx, [r15+8]; this
0x180061e5e  call    ?Flush@RegistryKey@Csl@@QEBAJXZ; Csl::RegistryKey::Flush(void)
0x180061e63  test    eax, eax
0x180061e65  jns     short loc_180061E80
0x180061e67  mov     rcx, [rsp+58h]; this
0x180061e6c  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180061e73  mov     r9d, eax; char *
0x180061e76  mov     edx, 18C6h; void *
0x180061e7b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180061e80  lea     rdi, [r15+10h]
0x180061e84  mov     rcx, rdi; SRWLock
0x180061e87  call    cs:__imp_AcquireSRWLockExclusive
0x180061e8e  nop     dword ptr [rax+rax+00h]
0x180061e93  call    cs:__imp_GetCurrentThreadId
0x180061e9a  nop     dword ptr [rax+rax+00h]
0x180061e9f  mov     [rdi+8], eax
0x180061ea2  lea     rax, [rsp+58h+var_30]
0x180061ea7  cmp     rbx, rax
0x180061eaa  jz      loc_180061F8D
0x180061eb0  mov     rcx, [rbx]; SRWLock
0x180061eb3  test    rcx, rcx
0x180061eb6  jz      short loc_180061ECB
0x180061eb8  mov     dword ptr [rcx+8], 0
0x180061ebf  call    cs:__imp_ReleaseSRWLockExclusive
0x180061ec6  nop     dword ptr [rax+rax+00h]
0x180061ecb  mov     [rbx], rdi
0x180061ece  jmp     loc_180061FA3
0x180061ed3  cmp     byte ptr [rsi+58h], 0
0x180061ed7  jz      loc_180061FDF
0x180061edd  mov     rcx, [rsi+50h]; SRWLock
0x180061ee1  mov     dl, bpl; bool
0x180061ee4  call    ?SetDeleteOnClose@Zygote@Details@Core@Manager@Container@@AEAAX_N@Z; Container::Manager::Core::Details::Zygote::SetDeleteOnClose(bool)
0x180061ee9  jmp     loc_180061E17
0x180061eee  cmp     byte ptr [rsi+48h], 0
0x180061ef2  jz      loc_180061FF6
0x180061ef8  mov     r8, [rsp+58h+arg_28]; void *
0x180061f00  mov     dl, bpl; bool
0x180061f03  mov     rcx, [rsi+40h]; SRWLock
0x180061f07  call    ?SetDeleteOnClose@Snapshot@Details@Core@Manager@Container@@AEAAJ_NPEAX@Z; Container::Manager::Core::Details::Snapshot::SetDeleteOnClose(bool,void *)
0x180061f0c  mov     ebx, eax
0x180061f0e  test    eax, eax
0x180061f10  jns     loc_180061E17
0x180061f16  mov     edx, 1895h
0x180061f1b  jmp     short loc_180061F75
0x180061f1d  cmp     byte ptr [rsi+38h], 0
0x180061f21  jz      loc_18006200D
0x180061f27  mov     r8, [rsp+58h+arg_28]; void *
0x180061f2f  mov     dl, bpl; bool
0x180061f32  mov     rcx, [rsi+30h]; this
0x180061f36  call    ?SetDeleteOnClose@Layer@Details@Core@Manager@Container@@AEAAJ_NPEAX@Z; Container::Manager::Core::Details::Layer::SetDeleteOnClose(bool,void *)
0x180061f3b  mov     ebx, eax
0x180061f3d  test    eax, eax
0x180061f3f  jns     loc_180061E17
0x180061f45  mov     edx, 188Dh
0x180061f4a  jmp     short loc_180061F75
0x180061f4c  cmp     byte ptr [rsi+28h], 0
0x180061f50  jz      short loc_180061FB1
0x180061f52  mov     r8, [rsp+58h+arg_28]; void *
0x180061f5a  mov     dl, bpl; bool
0x180061f5d  mov     rcx, [rsi+20h]; this
0x180061f61  call    ?SetDeleteOnClose@ContainerStorage@Details@Core@Manager@Container@@AEAAJ_NPEAX@Z; Container::Manager::Core::Details::ContainerStorage::SetDeleteOnClose(bool,void *)
0x180061f66  mov     ebx, eax
0x180061f68  test    eax, eax
0x180061f6a  jns     loc_180061E17
0x180061f70  mov     edx, 1885h; void *
0x180061f75  mov     rcx, [rsp+58h]; this
0x180061f7a  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180061f81  mov     r9d, ebx; char *
0x180061f84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180061f89  mov     eax, ebx
0x180061f8b  jmp     short loc_180061FA5
0x180061f8d  mov     rcx, rdi; SRWLock
0x180061f90  mov     dword ptr [rdi+8], 0
0x180061f97  call    cs:__imp_ReleaseSRWLockExclusive
0x180061f9e  nop     dword ptr [rax+rax+00h]
0x180061fa3  xor     eax, eax
0x180061fa5  add     rsp, 30h
0x180061fa9  pop     r15
0x180061fab  pop     rdi
0x180061fac  pop     rsi
0x180061fad  pop     rbp
0x180061fae  pop     rbx
0x180061faf  retn
0x180061fb1  mov     rcx, [rsp+58h]; this
0x180061fb6  lea     r8, aOnecoreBaseGen_26; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180061fbd  mov     edx, 5Dh ; ']'; void *
0x180061fc2  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180061fc8  mov     rcx, [rsp+58h]; this
0x180061fcd  lea     r8, aOnecoreBaseGen_26; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180061fd4  mov     edx, 72h ; 'r'; void *
0x180061fd9  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180061fdf  mov     rcx, [rsp+58h]; this
0x180061fe4  lea     r8, aOnecoreBaseGen_26; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180061feb  mov     edx, 6Bh ; 'k'; void *
0x180061ff0  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180061ff6  mov     rcx, [rsp+58h]; this
0x180061ffb  lea     r8, aOnecoreBaseGen_26; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180062002  mov     edx, 64h ; 'd'; void *
0x180062007  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18006200d  mov     rcx, [rsp+58h]; this
0x180062012  lea     r8, aOnecoreBaseGen_26; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180062019  mov     edx, 56h ; 'V'; void *
0x18006201e  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
