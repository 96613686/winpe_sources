# NetSetupService::OnStop(void)

- ea: `0x18000affc`
- end: `0x18000b113`
- name: `?OnStop@NetSetupService@@AEAAXXZ`
- size: `279`
- prototype: `void __fastcall(SERVICE_STATUS_HANDLE *this)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180008294`

## callees

- `0x1800027c0`
- `0x1800072f8`
- `0x180007324`
- `0x1800076e0`
- `0x180008b70`
- `0x1800093b4`
- `0x18000adb0`
- `0x18000affc`
- `0x18000cf2c`
- `0x18000d04c`
- `0x18000d4ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b062`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b062`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall NetSetupService::OnStop(SERVICE_STATUS_HANDLE *this)
{
  RTL_SRWLOCK *v2; // rcx
  SERVICE_STATUS_HANDLE v3; // rdi
  unsigned int v4; // edx
  __int64 v5; // rcx
  int v6; // [rsp+30h] [rbp-38h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-30h]

  if ( (Microsoft_Windows_Network_SetupEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(this, EtwServiceStopping);
  NetSetupService::WaitForDevicesReady((NetSetupService *)this);
  RtlLockThisExclusive::RtlLockThisExclusive((RtlLockThisExclusive *)&v6, (struct RtlSrwLock *)(this + 48));
  v2 = SRWLock;
  LODWORD(SRWLock[1].Ptr) = 0;
  ReleaseSRWLockExclusive(v2);
  v6 = 0;
  NetSetupService::SetServiceStatus(this, 3);
  NetSetupService::StopSubsystems((NetSetupService *)this);
  v3 = this[12];
  *((_DWORD *)this + 30) = 4;
  g_NetSetupService = 0;
  NetSetupService::`scalar deleting destructor'((HKEY *)this);
  if ( (Microsoft_Windows_Network_SetupEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v5, EtwServiceStopped);
  if ( g_NetSetupTrace )
    RtlEtwTrace::`scalar deleting destructor'(g_NetSetupTrace, v4);
  g_NetSetupTrace = 0;
  NetSetupService::NotifyScmOfStateChange(v3, 4);
  RtlLockHolder::~RtlLockHolder((RtlLockHolder *)&v6);
}

```

## disassembly

```asm
0x18000affc  mov     [rsp+arg_8], rbx
0x18000b001  push    rdi
0x18000b002  sub     rsp, 60h
0x18000b006  mov     rax, cs:__security_cookie
0x18000b00d  xor     rax, rsp
0x18000b010  mov     [rsp+68h+var_18], rax
0x18000b015  test    cs:Microsoft_Windows_Network_SetupEnableBits, 1
0x18000b01c  mov     rbx, rcx
0x18000b01f  jz      short loc_18000B03D
0x18000b021  lea     rax, [rsp+68h+var_38]
0x18000b026  mov     r9d, 1
0x18000b02c  lea     rdx, EtwServiceStopping
0x18000b033  mov     [rsp+68h+var_48], rax
0x18000b038  call    McGenEventWrite_EventWriteTransfer
0x18000b03d  mov     rcx, rbx; this
0x18000b040  call    ?WaitForDevicesReady@NetSetupService@@QEAAXXZ; NetSetupService::WaitForDevicesReady(void)
0x18000b045  lea     rdx, [rbx+180h]; struct RtlSrwLock *
0x18000b04c  lea     rcx, [rsp+68h+var_38]; this
0x18000b051  call    ??0RtlLockThisExclusive@@QEAA@AEAVRtlSrwLock@@@Z; RtlLockThisExclusive::RtlLockThisExclusive(RtlSrwLock &)
0x18000b056  mov     rcx, [rsp+68h+SRWLock]; SRWLock
0x18000b05b  mov     dword ptr [rcx+8], 0
0x18000b062  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b068  mov     edx, 3
0x18000b06d  mov     [rsp+68h+var_38], 0
0x18000b075  mov     rcx, rbx
0x18000b078  call    ?SetServiceStatus@NetSetupService@@AEAAXW4ServiceState@1@K@Z; NetSetupService::SetServiceStatus(NetSetupService::ServiceState,ulong)
0x18000b07d  mov     rcx, rbx; this
0x18000b080  call    ?StopSubsystems@NetSetupService@@AEAAXXZ; NetSetupService::StopSubsystems(void)
0x18000b085  mov     rdi, [rbx+60h]
0x18000b089  mov     rcx, rbx; this
0x18000b08c  mov     dword ptr [rbx+78h], 4
0x18000b093  mov     cs:?g_NetSetupService@@3PEAVNetSetupService@@EA, 0; NetSetupService * g_NetSetupService
0x18000b09e  call    ??_GNetSetupService@@QEAAPEAXI@Z; NetSetupService::`scalar deleting destructor'(uint)
0x18000b0a3  test    cs:Microsoft_Windows_Network_SetupEnableBits, 1
0x18000b0aa  jz      short loc_18000B0C8
0x18000b0ac  lea     rax, [rsp+68h+var_28]
0x18000b0b1  mov     r9d, 1
0x18000b0b7  lea     rdx, EtwServiceStopped
0x18000b0be  mov     [rsp+68h+var_48], rax
0x18000b0c3  call    McGenEventWrite_EventWriteTransfer
0x18000b0c8  mov     rcx, cs:?g_NetSetupTrace@@3PEAVRtlEtwTrace@@EA; this
0x18000b0cf  test    rcx, rcx
0x18000b0d2  jz      short loc_18000B0D9
0x18000b0d4  call    ??_GRtlEtwTrace@@QEAAPEAXI@Z; RtlEtwTrace::`scalar deleting destructor'(uint)
0x18000b0d9  mov     edx, 4
0x18000b0de  mov     cs:?g_NetSetupTrace@@3PEAVRtlEtwTrace@@EA, 0; RtlEtwTrace * g_NetSetupTrace
0x18000b0e9  mov     rcx, rdi
0x18000b0ec  call    ?NotifyScmOfStateChange@NetSetupService@@CA_NPEAUSERVICE_STATUS_HANDLE__@@W4ServiceState@1@K@Z; NetSetupService::NotifyScmOfStateChange(SERVICE_STATUS_HANDLE__ *,NetSetupService::ServiceState,ulong)
0x18000b0f1  lea     rcx, [rsp+68h+var_38]; this
0x18000b0f6  call    ??1RtlLockHolder@@QEAA@XZ; RtlLockHolder::~RtlLockHolder(void)
0x18000b0fb  mov     rcx, [rsp+68h+var_18]
0x18000b100  xor     rcx, rsp; StackCookie
0x18000b103  call    __security_check_cookie
0x18000b108  mov     rbx, [rsp+68h+arg_8]
0x18000b10d  add     rsp, 60h
0x18000b111  pop     rdi
0x18000b112  retn
```
