# FSCreateSensorTransformFactory

- ea: `0x18002f698`
- end: `0x18002f90a`
- name: `FSCreateSensorTransformFactory`
- size: `626`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002ed6c`

## callees

- `0x180005f98`
- `0x1800060f8`
- `0x180006a98`
- `0x18002eb3c`
- `0x18002f698`
- `0x1800434dc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002f8eb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002f8eb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002f7a7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002f83f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002f7a7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002f83f`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x18002f756`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x18002f756`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002f7ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002f7ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f8cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f8dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f8cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f8dd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002f71d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002f71d`
- `MFPlat!MFTraceError` at `0x18002f7e0`
- `MFPlat!MFTraceError` at `0x18002f7e0`

## string_xrefs

- `0x18002f7cb`: `FSCreateSensorTransformFactory`

## pseudocode

```c
__int64 __fastcall FSCreateSensorTransformFactory(__int64 a1)
{
  HINSTANCE v1; // r15
  void *pvData; // r14
  int TransformFromModule; // ebx
  int v5; // ecx
  __int64 v6; // rdx
  LSTATUS ValueW; // eax
  __int64 v8; // rdx
  LSTATUS v9; // eax
  const struct _GUID *v10; // r8
  HINSTANCE v11; // rax
  DWORD pcbData; // [rsp+80h] [rbp+38h] BYREF
  LPVOID ppv; // [rsp+88h] [rbp+40h] BYREF
  HINSTANCE v15; // [rsp+90h] [rbp+48h] BYREF
  LPOLESTR lpsz; // [rsp+98h] [rbp+50h] BYREF

  v1 = 0;
  ppv = 0;
  pvData = 0;
  lpsz = 0;
  v15 = 0;
  if ( a1 )
  {
    TransformFromModule = CoCreateInstance(
                            (const IID *const)(a1 + 16),
                            0,
                            1u,
                            &GUID_00000000_0000_0000_c000_000000000046,
                            &ppv);
    if ( TransformFromModule >= 0 )
    {
      *(_QWORD *)(a1 + 8) = ppv;
      *(_DWORD *)a1 = 0;
      ppv = 0;
      goto LABEL_28;
    }
    if ( !IsSensorTransformModuleEnabled() )
      goto LABEL_28;
    pcbData = 0;
    TransformFromModule = StringFromIID((const IID *const)(a1 + 16), &lpsz);
    if ( TransformFromModule < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_28;
      v6 = 67;
      goto LABEL_4;
    }
    ValueW = RegGetValueW(
               HKEY_LOCAL_MACHINE,
               L"SOFTWARE\\Microsoft\\Windows Media Foundation\\FrameServer",
               lpsz,
               2u,
               0,
               0,
               &pcbData);
    TransformFromModule = ValueW;
    if ( ValueW )
    {
      if ( ValueW > 0 )
        TransformFromModule = (unsigned __int16)ValueW | 0x80070000;
      v8 = 339;
    }
    else
    {
      pvData = CoTaskMemAlloc(pcbData);
      if ( !pvData )
      {
        TransformFromModule = -2147024882;
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_28;
        v6 = 68;
        goto LABEL_4;
      }
      v9 = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows Media Foundation\\FrameServer",
             lpsz,
             2u,
             0,
             pvData,
             &pcbData);
      TransformFromModule = v9;
      if ( !v9 )
      {
        TransformFromModule = GetTransformFromModule((const unsigned __int16 *)pvData, &v15, v10, &ppv);
        if ( TransformFromModule >= 0 )
        {
          *(_QWORD *)(a1 + 8) = ppv;
          v11 = v15;
          *(_QWORD *)(a1 + 32) = pvData;
          pvData = 0;
          *(_QWORD *)(a1 + 40) = v11;
          *(_DWORD *)a1 = 2;
          ppv = 0;
        }
        else
        {
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              69,
              &WPP_d1d2e7bb2c893df46f1284d21fd62588_Traceguids,
              0,
              TransformFromModule);
          v1 = v15;
        }
        goto LABEL_28;
      }
      if ( v9 > 0 )
        TransformFromModule = (unsigned __int16)v9 | 0x80070000;
      v8 = 349;
    }
    MFTraceError(
      "avcore\\mf\\frameserver\\sensortransform\\manager\\sensortransform.cpp",
      v8,
      "FSCreateSensorTransformFactory",
      0,
      TransformFromModule,
      1);
    goto LABEL_28;
  }
  TransformFromModule = -2147024809;
  if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    goto LABEL_34;
  v6 = (unsigned int)(v5 + 66);
LABEL_4:
  WPP_SF_qD(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    v6,
    &WPP_d1d2e7bb2c893df46f1284d21fd62588_Traceguids,
    0,
    TransformFromModule);
LABEL_28:
  if ( lpsz )
    CoTaskMemFree(lpsz);
  if ( pvData )
    CoTaskMemFree(pvData);
  if ( v1 )
    FreeLibrary(v1);
LABEL_34:
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&ppv);
  return (unsigned int)TransformFromModule;
}

```

