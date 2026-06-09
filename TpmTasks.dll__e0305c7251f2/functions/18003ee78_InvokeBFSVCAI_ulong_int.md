# InvokeBFSVCAI(ulong,int *)

- ea: `0x18003ee78`
- end: `0x18003f163`
- name: `?InvokeBFSVCAI@@YAJKPEAH@Z`
- size: `747`
- prototype: `__int64 __fastcall(__int64, int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update`

## callers

- `0x180034634`

## callees

- `0x18000282c`
- `0x180002be4`
- `0x1800078b0`
- `0x18001bd50`
- `0x18001bddc`
- `0x18003ee78`
- `0x180047618`
- `0x180048078`
- `0x180048c3c`
- `0x180049234`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18003efbe`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18003efbe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003f11f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003f11f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003f111`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003f111`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eee2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ef9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f01b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f129`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eee2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ef9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f01b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f129`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18003eed8`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18003eed8`

## pseudocode

```c
__int64 __fastcall InvokeBFSVCAI(__int64 a1, int *a2)
{
  void *v2; // rdi
  int v4; // esi
  UINT WindowsDirectoryW; // eax
  signed int LastError; // eax
  signed int IsBitLockerResealNeeded; // ebx
  int v8; // r14d
  int v9; // r13d
  DWORD v10; // eax
  DWORD v11; // r15d
  wchar_t *v12; // rax
  __int64 v13; // rcx
  wchar_t *v14; // rdi
  int v15; // eax
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  HANDLE ProcessHeap; // rax
  signed int v20; // eax
  int v22; // [rsp+50h] [rbp-B0h] BYREF
  DWORD v23; // [rsp+54h] [rbp-ACh] BYREF
  int v24; // [rsp+58h] [rbp-A8h] BYREF
  DWORD v25; // [rsp+5Ch] [rbp-A4h] BYREF
  int v26; // [rsp+60h] [rbp-A0h] BYREF
  void *v27; // [rsp+68h] [rbp-98h] BYREF
  wchar_t Str[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Buffer[264]; // [rsp+280h] [rbp+180h] BYREF

  v2 = 0;
  *a2 = 0;
  v23 = 0;
  v24 = 0;
  v27 = 0;
  v4 = 1;
  WindowsDirectoryW = GetWindowsDirectoryW(Buffer, 0x104u);
  if ( !WindowsDirectoryW )
  {
    LastError = GetLastError();
    IsBitLockerResealNeeded = LastError;
    if ( LastError > 0 )
      IsBitLockerResealNeeded = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_31;
  }
  if ( WindowsDirectoryW > 0x104 )
  {
    IsBitLockerResealNeeded = -2147024774;
    goto LABEL_31;
  }
  IsBitLockerResealNeeded = StringCchCopyW(Str, 0x104u, Buffer);
  if ( IsBitLockerResealNeeded >= 0 )
  {
    IsBitLockerResealNeeded = StringCchCatW(Str, 0x104u, L"\\boot");
    if ( IsBitLockerResealNeeded >= 0 )
    {
      IsBitLockerResealNeeded = BfsIsBitLockerResealNeeded(&v23, &v24, &v27);
      if ( IsBitLockerResealNeeded < 0 )
      {
        v2 = v27;
        goto LABEL_31;
      }
      v8 = 0;
      v26 = 0;
      v22 = 0;
      v25 = 0;
      v9 = 0;
      v4 = BfsServiceBootFilesEx2(Str, 1372, 0, a2);
      if ( v4 )
      {
        v11 = 0;
        goto LABEL_20;
      }
      v10 = GetLastError();
      v11 = v10;
      if ( v10 - 1392 <= 1 || v10 == 6 )
      {
        v12 = wcsrchr(Str, 0x5Cu);
        v14 = v12;
        if ( v12 )
        {
          LOWORD(v8) = *v12;
          v13 = 0;
          *v12 = 0;
        }
        v9 = 1;
        v15 = BfsRepairSystemPartition(v13, Str);
        v4 = v15;
        if ( v14 )
          *v14 = v8;
        if ( v15 )
        {
          v26 = 1;
          v4 = BfsServiceBootFilesEx2(Str, 1372, 0, a2);
          if ( v4 )
          {
            v8 = 1;
            goto LABEL_20;
          }
          v25 = GetLastError();
        }
        v8 = v22;
      }
LABEL_20:
      v2 = v27;
      if ( !v23 && (!*a2 || !v24)
        || (IsBitLockerResealNeeded = BfsResealBitLockerWithRetry(v27), IsBitLockerResealNeeded >= 0) )
      {
        if ( v9
          && (unsigned int)dword_1800A30F8 > 5
          && (unsigned __int8)tlgKeywordOn(&dword_1800A30F8, 0x800000000000LL) )
        {
          v24 = 0;
          v23 = v11;
          v22 = v8;
          LODWORD(v27) = v4;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v16,
            (unsigned int)&unk_180095520,
            v17,
            v18,
            (__int64)&v27,
            (__int64)&v26,
            (__int64)&v22,
            (__int64)&v23,
            (__int64)&v25,
            (__int64)&v24);
        }
      }
    }
  }
LABEL_31:
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, v2);
  if ( !v4 )
  {
    v20 = GetLastError();
    IsBitLockerResealNeeded = v20;
    if ( v20 > 0 )
      return (unsigned __int16)v20 | 0x80070000;
  }
  return (unsigned int)IsBitLockerResealNeeded;
}

