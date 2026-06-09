# Throttler::AddNewTimestampValue(HKEY__ *)

- ea: `0x180005d44`
- end: `0x180005edb`
- name: `?AddNewTimestampValue@Throttler@@AEAAJPEAUHKEY__@@@Z`
- size: `407`
- prototype: `int(Throttler *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180006530`

## callees

- `0x180002590`
- `0x180005d44`
- `0x180007013`
- `0x180007040`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x180005e51`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180005e51`
- `ADVAPI32!RegSetValueExW` at `0x180005e9c`
- `ADVAPI32!RegSetValueExW` at `0x180005e9c`
- `RPCRT4!RpcStringFreeW` at `0x180005df9`
- `RPCRT4!RpcStringFreeW` at `0x180005df9`
- `RPCRT4!UuidCreate` at `0x180005d80`
- `RPCRT4!UuidCreate` at `0x180005d80`
- `RPCRT4!UuidToStringW` at `0x180005da7`
- `RPCRT4!UuidToStringW` at `0x180005da7`

## pseudocode

```c
__int64 __fastcall Throttler::AddNewTimestampValue(Throttler *this, HKEY a2)
{
  RPC_STATUS v3; // eax
  unsigned int v4; // ebx
  bool v5; // cc
  RPC_WSTR v6; // rdx
  __int64 v7; // rbx
  WCHAR *v8; // rax
  __int64 v9; // rcx
  WCHAR *v10; // rcx
  LSTATUS v12; // eax
  int v13; // edi
  RPC_WSTR StringUuid; // [rsp+30h] [rbp-59h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp-51h] BYREF
  BYTE Data[8]; // [rsp+40h] [rbp-49h] BYREF
  UUID Uuid; // [rsp+48h] [rbp-41h] BYREF
  WCHAR ValueName[40]; // [rsp+60h] [rbp-29h] BYREF

  memset_0(ValueName, 0, sizeof(ValueName));
  Uuid = 0;
  v3 = UuidCreate(&Uuid);
  v4 = v3;
  v5 = v3 <= 0;
  if ( v3 || (StringUuid = 0, v3 = UuidToStringW(&Uuid, &StringUuid), v4 = v3, v5 = v3 <= 0, v3) )
  {
    if ( !v5 )
      v4 = (unsigned __int16)v3 | 0x80070000;
  }
  else
  {
    v6 = StringUuid;
    v7 = 40;
    v8 = ValueName;
    v9 = 2147483646;
    do
    {
      if ( !v9 )
        break;
      if ( !*v6 )
        break;
      *v8++ = *v6++;
      --v9;
      --v7;
    }
    while ( v7 );
    v10 = v8 - 1;
    if ( v7 )
      v10 = v8;
    *v10 = 0;
    RpcStringFreeW(&StringUuid);
    v4 = v7 == 0 ? 0x8007007A : 0;
  }
  if ( (v4 & 0x80000000) != 0 )
  {
    DebugPrint(0, "THROTTLE ERROR: %s:%d - hr = 0x%08X\n", "Throttler::AddNewTimestampValue", 271, v4);
    return v4;
  }
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  *(_QWORD *)Data = (unsigned int)((SystemTimeAsFileTime.dwLowDateTime
                                  + ((unsigned __int64)SystemTimeAsFileTime.dwHighDateTime << 32))
                                 / 0x23C34600);
  v12 = RegSetValueExW(a2, ValueName, 0, 0xBu, Data, 8u);
  v13 = v12;
  if ( !v12 )
    return v4;
  DebugPrint(0, "THROTTLE ERROR: %s:%d - res = %d\n", "Throttler::AddNewTimestampValue", 288, v12);
  if ( v13 > 0 )
    return (unsigned __int16)v13 | 0x80070000;
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180005d44  push    rbp
0x180005d46  push    rbx
0x180005d47  push    rsi
0x180005d48  push    rdi
0x180005d49  lea     rbp, [rsp-3Fh]
0x180005d4e  sub     rsp, 0C8h
0x180005d55  mov     rax, cs:__security_cookie
0x180005d5c  xor     rax, rsp
0x180005d5f  mov     [rbp+57h+var_30], rax
0x180005d63  mov     rdi, rdx
0x180005d66  lea     rcx, [rbp+57h+ValueName]; void *
0x180005d6a  xor     edx, edx; Val
0x180005d6c  lea     r8d, [rdx+50h]; Size
0x180005d70  call    memset_0
0x180005d75  xorps   xmm0, xmm0
0x180005d78  lea     rcx, [rbp+57h+Uuid]; Uuid
0x180005d7c  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x180005d80  call    cs:__imp_UuidCreate
0x180005d86  xor     esi, esi
0x180005d88  mov     ebx, eax
0x180005d8a  test    eax, eax
0x180005d8c  jz      short loc_180005D9B
0x180005d8e  jle     short loc_180005E0C
0x180005d90  movzx   ebx, ax
0x180005d93  or      ebx, 80070000h
0x180005d99  jmp     short loc_180005E0C
0x180005d9b  lea     rdx, [rbp+57h+StringUuid]; StringUuid
0x180005d9f  mov     [rbp+57h+StringUuid], rsi
0x180005da3  lea     rcx, [rbp+57h+Uuid]; Uuid
0x180005da7  call    cs:__imp_UuidToStringW
0x180005dad  mov     ebx, eax
0x180005daf  test    eax, eax
0x180005db1  jnz     short loc_180005D8E
0x180005db3  mov     rdx, [rbp+57h+StringUuid]
0x180005db7  lea     ebx, [rax+28h]
0x180005dba  lea     rax, [rbp+57h+ValueName]
0x180005dbe  mov     ecx, 7FFFFFFEh
0x180005dc3  test    rcx, rcx
0x180005dc6  jz      short loc_180005DE7
0x180005dc8  movzx   r8d, word ptr [rdx]
0x180005dcc  test    r8w, r8w
0x180005dd0  jz      short loc_180005DE7
0x180005dd2  mov     [rax], r8w
0x180005dd6  add     rdx, 2
0x180005dda  add     rax, 2
0x180005dde  dec     rcx
0x180005de1  sub     rbx, 1
0x180005de5  jnz     short loc_180005DC3
0x180005de7  lea     rcx, [rax-2]
0x180005deb  test    rbx, rbx
0x180005dee  cmovnz  rcx, rax
0x180005df2  mov     [rcx], si
0x180005df5  lea     rcx, [rbp+57h+StringUuid]; String
0x180005df9  call    cs:__imp_RpcStringFreeW
0x180005dff  neg     rbx
0x180005e02  sbb     ebx, ebx
0x180005e04  not     ebx
0x180005e06  and     ebx, 8007007Ah
0x180005e0c  test    ebx, ebx
0x180005e0e  jns     short loc_180005E49
0x180005e10  mov     r9d, 10Fh
0x180005e16  mov     dword ptr [rsp+0E0h+lpData], ebx
0x180005e1a  lea     r8, aThrottlerAddne; "Throttler::AddNewTimestampValue"
0x180005e21  xor     ecx, ecx; Level
0x180005e23  lea     rdx, aThrottleErrorS_0; "THROTTLE ERROR: %s:%d - hr = 0x%08X\n"
0x180005e2a  call    ?DebugPrint@@YAXKPEBDZZ; DebugPrint(ulong,char const *,...)
0x180005e2f  mov     eax, ebx
0x180005e31  mov     rcx, [rbp+57h+var_30]
0x180005e35  xor     rcx, rsp; StackCookie
0x180005e38  call    __security_check_cookie
0x180005e3d  add     rsp, 0C8h
0x180005e44  pop     rdi
0x180005e45  pop     rsi
0x180005e46  pop     rbx
0x180005e47  pop     rbp
0x180005e48  retn
0x180005e49  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180005e4d  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], rsi
0x180005e51  call    cs:__imp_GetSystemTimeAsFileTime
0x180005e57  mov     eax, [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x180005e5a  mov     r9d, 0Bh; dwType
0x180005e60  mov     edx, [rbp+57h+SystemTimeAsFileTime.dwHighDateTime]
0x180005e63  xor     r8d, r8d; Reserved
0x180005e66  shl     rdx, 20h
0x180005e6a  mov     rcx, rdi; hKey
0x180005e6d  add     rdx, rax
0x180005e70  mov     [rsp+0E0h+cbData], 8; cbData
0x180005e78  mov     rax, 0E5109EC205D7BEA7h
0x180005e82  mul     rdx
0x180005e85  shr     rdx, 1Dh
0x180005e89  mov     eax, edx
0x180005e8b  lea     rdx, [rbp+57h+ValueName]; lpValueName
0x180005e8f  mov     qword ptr [rbp+57h+Data], rax
0x180005e93  lea     rax, [rbp+57h+Data]
0x180005e97  mov     [rsp+0E0h+lpData], rax; lpData
0x180005e9c  call    cs:__imp_RegSetValueExW
0x180005ea2  mov     edi, eax
0x180005ea4  test    eax, eax
0x180005ea6  jz      short loc_180005E2F
0x180005ea8  mov     r9d, 120h
0x180005eae  mov     dword ptr [rsp+0E0h+lpData], eax
0x180005eb2  lea     r8, aThrottlerAddne; "Throttler::AddNewTimestampValue"
0x180005eb9  xor     ecx, ecx; Level
0x180005ebb  lea     rdx, aThrottleErrorS_1; "THROTTLE ERROR: %s:%d - res = %d\n"
0x180005ec2  call    ?DebugPrint@@YAXKPEBDZZ; DebugPrint(ulong,char const *,...)
0x180005ec7  test    edi, edi
0x180005ec9  jle     short loc_180005ED4
0x180005ecb  movzx   edi, di
0x180005ece  or      edi, 80070000h
0x180005ed4  mov     eax, edi
0x180005ed6  jmp     loc_180005E31
```
