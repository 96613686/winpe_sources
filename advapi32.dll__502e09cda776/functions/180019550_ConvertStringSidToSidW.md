# ConvertStringSidToSidW

- ea: `0x180019550`
- end: `0x180019787`
- name: `ConvertStringSidToSidW`
- size: `567`
- prototype: `BOOL __stdcall(LPCWSTR StringSid, PSID *Sid)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180019440`
- `0x18004d470`
- `0x18004da7c`

## callees

- `0x180019550`
- `0x180019790`
- `0x18001c000`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x1800196ac`
- `ntdll!RtlLengthSid` at `0x1800196ac`
- `ntdll!RtlCopySid` at `0x1800196de`
- `ntdll!RtlCopySid` at `0x1800196de`
- `ntdll!RtlNtStatusToDosError` at `0x180019614`
- `ntdll!RtlNtStatusToDosError` at `0x1800196ec`
- `ntdll!RtlNtStatusToDosError` at `0x180019614`
- `ntdll!RtlNtStatusToDosError` at `0x1800196ec`
- `KERNELBASE!LocalAlloc` at `0x1800196c1`
- `KERNELBASE!LocalAlloc` at `0x1800196c1`
- `KERNEL32!LocalFree` at `0x18001971c`
- `KERNEL32!LocalFree` at `0x180019740`
- `KERNEL32!LocalFree` at `0x180019776`
- `KERNEL32!LocalFree` at `0x18001971c`
- `KERNEL32!LocalFree` at `0x180019740`
- `KERNEL32!LocalFree` at `0x180019776`
- `KERNEL32!GetLastError` at `0x180019631`
- `KERNEL32!GetLastError` at `0x180019631`
- `KERNEL32!SetLastError` at `0x180019594`
- `KERNEL32!SetLastError` at `0x1800195ce`
- `KERNEL32!SetLastError` at `0x180019604`
- `KERNEL32!SetLastError` at `0x180019622`
- `KERNEL32!SetLastError` at `0x18001970d`
- `KERNEL32!SetLastError` at `0x180019594`
- `KERNEL32!SetLastError` at `0x1800195ce`
- `KERNEL32!SetLastError` at `0x180019604`
- `KERNEL32!SetLastError` at `0x180019622`
- `KERNEL32!SetLastError` at `0x18001970d`

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
0x180019550  mov     rax, rsp
0x180019553  mov     [rax+10h], rbx
0x180019557  push    rbp
0x180019558  push    rsi
0x180019559  push    rdi
0x18001955a  push    r14
0x18001955c  push    r15
0x18001955e  sub     rsp, 40h
0x180019562  xor     r15d, r15d
0x180019565  mov     rdi, rdx
0x180019568  mov     [rax+18h], r15
0x18001956c  mov     rsi, rcx
0x18001956f  mov     [rax+8], r15
0x180019573  test    rcx, rcx
0x180019576  jz      loc_1800195FC
0x18001957c  test    rdx, rdx
0x18001957f  jz      short loc_1800195FC
0x180019581  lea     r8, [rax+18h]
0x180019585  call    LocalpConvertStringSidToSid
0x18001958a  test    eax, eax
0x18001958c  js      loc_180019612
0x180019592  xor     ecx, ecx; dwErrCode
0x180019594  call    cs:__imp_SetLastError
0x18001959b  nop     dword ptr [rax+rax+00h]
0x1800195a0  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800195a4  inc     rcx
0x1800195a7  cmp     [rsi+rcx*2], r15w
0x1800195ac  jnz     short loc_1800195A4
0x1800195ae  mov     rax, [rsp+68h+arg_10]
0x1800195b6  sub     rax, rsi
0x1800195b9  sar     rax, 1
0x1800195bc  mov     eax, eax
0x1800195be  cmp     rax, rcx
0x1800195c1  jnz     loc_180019708
0x1800195c7  mov     ebx, 1
0x1800195cc  xor     ecx, ecx; dwErrCode
0x1800195ce  call    cs:__imp_SetLastError
0x1800195d5  nop     dword ptr [rax+rax+00h]
0x1800195da  mov     rcx, [rsp+68h+hMem]; hMem
0x1800195df  test    rcx, rcx
0x1800195e2  jnz     loc_180019776
0x1800195e8  mov     eax, ebx
0x1800195ea  mov     rbx, [rsp+68h+arg_8]
0x1800195ef  add     rsp, 40h
0x1800195f3  pop     r15
0x1800195f5  pop     r14
0x1800195f7  pop     rdi
0x1800195f8  pop     rsi
0x1800195f9  pop     rbp
0x1800195fa  retn
0x1800195fc  mov     ecx, 57h ; 'W'; dwErrCode
0x180019601  mov     ebx, r15d
0x180019604  call    cs:__imp_SetLastError
0x18001960b  nop     dword ptr [rax+rax+00h]
0x180019610  jmp     short loc_1800195E8
0x180019612  mov     ecx, eax; Status
0x180019614  call    cs:__imp_RtlNtStatusToDosError
0x18001961b  nop     dword ptr [rax+rax+00h]
0x180019620  mov     ecx, eax; dwErrCode
0x180019622  call    cs:__imp_SetLastError
0x180019629  nop     dword ptr [rax+rax+00h]
0x18001962e  mov     ebx, r15d
0x180019631  call    cs:__imp_GetLastError
0x180019638  nop     dword ptr [rax+rax+00h]
0x18001963d  xor     r9d, r9d
0x180019640  xor     r8d, r8d
0x180019643  mov     r14d, eax
0x180019646  xor     edx, edx; Sid2
0x180019648  lea     rax, [rsp+68h+hMem]
0x18001964d  mov     rcx, rsi; String1
0x180019650  mov     [rsp+68h+var_38], rax; __int64
0x180019655  mov     byte ptr [rsp+68h+var_40], r15b; __int64
0x18001965a  mov     [rsp+68h+var_48], r15; __int64
0x18001965f  call    LookupSidInTable
0x180019664  mov     rbp, rax
0x180019667  test    rax, rax
0x18001966a  jnz     short loc_180019682
0x18001966c  mov     rax, [rsp+68h+hMem]
0x180019671  test    rax, rax
0x180019674  jnz     loc_180019751
0x18001967a  mov     ecx, r14d
0x18001967d  jmp     loc_1800195CE
0x180019682  cmp     [rax+10h], r15
0x180019686  jz      short loc_18001966C
0x180019688  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001968c  inc     rcx
0x18001968f  cmp     [rsi+rcx*2], r15w
0x180019694  jnz     short loc_18001968C
0x180019696  mov     eax, [rax+0Ch]
0x180019699  cmp     rcx, rax
0x18001969c  jz      short loc_1800196A8
0x18001969e  mov     ecx, 539h
0x1800196a3  jmp     loc_1800195CE
0x1800196a8  mov     rcx, [rbp+10h]; Sid
0x1800196ac  call    cs:__imp_RtlLengthSid
0x1800196b3  nop     dword ptr [rax+rax+00h]
0x1800196b8  mov     edx, eax; uBytes
0x1800196ba  mov     ecx, 40h ; '@'; uFlags
0x1800196bf  mov     esi, eax
0x1800196c1  call    cs:__imp_LocalAlloc
0x1800196c8  nop     dword ptr [rax+rax+00h]
0x1800196cd  mov     [rdi], rax
0x1800196d0  test    rax, rax
0x1800196d3  jz      short loc_180019733
0x1800196d5  mov     r8, [rbp+10h]; SourceSid
0x1800196d9  mov     rdx, rax; DestinationSid
0x1800196dc  mov     ecx, esi; DestinationSidLength
0x1800196de  call    cs:__imp_RtlCopySid
0x1800196e5  nop     dword ptr [rax+rax+00h]
0x1800196ea  mov     ecx, eax; Status
0x1800196ec  call    cs:__imp_RtlNtStatusToDosError
0x1800196f3  nop     dword ptr [rax+rax+00h]
0x1800196f8  mov     esi, eax
0x1800196fa  test    eax, eax
0x1800196fc  jnz     short loc_18001973D
0x1800196fe  lea     ebx, [rax+1]
0x180019701  mov     ecx, esi
0x180019703  jmp     loc_1800195CE
0x180019708  mov     ecx, 539h; dwErrCode
0x18001970d  call    cs:__imp_SetLastError
0x180019714  nop     dword ptr [rax+rax+00h]
0x180019719  mov     rcx, [rdi]; hMem
0x18001971c  call    cs:__imp_LocalFree
0x180019723  nop     dword ptr [rax+rax+00h]
0x180019728  mov     [rdi], r15
0x18001972b  mov     ebx, r15d
0x18001972e  jmp     loc_1800195DA
0x180019733  mov     ecx, 8
0x180019738  jmp     loc_1800195CE
0x18001973d  mov     rcx, [rdi]; hMem
0x180019740  call    cs:__imp_LocalFree
0x180019747  nop     dword ptr [rax+rax+00h]
0x18001974c  mov     [rdi], r15
0x18001974f  jmp     short loc_180019701
0x180019751  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180019755  inc     rcx
0x180019758  cmp     [rsi+rcx*2], r15w
0x18001975d  jnz     short loc_180019755
0x18001975f  cmp     rcx, 2
0x180019763  jnz     loc_18001967A
0x180019769  mov     [rdi], rax
0x18001976c  mov     [rsp+68h+hMem], r15
0x180019771  jmp     loc_1800195C7
0x180019776  call    cs:__imp_LocalFree
0x18001977d  nop     dword ptr [rax+rax+00h]
0x180019782  jmp     loc_1800195E8
```
