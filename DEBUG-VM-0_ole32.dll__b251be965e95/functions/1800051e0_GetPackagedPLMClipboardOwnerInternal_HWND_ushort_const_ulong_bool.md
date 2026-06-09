# GetPackagedPLMClipboardOwnerInternal(HWND__ *,ushort const * *,ulong *,bool *)

- ea: `0x1800051e0`
- end: `0x1800053d7`
- name: `?GetPackagedPLMClipboardOwnerInternal@@YAJPEAUHWND__@@PEAPEBGPEAKPEA_N@Z`
- size: `503`
- prototype: `HRESULT __fastcall(HWND__ *hWndClipboardOwner, const wchar_t **ppszPackageFullName, unsigned int *ppid, bool *pIsPLMManaged)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000e034`
- `0x180090230`

## callees

- `0x1800051e0`
- `0x1800053e0`
- `0x180019454`
- `0x180053014`
- `0x18008edb0`
- `0x180090068`

## import_xrefs

- `KERNELBASE!GetPackageFullName` at `0x180005339`
- `KERNELBASE!GetPackageFullName` at `0x180005339`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005389`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005389`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180005283`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180005283`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005381`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005381`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000525c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000525c`
- `USER32!GetWindowThreadProcessId` at `0x180005244`
- `USER32!GetWindowThreadProcessId` at `0x180005244`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800052fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800052fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000534e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000534e`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180005315`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180005315`

## pseudocode

```c
__int64 __fastcall GetPackagedPLMClipboardOwnerInternal(
        HWND__ *hWndClipboardOwner,
        wchar_t **ppszPackageFullName,
        unsigned int *ppid,
        bool *pIsPLMManaged)
{
  HRESULT Policy; // ebx
  DWORD v5; // r15d
  AppModelPolicy_PolicyValue v6; // edi
  HWND__ *v9; // rsi
  int ClipboardOwnerWindowProperty; // eax
  HANDLE v11; // rax
  AppModelPolicy_Type v12; // edx
  signed int LastError; // eax
  bool v14; // zf
  wchar_t *v15; // rax
  wchar_t *v16; // rsi
  LONG PackageFullName; // edi
  signed int v18; // eax
  HANDLE hProcess; // [rsp+20h] [rbp-10h]
  void *token; // [rsp+78h] [rbp+48h] BYREF
  AppModelPolicy_PolicyValue lifecyclePolicy; // [rsp+80h] [rbp+50h] BYREF
  bool *len; // [rsp+88h] [rbp+58h] BYREF

  len = pIsPLMManaged;
  Policy = 0;
  v5 = 0;
  LODWORD(token) = 0;
  v6 = AppModelPolicy_LifecycleManager_Unmanaged;
  lifecyclePolicy = AppModelPolicy_LifecycleManager_Unmanaged;
  *ppszPackageFullName = 0;
  *pIsPLMManaged = 0;
  v9 = hWndClipboardOwner;
  if ( ppid )
    *ppid = 0;
  if ( !hWndClipboardOwner
    || (ClipboardOwnerWindowProperty = GetClipboardOwnerWindowProperty(
                                         hWndClipboardOwner,
                                         (const wchar_t **)ppszPackageFullName,
                                         (unsigned int *)&token),
        v5 = (unsigned int)token,
        Policy = ClipboardOwnerWindowProperty,
        ClipboardOwnerWindowProperty >= 0) )
  {
    if ( GetWindowThreadProcessId(v9, 0) )
    {
      v11 = OpenProcess(0x400u, 0, v5);
      hProcess = v11;
      if ( v11 )
      {
        token = 0;
        if ( OpenProcessToken(v11, 8u, &token) )
        {
          Policy = AppModelPolicy_GetPolicy(token, v12, &lifecyclePolicy);
          CloseHandle(token);
          v6 = lifecyclePolicy;
        }
        else
        {
          LastError = GetLastError();
          Policy = LastError;
          if ( LastError > 0 )
            Policy = (unsigned __int16)LastError | 0x80070000;
          OleInternalOriginateError(Policy, 0x135u);
        }
        if ( Policy >= 0 && v6 == AppModelPolicy_LifecycleManager_ManagedByPLM )
        {
          v14 = *ppszPackageFullName == 0;
          *len = 1;
          if ( v14 )
          {
            LODWORD(len) = 127;
            v15 = (wchar_t *)CoTaskMemAlloc(0xFEu);
            v16 = v15;
            if ( v15 )
            {
              memset_0(v15, 0, 2LL * (unsigned int)len);
              PackageFullName = GetPackageFullName(hProcess, (UINT32 *)&len, v16);
              if ( PackageFullName )
              {
                CoTaskMemFree(v16);
                if ( PackageFullName != 15700 )
                {
                  if ( PackageFullName > 0 )
                    Policy = (unsigned __int16)PackageFullName | 0x80070000;
                  else
                    Policy = PackageFullName;
                  OleInternalOriginateError(Policy, 0x136u);
                }
              }
              else
              {
                *ppszPackageFullName = v16;
              }
            }
            else
            {
              Policy = -2147024882;
              RoOriginateError(2147942414LL, 0);
            }
            v9 = hWndClipboardOwner;
          }
        }
        CloseHandle(hProcess);
      }
      else
      {
        v18 = GetLastError();
        Policy = v18;
        if ( v18 > 0 )
          Policy = (unsigned __int16)v18 | 0x80070000;
        OleInternalOriginateError(Policy, 0x137u);
      }
    }
  }
  if ( ppid && Policy >= 0 )
    *ppid = v5;
  OleClipboardTracing::GetPackagedPLMClipboardOwnerInternalEtw(Policy, v9, (const wchar_t **)ppszPackageFullName, ppid);
  return (unsigned int)Policy;
}

```

