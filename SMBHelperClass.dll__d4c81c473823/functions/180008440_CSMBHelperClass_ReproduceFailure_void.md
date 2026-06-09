# CSMBHelperClass::ReproduceFailure(void)

- ea: `0x180008440`
- end: `0x1800088d0`
- name: `?ReproduceFailure@CSMBHelperClass@@UEAAJXZ`
- size: `1168`
- prototype: `__int64 __fastcall(CSMBHelperClass *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, loader_planting`

## callees

- `0x180004ee0`
- `0x180008214`
- `0x180008440`
- `0x180008b64`
- `0x18000d750`
- `0x18000dd04`
- `0x18000e10c`
- `0x18000fc30`
- `0x180012010`

## import_xrefs

- `msvcrt!_itow_s` at `0x18000888d`
- `msvcrt!_itow_s` at `0x18000888d`
- `ntdll!NtOpenFile` at `0x1800084f3`
- `ntdll!NtOpenFile` at `0x1800084f3`
- `ntdll!RtlInitUnicodeString` at `0x18000849b`
- `ntdll!RtlInitUnicodeString` at `0x18000849b`
- `ntdll!NtClose` at `0x18000854d`
- `ntdll!NtClose` at `0x18000854d`
- `ntdll!NtFsControlFile` at `0x18000853d`
- `ntdll!NtFsControlFile` at `0x18000853d`
- `KERNEL32!WaitForSingleObjectEx` at `0x1800086f7`
- `KERNEL32!WaitForSingleObjectEx` at `0x1800086f7`
- `KERNEL32!CreateThread` at `0x180008633`
- `KERNEL32!CreateThread` at `0x180008633`
- `KERNEL32!GetCurrentThread` at `0x18000855a`
- `KERNEL32!GetCurrentThread` at `0x18000855a`
- `KERNEL32!CloseHandle` at `0x180008705`
- `KERNEL32!CloseHandle` at `0x180008705`
- `KERNEL32!GetLastError` at `0x180008673`
- `KERNEL32!GetLastError` at `0x180008673`
- `ADVAPI32!OpenThreadToken` at `0x18000856d`
- `ADVAPI32!OpenThreadToken` at `0x18000856d`
- `ADVAPI32!EventActivityIdControl` at `0x180008607`
- `ADVAPI32!EventActivityIdControl` at `0x180008607`

## string_xrefs

