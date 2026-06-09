# XusbWatcher::WorkerThread(void)

- ea: `0x180042970`
- end: `0x180042b59`
- name: `?WorkerThread@XusbWatcher@@AEAAXXZ`
- size: `489`
- prototype: `void __fastcall(XusbWatcher *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180042f60`

## callees

- `0x18000d658`
- `0x18000d68c`
- `0x18003bb28`
- `0x18003bbd0`
- `0x180040020`
- `0x180042970`
- `0x18004c881`
- `0x18004c8e0`

## import_xrefs

- `ntdll!NtWaitForSingleObject` at `0x180042a28`
- `ntdll!NtWaitForSingleObject` at `0x180042af5`
- `ntdll!NtWaitForSingleObject` at `0x180042a28`
- `ntdll!NtWaitForSingleObject` at `0x180042af5`
- `ntdll!NtDelayExecution` at `0x1800429d0`
- `ntdll!NtDelayExecution` at `0x1800429d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042ad5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042ad5`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180042ac5`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180042ac5`

## pseudocode

```c
void __fastcall XusbWatcher::WorkerThread(XusbWatcher *this)
{
  struct Windows::Gaming::Input::Internal::IXusbGameControllerProviderPrivate *v2; // rcx
  void *v3; // rdx
  void *v4; // rcx
  char v5; // cl
  bool v6; // zf
  __int64 v7; // rdx
  __int64 v8; // rcx
  GameInputServerDevice *v9; // rbx
  unsigned __int64 v10; // rax
  int v11; // eax
  signed int LastError; // eax
  NTSTATUS v13; // eax
  LARGE_INTEGER Interval; // [rsp+30h] [rbp-19h] BYREF
  _BYTE Buf1[19]; // [rsp+38h] [rbp-11h] BYREF
  struct _OVERLAPPED v16; // [rsp+50h] [rbp+7h] BYREF
  _BYTE v17[24]; // [rsp+70h] [rbp+27h] BYREF

  while ( !*((_BYTE *)this + 40) )
  {
    v2 = (struct Windows::Gaming::Input::Internal::IXusbGameControllerProviderPrivate *)*((_QWORD *)this + 3);
    Interval.LowPart = 0;
    if ( XusbWatcher::GetXusbDeviceIndex(v2, (unsigned int *)&Interval)
      && (v3 = (void *)*((_QWORD *)this + 1),
          v4 = *(void **)this,
          memset(v17, 0, sizeof(v17)),
          memset(&v16, 0, sizeof(v16)),
          XusbWatcher::RequestUnfilteredState(
            v4,
            v3,
            Interval.LowPart,
            1,
            (struct GamepadState0101::GamepadData *)v17,
            &v16)) )
    {
      if ( NtWaitForSingleObject(*((HANDLE *)this + 1), 1u, 0) )
      {
        if ( !CancelIoEx(*(HANDLE *)this, 0) )
        {
          LastError = GetLastError();
          if ( LastError )
          {
            if ( LastError != 1168 )
            {
              if ( LastError > 0 )
                LastError = (unsigned __int16)LastError | 0x80070000;
              GameInputFailFast((unsigned int)LastError, 433);
              JUMPOUT(0x180042B58LL);
            }
          }
        }
        v13 = NtWaitForSingleObject(*((HANDLE *)this + 1), 0, 0);
        if ( v13 )
        {
          GameInputFailFast(v13 | 0x10000000u, 438);
          __debugbreak();
        }
      }
      else if ( !*((_BYTE *)this + 40) )
      {
        if ( LODWORD(v16.Internal) || v16.InternalHigh != 24 )
          goto LABEL_3;
        v5 = v17[23];
        *(_WORD *)&Buf1[16] = *(_WORD *)&v17[21];
        v6 = *((_DWORD *)this + 15) == 0;
        *(_OWORD *)Buf1 = *(_OWORD *)&v17[5];
        if ( !v6 )
          v5 = 0;
        Buf1[18] = v5;
        if ( memcmp_0(Buf1, (char *)this + 41, 0x13u) )
        {
          v9 = (GameInputServerDevice *)*((_QWORD *)this + 2);
          v10 = GameInputCurrentTime(v8, v7);
          GameInputServerDevice::HandleXusbStateChange(v9, v10, (const struct XusbGamepadState *)Buf1);
          v11 = *(_DWORD *)&Buf1[15];
          *(_OWORD *)((char *)this + 41) = *(_OWORD *)Buf1;
          *((_DWORD *)this + 14) = v11;
        }
      }
    }
    else
    {
LABEL_3:
      Interval.QuadPart = -1000000;
      NtDelayExecution(1u, &Interval);
    }
  }
}

```

