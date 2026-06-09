# UpdateReserveManager::SetReserveSizes(unsigned __int64,unsigned __int64,unsigned __int64,bool)

- ea: `0x18001faf0`
- end: `0x18001fcf7`
- name: `?SetReserveSizes@UpdateReserveManager@@AEAAJ_K00_N@Z`
- size: `519`
- prototype: `__int64 __fastcall(HANDLE *this, unsigned __int64, unsigned __int64, unsigned __int64, bool)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x180019634`

## callees

- `0x180003870`
- `0x180003c84`
- `0x1800044e0`
- `0x18000fafc`
- `0x180015ad0`
- `0x18001faf0`

## import_xrefs

- `ntdll!NtFsControlFile` at `0x18001fc7f`
- `ntdll!NtFsControlFile` at `0x18001fc7f`

## string_xrefs

- `0x18001fb43`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001fb91`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001fbbd`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001fc91`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001fb4e`: `UpdateReserveManager::SetReserveSizes`
- `0x18001fb9c`: `UpdateReserveManager::SetReserveSizes`
- `0x18001fbc8`: `UpdateReserveManager::SetReserveSizes`
- `0x18001fc9c`: `UpdateReserveManager::SetReserveSizes`
- `0x18001fbdb`: `::ULongLongToLongLong(UpdateScratchReserveSize, &SignedUpdateScratchReserveSize)`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::SetReserveSizes(
        HANDLE *this,
        unsigned __int64 a2,
        unsigned __int64 a3,
        unsigned __int64 a4,
        bool a5)
{
  __int64 result; // rax
  const char *v10; // rax
  _DWORD *InputBuffer; // rbx
  NTSTATUS v12; // edi
  const char *v13; // [rsp+50h] [rbp-31h] BYREF
  const char *v14; // [rsp+58h] [rbp-29h]
  __int64 v15; // [rsp+60h] [rbp-21h]
  const char *v16; // [rsp+68h] [rbp-19h]
  _DWORD *v17; // [rsp+70h] [rbp-11h]
  __int64 v18; // [rsp+78h] [rbp-9h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-1h] BYREF

  v18 = -2;
  result = UpdateReserveManager::EnsureNotInSafeMode((UpdateReserveManager *)this);
  if ( (int)result >= 0 )
  {
    if ( a2 > 0x7FFFFFFFFFFFFFFFLL )
    {
      v13 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
      v14 = "UpdateReserveManager::SetReserveSizes";
      v15 = 2668;
      v10 = "::ULongLongToLongLong(HardReserveSize, &SignedHardReserveSize)";
LABEL_4:
      v16 = v10;
      RtlReportErrorOrigination(&v13, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2147942934LL);
      return 2147942934LL;
    }
    if ( a3 > 0x7FFFFFFFFFFFFFFFLL )
    {
      v13 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
      v14 = "UpdateReserveManager::SetReserveSizes";
      v15 = 2670;
      v10 = "::ULongLongToLongLong(SoftReserveSize, &SignedSoftReserveSize)";
      goto LABEL_4;
    }
    if ( a4 > 0x7FFFFFFFFFFFFFFFLL )
    {
      v13 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
      v14 = "UpdateReserveManager::SetReserveSizes";
      v15 = 2672;
      v10 = "::ULongLongToLongLong(UpdateScratchReserveSize, &SignedUpdateScratchReserveSize)";
      goto LABEL_4;
    }
    InputBuffer = operator new[](0x40u);
    v17 = InputBuffer;
    *InputBuffer = 1;
    InputBuffer[1] = 1;
    InputBuffer[2] = 16;
    InputBuffer[3] = 3;
    InputBuffer[4] = 1;
    InputBuffer[5] = 1;
    *((_QWORD *)InputBuffer + 3) = a2;
    InputBuffer[8] = 2;
    InputBuffer[9] = 160;
    *((_QWORD *)InputBuffer + 5) = a3;
    InputBuffer[12] = 3;
    InputBuffer[13] = 1;
    *((_QWORD *)InputBuffer + 7) = a4;
    IoStatusBlock = 0;
    v12 = NtFsControlFile(this[16], 0, 0, 0, &IoStatusBlock, 0x90410u, InputBuffer, 0x40u, 0, 0);
    if ( v12 >= 0 )
    {
      v12 = 0;
    }
    else if ( !a5 )
    {
      v13 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
      v14 = "UpdateReserveManager::SetReserveSizes";
      v15 = 2727;
      v16 = "Status";
      RtlReportErrorOrigination(&v13, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)v12);
    }
    operator delete(InputBuffer);
    return (unsigned int)v12;
  }
  return result;
}

