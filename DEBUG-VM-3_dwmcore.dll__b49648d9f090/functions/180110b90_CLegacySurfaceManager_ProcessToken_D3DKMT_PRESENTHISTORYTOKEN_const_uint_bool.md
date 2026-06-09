# CLegacySurfaceManager::ProcessToken(_D3DKMT_PRESENTHISTORYTOKEN const *,uint *,bool *)

- ea: `0x180110b90`
- end: `0x180110f68`
- name: `?ProcessToken@CLegacySurfaceManager@@IEAAJPEBU_D3DKMT_PRESENTHISTORYTOKEN@@PEAIPEA_N@Z`
- size: `984`
- prototype: `__int64 __fastcall(CLegacySurfaceManager *__hidden this, const struct _D3DKMT_PRESENTHISTORYTOKEN *, unsigned int *, bool *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18010fd50`

## callees

- `0x180028e40`
- `0x18002ba60`
- `0x18002d3b0`
- `0x18002d640`
- `0x180042de0`
- `0x180110b90`
- `0x1801a68d8`
- `0x1801c0688`
- `0x1801c0c40`
- `0x1801ca9f0`
- `0x180200448`
- `0x180228490`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180110d09`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180110d09`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180110d17`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180110d17`
- `ntdll!RtlLookupElementGenericTable` at `0x180110d5d`
- `ntdll!RtlLookupElementGenericTable` at `0x180110e39`
- `ntdll!RtlLookupElementGenericTable` at `0x180110d5d`
- `ntdll!RtlLookupElementGenericTable` at `0x180110e39`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180110ea4`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180110ea4`

## string_xrefs

- `0x180110dac`: `onecoreuap\windows\DWM\common\shared\Region.h`
- `0x180110dc9`: `onecoreuap\windows\DWM\common\shared\Region.h`

## pseudocode

