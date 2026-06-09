# GetInboundCommandText

- ea: `0x140028b6c`
- end: `0x1400294d5`
- name: `GetInboundCommandText`
- size: `2409`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14002b684`

## callees

- `0x140001b8c`
- `0x140004aa4`
- `0x140004b30`
- `0x140004b58`
- `0x140004b98`
- `0x140004ce4`
- `0x14002862c`
- `0x140028988`
- `0x140028b6c`
- `0x14002c18c`
- `0x14002c28c`
- `0x14002c54c`
- `0x14004fb78`
- `0x14004fc7c`
- `0x14005049c`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140028c29`
- `KERNEL32!GetLastError` at `0x140028c82`
- `KERNEL32!GetLastError` at `0x140028fba`
- `KERNEL32!GetLastError` at `0x14002908f`
- `KERNEL32!GetLastError` at `0x140028c29`
- `KERNEL32!GetLastError` at `0x140028c82`
- `KERNEL32!GetLastError` at `0x140028fba`
- `KERNEL32!GetLastError` at `0x14002908f`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall GetInboundCommandText(__int64 a1, __int64 a2, _QWORD *a3)
{
  int RealFaxTimeAsSystemTime; // r12d
  DWORD LastError; // eax
  DWORD v8; // eax
  unsigned __int16 *v9; // rax
  __int64 v10; // rax
  unsigned __int16 *v11; // rax
  __int64 v12; // rax
  unsigned __int16 *String; // rax
  __int64 v14; // rax
  unsigned __int16 *v15; // r14
  char *v16; // rdx
  unsigned int *v17; // rdi
  char *v18; // rdx
  char *v19; // rax
  void **v20; // rdx
  __int64 v21; // rax
  unsigned __int16 *v22; // rdx
  int v23; // eax
  DWORD v24; // eax
  void **v25; // rdx
  __int64 v26; // rax
  DWORD v27; // eax
  void **v29; // rdx
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  int v33; // eax
  unsigned __int16 *v34; // rdx
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  int v39; // eax
  unsigned __int16 *v40; // rdx
  int v41; // eax
  int v42; // [rsp+30h] [rbp-D0h]
  void *Block[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v44; // [rsp+48h] [rbp-B8h]
  unsigned __int64 v45; // [rsp+50h] [rbp-B0h]
  void *v46[3]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v47; // [rsp+70h] [rbp-90h]
  void *Src[3]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v49; // [rsp+90h] [rbp-70h]
  SYSTEMTIME UniversalTime; // [rsp+98h] [rbp-68h] BYREF
  SYSTEMTIME v51; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 v52[40]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v53[40]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v54[40]; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int16 v55[104]; // [rsp+1B0h] [rbp+B0h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids);
  }
  UniversalTime = 0;
  v51 = 0;
  RealFaxTimeAsSystemTime = GetRealFaxTimeAsSystemTime(*(_QWORD *)(a1 + 40), 1, &UniversalTime);
  if ( !RealFaxTimeAsSystemTime
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, LastError);
  }
  v42 = GetRealFaxTimeAsSystemTime(*(_QWORD *)(a1 + 40), 2, &v51);
  if ( !v42
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v8 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, v8);
  }
  std::wstring::append(a3, (void *)L"\"");
  switch ( *(_DWORD *)(a2 + 8) )
  {
    case 8:
      String = GetString(0x1F69u);
      v14 = FilteredLogString(Block, String);
      std::wstring::append(a3, v14, 0, -1);
      break;
    case 9:
      v11 = GetString(0x20000008u);
      v12 = FilteredLogString(Block, v11);
      std::wstring::append(a3, v12, 0, -1);
      break;
    case 0xB:
      v9 = GetString(0x1F67u);
      v10 = FilteredLogString(Block, v9);
      std::wstring::append(a3, v10, 0, -1);
      break;
    default:
      goto LABEL_23;
  }
  if ( v45 >= 8 )
    operator delete(Block[0]);
