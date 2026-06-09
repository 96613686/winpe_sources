# CFaxArchiving::CreateArchiveStructure(ushort const *)

- ea: `0x140006954`
- end: `0x140006b05`
- name: `?CreateArchiveStructure@CFaxArchiving@@QEAAKPEBG@Z`
- size: `433`
- prototype: `__int64 __fastcall(CFaxArchiving *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140051d80`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x140006760`
- `0x140006954`
- `0x14000bde0`

## import_xrefs

- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400069c8`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400069c8`
- `KERNEL32!GetLastError` at `0x1400069d2`
- `KERNEL32!GetLastError` at `0x1400069d2`
- `KERNEL32!LocalFree` at `0x140006aef`
- `KERNEL32!LocalFree` at `0x140006aef`

## pseudocode

```c
__int64 __fastcall CFaxArchiving::CreateArchiveStructure(CFaxArchiving *this, const unsigned __int16 *a2)
{
  CFaxArchiving *v3; // rcx
  DWORD LastError; // eax
  DWORD v5; // ebx
  unsigned int v6; // eax
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
0x140006954  mov     [rsp-18h+arg_8], rbx
0x140006959  mov     qword ptr [rsp-18h+arg_0], rcx
0x14000695e  push    rbp
0x14000695f  push    rdi
0x140006960  push    r15
0x140006962  mov     rbp, rsp
0x140006965  sub     rsp, 50h
0x140006969  mov     rdi, rdx
0x14000696c  mov     [rbp+arg_0], 0
0x140006973  mov     [rbp+arg_10], 0
0x14000697a  mov     rcx, cs:WPP_GLOBAL_Control
0x140006981  lea     r15, WPP_GLOBAL_Control
0x140006988  cmp     rcx, r15
0x14000698b  jz      short loc_1400069AE
0x14000698d  test    byte ptr [rcx+1Ch], 4
0x140006991  jz      short loc_1400069AE
0x140006993  cmp     byte ptr [rcx+19h], 5
0x140006997  jb      short loc_1400069AE
0x140006999  mov     rcx, [rcx+10h]
0x14000699d  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x1400069a4  mov     edx, 0B0h
0x1400069a9  call    WPP_SF_
0x1400069ae  xor     r9d, r9d; SecurityDescriptorSize
0x1400069b1  mov     [rbp+SecurityDescriptor], 0
0x1400069b9  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1400069bd  lea     rcx, StringSecurityDescriptor; "D:PAI(A;OICI;FA;;;BA)(A;OICI;FA;;;NS)"
0x1400069c4  lea     edx, [r9+1]; StringSDRevision
0x1400069c8  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1400069ce  test    eax, eax
0x1400069d0  jnz     short loc_140006A1B
0x1400069d2  call    cs:__imp_GetLastError
0x1400069d8  mov     ebx, eax
0x1400069da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400069e1  cmp     rcx, r15
0x1400069e4  jz      loc_140006AF5
0x1400069ea  test    byte ptr [rcx+1Ch], 4
0x1400069ee  jz      loc_140006AF5
0x1400069f4  cmp     byte ptr [rcx+19h], 2
0x1400069f8  jb      loc_140006AF5
0x1400069fe  mov     rcx, [rcx+10h]
0x140006a02  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x140006a09  mov     edx, 0B1h
0x140006a0e  mov     r9d, eax
0x140006a11  call    WPP_SF_d
0x140006a16  jmp     loc_140006AF5
0x140006a1b  mov     rax, [rbp+SecurityDescriptor]
0x140006a1f  lea     r9, [rbp+var_20]; struct _SECURITY_ATTRIBUTES *
0x140006a23  mov     [rbp+var_20.lpSecurityDescriptor], rax
0x140006a27  mov     r8d, 1; int
0x140006a2d  lea     rax, [rbp+arg_0]
0x140006a31  mov     qword ptr [rbp+var_20.nLength], 18h
0x140006a39  mov     rdx, rdi; unsigned __int16 *
0x140006a3c  mov     [rsp+50h+var_30], rax; int *
0x140006a41  mov     qword ptr [rbp+var_20.bInheritHandle], 0
0x140006a49  call    ?CreateArchiveFolder@CFaxArchiving@@AEAAKPEBGHPEAU_SECURITY_ATTRIBUTES@@PEAH@Z; CFaxArchiving::CreateArchiveFolder(ushort const *,int,_SECURITY_ATTRIBUTES *,int *)
0x140006a4e  mov     ebx, eax
0x140006a50  test    eax, eax
0x140006a52  jz      short loc_140006A73
0x140006a54  mov     rcx, cs:WPP_GLOBAL_Control
0x140006a5b  cmp     rcx, r15
0x140006a5e  jz      short loc_140006AC1
0x140006a60  test    byte ptr [rcx+1Ch], 4
0x140006a64  jz      short loc_140006AC1
0x140006a66  cmp     byte ptr [rcx+19h], 2
0x140006a6a  jb      short loc_140006AC1
0x140006a6c  mov     edx, 0B2h
0x140006a71  jmp     short loc_140006AAE
0x140006a73  lea     rax, [rbp+arg_10]
0x140006a77  xor     r8d, r8d; int
0x140006a7a  lea     r9, [rbp+var_20]; struct _SECURITY_ATTRIBUTES *
0x140006a7e  mov     [rsp+50h+var_30], rax; int *
0x140006a83  mov     rdx, rdi; unsigned __int16 *
0x140006a86  call    ?CreateArchiveFolder@CFaxArchiving@@AEAAKPEBGHPEAU_SECURITY_ATTRIBUTES@@PEAH@Z; CFaxArchiving::CreateArchiveFolder(ushort const *,int,_SECURITY_ATTRIBUTES *,int *)
0x140006a8b  mov     ebx, eax
0x140006a8d  test    eax, eax
0x140006a8f  jz      short loc_140006AE6
0x140006a91  mov     rcx, cs:WPP_GLOBAL_Control
0x140006a98  cmp     rcx, r15
0x140006a9b  jz      short loc_140006AC1
0x140006a9d  test    byte ptr [rcx+1Ch], 4
0x140006aa1  jz      short loc_140006AC1
0x140006aa3  cmp     byte ptr [rcx+19h], 2
0x140006aa7  jb      short loc_140006AC1
0x140006aa9  mov     edx, 0B3h
0x140006aae  mov     rcx, [rcx+10h]
0x140006ab2  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x140006ab9  mov     r9d, eax
0x140006abc  call    WPP_SF_d
0x140006ac1  cmp     [rbp+arg_0], 0
0x140006ac5  jz      short loc_140006AD5
0x140006ac7  mov     r8d, 1; int
0x140006acd  mov     rdx, rdi; unsigned __int16 *
0x140006ad0  call    ?RemoveArchiveFolder@CFaxArchiving@@AEAAKPEBGH@Z; CFaxArchiving::RemoveArchiveFolder(ushort const *,int)
0x140006ad5  cmp     [rbp+arg_10], 0
0x140006ad9  jz      short loc_140006AE6
0x140006adb  xor     r8d, r8d; int
0x140006ade  mov     rdx, rdi; unsigned __int16 *
0x140006ae1  call    ?RemoveArchiveFolder@CFaxArchiving@@AEAAKPEBGH@Z; CFaxArchiving::RemoveArchiveFolder(ushort const *,int)
0x140006ae6  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x140006aea  test    rcx, rcx
0x140006aed  jz      short loc_140006AF5
0x140006aef  call    cs:__imp_LocalFree
0x140006af5  mov     eax, ebx
0x140006af7  mov     rbx, [rsp+50h+arg_8]
0x140006afc  add     rsp, 50h
0x140006b00  pop     r15
0x140006b02  pop     rdi
0x140006b03  pop     rbp
0x140006b04  retn
```
