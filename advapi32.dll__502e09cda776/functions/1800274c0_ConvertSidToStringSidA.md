# ConvertSidToStringSidA

- ea: `0x1800274c0`
- end: `0x18002770d`
- name: `ConvertSidToStringSidA`
- size: `589`
- prototype: `BOOL __stdcall(PSID Sid, LPSTR *StringSid)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800274c0`

## import_xrefs

- `ntdll!RtlConvertSidToUnicodeString` at `0x1800274ff`
- `ntdll!RtlConvertSidToUnicodeString` at `0x1800274ff`
- `ntdll!RtlFreeUnicodeString` at `0x180027607`
- `ntdll!RtlFreeUnicodeString` at `0x1800276d7`
- `ntdll!RtlFreeUnicodeString` at `0x180027607`
- `ntdll!RtlFreeUnicodeString` at `0x1800276d7`
- `ntdll!RtlNtStatusToDosError` at `0x18002759a`
- `ntdll!RtlNtStatusToDosError` at `0x18002759a`
- `KERNELBASE!LocalAlloc` at `0x180027521`
- `KERNELBASE!LocalAlloc` at `0x180027673`
- `KERNELBASE!LocalAlloc` at `0x180027521`
- `KERNELBASE!LocalAlloc` at `0x180027673`
- `KERNEL32!LocalFree` at `0x1800275bf`
- `KERNEL32!LocalFree` at `0x1800276be`
- `KERNEL32!LocalFree` at `0x1800275bf`
- `KERNEL32!LocalFree` at `0x1800276be`
- `KERNEL32!WideCharToMultiByte` at `0x180027654`
- `KERNEL32!WideCharToMultiByte` at `0x1800276a4`
- `KERNEL32!WideCharToMultiByte` at `0x180027654`
- `KERNEL32!WideCharToMultiByte` at `0x1800276a4`
- `KERNEL32!SetLastError` at `0x1800275a8`
- `KERNEL32!SetLastError` at `0x1800275d1`
- `KERNEL32!SetLastError` at `0x1800275f2`
- `KERNEL32!SetLastError` at `0x180027615`
- `KERNEL32!SetLastError` at `0x1800276f2`
- `KERNEL32!SetLastError` at `0x1800275a8`
- `KERNEL32!SetLastError` at `0x1800275d1`
- `KERNEL32!SetLastError` at `0x1800275f2`
- `KERNEL32!SetLastError` at `0x180027615`
- `KERNEL32!SetLastError` at `0x1800276f2`

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
0x1800274c0  push    rbx
0x1800274c2  push    rbp
0x1800274c3  push    rsi
0x1800274c4  push    rdi
0x1800274c5  push    r14
0x1800274c7  push    r15
0x1800274c9  sub     rsp, 58h
0x1800274cd  xor     r15d, r15d
0x1800274d0  mov     rsi, rdx
0x1800274d3  test    rdx, rdx
0x1800274d6  jz      loc_1800275ED
0x1800274dc  xorps   xmm0, xmm0
0x1800274df  mov     ebx, r15d
0x1800274e2  movups  xmmword ptr [rsp+88h+UnicodeString.Length], xmm0
0x1800274e7  test    rcx, rcx
0x1800274ea  jz      loc_180027703
0x1800274f0  mov     rdx, rcx; Sid
0x1800274f3  lea     edi, [r15+1]
0x1800274f7  mov     r8b, dil; AllocateDestinationString
0x1800274fa  lea     rcx, [rsp+88h+UnicodeString]; UnicodeString
0x1800274ff  call    cs:__imp_RtlConvertSidToUnicodeString
0x180027506  nop     dword ptr [rax+rax+00h]
0x18002750b  mov     edx, eax
0x18002750d  test    eax, eax
0x18002750f  js      loc_180027598
0x180027515  movzx   edx, [rsp+88h+UnicodeString.Length]
0x18002751a  lea     ecx, [rdi+3Fh]; uFlags
0x18002751d  add     rdx, 2; uBytes
0x180027521  call    cs:__imp_LocalAlloc
0x180027528  nop     dword ptr [rax+rax+00h]
0x18002752d  mov     rbx, rax
0x180027530  test    rax, rax
0x180027533  jz      loc_1800276D2
0x180027539  movzx   eax, [rsp+88h+UnicodeString.Length]
0x18002753e  lea     r8, [rax+2]
0x180027542  shr     r8, 1
0x180027545  jz      loc_180027703
0x18002754b  mov     rcx, [rsp+88h+UnicodeString.Buffer]
0x180027550  mov     r9, rbx
0x180027553  shr     rax, 1
0x180027556  test    rax, rax
0x180027559  jz      short loc_180027577
0x18002755b  movzx   edx, word ptr [rcx]
0x18002755e  test    dx, dx
0x180027561  jz      short loc_180027577
0x180027563  mov     [r9], dx
0x180027567  add     rcx, 2
0x18002756b  add     r9, 2
0x18002756f  sub     rax, rdi
0x180027572  sub     r8, rdi
0x180027575  jnz     short loc_180027556
0x180027577  mov     rax, r8
0x18002757a  lea     rcx, [r9-2]
0x18002757e  neg     rax
0x180027581  sbb     edx, edx
0x180027583  not     edx
0x180027585  and     edx, 80000005h
0x18002758b  test    r8, r8
0x18002758e  cmovnz  rcx, r9
0x180027592  mov     [rcx], r15w
0x180027596  jnz     short loc_180027602
0x180027598  mov     ecx, edx; Status
0x18002759a  call    cs:__imp_RtlNtStatusToDosError
0x1800275a1  nop     dword ptr [rax+rax+00h]
0x1800275a6  mov     ecx, eax; dwErrCode
0x1800275a8  call    cs:__imp_SetLastError
0x1800275af  nop     dword ptr [rax+rax+00h]
0x1800275b4  mov     edi, r15d
0x1800275b7  test    rbx, rbx
0x1800275ba  jz      short loc_1800275CB
0x1800275bc  mov     rcx, rbx; hMem
0x1800275bf  call    cs:__imp_LocalFree
0x1800275c6  nop     dword ptr [rax+rax+00h]
0x1800275cb  test    edi, edi
0x1800275cd  jz      short loc_1800275DD
0x1800275cf  xor     ecx, ecx; dwErrCode
0x1800275d1  call    cs:__imp_SetLastError
0x1800275d8  nop     dword ptr [rax+rax+00h]
0x1800275dd  mov     eax, edi
0x1800275df  add     rsp, 58h
0x1800275e3  pop     r15
0x1800275e5  pop     r14
0x1800275e7  pop     rdi
0x1800275e8  pop     rsi
0x1800275e9  pop     rbp
0x1800275ea  pop     rbx
0x1800275eb  retn
0x1800275ed  mov     ecx, 57h ; 'W'; dwErrCode
0x1800275f2  call    cs:__imp_SetLastError
0x1800275f9  nop     dword ptr [rax+rax+00h]
0x1800275fe  xor     eax, eax
0x180027600  jmp     short loc_1800275DF
0x180027602  lea     rcx, [rsp+88h+UnicodeString]; UnicodeString
0x180027607  call    cs:__imp_RtlFreeUnicodeString
0x18002760e  nop     dword ptr [rax+rax+00h]
0x180027613  xor     ecx, ecx; dwErrCode
0x180027615  call    cs:__imp_SetLastError
0x18002761c  nop     dword ptr [rax+rax+00h]
0x180027621  or      rax, 0FFFFFFFFFFFFFFFFh
0x180027625  inc     rax
0x180027628  cmp     [rbx+rax*2], r15w
0x18002762d  jnz     short loc_180027625
0x18002762f  lea     r14d, [rax+1]
0x180027633  mov     [rsp+88h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x180027638  mov     rax, [rsi]
0x18002763b  mov     r9d, r14d; cchWideChar
0x18002763e  mov     [rsp+88h+lpDefaultChar], r15; lpDefaultChar
0x180027643  mov     r8, rbx; lpWideCharStr
0x180027646  mov     [rsp+88h+cbMultiByte], r15d; cbMultiByte
0x18002764b  xor     edx, edx; dwFlags
0x18002764d  xor     ecx, ecx; CodePage
0x18002764f  mov     [rsp+88h+lpMultiByteStr], rax; lpMultiByteStr
0x180027654  call    cs:__imp_WideCharToMultiByte
0x18002765b  nop     dword ptr [rax+rax+00h]
0x180027660  mov     ebp, eax
0x180027662  test    eax, eax
0x180027664  jnz     short loc_18002766E
0x180027666  mov     edi, r15d
0x180027669  jmp     loc_1800275BC
0x18002766e  mov     rdx, rbp; uBytes
0x180027671  xor     ecx, ecx; uFlags
0x180027673  call    cs:__imp_LocalAlloc
0x18002767a  nop     dword ptr [rax+rax+00h]
0x18002767f  mov     [rsi], rax
0x180027682  test    rax, rax
0x180027685  jz      short loc_1800276ED
0x180027687  mov     [rsp+88h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x18002768c  mov     r9d, r14d; cchWideChar
0x18002768f  mov     [rsp+88h+lpDefaultChar], r15; lpDefaultChar
0x180027694  mov     r8, rbx; lpWideCharStr
0x180027697  mov     [rsp+88h+cbMultiByte], ebp; cbMultiByte
0x18002769b  xor     edx, edx; dwFlags
0x18002769d  xor     ecx, ecx; CodePage
0x18002769f  mov     [rsp+88h+lpMultiByteStr], rax; lpMultiByteStr
0x1800276a4  call    cs:__imp_WideCharToMultiByte
0x1800276ab  nop     dword ptr [rax+rax+00h]
0x1800276b0  test    eax, eax
0x1800276b2  jnz     loc_1800275BC
0x1800276b8  mov     rcx, [rsi]; hMem
0x1800276bb  mov     edi, r15d
0x1800276be  call    cs:__imp_LocalFree
0x1800276c5  nop     dword ptr [rax+rax+00h]
0x1800276ca  mov     [rsi], r15
0x1800276cd  jmp     loc_1800275BC
0x1800276d2  lea     rcx, [rsp+88h+UnicodeString]; UnicodeString
0x1800276d7  call    cs:__imp_RtlFreeUnicodeString
0x1800276de  nop     dword ptr [rax+rax+00h]
0x1800276e3  mov     edx, 0C0000017h
0x1800276e8  jmp     loc_180027598
0x1800276ed  mov     ecx, 8; dwErrCode
0x1800276f2  call    cs:__imp_SetLastError
0x1800276f9  nop     dword ptr [rax+rax+00h]
0x1800276fe  jmp     loc_180027666
0x180027703  mov     edx, 0C000000Dh
0x180027708  jmp     loc_180027598
```
