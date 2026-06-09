# CIcmColorTransform::Transform(void *,uint,uint,void *,uint,uint)

- ea: `0x180004ea0`
- end: `0x1800052bc`
- name: `?Transform@CIcmColorTransform@@IEAAJPEAXII0II@Z`
- size: `1052`
- prototype: `__int64 __fastcall(CIcmColorTransform *this, void *, unsigned int, int, void *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180005db0`

## callees

- `0x180004ea0`
- `0x180022348`
- `0x180022644`
- `0x180022650`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005192`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800051ab`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800051c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800051dd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800051f6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000520f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005228`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005241`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000525a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005273`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000528c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800052a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005192`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800051ab`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800051c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800051dd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800051f6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000520f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005228`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005241`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000525a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005273`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000528c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800052a5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800050b1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800050b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005065`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005065`

## string_xrefs

- `0x1800050a8`: `mscms.dll`
- `0x18000524c`: `GetColorDirectoryW`
- `0x18000519d`: `OpenColorProfileW`
- `0x180005201`: `DeleteColorTransform`
- `0x180005188`: `OpenColorProfileA`
- `0x1800051b6`: `CreateMultiProfileTransform`

## pseudocode

```c
__int64 __fastcall CIcmColorTransform::Transform(
        CIcmColorTransform *this,
        void *a2,
        unsigned int a3,
        int a4,
        void *a5,
        unsigned int a6,
        unsigned int a7)
{
  unsigned int v7; // r10d
  int v12; // ebx
  unsigned int v13; // ecx
  __int64 v14; // r10
  int v15; // r13d
  int v16; // edi
  int v17; // eax
  __int64 result; // rax
  signed int LastError; // eax
  HMODULE Library; // rax
  signed __int32 v21[8]; // [rsp+0h] [rbp-98h] BYREF
  HMODULE hModule; // [rsp+60h] [rbp-38h]
  __int64 v23; // [rsp+68h] [rbp-30h]
  unsigned int v24; // [rsp+A0h] [rbp+8h]

  v7 = -2147024809;
  v12 = _mm_getcsr();
  if ( (v12 & 0xFF80) != 0x1F80 )
    _mm_setcsr(0x1F80u);
  if ( *((_DWORD *)this + 44) && a2 && a5 && a3 && a4 )
  {
    if ( *((_DWORD *)this + 42) == 8 || *((_DWORD *)this + 42) == 16 )
      memset_0(a5, 255, a7 * a4);
    v13 = *((_DWORD *)this + 40);
    v14 = *((_QWORD *)this + 19);
    v15 = *((_DWORD *)this + 42);
    v16 = 0;
    v17 = ICMModule::s_icmState;
    v24 = v13;
    v23 = v14;
    if ( !ICMModule::s_icmState )
    {
      if ( !byte_180041DC0 || (EnterCriticalSection_0(&CriticalSection), (v17 = ICMModule::s_icmState) == 0) )
      {
        Library = LoadLibraryExW(L"mscms.dll", 0, 0);
        hModule = Library;
        if ( Library )
        {
          ICMModule::s_pfnOpenColorProfileA = (void *(*)(struct tagPROFILE *, unsigned int, unsigned int, unsigned int))GetProcAddress(Library, "OpenColorProfileA");
          ICMModule::s_pfnOpenColorProfileW = (void *(*)(struct tagPROFILE *, unsigned int, unsigned int, unsigned int))GetProcAddress(hModule, "OpenColorProfileW");
          ICMModule::s_pfnCreateMultiProfileTransform = (void *(*)(void **, unsigned int, unsigned int *, unsigned int, unsigned int, unsigned int))GetProcAddress(hModule, "CreateMultiProfileTransform");
          ICMModule::s_pfnTranslateBitmapBits = (int (*)(void *, void *, enum BMFORMAT, unsigned int, unsigned int, unsigned int, void *, enum BMFORMAT, unsigned int, int (*)(unsigned int, unsigned int, __int64), unsigned int))GetProcAddress(hModule, "TranslateBitmapBits");
          ICMModule::s_pfnCloseColorProfile = (int (*)(void *))GetProcAddress(hModule, "CloseColorProfile");
          ICMModule::s_pfnDeleteColorTransform = (int (*)(void *))GetProcAddress(hModule, "DeleteColorTransform");
          ICMModule::s_pfnTranslateColors = (int (*)(void *, void *, unsigned int, unsigned int, void *, unsigned int))GetProcAddress(hModule, "TranslateColors");
          ICMModule::s_pfnGetColorProfileHeader = (int (*)(void *, struct tagPROFILEHEADER *))GetProcAddress(
                                                                                                hModule,
                                                                                                "GetColorProfileHeader");
          ICMModule::s_pfnGetColorDirectoryW = (int (*)(const unsigned __int16 *, unsigned __int16 *, unsigned int *))GetProcAddress(hModule, "GetColorDirectoryW");
          ICMModule::s_pfnGetStandardColorSpaceProfileW = (int (*)(const unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int *))GetProcAddress(hModule, "GetStandardColorSpaceProfileW");
          ICMModule::s_pfnGetColorProfileFromHandle = (int (*)(void *, unsigned __int8 *, unsigned int *))GetProcAddress(hModule, "GetColorProfileFromHandle");
          ICMModule::s_pfnGetColorProfileElement = (int (*)(void *, unsigned int, unsigned int, unsigned int *, void *, int *))GetProcAddress(hModule, "GetColorProfileElement");
          Library = hModule;
        }
        _InterlockedOr(v21, 0);
        if ( Library
          && ICMModule::s_pfnOpenColorProfileA
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
          v17 = 1;
        }
        else
        {
          v17 = 2;
        }
        ICMModule::s_icmState = v17;
      }
      if ( byte_180041DC0 )
      {
        LeaveCriticalSection_0(&CriticalSection);
        v17 = ICMModule::s_icmState;
      }
      v13 = v24;
      v14 = v23;
    }
    if ( v17 == 1 )
      v16 = ((__int64 (__fastcall *)(__int64, void *, _QWORD, _QWORD, int, unsigned int, void *, int, unsigned int, _QWORD, _DWORD))ICMModule::s_pfnTranslateBitmapBits)(
              v14,
              a2,
              v13,
              a3,
              a4,
              a6,
              a5,
              v15,
              a7,
              0,
              0);
    if ( v16 )
    {
      v7 = 0;
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  result = v7;
  if ( (v12 & 0xFF80) != 0x1F80 )
    _mm_setcsr(v12 & 0xFFFFFFC0);
  return result;
}

```

