# FveCreatePersistentRequestsFolder(ushort const *)

- ea: `0x180029df0`
- end: `0x180029f80`
- name: `?FveCreatePersistentRequestsFolder@@YAJPEBG@Z`
- size: `400`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path, loader_planting`

## callers

- `0x1800053a0`
- `0x180061f40`

## callees

- `0x180009f30`
- `0x180009f60`
- `0x18000b020`
- `0x180029df0`
- `0x180034070`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180029e5a`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180029e5a`
- `ntdll!RtlCreateSystemVolumeInformationFolder` at `0x180029ea2`
- `ntdll!RtlCreateSystemVolumeInformationFolder` at `0x180029ea2`
- `ntdll!RtlFreeUnicodeString` at `0x180029f51`
- `ntdll!RtlFreeUnicodeString` at `0x180029f51`
- `ntdll!RtlNtStatusToDosError` at `0x180029e68`
- `ntdll!RtlNtStatusToDosError` at `0x180029eb0`
- `ntdll!RtlNtStatusToDosError` at `0x180029e68`
- `ntdll!RtlNtStatusToDosError` at `0x180029eb0`

## pseudocode

```c
__int64 __fastcall FveCreatePersistentRequestsFolder(const unsigned __int16 *a1)
{
  unsigned int v2; // edi
  NTSTATUS v3; // eax
  signed int v4; // eax
  bool v5; // sf
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  NTSTATUS v8; // eax
  bool v9; // sf
  unsigned int SVIRequestFolder; // eax
  int v11; // ebx
  UNICODE_STRING VolumeRootPath; // [rsp+20h] [rbp-38h] BYREF

  VolumeRootPath = 0;
  v2 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 150, &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids);
  v3 = ((__int64 (__fastcall *)(const unsigned __int16 *, UNICODE_STRING *, _QWORD, _QWORD))RtlDosPathNameToNtPathName_U_WithStatus)(
         a1,
         &VolumeRootPath,
         0,
         0);
  v4 = RtlNtStatusToDosError(v3);
  v5 = v4 < 0;
  if ( v4 > 0 )
  {
    v4 = (unsigned __int16)v4 | 0x80070000;
    v5 = v4 < 0;
  }
  if ( v5 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v7 = 151;
LABEL_16:
      WPP_SF_d(v6[2], v7, &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids, (unsigned int)v4);
      goto LABEL_17;
    }
  }
  else
  {
    v8 = RtlCreateSystemVolumeInformationFolder(&VolumeRootPath);
    v4 = RtlNtStatusToDosError(v8);
    v9 = v4 < 0;
    if ( v4 > 0 )
    {
      v4 = (unsigned __int16)v4 | 0x80070000;
      v9 = v4 < 0;
    }
    if ( v9 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v7 = 152;
        goto LABEL_16;
      }
    }
  }
  do
  {
LABEL_17:
    SVIRequestFolder = FvePersistentRequest::CreateSVIRequestFolder(a1, *((_DWORD *)&g_persistentRequestsMap + 4 * v2));
    v11 = SVIRequestFolder;
    if ( SVIRequestFolder )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          153,
          &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids,
          SVIRequestFolder);
      if ( v11 < 0 )
        break;
    }
    ++v2;
  }
  while ( v2 < 4 );
  RtlFreeUnicodeString(&VolumeRootPath);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180029df0  mov     [rsp+arg_8], rbx