## disassembly

```asm
0x1800051e0  mov     [rsp-38h+len], pIsPLMManaged
0x1800051e5  mov     [rsp-38h+arg_0], hWndClipboardOwner
0x1800051ea  push    rbp
0x1800051eb  push    rbx
0x1800051ec  push    rsi
0x1800051ed  push    rdi
0x1800051ee  push    r13
0x1800051f0  push    r14
0x1800051f2  push    r15
0x1800051f4  mov     rbp, rsp
0x1800051f7  sub     rsp, 30h
0x1800051fb  xor     ebx, ebx
0x1800051fd  xor     r15d, r15d
0x180005200  mov     dword ptr [rbp+token], r15d
0x180005204  mov     edi, 10000h
0x180005209  mov     [rbp+lifecyclePolicy], edi
0x18000520c  mov     r14, ppid
0x18000520f  mov     [ppszPackageFullName], rbx
0x180005212  mov     r13, ppszPackageFullName
0x180005215  mov     [pIsPLMManaged], bl
0x180005218  mov     rsi, hWndClipboardOwner
0x18000521b  test    ppid, ppid
0x18000521e  jz      short loc_180005223
0x180005220  mov     [ppid], ebx
0x180005223  test    rsi, rsi
0x180005226  jz      short loc_18000523F
0x180005228  lea     ppid, [rbp+token]; pdwProcessId
0x18000522c  call    ?GetClipboardOwnerWindowProperty@@YAJPEAUHWND__@@PEAPEBGPEAK@Z; GetClipboardOwnerWindowProperty(HWND__ *,ushort const * *,ulong *)
0x180005231  mov     r15d, dword ptr [rbp+token]
0x180005235  mov     ebx, eax
0x180005237  test    eax, eax
0x180005239  js      loc_1800053AA
0x18000523f  xor     edx, edx; lpdwProcessId
0x180005241  mov     hWndClipboardOwner, rsi; hWnd
0x180005244  call    cs:__imp_GetWindowThreadProcessId
0x18000524a  test    eax, eax
0x18000524c  jz      loc_1800053AA
0x180005252  mov     r8d, r15d; dwProcessId
0x180005255  xor     edx, edx; bInheritHandle
0x180005257  mov     ecx, 400h; dwDesiredAccess
0x18000525c  call    cs:__imp_OpenProcess
0x180005262  mov     [rbp+hProcess], rax
0x180005266  test    rax, rax
0x180005269  jz      loc_180005389
0x18000526f  lea     ppid, [rbp+token]; TokenHandle
0x180005273  mov     [rbp+token], 0
0x18000527b  mov     edx, 8; DesiredAccess
0x180005280  mov     hWndClipboardOwner, rax; ProcessHandle
0x180005283  call    cs:__imp_OpenProcessToken
0x180005289  test    eax, eax
0x18000528b  jz      short loc_1800052AB
0x18000528d  mov     hWndClipboardOwner, [rbp+token]; token
0x180005291  lea     ppid, [rbp+lifecyclePolicy]; token
0x180005295  call    ?AppModelPolicy_GetPolicy@@YAJPEAXW4AppModelPolicy_Type@@PEAW4AppModelPolicy_PolicyValue@@@Z; AppModelPolicy_GetPolicy(void *,AppModelPolicy_Type,AppModelPolicy_PolicyValue *)
0x18000529a  mov     hWndClipboardOwner, [rbp+token]; hObject
0x18000529e  mov     ebx, eax
0x1800052a0  call    cs:__imp_CloseHandle
0x1800052a6  mov     edi, [rbp+lifecyclePolicy]
0x1800052a9  jmp     short loc_1800052CC
0x1800052ab  call    cs:__imp_GetLastError
0x1800052b1  mov     ebx, eax
0x1800052b3  test    eax, eax
0x1800052b5  jle     short loc_1800052C0
0x1800052b7  movzx   ebx, ax
0x1800052ba  or      ebx, 80070000h
0x1800052c0  mov     edx, 135h; messageID
0x1800052c5  mov     ecx, ebx; hr
0x1800052c7  call    ?OleInternalOriginateError@@YAXJG@Z; OleInternalOriginateError(long,ushort)
0x1800052cc  test    ebx, ebx
0x1800052ce  js      loc_18000537D
0x1800052d4  cmp     edi, 10001h
0x1800052da  jnz     loc_18000537D
0x1800052e0  cmp     qword ptr [r13+0], 0
0x1800052e5  mov     rax, [rbp+len]
0x1800052e9  mov     byte ptr [rax], 1
0x1800052ec  jnz     loc_18000537D
0x1800052f2  mov     ecx, 0FEh; cb
0x1800052f7  mov     dword ptr [rbp+len], 7Fh
0x1800052fe  call    cs:__imp_CoTaskMemAlloc
0x180005304  mov     rsi, rax
0x180005307  test    rax, rax
0x18000530a  jnz     short loc_18000531D
0x18000530c  mov     ebx, 8007000Eh
0x180005311  xor     edx, edx
0x180005313  mov     ecx, ebx
0x180005315  call    cs:__imp_RoOriginateError
0x18000531b  jmp     short loc_180005379
0x18000531d  mov     r8d, dword ptr [rbp+len]
0x180005321  xor     edx, edx; Val
0x180005323  add     ppid, ppid; Size
0x180005326  mov     hWndClipboardOwner, rsi; void *
0x180005329  call    memset_0
0x18000532e  mov     hWndClipboardOwner, [rbp+hProcess]; hProcess
0x180005332  lea     ppszPackageFullName, [rbp+len]; packageFullNameLength
0x180005336  mov     ppid, rsi; packageFullName
0x180005339  call    cs:__imp_GetPackageFullName
0x18000533f  mov     edi, eax
0x180005341  test    eax, eax
0x180005343  jnz     short loc_18000534B
0x180005345  mov     [r13+0], rsi
0x180005349  jmp     short loc_180005379
0x18000534b  mov     hWndClipboardOwner, rsi; pv
0x18000534e  call    cs:__imp_CoTaskMemFree
0x180005354  cmp     edi, 3D54h
0x18000535a  jz      short loc_180005379
0x18000535c  test    edi, edi
0x18000535e  jg      short loc_180005364
0x180005360  mov     ebx, edi
0x180005362  jmp     short loc_18000536D
0x180005364  movzx   ebx, di
0x180005367  or      ebx, 80070000h
0x18000536d  mov     edx, 136h; messageID
0x180005372  mov     ecx, ebx; hr
0x180005374  call    ?OleInternalOriginateError@@YAXJG@Z; OleInternalOriginateError(long,ushort)
0x180005379  mov     rsi, [rbp+arg_0]
0x18000537d  mov     hWndClipboardOwner, [rbp+hProcess]; hObject
0x180005381  call    cs:__imp_CloseHandle
0x180005387  jmp     short loc_1800053AA
0x180005389  call    cs:__imp_GetLastError
0x18000538f  mov     ebx, eax
0x180005391  test    eax, eax
0x180005393  jle     short loc_18000539E
0x180005395  movzx   ebx, ax
0x180005398  or      ebx, 80070000h
0x18000539e  mov     edx, 137h; messageID
0x1800053a3  mov     ecx, ebx; hr
0x1800053a5  call    ?OleInternalOriginateError@@YAXJG@Z; OleInternalOriginateError(long,ushort)
0x1800053aa  test    r14, r14
0x1800053ad  jz      short loc_1800053B6
0x1800053af  test    ebx, ebx
0x1800053b1  js      short loc_1800053B6
0x1800053b3  mov     [r14], r15d
0x1800053b6  mov     pIsPLMManaged, r14; ppid
0x1800053b9  mov     ppid, r13; ppszPackageFullName
0x1800053bc  mov     ppszPackageFullName, rsi; hWndClipboardOwner
0x1800053bf  mov     ecx, ebx; hr
0x1800053c1  call    ?GetPackagedPLMClipboardOwnerInternalEtw@OleClipboardTracing@@SAXJPEAUHWND__@@PEAPEBGPEAK@Z; OleClipboardTracing::GetPackagedPLMClipboardOwnerInternalEtw(long,HWND__ *,ushort const * *,ulong *)
0x1800053c6  mov     eax, ebx
0x1800053c8  add     rsp, 30h
0x1800053cc  pop     r15
0x1800053ce  pop     r14
0x1800053d0  pop     r13
0x1800053d2  pop     rdi
0x1800053d3  pop     rsi
0x1800053d4  pop     rbx
0x1800053d5  pop     rbp
0x1800053d6  retn
```
