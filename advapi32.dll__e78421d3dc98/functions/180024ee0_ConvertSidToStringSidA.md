# ConvertSidToStringSidA

- ea: `0x180024ee0`
- end: `0x1800250cb`
- name: `ConvertSidToStringSidA`
- size: `491`
- prototype: `BOOL __stdcall(PSID Sid, LPSTR *StringSid)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180024ee0`

## import_xrefs

- `ntdll!RtlConvertSidToUnicodeString` at `0x180024f1f`
- `ntdll!RtlConvertSidToUnicodeString` at `0x180024f1f`
- `ntdll!RtlFreeUnicodeString` at `0x180024ff8`
- `ntdll!RtlFreeUnicodeString` at `0x1800250a4`
- `ntdll!RtlFreeUnicodeString` at `0x180024ff8`
- `ntdll!RtlFreeUnicodeString` at `0x1800250a4`
- `ntdll!RtlNtStatusToDosError` at `0x180024faa`
- `ntdll!RtlNtStatusToDosError` at `0x180024faa`
- `KERNELBASE!LocalAlloc` at `0x180024f37`
- `KERNELBASE!LocalAlloc` at `0x180025052`
- `KERNELBASE!LocalAlloc` at `0x180024f37`
- `KERNELBASE!LocalAlloc` at `0x180025052`
- `KERNEL32!LocalFree` at `0x180024fc3`
- `KERNEL32!LocalFree` at `0x180025091`
- `KERNEL32!LocalFree` at `0x180024fc3`
- `KERNEL32!LocalFree` at `0x180025091`
- `KERNEL32!WideCharToMultiByte` at `0x180025039`
- `KERNEL32!WideCharToMultiByte` at `0x18002507d`
- `KERNEL32!WideCharToMultiByte` at `0x180025039`
- `KERNEL32!WideCharToMultiByte` at `0x18002507d`
- `KERNEL32!SetLastError` at `0x180024fb2`
- `KERNEL32!SetLastError` at `0x180024fcf`
- `KERNEL32!SetLastError` at `0x180024fe9`
- `KERNEL32!SetLastError` at `0x180025000`
- `KERNEL32!SetLastError` at `0x1800250b9`
- `KERNEL32!SetLastError` at `0x180024fb2`
- `KERNEL32!SetLastError` at `0x180024fcf`
- `KERNEL32!SetLastError` at `0x180024fe9`
- `KERNEL32!SetLastError` at `0x180025000`
- `KERNEL32!SetLastError` at `0x1800250b9`

## pseudocode

```c
BOOL __stdcall ConvertSidToStringSidA(PSID Sid, LPSTR *StringSid)
{
  WCHAR *v3; // rbx
  BOOL v4; // edi
  signed int v5; // edx
  unsigned __int64 v6; // r8
  PWSTR Buffer; // rcx
  WCHAR *v8; // r9
  unsigned __int64 v9; // rax
  WCHAR *v10; // rcx
  ULONG v11; // eax
  __int64 v13; // rax
  int v14; // r14d
  unsigned int v15; // eax
  int cbMultiByte; // ebp
  CHAR *lpMultiByteStr; // rax
  struct _UNICODE_STRING UnicodeString; // [rsp+40h] [rbp-48h] BYREF

  if ( !StringSid )
  {
    SetLastError(0x57u);
    return 0;
  }
  v3 = 0;
  UnicodeString = 0;
  if ( !Sid )
    goto LABEL_28;
  v4 = 1;
  v5 = RtlConvertSidToUnicodeString(&UnicodeString, Sid, 1u);
  if ( v5 < 0 )
    goto LABEL_13;
  v3 = (WCHAR *)LocalAlloc(0x40u, UnicodeString.Length + 2LL);
  if ( !v3 )
  {
    RtlFreeUnicodeString(&UnicodeString);
    v5 = -1073741801;
    goto LABEL_13;
  }
  v6 = ((unsigned __int64)UnicodeString.Length + 2) >> 1;
  if ( v6 )
  {
    Buffer = UnicodeString.Buffer;
    v8 = v3;
    v9 = (unsigned __int64)UnicodeString.Length >> 1;
    do
    {
      if ( !v9 )
        break;
      if ( !*Buffer )
        break;
      *v8++ = *Buffer++;
      --v9;
      --v6;
    }
    while ( v6 );
    v10 = v8 - 1;
    v5 = v6 == 0 ? 0x80000005 : 0;
    if ( v6 )
      v10 = v8;
    *v10 = 0;
    if ( v6 )
    {
      RtlFreeUnicodeString(&UnicodeString);
      SetLastError(0);
      v13 = -1;
      do
        ++v13;
      while ( v3[v13] );
      v14 = v13 + 1;
      v15 = WideCharToMultiByte(0, 0, v3, v13 + 1, *StringSid, 0, 0, 0);
      cbMultiByte = v15;
      if ( v15 )
      {
        lpMultiByteStr = (CHAR *)LocalAlloc(0, v15);
        *StringSid = lpMultiByteStr;
        if ( lpMultiByteStr )
        {
          if ( !WideCharToMultiByte(0, 0, v3, v14, lpMultiByteStr, cbMultiByte, 0, 0) )
          {
            v4 = 0;
            LocalFree(*StringSid);
            *StringSid = 0;
          }
          goto LABEL_14;
        }
        SetLastError(8u);
      }
      v4 = 0;
LABEL_14:
      LocalFree(v3);
      goto LABEL_15;
    }
  }
  else
  {
LABEL_28:
    v5 = -1073741811;
  }
LABEL_13:
  v11 = RtlNtStatusToDosError(v5);
  SetLastError(v11);
  v4 = 0;
  if ( v3 )
    goto LABEL_14;
LABEL_15:
  if ( v4 )
    SetLastError(0);
  return v4;
}

```