## disassembly

```asm
0x180042970  mov     [rsp-8+arg_8], rbx
0x180042975  mov     [rsp-8+arg_10], rsi
0x18004297a  push    rbp
0x18004297b  push    rdi
0x18004297c  push    r15
0x18004297e  lea     rbp, [rsp-47h]
0x180042983  sub     rsp, 90h
0x18004298a  mov     rax, cs:__security_cookie
0x180042991  xor     rax, rsp
0x180042994  mov     [rbp+57h+var_18], rax
0x180042998  mov     rdi, rcx
0x18004299b  mov     r15, 0FFFFFFFFFFF0BDC0h
0x1800429a2  mov     al, [rdi+28h]
0x1800429a5  nop
0x1800429a6  test    al, al
0x1800429a8  jnz     loc_180042B0A
0x1800429ae  mov     rcx, [rdi+18h]; struct Windows::Gaming::Input::Internal::IXusbGameControllerProviderPrivate *
0x1800429b2  lea     rdx, [rbp+57h+Interval]; unsigned int *
0x1800429b6  mov     dword ptr [rbp+57h+Interval], 0
0x1800429bd  call    ?GetXusbDeviceIndex@XusbWatcher@@CA_NPEAUIXusbGameControllerProviderPrivate@Internal@Input@Gaming@Windows@@AEAI@Z; XusbWatcher::GetXusbDeviceIndex(Windows::Gaming::Input::Internal::IXusbGameControllerProviderPrivate *,uint &)
0x1800429c2  test    al, al
0x1800429c4  jnz     short loc_1800429DE
0x1800429c6  lea     rdx, [rbp+57h+Interval]; Interval
0x1800429ca  mov     qword ptr [rbp+57h+Interval], r15
0x1800429ce  mov     cl, 1; Alertable
0x1800429d0  call    cs:__imp_NtDelayExecution
0x1800429d7  nop     dword ptr [rax+rax+00h]
0x1800429dc  jmp     short loc_1800429A2
0x1800429de  mov     r8d, dword ptr [rbp+57h+Interval]; unsigned int
0x1800429e2  xor     eax, eax
0x1800429e4  mov     rdx, [rdi+8]; hEvent
0x1800429e8  xorps   xmm1, xmm1
0x1800429eb  mov     rcx, [rdi]; hDevice
0x1800429ee  xorps   xmm0, xmm0
0x1800429f1  mov     [rbp+57h+var_20], rax
0x1800429f5  mov     r9b, 1; bool
0x1800429f8  lea     rax, [rbp+57h+var_50]
0x1800429fc  mov     [rsp+0A0h+var_78], rax; struct _OVERLAPPED *
0x180042a01  lea     rax, [rbp+57h+var_30]
0x180042a05  mov     [rsp+0A0h+var_80], rax; struct GamepadState0101::GamepadData *
0x180042a0a  movups  [rbp+57h+var_30], xmm0
0x180042a0e  movups  xmmword ptr [rbp+57h+var_50.Internal], xmm1
0x180042a12  movups  xmmword ptr [rbp+57h+var_50.10h], xmm1
0x180042a16  call    ?RequestUnfilteredState@XusbWatcher@@CA_NPEAX0I_NPEAUGamepadData@GamepadState0101@@PEAU_OVERLAPPED@@@Z; XusbWatcher::RequestUnfilteredState(void *,void *,uint,bool,GamepadState0101::GamepadData *,_OVERLAPPED *)
0x180042a1b  test    al, al
0x180042a1d  jz      short loc_1800429C6
0x180042a1f  mov     rcx, [rdi+8]; Handle
0x180042a23  xor     r8d, r8d; Timeout
0x180042a26  mov     dl, 1; Alertable
0x180042a28  call    cs:__imp_NtWaitForSingleObject
0x180042a2f  nop     dword ptr [rax+rax+00h]
0x180042a34  test    eax, eax
0x180042a36  jnz     loc_180042AC0
0x180042a3c  mov     al, [rdi+28h]
0x180042a3f  nop
0x180042a40  test    al, al
0x180042a42  jnz     loc_1800429A2
0x180042a48  cmp     dword ptr [rbp+57h+var_50.Internal], 0
0x180042a4c  jnz     loc_1800429C6
0x180042a52  cmp     [rbp+57h+var_50.InternalHigh], 18h
0x180042a57  jnz     loc_1800429C6
0x180042a5d  movzx   eax, word ptr [rbp+57h+var_20+5]
0x180042a61  lea     rdx, [rdi+29h]; Buf2
0x180042a65  movzx   ecx, byte ptr [rbp+57h+var_20+7]
0x180042a69  movups  xmm0, [rbp+57h+var_30+5]
0x180042a6d  mov     [rbp+57h+var_58], ax
0x180042a71  xor     eax, eax
0x180042a73  cmp     [rdi+3Ch], eax
0x180042a76  movups  [rbp+57h+Buf1], xmm0
0x180042a7a  cmovnz  ecx, eax
0x180042a7d  mov     [rbp+57h+var_56], cl
0x180042a80  lea     r8d, [rax+13h]; Size
0x180042a84  lea     rcx, [rbp+57h+Buf1]; Buf1
0x180042a88  call    memcmp_0
0x180042a8d  test    eax, eax
0x180042a8f  jz      loc_1800429A2
0x180042a95  mov     rbx, [rdi+10h]
0x180042a99  call    GameInputCurrentTime
0x180042a9e  lea     r8, [rbp+57h+Buf1]; struct XusbGamepadState *
0x180042aa2  mov     rdx, rax; unsigned __int64
0x180042aa5  mov     rcx, rbx; this
0x180042aa8  call    ?HandleXusbStateChange@GameInputServerDevice@@QEAAX_KAEBUXusbGamepadState@@@Z; GameInputServerDevice::HandleXusbStateChange(unsigned __int64,XusbGamepadState const &)
0x180042aad  movups  xmm0, [rbp+57h+Buf1]
0x180042ab1  mov     eax, dword ptr [rbp+57h+Buf1+0Fh]
0x180042ab4  movups  xmmword ptr [rdi+29h], xmm0
0x180042ab8  mov     [rdi+38h], eax
0x180042abb  jmp     loc_1800429A2
0x180042ac0  mov     rcx, [rdi]; hFile
0x180042ac3  xor     edx, edx; lpOverlapped
0x180042ac5  call    cs:__imp_CancelIoEx
0x180042acc  nop     dword ptr [rax+rax+00h]
0x180042ad1  test    eax, eax
0x180042ad3  jnz     short loc_180042AEC
0x180042ad5  call    cs:__imp_GetLastError
0x180042adc  nop     dword ptr [rax+rax+00h]
0x180042ae1  test    eax, eax
0x180042ae3  jz      short loc_180042AEC
0x180042ae5  cmp     eax, 490h
0x180042aea  jnz     short loc_180042B40
0x180042aec  mov     rcx, [rdi+8]; Handle
0x180042af0  xor     r8d, r8d; Timeout
0x180042af3  xor     edx, edx; Alertable
0x180042af5  call    cs:__imp_NtWaitForSingleObject
0x180042afc  nop     dword ptr [rax+rax+00h]
0x180042b01  test    eax, eax
0x180042b03  jnz     short loc_180042B2F
0x180042b05  jmp     loc_1800429A2
0x180042b0a  mov     rcx, [rbp+57h+var_18]
0x180042b0e  xor     rcx, rsp; StackCookie
0x180042b11  call    __security_check_cookie
0x180042b16  lea     r11, [rsp+0A0h+var_10]
0x180042b1e  mov     rbx, [r11+28h]
0x180042b22  mov     rsi, [r11+30h]
0x180042b26  mov     rsp, r11
0x180042b29  pop     r15
0x180042b2b  pop     rdi
0x180042b2c  pop     rbp
0x180042b2d  retn
0x180042b2f  bts     eax, 1Ch
0x180042b33  mov     edx, 1B6h
0x180042b38  mov     ecx, eax
0x180042b3a  call    GameInputFailFast
0x180042b3f  int     3; Trap to Debugger
0x180042b40  test    eax, eax
0x180042b42  jle     short loc_180042B4C
0x180042b44  movzx   eax, ax
0x180042b47  or      eax, 80070000h
0x180042b4c  mov     edx, 1B1h
0x180042b51  mov     ecx, eax
0x180042b53  call    GameInputFailFast
```
