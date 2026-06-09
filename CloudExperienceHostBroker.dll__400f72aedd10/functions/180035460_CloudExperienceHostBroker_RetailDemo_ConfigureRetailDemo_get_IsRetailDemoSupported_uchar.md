# CloudExperienceHostBroker::RetailDemo::ConfigureRetailDemo::get_IsRetailDemoSupported(uchar *)

- ea: `0x180035460`
- end: `0x1800354e7`
- name: `?get_IsRetailDemoSupported@ConfigureRetailDemo@RetailDemo@CloudExperienceHostBroker@@UEAAJPEAE@Z`
- size: `135`
- prototype: `__int64 __fastcall(CloudExperienceHostBroker::RetailDemo::ConfigureRetailDemo *__hidden this, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18001793c`
- `0x180018be8`
- `0x180035460`

## import_xrefs

- `ext-ms-win-security-slc-l1-1-0!SLGetWindowsInformationDWORD` at `0x1800354a6`
- `ext-ms-win-security-slc-l1-1-0!SLGetWindowsInformationDWORD` at `0x1800354a6`

## string_xrefs

- `0x1800354b5`: `shell\cloudexperiencehost\broker\lib\retaildemo.cpp`

## pseudocode

```c
__int64 __fastcall CloudExperienceHostBroker::RetailDemo::ConfigureRetailDemo::get_IsRetailDemoSupported(
        CloudExperienceHostBroker::RetailDemo::ConfigureRetailDemo *this,
        bool *a2,
        __int64 a3,
        unsigned int a4)
{
  HRESULT v5; // eax
  int v6; // eax
  int v8; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v10; // [rsp+48h] [rbp+10h] BYREF
  DWORD pdwValue; // [rsp+50h] [rbp+18h] BYREF

  v10 = 0;
  if ( (int)SHRegGetBOOLWithREGSAM(
              (HKEY)this,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE\\TestHooks",
              L"TestRetailDemoSupported",
              a4,
              &v10) < 0 )
  {
    pdwValue = 0;
    v5 = SLGetWindowsInformationDWORD(L"RetailDemo.License-RetailDemoAllowed", &pdwValue);
    if ( v5 >= 0 )
    {
      v6 = pdwValue != 0;
      goto LABEL_5;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\retaildemo.cpp",
      (const char *)(unsigned int)v5,
      v8);
  }
  v6 = v10;
LABEL_5:
  *a2 = v6 != 0;
  return 0;
}

```

## disassembly

```asm
0x180035460  push    rbx
0x180035462  sub     rsp, 30h
0x180035466  mov     rbx, rdx
0x180035469  mov     [rsp+38h+arg_8], 0
0x180035471  lea     rax, [rsp+38h+arg_8]
0x180035476  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18003547d  mov     qword ptr [rsp+38h+var_18], rax; int
0x180035482  lea     r8, aTestretaildemo; "TestRetailDemoSupported"
0x180035489  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x18003548e  test    eax, eax
0x180035490  jns     short loc_1800354C9
0x180035492  lea     rdx, [rsp+38h+pdwValue]; pdwValue
0x180035497  mov     [rsp+38h+pdwValue], 0
0x18003549f  lea     rcx, aRetaildemoLice; "RetailDemo.License-RetailDemoAllowed"
0x1800354a6  call    cs:__imp_SLGetWindowsInformationDWORD
0x1800354ac  test    eax, eax
0x1800354ae  jns     short loc_1800354DC
0x1800354b0  mov     rcx, [rsp+38h]; this
0x1800354b5  lea     r8, aShellCloudexpe_3; "shell\\cloudexperiencehost\\broker\\lib"...
0x1800354bc  mov     r9d, eax; char *
0x1800354bf  mov     edx, 63h ; 'c'; void *
0x1800354c4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800354c9  mov     eax, [rsp+38h+arg_8]
0x1800354cd  test    eax, eax
0x1800354cf  setnz   al
0x1800354d2  mov     [rbx], al
0x1800354d4  xor     eax, eax
0x1800354d6  add     rsp, 30h
0x1800354da  pop     rbx
0x1800354db  retn
0x1800354dc  xor     eax, eax
0x1800354de  cmp     [rsp+38h+pdwValue], eax
0x1800354e2  setnz   al
0x1800354e5  jmp     short loc_1800354CD
```
