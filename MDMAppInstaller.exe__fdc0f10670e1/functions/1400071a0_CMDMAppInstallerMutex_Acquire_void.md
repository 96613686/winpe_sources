# CMDMAppInstallerMutex::Acquire(void)

- ea: `0x1400071a0`
- end: `0x1400072a2`
- name: `?Acquire@CMDMAppInstallerMutex@@QEAAJXZ`
- size: `258`
- prototype: `__int64 __fastcall(CMDMAppInstallerMutex *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140006dc8`

## callees

- `0x1400036ac`
- `0x1400055f8`
- `0x140006480`
- `0x1400071a0`
- `0x14000740c`
- `0x14001a8d0`

## import_xrefs

- `KERNEL32!CreateMutexW` at `0x140007203`
- `KERNEL32!CreateMutexW` at `0x140007203`
- `KERNEL32!ReleaseMutex` at `0x140007257`
- `KERNEL32!ReleaseMutex` at `0x140007257`
- `KERNEL32!CloseHandle` at `0x140007261`
- `KERNEL32!CloseHandle` at `0x140007261`
- `KERNEL32!GetLastError` at `0x140007216`
- `KERNEL32!GetLastError` at `0x140007216`

## string_xrefs

- `0x140007238`: `Failed to create mutex hr=0x%1!x!`
- `0x1400071bc`: `Global\MDMAppInstaller`

## pseudocode

```c
__int64 __fastcall CMDMAppInstallerMutex::Acquire(CMDMAppInstallerMutex *this)
{
  unsigned int v2; // edi
  const WCHAR *v3; // r8
  char *MutexW; // rax
  unsigned int Error; // eax
  void *v6; // rcx
  LPCWSTR lpName[4]; // [rsp+20h] [rbp-58h] BYREF
  _QWORD v9[4]; // [rsp+40h] [rbp-38h] BYREF

  std::wstring::wstring((__int64)lpName, (__int64)L"Global\\MDMAppInstaller");
  v9[3] = 7;
  v9[2] = 0;
  LOWORD(v9[0]) = 0;
  if ( *(_BYTE *)this )
  {
    v2 = 0;
  }
  else
  {
    v3 = (const WCHAR *)lpName;
    if ( lpName[3] >= (LPCWSTR)8 )
      v3 = lpName[0];
    MutexW = (char *)CreateMutexW(0, 0, v3);
    *((_QWORD *)this + 1) = MutexW;
    if ( (unsigned __int64)(MutexW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      Error = ResultFromLastError();
      LogError(L"Failed to create mutex hr=0x%1!x!", Error);
      v2 = -2147467259;
    }
    else
    {
      if ( GetLastError() != 183 )
      {
        v2 = 0;
        *(_BYTE *)this = 1;
        goto LABEL_13;
      }
      v2 = -2147024713;
    }
    if ( !*(_BYTE *)this )
    {
      v6 = (void *)*((_QWORD *)this + 1);
      if ( v6 )
      {
        ReleaseMutex(v6);
        CloseHandle(*((HANDLE *)this + 1));
      }
    }
  }
LABEL_13:
  std::wstring::_Tidy(v9, 1, 0);
  std::wstring::_Tidy(lpName, 1, 0);
  return v2;
}

```

## disassembly

```asm
0x1400071a0  mov     [rsp+arg_8], rbx
0x1400071a5  push    rdi
0x1400071a6  sub     rsp, 70h
0x1400071aa  mov     rax, cs:__security_cookie
0x1400071b1  xor     rax, rsp
0x1400071b4  mov     [rsp+78h+var_18], rax
0x1400071b9  mov     rbx, rcx
0x1400071bc  lea     rdx, aGlobalMdmappin_0; "Global\\MDMAppInstaller"
0x1400071c3  lea     rcx, [rsp+78h+lpName]
0x1400071c8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1400071cd  xor     eax, eax
0x1400071cf  mov     [rsp+78h+var_20], 7
0x1400071d8  mov     [rsp+78h+var_28], 0
0x1400071e1  mov     [rsp+78h+var_38], ax
0x1400071e6  cmp     [rbx], al
0x1400071e8  jz      short loc_1400071EE
0x1400071ea  xor     edi, edi
0x1400071ec  jmp     short loc_140007267
0x1400071ee  cmp     [rsp+78h+var_40], 8
0x1400071f4  lea     r8, [rsp+78h+lpName]
0x1400071f9  cmovnb  r8, [rsp+78h+lpName]; lpName
0x1400071ff  xor     edx, edx; bInitialOwner
0x140007201  xor     ecx, ecx; lpMutexAttributes
0x140007203  call    cs:__imp_CreateMutexW
0x140007209  mov     [rbx+8], rax
0x14000720d  dec     rax
0x140007210  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140007214  ja      short loc_140007231
0x140007216  call    cs:__imp_GetLastError
0x14000721c  cmp     eax, 0B7h
0x140007221  jnz     short loc_14000722A
0x140007223  mov     edi, 800700B7h
0x140007228  jmp     short loc_140007249
0x14000722a  xor     edi, edi
0x14000722c  mov     byte ptr [rbx], 1
0x14000722f  jmp     short loc_140007267
0x140007231  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x140007236  mov     edx, eax
0x140007238  lea     rcx, aFailedToCreate_2; "Failed to create mutex hr=0x%1!x!"
0x14000723f  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140007244  mov     edi, 80004005h
0x140007249  cmp     byte ptr [rbx], 0
0x14000724c  jnz     short loc_140007267
0x14000724e  mov     rcx, [rbx+8]; hMutex
0x140007252  test    rcx, rcx
0x140007255  jz      short loc_140007267
0x140007257  call    cs:__imp_ReleaseMutex
0x14000725d  mov     rcx, [rbx+8]; hObject
0x140007261  call    cs:__imp_CloseHandle
0x140007267  xor     r8d, r8d
0x14000726a  lea     rcx, [rsp+78h+var_38]
0x14000726f  mov     dl, 1
0x140007271  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140007276  xor     r8d, r8d
0x140007279  lea     rcx, [rsp+78h+lpName]
0x14000727e  mov     dl, 1
0x140007280  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140007285  mov     eax, edi
0x140007287  mov     rcx, [rsp+78h+var_18]
0x14000728c  xor     rcx, rsp; StackCookie
0x14000728f  call    __security_check_cookie
0x140007294  mov     rbx, [rsp+78h+arg_8]
0x14000729c  add     rsp, 70h
0x1400072a0  pop     rdi
0x1400072a1  retn
```
