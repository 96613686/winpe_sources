# StartList::CreateBreakawayATProcess(Accommodation *,int)

- ea: `0x18023bd78`
- end: `0x18023c156`
- name: `?CreateBreakawayATProcess@StartList@@AEAAJPEAVAccommodation@@H@Z`
- size: `990`
- prototype: `int(StartList *__hidden this, struct Accommodation *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18023dd44`

## callees

- `0x18000d44c`
- `0x18001a64c`
- `0x18009af1c`
- `0x18023a608`
- `0x18023aedc`
- `0x18023b6f0`
- `0x18023bd78`
- `0x18023c540`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18023be8c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18023bf5e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18023bf73`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18023c122`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18023be8c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18023bf5e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18023bf73`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18023c122`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18023bff1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18023c0fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18023bff1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18023c0fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18023c112`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18023c112`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18023c005`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18023c005`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18023be22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18023be22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18023c0c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18023c0d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18023c0c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18023c0d2`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18023be12`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18023be12`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x18023bfe1`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x18023c026`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x18023bfe1`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x18023c026`
- `KERNEL32!UpdateProcThreadAttribute` at `0x18023c05b`
- `KERNEL32!UpdateProcThreadAttribute` at `0x18023c05b`
- `KERNEL32!CreateProcessW` at `0x18023c0ab`
- `KERNEL32!CreateProcessW` at `0x18023c0ab`
- `KERNEL32!DeleteProcThreadAttributeList` at `0x18023c0ed`
- `KERNEL32!DeleteProcThreadAttributeList` at `0x18023c0ed`

## string_xrefs

- `0x18023becd`: `/launchnarratorupdates`
- `0x18023bdc4`: `%SystemRoot%\System32\ATBroker.exe`
- `0x18023be0b`: `%SystemRoot%\System32\ATBroker.exe`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall StartList::CreateBreakawayATProcess(WCHAR *this, struct Accommodation *a2, int a3)
{
  LPWSTR v6; // rbx
  DWORD v7; // eax
  signed int LastError; // eax
  unsigned int v9; // esi
  unsigned __int64 v10; // rax
  LPWSTR v11; // rbx
  char IsEnabled; // al
  char v13; // dl
  const WCHAR *v14; // rcx
  const WCHAR *v15; // rax
  const wchar_t *v16; // rdx
  unsigned __int64 v17; // rdx
  WCHAR *v18; // rbx
  int v19; // eax
  const wchar_t *v20; // rdx
  unsigned __int64 v21; // rdx
  unsigned int v22; // ecx
  int v23; // r15d
  struct _PROC_THREAD_ATTRIBUTE_LIST *v24; // r14
  SIZE_T v25; // rsi
  HANDLE ProcessHeap; // rax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v27; // rax
  BOOL updated; // eax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v29; // rcx
  HANDLE v30; // rax
  const wchar_t *lpPreviousValue; // [rsp+30h] [rbp-91h]
  const wchar_t *lpPreviousValuea; // [rsp+30h] [rbp-91h]
  ULONG_PTR Size; // [rsp+58h] [rbp-69h] BYREF
  void *Value; // [rsp+60h] [rbp-61h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+68h] [rbp-59h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+88h] [rbp-39h] BYREF
  struct _PROC_THREAD_ATTRIBUTE_LIST *v37; // [rsp+F0h] [rbp+2Fh]
  LPWSTR lpDst; // [rsp+128h] [rbp+67h] BYREF
  void *Block; // [rsp+140h] [rbp+7Fh] BYREF

  lpDst = this;
  if ( (unsigned int)Accommodation::IsRunning(a2) )
    return 0;
  lpDst = 0;
  if ( (int)StringCchLengthW(StartList::_atBrokerExe, 0x7FFFFFFFu, (unsigned __int64 *)&lpDst) >= 0 )
  {
    v6 = lpDst + 130;
    if ( lpDst + 130 >= lpDst )
    {
      lpDst = 0;
      if ( (unsigned __int8)ATL::CHeapPtr<unsigned short,ATL::CCRTAllocator>::Allocate(&lpDst, v6) )
      {
        v7 = ExpandEnvironmentStringsW(StartList::_atBrokerExe, lpDst, (DWORD)v6);
        if ( !v7 )
        {
          LastError = GetLastError();
          v9 = LastError;
          if ( LastError > 0 )
            v9 = (unsigned __int16)LastError | 0x80070000;
          goto LABEL_32;
        }
        if ( v7 > (unsigned __int64)v6 )
        {
          v9 = -2147024774;
LABEL_32:
          free(lpDst);
          return v9;
        }
        v10 = (unsigned __int64)(v6 + 11);
        if ( v6 + 11 >= v6 )
        {
          v11 = v6 + 141;
          if ( v10 + 260 >= v10 )
          {
            Block = 0;
            if ( !(unsigned __int8)ATL::CHeapPtr<unsigned short,ATL::CCRTAllocator>::Allocate(&Block, v10 + 260) )
            {
              free(Block);
              goto LABEL_15;
            }
            IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Narrator_AddUpdates>::GetImpl'::`2'::impl);
            v13 = *((_BYTE *)a2 + 85);
            v14 = L"/launchnarratorhome";
            if ( IsEnabled )
            {
              if ( !v13 )
                v14 = &LocaleName;
              v15 = L"/launchnarratorupdates";
              if ( !*((_BYTE *)a2 + 86) )
                v15 = &LocaleName;
              v16 = L"/hardwarebuttonlaunch";
              if ( !*((_BYTE *)a2 + 84) )
                v16 = &LocaleName;
              lpPreviousValue = v16;
              v17 = (unsigned __int64)v11;
              v18 = (WCHAR *)Block;
              v19 = StringCchPrintfW(
                      (unsigned __int16 *)Block,
                      v17,
                      L"%s /start %s %s %s %s",
                      lpDst,
                      *(_QWORD *)a2,
                      lpPreviousValue,
                      v15,
                      v14);
            }
            else
            {
              if ( !v13 )
                v14 = &LocaleName;
              v20 = L"/hardwarebuttonlaunch";
              if ( !*((_BYTE *)a2 + 84) )
                v20 = &LocaleName;
              lpPreviousValuea = v20;
              v21 = (unsigned __int64)v11;
              v18 = (WCHAR *)Block;
              v19 = StringCchPrintfW(
                      (unsigned __int16 *)Block,
                      v21,
                      L"%s /start %s %s %s",
                      lpDst,
                      *(_QWORD *)a2,
                      lpPreviousValuea,
                      v14);
            }
            if ( v19 >= 0 )
            {
              memset(&ProcessInformation, 0, sizeof(ProcessInformation));
              memset_0(&StartupInfo.cb + 1, 0, 0x6Cu);
              StartupInfo.cb = 112;
              Value = 0;
              v23 = 0;
              v24 = 0;
              Size = 0;
              if ( a3 )
              {
                if ( (int)GetShellProcessHandle(v22, &Value) >= 0 )
                {
                  InitializeProcThreadAttributeList(0, 1u, 0, &Size);
                  v25 = Size;
                  ProcessHeap = GetProcessHeap();
                  v27 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)HeapAlloc(ProcessHeap, 0, v25);
                  v24 = v27;
                  if ( v27 )
                  {
                    if ( InitializeProcThreadAttributeList(v27, 1u, 0, &Size) )
                    {
                      v23 = 1;
                      updated = UpdateProcThreadAttribute(v24, 0, 0x20000u, &Value, 8u, 0, 0);
                      v29 = v37;
                      if ( updated )
                        v29 = v24;
                      v37 = v29;
                    }
                  }
                }
              }
              if ( CreateProcessW(lpDst, v18, 0, 0, 0, 0x1080000u, 0, 0, &StartupInfo, &ProcessInformation) )
              {
                v9 = 0;
                CloseHandle(ProcessInformation.hProcess);
                CloseHandle(ProcessInformation.hThread);
              }
              else
              {
                v9 = -2147467259;
              }
              if ( v23 )
                DeleteProcThreadAttributeList(v24);
              if ( v24 )
              {
                v30 = GetProcessHeap();
                HeapFree(v30, 0, v24);
              }
              free(v18);
              goto LABEL_32;
            }
            free(v18);
          }
        }
        v9 = -2147467259;
        goto LABEL_32;
      }
