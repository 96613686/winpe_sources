# WinReUpdateLogInstance

- ea: `0x18002c810`
- end: `0x18002ca46`
- name: `WinReUpdateLogInstance`
- size: `566`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x1800055c8`
- `0x180005694`
- `0x1800059fc`
- `0x18000fe58`
- `0x18000ffcc`
- `0x180014754`
- `0x18001c598`
- `0x18002b6f0`
- `0x18002c590`
- `0x18002c810`
- `0x18003f2c0`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18002ca18`
- `KERNEL32!SetLastError` at `0x18002ca18`
- `ole32!CoTaskMemFree` at `0x18002c9e2`
- `ole32!CoTaskMemFree` at `0x18002c9f0`
- `ole32!CoTaskMemFree` at `0x18002c9e2`
- `ole32!CoTaskMemFree` at `0x18002c9f0`

## string_xrefs

- `0x18002c8e8`: `failed to allocate path`
- `0x18002c92c`: `failed to add file to directory path`
- `0x18002c8d1`: `base\diagnosis\srt\reagent2\reagent\logfile.cpp`
- `0x18002c9b9`: `base\diagnosis\srt\reagent2\reagent\logfile.cpp`
- `0x18002c982`: `failed to update agent reload`
- `0x18002c8ad`: `failed to create log directory`
- `0x18002c958`: `failed to init agent reload`
- `0x18002c888`: `Enter WinReUpdateLogInstance`
- `0x18002c8f2`: `WinReUpdateLogInstance %s (0x%x) in file %S line %d`
- `0x18002c9c3`: `WinReUpdateLogInstance %s (0x%x) in file %S line %d`
- `0x18002c9f8`: `Exit WinReUpdateLogInstance returns %d with last error: 0x%x`
- `0x18002c90b`: `Reload.xml`

## pseudocode

```c
_BOOL8 __fastcall WinReUpdateLogInstance(_DWORD *a1, _DWORD *a2)
{
  unsigned __int16 *v2; // rbx
  DWORD v5; // edi
  const wchar_t *v6; // r8
  int v8; // [rsp+28h] [rbp-61h]
  LPVOID pv; // [rsp+30h] [rbp-59h] BYREF
  unsigned __int16 *v10; // [rsp+38h] [rbp-51h] BYREF
  _QWORD v11[3]; // [rsp+40h] [rbp-49h] BYREF
  int v12; // [rsp+58h] [rbp-31h]
  int v13; // [rsp+5Ch] [rbp-2Dh]
  __int128 v14; // [rsp+60h] [rbp-29h]
  __int128 v15; // [rsp+70h] [rbp-19h]
  __int64 v16; // [rsp+80h] [rbp-9h]
  int v17; // [rsp+88h] [rbp-1h]
  __int64 v18; // [rsp+90h] [rbp+7h]

  v2 = 0;
  pv = 0;
  v10 = 0;
  v11[1] = 0;
  v11[2] = 0;
  v12 = 0;
  v14 = 0;
  v13 = 2;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v11[0] = &ReAgentReload::`vftable';
  v18 = 0;
  UnattendInitializeLogEx2(0);
  UnattendLogW(0, L"Enter WinReUpdateLogInstance");
  v5 = winreCreateOrOpenLogDir((unsigned __int16 **)&pv);
  if ( v5 )
  {
    v8 = 667;
    v6 = L"failed to create log directory";
LABEL_16:
    UnattendLogW(
      2,
      L"WinReUpdateLogInstance %s (0x%x) in file %S line %d",
      v6,
      v5,
      "base\\diagnosis\\srt\\reagent2\\reagent\\logfile.cpp",
      v8);
    goto LABEL_17;
  }
  if ( a1 )
  {
    v5 = winreAllocPath(&v10);
    if ( v5 )
    {
      UnattendLogW(
        2,
        L"WinReUpdateLogInstance %s (0x%x) in file %S line %d",
        L"failed to allocate path",
        v5,
        "base\\diagnosis\\srt\\reagent2\\reagent\\logfile.cpp",
        676);
      v2 = v10;
      goto LABEL_17;
    }
    v2 = v10;
    v5 = winreAddFileToDirPath((unsigned __int16 *)pv, L"Reload.xml", v10);
    if ( v5 )
    {
      v8 = 680;
      v6 = L"failed to add file to directory path";
      goto LABEL_16;
    }
    v5 = ReAgentReload::Init((ReAgentReload *)v11, v2, 1);
    if ( v5 )
    {
      v8 = 683;
      v6 = L"failed to init agent reload";
      goto LABEL_16;
    }
    *(_DWORD *)(v18 + 32) = *a1;
    v5 = ReAgentXMLParser::Update((ReAgentXMLParser *)v11);
    if ( v5 )
    {
      v8 = 694;
      v6 = L"failed to update agent reload";
      goto LABEL_16;
    }
  }
  if ( a2 )
  {
    if ( *a2 == 1 )
    {
      v5 = WinReSetTriggerFile((unsigned __int16 *)pv, 1u);
      if ( v5 )
      {
        v8 = 703;
        v6 = L"failed to set trigger file";
        goto LABEL_16;
      }
    }
  }