```

## disassembly

```asm
0x18001faf0  push    rbp
0x18001faf2  push    rbx
0x18001faf3  push    rsi
0x18001faf4  push    rdi
0x18001faf5  push    r14
0x18001faf7  push    r15
0x18001faf9  lea     rbp, [rsp-27h]
0x18001fafe  sub     rsp, 0A8h
0x18001fb05  mov     [rbp+4Fh+var_58], 0FFFFFFFFFFFFFFFEh
0x18001fb0d  mov     rax, cs:__security_cookie
0x18001fb14  xor     rax, rsp
0x18001fb17  mov     [rbp+4Fh+var_40], rax
0x18001fb1b  mov     rdi, r9
0x18001fb1e  mov     rsi, r8
0x18001fb21  mov     r14, rdx
0x18001fb24  mov     r15, rcx
0x18001fb27  call    ?EnsureNotInSafeMode@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::EnsureNotInSafeMode(void)
0x18001fb2c  test    eax, eax
0x18001fb2e  js      loc_18001FCDB
0x18001fb34  mov     rax, 7FFFFFFFFFFFFFFFh
0x18001fb3e  cmp     r14, rax
0x18001fb41  jbe     short loc_18001FB8C
0x18001fb43  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001fb4a  mov     [rbp+4Fh+var_80], rax
0x18001fb4e  lea     rax, aUpdatereservem_20; "UpdateReserveManager::SetReserveSizes"
0x18001fb55  mov     [rbp+4Fh+var_78], rax
0x18001fb59  mov     [rbp+4Fh+var_70], 0A6Ch
0x18001fb61  lea     rax, aUlonglongtolon_1; "::ULongLongToLongLong(HardReserveSize, "...
0x18001fb68  mov     [rbp+4Fh+var_68], rax
0x18001fb6c  mov     r8d, 80070216h
0x18001fb72  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18001fb79  lea     rcx, [rbp+4Fh+var_80]
0x18001fb7d  call    RtlReportErrorOrigination
0x18001fb82  mov     eax, 80070216h
0x18001fb87  jmp     loc_18001FCDB
0x18001fb8c  cmp     rsi, rax
0x18001fb8f  jbe     short loc_18001FBB8
0x18001fb91  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001fb98  mov     [rbp+4Fh+var_80], rax
0x18001fb9c  lea     rax, aUpdatereservem_20; "UpdateReserveManager::SetReserveSizes"
0x18001fba3  mov     [rbp+4Fh+var_78], rax
0x18001fba7  mov     [rbp+4Fh+var_70], 0A6Eh
0x18001fbaf  lea     rax, aUlonglongtolon; "::ULongLongToLongLong(SoftReserveSize, "...
0x18001fbb6  jmp     short loc_18001FB68
0x18001fbb8  cmp     rdi, rax
0x18001fbbb  jbe     short loc_18001FBE4
0x18001fbbd  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001fbc4  mov     [rbp+4Fh+var_80], rax
0x18001fbc8  lea     rax, aUpdatereservem_20; "UpdateReserveManager::SetReserveSizes"
0x18001fbcf  mov     [rbp+4Fh+var_78], rax
0x18001fbd3  mov     [rbp+4Fh+var_70], 0A70h
0x18001fbdb  lea     rax, aUlonglongtolon_2; "::ULongLongToLongLong(UpdateScratchRese"...
0x18001fbe2  jmp     short loc_18001FB68
0x18001fbe4  mov     [rbp+4Fh+var_60], 0
0x18001fbec  mov     ecx, 40h ; '@'; unsigned __int64
0x18001fbf1  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001fbf6  mov     rbx, rax
0x18001fbf9  mov     [rbp+4Fh+var_60], rax
0x18001fbfd  mov     ecx, 1
0x18001fc02  mov     [rax], ecx
0x18001fc04  mov     [rax+4], ecx
0x18001fc07  mov     dword ptr [rax+8], 10h
0x18001fc0e  lea     eax, [rcx+2]
0x18001fc11  mov     [rbx+0Ch], eax
0x18001fc14  mov     [rbx+10h], ecx
0x18001fc17  mov     [rbx+14h], ecx
0x18001fc1a  mov     [rbx+18h], r14
0x18001fc1e  mov     dword ptr [rbx+20h], 2
0x18001fc25  mov     dword ptr [rbx+24h], 0A0h
0x18001fc2c  mov     [rbx+28h], rsi
0x18001fc30  mov     [rbx+30h], eax
0x18001fc33  mov     [rbx+34h], ecx
0x18001fc36  mov     [rbx+38h], rdi
0x18001fc3a  xorps   xmm0, xmm0
0x18001fc3d  movups  xmmword ptr [rbp+4Fh+var_50], xmm0
0x18001fc41  mov     [rsp+0D0h+OutputBufferLength], 0; OutputBufferLength
0x18001fc49  mov     [rsp+0D0h+OutputBuffer], 0; OutputBuffer
0x18001fc52  mov     [rsp+0D0h+InputBufferLength], 40h ; '@'; InputBufferLength
0x18001fc5a  mov     [rsp+0D0h+InputBuffer], rbx; InputBuffer
0x18001fc5f  mov     [rsp+0D0h+FsControlCode], 90410h; FsControlCode
0x18001fc67  lea     rax, [rbp+4Fh+var_50]
0x18001fc6b  mov     [rsp+0D0h+IoStatusBlock], rax; IoStatusBlock
0x18001fc70  xor     r9d, r9d; ApcContext
0x18001fc73  xor     r8d, r8d; ApcRoutine
0x18001fc76  xor     edx, edx; Event
0x18001fc78  mov     rcx, [r15+80h]; FileHandle
0x18001fc7f  call    cs:__imp_NtFsControlFile
0x18001fc85  mov     edi, eax
0x18001fc87  test    eax, eax
0x18001fc89  jns     short loc_18001FCCF
0x18001fc8b  cmp     [rbp+4Fh+arg_20], 0
0x18001fc8f  jnz     short loc_18001FCD1
0x18001fc91  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001fc98  mov     [rbp+4Fh+var_80], rax
0x18001fc9c  lea     rax, aUpdatereservem_20; "UpdateReserveManager::SetReserveSizes"
0x18001fca3  mov     [rbp+4Fh+var_78], rax
0x18001fca7  mov     [rbp+4Fh+var_70], 0AA7h
0x18001fcaf  lea     rax, aStatus; "Status"
0x18001fcb6  mov     [rbp+4Fh+var_68], rax
0x18001fcba  mov     r8d, edi
0x18001fcbd  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18001fcc4  lea     rcx, [rbp+4Fh+var_80]
0x18001fcc8  call    RtlReportErrorOrigination
0x18001fccd  jmp     short loc_18001FCD1
0x18001fccf  xor     edi, edi
0x18001fcd1  mov     rcx, rbx; void *
0x18001fcd4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001fcd9  mov     eax, edi
0x18001fcdb  mov     rcx, [rbp+4Fh+var_40]
0x18001fcdf  xor     rcx, rsp; StackCookie
0x18001fce2  call    __security_check_cookie
0x18001fce7  add     rsp, 0A8h
0x18001fcee  pop     r15
0x18001fcf0  pop     r14
0x18001fcf2  pop     rdi
0x18001fcf3  pop     rsi
0x18001fcf4  pop     rbx
0x18001fcf5  pop     rbp
0x18001fcf6  retn
```