## disassembly

```asm
0x180024ee0  push    rbx
0x180024ee2  push    rbp
0x180024ee3  push    rsi
0x180024ee4  push    rdi
0x180024ee5  push    r14
0x180024ee7  push    r15
0x180024ee9  sub     rsp, 58h
0x180024eed  xor     r15d, r15d
0x180024ef0  mov     rsi, rdx
0x180024ef3  test    rdx, rdx
0x180024ef6  jz      loc_180024FE4
0x180024efc  xorps   xmm0, xmm0
0x180024eff  mov     ebx, r15d
0x180024f02  movups  xmmword ptr [rsp+88h+UnicodeString.Length], xmm0
0x180024f07  test    rcx, rcx
0x180024f0a  jz      loc_1800250C1
0x180024f10  mov     rdx, rcx; Sid
0x180024f13  lea     edi, [r15+1]
0x180024f17  mov     r8b, dil; AllocateDestinationString
0x180024f1a  lea     rcx, [rsp+88h+UnicodeString]; UnicodeString
0x180024f1f  call    cs:__imp_RtlConvertSidToUnicodeString
0x180024f25  mov     edx, eax
0x180024f27  test    eax, eax
0x180024f29  js      short loc_180024FA8
0x180024f2b  movzx   edx, [rsp+88h+UnicodeString.Length]
0x180024f30  lea     ecx, [rdi+3Fh]; uFlags
0x180024f33  add     rdx, 2; uBytes
0x180024f37  call    cs:__imp_LocalAlloc
0x180024f3d  mov     rbx, rax
0x180024f40  test    rax, rax
0x180024f43  jz      loc_18002509F
0x180024f49  movzx   eax, [rsp+88h+UnicodeString.Length]
0x180024f4e  lea     r8, [rax+2]
0x180024f52  shr     r8, 1
0x180024f55  jz      loc_1800250C1
0x180024f5b  mov     rcx, [rsp+88h+UnicodeString.Buffer]
0x180024f60  mov     r9, rbx
0x180024f63  shr     rax, 1
0x180024f66  test    rax, rax
0x180024f69  jz      short loc_180024F87
0x180024f6b  movzx   edx, word ptr [rcx]
0x180024f6e  test    dx, dx
0x180024f71  jz      short loc_180024F87
0x180024f73  mov     [r9], dx
0x180024f77  add     rcx, 2
0x180024f7b  add     r9, 2
0x180024f7f  sub     rax, rdi
0x180024f82  sub     r8, rdi
0x180024f85  jnz     short loc_180024F66
0x180024f87  mov     rax, r8
0x180024f8a  lea     rcx, [r9-2]
0x180024f8e  neg     rax
0x180024f91  sbb     edx, edx
0x180024f93  not     edx
0x180024f95  and     edx, 80000005h
0x180024f9b  test    r8, r8
0x180024f9e  cmovnz  rcx, r9
0x180024fa2  mov     [rcx], r15w
0x180024fa6  jnz     short loc_180024FF3
0x180024fa8  mov     ecx, edx; Status
0x180024faa  call    cs:__imp_RtlNtStatusToDosError
0x180024fb0  mov     ecx, eax; dwErrCode
0x180024fb2  call    cs:__imp_SetLastError
0x180024fb8  mov     edi, r15d
0x180024fbb  test    rbx, rbx
0x180024fbe  jz      short loc_180024FC9
0x180024fc0  mov     rcx, rbx; hMem
0x180024fc3  call    cs:__imp_LocalFree
0x180024fc9  test    edi, edi
0x180024fcb  jz      short loc_180024FD5
0x180024fcd  xor     ecx, ecx; dwErrCode
0x180024fcf  call    cs:__imp_SetLastError
0x180024fd5  mov     eax, edi
0x180024fd7  add     rsp, 58h
0x180024fdb  pop     r15
0x180024fdd  pop     r14
0x180024fdf  pop     rdi
0x180024fe0  pop     rsi
0x180024fe1  pop     rbp
0x180024fe2  pop     rbx
0x180024fe3  retn
0x180024fe4  mov     ecx, 57h ; 'W'; dwErrCode
0x180024fe9  call    cs:__imp_SetLastError
0x180024fef  xor     eax, eax
0x180024ff1  jmp     short loc_180024FD7
0x180024ff3  lea     rcx, [rsp+88h+UnicodeString]; UnicodeString
0x180024ff8  call    cs:__imp_RtlFreeUnicodeString
0x180024ffe  xor     ecx, ecx; dwErrCode
0x180025000  call    cs:__imp_SetLastError
0x180025006  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002500a  inc     rax
0x18002500d  cmp     [rbx+rax*2], r15w
0x180025012  jnz     short loc_18002500A
0x180025014  lea     r14d, [rax+1]
0x180025018  mov     [rsp+88h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x18002501d  mov     rax, [rsi]
0x180025020  mov     r9d, r14d; cchWideChar
0x180025023  mov     [rsp+88h+lpDefaultChar], r15; lpDefaultChar
0x180025028  mov     r8, rbx; lpWideCharStr
0x18002502b  mov     [rsp+88h+cbMultiByte], r15d; cbMultiByte
0x180025030  xor     edx, edx; dwFlags
0x180025032  xor     ecx, ecx; CodePage
0x180025034  mov     [rsp+88h+lpMultiByteStr], rax; lpMultiByteStr
0x180025039  call    cs:__imp_WideCharToMultiByte
0x18002503f  mov     ebp, eax
0x180025041  test    eax, eax
0x180025043  jnz     short loc_18002504D
0x180025045  mov     edi, r15d
0x180025048  jmp     loc_180024FC0
0x18002504d  mov     rdx, rbp; uBytes
0x180025050  xor     ecx, ecx; uFlags
0x180025052  call    cs:__imp_LocalAlloc
0x180025058  mov     [rsi], rax
0x18002505b  test    rax, rax
0x18002505e  jz      short loc_1800250B4
0x180025060  mov     [rsp+88h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x180025065  mov     r9d, r14d; cchWideChar
0x180025068  mov     [rsp+88h+lpDefaultChar], r15; lpDefaultChar
0x18002506d  mov     r8, rbx; lpWideCharStr
0x180025070  mov     [rsp+88h+cbMultiByte], ebp; cbMultiByte
0x180025074  xor     edx, edx; dwFlags
0x180025076  xor     ecx, ecx; CodePage
0x180025078  mov     [rsp+88h+lpMultiByteStr], rax; lpMultiByteStr
0x18002507d  call    cs:__imp_WideCharToMultiByte
0x180025083  test    eax, eax
0x180025085  jnz     loc_180024FC0
0x18002508b  mov     rcx, [rsi]; hMem
0x18002508e  mov     edi, r15d
0x180025091  call    cs:__imp_LocalFree
0x180025097  mov     [rsi], r15
0x18002509a  jmp     loc_180024FC0
0x18002509f  lea     rcx, [rsp+88h+UnicodeString]; UnicodeString
0x1800250a4  call    cs:__imp_RtlFreeUnicodeString
0x1800250aa  mov     edx, 0C0000017h
0x1800250af  jmp     loc_180024FA8
0x1800250b4  mov     ecx, 8; dwErrCode
0x1800250b9  call    cs:__imp_SetLastError
0x1800250bf  jmp     short loc_180025045
0x1800250c1  mov     edx, 0C000000Dh
0x1800250c6  jmp     loc_180024FA8
```
