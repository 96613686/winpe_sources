# CPenProcess::OpenProcessMutexInSession(void)

- ea: `0x180002cd0`
- end: `0x18000316a`
- name: `?OpenProcessMutexInSession@CPenProcess@@AEAAPEAXXZ`
- size: `1178`
- prototype: `void *__fastcall(CPenProcess *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180015660`

## callees

- `0x180002cd0`
- `0x1800037d0`
- `0x18001bbe0`
- `0x18001c684`
- `0x18002b3a8`
- `0x18002b404`
- `0x18002b4cc`
- `0x18002e5f0`
- `0x180031010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180002e96`
- `ntdll!RtlInitUnicodeString` at `0x180002f05`
- `ntdll!RtlInitUnicodeString` at `0x180002e96`
- `ntdll!RtlInitUnicodeString` at `0x180002f05`
- `ntdll!NtClose` at `0x180002f66`
- `ntdll!NtClose` at `0x180002f66`
- `ntdll!NtOpenDirectoryObject` at `0x180002ece`
- `ntdll!NtOpenDirectoryObject` at `0x180002ece`
- `ntdll!NtOpenMutant` at `0x180002f3e`
- `ntdll!NtOpenMutant` at `0x180002f3e`

## string_xrefs

- `0x180002fff`: `PENSERVICE_CPenProcess::OpenProcessMutexInSession`
- `0x180003065`: `PENSERVICE_CPenProcess::OpenProcessMutexInSession`
- `0x18000308d`: `PENSERVICE_CPenProcess::OpenProcessMutexInSession`
- `0x1800030e4`: `PENSERVICE__OpenSessionDirectory`
- `0x18000311f`: `PENSERVICE__OpenSessionDirectory`
- `0x180002fd4`: `PENSERVICE_OpenMutexInSession`
- `0x18000302a`: `PENSERVICE_OpenMutexInSession`
- `0x1800030ae`: `PENSERVICE_OpenMutexInSession`
- `0x180003144`: `PENSERVICE_OpenMutexInSession`

## pseudocode