- `0x180008840`: `UNCPath`
- `0x1800085a1`: `CSMBHelperClass::ReproduceFailure OpenThreadToken failed`
- `0x1800087d9`: `CSMBHelperClass::CreateThread repro  running in main thread`
- `0x180008752`: `CSMBHelperClass::Repro in thread timedout`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSMBHelperClass::ReproduceFailure(CSMBHelperClass *this)
{
  HANDLE CurrentThread; // rax
  volatile signed __int32 *v3; // rbx
  struct INDFEtw **v4; // rsi
  __int64 LastError; // r8
  volatile signed __int32 *v6; // rbx
  void *v7; // rcx
  DWORD v8; // eax
  volatile signed __int32 *v9; // rbx
  volatile signed __int32 *v10; // rbx
  unsigned __int16 *v11; // rcx
  unsigned int *v12; // r8
  struct INDFEtw *v13; // rdx
  __int64; // rax
  CSMBHelperClass *v15; // rdi
  volatile signed __int32 *v16; // rbx
  CSMBHelperClass *v17; // rdi
  CSMBHelperClass *v18; // rbx
  void *FileHandle; // [rsp+50h] [rbp-A8h] BYREF
  CSMBHelperClass *v20; // [rsp+58h] [rbp-A0h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-98h] BYREF
  struct _UNICODE_STRING v22; // [rsp+90h] [rbp-68h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A8h] [rbp-50h] BYREF

  v20 = this;
  v22 = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes.Length + 1, 0, 44);
  FileHandle = 0;
  RtlInitUnicodeString(&v22, L"\\Device\\LanmanRedirector");
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &v22;
  if ( NtOpenFile(&FileHandle, 0x100000u, &ObjectAttributes, &IoStatusBlock, 0, 0x20u) >= 0 && IoStatusBlock.Status >= 0 )
  {
    NtFsControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x1401F8u, 0, 0, 0, 0);
    if ( FileHandle )
      NtClose(FileHandle);
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xEu, 0, (PHANDLE)this + 27) )
  {
    if ( *((_QWORD *)this + 15) )
    {
      FileHandle = (void *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        &FileHandle,
        L"CSMBHelperClass::ReproduceFailure OpenThreadToken failed");
      v3 = (volatile signed __int32 *)FileHandle;
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD, const unsigned __int16 *, void *))(**((_QWORD **)this + 15) + 24LL))(
        *((_QWORD *)this + 15),
        2,
        0,
        L"SMBHelperClass",
        FileHandle);
      if ( _InterlockedExchangeAdd(v3 - 2, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v3 - 3) + 8LL))(*((_QWORD *)v3 - 3));
    }
    *((_QWORD *)this + 27) = 0;
  }
  if ( EventActivityIdControl(1u, (LPGUID)((char *)this + 84)) || (int)CSMBHelperClass::TransferActivityID() < 0 )
  {
    v4 = (struct INDFEtw **)((char *)this + 120);
    if ( *((_QWORD *)this + 15) )
    {
      FileHandle = (void *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
      LastError = GetLastError();
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        &FileHandle,
        L"CSMBHelperClass::EventActivityIdControl/TransferActivityID failed %d",
        LastError);
      v6 = (volatile signed __int32 *)FileHandle;
      (*(void (__fastcall **)(struct INDFEtw *, __int64, _QWORD, const unsigned __int16 *, void *))(*(_QWORD *)*v4 + 24LL))(
        *v4,
        2,
        0,
        L"SMBHelperClass",
        FileHandle);
      if ( _InterlockedExchangeAdd(v6 - 2, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v6 - 3) + 8LL))(*((_QWORD *)v6 - 3));
    }
  }
  else
  {
    *((_QWORD *)this + 8) = CreateThread(
                              0,
                              0,
                              (LPTHREAD_START_ROUTINE)CSMBHelperClass::ReproduceFailureThreadExecutive,
                              (char *)this - 56,
                              0,
                              0);
    v4 = (struct INDFEtw **)((char *)this + 120);
  }
  v7 = (void *)*((_QWORD *)this + 8);
  if ( v7 && *((_QWORD *)this + 27) )
  {
    v8 = WaitForSingleObjectEx(v7, 0x4E20u, 0);
    if ( v8 )
    {
      if ( v8 == 258 )
      {
        *((_DWORD *)this + 58) = 1;
        if ( *v4 )
        {
          FileHandle = (void *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
            &FileHandle,
            L"CSMBHelperClass::Repro in thread timedout");
          v9 = (volatile signed __int32 *)FileHandle;
          (*(void (__fastcall **)(struct INDFEtw *, __int64, _QWORD, const unsigned __int16 *, void *))(*(_QWORD *)*v4 + 24LL))(
            *v4,
            2,
            0,
            L"SMBHelperClass",
            FileHandle);
          if ( _InterlockedExchangeAdd(v9 - 2, 0xFFFFFFFF) <= 1 )
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v9 - 3) + 8LL))(*((_QWORD *)v9 - 3));
        }
      }
    }
    else
    {
      CloseHandle(*((HANDLE *)this + 8));
      *((_QWORD *)this + 8) = 0;
    }
