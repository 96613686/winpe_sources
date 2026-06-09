# _AttributesFromSignatureInfo(AslFileMapping &,tagFILEATTRIBUTE *,unsigned __int64,FAR_MODE_FLAGS)

- ea: `0x18011d570`
- end: `0x18011dbc2`
- name: `?_AttributesFromSignatureInfo@@YAJAEAVAslFileMapping@@PEAUtagFILEATTRIBUTE@@_KW4FAR_MODE_FLAGS@@@Z`
- size: `1618`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, loader_planting, installer_update`

## callees

- `0x180008570`
- `0x1800092ac`
- `0x1800092dc`
- `0x18001a2f4`
- `0x18011d570`
- `0x18011e550`
- `0x18021f010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18011d87c`
- `ntdll!RtlFreeHeap` at `0x18011d9ca`
- `ntdll!RtlFreeHeap` at `0x18011db1e`
- `ntdll!RtlFreeHeap` at `0x18011d87c`
- `ntdll!RtlFreeHeap` at `0x18011d9ca`
- `ntdll!RtlFreeHeap` at `0x18011db1e`
- `ntdll!RtlAllocateHeap` at `0x18011d7dc`
- `ntdll!RtlAllocateHeap` at `0x18011d927`
- `ntdll!RtlAllocateHeap` at `0x18011da7b`
- `ntdll!RtlAllocateHeap` at `0x18011d7dc`
- `ntdll!RtlAllocateHeap` at `0x18011d927`
- `ntdll!RtlAllocateHeap` at `0x18011da7b`
- `KERNEL32!FreeLibrary` at `0x18011db86`
- `KERNEL32!FreeLibrary` at `0x18011db94`
- `KERNEL32!FreeLibrary` at `0x18011db86`
- `KERNEL32!FreeLibrary` at `0x18011db94`
- `KERNEL32!GetProcAddress` at `0x18011d6af`
- `KERNEL32!GetProcAddress` at `0x18011d715`
- `KERNEL32!GetProcAddress` at `0x18011d6af`
- `KERNEL32!GetProcAddress` at `0x18011d715`
- `KERNEL32!GetLastError` at `0x18011d720`
- `KERNEL32!GetLastError` at `0x18011d720`

## string_xrefs

- `0x18011d609`: `wintrust.dll`
- `0x18011d644`: `_AttributesFromSignatureInfo`
- `0x18011d653`: `_LoadSystemModule failed for wintrust.dll`
- `0x18011d683`: `_LoadSystemModule failed for shlwapi.dll`
- `0x18011d66b`: `shlwapi.dll`
- `0x18011d83e`: `Failed to copy attribute value (index %d) [%x]`
- `0x18011d98c`: `Failed to copy attribute value (index %d) [%x]`
- `0x18011dae0`: `Failed to copy attribute value (index %d) [%x]`
- `0x18011d803`: `_SetFileAttributeValue`
- `0x18011d853`: `_SetFileAttributeValue`
- `0x18011d94e`: `_SetFileAttributeValue`
- `0x18011d9a1`: `_SetFileAttributeValue`
- `0x18011daa2`: `_SetFileAttributeValue`
- `0x18011daf5`: `_SetFileAttributeValue`

## pseudocode

```c
__int64 __fastcall _AttributesFromSignatureInfo(_QWORD **a1, __int64 a2)
{
  unsigned int v4; // ebx
  HMODULE SystemModule; // rax
  HMODULE v6; // r12
  HMODULE v7; // rax
  HMODULE v8; // r14
  FARPROC ProcAddress; // rax
  int v10; // eax
  FARPROC v11; // rax
  signed int LastError; // eax
  int v13; // eax
  int v14; // ebx
  wchar_t *Heap; // rax
  int v16; // eax
  void *v17; // r8
  int v18; // ebx
  wchar_t *v19; // rax
  int v20; // eax
  void *v21; // r8
  int v22; // ebx
  wchar_t *v23; // rax
  int v24; // eax
  void *v25; // r8
  _DWORD v27[3]; // [rsp+40h] [rbp-C0h] BYREF
  char v28; // [rsp+4Ch] [rbp-B4h]
  wchar_t *v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-A0h]
  wchar_t *v31; // [rsp+68h] [rbp-98h]
  int v32; // [rsp+70h] [rbp-90h]
  wchar_t *v33; // [rsp+78h] [rbp-88h]
  int v34; // [rsp+80h] [rbp-80h]
  wchar_t S2[264]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t v36[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  wchar_t v37[264]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(v27, 0, 0x58u);
  memset_0(S2, 0, 0x208u);
  memset_0(v36, 0, 0x208u);
  memset_0(v37, 0, 0x208u);
  if ( a2 )
  {
    v27[0] = 88;
    v29 = S2;
    v30 = 260;
    v31 = v36;
    v33 = v37;
    v32 = 260;
    v34 = 260;
    SystemModule = _LoadSystemModule(L"wintrust.dll");
    v6 = SystemModule;
    if ( SystemModule )
    {
      ProcAddress = GetProcAddress(SystemModule, "WTGetSignatureInfo");
      if ( ProcAddress )
      {
        v8 = 0;
        v10 = ((__int64 (__fastcall *)(_QWORD, __int64, __int64, _DWORD *, _QWORD, _QWORD))ProcAddress)(
                **a1,
                -1,
                4099,
                v27,
                0,
                0);
        v4 = v10;
        if ( v10 < 0 )
        {
          AslLogCallPrintf(1, "_AttributesFromSignatureInfo", 1530, "WTGetSignatureInfo failed [%x]", v10);
          goto LABEL_64;
        }
        goto LABEL_16;
      }
    }
    else
    {
      AslLogCallPrintf(2, "_AttributesFromSignatureInfo", 1506, "_LoadSystemModule failed for wintrust.dll");
    }
    v7 = _LoadSystemModule(L"shlwapi.dll");
    v8 = v7;
    if ( !v7 )
    {
      v4 = -2147467259;
      AslLogCallPrintf(1, "_AttributesFromSignatureInfo", 1544, "_LoadSystemModule failed for shlwapi.dll");
      goto LABEL_63;
    }
    v11 = GetProcAddress(v7, (LPCSTR)0x22F);
    if ( !v11 )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      AslLogCallPrintf(1, "_AttributesFromSignatureInfo", 1552, "Failed to get function SHGetSignatureInfo [%x]", v4);
      goto LABEL_62;
    }
    v13 = ((__int64 (__fastcall *)(_QWORD, __int64, _DWORD *))v11)(**a1, 4099, v27);
    v4 = v13;
    if ( v13 < 0 )
    {
      AslLogCallPrintf(1, "_AttributesFromSignatureInfo", 1565, "SHGetSignatureInfo failed [%x]", v13);
LABEL_62:
      FreeLibrary(v8);
LABEL_63:
      if ( !v6 )
        return v4;
LABEL_64:
      FreeLibrary(v6);
      return v4;
    }
LABEL_16:
    if ( (v28 & 1) == 0 )
      goto LABEL_31;
    v14 = dword_1802C8F1C;
    if ( (unsigned int)dword_1802C8F1C <= 2 )
    {
      *(_DWORD *)(a2 + 10336) = *(_DWORD *)S2;
    }
    else if ( dword_1802C8F1C == 3 )
    {
      *(_QWORD *)(a2 + 10336) = *(_QWORD *)S2;
    }
    else
    {
      if ( dword_1802C8F1C != 4 )
        goto LABEL_31;
      Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x20Au);
      *(_QWORD *)(a2 + 10872) = Heap;
      if ( !Heap )
      {
        AslLogCallPrintf(1, "_SetFileAttributeValue", 3144, "Failed to alloc memory for string value (index %d)", 19);
        goto LABEL_31;
      }
      v16 = o_wmemcpy_s_0(Heap, 0x105u, S2, 0x104u);
      if ( v16 )
      {
        if ( v16 > 0 )
          v16 = (unsigned __int16)v16 | 0x80070000;
        AslLogCallPrintf(1, "_SetFileAttributeValue", 3156, "Failed to copy attribute value (index %d) [%x]", 19, v16);
        v17 = *(void **)(a2 + 10872);
        if ( v17 )
        {
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v17);
          *(_QWORD *)(a2 + 10872) = 0;
        }
LABEL_31:
        if ( (v28 & 2) == 0 )
          goto LABEL_46;
        v18 = dword_1802C8F34;
        if ( (unsigned int)dword_1802C8F34 <= 2 )
        {
          *(_DWORD *)(a2 + 10880) = *(_DWORD *)v36;
        }
        else if ( dword_1802C8F34 == 3 )
        {
          *(_QWORD *)(a2 + 10880) = *(_QWORD *)v36;
        }
        else
        {
          if ( dword_1802C8F34 != 4 )
            goto LABEL_46;
          v19 = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x20Au);
          *(_QWORD *)(a2 + 11416) = v19;
          if ( !v19 )
          {
            AslLogCallPrintf(
              1,
              "_SetFileAttributeValue",
              3144,
              "Failed to alloc memory for string value (index %d)",
              20);
            goto LABEL_46;
          }
          v20 = o_wmemcpy_s_0(v19, 0x105u, v36, 0x104u);
          if ( v20 )
          {
            if ( v20 > 0 )
              v20 = (unsigned __int16)v20 | 0x80070000;
            AslLogCallPrintf(
              1,
              "_SetFileAttributeValue",
              3156,
              "Failed to copy attribute value (index %d) [%x]",
              20,
              v20);
            v21 = *(void **)(a2 + 11416);
            if ( v21 )
            {
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v21);
              *(_QWORD *)(a2 + 11416) = 0;
            }
LABEL_46:
            if ( (v28 & 4) == 0 )
              goto LABEL_61;
            v22 = dword_1802C8F4C;
            if ( (unsigned int)dword_1802C8F4C <= 2 )
            {
              *(_DWORD *)(a2 + 11424) = *(_DWORD *)v37;
            }
            else if ( dword_1802C8F4C == 3 )
            {
              *(_QWORD *)(a2 + 11424) = *(_QWORD *)v37;
            }
            else
            {
              if ( dword_1802C8F4C != 4 )
                goto LABEL_61;
              v23 = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x20Au);
              *(_QWORD *)(a2 + 11960) = v23;
              if ( !v23 )
              {
                AslLogCallPrintf(
                  1,
                  "_SetFileAttributeValue",
                  3144,
                  "Failed to alloc memory for string value (index %d)",
                  21);
                goto LABEL_61;
              }
              v24 = o_wmemcpy_s_0(v23, 0x105u, v37, 0x104u);
              if ( v24 )
              {
                if ( v24 > 0 )
                  v24 = (unsigned __int16)v24 | 0x80070000;
                AslLogCallPrintf(
                  1,
                  "_SetFileAttributeValue",
                  3156,
                  "Failed to copy attribute value (index %d) [%x]",
                  21,
                  v24);
                v25 = *(void **)(a2 + 11960);
                if ( v25 )
                {
                  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v25);
                  *(_QWORD *)(a2 + 11960) = 0;
                }
LABEL_61:
                v4 = 0;
                if ( !v8 )
                  goto LABEL_63;
                goto LABEL_62;
              }
              *(_WORD *)(*(_QWORD *)(a2 + 11960) + 520LL) = 0;
              *(_WORD *)(a2 + 11424) = 0;
            }
            *(_DWORD *)(a2 + 11944) = 21;
            *(_DWORD *)(a2 + 11948) = v22;
            *(_DWORD *)(a2 + 11952) = 1;
            goto LABEL_61;
          }
          *(_WORD *)(*(_QWORD *)(a2 + 11416) + 520LL) = 0;
          *(_WORD *)(a2 + 10880) = 0;
        }
        *(_DWORD *)(a2 + 11400) = 20;
        *(_DWORD *)(a2 + 11404) = v18;
        *(_DWORD *)(a2 + 11408) = 1;
        goto LABEL_46;
      }
      *(_WORD *)(*(_QWORD *)(a2 + 10872) + 520LL) = 0;
      *(_WORD *)(a2 + 10336) = 0;
    }
    *(_DWORD *)(a2 + 10856) = 19;
    *(_DWORD *)(a2 + 10860) = v14;
    *(_DWORD *)(a2 + 10864) = 1;
    goto LABEL_31;
  }
  return (unsigned int)-2147024809;
}

