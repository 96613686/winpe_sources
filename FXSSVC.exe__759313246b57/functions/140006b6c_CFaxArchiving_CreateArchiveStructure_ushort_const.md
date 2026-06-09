# CFaxArchiving::CreateArchiveStructure(ushort const *)

- ea: `0x140006b6c`
- end: `0x140006d30`
- name: `?CreateArchiveStructure@CFaxArchiving@@QEAAKPEBG@Z`
- size: `452`
- prototype: `__int64 __fastcall(CFaxArchiving *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400551cc`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x140006964`
- `0x140006b6c`
- `0x14000c440`

## import_xrefs

- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140006be0`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140006be0`
- `KERNEL32!GetLastError` at `0x140006bf0`
- `KERNEL32!GetLastError` at `0x140006bf0`
- `KERNEL32!LocalFree` at `0x140006d13`
- `KERNEL32!LocalFree` at `0x140006d13`

## pseudocode

```c
__int64 __fastcall CFaxArchiving::CreateArchiveStructure(CFaxArchiving *this, const unsigned __int16 *a2)
{
  CFaxArchiving *v3; // rcx
  DWORD LastError; // eax
  DWORD v5; // ebx
  DWORD v6; // eax
  CFaxArchiving *v7; // rcx
  CMapDeviceId *v8; // rcx
  __int64 v9; // rdx
  struct _SECURITY_ATTRIBUTES v11; // [rsp+30h] [rbp-20h] BYREF
  int v12; // [rsp+70h] [rbp+20h] BYREF
  int v13; // [rsp+74h] [rbp+24h]
  int v14; // [rsp+80h] [rbp+30h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+88h] [rbp+38h] BYREF

  v13 = HIDWORD(this);
  v12 = 0;
  v14 = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 176, &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids);
  }
  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"D:PAI(A;OICI;FA;;;BA)(A;OICI;FA;;;NS)",
          1u,
          &SecurityDescriptor,
          0) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 177, &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids, LastError);
    }
    return v5;
  }
  v11.lpSecurityDescriptor = SecurityDescriptor;
  *(_QWORD *)&v11.nLength = 24;
  *(_QWORD *)&v11.bInheritHandle = 0;
  v6 = CFaxArchiving::CreateArchiveFolder(v3, a2, 1, &v11, &v12);
  v5 = v6;
  if ( v6 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_21;
    }
    v9 = 178;
LABEL_20:
    WPP_SF_d(*((_QWORD *)v8 + 2), v9, &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids, v6);
LABEL_21:
    if ( v12 )
      CFaxArchiving::RemoveArchiveFolder(v8, a2, 1);
    if ( v14 )
      CFaxArchiving::RemoveArchiveFolder(v8, a2, 0);
    goto LABEL_25;
  }
  v6 = CFaxArchiving::CreateArchiveFolder(v7, a2, 0, &v11, &v14);
  v5 = v6;
  if ( v6 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_21;
    }
    v9 = 179;
    goto LABEL_20;
  }
LABEL_25:
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return v5;
}