LABEL_23:
  std::wstring::append(a3, L"\"\t\"");
  v49 = 7;
  Src[2] = 0;
  LOWORD(Src[0]) = 0;
  v15 = L" ";
  v16 = (char *)(*(_QWORD *)(a1 + 40) + 1216LL);
  if ( *(_QWORD *)(a1 + 40) != -1216 && *(_WORD *)v16 )
  {
    std::wstring::assign((const void **)Src, v16);
    v17 = (unsigned int *)(a2 + 12);
    goto LABEL_39;
  }
  v17 = (unsigned int *)(a2 + 12);
  if ( !*(_DWORD *)(a2 + 12) )
  {
    v18 = (char *)L" ";
LABEL_38:
    std::wstring::assign((const void **)Src, v18);
    goto LABEL_39;
  }
  v19 = (char *)MapFSPIJobExtendedStatusToString(*v17);
  if ( v19 )
  {
    if ( *v17 == 16 && a1 != -1176 && *(_WORD *)(a1 + 1176) )
    {
      std::wstring::assign((const void **)Src, v19);
      std::wstring::append(Src, L" - ");
      std::wstring::append(Src, (void *)(a1 + 1176));
      goto LABEL_39;
    }
    v18 = v19;
    goto LABEL_38;
  }
  std::wstring::assign((const void **)Src, (char *)L" ");
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      44,
      (unsigned int)WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids,
      *v17,
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 40) + 16LL) + 40LL) + 584LL);
  }
LABEL_39:
  v20 = Src;
  if ( v49 >= 8 )
    v20 = (void **)Src[0];
  v21 = FilteredLogString(Block, v20);
  std::wstring::append(a3, v21, 0, -1);
  if ( v45 >= 8 )
    operator delete(Block[0]);
  std::wstring::append(a3, L"\"\t\"");
  if ( !*v17 )
    goto LABEL_44;
  v23 = StringCchPrintfW(v52, 0x28u, L"0x%08x");
  if ( v23 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        45,
        WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids,
        (unsigned int)v23);
    }
LABEL_44:
    v22 = L" ";
    goto LABEL_51;
  }
  v22 = v52;
LABEL_51:
  std::wstring::assign((const void **)Src, (char *)v22);
  std::wstring::append(a3, Src, 0, -1);
  std::wstring::append(a3, L"\"\t");
  if ( RealFaxTimeAsSystemTime )
  {
    v45 = 7;
    v44 = 0;
    LOWORD(Block[0]) = 0;
    if ( !(unsigned int)GetFaxTimeAsString(&UniversalTime, Block) )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v24 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, v24);
      }
