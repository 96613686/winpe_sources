# InitializeDirectDrawGlobals(void)

- ea: `0x1800a3ed4`
- end: `0x1800a401e`
- name: `?InitializeDirectDrawGlobals@@YAHXZ`
- size: `330`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800a3a28`

## callees

- `0x1800a3ed4`
- `0x180169010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800a3f1f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800a3f1f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a3f3f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a3f63`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a3f87`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a3f3f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a3f63`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a3f87`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a3f02`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a3f02`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a4011`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a4011`

## string_xrefs

- `0x1800a3f0d`: `ddraw.dll`
- `0x1800a3f5c`: `DirectDrawCreateEx`

## pseudocode

```c
__int64 InitializeDirectDrawGlobals(void)
{
  unsigned int v1; // ebx
  HMODULE Library; // rax

  if ( Globals::DirectDrawInitialized )
    return 1;
  if ( Globals::DirectDrawInitAttempted )
    return 0;
  EnterCriticalSection(&LoadLibraryCriticalSection::critSec);
  v1 = 1;
  Globals::DirectDrawInitAttempted = 1;
  Library = LoadLibraryExA("ddraw.dll", 0, 0);
  Globals::DdrawHandle = Library;
  if ( Library
    && (Globals::GetDdrawSurfaceFromDcFunction = (int (*)(HDC, struct IDirectDrawSurface **, HDC *))GetProcAddress(Library, "GetSurfaceFromDC")) != 0
    && (Globals::DirectDrawCreateExFunction = (int (*)(struct _GUID *, void *, const struct _GUID *, struct IUnknown *))GetProcAddress(Globals::DdrawHandle, "DirectDrawCreateEx")) != 0
    && (Globals::DirectDrawEnumerateExFunction = (int (*)(int (*)(struct _GUID *, char *, char *, void *, HMONITOR), void *, unsigned int))GetProcAddress(Globals::DdrawHandle, "DirectDrawEnumerateExA")) != 0
    && (int)((__int64 (__fastcall *)(_QWORD, struct IDirectDraw7 **, GUID *, _QWORD))Globals::DirectDrawCreateExFunction)(
              0,
              &Globals::DirectDraw,
              &IID_IDirectDraw7,
              0) >= 0
    && ((int (__fastcall *)(struct IDirectDraw7 *, _QWORD, __int64))Globals::DirectDraw->lpVtbl->SetCooperativeLevel)(
         Globals::DirectDraw,
         0,
         8) >= 0
    && ((__int64 (__fastcall *)(struct IDirectDraw7 *, GUID *, struct IDirect3D7 **))Globals::DirectDraw->lpVtbl->QueryInterface)(
         Globals::DirectDraw,
         &IID_IDirect3D7,
         &Globals::Direct3D) >= 0 )
  {
    Globals::DirectDrawInitialized = 1;
  }
  else
  {
    v1 = 0;
  }
  LeaveCriticalSection(&LoadLibraryCriticalSection::critSec);
  return v1;
}

```

## disassembly

