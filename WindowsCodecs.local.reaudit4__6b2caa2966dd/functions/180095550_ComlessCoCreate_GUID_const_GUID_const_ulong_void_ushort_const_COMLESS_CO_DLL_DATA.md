# ComlessCoCreate(_GUID const &,_GUID const &,ulong,void * *,ushort const *,_COMLESS_CO_DLL_DATA &)

- ea: `0x180095550`
- end: `0x18009565d`
- name: `?ComlessCoCreate@@YAJAEBU_GUID@@0KPEAPEAXPEBGAEAU_COMLESS_CO_DLL_DATA@@@Z`
- size: `269`
- prototype: `__int64 __fastcall(const struct _GUID *, const struct _GUID *, unsigned int, void **, LPCWSTR lpLibFileName, struct _COMLESS_CO_DLL_DATA *)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180094de0`
- `0x1800951c0`
- `0x180095390`

## callees

- `0x180095550`
- `0x1800bd9d4`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009563f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009563f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18009561d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18009561d`

## string_xrefs

- `0x180095635`: `DllGetClassObject`

## pseudocode

```c
__int64 __fastcall ComlessCoCreate(
        const struct _GUID *a1,
        const struct _GUID *a2,
        __int64 a3,
        void **a4,
        LPCWSTR lpLibFileName,
        struct _COMLESS_CO_DLL_DATA *a6)
{
  struct _COMLESS_CO_DLL_DATA *v6; // rdi
  __int64 (__fastcall *v10)(const struct _GUID *, GUID *, __int64 *); // rax
  unsigned int v11; // ebx
  int v12; // eax
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v16; // [rsp+68h] [rbp+20h] BYREF

  v6 = a6;
  *a4 = 0;
  v16 = 0;
  if ( !*((_QWORD *)v6 + 1) )
  {
    Library = LoadLibraryExW(lpLibFileName, 0, 0x800u);
    *(_QWORD *)v6 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "DllGetClassObject");
      if ( ProcAddress )
        _InterlockedExchange64((volatile __int64 *)v6 + 1, (__int64)ProcAddress);
    }
  }
  v10 = (__int64 (__fastcall *)(const struct _GUID *, GUID *, __int64 *))*((_QWORD *)v6 + 1);
  v11 = -2147467259;
  if ( v10 )
  {
    v12 = v10(a1, &IID_IClassFactory, &v16);
    v11 = v12;
    if ( v12 < 0
      || (v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, const struct _GUID *, void **))(*(_QWORD *)v16 + 24LL))(
                  v16,
                  0,
                  a2,
                  a4),
          v11 = v12,
          v12 < 0) )
    {
      if ( (_DWORD)g_doStackCaptures )
        DoStackCapture(v12);
    }
  }
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  return v11;
}

```

## disassembly

```asm
0x180095550  mov     [rsp+arg_0], rbx
0x180095555  mov     [rsp+arg_8], rbp
0x18009555a  push    rsi
0x18009555b  push    rdi
0x18009555c  push    r14
0x18009555e  sub     rsp, 30h
0x180095562  mov     rdi, [rsp+48h+arg_28]
0x180095567  mov     rsi, r9
0x18009556a  mov     qword ptr [r9], 0
0x180095571  mov     r14, rdx
0x180095574  mov     rbp, rcx
0x180095577  mov     [rsp+48h+arg_18], 0
0x180095580  cmp     qword ptr [rdi+8], 0
0x180095585  jz      loc_180095610
0x18009558b  mov     rax, [rdi+8]
0x18009558f  mov     ebx, 80004005h
0x180095594  test    rax, rax
0x180095597  jz      short loc_1800955D2
0x180095599  lea     r8, [rsp+48h+arg_18]
0x18009559e  mov     rcx, rbp
0x1800955a1  lea     rdx, IID_IClassFactory
0x1800955a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800955ad  mov     ebx, eax
0x1800955af  test    eax, eax
0x1800955b1  js      short loc_1800955FE
0x1800955b3  mov     rcx, [rsp+48h+arg_18]
0x1800955b8  mov     r9, rsi
0x1800955bb  mov     r8, r14
0x1800955be  xor     edx, edx
0x1800955c0  mov     rax, [rcx]
0x1800955c3  mov     rax, [rax+18h]
0x1800955c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800955cc  mov     ebx, eax
0x1800955ce  test    eax, eax
0x1800955d0  js      short loc_1800955FE
0x1800955d2  mov     rcx, [rsp+48h+arg_18]
0x1800955d7  test    rcx, rcx
0x1800955da  jz      short loc_1800955E8
0x1800955dc  mov     rdx, [rcx]
0x1800955df  mov     rax, [rdx+10h]
0x1800955e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800955e8  mov     rbp, [rsp+48h+arg_8]
0x1800955ed  mov     eax, ebx
0x1800955ef  mov     rbx, [rsp+48h+arg_0]
0x1800955f4  add     rsp, 30h
0x1800955f8  pop     r14
0x1800955fa  pop     rdi
0x1800955fb  pop     rsi
0x1800955fc  retn
0x1800955fe  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180095605  jz      short loc_1800955D2
0x180095607  mov     ecx, eax; int
0x180095609  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18009560e  jmp     short loc_1800955D2
0x180095610  mov     rcx, [rsp+48h+lpLibFileName]; lpLibFileName
0x180095615  xor     edx, edx; hFile
0x180095617  mov     r8d, 800h; dwFlags
0x18009561d  call    cs:__imp_LoadLibraryExW
0x180095624  nop     dword ptr [rax+rax+00h]
0x180095629  mov     [rdi], rax
0x18009562c  test    rax, rax
0x18009562f  jz      loc_18009558B
0x180095635  lea     rdx, ProcName; "DllGetClassObject"
0x18009563c  mov     rcx, rax; hModule
0x18009563f  call    cs:__imp_GetProcAddress
0x180095646  nop     dword ptr [rax+rax+00h]
0x18009564b  test    rax, rax
0x18009564e  jz      loc_18009558B
0x180095654  xchg    rax, [rdi+8]
0x180095658  jmp     loc_18009558B
```
