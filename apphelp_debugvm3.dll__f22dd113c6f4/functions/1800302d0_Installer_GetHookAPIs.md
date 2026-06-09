# Installer_GetHookAPIs

- ea: `0x1800302d0`
- end: `0x18003040b`
- name: `Installer_GetHookAPIs`
- size: `315`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting, installer_update`

## callees

- `0x1800302d0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800302f1`
- `ntdll!RtlAllocateHeap` at `0x1800302f1`

## string_xrefs

- `0x1800303e3`: `USER32.DLL`
- `0x180030356`: `ISRT.DLL`
- `0x18003030a`: `NTDLL.DLL`
- `0x180030311`: `NtCreateFile`
- `0x18003038e`: `CoCreateInstance`
- `0x180030380`: `OLE32.DLL`

## pseudocode

```c
_QWORD *__fastcall Installer_GetHookAPIs(__int64 a1, __int64 a2, _DWORD *a3)
{
  _QWORD *result; // rax

  result = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x150u);
  InsApiHooks = (__int64)result;
  if ( result )
  {
    *result = "NTDLL.DLL";
    result[1] = "NtCreateFile";
    result[2] = &InsHook_NtCreateFile;
    result[7] = "NtSetInformationFile";
    result[8] = InsHook_NtSetInformationFile;
    result[13] = "NtSetValueKey";
    result[14] = InsHook_NtSetValueKey;
    result[18] = "ISRT.DLL";
    result[19] = "_ShowWizardPages";
    result[20] = InsHook__ShowWizardPages;
    result[24] = "OLE32.DLL";
    result[25] = "CoCreateInstance";
    result[26] = InsHook_CoCreateInstance;
    result[31] = "SetWindowsHookExW";
    result[32] = InsHook_SetWindowsHookExW;
    result[37] = "CallNextHookEx";
    result[6] = "NTDLL.DLL";
    result[12] = "NTDLL.DLL";
    result[38] = InsHook_CallNextHookEx;
    result[30] = "USER32.DLL";
    result[36] = "USER32.DLL";
    *a3 = 7;
  }
  else
  {
    *a3 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800302d0  push    rbx
0x1800302d2  sub     rsp, 20h
0x1800302d6  mov     rcx, gs:60h
0x1800302df  mov     rbx, r8
0x1800302e2  mov     edx, 8; Flags
0x1800302e7  mov     r8d, 150h; Size
0x1800302ed  mov     rcx, [rcx+30h]; HeapHandle
0x1800302f1  call    cs:__imp_RtlAllocateHeap
0x1800302f7  mov     cs:InsApiHooks, rax
0x1800302fe  test    rax, rax
0x180030301  jnz     short loc_18003030A
0x180030303  mov     [rbx], eax
0x180030305  jmp     loc_180030405
0x18003030a  lea     rdx, aNtdllDll_0; "NTDLL.DLL"
0x180030311  lea     rcx, aNtcreatefile; "NtCreateFile"
0x180030318  mov     [rax], rdx
0x18003031b  mov     [rax+8], rcx
0x18003031f  lea     rcx, InsHook_NtCreateFile
0x180030326  mov     [rax+10h], rcx
0x18003032a  lea     rcx, aNtsetinformati; "NtSetInformationFile"
0x180030331  mov     [rax+38h], rcx
0x180030335  lea     rcx, InsHook_NtSetInformationFile
0x18003033c  mov     [rax+40h], rcx
0x180030340  lea     rcx, aNtsetvaluekey; "NtSetValueKey"
0x180030347  mov     [rax+68h], rcx
0x18003034b  lea     rcx, InsHook_NtSetValueKey
0x180030352  mov     [rax+70h], rcx
0x180030356  lea     rcx, aIsrtDll; "ISRT.DLL"
0x18003035d  mov     [rax+90h], rcx
0x180030364  lea     rcx, aShowwizardpage; "_ShowWizardPages"
0x18003036b  mov     [rax+98h], rcx
0x180030372  lea     rcx, InsHook__ShowWizardPages
0x180030379  mov     [rax+0A0h], rcx
0x180030380  lea     rcx, aOle32Dll_0; "OLE32.DLL"
0x180030387  mov     [rax+0C0h], rcx
0x18003038e  lea     rcx, aCocreateinstan; "CoCreateInstance"
0x180030395  mov     [rax+0C8h], rcx
0x18003039c  lea     rcx, InsHook_CoCreateInstance
0x1800303a3  mov     [rax+0D0h], rcx
0x1800303aa  lea     rcx, aSetwindowshook; "SetWindowsHookExW"
0x1800303b1  mov     [rax+0F8h], rcx
0x1800303b8  lea     rcx, InsHook_SetWindowsHookExW
0x1800303bf  mov     [rax+100h], rcx
0x1800303c6  lea     rcx, aCallnexthookex; "CallNextHookEx"
0x1800303cd  mov     [rax+128h], rcx
0x1800303d4  lea     rcx, InsHook_CallNextHookEx
0x1800303db  mov     [rax+30h], rdx
0x1800303df  mov     [rax+60h], rdx
0x1800303e3  lea     rdx, aUser32Dll_0; "USER32.DLL"
0x1800303ea  mov     [rax+130h], rcx
0x1800303f1  mov     [rax+0F0h], rdx
0x1800303f8  mov     [rax+120h], rdx
0x1800303ff  mov     dword ptr [rbx], 7
0x180030405  add     rsp, 20h
0x180030409  pop     rbx
0x18003040a  retn
```
