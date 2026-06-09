# FveBackupMonitor::SetOsEncryptionID(_GUID const *)

- ea: `0x180031908`
- end: `0x180031ae5`
- name: `?SetOsEncryptionID@FveBackupMonitor@@SAJPEBU_GUID@@@Z`
- size: `477`
- prototype: `__int64 __fastcall(GUID *Guid)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180043e5c`

## callees

- `0x180009f60`
- `0x18001b7f0`
- `0x18001b890`
- `0x180031908`
- `0x180034070`
- `0x180034d28`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x180031ab5`
- `ntdll!RtlFreeUnicodeString` at `0x180031ab5`
- `ntdll!RtlStringFromGUID` at `0x180031981`
- `ntdll!RtlStringFromGUID` at `0x180031981`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180031a5f`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180031a5f`

## pseudocode

```c
__int64 __fastcall FveBackupMonitor::SetOsEncryptionID(GUID *Guid)
{
  signed int v2; // ebx
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  NTSTATUS v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  LSTATUS v8; // eax
  struct _UNICODE_STRING GuidString; // [rsp+30h] [rbp-238h] BYREF
  WCHAR SubKey[264]; // [rsp+40h] [rbp-228h] BYREF

  memset_0(SubKey, 0, 0x208u);
  GuidString = 0;
  if ( Guid )
  {
    v5 = RtlStringFromGUID(Guid, &GuidString);
    v6 = FromNtStatus(v5);
    v2 = v6;
    if ( !v6 )
      goto LABEL_19;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_929186be452536e5252128d48ffaedab_Traceguids, v6);
    if ( v2 >= 0 )
    {
LABEL_19:
      v7 = StringCchPrintfW(
             SubKey,
             0x104u,
             L"%s\\%s",
             L"Software\\Microsoft\\Windows\\CurrentVersion\\BitLocker\\KeyBackupMonitor",
             L"OSV");
      v2 = v7;
      if ( !v7 )
        goto LABEL_27;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_929186be452536e5252128d48ffaedab_Traceguids, v7);
      if ( v2 >= 0 )
      {
LABEL_27:
        v8 = RegSetKeyValueW(HKEY_CURRENT_USER, SubKey, L"OSEncryptionId", 2u, GuidString.Buffer, GuidString.Length + 2);
        v2 = v8;
        if ( v8 > 0 )
          v2 = (unsigned __int16)v8 | 0x80070000;
        if ( v2 )
        {
          v3 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          {
            v4 = 49;
            goto LABEL_21;
          }
        }
      }
    }
  }
  else
  {
    v2 = -2147024809;
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      v4 = 46;
LABEL_21:
      WPP_SF_d(v3[2], v4, WPP_929186be452536e5252128d48ffaedab_Traceguids, (unsigned int)v2);
    }
  }
  if ( GuidString.Buffer )
    RtlFreeUnicodeString(&GuidString);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180031908  mov     [rsp+arg_8], rbx
