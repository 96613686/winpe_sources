# ClearCompressor::Initialize(void)

- ea: `0x180175980`
- end: `0x180175cc0`
- name: `?Initialize@ClearCompressor@@EEAAJXZ`
- size: `832`
- prototype: `__int64 __fastcall(ClearCompressor *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1801756e8`

## callees

- `0x18003aa1c`
- `0x180076090`
- `0x180079724`
- `0x18007cf90`
- `0x1800e46a4`
- `0x1801758d0`
- `0x180175980`

## import_xrefs

- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1801759b9`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180175a2f`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180175a79`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180175afb`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180175b5a`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180175bb6`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180175c15`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180175c5d`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1801759b9`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180175a2f`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180175a79`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180175afb`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180175b5a`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180175bb6`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180175c15`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180175c5d`
- `RDPBASE!?CreateInstance@NSCodecCompressor@@SA_N_N00EAEAV?$TCntPtr@VNSCodecCompressor@@@@@Z` at `0x180175a06`
- `RDPBASE!?CreateInstance@NSCodecCompressor@@SA_N_N00EAEAV?$TCntPtr@VNSCodecCompressor@@@@@Z` at `0x180175a06`

## string_xrefs

- `0x180175a84`: `RgnlibBA_CreateInstance failed`
- `0x180175b06`: `m_cacheTable.Initialize failed`
- `0x180175c20`: `nonCommitCacheTable.Initialize failed`
- `0x180175b65`: `m_shortCacheTable.Initialize failed`
- `0x180175bc1`: `m_glyphCacheTable.Initialize failed`

## pseudocode

