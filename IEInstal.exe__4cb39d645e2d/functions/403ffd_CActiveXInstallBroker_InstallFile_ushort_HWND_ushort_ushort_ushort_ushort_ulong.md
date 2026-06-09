# CActiveXInstallBroker::InstallFile(ushort *,HWND__ *,ushort *,ushort *,ushort *,ushort *,ulong)

- ea: `0x403ffd`
- end: `0x40420e`
- name: `?InstallFile@CActiveXInstallBroker@@QAGJPAGPAUHWND__@@0000K@Z`
- size: `529`
- prototype: `int __userpurge@<eax>(const unsigned __int16 *@<edx>, int@<ecx>, CActiveXInstallBroker *this, unsigned __int16 *, HWND, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x405db0`

## callees

- `0x402eb9`
- `0x402ed3`
- `0x403094`
- `0x403ffd`
- `0x406e47`
- `0x407142`
- `0x4076da`
- `0x408480`
- `0x408a2f`
- `0x40d1d0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x404160`
- `KERNEL32!GetProcAddress` at `0x404160`
- `KERNEL32!LoadLibraryExW` at `0x404134`
- `KERNEL32!LoadLibraryExW` at `0x404134`
- `KERNEL32!GetLastError` at `0x404141`
- `KERNEL32!GetLastError` at `0x404141`
- `ole32!CoTaskMemFree` at `0x4041ea`
- `ole32!CoTaskMemFree` at `0x4041f8`
- `ole32!CoTaskMemFree` at `0x4041ea`
- `ole32!CoTaskMemFree` at `0x4041f8`
- `urlmon!CoInternetSetFeatureEnabled` at `0x4041ae`
- `urlmon!CoInternetSetFeatureEnabled` at `0x4041ca`
- `urlmon!CoInternetSetFeatureEnabled` at `0x4041ae`
- `urlmon!CoInternetSetFeatureEnabled` at `0x4041ca`
- `urlmon!__imp__CoInternetApproveExtension@8` at `0x4041be`
- `urlmon!__imp__CoInternetApproveExtension@8` at `0x4041be`

## string_xrefs

- `0x40412f`: `IEAdvpack.Dll`
- `0x40415a`: `AdvInstallFileW`

## pseudocode