```c
void *__fastcall CPenProcess::OpenProcessMutexInSession(CPenProcess *this)
{
  const wchar_t *v2; // rdi
  __int64 v3; // rax
  wchar_t v4; // cx
  bool v5; // cf
  wchar_t v6; // cx
  int v7; // r14d
  __int64 v8; // rcx
  const wchar_t *v9; // rdx
  WCHAR *v10; // r8
  __int64 v11; // rbx
  WCHAR *v12; // rax
  int v13; // ebx
  __int64 v14; // rax
  unsigned int v15; // edi
  struct _GUID *v16; // r14
  NTSTATUS v17; // eax
  struct _GUID *v18; // rcx
  void *v19; // rbx
  NTSTATUS v20; // eax
  int v21; // r8d
  void *v22; // rbx
  int v24; // [rsp+28h] [rbp-D8h]
  void *MutantHandle; // [rsp+30h] [rbp-D0h] BYREF
  void *FileHandle; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING v28; // [rsp+50h] [rbp-B0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-A0h] BYREF
  struct _OBJECT_ATTRIBUTES v30; // [rsp+90h] [rbp-70h] BYREF
  WCHAR SourceString[264]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR v32[264]; // [rsp+2D0h] [rbp+1D0h] BYREF

  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      35,
      WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids,
      "PENSERVICE_CPenProcess::OpenProcessMutexInSession");
  v2 = L"Winlogon";
  v3 = -1;
  while ( 1 )
  {
    v4 = *((_WORD *)this + v3 + 280);
    v5 = v4 < aWinlogon[v3 + 1];
    if ( v4 != aWinlogon[v3 + 1] )
    {
LABEL_8:
      v7 = v5 ? -1 : 1;
      goto LABEL_17;
    }
    v3 += 2;
    if ( v3 == 9 )
      break;
    v6 = *((_WORD *)this + v3 + 279);
    v5 = v6 < aWinlogon[v3];
    if ( v6 != aWinlogon[v3] )
      goto LABEL_8;
  }
  v7 = 0;
LABEL_17:
  memset_0(v32, 0, 0x208u);
  v13 = *((_DWORD *)this + 8);
  v14 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 32LL))(*(_QWORD *)this);
  v24 = v13;
  v11 = 260;
  if ( v7 )
    v2 = L"Default";
  StringCchPrintfW(v32, 0x104u, L"%s%s%d", v14, v2, v24);
  v15 = *((_DWORD *)this + 8);
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
  {
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      12,
      WPP_5dcd8414c92c33ed143342dc983ec5b8_Traceguids,
      "PENSERVICE_OpenMutexInSession");
    v16 = WPP_GLOBAL_Control;
  }
  MutantHandle = 0;
  FileHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  memset_0(SourceString, 0, 0x208u);
  if ( v15 )
  {
    StringCchPrintfW(SourceString, 0x104u, L"\\Sessions\\%d\\BaseNamedObjects", v15);
    v16 = WPP_GLOBAL_Control;
  }
  else
  {
    v8 = 2147483646;
    v9 = L"\\BaseNamedObjects";
    v10 = SourceString;
    do
    {
      if ( !v8 )
        break;
      if ( !*v9 )
        break;
      *v10++ = *v9++;
      --v8;
      --v11;
    }
    while ( v11 );
    v12 = v10 - 1;
    if ( v11 )
      v12 = v10;
    *v12 = 0;
  }
  if ( v16 != (struct _GUID *)&WPP_GLOBAL_Control && (v16[1].Data4[4] & 0x10) != 0 )
    WPP_SF_sS(
      *(_QWORD *)&v16[1].Data1,
      10,
      (unsigned int)WPP_5dcd8414c92c33ed143342dc983ec5b8_Traceguids,
      (unsigned int)"PENSERVICE__OpenSessionDirectory",
      (__int64)SourceString);
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v17 = NtOpenDirectoryObject(&FileHandle, 4u, &ObjectAttributes);
  if ( v17 >= 0 )
    goto LABEL_28;
  FileHandle = 0;
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 4) != 0 )
  {
    WPP_SF_sd(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      11,
      (unsigned int)WPP_5dcd8414c92c33ed143342dc983ec5b8_Traceguids,
      (unsigned int)"PENSERVICE__OpenSessionDirectory",
      v17);
LABEL_28:
    v18 = WPP_GLOBAL_Control;
  }
  v19 = FileHandle;
  if ( FileHandle )
  {
    v28 = 0;
    RtlInitUnicodeString(&v28, v32);
    *(_QWORD *)&v30.Length = 48;
    v30.ObjectName = &v28;
    memset(&v30.Attributes, 0, 24);
    v30.RootDirectory = v19;
    v20 = NtOpenMutant(&MutantHandle, 0x100000u, &v30);
    if ( v20 < 0 )
    {
      if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 4) != 0 )
        WPP_SF_sSd(
          *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
          13,
          v21,
          (unsigned int)"PENSERVICE_OpenMutexInSession",
          (__int64)v32,
          v20);
      MutantHandle = 0;
    }
    NtClose(v19);
    v18 = WPP_GLOBAL_Control;
  }
  if ( !MutantHandle )
  {
    if ( v18 == (struct _GUID *)&WPP_GLOBAL_Control )
      goto LABEL_38;
    if ( (v18[1].Data4[4] & 4) != 0 )
    {
      WPP_SF_s(
        *(_QWORD *)&v18[1].Data1,
        14,
        WPP_5dcd8414c92c33ed143342dc983ec5b8_Traceguids,
        "PENSERVICE_OpenMutexInSession");
      v18 = WPP_GLOBAL_Control;
    }
  }
  if ( v18 != (struct _GUID *)&WPP_GLOBAL_Control && (v18[1].Data4[4] & 0x10) != 0 )
  {
    WPP_SF_s(
      *(_QWORD *)&v18[1].Data1,
      15,
      WPP_5dcd8414c92c33ed143342dc983ec5b8_Traceguids,
      "PENSERVICE_OpenMutexInSession");
    v18 = WPP_GLOBAL_Control;
  }
LABEL_38:
  v22 = MutantHandle;
  if ( !MutantHandle )
  {
    if ( v18 == (struct _GUID *)&WPP_GLOBAL_Control )
      return v22;
    if ( (v18[1].Data4[4] & 4) != 0 )
    {
      WPP_SF_s(
        *(_QWORD *)&v18[1].Data1,
        36,
        WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids,
        "PENSERVICE_CPenProcess::OpenProcessMutexInSession");
      v18 = WPP_GLOBAL_Control;
    }
  }
  if ( v18 != (struct _GUID *)&WPP_GLOBAL_Control && (v18[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&v18[1].Data1,
      37,
      WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids,
      "PENSERVICE_CPenProcess::OpenProcessMutexInSession");
  return v22;
}

```

