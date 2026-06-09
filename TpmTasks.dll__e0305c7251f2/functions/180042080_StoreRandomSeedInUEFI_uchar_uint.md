# StoreRandomSeedInUEFI(uchar *,uint)

- ea: `0x180042080`
- end: `0x1800421e1`
- name: `?StoreRandomSeedInUEFI@@YAJPEAEI@Z`
- size: `353`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800414c4`

## callees

- `0x1800078b0`
- `0x18004128c`
- `0x180041c64`
- `0x180042080`

## import_xrefs

- `ntdll!RtlAcquirePrivilege` at `0x1800420ea`
- `ntdll!RtlAcquirePrivilege` at `0x1800420ea`
- `ntdll!RtlReleasePrivilege` at `0x18004219f`
- `ntdll!RtlReleasePrivilege` at `0x18004219f`
- `ntdll!RtlComputeCrc32` at `0x180042153`
- `ntdll!RtlComputeCrc32` at `0x180042153`
- `ntdll!RtlNtStatusToDosError` at `0x1800421a9`
- `ntdll!RtlNtStatusToDosError` at `0x1800421a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042186`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042186`
- `api-ms-win-core-firmware-l1-1-0!SetFirmwareEnvironmentVariableExW` at `0x180042117`
- `api-ms-win-core-firmware-l1-1-0!SetFirmwareEnvironmentVariableExW` at `0x18004217c`
- `api-ms-win-core-firmware-l1-1-0!SetFirmwareEnvironmentVariableExW` at `0x180042117`
- `api-ms-win-core-firmware-l1-1-0!SetFirmwareEnvironmentVariableExW` at `0x18004217c`

## pseudocode

