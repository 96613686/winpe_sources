# CModule::SDKLoadLibrary(CModule::SDKLoadLibraryModule)

- ea: `0x18007eb04`
- end: `0x18007ec8a`
- name: `?SDKLoadLibrary@CModule@@QEAAPEAUHINSTANCE__@@W4SDKLoadLibraryModule@1@@Z`
- size: `390`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18002a41c`
- `0x18007703c`
- `0x18007ea60`
- `0x18007eb04`
- `0x180145068`

## callees

- `0x180029b30`
- `0x18007eb04`
- `0x18007ec90`
- `0x18007f054`
- `0x1800c3770`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007eb80`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007ebdd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007eb80`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007ebdd`

## string_xrefs

- `0x18007ec6d`: `DXGIDebug.dll`
- `0x18007eb4c`: `D3D12SDKLayers.dll`
- `0x18007ebad`: `D3D12SDKLayers.dll`
- `0x18007ec2f`: `Using the D3D12 SDKLayers dll requires that the latest SDKLayers for Windows 10 is installed.`
- `0x18007ebfd`: `Graphics tools for Windows 10 need to be installed.`
- `0x18007ec21`: `Graphics tools for Windows 10 need to be installed.`
- `0x18007eb9e`: `D3D12 SDKLayers dll in the D3D12SDKPath does not match the D3D12SDKVersion of D3D12 Core dll.`
- `0x18007ebef`: `D3D12 SDKLayers dll does not match the D3D12SDKVersion of D3D12 Core dll.`
- `0x18007ec13`: `D3D12 SDKLayers dll not found at D3D12SDKPath.`

## pseudocode

```c
HMODULE __fastcall CModule::SDKLoadLibrary(__int64 a1, int a2)
{
  HMODULE v3; // rdi
  __int64 v4; // rcx
  __int64 v5; // r9
  HMODULE v6; // rax
  unsigned int *ProcAddress; // rax
  CModule *v8; // rcx
  const char *v9; // r8
  HMODULE v10; // rax
  unsigned int *v11; // rax
  CModule *v12; // rcx
  int v13; // edx
  HMODULE hModule; // [rsp+50h] [rbp+18h] BYREF
  __int64 v16; // [rsp+58h] [rbp+20h] BYREF

  if ( !a2 )
  {
    v3 = 0;
    hModule = 0;
    v16 = CModule::SDKLoadLibrary(a1, 1);
    if ( !v16 )
    {
      v9 = "Using the D3D12 SDKLayers dll requires that the latest SDKLayers for Windows 10 is installed.";
      goto LABEL_16;
    }
    v6 = CModule::SDKLoadLibraryW(a1, L"D3D12SDKLayers.dll", *(_BYTE *)(a1 + 880) != 0 ? 2 : 0);
    D3DXPlat::unique_module::reset((D3DXPlat::unique_module *)&hModule, v6);
    v3 = hModule;
    if ( !hModule )
    {
      if ( *(_BYTE *)(a1 + 880) )
      {
        v9 = "D3D12 SDKLayers dll not found at D3D12SDKPath.";
        v13 = -2005008381;
      }
      else
      {
        v9 = "Graphics tools for Windows 10 need to be installed.";
        v13 = -2005270483;
      }
      goto LABEL_17;
    }
    ProcAddress = (unsigned int *)GetProcAddress(hModule, "D3D12SDKVersion");
    if ( !CModule::CheckLibraryVersion(v8, ProcAddress) )
    {
      if ( *(_BYTE *)(a1 + 880) )
      {
        v9 = "D3D12 SDKLayers dll in the D3D12SDKPath does not match the D3D12SDKVersion of D3D12 Core dll.";
LABEL_16:
        v13 = -2005008381;
        goto LABEL_17;
      }
      v10 = CModule::SDKLoadLibraryW(a1, L"D3D12SDKLayers.dll", 1);
      D3DXPlat::unique_module::reset((D3DXPlat::unique_module *)&hModule, v10);
      v3 = hModule;
      if ( !hModule )
      {
        v9 = "Graphics tools for Windows 10 need to be installed.";
        goto LABEL_10;
      }
      v11 = (unsigned int *)GetProcAddress(hModule, "D3D12SDKVersion");
      if ( !CModule::CheckLibraryVersion(v12, v11) )
      {
        v9 = "D3D12 SDKLayers dll does not match the D3D12SDKVersion of D3D12 Core dll.";
LABEL_10:
        v13 = -2005270483;
LABEL_17:
        CJournal::RecordJournal(v4, v13, (__int64)v9, v5, 1);
      }
    }
    hModule = 0;
    D3DXPlat::unique_module::reset((D3DXPlat::unique_module *)&v16, 0);
    D3DXPlat::unique_module::reset((D3DXPlat::unique_module *)&hModule, 0);
    return v3;
  }
  return CModule::SDKLoadLibraryW(a1, L"DXGIDebug.dll", 0);
}

```