## disassembly

```asm
0x180002cd0  mov     [rsp-8+arg_8], rbx
0x180002cd5  mov     [rsp-8+arg_10], rsi
0x180002cda  push    rbp
0x180002cdb  push    rdi
0x180002cdc  push    r12
0x180002cde  push    r14
0x180002ce0  push    r15
0x180002ce2  lea     rbp, [rsp-3F0h]
0x180002cea  sub     rsp, 4F0h
0x180002cf1  mov     rax, cs:__security_cookie
0x180002cf8  xor     rax, rsp
0x180002cfb  mov     [rbp+410h+var_30], rax
0x180002d02  mov     r15, rcx
0x180002d05  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d0c  lea     r12, WPP_GLOBAL_Control
0x180002d13  cmp     rcx, r12
0x180002d16  jz      short loc_180002D22
0x180002d18  test    byte ptr [rcx+1Ch], 10h
0x180002d1c  jnz     loc_180003089
0x180002d22  lea     rdi, aWinlogon; "Winlogon"
0x180002d29  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180002d30  movzx   ecx, word ptr [r15+rax*2+230h]
0x180002d39  cmp     cx, [rdi+rax*2+2]
0x180002d3e  jnz     short loc_180002D59
0x180002d40  add     rax, 2
0x180002d44  cmp     rax, 9
0x180002d48  jz      short loc_180002DA9
0x180002d4a  movzx   ecx, word ptr [r15+rax*2+22Eh]
0x180002d53  cmp     cx, [rdi+rax*2]
0x180002d57  jz      short loc_180002D30
0x180002d59  sbb     r14d, r14d
0x180002d5c  or      r14d, 1
0x180002d60  xor     esi, esi
0x180002d62  jmp     short loc_180002DAE
0x180002d64  mov     ecx, 7FFFFFFEh
0x180002d69  lea     rdx, aBasenamedobjec; "\\BaseNamedObjects"
0x180002d70  lea     r8, [rbp+410h+SourceString]
0x180002d74  test    rcx, rcx
0x180002d77  jz      short loc_180002D96
0x180002d79  movzx   eax, word ptr [rdx]
0x180002d7c  test    ax, ax
0x180002d7f  jz      short loc_180002D96
0x180002d81  mov     [r8], ax
0x180002d85  add     rdx, 2
0x180002d89  add     r8, 2
0x180002d8d  dec     rcx
0x180002d90  sub     rbx, 1
0x180002d94  jnz     short loc_180002D74
0x180002d96  test    rbx, rbx
0x180002d99  lea     rax, [r8-2]
0x180002d9d  cmovnz  rax, r8
0x180002da1  mov     [rax], si
0x180002da4  jmp     loc_180002E75
0x180002da9  xor     esi, esi
0x180002dab  mov     r14d, esi
0x180002dae  xor     edx, edx; Val
0x180002db0  lea     rcx, [rbp+410h+var_240]; void *
0x180002db7  mov     r8d, 208h; Size
0x180002dbd  call    memset_0
0x180002dc2  mov     rcx, [r15]
0x180002dc5  mov     ebx, [r15+20h]
0x180002dc9  mov     rax, [rcx]
0x180002dcc  mov     rax, [rax+20h]
0x180002dd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dd5  test    r14d, r14d
0x180002dd8  mov     [rsp+510h+var_4E8], ebx
0x180002ddc  lea     rcx, aDefault; "Default"
0x180002de3  mov     ebx, 104h
0x180002de8  cmovnz  rdi, rcx
0x180002dec  lea     r8, aSSD; "%s%s%d"
0x180002df3  lea     rcx, [rbp+410h+var_240]; unsigned __int16 *
0x180002dfa  mov     [rsp+510h+var_4F0], rdi
0x180002dff  mov     r9, rax
0x180002e02  mov     edx, ebx; unsigned __int64
0x180002e04  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002e09  mov     edi, [r15+20h]
0x180002e0d  mov     r14, cs:WPP_GLOBAL_Control
0x180002e14  cmp     r14, r12
0x180002e17  jz      short loc_180002E24
0x180002e19  test    byte ptr [r14+1Ch], 10h
0x180002e1e  jnz     loc_1800030AA
0x180002e24  xorps   xmm0, xmm0
0x180002e27  mov     [rsp+510h+MutantHandle], rsi
0x180002e2c  xor     edx, edx; Val
0x180002e2e  mov     [rsp+510h+FileHandle], rsi
0x180002e33  mov     r8d, 208h; Size
0x180002e39  lea     rcx, [rbp+410h+SourceString]; void *
0x180002e3d  movups  xmmword ptr [rsp+510h+ObjectAttributes.Length], xmm0
0x180002e42  movups  xmmword ptr [rsp+510h+ObjectAttributes.ObjectName], xmm0
0x180002e47  movups  xmmword ptr [rbp+410h+ObjectAttributes.SecurityDescriptor], xmm0
0x180002e4b  call    memset_0
0x180002e50  test    edi, edi
0x180002e52  jz      loc_180002D64
0x180002e58  mov     r9d, edi
0x180002e5b  lea     r8, aSessionsDBasen; "\\Sessions\\%d\\BaseNamedObjects"
0x180002e62  mov     rdx, rbx; unsigned __int64
0x180002e65  lea     rcx, [rbp+410h+SourceString]; unsigned __int16 *
0x180002e69  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002e6e  mov     r14, cs:WPP_GLOBAL_Control
0x180002e75  cmp     r14, r12
0x180002e78  jz      short loc_180002E85
0x180002e7a  test    byte ptr [r14+1Ch], 10h
0x180002e7f  jnz     loc_1800030D2
0x180002e85  xorps   xmm0, xmm0
0x180002e88  lea     rdx, [rbp+410h+SourceString]; SourceString
0x180002e8c  lea     rcx, [rsp+510h+DestinationString]; DestinationString
0x180002e91  movups  xmmword ptr [rsp+510h+DestinationString.Length], xmm0
0x180002e96  call    cs:__imp_RtlInitUnicodeString
0x180002e9c  lea     rax, [rsp+510h+DestinationString]
0x180002ea1  mov     [rsp+510h+ObjectAttributes.Length], 30h ; '0'
0x180002ea9  xorps   xmm0, xmm0
0x180002eac  mov     [rsp+510h+ObjectAttributes.ObjectName], rax
0x180002eb1  lea     r8, [rsp+510h+ObjectAttributes]; ObjectAttributes
0x180002eb6  mov     [rsp+510h+ObjectAttributes.RootDirectory], rsi
0x180002ebb  mov     edx, 4; DesiredAccess
0x180002ec0  mov     [rsp+510h+ObjectAttributes.Attributes], esi
0x180002ec4  lea     rcx, [rsp+510h+FileHandle]; FileHandle
0x180002ec9  movdqu  xmmword ptr [rbp+410h+ObjectAttributes.SecurityDescriptor], xmm0
0x180002ece  call    cs:__imp_NtOpenDirectoryObject
0x180002ed4  test    eax, eax
0x180002ed6  js      loc_1800030FC
0x180002edc  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ee3  mov     rbx, [rsp+510h+FileHandle]
0x180002ee8  test    rbx, rbx
0x180002eeb  jz      loc_180002F73
0x180002ef1  xorps   xmm0, xmm0
0x180002ef4  lea     rdx, [rbp+410h+var_240]; SourceString
0x180002efb  lea     rcx, [rsp+510h+var_4C0]; DestinationString
0x180002f00  movups  xmmword ptr [rsp+510h+var_4C0.Length], xmm0
0x180002f05  call    cs:__imp_RtlInitUnicodeString
0x180002f0b  lea     rax, [rsp+510h+var_4C0]
0x180002f10  mov     qword ptr [rbp+410h+var_480.Length], 30h ; '0'
0x180002f18  xorps   xmm0, xmm0
0x180002f1b  mov     [rbp+410h+var_480.ObjectName], rax
0x180002f1f  lea     r8, [rbp+410h+var_480]; ObjectAttributes
0x180002f23  mov     qword ptr [rbp+410h+var_480.Attributes], 0
0x180002f2b  mov     edx, 100000h; DesiredAccess
0x180002f30  mov     [rbp+410h+var_480.RootDirectory], rbx
0x180002f34  lea     rcx, [rsp+510h+MutantHandle]; MutantHandle
0x180002f39  movdqu  xmmword ptr [rbp+410h+var_480.SecurityDescriptor], xmm0
0x180002f3e  call    cs:__imp_NtOpenMutant
0x180002f44  test    eax, eax
0x180002f46  jns     short loc_180002F63
0x180002f48  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f4f  cmp     rcx, r12
0x180002f52  jz      short loc_180002F5E
0x180002f54  test    byte ptr [rcx+1Ch], 4
0x180002f58  jnz     loc_180003140
0x180002f5e  mov     [rsp+510h+MutantHandle], rsi
0x180002f63  mov     rcx, rbx; Handle
0x180002f66  call    cs:__imp_NtClose
0x180002f6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f73  cmp     [rsp+510h+MutantHandle], 0
0x180002f79  jz      short loc_180002FC5
0x180002f7b  cmp     rcx, r12
0x180002f7e  jnz     loc_18000301C
0x180002f84  mov     rbx, [rsp+510h+MutantHandle]
0x180002f89  test    rbx, rbx
0x180002f8c  jz      loc_18000304E
0x180002f92  cmp     rcx, r12
0x180002f95  jnz     short loc_180002FF5
0x180002f97  mov     rax, rbx
0x180002f9a  mov     rcx, [rbp+410h+var_30]
0x180002fa1  xor     rcx, rsp; StackCookie
0x180002fa4  call    __security_check_cookie
0x180002fa9  lea     r11, [rsp+510h+var_20]
0x180002fb1  mov     rbx, [r11+38h]
0x180002fb5  mov     rsi, [r11+40h]
0x180002fb9  mov     rsp, r11
0x180002fbc  pop     r15
0x180002fbe  pop     r14
0x180002fc0  pop     r12
0x180002fc2  pop     rdi
0x180002fc3  pop     rbp
0x180002fc4  retn
0x180002fc5  cmp     rcx, r12
0x180002fc8  jz      short loc_180002F84
0x180002fca  test    byte ptr [rcx+1Ch], 4
0x180002fce  jz      short loc_180002F7B
0x180002fd0  mov     rcx, [rcx+10h]
0x180002fd4  lea     r9, aPenserviceOpen_1; "PENSERVICE_OpenMutexInSession"
0x180002fdb  mov     edx, 0Eh
0x180002fe0  lea     r8, WPP_5dcd8414c92c33ed143342dc983ec5b8_Traceguids
0x180002fe7  call    WPP_SF_s
0x180002fec  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ff3  jmp     short loc_180002F7B
0x180002ff5  test    byte ptr [rcx+1Ch], 10h
0x180002ff9  jz      short loc_180002F97
0x180002ffb  mov     rcx, [rcx+10h]
0x180002fff  lea     r9, aPenserviceCpen_3; "PENSERVICE_CPenProcess::OpenProcessMute"...
0x180003006  mov     edx, 25h ; '%'
0x18000300b  lea     r8, WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids
0x180003012  call    WPP_SF_s
0x180003017  jmp     loc_180002F97
0x18000301c  test    byte ptr [rcx+1Ch], 10h
0x180003020  jz      loc_180002F84
0x180003026  mov     rcx, [rcx+10h]
0x18000302a  lea     r9, aPenserviceOpen_1; "PENSERVICE_OpenMutexInSession"
0x180003031  mov     edx, 0Fh
0x180003036  lea     r8, WPP_5dcd8414c92c33ed143342dc983ec5b8_Traceguids
0x18000303d  call    WPP_SF_s
0x180003042  mov     rcx, cs:WPP_GLOBAL_Control
0x180003049  jmp     loc_180002F84
0x18000304e  cmp     rcx, r12
0x180003051  jz      loc_180002F97
0x180003057  test    byte ptr [rcx+1Ch], 4
0x18000305b  jz      loc_180002F92
0x180003061  mov     rcx, [rcx+10h]
0x180003065  lea     r9, aPenserviceCpen_3; "PENSERVICE_CPenProcess::OpenProcessMute"...
0x18000306c  mov     edx, 24h ; '$'
0x180003071  lea     r8, WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids
0x180003078  call    WPP_SF_s
0x18000307d  mov     rcx, cs:WPP_GLOBAL_Control
0x180003084  jmp     loc_180002F92
0x180003089  mov     rcx, [rcx+10h]
0x18000308d  lea     r9, aPenserviceCpen_3; "PENSERVICE_CPenProcess::OpenProcessMute"...
0x180003094  mov     edx, 23h ; '#'
0x180003099  lea     r8, WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids
0x1800030a0  call    WPP_SF_s
0x1800030a5  jmp     loc_180002D22
0x1800030aa  mov     rcx, [r14+10h]
0x1800030ae  lea     r9, aPenserviceOpen_1; "PENSERVICE_OpenMutexInSession"
0x1800030b5  mov     edx, 0Ch
0x1800030ba  lea     r8, WPP_5dcd8414c92c33ed143342dc983ec5b8_Traceguids
0x1800030c1  call    WPP_SF_s
0x1800030c6  mov     r14, cs:WPP_GLOBAL_Control
0x1800030cd  jmp     loc_180002E24
0x1800030d2  mov     rcx, [r14+10h]
0x1800030d6  lea     rax, [rbp+410h+SourceString]
0x1800030da  mov     edx, 0Ah
0x1800030df  mov     [rsp+510h+var_4F0], rax
0x1800030e4  lea     r9, aPenserviceOpen; "PENSERVICE__OpenSessionDirectory"
0x1800030eb  lea     r8, WPP_5dcd8414c92c33ed143342dc983ec5b8_Traceguids
0x1800030f2  call    WPP_SF_sS
0x1800030f7  jmp     loc_180002E85
0x1800030fc  mov     [rsp+510h+FileHandle], rsi
0x180003101  mov     rcx, cs:WPP_GLOBAL_Control
0x180003108  cmp     rcx, r12
0x18000310b  jz      loc_180002EE3
0x180003111  test    byte ptr [rcx+1Ch], 4
0x180003115  jz      loc_180002EE3
0x18000311b  mov     rcx, [rcx+10h]
0x18000311f  lea     r9, aPenserviceOpen; "PENSERVICE__OpenSessionDirectory"
0x180003126  mov     edx, 0Bh
0x18000312b  mov     dword ptr [rsp+510h+var_4F0], eax
0x18000312f  lea     r8, WPP_5dcd8414c92c33ed143342dc983ec5b8_Traceguids
0x180003136  call    WPP_SF_sd
0x18000313b  jmp     loc_180002EDC
0x180003140  mov     rcx, [rcx+10h]
0x180003144  lea     r9, aPenserviceOpen_1; "PENSERVICE_OpenMutexInSession"
0x18000314b  mov     [rsp+510h+var_4E8], eax
0x18000314f  mov     edx, 0Dh
0x180003154  lea     rax, [rbp+410h+var_240]
0x18000315b  mov     [rsp+510h+var_4F0], rax
0x180003160  call    WPP_SF_sSd
0x180003165  jmp     loc_180002F5E
```