```asm
0x1800a3ed4  push    rbx
0x1800a3ed6  sub     rsp, 30h
0x1800a3eda  cmp     cs:?DirectDrawInitialized@Globals@@3HA, 0; int Globals::DirectDrawInitialized
0x1800a3ee1  jnz     short loc_1800A3EF4
0x1800a3ee3  cmp     cs:?DirectDrawInitAttempted@Globals@@3HA, 0; int Globals::DirectDrawInitAttempted
0x1800a3eea  jz      short loc_1800A3EFB
0x1800a3eec  xor     eax, eax
0x1800a3eee  add     rsp, 30h
0x1800a3ef2  pop     rbx
0x1800a3ef3  retn
0x1800a3ef4  mov     eax, 1
0x1800a3ef9  jmp     short loc_1800A3EEE
0x1800a3efb  lea     rcx, ?critSec@LoadLibraryCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800a3f02  call    cs:__imp_EnterCriticalSection
0x1800a3f08  mov     ebx, 1
0x1800a3f0d  lea     rcx, aDdrawDll; "ddraw.dll"
0x1800a3f14  xor     r8d, r8d; dwFlags
0x1800a3f17  mov     cs:?DirectDrawInitAttempted@Globals@@3HA, ebx; int Globals::DirectDrawInitAttempted
0x1800a3f1d  xor     edx, edx; hFile
0x1800a3f1f  call    cs:__imp_LoadLibraryExA
0x1800a3f25  mov     cs:?DdrawHandle@Globals@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * Globals::DdrawHandle
0x1800a3f2c  test    rax, rax
0x1800a3f2f  jz      loc_1800A4008
0x1800a3f35  lea     rdx, aGetsurfacefrom; "GetSurfaceFromDC"
0x1800a3f3c  mov     rcx, rax; hModule
0x1800a3f3f  call    cs:__imp_GetProcAddress
0x1800a3f45  mov     cs:?GetDdrawSurfaceFromDcFunction@Globals@@3P6AJPEAUHDC__@@PEAPEAUIDirectDrawSurface@@PEAPEAU2@@ZEA, rax; long (*Globals::GetDdrawSurfaceFromDcFunction)(HDC__ *,IDirectDrawSurface * *,HDC__ * *)
0x1800a3f4c  test    rax, rax
0x1800a3f4f  jz      loc_1800A4008
0x1800a3f55  mov     rcx, cs:?DdrawHandle@Globals@@3PEAUHINSTANCE__@@EA; hModule
0x1800a3f5c  lea     rdx, aDirectdrawcrea; "DirectDrawCreateEx"
0x1800a3f63  call    cs:__imp_GetProcAddress
0x1800a3f69  mov     cs:?DirectDrawCreateExFunction@Globals@@3P6AJPEAU_GUID@@PEAXAEBU2@PEAUIUnknown@@@ZEA, rax; long (*Globals::DirectDrawCreateExFunction)(_GUID *,void *,_GUID const &,IUnknown *)
0x1800a3f70  test    rax, rax
0x1800a3f73  jz      loc_1800A4008
0x1800a3f79  mov     rcx, cs:?DdrawHandle@Globals@@3PEAUHINSTANCE__@@EA; hModule
0x1800a3f80  lea     rdx, aDirectdrawenum; "DirectDrawEnumerateExA"
0x1800a3f87  call    cs:__imp_GetProcAddress
0x1800a3f8d  mov     cs:?DirectDrawEnumerateExFunction@Globals@@3P6AJP6AHPEAU_GUID@@PEAD1PEAXPEAUHMONITOR__@@@Z2K@ZEA, rax; long (*Globals::DirectDrawEnumerateExFunction)(int (*)(_GUID *,char *,char *,void *,HMONITOR__ *),void *,ulong)
0x1800a3f94  test    rax, rax
0x1800a3f97  jz      short loc_1800A4008
0x1800a3f99  mov     rax, cs:?DirectDrawCreateExFunction@Globals@@3P6AJPEAU_GUID@@PEAXAEBU2@PEAUIUnknown@@@ZEA; long (*Globals::DirectDrawCreateExFunction)(_GUID *,void *,_GUID const &,IUnknown *)
0x1800a3fa0  lea     r8, IID_IDirectDraw7
0x1800a3fa7  xor     r9d, r9d
0x1800a3faa  lea     rdx, ?DirectDraw@Globals@@3PEAUIDirectDraw7@@EA; IDirectDraw7 * Globals::DirectDraw
0x1800a3fb1  xor     ecx, ecx
0x1800a3fb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3fb8  test    eax, eax
0x1800a3fba  js      short loc_1800A4008
0x1800a3fbc  mov     rcx, cs:?DirectDraw@Globals@@3PEAUIDirectDraw7@@EA; IDirectDraw7 * Globals::DirectDraw
0x1800a3fc3  lea     r8d, [rbx+7]
0x1800a3fc7  xor     edx, edx
0x1800a3fc9  mov     rax, [rcx]
0x1800a3fcc  mov     rax, [rax+0A0h]
0x1800a3fd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3fd8  test    eax, eax
0x1800a3fda  js      short loc_1800A4008
0x1800a3fdc  mov     rcx, cs:?DirectDraw@Globals@@3PEAUIDirectDraw7@@EA; IDirectDraw7 * Globals::DirectDraw
0x1800a3fe3  lea     r8, ?Direct3D@Globals@@3PEAUIDirect3D7@@EA; IDirect3D7 * Globals::Direct3D
0x1800a3fea  lea     rdx, IID_IDirect3D7
0x1800a3ff1  mov     rax, [rcx]
0x1800a3ff4  mov     rax, [rax]
0x1800a3ff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3ffc  test    eax, eax
0x1800a3ffe  js      short loc_1800A4008
0x1800a4000  mov     cs:?DirectDrawInitialized@Globals@@3HA, ebx; int Globals::DirectDrawInitialized
0x1800a4006  jmp     short loc_1800A400A
0x1800a4008  xor     ebx, ebx
0x1800a400a  lea     rcx, ?critSec@LoadLibraryCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800a4011  call    cs:__imp_LeaveCriticalSection
0x1800a4017  mov     eax, ebx
0x1800a4019  jmp     loc_1800A3EEE
```
