# WaitForInstallMutex

- ea: `0x140019700`
- end: `0x140019926`
- name: `WaitForInstallMutex`
- size: `550`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140018dc0`

## callees

- `0x140018dc0`
- `0x1400191fc`
- `0x14001923c`
- `0x140019700`
- `0x14002102c`
- `0x140027864`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x14001977a`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x14001977a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140019879`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140019879`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019787`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019787`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400197c2`
- `DEVRTL!DevRtlWriteTextLog` at `0x140019839`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400197c2`
- `DEVRTL!DevRtlWriteTextLog` at `0x140019839`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x140019743`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x140019743`

## string_xrefs

- `0x1400197ab`: `Failed to create drvinst install mutex. Error = 0x%08X`
- `0x140019822`: `Waiting for previous device install to complete.`

## pseudocode

```c
__int64 __fastcall WaitForInstallMutex(__int64 a1)
{
  unsigned int v2; // [rsp+30h] [rbp-48h]
  DWORD LastError; // [rsp+34h] [rbp-44h]
  DWORD v4; // [rsp+38h] [rbp-40h]
  int v5; // [rsp+3Ch] [rbp-3Ch]
  int v6; // [rsp+40h] [rbp-38h]
  __int64 ThreadLogToken; // [rsp+50h] [rbp-28h]

  v2 = 0;
  v5 = 0;
  v6 = 0;
  ThreadLogToken = DevRtlGetThreadLogToken();
  if ( (unsigned int)DevUtilsIsVolumeSnapshotDevice(a1) )
  {
    return 0;
  }
  else
  {
    g_hMutex = CreateMutexW(0, 1, L"DrvInst.exe_mutex_{5B10AC83-4F13-4fde-8C0B-B85681BA8D73}");
    LastError = GetLastError();
    if ( g_hMutex )
    {
      GetCurrentTickCount();
      if ( LastError == 183 )
      {
        if ( (Microsoft_Windows_UserPnpEnableBits & 4) != 0 )
          McTemplateU0_EtwEventWriteTransfer(&userpnp_Context, ENTER_CORE_DEVICE_INSTALL_WAIT);
        while ( 1 )
        {
          DevRtlWriteTextLog(ThreadLogToken, 1, 65540, "Waiting for previous device install to complete.");
          DrvInstActionCallback(0, 0);
          GetCurrentTickCount();
          ++v6;
          if ( (unsigned int)ShutdownPending() )
            break;
          v4 = WaitForSingleObjectEx(g_hMutex, 0xEA60u, 0);
          if ( !v4 || v4 == 128 )
          {
            DrvInstActionCallback(0, 0);
            v5 = 1;
            break;
          }
        }
        if ( (Microsoft_Windows_UserPnpEnableBits & 4) != 0 )
          McTemplateU0_EtwEventWriteTransfer(&userpnp_Context, EXIT_CORE_DEVICE_INSTALL_WAIT);
      }
      else
      {
        v5 = 1;
      }
      if ( (unsigned int)ShutdownPending() )
      {
        v2 = 1115;
        if ( v5 )
          DrvInstActionCallback(5, 0);
      }
    }
    else
    {
      v2 = LastError;
      DevRtlWriteTextLog(ThreadLogToken, 1, 1, "Failed to create drvinst install mutex. Error = 0x%08X", LastError);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x140019700  mov     [rsp+arg_0], rcx
0x140019705  sub     rsp, 78h
0x140019709  mov     [rsp+78h+var_48], 0
0x140019711  mov     [rsp+78h+var_44], 0
0x140019719  mov     [rsp+78h+var_40], 0FFFFFFFFh
0x140019721  mov     [rsp+78h+var_3C], 0
0x140019729  mov     [rsp+78h+var_20], 0
0x140019732  mov     [rsp+78h+var_18], 0
0x14001973b  mov     [rsp+78h+var_38], 0
0x140019743  call    cs:__imp_DevRtlGetThreadLogToken
0x140019749  mov     [rsp+78h+var_28], rax
0x14001974e  mov     rcx, [rsp+78h+arg_0]
0x140019756  call    DevUtilsIsVolumeSnapshotDevice
0x14001975b  test    eax, eax
0x14001975d  jz      short loc_14001976C
0x14001975f  mov     [rsp+78h+var_48], 0
0x140019767  jmp     loc_14001991D
0x14001976c  lea     r8, Name; "DrvInst.exe_mutex_{5B10AC83-4F13-4fde-8"...
0x140019773  mov     edx, 1; bInitialOwner
0x140019778  xor     ecx, ecx; lpMutexAttributes
0x14001977a  call    cs:__imp_CreateMutexW
0x140019780  mov     cs:g_hMutex, rax
0x140019787  call    cs:__imp_GetLastError
0x14001978d  mov     [rsp+78h+var_44], eax
0x140019791  cmp     cs:g_hMutex, 0
0x140019799  jnz     short loc_1400197CE
0x14001979b  mov     eax, [rsp+78h+var_44]
0x14001979f  mov     [rsp+78h+var_48], eax
0x1400197a3  mov     eax, [rsp+78h+var_48]
0x1400197a7  mov     [rsp+78h+var_58], eax
0x1400197ab  lea     r9, aFailedToCreate_4; "Failed to create drvinst install mutex."...
0x1400197b2  mov     r8d, 1
0x1400197b8  mov     edx, 1
0x1400197bd  mov     rcx, [rsp+78h+var_28]
0x1400197c2  call    cs:__imp_DevRtlWriteTextLog
0x1400197c8  nop
0x1400197c9  jmp     loc_14001991D
0x1400197ce  call    GetCurrentTickCount
0x1400197d3  mov     [rsp+78h+var_20], rax
0x1400197d8  cmp     [rsp+78h+var_44], 0B7h
0x1400197e0  jnz     loc_1400198ED
0x1400197e6  mov     eax, 1
0x1400197eb  imul    rax, 0
0x1400197ef  lea     rcx, Microsoft_Windows_UserPnpEnableBits
0x1400197f6  movzx   eax, byte ptr [rcx+rax]
0x1400197fa  and     eax, 4
0x1400197fd  test    eax, eax
0x1400197ff  jz      short loc_14001981A
0x140019801  lea     rdx, ENTER_CORE_DEVICE_INSTALL_WAIT
0x140019808  lea     rcx, userpnp_Context
0x14001980f  call    McTemplateU0_EtwEventWriteTransfer
0x140019814  mov     [rsp+78h+var_34], eax
0x140019818  jmp     short loc_140019822
0x14001981a  mov     [rsp+78h+var_34], 0
0x140019822  lea     r9, aWaitingForPrev; "Waiting for previous device install to "...
0x140019829  mov     r8d, 10004h
0x14001982f  mov     edx, 1
0x140019834  mov     rcx, [rsp+78h+var_28]
0x140019839  call    cs:__imp_DevRtlWriteTextLog
0x14001983f  xor     r8d, r8d
0x140019842  xor     edx, edx
0x140019844  xor     ecx, ecx
0x140019846  call    DrvInstActionCallback
0x14001984b  call    GetCurrentTickCount
0x140019850  mov     [rsp+78h+var_18], rax
0x140019855  mov     eax, [rsp+78h+var_38]
0x140019859  inc     eax
0x14001985b  mov     [rsp+78h+var_38], eax
0x14001985f  call    ShutdownPending
0x140019864  test    eax, eax
0x140019866  jz      short loc_14001986A
0x140019868  jmp     short loc_1400198AF
0x14001986a  xor     r8d, r8d; bAlertable
0x14001986d  mov     edx, 0EA60h; dwMilliseconds
0x140019872  mov     rcx, cs:g_hMutex; hHandle
0x140019879  call    cs:__imp_WaitForSingleObjectEx
0x14001987f  mov     [rsp+78h+var_40], eax
0x140019883  cmp     [rsp+78h+var_40], 0
0x140019888  jz      short loc_140019894
0x14001988a  cmp     [rsp+78h+var_40], 80h
0x140019892  jnz     short loc_1400198AA
0x140019894  xor     r8d, r8d
0x140019897  xor     edx, edx
0x140019899  xor     ecx, ecx
0x14001989b  call    DrvInstActionCallback
0x1400198a0  mov     [rsp+78h+var_3C], 1
0x1400198a8  jmp     short loc_1400198AF
0x1400198aa  jmp     loc_140019822
0x1400198af  mov     eax, 1
0x1400198b4  imul    rax, 0
0x1400198b8  lea     rcx, Microsoft_Windows_UserPnpEnableBits
0x1400198bf  movzx   eax, byte ptr [rcx+rax]
0x1400198c3  and     eax, 4
0x1400198c6  test    eax, eax
0x1400198c8  jz      short loc_1400198E3
0x1400198ca  lea     rdx, EXIT_CORE_DEVICE_INSTALL_WAIT
0x1400198d1  lea     rcx, userpnp_Context
0x1400198d8  call    McTemplateU0_EtwEventWriteTransfer
0x1400198dd  mov     [rsp+78h+var_30], eax
0x1400198e1  jmp     short loc_1400198EB
0x1400198e3  mov     [rsp+78h+var_30], 0
0x1400198eb  jmp     short loc_1400198F5
0x1400198ed  mov     [rsp+78h+var_3C], 1
0x1400198f5  call    ShutdownPending
0x1400198fa  test    eax, eax
0x1400198fc  jz      short loc_14001991D
0x1400198fe  mov     [rsp+78h+var_48], 45Bh
0x140019906  cmp     [rsp+78h+var_3C], 0
0x14001990b  jz      short loc_14001991D
0x14001990d  xor     r8d, r8d
0x140019910  xor     edx, edx
0x140019912  mov     ecx, 5
0x140019917  call    DrvInstActionCallback
0x14001991c  nop
0x14001991d  mov     eax, [rsp+78h+var_48]
0x140019921  add     rsp, 78h
0x140019925  retn
```