## disassembly

```asm
0x180004ea0  mov     rax, rsp
0x180004ea3  push    rbx
0x180004ea4  sub     rsp, 90h
0x180004eab  mov     [rax+10h], rbp
0x180004eaf  mov     r10d, 80070057h
0x180004eb5  mov     [rax+20h], rdi
0x180004eb9  mov     ebp, r9d
0x180004ebc  mov     [rax-20h], r14
0x180004ec0  mov     rdi, rcx
0x180004ec3  mov     [rax-28h], r15
0x180004ec7  mov     r14, rdx
0x180004eca  mov     r15d, r8d
0x180004ecd  stmxcsr [rsp+98h+arg_0]
0x180004ed5  mov     ebx, [rsp+98h+arg_0]
0x180004edc  mov     eax, ebx
0x180004ede  and     eax, 0FF80h
0x180004ee3  cmp     eax, 1F80h
0x180004ee8  jz      short loc_180004EFD
0x180004eea  mov     [rsp+98h+arg_0], 1F80h
0x180004ef5  ldmxcsr [rsp+98h+arg_0]
0x180004efd  cmp     dword ptr [rcx+0B0h], 0
0x180004f04  jz      loc_180005004
0x180004f0a  test    r14, r14
0x180004f0d  jz      loc_180005004
0x180004f13  mov     [rsp+98h+arg_10], rsi
0x180004f1b  mov     rsi, [rsp+98h+arg_20]
0x180004f23  test    rsi, rsi
0x180004f26  jz      loc_180004FFC
0x180004f2c  test    r15d, r15d
0x180004f2f  jz      loc_180004FFC
0x180004f35  test    ebp, ebp
0x180004f37  jz      loc_180004FFC
0x180004f3d  cmp     dword ptr [rcx+0A8h], 8
0x180004f44  mov     [rsp+98h+var_10], r12
0x180004f4c  mov     r12d, [rsp+98h+arg_30]
0x180004f54  mov     [rsp+98h+var_18], r13
0x180004f5c  jz      loc_18000504C
0x180004f62  cmp     dword ptr [rcx+0A8h], 10h
0x180004f69  jz      loc_18000504C
0x180004f6f  mov     ecx, [rdi+0A0h]
0x180004f75  mov     r10, [rdi+98h]
0x180004f7c  mov     r13d, [rdi+0A8h]
0x180004f83  xor     edi, edi
0x180004f85  mov     eax, cs:?s_icmState@ICMModule@@0W4DllLoadState@@A; DllLoadState ICMModule::s_icmState
0x180004f8b  mov     [rsp+98h+arg_0], ecx
0x180004f92  mov     [rsp+98h+var_30], r10
0x180004f97  test    eax, eax
0x180004f99  jz      loc_180005082
0x180004f9f  cmp     eax, 1
0x180004fa2  jnz     short loc_180004FE5
0x180004fa4  mov     eax, [rsp+98h+arg_28]
0x180004fab  mov     r8d, ecx
0x180004fae  mov     [rsp+98h+var_48], edi
0x180004fb2  mov     r9d, r15d
0x180004fb5  mov     [rsp+98h+var_50], rdi
0x180004fba  mov     rdx, r14
0x180004fbd  mov     [rsp+98h+var_58], r12d
0x180004fc2  mov     rcx, r10
0x180004fc5  mov     [rsp+98h+var_60], r13d
0x180004fca  mov     [rsp+98h+var_68], rsi
0x180004fcf  mov     [rsp+98h+var_70], eax
0x180004fd3  mov     rax, cs:?s_pfnTranslateBitmapBits@ICMModule@@0P6AHPEAX0W4BMFORMAT@@KKK01KP6AHKK_J@ZK@ZEA; int (*ICMModule::s_pfnTranslateBitmapBits)(void *,void *,BMFORMAT,ulong,ulong,ulong,void *,BMFORMAT,ulong,int (*)(ulong,ulong,__int64),ulong)
0x180004fda  mov     [rsp+98h+var_78], ebp
0x180004fde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fe3  mov     edi, eax
0x180004fe5  mov     r13, [rsp+98h+var_18]
0x180004fed  mov     r12, [rsp+98h+var_10]
0x180004ff5  test    edi, edi
0x180004ff7  jz      short loc_180005065
0x180004ff9  xor     r10d, r10d
0x180004ffc  mov     rsi, [rsp+98h+arg_10]
0x180005004  mov     r15, [rsp+98h+var_28]
0x180005009  mov     ecx, ebx
0x18000500b  mov     r14, [rsp+98h+var_20]
0x180005010  and     ecx, 0FF80h
0x180005016  mov     rdi, [rsp+98h+arg_18]
0x18000501e  mov     eax, r10d
0x180005021  mov     rbp, [rsp+98h+arg_8]
0x180005029  cmp     ecx, 1F80h
0x18000502f  jz      short loc_180005043
0x180005031  and     ebx, 0FFFFFFC0h
0x180005034  mov     [rsp+98h+arg_0], ebx
0x18000503b  ldmxcsr [rsp+98h+arg_0]
0x180005043  add     rsp, 90h
0x18000504a  pop     rbx
0x18000504b  retn
0x18000504c  mov     r8d, ebp
0x18000504f  mov     edx, 0FFh; Val
0x180005054  imul    r8d, r12d; Size
0x180005058  mov     rcx, rsi; void *
0x18000505b  call    memset_0
0x180005060  jmp     loc_180004F6F
0x180005065  call    cs:__imp_GetLastError
0x18000506b  mov     r10d, eax
0x18000506e  test    eax, eax
0x180005070  jle     short loc_180004FFC
0x180005072  movzx   r10d, ax
0x180005076  or      r10d, 80070000h
0x18000507d  jmp     loc_180004FFC
0x180005082  cmp     cs:byte_180041DC0, dil
0x180005089  jz      short loc_1800050A5
0x18000508b  lea     rcx, CriticalSection; lpCriticalSection
0x180005092  call    EnterCriticalSection_0
0x180005097  mov     eax, cs:?s_icmState@ICMModule@@0W4DllLoadState@@A; DllLoadState ICMModule::s_icmState
0x18000509d  test    eax, eax
0x18000509f  jnz     loc_180005155
0x1800050a5  xor     r8d, r8d; dwFlags
0x1800050a8  lea     rcx, LibFileName; "mscms.dll"
0x1800050af  xor     edx, edx; hFile
0x1800050b1  call    cs:__imp_LoadLibraryExW
0x1800050b7  mov     [rsp+98h+hModule], rax
0x1800050bc  test    rax, rax
0x1800050bf  jnz     loc_180005188
0x1800050c5  lock or [rsp+98h+var_98], edi
0x1800050c9  test    rax, rax
0x1800050cc  jz      loc_180005181
0x1800050d2  cmp     cs:?s_pfnOpenColorProfileA@ICMModule@@0P6APEAXPEAUtagPROFILE@@KKK@ZEA, rdi; void * (*ICMModule::s_pfnOpenColorProfileA)(tagPROFILE *,ulong,ulong,ulong)
0x1800050d9  jz      loc_180005181
0x1800050df  cmp     cs:?s_pfnOpenColorProfileW@ICMModule@@0P6APEAXPEAUtagPROFILE@@KKK@ZEA, rdi; void * (*ICMModule::s_pfnOpenColorProfileW)(tagPROFILE *,ulong,ulong,ulong)
0x1800050e6  jz      loc_180005181
0x1800050ec  cmp     cs:?s_pfnCloseColorProfile@ICMModule@@0P6AHPEAX@ZEA, rdi; int (*ICMModule::s_pfnCloseColorProfile)(void *)
0x1800050f3  jz      loc_180005181
0x1800050f9  cmp     cs:?s_pfnCreateMultiProfileTransform@ICMModule@@0P6APEAXPEAPEAXKPEAKKKK@ZEA, rdi; void * (*ICMModule::s_pfnCreateMultiProfileTransform)(void * *,ulong,ulong *,ulong,ulong,ulong)
0x180005100  jz      short loc_180005181
0x180005102  cmp     cs:?s_pfnDeleteColorTransform@ICMModule@@0P6AHPEAX@ZEA, rdi; int (*ICMModule::s_pfnDeleteColorTransform)(void *)
0x180005109  jz      short loc_180005181
0x18000510b  cmp     cs:?s_pfnTranslateBitmapBits@ICMModule@@0P6AHPEAX0W4BMFORMAT@@KKK01KP6AHKK_J@ZK@ZEA, rdi; int (*ICMModule::s_pfnTranslateBitmapBits)(void *,void *,BMFORMAT,ulong,ulong,ulong,void *,BMFORMAT,ulong,int (*)(ulong,ulong,__int64),ulong)
0x180005112  jz      short loc_180005181
0x180005114  cmp     cs:?s_pfnTranslateColors@ICMModule@@0P6AHPEAX0KK0K@ZEA, rdi; int (*ICMModule::s_pfnTranslateColors)(void *,void *,ulong,ulong,void *,ulong)
0x18000511b  jz      short loc_180005181
0x18000511d  cmp     cs:?s_pfnGetColorProfileHeader@ICMModule@@0P6AHPEAXPEAUtagPROFILEHEADER@@@ZEA, rdi; int (*ICMModule::s_pfnGetColorProfileHeader)(void *,tagPROFILEHEADER *)
0x180005124  jz      short loc_180005181
0x180005126  cmp     cs:?s_pfnGetColorDirectoryW@ICMModule@@0P6AHPEBGPEAGPEAK@ZEA, rdi; int (*ICMModule::s_pfnGetColorDirectoryW)(ushort const *,ushort *,ulong *)
0x18000512d  jz      short loc_180005181
0x18000512f  cmp     cs:?s_pfnGetStandardColorSpaceProfileW@ICMModule@@0P6AHPEBGKPEAGPEAK@ZEA, rdi; int (*ICMModule::s_pfnGetStandardColorSpaceProfileW)(ushort const *,ulong,ushort *,ulong *)
0x180005136  jz      short loc_180005181
0x180005138  cmp     cs:?s_pfnGetColorProfileFromHandle@ICMModule@@0P6AHPEAXPEAEPEAK@ZEA, rdi; int (*ICMModule::s_pfnGetColorProfileFromHandle)(void *,uchar *,ulong *)
0x18000513f  jz      short loc_180005181
0x180005141  cmp     cs:?s_pfnGetColorProfileElement@ICMModule@@0P6AHPEAXKKPEAK0PEAH@ZEA, rdi; int (*ICMModule::s_pfnGetColorProfileElement)(void *,ulong,ulong,ulong *,void *,int *)
0x180005148  jz      short loc_180005181
0x18000514a  mov     eax, 1
0x18000514f  mov     cs:?s_icmState@ICMModule@@0W4DllLoadState@@A, eax; DllLoadState ICMModule::s_icmState
0x180005155  cmp     cs:byte_180041DC0, dil
0x18000515c  jz      short loc_180005170
0x18000515e  lea     rcx, CriticalSection; lpCriticalSection
0x180005165  call    LeaveCriticalSection_0
0x18000516a  mov     eax, cs:?s_icmState@ICMModule@@0W4DllLoadState@@A; DllLoadState ICMModule::s_icmState
0x180005170  mov     ecx, [rsp+98h+arg_0]
0x180005177  mov     r10, [rsp+98h+var_30]
0x18000517c  jmp     loc_180004F9F
0x180005181  mov     eax, 2
0x180005186  jmp     short loc_18000514F
0x180005188  lea     rdx, ProcName; "OpenColorProfileA"
0x18000518f  mov     rcx, rax; hModule
0x180005192  call    cs:__imp_GetProcAddress
0x180005198  mov     rcx, [rsp+98h+hModule]; hModule
0x18000519d  lea     rdx, aOpencolorprofi_0; "OpenColorProfileW"
0x1800051a4  mov     cs:?s_pfnOpenColorProfileA@ICMModule@@0P6APEAXPEAUtagPROFILE@@KKK@ZEA, rax; void * (*ICMModule::s_pfnOpenColorProfileA)(tagPROFILE *,ulong,ulong,ulong)
0x1800051ab  call    cs:__imp_GetProcAddress
0x1800051b1  mov     rcx, [rsp+98h+hModule]; hModule
0x1800051b6  lea     rdx, aCreatemultipro; "CreateMultiProfileTransform"
0x1800051bd  mov     cs:?s_pfnOpenColorProfileW@ICMModule@@0P6APEAXPEAUtagPROFILE@@KKK@ZEA, rax; void * (*ICMModule::s_pfnOpenColorProfileW)(tagPROFILE *,ulong,ulong,ulong)
0x1800051c4  call    cs:__imp_GetProcAddress
0x1800051ca  mov     rcx, [rsp+98h+hModule]; hModule
0x1800051cf  lea     rdx, aTranslatebitma; "TranslateBitmapBits"
0x1800051d6  mov     cs:?s_pfnCreateMultiProfileTransform@ICMModule@@0P6APEAXPEAPEAXKPEAKKKK@ZEA, rax; void * (*ICMModule::s_pfnCreateMultiProfileTransform)(void * *,ulong,ulong *,ulong,ulong,ulong)
0x1800051dd  call    cs:__imp_GetProcAddress
0x1800051e3  mov     rcx, [rsp+98h+hModule]; hModule
0x1800051e8  lea     rdx, aClosecolorprof; "CloseColorProfile"
0x1800051ef  mov     cs:?s_pfnTranslateBitmapBits@ICMModule@@0P6AHPEAX0W4BMFORMAT@@KKK01KP6AHKK_J@ZK@ZEA, rax; int (*ICMModule::s_pfnTranslateBitmapBits)(void *,void *,BMFORMAT,ulong,ulong,ulong,void *,BMFORMAT,ulong,int (*)(ulong,ulong,__int64),ulong)
0x1800051f6  call    cs:__imp_GetProcAddress
0x1800051fc  mov     rcx, [rsp+98h+hModule]; hModule
0x180005201  lea     rdx, aDeletecolortra; "DeleteColorTransform"
0x180005208  mov     cs:?s_pfnCloseColorProfile@ICMModule@@0P6AHPEAX@ZEA, rax; int (*ICMModule::s_pfnCloseColorProfile)(void *)
0x18000520f  call    cs:__imp_GetProcAddress
0x180005215  mov     rcx, [rsp+98h+hModule]; hModule
0x18000521a  lea     rdx, aTranslatecolor; "TranslateColors"
0x180005221  mov     cs:?s_pfnDeleteColorTransform@ICMModule@@0P6AHPEAX@ZEA, rax; int (*ICMModule::s_pfnDeleteColorTransform)(void *)
0x180005228  call    cs:__imp_GetProcAddress
0x18000522e  mov     rcx, [rsp+98h+hModule]; hModule
0x180005233  lea     rdx, aGetcolorprofil; "GetColorProfileHeader"
0x18000523a  mov     cs:?s_pfnTranslateColors@ICMModule@@0P6AHPEAX0KK0K@ZEA, rax; int (*ICMModule::s_pfnTranslateColors)(void *,void *,ulong,ulong,void *,ulong)
0x180005241  call    cs:__imp_GetProcAddress
0x180005247  mov     rcx, [rsp+98h+hModule]; hModule
0x18000524c  lea     rdx, aGetcolordirect; "GetColorDirectoryW"
0x180005253  mov     cs:?s_pfnGetColorProfileHeader@ICMModule@@0P6AHPEAXPEAUtagPROFILEHEADER@@@ZEA, rax; int (*ICMModule::s_pfnGetColorProfileHeader)(void *,tagPROFILEHEADER *)
0x18000525a  call    cs:__imp_GetProcAddress
0x180005260  mov     rcx, [rsp+98h+hModule]; hModule
0x180005265  lea     rdx, aGetstandardcol; "GetStandardColorSpaceProfileW"
0x18000526c  mov     cs:?s_pfnGetColorDirectoryW@ICMModule@@0P6AHPEBGPEAGPEAK@ZEA, rax; int (*ICMModule::s_pfnGetColorDirectoryW)(ushort const *,ushort *,ulong *)
0x180005273  call    cs:__imp_GetProcAddress
0x180005279  mov     rcx, [rsp+98h+hModule]; hModule
0x18000527e  lea     rdx, aGetcolorprofil_0; "GetColorProfileFromHandle"
0x180005285  mov     cs:?s_pfnGetStandardColorSpaceProfileW@ICMModule@@0P6AHPEBGKPEAGPEAK@ZEA, rax; int (*ICMModule::s_pfnGetStandardColorSpaceProfileW)(ushort const *,ulong,ushort *,ulong *)
0x18000528c  call    cs:__imp_GetProcAddress
0x180005292  mov     rcx, [rsp+98h+hModule]; hModule
0x180005297  lea     rdx, aGetcolorprofil_1; "GetColorProfileElement"
0x18000529e  mov     cs:?s_pfnGetColorProfileFromHandle@ICMModule@@0P6AHPEAXPEAEPEAK@ZEA, rax; int (*ICMModule::s_pfnGetColorProfileFromHandle)(void *,uchar *,ulong *)
0x1800052a5  call    cs:__imp_GetProcAddress
0x1800052ab  mov     cs:?s_pfnGetColorProfileElement@ICMModule@@0P6AHPEAXKKPEAK0PEAH@ZEA, rax; int (*ICMModule::s_pfnGetColorProfileElement)(void *,ulong,ulong,ulong *,void *,int *)
0x1800052b2  mov     rax, [rsp+98h+hModule]
0x1800052b7  jmp     loc_1800050C5
```