```

## disassembly

```asm
0x18003ee78  push    rbp
0x18003ee7a  push    rbx
0x18003ee7b  push    rsi
0x18003ee7c  push    rdi
0x18003ee7d  push    r12
0x18003ee7f  push    r13
0x18003ee81  push    r14
0x18003ee83  push    r15
0x18003ee85  lea     rbp, [rsp-3A8h]
0x18003ee8d  sub     rsp, 4A8h
0x18003ee94  mov     rax, cs:__security_cookie
0x18003ee9b  xor     rax, rsp
0x18003ee9e  mov     [rbp+3E0h+var_50], rax
0x18003eea5  xor     edi, edi
0x18003eea7  mov     dword ptr [rdx], 0
0x18003eead  mov     r12, rdx
0x18003eeb0  mov     [rsp+4E0h+var_48C], 0
0x18003eeb8  mov     r14d, 104h
0x18003eebe  mov     [rsp+4E0h+var_488], 0
0x18003eec6  mov     edx, r14d; uSize
0x18003eec9  mov     [rsp+4E0h+var_478], rdi
0x18003eece  lea     rcx, [rbp+3E0h+Buffer]; lpBuffer
0x18003eed5  lea     esi, [rdi+1]
0x18003eed8  call    cs:__imp_GetWindowsDirectoryW
0x18003eede  test    eax, eax
0x18003eee0  jnz     short loc_18003EF00
0x18003eee2  call    cs:__imp_GetLastError
0x18003eee8  mov     ebx, eax
0x18003eeea  test    eax, eax
0x18003eeec  jle     loc_18003F111
0x18003eef2  movzx   ebx, ax
0x18003eef5  or      ebx, 80070000h
0x18003eefb  jmp     loc_18003F111
0x18003ef00  cmp     eax, r14d
0x18003ef03  jbe     short loc_18003EF0F
0x18003ef05  mov     ebx, 8007007Ah
0x18003ef0a  jmp     loc_18003F111
0x18003ef0f  lea     r8, [rbp+3E0h+Buffer]; unsigned __int16 *
0x18003ef16  mov     rdx, r14; unsigned __int64
0x18003ef19  lea     rcx, [rsp+4E0h+Str]; unsigned __int16 *
0x18003ef1e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003ef23  mov     ebx, eax
0x18003ef25  test    eax, eax
0x18003ef27  js      loc_18003F111
0x18003ef2d  lea     r8, aBoot; "\\boot"
0x18003ef34  mov     rdx, r14; unsigned __int64
0x18003ef37  lea     rcx, [rsp+4E0h+Str]; unsigned __int16 *
0x18003ef3c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003ef41  mov     ebx, eax
0x18003ef43  test    eax, eax
0x18003ef45  js      loc_18003F111
0x18003ef4b  lea     r8, [rsp+4E0h+var_478]
0x18003ef50  lea     rdx, [rsp+4E0h+var_488]
0x18003ef55  lea     rcx, [rsp+4E0h+var_48C]
0x18003ef5a  call    BfsIsBitLockerResealNeeded
0x18003ef5f  mov     ebx, eax
0x18003ef61  test    eax, eax
0x18003ef63  js      loc_18003F10C
0x18003ef69  xor     r14d, r14d
0x18003ef6c  mov     [rsp+4E0h+var_480], edi
0x18003ef70  mov     r9, r12
0x18003ef73  mov     [rsp+4E0h+var_490], r14d
0x18003ef78  xor     r8d, r8d
0x18003ef7b  mov     [rsp+4E0h+var_484], edi
0x18003ef7f  mov     edx, 55Ch
0x18003ef84  lea     rcx, [rsp+4E0h+Str]
0x18003ef89  xor     r13d, r13d
0x18003ef8c  call    BfsServiceBootFilesEx2
0x18003ef91  mov     esi, eax
0x18003ef93  test    eax, eax
0x18003ef95  jnz     loc_18003F104
0x18003ef9b  call    cs:__imp_GetLastError
0x18003efa1  mov     r15d, eax
0x18003efa4  lea     ecx, [rax-570h]
0x18003efaa  cmp     ecx, 1
0x18003efad  jbe     short loc_18003EFB4
0x18003efaf  cmp     eax, 6
0x18003efb2  jnz     short loc_18003F02A
0x18003efb4  mov     edx, 5Ch ; '\'; Ch
0x18003efb9  lea     rcx, [rsp+4E0h+Str]; Str
0x18003efbe  call    cs:__imp_wcsrchr
0x18003efc4  mov     rdi, rax
0x18003efc7  test    rax, rax
0x18003efca  jz      short loc_18003EFD5
0x18003efcc  movzx   r14d, word ptr [rax]
0x18003efd0  xor     ecx, ecx
0x18003efd2  mov     [rax], cx
0x18003efd5  lea     rdx, [rsp+4E0h+Str]
0x18003efda  mov     r13d, 1
0x18003efe0  call    BfsRepairSystemPartition
0x18003efe5  mov     esi, eax
0x18003efe7  test    rdi, rdi
0x18003efea  jz      short loc_18003EFF0
0x18003efec  mov     [rdi], r14w
0x18003eff0  test    eax, eax
0x18003eff2  jz      short loc_18003F025
0x18003eff4  mov     r9, r12
0x18003eff7  mov     [rsp+4E0h+var_480], r13d
0x18003effc  xor     r8d, r8d
0x18003efff  lea     rcx, [rsp+4E0h+Str]
0x18003f004  mov     edx, 55Ch
0x18003f009  mov     edi, r13d
0x18003f00c  call    BfsServiceBootFilesEx2
0x18003f011  mov     esi, eax
0x18003f013  test    eax, eax
0x18003f015  jnz     loc_18003F0FC
0x18003f01b  call    cs:__imp_GetLastError
0x18003f021  mov     [rsp+4E0h+var_484], eax
0x18003f025  mov     r14d, [rsp+4E0h+var_490]
0x18003f02a  cmp     [rsp+4E0h+var_48C], 0
0x18003f02f  mov     rdi, [rsp+4E0h+var_478]
0x18003f034  jnz     short loc_18003F044
0x18003f036  cmp     dword ptr [r12], 0
0x18003f03b  jz      short loc_18003F056
0x18003f03d  cmp     [rsp+4E0h+var_488], 0
0x18003f042  jz      short loc_18003F056
0x18003f044  mov     rcx, rdi
0x18003f047  call    BfsResealBitLockerWithRetry
0x18003f04c  mov     ebx, eax
0x18003f04e  test    eax, eax
0x18003f050  js      loc_18003F111
0x18003f056  test    r13d, r13d
0x18003f059  jz      loc_18003F111
0x18003f05f  mov     eax, cs:dword_1800A30F8
0x18003f065  cmp     eax, 5
0x18003f068  jbe     loc_18003F111
0x18003f06e  mov     rdx, 800000000000h
0x18003f078  lea     rcx, dword_1800A30F8
0x18003f07f  call    _tlgKeywordOn
0x18003f084  test    al, al
0x18003f086  jz      loc_18003F111
0x18003f08c  mov     eax, [rsp+4E0h+var_484]
0x18003f090  lea     rdx, unk_180095520
0x18003f097  mov     [rsp+4E0h+var_484], eax
0x18003f09b  mov     eax, [rsp+4E0h+var_480]
0x18003f09f  mov     [rsp+4E0h+var_480], eax
0x18003f0a3  lea     rax, [rsp+4E0h+var_488]
0x18003f0a8  mov     [rsp+4E0h+var_498], rax
0x18003f0ad  lea     rax, [rsp+4E0h+var_484]
0x18003f0b2  mov     [rsp+4E0h+var_4A0], rax
0x18003f0b7  lea     rax, [rsp+4E0h+var_48C]
0x18003f0bc  mov     [rsp+4E0h+var_4A8], rax
0x18003f0c1  lea     rax, [rsp+4E0h+var_490]
0x18003f0c6  mov     [rsp+4E0h+var_4B0], rax
0x18003f0cb  lea     rax, [rsp+4E0h+var_480]
0x18003f0d0  mov     [rsp+4E0h+var_4B8], rax
0x18003f0d5  lea     rax, [rsp+4E0h+var_478]
0x18003f0da  mov     [rsp+4E0h+var_4C0], rax
0x18003f0df  mov     [rsp+4E0h+var_488], 0
0x18003f0e7  mov     [rsp+4E0h+var_48C], r15d
0x18003f0ec  mov     [rsp+4E0h+var_490], r14d
0x18003f0f1  mov     dword ptr [rsp+4E0h+var_478], esi
0x18003f0f5  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003f0fa  jmp     short loc_18003F111
0x18003f0fc  mov     r14d, edi
0x18003f0ff  jmp     loc_18003F02A
0x18003f104  xor     r15d, r15d
0x18003f107  jmp     loc_18003F02A
0x18003f10c  mov     rdi, [rsp+4E0h+var_478]
0x18003f111  call    cs:__imp_GetProcessHeap
0x18003f117  mov     r8, rdi; lpMem
0x18003f11a  xor     edx, edx; dwFlags
0x18003f11c  mov     rcx, rax; hHeap
0x18003f11f  call    cs:__imp_HeapFree
0x18003f125  test    esi, esi
0x18003f127  jnz     short loc_18003F13E
0x18003f129  call    cs:__imp_GetLastError
0x18003f12f  mov     ebx, eax
0x18003f131  test    eax, eax
0x18003f133  jle     short loc_18003F13E
0x18003f135  movzx   ebx, ax
0x18003f138  or      ebx, 80070000h
0x18003f13e  mov     eax, ebx
0x18003f140  mov     rcx, [rbp+3E0h+var_50]
0x18003f147  xor     rcx, rsp; StackCookie
0x18003f14a  call    __security_check_cookie
0x18003f14f  add     rsp, 4A8h
0x18003f156  pop     r15
0x18003f158  pop     r14
0x18003f15a  pop     r13
0x18003f15c  pop     r12
0x18003f15e  pop     rdi
0x18003f15f  pop     rsi
0x18003f160  pop     rbx
0x18003f161  pop     rbp
0x18003f162  retn
```
