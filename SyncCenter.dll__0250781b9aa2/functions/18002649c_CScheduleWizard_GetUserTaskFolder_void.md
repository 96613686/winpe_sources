# CScheduleWizard::_GetUserTaskFolder(void)

- ea: `0x18002649c`
- end: `0x180026565`
- name: `?_GetUserTaskFolder@CScheduleWizard@@AEAAJXZ`
- size: `201`
- prototype: `__int64 __fastcall(CScheduleWizard *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180026360`

## callees

- `0x18000b310`
- `0x180012e54`
- `0x1800133b0`
- `0x1800134dc`
- `0x18002649c`
- `0x180028648`
- `0x1800286bc`
- `0x18004ed94`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800264b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800264fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026550`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800264b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800264fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026550`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800264e8`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800264e8`

## pseudocode

```c
__int64 __fastcall CScheduleWizard::_GetUserTaskFolder(CScheduleWizard *this)
{
  int v2; // edx
  void *v3; // rcx
  DWORD v4; // r8d
  int Error; // ebx
  HLOCAL v6; // rdi
  struct ITaskService *v7; // rax
  struct ITaskFolder **v8; // r8
  struct ITaskFolder **v9; // r9
  LPWSTR StringSid; // [rsp+48h] [rbp+28h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp+30h] BYREF

  StringSid = 0;
  LocalFree(0);
  StringSid = 0;
  hMem = 0;
  Error = SHQueryToken<_TOKEN_USER>(v3, v2, v4, &hMem);
  if ( Error >= 0 )
  {
    v6 = hMem;
    if ( !ConvertSidToStringSidW(*(PSID *)hMem, &StringSid) )
      Error = ResultFromKnownLastError();
    LocalFree(v6);
    if ( Error >= 0 )
    {
      ATL::CComPtr<IDefaultExtractIconInit>::CComPtr<IDefaultExtractIconInit>(&hMem);
      v7 = (struct ITaskService *)ATL::CComPtrBase<ISyncClientFolderItemCache>::operator&(&hMem);
      Error = ScheduleHelpers::GetSyncCenterTaskFolder(*((ScheduleHelpers **)this + 175), v7, v8);
      if ( Error >= 0 )
        Error = ScheduleHelpers::GetOrCreateUserTaskFolder(
                  (ScheduleHelpers *)hMem,
                  (struct ITaskFolder *)StringSid,
                  (const unsigned __int16 *)this + 704,
                  v9);
      ATL::CComPtr<IDefaultExtractIconInit>::~CComPtr<IDefaultExtractIconInit>((__int64)&hMem);
    }
  }
  LocalFree(StringSid);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18002649c  mov     [rsp-18h+arg_0], rbx
0x1800264a1  push    rbp
0x1800264a2  push    rsi
0x1800264a3  push    rdi
0x1800264a4  mov     rbp, rsp
0x1800264a7  sub     rsp, 20h
0x1800264ab  mov     rsi, rcx
0x1800264ae  mov     [rbp+StringSid], 0
0x1800264b6  xor     ecx, ecx; hMem
0x1800264b8  call    cs:__imp_LocalFree
0x1800264be  lea     r9, [rbp+hMem]
0x1800264c2  mov     [rbp+StringSid], 0
0x1800264ca  mov     [rbp+hMem], 0
0x1800264d2  call    ??$SHQueryToken@U_TOKEN_USER@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@HPEAPEAU_TOKEN_USER@@@Z; SHQueryToken<_TOKEN_USER>(void *,_TOKEN_INFORMATION_CLASS,int,_TOKEN_USER * *)
0x1800264d7  mov     ebx, eax
0x1800264d9  test    eax, eax
0x1800264db  js      short loc_18002654C
0x1800264dd  mov     rdi, [rbp+hMem]
0x1800264e1  lea     rdx, [rbp+StringSid]; StringSid
0x1800264e5  mov     rcx, [rdi]; Sid
0x1800264e8  call    cs:__imp_ConvertSidToStringSidW
0x1800264ee  test    eax, eax
0x1800264f0  jnz     short loc_1800264F9
0x1800264f2  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800264f7  mov     ebx, eax
0x1800264f9  mov     rcx, rdi; hMem
0x1800264fc  call    cs:__imp_LocalFree
0x180026502  test    ebx, ebx
0x180026504  js      short loc_18002654C
0x180026506  lea     rcx, [rbp+hMem]; void *
0x18002650a  call    ??0?$CComPtr@UIDefaultExtractIconInit@@@ATL@@QEAA@XZ; ATL::CComPtr<IDefaultExtractIconInit>::CComPtr<IDefaultExtractIconInit>(void)
0x18002650f  lea     rcx, [rbp+hMem]; void *
0x180026513  call    ??I?$CComPtrBase@UISyncClientFolderItemCache@@@ATL@@QEAAPEAPEAUISyncClientFolderItemCache@@XZ; ATL::CComPtrBase<ISyncClientFolderItemCache>::operator&(void)
0x180026518  mov     rcx, [rsi+578h]; this
0x18002651f  mov     rdx, rax; struct ITaskService *
0x180026522  call    ?GetSyncCenterTaskFolder@ScheduleHelpers@@YAJPEAUITaskService@@PEAPEAUITaskFolder@@@Z; ScheduleHelpers::GetSyncCenterTaskFolder(ITaskService *,ITaskFolder * *)
0x180026527  mov     ebx, eax
0x180026529  test    eax, eax
0x18002652b  js      short loc_180026543
0x18002652d  mov     rdx, [rbp+StringSid]; struct ITaskFolder *
0x180026531  lea     r8, [rsi+580h]; unsigned __int16 *
0x180026538  mov     rcx, [rbp+hMem]; this
0x18002653c  call    ?GetOrCreateUserTaskFolder@ScheduleHelpers@@YAJPEAUITaskFolder@@PEBGPEAPEAU2@@Z; ScheduleHelpers::GetOrCreateUserTaskFolder(ITaskFolder *,ushort const *,ITaskFolder * *)
0x180026541  mov     ebx, eax
0x180026543  lea     rcx, [rbp+hMem]
0x180026547  call    ??1?$CComPtr@UIDefaultExtractIconInit@@@ATL@@QEAA@XZ; ATL::CComPtr<IDefaultExtractIconInit>::~CComPtr<IDefaultExtractIconInit>(void)
0x18002654c  mov     rcx, [rbp+StringSid]; hMem
0x180026550  call    cs:__imp_LocalFree
0x180026556  mov     eax, ebx
0x180026558  mov     rbx, [rsp+20h+arg_0]
0x18002655d  add     rsp, 20h
0x180026561  pop     rdi
0x180026562  pop     rsi
0x180026563  pop     rbp
0x180026564  retn
```
