# WindowsPerformanceRecorder::CControlManager::RestoreHardwareCounter(WindowsPerformanceRecorder::CETWProperties &)

- ea: `0x18005d068`
- end: `0x18005d1b6`
- name: `?RestoreHardwareCounter@CControlManager@WindowsPerformanceRecorder@@AEAAJAEAVCETWProperties@2@@Z`
- size: `334`
- prototype: `__int64 __fastcall(WindowsPerformanceRecorder::CControlManager *__hidden this, struct WindowsPerformanceRecorder::CETWProperties *)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180032adc`
- `0x180058800`
- `0x18005deb0`

## callees

- `0x18001e6e0`
- `0x180039de4`
- `0x18005d068`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x18005d0cc`
- `ntdll!RtlAdjustPrivilege` at `0x18005d12f`
- `ntdll!RtlAdjustPrivilege` at `0x18005d0cc`
- `ntdll!RtlAdjustPrivilege` at `0x18005d12f`
- `ntdll!NtSetSystemInformation` at `0x18005d103`
- `ntdll!NtSetSystemInformation` at `0x18005d103`
- `ntdll!NtSetIntervalProfile` at `0x18005d113`
- `ntdll!NtSetIntervalProfile` at `0x18005d113`

## pseudocode

```c
__int64 __fastcall WindowsPerformanceRecorder::CControlManager::RestoreHardwareCounter(
        WindowsPerformanceRecorder::CControlManager *this,
        struct WindowsPerformanceRecorder::CETWProperties *a2)
{
  __int64 v2; // rsi
  __int64 v4; // rbx
  KPROFILE_SOURCE v7; // r14d
  NTSTATUS v8; // edi
  const struct _GUID *v9; // r8
  NTSTATUS v10; // eax
  unsigned int v11; // edi
  struct IControlErrorInfo *v12; // [rsp+38h] [rbp-30h]
  unsigned __int8 OldValue; // [rsp+78h] [rbp+10h] BYREF
  int SystemInformation; // [rsp+80h] [rbp+18h] BYREF
  int v15; // [rsp+84h] [rbp+1Ch]