## disassembly

```asm
0x18002f698  push    rbp
0x18002f69a  push    rbx
0x18002f69b  push    rdi
0x18002f69c  push    r12
0x18002f69e  push    r14
0x18002f6a0  push    r15
0x18002f6a2  mov     rbp, rsp
0x18002f6a5  sub     rsp, 48h
0x18002f6a9  xor     r15d, r15d
0x18002f6ac  mov     [rbp+arg_8], 0
0x18002f6b4  xor     r14d, r14d
0x18002f6b7  mov     [rbp+lpsz], 0
0x18002f6bf  mov     [rbp+arg_10], r15
0x18002f6c3  mov     rdi, rcx
0x18002f6c6  test    rcx, rcx
0x18002f6c9  jnz     short loc_18002F703
0x18002f6cb  mov     ebx, 80070057h
0x18002f6d0  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002f6d5  cmp     al, 1
0x18002f6d7  jb      loc_18002F8F1
0x18002f6dd  lea     edx, [rcx+42h]
0x18002f6e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f6e7  lea     r8, WPP_d1d2e7bb2c893df46f1284d21fd62588_Traceguids
0x18002f6ee  xor     r9d, r9d
0x18002f6f1  mov     dword ptr [rsp+48h+ppv], ebx
0x18002f6f5  mov     rcx, [rcx+10h]
0x18002f6f9  call    WPP_SF_qD
0x18002f6fe  jmp     loc_18002F8C6
0x18002f703  xor     edx, edx; pUnkOuter
0x18002f705  lea     rax, [rbp+arg_8]
0x18002f709  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18002f710  mov     [rsp+48h+ppv], rax; ppv
0x18002f715  add     rcx, 10h; rclsid
0x18002f719  lea     r8d, [rdx+1]; dwClsContext
0x18002f71d  call    cs:__imp_CoCreateInstance
0x18002f723  mov     ebx, eax
0x18002f725  test    eax, eax
0x18002f727  js      short loc_18002F73D
0x18002f729  mov     rax, [rbp+arg_8]
0x18002f72d  mov     [rdi+8], rax
0x18002f731  mov     [rdi], r14d
0x18002f734  mov     [rbp+arg_8], r14
0x18002f738  jmp     loc_18002F8C6
0x18002f73d  call    ?IsSensorTransformModuleEnabled@@YA_NXZ; IsSensorTransformModuleEnabled(void)
0x18002f742  test    al, al
0x18002f744  jz      loc_18002F8C6
0x18002f74a  lea     rdx, [rbp+lpsz]; lplpsz
0x18002f74e  mov     [rbp+arg_0], r14d
0x18002f752  lea     rcx, [rdi+10h]; rclsid
0x18002f756  call    cs:__imp_StringFromIID
0x18002f75c  mov     ebx, eax
0x18002f75e  test    eax, eax
0x18002f760  jns     short loc_18002F779
0x18002f762  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002f767  cmp     al, 1
0x18002f769  jb      loc_18002F8C6
0x18002f76f  mov     edx, 43h ; 'C'
0x18002f774  jmp     loc_18002F6E0
0x18002f779  mov     r8, [rbp+lpsz]; lpValue
0x18002f77d  lea     rax, [rbp+arg_0]
0x18002f781  mov     [rsp+48h+pcbData], rax; pcbData
0x18002f786  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows Media Foun"...
0x18002f78d  mov     r12d, 2
0x18002f793  mov     [rsp+48h+pvData], r14; pvData
0x18002f798  mov     r9d, r12d; dwFlags
0x18002f79b  mov     [rsp+48h+ppv], r14; pdwType
0x18002f7a0  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18002f7a7  call    cs:__imp_RegGetValueW
0x18002f7ad  mov     ebx, eax
0x18002f7af  test    eax, eax
0x18002f7b1  jz      short loc_18002F7EB
0x18002f7b3  jle     short loc_18002F7BE
0x18002f7b5  movzx   ebx, ax
0x18002f7b8  or      ebx, 80070000h
0x18002f7be  mov     edx, 153h
0x18002f7c3  mov     dword ptr [rsp+48h+pvData], 1
0x18002f7cb  lea     r8, aFscreatesensor; "FSCreateSensorTransformFactory"
0x18002f7d2  xor     r9d, r9d
0x18002f7d5  mov     dword ptr [rsp+48h+ppv], ebx
0x18002f7d9  lea     rcx, aAvcoreMfFrames; "avcore\\mf\\frameserver\\sensortransfor"...
0x18002f7e0  call    cs:__imp_MFTraceError
0x18002f7e6  jmp     loc_18002F8C6
0x18002f7eb  mov     ecx, [rbp+arg_0]; cb
0x18002f7ee  call    cs:__imp_CoTaskMemAlloc
0x18002f7f4  mov     r14, rax
0x18002f7f7  test    rax, rax
0x18002f7fa  jnz     short loc_18002F817
0x18002f7fc  mov     ebx, 8007000Eh
0x18002f801  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002f806  cmp     al, 1
0x18002f808  jb      loc_18002F8C6
0x18002f80e  lea     edx, [r14+44h]
0x18002f812  jmp     loc_18002F6E0
0x18002f817  mov     r8, [rbp+lpsz]; lpValue
0x18002f81b  lea     rax, [rbp+arg_0]
0x18002f81f  mov     [rsp+48h+pcbData], rax; pcbData
0x18002f824  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows Media Foun"...
0x18002f82b  mov     [rsp+48h+pvData], r14; pvData
0x18002f830  mov     r9d, r12d; dwFlags
0x18002f833  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18002f83a  mov     [rsp+48h+ppv], r15; pdwType
0x18002f83f  call    cs:__imp_RegGetValueW
0x18002f845  mov     ebx, eax
0x18002f847  test    eax, eax
0x18002f849  jz      short loc_18002F860
0x18002f84b  jle     short loc_18002F856
0x18002f84d  movzx   ebx, ax
0x18002f850  or      ebx, 80070000h
0x18002f856  mov     edx, 15Dh
0x18002f85b  jmp     loc_18002F7C3
0x18002f860  lea     r9, [rbp+arg_8]; void **
0x18002f864  mov     rcx, r14; unsigned __int16 *
0x18002f867  lea     rdx, [rbp+arg_10]; HINSTANCE *
0x18002f86b  call    ?GetTransformFromModule@@YAJPEBGPEAPEAUHINSTANCE__@@AEBU_GUID@@PEAPEAX@Z; GetTransformFromModule(ushort const *,HINSTANCE__ * *,_GUID const &,void * *)
0x18002f870  mov     ebx, eax
0x18002f872  test    eax, eax
0x18002f874  jns     short loc_18002F8A8
0x18002f876  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002f87b  cmp     al, 1
0x18002f87d  jb      short loc_18002F8A2
0x18002f87f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f886  lea     r8, WPP_d1d2e7bb2c893df46f1284d21fd62588_Traceguids
0x18002f88d  mov     edx, 45h ; 'E'
0x18002f892  mov     dword ptr [rsp+48h+ppv], ebx
0x18002f896  xor     r9d, r9d
0x18002f899  mov     rcx, [rcx+10h]
0x18002f89d  call    WPP_SF_qD
0x18002f8a2  mov     r15, [rbp+arg_10]
0x18002f8a6  jmp     short loc_18002F8C6
0x18002f8a8  mov     rax, [rbp+arg_8]
0x18002f8ac  mov     [rdi+8], rax
0x18002f8b0  mov     rax, [rbp+arg_10]
0x18002f8b4  mov     [rdi+20h], r14
0x18002f8b8  xor     r14d, r14d
0x18002f8bb  mov     [rdi+28h], rax
0x18002f8bf  mov     [rdi], r12d
0x18002f8c2  mov     [rbp+arg_8], r15
0x18002f8c6  mov     rcx, [rbp+lpsz]; pv
0x18002f8ca  test    rcx, rcx
0x18002f8cd  jz      short loc_18002F8D5
0x18002f8cf  call    cs:__imp_CoTaskMemFree
0x18002f8d5  test    r14, r14
0x18002f8d8  jz      short loc_18002F8E3
0x18002f8da  mov     rcx, r14; pv
0x18002f8dd  call    cs:__imp_CoTaskMemFree
0x18002f8e3  test    r15, r15
0x18002f8e6  jz      short loc_18002F8F1
0x18002f8e8  mov     rcx, r15; hLibModule
0x18002f8eb  call    cs:__imp_FreeLibrary
0x18002f8f1  lea     rcx, [rbp+arg_8]
0x18002f8f5  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18002f8fa  mov     eax, ebx
0x18002f8fc  add     rsp, 48h
0x18002f900  pop     r15
0x18002f902  pop     r14
0x18002f904  pop     r12
0x18002f906  pop     rdi
0x18002f907  pop     rbx
0x18002f908  pop     rbp
0x18002f909  retn
```