LABEL_17:
  if ( pv )
    CoTaskMemFree(pv);
  if ( v2 )
    CoTaskMemFree(v2);
  UnattendLogW(0, L"Exit WinReUpdateLogInstance returns %d with last error: 0x%x", v5 == 0, v5);
  UnattendFinalizeLog();
  SetLastError(v5);
  ReAgentReload::~ReAgentReload((ReAgentReload *)v11);
  return v5 == 0;
}

```

## disassembly

```asm
0x18002c810  push    rbp
0x18002c812  push    rbx
0x18002c813  push    rdi
0x18002c814  push    r13
0x18002c816  push    r14
0x18002c818  push    r15
0x18002c81a  lea     rbp, [rsp-2Fh]
0x18002c81f  sub     rsp, 0B8h
0x18002c826  mov     rax, cs:__security_cookie
0x18002c82d  xor     rax, rsp
0x18002c830  mov     [rbp+57h+var_40], rax
0x18002c834  xor     ebx, ebx
0x18002c836  mov     [rbp+57h+pv], 0
0x18002c83e  mov     r15, rcx
0x18002c841  mov     [rbp+57h+var_A8], rbx
0x18002c845  xorps   xmm0, xmm0
0x18002c848  mov     [rbp+57h+var_98], rbx
0x18002c84c  xorps   xmm1, xmm1
0x18002c84f  mov     [rbp+57h+var_90], rbx
0x18002c853  lea     rax, ??_7ReAgentReload@@6B@; const ReAgentReload::`vftable'
0x18002c85a  mov     [rbp+57h+var_88], ebx
0x18002c85d  lea     r13d, [rbx+2]
0x18002c861  movdqa  [rbp+57h+var_80], xmm0
0x18002c866  xor     ecx, ecx
0x18002c868  mov     [rbp+57h+var_84], r13d
0x18002c86c  mov     r14, rdx
0x18002c86f  movdqa  [rbp+57h+var_70], xmm1
0x18002c874  mov     [rbp+57h+var_60], rbx
0x18002c878  mov     [rbp+57h+var_58], ebx
0x18002c87b  mov     [rbp+57h+var_A0], rax
0x18002c87f  mov     [rbp+57h+var_50], rbx
0x18002c883  call    UnattendInitializeLogEx2
0x18002c888  lea     rdx, aEnterWinreupda_0; "Enter WinReUpdateLogInstance"
0x18002c88f  xor     ecx, ecx
0x18002c891  call    UnattendLogW
0x18002c896  lea     rcx, [rbp+57h+pv]; unsigned __int16 **
0x18002c89a  call    ?winreCreateOrOpenLogDir@@YAKPEAPEAG@Z; winreCreateOrOpenLogDir(ushort * *)
0x18002c89f  mov     edi, eax
0x18002c8a1  test    eax, eax
0x18002c8a3  jz      short loc_18002C8B9
0x18002c8a5  mov     [rsp+0E0h+var_B8], 29Bh
0x18002c8ad  lea     r8, aFailedToCreate_25; "failed to create log directory"
0x18002c8b4  jmp     loc_18002C9B9
0x18002c8b9  test    r15, r15
0x18002c8bc  jz      loc_18002C98B
0x18002c8c2  lea     rcx, [rbp+57h+var_A8]
0x18002c8c6  call    winreAllocPath
0x18002c8cb  mov     edi, eax
0x18002c8cd  test    eax, eax
0x18002c8cf  jz      short loc_18002C907
0x18002c8d1  lea     rax, aBaseDiagnosisS_6; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18002c8d8  mov     [rsp+0E0h+var_B8], 2A4h
0x18002c8e0  mov     r9d, edi
0x18002c8e3  mov     [rsp+0E0h+var_C0], rax
0x18002c8e8  lea     r8, aFailedToAlloca_4; "failed to allocate path"
0x18002c8ef  mov     ecx, r13d
0x18002c8f2  lea     rdx, aWinreupdatelog_0; "WinReUpdateLogInstance %s (0x%x) in fil"...
0x18002c8f9  call    UnattendLogW
0x18002c8fe  mov     rbx, [rbp+57h+var_A8]
0x18002c902  jmp     loc_18002C9D7
0x18002c907  mov     rbx, [rbp+57h+var_A8]
0x18002c90b  lea     rdx, aReloadXml; "Reload.xml"
0x18002c912  mov     rcx, [rbp+57h+pv]; unsigned __int16 *
0x18002c916  mov     r8, rbx; unsigned __int16 *
0x18002c919  call    winreAddFileToDirPath
0x18002c91e  mov     edi, eax
0x18002c920  test    eax, eax
0x18002c922  jz      short loc_18002C938
0x18002c924  mov     [rsp+0E0h+var_B8], 2A8h
0x18002c92c  lea     r8, aFailedToAddFil_3; "failed to add file to directory path"
0x18002c933  jmp     loc_18002C9B9
0x18002c938  mov     r8d, 1; int
0x18002c93e  lea     rcx, [rbp+57h+var_A0]; this
0x18002c942  mov     rdx, rbx; unsigned __int16 *
0x18002c945  call    ?Init@ReAgentReload@@UEAAKPEAGH@Z; ReAgentReload::Init(ushort *,int)
0x18002c94a  mov     edi, eax
0x18002c94c  test    eax, eax
0x18002c94e  jz      short loc_18002C961
0x18002c950  mov     [rsp+0E0h+var_B8], 2ABh
0x18002c958  lea     r8, aFailedToInitAg_1; "failed to init agent reload"
0x18002c95f  jmp     short loc_18002C9B9
0x18002c961  mov     ecx, [r15]
0x18002c964  mov     rax, [rbp+57h+var_50]
0x18002c968  mov     [rax+20h], ecx
0x18002c96b  lea     rcx, [rbp+57h+var_A0]; this
0x18002c96f  call    ?Update@ReAgentXMLParser@@QEAAKXZ; ReAgentXMLParser::Update(void)
0x18002c974  mov     edi, eax
0x18002c976  test    eax, eax
0x18002c978  jz      short loc_18002C98B
0x18002c97a  mov     [rsp+0E0h+var_B8], 2B6h
0x18002c982  lea     r8, aFailedToUpdate_4; "failed to update agent reload"
0x18002c989  jmp     short loc_18002C9B9
0x18002c98b  test    r14, r14
0x18002c98e  jz      short loc_18002C9D7
0x18002c990  cmp     dword ptr [r14], 1
0x18002c994  jnz     short loc_18002C9D7
0x18002c996  mov     rcx, [rbp+57h+pv]; unsigned __int16 *
0x18002c99a  mov     edx, 1
0x18002c99f  call    WinReSetTriggerFile
0x18002c9a4  mov     edi, eax
0x18002c9a6  test    eax, eax
0x18002c9a8  jz      short loc_18002C9D7
0x18002c9aa  mov     [rsp+0E0h+var_B8], 2BFh
0x18002c9b2  lea     r8, aFailedToSetTri; "failed to set trigger file"
0x18002c9b9  lea     rax, aBaseDiagnosisS_6; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18002c9c0  mov     r9d, edi
0x18002c9c3  lea     rdx, aWinreupdatelog_0; "WinReUpdateLogInstance %s (0x%x) in fil"...
0x18002c9ca  mov     [rsp+0E0h+var_C0], rax
0x18002c9cf  mov     ecx, r13d
0x18002c9d2  call    UnattendLogW
0x18002c9d7  cmp     [rbp+57h+pv], 0
0x18002c9dc  jz      short loc_18002C9E8
0x18002c9de  mov     rcx, [rbp+57h+pv]; pv
0x18002c9e2  call    cs:__imp_CoTaskMemFree
0x18002c9e8  test    rbx, rbx
0x18002c9eb  jz      short loc_18002C9F6
0x18002c9ed  mov     rcx, rbx; pv
0x18002c9f0  call    cs:__imp_CoTaskMemFree
0x18002c9f6  xor     ebx, ebx
0x18002c9f8  lea     rdx, aExitWinreupdat; "Exit WinReUpdateLogInstance returns %d "...
0x18002c9ff  test    edi, edi
0x18002ca01  mov     r9d, edi
0x18002ca04  setz    bl
0x18002ca07  xor     ecx, ecx
0x18002ca09  mov     r8d, ebx
0x18002ca0c  call    UnattendLogW
0x18002ca11  call    UnattendFinalizeLog
0x18002ca16  mov     ecx, edi; dwErrCode
0x18002ca18  call    cs:__imp_SetLastError
0x18002ca1e  lea     rcx, [rbp+57h+var_A0]; this
0x18002ca22  call    ??1ReAgentReload@@UEAA@XZ; ReAgentReload::~ReAgentReload(void)
0x18002ca27  mov     eax, ebx
0x18002ca29  mov     rcx, [rbp+57h+var_40]
0x18002ca2d  xor     rcx, rsp; StackCookie
0x18002ca30  call    __security_check_cookie
0x18002ca35  add     rsp, 0B8h
0x18002ca3c  pop     r15
0x18002ca3e  pop     r14
0x18002ca40  pop     r13
0x18002ca42  pop     rdi
0x18002ca43  pop     rbx
0x18002ca44  pop     rbp
0x18002ca45  retn
```
