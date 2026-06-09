# LoadICMDll(void)

- ea: `0x18000c650`
- end: `0x18000c805`
- name: `?LoadICMDll@@YAJXZ`
- size: `437`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000c350`
- `0x180039034`
- `0x180116ce8`
- `0x18014b834`

## callees

- `0x18000c650`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000c6a5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000c6a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c6c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c6dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c6f7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c712`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c72d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c748`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c763`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c77e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c6c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c6dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c6f7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c712`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c72d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c748`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c763`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c77e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c65d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c65d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c677`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c677`

## string_xrefs

- `0x18000c6b7`: `OpenColorProfileA`
- `0x18000c69e`: `mscms.dll`
- `0x18000c6e9`: `CreateMultiProfileTransform`
- `0x18000c6ce`: `OpenColorProfileW`
- `0x18000c73a`: `DeleteColorTransform`

## pseudocode

```c
__int64 LoadICMDll(void)
{
  unsigned int v0; // edi
  HMODULE Library; // rax
  int (*ProcAddress)(void *, unsigned __int8 *, unsigned int *); // rax

  EnterCriticalSection(&LoadLibraryCriticalSection::critSec);
  if ( IcmState == 1 )
    goto LABEL_2;
  v0 = -2147467259;
  if ( IcmState != 2 )
  {
    IcmState = 2;
    Library = LoadLibraryExW(L"mscms.dll", 0, 0);
    ghInstICMDll = Library;
    if ( Library )
    {
      pfnOpenColorProfile = (void *(*)(struct tagPROFILE *, unsigned int, unsigned int, unsigned int))GetProcAddress(Library, "OpenColorProfileA");
      pfnOpenColorProfileW = (void *(*)(struct tagPROFILE *, unsigned int, unsigned int, unsigned int))GetProcAddress(ghInstICMDll, "OpenColorProfileW");
      pfnCreateMultiProfileTransform = (void *(*)(void **, unsigned int, unsigned int *, unsigned int, unsigned int, unsigned int))GetProcAddress(ghInstICMDll, "CreateMultiProfileTransform");
      pfnTranslateBitmapBits = (int (*)(void *, void *, enum BMFORMAT, unsigned int, unsigned int, unsigned int, void *, enum BMFORMAT, unsigned int, int (*)(unsigned int, unsigned int, __int64), unsigned int))GetProcAddress(ghInstICMDll, "TranslateBitmapBits");
      pfnCloseColorProfile = (int (*)(void *))GetProcAddress(ghInstICMDll, "CloseColorProfile");
      pfnDeleteColorTransform = (int (*)(void *))GetProcAddress(ghInstICMDll, "DeleteColorTransform");
      pfnGetStandardColorSpaceProfileW = (int (*)(const unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int *))GetProcAddress(ghInstICMDll, "GetStandardColorSpaceProfileW");
      ProcAddress = (int (*)(void *, unsigned __int8 *, unsigned int *))GetProcAddress(
                                                                          ghInstICMDll,
                                                                          "GetColorProfileFromHandle");
      pfnGetColorProfileFromHandle = ProcAddress;
      if ( pfnOpenColorProfile )
      {
        if ( pfnOpenColorProfileW
          && pfnCloseColorProfile
          && pfnCreateMultiProfileTransform
          && pfnDeleteColorTransform
          && pfnTranslateBitmapBits
          && pfnGetStandardColorSpaceProfileW
          && ProcAddress )
        {
          IcmState = 1;
LABEL_2:
          v0 = 0;
        }
      }
    }
  }
  LeaveCriticalSection(&LoadLibraryCriticalSection::critSec);
  return v0;
}

