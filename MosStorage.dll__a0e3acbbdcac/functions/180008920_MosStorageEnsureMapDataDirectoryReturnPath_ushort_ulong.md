# MosStorageEnsureMapDataDirectoryReturnPath(ushort *,ulong)

- ea: `0x180008920`
- end: `0x180008a18`
- name: `?MosStorageEnsureMapDataDirectoryReturnPath@@YAJPEAGK@Z`
- size: `248`
- prototype: `__int64 __fastcall(WCHAR *lpFileName, size_t)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001c80`
- `0x180006c44`
- `0x180008690`
- `0x180008920`
- `0x180008ac0`
- `0x18000cb1c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800089cf`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800089cf`
- `ZTrace_Maps!ZTraceReportIgnoreNoThis` at `0x1800089b7`
- `ZTrace_Maps!ZTraceReportIgnoreNoThis` at `0x1800089b7`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180008970`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180008970`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180008992`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180008992`

## string_xrefs

- `0x180008964`: `MosStorageEnsureMapDataDirectoryReturnPath`
- `0x180008989`: `MosStorageEnsureMapDataDirectoryReturnPath`
- `0x1800089ae`: `MosStorageEnsureMapDataDirectoryReturnPath`

## pseudocode

```c
__int64 __fastcall MosStorageEnsureMapDataDirectoryReturnPath(WCHAR *lpFileName, size_t a2)
{
  unsigned int v3; // eax
  unsigned int v4; // ebx
  int DataDirectory; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  int v9; // r8d
  int v10; // eax
  char v11; // dl
  __int128 v13; // [rsp+20h] [rbp-38h] BYREF
  __int64 v14; // [rsp+30h] [rbp-28h]
  __int64 v15; // [rsp+38h] [rbp-20h]

  v13 = 0;
  v14 = 0;
  v15 = 7;
  LOWORD(v13) = 0;
  if ( lpFileName )
  {
    DataDirectory = MosStorageGetDataDirectory(lpFileName, a2);
    if ( DataDirectory >= 0 )
    {
      v10 = ((__int64 (__fastcall *)(__int64, __int64, __int64, __int128 *))RegUtils::GetMapsPersistedRegString)(
              v7,
              v6,
              v8,
              &v13);
      if ( v10 < 0 )
        ZTraceReportIgnoreNoThis(v10, "MosStorageEnsureMapDataDirectoryReturnPath", 1162);
      v11 = !v14 || wcsstr(lpFileName, L"Microsoft\\MapData\\");
      DataDirectory = MosStorageEnsureMapDataDirectoryAndKeepFileHandle(lpFileName, v11, 0);
      if ( DataDirectory >= 0 )
      {
        v4 = 0;
        goto LABEL_16;
      }
      v9 = 1167;
    }
    else
    {
      v9 = 1158;
    }
    v3 = ZTraceReportPropagationNoThis(DataDirectory, "MosStorageEnsureMapDataDirectoryReturnPath", v9);
  }
  else
  {
    v3 = ZTraceReportOriginationNoThis(-2147467261, "MosStorageEnsureMapDataDirectoryReturnPath", 1156);
  }
  v4 = v3;
LABEL_16:
  std::wstring::~wstring(&v13);
  return v4;
}

```

## disassembly

```asm
0x180008920  push    rbx
0x180008922  sub     rsp, 50h
0x180008926  mov     rax, cs:__security_cookie
0x18000892d  xor     rax, rsp
0x180008930  mov     [rsp+58h+var_18], rax
0x180008935  mov     rbx, rcx
0x180008938  xorps   xmm0, xmm0
0x18000893b  movups  [rsp+58h+var_38], xmm0
0x180008940  mov     [rsp+58h+var_28], 0
0x180008949  mov     [rsp+58h+var_20], 7
0x180008952  xor     eax, eax
0x180008954  mov     word ptr [rsp+58h+var_38], ax
0x180008959  test    rcx, rcx
0x18000895c  jnz     short loc_18000897A
0x18000895e  mov     r8d, 484h
0x180008964  lea     rdx, aMosstorageensu_5; "MosStorageEnsureMapDataDirectoryReturnP"...
0x18000896b  mov     ecx, 80004003h
0x180008970  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x180008976  mov     ebx, eax
0x180008978  jmp     short loc_1800089F9
0x18000897a  call    ?MosStorageGetDataDirectory@@YAJPEAGK@Z; MosStorageGetDataDirectory(ushort *,ulong)
0x18000897f  test    eax, eax
0x180008981  jns     short loc_18000899A
0x180008983  mov     r8d, 486h
0x180008989  lea     rdx, aMosstorageensu_5; "MosStorageEnsureMapDataDirectoryReturnP"...
0x180008990  mov     ecx, eax
0x180008992  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180008998  jmp     short loc_180008976
0x18000899a  lea     r9, [rsp+58h+var_38]
0x18000899f  call    ?GetMapsPersistedRegString@RegUtils@@SAJW4MapsRegKeys@@PEBG1PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegUtils::GetMapsPersistedRegString(MapsRegKeys,ushort const *,ushort const *,std::wstring *)
0x1800089a4  test    eax, eax
0x1800089a6  jns     short loc_1800089BD
0x1800089a8  mov     r8d, 48Ah
0x1800089ae  lea     rdx, aMosstorageensu_5; "MosStorageEnsureMapDataDirectoryReturnP"...
0x1800089b5  mov     ecx, eax
0x1800089b7  call    cs:__imp_?ZTraceReportIgnoreNoThis@@YAXHPEBDH@Z; ZTraceReportIgnoreNoThis(int,char const *,int)
0x1800089bd  cmp     [rsp+58h+var_28], 0
0x1800089c3  jz      short loc_1800089DE
0x1800089c5  lea     rdx, aMicrosoftMapda; "Microsoft\\MapData\\"
0x1800089cc  mov     rcx, rbx; Str
0x1800089cf  call    cs:__imp_wcsstr
0x1800089d5  test    rax, rax
0x1800089d8  jnz     short loc_1800089DE
0x1800089da  xor     dl, dl
0x1800089dc  jmp     short loc_1800089E0
0x1800089de  mov     dl, 1; bool
0x1800089e0  xor     r8d, r8d; void **
0x1800089e3  mov     rcx, rbx; lpFileName
0x1800089e6  call    ?MosStorageEnsureMapDataDirectoryAndKeepFileHandle@@YAJPEBG_NPEAPEAX@Z; MosStorageEnsureMapDataDirectoryAndKeepFileHandle(ushort const *,bool,void * *)
0x1800089eb  test    eax, eax
0x1800089ed  jns     short loc_1800089F7
0x1800089ef  mov     r8d, 48Fh
0x1800089f5  jmp     short loc_180008989
0x1800089f7  xor     ebx, ebx
0x1800089f9  lea     rcx, [rsp+58h+var_38]
0x1800089fe  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008a03  mov     eax, ebx
0x180008a05  mov     rcx, [rsp+58h+var_18]
0x180008a0a  xor     rcx, rsp; StackCookie
0x180008a0d  call    __security_check_cookie
0x180008a12  add     rsp, 50h
0x180008a16  pop     rbx
0x180008a17  retn
```
