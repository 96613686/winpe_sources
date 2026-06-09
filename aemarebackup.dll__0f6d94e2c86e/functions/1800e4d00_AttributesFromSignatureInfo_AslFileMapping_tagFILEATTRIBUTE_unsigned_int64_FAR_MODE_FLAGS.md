# _AttributesFromSignatureInfo(AslFileMapping &,tagFILEATTRIBUTE *,unsigned __int64,FAR_MODE_FLAGS)

- ea: `0x1800e4d00`
- end: `0x1800e534f`
- name: `?_AttributesFromSignatureInfo@@YAJAEAVAslFileMapping@@PEAUtagFILEATTRIBUTE@@_KW4FAR_MODE_FLAGS@@@Z`
- size: `1615`
- prototype: `__int64 __fastcall(_QWORD **, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, loader_planting, installer_update`

## callees

- `0x180004ea0`
- `0x1800058fc`
- `0x180005914`
- `0x180005b90`
- `0x180005be0`
- `0x18004c020`
- `0x1800e4d00`
- `0x1800e5cd8`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800e5313`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800e5321`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800e5313`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800e5321`
- `ntdll!RtlAllocateHeap` at `0x1800e4f69`
- `ntdll!RtlAllocateHeap` at `0x1800e50b4`
- `ntdll!RtlAllocateHeap` at `0x1800e5208`
- `ntdll!RtlAllocateHeap` at `0x1800e4f69`
- `ntdll!RtlAllocateHeap` at `0x1800e50b4`
- `ntdll!RtlAllocateHeap` at `0x1800e5208`
- `ntdll!RtlFreeHeap` at `0x1800e5009`
- `ntdll!RtlFreeHeap` at `0x1800e5157`
- `ntdll!RtlFreeHeap` at `0x1800e52ab`
- `ntdll!RtlFreeHeap` at `0x1800e5009`
- `ntdll!RtlFreeHeap` at `0x1800e5157`
- `ntdll!RtlFreeHeap` at `0x1800e52ab`

## string_xrefs

- `0x1800e4d99`: `wintrust.dll`
- `0x1800e4dd4`: `_AttributesFromSignatureInfo`
- `0x1800e4de3`: `_LoadSystemModule failed for wintrust.dll`
- `0x1800e4e13`: `_LoadSystemModule failed for shlwapi.dll`
- `0x1800e4dfb`: `shlwapi.dll`
- `0x1800e4f90`: `_SetFileAttributeValue`
- `0x1800e4fe0`: `_SetFileAttributeValue`
- `0x1800e50db`: `_SetFileAttributeValue`
- `0x1800e512e`: `_SetFileAttributeValue`
- `0x1800e522f`: `_SetFileAttributeValue`
- `0x1800e5282`: `_SetFileAttributeValue`
- `0x1800e4fcb`: `Failed to copy attribute value (index %d) [%x]`
- `0x1800e5119`: `Failed to copy attribute value (index %d) [%x]`
- `0x1800e526d`: `Failed to copy attribute value (index %d) [%x]`

## pseudocode