LABEL_30:
     = 0;
    goto LABEL_46;
  }
  if ( *v4 )
  {
    FileHandle = (void *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      &FileHandle,
      L"CSMBHelperClass::CreateThread repro  running in main thread");
    v10 = (volatile signed __int32 *)FileHandle;
    (*(void (__fastcall **)(struct INDFEtw *, __int64, _QWORD, const unsigned __int16 *, void *))(*(_QWORD *)*v4 + 24LL))(
      *v4,
      2,
      0,
      L"SMBHelperClass",
      FileHandle);
    if ( _InterlockedExchangeAdd(v10 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v10 - 3) + 8LL))(*((_QWORD *)v10 - 3));
  }
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v11 = *(unsigned __int16 **)(((__int64 (*)(void))AttributeList::getAttribute)() + 8);
    v12 = (unsigned int *)((char *)this + 80);
    v13 = *v4;
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &enum TestException `RTTI Type Descriptor', 0) )
    {
      v15 = v20;
      if ( *((_QWORD *)v20 + 15) )
      {
        FileHandle = (void *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          &FileHandle,
          L"CSMBHelperClass::ReproduceFailure UNCPath not found");
        v16 = (volatile signed __int32 *)FileHandle;
        (*(void (__fastcall **)(_QWORD, __int64, _QWORD, const unsigned __int16 *, void *))(**((_QWORD **)v15 + 15)
                                                                                          + 24LL))(
          *((_QWORD *)v15 + 15),
          2,
          0,
          L"SMBHelperClass",
          FileHandle);
        if ( _InterlockedExchangeAdd(v16 - 2, 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**((_QWORD **)v16 - 3) + 8LL))(
            *((_QWORD *)v16 - 3),
            v16 - 6);
      }
       = 2147500037LL;
      __eh34_try_continuation(0, &enum TestException `RTTI Type Descriptor', &loc_1800088AE);
      goto LABEL_46;
    }
    if ( __eh34_catch_type(0, &exception `RTTI Type Descriptor', 0) )
    {
      v17 = v20;
      if ( *((_QWORD *)v20 + 15) )
      {
        v20 = (CSMBHelperClass *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          &v20,
          L"CSMBHelperClass::ReproduceFailure Unknown Exception");
        v18 = v20;
        (*(void (__fastcall **)(_QWORD, __int64, _QWORD, const unsigned __int16 *, CSMBHelperClass *))(**((_QWORD **)v17 + 15) + 24LL))(
          *((_QWORD *)v17 + 15),
          2,
          0,
          L"SMBHelperClass",
          v20);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v18 - 2, 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)v18 - 3) + 8LL))(
            *((_QWORD *)v18 - 3),
            (char *)v18 - 24);
      }
       = 2147500037LL;
      __eh34_try_continuation(0, &exception `RTTI Type Descriptor', &loc_1800088AE);
LABEL_46:
      ;
    }
  }
  CSMBHelperClass::ReproduceFailure(v11, v13, v12);
  if ( !(unsigned int)AttributeList::attributeExists((CSMBHelperClass *)((char *)this + 152), L"ErrorCode") )
  {
    _itow_s(*((_DWORD *)this + 20), (wchar_t *)&IoStatusBlock, 0x10u, 10);
    AttributeList::setStringAttribute(
      (CSMBHelperClass *)((char *)this + 152),
      L"ErrorCode",
      (unsigned __int16 *)&IoStatusBlock);
  }
  goto LABEL_30;
}

