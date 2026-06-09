# IEFavResolver::HandleFaviconRequest(ushort const *,ushort const *)

- ea: `0x180018528`
- end: `0x18001875c`
- name: `?HandleFaviconRequest@IEFavResolver@@AEAAJPEBG0@Z`
- size: `564`
- prototype: `int(IEFavResolver *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180019b8c`

## callees

- `0x180002ce0`
- `0x180006cc4`
- `0x18000d17c`
- `0x18001787c`
- `0x180017ba0`
- `0x180017cdc`
- `0x180017e50`
- `0x180018528`

## import_xrefs

- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Reset` at `0x18001866c`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Reset` at `0x18001866c`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Read` at `0x180018688`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Read` at `0x180018688`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Size` at `0x18001861d`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Size` at `0x18001861d`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateStreamOnFileEx` at `0x1800185fa`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateStreamOnFileEx` at `0x1800185fa`
- `edgeIso!__imp_?LCIEPostMessage@@YAJKKKKK@Z` at `0x18001871c`
- `edgeIso!__imp_?LCIEPostMessage@@YAJKKKKK@Z` at `0x18001871c`
- `edgeIso!__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z` at `0x180018657`
- `edgeIso!__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z` at `0x180018657`
- `edgeIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x18001872c`
- `edgeIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x18001872c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IEFavResolver::HandleFaviconRequest(
        IEFavResolver *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4)
{
  IEFavResolver *v7; // rcx
  HRESULT FullPathFromUnifiedPath; // ebx
  IEFavResolver *v9; // rcx
  unsigned int v10; // r9d
  IEFavResolver *v11; // rcx
  int v12; // r9d
  unsigned int v13; // r11d
  unsigned int v14; // r11d
  unsigned int ppstm; // [rsp+28h] [rbp-D8h]
  unsigned int v17; // [rsp+30h] [rbp-D0h] BYREF
  struct _IsoMessage *v18; // [rsp+38h] [rbp-C8h] BYREF
  IStream *pstm; // [rsp+40h] [rbp-C0h] BYREF
  ULARGE_INTEGER pui; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v21[264]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v22[264]; // [rsp+260h] [rbp+160h] BYREF
  WCHAR pszFile[264]; // [rsp+470h] [rbp+370h] BYREF
  unsigned __int16 v24[264]; // [rsp+680h] [rbp+580h] BYREF

  FullPathFromUnifiedPath = IEFavResolver::GetFullPathFromUnifiedPath(this, a3, v22, a4);
  if ( FullPathFromUnifiedPath >= 0 )
  {
    FullPathFromUnifiedPath = IEFavResolver::GetCompleteItemPathFromTitle(v7, v22, a2, 0, v21, ppstm);
    if ( FullPathFromUnifiedPath >= 0 )
    {
      FullPathFromUnifiedPath = IEFavResolver::BuildAlternateStreamFilename(v9, v21, pszFile, v10);
      if ( FullPathFromUnifiedPath >= 0 )
      {
        FullPathFromUnifiedPath = IEFavResolver::GetFavoriteUrl(v11, v21, v24, v12);
        if ( FullPathFromUnifiedPath >= 0 )
        {
          pstm = 0;
          FullPathFromUnifiedPath = SHCreateStreamOnFileEx(pszFile, 0x40u, 0, 0, 0, &pstm);
          if ( FullPathFromUnifiedPath >= 0 )
          {
            pui.QuadPart = 0;
            FullPathFromUnifiedPath = IStream_Size(pstm, &pui);
            if ( FullPathFromUnifiedPath >= 0 )
            {
              v17 = 0;
              v18 = 0;
              FullPathFromUnifiedPath = IsoAllocMessageBuffer(*((_DWORD *)this + 2), &v17, pui.LowPart + 1600, &v18);
              if ( FullPathFromUnifiedPath >= 0 )
              {
                IStream_Reset(pstm);
                FullPathFromUnifiedPath = IStream_Read(pstm, (char *)v18 + 1596, pui.LowPart);
                if ( FullPathFromUnifiedPath < 0
                  || (FullPathFromUnifiedPath = StringCchCopyW((unsigned __int16 *)v18 + 16, 0x104u, a2),
                      FullPathFromUnifiedPath < 0)
                  || (FullPathFromUnifiedPath = StringCchCopyW((unsigned __int16 *)v18 + 276, v13, a3),
                      FullPathFromUnifiedPath < 0)
                  || (FullPathFromUnifiedPath = StringCchCopyW((unsigned __int16 *)v18 + 536, v14, v24),
                      FullPathFromUnifiedPath < 0)
                  || (*((_DWORD *)v18 + 398) = pui.LowPart,
                      FullPathFromUnifiedPath = LCIEPostMessage(
                                                  *((_DWORD *)this + 2),
                                                  *((_DWORD *)this + 1),
                                                  0xDC8u,
                                                  0,
                                                  v17),
                      FullPathFromUnifiedPath < 0) )
                {
                  IsoFreeMessageBuffer(v17);
                }
              }
            }
          }
          ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>((__int64 *)&pstm);
        }
      }
    }
  }
  return (unsigned int)FullPathFromUnifiedPath;
}

```