```c
__int64 __fastcall StoreRandomSeedInUEFI(unsigned __int8 *a1)
{
  signed int v2; // ebx
  int v3; // eax
  unsigned __int8 *v4; // rdx
  unsigned int v5; // ecx
  signed int LastError; // eax
  signed int v7; // eax
  ULONG Privilege; // [rsp+30h] [rbp-40h] BYREF
  unsigned int v10; // [rsp+34h] [rbp-3Ch] BYREF
  ULONG v11; // [rsp+38h] [rbp-38h] BYREF
  PVOID ReturnedState; // [rsp+40h] [rbp-30h] BYREF
  UCHAR Buffer[16]; // [rsp+48h] [rbp-28h] BYREF
  __int128 v14; // [rsp+58h] [rbp-18h]

  Privilege = 22;
  ReturnedState = 0;
  v10 = 32;
  *(_OWORD *)Buffer = 0;
  v14 = 0;
  if ( a1 )
  {
    if ( (unsigned __int8)IsUEFIFW() )
    {
      v3 = RtlAcquirePrivilege(&Privilege, 1u, 0, &ReturnedState);
      if ( v3 < 0 )
      {
        v7 = RtlNtStatusToDosError(v3);
        v2 = v7;
        if ( v7 > 0 )
          return (unsigned __int16)v7 | 0x80070000;
      }
      else
      {
        if ( !(unsigned int)SetFirmwareEnvironmentVariableExW(
                              L"OfflineUniqueIDRandomSeed",
                              L"{eaec226f-c9a3-477a-a826-ddc716cdc0e3}",
                              a1,
                              32,
                              7)
          || (v2 = GenerateOfflineDeviceID(v5, v4, 0x20u, a1, Buffer, &v10), v2 >= 0)
          && (v11 = RtlComputeCrc32(0, Buffer, 0x20u),
              !(unsigned int)SetFirmwareEnvironmentVariableExW(
                               L"OfflineUniqueIDRandomSeedCRC",
                               L"{eaec226f-c9a3-477a-a826-ddc716cdc0e3}",
                               &v11,
                               4,
                               7)) )
        {
          LastError = GetLastError();
          v2 = LastError;
          if ( LastError > 0 )
            v2 = (unsigned __int16)LastError | 0x80070000;
        }
        RtlReleasePrivilege(ReturnedState);
      }
    }
    else
    {
      return (unsigned int)-2147023091;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180042080  mov     [rsp-8+arg_8], rbx
0x180042085  push    rbp
0x180042086  mov     rbp, rsp
0x180042089  sub     rsp, 70h
0x18004208d  mov     rax, cs:__security_cookie
0x180042094  xor     rax, rsp
0x180042097  mov     [rbp+var_8], rax
0x18004209b  mov     [rbp+Privilege], 16h
0x1800420a2  xorps   xmm0, xmm0
0x1800420a5  mov     [rbp+ReturnedState], 0
0x1800420ad  mov     rbx, rcx
0x1800420b0  mov     [rbp+var_3C], 20h ; ' '
0x1800420b7  movups  xmmword ptr [rbp+Buffer], xmm0
0x1800420bb  movups  [rbp+var_18], xmm0
0x1800420bf  test    rcx, rcx
0x1800420c2  jz      loc_1800421C0
0x1800420c8  call    IsUEFIFW
0x1800420cd  test    al, al
0x1800420cf  jnz     short loc_1800420DB
0x1800420d1  mov     ebx, 8007070Dh
0x1800420d6  jmp     loc_1800421C5
0x1800420db  xor     r8d, r8d; Flags
0x1800420de  lea     r9, [rbp+ReturnedState]; ReturnedState
0x1800420e2  lea     rcx, [rbp+Privilege]; Privilege
0x1800420e6  lea     edx, [r8+1]; NumPriv
0x1800420ea  call    cs:__imp_RtlAcquirePrivilege
0x1800420f0  test    eax, eax
0x1800420f2  js      loc_1800421A7
0x1800420f8  mov     r9d, 20h ; ' '
0x1800420fe  mov     dword ptr [rsp+70h+var_50], 7
0x180042106  mov     r8, rbx
0x180042109  lea     rdx, Guid; "{eaec226f-c9a3-477a-a826-ddc716cdc0e3}"
0x180042110  lea     rcx, aOfflineuniquei; "OfflineUniqueIDRandomSeed"
0x180042117  call    cs:__imp_SetFirmwareEnvironmentVariableExW
0x18004211d  test    eax, eax
0x18004211f  jz      short loc_180042186
0x180042121  lea     rax, [rbp+var_3C]
0x180042125  mov     r9, rbx; unsigned __int8 *
0x180042128  mov     [rsp+70h+var_48], rax; unsigned int *
0x18004212d  mov     r8d, 20h ; ' '; unsigned int
0x180042133  lea     rax, [rbp+Buffer]
0x180042137  mov     [rsp+70h+var_50], rax; unsigned __int8 *
0x18004213c  call    ?GenerateOfflineDeviceID@@YAJIPEAEI00PEAI@Z; GenerateOfflineDeviceID(uint,uchar *,uint,uchar *,uchar *,uint *)
0x180042141  mov     ebx, eax
0x180042143  test    eax, eax
0x180042145  js      short loc_18004219B
0x180042147  mov     r8d, 20h ; ' '; Length
0x18004214d  lea     rdx, [rbp+Buffer]; Buffer
0x180042151  xor     ecx, ecx; InitialCrc
0x180042153  call    cs:__imp_RtlComputeCrc32
0x180042159  mov     r9d, 4
0x18004215f  mov     dword ptr [rsp+70h+var_50], 7
0x180042167  lea     r8, [rbp+var_38]
0x18004216b  mov     [rbp+var_38], eax
0x18004216e  lea     rdx, Guid; "{eaec226f-c9a3-477a-a826-ddc716cdc0e3}"
0x180042175  lea     rcx, aOfflineuniquei_0; "OfflineUniqueIDRandomSeedCRC"
0x18004217c  call    cs:__imp_SetFirmwareEnvironmentVariableExW
0x180042182  test    eax, eax
0x180042184  jnz     short loc_18004219B
0x180042186  call    cs:__imp_GetLastError
0x18004218c  mov     ebx, eax
0x18004218e  test    eax, eax
0x180042190  jle     short loc_18004219B
0x180042192  movzx   ebx, ax
0x180042195  or      ebx, 80070000h
0x18004219b  mov     rcx, [rbp+ReturnedState]; ReturnedState
0x18004219f  call    cs:__imp_RtlReleasePrivilege
0x1800421a5  jmp     short loc_1800421C5
0x1800421a7  mov     ecx, eax; Status
0x1800421a9  call    cs:__imp_RtlNtStatusToDosError
0x1800421af  mov     ebx, eax
0x1800421b1  test    eax, eax
0x1800421b3  jle     short loc_1800421C5
0x1800421b5  movzx   ebx, ax
0x1800421b8  or      ebx, 80070000h
0x1800421be  jmp     short loc_1800421C5
0x1800421c0  mov     ebx, 80070057h
0x1800421c5  mov     eax, ebx
0x1800421c7  mov     rcx, [rbp+var_8]
0x1800421cb  xor     rcx, rsp; StackCookie
0x1800421ce  call    __security_check_cookie
0x1800421d3  mov     rbx, [rsp+70h+arg_8]
0x1800421db  add     rsp, 70h
0x1800421df  pop     rbp
0x1800421e0  retn
```
