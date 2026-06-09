# CreateDefaultSecurityDescriptor(void)

- ea: `0x140047a48`
- end: `0x140047d18`
- name: `?CreateDefaultSecurityDescriptor@@YAKXZ`
- size: `720`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400483d4`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x140047a48`
- `0x1400487d4`
- `0x14007566c`

## import_xrefs

- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140047ad2`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140047ad2`
- `ADVAPI32!DestroyPrivateObjectSecurity` at `0x140047cbb`
- `ADVAPI32!DestroyPrivateObjectSecurity` at `0x140047cbb`
- `ADVAPI32!OpenProcessToken` at `0x140047b45`
- `ADVAPI32!OpenProcessToken` at `0x140047b45`
- `ADVAPI32!CreatePrivateObjectSecurity` at `0x140047bc2`
- `ADVAPI32!CreatePrivateObjectSecurity` at `0x140047bc2`
- `KERNEL32!GetLastError` at `0x140047ae2`
- `KERNEL32!GetLastError` at `0x140047b55`
- `KERNEL32!GetLastError` at `0x140047bd2`
- `KERNEL32!GetLastError` at `0x140047c89`
- `KERNEL32!GetLastError` at `0x140047ce3`
- `KERNEL32!GetLastError` at `0x140047ae2`
- `KERNEL32!GetLastError` at `0x140047b55`
- `KERNEL32!GetLastError` at `0x140047bd2`
- `KERNEL32!GetLastError` at `0x140047c89`
- `KERNEL32!GetLastError` at `0x140047ce3`
- `KERNEL32!CloseHandle` at `0x140047c61`
- `KERNEL32!CloseHandle` at `0x140047c61`
- `KERNEL32!LocalFree` at `0x140047c4c`
- `KERNEL32!LocalFree` at `0x140047c4c`
- `KERNEL32!GetCurrentProcess` at `0x140047b2d`
- `KERNEL32!GetCurrentProcess` at `0x140047b2d`

## pseudocode

```c
__int64 CreateDefaultSecurityDescriptor(void)
{
  int v0; // eax
  const WCHAR *v1; // rcx
  DWORD LastError; // eax
  DWORD v3; // ebx
  HANDLE CurrentProcess; // rax
  DWORD v5; // eax
  CMapDeviceId *v6; // rcx
  __int64 v7; // rdx
  DWORD v8; // eax
  DWORD v9; // eax
  ULONG SecurityDescriptorSize; // [rsp+60h] [rbp+28h] BYREF
  PSECURITY_DESCRIPTOR NewDescriptor; // [rsp+68h] [rbp+30h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+70h] [rbp+38h] BYREF
  void *TokenHandle; // [rsp+78h] [rbp+40h] BYREF

  SecurityDescriptor = 0;
  NewDescriptor = 0;
  SecurityDescriptorSize = 0;
  TokenHandle = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids);
  }
  v0 = IsServerSku();
  v1 = L"O:NSG:NSD:(A;;0xe02e7;;;BA)(A;;0x20003;;;WD)(A;;0x20227;;;IU)";
  if ( v0 )
    v1 = L"O:NSG:NSD:(A;;0xe02e7;;;BA)(A;;0x20003;;;WD)";
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v1, 1u, &SecurityDescriptor, &SecurityDescriptorSize) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids, LastError);
    }
    goto LABEL_29;
  }
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    v5 = GetLastError();
    v3 = v5;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_29;
    }
    v7 = 32;
    goto LABEL_17;
  }
  if ( !CreatePrivateObjectSecurity(
          0,
          SecurityDescriptor,
          &NewDescriptor,
          0,
          TokenHandle,
          (PGENERIC_MAPPING)&GenericMapping) )
  {
    v5 = GetLastError();
    v3 = v5;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_29;
    }
    v7 = 33;
LABEL_17:
    WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids, v5);
    goto LABEL_29;
  }
  v5 = SaveSecurityDescriptor(NewDescriptor);
  v3 = v5;
  if ( !v5 )
  {
    g_pFaxSD = NewDescriptor;
    NewDescriptor = 0;
    goto LABEL_29;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v7 = 34;
    goto LABEL_17;
  }
LABEL_29:
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( TokenHandle
    && !CloseHandle(TokenHandle)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v8 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids, v8);
  }
  if ( NewDescriptor
    && !DestroyPrivateObjectSecurity(&NewDescriptor)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v9 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids, v9);
  }
  return v3;
}

```

## disassembly

