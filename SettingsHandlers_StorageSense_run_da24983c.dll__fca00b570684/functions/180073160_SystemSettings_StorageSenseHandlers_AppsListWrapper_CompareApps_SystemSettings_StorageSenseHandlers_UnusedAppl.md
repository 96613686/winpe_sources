# SystemSettings::StorageSenseHandlers::AppsListWrapper::CompareApps(SystemSettings::StorageSenseHandlers::UnusedApplicationItem const *,SystemSettings::StorageSenseHandlers::UnusedApplicationItem const *)

- ea: `0x180073160`
- end: `0x1800732ec`
- name: `?CompareApps@AppsListWrapper@StorageSenseHandlers@SystemSettings@@AEBA_NPEBVUnusedApplicationItem@23@0@Z`
- size: `396`
- prototype: `bool __fastcall(SystemSettings::StorageSenseHandlers::AppsListWrapper *__hidden this, const struct SystemSettings::StorageSenseHandlers::UnusedApplicationItem *, const struct SystemSettings::StorageSenseHandlers::UnusedApplicationItem *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800725bc`

## callees

- `0x18001f784`
- `0x180073160`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073193`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800731fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073193`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800731fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800732a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800732a8`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180073237`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180073237`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180073189`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800731f2`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180073189`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800731f2`

## string_xrefs

- `0x1800731a5`: `CleanupRecommendations`
- `0x18007320e`: `CleanupRecommendations`
- `0x180073250`: `CleanupRecommendations`
- `0x1800732b2`: `CleanupRecommendations`
- `0x1800731ca`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\recommenderengine.cpp`

## pseudocode

```c
bool __fastcall SystemSettings::StorageSenseHandlers::AppsListWrapper::CompareApps(
        SystemSettings::StorageSenseHandlers::AppsListWrapper *this,
        const struct SystemSettings::StorageSenseHandlers::UnusedApplicationItem *a2,
        const struct SystemSettings::StorageSenseHandlers::UnusedApplicationItem *a3)
{
  int LastError; // eax
  __int64 v6; // rdx
  LONG v8; // eax
  unsigned __int64 v9; // rax
  HSTRING v10; // rdx
  HSTRING v11; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  SystemSettings::StorageSenseHandlers::AppsListWrapper *result; // [rsp+40h] [rbp+8h] BYREF
  struct _FILETIME FileTime; // [rsp+48h] [rbp+10h] BYREF
  FILETIME FileTime1; // [rsp+58h] [rbp+20h] BYREF

  result = this;
  FileTime1 = 0;
  if ( !SystemTimeToFileTime((const SYSTEMTIME *)((char *)a2 + 378), &FileTime1) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v6 = 1521;
    goto LABEL_5;
  }
  FileTime = 0;
  if ( !SystemTimeToFileTime((const SYSTEMTIME *)((char *)a3 + 378), &FileTime) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v6 = 1528;
    goto LABEL_5;
  }
  v8 = CompareFileTime(&FileTime1, &FileTime);
  if ( ((v8 + 1) & 0xFFFFFFFD) == 0 )
    return v8 == -1;
  if ( v8 )
  {
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x605,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommenderengine.cpp",
      (const char *)0x80070272LL,
      (int)"%hs",
      "CleanupRecommendations");
    return 0;
  }
  v9 = *((_QWORD *)a2 + 46);
  if ( v9 != *((_QWORD *)a3 + 46) )
    return v9 > *((_QWORD *)a3 + 46);
  v10 = (HSTRING)*((_QWORD *)a3 + 51);
  v11 = (HSTRING)*((_QWORD *)a2 + 51);
  LODWORD(result) = 0;
  LastError = WindowsCompareStringOrdinal(v11, v10, (INT32 *)&result);
  if ( LastError < 0 )
  {
    v6 = 1561;
LABEL_5:
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommenderengine.cpp",
      (const char *)(unsigned int)LastError,
      (int)"%hs",
      "CleanupRecommendations");
    return 0;
  }
  return (_DWORD)result == -1;
}

```

## disassembly

