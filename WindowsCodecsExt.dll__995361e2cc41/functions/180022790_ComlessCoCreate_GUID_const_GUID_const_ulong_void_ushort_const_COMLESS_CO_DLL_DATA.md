# ComlessCoCreate(_GUID const &,_GUID const &,ulong,void * *,ushort const *,_COMLESS_CO_DLL_DATA &)

- ea: `0x180022790`
- end: `0x180022874`
- name: `?ComlessCoCreate@@YAJAEBU_GUID@@0KPEAPEAXPEBGAEAU_COMLESS_CO_DLL_DATA@@@Z`
- size: `228`
- prototype: `__int64 __fastcall(const struct _GUID *, const struct _GUID *, unsigned int, void **, const unsigned __int16 *, struct _COMLESS_CO_DLL_DATA *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004004`
- `0x180004abc`

## callees

- `0x1800171c4`
- `0x180022790`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800227e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800227e7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800227cb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800227cb`

## string_xrefs

- `0x1800227dd`: `DllGetClassObject`
- `0x1800227be`: `WindowsCodecs.dll`

## pseudocode

```c
__int64 __fastcall ComlessCoCreate(const struct _GUID *a1, const struct _GUID *a2, __int64 a3, void **a4)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  unsigned int v9; // ebx
  int v10; // eax
  __int64 v12; // [rsp+78h] [rbp+20h] BYREF

  *a4 = 0;
  v12 = 0;
  if ( !qword_1800402E0 )
  {
    Library = LoadLibraryExW(L"WindowsCodecs.dll", 0, 0x800u);
    g_WindowsCodecs_DLL = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "DllGetClassObject");
      if ( ProcAddress )
        _InterlockedExchange64((volatile __int64 *)&qword_1800402E0, (__int64)ProcAddress);
    }
  }
  v9 = -2147467259;
  if ( qword_1800402E0 )
  {
    v10 = qword_1800402E0(a1, &IID_IClassFactory, &v12);
    v9 = v10;
    if ( v10 < 0
      || (v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, const struct _GUID *, void **))(*(_QWORD *)v12 + 24LL))(
                  v12,
                  0,
                  a2,
                  a4),
          v9 = v10,
          v10 < 0) )
    {
      if ( g_doStackCaptures )
        DoStackCapture(v10);
    }
  }
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  return v9;
}

```

## disassembly

```asm
0x180022790  push    rbx
0x180022792  push    rbp
0x180022793  push    rsi
0x180022794  push    rdi
0x180022795  sub     rsp, 38h
0x180022799  mov     qword ptr [r9], 0
0x1800227a0  mov     rdi, r9
0x1800227a3  cmp     cs:qword_1800402E0, 0
0x1800227ab  mov     rbp, rdx
0x1800227ae  mov     rsi, rcx
0x1800227b1  mov     [rsp+58h+arg_18], 0
0x1800227ba  jnz     short loc_1800227F9
0x1800227bc  xor     edx, edx; hFile
0x1800227be  lea     rcx, aWindowscodecsD_0; "WindowsCodecs.dll"
0x1800227c5  mov     r8d, 800h; dwFlags
0x1800227cb  call    cs:__imp_LoadLibraryExW
0x1800227d1  mov     cs:?g_WindowsCodecs_DLL@@3U_COMLESS_CO_DLL_DATA@@A, rax; _COMLESS_CO_DLL_DATA g_WindowsCodecs_DLL
0x1800227d8  test    rax, rax
0x1800227db  jz      short loc_1800227F9
0x1800227dd  lea     rdx, aDllgetclassobj_0; "DllGetClassObject"
0x1800227e4  mov     rcx, rax; hModule
0x1800227e7  call    cs:__imp_GetProcAddress
0x1800227ed  test    rax, rax
0x1800227f0  jz      short loc_1800227F9
0x1800227f2  xchg    rax, cs:qword_1800402E0
0x1800227f9  mov     rax, cs:qword_1800402E0
0x180022800  mov     ebx, 80004005h
0x180022805  test    rax, rax
0x180022808  jz      short loc_180022853
0x18002280a  lea     r8, [rsp+58h+arg_18]
0x18002280f  mov     rcx, rsi
0x180022812  lea     rdx, IID_IClassFactory
0x180022819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002281e  mov     ebx, eax
0x180022820  test    eax, eax
0x180022822  js      short loc_180022843
0x180022824  mov     rcx, [rsp+58h+arg_18]
0x180022829  mov     r9, rdi
0x18002282c  mov     r8, rbp
0x18002282f  xor     edx, edx
0x180022831  mov     rax, [rcx]
0x180022834  mov     rax, [rax+18h]
0x180022838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002283d  mov     ebx, eax
0x18002283f  test    eax, eax
0x180022841  jns     short loc_180022853
0x180022843  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18002284a  jz      short loc_180022853
0x18002284c  mov     ecx, eax; int
0x18002284e  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180022853  mov     rcx, [rsp+58h+arg_18]
0x180022858  test    rcx, rcx
0x18002285b  jz      short loc_180022869
0x18002285d  mov     rdx, [rcx]
0x180022860  mov     rax, [rdx+10h]
0x180022864  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022869  mov     eax, ebx
0x18002286b  add     rsp, 38h
0x18002286f  pop     rdi
0x180022870  pop     rsi
0x180022871  pop     rbp
0x180022872  pop     rbx
0x180022873  retn
```
