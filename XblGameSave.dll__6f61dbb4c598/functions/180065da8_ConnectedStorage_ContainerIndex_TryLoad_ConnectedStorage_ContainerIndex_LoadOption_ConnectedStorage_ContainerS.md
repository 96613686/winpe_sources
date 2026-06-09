# ConnectedStorage::ContainerIndex::TryLoad(ConnectedStorage::ContainerIndex::LoadOption,ConnectedStorage::ContainerSyncTrackingFlag)

- ea: `0x180065da8`
- end: `0x180065ff5`
- name: `?TryLoad@ContainerIndex@ConnectedStorage@@AEBA_NW4LoadOption@12@W4ContainerSyncTrackingFlag@2@@Z`
- size: `589`
- prototype: `char __fastcall(__int64, int, char *)`
- caller_count: `2`
- callee_count: `15`
- tags: ``

## callers

- `0x180064c00`
- `0x180064df4`

## callees

- `0x180003c70`
- `0x18000cb9c`
- `0x180011040`
- `0x18001b9c8`
- `0x1800313e4`
- `0x18004ec4c`
- `0x18004edb0`
- `0x18004f73c`
- `0x18005b02c`
- `0x180063888`
- `0x1800638dc`
- `0x180064c74`
- `0x180064d14`
- `0x180065da8`
- `0x1800663d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180065ed9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180065f2a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180065fbf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180065fd0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180065ed9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180065f2a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180065fbf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180065fd0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065eba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065f0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065fa0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065eba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065f0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065fa0`

## pseudocode

