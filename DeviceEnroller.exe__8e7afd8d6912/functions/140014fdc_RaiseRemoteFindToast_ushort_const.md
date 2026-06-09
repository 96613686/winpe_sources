# RaiseRemoteFindToast(ushort const *)

- ea: `0x140014fdc`
- end: `0x14001510e`
- name: `?RaiseRemoteFindToast@@YAJPEBG@Z`
- size: `306`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140019a6c`

## callees

- `0x140009594`
- `0x1400095b4`
- `0x1400127f0`
- `0x140014fdc`

## import_xrefs

- `DMCmnUtils!DmRaiseToastNotification` at `0x1400150db`
- `DMCmnUtils!DmRaiseToastNotification` at `0x1400150db`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140014ffd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140014ffd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400150f6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400150f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400150a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400150eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400150a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400150eb`

## string_xrefs

- `0x140014ff6`: `DMAppsRes.dll`
- `0x1400150bf`: `protocol`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RaiseRemoteFindToast(const unsigned __int16 *a1)
{
  HMODULE Library; // rax
  const char *v3; // r9
  HMODULE v4; // rbx
  int v6; // eax
  unsigned int v7; // edi
  __int64 v8; // rdx
  void *v9; // rdi
  unsigned int v10; // esi
  int v11; // [rsp+20h] [rbp-38h]
  LPVOID pv[5]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  Library = LoadLibraryExW(L"DMAppsRes.dll", 0, 0x800u);
  v4 = Library;
  if ( !Library )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x3D4,
             (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\exe\\main.cpp",
             v3);
  memset(pv, 0, 24);
  if ( a1 )
  {
    v6 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeResMessage(
           pv,
           Library,
           26107);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 986;
      goto LABEL_8;
    }
LABEL_10:
    v9 = pv[0];
    v10 = DmRaiseToastNotification(
            L"Windows.SystemToast.DeviceManagement",
            L"RemoteFind",
            L"ms-settings:workplace",
            L"protocol",
            0,
            (const unsigned __int16 *)pv[0]);
    if ( v9 )
      CoTaskMemFree(v9);
    v7 = v10;
    goto LABEL_13;
  }
  v6 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeResMessage(
         pv,
         Library,
         26108);
  v7 = v6;
  if ( v6 >= 0 )
    goto LABEL_10;
  v8 = 991;
LABEL_8:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\exe\\main.cpp",
    (const char *)(unsigned int)v6,
    v11);
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
LABEL_13:
  FreeLibrary(v4);
  return v7;
}

```

## disassembly

```asm
0x140014fdc  mov     [rsp+arg_0], rbx
0x140014fe1  mov     [rsp+arg_10], rsi
0x140014fe6  push    rdi
0x140014fe7  sub     rsp, 50h
0x140014feb  mov     rdi, rcx
0x140014fee  xor     edx, edx; hFile
0x140014ff0  mov     r8d, 800h; dwFlags
0x140014ff6  lea     rcx, aDmappsresDll; "DMAppsRes.dll"
0x140014ffd  call    cs:__imp_LoadLibraryExW
0x140015003  mov     rbx, rax
0x140015006  mov     [rsp+58h+arg_8], rax
0x14001500b  test    rax, rax
0x14001500e  jnz     short loc_14001502C
0x140015010  mov     rcx, [rsp+58h]; this
0x140015015  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x14001501c  mov     edx, 3D4h; void *
0x140015021  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140015026  nop
0x140015027  jmp     loc_1400150FE
0x14001502c  mov     [rsp+58h+pv], 0
0x140015035  mov     [rsp+58h+var_20], 0
0x14001503e  mov     [rsp+58h+var_18], 0
0x140015047  mov     rdx, rbx
0x14001504a  lea     rcx, [rsp+58h+pv]
0x14001504f  test    rdi, rdi
0x140015052  jz      short loc_14001506F
0x140015054  mov     r9, rdi
0x140015057  mov     r8d, 65FBh
0x14001505d  call    ?InitializeResMessage@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@HZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeResMessage(HINSTANCE__ *,int,...)
0x140015062  mov     edi, eax
0x140015064  test    eax, eax
0x140015066  jns     short loc_1400150AC
0x140015068  mov     edx, 3DAh
0x14001506d  jmp     short loc_140015085
0x14001506f  mov     r8d, 65FCh
0x140015075  call    ?InitializeResMessage@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@HZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeResMessage(HINSTANCE__ *,int,...)
0x14001507a  mov     edi, eax
0x14001507c  test    eax, eax
0x14001507e  jns     short loc_1400150AC
0x140015080  mov     edx, 3DFh; void *
0x140015085  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x14001508c  mov     r9d, eax; char *
0x14001508f  mov     rcx, [rsp+58h]; this
0x140015094  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140015099  nop
0x14001509a  mov     rcx, [rsp+58h+pv]; pv
0x14001509f  test    rcx, rcx
0x1400150a2  jz      short loc_1400150F3
0x1400150a4  call    cs:__imp_CoTaskMemFree
0x1400150aa  jmp     short loc_1400150F3
0x1400150ac  mov     rdi, [rsp+58h+pv]
0x1400150b1  mov     [rsp+58h+var_30], rdi
0x1400150b6  mov     [rsp+58h+var_38], 0
0x1400150bf  lea     r9, aProtocol; "protocol"
0x1400150c6  lea     r8, aMsSettingsWork; "ms-settings:workplace"
0x1400150cd  lea     rdx, aRemotefind; "RemoteFind"
0x1400150d4  lea     rcx, aWindowsSystemt; "Windows.SystemToast.DeviceManagement"
0x1400150db  call    cs:__imp_?DmRaiseToastNotification@@YAJPEBG00000@Z; DmRaiseToastNotification(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x1400150e1  mov     esi, eax
0x1400150e3  test    rdi, rdi
0x1400150e6  jz      short loc_1400150F1
0x1400150e8  mov     rcx, rdi; pv
0x1400150eb  call    cs:__imp_CoTaskMemFree
0x1400150f1  mov     edi, esi
0x1400150f3  mov     rcx, rbx; hLibModule
0x1400150f6  call    cs:__imp_FreeLibrary
0x1400150fc  mov     eax, edi
0x1400150fe  mov     rbx, [rsp+58h+arg_0]
0x140015103  mov     rsi, [rsp+58h+arg_10]
0x140015108  add     rsp, 50h
0x14001510c  pop     rdi
0x14001510d  retn
```
