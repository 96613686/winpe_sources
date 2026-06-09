# CSyncMgrSynchronize::UpdateItems(ulong,_GUID const &,ulong,uchar const *)

- ea: `0x18001b020`
- end: `0x18001b258`
- name: `?UpdateItems@CSyncMgrSynchronize@@UEAAJKAEBU_GUID@@KPEBE@Z`
- size: `568`
- prototype: `__int64 __fastcall(CSyncMgrSynchronize *this, int, const struct _GUID *, unsigned int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180007f44`
- `0x18000a5e4`
- `0x18001b020`
- `0x18001c938`
- `0x18005292a`
- `0x180052950`
- `0x180053010`

## import_xrefs

- `SHELL32!SHGetKnownFolderIDList` at `0x18001b213`
- `SHELL32!SHGetKnownFolderIDList` at `0x18001b213`
- `SHELL32!ShellExecuteExW` at `0x18001b22b`
- `SHELL32!ShellExecuteExW` at `0x18001b22b`
- `SHELL32!__imp_ILFree` at `0x18001b235`
- `SHELL32!__imp_ILFree` at `0x18001b235`
- `SHLWAPI!__imp_SHStringFromGUIDW` at `0x18001b0a8`
- `SHLWAPI!__imp_SHStringFromGUIDW` at `0x18001b0a8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001b0c2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001b0c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b1a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b1a7`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18001b19d`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18001b19d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001b08b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001b08b`

## pseudocode

