# WsRestoreGlobalMapping

- ea: `0x1800299a4`
- end: `0x180029d99`
- name: `WsRestoreGlobalMapping`
- size: `1013`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000d904`

## callees

- `0x1800024f0`
- `0x180004a40`
- `0x180008650`
- `0x180008a4c`
- `0x180009f80`
- `0x18000af60`
- `0x18000b6d0`
- `0x18000b7f4`
- `0x18000c888`
- `0x18001e420`
- `0x1800299a4`
- `0x18002ebd4`

## import_xrefs

- `ntdll!DbgPrint` at `0x180029a10`
- `ntdll!DbgPrint` at `0x180029aa1`
- `ntdll!DbgPrint` at `0x180029a10`
- `ntdll!DbgPrint` at `0x180029aa1`
- `ntdll!RtlAcquireResourceExclusive` at `0x180029bb1`
- `ntdll!RtlAcquireResourceExclusive` at `0x180029bb1`
- `ntdll!NtClose` at `0x180029d8c`
- `ntdll!NtClose` at `0x180029d8c`
- `ntdll!RtlReleaseResource` at `0x180029c34`
- `ntdll!RtlReleaseResource` at `0x180029c34`
- `ntdll!RtlInitUnicodeString` at `0x180029c5d`
- `ntdll!RtlInitUnicodeString` at `0x180029c73`
- `ntdll!RtlInitUnicodeString` at `0x180029c5d`
- `ntdll!RtlInitUnicodeString` at `0x180029c73`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x180029b12`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x180029b12`

## pseudocode

```c
__int64 __fastcall WsRestoreGlobalMapping(__int64 a1)
{
  int v1; // r15d
  unsigned int v3; // r14d
  _WORD *v4; // rax
  __int64 v5; // rdx
  int v6; // r13d
  __int64 v7; // rcx
  _WORD *v9; // rcx
  const WCHAR *v10; // rdi
  ULONG v11; // edx
  char *hMem; // rsi
  int v13; // r9d
  unsigned int v14; // r12d
  unsigned int v15; // ebx
  __int64 v16; // rcx
  DWORD v17; // eax
  struct _LUID SourceLuid; // [rsp+90h] [rbp-80h] BYREF
  struct _UNICODE_STRING v19; // [rsp+98h] [rbp-78h] BYREF
  HANDLE Handle; // [rsp+A8h] [rbp-68h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+B0h] [rbp-60h] BYREF
  __int64 v22; // [rsp+C0h] [rbp-50h] BYREF
  __int64 v23; // [rsp+C8h] [rbp-48h] BYREF
  __int64 v24; // [rsp+D0h] [rbp-40h] BYREF
  __int64 v25; // [rsp+D8h] [rbp-38h] BYREF
  struct _LUID v26; // [rsp+E0h] [rbp-30h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+E8h] [rbp-28h] BYREF
  int v28; // [rsp+100h] [rbp-10h] BYREF
  __int64 *v29; // [rsp+108h] [rbp-8h]
  __int64 v30; // [rsp+110h] [rbp+0h]
  int v31; // [rsp+118h] [rbp+8h]
  __int64 *v32; // [rsp+120h] [rbp+10h]
  __int64 v33; // [rsp+128h] [rbp+18h]
  int v34; // [rsp+130h] [rbp+20h]
  __int64 *v35; // [rsp+138h] [rbp+28h]
  __int64 v36; // [rsp+140h] [rbp+30h]
  int v37; // [rsp+148h] [rbp+38h]
  __int64 *v38; // [rsp+150h] [rbp+40h]
  __int64 v39; // [rsp+158h] [rbp+48h]
  _BYTE v40[176]; // [rsp+160h] [rbp+50h] BYREF
  WCHAR v41[264]; // [rsp+210h] [rbp+100h] BYREF
  WCHAR SourceString[344]; // [rsp+420h] [rbp+310h] BYREF

  v1 = *(_DWORD *)(a1 + 20);
  SourceLuid = 0;
  v26 = 0;
  *(_DWORD *)&v19.Length = 0;
  v3 = 0;
  *(_DWORD *)&DestinationString.Length = 0;
  Handle = 0;
  Destination = 0;
  v25 = 0;
  v24 = 0;
  v23 = 0;
  v22 = 0;
  DbgPrint("WsRestoreGlobalMapping\n");
  v4 = *(_WORD **)(a1 + 8);
  if ( !v4 || !*v4 )
    return 87;
  v5 = *(unsigned int *)(a1 + 32);
  v6 = *(_DWORD *)(a1 + 16);
  v29 = &v25;
  v36 = 16;
  v32 = &v24;
  v35 = &v23;
  v39 = 16;
  v7 = *(_QWORD *)(a1 + 24);
  v38 = &v22;
  v28 = 1130784068;
  v30 = 124;
  v31 = 1348563540;
  v33 = 24;
  v34 = 1349349187;
  v37 = 1315925058;
  if ( !(unsigned __int8)LmPopulateAndValidateUseOptionInfo(v7, v5, &v28) )
  {
    DbgPrint("Invalid value specified for a UseOption\n");
    return 87;
  }
  v9 = *(_WORD **)a1;
  v10 = 0;
  if ( *(_QWORD *)a1 && *v9 )
  {
    if ( (unsigned int)WsUseCheckLocal((__int64)v9, (__int64)v40, &DestinationString) )
      return 87;
    v3 = *(_DWORD *)&DestinationString.Length;
    v10 = (const WCHAR *)v40;
  }
  v11 = *(_DWORD *)(a1 + 48);
  hMem = 0;
  if ( v11 )
  {
    hMem = *(char **)(a1 + 40);
    if ( hMem )
    {
      if ( !RtlValidRelativeSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)(a1 + 40), v11, 0) )
        return 87;
    }
  }
  if ( (unsigned int)WsUseCheckRemote(*(_QWORD *)(a1 + 8), (__int64)v41, &v19) )
    return 87;
  v14 = *(_DWORD *)&v19.Length;
  SourceLuid = (struct _LUID)-1LL;
  LOBYTE(v13) = 1;
  v26 = (struct _LUID)-1LL;
  v15 = WsCreateTreeConnectName((int)v41, *(int *)&v19.Length, (int)v10, v13, &Destination);
  if ( !v15 )
  {
    if ( !v1 || (unsigned int)ComputeTargetNameFromUncName(v41, SourceString) )
    {
      if ( v10 )
      {
        *(_DWORD *)&v19.Length = 0;
        if ( !RtlAcquireResourceExclusive(&Resource, 1u) )
          return 2140;
        if ( !(unsigned int)WsGetUserEntry((__int64)&Use, &SourceLuid, (unsigned int *)&v19.Length, 0, 0) )
        {
          v16 = *(_QWORD *)(Use + 24LL * *(unsigned int *)&v19.Length);
          if ( v16 )
          {
            *(_QWORD *)&v19.Length = 0;
            *(_QWORD *)&DestinationString.Length = 0;
            WsFindLocal(v16, v10, &v19, &DestinationString);
            if ( *(_QWORD *)&v19.Length )
              v15 = 85;
          }
        }
        RtlReleaseResource(&Resource);
        if ( v15 )
          return v15;
      }
      DestinationString = 0;
      v19 = 0;
      RtlInitUnicodeString(&DestinationString, v10);
      if ( v1 )
        RtlInitUnicodeString(&v19, SourceString);
      v17 = WsOpenCreateConnectionSpecifyImpersonation(
              &Destination,
              (const void **)&DestinationString,
              0,
              0,
              (const void **)((unsigned __int64)&v19 & -(__int64)(v1 != 0)),
              hMem,
              v25,
              v24,
              v23,
              v22,
              v6 | 1,
              3u,
              0,
              1,
              0,
              1,
              &Handle);
      v15 = v17;
      if ( v17 )
      {
        if ( v17 == 2250 )
          return 55;
      }
      else
      {
        v15 = WsAddUse(
                &SourceLuid,
                &v26,
                Handle,
                (__int64)v10,
                v3,
                v41,
                v14,
                (__int64)&Destination,
                v6,
                (_OWORD *)v24,
                (_QWORD *)v23,
                (_QWORD *)v22);
        if ( v15 && (unsigned int)WsDeleteConnectionEx(&SourceLuid, Handle, 2u, 1) )
          NtClose(Handle);
      }
      return v15;
    }
    return 87;
  }
  return v15;
}

