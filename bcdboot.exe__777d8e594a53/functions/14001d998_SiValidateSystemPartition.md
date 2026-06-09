# SiValidateSystemPartition

- ea: `0x14001d998`
- end: `0x14001db4b`
- name: `SiValidateSystemPartition`
- size: `435`
- prototype: `__int64 __fastcall(PCWSTR SourceString, _DWORD *, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x14001cb14`

## callees

- `0x14001d47c`
- `0x14001d514`
- `0x14001d998`
- `0x1400265d6`
- `0x1400265fa`
- `0x140026650`

## import_xrefs

- `ntdll!NtClose` at `0x14001da69`
- `ntdll!NtClose` at `0x14001da69`
- `ntdll!NtDeviceIoControlFile` at `0x14001da57`
- `ntdll!NtDeviceIoControlFile` at `0x14001da57`

## pseudocode

```c
__int64 __fastcall SiValidateSystemPartition(PCWSTR SourceString, _DWORD *a2, __int64 a3, __int64 a4, char a5)
{
  NTSTATUS v7; // ebx
  HANDLE FileHandle; // [rsp+50h] [rbp-B0h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD OutputBuffer[8]; // [rsp+70h] [rbp-90h] BYREF
  char Buf1; // [rsp+90h] [rbp-70h] BYREF
  char v13; // [rsp+91h] [rbp-6Fh]
  _QWORD v14[2]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v15; // [rsp+110h] [rbp+10h] BYREF
  __int128 v16; // [rsp+120h] [rbp+20h]
  __int64 v17; // [rsp+130h] [rbp+30h]

  v17 = 0;
  OutputBuffer[1] = 0;
  v15 = 0;
  v16 = 0;
  memset_0(OutputBuffer, 0, 0x8Cu);
  memset(v14, 0, 12);
  IoStatusBlock = 0;
  FileHandle = 0;
  v7 = SiOpenDevice(SourceString, &FileHandle);
  if ( v7 >= 0 )
  {
    IoStatusBlock = 0;
    v7 = NtDeviceIoControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x70048u, 0, 0, OutputBuffer, 0x90u);
  }
  if ( FileHandle )
    NtClose(FileHandle);
  if ( v7 >= 0 )
  {
    if ( !a2 || OutputBuffer[0] == *a2 )
    {
      if ( OutputBuffer[0] == 1 )
      {
        v7 = -1073741823;
        if ( memcmp_0(&Buf1, &PARTITION_SYSTEM_GUID, 0x10u) )
          return (unsigned int)v7;
        v7 = 0;
        goto LABEL_13;
      }
      if ( !OutputBuffer[0] )
      {
        v7 = v13 == 0 ? 0xC0000001 : 0;
        if ( !v13 )
          return (unsigned int)v7;
LABEL_13:
        if ( a5 )
        {
          v17 = 0;
          memset(v14, 0, 12);
          v15 = 0;
          v16 = 0;
          v7 = SiIssueSynchronousIoctl(SourceString, 2954240, v14, 12, &v15, 40);
          if ( v7 >= 0 )
          {
            if ( BYTE10(v15) )
              return (unsigned int)-1073741436;
          }
        }
        return (unsigned int)v7;
      }
    }
    return (unsigned int)-1073741823;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14001d998  push    rbp
0x14001d99a  push    rbx
0x14001d99b  push    rsi
0x14001d99c  push    rdi
0x14001d99d  lea     rbp, [rsp-48h]
0x14001d9a2  sub     rsp, 148h
0x14001d9a9  mov     rax, cs:__security_cookie
0x14001d9b0  xor     rax, rsp
0x14001d9b3  mov     [rbp+60h+var_28], rax
0x14001d9b7  xorps   xmm0, xmm0
0x14001d9ba  xor     eax, eax
0x14001d9bc  mov     rdi, rdx
0x14001d9bf  mov     [rbp+60h+var_30], rax
0x14001d9c3  mov     rsi, rcx
0x14001d9c6  mov     [rsp+160h+var_EC], eax
0x14001d9ca  xor     edx, edx; Val
0x14001d9cc  lea     rcx, [rsp+160h+var_F0]; void *
0x14001d9d1  mov     r8d, 8Ch; Size
0x14001d9d7  movups  [rbp+60h+var_50], xmm0
0x14001d9db  movups  [rbp+60h+var_40], xmm0
0x14001d9df  call    memset_0
0x14001d9e4  xor     eax, eax
0x14001d9e6  lea     rdx, [rsp+160h+FileHandle]; FileHandle
0x14001d9eb  xorps   xmm0, xmm0
0x14001d9ee  mov     [rbp+60h+var_60], rax
0x14001d9f2  mov     rcx, rsi; SourceString
0x14001d9f5  mov     [rbp+60h+var_58], eax
0x14001d9f8  movups  xmmword ptr [rsp+160h+var_108], xmm0
0x14001d9fd  mov     [rsp+160h+FileHandle], rax
0x14001da02  call    SiOpenDevice
0x14001da07  mov     ebx, eax
0x14001da09  test    eax, eax
0x14001da0b  js      short loc_14001DA5F
0x14001da0d  mov     rcx, [rsp+160h+FileHandle]; FileHandle
0x14001da12  lea     rax, [rsp+160h+var_F0]
0x14001da17  mov     [rsp+160h+OutputBufferLength], 90h; OutputBufferLength
0x14001da1f  xorps   xmm0, xmm0
0x14001da22  mov     [rsp+160h+OutputBuffer], rax; OutputBuffer
0x14001da27  xor     r9d, r9d; ApcContext
0x14001da2a  mov     [rsp+160h+InputBufferLength], 0; InputBufferLength
0x14001da32  lea     rax, [rsp+160h+var_108]
0x14001da37  mov     [rsp+160h+InputBuffer], 0; InputBuffer
0x14001da40  xor     r8d, r8d; ApcRoutine
0x14001da43  mov     [rsp+160h+IoControlCode], 70048h; IoControlCode
0x14001da4b  xor     edx, edx; Event
0x14001da4d  mov     [rsp+160h+IoStatusBlock], rax; IoStatusBlock
0x14001da52  movups  xmmword ptr [rsp+160h+var_108], xmm0
0x14001da57  call    cs:__imp_NtDeviceIoControlFile
0x14001da5d  mov     ebx, eax
0x14001da5f  mov     rcx, [rsp+160h+FileHandle]; Handle
0x14001da64  test    rcx, rcx
0x14001da67  jz      short loc_14001DA6F
0x14001da69  call    cs:__imp_NtClose
0x14001da6f  test    ebx, ebx
0x14001da71  js      loc_14001DB31
0x14001da77  mov     eax, [rsp+160h+var_F0]
0x14001da7b  test    rdi, rdi
0x14001da7e  jz      short loc_14001DA88
0x14001da80  cmp     eax, [rdi]
0x14001da82  jnz     loc_14001DB2C
0x14001da88  cmp     eax, 1
0x14001da8b  jnz     short loc_14001DAB2
0x14001da8d  lea     r8d, [rax+0Fh]; Size
0x14001da91  mov     ebx, 0C0000001h
0x14001da96  lea     rdx, PARTITION_SYSTEM_GUID; Buf2
0x14001da9d  lea     rcx, [rbp+60h+Buf1]; Buf1
0x14001daa1  call    memcmp_0
0x14001daa6  test    eax, eax
0x14001daa8  jnz     loc_14001DB31
0x14001daae  xor     ebx, ebx
0x14001dab0  jmp     short loc_14001DACC
0x14001dab2  test    eax, eax
0x14001dab4  jnz     short loc_14001DB2C
0x14001dab6  mov     dl, [rbp+60h+var_CF]
0x14001dab9  mov     ebx, 0C0000001h
0x14001dabe  mov     al, dl
0x14001dac0  neg     al
0x14001dac2  sbb     ecx, ecx
0x14001dac4  not     ecx
0x14001dac6  and     ebx, ecx
0x14001dac8  test    dl, dl
0x14001daca  jz      short loc_14001DB31
0x14001dacc  cmp     [rbp+60h+arg_20], 0
0x14001dad3  jz      short loc_14001DB31
0x14001dad5  xor     eax, eax
0x14001dad7  mov     [rsp+160h+IoControlCode], 28h ; '('
0x14001dadf  xorps   xmm0, xmm0
0x14001dae2  mov     [rbp+60h+var_30], rax
0x14001dae6  mov     dword ptr [rbp+60h+var_60], eax
0x14001dae9  lea     r8, [rbp+60h+var_60]
0x14001daed  lea     rax, [rbp+60h+var_50]
0x14001daf1  mov     [rbp+60h+var_60+4], 0
0x14001daf9  mov     r9d, 0Ch
0x14001daff  mov     [rsp+160h+IoStatusBlock], rax
0x14001db04  mov     edx, 2D1400h
0x14001db09  mov     rcx, rsi
0x14001db0c  movups  [rbp+60h+var_50], xmm0
0x14001db10  movups  [rbp+60h+var_40], xmm0
0x14001db14  call    SiIssueSynchronousIoctl
0x14001db19  mov     ebx, eax
0x14001db1b  test    eax, eax
0x14001db1d  js      short loc_14001DB31
0x14001db1f  cmp     byte ptr [rbp+60h+var_50+0Ah], 0
0x14001db23  jz      short loc_14001DB31
0x14001db25  mov     ebx, 0C0000184h
0x14001db2a  jmp     short loc_14001DB31
0x14001db2c  mov     ebx, 0C0000001h
0x14001db31  mov     eax, ebx
0x14001db33  mov     rcx, [rbp+60h+var_28]
0x14001db37  xor     rcx, rsp; StackCookie
0x14001db3a  call    __security_check_cookie
0x14001db3f  add     rsp, 148h
0x14001db46  pop     rdi
0x14001db47  pop     rsi
0x14001db48  pop     rbx
0x14001db49  pop     rbp
0x14001db4a  retn
```