```c
__int64 __fastcall _AttributesFromSignatureInfo(_QWORD **a1, __int64 a2)
{
  unsigned int v4; // ebx
  HMODULE SystemModule; // rax
  HMODULE v6; // r12
  HMODULE v7; // rax
  HMODULE v8; // r14
  FARPROC WTGetSignatureInfo; // rax
  int v10; // eax
  FARPROC ProcAddress_0; // rax
  signed int LastError_0; // eax
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
      WTGetSignatureInfo = GetProcAddress_0(SystemModule, "WTGetSignatureInfo");
      if ( WTGetSignatureInfo )
      {
        v8 = 0;
        v10 = ((__int64 (__fastcall *)(_QWORD, __int64, __int64, _DWORD *, _QWORD, _QWORD))WTGetSignatureInfo)(
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
    ProcAddress_0 = GetProcAddress_0(v7, (LPCSTR)0x22F);
    if ( !ProcAddress_0 )
    {
      LastError_0 = GetLastError_0();
      v4 = LastError_0;
      if ( LastError_0 > 0 )
        v4 = (unsigned __int16)LastError_0 | 0x80070000;
      AslLogCallPrintf(1, "_AttributesFromSignatureInfo", 1552, "Failed to get function SHGetSignatureInfo [%x]", v4);
      goto LABEL_62;
    }
    v13 = ((__int64 (__fastcall *)(_QWORD, __int64, _DWORD *))ProcAddress_0)(**a1, 4099, v27);
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
    v14 = dword_18011996C;
    if ( (unsigned int)dword_18011996C <= 2 )
    {
      *(_DWORD *)(a2 + 10336) = *(_DWORD *)S2;
    }
    else if ( dword_18011996C == 3 )
    {
      *(_QWORD *)(a2 + 10336) = *(_QWORD *)S2;
    }
    else
    {
      if ( dword_18011996C != 4 )
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
        v18 = dword_180119984;
        if ( (unsigned int)dword_180119984 <= 2 )
        {
          *(_DWORD *)(a2 + 10880) = *(_DWORD *)v36;
        }
        else if ( dword_180119984 == 3 )
        {
          *(_QWORD *)(a2 + 10880) = *(_QWORD *)v36;
        }
        else
        {
          if ( dword_180119984 != 4 )
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
            v22 = dword_18011999C;
            if ( (unsigned int)dword_18011999C <= 2 )
            {
              *(_DWORD *)(a2 + 11424) = *(_DWORD *)v37;
            }
            else if ( dword_18011999C == 3 )
            {
              *(_QWORD *)(a2 + 11424) = *(_QWORD *)v37;
            }
            else
            {
              if ( dword_18011999C != 4 )
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
0x1800e4d00  mov     [rsp-8+arg_10], rbx
0x1800e4d05  push    rbp
0x1800e4d06  push    rsi
0x1800e4d07  push    rdi
0x1800e4d08  push    r12
0x1800e4d0a  push    r14
0x1800e4d0c  lea     rbp, [rsp-5E0h]
0x1800e4d14  sub     rsp, 6E0h
0x1800e4d1b  mov     rax, cs:__security_cookie
0x1800e4d22  xor     rax, rsp
0x1800e4d25  mov     [rbp+600h+var_30], rax
0x1800e4d2c  mov     rdi, rdx
0x1800e4d2f  mov     rbx, rcx
0x1800e4d32  mov     r14d, 58h ; 'X'
0x1800e4d38  lea     rcx, [rsp+700h+var_6C0]; void *
0x1800e4d3d  mov     r8d, r14d; Size
0x1800e4d40  xor     edx, edx; Val
0x1800e4d42  call    memset_0
0x1800e4d47  mov     esi, 208h
0x1800e4d4c  lea     rcx, [rbp+600h+S2]; void *
0x1800e4d50  mov     r8d, esi; Size
0x1800e4d53  xor     edx, edx; Val
0x1800e4d55  call    memset_0
0x1800e4d5a  mov     r8d, esi; Size
0x1800e4d5d  lea     rcx, [rbp+600h+var_450]; void *
0x1800e4d64  xor     edx, edx; Val
0x1800e4d66  call    memset_0
0x1800e4d6b  mov     r8d, esi; Size
0x1800e4d6e  lea     rcx, [rbp+600h+var_240]; void *
0x1800e4d75  xor     edx, edx; Val
0x1800e4d77  call    memset_0
0x1800e4d7c  test    rdi, rdi
0x1800e4d7f  jnz     short loc_1800E4D8B
0x1800e4d81  mov     ebx, 80070057h
0x1800e4d86  jmp     loc_1800E5327
0x1800e4d8b  lea     rax, [rbp+600h+S2]
0x1800e4d8f  mov     [rsp+700h+var_6C0], r14d
0x1800e4d94  mov     [rsp+700h+var_6A8], rax
0x1800e4d99  lea     rcx, aWintrustDll; "wintrust.dll"
0x1800e4da0  lea     rax, [rbp+600h+var_450]
0x1800e4da7  mov     [rsp+700h+var_6A0], 104h
0x1800e4daf  mov     [rsp+700h+var_698], rax
0x1800e4db4  lea     rax, [rbp+600h+var_240]
0x1800e4dbb  mov     [rsp+700h+var_688], rax
0x1800e4dc0  mov     [rsp+700h+var_690], 104h
0x1800e4dc8  mov     [rbp+600h+var_680], 104h
0x1800e4dcf  call    ?_LoadSystemModule@@YAPEAUHINSTANCE__@@PEBG@Z; _LoadSystemModule(ushort const *)
0x1800e4dd4  lea     rsi, aAttributesfrom_2; "_AttributesFromSignatureInfo"
0x1800e4ddb  mov     r12, rax
0x1800e4dde  test    rax, rax
0x1800e4de1  jnz     short loc_1800E4E35
0x1800e4de3  lea     r9, aLoadsystemmodu_0; "_LoadSystemModule failed for wintrust.d"...
0x1800e4dea  mov     r8d, 5E2h
0x1800e4df0  mov     rdx, rsi
0x1800e4df3  lea     ecx, [rax+2]
0x1800e4df6  call    AslLogCallPrintf
0x1800e4dfb  lea     rcx, aShlwapiDll; "shlwapi.dll"
0x1800e4e02  call    ?_LoadSystemModule@@YAPEAUHINSTANCE__@@PEBG@Z; _LoadSystemModule(ushort const *)
0x1800e4e07  mov     r14, rax
0x1800e4e0a  test    rax, rax
0x1800e4e0d  jnz     loc_1800E4E9C
0x1800e4e13  lea     r9, aLoadsystemmodu; "_LoadSystemModule failed for shlwapi.dl"...
0x1800e4e1a  mov     r8d, 608h
0x1800e4e20  mov     rdx, rsi
0x1800e4e23  lea     ecx, [rax+1]
0x1800e4e26  mov     ebx, 80004005h
0x1800e4e2b  call    AslLogCallPrintf
0x1800e4e30  jmp     loc_1800E5319
0x1800e4e35  lea     rdx, aWtgetsignature_0; "WTGetSignatureInfo"
0x1800e4e3c  mov     rcx, r12; hModule
0x1800e4e3f  call    GetProcAddress_0
0x1800e4e44  test    rax, rax
0x1800e4e47  jz      short loc_1800E4DFB
0x1800e4e49  mov     rcx, [rbx]
0x1800e4e4c  lea     r9, [rsp+700h+var_6C0]
0x1800e4e51  xor     r14d, r14d
0x1800e4e54  mov     r8d, 1003h
0x1800e4e5a  mov     [rsp+700h+var_6D8], r14
0x1800e4e5f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800e4e63  mov     [rsp+700h+var_6E0], r14
0x1800e4e68  mov     rcx, [rcx]
0x1800e4e6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e4e70  mov     ebx, eax
0x1800e4e72  test    eax, eax
0x1800e4e74  jns     loc_1800E4F13
0x1800e4e7a  lea     r9, aWtgetsignature; "WTGetSignatureInfo failed [%x]"
0x1800e4e81  mov     dword ptr [rsp+700h+var_6E0], eax
0x1800e4e85  mov     r8d, 5FAh
0x1800e4e8b  lea     ecx, [r14+1]
0x1800e4e8f  mov     rdx, rsi
0x1800e4e92  call    AslLogCallPrintf
0x1800e4e97  jmp     loc_1800E531E
0x1800e4e9c  mov     edx, 22Fh; lpProcName
0x1800e4ea1  mov     rcx, rax; hModule
0x1800e4ea4  call    GetProcAddress_0
0x1800e4ea9  test    rax, rax
0x1800e4eac  jnz     short loc_1800E4EE5
0x1800e4eae  call    GetLastError_0
0x1800e4eb3  mov     ebx, eax
0x1800e4eb5  test    eax, eax
0x1800e4eb7  jle     short loc_1800E4EC2
0x1800e4eb9  movzx   ebx, ax
0x1800e4ebc  or      ebx, 80070000h
0x1800e4ec2  mov     dword ptr [rsp+700h+var_6E0], ebx
0x1800e4ec6  lea     r9, aFailedToGetFun; "Failed to get function SHGetSignatureIn"...
0x1800e4ecd  mov     r8d, 610h
0x1800e4ed3  mov     rdx, rsi
0x1800e4ed6  mov     ecx, 1
0x1800e4edb  call    AslLogCallPrintf
0x1800e4ee0  jmp     loc_1800E5310
0x1800e4ee5  mov     rcx, [rbx]
0x1800e4ee8  lea     r8, [rsp+700h+var_6C0]
0x1800e4eed  mov     edx, 1003h
0x1800e4ef2  mov     rcx, [rcx]
0x1800e4ef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e4efa  mov     ebx, eax
0x1800e4efc  test    eax, eax
0x1800e4efe  jns     short loc_1800E4F13
0x1800e4f00  mov     dword ptr [rsp+700h+var_6E0], eax
0x1800e4f04  lea     r9, aShgetsignature; "SHGetSignatureInfo failed [%x]"
0x1800e4f0b  mov     r8d, 61Dh
0x1800e4f11  jmp     short loc_1800E4ED3
0x1800e4f13  mov     esi, 1
0x1800e4f18  test    [rsp+700h+var_6B4], sil
0x1800e4f1d  jz      loc_1800E5061
0x1800e4f23  mov     ebx, cs:dword_18011996C
0x1800e4f29  mov     ecx, ebx
0x1800e4f2b  test    ebx, ebx
0x1800e4f2d  jz      loc_1800E5042
0x1800e4f33  sub     ecx, esi
0x1800e4f35  jz      loc_1800E5042
0x1800e4f3b  sub     ecx, esi
0x1800e4f3d  jz      loc_1800E5042
0x1800e4f43  sub     ecx, esi
0x1800e4f45  jz      loc_1800E5035
0x1800e4f4b  cmp     ecx, esi
0x1800e4f4d  jnz     loc_1800E5061
0x1800e4f53  mov     rcx, gs:60h
0x1800e4f5c  lea     edx, [rsi+7]; Flags
0x1800e4f5f  mov     r8d, 20Ah; Size
0x1800e4f65  mov     rcx, [rcx+30h]; HeapHandle
0x1800e4f69  call    cs:__imp_RtlAllocateHeap
0x1800e4f6f  mov     [rdi+2A78h], rax
0x1800e4f76  test    rax, rax
0x1800e4f79  jnz     short loc_1800E4FA3
0x1800e4f7b  lea     r9, aFailedToAllocM_0; "Failed to alloc memory for string value"...
0x1800e4f82  mov     dword ptr [rsp+700h+var_6E0], 13h
0x1800e4f8a  mov     r8d, 0C48h
0x1800e4f90  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x1800e4f97  mov     ecx, esi
0x1800e4f99  call    AslLogCallPrintf
0x1800e4f9e  jmp     loc_1800E5061
0x1800e4fa3  mov     r9d, 104h; N
0x1800e4fa9  lea     r8, [rbp+600h+S2]; S2
0x1800e4fad  mov     rcx, rax; S1
0x1800e4fb0  lea     edx, [r9+1]; N1
0x1800e4fb4  call    _o_wmemcpy_s_0
0x1800e4fb9  test    eax, eax
0x1800e4fbb  jz      short loc_1800E501C
0x1800e4fbd  jle     short loc_1800E4FC7
0x1800e4fbf  movzx   eax, ax
0x1800e4fc2  or      eax, 80070000h
0x1800e4fc7  mov     dword ptr [rsp+700h+var_6D8], eax
0x1800e4fcb  lea     r9, aFailedToCopyAt; "Failed to copy attribute value (index %"...
0x1800e4fd2  mov     r8d, 0C54h
0x1800e4fd8  mov     dword ptr [rsp+700h+var_6E0], 13h
0x1800e4fe0  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x1800e4fe7  mov     ecx, esi
0x1800e4fe9  call    AslLogCallPrintf
0x1800e4fee  mov     r8, [rdi+2A78h]; P
0x1800e4ff5  test    r8, r8
0x1800e4ff8  jz      short loc_1800E5061
0x1800e4ffa  mov     rcx, gs:60h
0x1800e5003  xor     edx, edx; Flags
0x1800e5005  mov     rcx, [rcx+30h]; HeapHandle
0x1800e5009  call    cs:__imp_RtlFreeHeap
0x1800e500f  mov     qword ptr [rdi+2A78h], 0
0x1800e501a  jmp     short loc_1800E5061
0x1800e501c  mov     rcx, [rdi+2A78h]
0x1800e5023  xor     eax, eax
0x1800e5025  mov     [rcx+208h], ax
0x1800e502c  mov     [rdi+2860h], ax
0x1800e5033  jmp     short loc_1800E504B
0x1800e5035  mov     rax, qword ptr [rbp+600h+S2]
0x1800e5039  mov     [rdi+2860h], rax
0x1800e5040  jmp     short loc_1800E504B
0x1800e5042  mov     eax, dword ptr [rbp+600h+S2]
0x1800e5045  mov     [rdi+2860h], eax
0x1800e504b  mov     dword ptr [rdi+2A68h], 13h
0x1800e5055  mov     [rdi+2A6Ch], ebx
0x1800e505b  mov     [rdi+2A70h], esi
0x1800e5061  test    [rsp+700h+var_6B4], 2
0x1800e5066  jz      loc_1800E51B5
0x1800e506c  mov     ebx, cs:dword_180119984
0x1800e5072  mov     ecx, ebx
0x1800e5074  test    ebx, ebx
0x1800e5076  jz      loc_1800E5193
0x1800e507c  sub     ecx, esi
0x1800e507e  jz      loc_1800E5193
0x1800e5084  sub     ecx, esi
0x1800e5086  jz      loc_1800E5193
0x1800e508c  sub     ecx, esi
0x1800e508e  jz      loc_1800E5183
0x1800e5094  cmp     ecx, esi
0x1800e5096  jnz     loc_1800E51B5
0x1800e509c  mov     rcx, gs:60h
0x1800e50a5  mov     edx, 8; Flags
0x1800e50aa  mov     r8d, 20Ah; Size
0x1800e50b0  mov     rcx, [rcx+30h]; HeapHandle
0x1800e50b4  call    cs:__imp_RtlAllocateHeap
0x1800e50ba  mov     [rdi+2C98h], rax
0x1800e50c1  test    rax, rax
0x1800e50c4  jnz     short loc_1800E50EE
0x1800e50c6  lea     r9, aFailedToAllocM_0; "Failed to alloc memory for string value"...
0x1800e50cd  mov     dword ptr [rsp+700h+var_6E0], 14h
0x1800e50d5  mov     r8d, 0C48h
0x1800e50db  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x1800e50e2  mov     ecx, esi
0x1800e50e4  call    AslLogCallPrintf
0x1800e50e9  jmp     loc_1800E51B5
0x1800e50ee  mov     r9d, 104h; N
0x1800e50f4  lea     r8, [rbp+600h+var_450]; S2
0x1800e50fb  mov     rcx, rax; S1
0x1800e50fe  lea     edx, [r9+1]; N1
0x1800e5102  call    _o_wmemcpy_s_0
0x1800e5107  test    eax, eax
0x1800e5109  jz      short loc_1800E516A
0x1800e510b  jle     short loc_1800E5115
0x1800e510d  movzx   eax, ax
0x1800e5110  or      eax, 80070000h
0x1800e5115  mov     dword ptr [rsp+700h+var_6D8], eax
0x1800e5119  lea     r9, aFailedToCopyAt; "Failed to copy attribute value (index %"...
0x1800e5120  mov     r8d, 0C54h
0x1800e5126  mov     dword ptr [rsp+700h+var_6E0], 14h
0x1800e512e  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x1800e5135  mov     ecx, esi
0x1800e5137  call    AslLogCallPrintf
0x1800e513c  mov     r8, [rdi+2C98h]; P
0x1800e5143  test    r8, r8
0x1800e5146  jz      short loc_1800E51B5
0x1800e5148  mov     rcx, gs:60h
0x1800e5151  xor     edx, edx; Flags
0x1800e5153  mov     rcx, [rcx+30h]; HeapHandle
0x1800e5157  call    cs:__imp_RtlFreeHeap
0x1800e515d  mov     qword ptr [rdi+2C98h], 0
0x1800e5168  jmp     short loc_1800E51B5
0x1800e516a  mov     rcx, [rdi+2C98h]
0x1800e5171  xor     eax, eax
0x1800e5173  mov     [rcx+208h], ax
0x1800e517a  mov     [rdi+2A80h], ax
0x1800e5181  jmp     short loc_1800E519F
0x1800e5183  mov     rax, qword ptr [rbp+600h+var_450]
0x1800e518a  mov     [rdi+2A80h], rax
0x1800e5191  jmp     short loc_1800E519F
0x1800e5193  mov     eax, dword ptr [rbp+600h+var_450]
0x1800e5199  mov     [rdi+2A80h], eax
0x1800e519f  mov     dword ptr [rdi+2C88h], 14h
0x1800e51a9  mov     [rdi+2C8Ch], ebx
0x1800e51af  mov     [rdi+2C90h], esi
0x1800e51b5  test    [rsp+700h+var_6B4], 4
0x1800e51ba  jz      loc_1800E5309
0x1800e51c0  mov     ebx, cs:dword_18011999C
0x1800e51c6  mov     ecx, ebx
0x1800e51c8  test    ebx, ebx
0x1800e51ca  jz      loc_1800E52E7
0x1800e51d0  sub     ecx, esi
0x1800e51d2  jz      loc_1800E52E7
0x1800e51d8  sub     ecx, esi
0x1800e51da  jz      loc_1800E52E7
0x1800e51e0  sub     ecx, esi
0x1800e51e2  jz      loc_1800E52D7
0x1800e51e8  cmp     ecx, esi
0x1800e51ea  jnz     loc_1800E5309
0x1800e51f0  mov     rcx, gs:60h
0x1800e51f9  mov     edx, 8; Flags
0x1800e51fe  mov     r8d, 20Ah; Size
0x1800e5204  mov     rcx, [rcx+30h]; HeapHandle
0x1800e5208  call    cs:__imp_RtlAllocateHeap
0x1800e520e  mov     [rdi+2EB8h], rax
0x1800e5215  test    rax, rax
0x1800e5218  jnz     short loc_1800E5242
0x1800e521a  lea     r9, aFailedToAllocM_0; "Failed to alloc memory for string value"...
0x1800e5221  mov     dword ptr [rsp+700h+var_6E0], 15h
0x1800e5229  mov     r8d, 0C48h
0x1800e522f  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x1800e5236  mov     ecx, esi
0x1800e5238  call    AslLogCallPrintf
0x1800e523d  jmp     loc_1800E5309
0x1800e5242  mov     r9d, 104h; N
0x1800e5248  lea     r8, [rbp+600h+var_240]; S2
0x1800e524f  mov     rcx, rax; S1
0x1800e5252  lea     edx, [r9+1]; N1
0x1800e5256  call    _o_wmemcpy_s_0
0x1800e525b  test    eax, eax
0x1800e525d  jz      short loc_1800E52BE
0x1800e525f  jle     short loc_1800E5269
0x1800e5261  movzx   eax, ax
0x1800e5264  or      eax, 80070000h
0x1800e5269  mov     dword ptr [rsp+700h+var_6D8], eax
0x1800e526d  lea     r9, aFailedToCopyAt; "Failed to copy attribute value (index %"...
  ... truncated ...
```