```c
int __userpurge CActiveXInstallBroker::InstallFile@<eax>(
        const unsigned __int16 *a1@<edx>,
        int a2@<ecx>,
        CActiveXInstallBroker *this,
        unsigned __int16 *a4,
        HWND a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        unsigned __int16 *a8,
        unsigned __int16 *a9,
        unsigned int a10)
{
  unsigned __int16 *v10; // ebx
  int HasExtensionW; // esi
  int v14; // eax
  unsigned __int16 *v15; // ebx
  int v16; // ecx
  BOOL v17; // eax
  HMODULE Library; // eax
  signed int LastError; // eax
  HRESULT (__stdcall *AdvInstallFileW)(HWND, LPCWSTR, LPCWSTR, LPCWSTR, LPCWSTR, DWORD, DWORD); // eax
  const unsigned __int16 *v22; // [esp+0h] [ebp-14h]
  const unsigned __int16 *v23; // [esp+0h] [ebp-14h]
  const unsigned __int16 *v24; // [esp+0h] [ebp-14h]
  const unsigned __int16 *v25; // [esp+0h] [ebp-14h]
  unsigned __int16 **v26; // [esp+4h] [ebp-10h]
  unsigned __int16 **v27; // [esp+4h] [ebp-10h]
  unsigned __int16 *v28; // [esp+Ch] [ebp-8h] BYREF
  LPVOID pv; // [esp+10h] [ebp-4h] BYREF

  v10 = 0;
  v28 = 0;
  pv = 0;
  if ( !CLock::Lock((CLock *)a2) )
  {
    HasExtensionW = -2147024882;
    goto LABEL_38;
  }
  if ( *(int *)(a2 + 28) < 2 )
  {
    HasExtensionW = -2147019873;
    goto LABEL_38;
  }
  if ( !a1 || !a5 || !a7 )
  {
    HasExtensionW = -2147024809;
    goto LABEL_34;
  }
  v14 = wcscmp(a1, *(const unsigned __int16 **)(a2 + 36));
  if ( v14 )
    v14 = v14 < 0 ? -1 : 1;
  if ( v14 )
  {
    HasExtensionW = -2147024891;
    goto LABEL_38;
  }
  if ( !CatDirAndFileW((int)a4, (const unsigned __int16 *)&v28, v22, v26) )
  {
LABEL_32:
    HasExtensionW = -2147024882;
    goto LABEL_34;
  }
  v15 = v28;
  HasExtensionW = VerifyFileHasExtensionW(v23);
  if ( HasExtensionW >= 0 )
  {
    HasExtensionW = CActiveXInstallBroker::FileIsAuthorized((CActiveXInstallBroker *)a2, v15, v16);
    if ( HasExtensionW >= 0 )
    {
      v17 = CatDirAndFileW((int)a6, (const unsigned __int16 *)&pv, v24, v27);
      v10 = (unsigned __int16 *)pv;
      if ( v17 )
      {
        HasExtensionW = VerifyFileHasExtensionW(v25);
        if ( HasExtensionW < 0 )
          goto LABEL_34;
        if ( !*(_DWORD *)(a2 + 84) && !ContainingPathIsTamperProof(v10) )
          goto LABEL_28;
        HasExtensionW = AddToFileListW((int)v10, (LPVOID **)(a2 + 76));
        if ( HasExtensionW >= 0 )
        {
          Library = *(HMODULE *)(a2 + 68);
          if ( !Library
            && (Library = LoadLibraryExW(L"IEAdvpack.Dll", 0, 0x800u), (*(_DWORD *)(a2 + 68) = Library) == 0)
            || (AdvInstallFileW = (HRESULT (__stdcall *)(HWND, LPCWSTR, LPCWSTR, LPCWSTR, LPCWSTR, DWORD, DWORD))GetProcAddress(Library, "AdvInstallFileW")) == 0 )
          {
            LastError = GetLastError();
            HasExtensionW = (unsigned __int16)LastError | 0x80070000;
            if ( LastError <= 0 )
              HasExtensionW = LastError;
            goto LABEL_34;
          }
          HasExtensionW = ((int (__thiscall *)(HRESULT (__stdcall *)(HWND, LPCWSTR, LPCWSTR, LPCWSTR, LPCWSTR, DWORD, DWORD), CActiveXInstallBroker *, unsigned __int16 *, HWND, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, _DWORD))AdvInstallFileW)(
                            AdvInstallFileW,
                            this,
                            a4,
                            a5,
                            a6,
                            a7,
                            a8,
                            0);
          if ( HasExtensionW >= 0 )
          {
            HasExtensionW = EnsureACILCanReadFile((int)a6, (int)a7);
            if ( HasExtensionW >= 0 )
            {
              if ( CoInternetSetFeatureEnabled(FEATURE_ADDON_MANAGEMENT, 2u, 1) >= 0 )
              {
                CoInternetApproveExtension(a2 + 48, 1);
                CoInternetSetFeatureEnabled(FEATURE_ADDON_MANAGEMENT, 2u, 0);
              }
              *(_DWORD *)(a2 + 28) = 7;
              goto LABEL_34;
            }
LABEL_28:
            HasExtensionW = -2147024891;
          }
        }
LABEL_34:
        if ( v10 )
          CoTaskMemFree(v10);
        goto LABEL_36;
      }
      goto LABEL_32;
    }
  }
LABEL_36:
  if ( v28 )
    CoTaskMemFree(v28);
LABEL_38:
  CLock::Unlock((CLock *)a2);
  return HasExtensionW;
}

```

## disassembly

