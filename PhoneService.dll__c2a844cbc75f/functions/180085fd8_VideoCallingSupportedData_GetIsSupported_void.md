# VideoCallingSupportedData::GetIsSupported(void)

- ea: `0x180085fd8`
- end: `0x180086175`
- name: `?GetIsSupported@VideoCallingSupportedData@@QEAAHXZ`
- size: `413`
- prototype: `__int64 __fastcall(VideoCallingSupportedData *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18008a3b0`

## callees

- `0x180003db0`
- `0x180004a08`
- `0x18001de50`
- `0x18001f514`
- `0x180085fd8`
- `0x18008d95a`
- `0x18008d9b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800860a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800860a4`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18008603c`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18008603c`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180086077`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180086077`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18008612d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180086136`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18008612d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180086136`

## string_xrefs

- `0x180086033`: `ServicesActive`
- `0x1800860b4`: `PublicPhoneRpc: Checking for device support of video calling. This service does NOT exist`

## pseudocode

```c
__int64 __fastcall VideoCallingSupportedData::GetIsSupported(VideoCallingSupportedData *this)
{
  SC_HANDLE v1; // rbx
  __int64 v2; // rsi
  const WCHAR *v3; // r14
  SC_HANDLE v4; // rax
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  SC_HANDLE v8; // rdi
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  unsigned int v12; // ebx
  DWORD LastError; // [rsp+40h] [rbp-49h] BYREF
  const char *v15; // [rsp+48h] [rbp-41h] BYREF
  const char *v16; // [rsp+50h] [rbp-39h] BYREF
  LPCWSTR lpServiceName[3]; // [rsp+58h] [rbp-31h]
  LPCRITICAL_SECTION v18[8]; // [rsp+70h] [rbp-19h] BYREF

  memset_0(v18, 0, sizeof(v18));
  AutoLockWithWatchdog::AutoLockWithWatchdog(
    (AutoLockWithWatchdog *)v18,
    &stru_1800B3658,
    "VideoCallingSupportedData::GetIsSupported");
  if ( g_videoCallingSupportedData )
  {
    v1 = OpenSCManagerW(0, L"ServicesActive", 1u);
    if ( v1 )
    {
      v2 = 0;
      lpServiceName[0] = L"QcRcsPresSvc";
      lpServiceName[1] = L"FakePresenceSvc";
      while ( 1 )
      {
        v3 = lpServiceName[v2];
        v4 = OpenServiceW(v1, v3, 1u);
        g_videoCallingSupportedData = 0;
        v8 = v4;
        if ( v4 )
          break;
        dword_1800B3654 = 0;
        if ( (unsigned int)dword_1800B3200 > 5 )
        {
          v15 = (const char *)v3;
          LastError = GetLastError();
          v16 = "PublicPhoneRpc: Checking for device support of video calling. This service does NOT exist";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
            v9,
            (int)byte_1800AB181,
            v10,
            v11,
            (const unsigned __int16 **)&v16,
            (__int64)&LastError,
            (const unsigned __int16 **)&v15);
        }
        v2 = (unsigned int)(v2 + 1);
        if ( (unsigned int)v2 >= 2 )
          goto LABEL_12;
      }
      dword_1800B3654 = 1;
      if ( (unsigned int)dword_1800B3200 > 5 )
      {
        v16 = (const char *)v3;
        v15 = "PublicPhoneRpc: Checking for device support of video calling.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v5,
          (int)&byte_1800AB12F,
          v6,
          v7,
          (const unsigned __int16 **)&v15,
          (const unsigned __int16 **)&v16);
      }
      CloseServiceHandle(v8);
LABEL_12:
      CloseServiceHandle(v1);
    }
  }
  if ( g_videoCallingSupportedData )
    v12 = 0;
  else
    v12 = dword_1800B3654;
  AutoLockWithWatchdog::~AutoLockWithWatchdog(v18);
  return v12;
}

```

## disassembly

