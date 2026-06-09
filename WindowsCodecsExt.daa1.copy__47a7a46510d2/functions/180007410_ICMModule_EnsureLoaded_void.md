# ICMModule::EnsureLoaded(void)

- ea: `0x180007410`
- end: `0x180007667`
- name: `?EnsureLoaded@ICMModule@@SAHXZ`
- size: `599`
- prototype: `_BOOL8(void)`
- caller_count: `20`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180005540`
- `0x1800057a0`
- `0x180005db0`
- `0x180007670`
- `0x180008240`
- `0x180009bb0`
- `0x180011540`
- `0x180011760`
- `0x18001179c`
- `0x180011ad4`
- `0x180013390`
- `0x180013ab8`
- `0x180013ff4`
- `0x180014930`
- `0x18002a940`
- `0x18002aae0`
- `0x18002ab70`
- `0x18002acd0`
- `0x18002ad70`
- `0x18002ae30`

## callees

- `0x180007410`
- `0x180022644`
- `0x180022650`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800074a6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800074bd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800074d4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800074eb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007502`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007519`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007530`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007547`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000755e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007575`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000758c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800075a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800074a6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800074bd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800074d4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800074eb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007502`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007519`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007530`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007547`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000755e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007575`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000758c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800075a3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000745d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000745d`

## string_xrefs

- `0x180007456`: `mscms.dll`
- `0x18000754d`: `GetColorDirectoryW`
- `0x1800074ac`: `OpenColorProfileW`
- `0x180007508`: `DeleteColorTransform`
- `0x18000749c`: `OpenColorProfileA`
- `0x1800074c3`: `CreateMultiProfileTransform`

## pseudocode

```c
_BOOL8 ICMModule::EnsureLoaded(void)
{
  int v0; // eax
  HMODULE Library; // rax
  HMODULE v3; // rbx
  signed __int32 v4[8]; // [rsp+0h] [rbp-28h] BYREF

  v0 = ICMModule::s_icmState;
  if ( ICMModule::s_icmState )
    return v0 == 1;
  if ( !byte_180041DC0 || (EnterCriticalSection_0(&CriticalSection), (v0 = ICMModule::s_icmState) == 0) )
  {
    Library = LoadLibraryExW(L"mscms.dll", 0, 0);
    v3 = Library;
    if ( Library )
    {
      ICMModule::s_pfnOpenColorProfileA = (void *(*)(struct tagPROFILE *, unsigned int, unsigned int, unsigned int))GetProcAddress(Library, "OpenColorProfileA");
      ICMModule::s_pfnOpenColorProfileW = (void *(*)(struct tagPROFILE *, unsigned int, unsigned int, unsigned int))GetProcAddress(v3, "OpenColorProfileW");
      ICMModule::s_pfnCreateMultiProfileTransform = (void *(*)(void **, unsigned int, unsigned int *, unsigned int, unsigned int, unsigned int))GetProcAddress(v3, "CreateMultiProfileTransform");
      ICMModule::s_pfnTranslateBitmapBits = (int (*)(void *, void *, enum BMFORMAT, unsigned int, unsigned int, unsigned int, void *, enum BMFORMAT, unsigned int, int (*)(unsigned int, unsigned int, __int64), unsigned int))GetProcAddress(v3, "TranslateBitmapBits");
      ICMModule::s_pfnCloseColorProfile = (int (*)(void *))GetProcAddress(v3, "CloseColorProfile");
      ICMModule::s_pfnDeleteColorTransform = (int (*)(void *))GetProcAddress(v3, "DeleteColorTransform");
      ICMModule::s_pfnTranslateColors = (int (*)(void *, void *, unsigned int, unsigned int, void *, unsigned int))GetProcAddress(v3, "TranslateColors");
      ICMModule::s_pfnGetColorProfileHeader = (int (*)(void *, struct tagPROFILEHEADER *))GetProcAddress(
                                                                                            v3,
                                                                                            "GetColorProfileHeader");
      ICMModule::s_pfnGetColorDirectoryW = (int (*)(const unsigned __int16 *, unsigned __int16 *, unsigned int *))GetProcAddress(v3, "GetColorDirectoryW");
      ICMModule::s_pfnGetStandardColorSpaceProfileW = (int (*)(const unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int *))GetProcAddress(v3, "GetStandardColorSpaceProfileW");
      ICMModule::s_pfnGetColorProfileFromHandle = (int (*)(void *, unsigned __int8 *, unsigned int *))GetProcAddress(v3, "GetColorProfileFromHandle");
      ICMModule::s_pfnGetColorProfileElement = (int (*)(void *, unsigned int, unsigned int, unsigned int *, void *, int *))GetProcAddress(v3, "GetColorProfileElement");
      _InterlockedOr(v4, 0);
      if ( ICMModule::s_pfnOpenColorProfileA
        && ICMModule::s_pfnOpenColorProfileW
        && ICMModule::s_pfnCloseColorProfile
        && ICMModule::s_pfnCreateMultiProfileTransform
        && ICMModule::s_pfnDeleteColorTransform
        && ICMModule::s_pfnTranslateBitmapBits
        && ICMModule::s_pfnTranslateColors
        && ICMModule::s_pfnGetColorProfileHeader
        && ICMModule::s_pfnGetColorDirectoryW
        && ICMModule::s_pfnGetStandardColorSpaceProfileW
        && ICMModule::s_pfnGetColorProfileFromHandle
        && ICMModule::s_pfnGetColorProfileElement )
      {
        v0 = 1;
        goto LABEL_8;
      }
    }
    else
    {
      _InterlockedOr(v4, 0);
    }
    v0 = 2;
LABEL_8:
    ICMModule::s_icmState = v0;
  }
  if ( byte_180041DC0 )
  {
    LeaveCriticalSection_0(&CriticalSection);
    v0 = ICMModule::s_icmState;
  }
  return v0 == 1;
}

```