```asm
0x403ffd  mov     edi, edi
0x403fff  push    ebp
0x404000  mov     ebp, esp
0x404002  push    ecx
0x404003  push    ecx
0x404004  push    ebx
0x404005  push    esi; unsigned __int16 *
0x404006  push    edi; unsigned __int16 *
0x404007  xor     ebx, ebx
0x404009  mov     [ebp+var_8], 0
0x404010  mov     esi, edx
0x404012  mov     [ebp+pv], ebx
0x404015  mov     edi, ecx
0x404017  call    ?Lock@CLock@@QAEHXZ; CLock::Lock(void)
0x40401c  test    eax, eax
0x40401e  jnz     short loc_40402A
0x404020  mov     esi, 8007000Eh
0x404025  jmp     loc_4041FE
0x40402a  cmp     dword ptr [edi+1Ch], 2
0x40402e  jge     short loc_40403A
0x404030  mov     esi, 8007139Fh
0x404035  jmp     loc_4041FE
0x40403a  test    esi, esi
0x40403c  jz      loc_4041E0
0x404042  cmp     [ebp+arg_8], ebx
0x404045  jz      loc_4041E0
0x40404b  cmp     [ebp+arg_10], ebx
0x40404e  jz      loc_4041E0
0x404054  mov     eax, [edi+24h]
0x404057  mov     cx, [esi]
0x40405a  cmp     cx, [eax]
0x40405d  jnz     short loc_40407D
0x40405f  test    cx, cx
0x404062  jz      short loc_404079
0x404064  mov     cx, [esi+2]
0x404068  cmp     cx, [eax+2]
0x40406c  jnz     short loc_40407D
0x40406e  add     esi, 4
0x404071  add     eax, 4
0x404074  test    cx, cx
0x404077  jnz     short loc_404057
0x404079  xor     eax, eax
0x40407b  jmp     short loc_404082
0x40407d  sbb     eax, eax
0x40407f  or      eax, 1
0x404082  test    eax, eax
0x404084  jz      short loc_404090
0x404086  mov     esi, 80070005h
0x40408b  jmp     loc_4041FE
0x404090  mov     edx, [ebp+arg_8]
0x404093  lea     eax, [ebp+var_8]
0x404096  mov     ecx, [ebp+arg_4]
0x404099  push    eax; unsigned __int16 *
0x40409a  call    ?CatDirAndFileW@@YGHPBG0PAPAG@Z; CatDirAndFileW(ushort const *,ushort const *,ushort * *)
0x40409f  test    eax, eax
0x4040a1  jz      loc_4041D9
0x4040a7  mov     ebx, [ebp+var_8]
0x4040aa  mov     ecx, ebx
0x4040ac  call    ?VerifyFileHasExtensionW@@YGJPBG@Z; VerifyFileHasExtensionW(ushort const *)
0x4040b1  mov     esi, eax
0x4040b3  test    esi, esi
0x4040b5  js      loc_4041F0
0x4040bb  push    ecx; int
0x4040bc  push    ebx; unsigned __int16 *
0x4040bd  mov     ecx, edi; this
0x4040bf  call    ?FileIsAuthorized@CActiveXInstallBroker@@AAEJPBGH@Z; CActiveXInstallBroker::FileIsAuthorized(ushort const *,int)
0x4040c4  mov     esi, eax
0x4040c6  test    esi, esi
0x4040c8  js      loc_4041F0
0x4040ce  mov     edx, [ebp+arg_10]
0x4040d1  lea     eax, [ebp+pv]
0x4040d4  mov     ecx, [ebp+arg_C]
0x4040d7  push    eax; unsigned __int16 *
0x4040d8  call    ?CatDirAndFileW@@YGHPBG0PAPAG@Z; CatDirAndFileW(ushort const *,ushort const *,ushort * *)
0x4040dd  mov     ebx, [ebp+pv]
0x4040e0  test    eax, eax
0x4040e2  jz      loc_4041D9
0x4040e8  mov     ecx, ebx
0x4040ea  call    ?VerifyFileHasExtensionW@@YGJPBG@Z; VerifyFileHasExtensionW(ushort const *)
0x4040ef  mov     esi, eax
0x4040f1  test    esi, esi
0x4040f3  js      loc_4041E5
0x4040f9  cmp     dword ptr [edi+54h], 0
0x4040fd  jnz     short loc_40410E
0x4040ff  mov     ecx, ebx
0x404101  call    ?ContainingPathIsTamperProof@@YGHPBG@Z; ContainingPathIsTamperProof(ushort const *)
0x404106  test    eax, eax
0x404108  jz      loc_4041A1
0x40410e  lea     edx, [edi+4Ch]
0x404111  mov     ecx, ebx
0x404113  call    ?AddToFileListW@@YGJPBGPAPAUsFNAME@@@Z; AddToFileListW(ushort const *,sFNAME * *)
0x404118  mov     esi, eax
0x40411a  test    esi, esi
0x40411c  js      loc_4041E5
0x404122  mov     eax, [edi+44h]
0x404125  test    eax, eax
0x404127  jnz     short loc_40415A
0x404129  push    800h; dwFlags
0x40412e  push    eax; hFile
0x40412f  push    offset LibFileName; "IEAdvpack.Dll"
0x404134  call    ds:__imp__LoadLibraryExW@12; LoadLibraryExW(x,x,x)
0x40413a  mov     [edi+44h], eax
0x40413d  test    eax, eax
0x40413f  jnz     short loc_40415A
0x404141  call    ds:__imp__GetLastError@0; GetLastError()
0x404147  movzx   esi, ax
0x40414a  or      esi, 80070000h
0x404150  test    eax, eax
0x404152  cmovle  esi, eax
0x404155  jmp     loc_4041E5
0x40415a  push    offset aAdvinstallfile; "AdvInstallFileW"
0x40415f  push    eax; hModule
0x404160  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x404166  mov     esi, eax
0x404168  test    esi, esi
0x40416a  jz      short loc_404141
0x40416c  push    0
0x40416e  push    [ebp+arg_14]
0x404171  mov     ecx, esi
0x404173  push    [ebp+arg_10]
0x404176  push    [ebp+arg_C]
0x404179  push    [ebp+arg_8]
0x40417c  push    [ebp+arg_4]
0x40417f  push    [ebp+this]
0x404182  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x404188  call    esi
0x40418a  mov     esi, eax
0x40418c  test    esi, esi
0x40418e  js      short loc_4041E5
0x404190  mov     edx, [ebp+arg_10]
0x404193  mov     ecx, [ebp+arg_C]
0x404196  call    ?EnsureACILCanReadFile@@YGJPBG0@Z; EnsureACILCanReadFile(ushort const *,ushort const *)
0x40419b  mov     esi, eax
0x40419d  test    esi, esi
0x40419f  jns     short loc_4041A8
0x4041a1  mov     esi, 80070005h
0x4041a6  jmp     short loc_4041E5
0x4041a8  push    1; fEnable
0x4041aa  push    2; dwFlags
0x4041ac  push    0Dh; FeatureEntry
0x4041ae  call    ds:__imp__CoInternetSetFeatureEnabled@12; CoInternetSetFeatureEnabled(x,x,x)
0x4041b4  test    eax, eax
0x4041b6  js      short loc_4041D0
0x4041b8  push    1
0x4041ba  lea     eax, [edi+30h]
0x4041bd  push    eax
0x4041be  call    ds:__imp__CoInternetApproveExtension@8; CoInternetApproveExtension(x,x)
0x4041c4  push    0; fEnable
0x4041c6  push    2; dwFlags
0x4041c8  push    0Dh; FeatureEntry
0x4041ca  call    ds:__imp__CoInternetSetFeatureEnabled@12; CoInternetSetFeatureEnabled(x,x,x)
0x4041d0  mov     dword ptr [edi+1Ch], 7
0x4041d7  jmp     short loc_4041E5
0x4041d9  mov     esi, 8007000Eh
0x4041de  jmp     short loc_4041E5
0x4041e0  mov     esi, 80070057h
0x4041e5  test    ebx, ebx
0x4041e7  jz      short loc_4041F0
0x4041e9  push    ebx; pv
0x4041ea  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x4041f0  mov     eax, [ebp+var_8]
0x4041f3  test    eax, eax
0x4041f5  jz      short loc_4041FE
0x4041f7  push    eax; pv
0x4041f8  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x4041fe  mov     ecx, edi; this
0x404200  call    ?Unlock@CLock@@QAEHXZ; CLock::Unlock(void)
0x404205  pop     edi
0x404206  mov     eax, esi
0x404208  pop     esi
0x404209  pop     ebx
0x40420a  leave
0x40420b  retn    18h
```