0x18003190d  push    rdi
0x18003190e  sub     rsp, 260h
0x180031915  mov     rax, cs:__security_cookie
0x18003191c  xor     rax, rsp
0x18003191f  mov     [rsp+268h+var_18], rax
0x180031927  mov     rbx, rcx
0x18003192a  xor     edx, edx; Val
0x18003192c  lea     rcx, [rsp+268h+SubKey]; void *
0x180031931  mov     r8d, 208h; Size
0x180031937  call    memset_0
0x18003193c  xorps   xmm0, xmm0
0x18003193f  movups  xmmword ptr [rsp+268h+GuidString.Length], xmm0
0x180031944  test    rbx, rbx
0x180031947  jnz     short loc_180031979
0x180031949  mov     ebx, 80070057h
0x18003194e  mov     rcx, cs:WPP_GLOBAL_Control
0x180031955  lea     rdi, WPP_GLOBAL_Control
0x18003195c  cmp     rcx, rdi
0x18003195f  jz      loc_180031AA8
0x180031965  test    byte ptr [rcx+1Ch], 40h
0x180031969  jz      loc_180031AA8
0x18003196f  mov     edx, 2Eh ; '.'
0x180031974  jmp     loc_180031A95
0x180031979  lea     rdx, [rsp+268h+GuidString]; GuidString
0x18003197e  mov     rcx, rbx; Guid
0x180031981  call    cs:__imp_RtlStringFromGUID
0x180031988  nop     dword ptr [rax+rax+00h]
0x18003198d  mov     ecx, eax; int
0x18003198f  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x180031994  lea     rdi, WPP_GLOBAL_Control
0x18003199b  mov     ebx, eax
0x18003199d  test    eax, eax
0x18003199f  jz      short loc_1800319D3
0x1800319a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800319a8  cmp     rcx, rdi
0x1800319ab  jz      short loc_1800319CB
0x1800319ad  test    byte ptr [rcx+1Ch], 40h
0x1800319b1  jz      short loc_1800319CB
0x1800319b3  mov     rcx, [rcx+10h]
0x1800319b7  lea     r8, WPP_929186be452536e5252128d48ffaedab_Traceguids
0x1800319be  mov     edx, 2Fh ; '/'
0x1800319c3  mov     r9d, eax
0x1800319c6  call    WPP_SF_d
0x1800319cb  test    ebx, ebx
0x1800319cd  js      loc_180031AA8
0x1800319d3  lea     rax, aOsv; "OSV"
0x1800319da  mov     edx, 104h; unsigned __int64
0x1800319df  lea     r9, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800319e6  mov     [rsp+268h+lpData], rax
0x1800319eb  lea     r8, aSS; "%s\\%s"
0x1800319f2  lea     rcx, [rsp+268h+SubKey]; unsigned __int16 *
0x1800319f7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800319fc  mov     ebx, eax
0x1800319fe  test    eax, eax
0x180031a00  jz      short loc_180031A30
0x180031a02  mov     rcx, cs:WPP_GLOBAL_Control
0x180031a09  cmp     rcx, rdi
0x180031a0c  jz      short loc_180031A2C
0x180031a0e  test    byte ptr [rcx+1Ch], 40h
0x180031a12  jz      short loc_180031A2C
0x180031a14  mov     rcx, [rcx+10h]
0x180031a18  lea     r8, WPP_929186be452536e5252128d48ffaedab_Traceguids
0x180031a1f  mov     edx, 30h ; '0'
0x180031a24  mov     r9d, eax
0x180031a27  call    WPP_SF_d
0x180031a2c  test    ebx, ebx
0x180031a2e  js      short loc_180031AA8
0x180031a30  movzx   eax, [rsp+268h+GuidString.Length]
0x180031a35  lea     r8, aOsencryptionid; "OSEncryptionId"
0x180031a3c  mov     r9d, 2; dwType
0x180031a42  lea     rdx, [rsp+268h+SubKey]; lpSubKey
0x180031a47  add     eax, r9d
0x180031a4a  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180031a51  mov     [rsp+268h+cbData], eax; cbData
0x180031a55  mov     rax, [rsp+268h+GuidString.Buffer]
0x180031a5a  mov     [rsp+268h+lpData], rax; lpData
0x180031a5f  call    cs:__imp_RegSetKeyValueW
0x180031a66  nop     dword ptr [rax+rax+00h]
0x180031a6b  mov     ebx, eax
0x180031a6d  test    eax, eax
0x180031a6f  jle     short loc_180031A7A
0x180031a71  movzx   ebx, ax
0x180031a74  or      ebx, 80070000h
0x180031a7a  test    ebx, ebx
0x180031a7c  jz      short loc_180031AA8
0x180031a7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180031a85  cmp     rcx, rdi
0x180031a88  jz      short loc_180031AA8
0x180031a8a  test    byte ptr [rcx+1Ch], 40h
0x180031a8e  jz      short loc_180031AA8
0x180031a90  mov     edx, 31h ; '1'
0x180031a95  mov     rcx, [rcx+10h]
0x180031a99  lea     r8, WPP_929186be452536e5252128d48ffaedab_Traceguids
0x180031aa0  mov     r9d, ebx
0x180031aa3  call    WPP_SF_d
0x180031aa8  cmp     [rsp+268h+GuidString.Buffer], 0
0x180031aae  jz      short loc_180031AC1
0x180031ab0  lea     rcx, [rsp+268h+GuidString]; UnicodeString
0x180031ab5  call    cs:__imp_RtlFreeUnicodeString
0x180031abc  nop     dword ptr [rax+rax+00h]
0x180031ac1  mov     eax, ebx
0x180031ac3  mov     rcx, [rsp+268h+var_18]
0x180031acb  xor     rcx, rsp; StackCookie
0x180031ace  call    __security_check_cookie
0x180031ad3  mov     rbx, [rsp+268h+arg_8]
0x180031adb  add     rsp, 260h
0x180031ae2  pop     rdi
0x180031ae3  retn
```
