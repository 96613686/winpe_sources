# Apx::ApfDevice::FindOrCreateApxRootContainer(void)

- ea: `0x18000f8fc`
- end: `0x18000fb63`
- name: `?FindOrCreateApxRootContainer@ApfDevice@Apx@@AEAAJXZ`
- size: `615`
- prototype: `__int64 __fastcall(unsigned __int64 this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000f2ac`

## callees

- `0x1800027c8`
- `0x18000a12c`
- `0x18000afac`
- `0x18000f8fc`
- `0x18001051c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000faab`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000faab`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000f99c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000f99c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f9ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f9ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fb18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fb18`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x18000f982`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x18000f982`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x18000fa8f`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x18000fa8f`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x18000fab7`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x18000fab7`

## pseudocode

```c
__int64 __fastcall Apx::ApfDevice::FindOrCreateApxRootContainer(unsigned __int64 this)
{
  signed int LastError; // eax
  unsigned int v3; // ebx
  _QWORD *v4; // rcx
  int v5; // eax
  DWORD v6; // esi
  __int64 v8; // [rsp+40h] [rbp-19h] BYREF
  _QWORD v9[4]; // [rsp+48h] [rbp-11h] BYREF
  int v10; // [rsp+68h] [rbp+Fh]
  const wchar_t *v11; // [rsp+70h] [rbp+17h]
  __int64 v12; // [rsp+78h] [rbp+1Fh]
  __int64 v13; // [rsp+80h] [rbp+27h]
  DEVNODE pdnDevInst; // [rsp+C8h] [rbp+6Fh] BYREF
  HANDLE hHandle; // [rsp+D0h] [rbp+77h] BYREF
  __int64 v16; // [rsp+D8h] [rbp+7Fh] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids);
  }
  v16 = 0;
  v8 = 72;
  memset_0(v9, 0, 0x40u);
  hHandle = 0;
  pdnDevInst = 0;
  if ( !CM_Locate_DevNodeW(&pdnDevInst, (DEVINSTID_W)L"SWD\\APXENUM\\0", 0) )
    goto LABEL_20;
  hHandle = CreateEventW(0, 1, 0, 0);
  if ( hHandle )
  {
    v9[3] = 0;
    v9[0] = L"0";
    v10 = 2;
    v9[1] = L"SWD\\APXENUM";
    v12 = 0;
    v9[2] = &dword_18002CB6C;
    v13 = 0;
    v11 = L"APX Device Bus";
    v5 = ((__int64 (__fastcall *)(const wchar_t *, const wchar_t *, __int64 *, _QWORD, _QWORD, void (__fastcall *)(struct HSWDEVICE__ *, int, void *, const unsigned __int16 *), HANDLE *, __int64 *))SwDeviceCreate)(
           L"APXENUM",
           L"HTREE\\ROOT\\0",
           &v8,
           0,
           0,
           Apx::ApfDevice::SwCreateApxRootContainerCallback,
           &hHandle,
           &v16);
    v3 = v5;
    if ( v5 != -2147024713 )
    {
      if ( v5 < 0 )
        goto LABEL_21;
      v6 = WaitForSingleObject(hHandle, 0x4E20u);
      SwDeviceClose(v16);
      if ( v6 )
      {
        v3 = -2147467259;
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 28) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_qdd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            38,
            WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids,
            ~this,
            v6,
            -2147467259);
          goto LABEL_21;
        }
        goto LABEL_22;
      }
    }
LABEL_20:
    v3 = 0;
    goto LABEL_21;
  }
  LastError = GetLastError();
  v3 = LastError;
  if ( LastError > 0 )
    v3 = (unsigned __int16)LastError | 0x80070000;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids, ~this, v3);
LABEL_21:
    v4 = WPP_GLOBAL_Control;
  }
LABEL_22:
  if ( hHandle )
  {
    CloseHandle(hHandle);
    v4 = WPP_GLOBAL_Control;
    hHandle = 0;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 5u )
    WPP_SF_(v4[2], 39, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids);
  return v3;
}

```

## disassembly