```c
char __fastcall ConnectedStorage::ContainerIndex::TryLoad(__int64 a1, int a2, char *a3)
{
  int v3; // esi
  const unsigned __int16 *v6; // rcx
  const unsigned __int16 *v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // rax
  __int64 v12; // r8
  unsigned int v13; // r8d
  char result; // al
  __int64 v15; // [rsp+30h] [rbp-2F8h] BYREF
  int v16; // [rsp+38h] [rbp-2F0h]
  HSTRING string; // [rsp+40h] [rbp-2E8h]
  __int64 v18; // [rsp+48h] [rbp-2E0h]
  __int64 v19; // [rsp+50h] [rbp-2D8h] BYREF
  HSTRING newString[2]; // [rsp+58h] [rbp-2D0h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+68h] [rbp-2C0h] BYREF
  _BYTE v22[24]; // [rsp+78h] [rbp-2B0h] BYREF
  void *v23[76]; // [rsp+90h] [rbp-298h] BYREF

  v3 = (int)a3;
  ((void (__stdcall *)(ConnectedStorage::Mutex::Lock *, struct ConnectedStorage::Mutex *, char *))ConnectedStorage::Mutex::Lock::Lock)(
    (ConnectedStorage::Mutex::Lock *)lpCriticalSection,
    (struct ConnectedStorage::Mutex *)(a1 + 64),
    a3);
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 32);
  v6 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
  if ( !ConnectedStorage::File::Exists(v6, v7) )
    goto LABEL_8;
  v19 = 0;
  *(_OWORD *)newString = 0;
  v16 = 0;
  string = 0;
  v18 = 0;
  v15 = 0;
  ((void (__fastcall *)(_BYTE *, __int64, __int64, __int64))std::vector<ConnectedStorage::MultiFileWrite::Entry>::vector<ConnectedStorage::MultiFileWrite::Entry>)(
    v22,
    v8,
    v9,
    v10);
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 32);
  v11 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    ConnectedStorage::File::File((__int64)v23, v11, v12, 0, 0);
    ConnectedStorage::LoadContainerIndexMetaData(v23, (unsigned int *)&v19, newString, (char *)&v15);
    if ( a2 == 1 && ((v16 & 1) != 0 || (v16 & 0x10) != 0) )
    {
      ConnectedStorage::File::~File((ConnectedStorage::File *)v23);
      std::vector<std::unique_ptr<ConnectedStorage::ContainerIndexEntry>>::~vector<std::unique_ptr<ConnectedStorage::ContainerIndexEntry>>(v22);
      WindowsDeleteString(string);
      string = 0;
      ConnectedStorage::ContainerIndexMetaData::~ContainerIndexMetaData((ConnectedStorage::ContainerIndexMetaData *)newString);
      LeaveCriticalSection(lpCriticalSection[0]);
      result = 0;
    }
    else
    {
      ConnectedStorage::LoadContainerIndexEntries(v23, (unsigned int *)&v19, (__int64)v22, v3);
      std::swap<ConnectedStorage::ContainerIndexMetaData,0>(newString, a1 + 112);
      ((void (__fastcall *)(__int64 *, __int64))std::swap<ConnectedStorage::ContainerIndexSyncMetaData,0>)(
        &v15,
        a1 + 128);
      std::vector<std::unique_ptr<ConnectedStorage::ContainerIndexEntry>>::swap(v22, a1 + 160);
      ConnectedStorage::File::~File((ConnectedStorage::File *)v23);
      std::vector<std::unique_ptr<ConnectedStorage::ContainerIndexEntry>>::~vector<std::unique_ptr<ConnectedStorage::ContainerIndexEntry>>(v22);
      WindowsDeleteString(string);
      string = 0;
      ConnectedStorage::ContainerIndexMetaData::~ContainerIndexMetaData((ConnectedStorage::ContainerIndexMetaData *)newString);
      LeaveCriticalSection(lpCriticalSection[0]);
      result = 1;
    }
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &ConnectedStorage::CorruptIndexFileException `RTTI Type Descriptor', 0) )
    {
      ConnectedStorage::EventWriteInternalError(
        (ConnectedStorage *)L"ContainerIndex corrupt index",
        (const unsigned __int16 *const)0x80832010LL,
        v13);
      __eh34_try_continuation(0, &ConnectedStorage::CorruptIndexFileException `RTTI Type Descriptor', &loc_180065FC9);
LABEL_8:
      LeaveCriticalSection(lpCriticalSection[0]);
      return 0;
    }
    if ( __eh34_catch_type(0, &ConnectedStorage::File::EofException `RTTI Type Descriptor', 0) )
    {
      ConnectedStorage::EventWriteInternalError(
        (ConnectedStorage *)L"ContainerIndex corrupt eof",
        (const unsigned __int16 *const)0x80832010LL,
        v13);
      __eh34_try_continuation(0, &ConnectedStorage::File::EofException `RTTI Type Descriptor', &loc_180065FCB);
      goto LABEL_8;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180065da8  push    rbx
0x180065daa  push    rsi
0x180065dab  push    rdi
0x180065dac  push    r14
0x180065dae  sub     rsp, 308h
0x180065db5  mov     rax, cs:__security_cookie
0x180065dbc  xor     rax, rsp
0x180065dbf  mov     [rsp+328h+var_38], rax
0x180065dc7  mov     esi, r8d
0x180065dca  mov     edi, edx
0x180065dcc  mov     rbx, rcx
0x180065dcf  lea     rdx, [rcx+40h]; struct ConnectedStorage::Mutex *
0x180065dd3  lea     rcx, [rsp+328h+lpCriticalSection]; this
0x180065dd8  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x180065ddd  nop
0x180065dde  lea     rcx, [rbx+20h]
0x180065de2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180065de7  mov     rdx, rax
0x180065dea  mov     rcx, rbx
0x180065ded  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180065df2  mov     rcx, rax; unsigned __int16 *
0x180065df5  call    ?Exists@File@ConnectedStorage@@SA_NPEBG0@Z; ConnectedStorage::File::Exists(ushort const *,ushort const *)
0x180065dfa  test    al, al
0x180065dfc  jz      loc_180065FCB
0x180065e02  mov     [rsp+328h+var_2D8], 0
0x180065e0b  xorps   xmm0, xmm0
0x180065e0e  movdqu  xmmword ptr [rsp+328h+newString], xmm0
0x180065e14  mov     [rsp+328h+var_2F0], 0
0x180065e1c  mov     [rsp+328h+string], 0
0x180065e25  mov     [rsp+328h+var_2E0], 0
0x180065e2e  xor     eax, eax
0x180065e30  mov     [rsp+328h+var_2F8], rax
0x180065e35  lea     rcx, [rsp+328h+var_2B0]
0x180065e3a  call    ??0?$vector@UEntry@MultiFileWrite@ConnectedStorage@@V?$allocator@UEntry@MultiFileWrite@ConnectedStorage@@@std@@@std@@QEAA@XZ; std::vector<ConnectedStorage::MultiFileWrite::Entry>::vector<ConnectedStorage::MultiFileWrite::Entry>(void)
0x180065e3f  nop
0x180065e40  lea     rcx, [rbx+20h]
0x180065e44  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180065e49  mov     r8, rax
0x180065e4c  mov     rcx, rbx
0x180065e4f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180065e54  mov     [rsp+328h+var_308], 0
0x180065e5c  xor     r9d, r9d
0x180065e5f  mov     rdx, rax
0x180065e62  lea     rcx, [rsp+328h+var_298]
0x180065e6a  call    ??0File@ConnectedStorage@@QEAA@PEBG0W4Access@01@W4CloseBehavior@01@@Z; ConnectedStorage::File::File(ushort const *,ushort const *,ConnectedStorage::File::Access,ConnectedStorage::File::CloseBehavior)
0x180065e6f  nop
0x180065e70  lea     r9, [rsp+328h+var_2F8]; void *
0x180065e75  lea     r8, [rsp+328h+newString]; newString
0x180065e7a  lea     rdx, [rsp+328h+var_2D8]; void *
0x180065e7f  lea     rcx, [rsp+328h+var_298]; this
0x180065e87  call    ConnectedStorage__LoadContainerIndexMetaData
0x180065e8c  cmp     edi, 1
0x180065e8f  jnz     loc_180065F37
0x180065e95  test    byte ptr [rsp+328h+var_2F0], dil
0x180065e9a  jz      short loc_180065EE6
0x180065e9c  lea     rcx, [rsp+328h+var_298]; this
0x180065ea4  call    ??1File@ConnectedStorage@@QEAA@XZ; ConnectedStorage::File::~File(void)
0x180065ea9  nop
0x180065eaa  lea     rcx, [rsp+328h+var_2B0]
0x180065eaf  call    ??1?$vector@V?$unique_ptr@VContainerIndexEntry@ConnectedStorage@@U?$default_delete@VContainerIndexEntry@ConnectedStorage@@@std@@@std@@V?$allocator@V?$unique_ptr@VContainerIndexEntry@ConnectedStorage@@U?$default_delete@VContainerIndexEntry@ConnectedStorage@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<ConnectedStorage::ContainerIndexEntry>>::~vector<std::unique_ptr<ConnectedStorage::ContainerIndexEntry>>(void)
0x180065eb4  nop
0x180065eb5  mov     rcx, [rsp+328h+string]; string
0x180065eba  call    cs:__imp_WindowsDeleteString
0x180065ec0  mov     [rsp+328h+string], 0
0x180065ec9  lea     rcx, [rsp+328h+newString]; this
0x180065ece  call    ??1ContainerIndexMetaData@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ContainerIndexMetaData::~ContainerIndexMetaData(void)
0x180065ed3  nop
0x180065ed4  mov     rcx, [rsp+328h+lpCriticalSection]; lpCriticalSection
0x180065ed9  call    cs:__imp_LeaveCriticalSection
0x180065edf  xor     al, al
0x180065ee1  jmp     loc_180065FD8
0x180065ee6  test    byte ptr [rsp+328h+var_2F0], 10h
0x180065eeb  jz      short loc_180065F37
0x180065eed  lea     rcx, [rsp+328h+var_298]; this
0x180065ef5  call    ??1File@ConnectedStorage@@QEAA@XZ; ConnectedStorage::File::~File(void)
0x180065efa  nop
0x180065efb  lea     rcx, [rsp+328h+var_2B0]
0x180065f00  call    ??1?$vector@V?$unique_ptr@VContainerIndexEntry@ConnectedStorage@@U?$default_delete@VContainerIndexEntry@ConnectedStorage@@@std@@@std@@V?$allocator@V?$unique_ptr@VContainerIndexEntry@ConnectedStorage@@U?$default_delete@VContainerIndexEntry@ConnectedStorage@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<ConnectedStorage::ContainerIndexEntry>>::~vector<std::unique_ptr<ConnectedStorage::ContainerIndexEntry>>(void)
0x180065f05  nop
0x180065f06  mov     rcx, [rsp+328h+string]; string
0x180065f0b  call    cs:__imp_WindowsDeleteString
0x180065f11  mov     [rsp+328h+string], 0
0x180065f1a  lea     rcx, [rsp+328h+newString]; this
0x180065f1f  call    ??1ContainerIndexMetaData@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ContainerIndexMetaData::~ContainerIndexMetaData(void)
0x180065f24  nop
0x180065f25  mov     rcx, [rsp+328h+lpCriticalSection]; lpCriticalSection
0x180065f2a  call    cs:__imp_LeaveCriticalSection
0x180065f30  xor     al, al
0x180065f32  jmp     loc_180065FD8
0x180065f37  mov     r9d, esi
0x180065f3a  lea     r8, [rsp+328h+var_2B0]
0x180065f3f  lea     rdx, [rsp+328h+var_2D8]
0x180065f44  lea     rcx, [rsp+328h+var_298]; this
0x180065f4c  call    ConnectedStorage__LoadContainerIndexEntries
0x180065f51  lea     rdx, [rbx+70h]
0x180065f55  lea     rcx, [rsp+328h+newString]
0x180065f5a  call    ??$swap@UContainerIndexMetaData@ConnectedStorage@@$0A@@std@@YAXAEAUContainerIndexMetaData@ConnectedStorage@@0@Z; std::swap<ConnectedStorage::ContainerIndexMetaData,0>(ConnectedStorage::ContainerIndexMetaData &,ConnectedStorage::ContainerIndexMetaData &)
0x180065f5f  lea     rdx, [rbx+80h]
0x180065f66  lea     rcx, [rsp+328h+var_2F8]
0x180065f6b  call    ??$swap@UContainerIndexSyncMetaData@ConnectedStorage@@$0A@@std@@YAXAEAUContainerIndexSyncMetaData@ConnectedStorage@@0@Z; std::swap<ConnectedStorage::ContainerIndexSyncMetaData,0>(ConnectedStorage::ContainerIndexSyncMetaData &,ConnectedStorage::ContainerIndexSyncMetaData &)
0x180065f70  lea     rdx, [rbx+0A0h]
0x180065f77  lea     rcx, [rsp+328h+var_2B0]
0x180065f7c  call    ?swap@?$vector@V?$unique_ptr@VContainerIndexEntry@ConnectedStorage@@U?$default_delete@VContainerIndexEntry@ConnectedStorage@@@std@@@std@@V?$allocator@V?$unique_ptr@VContainerIndexEntry@ConnectedStorage@@U?$default_delete@VContainerIndexEntry@ConnectedStorage@@@std@@@std@@@2@@std@@QEAAXAEAV12@@Z; std::vector<std::unique_ptr<ConnectedStorage::ContainerIndexEntry>>::swap(std::vector<std::unique_ptr<ConnectedStorage::ContainerIndexEntry>> &)
0x180065f81  nop
0x180065f82  lea     rcx, [rsp+328h+var_298]; this
0x180065f8a  call    ??1File@ConnectedStorage@@QEAA@XZ; ConnectedStorage::File::~File(void)
0x180065f8f  nop
0x180065f90  lea     rcx, [rsp+328h+var_2B0]
0x180065f95  call    ??1?$vector@V?$unique_ptr@VContainerIndexEntry@ConnectedStorage@@U?$default_delete@VContainerIndexEntry@ConnectedStorage@@@std@@@std@@V?$allocator@V?$unique_ptr@VContainerIndexEntry@ConnectedStorage@@U?$default_delete@VContainerIndexEntry@ConnectedStorage@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<ConnectedStorage::ContainerIndexEntry>>::~vector<std::unique_ptr<ConnectedStorage::ContainerIndexEntry>>(void)
0x180065f9a  nop
0x180065f9b  mov     rcx, [rsp+328h+string]; string
0x180065fa0  call    cs:__imp_WindowsDeleteString
0x180065fa6  mov     [rsp+328h+string], 0
0x180065faf  lea     rcx, [rsp+328h+newString]; this
0x180065fb4  call    ??1ContainerIndexMetaData@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ContainerIndexMetaData::~ContainerIndexMetaData(void)
0x180065fb9  nop
0x180065fba  mov     rcx, [rsp+328h+lpCriticalSection]; lpCriticalSection
0x180065fbf  call    cs:__imp_LeaveCriticalSection
0x180065fc5  mov     al, 1
0x180065fc7  jmp     short loc_180065FD8
0x180065fc9  jmp     short $+2
0x180065fcb  mov     rcx, [rsp+328h+lpCriticalSection]; lpCriticalSection
0x180065fd0  call    cs:__imp_LeaveCriticalSection
0x180065fd6  xor     al, al
0x180065fd8  mov     rcx, [rsp+328h+var_38]
0x180065fe0  xor     rcx, rsp; StackCookie
0x180065fe3  call    __security_check_cookie
0x180065fe8  add     rsp, 308h
0x180065fef  pop     r14
0x180065ff1  pop     rdi
0x180065ff2  pop     rsi
0x180065ff3  pop     rbx
0x180065ff4  retn
```