```

## disassembly

```asm
0x18011d570  mov     [rsp-8+arg_10], rbx
0x18011d575  push    rbp
0x18011d576  push    rsi
0x18011d577  push    rdi
0x18011d578  push    r12
0x18011d57a  push    r14
0x18011d57c  lea     rbp, [rsp-5E0h]
0x18011d584  sub     rsp, 6E0h
0x18011d58b  mov     rax, cs:__security_cookie
0x18011d592  xor     rax, rsp
0x18011d595  mov     [rbp+600h+var_30], rax
0x18011d59c  mov     rdi, rdx
0x18011d59f  mov     rbx, rcx
0x18011d5a2  mov     r14d, 58h ; 'X'
0x18011d5a8  lea     rcx, [rsp+700h+var_6C0]; void *
0x18011d5ad  mov     r8d, r14d; Size
0x18011d5b0  xor     edx, edx; Val
0x18011d5b2  call    memset_0
0x18011d5b7  mov     esi, 208h
0x18011d5bc  lea     rcx, [rbp+600h+S2]; void *
0x18011d5c0  mov     r8d, esi; Size
0x18011d5c3  xor     edx, edx; Val
0x18011d5c5  call    memset_0
0x18011d5ca  mov     r8d, esi; Size
0x18011d5cd  lea     rcx, [rbp+600h+var_450]; void *
0x18011d5d4  xor     edx, edx; Val
0x18011d5d6  call    memset_0
0x18011d5db  mov     r8d, esi; Size
0x18011d5de  lea     rcx, [rbp+600h+var_240]; void *
0x18011d5e5  xor     edx, edx; Val
0x18011d5e7  call    memset_0
0x18011d5ec  test    rdi, rdi
0x18011d5ef  jnz     short loc_18011D5FB
0x18011d5f1  mov     ebx, 80070057h
0x18011d5f6  jmp     loc_18011DB9A
0x18011d5fb  lea     rax, [rbp+600h+S2]
0x18011d5ff  mov     [rsp+700h+var_6C0], r14d
0x18011d604  mov     [rsp+700h+var_6A8], rax
0x18011d609  lea     rcx, aWintrustDll_0; "wintrust.dll"
0x18011d610  lea     rax, [rbp+600h+var_450]
0x18011d617  mov     [rsp+700h+var_6A0], 104h
0x18011d61f  mov     [rsp+700h+var_698], rax
0x18011d624  lea     rax, [rbp+600h+var_240]
0x18011d62b  mov     [rsp+700h+var_688], rax
0x18011d630  mov     [rsp+700h+var_690], 104h
0x18011d638  mov     [rbp+600h+var_680], 104h
0x18011d63f  call    ?_LoadSystemModule@@YAPEAUHINSTANCE__@@PEBG@Z; _LoadSystemModule(ushort const *)
0x18011d644  lea     rsi, aAttributesfrom_2; "_AttributesFromSignatureInfo"
0x18011d64b  mov     r12, rax
0x18011d64e  test    rax, rax
0x18011d651  jnz     short loc_18011D6A5
0x18011d653  lea     r9, aLoadsystemmodu_0; "_LoadSystemModule failed for wintrust.d"...
0x18011d65a  mov     r8d, 5E2h
0x18011d660  mov     rdx, rsi
0x18011d663  lea     ecx, [rax+2]
0x18011d666  call    AslLogCallPrintf
0x18011d66b  lea     rcx, aShlwapiDll_0; "shlwapi.dll"
0x18011d672  call    ?_LoadSystemModule@@YAPEAUHINSTANCE__@@PEBG@Z; _LoadSystemModule(ushort const *)
0x18011d677  mov     r14, rax
0x18011d67a  test    rax, rax
0x18011d67d  jnz     loc_18011D70D
0x18011d683  lea     r9, aLoadsystemmodu; "_LoadSystemModule failed for shlwapi.dl"...
0x18011d68a  mov     r8d, 608h
0x18011d690  mov     rdx, rsi
0x18011d693  lea     ecx, [rax+1]
0x18011d696  mov     ebx, 80004005h
0x18011d69b  call    AslLogCallPrintf
0x18011d6a0  jmp     loc_18011DB8C
0x18011d6a5  lea     rdx, aWtgetsignature_0; "WTGetSignatureInfo"
0x18011d6ac  mov     rcx, r12; hModule
0x18011d6af  call    cs:__imp_GetProcAddress
0x18011d6b5  test    rax, rax
0x18011d6b8  jz      short loc_18011D66B
0x18011d6ba  mov     rcx, [rbx]
0x18011d6bd  lea     r9, [rsp+700h+var_6C0]
0x18011d6c2  xor     r14d, r14d
0x18011d6c5  mov     r8d, 1003h
0x18011d6cb  mov     [rsp+700h+var_6D8], r14
0x18011d6d0  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18011d6d4  mov     [rsp+700h+var_6E0], r14
0x18011d6d9  mov     rcx, [rcx]
0x18011d6dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011d6e1  mov     ebx, eax
0x18011d6e3  test    eax, eax
0x18011d6e5  jns     loc_18011D786
0x18011d6eb  lea     r9, aWtgetsignature; "WTGetSignatureInfo failed [%x]"
0x18011d6f2  mov     dword ptr [rsp+700h+var_6E0], eax
0x18011d6f6  mov     r8d, 5FAh
0x18011d6fc  lea     ecx, [r14+1]
0x18011d700  mov     rdx, rsi
0x18011d703  call    AslLogCallPrintf
0x18011d708  jmp     loc_18011DB91
0x18011d70d  mov     edx, 22Fh; lpProcName
0x18011d712  mov     rcx, rax; hModule
0x18011d715  call    cs:__imp_GetProcAddress
0x18011d71b  test    rax, rax
0x18011d71e  jnz     short loc_18011D758
0x18011d720  call    cs:__imp_GetLastError
0x18011d726  mov     ebx, eax
0x18011d728  test    eax, eax
0x18011d72a  jle     short loc_18011D735
0x18011d72c  movzx   ebx, ax
0x18011d72f  or      ebx, 80070000h
0x18011d735  mov     dword ptr [rsp+700h+var_6E0], ebx
0x18011d739  lea     r9, aFailedToGetFun; "Failed to get function SHGetSignatureIn"...
0x18011d740  mov     r8d, 610h
0x18011d746  mov     rdx, rsi
0x18011d749  mov     ecx, 1
0x18011d74e  call    AslLogCallPrintf
0x18011d753  jmp     loc_18011DB83
0x18011d758  mov     rcx, [rbx]
0x18011d75b  lea     r8, [rsp+700h+var_6C0]
0x18011d760  mov     edx, 1003h
0x18011d765  mov     rcx, [rcx]
0x18011d768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011d76d  mov     ebx, eax
0x18011d76f  test    eax, eax
0x18011d771  jns     short loc_18011D786
0x18011d773  mov     dword ptr [rsp+700h+var_6E0], eax
0x18011d777  lea     r9, aShgetsignature; "SHGetSignatureInfo failed [%x]"
0x18011d77e  mov     r8d, 61Dh
0x18011d784  jmp     short loc_18011D746
0x18011d786  mov     esi, 1
0x18011d78b  test    [rsp+700h+var_6B4], sil
0x18011d790  jz      loc_18011D8D4
0x18011d796  mov     ebx, cs:dword_1802C8F1C
0x18011d79c  mov     ecx, ebx
0x18011d79e  test    ebx, ebx
0x18011d7a0  jz      loc_18011D8B5
0x18011d7a6  sub     ecx, esi
0x18011d7a8  jz      loc_18011D8B5
0x18011d7ae  sub     ecx, esi
0x18011d7b0  jz      loc_18011D8B5
0x18011d7b6  sub     ecx, esi
0x18011d7b8  jz      loc_18011D8A8
0x18011d7be  cmp     ecx, esi
0x18011d7c0  jnz     loc_18011D8D4
0x18011d7c6  mov     rcx, gs:60h
0x18011d7cf  lea     edx, [rsi+7]; Flags
0x18011d7d2  mov     r8d, 20Ah; Size
0x18011d7d8  mov     rcx, [rcx+30h]; HeapHandle
0x18011d7dc  call    cs:__imp_RtlAllocateHeap
0x18011d7e2  mov     [rdi+2A78h], rax
0x18011d7e9  test    rax, rax
0x18011d7ec  jnz     short loc_18011D816
0x18011d7ee  lea     r9, aFailedToAllocM; "Failed to alloc memory for string value"...
0x18011d7f5  mov     dword ptr [rsp+700h+var_6E0], 13h
0x18011d7fd  mov     r8d, 0C48h
0x18011d803  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x18011d80a  mov     ecx, esi
0x18011d80c  call    AslLogCallPrintf
0x18011d811  jmp     loc_18011D8D4
0x18011d816  mov     r9d, 104h; N
0x18011d81c  lea     r8, [rbp+600h+S2]; S2
0x18011d820  mov     rcx, rax; S1
0x18011d823  lea     edx, [r9+1]; N1
0x18011d827  call    _o_wmemcpy_s_0
0x18011d82c  test    eax, eax
0x18011d82e  jz      short loc_18011D88F
0x18011d830  jle     short loc_18011D83A
0x18011d832  movzx   eax, ax
0x18011d835  or      eax, 80070000h
0x18011d83a  mov     dword ptr [rsp+700h+var_6D8], eax
0x18011d83e  lea     r9, aFailedToCopyAt; "Failed to copy attribute value (index %"...
0x18011d845  mov     r8d, 0C54h
0x18011d84b  mov     dword ptr [rsp+700h+var_6E0], 13h
0x18011d853  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x18011d85a  mov     ecx, esi
0x18011d85c  call    AslLogCallPrintf
0x18011d861  mov     r8, [rdi+2A78h]; P
0x18011d868  test    r8, r8
0x18011d86b  jz      short loc_18011D8D4
0x18011d86d  mov     rcx, gs:60h
0x18011d876  xor     edx, edx; Flags
0x18011d878  mov     rcx, [rcx+30h]; HeapHandle
0x18011d87c  call    cs:__imp_RtlFreeHeap
0x18011d882  mov     qword ptr [rdi+2A78h], 0
0x18011d88d  jmp     short loc_18011D8D4
0x18011d88f  mov     rcx, [rdi+2A78h]
0x18011d896  xor     eax, eax
0x18011d898  mov     [rcx+208h], ax
0x18011d89f  mov     [rdi+2860h], ax
0x18011d8a6  jmp     short loc_18011D8BE
0x18011d8a8  mov     rax, qword ptr [rbp+600h+S2]
0x18011d8ac  mov     [rdi+2860h], rax
0x18011d8b3  jmp     short loc_18011D8BE
0x18011d8b5  mov     eax, dword ptr [rbp+600h+S2]
0x18011d8b8  mov     [rdi+2860h], eax
0x18011d8be  mov     dword ptr [rdi+2A68h], 13h
0x18011d8c8  mov     [rdi+2A6Ch], ebx
0x18011d8ce  mov     [rdi+2A70h], esi
0x18011d8d4  test    [rsp+700h+var_6B4], 2
0x18011d8d9  jz      loc_18011DA28
0x18011d8df  mov     ebx, cs:dword_1802C8F34
0x18011d8e5  mov     ecx, ebx
0x18011d8e7  test    ebx, ebx
0x18011d8e9  jz      loc_18011DA06
0x18011d8ef  sub     ecx, esi
0x18011d8f1  jz      loc_18011DA06
0x18011d8f7  sub     ecx, esi
0x18011d8f9  jz      loc_18011DA06
0x18011d8ff  sub     ecx, esi
0x18011d901  jz      loc_18011D9F6
0x18011d907  cmp     ecx, esi
0x18011d909  jnz     loc_18011DA28
0x18011d90f  mov     rcx, gs:60h
0x18011d918  mov     edx, 8; Flags
0x18011d91d  mov     r8d, 20Ah; Size
0x18011d923  mov     rcx, [rcx+30h]; HeapHandle
0x18011d927  call    cs:__imp_RtlAllocateHeap
0x18011d92d  mov     [rdi+2C98h], rax
0x18011d934  test    rax, rax
0x18011d937  jnz     short loc_18011D961
0x18011d939  lea     r9, aFailedToAllocM; "Failed to alloc memory for string value"...
0x18011d940  mov     dword ptr [rsp+700h+var_6E0], 14h
0x18011d948  mov     r8d, 0C48h
0x18011d94e  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x18011d955  mov     ecx, esi
0x18011d957  call    AslLogCallPrintf
0x18011d95c  jmp     loc_18011DA28
0x18011d961  mov     r9d, 104h; N
0x18011d967  lea     r8, [rbp+600h+var_450]; S2
0x18011d96e  mov     rcx, rax; S1
0x18011d971  lea     edx, [r9+1]; N1
0x18011d975  call    _o_wmemcpy_s_0
0x18011d97a  test    eax, eax
0x18011d97c  jz      short loc_18011D9DD
0x18011d97e  jle     short loc_18011D988
0x18011d980  movzx   eax, ax
0x18011d983  or      eax, 80070000h
0x18011d988  mov     dword ptr [rsp+700h+var_6D8], eax
0x18011d98c  lea     r9, aFailedToCopyAt; "Failed to copy attribute value (index %"...
0x18011d993  mov     r8d, 0C54h
0x18011d999  mov     dword ptr [rsp+700h+var_6E0], 14h
0x18011d9a1  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x18011d9a8  mov     ecx, esi
0x18011d9aa  call    AslLogCallPrintf
0x18011d9af  mov     r8, [rdi+2C98h]; P
0x18011d9b6  test    r8, r8
0x18011d9b9  jz      short loc_18011DA28
0x18011d9bb  mov     rcx, gs:60h
0x18011d9c4  xor     edx, edx; Flags
0x18011d9c6  mov     rcx, [rcx+30h]; HeapHandle
0x18011d9ca  call    cs:__imp_RtlFreeHeap
0x18011d9d0  mov     qword ptr [rdi+2C98h], 0
0x18011d9db  jmp     short loc_18011DA28
0x18011d9dd  mov     rcx, [rdi+2C98h]
0x18011d9e4  xor     eax, eax
0x18011d9e6  mov     [rcx+208h], ax
0x18011d9ed  mov     [rdi+2A80h], ax
0x18011d9f4  jmp     short loc_18011DA12
0x18011d9f6  mov     rax, qword ptr [rbp+600h+var_450]
0x18011d9fd  mov     [rdi+2A80h], rax
0x18011da04  jmp     short loc_18011DA12
0x18011da06  mov     eax, dword ptr [rbp+600h+var_450]
0x18011da0c  mov     [rdi+2A80h], eax
0x18011da12  mov     dword ptr [rdi+2C88h], 14h
0x18011da1c  mov     [rdi+2C8Ch], ebx
0x18011da22  mov     [rdi+2C90h], esi
0x18011da28  test    [rsp+700h+var_6B4], 4
0x18011da2d  jz      loc_18011DB7C
0x18011da33  mov     ebx, cs:dword_1802C8F4C
0x18011da39  mov     ecx, ebx
0x18011da3b  test    ebx, ebx
0x18011da3d  jz      loc_18011DB5A
0x18011da43  sub     ecx, esi
0x18011da45  jz      loc_18011DB5A
0x18011da4b  sub     ecx, esi
0x18011da4d  jz      loc_18011DB5A
0x18011da53  sub     ecx, esi
0x18011da55  jz      loc_18011DB4A
0x18011da5b  cmp     ecx, esi
0x18011da5d  jnz     loc_18011DB7C
0x18011da63  mov     rcx, gs:60h
0x18011da6c  mov     edx, 8; Flags
0x18011da71  mov     r8d, 20Ah; Size
0x18011da77  mov     rcx, [rcx+30h]; HeapHandle
0x18011da7b  call    cs:__imp_RtlAllocateHeap
0x18011da81  mov     [rdi+2EB8h], rax
0x18011da88  test    rax, rax
0x18011da8b  jnz     short loc_18011DAB5
0x18011da8d  lea     r9, aFailedToAllocM; "Failed to alloc memory for string value"...
0x18011da94  mov     dword ptr [rsp+700h+var_6E0], 15h
0x18011da9c  mov     r8d, 0C48h
0x18011daa2  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x18011daa9  mov     ecx, esi
0x18011daab  call    AslLogCallPrintf
0x18011dab0  jmp     loc_18011DB7C
0x18011dab5  mov     r9d, 104h; N
0x18011dabb  lea     r8, [rbp+600h+var_240]; S2
0x18011dac2  mov     rcx, rax; S1
0x18011dac5  lea     edx, [r9+1]; N1
0x18011dac9  call    _o_wmemcpy_s_0
0x18011dace  test    eax, eax
0x18011dad0  jz      short loc_18011DB31
0x18011dad2  jle     short loc_18011DADC
0x18011dad4  movzx   eax, ax
0x18011dad7  or      eax, 80070000h
0x18011dadc  mov     dword ptr [rsp+700h+var_6D8], eax
0x18011dae0  lea     r9, aFailedToCopyAt; "Failed to copy attribute value (index %"...
  ... truncated ...
```
