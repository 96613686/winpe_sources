# SystemSettings::StorageSenseHandlers::RecommendationSingleton::GetStorageSenseDynamicDatabase(IInspectable * *)

- ea: `0x180075690`
- end: `0x180075838`
- name: `?GetStorageSenseDynamicDatabase@RecommendationSingleton@StorageSenseHandlers@SystemSettings@@QEAAJPEAPEAUIInspectable@@@Z`
- size: `424`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers::RecommendationSingleton *__hidden this, struct IInspectable **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180064a40`

## callees

- `0x180006e50`
- `0x18000c964`
- `0x180012374`
- `0x180036ae4`
- `0x18005190c`
- `0x180075690`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800756d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800756d5`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800756cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800756cb`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180075702`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180075702`

## string_xrefs

- `0x180075760`: `CleanupRecommendations`
- `0x1800757b3`: `CleanupRecommendations`
- `0x18007577b`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\recommenderengine.cpp`
- `0x1800757ce`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\recommenderengine.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
signed int __fastcall SystemSettings::StorageSenseHandlers::RecommendationSingleton::GetStorageSenseDynamicDatabase(
        SystemSettings::StorageSenseHandlers::RecommendationSingleton *this,
        struct IInspectable **a2)
{
  signed int result; // eax
  int v5; // ebx
  struct IInspectable *v6; // rax
  struct IInspectable *v7; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v8; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+260h] [rbp+160h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+488h] [rbp+388h]

  if ( GetWindowsDirectoryW(Buffer, 0x104u) && GetVolumePathNameW(Buffer, szVolumePathName, 0x104u) )
  {
    v8 = 0;
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v8);
    v5 = SystemSettings::StorageSenseHandlers::CStorageSenseDynamicDatabase::CreateInstance(
           *((_QWORD *)this + 29),
           0,
           0,
           szVolumePathName,
           0,
           0,
           &v8);
    if ( v5 >= 0 )
    {
      v7 = 0;
      v5 = Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::CStorageSenseDynamicDatabase>::As<IInspectable>(
             &v8,
             &v7);
      if ( v5 >= 0 )
      {
        v6 = v7;
        v7 = 0;
        *a2 = v6;
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v7);
        v5 = 0;
      }
      else
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x75B,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommenderengine.cpp",
          (const char *)(unsigned int)v5,
          (int)"%hs",
          "CleanupRecommendations");
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v7);
      }
    }
    else
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x758,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommenderengine.cpp",
        (const char *)(unsigned int)v5,
        (int)"%hs",
        "CleanupRecommendations");
    }
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v8);
    return v5;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180075690  mov     [rsp-8+arg_10], rbx
