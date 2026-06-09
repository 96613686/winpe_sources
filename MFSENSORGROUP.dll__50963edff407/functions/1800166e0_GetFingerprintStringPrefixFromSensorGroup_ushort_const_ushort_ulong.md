# GetFingerprintStringPrefixFromSensorGroup(ushort const *,ushort *,ulong)

- ea: `0x1800166e0`
- end: `0x1800169a3`
- name: `?GetFingerprintStringPrefixFromSensorGroup@@YAJPEBGPEAGK@Z`
- size: `707`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000f5c8`
- `0x180016690`

## callees

- `0x1800166e0`
- `0x180076280`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180016734`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180016734`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016750`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016750`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001693d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001693d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016932`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016964`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016932`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016964`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016945`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016945`

## string_xrefs

- `0x180016746`: `MFCreateSensorGroupIdManager`
- `0x180016718`: `mfsensorgroup.dll`

## pseudocode

```c
__int64 __fastcall GetFingerprintStringPrefixFromSensorGroup(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  HMODULE Library; // rax
  HMODULE v5; // rsi
  FARPROC ProcAddress; // rbx
  signed int v7; // edi
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 (__fastcall ***v10)(__int64, GUID *, __int64 *); // rbx
  __int64 (__fastcall **v11)(__int64, GUID *, __int64 *); // rax
  __int64 (__fastcall *v12)(__int64, GUID *, __int64 *); // rdi
  __int64 *v13; // rcx
  __int64 (__fastcall ***v14)(__int64, GUID *, __int64 *); // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  DWORD v18; // ebx
  signed int LastError; // eax
  unsigned int v20; // eax
  __int64 (__fastcall ***v21)(__int64, GUID *, __int64 *); // [rsp+30h] [rbp-20h] BYREF
  __int64 *v22; // [rsp+38h] [rbp-18h] BYREF
  void *Src; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v24; // [rsp+90h] [rbp+40h] BYREF
  __int64 v25; // [rsp+98h] [rbp+48h] BYREF

  v22 = 0;
  v21 = 0;
  v25 = 0;
  Src = 0;
  v24 = 0;
  Library = LoadLibraryExW(L"mfsensorgroup.dll", 0, 0x800u);
  v5 = Library;
  if ( Library && (ProcAddress = GetProcAddress(Library, "MFCreateSensorGroupIdManager")) != 0 )
  {
    v22 = 0;
    v7 = ((__int64 (__fastcall *)(__int64 **))ProcAddress)(&v22);
    if ( v7 >= 0 )
    {
      v8 = *v22;
      v21 = 0;
      v7 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, __int64 (__fastcall ****)(__int64, GUID *, __int64 *)))(v8 + 32))(
             v22,
             0,
             0,
             &v21);
      if ( v7 >= 0 )
      {
        v9 = v25;
        v10 = v21;
        v11 = *v21;
        v25 = 0;
        v12 = *v11;
        if ( v9 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        v7 = v12((__int64)v10, &GUID_1725de0f_cf7a_4075_9365_d8c5d1eea8d7, &v25);
        if ( v7 >= 0 )
        {
          v7 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v25 + 64LL))(v25, a1);
          if ( v7 >= 0 )
          {
            v7 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v25 + 72LL))(v25, 0);
            if ( v7 >= 0 )
            {
              v7 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, void **, unsigned int *))(*(_QWORD *)v25 + 192LL))(
                     v25,
                     11,
                     0,
                     &Src,
                     &v24);
              if ( v7 >= 0 )
              {
                if ( Src && (v20 = v24) != 0 )
                {
                  if ( v24 > 0xD2 )
                    v20 = 210;
                  memcpy_0(a2, Src, v20);
                }
                else
                {
                  v7 = -1072875819;
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
  }
  v13 = v22;
  v22 = 0;
  if ( v13 )
    (*(void (__fastcall **)(__int64 *))(*v13 + 16))(v13);
  v14 = v21;
  v21 = 0;
  if ( v14 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 *)))(*v14)[2])(v14);
  v15 = v25;
  v16 = 0;
  v25 = 0;
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    v16 = v25;
  }
  if ( v5 )
  {
    v18 = GetLastError();
    FreeLibrary(v5);
    SetLastError(v18);
    v16 = v25;
  }
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  if ( v21 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 *)))(*v21)[2])(v21);
  if ( v22 )
    (*(void (__fastcall **)(__int64 *))(*v22 + 16))(v22);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800166e0  mov     [rsp-28h+arg_0], rbx
