# GetCachedCurrentMapDataDirectory

- ea: `0x18000733c`
- end: `0x180007644`
- name: `GetCachedCurrentMapDataDirectory`
- size: `776`
- prototype: `__int64 __fastcall(__int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x18000764c`
- `0x180008ac0`
- `0x180009220`

## callees

- `0x180001c80`
- `0x180002802`
- `0x180006c44`
- `0x18000733c`
- `0x1800078d4`
- `0x180009010`
- `0x18000cb1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000737e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000737e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007619`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007619`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000760e`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000760e`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x1800075bc`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x1800075e6`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x1800075bc`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x1800075e6`

## string_xrefs

- `0x1800075b2`: `GetCachedCurrentMapDataDirectory`
- `0x1800075df`: `GetCachedCurrentMapDataDirectory`
- `0x180007602`: `GetCachedCurrentMapDataDirectory`

## pseudocode

```c
__int64 __fastcall GetCachedCurrentMapDataDirectory(__int16 *a1, unsigned int a2)
{
  unsigned __int64 v2; // r15
  unsigned int v4; // ebx
  __int64 v5; // rsi
  __int16 *v6; // r14
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  int MapsPersistedRegString; // eax
  int v11; // r8d
  const unsigned __int16 *v12; // rcx
  __int64 v13; // rax
  __int16 *v14; // rcx
  __int64 v15; // rdx
  __int16 *v16; // r8
  __int16 v17; // r9
  __int16 *v18; // rcx
  char *v19; // rax
  unsigned __int64 v20; // rdx
  unsigned int v21; // r9d
  __int16 v22; // ax
  __int16 *v23; // rcx
  unsigned int v24; // eax
  int v25; // ecx
  __int64 v27; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v28[205]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v29[2]; // [rsp+6A0h] [rbp+5A0h] BYREF
  __int64 v30; // [rsp+6B0h] [rbp+5B0h]
  unsigned __int64 v31; // [rsp+6B8h] [rbp+5B8h]

  v2 = a2;
  EnterCriticalSection(&CriticalSection);
  if ( !a1 )
  {
    v24 = ZTraceReportOriginationNoThis(-2147467261, "GetCachedCurrentMapDataDirectory", 402);
    goto LABEL_50;
  }
  v4 = 0;
  v5 = 2147483646;
  v6 = &word_180018B50;
  if ( !word_180018B50 || !qword_180018B48 )
  {
    *(_OWORD *)v29 = 0;
    v30 = 0;
    v31 = 7;
    LOWORD(v29[0]) = 0;
    memset_0(&v27, 0, 0x670u);
    MapsPersistedRegString = RegUtils::GetMapsPersistedRegString(v8, v7, v9, v29, &CriticalSection, 1, v27, v28[0]);
    if ( MapsPersistedRegString < 0 )
    {
      v11 = 412;
      goto LABEL_47;
    }
    if ( v30 )
    {
      v12 = (const unsigned __int16 *)v29;
      if ( v31 > 7 )
        v12 = v29[0];
      MapsPersistedRegString = MosStorageGetStorageDeviceDataFromDeviceGuid(v12, (struct _STORAGE_DEVICE_DATA *)&v27);
      v4 = MapsPersistedRegString;
      if ( MapsPersistedRegString == -2147023728 )
      {
        MapsPersistedRegString = GetDefaultStorageLocation(&v27);
        if ( MapsPersistedRegString < 0 )
        {
          v11 = 426;
          goto LABEL_47;
        }
        v4 = 0;
      }
      else if ( MapsPersistedRegString < 0 )
      {
        v11 = 429;
        goto LABEL_47;
      }
    }
    else
    {
      MapsPersistedRegString = GetDefaultStorageLocation(&v27);
      if ( MapsPersistedRegString < 0 )
      {
        v11 = 416;
LABEL_47:
        v25 = MapsPersistedRegString;
        goto LABEL_48;
      }
    }
    v13 = 2147483646;
    v14 = (__int16 *)v28 + 2;
    v15 = 260;
    v16 = &word_180018B50;
    do
    {
      if ( !v13 )
        break;
      v17 = *v14;
      if ( !*v14 )
        break;
      ++v14;
      *v16++ = v17;
      --v13;
      --v15;
    }
    while ( v15 );
    v18 = v16 - 1;
    if ( v15 )
      v18 = v16;
    *v18 = 0;
    if ( !v15 )
    {
      v11 = 433;
      v25 = -2147024774;
LABEL_48:
      v4 = ZTraceReportPropagationNoThis(v25, "GetCachedCurrentMapDataDirectory", v11);
      std::wstring::~wstring(v29);
      goto LABEL_51;
    }
    v19 = (char *)Src;
    if ( Src == (void *)qword_180018DD8 )
    {
      __int2c();
    }
    else
    {
      while ( *(unsigned __int16 **)(v19 + 1084) != *(unsigned __int16 **)((char *)&v28[134] + 4)
           || *(unsigned __int16 **)(v19 + 1092) != *(unsigned __int16 **)((char *)&v28[135] + 4) )
      {
        v19 += 1648;
        if ( v19 == (char *)qword_180018DD8 )
          goto LABEL_29;
      }
      *((_DWORD *)v19 + 2) = 1;
      qword_180018B48 = v19;
    }
LABEL_29:
    if ( !qword_180018B48 )
      __int2c();
    std::wstring::~wstring(v29);
  }
  v20 = v2;
  if ( !(_DWORD)v2 )
  {
    v21 = -2147024809;
    goto LABEL_43;
  }
  if ( v2 > 0x7FFFFFFF )
  {
    v21 = -2147024809;
    *a1 = 0;
LABEL_43:
    v24 = ZTraceReportPropagationNoThis(v21, "GetCachedCurrentMapDataDirectory", 450);
LABEL_50:
    v4 = v24;
    goto LABEL_51;
  }
  do
  {
    if ( !v5 )
      break;
    v22 = *v6;
    if ( !*v6 )
      break;
    ++v6;
    *a1++ = v22;
    --v5;
    --v20;
  }
  while ( v20 );
  v21 = v20 == 0 ? 0x8007007A : 0;
  v23 = a1 - 1;
  if ( v20 )
    v23 = a1;
  *v23 = 0;
  if ( !v20 )
    goto LABEL_43;
LABEL_51:
  LeaveCriticalSection(&CriticalSection);
  return v4;
}