## disassembly

```asm
0x18007eb04  mov     [rsp+arg_0], rbx
0x18007eb09  mov     [rsp+arg_8], rbp
0x18007eb0e  push    rdi
0x18007eb0f  sub     rsp, 30h
0x18007eb13  mov     rbx, rcx
0x18007eb16  test    edx, edx
0x18007eb18  jnz     loc_18007EC6A
0x18007eb1e  xor     edi, edi
0x18007eb20  mov     [rsp+38h+hModule], rdi
0x18007eb25  lea     ebp, [rdx+1]
0x18007eb28  mov     edx, ebp
0x18007eb2a  call    ?SDKLoadLibrary@CModule@@QEAAPEAUHINSTANCE__@@W4SDKLoadLibraryModule@1@@Z; CModule::SDKLoadLibrary(CModule::SDKLoadLibraryModule)
0x18007eb2f  mov     [rsp+38h+arg_18], rax
0x18007eb34  test    rax, rax
0x18007eb37  jz      loc_18007EC2F
0x18007eb3d  mov     al, [rbx+370h]
0x18007eb43  neg     al
0x18007eb45  sbb     r8d, r8d
0x18007eb48  and     r8d, 2
0x18007eb4c  lea     rdx, aD3d12sdklayers; "D3D12SDKLayers.dll"
0x18007eb53  mov     rcx, rbx
0x18007eb56  call    ?SDKLoadLibraryW@CModule@@AEAAPEAUHINSTANCE__@@PEBGW4CheckLibraryPath@1@@Z; CModule::SDKLoadLibraryW(ushort const *,CModule::CheckLibraryPath)
0x18007eb5b  mov     rdx, rax; HINSTANCE
0x18007eb5e  lea     rcx, [rsp+38h+hModule]; this
0x18007eb63  call    ?reset@unique_module@D3DXPlat@@QEAAXPEAUHINSTANCE__@@@Z; D3DXPlat::unique_module::reset(HINSTANCE__ *)
0x18007eb68  mov     rdi, [rsp+38h+hModule]
0x18007eb6d  test    rdi, rdi
0x18007eb70  jz      loc_18007EC06
0x18007eb76  lea     rdx, aD3d12sdkversio_0; "D3D12SDKVersion"
0x18007eb7d  mov     rcx, rdi; hModule
0x18007eb80  call    cs:__imp_GetProcAddress
0x18007eb86  mov     rdx, rax; unsigned int *
0x18007eb89  call    ?CheckLibraryVersion@CModule@@AEAA_NPEAI@Z; CModule::CheckLibraryVersion(uint *)
0x18007eb8e  test    al, al
0x18007eb90  jnz     loc_18007EC44
0x18007eb96  cmp     [rbx+370h], al
0x18007eb9c  jz      short loc_18007EBAA
0x18007eb9e  lea     r8, aD3d12Sdklayers_0; "D3D12 SDKLayers dll in the D3D12SDKPath"...
0x18007eba5  jmp     loc_18007EC36
0x18007ebaa  mov     r8d, ebp
0x18007ebad  lea     rdx, aD3d12sdklayers; "D3D12SDKLayers.dll"
0x18007ebb4  mov     rcx, rbx
0x18007ebb7  call    ?SDKLoadLibraryW@CModule@@AEAAPEAUHINSTANCE__@@PEBGW4CheckLibraryPath@1@@Z; CModule::SDKLoadLibraryW(ushort const *,CModule::CheckLibraryPath)
0x18007ebbc  mov     rdx, rax; HINSTANCE
0x18007ebbf  lea     rcx, [rsp+38h+hModule]; this
0x18007ebc4  call    ?reset@unique_module@D3DXPlat@@QEAAXPEAUHINSTANCE__@@@Z; D3DXPlat::unique_module::reset(HINSTANCE__ *)
0x18007ebc9  mov     rdi, [rsp+38h+hModule]
0x18007ebce  test    rdi, rdi
0x18007ebd1  jz      short loc_18007EBFD
0x18007ebd3  lea     rdx, aD3d12sdkversio_0; "D3D12SDKVersion"
0x18007ebda  mov     rcx, rdi; hModule
0x18007ebdd  call    cs:__imp_GetProcAddress
0x18007ebe3  mov     rdx, rax; unsigned int *
0x18007ebe6  call    ?CheckLibraryVersion@CModule@@AEAA_NPEAI@Z; CModule::CheckLibraryVersion(uint *)
0x18007ebeb  test    al, al
0x18007ebed  jnz     short loc_18007EC44
0x18007ebef  lea     r8, aD3d12Sdklayers_1; "D3D12 SDKLayers dll does not match the "...
0x18007ebf6  mov     edx, 887A002Dh
0x18007ebfb  jmp     short loc_18007EC3B
0x18007ebfd  lea     r8, aGraphicsToolsF; "Graphics tools for Windows 10 need to b"...
0x18007ec04  jmp     short loc_18007EBF6
0x18007ec06  mov     [rsp+38h+var_18], ebp
0x18007ec0a  cmp     byte ptr [rbx+370h], 0
0x18007ec11  jz      short loc_18007EC21
0x18007ec13  lea     r8, aD3d12Sdklayers; "D3D12 SDKLayers dll not found at D3D12S"...
0x18007ec1a  mov     edx, 887E0003h
0x18007ec1f  jmp     short loc_18007EC3F
0x18007ec21  lea     r8, aGraphicsToolsF; "Graphics tools for Windows 10 need to b"...
0x18007ec28  mov     edx, 887A002Dh
0x18007ec2d  jmp     short loc_18007EC3F
0x18007ec2f  lea     r8, aUsingTheD3d12S; "Using the D3D12 SDKLayers dll requires "...
0x18007ec36  mov     edx, 887E0003h
0x18007ec3b  mov     [rsp+38h+var_18], ebp
0x18007ec3f  call    ?RecordJournal@CJournal@@QEAAXIPEBD_NW4RecordJournalOptions@@@Z; CJournal::RecordJournal(uint,char const *,bool,RecordJournalOptions)
0x18007ec44  mov     [rsp+38h+hModule], 0
0x18007ec4d  xor     edx, edx; HINSTANCE
0x18007ec4f  lea     rcx, [rsp+38h+arg_18]; this
0x18007ec54  call    ?reset@unique_module@D3DXPlat@@QEAAXPEAUHINSTANCE__@@@Z; D3DXPlat::unique_module::reset(HINSTANCE__ *)
0x18007ec59  xor     edx, edx; HINSTANCE
0x18007ec5b  lea     rcx, [rsp+38h+hModule]; this
0x18007ec60  call    ?reset@unique_module@D3DXPlat@@QEAAXPEAUHINSTANCE__@@@Z; D3DXPlat::unique_module::reset(HINSTANCE__ *)
0x18007ec65  mov     rax, rdi
0x18007ec68  jmp     short loc_18007EC7A
0x18007ec6a  xor     r8d, r8d
0x18007ec6d  lea     rdx, aDxgidebugDll; "DXGIDebug.dll"
0x18007ec74  call    ?SDKLoadLibraryW@CModule@@AEAAPEAUHINSTANCE__@@PEBGW4CheckLibraryPath@1@@Z; CModule::SDKLoadLibraryW(ushort const *,CModule::CheckLibraryPath)
0x18007ec79  nop
0x18007ec7a  mov     rbx, [rsp+38h+arg_0]
0x18007ec7f  mov     rbp, [rsp+38h+arg_8]
0x18007ec84  add     rsp, 30h
0x18007ec88  pop     rdi
0x18007ec89  retn
```