## disassembly

```asm
0x180007410  sub     rsp, 28h
0x180007414  mov     eax, cs:?s_icmState@ICMModule@@0W4DllLoadState@@A; DllLoadState ICMModule::s_icmState
0x18000741a  test    eax, eax
0x18000741c  jz      short loc_18000742D
0x18000741e  xor     ecx, ecx
0x180007420  cmp     eax, 1
0x180007423  setz    cl
0x180007426  mov     eax, ecx
0x180007428  add     rsp, 28h
0x18000742c  retn
0x18000742d  cmp     cs:byte_180041DC0, 0
0x180007434  jz      short loc_18000744C
0x180007436  lea     rcx, CriticalSection; lpCriticalSection
0x18000743d  call    EnterCriticalSection_0
0x180007442  mov     eax, cs:?s_icmState@ICMModule@@0W4DllLoadState@@A; DllLoadState ICMModule::s_icmState
0x180007448  test    eax, eax
0x18000744a  jnz     short loc_18000747F
0x18000744c  xor     r8d, r8d; dwFlags
0x18000744f  mov     [rsp+28h+var_8], rbx
0x180007454  xor     edx, edx; hFile
0x180007456  lea     rcx, LibFileName; "mscms.dll"
0x18000745d  call    cs:__imp_LoadLibraryExW
0x180007463  mov     rbx, rax
0x180007466  test    rax, rax
0x180007469  jnz     short loc_18000749C
0x18000746b  lock or [rsp+28h+var_28], eax
0x18000746f  mov     eax, 2
0x180007474  mov     rbx, [rsp+28h+var_8]
0x180007479  mov     cs:?s_icmState@ICMModule@@0W4DllLoadState@@A, eax; DllLoadState ICMModule::s_icmState
0x18000747f  cmp     cs:byte_180041DC0, 0
0x180007486  jz      short loc_18000741E
0x180007488  lea     rcx, CriticalSection; lpCriticalSection
0x18000748f  call    LeaveCriticalSection_0
0x180007494  mov     eax, cs:?s_icmState@ICMModule@@0W4DllLoadState@@A; DllLoadState ICMModule::s_icmState
0x18000749a  jmp     short loc_18000741E
0x18000749c  lea     rdx, ProcName; "OpenColorProfileA"
0x1800074a3  mov     rcx, rbx; hModule
0x1800074a6  call    cs:__imp_GetProcAddress
0x1800074ac  lea     rdx, aOpencolorprofi_0; "OpenColorProfileW"
0x1800074b3  mov     rcx, rbx; hModule
0x1800074b6  mov     cs:?s_pfnOpenColorProfileA@ICMModule@@0P6APEAXPEAUtagPROFILE@@KKK@ZEA, rax; void * (*ICMModule::s_pfnOpenColorProfileA)(tagPROFILE *,ulong,ulong,ulong)
0x1800074bd  call    cs:__imp_GetProcAddress
0x1800074c3  lea     rdx, aCreatemultipro; "CreateMultiProfileTransform"
0x1800074ca  mov     rcx, rbx; hModule
0x1800074cd  mov     cs:?s_pfnOpenColorProfileW@ICMModule@@0P6APEAXPEAUtagPROFILE@@KKK@ZEA, rax; void * (*ICMModule::s_pfnOpenColorProfileW)(tagPROFILE *,ulong,ulong,ulong)
0x1800074d4  call    cs:__imp_GetProcAddress
0x1800074da  lea     rdx, aTranslatebitma; "TranslateBitmapBits"
0x1800074e1  mov     rcx, rbx; hModule
0x1800074e4  mov     cs:?s_pfnCreateMultiProfileTransform@ICMModule@@0P6APEAXPEAPEAXKPEAKKKK@ZEA, rax; void * (*ICMModule::s_pfnCreateMultiProfileTransform)(void * *,ulong,ulong *,ulong,ulong,ulong)
0x1800074eb  call    cs:__imp_GetProcAddress
0x1800074f1  lea     rdx, aClosecolorprof; "CloseColorProfile"
0x1800074f8  mov     rcx, rbx; hModule
0x1800074fb  mov     cs:?s_pfnTranslateBitmapBits@ICMModule@@0P6AHPEAX0W4BMFORMAT@@KKK01KP6AHKK_J@ZK@ZEA, rax; int (*ICMModule::s_pfnTranslateBitmapBits)(void *,void *,BMFORMAT,ulong,ulong,ulong,void *,BMFORMAT,ulong,int (*)(ulong,ulong,__int64),ulong)
0x180007502  call    cs:__imp_GetProcAddress
0x180007508  lea     rdx, aDeletecolortra; "DeleteColorTransform"
0x18000750f  mov     rcx, rbx; hModule
0x180007512  mov     cs:?s_pfnCloseColorProfile@ICMModule@@0P6AHPEAX@ZEA, rax; int (*ICMModule::s_pfnCloseColorProfile)(void *)
0x180007519  call    cs:__imp_GetProcAddress
0x18000751f  lea     rdx, aTranslatecolor; "TranslateColors"
0x180007526  mov     rcx, rbx; hModule
0x180007529  mov     cs:?s_pfnDeleteColorTransform@ICMModule@@0P6AHPEAX@ZEA, rax; int (*ICMModule::s_pfnDeleteColorTransform)(void *)
0x180007530  call    cs:__imp_GetProcAddress
0x180007536  lea     rdx, aGetcolorprofil; "GetColorProfileHeader"
0x18000753d  mov     rcx, rbx; hModule
0x180007540  mov     cs:?s_pfnTranslateColors@ICMModule@@0P6AHPEAX0KK0K@ZEA, rax; int (*ICMModule::s_pfnTranslateColors)(void *,void *,ulong,ulong,void *,ulong)
0x180007547  call    cs:__imp_GetProcAddress
0x18000754d  lea     rdx, aGetcolordirect; "GetColorDirectoryW"
0x180007554  mov     rcx, rbx; hModule
0x180007557  mov     cs:?s_pfnGetColorProfileHeader@ICMModule@@0P6AHPEAXPEAUtagPROFILEHEADER@@@ZEA, rax; int (*ICMModule::s_pfnGetColorProfileHeader)(void *,tagPROFILEHEADER *)
0x18000755e  call    cs:__imp_GetProcAddress
0x180007564  lea     rdx, aGetstandardcol; "GetStandardColorSpaceProfileW"
0x18000756b  mov     rcx, rbx; hModule
0x18000756e  mov     cs:?s_pfnGetColorDirectoryW@ICMModule@@0P6AHPEBGPEAGPEAK@ZEA, rax; int (*ICMModule::s_pfnGetColorDirectoryW)(ushort const *,ushort *,ulong *)
0x180007575  call    cs:__imp_GetProcAddress
0x18000757b  lea     rdx, aGetcolorprofil_0; "GetColorProfileFromHandle"
0x180007582  mov     rcx, rbx; hModule
0x180007585  mov     cs:?s_pfnGetStandardColorSpaceProfileW@ICMModule@@0P6AHPEBGKPEAGPEAK@ZEA, rax; int (*ICMModule::s_pfnGetStandardColorSpaceProfileW)(ushort const *,ulong,ushort *,ulong *)
0x18000758c  call    cs:__imp_GetProcAddress
0x180007592  lea     rdx, aGetcolorprofil_1; "GetColorProfileElement"
0x180007599  mov     rcx, rbx; hModule
0x18000759c  mov     cs:?s_pfnGetColorProfileFromHandle@ICMModule@@0P6AHPEAXPEAEPEAK@ZEA, rax; int (*ICMModule::s_pfnGetColorProfileFromHandle)(void *,uchar *,ulong *)
0x1800075a3  call    cs:__imp_GetProcAddress
0x1800075a9  mov     cs:?s_pfnGetColorProfileElement@ICMModule@@0P6AHPEAXKKPEAK0PEAH@ZEA, rax; int (*ICMModule::s_pfnGetColorProfileElement)(void *,ulong,ulong,ulong *,void *,int *)
0x1800075b0  lock or [rsp+28h+var_28], 0
0x1800075b5  cmp     cs:?s_pfnOpenColorProfileA@ICMModule@@0P6APEAXPEAUtagPROFILE@@KKK@ZEA, 0; void * (*ICMModule::s_pfnOpenColorProfileA)(tagPROFILE *,ulong,ulong,ulong)
0x1800075bd  jz      loc_18000746F
0x1800075c3  cmp     cs:?s_pfnOpenColorProfileW@ICMModule@@0P6APEAXPEAUtagPROFILE@@KKK@ZEA, 0; void * (*ICMModule::s_pfnOpenColorProfileW)(tagPROFILE *,ulong,ulong,ulong)
0x1800075cb  jz      loc_18000746F
0x1800075d1  cmp     cs:?s_pfnCloseColorProfile@ICMModule@@0P6AHPEAX@ZEA, 0; int (*ICMModule::s_pfnCloseColorProfile)(void *)
0x1800075d9  jz      loc_18000746F
0x1800075df  cmp     cs:?s_pfnCreateMultiProfileTransform@ICMModule@@0P6APEAXPEAPEAXKPEAKKKK@ZEA, 0; void * (*ICMModule::s_pfnCreateMultiProfileTransform)(void * *,ulong,ulong *,ulong,ulong,ulong)
0x1800075e7  jz      loc_18000746F
0x1800075ed  cmp     cs:?s_pfnDeleteColorTransform@ICMModule@@0P6AHPEAX@ZEA, 0; int (*ICMModule::s_pfnDeleteColorTransform)(void *)
0x1800075f5  jz      loc_18000746F
0x1800075fb  cmp     cs:?s_pfnTranslateBitmapBits@ICMModule@@0P6AHPEAX0W4BMFORMAT@@KKK01KP6AHKK_J@ZK@ZEA, 0; int (*ICMModule::s_pfnTranslateBitmapBits)(void *,void *,BMFORMAT,ulong,ulong,ulong,void *,BMFORMAT,ulong,int (*)(ulong,ulong,__int64),ulong)
0x180007603  jz      loc_18000746F
0x180007609  cmp     cs:?s_pfnTranslateColors@ICMModule@@0P6AHPEAX0KK0K@ZEA, 0; int (*ICMModule::s_pfnTranslateColors)(void *,void *,ulong,ulong,void *,ulong)
0x180007611  jz      loc_18000746F
0x180007617  cmp     cs:?s_pfnGetColorProfileHeader@ICMModule@@0P6AHPEAXPEAUtagPROFILEHEADER@@@ZEA, 0; int (*ICMModule::s_pfnGetColorProfileHeader)(void *,tagPROFILEHEADER *)
0x18000761f  jz      loc_18000746F
0x180007625  cmp     cs:?s_pfnGetColorDirectoryW@ICMModule@@0P6AHPEBGPEAGPEAK@ZEA, 0; int (*ICMModule::s_pfnGetColorDirectoryW)(ushort const *,ushort *,ulong *)
0x18000762d  jz      loc_18000746F
0x180007633  cmp     cs:?s_pfnGetStandardColorSpaceProfileW@ICMModule@@0P6AHPEBGKPEAGPEAK@ZEA, 0; int (*ICMModule::s_pfnGetStandardColorSpaceProfileW)(ushort const *,ulong,ushort *,ulong *)
0x18000763b  jz      loc_18000746F
0x180007641  cmp     cs:?s_pfnGetColorProfileFromHandle@ICMModule@@0P6AHPEAXPEAEPEAK@ZEA, 0; int (*ICMModule::s_pfnGetColorProfileFromHandle)(void *,uchar *,ulong *)
0x180007649  jz      loc_18000746F
0x18000764f  cmp     cs:?s_pfnGetColorProfileElement@ICMModule@@0P6AHPEAXKKPEAK0PEAH@ZEA, 0; int (*ICMModule::s_pfnGetColorProfileElement)(void *,ulong,ulong,ulong *,void *,int *)
0x180007657  jz      loc_18000746F
0x18000765d  mov     eax, 1
0x180007662  jmp     loc_180007474
```