LABEL_15:
      v9 = -2147024882;
      goto LABEL_32;
    }
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x18023bd78  mov     rax, rsp
0x18023bd7b  mov     [rax+10h], rbx
0x18023bd7f  mov     [rax+18h], rsi
0x18023bd83  mov     [rax+8], rcx
0x18023bd87  push    rbp
0x18023bd88  push    r12
0x18023bd8a  push    r13
0x18023bd8c  push    r14
0x18023bd8e  push    r15
0x18023bd90  lea     rbp, [rax-5Fh]
0x18023bd94  sub     rsp, 0F0h
0x18023bd9b  mov     r12d, r8d
0x18023bd9e  mov     rsi, rdx
0x18023bda1  mov     rcx, rdx; this
0x18023bda4  call    ?IsRunning@Accommodation@@QEAAHXZ; Accommodation::IsRunning(void)
0x18023bda9  xor     r13d, r13d
0x18023bdac  test    eax, eax
0x18023bdae  jz      short loc_18023BDB7
0x18023bdb0  xor     eax, eax
0x18023bdb2  jmp     loc_18023C138
0x18023bdb7  mov     [rbp+57h+lpDst], r13
0x18023bdbb  lea     r8, [rbp+57h+lpDst]; unsigned __int64 *
0x18023bdbf  mov     edx, 7FFFFFFFh; unsigned __int64
0x18023bdc4  lea     rcx, ?_atBrokerExe@StartList@@0PAGA; "%SystemRoot%\\System32\\ATBroker.exe"
0x18023bdcb  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18023bdd0  test    eax, eax
0x18023bdd2  js      loc_18023C133
0x18023bdd8  mov     rax, [rbp+57h+lpDst]
0x18023bddc  lea     rbx, [rax+104h]
0x18023bde3  cmp     rbx, rax
0x18023bde6  jb      loc_18023C133
0x18023bdec  mov     [rbp+57h+lpDst], r13
0x18023bdf0  mov     rdx, rbx
0x18023bdf3  lea     rcx, [rbp+57h+lpDst]
0x18023bdf7  call    ?Allocate@?$CHeapPtr@GVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<ushort,ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x18023bdfc  test    al, al
0x18023bdfe  jz      loc_18023BE98
0x18023be04  mov     r8d, ebx; nSize
0x18023be07  mov     rdx, [rbp+57h+lpDst]; lpDst
0x18023be0b  lea     rcx, ?_atBrokerExe@StartList@@0PAGA; "%SystemRoot%\\System32\\ATBroker.exe"
0x18023be12  call    cs:__imp_ExpandEnvironmentStringsW
0x18023be19  nop     dword ptr [rax+rax+00h]
0x18023be1e  test    eax, eax
0x18023be20  jnz     short loc_18023BE46
0x18023be22  call    cs:__imp_GetLastError
0x18023be29  nop     dword ptr [rax+rax+00h]
0x18023be2e  mov     esi, eax
0x18023be30  test    eax, eax
0x18023be32  jle     loc_18023BF6F
0x18023be38  movzx   esi, ax
0x18023be3b  or      esi, 80070000h
0x18023be41  jmp     loc_18023BF6F
0x18023be46  mov     eax, eax
0x18023be48  cmp     rax, rbx
0x18023be4b  jbe     short loc_18023BE57
0x18023be4d  mov     esi, 8007007Ah
0x18023be52  jmp     loc_18023BF6F
0x18023be57  lea     rax, [rbx+16h]
0x18023be5b  cmp     rax, rbx
0x18023be5e  jb      loc_18023BF6A
0x18023be64  lea     rbx, [rax+104h]
0x18023be6b  cmp     rbx, rax
0x18023be6e  jb      loc_18023BF6A
0x18023be74  mov     [rbp+57h+Block], r13
0x18023be78  mov     rdx, rbx
0x18023be7b  lea     rcx, [rbp+57h+Block]
0x18023be7f  call    ?Allocate@?$CHeapPtr@GVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<ushort,ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x18023be84  test    al, al
0x18023be86  jnz     short loc_18023BEA2
0x18023be88  mov     rcx, [rbp+57h+Block]; Block
0x18023be8c  call    cs:__imp_free
0x18023be93  nop     dword ptr [rax+rax+00h]
0x18023be98  mov     esi, 8007000Eh
0x18023be9d  jmp     loc_18023BF6F
0x18023bea2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates> `wil::Feature<__WilFeatureTraits_Feature_Narrator_AddUpdates>::GetImpl(void)'::`2'::impl
0x18023bea9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates>::__private_IsEnabled(void)
0x18023beae  mov     dl, [rsi+55h]
0x18023beb1  lea     r8, LocaleName
0x18023beb8  lea     rcx, aLaunchnarrator; "/launchnarratorhome"
0x18023bebf  mov     r9, [rbp+57h+lpDst]
0x18023bec3  test    al, al
0x18023bec5  jz      short loc_18023BF1A
0x18023bec7  test    dl, dl
0x18023bec9  cmovz   rcx, r8
0x18023becd  lea     rax, aLaunchnarrator_0; "/launchnarratorupdates"
0x18023bed4  cmp     [rsi+56h], r13b
0x18023bed8  cmovz   rax, r8
0x18023bedc  lea     rdx, aHardwarebutton; "/hardwarebuttonlaunch"
0x18023bee3  cmp     [rsi+54h], r13b
0x18023bee7  cmovz   rdx, r8
0x18023beeb  mov     [rsp+110h+lpCurrentDirectory], rcx
0x18023bef0  mov     [rsp+110h+lpReturnSize], rax
0x18023bef5  mov     [rsp+110h+lpPreviousValue], rdx
0x18023befa  mov     rax, [rsi]
0x18023befd  mov     [rsp+110h+cbSize], rax
0x18023bf02  lea     r8, aSStartSSSS; "%s /start %s %s %s %s"
0x18023bf09  mov     rdx, rbx; unsigned __int64
0x18023bf0c  mov     rbx, [rbp+57h+Block]
0x18023bf10  mov     rcx, rbx; unsigned __int16 *
0x18023bf13  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18023bf18  jmp     short loc_18023BF57
0x18023bf1a  test    dl, dl
0x18023bf1c  cmovz   rcx, r8
0x18023bf20  lea     rdx, aHardwarebutton; "/hardwarebuttonlaunch"
0x18023bf27  cmp     [rsi+54h], r13b
0x18023bf2b  cmovz   rdx, r8
0x18023bf2f  mov     [rsp+110h+lpReturnSize], rcx
0x18023bf34  mov     [rsp+110h+lpPreviousValue], rdx
0x18023bf39  mov     rax, [rsi]
0x18023bf3c  mov     [rsp+110h+cbSize], rax
0x18023bf41  lea     r8, aSStartSSS; "%s /start %s %s %s"
0x18023bf48  mov     rdx, rbx; unsigned __int64
0x18023bf4b  mov     rbx, [rbp+57h+Block]
0x18023bf4f  mov     rcx, rbx; unsigned __int16 *
0x18023bf52  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18023bf57  test    eax, eax
0x18023bf59  jns     short loc_18023BF86
0x18023bf5b  mov     rcx, rbx; Block
0x18023bf5e  call    cs:__imp_free
0x18023bf65  nop     dword ptr [rax+rax+00h]
0x18023bf6a  mov     esi, 80004005h
0x18023bf6f  mov     rcx, [rbp+57h+lpDst]; Block
0x18023bf73  call    cs:__imp_free
0x18023bf7a  nop     dword ptr [rax+rax+00h]
0x18023bf7f  mov     eax, esi
0x18023bf81  jmp     loc_18023C138
0x18023bf86  xorps   xmm0, xmm0
0x18023bf89  xor     eax, eax
0x18023bf8b  movups  xmmword ptr [rbp+57h+ProcessInformation.hProcess], xmm0
0x18023bf8f  mov     qword ptr [rbp+57h+ProcessInformation.dwProcessId], rax
0x18023bf93  xor     edx, edx; Val
0x18023bf95  lea     r8d, [rax+6Ch]; Size
0x18023bf99  lea     rcx, [rbp+57h+StartupInfo+4]; void *
0x18023bf9d  call    memset_0
0x18023bfa2  mov     [rbp+57h+StartupInfo.cb], 70h ; 'p'
0x18023bfa9  mov     [rbp+57h+Value], r13
0x18023bfad  mov     r15d, r13d
0x18023bfb0  mov     r14, r13
0x18023bfb3  mov     [rbp+57h+Size], r13
0x18023bfb7  test    r12d, r12d
0x18023bfba  jz      loc_18023C075
0x18023bfc0  lea     rdx, [rbp+57h+Value]; void **
0x18023bfc4  call    ?GetShellProcessHandle@@YAJKPEAPEAX@Z; GetShellProcessHandle(ulong,void * *)
0x18023bfc9  test    eax, eax
0x18023bfcb  js      loc_18023C075
0x18023bfd1  lea     r9, [rbp+57h+Size]; lpSize
0x18023bfd5  xor     r8d, r8d; dwFlags
0x18023bfd8  lea     r12d, [r8+1]
0x18023bfdc  mov     edx, r12d; dwAttributeCount
0x18023bfdf  xor     ecx, ecx; lpAttributeList
0x18023bfe1  call    cs:__imp_InitializeProcThreadAttributeList
0x18023bfe8  nop     dword ptr [rax+rax+00h]
0x18023bfed  mov     rsi, [rbp+57h+Size]
0x18023bff1  call    cs:__imp_GetProcessHeap
0x18023bff8  nop     dword ptr [rax+rax+00h]
0x18023bffd  mov     r8, rsi; dwBytes
0x18023c000  xor     edx, edx; dwFlags
0x18023c002  mov     rcx, rax; hHeap
0x18023c005  call    cs:__imp_HeapAlloc
0x18023c00c  nop     dword ptr [rax+rax+00h]
0x18023c011  mov     r14, rax
0x18023c014  test    rax, rax
0x18023c017  jz      short loc_18023C075
0x18023c019  lea     r9, [rbp+57h+Size]; lpSize
0x18023c01d  xor     r8d, r8d; dwFlags
0x18023c020  mov     edx, r12d; dwAttributeCount
0x18023c023  mov     rcx, rax; lpAttributeList
0x18023c026  call    cs:__imp_InitializeProcThreadAttributeList
0x18023c02d  nop     dword ptr [rax+rax+00h]
0x18023c032  test    eax, eax
0x18023c034  jz      short loc_18023C075
0x18023c036  mov     r15d, r12d
0x18023c039  mov     [rsp+110h+lpReturnSize], r13; lpReturnSize
0x18023c03e  mov     [rsp+110h+lpPreviousValue], r13; lpPreviousValue
0x18023c043  mov     [rsp+110h+cbSize], 8; cbSize
0x18023c04c  lea     r9, [rbp+57h+Value]; lpValue
0x18023c050  xor     edx, edx; dwFlags
0x18023c052  mov     r8d, 20000h; Attribute
0x18023c058  mov     rcx, r14; lpAttributeList
0x18023c05b  call    cs:__imp_UpdateProcThreadAttribute
0x18023c062  nop     dword ptr [rax+rax+00h]
0x18023c067  mov     rcx, [rbp+57h+var_28]
0x18023c06b  test    eax, eax
0x18023c06d  cmovnz  rcx, r14
0x18023c071  mov     [rbp+57h+var_28], rcx
0x18023c075  lea     rax, [rbp+57h+ProcessInformation]
0x18023c079  mov     [rsp+110h+lpProcessInformation], rax; lpProcessInformation
0x18023c07e  lea     rax, [rbp+57h+StartupInfo]
0x18023c082  mov     [rsp+110h+lpStartupInfo], rax; lpStartupInfo
0x18023c087  mov     [rsp+110h+lpCurrentDirectory], r13; lpCurrentDirectory
0x18023c08c  mov     [rsp+110h+lpReturnSize], r13; lpEnvironment
0x18023c091  mov     dword ptr [rsp+110h+lpPreviousValue], 1080000h; dwCreationFlags
0x18023c099  mov     dword ptr [rsp+110h+cbSize], r13d; bInheritHandles
0x18023c09e  xor     r9d, r9d; lpThreadAttributes
0x18023c0a1  xor     r8d, r8d; lpProcessAttributes
0x18023c0a4  mov     rdx, rbx; lpCommandLine
0x18023c0a7  mov     rcx, [rbp+57h+lpDst]; lpApplicationName
0x18023c0ab  call    cs:__imp_CreateProcessW
0x18023c0b2  nop     dword ptr [rax+rax+00h]
0x18023c0b7  test    eax, eax
0x18023c0b9  jz      short loc_18023C0E0
0x18023c0bb  mov     esi, r13d
0x18023c0be  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hObject
0x18023c0c2  call    cs:__imp_CloseHandle
0x18023c0c9  nop     dword ptr [rax+rax+00h]
0x18023c0ce  mov     rcx, [rbp+57h+ProcessInformation.hThread]; hObject
0x18023c0d2  call    cs:__imp_CloseHandle
0x18023c0d9  nop     dword ptr [rax+rax+00h]
0x18023c0de  jmp     short loc_18023C0E5
0x18023c0e0  mov     esi, 80004005h
0x18023c0e5  test    r15d, r15d
0x18023c0e8  jz      short loc_18023C0F9
0x18023c0ea  mov     rcx, r14; lpAttributeList
0x18023c0ed  call    cs:__imp_DeleteProcThreadAttributeList
0x18023c0f4  nop     dword ptr [rax+rax+00h]
0x18023c0f9  test    r14, r14
0x18023c0fc  jz      short loc_18023C11F
0x18023c0fe  call    cs:__imp_GetProcessHeap
0x18023c105  nop     dword ptr [rax+rax+00h]
0x18023c10a  mov     rcx, rax; hHeap
0x18023c10d  mov     r8, r14; lpMem
0x18023c110  xor     edx, edx; dwFlags
0x18023c112  call    cs:__imp_HeapFree
0x18023c119  nop     dword ptr [rax+rax+00h]
0x18023c11e  nop
0x18023c11f  mov     rcx, rbx; Block
0x18023c122  call    cs:__imp_free
0x18023c129  nop     dword ptr [rax+rax+00h]
0x18023c12e  jmp     loc_18023BF6F
0x18023c133  mov     eax, 80004005h
0x18023c138  lea     r11, [rsp+110h+var_20]
0x18023c140  mov     rbx, [r11+38h]
0x18023c144  mov     rsi, [r11+40h]
0x18023c148  mov     rsp, r11
0x18023c14b  pop     r15
0x18023c14d  pop     r14
0x18023c14f  pop     r13
0x18023c151  pop     r12
0x18023c153  pop     rbp
0x18023c154  retn
```