```

## disassembly

```asm
0x1800299a4  push    rbp
0x1800299a6  push    rbx
0x1800299a7  push    rsi
0x1800299a8  push    rdi
0x1800299a9  push    r12
0x1800299ab  push    r13
0x1800299ad  push    r14
0x1800299af  push    r15
0x1800299b1  lea     rbp, [rsp-5D8h]
0x1800299b9  sub     rsp, 6E8h
0x1800299c0  mov     rax, cs:__security_cookie
0x1800299c7  xor     rax, rsp
0x1800299ca  mov     [rbp+610h+var_50], rax
0x1800299d1  mov     r15d, [rcx+14h]
0x1800299d5  xor     r12d, r12d
0x1800299d8  mov     rbx, rcx
0x1800299db  mov     qword ptr [rbp+610h+SourceLuid.LowPart], r12
0x1800299df  xorps   xmm0, xmm0
0x1800299e2  mov     qword ptr [rbp+610h+var_640.LowPart], r12
0x1800299e6  lea     rcx, aWsrestoregloba; "WsRestoreGlobalMapping\n"
0x1800299ed  mov     dword ptr [rbp+610h+var_688.Length], r12d
0x1800299f1  mov     r14d, r12d
0x1800299f4  mov     dword ptr [rbp+610h+DestinationString.Length], r12d
0x1800299f8  mov     [rbp+610h+Handle], r12
0x1800299fc  movups  xmmword ptr [rbp+610h+var_638.Length], xmm0
0x180029a00  mov     [rbp+610h+var_648], r12
0x180029a04  mov     [rbp+610h+var_650], r12
0x180029a08  mov     [rbp+610h+var_658], r12
0x180029a0c  mov     [rbp+610h+var_660], r12
0x180029a10  call    cs:__imp_DbgPrint
0x180029a16  mov     rax, [rbx+8]
0x180029a1a  test    rax, rax
0x180029a1d  jz      loc_180029AA7
0x180029a23  cmp     [rax], r12w
0x180029a27  jz      short loc_180029AA7
0x180029a29  mov     edx, [rbx+20h]
0x180029a2c  lea     ecx, [r12+10h]
0x180029a31  mov     r13d, [rbx+10h]
0x180029a35  lea     rax, [rbp+610h+var_648]
0x180029a39  mov     [rbp+610h+var_618], rax
0x180029a3d  lea     r8, [rbp+610h+var_620]
0x180029a41  lea     rax, [rbp+610h+var_650]
0x180029a45  mov     [rbp+610h+var_5E0], rcx
0x180029a49  mov     [rbp+610h+var_600], rax
0x180029a4d  lea     rax, [rbp+610h+var_658]
0x180029a51  mov     [rbp+610h+var_5E8], rax
0x180029a55  lea     rax, [rbp+610h+var_660]
0x180029a59  mov     [rbp+610h+var_5C8], rcx
0x180029a5d  mov     rcx, [rbx+18h]
0x180029a61  mov     [rbp+610h+var_5D0], rax
0x180029a65  mov     [rbp+610h+var_620], 43666544h
0x180029a6c  mov     [rbp+610h+var_610], 7Ch ; '|'
0x180029a74  mov     [rbp+610h+var_608], 50617254h
0x180029a7b  mov     [rbp+610h+var_5F8], 18h
0x180029a83  mov     [rbp+610h+var_5F0], 506D6F43h
0x180029a8a  mov     [rbp+610h+var_5D8], 4E6F6C42h
0x180029a91  call    LmPopulateAndValidateUseOptionInfo
0x180029a96  test    al, al
0x180029a98  jnz     short loc_180029ACF
0x180029a9a  lea     rcx, aInvalidValueSp; "Invalid value specified for a UseOption"...
0x180029aa1  call    cs:__imp_DbgPrint
0x180029aa7  mov     eax, 57h ; 'W'
0x180029aac  mov     rcx, [rbp+610h+var_50]
0x180029ab3  xor     rcx, rsp; StackCookie
0x180029ab6  call    __security_check_cookie
0x180029abb  add     rsp, 6E8h
0x180029ac2  pop     r15
0x180029ac4  pop     r14
0x180029ac6  pop     r13
0x180029ac8  pop     r12
0x180029aca  pop     rdi
0x180029acb  pop     rsi
0x180029acc  pop     rbx
0x180029acd  pop     rbp
0x180029ace  retn
0x180029acf  mov     rcx, [rbx]
0x180029ad2  mov     rdi, r12
0x180029ad5  test    rcx, rcx
0x180029ad8  jz      short loc_180029AF9
0x180029ada  cmp     [rcx], r12w
0x180029ade  jz      short loc_180029AF9
0x180029ae0  lea     r8, [rbp+610h+DestinationString]
0x180029ae4  lea     rdx, [rbp+610h+var_5C0]
0x180029ae8  call    WsUseCheckLocal
0x180029aed  test    eax, eax
0x180029aef  jnz     short loc_180029AA7
0x180029af1  mov     r14d, dword ptr [rbp+610h+DestinationString.Length]
0x180029af5  lea     rdi, [rbp+610h+var_5C0]
0x180029af9  mov     edx, [rbx+30h]; SecurityDescriptorLength
0x180029afc  mov     rsi, r12
0x180029aff  test    edx, edx
0x180029b01  jz      short loc_180029B1C
0x180029b03  mov     rsi, [rbx+28h]
0x180029b07  test    rsi, rsi
0x180029b0a  jz      short loc_180029B1C
0x180029b0c  xor     r8d, r8d; RequiredInformation
0x180029b0f  mov     rcx, rsi; SecurityDescriptorInput
0x180029b12  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x180029b18  test    al, al
0x180029b1a  jz      short loc_180029AA7
0x180029b1c  mov     rcx, [rbx+8]
0x180029b20  lea     r8, [rbp+610h+var_688]
0x180029b24  lea     rdx, [rbp+610h+var_510]
0x180029b2b  call    WsUseCheckRemote
0x180029b30  test    eax, eax
0x180029b32  jnz     loc_180029AA7
0x180029b38  mov     r12d, dword ptr [rbp+610h+var_688.Length]
0x180029b3c  lea     rcx, [rbp+610h+var_510]; int
0x180029b43  mov     qword ptr [rbp+610h+SourceLuid.LowPart], 0FFFFFFFFFFFFFFFFh
0x180029b4b  mov     r9b, 1; int
0x180029b4e  mov     rax, qword ptr [rbp+610h+SourceLuid.LowPart]
0x180029b52  mov     r8, rdi; int
0x180029b55  mov     qword ptr [rbp+610h+var_640.LowPart], rax
0x180029b59  mov     edx, r12d; int
0x180029b5c  lea     rax, [rbp+610h+var_638]
0x180029b60  mov     [rsp+720h+Destination], rax; Destination
0x180029b65  call    WsCreateTreeConnectName
0x180029b6a  mov     ebx, eax
0x180029b6c  test    eax, eax
0x180029b6e  jnz     loc_180029D92
0x180029b74  test    r15d, r15d
0x180029b77  jz      short loc_180029B98
0x180029b79  lea     rdx, [rbp+610h+SourceString]
0x180029b80  lea     rcx, [rbp+610h+var_510]
0x180029b87  call    ComputeTargetNameFromUncName
0x180029b8c  test    eax, eax
0x180029b8e  jnz     short loc_180029B98
0x180029b90  lea     ebx, [rax+57h]
0x180029b93  jmp     loc_180029D92
0x180029b98  test    rdi, rdi
0x180029b9b  jz      loc_180029C42
0x180029ba1  mov     dl, 1; Wait
0x180029ba3  mov     dword ptr [rbp+610h+var_688.Length], 0
0x180029baa  lea     rcx, Resource; Resource
0x180029bb1  call    cs:__imp_RtlAcquireResourceExclusive
0x180029bb7  test    al, al
0x180029bb9  jnz     short loc_180029BC5
0x180029bbb  mov     ebx, 85Ch
0x180029bc0  jmp     loc_180029D92
0x180029bc5  xor     r9d, r9d
0x180029bc8  mov     [rsp+720h+Destination], 0
0x180029bd1  lea     r8, [rbp+610h+var_688]
0x180029bd5  lea     rdx, [rbp+610h+SourceLuid]
0x180029bd9  lea     rcx, Use
0x180029be0  call    WsGetUserEntry
0x180029be5  test    eax, eax
0x180029be7  jnz     short loc_180029C2D
0x180029be9  mov     eax, dword ptr [rbp+610h+var_688.Length]
0x180029bec  lea     rcx, [rax+rax*2]
0x180029bf0  mov     rax, cs:Use
0x180029bf7  mov     rcx, [rax+rcx*8]
0x180029bfb  test    rcx, rcx
0x180029bfe  jz      short loc_180029C2D
0x180029c00  lea     r9, [rbp+610h+DestinationString]
0x180029c04  mov     qword ptr [rbp+610h+var_688.Length], 0
0x180029c0c  lea     r8, [rbp+610h+var_688]
0x180029c10  mov     qword ptr [rbp+610h+DestinationString.Length], 0
0x180029c18  mov     rdx, rdi
0x180029c1b  call    WsFindLocal
0x180029c20  cmp     qword ptr [rbp+610h+var_688.Length], 0
0x180029c25  mov     eax, 55h ; 'U'
0x180029c2a  cmovnz  ebx, eax
0x180029c2d  lea     rcx, Resource; Resource
0x180029c34  call    cs:__imp_RtlReleaseResource
0x180029c3a  test    ebx, ebx
0x180029c3c  jnz     loc_180029D92
0x180029c42  xorps   xmm0, xmm0
0x180029c45  lea     rcx, [rbp+610h+DestinationString]; DestinationString
0x180029c49  xorps   xmm1, xmm1
0x180029c4c  mov     ebx, r13d
0x180029c4f  mov     rdx, rdi; SourceString
0x180029c52  or      ebx, 1
0x180029c55  movups  xmmword ptr [rbp+610h+DestinationString.Length], xmm0
0x180029c59  movups  xmmword ptr [rbp+610h+var_688.Length], xmm1
0x180029c5d  call    cs:__imp_RtlInitUnicodeString
0x180029c63  test    r15d, r15d
0x180029c66  jz      short loc_180029C79
0x180029c68  lea     rdx, [rbp+610h+SourceString]; SourceString
0x180029c6f  lea     rcx, [rbp+610h+var_688]; DestinationString
0x180029c73  call    cs:__imp_RtlInitUnicodeString
0x180029c79  neg     r15d
0x180029c7c  lea     rax, [rbp+610h+var_688]
0x180029c80  lea     rdx, [rbp+610h+DestinationString]; int
0x180029c84  sbb     rcx, rcx
0x180029c87  xor     r15d, r15d
0x180029c8a  mov     [rsp+720h+var_698], r15
0x180029c92  and     rcx, rax
0x180029c95  lea     rax, [rbp+610h+Handle]
0x180029c99  xor     r9d, r9d; int
0x180029c9c  mov     [rsp+720h+FileHandle], rax; FileHandle
0x180029ca4  xor     r8d, r8d; int
0x180029ca7  mov     rax, [rbp+610h+var_660]
0x180029cab  mov     [rsp+720h+var_6A8], 1; char
0x180029cb0  mov     [rsp+720h+var_6B0], r15b; char
0x180029cb5  mov     [rsp+720h+var_6B8], 1; char
0x180029cba  mov     [rsp+720h+var_6C0], r15d; int
0x180029cbf  mov     [rsp+720h+var_6C8], 3; ULONG
0x180029cc7  mov     [rsp+720h+var_6D0], ebx; ULONG
0x180029ccb  mov     [rsp+720h+var_6D8], rax; __int64
0x180029cd0  mov     rax, [rbp+610h+var_658]
0x180029cd4  mov     [rsp+720h+var_6E0], rax; __int64
0x180029cd9  mov     rax, [rbp+610h+var_650]
0x180029cdd  mov     [rsp+720h+var_6E8], rax; __int64
0x180029ce2  mov     rax, [rbp+610h+var_648]
0x180029ce6  mov     [rsp+720h+var_6F0], rax; __int64
0x180029ceb  mov     [rsp+720h+hMem], rsi; hMem
0x180029cf0  mov     [rsp+720h+Destination], rcx; __int64
0x180029cf5  lea     rcx, [rbp+610h+var_638]; int
0x180029cf9  call    WsOpenCreateConnectionSpecifyImpersonation
0x180029cfe  mov     ebx, eax
0x180029d00  test    eax, eax
0x180029d02  jz      short loc_180029D15
0x180029d04  cmp     eax, 8CAh
0x180029d09  jnz     loc_180029D92
0x180029d0f  lea     ebx, [r15+37h]
0x180029d13  jmp     short loc_180029D92
0x180029d15  mov     rax, [rbp+610h+var_660]
0x180029d19  lea     rdx, [rbp+610h+var_640]; PLUID
0x180029d1d  mov     r8, [rbp+610h+Handle]
0x180029d21  lea     rcx, [rbp+610h+SourceLuid]; SourceLuid
0x180029d25  mov     qword ptr [rsp+720h+var_6C8], rax; __int64
0x180029d2a  mov     r9, rdi
0x180029d2d  mov     rax, [rbp+610h+var_658]
0x180029d31  mov     qword ptr [rsp+720h+var_6D0], rax; __int64
0x180029d36  mov     rax, [rbp+610h+var_650]
0x180029d3a  mov     [rsp+720h+var_6D8], rax; __int64
0x180029d3f  lea     rax, [rbp+610h+var_638]
0x180029d43  mov     dword ptr [rsp+720h+var_6E0], r13d; int
0x180029d48  mov     [rsp+720h+var_6E8], rax; __int64
0x180029d4d  lea     rax, [rbp+610h+var_510]
0x180029d54  mov     dword ptr [rsp+720h+var_6F0], r12d; int
0x180029d59  mov     [rsp+720h+hMem], rax; __int64
0x180029d5e  mov     dword ptr [rsp+720h+Destination], r14d; int
0x180029d63  call    WsAddUse
0x180029d68  mov     ebx, eax
0x180029d6a  test    eax, eax
0x180029d6c  jz      short loc_180029D92
0x180029d6e  mov     rdx, [rbp+610h+Handle]; Handle
0x180029d72  lea     rcx, [rbp+610h+SourceLuid]; SourceLuid
0x180029d76  mov     r9b, 1
0x180029d79  mov     r8d, 2
0x180029d7f  call    WsDeleteConnectionEx
0x180029d84  test    eax, eax
0x180029d86  jz      short loc_180029D92
0x180029d88  mov     rcx, [rbp+610h+Handle]; Handle
0x180029d8c  call    cs:__imp_NtClose
0x180029d92  mov     eax, ebx
0x180029d94  jmp     loc_180029AAC
```
