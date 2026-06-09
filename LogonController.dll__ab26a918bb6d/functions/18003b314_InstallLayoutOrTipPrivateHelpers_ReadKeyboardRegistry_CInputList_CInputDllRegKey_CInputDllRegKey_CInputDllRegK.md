# InstallLayoutOrTipPrivateHelpers::ReadKeyboardRegistry(CInputList &,CInputDllRegKey &,CInputDllRegKey &,CInputDllRegKey &,CInputDllRegKey &)

- ea: `0x18003b314`
- end: `0x18003b850`
- name: `?ReadKeyboardRegistry@InstallLayoutOrTipPrivateHelpers@@SAXAEAVCInputList@@AEAVCInputDllRegKey@@111@Z`
- size: `1340`
- prototype: `void __fastcall(struct CInputList *this, struct CInputDllRegKey *, struct CInputDllRegKey *, struct CInputDllRegKey *, struct CInputDllRegKey *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180005500`
- `0x180096a78`

## callees

- `0x180004b70`
- `0x180007ff0`
- `0x18003b314`
- `0x18003b860`
- `0x18006c000`
- `0x18006caa0`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003b3ae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003b6a2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003b3ae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003b6a2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003b53e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003b53e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b419`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b481`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b70e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b728`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b419`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b481`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b70e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b728`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003b401`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003b6f1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003b401`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003b6f1`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18003b386`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18003b67a`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18003b386`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18003b67a`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18003b4d7`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18003b4d7`

## pseudocode

```c
void __fastcall InstallLayoutOrTipPrivateHelpers::ReadKeyboardRegistry(
        struct CInputList *this,
        struct CInputDllRegKey *a2,
        struct CInputDllRegKey *a3,
        struct CInputDllRegKey *a4,
        struct CInputDllRegKey *a5)
{
  HKEY v5; // rbx
  struct CInputDllRegKey *v6; // r15
  struct CInputDllRegKey *v7; // r14
  struct CInputList *v8; // r12
  LSTATUS v9; // eax
  HKEY v10; // rdi
  DWORD v11; // r13d
  struct InputContainer *v12; // rax
  struct InputContainer *v13; // rbx
  LSTATUS v14; // eax
  LSTATUS Value; // eax
  unsigned int v16; // esi
  struct InputContainer *NextEmptyEntry; // rax
  struct InputContainer *v18; // rbx
  unsigned int v19; // eax
  __int64 v20; // r9
  int v21; // esi
  bool v22; // al
  __int64 v23; // r9
  HKEY v24; // r15
  LSTATUS v25; // eax
  LSTATUS v26; // esi
  HKEY v27; // r14
  bool v28; // si
  int v29; // edx
  unsigned int i; // r8d
  __int64 v31; // r9
  __int64 v32; // rcx
  __int64 v33; // rcx
  int v34; // edx
  unsigned int v35; // r8d
  __int64 v36; // r9
  __int64 v37; // rcx
  DWORD cchValueName[2]; // [rsp+50h] [rbp-B0h] BYREF
  DWORD Type[2]; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  DWORD dwDisposition; // [rsp+68h] [rbp-98h] BYREF
  DWORD lpdwDisposition; // [rsp+6Ch] [rbp-94h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  struct CInputDllRegKey *v44; // [rsp+78h] [rbp-88h]
  struct CInputList *v45; // [rsp+80h] [rbp-80h]
  struct CInputDllRegKey *v46; // [rsp+88h] [rbp-78h]
  struct CInputDllRegKey *v47; // [rsp+90h] [rbp-70h]
  WCHAR SubKey[12]; // [rsp+98h] [rbp-68h] BYREF
  BYTE Data[2]; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t String[12]; // [rsp+C8h] [rbp-38h] BYREF
  wchar_t v51[16]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR ValueName[256]; // [rsp+100h] [rbp+0h] BYREF