  v2 = *((_QWORD *)a2 + 13);
  v4 = *((_QWORD *)a2 + 12);
  if ( (unsigned int)((v2 - v4) >> 4) )
  {
    while ( v4 != v2 )
    {
      if ( *(_DWORD *)(v4 + 12) )
      {
        v7 = *(_DWORD *)(v4 + 8);
        OldValue = 0;
        v8 = RtlAdjustPrivilege(0xBu, 1u, 0, &OldValue);
        if ( v8 >= 0 )
        {
          if ( v7 )
          {
            v10 = NtSetIntervalProfile(0x10000u, v7);
          }
          else
          {
            SystemInformation = 3;
            v15 = 10000;
            v10 = NtSetSystemInformation(SystemPerformanceTraceInformation, &SystemInformation, 8u);
          }
          v8 = v10;
        }
        if ( !OldValue )
          RtlAdjustPrivilege(0xBu, 0, 0, &OldValue);
        if ( v8 < 0 )
        {
          v11 = v8 | 0x10000000;
          WindowsPerformanceRecorder::CControlManager::AddProviderControlWarningInfo(
            this,
            v11,
            v9,
            0,
            *((const unsigned __int16 **)a2 + 4),
            *((const unsigned __int16 **)a2 + 40),
            0,
            v12);
          WindowsPerformanceRecorder::TraceHR(
            (WindowsPerformanceRecorder *)3,
            (unsigned __int8)"RestoreHardwareCounter",
            (const char *)0x1ADB,
            v11,
            "%ws",
            *((const char **)a2 + 4));
          if ( *((_BYTE *)a2 + 40) )
            return v11;
        }
      }
      v4 += 16;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18005d068  mov     [rsp+arg_0], rbx
0x18005d06d  push    rbp
0x18005d06e  push    rsi
0x18005d06f  push    rdi
0x18005d070  push    r14
0x18005d072  push    r15
0x18005d074  sub     rsp, 40h
0x18005d078  mov     rsi, [rdx+68h]
0x18005d07c  mov     rbp, rdx
0x18005d07f  mov     rbx, [rdx+60h]
0x18005d083  mov     rax, rsi
0x18005d086  sub     rax, rbx
0x18005d089  mov     r15, rcx
0x18005d08c  sar     rax, 4
0x18005d090  test    eax, eax
0x18005d092  jnz     loc_18005D1A1
0x18005d098  xor     eax, eax
0x18005d09a  mov     rbx, [rsp+68h+arg_0]
0x18005d09f  add     rsp, 40h
0x18005d0a3  pop     r15
0x18005d0a5  pop     r14
0x18005d0a7  pop     rdi
0x18005d0a8  pop     rsi
0x18005d0a9  pop     rbp
0x18005d0aa  retn
0x18005d0ab  cmp     dword ptr [rbx+0Ch], 0
0x18005d0af  jz      loc_18005D19D
0x18005d0b5  mov     r14d, [rbx+8]
0x18005d0b9  lea     r9, [rsp+68h+OldValue]; OldValue
0x18005d0be  xor     r8d, r8d; ForThread
0x18005d0c1  mov     [rsp+68h+OldValue], 0
0x18005d0c6  mov     dl, 1; NewValue
0x18005d0c8  lea     ecx, [r8+0Bh]; Privilege
0x18005d0cc  call    cs:__imp_RtlAdjustPrivilege
0x18005d0d2  mov     edi, eax
0x18005d0d4  test    eax, eax
0x18005d0d6  js      short loc_18005D11B
0x18005d0d8  test    r14d, r14d
0x18005d0db  jnz     short loc_18005D10B
0x18005d0dd  lea     r8d, [r14+8]; SystemInformationLength
0x18005d0e1  mov     [rsp+68h+SystemInformation], 3
0x18005d0ec  lea     rdx, [rsp+68h+SystemInformation]; SystemInformation
0x18005d0f4  mov     [rsp+68h+arg_14], 2710h
0x18005d0ff  lea     ecx, [r14+1Fh]; SystemInformationClass
0x18005d103  call    cs:__imp_NtSetSystemInformation
0x18005d109  jmp     short loc_18005D119
0x18005d10b  mov     edx, r14d; ClockSource
0x18005d10e  mov     ecx, 10000h; Interval
0x18005d113  call    cs:__imp_NtSetIntervalProfile
0x18005d119  mov     edi, eax
0x18005d11b  cmp     [rsp+68h+OldValue], 0
0x18005d120  jnz     short loc_18005D135
0x18005d122  xor     edx, edx; NewValue
0x18005d124  lea     r9, [rsp+68h+OldValue]; OldValue
0x18005d129  xor     r8d, r8d; ForThread
0x18005d12c  lea     ecx, [rdx+0Bh]; Privilege
0x18005d12f  call    cs:__imp_RtlAdjustPrivilege
0x18005d135  test    edi, edi
0x18005d137  jns     short loc_18005D19D
0x18005d139  mov     rax, [rbp+140h]
0x18005d140  bts     edi, 1Ch
0x18005d144  mov     [rsp+68h+var_38], 0; unsigned __int16 *
0x18005d14d  xor     r9d, r9d; struct _GUID *
0x18005d150  mov     [rsp+68h+var_40], rax; unsigned __int16 *
0x18005d155  mov     edx, edi; int
0x18005d157  mov     rax, [rbp+20h]
0x18005d15b  mov     rcx, r15; this
0x18005d15e  mov     [rsp+68h+Format], rax; unsigned __int16 *
0x18005d163  call    ?AddProviderControlWarningInfo@CControlManager@WindowsPerformanceRecorder@@QEAAXJAEBU_GUID@@PEBU3@PEBG22PEAUIControlErrorInfo@@@Z; WindowsPerformanceRecorder::CControlManager::AddProviderControlWarningInfo(long,_GUID const &,_GUID const *,ushort const *,ushort const *,ushort const *,IControlErrorInfo *)
0x18005d168  mov     rax, [rbp+20h]
0x18005d16c  lea     rdx, aRestorehardwar; "RestoreHardwareCounter"
0x18005d173  mov     [rsp+68h+var_40], rax; char *
0x18005d178  mov     r9d, edi; unsigned int
0x18005d17b  lea     rax, aWs_0; "%ws"
0x18005d182  mov     r8d, 1ADBh; char *
0x18005d188  mov     ecx, 3; this
0x18005d18d  mov     [rsp+68h+Format], rax; Format
0x18005d192  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18005d197  cmp     byte ptr [rbp+28h], 0
0x18005d19b  jnz     short loc_18005D1AF
0x18005d19d  add     rbx, 10h
0x18005d1a1  cmp     rbx, rsi
0x18005d1a4  jnz     loc_18005D0AB
0x18005d1aa  jmp     loc_18005D098
0x18005d1af  mov     eax, edi
0x18005d1b1  jmp     loc_18005D09A
```
