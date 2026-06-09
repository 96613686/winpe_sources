# MosStorageGetDataDirectory(ushort *,ulong)

- ea: `0x180008ac0`
- end: `0x180008c60`
- name: `?MosStorageGetDataDirectory@@YAJPEAGK@Z`
- size: `416`
- prototype: `__int64 __fastcall(PWSTR pszPathOut, size_t cchPathOut)`
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x1800083e0`
- `0x180008920`
- `0x18000af60`
- `0x18000b1d0`

## callees

- `0x180001c80`
- `0x180006c44`
- `0x18000733c`
- `0x180007958`
- `0x180008ac0`
- `0x18000cb1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008af4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008af4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008c38`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008c38`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180008c2d`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180008c2d`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180008b9c`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180008c08`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180008b9c`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180008c08`

## string_xrefs

- `0x180008b92`: `MosStorageGetDataDirectory`
- `0x180008bff`: `MosStorageGetDataDirectory`
- `0x180008c21`: `MosStorageGetDataDirectory`

## pseudocode

```c
__int64 __fastcall MosStorageGetDataDirectory(PWSTR pszPathOut, size_t cchPathOut)
{
  unsigned int v2; // esi
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  unsigned int v7; // edi
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int16 *v10; // rax
  WCHAR v11; // r8
  unsigned int v12; // r9d
  PWSTR v13; // rcx
  unsigned int v14; // eax
  int CachedCurrentMapDataDirectory; // eax
  int v16; // r8d
  __int128 v18; // [rsp+30h] [rbp-30h] BYREF
  __int64 v19; // [rsp+40h] [rbp-20h]
  __int64 v20; // [rsp+48h] [rbp-18h]

  v2 = cchPathOut;
  EnterCriticalSection(&CriticalSection);
  if ( !pszPathOut )
  {
    v14 = ZTraceReportOriginationNoThis(-2147467261, "MosStorageGetDataDirectory", 946);
    goto LABEL_25;
  }
  v7 = 0;
  if ( !word_180018B50 )
  {
    v18 = 0;
    v19 = 0;
    v20 = 7;
    LOWORD(v18) = 0;
    CachedCurrentMapDataDirectory = ((__int64 (__fastcall *)(__int64, __int64, __int64, __int128 *, struct _RTL_CRITICAL_SECTION *, char))RegUtils::GetMapsPersistedRegString)(
                                      v5,
                                      v4,
                                      v6,
                                      &v18,
                                      &CriticalSection,
                                      1);
    if ( CachedCurrentMapDataDirectory < 0 )
    {
      v16 = 958;
      goto LABEL_22;
    }
    if ( v19 )
    {
      CachedCurrentMapDataDirectory = GetCachedCurrentMapDataDirectory(pszPathOut, v2);
      if ( CachedCurrentMapDataDirectory < 0 )
      {
        v16 = 968;
        goto LABEL_22;
      }
    }
    else
    {
      CachedCurrentMapDataDirectory = GetDefaultStoragePath(pszPathOut, v2);
      if ( CachedCurrentMapDataDirectory < 0 )
      {
        v16 = 962;
LABEL_22:
        v7 = ZTraceReportPropagationNoThis(CachedCurrentMapDataDirectory, "MosStorageGetDataDirectory", v16);
      }
    }
    std::wstring::~wstring(&v18);
    goto LABEL_26;
  }
  v8 = v2;
  v9 = 2147483646;
  if ( v2 - 1 > 0x7FFFFFFE )
  {
    v12 = -2147024809;
    if ( v2 )
      *pszPathOut = 0;
    goto LABEL_14;
  }
  v10 = &word_180018B50;
  do
  {
    if ( !v9 )
      break;
    v11 = *v10;
    if ( !*v10 )
      break;
    ++v10;
    *pszPathOut++ = v11;
    --v9;
    --v8;
  }
  while ( v8 );
  v12 = v8 == 0 ? 0x8007007A : 0;
  v13 = pszPathOut - 1;
  if ( v8 )
    v13 = pszPathOut;
  *v13 = 0;
  if ( !v8 )
  {
LABEL_14:
    v14 = ZTraceReportPropagationNoThis(v12, "MosStorageGetDataDirectory", 951);
LABEL_25:
    v7 = v14;
  }
LABEL_26:
  LeaveCriticalSection(&CriticalSection);
  return v7;
}

```

## disassembly