0x1800166e5  mov     [rsp-28h+arg_10], r8d
0x1800166ea  push    rbp
0x1800166eb  push    rsi
0x1800166ec  push    rdi
0x1800166ed  push    r14
0x1800166ef  push    r15
0x1800166f1  mov     rbp, rsp
0x1800166f4  sub     rsp, 50h
0x1800166f8  mov     r15, rdx
0x1800166fb  mov     [rbp+var_18], 0
0x180016703  mov     r14, rcx
0x180016706  mov     [rbp+var_20], 0
0x18001670e  xor     edx, edx; hFile
0x180016710  mov     [rbp+arg_18], 0
0x180016718  lea     rcx, LibFileName; "mfsensorgroup.dll"
0x18001671f  mov     [rbp+Src], 0
0x180016727  mov     r8d, 800h; dwFlags
0x18001672d  mov     [rbp+arg_10], 0
0x180016734  call    cs:__imp_LoadLibraryExW
0x18001673a  mov     rsi, rax
0x18001673d  test    rax, rax
0x180016740  jz      loc_180016964
0x180016746  lea     rdx, ProcName; "MFCreateSensorGroupIdManager"
0x18001674d  mov     rcx, rax; hModule
0x180016750  call    cs:__imp_GetProcAddress
0x180016756  mov     rbx, rax
0x180016759  test    rax, rax
0x18001675c  jz      loc_180016964
0x180016762  mov     rcx, [rbp+var_18]
0x180016766  mov     [rbp+var_18], 0
0x18001676e  test    rcx, rcx
0x180016771  jz      short loc_18001677F
0x180016773  mov     rax, [rcx]
0x180016776  mov     rax, [rax+10h]
0x18001677a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001677f  lea     rcx, [rbp+var_18]
0x180016783  mov     rax, rbx
0x180016786  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001678b  mov     edi, eax
0x18001678d  test    eax, eax
0x18001678f  js      loc_180016880
0x180016795  mov     rcx, [rbp+var_20]
0x180016799  mov     rbx, [rbp+var_18]
0x18001679d  mov     rax, [rbx]
0x1800167a0  mov     [rbp+var_20], 0
0x1800167a8  mov     rdi, [rax+20h]
0x1800167ac  test    rcx, rcx
0x1800167af  jz      short loc_1800167BD
0x1800167b1  mov     rdx, [rcx]
0x1800167b4  mov     rax, [rdx+10h]
0x1800167b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167bd  lea     r9, [rbp+var_20]
0x1800167c1  xor     r8d, r8d
0x1800167c4  xor     edx, edx
0x1800167c6  mov     rcx, rbx
0x1800167c9  mov     rax, rdi
0x1800167cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167d1  mov     edi, eax
0x1800167d3  test    eax, eax
0x1800167d5  js      loc_180016880
0x1800167db  mov     rcx, [rbp+arg_18]
0x1800167df  mov     rbx, [rbp+var_20]
0x1800167e3  mov     rax, [rbx]
0x1800167e6  mov     [rbp+arg_18], 0
0x1800167ee  mov     rdi, [rax]
0x1800167f1  test    rcx, rcx
0x1800167f4  jz      short loc_180016802
0x1800167f6  mov     rdx, [rcx]
0x1800167f9  mov     rax, [rdx+10h]
0x1800167fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016802  lea     r8, [rbp+arg_18]
0x180016806  mov     rcx, rbx
0x180016809  lea     rdx, _GUID_1725de0f_cf7a_4075_9365_d8c5d1eea8d7
0x180016810  mov     rax, rdi
0x180016813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016818  mov     edi, eax
0x18001681a  test    eax, eax
0x18001681c  js      short loc_180016880
0x18001681e  mov     rcx, [rbp+arg_18]
0x180016822  mov     rdx, r14
0x180016825  mov     rax, [rcx]
0x180016828  mov     rax, [rax+40h]
0x18001682c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016831  mov     edi, eax
0x180016833  test    eax, eax
0x180016835  js      short loc_180016880
0x180016837  mov     rcx, [rbp+arg_18]
0x18001683b  xor     edx, edx
0x18001683d  mov     rax, [rcx]
0x180016840  mov     rax, [rax+48h]
0x180016844  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016849  mov     edi, eax
0x18001684b  test    eax, eax
0x18001684d  js      short loc_180016880
0x18001684f  mov     rcx, [rbp+arg_18]
0x180016853  lea     rdx, [rbp+arg_10]
0x180016857  xor     r8d, r8d
0x18001685a  mov     [rsp+50h+var_30], rdx
0x18001685f  lea     r9, [rbp+Src]
0x180016863  mov     rax, [rcx]
0x180016866  lea     edx, [r8+0Bh]
0x18001686a  mov     rax, [rax+0C0h]
0x180016871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016876  mov     edi, eax
0x180016878  test    eax, eax
0x18001687a  jns     loc_180016951
0x180016880  mov     rcx, [rbp+var_18]
0x180016884  mov     [rbp+var_18], 0
0x18001688c  test    rcx, rcx
0x18001688f  jz      short loc_18001689D
0x180016891  mov     rax, [rcx]
0x180016894  mov     rax, [rax+10h]
0x180016898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001689d  mov     rcx, [rbp+var_20]
0x1800168a1  mov     [rbp+var_20], 0
0x1800168a9  test    rcx, rcx
0x1800168ac  jz      short loc_1800168BA
0x1800168ae  mov     rax, [rcx]
0x1800168b1  mov     rax, [rax+10h]
0x1800168b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168ba  mov     rdx, [rbp+arg_18]
0x1800168be  xor     ecx, ecx
0x1800168c0  mov     [rbp+arg_18], rcx
0x1800168c4  test    rdx, rdx
0x1800168c7  jz      short loc_1800168DC
0x1800168c9  mov     rax, [rdx]
0x1800168cc  mov     rcx, rdx
0x1800168cf  mov     rax, [rax+10h]
0x1800168d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168d8  mov     rcx, [rbp+arg_18]
0x1800168dc  test    rsi, rsi
0x1800168df  jnz     short loc_180016932
0x1800168e1  test    rcx, rcx
0x1800168e4  jz      short loc_1800168F2
0x1800168e6  mov     rax, [rcx]
0x1800168e9  mov     rax, [rax+10h]
0x1800168ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168f2  mov     rcx, [rbp+var_20]
0x1800168f6  test    rcx, rcx
0x1800168f9  jz      short loc_180016907
0x1800168fb  mov     rax, [rcx]
0x1800168fe  mov     rax, [rax+10h]
0x180016902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016907  mov     rcx, [rbp+var_18]
0x18001690b  test    rcx, rcx
0x18001690e  jz      short loc_18001691C
0x180016910  mov     rax, [rcx]
0x180016913  mov     rax, [rax+10h]
0x180016917  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001691c  mov     rbx, [rsp+50h+arg_0]
0x180016924  mov     eax, edi
0x180016926  add     rsp, 50h
0x18001692a  pop     r15
0x18001692c  pop     r14
0x18001692e  pop     rdi
0x18001692f  pop     rsi
0x180016930  pop     rbp
0x180016931  retn
0x180016932  call    cs:__imp_GetLastError
0x180016938  mov     rcx, rsi; hLibModule
0x18001693b  mov     ebx, eax
0x18001693d  call    cs:__imp_FreeLibrary
0x180016943  mov     ecx, ebx; dwErrCode
0x180016945  call    cs:__imp_SetLastError
0x18001694b  mov     rcx, [rbp+arg_18]
0x18001694f  jmp     short loc_1800168E1
0x180016951  mov     rdx, [rbp+Src]; Src
0x180016955  test    rdx, rdx
0x180016958  jnz     short loc_180016982
0x18001695a  mov     edi, 0C00D36D5h
0x18001695f  jmp     loc_180016880
0x180016964  call    cs:__imp_GetLastError
0x18001696a  mov     edi, eax
0x18001696c  test    eax, eax
0x18001696e  jle     loc_180016880
0x180016974  movzx   edi, ax
0x180016977  or      edi, 80070000h
0x18001697d  jmp     loc_180016880
0x180016982  mov     eax, [rbp+arg_10]
0x180016985  test    eax, eax
0x180016987  jz      short loc_18001695A
0x180016989  mov     ecx, 0D2h
0x18001698e  cmp     eax, ecx
0x180016990  cmova   eax, ecx
0x180016993  mov     rcx, r15; void *
0x180016996  mov     r8d, eax; Size
0x180016999  call    memcpy_0
0x18001699e  jmp     loc_180016880
```