LABEL_70:
      if ( v45 >= 8 )
        operator delete(Block[0]);
      LOWORD(Block[0]) = 0;
      v44 = 0;
      v45 = 7;
      if ( v49 >= 8 )
        operator delete(Src[0]);
      return 0;
    }
    v25 = Block;
    if ( v45 >= 8 )
      v25 = (void **)Block[0];
    v26 = FilteredLogString(v46, v25);
    std::wstring::append(a3, v26, 0, -1);
    if ( v47 >= 8 )
      operator delete(v46[0]);
    if ( v45 >= 8 )
      operator delete(Block[0]);
  }
  std::wstring::append(a3, L"\t");
  if ( v42 )
  {
    v45 = 7;
    v44 = 0;
    LOWORD(Block[0]) = 0;
    if ( !(unsigned int)GetFaxTimeAsString(&v51, Block) )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v27 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, v27);
      }
      goto LABEL_70;
    }
    v29 = Block;
    if ( v45 >= 8 )
      v29 = (void **)Block[0];
    v30 = FilteredLogString(v46, v29);
    std::wstring::append(a3, v30, 0, -1);
    if ( v47 >= 8 )
      operator delete(v46[0]);
    if ( v45 >= 8 )
      operator delete(Block[0]);
  }
  std::wstring::append(a3, L"\t\"");
  v31 = FilteredLogString(v46, *(void **)(*(_QWORD *)(*(_QWORD *)(a1 + 40) + 16LL) + 56LL));
  std::wstring::append(a3, v31, 0, -1);
  if ( v47 >= 8 )
    operator delete(v46[0]);
  std::wstring::append(a3, L"\"\t\"");
  v32 = FilteredLogString(v46, *(void **)(a1 + 72));
  std::wstring::append(a3, v32, 0, -1);
  if ( v47 >= 8 )
    operator delete(v46[0]);
  std::wstring::append(a3, L"\"\t");
  v33 = StringCchPrintfW(v53, 0x28u, L"%ld", *(unsigned int *)(a1 + 388));
  if ( v33 >= 0 )
  {
    v34 = v53;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        48,
        WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids,
        (unsigned int)v33);
    }
    v34 = L" ";
  }
  std::wstring::append(a3, v34);
  std::wstring::append(a3, L"\t\"");
  v35 = FilteredLogString(v46, *(void **)(*(_QWORD *)(*(_QWORD *)(a1 + 40) + 16LL) + 88LL));
  std::wstring::append(a3, v35, 0, -1);
  if ( v47 >= 8 )
    operator delete(v46[0]);
  std::wstring::append(a3, L"\"\t\"");
  v36 = FilteredLogString(v46, *(void **)(a2 + 24));
  std::wstring::append(a3, v36, 0, -1);
  if ( v47 >= 8 )
    operator delete(v46[0]);
  std::wstring::append(a3, L"\"\t\"");
  v37 = FilteredLogString(v46, *(void **)(a2 + 32));
  std::wstring::append(a3, v37, 0, -1);
  if ( v47 >= 8 )
    operator delete(v46[0]);
  std::wstring::append(a3, L"\"\t\"");
  v38 = FilteredLogString(v46, *(void **)(a2 + 40));
  std::wstring::append(a3, v38, 0, -1);
  if ( v47 >= 8 )
    operator delete(v46[0]);
  std::wstring::append(a3, L"\"\t");
  v39 = StringCchPrintfW(v54, 0x28u, L"%ld", *(unsigned int *)(a2 + 48));
  if ( v39 >= 0 )
  {
    v40 = v54;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        49,
        WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids,
        (unsigned int)v39);
    }
    v40 = L" ";
  }
  std::wstring::append(a3, v40);
  std::wstring::append(a3, L"\t");
  std::wstring::append(a3, (void *)L"\"");
  v41 = StringCchPrintfW(v55, 0x64u, L"0x%016I64x", *(_QWORD *)(a1 + 16));
  if ( v41 >= 0 )
  {
    v15 = v55;
  }
  else if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      50,
      WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids,
      (unsigned int)v41);
  }
  std::wstring::append(a3, v15);
  std::wstring::append(a3, L"\"\r\n");
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    if ( a3[3] >= 8u )
      a3 = (_QWORD *)*a3;
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, a3);
  }
  if ( v49 >= 8 )
    operator delete(Src[0]);
  return 1;
}