```

## disassembly

```asm
0x18000c650  push    rdi
0x18000c652  sub     rsp, 20h
0x18000c656  lea     rcx, ?critSec@LoadLibraryCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000c65d  call    cs:__imp_EnterCriticalSection
0x18000c663  mov     eax, cs:?IcmState@@3W4IcmDllLoadState@@A; IcmDllLoadState IcmState
0x18000c669  cmp     eax, 1
0x18000c66c  jnz     short loc_18000C685
0x18000c66e  xor     edi, edi
0x18000c670  lea     rcx, ?critSec@LoadLibraryCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000c677  call    cs:__imp_LeaveCriticalSection
0x18000c67d  mov     eax, edi
0x18000c67f  add     rsp, 20h
0x18000c683  pop     rdi
0x18000c684  retn
0x18000c685  mov     edi, 80004005h
0x18000c68a  cmp     eax, 2
0x18000c68d  jz      short loc_18000C670
0x18000c68f  xor     r8d, r8d; dwFlags
0x18000c692  mov     cs:?IcmState@@3W4IcmDllLoadState@@A, 2; IcmDllLoadState IcmState
0x18000c69c  xor     edx, edx; hFile
0x18000c69e  lea     rcx, LibFileName; "mscms.dll"
0x18000c6a5  call    cs:__imp_LoadLibraryExW
0x18000c6ab  mov     cs:?ghInstICMDll@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * ghInstICMDll
0x18000c6b2  test    rax, rax
0x18000c6b5  jz      short loc_18000C670
0x18000c6b7  lea     rdx, ProcName; "OpenColorProfileA"
0x18000c6be  mov     rcx, rax; hModule
0x18000c6c1  call    cs:__imp_GetProcAddress
0x18000c6c7  mov     rcx, cs:?ghInstICMDll@@3PEAUHINSTANCE__@@EA; hModule
0x18000c6ce  lea     rdx, aOpencolorprofi_0; "OpenColorProfileW"
0x18000c6d5  mov     cs:?pfnOpenColorProfile@@3P6APEAXPEAUtagPROFILE@@KKK@ZEA, rax; void * (*pfnOpenColorProfile)(tagPROFILE *,ulong,ulong,ulong)
0x18000c6dc  call    cs:__imp_GetProcAddress
0x18000c6e2  mov     rcx, cs:?ghInstICMDll@@3PEAUHINSTANCE__@@EA; hModule
0x18000c6e9  lea     rdx, aCreatemultipro; "CreateMultiProfileTransform"
0x18000c6f0  mov     cs:?pfnOpenColorProfileW@@3P6APEAXPEAUtagPROFILE@@KKK@ZEA, rax; void * (*pfnOpenColorProfileW)(tagPROFILE *,ulong,ulong,ulong)
0x18000c6f7  call    cs:__imp_GetProcAddress
0x18000c6fd  mov     rcx, cs:?ghInstICMDll@@3PEAUHINSTANCE__@@EA; hModule
0x18000c704  lea     rdx, aTranslatebitma; "TranslateBitmapBits"
0x18000c70b  mov     cs:?pfnCreateMultiProfileTransform@@3P6APEAXPEAPEAXKPEAKKKK@ZEA, rax; void * (*pfnCreateMultiProfileTransform)(void * *,ulong,ulong *,ulong,ulong,ulong)
0x18000c712  call    cs:__imp_GetProcAddress
0x18000c718  mov     rcx, cs:?ghInstICMDll@@3PEAUHINSTANCE__@@EA; hModule
0x18000c71f  lea     rdx, aClosecolorprof; "CloseColorProfile"
0x18000c726  mov     cs:?pfnTranslateBitmapBits@@3P6AHPEAX0W4BMFORMAT@@KKK01KP6AHKK_J@ZK@ZEA, rax; int (*pfnTranslateBitmapBits)(void *,void *,BMFORMAT,ulong,ulong,ulong,void *,BMFORMAT,ulong,int (*)(ulong,ulong,__int64),ulong)
0x18000c72d  call    cs:__imp_GetProcAddress
0x18000c733  mov     rcx, cs:?ghInstICMDll@@3PEAUHINSTANCE__@@EA; hModule
0x18000c73a  lea     rdx, aDeletecolortra; "DeleteColorTransform"
0x18000c741  mov     cs:?pfnCloseColorProfile@@3P6AHPEAX@ZEA, rax; int (*pfnCloseColorProfile)(void *)
0x18000c748  call    cs:__imp_GetProcAddress
0x18000c74e  mov     rcx, cs:?ghInstICMDll@@3PEAUHINSTANCE__@@EA; hModule
0x18000c755  lea     rdx, aGetstandardcol; "GetStandardColorSpaceProfileW"
0x18000c75c  mov     cs:?pfnDeleteColorTransform@@3P6AHPEAX@ZEA, rax; int (*pfnDeleteColorTransform)(void *)
0x18000c763  call    cs:__imp_GetProcAddress
0x18000c769  mov     rcx, cs:?ghInstICMDll@@3PEAUHINSTANCE__@@EA; hModule
0x18000c770  lea     rdx, aGetcolorprofil; "GetColorProfileFromHandle"
0x18000c777  mov     cs:?pfnGetStandardColorSpaceProfileW@@3P6AHPEBGKPEAGPEAK@ZEA, rax; int (*pfnGetStandardColorSpaceProfileW)(ushort const *,ulong,ushort *,ulong *)
0x18000c77e  call    cs:__imp_GetProcAddress
0x18000c784  cmp     cs:?pfnOpenColorProfile@@3P6APEAXPEAUtagPROFILE@@KKK@ZEA, 0; void * (*pfnOpenColorProfile)(tagPROFILE *,ulong,ulong,ulong)
0x18000c78c  mov     cs:?pfnGetColorProfileFromHandle@@3P6AHPEAXPEAEPEAK@ZEA, rax; int (*pfnGetColorProfileFromHandle)(void *,uchar *,ulong *)
0x18000c793  jz      loc_18000C670
0x18000c799  cmp     cs:?pfnOpenColorProfileW@@3P6APEAXPEAUtagPROFILE@@KKK@ZEA, 0; void * (*pfnOpenColorProfileW)(tagPROFILE *,ulong,ulong,ulong)
0x18000c7a1  jz      loc_18000C670
0x18000c7a7  cmp     cs:?pfnCloseColorProfile@@3P6AHPEAX@ZEA, 0; int (*pfnCloseColorProfile)(void *)
0x18000c7af  jz      loc_18000C670
0x18000c7b5  cmp     cs:?pfnCreateMultiProfileTransform@@3P6APEAXPEAPEAXKPEAKKKK@ZEA, 0; void * (*pfnCreateMultiProfileTransform)(void * *,ulong,ulong *,ulong,ulong,ulong)
0x18000c7bd  jz      loc_18000C670
0x18000c7c3  cmp     cs:?pfnDeleteColorTransform@@3P6AHPEAX@ZEA, 0; int (*pfnDeleteColorTransform)(void *)
0x18000c7cb  jz      loc_18000C670
0x18000c7d1  cmp     cs:?pfnTranslateBitmapBits@@3P6AHPEAX0W4BMFORMAT@@KKK01KP6AHKK_J@ZK@ZEA, 0; int (*pfnTranslateBitmapBits)(void *,void *,BMFORMAT,ulong,ulong,ulong,void *,BMFORMAT,ulong,int (*)(ulong,ulong,__int64),ulong)
0x18000c7d9  jz      loc_18000C670
0x18000c7df  cmp     cs:?pfnGetStandardColorSpaceProfileW@@3P6AHPEBGKPEAGPEAK@ZEA, 0; int (*pfnGetStandardColorSpaceProfileW)(ushort const *,ulong,ushort *,ulong *)
0x18000c7e7  jz      loc_18000C670
0x18000c7ed  test    rax, rax
0x18000c7f0  jz      loc_18000C670
0x18000c7f6  mov     cs:?IcmState@@3W4IcmDllLoadState@@A, 1; IcmDllLoadState IcmState
0x18000c800  jmp     loc_18000C66E
```
