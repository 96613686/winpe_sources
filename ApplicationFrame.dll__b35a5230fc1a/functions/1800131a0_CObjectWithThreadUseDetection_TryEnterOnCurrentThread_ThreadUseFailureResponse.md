# CObjectWithThreadUseDetection::TryEnterOnCurrentThread(ThreadUseFailureResponse)

- ea: `0x1800131a0`
- end: `0x18001333e`
- name: `?TryEnterOnCurrentThread@CObjectWithThreadUseDetection@@IEAAJW4ThreadUseFailureResponse@@@Z`
- size: `414`
- prototype: ``
- caller_count: `10`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000592c`
- `0x18000dd70`
- `0x18000f784`
- `0x180011ce8`
- `0x180011db8`
- `0x180011e4c`
- `0x180012010`
- `0x1800126a0`
- `0x1800128d0`
- `0x18003f53c`

## callees

- `0x1800131a0`
- `0x180024184`
- `0x180043c30`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1800132c0`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1800132c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001328f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001328f`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x1800131e7`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x1800131e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001324f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001324f`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180013236`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180013236`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x1800132ec`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x1800132ec`

## string_xrefs

- `0x180013269`: `onecoreuap\internal\shell\inc\private\cowthreadusedetection.h`

## pseudocode

```c
__int64 __fastcall CObjectWithThreadUseDetection::TryEnterOnCurrentThread(__int64 a1)
{
  int v1; // edi
  int v3; // eax
  unsigned int ApartmentType; // edi
  DWORD CurrentThreadId; // edx
  int v7; // ecx
  int cchValue; // [rsp+20h] [rbp-248h]
  APTTYPE pAptType; // [rsp+30h] [rbp-238h] BYREF
  APTTYPEQUALIFIER pAptQualifier[3]; // [rsp+34h] [rbp-234h] BYREF
  WCHAR Filename[264]; // [rsp+40h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  v1 = *(_DWORD *)(a1 + 44);
  if ( v1 != 2 )
  {
    v3 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
    if ( `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess )
    {
LABEL_3:
      if ( v3 != 1 )
        goto LABEL_4;
      goto LABEL_7;
    }
    if ( GetModuleFileNameW(0, Filename, 0x104u) )
    {
      v7 = (FindStringOrdinal(0x800000u, Filename, -1, L"\\EXPLORER.EXE", -1, 1) != -1) + 1;
      `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess = v7;
    }
    else
    {
      v7 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
    }
    if ( v7 != 1 )
      goto LABEL_4;
    if ( v1 == 1 )
    {
      if ( (unsigned int)IsAppCompatModeEnabled(16) )
      {
        `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess = 2;
        goto LABEL_4;
      }
      v3 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
      goto LABEL_3;
    }
  }
LABEL_7:
  if ( *(_DWORD *)(a1 + 40) != -3 )
  {
    pAptType = APTTYPE_STA;
    pAptQualifier[0] = APTTYPEQUALIFIER_NONE;
    ApartmentType = CoGetApartmentType(&pAptType, pAptQualifier);
    if ( (ApartmentType & 0x80000000) == 0 )
    {
      if ( pAptType == APTTYPE_MAINSTA || (CurrentThreadId = 0, pAptType == APTTYPE_STA) )
      {
        CurrentThreadId = GetCurrentThreadId();
      }
      else if ( pAptType == APTTYPE_NA )
      {
        CurrentThreadId = -1;
      }
      if ( CurrentThreadId == *(_DWORD *)(a1 + 40) )
        goto LABEL_4;
      ApartmentType = -2147417842;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xC8,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\cowthreadusedetection.h",
      (const char *)ApartmentType,
      cchValue);
    return ApartmentType;
  }
LABEL_4:
  ApartmentType = -2147417842;
  if ( TryEnterCriticalSection((LPCRITICAL_SECTION)a1) )
    return 0;
  return ApartmentType;
}

```

## disassembly

```asm
0x1800131a0  mov     [rsp+arg_8], rbx
0x1800131a5  mov     [rsp+arg_10], rsi
0x1800131aa  push    rdi
0x1800131ab  sub     rsp, 260h
0x1800131b2  mov     rax, cs:__security_cookie
0x1800131b9  xor     rax, rsp
0x1800131bc  mov     [rsp+268h+var_18], rax
0x1800131c4  mov     edi, [rcx+2Ch]
0x1800131c7  xor     esi, esi
0x1800131c9  mov     rbx, rcx
0x1800131cc  cmp     edi, 2
0x1800131cf  jz      short loc_18001321E
0x1800131d1  mov     eax, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x1800131d7  test    eax, eax
0x1800131d9  jz      loc_180013282
0x1800131df  cmp     eax, 1
0x1800131e2  jz      short loc_18001321E
0x1800131e4  mov     rcx, rbx; lpCriticalSection
0x1800131e7  call    cs:__imp_TryEnterCriticalSection
0x1800131ed  test    eax, eax
0x1800131ef  mov     edi, 8001010Eh
0x1800131f4  cmovnz  edi, esi
0x1800131f7  mov     eax, edi
0x1800131f9  mov     rcx, [rsp+268h+var_18]
0x180013201  xor     rcx, rsp; StackCookie
0x180013204  call    __security_check_cookie
0x180013209  lea     r11, [rsp+268h+var_8]
0x180013211  mov     rbx, [r11+18h]
0x180013215  mov     rsi, [r11+20h]
0x180013219  mov     rsp, r11
0x18001321c  pop     rdi
0x18001321d  retn
0x18001321e  cmp     dword ptr [rbx+28h], 0FFFFFFFDh
0x180013222  jz      short loc_1800131E4
0x180013224  lea     rdx, [rsp+268h+pAptQualifier]; pAptQualifier
0x180013229  mov     [rsp+268h+pAptType], esi
0x18001322d  lea     rcx, [rsp+268h+pAptType]; pAptType
0x180013232  mov     [rsp+268h+pAptQualifier], esi
0x180013236  call    cs:__imp_CoGetApartmentType
0x18001323c  mov     edi, eax
0x18001323e  test    eax, eax
0x180013240  js      short loc_180013261
0x180013242  mov     ecx, [rsp+268h+pAptType]
0x180013246  cmp     ecx, 3
0x180013249  jnz     loc_180013318
0x18001324f  call    cs:__imp_GetCurrentThreadId
0x180013255  mov     edx, eax
0x180013257  cmp     edx, [rbx+28h]
0x18001325a  jz      short loc_1800131E4
0x18001325c  mov     edi, 8001010Eh
0x180013261  mov     rcx, [rsp+268h]; this
0x180013269  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180013270  mov     r9d, edi; char *
0x180013273  mov     edx, 0C8h; void *
0x180013278  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001327d  jmp     loc_1800131F7
0x180013282  mov     r8d, 104h; nSize
0x180013288  lea     rdx, [rsp+268h+Filename]; lpFilename
0x18001328d  xor     ecx, ecx; hModule
0x18001328f  call    cs:__imp_GetModuleFileNameW
0x180013295  test    eax, eax
0x180013297  jz      short loc_180013305
0x180013299  mov     [rsp+268h+bIgnoreCase], 1; bIgnoreCase
0x1800132a1  lea     r9, StringValue; "\\EXPLORER.EXE"
0x1800132a8  mov     r8d, 0FFFFFFFFh; cchSource
0x1800132ae  mov     [rsp+268h+cchValue], 0FFFFFFFFh; cchValue
0x1800132b6  lea     rdx, [rsp+268h+Filename]; lpStringSource
0x1800132bb  mov     ecx, 800000h; dwFindStringOrdinalFlags
0x1800132c0  call    cs:__imp_FindStringOrdinal
0x1800132c6  cmp     eax, 0FFFFFFFFh
0x1800132c9  mov     ecx, esi
0x1800132cb  setnz   cl
0x1800132ce  inc     ecx
0x1800132d0  mov     cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A, ecx; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x1800132d6  cmp     ecx, 1
0x1800132d9  jnz     loc_1800131E4
0x1800132df  cmp     edi, ecx
0x1800132e1  jnz     loc_18001321E
0x1800132e7  mov     ecx, 10h
0x1800132ec  call    cs:__imp_IsAppCompatModeEnabled
0x1800132f2  test    eax, eax
0x1800132f4  jz      short loc_18001330D
0x1800132f6  mov     cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A, 2; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x180013300  jmp     loc_1800131E4
0x180013305  mov     ecx, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x18001330b  jmp     short loc_1800132D6
0x18001330d  mov     eax, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x180013313  jmp     loc_1800131DF
0x180013318  mov     edx, esi
0x18001331a  test    ecx, ecx
0x18001331c  jz      loc_18001324F
0x180013322  sub     ecx, 1
0x180013325  jz      loc_180013257
0x18001332b  cmp     ecx, 1
0x18001332e  jnz     loc_180013257
0x180013334  mov     edx, 0FFFFFFFFh
0x180013339  jmp     loc_180013257
```