0x180075695  mov     [rsp-8+arg_18], rdi
0x18007569a  push    rbp
0x18007569b  lea     rbp, [rsp-380h]
0x1800756a3  sub     rsp, 480h
0x1800756aa  mov     rax, cs:__security_cookie
0x1800756b1  xor     rax, rsp
0x1800756b4  mov     [rbp+380h+var_10], rax
0x1800756bb  mov     rdi, rdx
0x1800756be  mov     rbx, rcx
0x1800756c1  mov     edx, 104h; uSize
0x1800756c6  lea     rcx, [rsp+480h+Buffer]; lpBuffer
0x1800756cb  call    cs:__imp_GetWindowsDirectoryW
0x1800756d1  test    eax, eax
0x1800756d3  jnz     short loc_1800756F0
0x1800756d5  call    cs:__imp_GetLastError
0x1800756db  test    eax, eax
0x1800756dd  jle     loc_180075814
0x1800756e3  movzx   eax, ax
0x1800756e6  or      eax, 80070000h
0x1800756eb  jmp     loc_180075814
0x1800756f0  mov     r8d, 104h; cchBufferLength
0x1800756f6  lea     rdx, [rbp+380h+szVolumePathName]; lpszVolumePathName
0x1800756fd  lea     rcx, [rsp+480h+Buffer]; lpszFileName
0x180075702  call    cs:__imp_GetVolumePathNameW
0x180075708  test    eax, eax
0x18007570a  jz      short loc_1800756D5
0x18007570c  mov     [rsp+480h+var_438], 0
0x180075715  lea     rcx, [rsp+480h+var_438]
0x18007571a  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18007571f  lea     rax, [rsp+480h+var_438]
0x180075724  mov     [rsp+480h+var_450], rax
0x180075729  mov     [rsp+480h+var_458], 0
0x180075732  mov     qword ptr [rsp+480h+var_460], 0
0x18007573b  lea     r9, [rbp+380h+szVolumePathName]
0x180075742  xor     r8d, r8d
0x180075745  xor     edx, edx
0x180075747  mov     rcx, [rbx+0E8h]
0x18007574e  call    ?CreateInstance@CStorageSenseDynamicDatabase@StorageSenseHandlers@SystemSettings@@SAJPEAUIUser@System@Windows@@W4_STORAGE_DEVICE_TYPE@@KPEBG_K3PEAPEAV123@@Z; SystemSettings::StorageSenseHandlers::CStorageSenseDynamicDatabase::CreateInstance(Windows::System::IUser *,_STORAGE_DEVICE_TYPE,ulong,ushort const *,unsigned __int64,unsigned __int64,SystemSettings::StorageSenseHandlers::CStorageSenseDynamicDatabase * *)
0x180075753  mov     ebx, eax
0x180075755  test    eax, eax
0x180075757  jns     short loc_18007578E
0x180075759  mov     rcx, [rbp+388h]; this
0x180075760  lea     rax, aCleanuprecomme; "CleanupRecommendations"
0x180075767  mov     [rsp+480h+var_458], rax; char *
0x18007576c  lea     rax, aHs; "%hs"
0x180075773  mov     qword ptr [rsp+480h+var_460], rax; int
0x180075778  mov     r9d, ebx; char *
0x18007577b  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\coresettinghandlers"...
0x180075782  mov     edx, 758h; void *
0x180075787  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18007578c  jmp     short loc_180075808
0x18007578e  mov     [rsp+480h+var_440], 0
0x180075797  lea     rdx, [rsp+480h+var_440]
0x18007579c  lea     rcx, [rsp+480h+var_438]
0x1800757a1  call    ??$As@UIInspectable@@@?$ComPtr@VCStorageSenseDynamicDatabase@StorageSenseHandlers@SystemSettings@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIInspectable@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::CStorageSenseDynamicDatabase>::As<IInspectable>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IInspectable>>)
0x1800757a6  mov     ebx, eax
0x1800757a8  test    eax, eax
0x1800757aa  jns     short loc_1800757EB
0x1800757ac  mov     rcx, [rbp+388h]; this
0x1800757b3  lea     rax, aCleanuprecomme; "CleanupRecommendations"
0x1800757ba  mov     [rsp+480h+var_458], rax; char *
0x1800757bf  lea     rax, aHs; "%hs"
0x1800757c6  mov     qword ptr [rsp+480h+var_460], rax; int
0x1800757cb  mov     r9d, ebx; char *
0x1800757ce  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\coresettinghandlers"...
0x1800757d5  mov     edx, 75Bh; void *
0x1800757da  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800757df  lea     rcx, [rsp+480h+var_440]
0x1800757e4  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800757e9  jmp     short loc_180075808
0x1800757eb  mov     rax, [rsp+480h+var_440]
0x1800757f0  mov     [rsp+480h+var_440], 0
0x1800757f9  mov     [rdi], rax
0x1800757fc  lea     rcx, [rsp+480h+var_440]
0x180075801  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180075806  xor     ebx, ebx
0x180075808  lea     rcx, [rsp+480h+var_438]
0x18007580d  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180075812  mov     eax, ebx
0x180075814  mov     rcx, [rbp+380h+var_10]
0x18007581b  xor     rcx, rsp; StackCookie
0x18007581e  call    __security_check_cookie
0x180075823  lea     r11, [rsp+480h+var_s0]
0x18007582b  mov     rbx, [r11+20h]
0x18007582f  mov     rdi, [r11+28h]
0x180075833  mov     rsp, r11
0x180075836  pop     rbp
0x180075837  retn
```