```asm
0x180085fd8  push    rbp
0x180085fda  push    rbx
0x180085fdb  push    rsi
0x180085fdc  push    rdi
0x180085fdd  push    r14
0x180085fdf  lea     rbp, [rsp-37h]
0x180085fe4  sub     rsp, 0C0h
0x180085feb  mov     rax, cs:__security_cookie
0x180085ff2  xor     rax, rsp
0x180085ff5  mov     [rbp+57h+var_30], rax
0x180085ff9  xor     edx, edx; Val
0x180085ffb  lea     rcx, [rbp+57h+var_70]; void *
0x180085fff  lea     r8d, [rdx+40h]; Size
0x180086003  call    memset_0
0x180086008  lea     r8, aVideocallingsu; "VideoCallingSupportedData::GetIsSupport"...
0x18008600f  lea     rdx, stru_1800B3658; struct utl::recursive_mutex *
0x180086016  lea     rcx, [rbp+57h+var_70]; this
0x18008601a  call    ??0AutoLockWithWatchdog@@QEAA@PEAVrecursive_mutex@utl@@PEBD@Z; AutoLockWithWatchdog::AutoLockWithWatchdog(utl::recursive_mutex *,char const *)
0x18008601f  mov     eax, cs:?g_videoCallingSupportedData@@3UVideoCallingSupportedData@@A; VideoCallingSupportedData g_videoCallingSupportedData
0x180086025  test    eax, eax
0x180086027  jz      loc_18008613C
0x18008602d  mov     r8d, 1; dwDesiredAccess
0x180086033  lea     rdx, DatabaseName; "ServicesActive"
0x18008603a  xor     ecx, ecx; lpMachineName
0x18008603c  call    cs:__imp_OpenSCManagerW
0x180086042  mov     rbx, rax
0x180086045  test    rax, rax
0x180086048  jz      loc_18008613C
0x18008604e  lea     rax, aQcrcspressvc; "QcRcsPresSvc"
0x180086055  xor     esi, esi
0x180086057  mov     [rbp+57h+lpServiceName], rax
0x18008605b  lea     rax, aFakepresencesv; "FakePresenceSvc"
0x180086062  mov     [rbp+57h+var_80], rax
0x180086066  mov     r14, [rbp+rsi*8+57h+lpServiceName]
0x18008606b  mov     r8d, 1; dwDesiredAccess
0x180086071  mov     rdx, r14; lpServiceName
0x180086074  mov     rcx, rbx; hSCManager
0x180086077  call    cs:__imp_OpenServiceW
0x18008607d  mov     cs:?g_videoCallingSupportedData@@3UVideoCallingSupportedData@@A, 0; VideoCallingSupportedData g_videoCallingSupportedData
0x180086087  mov     rdi, rax
0x18008608a  test    rax, rax
0x18008608d  jnz     short loc_1800860E8
0x18008608f  mov     cs:dword_1800B3654, eax
0x180086095  mov     eax, cs:dword_1800B3200
0x18008609b  cmp     eax, 5
0x18008609e  jbe     short loc_1800860DF
0x1800860a0  mov     [rbp+57h+var_98], r14
0x1800860a4  call    cs:__imp_GetLastError
0x1800860aa  mov     [rbp+57h+var_A0], eax
0x1800860ad  lea     rdx, byte_1800AB181
0x1800860b4  lea     rax, aPublicphonerpc_3; "PublicPhoneRpc: Checking for device sup"...
0x1800860bb  mov     [rbp+57h+var_90], rax
0x1800860bf  lea     rax, [rbp+57h+var_98]
0x1800860c3  mov     [rsp+0E0h+var_B0], rax
0x1800860c8  lea     rax, [rbp+57h+var_A0]
0x1800860cc  mov     [rsp+0E0h+var_B8], rax
0x1800860d1  lea     rax, [rbp+57h+var_90]
0x1800860d5  mov     [rsp+0E0h+var_C0], rax
0x1800860da  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x1800860df  inc     esi
0x1800860e1  cmp     esi, 2
0x1800860e4  jb      short loc_180086066
0x1800860e6  jmp     short loc_180086133
0x1800860e8  mov     cs:dword_1800B3654, 1
0x1800860f2  mov     eax, cs:dword_1800B3200
0x1800860f8  cmp     eax, 5
0x1800860fb  jbe     short loc_18008612A
0x1800860fd  lea     rax, aPublicphonerpc_5; "PublicPhoneRpc: Checking for device sup"...
0x180086104  mov     [rbp+57h+var_90], r14
0x180086108  mov     [rbp+57h+var_98], rax
0x18008610c  lea     rdx, byte_1800AB12F
0x180086113  lea     rax, [rbp+57h+var_90]
0x180086117  mov     [rsp+0E0h+var_B8], rax
0x18008611c  lea     rax, [rbp+57h+var_98]
0x180086120  mov     [rsp+0E0h+var_C0], rax
0x180086125  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18008612a  mov     rcx, rdi; hSCObject
0x18008612d  call    cs:__imp_CloseServiceHandle
0x180086133  mov     rcx, rbx; hSCObject
0x180086136  call    cs:__imp_CloseServiceHandle
0x18008613c  mov     eax, cs:?g_videoCallingSupportedData@@3UVideoCallingSupportedData@@A; VideoCallingSupportedData g_videoCallingSupportedData
0x180086142  test    eax, eax
0x180086144  jnz     short loc_18008614E
0x180086146  mov     ebx, cs:dword_1800B3654
0x18008614c  jmp     short loc_180086150
0x18008614e  xor     ebx, ebx
0x180086150  lea     rcx, [rbp+57h+var_70]; this
0x180086154  call    ??1AutoLockWithWatchdog@@QEAA@XZ; AutoLockWithWatchdog::~AutoLockWithWatchdog(void)
0x180086159  mov     eax, ebx
0x18008615b  mov     rcx, [rbp+57h+var_30]
0x18008615f  xor     rcx, rsp; StackCookie
0x180086162  call    __security_check_cookie
0x180086167  add     rsp, 0C0h
0x18008616e  pop     r14
0x180086170  pop     rdi
0x180086171  pop     rsi
0x180086172  pop     rbx
0x180086173  pop     rbp
0x180086174  retn
```