```asm
0x180008ac0  mov     [rsp-28h+arg_10], rbx
0x180008ac5  push    rbp
0x180008ac6  push    rsi
0x180008ac7  push    rdi
0x180008ac8  push    r14
0x180008aca  push    r15
0x180008acc  mov     rbp, rsp
0x180008acf  sub     rsp, 60h
0x180008ad3  mov     rax, cs:__security_cookie
0x180008ada  xor     rax, rsp
0x180008add  mov     [rbp+var_10], rax
0x180008ae1  mov     esi, edx
0x180008ae3  mov     rbx, rcx
0x180008ae6  lea     r15, CriticalSection
0x180008aed  mov     [rbp+var_40], r15
0x180008af1  mov     rcx, r15; lpCriticalSection
0x180008af4  call    cs:__imp_EnterCriticalSection
0x180008afa  mov     [rbp+var_38], 1
0x180008afe  xor     r14d, r14d
0x180008b01  test    rbx, rbx
0x180008b04  jz      loc_180008C1B
0x180008b0a  mov     edi, r14d
0x180008b0d  cmp     cs:word_180018B50, r14w
0x180008b15  jz      loc_180008BA7
0x180008b1b  mov     edx, esi
0x180008b1d  lea     eax, [rsi-1]
0x180008b20  mov     ecx, 7FFFFFFEh
0x180008b25  cmp     eax, ecx
0x180008b27  ja      short loc_180008B7E
0x180008b29  lea     rax, word_180018B50
0x180008b30  test    rcx, rcx
0x180008b33  jz      short loc_180008B54
0x180008b35  movzx   r8d, word ptr [rax]
0x180008b39  test    r8w, r8w
0x180008b3d  jz      short loc_180008B54
0x180008b3f  add     rax, 2
0x180008b43  mov     [rbx], r8w
0x180008b47  add     rbx, 2
0x180008b4b  dec     rcx
0x180008b4e  sub     rdx, 1
0x180008b52  jnz     short loc_180008B30
0x180008b54  mov     rax, rdx
0x180008b57  neg     rax
0x180008b5a  sbb     r9d, r9d
0x180008b5d  not     r9d
0x180008b60  and     r9d, 8007007Ah
0x180008b67  lea     rcx, [rbx-2]
0x180008b6b  test    rdx, rdx
0x180008b6e  cmovnz  rcx, rbx
0x180008b72  mov     [rcx], r14w
0x180008b76  jnz     loc_180008C35
0x180008b7c  jmp     short loc_180008B8C
0x180008b7e  mov     r9d, 80070057h
0x180008b84  test    esi, esi
0x180008b86  jz      short loc_180008B8C
0x180008b88  mov     [rbx], r14w
0x180008b8c  mov     r8d, 3B7h
0x180008b92  lea     rdx, aMosstoragegetd_1; "MosStorageGetDataDirectory"
0x180008b99  mov     ecx, r9d
0x180008b9c  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180008ba2  jmp     loc_180008C33
0x180008ba7  xorps   xmm0, xmm0
0x180008baa  movups  [rbp+var_30], xmm0
0x180008bae  mov     [rbp+var_20], r14
0x180008bb2  mov     [rbp+var_18], 7
0x180008bba  mov     word ptr [rbp+var_30], r14w
0x180008bbf  lea     r9, [rbp+var_30]
0x180008bc3  call    ?GetMapsPersistedRegString@RegUtils@@SAJW4MapsRegKeys@@PEBG1PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegUtils::GetMapsPersistedRegString(MapsRegKeys,ushort const *,ushort const *,std::wstring *)
0x180008bc8  test    eax, eax
0x180008bca  js      short loc_180008BF9
0x180008bcc  mov     edx, esi; cchPathOut
0x180008bce  mov     rcx, rbx; pszPathOut
0x180008bd1  cmp     [rbp+var_20], r14
0x180008bd5  jnz     short loc_180008BE8
0x180008bd7  call    GetDefaultStoragePath
0x180008bdc  test    eax, eax
0x180008bde  jns     short loc_180008C10
0x180008be0  mov     r8d, 3C2h
0x180008be6  jmp     short loc_180008BFF
0x180008be8  call    GetCachedCurrentMapDataDirectory
0x180008bed  test    eax, eax
0x180008bef  jns     short loc_180008C10
0x180008bf1  mov     r8d, 3C8h
0x180008bf7  jmp     short loc_180008BFF
0x180008bf9  mov     r8d, 3BEh
0x180008bff  lea     rdx, aMosstoragegetd_1; "MosStorageGetDataDirectory"
0x180008c06  mov     ecx, eax
0x180008c08  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180008c0e  mov     edi, eax
0x180008c10  lea     rcx, [rbp+var_30]
0x180008c14  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008c19  jmp     short loc_180008C35
0x180008c1b  mov     r8d, 3B2h
0x180008c21  lea     rdx, aMosstoragegetd_1; "MosStorageGetDataDirectory"
0x180008c28  mov     ecx, 80004003h
0x180008c2d  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x180008c33  mov     edi, eax
0x180008c35  mov     rcx, r15; lpCriticalSection
0x180008c38  call    cs:__imp_LeaveCriticalSection
0x180008c3e  mov     eax, edi
0x180008c40  mov     rcx, [rbp+var_10]
0x180008c44  xor     rcx, rsp; StackCookie
0x180008c47  call    __security_check_cookie
0x180008c4c  mov     rbx, [rsp+60h+arg_10]
0x180008c54  add     rsp, 60h
0x180008c58  pop     r15
0x180008c5a  pop     r14
0x180008c5c  pop     rdi
0x180008c5d  pop     rsi
0x180008c5e  pop     rbp
0x180008c5f  retn
```