```c
__int64 __fastcall CLegacySurfaceManager::ProcessToken(
        CLegacySurfaceManager *this,
        const struct _D3DKMT_PRESENTHISTORYTOKEN *a2,
        unsigned int *a3,
        bool *a4)
{
  unsigned int v4; // ebp
  int v6; // ecx
  const struct _D3DKMT_PRESENTHISTORYTOKEN *v8; // rdi
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  unsigned __int64 *v12; // r15
  _QWORD *v13; // rax
  _QWORD *v14; // rbx
  int v15; // eax
  __int64 v16; // rax
  int v17; // r9d
  int v18; // r10d
  int v19; // ecx
  int v20; // edx
  int v21; // r8d
  int v22; // eax
  int v23; // eax
  void *v24; // rdi
  HANDLE ProcessHeap; // rax
  _QWORD *v27; // rcx
  PVOID v28; // rax
  CGdiSpriteBitmap *v29; // rbx
  int v30; // eax
  _QWORD *v31; // rax
  CGdiSpriteBitmap *v32; // rbx
  unsigned __int64 v33; // rdx
  CRedirectedGDISurface *v34; // rcx
  int v35; // eax
  int v36; // [rsp+20h] [rbp-D8h]
  HGDIOBJ ho; // [rsp+40h] [rbp-B8h] BYREF
  __int64 Buffer; // [rsp+48h] [rbp-B0h] BYREF
  __int128 v39; // [rsp+50h] [rbp-A8h]
  LPVOID lpMem; // [rsp+60h] [rbp-98h] BYREF
  _DWORD v41[18]; // [rsp+68h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v4 = 0;
  lpMem = v41;
  *a4 = 0;
  v6 = *(_DWORD *)a2;
  v41[0] = 0;
  v8 = a2;
  if ( v6 == 5 )
  {
    v27 = (_QWORD *)*((_QWORD *)this + 26);
    LOBYTE(a2) = 0;
    if ( v27 && v27[7] == *((_QWORD *)v8 + 2) && *((_BYTE *)this + 220) )
    {
      (*(void (__fastcall **)(_QWORD *, const struct _D3DKMT_PRESENTHISTORYTOKEN *, unsigned int *))(*v27 + 40LL))(
        v27,
        a2,
        a3);
      LOBYTE(a2) = 1;
      *((_BYTE *)this + 220) = 0;
    }
    *a4 = (char)a2;
    goto LABEL_23;
  }
  v9 = v6 - 1;
  if ( v9 )
  {
    v10 = v9 - 1;
    if ( !v10 )
      goto LABEL_47;
    v11 = v10 - 1;
    if ( !v11 )
    {
      v12 = (unsigned __int64 *)((char *)a2 + 32);
      if ( (Microsoft_Windows_Dwm_CoreEnableBits & 2) != 0 )
        McTemplateU0xxxqNR3_EventWriteTransfer(
          0,
          (_DWORD)a2,
          *((_QWORD *)a2 + 2),
          *((_QWORD *)a2 + 3),
          *v12,
          *((_DWORD *)a2 + 10));
      v13 = (_QWORD *)*((_QWORD *)this + 11);
      while ( v13 != (_QWORD *)((char *)this + 80) )
      {
        v14 = v13 - 20;
        v13 = (_QWORD *)v13[1];
        if ( v14[52] == *((_QWORD *)v8 + 3) )
        {
          v15 = CRegion::TryAddRectangles(
                  (CRegion *)&lpMem,
                  (const struct tagRECT *)((char *)v8 + 44),
                  *((_DWORD *)v8 + 10));
          if ( v15 < 0 )
            wil::details::in1diag3::FailFast_Hr(
              retaddr,
              (void *)0x1D1,
              (unsigned int)"onecoreuap\\windows\\DWM\\common\\shared\\Region.h",
              (const char *)(unsigned int)v15,
              v36);
          v16 = *(int *)lpMem;
          if ( (_DWORD)v16 )
          {
            v17 = *((_DWORD *)lpMem + 2 * v16 + 1);
            v18 = -1;
            v19 = -1;
            v20 = *((_DWORD *)lpMem + 3);
            v21 = *((_DWORD *)lpMem + 2);
            if ( *((int *)lpMem + 1) >= 0 )
              v19 = *((_DWORD *)lpMem + 1);
            *((_DWORD *)v14 + 86) = v19;
            v22 = -1;
            if ( v20 >= 0 )
              v22 = v20;
            *((_DWORD *)v14 + 87) = v22;
            v23 = -1;
            if ( v21 >= 0 )
              v23 = v21;
            *((_DWORD *)v14 + 88) = v23;
            if ( v17 >= 0 )
              v18 = v17;
            *((_DWORD *)v14 + 89) = v18;
            CGdiSpriteBitmap::AddDirtyRegion((CGdiSpriteBitmap *)v14, (struct CRegion *)&lpMem, 1);
          }
          break;
        }
      }
      if ( *v12 )
      {
        v35 = CLegacySurfaceManager::AddIntervalOneDxBltEventId(this, *v12);
        v4 = v35;
        if ( v35 < 0 )
        {
          MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v35, 0xB7u, 0);
          goto LABEL_23;
        }
      }
      goto LABEL_22;
    }
    if ( v11 != 3 )
    {
LABEL_47:
      *a4 = 1;
      return v4;
    }
    if ( (Microsoft_Windows_Dwm_CoreEnableBits & 2) != 0 )
      McTemplateU0xxq_EventWriteTransfer(
        3,
        (unsigned int)"X",
        *((_QWORD *)a2 + 2),
        *((_QWORD *)a2 + 4),
        *((_DWORD *)a2 + 6));
    Buffer = *((_QWORD *)v8 + 2);
    v39 = 0;
    v31 = RtlLookupElementGenericTable((PRTL_GENERIC_TABLE)((char *)this + 8), &Buffer);
    if ( v31 )
    {
      v32 = (CGdiSpriteBitmap *)v31[2];
      if ( v32 )
      {
        v33 = *((_QWORD *)v8 + 4);
        v34 = (CRedirectedGDISurface *)*((_QWORD *)v32 + 16);
        ho = 0;
        if ( (int)CRedirectedGDISurface::GetDirtyRegion(v34, v33, (HRGN *)&ho) >= 0 )
        {
          if ( ho )
          {
            CRegion::SetHRGN((CRegion *)&lpMem, (HRGN)ho);
            CGdiSpriteBitmap::AddDirtyRegion(v32, (struct CRegion *)&lpMem, 1);
            DeleteObject(ho);
            *a4 = 1;
            goto LABEL_23;
          }
        }
      }
    }
  }
  else
  {
    if ( (Microsoft_Windows_Dwm_CoreEnableBits & 2) != 0 )
      McTemplateU0xxqNR2_EventWriteTransfer(
        0,
        (_DWORD)a2,
        *((_QWORD *)a2 + 2),
        *((_QWORD *)a2 + 3),
        *((_DWORD *)a2 + 14));
    Buffer = *((_QWORD *)v8 + 2);
    v39 = 0;
    v28 = RtlLookupElementGenericTable((PRTL_GENERIC_TABLE)((char *)this + 8), &Buffer);
    if ( v28 )
    {
      v29 = (CGdiSpriteBitmap *)*((_QWORD *)v28 + 2);
      if ( v29 )
      {
        v30 = CRegion::TryAddRectangles(
                (CRegion *)&lpMem,
                (const struct tagRECT *)((char *)v8 + 60),
                *((_DWORD *)v8 + 14));
        if ( v30 < 0 )
          wil::details::in1diag3::FailFast_Hr(
            retaddr,
            (void *)0x1D1,
            (unsigned int)"onecoreuap\\windows\\DWM\\common\\shared\\Region.h",
            (const char *)(unsigned int)v30,
            v36);
        CGdiSpriteBitmap::AddDirtyRegion(v29, (struct CRegion *)&lpMem, 1);
      }
    }
  }
LABEL_22:
  *a4 = 1;
LABEL_23:
  v24 = lpMem;
  if ( v41 != lpMem && lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
  }
  return v4;
}

```

