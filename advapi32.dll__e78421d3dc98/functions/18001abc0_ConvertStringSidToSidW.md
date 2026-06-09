# ConvertStringSidToSidW

- ea: `0x18001abc0`
- end: `0x18001ad9a`
- name: `ConvertStringSidToSidW`
- size: `474`
- prototype: `BOOL __stdcall(LPCWSTR StringSid, PSID *Sid)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001aaf0`
- `0x180047a10`
- `0x180047fd4`

## callees

- `0x18001abc0`
- `0x18001ada0`
- `0x18001d3d0`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18001acef`
- `ntdll!RtlLengthSid` at `0x18001acef`
- `ntdll!RtlCopySid` at `0x18001ad15`
- `ntdll!RtlCopySid` at `0x18001ad15`
- `ntdll!RtlNtStatusToDosError` at `0x18001ac69`
- `ntdll!RtlNtStatusToDosError` at `0x18001ad1d`
- `ntdll!RtlNtStatusToDosError` at `0x18001ac69`
- `ntdll!RtlNtStatusToDosError` at `0x18001ad1d`
- `KERNELBASE!LocalAlloc` at `0x18001acfe`
- `KERNELBASE!LocalAlloc` at `0x18001acfe`
- `KERNEL32!LocalFree` at `0x18001ad41`
- `KERNEL32!LocalFree` at `0x18001ad5f`
- `KERNEL32!LocalFree` at `0x18001ad8f`
- `KERNEL32!LocalFree` at `0x18001ad41`
- `KERNEL32!LocalFree` at `0x18001ad5f`
- `KERNEL32!LocalFree` at `0x18001ad8f`
- `KERNEL32!GetLastError` at `0x18001ac7a`
- `KERNEL32!GetLastError` at `0x18001ac7a`
- `KERNEL32!SetLastError` at `0x18001abfc`
- `KERNEL32!SetLastError` at `0x18001ac30`
- `KERNEL32!SetLastError` at `0x18001ac5f`
- `KERNEL32!SetLastError` at `0x18001ac71`
- `KERNEL32!SetLastError` at `0x18001ad38`
- `KERNEL32!SetLastError` at `0x18001abfc`
- `KERNEL32!SetLastError` at `0x18001ac30`
- `KERNEL32!SetLastError` at `0x18001ac5f`
- `KERNEL32!SetLastError` at `0x18001ac71`
- `KERNEL32!SetLastError` at `0x18001ad38`

## pseudocode

```c
BOOL __stdcall ConvertStringSidToSidW(LPCWSTR StringSid, PSID *Sid)
{
  NTSTATUS v4; // eax
  __int64 v5; // rcx
  BOOL v6; // ebx
  DWORD v7; // ecx
  ULONG v9; // eax
  DWORD LastError; // r14d
  __int64 *v11; // rax
  __int64 *v12; // rbp
  __int64 v13; // rcx
  ULONG v14; // esi
  HLOCAL v15; // rax
  NTSTATUS v16; // eax
  ULONG v17; // esi
  __int64 v18; // rcx
  __int64 v19; // [rsp+28h] [rbp-40h]
  HLOCAL hMem; // [rsp+70h] [rbp+8h] BYREF
  __int64 v21; // [rsp+80h] [rbp+18h] BYREF

  v21 = 0;
  hMem = 0;
  if ( !StringSid || !Sid )
  {
    v6 = 0;
    SetLastError(0x57u);
    return v6;
  }
  v4 = LocalpConvertStringSidToSid(StringSid, Sid, &v21);
  if ( v4 < 0 )
  {
    v9 = RtlNtStatusToDosError(v4);
    SetLastError(v9);
    v6 = 0;
    LastError = GetLastError();
    LOBYTE(v19) = 0;
    v11 = LookupSidInTable((wchar_t *)StringSid, 0, 0, 0, 0, v19, &hMem);
    v12 = v11;
    if ( v11 && v11[2] )
    {
      v13 = -1;
      do
        ++v13;
      while ( StringSid[v13] );
      if ( v13 == *((_DWORD *)v11 + 3) )
      {
        v14 = RtlLengthSid((PSID)v11[2]);
        v15 = LocalAlloc(0x40u, v14);
        *Sid = v15;
        if ( v15 )
        {
          v16 = RtlCopySid(v14, v15, (PSID)v12[2]);
          v17 = RtlNtStatusToDosError(v16);
          if ( v17 )
          {
            LocalFree(*Sid);
            *Sid = 0;
          }
          else
          {
            v6 = 1;
          }
          v7 = v17;
        }
        else
        {
          v7 = 8;
        }
      }
      else
      {
        v7 = 1337;
      }
      goto LABEL_8;
    }
    if ( !hMem )
      goto LABEL_15;
    v18 = -1;
    do
      ++v18;
    while ( StringSid[v18] );
    if ( v18 != 2 )
    {
LABEL_15:
      v7 = LastError;
      goto LABEL_8;
    }
    *Sid = hMem;
    hMem = 0;
LABEL_7:
    v6 = 1;
    v7 = 0;
LABEL_8:
    SetLastError(v7);
    goto LABEL_9;
  }
  SetLastError(0);
  v5 = -1;
  do
    ++v5;
  while ( StringSid[v5] );
  if ( (unsigned int)((v21 - (__int64)StringSid) >> 1) == v5 )
    goto LABEL_7;
  SetLastError(0x539u);
  LocalFree(*Sid);
  *Sid = 0;
  v6 = 0;
LABEL_9:
  if ( hMem )
    LocalFree(hMem);
  return v6;
}