```c
__int64 __fastcall ClearCompressor::Initialize(ClearCompressor *this)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // r9
  unsigned int ActivityIdPrefix; // eax
  __int64 v6; // rdx
  int Instance; // edi
  __int64 v8; // rdx
  __int64 v9; // rdx
  int v10; // eax
  int v11; // edx
  const char *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rdx

  if ( !(unsigned __int8)FixedList<HBand>::Initialize((char *)this + 40) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147024882;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v2);
    v6 = 13;
LABEL_6:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v6,
      WPP_3a5e1219709437e9e7ce4c056be78b35_Traceguids,
      ActivityIdPrefix,
      -2147024882);
    return (unsigned int)-2147024882;
  }
  LOBYTE(v4) = 3;
  LOBYTE(v3) = 1;
  if ( !(unsigned __int8)NSCodecCompressor::CreateInstance(v3, 0, 0, v4, (char *)this + 24072) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147024882;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v8);
    v6 = 14;
    goto LABEL_6;
  }
  Instance = RgnlibBA_CreateInstance((char *)this + 24080);
  if ( Instance >= 0 )
  {
    Instance = Remap<unsigned __int64>::Initialize((char *)this + 24088, 0x8000, 0x10000);
    if ( Instance >= 0 )
    {
      Instance = Remap<unsigned __int64>::Initialize((char *)this + 24128, 0x4000, 0x8000);
      if ( Instance >= 0 )
      {
        Instance = Remap<unsigned __int64>::Initialize((char *)this + 24208, 4000, 4000);
        if ( Instance >= 0 )
        {
          Instance = Remap<unsigned __int64>::Initialize((char *)this + 24168, 1000, 2000);
          if ( Instance >= 0 )
          {
            Instance = Remap<unsigned int>::Initialize((char *)this + 24248);
            if ( Instance >= 0 )
            {
              *((_DWORD *)this + 6016) = 0;
              *((_WORD *)this + 12144) = 0;
              *(_QWORD *)((char *)this + 24292) = 0;
              *(_QWORD *)((char *)this + 24300) = 0;
              *(_QWORD *)((char *)this + 24308) = 0;
              *(_QWORD *)((char *)this + 24316) = 0;
              return (unsigned int)Instance;
            }
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v10 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v17);
              v11 = 22;
              v12 = "m_subCodecPalette.Initialize failed";
              goto LABEL_18;
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v10 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v16);
            v11 = 21;
            v12 = "nonCommitCacheTable.Initialize failed";
            goto LABEL_18;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v10 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v15);
          v11 = 20;
          v12 = "m_glyphCacheTable.Initialize failed";
          goto LABEL_18;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v10 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v14);
        v11 = 19;
        v12 = "m_shortCacheTable.Initialize failed";
        goto LABEL_18;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v13);
      v11 = 18;
      v12 = "m_cacheTable.Initialize failed";
      goto LABEL_18;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v10 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v9);
    v11 = 15;
    v12 = "RgnlibBA_CreateInstance failed";
LABEL_18:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      (unsigned int)WPP_3a5e1219709437e9e7ce4c056be78b35_Traceguids,
      v10,
      (__int64)v12,
      Instance);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180175980  mov     [rsp+arg_0], rbx
0x180175985  push    rdi
0x180175986  sub     rsp, 30h
0x18017598a  mov     rbx, rcx
0x18017598d  add     rcx, 28h ; '('
0x180175991  call    ?Initialize@?$FixedList@UHBand@@@@QEAA_NH@Z; FixedList<HBand>::Initialize(int)
0x180175996  test    al, al
0x180175998  jnz     short loc_1801759F0
0x18017599a  mov     rcx, cs:WPP_GLOBAL_Control
0x1801759a1  lea     rax, WPP_GLOBAL_Control
0x1801759a8  cmp     rcx, rax
0x1801759ab  jz      short loc_1801759E6
0x1801759ad  test    byte ptr [rcx+1Ch], 8
0x1801759b1  jz      short loc_1801759E6
0x1801759b3  cmp     byte ptr [rcx+19h], 2
0x1801759b7  jb      short loc_1801759E6
0x1801759b9  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1801759bf  mov     edx, 0Dh
0x1801759c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1801759cb  lea     r8, WPP_3a5e1219709437e9e7ce4c056be78b35_Traceguids
0x1801759d2  mov     r9d, eax
0x1801759d5  mov     dword ptr [rsp+38h+var_18], 8007000Eh
0x1801759dd  mov     rcx, [rcx+10h]
0x1801759e1  call    WPP_SF_Dd
0x1801759e6  mov     edi, 8007000Eh
0x1801759eb  jmp     loc_180175CB3
0x1801759f0  lea     rax, [rbx+5E08h]
0x1801759f7  mov     r9b, 3
0x1801759fa  xor     r8d, r8d
0x1801759fd  mov     [rsp+38h+var_18], rax
0x180175a02  xor     edx, edx
0x180175a04  mov     cl, 1
0x180175a06  call    cs:__imp_?CreateInstance@NSCodecCompressor@@SA_N_N00EAEAV?$TCntPtr@VNSCodecCompressor@@@@@Z; NSCodecCompressor::CreateInstance(bool,bool,bool,uchar,TCntPtr<NSCodecCompressor> &)
0x180175a0c  test    al, al
0x180175a0e  jnz     short loc_180175A3C
0x180175a10  mov     rcx, cs:WPP_GLOBAL_Control
0x180175a17  lea     rax, WPP_GLOBAL_Control
0x180175a1e  cmp     rcx, rax
0x180175a21  jz      short loc_1801759E6
0x180175a23  test    byte ptr [rcx+1Ch], 8
0x180175a27  jz      short loc_1801759E6
0x180175a29  cmp     byte ptr [rcx+19h], 2
0x180175a2d  jb      short loc_1801759E6
0x180175a2f  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180175a35  mov     edx, 0Eh
0x180175a3a  jmp     short loc_1801759C4
0x180175a3c  lea     rcx, [rbx+5E10h]
0x180175a43  call    RgnlibBA_CreateInstance
0x180175a48  mov     edi, eax
0x180175a4a  test    eax, eax
0x180175a4c  jns     short loc_180175AB3
0x180175a4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180175a55  lea     rax, WPP_GLOBAL_Control
0x180175a5c  cmp     rcx, rax
0x180175a5f  jz      loc_180175CB3
0x180175a65  test    byte ptr [rcx+1Ch], 8
0x180175a69  jz      loc_180175CB3
0x180175a6f  cmp     byte ptr [rcx+19h], 2
0x180175a73  jb      loc_180175CB3
0x180175a79  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180175a7f  mov     edx, 0Fh
0x180175a84  lea     rcx, aRgnlibbaCreate; "RgnlibBA_CreateInstance failed"
0x180175a8b  mov     [rsp+38h+var_10], edi
0x180175a8f  lea     r8, WPP_3a5e1219709437e9e7ce4c056be78b35_Traceguids
0x180175a96  mov     [rsp+38h+var_18], rcx
0x180175a9b  mov     r9d, eax
0x180175a9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180175aa5  mov     rcx, [rcx+10h]
0x180175aa9  call    WPP_SF_DsD
0x180175aae  jmp     loc_180175CB3
0x180175ab3  lea     rcx, [rbx+5E18h]
0x180175aba  mov     edx, 8000h
0x180175abf  mov     r8d, 10000h
0x180175ac5  call    ?Initialize@?$Remap@_K@@QEAAJHH@Z; Remap<unsigned __int64>::Initialize(int,int)
0x180175aca  mov     edi, eax
0x180175acc  test    eax, eax
0x180175ace  jns     short loc_180175B12
0x180175ad0  mov     rcx, cs:WPP_GLOBAL_Control
0x180175ad7  lea     rax, WPP_GLOBAL_Control
0x180175ade  cmp     rcx, rax
0x180175ae1  jz      loc_180175CB3
0x180175ae7  test    byte ptr [rcx+1Ch], 8
0x180175aeb  jz      loc_180175CB3
0x180175af1  cmp     byte ptr [rcx+19h], 2
0x180175af5  jb      loc_180175CB3
0x180175afb  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180175b01  mov     edx, 12h
0x180175b06  lea     rcx, aMCachetableIni; "m_cacheTable.Initialize failed"
0x180175b0d  jmp     loc_180175A8B
0x180175b12  lea     rcx, [rbx+5E40h]
0x180175b19  mov     edx, 4000h
0x180175b1e  mov     r8d, 8000h
0x180175b24  call    ?Initialize@?$Remap@_K@@QEAAJHH@Z; Remap<unsigned __int64>::Initialize(int,int)
0x180175b29  mov     edi, eax
0x180175b2b  test    eax, eax
0x180175b2d  jns     short loc_180175B71
0x180175b2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180175b36  lea     rax, WPP_GLOBAL_Control
0x180175b3d  cmp     rcx, rax
0x180175b40  jz      loc_180175CB3
0x180175b46  test    byte ptr [rcx+1Ch], 8
0x180175b4a  jz      loc_180175CB3
0x180175b50  cmp     byte ptr [rcx+19h], 2
0x180175b54  jb      loc_180175CB3
0x180175b5a  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180175b60  mov     edx, 13h
0x180175b65  lea     rcx, aMShortcachetab; "m_shortCacheTable.Initialize failed"
0x180175b6c  jmp     loc_180175A8B
0x180175b71  mov     edx, 0FA0h
0x180175b76  lea     rcx, [rbx+5E90h]
0x180175b7d  mov     r8d, edx
0x180175b80  call    ?Initialize@?$Remap@_K@@QEAAJHH@Z; Remap<unsigned __int64>::Initialize(int,int)
0x180175b85  mov     edi, eax
0x180175b87  test    eax, eax
0x180175b89  jns     short loc_180175BCD
0x180175b8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180175b92  lea     rax, WPP_GLOBAL_Control
0x180175b99  cmp     rcx, rax
0x180175b9c  jz      loc_180175CB3
0x180175ba2  test    byte ptr [rcx+1Ch], 8
0x180175ba6  jz      loc_180175CB3
0x180175bac  cmp     byte ptr [rcx+19h], 2
0x180175bb0  jb      loc_180175CB3
0x180175bb6  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180175bbc  mov     edx, 14h
0x180175bc1  lea     rcx, aMGlyphcachetab; "m_glyphCacheTable.Initialize failed"
0x180175bc8  jmp     loc_180175A8B
0x180175bcd  lea     rcx, [rbx+5E68h]
0x180175bd4  mov     edx, 3E8h
0x180175bd9  mov     r8d, 7D0h
0x180175bdf  call    ?Initialize@?$Remap@_K@@QEAAJHH@Z; Remap<unsigned __int64>::Initialize(int,int)
0x180175be4  mov     edi, eax
0x180175be6  test    eax, eax
0x180175be8  jns     short loc_180175C2C
0x180175bea  mov     rcx, cs:WPP_GLOBAL_Control
0x180175bf1  lea     rax, WPP_GLOBAL_Control
0x180175bf8  cmp     rcx, rax
0x180175bfb  jz      loc_180175CB3
0x180175c01  test    byte ptr [rcx+1Ch], 8
0x180175c05  jz      loc_180175CB3
0x180175c0b  cmp     byte ptr [rcx+19h], 2
0x180175c0f  jb      loc_180175CB3
0x180175c15  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180175c1b  mov     edx, 15h
0x180175c20  lea     rcx, aNoncommitcache; "nonCommitCacheTable.Initialize failed"
0x180175c27  jmp     loc_180175A8B
0x180175c2c  lea     rcx, [rbx+5EB8h]
0x180175c33  call    ?Initialize@?$Remap@I@@QEAAJHH@Z; Remap<uint>::Initialize(int,int)
0x180175c38  mov     edi, eax
0x180175c3a  test    eax, eax
0x180175c3c  jns     short loc_180175C74
0x180175c3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180175c45  lea     rax, WPP_GLOBAL_Control
0x180175c4c  cmp     rcx, rax
0x180175c4f  jz      short loc_180175CB3
0x180175c51  test    byte ptr [rcx+1Ch], 8
0x180175c55  jz      short loc_180175CB3
0x180175c57  cmp     byte ptr [rcx+19h], 2
0x180175c5b  jb      short loc_180175CB3
0x180175c5d  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180175c63  mov     edx, 16h
0x180175c68  lea     rcx, aMSubcodecpalet; "m_subCodecPalette.Initialize failed"
0x180175c6f  jmp     loc_180175A8B
0x180175c74  mov     dword ptr [rbx+5E00h], 0
0x180175c7e  mov     word ptr [rbx+5EE0h], 0
0x180175c87  mov     qword ptr [rbx+5EE4h], 0
0x180175c92  mov     qword ptr [rbx+5EECh], 0
0x180175c9d  mov     qword ptr [rbx+5EF4h], 0
0x180175ca8  mov     qword ptr [rbx+5EFCh], 0
0x180175cb3  mov     rbx, [rsp+38h+arg_0]
0x180175cb8  mov     eax, edi
0x180175cba  add     rsp, 30h
0x180175cbe  pop     rdi
0x180175cbf  retn
```
