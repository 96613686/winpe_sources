# NFCConnector::Initialize(ushort const *,void * *)

- ea: `0x18001ad58`
- end: `0x18001afb1`
- name: `?Initialize@NFCConnector@@QEAAJPEBGPEAPEAX@Z`
- size: `601`
- prototype: `__int64 __fastcall(NFCConnector *__hidden this, const unsigned __int16 *Src, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180017094`

## callees

- `0x180001008`
- `0x180001194`
- `0x1800049a0`
- `0x18000584c`
- `0x18000d4ec`
- `0x1800127c0`
- `0x180013014`
- `0x18001ad58`
- `0x18001b844`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001af7f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001af7f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ad9d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ad9d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001ae1c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001ae1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aedb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aedb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001aecc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001aecc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NFCConnector::Initialize(
        struct _RTL_CRITICAL_SECTION *this,
        const unsigned __int16 *Src,
        PRTL_CRITICAL_SECTION_DEBUG *a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // r12
  __int64 v7; // rcx
  __int64 v8; // r8
  int v9; // r9d
  HANDLE EventW; // rax
  __int64 v11; // r8
  LONG *p_LockCount; // rcx
  unsigned __int64 v13; // rdx
  LONG *v14; // rdi
  __int64 v15; // rbx
  signed int v16; // ebx
  struct _RTL_CRITICAL_SECTION_DEBUG *FileW; // rax
  __int64 v18; // rcx
  __int64 v19; // r8
  int v20; // r9d
  signed int LastError; // eax
  const char *v23; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v24[2]; // [rsp+48h] [rbp-B8h] BYREF
  const char *v25; // [rsp+58h] [rbp-A8h] BYREF
  char v26; // [rsp+60h] [rbp-A0h]
  WCHAR FileName[264]; // [rsp+70h] [rbp-90h] BYREF

  v6 = this + 1;
  v25 = (const char *)&this[1];
  EnterCriticalSection(this + 1);
  v26 = 1;
  if ( (unsigned int)dword_18012F048 > 5 )
  {
    v23 = "Enter";
    v24[0] = "NFCConnector::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v7,
      (unsigned int)&dword_18011A1A4,
      v8,
      v9,
      (__int64)v24,
      (__int64)&v23);
  }
  if ( (Microsoft_WindowsPhone_SEManagementProviderEnableBits & 0x20) != 0 )
    McGenEventWrite_EventWriteTransfer(v7, SEMgr_Event_NFCCtor_Initialize_Start, v8, 1, v24);
  EventW = CreateEventW(0, 1, 0, 0);
  *(_QWORD *)&this[4].LockCount = EventW;
  if ( !EventW )
    goto LABEL_16;
  p_LockCount = &this->LockCount;
  v13 = -1;
  do
    ++v13;
  while ( Src[v13] );
  if ( v13 > this->SpinCount )
  {
    ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
      p_LockCount,
      v13,
      v11,
      Src);
  }
  else
  {
    if ( this->SpinCount <= 7 )
      v14 = &this->LockCount;
    else
      v14 = *(LONG **)p_LockCount;
    this->LockSemaphore = (HANDLE)v13;
    v15 = 2 * v13;
    memmove_0(v14, Src, 2 * v13);
    *(_WORD *)((char *)v14 + v15) = 0;
  }
  v16 = StringCchPrintfW(FileName, 0x104u, L"%s\\SEManage", Src);
  if ( v16 < 0 )
  {
LABEL_19:
    NFCConnector::Uninitialize((NFCConnector *)this);
    goto LABEL_21;
  }
  FileW = (struct _RTL_CRITICAL_SECTION_DEBUG *)CreateFileW(FileName, 0xC0000000, 3u, 0, 3u, 0x40000000u, 0);
  this->DebugInfo = FileW;
  if ( FileW != (struct _RTL_CRITICAL_SECTION_DEBUG *)-1LL )
  {
    v16 = 0;
  }
  else
  {
LABEL_16:
    LastError = GetLastError();
    v16 = LastError;
    if ( LastError > 0 )
      v16 = (unsigned __int16)LastError | 0x80070000;
    if ( v16 < 0 )
      goto LABEL_19;
  }