```asm
0x140047a48  push    rbp
0x140047a4a  push    rbx
0x140047a4b  push    r12
0x140047a4d  push    r14
0x140047a4f  mov     rbp, rsp
0x140047a52  sub     rsp, 38h
0x140047a56  mov     [rbp+SecurityDescriptor], 0
0x140047a5e  mov     [rbp+NewDescriptor], 0
0x140047a66  mov     [rbp+SecurityDescriptorSize], 0
0x140047a6d  mov     [rbp+TokenHandle], 0
0x140047a75  mov     rcx, cs:WPP_GLOBAL_Control
0x140047a7c  lea     r14, WPP_GLOBAL_Control
0x140047a83  lea     r12, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids
0x140047a8a  cmp     rcx, r14
0x140047a8d  jz      short loc_140047AAC
0x140047a8f  test    byte ptr [rcx+1Ch], 4
0x140047a93  jz      short loc_140047AAC
0x140047a95  cmp     byte ptr [rcx+19h], 5
0x140047a99  jb      short loc_140047AAC
0x140047a9b  mov     rcx, [rcx+10h]
0x140047a9f  mov     edx, 1Eh
0x140047aa4  mov     r8, r12
0x140047aa7  call    WPP_SF_
0x140047aac  call    IsServerSku
0x140047ab1  lea     rdx, aONsgNsdA0xe02e; "O:NSG:NSD:(A;;0xe02e7;;;BA)(A;;0x20003;"...
0x140047ab8  test    eax, eax
0x140047aba  lea     rcx, aONsgNsdA0xe02e_0; "O:NSG:NSD:(A;;0xe02e7;;;BA)(A;;0x20003;"...
0x140047ac1  cmovnz  rcx, rdx; StringSecurityDescriptor
0x140047ac5  lea     r9, [rbp+SecurityDescriptorSize]; SecurityDescriptorSize
0x140047ac9  mov     edx, 1; StringSDRevision
0x140047ace  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140047ad2  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x140047ad9  nop     dword ptr [rax+rax+00h]
0x140047ade  test    eax, eax
0x140047ae0  jnz     short loc_140047B2D
0x140047ae2  call    cs:__imp_GetLastError
0x140047ae9  nop     dword ptr [rax+rax+00h]
0x140047aee  mov     ebx, eax
0x140047af0  mov     rcx, cs:WPP_GLOBAL_Control
0x140047af7  cmp     rcx, r14
0x140047afa  jz      loc_140047C43
0x140047b00  test    byte ptr [rcx+1Ch], 4
0x140047b04  jz      loc_140047C43
0x140047b0a  cmp     byte ptr [rcx+19h], 2
0x140047b0e  jb      loc_140047C43
0x140047b14  mov     rcx, [rcx+10h]
0x140047b18  mov     edx, 1Fh
0x140047b1d  mov     r9d, eax
0x140047b20  mov     r8, r12
0x140047b23  call    WPP_SF_d
0x140047b28  jmp     loc_140047C43
0x140047b2d  call    cs:__imp_GetCurrentProcess
0x140047b34  nop     dword ptr [rax+rax+00h]
0x140047b39  lea     r8, [rbp+TokenHandle]; TokenHandle
0x140047b3d  mov     edx, 8; DesiredAccess
0x140047b42  mov     rcx, rax; ProcessHandle
0x140047b45  call    cs:__imp_OpenProcessToken
0x140047b4c  nop     dword ptr [rax+rax+00h]
0x140047b51  test    eax, eax
0x140047b53  jnz     short loc_140047BA0
0x140047b55  call    cs:__imp_GetLastError
0x140047b5c  nop     dword ptr [rax+rax+00h]
0x140047b61  mov     ebx, eax
0x140047b63  mov     rcx, cs:WPP_GLOBAL_Control
0x140047b6a  cmp     rcx, r14
0x140047b6d  jz      loc_140047C43
0x140047b73  test    byte ptr [rcx+1Ch], 4
0x140047b77  jz      loc_140047C43
0x140047b7d  cmp     byte ptr [rcx+19h], 2
0x140047b81  jb      loc_140047C43
0x140047b87  mov     edx, 20h ; ' '
0x140047b8c  mov     rcx, [rcx+10h]
0x140047b90  mov     r9d, eax
0x140047b93  mov     r8, r12
0x140047b96  call    WPP_SF_d
0x140047b9b  jmp     loc_140047C43
0x140047ba0  mov     rdx, [rbp+SecurityDescriptor]; CreatorDescriptor
0x140047ba4  lea     rax, GenericMapping
0x140047bab  mov     [rsp+38h+GenericMapping], rax; GenericMapping
0x140047bb0  lea     r8, [rbp+NewDescriptor]; NewDescriptor
0x140047bb4  mov     rax, [rbp+TokenHandle]
0x140047bb8  xor     r9d, r9d; IsDirectoryObject
0x140047bbb  xor     ecx, ecx; ParentDescriptor
0x140047bbd  mov     [rsp+38h+Token], rax; Token
0x140047bc2  call    cs:__imp_CreatePrivateObjectSecurity
0x140047bc9  nop     dword ptr [rax+rax+00h]
0x140047bce  test    eax, eax
0x140047bd0  jnz     short loc_140047BFF
0x140047bd2  call    cs:__imp_GetLastError
0x140047bd9  nop     dword ptr [rax+rax+00h]
0x140047bde  mov     ebx, eax
0x140047be0  mov     rcx, cs:WPP_GLOBAL_Control
0x140047be7  cmp     rcx, r14
0x140047bea  jz      short loc_140047C43
0x140047bec  test    byte ptr [rcx+1Ch], 4
0x140047bf0  jz      short loc_140047C43
0x140047bf2  cmp     byte ptr [rcx+19h], 2
0x140047bf6  jb      short loc_140047C43
0x140047bf8  mov     edx, 21h ; '!'
0x140047bfd  jmp     short loc_140047B8C
0x140047bff  mov     rcx, [rbp+NewDescriptor]; pAbsoluteSecurityDescriptor
0x140047c03  call    ?SaveSecurityDescriptor@@YAKPEAX@Z; SaveSecurityDescriptor(void *)
0x140047c08  mov     ebx, eax
0x140047c0a  test    eax, eax
0x140047c0c  jz      short loc_140047C30
0x140047c0e  mov     rcx, cs:WPP_GLOBAL_Control
0x140047c15  cmp     rcx, r14
0x140047c18  jz      short loc_140047C43
0x140047c1a  test    byte ptr [rcx+1Ch], 4
0x140047c1e  jz      short loc_140047C43
0x140047c20  cmp     byte ptr [rcx+19h], 2
0x140047c24  jb      short loc_140047C43
0x140047c26  mov     edx, 22h ; '"'
0x140047c2b  jmp     loc_140047B8C
0x140047c30  mov     rax, [rbp+NewDescriptor]
0x140047c34  mov     cs:?g_pFaxSD@@3PEAXEA, rax; void * g_pFaxSD
0x140047c3b  mov     [rbp+NewDescriptor], 0
0x140047c43  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x140047c47  test    rcx, rcx
0x140047c4a  jz      short loc_140047C58
0x140047c4c  call    cs:__imp_LocalFree
0x140047c53  nop     dword ptr [rax+rax+00h]
0x140047c58  mov     rcx, [rbp+TokenHandle]; hObject
0x140047c5c  test    rcx, rcx
0x140047c5f  jz      short loc_140047CB0
0x140047c61  call    cs:__imp_CloseHandle
0x140047c68  nop     dword ptr [rax+rax+00h]
0x140047c6d  test    eax, eax
0x140047c6f  jnz     short loc_140047CB0
0x140047c71  mov     rax, cs:WPP_GLOBAL_Control
0x140047c78  cmp     rax, r14
0x140047c7b  jz      short loc_140047CB0
0x140047c7d  test    byte ptr [rax+1Ch], 4
0x140047c81  jz      short loc_140047CB0
0x140047c83  cmp     byte ptr [rax+19h], 2
0x140047c87  jb      short loc_140047CB0
0x140047c89  call    cs:__imp_GetLastError
0x140047c90  nop     dword ptr [rax+rax+00h]
0x140047c95  mov     rcx, cs:WPP_GLOBAL_Control
0x140047c9c  mov     edx, 23h ; '#'
0x140047ca1  mov     r9d, eax
0x140047ca4  mov     r8, r12
0x140047ca7  mov     rcx, [rcx+10h]
0x140047cab  call    WPP_SF_d
0x140047cb0  cmp     [rbp+NewDescriptor], 0
0x140047cb5  jz      short loc_140047D0A
0x140047cb7  lea     rcx, [rbp+NewDescriptor]; ObjectDescriptor
0x140047cbb  call    cs:__imp_DestroyPrivateObjectSecurity
0x140047cc2  nop     dword ptr [rax+rax+00h]
0x140047cc7  test    eax, eax
0x140047cc9  jnz     short loc_140047D0A
0x140047ccb  mov     rax, cs:WPP_GLOBAL_Control
0x140047cd2  cmp     rax, r14
0x140047cd5  jz      short loc_140047D0A
0x140047cd7  test    byte ptr [rax+1Ch], 4
0x140047cdb  jz      short loc_140047D0A
0x140047cdd  cmp     byte ptr [rax+19h], 2
0x140047ce1  jb      short loc_140047D0A
0x140047ce3  call    cs:__imp_GetLastError
0x140047cea  nop     dword ptr [rax+rax+00h]
0x140047cef  mov     rcx, cs:WPP_GLOBAL_Control
0x140047cf6  mov     edx, 24h ; '$'
0x140047cfb  mov     r9d, eax
0x140047cfe  mov     r8, r12
0x140047d01  mov     rcx, [rcx+10h]
0x140047d05  call    WPP_SF_d
0x140047d0a  mov     eax, ebx
0x140047d0c  add     rsp, 38h
0x140047d10  pop     r14
0x140047d12  pop     r12
0x140047d14  pop     rbx
0x140047d15  pop     rbp
0x140047d16  retn
```