```

## disassembly

```asm
0x18000733c  push    rbp
0x18000733e  push    rbx
0x18000733f  push    rsi
0x180007340  push    rdi
0x180007341  push    r12
0x180007343  push    r13
0x180007345  push    r14
0x180007347  push    r15
0x180007349  lea     rbp, [rsp-5D8h]
0x180007351  sub     rsp, 6D8h
0x180007358  mov     rax, cs:__security_cookie
0x18000735f  xor     rax, rsp
0x180007362  mov     [rbp+610h+var_50], rax
0x180007369  mov     r15d, edx
0x18000736c  mov     rdi, rcx
0x18000736f  lea     r13, CriticalSection
0x180007376  mov     [rsp+710h+var_6F0], r13
0x18000737b  mov     rcx, r13; lpCriticalSection
0x18000737e  call    cs:__imp_EnterCriticalSection
0x180007384  mov     [rsp+710h+var_6E8], 1
0x180007389  xor     r12d, r12d
0x18000738c  test    rdi, rdi
0x18000738f  jz      loc_1800075FC
0x180007395  mov     ebx, r12d
0x180007398  mov     esi, 7FFFFFFEh
0x18000739d  lea     r14, word_180018B50
0x1800073a4  cmp     cs:word_180018B50, r12w
0x1800073ac  jz      short loc_1800073BB
0x1800073ae  cmp     cs:qword_180018B48, r12
0x1800073b5  jnz     loc_18000753C
0x1800073bb  xorps   xmm0, xmm0
0x1800073be  movups  xmmword ptr [rbp+610h+var_70], xmm0
0x1800073c5  mov     [rbp+610h+var_60], r12
0x1800073cc  mov     [rbp+610h+var_58], 7
0x1800073d7  mov     word ptr [rbp+610h+var_70], r12w
0x1800073df  xor     edx, edx; Val
0x1800073e1  mov     r8d, 670h; Size
0x1800073e7  lea     rcx, [rsp+710h+var_6E0]; void *
0x1800073ec  call    memset_0
0x1800073f1  lea     r9, [rbp+610h+var_70]
0x1800073f8  call    ?GetMapsPersistedRegString@RegUtils@@SAJW4MapsRegKeys@@PEBG1PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegUtils::GetMapsPersistedRegString(MapsRegKeys,ushort const *,ushort const *,std::wstring *)
0x1800073fd  test    eax, eax
0x1800073ff  js      loc_1800075D7
0x180007405  cmp     [rbp+610h+var_60], r12
0x18000740c  jnz     short loc_180007427
0x18000740e  lea     rcx, [rsp+710h+var_6E0]; void *
0x180007413  call    GetDefaultStorageLocation
0x180007418  test    eax, eax
0x18000741a  jns     short loc_180007477
0x18000741c  mov     r8d, 1A0h
0x180007422  jmp     loc_1800075DD
0x180007427  lea     rcx, [rbp+610h+var_70]
0x18000742e  cmp     [rbp+610h+var_58], 7
0x180007436  cmova   rcx, [rbp+610h+var_70]; unsigned __int16 *
0x18000743e  lea     rdx, [rsp+710h+var_6E0]; struct _STORAGE_DEVICE_DATA *
0x180007443  call    ?MosStorageGetStorageDeviceDataFromDeviceGuid@@YAJPEBGPEAU_STORAGE_DEVICE_DATA@@@Z; MosStorageGetStorageDeviceDataFromDeviceGuid(ushort const *,_STORAGE_DEVICE_DATA *)
0x180007448  mov     ebx, eax
0x18000744a  cmp     eax, 80070490h
0x18000744f  jnz     short loc_18000746F
0x180007451  lea     rcx, [rsp+710h+var_6E0]; void *
0x180007456  call    GetDefaultStorageLocation
0x18000745b  test    eax, eax
0x18000745d  js      short loc_180007464
0x18000745f  mov     ebx, r12d
0x180007462  jmp     short loc_180007477
0x180007464  mov     r8d, 1AAh
0x18000746a  jmp     loc_1800075DD
0x18000746f  test    eax, eax
0x180007471  js      loc_1800075CF
0x180007477  mov     rax, rsi
0x18000747a  lea     rcx, [rsp+710h+var_6D4]
0x18000747f  mov     edx, 104h
0x180007484  mov     r8, r14
0x180007487  test    rax, rax
0x18000748a  jz      short loc_1800074AB
0x18000748c  movzx   r9d, word ptr [rcx]
0x180007490  test    r9w, r9w
0x180007494  jz      short loc_1800074AB
0x180007496  add     rcx, 2
0x18000749a  mov     [r8], r9w
0x18000749e  add     r8, 2
0x1800074a2  dec     rax
0x1800074a5  sub     rdx, 1
0x1800074a9  jnz     short loc_180007487
0x1800074ab  mov     rax, rdx
0x1800074ae  neg     rax
0x1800074b1  sbb     r9d, r9d
0x1800074b4  not     r9d
0x1800074b7  and     r9d, 8007007Ah
0x1800074be  lea     rcx, [r8-2]
0x1800074c2  test    rdx, rdx
0x1800074c5  cmovnz  rcx, r8
0x1800074c9  mov     [rcx], r12w
0x1800074cd  jz      loc_1800075C4
0x1800074d3  mov     rcx, cs:qword_180018DD8
0x1800074da  mov     rax, cs:Src
0x1800074e1  cmp     rax, rcx
0x1800074e4  jnz     short loc_1800074EA
0x1800074e6  int     2Ch; Windows NT - assertion failure
0x1800074e8  jmp     short loc_180007525
0x1800074ea  mov     rdx, [rbp+610h+var_29C]
0x1800074f1  mov     r8, [rbp+610h+var_2A4]
0x1800074f8  cmp     [rax+43Ch], r8
0x1800074ff  jnz     short loc_18000750A
0x180007501  cmp     [rax+444h], rdx
0x180007508  jz      short loc_180007517
0x18000750a  add     rax, 670h
0x180007510  cmp     rax, rcx
0x180007513  jnz     short loc_1800074F8
0x180007515  jmp     short loc_180007525
0x180007517  mov     dword ptr [rax+8], 1
0x18000751e  mov     cs:qword_180018B48, rax
0x180007525  cmp     cs:qword_180018B48, r12
0x18000752c  jnz     short loc_180007530
0x18000752e  int     2Ch; Windows NT - assertion failure
0x180007530  lea     rcx, [rbp+610h+var_70]
0x180007537  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000753c  mov     rdx, r15
0x18000753f  test    r15d, r15d
0x180007542  jz      short loc_18000759D
0x180007544  cmp     rdx, 7FFFFFFFh
0x18000754b  jbe     short loc_180007555
0x18000754d  mov     r9d, 80070057h
0x180007553  jmp     short loc_1800075A8
0x180007555  test    rsi, rsi
0x180007558  jz      short loc_180007577
0x18000755a  movzx   eax, word ptr [r14]
0x18000755e  test    ax, ax
0x180007561  jz      short loc_180007577
0x180007563  add     r14, 2
0x180007567  mov     [rdi], ax
0x18000756a  add     rdi, 2
0x18000756e  dec     rsi
0x180007571  sub     rdx, 1
0x180007575  jnz     short loc_180007555
0x180007577  mov     rax, rdx
0x18000757a  neg     rax
0x18000757d  sbb     r9d, r9d
0x180007580  not     r9d
0x180007583  and     r9d, 8007007Ah
0x18000758a  lea     rcx, [rdi-2]
0x18000758e  test    rdx, rdx
0x180007591  cmovnz  rcx, rdi
0x180007595  mov     [rcx], r12w
0x180007599  jnz     short loc_180007616
0x18000759b  jmp     short loc_1800075AC
0x18000759d  mov     r9d, 80070057h
0x1800075a3  test    r15d, r15d
0x1800075a6  jz      short loc_1800075AC
0x1800075a8  mov     [rdi], r12w
0x1800075ac  mov     r8d, 1C2h
0x1800075b2  lea     rdx, aGetcachedcurre; "GetCachedCurrentMapDataDirectory"
0x1800075b9  mov     ecx, r9d
0x1800075bc  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x1800075c2  jmp     short loc_180007614
0x1800075c4  mov     r8d, 1B1h
0x1800075ca  mov     ecx, r9d
0x1800075cd  jmp     short loc_1800075DF
0x1800075cf  mov     r8d, 1ADh
0x1800075d5  jmp     short loc_1800075DD
0x1800075d7  mov     r8d, 19Ch
0x1800075dd  mov     ecx, eax
0x1800075df  lea     rdx, aGetcachedcurre; "GetCachedCurrentMapDataDirectory"
0x1800075e6  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x1800075ec  mov     ebx, eax
0x1800075ee  lea     rcx, [rbp+610h+var_70]
0x1800075f5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800075fa  jmp     short loc_180007616
0x1800075fc  mov     r8d, 192h
0x180007602  lea     rdx, aGetcachedcurre; "GetCachedCurrentMapDataDirectory"
0x180007609  mov     ecx, 80004003h
0x18000760e  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x180007614  mov     ebx, eax
0x180007616  mov     rcx, r13; lpCriticalSection
0x180007619  call    cs:__imp_LeaveCriticalSection
0x18000761f  mov     eax, ebx
0x180007621  mov     rcx, [rbp+610h+var_50]
0x180007628  xor     rcx, rsp; StackCookie
0x18000762b  call    __security_check_cookie
0x180007630  add     rsp, 6D8h
0x180007637  pop     r15
0x180007639  pop     r14
0x18000763b  pop     r13
0x18000763d  pop     r12
0x18000763f  pop     rdi
0x180007640  pop     rsi
0x180007641  pop     rbx
0x180007642  pop     rbp
0x180007643  retn
```