  v5 = (HKEY)*((_QWORD *)a2 + 1);
  v6 = a5;
  v7 = a3;
  v44 = a4;
  v8 = this;
  v46 = a3;
  v45 = this;
  v47 = a5;
  hKey = 0;
  phkResult = 0;
  if ( v5 == HKEY_CURRENT_USER && !RegOpenCurrentUser(0x20019u, &phkResult) )
    v5 = phkResult;
  v9 = RegOpenKeyExW(v5, &sourceString, 0, 0x20019u, &hKey);
  if ( v9 )
  {
    v10 = 0;
    if ( v9 == 5 )
    {
      dwDisposition = 0;
      if ( !RegCreateKeyExW(v5, &sourceString, 0, 0, 4u, 0x20019u, 0, &hKey, &dwDisposition) )
        v10 = hKey;
    }
  }
  else
  {
    v10 = hKey;
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  v11 = 0;
  if ( v10 )
  {
    while ( 1 )
    {
      cchValueName[0] = 256;
      v14 = RegEnumValueW(v10, v11, ValueName, cchValueName, 0, 0, 0, 0);
      *(WCHAR *)((char *)ValueName + (v14 == 0 ? 0x1FE : 0)) = 0;
      if ( v14 )
        break;
      ++v11;
      if ( o_wcstoul_0(ValueName, 0, 10) )
      {
        cchValueName[0] = 18;
        Type[0] = 0;
        Value = RegQueryValueExW(v10, ValueName, 0, Type, Data, cchValueName);
        *(_WORD *)&Data[Value == 0 ? 0x10 : 0] = 0;
        if ( !Value )
        {
          v16 = o_wcstoul_0((const wchar_t *)Data, 0, 16);
          if ( v16 )
          {
            NextEmptyEntry = CInputList::GetNextEmptyEntry((const void **)v8);
            v18 = NextEmptyEntry;
            if ( NextEmptyEntry )
            {
              *((_DWORD *)NextEmptyEntry + 3) = 1;
              *((_DWORD *)NextEmptyEntry + 1) = v16;
              *(_WORD *)NextEmptyEntry = v16;
              if ( !(*(unsigned int (__fastcall **)(struct CInputDllRegKey *, wchar_t *, BYTE *, __int64))(*(_QWORD *)v7 + 8LL))(
                      v7,
                      String,
                      Data,
                      9) )
              {
                v19 = o_wcstoul_0(String, 0, 16);
                *((_DWORD *)v18 + 2) = *((_DWORD *)v18 + 1);
                *((_DWORD *)v18 + 1) = v19;
              }
              v20 = *(unsigned __int16 *)v18;
              v21 = *((_DWORD *)v18 + 1);
              *((_DWORD *)v18 + 3) = 1;
              *((_BYTE *)v18 + 16) = 1;
              StringCchPrintfW(SubKey, 9u, L"%08x", v20);
              if ( (*(unsigned int (__fastcall **)(struct CInputDllRegKey *, wchar_t *, WCHAR *, __int64))(*(_QWORD *)v44 + 8LL))(
                     v44,
                     v51,
                     SubKey,
                     9) )
              {
                v22 = 0;
              }
              else
              {
                v22 = o_wcstoul_0(v51, 0, 16) == v21;
              }
              v23 = *((unsigned int *)v18 + 1);
              *((_BYTE *)v18 + 18) = v22;
              StringCchPrintfW(SubKey, 9u, L"%08x", v23);
              v24 = (HKEY)*((_QWORD *)v6 + 1);
              *(_QWORD *)Type = 0;
              *(_QWORD *)cchValueName = 0;
              if ( v24 == HKEY_CURRENT_USER && !RegOpenCurrentUser(0x20019u, (PHKEY)cchValueName) )
                v24 = *(HKEY *)cchValueName;
              v25 = RegOpenKeyExW(v24, SubKey, 0, 0x20019u, (PHKEY)Type);
              v26 = v25;
              if ( !v25
                || (v27 = 0, v25 == 5)
                && (lpdwDisposition = 0,
                    (v26 = RegCreateKeyExW(v24, SubKey, 0, 0, 4u, 0x20019u, 0, (PHKEY)Type, &lpdwDisposition)) == 0) )
              {
                v27 = *(HKEY *)Type;
                v26 = 0;
              }
              if ( *(_QWORD *)cchValueName )
                RegCloseKey(*(HKEY *)cchValueName);
              v28 = v26 == 0;
              if ( v27 )
                RegCloseKey(v27);
              *((_BYTE *)v18 + 17) = v28;
              *((_WORD *)v18 + 10) = 123;
              v29 = 1;
              for ( i = 0; i < 0x14; ++i )
              {
                if ( v29 >= 36 )
                  break;
                v31 = v29;
                v32 = *((unsigned __int8 *)qword_1800B0EC0 + (int)i);
                if ( (_BYTE)v32 == 45 )
                {
                  *((_WORD *)v18 + v29 + 10) = 45;
                }
                else
                {
                  ++v29;
                  *((_WORD *)v18 + v31 + 10) = word_1800B0E90[(unsigned __int64)*((unsigned __int8 *)&GUID_NULL.Data1
                                                                                + v32) >> 4];
                  *((_WORD *)v18 + v29 + 10) = word_1800B0E90[*((_BYTE *)&GUID_NULL.Data1 + v32) & 0xF];
                }
                ++v29;
              }
              v33 = v29;
              v34 = 1;
              v35 = 0;
              *(_DWORD *)((char *)v18 + 2 * v33 + 20) = 125;
              *((_WORD *)v18 + 49) = 123;
              do
              {
                if ( v34 >= 36 )
                  break;
                v36 = v34;
                v37 = *((unsigned __int8 *)qword_1800B0EC0 + (int)v35);
                if ( (_BYTE)v37 == 45 )
                {
                  *((_WORD *)v18 + v34 + 49) = 45;
                }
                else
                {
                  ++v34;
                  *((_WORD *)v18 + v36 + 49) = word_1800B0E90[(unsigned __int64)*((unsigned __int8 *)&GUID_NULL.Data1
                                                                                + v37) >> 4];
                  *((_WORD *)v18 + v34 + 49) = word_1800B0E90[*((_BYTE *)&GUID_NULL.Data1 + v37) & 0xF];
                }
                ++v35;
                ++v34;
              }
              while ( v35 < 0x14 );
              v8 = v45;
              v7 = v46;
              v6 = v47;
              *(_DWORD *)((char *)v18 + 2 * v34 + 98) = 125;
            }
          }
        }
      }
    }
  }
  if ( !*((_DWORD *)v8 + 1) )
  {
    v12 = CInputList::GetNextEmptyEntry((const void **)v8);
    v13 = v12;
    if ( v12 )
    {
      *((_DWORD *)v12 + 3) = 1;
      *((_WORD *)v12 + 8) = 257;
      *((_DWORD *)v12 + 1) = 1033;
      *(_WORD *)v12 = 1033;
      CLSIDToStringW(&GUID_NULL, (unsigned __int16 *)v12 + 10);
      CLSIDToStringW(&GUID_NULL, (unsigned __int16 *)v13 + 49);
    }
  }
  if ( v10 )
    RegCloseKey(v10);
}

```

## disassembly

```asm
0x18003b314  push    rbp
0x18003b316  push    rbx
0x18003b317  push    rsi
0x18003b318  push    rdi
0x18003b319  push    r12
0x18003b31b  push    r13
0x18003b31d  push    r14
0x18003b31f  push    r15
0x18003b321  lea     rbp, [rsp-218h]
0x18003b329  sub     rsp, 318h
0x18003b330  mov     rax, cs:__security_cookie
0x18003b337  xor     rax, rsp
0x18003b33a  mov     [rbp+250h+var_50], rax
0x18003b341  mov     rbx, [rdx+8]
0x18003b345  xor     esi, esi
0x18003b347  mov     r15, [rbp+250h+arg_20]
0x18003b34e  mov     r14, r8
0x18003b351  mov     [rsp+350h+var_2D8], r9
0x18003b356  mov     r12, rcx
0x18003b359  mov     [rbp+250h+var_2C8], r8
0x18003b35d  mov     r13d, 20019h
0x18003b363  mov     [rbp+250h+var_2D0], rcx
0x18003b367  mov     [rbp+250h+var_2C0], r15
0x18003b36b  mov     [rsp+350h+hKey], rsi
0x18003b370  mov     [rsp+350h+phkResult], rsi
0x18003b375  cmp     rbx, 0FFFFFFFF80000001h
0x18003b37c  jnz     short loc_18003B394
0x18003b37e  lea     rdx, [rsp+350h+phkResult]; phkResult
0x18003b383  mov     ecx, r13d; samDesired
0x18003b386  call    cs:__imp_RegOpenCurrentUser
0x18003b38c  test    eax, eax
0x18003b38e  cmovz   rbx, [rsp+350h+phkResult]
0x18003b394  lea     rax, [rsp+350h+hKey]
0x18003b399  mov     r9d, r13d; samDesired
0x18003b39c  xor     r8d, r8d; ulOptions
0x18003b39f  mov     [rsp+350h+var_330], rax; phkResult
0x18003b3a4  lea     rdx, sourceString; lpSubKey
0x18003b3ab  mov     rcx, rbx; hKey
0x18003b3ae  call    cs:__imp_RegOpenKeyExW
0x18003b3b4  test    eax, eax
0x18003b3b6  jnz     short loc_18003B3BF
0x18003b3b8  mov     rdi, [rsp+350h+hKey]
0x18003b3bd  jmp     short loc_18003B40F
0x18003b3bf  mov     rdi, rsi
0x18003b3c2  cmp     eax, 5
0x18003b3c5  jnz     short loc_18003B40F
0x18003b3c7  lea     rax, [rsp+350h+dwDisposition]
0x18003b3cc  mov     [rsp+350h+dwDisposition], esi
0x18003b3d0  mov     [rsp+350h+lpdwDisposition], rax; lpdwDisposition
0x18003b3d5  lea     rdx, sourceString; lpSubKey
0x18003b3dc  lea     rax, [rsp+350h+hKey]
0x18003b3e1  xor     r9d, r9d; lpClass
0x18003b3e4  mov     [rsp+350h+var_318], rax; phkResult
0x18003b3e9  xor     r8d, r8d; Reserved
0x18003b3ec  mov     [rsp+350h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18003b3f1  mov     rcx, rbx; hKey
0x18003b3f4  mov     [rsp+350h+samDesired], r13d; samDesired
0x18003b3f9  mov     dword ptr [rsp+350h+var_330], 4; dwOptions
0x18003b401  call    cs:__imp_RegCreateKeyExW
0x18003b407  test    eax, eax
0x18003b409  cmovz   rdi, [rsp+350h+hKey]
0x18003b40f  mov     rcx, [rsp+350h+phkResult]; hKey
0x18003b414  test    rcx, rcx
0x18003b417  jz      short loc_18003B41F
0x18003b419  call    cs:__imp_RegCloseKey
0x18003b41f  mov     r13d, esi
0x18003b422  test    rdi, rdi
0x18003b425  jnz     loc_18003B4AC
0x18003b42b  cmp     [r12+4], esi
0x18003b430  jnz     short loc_18003B479
0x18003b432  mov     rcx, r12; this
0x18003b435  call    ?GetNextEmptyEntry@CInputList@@QEAAPEAUInputContainer@@XZ; CInputList::GetNextEmptyEntry(void)
0x18003b43a  mov     rbx, rax
0x18003b43d  test    rax, rax
0x18003b440  jz      short loc_18003B479
0x18003b442  mov     dword ptr [rax+0Ch], 1
0x18003b449  lea     r15, GUID_NULL
0x18003b450  mov     eax, 409h
0x18003b455  mov     word ptr [rbx+10h], 101h
0x18003b45b  mov     rcx, r15; struct _GUID *
0x18003b45e  mov     [rbx+4], eax
0x18003b461  lea     rdx, [rbx+14h]; unsigned __int16 *
0x18003b465  mov     [rbx], ax
0x18003b468  call    ?CLSIDToStringW@@YAHAEBU_GUID@@PEAG@Z; CLSIDToStringW(_GUID const &,ushort *)
0x18003b46d  lea     rdx, [rbx+62h]; unsigned __int16 *
0x18003b471  mov     rcx, r15; struct _GUID *
0x18003b474  call    ?CLSIDToStringW@@YAHAEBU_GUID@@PEAG@Z; CLSIDToStringW(_GUID const &,ushort *)
0x18003b479  test    rdi, rdi
0x18003b47c  jz      short loc_18003B487
0x18003b47e  mov     rcx, rdi; hKey
0x18003b481  call    cs:__imp_RegCloseKey
0x18003b487  mov     rcx, [rbp+250h+var_50]
0x18003b48e  xor     rcx, rsp; StackCookie
0x18003b491  call    __security_check_cookie
0x18003b496  add     rsp, 318h
0x18003b49d  pop     r15
0x18003b49f  pop     r14
0x18003b4a1  pop     r13
0x18003b4a3  pop     r12
0x18003b4a5  pop     rdi
0x18003b4a6  pop     rsi
0x18003b4a7  pop     rbx
0x18003b4a8  pop     rbp
0x18003b4a9  retn
0x18003b4aa  xor     esi, esi
0x18003b4ac  mov     [rsp+350h+var_318], rsi; lpcbData
0x18003b4b1  lea     r9, [rsp+350h+cchValueName]; lpcchValueName
0x18003b4b6  mov     [rsp+350h+lpSecurityAttributes], rsi; lpData
0x18003b4bb  lea     r8, [rbp+250h+ValueName]; lpValueName
0x18003b4bf  mov     qword ptr [rsp+350h+samDesired], rsi; lpType
0x18003b4c4  mov     edx, r13d; dwIndex
0x18003b4c7  mov     rcx, rdi; hKey
0x18003b4ca  mov     [rsp+350h+var_330], rsi; lpReserved
0x18003b4cf  mov     [rsp+350h+cchValueName], 100h
0x18003b4d7  call    cs:__imp_RegEnumValueW
0x18003b4dd  mov     ecx, eax
0x18003b4df  neg     ecx
0x18003b4e1  sbb     rdx, rdx
0x18003b4e4  not     rdx
0x18003b4e7  and     edx, 1FEh
0x18003b4ed  mov     [rbp+rdx+250h+ValueName], si
0x18003b4f2  test    eax, eax
0x18003b4f4  jnz     loc_18003B42B
0x18003b4fa  xor     edx, edx; EndPtr
0x18003b4fc  lea     r8d, [rax+0Ah]; Radix
0x18003b500  lea     rcx, [rbp+250h+ValueName]; String
0x18003b504  inc     r13d
0x18003b507  call    _o_wcstoul_0
0x18003b50c  test    eax, eax
0x18003b50e  jz      short loc_18003B4AC
0x18003b510  lea     rax, [rsp+350h+cchValueName]
0x18003b515  mov     [rsp+350h+cchValueName], 12h
0x18003b51d  mov     qword ptr [rsp+350h+samDesired], rax; lpcbData
0x18003b522  lea     r9, [rsp+350h+Type]; lpType
0x18003b527  lea     rax, [rbp+250h+Data]
0x18003b52b  mov     [rsp+350h+Type], esi
0x18003b52f  xor     r8d, r8d; lpReserved
0x18003b532  mov     [rsp+350h+var_330], rax; lpData
0x18003b537  lea     rdx, [rbp+250h+ValueName]; lpValueName
0x18003b53b  mov     rcx, rdi; hKey
0x18003b53e  call    cs:__imp_RegQueryValueExW
0x18003b544  mov     ecx, eax
0x18003b546  neg     ecx
0x18003b548  sbb     rdx, rdx
0x18003b54b  not     rdx
0x18003b54e  and     edx, 10h
0x18003b551  mov     word ptr [rbp+rdx+250h+Data], si
0x18003b556  test    eax, eax
0x18003b558  jnz     loc_18003B4AC
0x18003b55e  xor     edx, edx; EndPtr
0x18003b560  lea     r8d, [rax+10h]; Radix
0x18003b564  lea     rcx, [rbp+250h+Data]; String
0x18003b568  call    _o_wcstoul_0
0x18003b56d  mov     esi, eax
0x18003b56f  test    eax, eax
0x18003b571  jz      loc_18003B4AA
0x18003b577  mov     rcx, r12; this
0x18003b57a  call    ?GetNextEmptyEntry@CInputList@@QEAAPEAUInputContainer@@XZ; CInputList::GetNextEmptyEntry(void)
0x18003b57f  mov     rbx, rax
0x18003b582  test    rax, rax
0x18003b585  jz      loc_18003B4AA
0x18003b58b  mov     dword ptr [rax+0Ch], 1
0x18003b592  lea     r8, [rbp+250h+Data]
0x18003b596  mov     [rax+4], esi
0x18003b599  lea     rdx, [rbp+250h+String]
0x18003b59d  movzx   ecx, si
0x18003b5a0  mov     r9d, 9
0x18003b5a6  mov     [rax], cx
0x18003b5a9  mov     rcx, [r14]
0x18003b5ac  mov     rax, [rcx+8]
0x18003b5b0  mov     rcx, r14
0x18003b5b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b5b8  test    eax, eax
0x18003b5ba  jnz     short loc_18003B5D4
0x18003b5bc  xor     edx, edx; EndPtr
0x18003b5be  lea     r8d, [rax+10h]; Radix
0x18003b5c2  lea     rcx, [rbp+250h+String]; String
0x18003b5c6  call    _o_wcstoul_0
0x18003b5cb  mov     ecx, [rbx+4]
0x18003b5ce  mov     [rbx+8], ecx
0x18003b5d1  mov     [rbx+4], eax
0x18003b5d4  movzx   r9d, word ptr [rbx]
0x18003b5d8  lea     r8, a08x_1; "%08x"
0x18003b5df  mov     esi, [rbx+4]
0x18003b5e2  lea     rcx, [rbp+250h+SubKey]; unsigned __int16 *
0x18003b5e6  mov     r14d, 9
0x18003b5ec  mov     dword ptr [rbx+0Ch], 1
0x18003b5f3  mov     edx, r14d; unsigned __int64
0x18003b5f6  mov     byte ptr [rbx+10h], 1
0x18003b5fa  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003b5ff  mov     rcx, [rsp+350h+var_2D8]
0x18003b604  lea     r8, [rbp+250h+SubKey]
0x18003b608  mov     r9d, r14d
0x18003b60b  lea     rdx, [rbp+250h+var_270]
0x18003b60f  mov     rax, [rcx]
0x18003b612  mov     rax, [rax+8]
0x18003b616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b61b  test    eax, eax
0x18003b61d  jnz     short loc_18003B635
0x18003b61f  xor     edx, edx; EndPtr
0x18003b621  lea     r8d, [r14+7]; Radix
0x18003b625  lea     rcx, [rbp+250h+var_270]; String
0x18003b629  call    _o_wcstoul_0
0x18003b62e  cmp     eax, esi
0x18003b630  setz    al
0x18003b633  jmp     short loc_18003B637
0x18003b635  xor     al, al
0x18003b637  mov     r9d, [rbx+4]
0x18003b63b  lea     r8, a08x_1; "%08x"
0x18003b642  mov     rdx, r14; unsigned __int64
0x18003b645  mov     [rbx+12h], al
0x18003b648  lea     rcx, [rbp+250h+SubKey]; unsigned __int16 *
0x18003b64c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003b651  mov     r15, [r15+8]
0x18003b655  mov     qword ptr [rsp+350h+Type], 0
0x18003b65e  mov     qword ptr [rsp+350h+cchValueName], 0
0x18003b667  cmp     r15, 0FFFFFFFF80000001h
0x18003b66e  jnz     short loc_18003B688
0x18003b670  lea     rdx, [rsp+350h+cchValueName]; phkResult
0x18003b675  mov     ecx, 20019h; samDesired
0x18003b67a  call    cs:__imp_RegOpenCurrentUser
0x18003b680  test    eax, eax
0x18003b682  cmovz   r15, qword ptr [rsp+350h+cchValueName]
0x18003b688  lea     rax, [rsp+350h+Type]
0x18003b68d  mov     r9d, 20019h; samDesired
0x18003b693  xor     r8d, r8d; ulOptions
0x18003b696  mov     [rsp+350h+var_330], rax; phkResult
0x18003b69b  lea     rdx, [rbp+250h+SubKey]; lpSubKey
0x18003b69f  mov     rcx, r15; hKey
0x18003b6a2  call    cs:__imp_RegOpenKeyExW
0x18003b6a8  mov     esi, eax
0x18003b6aa  test    eax, eax
0x18003b6ac  jz      short loc_18003B6FD
0x18003b6ae  xor     r14d, r14d
0x18003b6b1  cmp     eax, 5
0x18003b6b4  jnz     short loc_18003B704
0x18003b6b6  lea     rax, [rsp+350h+var_2E4]
0x18003b6bb  mov     [rsp+350h+var_2E4], r14d
0x18003b6c0  mov     [rsp+350h+lpdwDisposition], rax; lpdwDisposition
0x18003b6c5  lea     rdx, [rbp+250h+SubKey]; lpSubKey
0x18003b6c9  lea     rax, [rsp+350h+Type]
0x18003b6ce  xor     r9d, r9d; lpClass
0x18003b6d1  mov     [rsp+350h+var_318], rax; phkResult
0x18003b6d6  xor     r8d, r8d; Reserved
0x18003b6d9  mov     [rsp+350h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18003b6de  mov     rcx, r15; hKey
0x18003b6e1  mov     [rsp+350h+samDesired], 20019h; samDesired
0x18003b6e9  mov     dword ptr [rsp+350h+var_330], 4; dwOptions
0x18003b6f1  call    cs:__imp_RegCreateKeyExW
0x18003b6f7  mov     esi, eax
0x18003b6f9  test    eax, eax
0x18003b6fb  jnz     short loc_18003B704
0x18003b6fd  mov     r14, qword ptr [rsp+350h+Type]
0x18003b702  xor     esi, esi
0x18003b704  mov     rcx, qword ptr [rsp+350h+cchValueName]; hKey
0x18003b709  test    rcx, rcx
0x18003b70c  jz      short loc_18003B714
0x18003b70e  call    cs:__imp_RegCloseKey
0x18003b714  test    esi, esi
0x18003b716  jnz     short loc_18003B71D
0x18003b718  mov     sil, 1
0x18003b71b  jmp     short loc_18003B720
0x18003b71d  xor     sil, sil
0x18003b720  test    r14, r14
0x18003b723  jz      short loc_18003B72E
0x18003b725  mov     rcx, r14; hKey
0x18003b728  call    cs:__imp_RegCloseKey
0x18003b72e  mov     r14d, 1
0x18003b734  mov     [rbx+11h], sil
0x18003b738  xor     esi, esi
0x18003b73a  mov     word ptr [rbx+14h], 7Bh ; '{'
0x18003b740  mov     edx, r14d
0x18003b743  lea     r15, GUID_NULL
0x18003b74a  mov     r8d, esi
0x18003b74d  lea     r11, __ImageBase
0x18003b754  lea     r10d, [r14+2Ch]
0x18003b758  cmp     edx, 24h ; '$'
0x18003b75b  jge     short loc_18003B7B7
0x18003b75d  movsxd  rax, r8d
0x18003b760  movsxd  r9, edx
0x18003b763  movzx   ecx, byte ptr [rax+r11+0B0EC0h]
0x18003b76c  cmp     cl, r10b
0x18003b76f  jnz     short loc_18003B779
0x18003b771  mov     [rbx+r9*2+14h], r10w
0x18003b777  jmp     short loc_18003B7AC
0x18003b779  movzx   eax, byte ptr [rcx+r15]
0x18003b77e  inc     edx
0x18003b780  shr     rax, 4
0x18003b784  movzx   eax, ds:rva word_1800B0E90[r11+rax*2]
0x18003b78d  mov     [rbx+r9*2+14h], ax
0x18003b793  movzx   eax, byte ptr [rcx+r15]
0x18003b798  and     eax, 0Fh
0x18003b79b  movsxd  rcx, edx
0x18003b79e  movzx   eax, ds:rva word_1800B0E90[r11+rax*2]
0x18003b7a7  mov     [rbx+rcx*2+14h], ax
0x18003b7ac  add     r8d, r14d
0x18003b7af  inc     edx
0x18003b7b1  cmp     r8d, 14h
0x18003b7b5  jb      short loc_18003B758
0x18003b7b7  movsxd  rcx, edx
  ... truncated ...
```