```

## disassembly

```asm
0x180008440  mov     r11, rsp
0x180008443  push    rbx
0x180008444  push    rsi
0x180008445  push    rdi
0x180008446  push    r15
0x180008448  sub     rsp, 0D8h
0x18000844f  mov     rax, cs:__security_cookie
0x180008456  xor     rax, rsp
0x180008459  mov     [rsp+0F8h+var_30], rax
0x180008461  mov     rdi, rcx
0x180008464  mov     [rsp+0F8h+var_A0], rcx
0x180008469  xorps   xmm0, xmm0
0x18000846c  movups  xmmword ptr [r11-68h], xmm0
0x180008471  xorps   xmm1, xmm1
0x180008474  movups  xmmword ptr [r11-50h], xmm1
0x180008479  movups  xmmword ptr [rsp+0F8h+ObjectAttributes.Length], xmm0
0x18000847e  movups  xmmword ptr [rsp+0F8h+ObjectAttributes.ObjectName], xmm0
0x180008483  movups  xmmword ptr [r11-78h], xmm0
0x180008488  xor     r15d, r15d
0x18000848b  mov     [rsp+0F8h+FileHandle], r15
0x180008490  lea     rdx, SourceString; "\\Device\\LanmanRedirector"
0x180008497  lea     rcx, [r11-68h]; DestinationString
0x18000849b  call    cs:__imp_RtlInitUnicodeString
0x1800084a1  mov     [rsp+0F8h+ObjectAttributes.Length], 30h ; '0'
0x1800084a9  mov     [rsp+0F8h+ObjectAttributes.RootDirectory], r15
0x1800084ae  mov     [rsp+0F8h+ObjectAttributes.Attributes], 40h ; '@'
0x1800084b6  lea     rax, [rsp+0F8h+var_68]
0x1800084be  mov     [rsp+0F8h+ObjectAttributes.ObjectName], rax
0x1800084c3  xorps   xmm0, xmm0
0x1800084c6  movdqu  xmmword ptr [rsp+0F8h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800084cf  mov     [rsp+0F8h+OpenOptions], 20h ; ' '; OpenOptions
0x1800084d7  mov     [rsp+0F8h+ShareAccess], r15d; ShareAccess
0x1800084dc  lea     r9, [rsp+0F8h+IoStatusBlock]; IoStatusBlock
0x1800084e4  lea     r8, [rsp+0F8h+ObjectAttributes]; ObjectAttributes
0x1800084e9  mov     edx, 100000h; DesiredAccess
0x1800084ee  lea     rcx, [rsp+0F8h+FileHandle]; FileHandle
0x1800084f3  call    cs:__imp_NtOpenFile
0x1800084f9  test    eax, eax
0x1800084fb  js      short loc_180008553
0x1800084fd  cmp     dword ptr [rsp+0F8h+IoStatusBlock], r15d
0x180008505  jl      short loc_180008553
0x180008507  mov     [rsp+0F8h+OutputBufferLength], r15d; OutputBufferLength
0x18000850c  mov     [rsp+0F8h+OutputBuffer], r15; OutputBuffer
0x180008511  mov     [rsp+0F8h+InputBufferLength], r15d; InputBufferLength
0x180008516  mov     [rsp+0F8h+InputBuffer], r15; InputBuffer
0x18000851b  mov     [rsp+0F8h+OpenOptions], 1401F8h; FsControlCode
0x180008523  lea     rax, [rsp+0F8h+IoStatusBlock]
0x18000852b  mov     qword ptr [rsp+0F8h+ShareAccess], rax; IoStatusBlock
0x180008530  xor     r9d, r9d; ApcContext
0x180008533  xor     r8d, r8d; ApcRoutine
0x180008536  xor     edx, edx; Event
0x180008538  mov     rcx, [rsp+0F8h+FileHandle]; FileHandle
0x18000853d  call    cs:__imp_NtFsControlFile
0x180008543  mov     rcx, [rsp+0F8h+FileHandle]; Handle
0x180008548  test    rcx, rcx
0x18000854b  jz      short loc_180008553
0x18000854d  call    cs:__imp_NtClose
0x180008553  lea     rsi, [rdi+0D8h]
0x18000855a  call    cs:__imp_GetCurrentThread
0x180008560  mov     rcx, rax; ThreadHandle
0x180008563  mov     r9, rsi; TokenHandle
0x180008566  xor     r8d, r8d; OpenAsSelf
0x180008569  lea     edx, [r8+0Eh]; DesiredAccess
0x18000856d  call    cs:__imp_OpenThreadToken
0x180008573  test    eax, eax
0x180008575  jnz     loc_1800085FE
0x18000857b  cmp     [rdi+78h], r15
0x18000857f  jz      short loc_1800085FB
0x180008581  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180008588  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000858f  mov     rax, [rax+18h]
0x180008593  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008598  add     rax, 18h
0x18000859c  mov     [rsp+0F8h+FileHandle], rax
0x1800085a1  lea     rdx, aCsmbhelperclas_6; "CSMBHelperClass::ReproduceFailure OpenT"...
0x1800085a8  lea     rcx, [rsp+0F8h+FileHandle]
0x1800085ad  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x1800085b2  mov     rcx, [rdi+78h]
0x1800085b6  mov     rax, [rcx]
0x1800085b9  xor     r8d, r8d
0x1800085bc  mov     rbx, [rsp+0F8h+FileHandle]
0x1800085c1  mov     qword ptr [rsp+0F8h+ShareAccess], rbx
0x1800085c6  lea     r9, aSmbhelperclass_0; "SMBHelperClass"
0x1800085cd  lea     edx, [r8+2]
0x1800085d1  mov     rax, [rax+18h]
0x1800085d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085da  nop
0x1800085db  lea     rdx, [rbx-18h]
0x1800085df  or      eax, 0FFFFFFFFh
0x1800085e2  lock xadd [rdx+10h], eax
0x1800085e7  sub     eax, 1
0x1800085ea  jg      short loc_1800085FB
0x1800085ec  mov     rcx, [rdx]
0x1800085ef  mov     rax, [rcx]
0x1800085f2  mov     rax, [rax+8]
0x1800085f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085fb  mov     [rsi], r15
0x1800085fe  lea     rdx, [rdi+54h]; ActivityId
0x180008602  mov     ecx, 1; ControlCode
0x180008607  call    cs:__imp_EventActivityIdControl
0x18000860d  test    eax, eax
0x18000860f  jnz     short loc_180008646
0x180008611  call    ?TransferActivityID@CSMBHelperClass@@SAJXZ; CSMBHelperClass::TransferActivityID(void)
0x180008616  test    eax, eax
0x180008618  js      short loc_180008646
0x18000861a  lea     r9, [rdi-38h]; lpParameter
0x18000861e  mov     qword ptr [rsp+0F8h+OpenOptions], r15; lpThreadId
0x180008623  mov     [rsp+0F8h+ShareAccess], r15d; dwCreationFlags
0x180008628  lea     r8, ?ReproduceFailureThreadExecutive@CSMBHelperClass@@SAKPEAX@Z; lpStartAddress
0x18000862f  xor     edx, edx; dwStackSize
0x180008631  xor     ecx, ecx; lpThreadAttributes
0x180008633  call    cs:__imp_CreateThread
0x180008639  mov     [rdi+40h], rax
0x18000863d  lea     rsi, [rdi+78h]
0x180008641  jmp     loc_1800086D5
0x180008646  lea     rsi, [rdi+78h]
0x18000864a  cmp     [rsi], r15
0x18000864d  jz      loc_1800086D5
0x180008653  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000865a  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180008661  mov     rax, [rax+18h]
0x180008665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000866a  add     rax, 18h
0x18000866e  mov     [rsp+0F8h+FileHandle], rax
0x180008673  call    cs:__imp_GetLastError
0x180008679  mov     r8d, eax
0x18000867c  lea     rdx, aCsmbhelperclas_9; "CSMBHelperClass::EventActivityIdControl"...
0x180008683  lea     rcx, [rsp+0F8h+FileHandle]
0x180008688  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18000868d  mov     rcx, [rsi]
0x180008690  mov     rax, [rcx]
0x180008693  xor     r8d, r8d
0x180008696  mov     rbx, [rsp+0F8h+FileHandle]
0x18000869b  mov     qword ptr [rsp+0F8h+ShareAccess], rbx
0x1800086a0  lea     r9, aSmbhelperclass_0; "SMBHelperClass"
0x1800086a7  lea     edx, [r8+2]
0x1800086ab  mov     rax, [rax+18h]
0x1800086af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086b4  nop
0x1800086b5  lea     rdx, [rbx-18h]
0x1800086b9  or      eax, 0FFFFFFFFh
0x1800086bc  lock xadd [rdx+10h], eax
0x1800086c1  sub     eax, 1
0x1800086c4  jg      short loc_1800086D5
0x1800086c6  mov     rcx, [rdx]
0x1800086c9  mov     rax, [rcx]
0x1800086cc  mov     rax, [rax+8]
0x1800086d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086d5  mov     rcx, [rdi+40h]; hHandle
0x1800086d9  test    rcx, rcx
0x1800086dc  jz      loc_1800087B4
0x1800086e2  cmp     [rdi+0D8h], r15
0x1800086e9  jz      loc_1800087B4
0x1800086ef  xor     r8d, r8d; bAlertable
0x1800086f2  mov     edx, 4E20h; dwMilliseconds
0x1800086f7  call    cs:__imp_WaitForSingleObjectEx
0x1800086fd  test    eax, eax
0x1800086ff  jnz     short loc_180008714
0x180008701  mov     rcx, [rdi+40h]; hObject
0x180008705  call    cs:__imp_CloseHandle
0x18000870b  mov     [rdi+40h], r15
0x18000870f  jmp     loc_1800088AA
0x180008714  cmp     eax, 102h
0x180008719  jnz     loc_1800088AA
0x18000871f  mov     dword ptr [rdi+0E8h], 1
0x180008729  cmp     [rsi], r15
0x18000872c  jz      loc_1800088AA
0x180008732  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180008739  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180008740  mov     rax, [rax+18h]
0x180008744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008749  add     rax, 18h
0x18000874d  mov     [rsp+0F8h+FileHandle], rax
0x180008752  lea     rdx, aCsmbhelperclas_0; "CSMBHelperClass::Repro in thread timedo"...
0x180008759  lea     rcx, [rsp+0F8h+FileHandle]
0x18000875e  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180008763  mov     rcx, [rsi]
0x180008766  mov     rax, [rcx]
0x180008769  xor     r8d, r8d
0x18000876c  mov     rbx, [rsp+0F8h+FileHandle]
0x180008771  mov     qword ptr [rsp+0F8h+ShareAccess], rbx
0x180008776  lea     r9, aSmbhelperclass_0; "SMBHelperClass"
0x18000877d  lea     edx, [r8+2]
0x180008781  mov     rax, [rax+18h]
0x180008785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000878a  nop
0x18000878b  lea     rdx, [rbx-18h]
0x18000878f  or      eax, 0FFFFFFFFh
0x180008792  lock xadd [rdx+10h], eax
0x180008797  sub     eax, 1
0x18000879a  jg      loc_1800088AA
0x1800087a0  mov     rcx, [rdx]
0x1800087a3  mov     rax, [rcx]
0x1800087a6  mov     rax, [rax+8]
0x1800087aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087af  jmp     loc_1800088AA
0x1800087b4  cmp     [rsi], r15
0x1800087b7  jz      short loc_180008833
0x1800087b9  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800087c0  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800087c7  mov     rax, [rax+18h]
0x1800087cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087d0  add     rax, 18h
0x1800087d4  mov     [rsp+0F8h+FileHandle], rax
0x1800087d9  lea     rdx, aCsmbhelperclas_5; "CSMBHelperClass::CreateThread repro  ru"...
0x1800087e0  lea     rcx, [rsp+0F8h+FileHandle]
0x1800087e5  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x1800087ea  mov     rcx, [rsi]
0x1800087ed  mov     rax, [rcx]
0x1800087f0  xor     r8d, r8d
0x1800087f3  mov     rbx, [rsp+0F8h+FileHandle]
0x1800087f8  mov     qword ptr [rsp+0F8h+ShareAccess], rbx
0x1800087fd  lea     r9, aSmbhelperclass_0; "SMBHelperClass"
0x180008804  lea     edx, [r8+2]
0x180008808  mov     rax, [rax+18h]
0x18000880c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008811  nop
0x180008812  lea     rdx, [rbx-18h]
0x180008816  or      eax, 0FFFFFFFFh
0x180008819  lock xadd [rdx+10h], eax
0x18000881e  sub     eax, 1
0x180008821  jg      short loc_180008833
0x180008823  mov     rcx, [rdx]
0x180008826  mov     rax, [rcx]
0x180008829  mov     rax, [rax+8]
0x18000882d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008832  nop
0x180008833  lea     rbx, [rdi+98h]
0x18000883a  mov     r9d, 1
0x180008840  lea     r8, aUncpath; "UNCPath"
0x180008847  lea     rdx, [rsp+0F8h+var_68]
0x18000884f  mov     rcx, rbx
0x180008852  call    ?getAttribute@AttributeList@@QEAA?AUAttribute@@PEAGW4AttributeType@@@Z; AttributeList::getAttribute(ushort *,AttributeType)
0x180008857  mov     rcx, [rax+8]; unsigned __int16 *
0x18000885b  lea     r8, [rdi+50h]; unsigned int *
0x18000885f  mov     rdx, [rsi]; struct INDFEtw *
0x180008862  call    ?ReproduceFailure@CSMBHelperClass@@CAJPEAGPEAUINDFEtw@@AEAK@Z; CSMBHelperClass::ReproduceFailure(ushort *,INDFEtw *,ulong &)
0x180008867  lea     rdx, aErrorcode; "ErrorCode"
0x18000886e  mov     rcx, rbx; this
0x180008871  call    ?attributeExists@AttributeList@@QEAAHPEAG@Z; AttributeList::attributeExists(ushort *)
0x180008876  test    eax, eax
0x180008878  jnz     short loc_1800088AA
0x18000887a  lea     r9d, [rax+0Ah]; Radix
0x18000887e  lea     r8d, [rax+10h]; BufferCount
0x180008882  lea     rdx, [rsp+0F8h+IoStatusBlock]; Buffer
0x18000888a  mov     ecx, [rdi+50h]; Value
0x18000888d  call    cs:__imp__itow_s
0x180008893  lea     r8, [rsp+0F8h+IoStatusBlock]; unsigned __int16 *
0x18000889b  lea     rdx, aErrorcode; "ErrorCode"
0x1800088a2  mov     rcx, rbx; this
0x1800088a5  call    ?setStringAttribute@AttributeList@@QEAAXPEAG0@Z; AttributeList::setStringAttribute(ushort *,ushort *)
0x1800088aa  xor     eax, eax
0x1800088ac  jmp     short loc_1800088B3
0x1800088ae  mov     eax, 80004005h
0x1800088b3  mov     rcx, [rsp+0F8h+var_30]
0x1800088bb  xor     rcx, rsp; StackCookie
0x1800088be  call    __security_check_cookie
0x1800088c3  add     rsp, 0D8h
0x1800088ca  pop     r15
0x1800088cc  pop     rdi
0x1800088cd  pop     rsi
0x1800088ce  pop     rbx
0x1800088cf  retn
```