LABEL_21:
  if ( a3 )
    *a3 = this->DebugInfo;
  if ( (Microsoft_WindowsPhone_SEManagementProviderEnableBits & 0x20) != 0 )
    McGenEventWrite_EventWriteTransfer(v18, SEMgr_Event_NFCCtor_Initialize_Stop, v19, 1, &v25);
  if ( (unsigned int)dword_18012F048 > 5 )
  {
    LODWORD(v23) = v16;
    v24[0] = "Exit";
    v25 = "NFCConnector::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v18,
      (unsigned int)&word_180119E26,
      v19,
      v20,
      (__int64)&v25,
      (__int64)v24,
      (__int64)&v23);
  }
  LeaveCriticalSection(v6);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x18001ad58  mov     [rsp-8+arg_18], rbx
0x18001ad5d  push    rbp
0x18001ad5e  push    rsi
0x18001ad5f  push    rdi
0x18001ad60  push    r12
0x18001ad62  push    r13
0x18001ad64  push    r14
0x18001ad66  push    r15
0x18001ad68  lea     rbp, [rsp-190h]
0x18001ad70  sub     rsp, 290h
0x18001ad77  mov     rax, cs:__security_cookie
0x18001ad7e  xor     rax, rsp
0x18001ad81  mov     [rbp+1C0h+var_40], rax
0x18001ad88  mov     r15, r8
0x18001ad8b  mov     r14, rdx
0x18001ad8e  mov     rsi, rcx
0x18001ad91  lea     r12, [rcx+28h]
0x18001ad95  mov     [rsp+2C0h+var_268], r12
0x18001ad9a  mov     rcx, r12; lpCriticalSection
0x18001ad9d  call    cs:__imp_EnterCriticalSection
0x18001ada3  mov     [rsp+2C0h+var_260], 1
0x18001ada8  mov     eax, cs:dword_18012F048
0x18001adae  lea     rdi, aNfcconnectorIn; "NFCConnector::Initialize"
0x18001adb5  cmp     eax, 5
0x18001adb8  jbe     short loc_18001ADEB
0x18001adba  lea     rax, aEnter; "Enter"
0x18001adc1  mov     [rsp+2C0h+var_280], rax
0x18001adc6  mov     [rsp+2C0h+var_278], rdi
0x18001adcb  lea     rax, [rsp+2C0h+var_280]
0x18001add0  mov     qword ptr [rsp+2C0h+dwFlagsAndAttributes], rax
0x18001add5  lea     rax, [rsp+2C0h+var_278]
0x18001adda  mov     qword ptr [rsp+2C0h+dwCreationDisposition], rax
0x18001addf  lea     rdx, dword_18011A1A4
0x18001ade6  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18001adeb  test    cs:Microsoft_WindowsPhone_SEManagementProviderEnableBits, 20h
0x18001adf2  jz      short loc_18001AE10
0x18001adf4  lea     rax, [rsp+2C0h+var_278]
0x18001adf9  mov     qword ptr [rsp+2C0h+dwCreationDisposition], rax
0x18001adfe  mov     r9d, 1
0x18001ae04  lea     rdx, SEMgr_Event_NFCCtor_Initialize_Start
0x18001ae0b  call    McGenEventWrite_EventWriteTransfer
0x18001ae10  xor     r9d, r9d; lpName
0x18001ae13  xor     r8d, r8d; bInitialState
0x18001ae16  lea     edx, [r9+1]; bManualReset
0x18001ae1a  xor     ecx, ecx; lpEventAttributes
0x18001ae1c  call    cs:__imp_CreateEventW
0x18001ae22  mov     [rsi+0A8h], rax
0x18001ae29  xor     r13d, r13d
0x18001ae2c  test    rax, rax
0x18001ae2f  jz      loc_18001AEDB
0x18001ae35  lea     rcx, [rsi+8]
0x18001ae39  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001ae3d  inc     rdx
0x18001ae40  cmp     [r14+rdx*2], r13w
0x18001ae45  jnz     short loc_18001AE3D
0x18001ae47  cmp     rdx, [rcx+18h]
0x18001ae4b  ja      short loc_18001AE80
0x18001ae4d  cmp     qword ptr [rcx+18h], 7
0x18001ae52  jbe     short loc_18001AE59
0x18001ae54  mov     rdi, [rcx]
0x18001ae57  jmp     short loc_18001AE5C
0x18001ae59  mov     rdi, rcx
0x18001ae5c  mov     [rcx+10h], rdx
0x18001ae60  lea     rbx, [rdx+rdx]
0x18001ae64  mov     r8, rbx; Size
0x18001ae67  mov     rdx, r14; Src
0x18001ae6a  mov     rcx, rdi; void *
0x18001ae6d  call    memmove_0
0x18001ae72  mov     [rbx+rdi], r13w
0x18001ae77  lea     rdi, aNfcconnectorIn; "NFCConnector::Initialize"
0x18001ae7e  jmp     short loc_18001AE88
0x18001ae80  mov     r9, r14
0x18001ae83  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x18001ae88  mov     r9, r14
0x18001ae8b  lea     r8, aSSemanage; "%s\\SEManage"
0x18001ae92  mov     edx, 104h; unsigned __int64
0x18001ae97  lea     rcx, [rsp+2C0h+FileName]; unsigned __int16 *
0x18001ae9c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001aea1  mov     ebx, eax
0x18001aea3  test    eax, eax
0x18001aea5  js      short loc_18001AEF4
0x18001aea7  mov     [rsp+2C0h+hTemplateFile], r13; hTemplateFile
0x18001aeac  mov     [rsp+2C0h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x18001aeb4  mov     r8d, 3; dwShareMode
0x18001aeba  mov     [rsp+2C0h+dwCreationDisposition], r8d; dwCreationDisposition
0x18001aebf  xor     r9d, r9d; lpSecurityAttributes
0x18001aec2  mov     edx, 0C0000000h; dwDesiredAccess
0x18001aec7  lea     rcx, [rsp+2C0h+FileName]; lpFileName
0x18001aecc  call    cs:__imp_CreateFileW
0x18001aed2  mov     [rsi], rax
0x18001aed5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001aed9  jnz     short loc_18001AEFE
0x18001aedb  call    cs:__imp_GetLastError
0x18001aee1  test    eax, eax
0x18001aee3  mov     ebx, eax
0x18001aee5  jle     short loc_18001AEF0
0x18001aee7  movzx   ebx, ax
0x18001aeea  or      ebx, 80070000h
0x18001aef0  test    ebx, ebx
0x18001aef2  jns     short loc_18001AF01
0x18001aef4  mov     rcx, rsi; this
0x18001aef7  call    ?Uninitialize@NFCConnector@@QEAAJXZ; NFCConnector::Uninitialize(void)
0x18001aefc  jmp     short loc_18001AF01
0x18001aefe  mov     ebx, r13d
0x18001af01  test    r15, r15
0x18001af04  jz      short loc_18001AF0C
0x18001af06  mov     rax, [rsi]
0x18001af09  mov     [r15], rax
0x18001af0c  test    cs:Microsoft_WindowsPhone_SEManagementProviderEnableBits, 20h
0x18001af13  jz      short loc_18001AF31
0x18001af15  lea     rax, [rsp+2C0h+var_268]
0x18001af1a  mov     qword ptr [rsp+2C0h+dwCreationDisposition], rax
0x18001af1f  mov     r9d, 1
0x18001af25  lea     rdx, SEMgr_Event_NFCCtor_Initialize_Stop
0x18001af2c  call    McGenEventWrite_EventWriteTransfer
0x18001af31  mov     eax, cs:dword_18012F048
0x18001af37  cmp     eax, 5
0x18001af3a  jbe     short loc_18001AF7C
0x18001af3c  mov     dword ptr [rsp+2C0h+var_280], ebx
0x18001af40  lea     rax, aExit; "Exit"
0x18001af47  mov     [rsp+2C0h+var_278], rax
0x18001af4c  mov     [rsp+2C0h+var_268], rdi
0x18001af51  lea     rax, [rsp+2C0h+var_280]
0x18001af56  mov     [rsp+2C0h+hTemplateFile], rax
0x18001af5b  lea     rax, [rsp+2C0h+var_278]
0x18001af60  mov     qword ptr [rsp+2C0h+dwFlagsAndAttributes], rax
0x18001af65  lea     rax, [rsp+2C0h+var_268]
0x18001af6a  mov     qword ptr [rsp+2C0h+dwCreationDisposition], rax
0x18001af6f  lea     rdx, word_180119E26
0x18001af76  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001af7b  nop
0x18001af7c  mov     rcx, r12; lpCriticalSection
0x18001af7f  call    cs:__imp_LeaveCriticalSection
0x18001af85  mov     eax, ebx
0x18001af87  mov     rcx, [rbp+1C0h+var_40]
0x18001af8e  xor     rcx, rsp; StackCookie
0x18001af91  call    __security_check_cookie
0x18001af96  mov     rbx, [rsp+2C0h+arg_18]
0x18001af9e  add     rsp, 290h
0x18001afa5  pop     r15
0x18001afa7  pop     r14
0x18001afa9  pop     r13
0x18001afab  pop     r12
0x18001afad  pop     rdi
0x18001afae  pop     rsi
0x18001afaf  pop     rbp
0x18001afb0  retn
```
