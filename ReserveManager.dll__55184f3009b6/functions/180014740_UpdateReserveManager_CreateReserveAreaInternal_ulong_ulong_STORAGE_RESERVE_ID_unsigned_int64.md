# UpdateReserveManager::CreateReserveAreaInternal(ulong,ulong,_STORAGE_RESERVE_ID,unsigned __int64)

- ea: `0x180014740`
- end: `0x18001484e`
- name: `?CreateReserveAreaInternal@UpdateReserveManager@@AEAAJKKW4_STORAGE_RESERVE_ID@@_K@Z`
- size: `270`
- prototype: `__int64 __fastcall(UpdateReserveManager *this, __int64, int, enum _STORAGE_RESERVE_ID)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180015b34`
- `0x18001fd00`

## callees

- `0x180003870`
- `0x18000fafc`
- `0x180014740`
- `0x180015ad0`
- `0x1800248e0`

## import_xrefs

- `ntdll!NtFsControlFile` at `0x1800147e1`
- `ntdll!NtFsControlFile` at `0x1800147e1`

## string_xrefs

- `0x1800147eb`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x1800147fe`: `UpdateReserveManager::CreateReserveAreaInternal`
- `0x180014809`: `::NtFsControlFile(m_VolumePathHandle, nullptr, nullptr, nullptr, &IoStatusBlock, ( ((0x00000009) << 16) | ((0) << 14) | ((260) << 2) | (0) ), &DefineInput, sizeof(DefineInput), nullptr, 0)`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::CreateReserveAreaInternal(
        UpdateReserveManager *this,
        __int64 a2,
        int a3,
        enum _STORAGE_RESERVE_ID a4)
{
  __int64 result; // rax
  void *v8; // rcx
  int v9; // eax
  unsigned int v10; // ebx
  _QWORD v11[4]; // [rsp+50h] [rbp-31h] BYREF
  _DWORD InputBuffer[6]; // [rsp+70h] [rbp-11h] BYREF
  __int64 v13; // [rsp+88h] [rbp+7h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+90h] [rbp+Fh] BYREF

  result = UpdateReserveManager::EnsureNotInSafeMode(this);
  if ( (int)result >= 0 )
  {
    v8 = (void *)*((_QWORD *)this + 16);
    InputBuffer[0] = 1;
    InputBuffer[1] = 1;
    InputBuffer[3] = 1;
    InputBuffer[2] = 16;
    InputBuffer[4] = a4;
    InputBuffer[5] = a3;
    v13 = 0;
    IoStatusBlock = 0;
    v9 = NtFsControlFile(v8, 0, 0, 0, &IoStatusBlock, 0x90410u, InputBuffer, 0x20u, 0, 0);
    if ( v9 >= 0 )
    {
      return 0;
    }
    else
    {
      v11[2] = 3966;
      v11[0] = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
      v11[1] = "UpdateReserveManager::CreateReserveAreaInternal";
      v11[3] = "::NtFsControlFile(m_VolumePathHandle, nullptr, nullptr, nullptr, &IoStatusBlock, ( ((0x00000009) << 16) |"
               " ((0) << 14) | ((260) << 2) | (0) ), &DefineInput, sizeof(DefineInput), nullptr, 0)";
      v10 = ConvertNtStatusToHResult(v9);
      RtlReportErrorOrigination(v11, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, v10);
      return v10;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180014740  push    rbp
0x180014742  push    rbx
0x180014743  push    rsi
0x180014744  push    rdi
0x180014745  lea     rbp, [rsp-37h]
0x18001474a  sub     rsp, 0B8h
0x180014751  mov     rax, cs:__security_cookie
0x180014758  xor     rax, rsp
0x18001475b  mov     [rbp+4Fh+var_30], rax
0x18001475f  mov     edi, r9d
0x180014762  mov     esi, r8d
0x180014765  mov     rbx, rcx
0x180014768  call    ?EnsureNotInSafeMode@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::EnsureNotInSafeMode(void)
0x18001476d  test    eax, eax
0x18001476f  js      loc_180014836
0x180014775  mov     rcx, [rbx+80h]; FileHandle
0x18001477c  mov     eax, 1
0x180014781  mov     [rsp+0D0h+OutputBufferLength], 0; OutputBufferLength
0x180014789  xorps   xmm0, xmm0
0x18001478c  mov     [rsp+0D0h+OutputBuffer], 0; OutputBuffer
0x180014795  xor     r9d, r9d; ApcContext
0x180014798  mov     [rbp+4Fh+var_60], eax
0x18001479b  xor     r8d, r8d; ApcRoutine
0x18001479e  mov     [rbp+4Fh+var_5C], eax
0x1800147a1  xor     edx, edx; Event
0x1800147a3  mov     [rbp+4Fh+var_54], eax
0x1800147a6  lea     rax, [rbp+4Fh+var_60]
0x1800147aa  mov     [rsp+0D0h+InputBufferLength], 20h ; ' '; InputBufferLength
0x1800147b2  mov     [rsp+0D0h+InputBuffer], rax; InputBuffer
0x1800147b7  lea     rax, [rbp+4Fh+var_40]
0x1800147bb  mov     [rsp+0D0h+FsControlCode], 90410h; FsControlCode
0x1800147c3  mov     [rsp+0D0h+IoStatusBlock], rax; IoStatusBlock
0x1800147c8  mov     [rbp+4Fh+var_58], 10h
0x1800147cf  mov     [rbp+4Fh+var_50], edi
0x1800147d2  mov     [rbp+4Fh+var_4C], esi
0x1800147d5  mov     [rbp+4Fh+var_48], 0
0x1800147dd  movups  xmmword ptr [rbp+4Fh+var_40], xmm0
0x1800147e1  call    cs:__imp_NtFsControlFile
0x1800147e7  test    eax, eax
0x1800147e9  jns     short loc_180014834
0x1800147eb  lea     rcx, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x1800147f2  mov     [rbp+4Fh+var_70], 0F7Eh
0x1800147fa  mov     [rbp+4Fh+var_80], rcx
0x1800147fe  lea     rcx, aUpdatereservem_45; "UpdateReserveManager::CreateReserveArea"...
0x180014805  mov     [rbp+4Fh+var_78], rcx
0x180014809  lea     rcx, aNtfscontrolfil_1; "::NtFsControlFile(m_VolumePathHandle, n"...
0x180014810  mov     [rbp+4Fh+var_68], rcx
0x180014814  mov     ecx, eax; Status
0x180014816  call    ConvertNtStatusToHResult
0x18001481b  mov     r8d, eax
0x18001481e  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180014825  lea     rcx, [rbp+4Fh+var_80]
0x180014829  mov     ebx, eax
0x18001482b  call    RtlReportErrorOrigination
0x180014830  mov     eax, ebx
0x180014832  jmp     short loc_180014836
0x180014834  xor     eax, eax
0x180014836  mov     rcx, [rbp+4Fh+var_30]
0x18001483a  xor     rcx, rsp; StackCookie
0x18001483d  call    __security_check_cookie
0x180014842  add     rsp, 0B8h
0x180014849  pop     rdi
0x18001484a  pop     rsi
0x18001484b  pop     rbx
0x18001484c  pop     rbp
0x18001484d  retn
```