```

## disassembly

```asm
0x140006b6c  mov     [rsp-18h+arg_8], rbx
0x140006b71  mov     qword ptr [rsp-18h+arg_0], rcx
0x140006b76  push    rbp
0x140006b77  push    rdi
0x140006b78  push    r15
0x140006b7a  mov     rbp, rsp
0x140006b7d  sub     rsp, 50h
0x140006b81  mov     rdi, rdx
0x140006b84  mov     [rbp+arg_0], 0
0x140006b8b  mov     [rbp+arg_10], 0
0x140006b92  mov     rcx, cs:WPP_GLOBAL_Control
0x140006b99  lea     r15, WPP_GLOBAL_Control
0x140006ba0  cmp     rcx, r15
0x140006ba3  jz      short loc_140006BC6
0x140006ba5  test    byte ptr [rcx+1Ch], 4
0x140006ba9  jz      short loc_140006BC6
0x140006bab  cmp     byte ptr [rcx+19h], 5
0x140006baf  jb      short loc_140006BC6
0x140006bb1  mov     rcx, [rcx+10h]
0x140006bb5  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x140006bbc  mov     edx, 0B0h
0x140006bc1  call    WPP_SF_
0x140006bc6  xor     r9d, r9d; SecurityDescriptorSize
0x140006bc9  mov     [rbp+SecurityDescriptor], 0
0x140006bd1  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140006bd5  lea     rcx, StringSecurityDescriptor; "D:PAI(A;OICI;FA;;;BA)(A;OICI;FA;;;NS)"
0x140006bdc  lea     edx, [r9+1]; StringSDRevision
0x140006be0  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x140006be7  nop     dword ptr [rax+rax+00h]
0x140006bec  test    eax, eax
0x140006bee  jnz     short loc_140006C3F
0x140006bf0  call    cs:__imp_GetLastError
0x140006bf7  nop     dword ptr [rax+rax+00h]
0x140006bfc  mov     ebx, eax
0x140006bfe  mov     rcx, cs:WPP_GLOBAL_Control
0x140006c05  cmp     rcx, r15
0x140006c08  jz      loc_140006D1F
0x140006c0e  test    byte ptr [rcx+1Ch], 4
0x140006c12  jz      loc_140006D1F
0x140006c18  cmp     byte ptr [rcx+19h], 2
0x140006c1c  jb      loc_140006D1F
0x140006c22  mov     rcx, [rcx+10h]
0x140006c26  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x140006c2d  mov     edx, 0B1h
0x140006c32  mov     r9d, eax
0x140006c35  call    WPP_SF_d
0x140006c3a  jmp     loc_140006D1F
0x140006c3f  mov     rax, [rbp+SecurityDescriptor]
0x140006c43  lea     r9, [rbp+var_20]; struct _SECURITY_ATTRIBUTES *
0x140006c47  mov     [rbp+var_20.lpSecurityDescriptor], rax
0x140006c4b  mov     r8d, 1; int
0x140006c51  lea     rax, [rbp+arg_0]
0x140006c55  mov     qword ptr [rbp+var_20.nLength], 18h
0x140006c5d  mov     rdx, rdi; unsigned __int16 *
0x140006c60  mov     [rsp+50h+var_30], rax; int *
0x140006c65  mov     qword ptr [rbp+var_20.bInheritHandle], 0
0x140006c6d  call    ?CreateArchiveFolder@CFaxArchiving@@AEAAKPEBGHPEAU_SECURITY_ATTRIBUTES@@PEAH@Z; CFaxArchiving::CreateArchiveFolder(ushort const *,int,_SECURITY_ATTRIBUTES *,int *)
0x140006c72  mov     ebx, eax
0x140006c74  test    eax, eax
0x140006c76  jz      short loc_140006C97
0x140006c78  mov     rcx, cs:WPP_GLOBAL_Control
0x140006c7f  cmp     rcx, r15
0x140006c82  jz      short loc_140006CE5
0x140006c84  test    byte ptr [rcx+1Ch], 4
0x140006c88  jz      short loc_140006CE5
0x140006c8a  cmp     byte ptr [rcx+19h], 2
0x140006c8e  jb      short loc_140006CE5
0x140006c90  mov     edx, 0B2h
0x140006c95  jmp     short loc_140006CD2
0x140006c97  lea     rax, [rbp+arg_10]
0x140006c9b  xor     r8d, r8d; int
0x140006c9e  lea     r9, [rbp+var_20]; struct _SECURITY_ATTRIBUTES *
0x140006ca2  mov     [rsp+50h+var_30], rax; int *
0x140006ca7  mov     rdx, rdi; unsigned __int16 *
0x140006caa  call    ?CreateArchiveFolder@CFaxArchiving@@AEAAKPEBGHPEAU_SECURITY_ATTRIBUTES@@PEAH@Z; CFaxArchiving::CreateArchiveFolder(ushort const *,int,_SECURITY_ATTRIBUTES *,int *)
0x140006caf  mov     ebx, eax
0x140006cb1  test    eax, eax
0x140006cb3  jz      short loc_140006D0A
0x140006cb5  mov     rcx, cs:WPP_GLOBAL_Control
0x140006cbc  cmp     rcx, r15
0x140006cbf  jz      short loc_140006CE5
0x140006cc1  test    byte ptr [rcx+1Ch], 4
0x140006cc5  jz      short loc_140006CE5
0x140006cc7  cmp     byte ptr [rcx+19h], 2
0x140006ccb  jb      short loc_140006CE5
0x140006ccd  mov     edx, 0B3h
0x140006cd2  mov     rcx, [rcx+10h]
0x140006cd6  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x140006cdd  mov     r9d, eax
0x140006ce0  call    WPP_SF_d
0x140006ce5  cmp     [rbp+arg_0], 0
0x140006ce9  jz      short loc_140006CF9
0x140006ceb  mov     r8d, 1; int
0x140006cf1  mov     rdx, rdi; unsigned __int16 *
0x140006cf4  call    ?RemoveArchiveFolder@CFaxArchiving@@AEAAKPEBGH@Z; CFaxArchiving::RemoveArchiveFolder(ushort const *,int)
0x140006cf9  cmp     [rbp+arg_10], 0
0x140006cfd  jz      short loc_140006D0A
0x140006cff  xor     r8d, r8d; int
0x140006d02  mov     rdx, rdi; unsigned __int16 *
0x140006d05  call    ?RemoveArchiveFolder@CFaxArchiving@@AEAAKPEBGH@Z; CFaxArchiving::RemoveArchiveFolder(ushort const *,int)
0x140006d0a  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x140006d0e  test    rcx, rcx
0x140006d11  jz      short loc_140006D1F
0x140006d13  call    cs:__imp_LocalFree
0x140006d1a  nop     dword ptr [rax+rax+00h]
0x140006d1f  mov     eax, ebx
0x140006d21  mov     rbx, [rsp+50h+arg_8]
0x140006d26  add     rsp, 50h
0x140006d2a  pop     r15
0x140006d2c  pop     rdi
0x140006d2d  pop     rbp
0x140006d2e  retn
```
