# _PictFreeLibraries(void)

- ea: `0x18001fea0`
- end: `0x18001ff58`
- name: `?_PictFreeLibraries@@YAJXZ`
- size: `184`
- prototype: `int __fastcall()`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001fab4`
- `0x18001fb94`

## callees

- `0x18001fea0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001fec8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001fef3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001fec8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001fef3`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18001ff13`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18001ff25`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18001ff37`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18001ff4d`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18001ff13`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18001ff25`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18001ff37`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18001ff4d`

## pseudocode

```c
__int64 __fastcall _PictFreeLibraries()
{
  if ( g_hURLMonDLL )
  {
    FreeLibrary(g_hURLMonDLL);
    g_hURLMonDLL = 0;
    g_fnCreateURLMoniker = 0;
    g_fnCreateAsyncBindCtx = 0;
    g_fnRegisterBindStatusCallback = 0;
    g_fnRevokeBindStatusCallback = 0;
  }
  if ( g_hFilterDLL )
  {
    FreeLibrary(g_hFilterDLL);
    g_hFilterDLL = 0;
    g_fnFilterCreateInstance = 0;
    if ( ITA_DCWAIT )
      GlobalDeleteAtom(ITA_DCWAIT);
    if ( ITA_DISPLAY )
      GlobalDeleteAtom(ITA_DISPLAY);
    if ( ITA_ABNORMAL )
      GlobalDeleteAtom(ITA_ABNORMAL);
    if ( ITA_FINISHED )
      GlobalDeleteAtom(ITA_FINISHED);
  }
  return 0;
}

```

## disassembly

```asm
0x18001fea0  push    rbx
0x18001fea2  sub     rsp, 20h
0x18001fea6  mov     rcx, cs:?g_hURLMonDLL@@3PEAUHINSTANCE__@@EA; hLibModule
0x18001fead  xor     ebx, ebx
0x18001feaf  test    rcx, rcx
0x18001feb2  jnz     short loc_18001FEC8
0x18001feb4  mov     rcx, cs:?g_hFilterDLL@@3PEAUHINSTANCE__@@EA; hLibModule
0x18001febb  test    rcx, rcx
0x18001febe  jnz     short loc_18001FEF3
0x18001fec0  xor     eax, eax
0x18001fec2  add     rsp, 20h
0x18001fec6  pop     rbx
0x18001fec7  retn
0x18001fec8  call    cs:__imp_FreeLibrary
0x18001fece  mov     cs:?g_hURLMonDLL@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hURLMonDLL
0x18001fed5  mov     cs:?g_fnCreateURLMoniker@@3P6AJPEAUIMoniker@@PEBGPEAPEAU1@@ZEA, rbx; long (*g_fnCreateURLMoniker)(IMoniker *,ushort const *,IMoniker * *)
0x18001fedc  mov     cs:?g_fnCreateAsyncBindCtx@@3P6AJKPEAUIBindStatusCallback@@PEAUIEnumFORMATETC@@PEAPEAUIBindCtx@@@ZEA, rbx; long (*g_fnCreateAsyncBindCtx)(ulong,IBindStatusCallback *,IEnumFORMATETC *,IBindCtx * *)
0x18001fee3  mov     cs:?g_fnRegisterBindStatusCallback@@3P6AJPEAUIBindCtx@@PEAUIBindStatusCallback@@PEAPEAU2@K@ZEA, rbx; long (*g_fnRegisterBindStatusCallback)(IBindCtx *,IBindStatusCallback *,IBindStatusCallback * *,ulong)
0x18001feea  mov     cs:?g_fnRevokeBindStatusCallback@@3P6AJPEAUIBindCtx@@PEAUIBindStatusCallback@@@ZEA, rbx; long (*g_fnRevokeBindStatusCallback)(IBindCtx *,IBindStatusCallback *)
0x18001fef1  jmp     short loc_18001FEB4
0x18001fef3  call    cs:__imp_FreeLibrary
0x18001fef9  movzx   ecx, cs:?ITA_DCWAIT@@3GA; nAtom
0x18001ff00  mov     cs:?g_hFilterDLL@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hFilterDLL
0x18001ff07  mov     cs:?g_fnFilterCreateInstance@@3P6AJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@ZEA, rbx; long (*g_fnFilterCreateInstance)(_GUID const &,IUnknown *,ulong,_GUID const &,void * *)
0x18001ff0e  test    cx, cx
0x18001ff11  jz      short loc_18001FF19
0x18001ff13  call    cs:__imp_GlobalDeleteAtom
0x18001ff19  movzx   ecx, cs:?ITA_DISPLAY@@3GA; nAtom
0x18001ff20  test    cx, cx
0x18001ff23  jz      short loc_18001FF2B
0x18001ff25  call    cs:__imp_GlobalDeleteAtom
0x18001ff2b  movzx   ecx, cs:?ITA_ABNORMAL@@3GA; nAtom
0x18001ff32  test    cx, cx
0x18001ff35  jz      short loc_18001FF3D
0x18001ff37  call    cs:__imp_GlobalDeleteAtom
0x18001ff3d  movzx   ecx, cs:?ITA_FINISHED@@3GA; nAtom
0x18001ff44  test    cx, cx
0x18001ff47  jz      loc_18001FEC0
0x18001ff4d  call    cs:__imp_GlobalDeleteAtom
0x18001ff53  jmp     loc_18001FEC0
```
