# CEventNotificationService::EnableProjectToAll(ushort *)

- ea: `0x140018e10`
- end: `0x1400190ef`
- name: `?EnableProjectToAll@CEventNotificationService@@UEAAJPEAG@Z`
- size: `735`
- prototype: `__int64 __fastcall(CEventNotificationService *this, BYTE *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x1400016b8`
- `0x140018e10`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14006379c`
- `0x14006c590`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1400190cf`
- `ADVAPI32!RegCloseKey` at `0x1400190cf`
- `ADVAPI32!RegDeleteValueW` at `0x140019019`
- `ADVAPI32!RegDeleteValueW` at `0x140019019`
- `ADVAPI32!RegCreateKeyExW` at `0x140018e83`
- `ADVAPI32!RegCreateKeyExW` at `0x140018e83`
- `ADVAPI32!RegSetValueExW` at `0x140018f47`
- `ADVAPI32!RegSetValueExW` at `0x140018f47`
- `KERNEL32!IsDebuggerPresent` at `0x140018fb4`
- `KERNEL32!IsDebuggerPresent` at `0x140019077`
- `KERNEL32!IsDebuggerPresent` at `0x140018fb4`
- `KERNEL32!IsDebuggerPresent` at `0x140019077`

## string_xrefs

- `0x140018f7b`: `CEventNotificationService::EnableProjectToAll`
- `0x14001904c`: `CEventNotificationService::EnableProjectToAll`

## pseudocode