## disassembly

```asm
0x180110b90  push    rbx
0x180110b92  push    rbp
0x180110b93  push    rsi
0x180110b94  push    rdi
0x180110b95  push    r12
0x180110b97  push    r14
0x180110b99  push    r15
0x180110b9b  sub     rsp, 0C0h
0x180110ba2  mov     rax, cs:__security_cookie
0x180110ba9  xor     rax, rsp
0x180110bac  mov     [rsp+0F8h+var_48], rax
0x180110bb4  xor     r12d, r12d
0x180110bb7  lea     rax, [rsp+0F8h+var_90]
0x180110bbc  mov     ebp, r12d
0x180110bbf  mov     [rsp+0F8h+lpMem], rax
0x180110bc4  mov     [r9], bpl
0x180110bc7  mov     r14, rcx
0x180110bca  mov     ecx, [rdx]
0x180110bcc  mov     rsi, r9
0x180110bcf  mov     [rsp+0F8h+var_90], r12d
0x180110bd4  mov     rdi, rdx
0x180110bd7  cmp     ecx, 5
0x180110bda  jz      loc_180110D1F
0x180110be0  sub     ecx, 1
0x180110be3  jz      loc_180110D35
0x180110be9  sub     ecx, 1
0x180110bec  jz      loc_180110F2A
0x180110bf2  sub     ecx, 1
0x180110bf5  jnz     loc_180110E08
0x180110bfb  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits, 2
0x180110c02  lea     r15, [rdx+20h]
0x180110c06  jnz     loc_180110DDE
0x180110c0c  mov     rdx, [rdi+18h]
0x180110c10  lea     rcx, [r14+50h]
0x180110c14  mov     rax, [r14+58h]
0x180110c18  nop     dword ptr [rax+rax+00000000h]
0x180110c20  cmp     rax, rcx
0x180110c23  jz      loc_180110CC2
0x180110c29  lea     rbx, [rax-0A0h]
0x180110c30  mov     rax, [rax+8]
0x180110c34  cmp     [rbx+1A0h], rdx
0x180110c3b  jnz     short loc_180110C20
0x180110c3d  mov     r8d, [rdi+28h]; unsigned int
0x180110c41  lea     rdx, [rdi+2Ch]; struct tagRECT *
0x180110c45  lea     rcx, [rsp+0F8h+lpMem]; this
0x180110c4a  call    ?TryAddRectangles@CRegion@@QEAAJPEBUtagRECT@@I@Z; CRegion::TryAddRectangles(tagRECT const *,uint)
0x180110c4f  test    eax, eax
0x180110c51  js      loc_180110DA4
0x180110c57  mov     rdi, [rsp+0F8h+lpMem]
0x180110c5c  movsxd  rax, dword ptr [rdi]
0x180110c5f  test    eax, eax
0x180110c61  jz      short loc_180110CC2
0x180110c63  mov     r9d, [rdi+rax*8+4]
0x180110c68  mov     r10d, 0FFFFFFFFh
0x180110c6e  mov     eax, [rdi+4]
0x180110c71  mov     ecx, r10d
0x180110c74  mov     edx, [rdi+0Ch]
0x180110c77  test    eax, eax
0x180110c79  mov     r8d, [rdi+8]
0x180110c7d  cmovns  ecx, eax
0x180110c80  test    edx, edx
0x180110c82  mov     [rbx+158h], ecx
0x180110c88  mov     eax, r10d
0x180110c8b  cmovns  eax, edx
0x180110c8e  mov     rcx, rbx; this
0x180110c91  mov     [rbx+15Ch], eax
0x180110c97  lea     rdx, [rsp+0F8h+lpMem]; struct CRegion *
0x180110c9c  test    r8d, r8d
0x180110c9f  mov     eax, r10d
0x180110ca2  cmovns  eax, r8d
0x180110ca6  test    r9d, r9d
0x180110ca9  mov     [rbx+160h], eax
0x180110caf  mov     r8b, 1; bool
0x180110cb2  cmovns  r10d, r9d
0x180110cb6  mov     [rbx+164h], r10d
0x180110cbd  call    ?AddDirtyRegion@CGdiSpriteBitmap@@AEAAXAEAVCRegion@@_N@Z; CGdiSpriteBitmap::AddDirtyRegion(CRegion &,bool)
0x180110cc2  mov     rdx, [r15]; unsigned __int64
0x180110cc5  test    rdx, rdx
0x180110cc8  jnz     loc_180110EB2
0x180110cce  mov     byte ptr [rsi], 1
0x180110cd1  mov     rdi, [rsp+0F8h+lpMem]
0x180110cd6  lea     rax, [rsp+0F8h+var_90]
0x180110cdb  cmp     rax, rdi
0x180110cde  jz      short loc_180110CE5
0x180110ce0  test    rdi, rdi
0x180110ce3  jnz     short loc_180110D09
0x180110ce5  mov     eax, ebp
0x180110ce7  mov     rcx, [rsp+0F8h+var_48]
0x180110cef  xor     rcx, rsp; StackCookie
0x180110cf2  call    __security_check_cookie
0x180110cf7  add     rsp, 0C0h
0x180110cfe  pop     r15
0x180110d00  pop     r14
0x180110d02  pop     r12
0x180110d04  pop     rdi
0x180110d05  pop     rsi
0x180110d06  pop     rbp
0x180110d07  pop     rbx
0x180110d08  retn
0x180110d09  call    cs:__imp_GetProcessHeap
0x180110d0f  mov     r8, rdi; lpMem
0x180110d12  xor     edx, edx; dwFlags
0x180110d14  mov     rcx, rax; hHeap
0x180110d17  call    cs:__imp_HeapFree
0x180110d1d  jmp     short loc_180110CE5
0x180110d1f  mov     rcx, [r14+0D0h]
0x180110d26  xor     dl, dl
0x180110d28  test    rcx, rcx
0x180110d2b  jnz     loc_180110F33
0x180110d31  mov     [rsi], dl
0x180110d33  jmp     short loc_180110CD1
0x180110d35  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits, 2
0x180110d3c  jnz     loc_180110EE8
0x180110d42  mov     rax, [rdi+10h]
0x180110d46  lea     rcx, [r14+8]; Table
0x180110d4a  xorps   xmm0, xmm0
0x180110d4d  mov     [rsp+0F8h+Buffer], rax
0x180110d52  lea     rdx, [rsp+0F8h+Buffer]; Buffer
0x180110d57  movdqu  [rsp+0F8h+var_A8], xmm0
0x180110d5d  call    cs:__imp_RtlLookupElementGenericTable
0x180110d63  test    rax, rax
0x180110d66  jz      loc_180110CCE
0x180110d6c  mov     rbx, [rax+10h]
0x180110d70  test    rbx, rbx
0x180110d73  jz      loc_180110CCE
0x180110d79  mov     r8d, [rdi+38h]; unsigned int
0x180110d7d  lea     rdx, [rdi+3Ch]; struct tagRECT *
0x180110d81  lea     rcx, [rsp+0F8h+lpMem]; this
0x180110d86  call    ?TryAddRectangles@CRegion@@QEAAJPEBUtagRECT@@I@Z; CRegion::TryAddRectangles(tagRECT const *,uint)
0x180110d8b  test    eax, eax
0x180110d8d  js      short loc_180110DC1
0x180110d8f  mov     r8b, 1; bool
0x180110d92  lea     rdx, [rsp+0F8h+lpMem]; struct CRegion *
0x180110d97  mov     rcx, rbx; this
0x180110d9a  call    ?AddDirtyRegion@CGdiSpriteBitmap@@AEAAXAEAVCRegion@@_N@Z; CGdiSpriteBitmap::AddDirtyRegion(CRegion &,bool)
0x180110d9f  jmp     loc_180110CCE
0x180110da4  mov     rcx, [rsp+0F8h]; this
0x180110dac  lea     r8, aOnecoreuapWind_215; "onecoreuap\\windows\\DWM\\common\\share"...
0x180110db3  mov     r9d, eax; char *
0x180110db6  mov     edx, 1D1h; void *
0x180110dbb  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180110dc1  mov     rcx, [rsp+0F8h]; this
0x180110dc9  lea     r8, aOnecoreuapWind_215; "onecoreuap\\windows\\DWM\\common\\share"...
0x180110dd0  mov     r9d, eax; char *
0x180110dd3  mov     edx, 1D1h; void *
0x180110dd8  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180110dde  mov     r9, [rdx+18h]
0x180110de2  lea     rax, [rdx+2Ch]
0x180110de6  mov     r8, [rdx+10h]
0x180110dea  mov     [rsp+0F8h+var_C0], rax
0x180110def  mov     eax, [rdx+28h]
0x180110df2  mov     dword ptr [rsp+0F8h+var_D0], eax
0x180110df6  mov     rax, [r15]
0x180110df9  mov     qword ptr [rsp+0F8h+var_D8], rax
0x180110dfe  call    McTemplateU0xxxqNR3_EventWriteTransfer
0x180110e03  jmp     loc_180110C0C
0x180110e08  cmp     ecx, 3
0x180110e0b  jnz     loc_180110F2A
0x180110e11  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits, 2
0x180110e18  jnz     loc_180110F0A
0x180110e1e  mov     rax, [rdi+10h]
0x180110e22  lea     rcx, [r14+8]; Table
0x180110e26  xorps   xmm0, xmm0
0x180110e29  mov     [rsp+0F8h+Buffer], rax
0x180110e2e  lea     rdx, [rsp+0F8h+Buffer]; Buffer
0x180110e33  movdqu  [rsp+0F8h+var_A8], xmm0
0x180110e39  call    cs:__imp_RtlLookupElementGenericTable
0x180110e3f  test    rax, rax
0x180110e42  jz      loc_180110CCE
0x180110e48  mov     rbx, [rax+10h]
0x180110e4c  test    rbx, rbx
0x180110e4f  jz      loc_180110CCE
0x180110e55  mov     rdx, [rdi+20h]; unsigned __int64
0x180110e59  lea     r8, [rsp+0F8h+ho]; HRGN *
0x180110e5e  mov     rcx, [rbx+80h]; this
0x180110e65  mov     [rsp+0F8h+ho], r12
0x180110e6a  call    ?GetDirtyRegion@CRedirectedGDISurface@@QEAAJ_KPEAPEAUHRGN__@@@Z; CRedirectedGDISurface::GetDirtyRegion(unsigned __int64,HRGN__ * *)
0x180110e6f  test    eax, eax
0x180110e71  js      loc_180110CCE
0x180110e77  mov     rdx, [rsp+0F8h+ho]; hrgn
0x180110e7c  test    rdx, rdx
0x180110e7f  jz      loc_180110CCE
0x180110e85  lea     rcx, [rsp+0F8h+lpMem]; this
0x180110e8a  call    ?SetHRGN@CRegion@@QEAAXQEAUHRGN__@@@Z; CRegion::SetHRGN(HRGN__ * const)
0x180110e8f  mov     r8b, 1; bool
0x180110e92  lea     rdx, [rsp+0F8h+lpMem]; struct CRegion *
0x180110e97  mov     rcx, rbx; this
0x180110e9a  call    ?AddDirtyRegion@CGdiSpriteBitmap@@AEAAXAEAVCRegion@@_N@Z; CGdiSpriteBitmap::AddDirtyRegion(CRegion &,bool)
0x180110e9f  mov     rcx, [rsp+0F8h+ho]; ho
0x180110ea4  call    cs:__imp_DeleteObject
0x180110eaa  mov     byte ptr [rsi], 1
0x180110ead  jmp     loc_180110CD1
0x180110eb2  mov     rcx, r14; this
0x180110eb5  call    ?AddIntervalOneDxBltEventId@CLegacySurfaceManager@@QEAAJ_K@Z; CLegacySurfaceManager::AddIntervalOneDxBltEventId(unsigned __int64)
0x180110eba  mov     ebp, eax
0x180110ebc  test    eax, eax
0x180110ebe  jns     loc_180110CCE
0x180110ec4  mov     [rsp+0F8h+var_D0], r12; void *
0x180110ec9  mov     r9d, eax; int
0x180110ecc  xor     r8d, r8d; unsigned int
0x180110ecf  mov     [rsp+0F8h+var_D8], 0B7h; unsigned int
0x180110ed7  xor     edx, edx; int *
0x180110ed9  mov     ecx, 14h; unsigned int
0x180110ede  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180110ee3  jmp     loc_180110CD1
0x180110ee8  mov     r9, [rdx+18h]
0x180110eec  lea     rax, [rdx+3Ch]
0x180110ef0  mov     r8, [rdx+10h]
0x180110ef4  mov     [rsp+0F8h+var_C8], rax
0x180110ef9  mov     eax, [rdx+38h]
0x180110efc  mov     [rsp+0F8h+var_D8], eax
0x180110f00  call    McTemplateU0xxqNR2_EventWriteTransfer
0x180110f05  jmp     loc_180110D42
0x180110f0a  mov     eax, [rdx+18h]
0x180110f0d  mov     r9, [rdx+20h]
0x180110f11  mov     r8, [rdx+10h]
0x180110f15  lea     rdx, EVTDESC_SCHEDULE_PRESENTHISTORYTOKEN_GDISYSMEM; "X"
0x180110f1c  mov     [rsp+0F8h+var_D8], eax
0x180110f20  call    McTemplateU0xxq_EventWriteTransfer
0x180110f25  jmp     loc_180110E1E
0x180110f2a  mov     byte ptr [r9], 1
0x180110f2e  jmp     loc_180110CE5
0x180110f33  mov     rax, [rdi+10h]
0x180110f37  cmp     [rcx+38h], rax
0x180110f3b  jnz     loc_180110D31
0x180110f41  cmp     [r14+0DCh], dl
0x180110f48  jz      loc_180110D31
0x180110f4e  mov     rax, [rcx]
0x180110f51  mov     rax, [rax+28h]
0x180110f55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180110f5a  mov     dl, 1
0x180110f5c  mov     [r14+0DCh], bpl
0x180110f63  jmp     loc_180110D31
```