```asm
0x18000f8fc  push    rbp
0x18000f8fe  push    rbx
0x18000f8ff  push    rsi
0x18000f900  push    rdi
0x18000f901  push    r15
0x18000f903  lea     rbp, [rsp-37h]
0x18000f908  sub     rsp, 90h
0x18000f90f  mov     rdi, rcx
0x18000f912  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f919  lea     r15, WPP_GLOBAL_Control
0x18000f920  cmp     rcx, r15
0x18000f923  jz      short loc_18000F946
0x18000f925  test    byte ptr [rcx+1Ch], 1
0x18000f929  jz      short loc_18000F946
0x18000f92b  cmp     byte ptr [rcx+19h], 5
0x18000f92f  jb      short loc_18000F946
0x18000f931  mov     rcx, [rcx+10h]
0x18000f935  lea     r8, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids
0x18000f93c  mov     edx, 24h ; '$'
0x18000f941  call    WPP_SF_
0x18000f946  xor     edx, edx; Val
0x18000f948  mov     [rbp+57h+arg_18], 0
0x18000f950  lea     rcx, [rbp+57h+var_68]; void *
0x18000f954  mov     [rbp+57h+var_70], 48h ; 'H'
0x18000f95c  lea     r8d, [rdx+40h]; Size
0x18000f960  call    memset_0
0x18000f965  xor     r8d, r8d; ulFlags
0x18000f968  mov     [rbp+57h+hHandle], 0
0x18000f970  lea     rdx, pDeviceID; "SWD\\APXENUM\\0"
0x18000f977  mov     [rbp+57h+pdnDevInst], 0
0x18000f97e  lea     rcx, [rbp+57h+pdnDevInst]; pdnDevInst
0x18000f982  call    cs:__imp_CM_Locate_DevNodeW
0x18000f988  test    eax, eax
0x18000f98a  jz      loc_18000FB03
0x18000f990  xor     r9d, r9d; lpName
0x18000f993  xor     r8d, r8d; bInitialState
0x18000f996  xor     ecx, ecx; lpEventAttributes
0x18000f998  lea     edx, [r9+1]; bManualReset
0x18000f99c  call    cs:__imp_CreateEventW
0x18000f9a2  mov     [rbp+57h+hHandle], rax
0x18000f9a6  test    rax, rax
0x18000f9a9  jnz     short loc_18000FA08
0x18000f9ab  call    cs:__imp_GetLastError
0x18000f9b1  mov     ebx, eax
0x18000f9b3  test    eax, eax
0x18000f9b5  jle     short loc_18000F9C0
0x18000f9b7  movzx   ebx, ax
0x18000f9ba  or      ebx, 80070000h
0x18000f9c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f9c7  cmp     rcx, r15
0x18000f9ca  jz      loc_18000FB0C
0x18000f9d0  test    byte ptr [rcx+1Ch], 80h
0x18000f9d4  jz      loc_18000FB0C
0x18000f9da  cmp     byte ptr [rcx+19h], 2
0x18000f9de  jb      loc_18000FB0C
0x18000f9e4  mov     rcx, [rcx+10h]
0x18000f9e8  lea     r8, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids
0x18000f9ef  not     rdi
0x18000f9f2  mov     dword ptr [rsp+0B0h+var_90], ebx
0x18000f9f6  mov     r9, rdi
0x18000f9f9  mov     edx, 25h ; '%'
0x18000f9fe  call    WPP_SF_qd
0x18000fa03  jmp     loc_18000FB05
0x18000fa08  lea     rax, a0; "0"
0x18000fa0f  mov     [rbp+57h+var_50], 0
0x18000fa17  mov     [rbp+57h+var_68], rax
0x18000fa1b  lea     r8, [rbp+57h+var_70]
0x18000fa1f  lea     rax, aSwdApxenum; "SWD\\APXENUM"
0x18000fa26  mov     [rbp+57h+var_48], 2
0x18000fa2d  mov     [rbp+57h+var_60], rax
0x18000fa31  lea     rdx, aHtreeRoot0; "HTREE\\ROOT\\0"
0x18000fa38  lea     rax, dword_18002CB6C
0x18000fa3f  mov     [rbp+57h+var_38], 0
0x18000fa47  mov     [rbp+57h+var_58], rax
0x18000fa4b  lea     rcx, aApxenum; "APXENUM"
0x18000fa52  lea     rax, aApxDeviceBus; "APX Device Bus"
0x18000fa59  mov     [rbp+57h+var_30], 0
0x18000fa61  mov     [rbp+57h+var_40], rax
0x18000fa65  xor     r9d, r9d
0x18000fa68  lea     rax, [rbp+57h+arg_18]
0x18000fa6c  mov     [rsp+0B0h+var_78], rax
0x18000fa71  lea     rax, [rbp+57h+hHandle]
0x18000fa75  mov     [rsp+0B0h+var_80], rax
0x18000fa7a  lea     rax, ?SwCreateApxRootContainerCallback@ApfDevice@Apx@@CAXPEAUHSWDEVICE__@@JPEAXPEBG@Z; Apx::ApfDevice::SwCreateApxRootContainerCallback(HSWDEVICE__ *,long,void *,ushort const *)
0x18000fa81  mov     [rsp+0B0h+var_88], rax
0x18000fa86  mov     [rsp+0B0h+var_90], 0
0x18000fa8f  call    cs:__imp_SwDeviceCreate
0x18000fa95  mov     ebx, eax
0x18000fa97  cmp     eax, 800700B7h
0x18000fa9c  jz      short loc_18000FB03
0x18000fa9e  test    eax, eax
0x18000faa0  js      short loc_18000FB05
0x18000faa2  mov     rcx, [rbp+57h+hHandle]; hHandle
0x18000faa6  mov     edx, 4E20h; dwMilliseconds
0x18000faab  call    cs:__imp_WaitForSingleObject
0x18000fab1  mov     rcx, [rbp+57h+arg_18]
0x18000fab5  mov     esi, eax
0x18000fab7  call    cs:__imp_SwDeviceClose
0x18000fabd  test    esi, esi
0x18000fabf  jz      short loc_18000FB03
0x18000fac1  mov     ebx, 80004005h
0x18000fac6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000facd  cmp     rcx, r15
0x18000fad0  jz      short loc_18000FB0C
0x18000fad2  test    byte ptr [rcx+1Ch], 80h
0x18000fad6  jz      short loc_18000FB0C
0x18000fad8  cmp     byte ptr [rcx+19h], 2
0x18000fadc  jb      short loc_18000FB0C
0x18000fade  mov     rcx, [rcx+10h]
0x18000fae2  lea     r8, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids
0x18000fae9  not     rdi
0x18000faec  mov     dword ptr [rsp+0B0h+var_88], ebx
0x18000faf0  mov     r9, rdi
0x18000faf3  mov     dword ptr [rsp+0B0h+var_90], esi
0x18000faf7  mov     edx, 26h ; '&'
0x18000fafc  call    WPP_SF_qdd
0x18000fb01  jmp     short loc_18000FB05
0x18000fb03  xor     ebx, ebx
0x18000fb05  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb0c  mov     rax, [rbp+57h+hHandle]
0x18000fb10  test    rax, rax
0x18000fb13  jz      short loc_18000FB2D
0x18000fb15  mov     rcx, rax; hObject
0x18000fb18  call    cs:__imp_CloseHandle
0x18000fb1e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb25  mov     [rbp+57h+hHandle], 0
0x18000fb2d  cmp     rcx, r15
0x18000fb30  jz      short loc_18000FB53
0x18000fb32  test    byte ptr [rcx+1Ch], 1
0x18000fb36  jz      short loc_18000FB53
0x18000fb38  cmp     byte ptr [rcx+19h], 5
0x18000fb3c  jb      short loc_18000FB53
0x18000fb3e  mov     rcx, [rcx+10h]
0x18000fb42  lea     r8, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids
0x18000fb49  mov     edx, 27h ; '''
0x18000fb4e  call    WPP_SF_
0x18000fb53  mov     eax, ebx
0x18000fb55  add     rsp, 90h
0x18000fb5c  pop     r15
0x18000fb5e  pop     rdi
0x18000fb5f  pop     rsi
0x18000fb60  pop     rbx
0x18000fb61  pop     rbp
0x18000fb62  retn
```
