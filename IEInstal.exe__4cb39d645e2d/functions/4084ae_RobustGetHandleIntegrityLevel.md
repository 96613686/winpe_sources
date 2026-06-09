# RobustGetHandleIntegrityLevel

- ea: `0x4084ae`
- end: `0x408658`
- name: `RobustGetHandleIntegrityLevel`
- size: `426`
- prototype: `unsigned int __fastcall(HANDLE Handle, PSID *Sid)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x4075cd`
- `0x4088b6`

## callees

- `0x4084ae`

## import_xrefs

- `ADVAPI32!GetLengthSid` at `0x4085ba`
- `ADVAPI32!GetLengthSid` at `0x4085d8`
- `ADVAPI32!GetLengthSid` at `0x4085ba`
- `ADVAPI32!GetLengthSid` at `0x4085d8`
- `ADVAPI32!GetKernelObjectSecurity` at `0x4084d5`
- `ADVAPI32!GetKernelObjectSecurity` at `0x40851a`
- `ADVAPI32!GetKernelObjectSecurity` at `0x4084d5`
- `ADVAPI32!GetKernelObjectSecurity` at `0x40851a`
- `ADVAPI32!ConvertStringSidToSidW` at `0x408621`
- `ADVAPI32!ConvertStringSidToSidW` at `0x408621`
- `ADVAPI32!CopySid` at `0x4085df`
- `ADVAPI32!CopySid` at `0x4085df`
- `ADVAPI32!GetAce` at `0x408590`
- `ADVAPI32!GetAce` at `0x408590`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x408558`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x408558`
- `KERNEL32!LocalAlloc` at `0x4084f7`
- `KERNEL32!LocalAlloc` at `0x4085c3`
- `KERNEL32!LocalAlloc` at `0x4084f7`
- `KERNEL32!LocalAlloc` at `0x4085c3`
- `KERNEL32!LocalFree` at `0x408605`
- `KERNEL32!LocalFree` at `0x408644`
- `KERNEL32!LocalFree` at `0x408605`
- `KERNEL32!LocalFree` at `0x408644`
- `KERNEL32!GetLastError` at `0x4084e7`
- `KERNEL32!GetLastError` at `0x408524`
- `KERNEL32!GetLastError` at `0x4085f0`
- `KERNEL32!GetLastError` at `0x40862b`
- `KERNEL32!GetLastError` at `0x4084e7`
- `KERNEL32!GetLastError` at `0x408524`
- `KERNEL32!GetLastError` at `0x4085f0`
- `KERNEL32!GetLastError` at `0x40862b`

## pseudocode

```c
unsigned int __fastcall RobustGetHandleIntegrityLevel(HANDLE Handle, PSID *Sid)
{
  unsigned int v3; // esi
  HLOCAL v4; // edi
  signed int LastError; // eax
  SIZE_T LengthSid; // eax
  HLOCAL v7; // ebx
  DWORD v8; // eax
  signed int v9; // eax
  signed int v10; // eax
  char *v13; // [esp+10h] [ebp-18h]
  BOOL bSaclDefaulted; // [esp+14h] [ebp-14h] BYREF
  HANDLE Handlea; // [esp+18h] [ebp-10h] BYREF
  PACL pSacl; // [esp+1Ch] [ebp-Ch] BYREF
  BOOL bSaclPresent; // [esp+20h] [ebp-8h] BYREF
  DWORD nLengthNeeded; // [esp+24h] [ebp-4h] BYREF

  Handlea = Handle;
  v3 = 0;
  nLengthNeeded = 0;
  v4 = 0;
  if ( GetKernelObjectSecurity(Handle, 0x10u, 0, 0, &nLengthNeeded) )
    return -2147418113;
  *Sid = 0;
  LastError = GetLastError();
  if ( LastError == 122 )
  {
    v4 = LocalAlloc(0x40u, nLengthNeeded);
    if ( !v4 )
      return -2147024882;
    if ( GetKernelObjectSecurity(Handlea, 0x10u, v4, nLengthNeeded, &nLengthNeeded) )
      goto LABEL_10;
    LastError = GetLastError();
  }
  v3 = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    v3 = LastError;
  if ( v3 )
    goto LABEL_29;
LABEL_10:
  pSacl = 0;
  bSaclPresent = 0;
  bSaclDefaulted = 0;
  if ( !GetSecurityDescriptorSacl(v4, &bSaclPresent, &pSacl, &bSaclDefaulted) )
    goto LABEL_27;
  if ( bSaclPresent && pSacl && pSacl->AceCount )
  {
    Handlea = 0;
    if ( GetAce(pSacl, 0, &Handlea) )
    {
      v13 = (char *)Handlea;
      if ( (*((_BYTE *)Handlea + 1) & 8) != 0 )
      {
        v3 = -2147023556;
      }
      else if ( Handlea == (HANDLE)-8 )
      {
        v3 = -2147467259;
      }
      else
      {
        LengthSid = GetLengthSid((char *)Handlea + 8);
        v7 = LocalAlloc(0x40u, LengthSid);
        if ( v7 )
        {
          v8 = GetLengthSid(v13 + 8);
          if ( CopySid(v8, v7, v13 + 8) )
          {
            *Sid = v7;
          }
          else
          {
            v9 = GetLastError();
            v3 = (unsigned __int16)v9 | 0x80070000;
            if ( v9 <= 0 )
              v3 = v9;
            LocalFree(v7);
          }
        }
        else
        {
          v3 = -2147024882;
        }
      }
      goto LABEL_29;
    }
LABEL_27:
    v10 = GetLastError();
    v3 = (unsigned __int16)v10 | 0x80070000;
    if ( v10 <= 0 )
      v3 = v10;
    goto LABEL_29;
  }
  if ( !ConvertStringSidToSidW(L"ME", Sid) )
    goto LABEL_27;
LABEL_29:
  if ( v4 )
    LocalFree(v4);
  return v3;
}

```