```

## disassembly

```asm
0x18001abc0  mov     rax, rsp
0x18001abc3  mov     [rax+10h], rbx
0x18001abc7  push    rbp
0x18001abc8  push    rsi
0x18001abc9  push    rdi
0x18001abca  push    r14
0x18001abcc  push    r15
0x18001abce  sub     rsp, 40h
0x18001abd2  xor     r15d, r15d
0x18001abd5  mov     rdi, rdx
0x18001abd8  mov     [rax+18h], r15
0x18001abdc  mov     rsi, rcx
0x18001abdf  mov     [rax+8], r15
0x18001abe3  test    rcx, rcx
0x18001abe6  jz      short loc_18001AC57
0x18001abe8  test    rdx, rdx
0x18001abeb  jz      short loc_18001AC57
0x18001abed  lea     r8, [rax+18h]
0x18001abf1  call    LocalpConvertStringSidToSid
0x18001abf6  test    eax, eax
0x18001abf8  js      short loc_18001AC67
0x18001abfa  xor     ecx, ecx; dwErrCode
0x18001abfc  call    cs:__imp_SetLastError
0x18001ac02  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001ac06  inc     rcx
0x18001ac09  cmp     [rsi+rcx*2], r15w
0x18001ac0e  jnz     short loc_18001AC06
0x18001ac10  mov     rax, [rsp+68h+arg_10]
0x18001ac18  sub     rax, rsi
0x18001ac1b  sar     rax, 1
0x18001ac1e  mov     eax, eax
0x18001ac20  cmp     rax, rcx
0x18001ac23  jnz     loc_18001AD33
0x18001ac29  mov     ebx, 1
0x18001ac2e  xor     ecx, ecx; dwErrCode
0x18001ac30  call    cs:__imp_SetLastError
0x18001ac36  mov     rcx, [rsp+68h+hMem]; hMem
0x18001ac3b  test    rcx, rcx
0x18001ac3e  jnz     loc_18001AD8F
0x18001ac44  mov     eax, ebx
0x18001ac46  mov     rbx, [rsp+68h+arg_8]
0x18001ac4b  add     rsp, 40h
0x18001ac4f  pop     r15
0x18001ac51  pop     r14
0x18001ac53  pop     rdi
0x18001ac54  pop     rsi
0x18001ac55  pop     rbp
0x18001ac56  retn
0x18001ac57  mov     ecx, 57h ; 'W'; dwErrCode
0x18001ac5c  mov     ebx, r15d
0x18001ac5f  call    cs:__imp_SetLastError
0x18001ac65  jmp     short loc_18001AC44
0x18001ac67  mov     ecx, eax; Status
0x18001ac69  call    cs:__imp_RtlNtStatusToDosError
0x18001ac6f  mov     ecx, eax; dwErrCode
0x18001ac71  call    cs:__imp_SetLastError
0x18001ac77  mov     ebx, r15d
0x18001ac7a  call    cs:__imp_GetLastError
0x18001ac80  xor     r9d, r9d
0x18001ac83  xor     r8d, r8d
0x18001ac86  mov     r14d, eax
0x18001ac89  xor     edx, edx; Sid2
0x18001ac8b  lea     rax, [rsp+68h+hMem]
0x18001ac90  mov     rcx, rsi; String1
0x18001ac93  mov     [rsp+68h+var_38], rax; __int64
0x18001ac98  mov     byte ptr [rsp+68h+var_40], r15b; __int64
0x18001ac9d  mov     [rsp+68h+var_48], r15; __int64
0x18001aca2  call    LookupSidInTable
0x18001aca7  mov     rbp, rax
0x18001acaa  test    rax, rax
0x18001acad  jnz     short loc_18001ACC5
0x18001acaf  mov     rax, [rsp+68h+hMem]
0x18001acb4  test    rax, rax
0x18001acb7  jnz     loc_18001AD6A
0x18001acbd  mov     ecx, r14d
0x18001acc0  jmp     loc_18001AC30
0x18001acc5  cmp     [rax+10h], r15
0x18001acc9  jz      short loc_18001ACAF
0x18001accb  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001accf  inc     rcx
0x18001acd2  cmp     [rsi+rcx*2], r15w
0x18001acd7  jnz     short loc_18001ACCF
0x18001acd9  mov     eax, [rax+0Ch]
0x18001acdc  cmp     rcx, rax
0x18001acdf  jz      short loc_18001ACEB
0x18001ace1  mov     ecx, 539h
0x18001ace6  jmp     loc_18001AC30
0x18001aceb  mov     rcx, [rbp+10h]; Sid
0x18001acef  call    cs:__imp_RtlLengthSid
0x18001acf5  mov     edx, eax; uBytes
0x18001acf7  mov     ecx, 40h ; '@'; uFlags
0x18001acfc  mov     esi, eax
0x18001acfe  call    cs:__imp_LocalAlloc
0x18001ad04  mov     [rdi], rax
0x18001ad07  test    rax, rax
0x18001ad0a  jz      short loc_18001AD52
0x18001ad0c  mov     r8, [rbp+10h]; SourceSid
0x18001ad10  mov     rdx, rax; DestinationSid
0x18001ad13  mov     ecx, esi; DestinationSidLength
0x18001ad15  call    cs:__imp_RtlCopySid
0x18001ad1b  mov     ecx, eax; Status
0x18001ad1d  call    cs:__imp_RtlNtStatusToDosError
0x18001ad23  mov     esi, eax
0x18001ad25  test    eax, eax
0x18001ad27  jnz     short loc_18001AD5C
0x18001ad29  lea     ebx, [rax+1]
0x18001ad2c  mov     ecx, esi
0x18001ad2e  jmp     loc_18001AC30
0x18001ad33  mov     ecx, 539h; dwErrCode
0x18001ad38  call    cs:__imp_SetLastError
0x18001ad3e  mov     rcx, [rdi]; hMem
0x18001ad41  call    cs:__imp_LocalFree
0x18001ad47  mov     [rdi], r15
0x18001ad4a  mov     ebx, r15d
0x18001ad4d  jmp     loc_18001AC36
0x18001ad52  mov     ecx, 8
0x18001ad57  jmp     loc_18001AC30
0x18001ad5c  mov     rcx, [rdi]; hMem
0x18001ad5f  call    cs:__imp_LocalFree
0x18001ad65  mov     [rdi], r15
0x18001ad68  jmp     short loc_18001AD2C
0x18001ad6a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001ad6e  inc     rcx
0x18001ad71  cmp     [rsi+rcx*2], r15w
0x18001ad76  jnz     short loc_18001AD6E
0x18001ad78  cmp     rcx, 2
0x18001ad7c  jnz     loc_18001ACBD
0x18001ad82  mov     [rdi], rax
0x18001ad85  mov     [rsp+68h+hMem], r15
0x18001ad8a  jmp     loc_18001AC29
0x18001ad8f  call    cs:__imp_LocalFree
0x18001ad95  jmp     loc_18001AC44
```
