# InstallLayoutOrTipPrivateHelpers::IsTfCatTip(ushort *)

- ea: `0x180008b40`
- end: `0x180008ee2`
- name: `?IsTfCatTip@InstallLayoutOrTipPrivateHelpers@@SA_NPEAG@Z`
- size: `930`
- prototype: `bool __fastcall(unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180002f10`
- `0x1800080d0`

## callees

- `0x180008b40`
- `0x180008ee8`
- `0x180008fb0`
- `0x18006c000`
- `0x18006f4c0`
- `0x18009b790`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180008ddb`
- `KERNEL32!InitializeCriticalSection` at `0x180008e66`
- `KERNEL32!InitializeCriticalSection` at `0x180008ddb`
- `KERNEL32!InitializeCriticalSection` at `0x180008e66`
- `KERNEL32!LeaveCriticalSection` at `0x180008c0c`
- `KERNEL32!LeaveCriticalSection` at `0x180008cca`
- `KERNEL32!LeaveCriticalSection` at `0x180008c0c`
- `KERNEL32!LeaveCriticalSection` at `0x180008cca`
- `KERNEL32!EnterCriticalSection` at `0x180008b9a`
- `KERNEL32!EnterCriticalSection` at `0x180008c66`
- `KERNEL32!EnterCriticalSection` at `0x180008b9a`
- `KERNEL32!EnterCriticalSection` at `0x180008c66`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180008b72`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180008b72`

## pseudocode

```c
bool __fastcall InstallLayoutOrTipPrivateHelpers::IsTfCatTip(unsigned __int16 *a1)
{
  _QWORD *v1; // r15
  int v2; // edx
  CVoidStructArray *v3; // rsi
  int v4; // ebp
  int i; // ebx
  int v6; // eax
  __int64 v7; // rdi
  int v8; // ecx
  GUID *v9; // rdx
  GUID v10; // xmm6
  _QWORD *v11; // rsi
  int v12; // edx
  CVoidStructArray *v13; // rdi
  int v14; // r14d
  int j; // ebx
  int v16; // eax
  __int64 v17; // rbp
  int v18; // ecx
  struct _GUID *v19; // rdx
  struct _GUID *v21; // rbx
  unsigned __int16 *v22; // rdx
  GUID *v23; // rbx
  unsigned __int16 *v24; // rdx
  GUID Buf2; // [rsp+20h] [rbp-88h] BYREF
  GUID pclsid; // [rsp+30h] [rbp-78h] BYREF

  pclsid = 0;
  if ( CLSIDFromString(a1, &pclsid) >= 0 )
  {
    v1 = 0;
    if ( !g_fInitCritSec )
    {
      InitializeCriticalSection(&g_csCicCategory);
      g_fInitCritSec = 1;
    }
    EnterCriticalSection(&g_csCicCategory);
    v3 = g_pGuidCatMap;
    if ( !g_pGuidCatMap )
    {
      v3 = (CVoidStructArray *)operator new(0x20u);
      g_pGuidCatMap = v3;
      *((_QWORD *)v3 + 1) = 0;
      *((_DWORD *)v3 + 5) = 24;
      *((_DWORD *)v3 + 4) = 0;
      *((_DWORD *)v3 + 6) = 0;
      *(_QWORD *)v3 = &CStructArray<tag_SKEYBOARDTOINSTALLITEM>::`vftable';
    }
    v4 = *((_DWORD *)v3 + 4);
    for ( i = 0; i < v4; ++i )
    {
      v6 = *((_DWORD *)v3 + 5) * i;
      v7 = *((_QWORD *)v3 + 1) + v6;
      if ( v7 && !memcmp_0((const void *)(*((_QWORD *)v3 + 1) + v6), &GUID_TFCAT_CATEGORY_OF_TIP, 0x10u) )
      {
        v1 = *(_QWORD **)(v7 + 16);
        if ( v1 )
          goto LABEL_12;
        break;
      }
    }
    v23 = (GUID *)CVoidStructArray::Append(v3, v2);
    if ( v23 )
    {
      v1 = operator new(0x28u);
      v1[1] = 0;
      *((_DWORD *)v1 + 5) = 16;
      *((_DWORD *)v1 + 4) = 0;
      *((_DWORD *)v1 + 6) = 0;
      *v1 = &CStructArray<tag_SKEYBOARDTOINSTALLITEM>::`vftable';
      *((_DWORD *)v1 + 8) = 0;
      _InterlockedIncrement((volatile signed __int32 *)&g_lCicCategoryInstanceCount);
      CCicCategory::Init((CCicCategory *)v1, v24, &GUID_TFCAT_CATEGORY_OF_TIP);
      *(_QWORD *)&v23[1].Data1 = v1;
      *v23 = GUID_TFCAT_CATEGORY_OF_TIP;
    }
LABEL_12:
    LeaveCriticalSection(&g_csCicCategory);
    if ( v1 )
    {
      *((_DWORD *)v1 + 8) = 0;
      while ( 1 )
      {
        v8 = *((_DWORD *)v1 + 8);
        if ( *((_DWORD *)v1 + 4) <= v8 )
          break;
        *((_DWORD *)v1 + 8) = v8 + 1;
        v9 = (GUID *)(v1[1] + *((_DWORD *)v1 + 5) * v8);
        if ( !v9 )
          break;
        v10 = *v9;
        v11 = 0;
        Buf2 = *v9;
        if ( !g_fInitCritSec )
        {
          InitializeCriticalSection(&g_csCicCategory);
          g_fInitCritSec = 1;
        }
        EnterCriticalSection(&g_csCicCategory);
        v13 = g_pGuidCatMap;
        if ( !g_pGuidCatMap )
        {
          v13 = (CVoidStructArray *)operator new(0x20u);
          g_pGuidCatMap = v13;
          *((_QWORD *)v13 + 1) = 0;
          *((_DWORD *)v13 + 5) = 24;
          *((_DWORD *)v13 + 4) = 0;
          *((_DWORD *)v13 + 6) = 0;
          *(_QWORD *)v13 = &CStructArray<tag_SKEYBOARDTOINSTALLITEM>::`vftable';
        }
        v14 = *((_DWORD *)v13 + 4);
        for ( j = 0; j < v14; ++j )
        {
          v16 = *((_DWORD *)v13 + 5) * j;
          v17 = *((_QWORD *)v13 + 1) + v16;
          if ( v17 && !memcmp_0((const void *)(*((_QWORD *)v13 + 1) + v16), &Buf2, 0x10u) )
          {
            v11 = *(_QWORD **)(v17 + 16);
            if ( v11 )
              goto LABEL_26;
            break;
          }
        }
        v21 = (struct _GUID *)CVoidStructArray::Append(v13, v12);
        if ( v21 )
        {
          v11 = operator new(0x28u);
          v11[1] = 0;
          *((_DWORD *)v11 + 5) = 16;
          *((_DWORD *)v11 + 4) = 0;
          *((_DWORD *)v11 + 6) = 0;
          *v11 = &CStructArray<tag_SKEYBOARDTOINSTALLITEM>::`vftable';
          *((_DWORD *)v11 + 8) = 0;
          _InterlockedIncrement((volatile signed __int32 *)&g_lCicCategoryInstanceCount);
          CCicCategory::Init((CCicCategory *)v11, v22, &Buf2);
          v10 = Buf2;
          *v21 = Buf2;
          *(_QWORD *)&v21[1].Data1 = v11;
        }
LABEL_26:
        LeaveCriticalSection(&g_csCicCategory);
        if ( v11 )
        {
          *((_DWORD *)v11 + 8) = 0;
          while ( 1 )
          {
            v18 = *((_DWORD *)v11 + 8);
            if ( *((_DWORD *)v11 + 4) <= v18 )
              break;
            *((_DWORD *)v11 + 8) = v18 + 1;
            v19 = (struct _GUID *)(v11[1] + *((_DWORD *)v11 + 5) * v18);
            if ( !v19 )
              break;
            Buf2 = *v19;
            if ( !memcmp_0(&pclsid, &Buf2, 0x10u) )
            {
              pclsid = v10;
              return memcmp_0(&pclsid, &GUID_TFCAT_TIP_KEYBOARD, 0x10u) == 0;
            }
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180008b40  push    rbx
0x180008b42  push    rbp
0x180008b43  push    rsi
0x180008b44  push    rdi
0x180008b45  push    r12
0x180008b47  push    r13
0x180008b49  push    r14
0x180008b4b  push    r15
0x180008b4d  sub     rsp, 68h
0x180008b51  movaps  [rsp+0A8h+var_58], xmm6
0x180008b56  mov     rax, cs:__security_cookie
0x180008b5d  xor     rax, rsp
0x180008b60  mov     [rsp+0A8h+var_68], rax
0x180008b65  xorps   xmm0, xmm0
0x180008b68  lea     rdx, [rsp+0A8h+pclsid]; pclsid
0x180008b6d  movups  xmmword ptr [rsp+0A8h+pclsid.Data1], xmm0
0x180008b72  call    cs:__imp_CLSIDFromString
0x180008b78  test    eax, eax
0x180008b7a  js      loc_180008E58
0x180008b80  xor     r13d, r13d
0x180008b83  cmp     cs:?g_fInitCritSec@@3_NA, r13b; bool g_fInitCritSec
0x180008b8a  mov     r15d, r13d
0x180008b8d  jz      loc_180008E5F
0x180008b93  lea     rcx, ?g_csCicCategory@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180008b9a  call    cs:__imp_EnterCriticalSection
0x180008ba0  mov     rsi, cs:?g_pGuidCatMap@@3PEAV?$CStructArray@Utag_GUIDCATEGORYMAP@@@@EA; CStructArray<tag_GUIDCATEGORYMAP> * g_pGuidCatMap
0x180008ba7  lea     r14, ??_7?$CStructArray@Utag_SKEYBOARDTOINSTALLITEM@@@@6B@; const CStructArray<tag_SKEYBOARDTOINSTALLITEM>::`vftable'
0x180008bae  test    rsi, rsi
0x180008bb1  jz      loc_180008E78
0x180008bb7  mov     ebp, [rsi+10h]
0x180008bba  mov     ebx, r13d
0x180008bbd  cmp     ebx, ebp
0x180008bbf  jge     loc_180008DED
0x180008bc5  mov     eax, ebx
0x180008bc7  imul    eax, [rsi+14h]
0x180008bcb  movsxd  rdi, eax
0x180008bce  add     rdi, [rsi+8]
0x180008bd2  jz      short loc_180008BED
0x180008bd4  mov     r8d, 10h; Size
0x180008bda  lea     rdx, GUID_TFCAT_CATEGORY_OF_TIP; Buf2
0x180008be1  mov     rcx, rdi; Buf1
0x180008be4  call    memcmp_0
0x180008be9  test    eax, eax
0x180008beb  jz      short loc_180008BF1
0x180008bed  inc     ebx
0x180008bef  jmp     short loc_180008BBD
0x180008bf1  mov     r15, [rdi+10h]
0x180008bf5  test    r15, r15
0x180008bf8  jz      loc_180008DED
0x180008bfe  lea     r12, ??_7?$CStructArray@Utag_SKEYBOARDTOINSTALLITEM@@@@6B@; const CStructArray<tag_SKEYBOARDTOINSTALLITEM>::`vftable'
0x180008c05  lea     rcx, ?g_csCicCategory@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180008c0c  call    cs:__imp_LeaveCriticalSection
0x180008c12  test    r15, r15
0x180008c15  jz      loc_180008E58
0x180008c1b  mov     [r15+20h], r13d
0x180008c1f  nop
0x180008c20  mov     ecx, [r15+20h]
0x180008c24  cmp     [r15+10h], ecx
0x180008c28  jle     loc_180008E58
0x180008c2e  lea     eax, [rcx+1]
0x180008c31  mov     [r15+20h], eax
0x180008c35  imul    ecx, [r15+14h]
0x180008c3a  movsxd  rdx, ecx
0x180008c3d  add     rdx, [r15+8]
0x180008c41  jz      loc_180008E58
0x180008c47  movups  xmm6, xmmword ptr [rdx]
0x180008c4a  mov     rsi, r13
0x180008c4d  cmp     cs:?g_fInitCritSec@@3_NA, sil; bool g_fInitCritSec
0x180008c54  movaps  [rsp+0A8h+Buf2], xmm6
0x180008c59  jz      loc_180008DD4
0x180008c5f  lea     rcx, ?g_csCicCategory@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180008c66  call    cs:__imp_EnterCriticalSection
0x180008c6c  mov     rdi, cs:?g_pGuidCatMap@@3PEAV?$CStructArray@Utag_GUIDCATEGORYMAP@@@@EA; CStructArray<tag_GUIDCATEGORYMAP> * g_pGuidCatMap
0x180008c73  test    rdi, rdi
0x180008c76  jz      loc_180008EA7
0x180008c7c  mov     r14d, [rdi+10h]
0x180008c80  mov     ebx, r13d
0x180008c83  cmp     ebx, r14d
0x180008c86  jge     loc_180008D74
0x180008c8c  mov     eax, ebx
0x180008c8e  imul    eax, [rdi+14h]
0x180008c92  movsxd  rbp, eax
0x180008c95  add     rbp, [rdi+8]
0x180008c99  jz      short loc_180008CB2
0x180008c9b  mov     r8d, 10h; Size
0x180008ca1  lea     rdx, [rsp+0A8h+Buf2]; Buf2
0x180008ca6  mov     rcx, rbp; Buf1
0x180008ca9  call    memcmp_0
0x180008cae  test    eax, eax
0x180008cb0  jz      short loc_180008CB6
0x180008cb2  inc     ebx
0x180008cb4  jmp     short loc_180008C83
0x180008cb6  mov     rsi, [rbp+10h]
0x180008cba  test    rsi, rsi
0x180008cbd  jz      loc_180008D74
0x180008cc3  lea     rcx, ?g_csCicCategory@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180008cca  call    cs:__imp_LeaveCriticalSection
0x180008cd0  lea     r14, ??_7?$CStructArray@Utag_SKEYBOARDTOINSTALLITEM@@@@6B@; const CStructArray<tag_SKEYBOARDTOINSTALLITEM>::`vftable'
0x180008cd7  test    rsi, rsi
0x180008cda  jz      loc_180008C20
0x180008ce0  mov     [rsi+20h], r13d
0x180008ce4  mov     ecx, [rsi+20h]
0x180008ce7  lea     r14, ??_7?$CStructArray@Utag_SKEYBOARDTOINSTALLITEM@@@@6B@; const CStructArray<tag_SKEYBOARDTOINSTALLITEM>::`vftable'
0x180008cee  cmp     [rsi+10h], ecx
0x180008cf1  jle     loc_180008C20
0x180008cf7  lea     eax, [rcx+1]
0x180008cfa  mov     [rsi+20h], eax
0x180008cfd  imul    ecx, [rsi+14h]
0x180008d01  movsxd  rdx, ecx
0x180008d04  add     rdx, [rsi+8]
0x180008d08  jz      loc_180008ED6
0x180008d0e  movups  xmm0, xmmword ptr [rdx]
0x180008d11  mov     r8d, 10h; Size
0x180008d17  lea     rdx, [rsp+0A8h+Buf2]; Buf2
0x180008d1c  lea     rcx, [rsp+0A8h+pclsid]; Buf1
0x180008d21  movups  [rsp+0A8h+Buf2], xmm0
0x180008d26  call    memcmp_0
0x180008d2b  test    eax, eax
0x180008d2d  jnz     short loc_180008CE4
0x180008d2f  mov     r8d, 10h; Size
0x180008d35  movdqa  xmmword ptr [rsp+0A8h+pclsid.Data1], xmm6
0x180008d3b  lea     rdx, GUID_TFCAT_TIP_KEYBOARD; Buf2
0x180008d42  lea     rcx, [rsp+0A8h+pclsid]; Buf1
0x180008d47  call    memcmp_0
0x180008d4c  test    eax, eax
0x180008d4e  setz    al
0x180008d51  mov     rcx, [rsp+0A8h+var_68]
0x180008d56  xor     rcx, rsp; StackCookie
0x180008d59  call    __security_check_cookie
0x180008d5e  movaps  xmm6, [rsp+0A8h+var_58]
0x180008d63  add     rsp, 68h
0x180008d67  pop     r15
0x180008d69  pop     r14
0x180008d6b  pop     r13
0x180008d6d  pop     r12
0x180008d6f  pop     rdi
0x180008d70  pop     rsi
0x180008d71  pop     rbp
0x180008d72  pop     rbx
0x180008d73  retn
0x180008d74  mov     rcx, rdi; this
0x180008d77  call    ?Append@CVoidStructArray@@QEAAPEAXH@Z; CVoidStructArray::Append(int)
0x180008d7c  mov     rbx, rax
0x180008d7f  test    rax, rax
0x180008d82  jz      loc_180008CC3
0x180008d88  mov     ecx, 28h ; '('; Size
0x180008d8d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008d92  mov     rsi, rax
0x180008d95  mov     [rax+8], r13
0x180008d99  mov     dword ptr [rax+14h], 10h
0x180008da0  mov     [rax+10h], r13d
0x180008da4  mov     [rax+18h], r13d
0x180008da8  mov     [rax], r12
0x180008dab  mov     [rax+20h], r13d
0x180008daf  lock inc cs:?g_lCicCategoryInstanceCount@@3KC; ulong volatile g_lCicCategoryInstanceCount
0x180008db6  lea     r8, [rsp+0A8h+Buf2]; struct _GUID *
0x180008dbb  mov     rcx, rax; this
0x180008dbe  call    ?Init@CCicCategory@@QEAAXPEAGAEBU_GUID@@@Z; CCicCategory::Init(ushort *,_GUID const &)
0x180008dc3  movaps  xmm6, [rsp+0A8h+Buf2]
0x180008dc8  movups  xmmword ptr [rbx], xmm6
0x180008dcb  mov     [rbx+10h], rsi
0x180008dcf  jmp     loc_180008CC3
0x180008dd4  lea     rcx, ?g_csCicCategory@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180008ddb  call    cs:__imp_InitializeCriticalSection
0x180008de1  mov     cs:?g_fInitCritSec@@3_NA, 1; bool g_fInitCritSec
0x180008de8  jmp     loc_180008C5F
0x180008ded  mov     rcx, rsi; this
0x180008df0  call    ?Append@CVoidStructArray@@QEAAPEAXH@Z; CVoidStructArray::Append(int)
0x180008df5  mov     rbx, rax
0x180008df8  test    rax, rax
0x180008dfb  jz      loc_180008BFE
0x180008e01  mov     ecx, 28h ; '('; Size
0x180008e06  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008e0b  lea     r12, ??_7?$CStructArray@Utag_SKEYBOARDTOINSTALLITEM@@@@6B@; const CStructArray<tag_SKEYBOARDTOINSTALLITEM>::`vftable'
0x180008e12  mov     r15, rax
0x180008e15  mov     [rax+8], r13
0x180008e19  mov     dword ptr [rax+14h], 10h
0x180008e20  mov     [rax+10h], r13d
0x180008e24  mov     [rax+18h], r13d
0x180008e28  mov     [rax], r12
0x180008e2b  mov     [rax+20h], r13d
0x180008e2f  lock inc cs:?g_lCicCategoryInstanceCount@@3KC; ulong volatile g_lCicCategoryInstanceCount
0x180008e36  lea     r8, GUID_TFCAT_CATEGORY_OF_TIP; struct _GUID *
0x180008e3d  mov     rcx, rax; this
0x180008e40  call    ?Init@CCicCategory@@QEAAXPEAGAEBU_GUID@@@Z; CCicCategory::Init(ushort *,_GUID const &)
0x180008e45  movups  xmm0, xmmword ptr cs:GUID_TFCAT_CATEGORY_OF_TIP.Data1
0x180008e4c  mov     [rbx+10h], r15
0x180008e50  movups  xmmword ptr [rbx], xmm0
0x180008e53  jmp     loc_180008C05
0x180008e58  xor     al, al
0x180008e5a  jmp     loc_180008D51
0x180008e5f  lea     rcx, ?g_csCicCategory@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180008e66  call    cs:__imp_InitializeCriticalSection
0x180008e6c  mov     cs:?g_fInitCritSec@@3_NA, 1; bool g_fInitCritSec
0x180008e73  jmp     loc_180008B93
0x180008e78  mov     ecx, 20h ; ' '; Size
0x180008e7d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008e82  mov     rsi, rax
0x180008e85  mov     cs:?g_pGuidCatMap@@3PEAV?$CStructArray@Utag_GUIDCATEGORYMAP@@@@EA, rax; CStructArray<tag_GUIDCATEGORYMAP> * g_pGuidCatMap
0x180008e8c  mov     [rax+8], r13
0x180008e90  mov     dword ptr [rax+14h], 18h
0x180008e97  mov     [rax+10h], r13d
0x180008e9b  mov     [rax+18h], r13d
0x180008e9f  mov     [rax], r14
0x180008ea2  jmp     loc_180008BB7
0x180008ea7  mov     ecx, 20h ; ' '; Size
0x180008eac  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008eb1  mov     rdi, rax
0x180008eb4  mov     cs:?g_pGuidCatMap@@3PEAV?$CStructArray@Utag_GUIDCATEGORYMAP@@@@EA, rax; CStructArray<tag_GUIDCATEGORYMAP> * g_pGuidCatMap
0x180008ebb  mov     [rax+8], r13
0x180008ebf  mov     dword ptr [rax+14h], 18h
0x180008ec6  mov     [rax+10h], r13d
0x180008eca  mov     [rax+18h], r13d
0x180008ece  mov     [rax], r14
0x180008ed1  jmp     loc_180008C7C
0x180008ed6  lea     r14, ??_7?$CStructArray@Utag_SKEYBOARDTOINSTALLITEM@@@@6B@; const CStructArray<tag_SKEYBOARDTOINSTALLITEM>::`vftable'
0x180008edd  jmp     loc_180008C20
```