## disassembly

```asm
0x4084ae  mov     edi, edi
0x4084b0  push    ebp
0x4084b1  mov     ebp, esp
0x4084b3  sub     esp, 1Ch
0x4084b6  push    ebx
0x4084b7  push    esi
0x4084b8  push    edi
0x4084b9  mov     eax, ecx
0x4084bb  mov     ebx, edx
0x4084bd  xor     edx, edx
0x4084bf  mov     [ebp+var_1C], ebx
0x4084c2  lea     ecx, [ebp+nLengthNeeded]
0x4084c5  mov     [ebp+Handle], eax
0x4084c8  push    ecx; lpnLengthNeeded
0x4084c9  push    edx; nLength
0x4084ca  push    edx; pSecurityDescriptor
0x4084cb  push    10h; RequestedInformation
0x4084cd  push    eax; Handle
0x4084ce  mov     esi, edx
0x4084d0  mov     [ebp+nLengthNeeded], edx
0x4084d3  mov     edi, edx
0x4084d5  call    ds:__imp__GetKernelObjectSecurity@20; GetKernelObjectSecurity(x,x,x,x,x)
0x4084db  test    eax, eax
0x4084dd  jnz     loc_40864C
0x4084e3  xor     edx, edx
0x4084e5  mov     [ebx], edx
0x4084e7  call    ds:__imp__GetLastError@0; GetLastError()
0x4084ed  cmp     eax, 7Ah ; 'z'
0x4084f0  jnz     short loc_40852A
0x4084f2  push    [ebp+nLengthNeeded]; uBytes
0x4084f5  push    40h ; '@'; uFlags
0x4084f7  call    ds:__imp__LocalAlloc@8; LocalAlloc(x,x)
0x4084fd  mov     edi, eax
0x4084ff  test    edi, edi
0x408501  jnz     short loc_40850D
0x408503  mov     esi, 8007000Eh
0x408508  jmp     loc_408651
0x40850d  lea     eax, [ebp+nLengthNeeded]
0x408510  push    eax; lpnLengthNeeded
0x408511  push    [ebp+nLengthNeeded]; nLength
0x408514  push    edi; pSecurityDescriptor
0x408515  push    10h; RequestedInformation
0x408517  push    [ebp+Handle]; Handle
0x40851a  call    ds:__imp__GetKernelObjectSecurity@20; GetKernelObjectSecurity(x,x,x,x,x)
0x408520  test    eax, eax
0x408522  jnz     short loc_408540
0x408524  call    ds:__imp__GetLastError@0; GetLastError()
0x40852a  movzx   esi, ax
0x40852d  or      esi, 80070000h
0x408533  test    eax, eax
0x408535  cmovle  esi, eax
0x408538  test    esi, esi
0x40853a  jnz     loc_40863F
0x408540  xor     eax, eax
0x408542  mov     [ebp+pSacl], eax
0x408545  mov     [ebp+bSaclPresent], eax
0x408548  mov     [ebp+bSaclDefaulted], eax
0x40854b  lea     eax, [ebp+bSaclDefaulted]
0x40854e  push    eax; lpbSaclDefaulted
0x40854f  lea     eax, [ebp+pSacl]
0x408552  push    eax; pSacl
0x408553  lea     eax, [ebp+bSaclPresent]
0x408556  push    eax; lpbSaclPresent
0x408557  push    edi; pSecurityDescriptor
0x408558  call    ds:__imp__GetSecurityDescriptorSacl@16; GetSecurityDescriptorSacl(x,x,x,x)
0x40855e  test    eax, eax
0x408560  jz      loc_40862B
0x408566  cmp     [ebp+bSaclPresent], 0
0x40856a  jz      loc_40861B
0x408570  mov     eax, [ebp+pSacl]
0x408573  test    eax, eax
0x408575  jz      loc_40861B
0x40857b  xor     edx, edx
0x40857d  cmp     [eax+4], dx
0x408581  jz      loc_40861B
0x408587  lea     ecx, [ebp+Handle]
0x40858a  mov     [ebp+Handle], edx
0x40858d  push    ecx; pAce
0x40858e  push    edx; dwAceIndex
0x40858f  push    eax; pAcl
0x408590  call    ds:__imp__GetAce@12; GetAce(x,x,x)
0x408596  test    eax, eax
0x408598  jz      loc_40862B
0x40859e  mov     eax, [ebp+Handle]
0x4085a1  mov     [ebp+var_18], eax
0x4085a4  test    byte ptr [eax+1], 8
0x4085a8  jz      short loc_4085B4
0x4085aa  mov     esi, 8007053Ch
0x4085af  jmp     loc_40863F
0x4085b4  add     eax, 8
0x4085b7  jz      short loc_408614
0x4085b9  push    eax; pSid
0x4085ba  call    ds:__imp__GetLengthSid@4; GetLengthSid(x)
0x4085c0  push    eax; uBytes
0x4085c1  push    40h ; '@'; uFlags
0x4085c3  call    ds:__imp__LocalAlloc@8; LocalAlloc(x,x)
0x4085c9  mov     ebx, eax
0x4085cb  test    ebx, ebx
0x4085cd  jz      short loc_40860D
0x4085cf  mov     eax, [ebp+var_18]
0x4085d2  add     eax, 8
0x4085d5  push    eax; pSourceSid
0x4085d6  push    ebx; pDestinationSid
0x4085d7  push    eax; pSid
0x4085d8  call    ds:__imp__GetLengthSid@4; GetLengthSid(x)
0x4085de  push    eax; nDestinationSidLength
0x4085df  call    ds:__imp__CopySid@12; CopySid(x,x,x)
0x4085e5  test    eax, eax
0x4085e7  jz      short loc_4085F0
0x4085e9  mov     eax, [ebp+var_1C]
0x4085ec  mov     [eax], ebx
0x4085ee  jmp     short loc_40863F
0x4085f0  call    ds:__imp__GetLastError@0; GetLastError()
0x4085f6  movzx   esi, ax
0x4085f9  or      esi, 80070000h
0x4085ff  test    eax, eax
0x408601  push    ebx; hMem
0x408602  cmovle  esi, eax
0x408605  call    ds:__imp__LocalFree@4; LocalFree(x)
0x40860b  jmp     short loc_40863F
0x40860d  mov     esi, 8007000Eh
0x408612  jmp     short loc_40863F
0x408614  mov     esi, 80004005h
0x408619  jmp     short loc_40863F
0x40861b  push    ebx; Sid
0x40861c  push    offset StringSid; "ME"
0x408621  call    ds:__imp__ConvertStringSidToSidW@8; ConvertStringSidToSidW(x,x)
0x408627  test    eax, eax
0x408629  jnz     short loc_40863F
0x40862b  call    ds:__imp__GetLastError@0; GetLastError()
0x408631  movzx   esi, ax
0x408634  or      esi, 80070000h
0x40863a  test    eax, eax
0x40863c  cmovle  esi, eax
0x40863f  test    edi, edi
0x408641  jz      short loc_408651
0x408643  push    edi; hMem
0x408644  call    ds:__imp__LocalFree@4; LocalFree(x)
0x40864a  jmp     short loc_408651
0x40864c  mov     esi, 8000FFFFh
0x408651  pop     edi
0x408652  mov     eax, esi
0x408654  pop     esi
0x408655  pop     ebx
0x408656  leave
0x408657  retn
```