```asm
0x180073160  mov     rax, rsp
0x180073163  mov     [rax+18h], rbx
0x180073167  mov     [rax+8], rcx
0x18007316b  push    rdi
0x18007316c  sub     rsp, 30h
0x180073170  mov     rdi, rdx
0x180073173  mov     qword ptr [rax+20h], 0
0x18007317b  lea     rcx, [rdx+17Ah]; lpSystemTime
0x180073182  mov     rbx, r8
0x180073185  lea     rdx, [rax+20h]; lpFileTime
0x180073189  call    cs:__imp_SystemTimeToFileTime
0x18007318f  test    eax, eax
0x180073191  jnz     short loc_1800731DD
0x180073193  call    cs:__imp_GetLastError
0x180073199  test    eax, eax
0x18007319b  jle     short loc_1800731A5
0x18007319d  movzx   eax, ax
0x1800731a0  or      eax, 80070000h
0x1800731a5  lea     rdx, aCleanuprecomme; "CleanupRecommendations"
0x1800731ac  mov     [rsp+38h+var_10], rdx; char *
0x1800731b1  lea     rdx, aHs; "%hs"
0x1800731b8  mov     qword ptr [rsp+38h+var_18], rdx; int
0x1800731bd  mov     edx, 5F1h; void *
0x1800731c2  mov     r9d, eax; char *
0x1800731c5  mov     rcx, [rsp+38h]; this
0x1800731ca  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\coresettinghandlers"...
0x1800731d1  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800731d6  xor     al, al
0x1800731d8  jmp     loc_1800732E1
0x1800731dd  lea     rcx, [rbx+17Ah]; lpSystemTime
0x1800731e4  mov     qword ptr [rsp+38h+FileTime.dwLowDateTime], 0
0x1800731ed  lea     rdx, [rsp+38h+FileTime]; lpFileTime
0x1800731f2  call    cs:__imp_SystemTimeToFileTime
0x1800731f8  test    eax, eax
0x1800731fa  jnz     short loc_18007322D
0x1800731fc  call    cs:__imp_GetLastError
0x180073202  test    eax, eax
0x180073204  jle     short loc_18007320E
0x180073206  movzx   eax, ax
0x180073209  or      eax, 80070000h
0x18007320e  lea     rdx, aCleanuprecomme; "CleanupRecommendations"
0x180073215  mov     [rsp+38h+var_10], rdx
0x18007321a  lea     rdx, aHs; "%hs"
0x180073221  mov     qword ptr [rsp+38h+var_18], rdx
0x180073226  mov     edx, 5F8h
0x18007322b  jmp     short loc_1800731C2
0x18007322d  lea     rdx, [rsp+38h+FileTime]; lpFileTime2
0x180073232  lea     rcx, [rsp+38h+FileTime1]; lpFileTime1
0x180073237  call    cs:__imp_CompareFileTime
0x18007323d  lea     ecx, [rax+1]
0x180073240  test    ecx, 0FFFFFFFDh
0x180073246  jz      loc_1800732DB
0x18007324c  test    eax, eax
0x18007324e  jz      short loc_180073278
0x180073250  lea     rdx, aCleanuprecomme; "CleanupRecommendations"
0x180073257  mov     r9d, 80070272h
0x18007325d  mov     [rsp+38h+var_10], rdx
0x180073262  lea     rdx, aHs; "%hs"
0x180073269  mov     qword ptr [rsp+38h+var_18], rdx
0x18007326e  mov     edx, 605h
0x180073273  jmp     loc_1800731C5
0x180073278  mov     rax, [rdi+170h]
0x18007327f  cmp     rax, [rbx+170h]
0x180073286  jz      short loc_18007328D
0x180073288  setnbe  al
0x18007328b  jmp     short loc_1800732E1
0x18007328d  mov     rdx, [rbx+198h]; string2
0x180073294  lea     r8, [rsp+38h+result]; result
0x180073299  mov     rcx, [rdi+198h]; string1
0x1800732a0  mov     dword ptr [rsp+38h+result], 0
0x1800732a8  call    cs:__imp_WindowsCompareStringOrdinal
0x1800732ae  test    eax, eax
0x1800732b0  jns     short loc_1800732D4
0x1800732b2  lea     rdx, aCleanuprecomme; "CleanupRecommendations"
0x1800732b9  mov     [rsp+38h+var_10], rdx
0x1800732be  lea     rdx, aHs; "%hs"
0x1800732c5  mov     qword ptr [rsp+38h+var_18], rdx
0x1800732ca  mov     edx, 619h
0x1800732cf  jmp     loc_1800731C2
0x1800732d4  cmp     dword ptr [rsp+38h+result], 0FFFFFFFFh
0x1800732d9  jmp     short loc_1800732DE
0x1800732db  cmp     eax, 0FFFFFFFFh
0x1800732de  setz    al
0x1800732e1  mov     rbx, [rsp+38h+arg_10]
0x1800732e6  add     rsp, 30h
0x1800732ea  pop     rdi
0x1800732eb  retn
```