```c
__int64 __fastcall CEventNotificationService::EnableProjectToAll(CEventNotificationService *this, BYTE *a2)
{
  BYTE *v3; // r14
  int v4; // ebx
  LSTATUS v5; // eax
  unsigned int v6; // r13d
  int v7; // eax
  __int64 v8; // rdx
  BYTE *v9; // rax
  int v10; // edi
  LSTATUS v11; // eax
  LSTATUS v12; // eax
  LPSECURITY_ATTRIBUTES lpSecurityAttributes; // [rsp+30h] [rbp-58h]
  PHKEY phkResult; // [rsp+38h] [rbp-50h]
  HKEY hKey; // [rsp+A0h] [rbp+18h] BYREF
  BYTE *lpData; // [rsp+A8h] [rbp+20h] BYREF

  lpData = 0;
  v3 = 0;
  hKey = 0;
  v4 = CUserManagement::s_VerifyAccessLevelEx(3u, 0);
  if ( v4 >= 0 )
  {
    v5 = RegCreateKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows Multipoint Server\\Orchestration",
           0,
           0,
           0,
           0x20006u,
           0,
           &hKey,
           0);
    if ( v5 )
    {
      if ( v5 > 0 )
        v4 = (unsigned __int16)v5 | 0x80070000;
      else
        v4 = v5;
      v6 = 4272;
LABEL_31:
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        v6,
        L"CEventNotificationService::EnableProjectToAll",
        L"CBRAEx",
        L"lr == 0L",
        v4);
      if ( IsDebuggerPresent() )
      {
        LODWORD(phkResult) = v4;
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
          v6,
          L"CEventNotificationService::EnableProjectToAll",
          L"CBRAEx",
          L"lr == 0L",
          phkResult);
      }
      else
      {
        LODWORD(lpSecurityAttributes) = v4;
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
          v6,
          L"CEventNotificationService::EnableProjectToAll",
          L"CBRAEx",
          L"lr == 0L",
          lpSecurityAttributes);
      }
      goto LABEL_34;
    }
    if ( !a2 || !*(_WORD *)a2 )
    {
      v12 = RegDeleteValueW(hKey, L"ProjectAllInvitation");
      if ( (v12 & 0xFFFFFFFD) == 0 )
        goto LABEL_34;
      if ( v12 > 0 )
        v4 = (unsigned __int16)v12 | 0x80070000;
      else
        v4 = v12;
      v6 = 4293;
      goto LABEL_31;
    }
    v7 = WmsEncrypt(a2, (unsigned __int16 **)&lpData);
    v3 = lpData;
    v4 = v7;
    if ( v7 < 0 )
      goto LABEL_34;
    if ( lpData )
    {
      v8 = 0x7FFFFFFF;
      v9 = lpData;
      do
      {
        if ( !*(_WORD *)v9 )
          break;
        v9 += 2;
        --v8;
      }
      while ( v8 );
      v10 = v8 == 0 ? 0x80070057 : 0;
      if ( v8 )
      {
        v11 = RegSetValueExW(hKey, L"ProjectAllInvitation", 0, 1u, lpData, v8 != 0 ? -2 - 2 * v8 + 2 : 2);
        v4 = v11;
        if ( !v11 )
        {
          v4 = v10;
          goto LABEL_34;
        }
        if ( v11 > 0 )
          v4 = (unsigned __int16)v11 | 0x80070000;
        v6 = 4285;
        goto LABEL_31;
      }
      v4 = -2147024809;
    }
    else
    {
      v4 = -2147024809;
      v10 = -2147024809;
    }
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      0x10B8u,
      L"CEventNotificationService::EnableProjectToAll",
      L"CHRA",
      L"hr",
      v10);
    if ( IsDebuggerPresent() )
    {
      LODWORD(phkResult) = v10;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        4280,
        L"CEventNotificationService::EnableProjectToAll",
        L"CHRA",
        L"hr",
        phkResult);
    }
    else
    {
      LODWORD(lpSecurityAttributes) = v10;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        4280,
        L"CEventNotificationService::EnableProjectToAll",
        L"CHRA",
        L"hr",
        lpSecurityAttributes);
    }
  }
LABEL_34:
  operator delete(v3);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140018e10  mov     rax, rsp
0x140018e13  mov     [rax+8], rbx
0x140018e17  push    rbp
0x140018e18  push    rsi
0x140018e19  push    rdi
0x140018e1a  push    r12
0x140018e1c  push    r13
0x140018e1e  push    r14
0x140018e20  push    r15
0x140018e22  sub     rsp, 50h
0x140018e26  xor     r12d, r12d
0x140018e29  mov     rdi, rdx
0x140018e2c  xor     edx, edx
0x140018e2e  mov     [rax+20h], r12
0x140018e32  mov     r14d, r12d
0x140018e35  mov     [rax+18h], r12
0x140018e39  lea     ecx, [rdx+3]
0x140018e3c  call    ?s_VerifyAccessLevelEx@CUserManagement@@SAJW4EUserAccessLevel@@H@Z; CUserManagement::s_VerifyAccessLevelEx(EUserAccessLevel,int)
0x140018e41  mov     ebx, eax
0x140018e43  test    eax, eax
0x140018e45  js      loc_1400190BA
0x140018e4b  mov     [rsp+88h+lpdwDisposition], r12; lpdwDisposition
0x140018e50  lea     rax, [rsp+88h+hKey]
0x140018e58  mov     [rsp+88h+phkResult], rax; phkResult
0x140018e5d  lea     rdx, ?g_kszOrchestrationRegKey@@3QBGB; "Software\\Microsoft\\Windows Multipoint"...
0x140018e64  mov     [rsp+88h+lpSecurityAttributes], r12; lpSecurityAttributes
0x140018e69  xor     r9d, r9d; lpClass
0x140018e6c  mov     [rsp+88h+samDesired], 20006h; samDesired
0x140018e74  xor     r8d, r8d; Reserved
0x140018e77  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140018e7e  mov     [rsp+88h+dwOptions], r12d; dwOptions
0x140018e83  call    cs:__imp_RegCreateKeyExW
0x140018e89  test    eax, eax
0x140018e8b  jz      short loc_140018EA7
0x140018e8d  jg      short loc_140018E93
0x140018e8f  mov     ebx, eax
0x140018e91  jmp     short loc_140018E9C
0x140018e93  movzx   ebx, ax
0x140018e96  or      ebx, 80070000h
0x140018e9c  mov     r13d, 10B0h
0x140018ea2  jmp     loc_140019041
0x140018ea7  test    rdi, rdi
0x140018eaa  jz      loc_14001900A
0x140018eb0  cmp     [rdi], r12w
0x140018eb4  jz      loc_14001900A
0x140018eba  lea     rdx, [rsp+88h+lpData]; unsigned __int16 **
0x140018ec2  mov     rcx, rdi; unsigned __int16 *
0x140018ec5  call    ?WmsEncrypt@@YAJPEBGPEAPEAG@Z; WmsEncrypt(ushort const *,ushort * *)
0x140018eca  mov     r14, [rsp+88h+lpData]
0x140018ed2  mov     ebx, eax
0x140018ed4  test    eax, eax
0x140018ed6  js      loc_1400190BA
0x140018edc  test    r14, r14
0x140018edf  jz      loc_140018F74
0x140018ee5  mov     edx, 7FFFFFFFh
0x140018eea  mov     rax, r14
0x140018eed  cmp     [rax], r12w
0x140018ef1  jz      short loc_140018EFD
0x140018ef3  add     rax, 2
0x140018ef7  sub     rdx, 1
0x140018efb  jnz     short loc_140018EED
0x140018efd  mov     rax, rdx
0x140018f00  neg     rax
0x140018f03  sbb     edi, edi
0x140018f05  not     edi
0x140018f07  and     edi, 80070057h
0x140018f0d  test    rdx, rdx
0x140018f10  jz      short loc_140018F70
0x140018f12  lea     eax, [rdx+rdx]
0x140018f15  mov     ecx, 0FFFFFFFEh
0x140018f1a  sub     ecx, eax
0x140018f1c  mov     r9d, 1; dwType
0x140018f22  neg     rdx
0x140018f25  lea     rdx, ?g_kszProjectAllInvitationRegValue@@3QBGB; "ProjectAllInvitation"
0x140018f2c  sbb     eax, eax
0x140018f2e  xor     r8d, r8d; Reserved
0x140018f31  and     eax, ecx
0x140018f33  mov     rcx, [rsp+88h+hKey]; hKey
0x140018f3b  add     eax, 2
0x140018f3e  mov     [rsp+88h+samDesired], eax; cbData
0x140018f42  mov     qword ptr [rsp+88h+dwOptions], r14; lpData
0x140018f47  call    cs:__imp_RegSetValueExW
0x140018f4d  mov     ebx, eax
0x140018f4f  test    eax, eax
0x140018f51  jz      short loc_140018F69
0x140018f53  jle     short loc_140018F5E
0x140018f55  movzx   ebx, ax
0x140018f58  or      ebx, 80070000h
0x140018f5e  mov     r13d, 10BDh
0x140018f64  jmp     loc_140019041
0x140018f69  mov     ebx, edi
0x140018f6b  jmp     loc_1400190BA
0x140018f70  mov     ebx, edi
0x140018f72  jmp     short loc_140018F7B
0x140018f74  mov     ebx, 80070057h
0x140018f79  mov     edi, ebx
0x140018f7b  lea     rbp, aCeventnotifica_142; "CEventNotificationService::EnableProjec"...
0x140018f82  mov     [rsp+88h+samDesired], edi; int
0x140018f86  mov     r15d, 10B8h
0x140018f8c  lea     rsi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x140018f93  lea     r13, aHr; "hr"
0x140018f9a  mov     r8, rbp; unsigned __int16 *
0x140018f9d  mov     edx, r15d; unsigned int
0x140018fa0  mov     qword ptr [rsp+88h+dwOptions], r13; unsigned __int16 *
0x140018fa5  mov     rcx, rsi; unsigned __int16 *
0x140018fa8  lea     r9, aChra; "CHRA"
0x140018faf  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140018fb4  call    cs:__imp_IsDebuggerPresent
0x140018fba  test    eax, eax
0x140018fbc  lea     rax, aChra; "CHRA"
0x140018fc3  jz      short loc_140018FF4
0x140018fc5  mov     dword ptr [rsp+88h+phkResult], edi
0x140018fc9  mov     r9d, r15d
0x140018fcc  mov     [rsp+88h+lpSecurityAttributes], r13
0x140018fd1  mov     qword ptr [rsp+88h+samDesired], rax
0x140018fd6  mov     r8, rsi
0x140018fd9  mov     qword ptr [rsp+88h+dwOptions], rbp
0x140018fde  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140018fe5  mov     ecx, 2; unsigned __int8
0x140018fea  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140018fef  jmp     loc_1400190BA
0x140018ff4  mov     dword ptr [rsp+88h+lpSecurityAttributes], edi
0x140018ff8  mov     r8d, r15d
0x140018ffb  mov     qword ptr [rsp+88h+samDesired], r13
0x140019000  mov     qword ptr [rsp+88h+dwOptions], rax
0x140019005  jmp     loc_1400190A8
0x14001900a  mov     rcx, [rsp+88h+hKey]; hKey
0x140019012  lea     rdx, ?g_kszProjectAllInvitationRegValue@@3QBGB; "ProjectAllInvitation"
0x140019019  call    cs:__imp_RegDeleteValueW
0x14001901f  test    eax, 0FFFFFFFDh
0x140019024  jz      loc_1400190BA
0x14001902a  test    eax, eax
0x14001902c  jg      short loc_140019032
0x14001902e  mov     ebx, eax
0x140019030  jmp     short loc_14001903B
0x140019032  movzx   ebx, ax
0x140019035  or      ebx, 80070000h
0x14001903b  mov     r13d, 10C5h
0x140019041  lea     r15, aCbraex; "CBRAEx"
0x140019048  mov     [rsp+88h+samDesired], ebx; int
0x14001904c  lea     rbp, aCeventnotifica_142; "CEventNotificationService::EnableProjec"...
0x140019053  mov     r9, r15; unsigned __int16 *
0x140019056  lea     rsi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x14001905d  mov     r8, rbp; unsigned __int16 *
0x140019060  lea     rdi, aLr0l; "lr == 0L"
0x140019067  mov     rcx, rsi; unsigned __int16 *
0x14001906a  mov     edx, r13d; unsigned int
0x14001906d  mov     qword ptr [rsp+88h+dwOptions], rdi; unsigned __int16 *
0x140019072  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140019077  call    cs:__imp_IsDebuggerPresent
0x14001907d  test    eax, eax
0x14001907f  jz      short loc_140019097
0x140019081  mov     dword ptr [rsp+88h+phkResult], ebx
0x140019085  mov     r9d, r13d
0x140019088  mov     [rsp+88h+lpSecurityAttributes], rdi
0x14001908d  mov     qword ptr [rsp+88h+samDesired], r15
0x140019092  jmp     loc_140018FD6
0x140019097  mov     dword ptr [rsp+88h+lpSecurityAttributes], ebx
0x14001909b  mov     r8d, r13d
0x14001909e  mov     qword ptr [rsp+88h+samDesired], rdi
0x1400190a3  mov     qword ptr [rsp+88h+dwOptions], r15
0x1400190a8  mov     r9, rbp
0x1400190ab  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400190b2  mov     rdx, rsi
0x1400190b5  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400190ba  mov     rcx, r14; Block
0x1400190bd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400190c2  mov     rcx, [rsp+88h+hKey]; hKey
0x1400190ca  test    rcx, rcx
0x1400190cd  jz      short loc_1400190D5
0x1400190cf  call    cs:__imp_RegCloseKey
0x1400190d5  mov     eax, ebx
0x1400190d7  mov     rbx, [rsp+88h+arg_0]
0x1400190df  add     rsp, 50h
0x1400190e3  pop     r15
0x1400190e5  pop     r14
0x1400190e7  pop     r13
0x1400190e9  pop     r12
0x1400190eb  pop     rdi
0x1400190ec  pop     rsi
0x1400190ed  pop     rbp
0x1400190ee  retn
```