## disassembly

```asm
0x180018528  push    rbp
0x18001852a  push    rbx
0x18001852b  push    rsi
0x18001852c  push    rdi
0x18001852d  push    r14
0x18001852f  lea     rbp, [rsp-7A0h]
0x180018537  sub     rsp, 8A0h
0x18001853e  mov     rax, cs:__security_cookie
0x180018545  xor     rax, rsp
0x180018548  mov     [rbp+7C0h+var_30], rax
0x18001854f  mov     r14, r8
0x180018552  mov     rsi, rdx
0x180018555  mov     rdi, rcx
0x180018558  lea     r8, [rbp+7C0h+var_660]; unsigned __int16 *
0x18001855f  mov     rdx, r14; unsigned __int16 *
0x180018562  call    ?GetFullPathFromUnifiedPath@IEFavResolver@@AEAAJPEBGPEAGI@Z; IEFavResolver::GetFullPathFromUnifiedPath(ushort const *,ushort *,uint)
0x180018567  mov     ebx, eax
0x180018569  test    eax, eax
0x18001856b  js      loc_18001873D
0x180018571  lea     rax, [rsp+8C0h+var_870]
0x180018576  mov     [rsp+8C0h+pstmTemplate], rax; unsigned __int16 *
0x18001857b  xor     r9d, r9d; bool
0x18001857e  mov     r8, rsi; unsigned __int16 *
0x180018581  lea     rdx, [rbp+7C0h+var_660]; unsigned __int16 *
0x180018588  call    ?GetCompleteItemPathFromTitle@IEFavResolver@@AEAAJPEBG0_NPEAGI@Z; IEFavResolver::GetCompleteItemPathFromTitle(ushort const *,ushort const *,bool,ushort *,uint)
0x18001858d  mov     ebx, eax
0x18001858f  test    eax, eax
0x180018591  js      loc_18001873D
0x180018597  lea     r8, [rbp+7C0h+pszFile]; unsigned __int16 *
0x18001859e  lea     rdx, [rsp+8C0h+var_870]; unsigned __int16 *
0x1800185a3  call    ?BuildAlternateStreamFilename@IEFavResolver@@AEAAJPEBGPEAGK@Z; IEFavResolver::BuildAlternateStreamFilename(ushort const *,ushort *,ulong)
0x1800185a8  mov     ebx, eax
0x1800185aa  test    eax, eax
0x1800185ac  js      loc_18001873D
0x1800185b2  lea     r8, [rbp+7C0h+var_240]; unsigned __int16 *
0x1800185b9  lea     rdx, [rsp+8C0h+var_870]; unsigned __int16 *
0x1800185be  call    ?GetFavoriteUrl@IEFavResolver@@AEAAJPEAG0H@Z; IEFavResolver::GetFavoriteUrl(ushort *,ushort *,int)
0x1800185c3  mov     ebx, eax
0x1800185c5  test    eax, eax
0x1800185c7  js      loc_18001873D
0x1800185cd  mov     [rsp+8C0h+pstm], 0
0x1800185d6  lea     rax, [rsp+8C0h+pstm]
0x1800185db  mov     [rsp+8C0h+ppstm], rax; ppstm
0x1800185e0  mov     [rsp+8C0h+pstmTemplate], 0; pstmTemplate
0x1800185e9  xor     r9d, r9d; fCreate
0x1800185ec  xor     r8d, r8d; dwAttributes
0x1800185ef  lea     edx, [r9+40h]; grfMode
0x1800185f3  lea     rcx, [rbp+7C0h+pszFile]; pszFile
0x1800185fa  call    cs:__imp_SHCreateStreamOnFileEx
0x180018600  mov     ebx, eax
0x180018602  test    eax, eax
0x180018604  js      loc_180018733
0x18001860a  mov     qword ptr [rsp+8C0h+pui], 0
0x180018613  lea     rdx, [rsp+8C0h+pui]; pui
0x180018618  mov     rcx, [rsp+8C0h+pstm]; pstm
0x18001861d  call    cs:__imp_IStream_Size
0x180018623  mov     ebx, eax
0x180018625  test    eax, eax
0x180018627  js      loc_180018733
0x18001862d  mov     [rsp+8C0h+var_890], 0
0x180018635  mov     [rsp+8C0h+var_888], 0
0x18001863e  mov     r8d, dword ptr [rsp+8C0h+pui]
0x180018643  add     r8d, 640h
0x18001864a  lea     r9, [rsp+8C0h+var_888]
0x18001864f  lea     rdx, [rsp+8C0h+var_890]
0x180018654  mov     ecx, [rdi+8]
0x180018657  call    cs:__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z; IsoAllocMessageBuffer(ulong,ulong *,ulong,_IsoMessage * *)
0x18001865d  mov     ebx, eax
0x18001865f  test    eax, eax
0x180018661  js      loc_180018733
0x180018667  mov     rcx, [rsp+8C0h+pstm]; pstm
0x18001866c  call    cs:__imp_IStream_Reset
0x180018672  mov     rdx, [rsp+8C0h+var_888]
0x180018677  add     rdx, 63Ch; pv
0x18001867e  mov     r8d, dword ptr [rsp+8C0h+pui]; cb
0x180018683  mov     rcx, [rsp+8C0h+pstm]; pstm
0x180018688  call    cs:__imp_IStream_Read
0x18001868e  mov     ebx, eax
0x180018690  test    eax, eax
0x180018692  js      loc_180018728
0x180018698  mov     rcx, [rsp+8C0h+var_888]
0x18001869d  add     rcx, 20h ; ' '; unsigned __int16 *
0x1800186a1  mov     r8, rsi; unsigned __int16 *
0x1800186a4  mov     r11d, 104h
0x1800186aa  mov     edx, r11d; unsigned __int64
0x1800186ad  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800186b2  mov     ebx, eax
0x1800186b4  test    eax, eax
0x1800186b6  js      short loc_180018728
0x1800186b8  mov     rcx, [rsp+8C0h+var_888]
0x1800186bd  add     rcx, 228h; unsigned __int16 *
0x1800186c4  mov     r8, r14; unsigned __int16 *
0x1800186c7  mov     edx, r11d; unsigned __int64
0x1800186ca  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800186cf  mov     ebx, eax
0x1800186d1  test    eax, eax
0x1800186d3  js      short loc_180018728
0x1800186d5  mov     rcx, [rsp+8C0h+var_888]
0x1800186da  add     rcx, 430h; unsigned __int16 *
0x1800186e1  lea     r8, [rbp+7C0h+var_240]; unsigned __int16 *
0x1800186e8  mov     edx, r11d; unsigned __int64
0x1800186eb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800186f0  mov     ebx, eax
0x1800186f2  test    eax, eax
0x1800186f4  js      short loc_180018728
0x1800186f6  mov     ecx, dword ptr [rsp+8C0h+pui]
0x1800186fa  mov     rax, [rsp+8C0h+var_888]
0x1800186ff  mov     [rax+638h], ecx
0x180018705  mov     eax, [rsp+8C0h+var_890]
0x180018709  mov     dword ptr [rsp+8C0h+pstmTemplate], eax
0x18001870d  xor     r9d, r9d
0x180018710  mov     r8d, 0DC8h
0x180018716  mov     edx, [rdi+4]
0x180018719  mov     ecx, [rdi+8]
0x18001871c  call    cs:__imp_?LCIEPostMessage@@YAJKKKKK@Z; LCIEPostMessage(ulong,ulong,ulong,ulong,ulong)
0x180018722  mov     ebx, eax
0x180018724  test    eax, eax
0x180018726  jns     short loc_180018733
0x180018728  mov     ecx, [rsp+8C0h+var_890]
0x18001872c  call    cs:__imp_?IsoFreeMessageBuffer@@YAJK@Z; IsoFreeMessageBuffer(ulong)
0x180018732  nop
0x180018733  lea     rcx, [rsp+8C0h+pstm]
0x180018738  call    ??1?$CComPtrBase@UIExtractIconW@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>(void)
0x18001873d  mov     eax, ebx
0x18001873f  mov     rcx, [rbp+7C0h+var_30]
0x180018746  xor     rcx, rsp; StackCookie
0x180018749  call    __security_check_cookie
0x18001874e  add     rsp, 8A0h
0x180018755  pop     r14
0x180018757  pop     rdi
0x180018758  pop     rsi
0x180018759  pop     rbx
0x18001875a  pop     rbp
0x18001875b  retn
```