```

## disassembly

```asm
0x140028b6c  mov     [rsp-8+arg_18], rbx
0x140028b71  push    rbp
0x140028b72  push    rsi
0x140028b73  push    rdi
0x140028b74  push    r12
0x140028b76  push    r13
0x140028b78  push    r14
0x140028b7a  push    r15
0x140028b7c  lea     rbp, [rsp-190h]
0x140028b84  sub     rsp, 290h
0x140028b8b  mov     rax, cs:__security_cookie
0x140028b92  xor     rax, rsp
0x140028b95  mov     [rbp+1C0h+var_40], rax
0x140028b9c  mov     rbx, r8
0x140028b9f  mov     r13, rdx
0x140028ba2  mov     r15, rcx
0x140028ba5  lea     rax, WPP_GLOBAL_Control
0x140028bac  mov     r14b, 4
0x140028baf  mov     rcx, cs:WPP_GLOBAL_Control
0x140028bb6  cmp     rcx, rax
0x140028bb9  jz      short loc_140028BDC
0x140028bbb  test    [rcx+1Ch], r14b
0x140028bbf  jz      short loc_140028BDC
0x140028bc1  cmp     byte ptr [rcx+19h], 5
0x140028bc5  jb      short loc_140028BDC
0x140028bc7  mov     edx, 29h ; ')'
0x140028bcc  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x140028bd3  mov     rcx, [rcx+10h]
0x140028bd7  call    WPP_SF_
0x140028bdc  xorps   xmm0, xmm0
0x140028bdf  movups  xmmword ptr [rbp+1C0h+UniversalTime.wYear], xmm0
0x140028be3  xorps   xmm1, xmm1
0x140028be6  movups  xmmword ptr [rbp+1C0h+var_218.wYear], xmm1
0x140028bea  lea     r8, [rbp+1C0h+UniversalTime]
0x140028bee  mov     edx, 1
0x140028bf3  mov     rcx, [r15+28h]
0x140028bf7  call    ?GetRealFaxTimeAsSystemTime@@YAHQEAU_JOB_ENTRY@@W4FAX_ENUM_TIME_TYPES@@PEAU_SYSTEMTIME@@@Z; GetRealFaxTimeAsSystemTime(_JOB_ENTRY * const,FAX_ENUM_TIME_TYPES,_SYSTEMTIME *)
0x140028bfc  mov     r12d, eax
0x140028bff  mov     edi, 2
0x140028c04  xor     esi, esi
0x140028c06  test    eax, eax
0x140028c08  jnz     short loc_140028C4C
0x140028c0a  mov     rax, cs:WPP_GLOBAL_Control
0x140028c11  lea     rcx, WPP_GLOBAL_Control
0x140028c18  cmp     rax, rcx
0x140028c1b  jz      short loc_140028C4C
0x140028c1d  test    [rax+1Ch], r14b
0x140028c21  jz      short loc_140028C4C
0x140028c23  cmp     [rax+19h], dil
0x140028c27  jb      short loc_140028C4C
0x140028c29  call    cs:__imp_GetLastError
0x140028c2f  lea     edx, [rdi+28h]
0x140028c32  mov     r9d, eax
0x140028c35  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x140028c3c  mov     rcx, cs:WPP_GLOBAL_Control
0x140028c43  mov     rcx, [rcx+10h]
0x140028c47  call    WPP_SF_d
0x140028c4c  lea     r8, [rbp+1C0h+var_218]
0x140028c50  mov     edx, edi
0x140028c52  mov     rcx, [r15+28h]
0x140028c56  call    ?GetRealFaxTimeAsSystemTime@@YAHQEAU_JOB_ENTRY@@W4FAX_ENUM_TIME_TYPES@@PEAU_SYSTEMTIME@@@Z; GetRealFaxTimeAsSystemTime(_JOB_ENTRY * const,FAX_ENUM_TIME_TYPES,_SYSTEMTIME *)
0x140028c5b  mov     [rsp+2C0h+var_290], eax
0x140028c5f  test    eax, eax
0x140028c61  jnz     short loc_140028CA7
0x140028c63  mov     rax, cs:WPP_GLOBAL_Control
0x140028c6a  lea     rcx, WPP_GLOBAL_Control
0x140028c71  cmp     rax, rcx
0x140028c74  jz      short loc_140028CA7
0x140028c76  test    [rax+1Ch], r14b
0x140028c7a  jz      short loc_140028CA7
0x140028c7c  cmp     [rax+19h], dil
0x140028c80  jb      short loc_140028CA7
0x140028c82  call    cs:__imp_GetLastError
0x140028c88  mov     edx, 2Bh ; '+'
0x140028c8d  mov     r9d, eax
0x140028c90  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x140028c97  mov     rcx, cs:WPP_GLOBAL_Control
0x140028c9e  mov     rcx, [rcx+10h]
0x140028ca2  call    WPP_SF_d
0x140028ca7  lea     rdx, asc_14008D0EC; "\""
0x140028cae  mov     rcx, rbx; Src
0x140028cb1  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x140028cb6  mov     ecx, [r13+8]
0x140028cba  or      r14, 0FFFFFFFFFFFFFFFFh
0x140028cbe  sub     ecx, 8
0x140028cc1  jz      short loc_140028D28
0x140028cc3  sub     ecx, 1
0x140028cc6  jz      short loc_140028CFC
0x140028cc8  cmp     ecx, edi
0x140028cca  jnz     loc_140028D64
0x140028cd0  mov     ecx, 1F67h; unsigned int
0x140028cd5  call    ?GetString@@YAPEAGK@Z; GetString(ulong)
0x140028cda  mov     rdx, rax; Src
0x140028cdd  lea     rcx, [rsp+2C0h+Block]; void *
0x140028ce2  call    FilteredLogString
0x140028ce7  nop
0x140028ce8  mov     r9, r14
0x140028ceb  xor     r8d, r8d
0x140028cee  mov     rdx, rax
0x140028cf1  mov     rcx, rbx
0x140028cf4  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x140028cf9  nop
0x140028cfa  jmp     short loc_140028D52
0x140028cfc  mov     ecx, 20000008h; unsigned int
0x140028d01  call    ?GetString@@YAPEAGK@Z; GetString(ulong)
0x140028d06  mov     rdx, rax; Src
0x140028d09  lea     rcx, [rsp+2C0h+Block]; void *
0x140028d0e  call    FilteredLogString
0x140028d13  nop
0x140028d14  mov     r9, r14
0x140028d17  xor     r8d, r8d
0x140028d1a  mov     rdx, rax
0x140028d1d  mov     rcx, rbx
0x140028d20  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x140028d25  nop
0x140028d26  jmp     short loc_140028D52
0x140028d28  mov     ecx, 1F69h; unsigned int
0x140028d2d  call    ?GetString@@YAPEAGK@Z; GetString(ulong)
0x140028d32  mov     rdx, rax; Src
0x140028d35  lea     rcx, [rsp+2C0h+Block]; void *
0x140028d3a  call    FilteredLogString
0x140028d3f  nop
0x140028d40  mov     r9, r14
0x140028d43  xor     r8d, r8d
0x140028d46  mov     rdx, rax
0x140028d49  mov     rcx, rbx
0x140028d4c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x140028d51  nop
0x140028d52  cmp     [rsp+2C0h+var_270], 8
0x140028d58  jb      short loc_140028D64
0x140028d5a  mov     rcx, [rsp+2C0h+Block]; Block
0x140028d5f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140028d64  lea     rdx, asc_14008D200; "\"\t\""
0x140028d6b  mov     rcx, rbx; Src
0x140028d6e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x140028d73  mov     [rbp+1C0h+var_230], 7
0x140028d7b  mov     [rbp+1C0h+var_238], rsi
0x140028d7f  mov     word ptr [rsp+2C0h+Src], si
0x140028d84  mov     rdx, [r15+28h]
0x140028d88  lea     r14, asc_14008D208; " "
0x140028d8f  add     rdx, 4C0h; Src
0x140028d96  jz      short loc_140028DB0
0x140028d98  cmp     [rdx], si
0x140028d9b  jz      short loc_140028DB0
0x140028d9d  lea     rcx, [rsp+2C0h+Src]; void *
0x140028da2  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x140028da7  lea     rdi, [r13+0Ch]
0x140028dab  jmp     loc_140028E87
0x140028db0  lea     rdi, [r13+0Ch]
0x140028db4  cmp     [rdi], esi
0x140028db6  jnz     short loc_140028DC0
0x140028db8  mov     rdx, r14
0x140028dbb  jmp     loc_140028E7D
0x140028dc0  mov     ecx, [rdi]; unsigned int
0x140028dc2  call    ?MapFSPIJobExtendedStatusToString@@YAPEAGK@Z; MapFSPIJobExtendedStatusToString(ulong)
0x140028dc7  test    rax, rax
0x140028dca  jnz     short loc_140028E35
0x140028dcc  mov     rdx, r14; Src
0x140028dcf  lea     rcx, [rsp+2C0h+Src]; void *
0x140028dd4  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x140028dd9  mov     rcx, cs:WPP_GLOBAL_Control
0x140028de0  lea     rax, WPP_GLOBAL_Control
0x140028de7  cmp     rcx, rax
0x140028dea  jz      loc_140028E87
0x140028df0  test    byte ptr [rcx+1Ch], 4
0x140028df4  jz      loc_140028E87
0x140028dfa  cmp     byte ptr [rcx+19h], 2
0x140028dfe  jb      loc_140028E87
0x140028e04  mov     rax, [r15+28h]
0x140028e08  mov     rdx, [rax+10h]
0x140028e0c  mov     rax, [rdx+28h]
0x140028e10  add     rax, 248h
0x140028e16  mov     edx, 2Ch ; ','
0x140028e1b  mov     [rsp+2C0h+var_2A0], rax
0x140028e20  mov     r9d, [rdi]
0x140028e23  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x140028e2a  mov     rcx, [rcx+10h]
0x140028e2e  call    WPP_SF_DS
0x140028e33  jmp     short loc_140028E87
0x140028e35  cmp     dword ptr [rdi], 10h
0x140028e38  jnz     short loc_140028E7A
0x140028e3a  lea     rsi, [r15+498h]
0x140028e41  xor     ecx, ecx
0x140028e43  test    rsi, rsi
0x140028e46  jz      short loc_140028E7A
0x140028e48  cmp     [rsi], cx
0x140028e4b  jz      short loc_140028E7A
0x140028e4d  mov     rdx, rax; Src
0x140028e50  lea     rcx, [rsp+2C0h+Src]; void *
0x140028e55  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x140028e5a  lea     rdx, asc_14008D210; " - "
0x140028e61  lea     rcx, [rsp+2C0h+Src]; Src
0x140028e66  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x140028e6b  mov     rdx, rsi; void *
0x140028e6e  lea     rcx, [rsp+2C0h+Src]; Src
0x140028e73  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x140028e78  jmp     short loc_140028E87
0x140028e7a  mov     rdx, rax; Src
0x140028e7d  lea     rcx, [rsp+2C0h+Src]; void *
0x140028e82  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x140028e87  lea     rdx, [rsp+2C0h+Src]
0x140028e8c  mov     esi, 8
0x140028e91  cmp     [rbp+1C0h+var_230], rsi
0x140028e95  cmovnb  rdx, [rsp+2C0h+Src]; Src
0x140028e9b  lea     rcx, [rsp+2C0h+Block]; void *
0x140028ea0  call    FilteredLogString
0x140028ea5  nop
0x140028ea6  or      r9, 0FFFFFFFFFFFFFFFFh
0x140028eaa  xor     r8d, r8d
0x140028ead  mov     rdx, rax
0x140028eb0  mov     rcx, rbx
0x140028eb3  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x140028eb8  nop
0x140028eb9  cmp     [rsp+2C0h+var_270], rsi
0x140028ebe  jb      short loc_140028ECA
0x140028ec0  mov     rcx, [rsp+2C0h+Block]; Block
0x140028ec5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140028eca  lea     rdx, asc_14008D200; "\"\t\""
0x140028ed1  mov     rcx, rbx; Src
0x140028ed4  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x140028ed9  mov     r9d, [rdi]
0x140028edc  xor     edi, edi
0x140028ede  test    r9d, r9d
0x140028ee1  jnz     short loc_140028EE8
0x140028ee3  mov     rdx, r14
0x140028ee6  jmp     short loc_140028F3E
0x140028ee8  lea     r8, a0x08x_0; "0x%08x"
0x140028eef  mov     edx, 28h ; '('; unsigned __int64
0x140028ef4  lea     rcx, [rbp+1C0h+var_200]; unsigned __int16 *
0x140028ef8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140028efd  test    eax, eax
0x140028eff  jns     short loc_140028F3A
0x140028f01  mov     rcx, cs:WPP_GLOBAL_Control
0x140028f08  lea     rdx, WPP_GLOBAL_Control
0x140028f0f  cmp     rcx, rdx
0x140028f12  jz      short loc_140028EE3
0x140028f14  test    byte ptr [rcx+1Ch], 4
0x140028f18  jz      short loc_140028EE3
0x140028f1a  cmp     byte ptr [rcx+19h], 2
0x140028f1e  jb      short loc_140028EE3
0x140028f20  mov     edx, 2Dh ; '-'
0x140028f25  mov     r9d, eax
0x140028f28  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x140028f2f  mov     rcx, [rcx+10h]
0x140028f33  call    WPP_SF_d
0x140028f38  jmp     short loc_140028EE3
0x140028f3a  lea     rdx, [rbp+1C0h+var_200]; Src
0x140028f3e  lea     rcx, [rsp+2C0h+Src]; void *
0x140028f43  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x140028f48  or      r9, 0FFFFFFFFFFFFFFFFh
0x140028f4c  xor     r8d, r8d
0x140028f4f  lea     rdx, [rsp+2C0h+Src]
0x140028f54  mov     rcx, rbx
0x140028f57  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x140028f5c  lea     rdx, asc_14008D228; "\"\t"
0x140028f63  mov     rcx, rbx; Src
0x140028f66  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x140028f6b  test    r12d, r12d
0x140028f6e  mov     r12d, 7
0x140028f74  jz      loc_140029036
0x140028f7a  mov     [rsp+2C0h+var_270], r12
0x140028f7f  mov     [rsp+2C0h+var_278], rdi
0x140028f84  mov     word ptr [rsp+2C0h+Block], di
0x140028f89  lea     rdx, [rsp+2C0h+Block]; void *
0x140028f8e  lea     rcx, [rbp+1C0h+UniversalTime]; lpUniversalTime
0x140028f92  call    GetFaxTimeAsString
0x140028f97  test    eax, eax
0x140028f99  jnz     short loc_140028FE5
0x140028f9b  mov     rax, cs:WPP_GLOBAL_Control
0x140028fa2  lea     rcx, WPP_GLOBAL_Control
0x140028fa9  cmp     rax, rcx
0x140028fac  jz      short loc_140028FE0
0x140028fae  test    byte ptr [rax+1Ch], 4
0x140028fb2  jz      short loc_140028FE0
0x140028fb4  cmp     byte ptr [rax+19h], 2
0x140028fb8  jb      short loc_140028FE0
0x140028fba  call    cs:__imp_GetLastError
0x140028fc0  lea     edx, [r12+27h]
0x140028fc5  mov     r9d, eax
0x140028fc8  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x140028fcf  mov     rcx, cs:WPP_GLOBAL_Control
0x140028fd6  mov     rcx, [rcx+10h]
0x140028fda  call    WPP_SF_d
0x140028fdf  nop
0x140028fe0  jmp     loc_1400290B5
0x140028fe5  lea     rdx, [rsp+2C0h+Block]
0x140028fea  cmp     [rsp+2C0h+var_270], rsi
0x140028fef  cmovnb  rdx, [rsp+2C0h+Block]; Src
0x140028ff5  lea     rcx, [rsp+2C0h+var_268]; void *
0x140028ffa  call    FilteredLogString
0x140028fff  nop
0x140029000  or      r9, 0FFFFFFFFFFFFFFFFh
0x140029004  xor     r8d, r8d
0x140029007  mov     rdx, rax
0x14002900a  mov     rcx, rbx
0x14002900d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x140029012  nop
0x140029013  cmp     [rsp+2C0h+var_250], rsi
0x140029018  jb      short loc_140029025
0x14002901a  mov     rcx, [rsp+2C0h+var_268]; Block
  ... truncated ...
```