```c
__int64 __fastcall CSyncMgrSynchronize::UpdateItems(
        CSyncMgrSynchronize *this,
        int a2,
        const struct _GUID *a3,
        unsigned int a4,
        unsigned __int8 *a5)
{
  HRESULT v7; // edi
  DWORD v8; // r8d
  HANDLE v9; // rsi
  CLegacyCookie *v10; // rax
  CLegacyCookie *v11; // rax
  CLegacyCookie *v12; // rsi
  LPVOID v13; // rcx
  LPITEMIDLIST ppidl; // [rsp+40h] [rbp-71h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-69h] BYREF
  DWORD dwindex; // [rsp+50h] [rbp-61h] BYREF
  HANDLE pHandles; // [rsp+58h] [rbp-59h] BYREF
  SHELLEXECUTEINFOW pExecInfo; // [rsp+60h] [rbp-51h] BYREF

  v7 = -2147024809;
  if ( (a2 & 0xFFFFFFF9) == 0 )
  {
    if ( (a2 & 2) != 0 )
    {
      v8 = *((_DWORD *)this + 5);
      ppv = 0;
      v7 = CoCreateInstance(&CLSID_SyncMgrControl, 0, v8, &GUID_9b63616c_36b2_46bc_959f_c1593952d19b, &ppv);
      if ( v7 >= 0 )
      {
        v7 = SHStringFromGUIDW(a3, &pExecInfo, 39);
        if ( v7 >= 0 )
        {
          pHandles = CreateEventW(0, 0, 0, 0);
          v9 = pHandles;
          if ( pHandles )
          {
            ppidl = 0;
            if ( !a5 )
              goto LABEL_11;
            v7 = -2147024882;
            v10 = (CLegacyCookie *)operator new(0x28u);
            if ( v10 )
            {
              v11 = CLegacyCookie::CLegacyCookie(v10, a4, a5, v9);
              v12 = v11;
              if ( v11 )
              {
                v7 = (**(__int64 (__fastcall ***)(CLegacyCookie *, GUID *, LPITEMIDLIST *))v11)(
                       v11,
                       &GUID_00000000_0000_0000_c000_000000000046,
                       &ppidl);
                (*(void (__fastcall **)(CLegacyCookie *))(*(_QWORD *)v12 + 16LL))(v12);
              }
            }
            if ( v7 >= 0 )
LABEL_11:
              v7 = (*(__int64 (__fastcall **)(LPVOID, SHELLEXECUTEINFOW *, _QWORD))(*(_QWORD *)ppv + 24LL))(
                     ppv,
                     &pExecInfo,
                     0);
            SafeRelease<ISyncMgrSyncItemContainer>(&ppidl);
            if ( v7 >= 0 && a5 )
            {
              dwindex = 0;
              CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, &pHandles, &dwindex);
            }
            CloseHandle(pHandles);
          }
        }
        v13 = ppv;
        ppv = 0;
        if ( v13 )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v13 + 16LL))(v13);
      }
    }
    else
    {
      ppidl = 0;
      memset_0(&pExecInfo, 0, sizeof(pExecInfo));
      pExecInfo.cbSize = 112;
      pExecInfo.lpVerb = L"open";
      pExecInfo.fMask = 4;
      pExecInfo.nShow = 1;
      v7 = SHGetKnownFolderIDList(&FOLDERID_SyncManagerFolder, 0, 0, &ppidl);
      if ( v7 >= 0 )
      {
        pExecInfo.lpIDList = ppidl;
        ShellExecuteExW(&pExecInfo);
        ILFree(ppidl);
      }
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001b020  push    rbp
0x18001b022  push    rsi
0x18001b023  push    rdi
0x18001b024  push    r14
0x18001b026  push    r15
0x18001b028  lea     rbp, [rsp-2Fh]
0x18001b02d  sub     rsp, 0E0h
0x18001b034  mov     rax, cs:__security_cookie
0x18001b03b  xor     rax, rsp
0x18001b03e  mov     [rbp+4Fh+var_30], rax
0x18001b042  mov     r14, [rbp+4Fh+arg_20]
0x18001b046  mov     r15d, r9d
0x18001b049  mov     rsi, r8
0x18001b04c  mov     edi, 80070057h
0x18001b051  test    edx, 0FFFFFFF9h
0x18001b057  jnz     loc_18001B23B
0x18001b05d  test    dl, 2
0x18001b060  jz      loc_18001B1CC
0x18001b066  mov     r8d, [rcx+14h]; dwClsContext
0x18001b06a  lea     rax, [rbp+4Fh+var_B8]
0x18001b06e  lea     rcx, CLSID_SyncMgrControl; rclsid
0x18001b075  mov     [rsp+100h+ppv], rax; ppv
0x18001b07a  lea     r9, _GUID_9b63616c_36b2_46bc_959f_c1593952d19b; riid
0x18001b081  mov     [rbp+4Fh+var_B8], 0
0x18001b089  xor     edx, edx; pUnkOuter
0x18001b08b  call    cs:__imp_CoCreateInstance
0x18001b091  mov     edi, eax
0x18001b093  test    eax, eax
0x18001b095  js      loc_18001B23B
0x18001b09b  mov     r8d, 27h ; '''
0x18001b0a1  lea     rdx, [rbp+4Fh+pExecInfo]
0x18001b0a5  mov     rcx, rsi
0x18001b0a8  call    cs:__imp_SHStringFromGUIDW
0x18001b0ae  mov     edi, eax
0x18001b0b0  test    eax, eax
0x18001b0b2  js      loc_18001B1AD
0x18001b0b8  xor     r9d, r9d; lpName
0x18001b0bb  xor     r8d, r8d; bInitialState
0x18001b0be  xor     edx, edx; bManualReset
0x18001b0c0  xor     ecx, ecx; lpEventAttributes
0x18001b0c2  call    cs:__imp_CreateEventW
0x18001b0c8  mov     [rbp+4Fh+pHandles], rax
0x18001b0cc  mov     rsi, rax
0x18001b0cf  test    rax, rax
0x18001b0d2  jz      loc_18001B1AD
0x18001b0d8  xor     r9d, r9d
0x18001b0db  mov     [rbp+4Fh+ppidl], r9
0x18001b0df  test    r14, r14
0x18001b0e2  jz      short loc_18001B142
0x18001b0e4  lea     ecx, [r9+28h]; unsigned __int64
0x18001b0e8  mov     edi, 8007000Eh
0x18001b0ed  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b0f2  test    rax, rax
0x18001b0f5  jz      short loc_18001B13A
0x18001b0f7  mov     r9, rsi; void *
0x18001b0fa  mov     r8, r14; unsigned __int8 *
0x18001b0fd  mov     edx, r15d; unsigned int
0x18001b100  mov     rcx, rax; this
0x18001b103  call    ??0CLegacyCookie@@QEAA@KPEBEPEAX@Z; CLegacyCookie::CLegacyCookie(ulong,uchar const *,void *)
0x18001b108  mov     rsi, rax
0x18001b10b  test    rax, rax
0x18001b10e  jz      short loc_18001B13A
0x18001b110  mov     rcx, [rax]
0x18001b113  lea     r8, [rbp+4Fh+ppidl]
0x18001b117  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18001b11e  mov     rax, [rcx]
0x18001b121  mov     rcx, rsi
0x18001b124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b129  mov     rcx, [rsi]
0x18001b12c  mov     edi, eax
0x18001b12e  mov     rax, [rcx+10h]
0x18001b132  mov     rcx, rsi
0x18001b135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b13a  test    edi, edi
0x18001b13c  js      short loc_18001B16C
0x18001b13e  mov     r9, [rbp+4Fh+ppidl]
0x18001b142  mov     rcx, [rbp+4Fh+var_B8]
0x18001b146  lea     rdx, [rbp+4Fh+pExecInfo]
0x18001b14a  mov     [rsp+100h+var_D8], 0
0x18001b153  xor     r8d, r8d
0x18001b156  mov     dword ptr [rsp+100h+ppv], 0
0x18001b15e  mov     rax, [rcx]
0x18001b161  mov     rax, [rax+18h]
0x18001b165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b16a  mov     edi, eax
0x18001b16c  lea     rcx, [rbp+4Fh+ppidl]
0x18001b170  call    ??$SafeRelease@UISyncMgrSyncItemContainer@@@@YAXPEAPEAUISyncMgrSyncItemContainer@@@Z; SafeRelease<ISyncMgrSyncItemContainer>(ISyncMgrSyncItemContainer * *)
0x18001b175  test    edi, edi
0x18001b177  js      short loc_18001B1A3
0x18001b179  test    r14, r14
0x18001b17c  jz      short loc_18001B1A3
0x18001b17e  lea     rax, [rbp+4Fh+dwindex]
0x18001b182  mov     [rbp+4Fh+dwindex], 0
0x18001b189  lea     r9, [rbp+4Fh+pHandles]; pHandles
0x18001b18d  mov     [rsp+100h+ppv], rax; lpdwindex
0x18001b192  mov     r8d, 1; cHandles
0x18001b198  or      edx, 0FFFFFFFFh; dwTimeout
0x18001b19b  xor     ecx, ecx; dwFlags
0x18001b19d  call    cs:__imp_CoWaitForMultipleHandles
0x18001b1a3  mov     rcx, [rbp+4Fh+pHandles]; hObject
0x18001b1a7  call    cs:__imp_CloseHandle
0x18001b1ad  mov     rcx, [rbp+4Fh+var_B8]
0x18001b1b1  mov     [rbp+4Fh+var_B8], 0
0x18001b1b9  test    rcx, rcx
0x18001b1bc  jz      short loc_18001B23B
0x18001b1be  mov     rax, [rcx]
0x18001b1c1  mov     rax, [rax+10h]
0x18001b1c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b1ca  jmp     short loc_18001B23B
0x18001b1cc  mov     edi, 70h ; 'p'
0x18001b1d1  mov     [rbp+4Fh+ppidl], 0
0x18001b1d9  mov     r8d, edi; Size
0x18001b1dc  lea     rcx, [rbp+4Fh+pExecInfo]; void *
0x18001b1e0  xor     edx, edx; Val
0x18001b1e2  call    memset_0
0x18001b1e7  lea     rax, aOpen; "open"
0x18001b1ee  mov     [rbp+4Fh+pExecInfo.cbSize], edi
0x18001b1f1  lea     r9, [rbp+4Fh+ppidl]; ppidl
0x18001b1f5  mov     [rbp+4Fh+pExecInfo.lpVerb], rax
0x18001b1f9  xor     r8d, r8d; hToken
0x18001b1fc  mov     [rbp+4Fh+pExecInfo.fMask], 4
0x18001b203  xor     edx, edx; dwFlags
0x18001b205  mov     [rbp+4Fh+pExecInfo.nShow], 1
0x18001b20c  lea     rcx, FOLDERID_SyncManagerFolder; rfid
0x18001b213  call    cs:__imp_SHGetKnownFolderIDList
0x18001b219  mov     edi, eax
0x18001b21b  test    eax, eax
0x18001b21d  js      short loc_18001B23B
0x18001b21f  mov     rax, [rbp+4Fh+ppidl]
0x18001b223  lea     rcx, [rbp+4Fh+pExecInfo]; pExecInfo
0x18001b227  mov     [rbp+4Fh+pExecInfo.lpIDList], rax
0x18001b22b  call    cs:__imp_ShellExecuteExW
0x18001b231  mov     rcx, [rbp+4Fh+ppidl]; pidl
0x18001b235  call    cs:__imp_ILFree
0x18001b23b  mov     eax, edi
0x18001b23d  mov     rcx, [rbp+4Fh+var_30]
0x18001b241  xor     rcx, rsp; StackCookie
0x18001b244  call    __security_check_cookie
0x18001b249  add     rsp, 0E0h
0x18001b250  pop     r15
0x18001b252  pop     r14
0x18001b254  pop     rdi
0x18001b255  pop     rsi
0x18001b256  pop     rbp
0x18001b257  retn
```