0x180029df5  mov     [rsp+arg_10], rbp
0x180029dfa  push    rsi
0x180029dfb  push    rdi
0x180029dfc  push    r14
0x180029dfe  sub     rsp, 40h
0x180029e02  mov     rax, cs:__security_cookie
0x180029e09  xor     rax, rsp
0x180029e0c  mov     [rsp+58h+var_28], rax
0x180029e11  xorps   xmm0, xmm0
0x180029e14  mov     rsi, rcx
0x180029e17  movups  xmmword ptr [rsp+58h+VolumeRootPath.Length], xmm0
0x180029e1c  xor     edi, edi
0x180029e1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180029e25  lea     rbp, WPP_GLOBAL_Control
0x180029e2c  cmp     rcx, rbp
0x180029e2f  jz      short loc_180029E4C
0x180029e31  test    byte ptr [rcx+1Ch], 20h
0x180029e35  jz      short loc_180029E4C
0x180029e37  mov     rcx, [rcx+10h]
0x180029e3b  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x180029e42  mov     edx, 96h
0x180029e47  call    WPP_SF_
0x180029e4c  xor     r9d, r9d
0x180029e4f  lea     rdx, [rsp+58h+VolumeRootPath]
0x180029e54  xor     r8d, r8d
0x180029e57  mov     rcx, rsi
0x180029e5a  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x180029e61  nop     dword ptr [rax+rax+00h]
0x180029e66  mov     ecx, eax; Status
0x180029e68  call    cs:__imp_RtlNtStatusToDosError
0x180029e6f  nop     dword ptr [rax+rax+00h]
0x180029e74  test    eax, eax
0x180029e76  jle     short loc_180029E82
0x180029e78  movzx   eax, ax
0x180029e7b  or      eax, 80070000h
0x180029e80  test    eax, eax
0x180029e82  jns     short loc_180029E9D
0x180029e84  mov     rcx, cs:WPP_GLOBAL_Control
0x180029e8b  cmp     rcx, rbp
0x180029e8e  jz      short loc_180029EF6
0x180029e90  test    byte ptr [rcx+1Ch], 2
0x180029e94  jz      short loc_180029EF6
0x180029e96  mov     edx, 97h
0x180029e9b  jmp     short loc_180029EE3
0x180029e9d  lea     rcx, [rsp+58h+VolumeRootPath]; VolumeRootPath
0x180029ea2  call    cs:__imp_RtlCreateSystemVolumeInformationFolder
0x180029ea9  nop     dword ptr [rax+rax+00h]
0x180029eae  mov     ecx, eax; Status
0x180029eb0  call    cs:__imp_RtlNtStatusToDosError
0x180029eb7  nop     dword ptr [rax+rax+00h]
0x180029ebc  test    eax, eax
0x180029ebe  jle     short loc_180029ECA
0x180029ec0  movzx   eax, ax
0x180029ec3  or      eax, 80070000h
0x180029ec8  test    eax, eax
0x180029eca  jns     short loc_180029EF6
0x180029ecc  mov     rcx, cs:WPP_GLOBAL_Control
0x180029ed3  cmp     rcx, rbp
0x180029ed6  jz      short loc_180029EF6
0x180029ed8  test    byte ptr [rcx+1Ch], 2
0x180029edc  jz      short loc_180029EF6
0x180029ede  mov     edx, 98h
0x180029ee3  mov     rcx, [rcx+10h]
0x180029ee7  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x180029eee  mov     r9d, eax
0x180029ef1  call    WPP_SF_d
0x180029ef6  lea     r14, ?g_persistentRequestsMap@@3PAU_FVE_PERSISTENT_REQUEST_CONFIG@@A; _FVE_PERSISTENT_REQUEST_CONFIG near * g_persistentRequestsMap
0x180029efd  nop     dword ptr [rax]
0x180029f00  mov     edx, edi
0x180029f02  mov     rcx, rsi
0x180029f05  add     rdx, rdx
0x180029f08  mov     edx, [r14+rdx*8]
0x180029f0c  call    ?CreateSVIRequestFolder@FvePersistentRequest@@SAJPEBGW4_FVE_REQUEST_TYPE@@@Z; FvePersistentRequest::CreateSVIRequestFolder(ushort const *,_FVE_REQUEST_TYPE)
0x180029f11  mov     ebx, eax
0x180029f13  test    eax, eax
0x180029f15  jz      short loc_180029F45
0x180029f17  mov     rcx, cs:WPP_GLOBAL_Control
0x180029f1e  cmp     rcx, rbp
0x180029f21  jz      short loc_180029F41
0x180029f23  test    byte ptr [rcx+1Ch], 40h
0x180029f27  jz      short loc_180029F41
0x180029f29  mov     rcx, [rcx+10h]
0x180029f2d  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x180029f34  mov     edx, 99h
0x180029f39  mov     r9d, eax
0x180029f3c  call    WPP_SF_d
0x180029f41  test    ebx, ebx
0x180029f43  js      short loc_180029F4C
0x180029f45  inc     edi
0x180029f47  cmp     edi, 4
0x180029f4a  jb      short loc_180029F00
0x180029f4c  lea     rcx, [rsp+58h+VolumeRootPath]; UnicodeString
0x180029f51  call    cs:__imp_RtlFreeUnicodeString
0x180029f58  nop     dword ptr [rax+rax+00h]
0x180029f5d  mov     eax, ebx
0x180029f5f  mov     rcx, [rsp+58h+var_28]
0x180029f64  xor     rcx, rsp; StackCookie
0x180029f67  call    __security_check_cookie
0x180029f6c  mov     rbx, [rsp+58h+arg_8]
0x180029f71  mov     rbp, [rsp+58h+arg_10]
0x180029f76  add     rsp, 40h
0x180029f7a  pop     r14
0x180029f7c  pop     rdi
0x180029f7d  pop     rsi
0x180029f7e  retn
```
