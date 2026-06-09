# GetInboundCommandText

- ea: `0x140029f2c`
- end: `0x14002a8b2`
- name: `GetInboundCommandText`
- size: `2438`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14002cb00`

## callees

- `0x140001bac`
- `0x140004be4`
- `0x140004c78`
- `0x140004ca8`
- `0x140004cec`
- `0x140004e48`
- `0x1400299d4`
- `0x140029d30`
- `0x140029f2c`
- `0x14002d68c`
- `0x14002d78c`
- `0x14002da4c`
- `0x140052e68`
- `0x140052f80`
- `0x1400537ec`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140029fe9`
- `KERNEL32!GetLastError` at `0x14002a048`
- `KERNEL32!GetLastError` at `0x14002a386`
- `KERNEL32!GetLastError` at `0x14002a465`
- `KERNEL32!GetLastError` at `0x140029fe9`
- `KERNEL32!GetLastError` at `0x14002a048`
- `KERNEL32!GetLastError` at `0x14002a386`
- `KERNEL32!GetLastError` at `0x14002a465`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall GetInboundCommandText(__int64 a1, __int64 a2, char *a3)
{
  int RealFaxTimeAsSystemTime; // r12d
  DWORD LastError; // eax
  DWORD v8; // eax
  unsigned __int16 *v9; // rax
  _QWORD *v10; // rax
  unsigned __int16 *v11; // rax
  _QWORD *v12; // rax
  unsigned __int16 *String; // rax
  _QWORD *v14; // rax
  unsigned __int16 *v15; // r14
  char *v16; // rdx
  unsigned int *v17; // rdi
  char *v18; // rdx
  char *v19; // rax
  void **v20; // rdx
  _QWORD *v21; // rax
  unsigned __int16 *v22; // rdx
  int v23; // eax
  DWORD v24; // eax
  void **v25; // rdx
  _QWORD *v26; // rax
  DWORD v27; // eax
  void **v29; // rdx
  _QWORD *v30; // rax
  _QWORD *v31; // rax
  _QWORD *v32; // rax
  int v33; // eax
  unsigned __int16 *v34; // rdx
  _QWORD *v35; // rax
  _QWORD *v36; // rax
  _QWORD *v37; // rax
  _QWORD *v38; // rax
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
  std::wstring::append(a3, (char *)L"\"");
  switch ( *(_DWORD *)(a2 + 8) )
  {
    case 8:
      String = GetString(0x1F69u);
      v14 = FilteredLogString(Block, String);
      std::wstring::append(a3, v14, 0, 0xFFFFFFFFFFFFFFFFuLL);
      break;
    case 9:
      v11 = GetString(0x20000008u);
      v12 = FilteredLogString(Block, v11);
      std::wstring::append(a3, v12, 0, 0xFFFFFFFFFFFFFFFFuLL);
      break;
    case 0xB:
      v9 = GetString(0x1F67u);
      v10 = FilteredLogString(Block, v9);
      std::wstring::append(a3, v10, 0, 0xFFFFFFFFFFFFFFFFuLL);
      break;
    default:
      goto LABEL_23;
  }
  if ( v45 >= 8 )
    operator delete(Block[0]);
LABEL_23:
  std::wstring::append(a3, (char *)L"\"\t\"");
  v49 = 7;
  Src[2] = 0;
  LOWORD(Src[0]) = 0;
  v15 = L" ";
  v16 = (char *)(*(_QWORD *)(a1 + 40) + 1216LL);
  if ( *(_QWORD *)(a1 + 40) != -1216 && *(_WORD *)v16 )
  {
    std::wstring::assign((char *)Src, v16);
    v17 = (unsigned int *)(a2 + 12);
    goto LABEL_39;
  }
  v17 = (unsigned int *)(a2 + 12);
  if ( !*(_DWORD *)(a2 + 12) )
  {
    v18 = (char *)L" ";
LABEL_38:
    std::wstring::assign((char *)Src, v18);
    goto LABEL_39;
  }
  v19 = (char *)MapFSPIJobExtendedStatusToString(*v17);
  if ( v19 )
  {
    if ( *v17 == 16 && a1 != -1176 && *(_WORD *)(a1 + 1176) )
    {
      std::wstring::assign((char *)Src, v19);
      std::wstring::append((char *)Src, (char *)L" - ");
      std::wstring::append((char *)Src, (char *)(a1 + 1176));
      goto LABEL_39;
    }
    v18 = v19;
    goto LABEL_38;
  }
  std::wstring::assign((char *)Src, (char *)L" ");
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
  std::wstring::append(a3, v21, 0, 0xFFFFFFFFFFFFFFFFuLL);
  if ( v45 >= 8 )
    operator delete(Block[0]);
  std::wstring::append(a3, (char *)L"\"\t\"");
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
  std::wstring::assign((char *)Src, (char *)v22);
  std::wstring::append(a3, Src, 0, 0xFFFFFFFFFFFFFFFFuLL);
  std::wstring::append(a3, (char *)L"\"\t");
  if ( RealFaxTimeAsSystemTime )
  {
    v45 = 7;
    v44 = 0;
    LOWORD(Block[0]) = 0;
    if ( !(unsigned int)GetFaxTimeAsString(&UniversalTime, (char *)Block) )
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
    std::wstring::append(a3, v26, 0, 0xFFFFFFFFFFFFFFFFuLL);
    if ( v47 >= 8 )
      operator delete(v46[0]);
    if ( v45 >= 8 )
      operator delete(Block[0]);
  }
  std::wstring::append(a3, (char *)L"\t");
  if ( v42 )
  {
    v45 = 7;
    v44 = 0;
    LOWORD(Block[0]) = 0;
    if ( !(unsigned int)GetFaxTimeAsString(&v51, (char *)Block) )
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
    std::wstring::append(a3, v30, 0, 0xFFFFFFFFFFFFFFFFuLL);
    if ( v47 >= 8 )
      operator delete(v46[0]);
    if ( v45 >= 8 )
      operator delete(Block[0]);
  }
  std::wstring::append(a3, (char *)L"\t\"");
  v31 = FilteredLogString(v46, *(void **)(*(_QWORD *)(*(_QWORD *)(a1 + 40) + 16LL) + 56LL));
  std::wstring::append(a3, v31, 0, 0xFFFFFFFFFFFFFFFFuLL);
  if ( v47 >= 8 )
    operator delete(v46[0]);
  std::wstring::append(a3, (char *)L"\"\t\"");
  v32 = FilteredLogString(v46, *(void **)(a1 + 72));
  std::wstring::append(a3, v32, 0, 0xFFFFFFFFFFFFFFFFuLL);
  if ( v47 >= 8 )
    operator delete(v46[0]);
  std::wstring::append(a3, (char *)L"\"\t");
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
  std::wstring::append(a3, (char *)v34);
  std::wstring::append(a3, (char *)L"\t\"");
  v35 = FilteredLogString(v46, *(void **)(*(_QWORD *)(*(_QWORD *)(a1 + 40) + 16LL) + 88LL));
  std::wstring::append(a3, v35, 0, 0xFFFFFFFFFFFFFFFFuLL);
  if ( v47 >= 8 )
    operator delete(v46[0]);
  std::wstring::append(a3, (char *)L"\"\t\"");
  v36 = FilteredLogString(v46, *(void **)(a2 + 24));
  std::wstring::append(a3, v36, 0, 0xFFFFFFFFFFFFFFFFuLL);
  if ( v47 >= 8 )
    operator delete(v46[0]);
  std::wstring::append(a3, (char *)L"\"\t\"");
  v37 = FilteredLogString(v46, *(void **)(a2 + 32));
  std::wstring::append(a3, v37, 0, 0xFFFFFFFFFFFFFFFFuLL);
  if ( v47 >= 8 )
    operator delete(v46[0]);
  std::wstring::append(a3, (char *)L"\"\t\"");
  v38 = FilteredLogString(v46, *(void **)(a2 + 40));
  std::wstring::append(a3, v38, 0, 0xFFFFFFFFFFFFFFFFuLL);
  if ( v47 >= 8 )
    operator delete(v46[0]);
  std::wstring::append(a3, (char *)L"\"\t");
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
  std::wstring::append(a3, (char *)v40);
  std::wstring::append(a3, (char *)L"\t");
  std::wstring::append(a3, (char *)L"\"");
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
  std::wstring::append(a3, (char *)v15);
  std::wstring::append(a3, (char *)L"\"\r\n");
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    if ( *((_QWORD *)a3 + 3) >= 8u )
      a3 = *(char **)a3;
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, a3);
  }
  if ( v49 >= 8 )
    operator delete(Src[0]);
  return 1;
}

```

## disassembly

```asm
0x140029f2c  mov     [rsp-8+arg_18], rbx
0x140029f31  push    rbp
0x140029f32  push    rsi
0x140029f33  push    rdi
0x140029f34  push    r12
0x140029f36  push    r13
0x140029f38  push    r14
0x140029f3a  push    r15
0x140029f3c  lea     rbp, [rsp-190h]
0x140029f44  sub     rsp, 290h
0x140029f4b  mov     rax, cs:__security_cookie
0x140029f52  xor     rax, rsp
0x140029f55  mov     [rbp+1C0h+var_40], rax
0x140029f5c  mov     rbx, r8
0x140029f5f  mov     r13, rdx
0x140029f62  mov     r15, rcx
0x140029f65  lea     rax, WPP_GLOBAL_Control
0x140029f6c  mov     r14b, 4
0x140029f6f  mov     rcx, cs:WPP_GLOBAL_Control
0x140029f76  cmp     rcx, rax
0x140029f79  jz      short loc_140029F9C
0x140029f7b  test    [rcx+1Ch], r14b
0x140029f7f  jz      short loc_140029F9C
0x140029f81  cmp     byte ptr [rcx+19h], 5
0x140029f85  jb      short loc_140029F9C
0x140029f87  mov     edx, 29h ; ')'
0x140029f8c  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x140029f93  mov     rcx, [rcx+10h]
0x140029f97  call    WPP_SF_
0x140029f9c  xorps   xmm0, xmm0
0x140029f9f  movups  xmmword ptr [rbp+1C0h+UniversalTime.wYear], xmm0
0x140029fa3  xorps   xmm1, xmm1
0x140029fa6  movups  xmmword ptr [rbp+1C0h+var_218.wYear], xmm1
0x140029faa  lea     r8, [rbp+1C0h+UniversalTime]
0x140029fae  mov     edx, 1
0x140029fb3  mov     rcx, [r15+28h]
0x140029fb7  call    ?GetRealFaxTimeAsSystemTime@@YAHQEAU_JOB_ENTRY@@W4FAX_ENUM_TIME_TYPES@@PEAU_SYSTEMTIME@@@Z; GetRealFaxTimeAsSystemTime(_JOB_ENTRY * const,FAX_ENUM_TIME_TYPES,_SYSTEMTIME *)
0x140029fbc  mov     r12d, eax
0x140029fbf  mov     edi, 2
0x140029fc4  xor     esi, esi
0x140029fc6  test    eax, eax
0x140029fc8  jnz     short loc_14002A012
0x140029fca  mov     rax, cs:WPP_GLOBAL_Control
0x140029fd1  lea     rcx, WPP_GLOBAL_Control
0x140029fd8  cmp     rax, rcx
0x140029fdb  jz      short loc_14002A012
0x140029fdd  test    [rax+1Ch], r14b
0x140029fe1  jz      short loc_14002A012
0x140029fe3  cmp     [rax+19h], dil
0x140029fe7  jb      short loc_14002A012
0x140029fe9  call    cs:__imp_GetLastError
0x140029ff0  nop     dword ptr [rax+rax+00h]
0x140029ff5  lea     edx, [rdi+28h]
0x140029ff8  mov     r9d, eax
0x140029ffb  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002a002  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a009  mov     rcx, [rcx+10h]
0x14002a00d  call    WPP_SF_d
0x14002a012  lea     r8, [rbp+1C0h+var_218]
0x14002a016  mov     edx, edi
0x14002a018  mov     rcx, [r15+28h]
0x14002a01c  call    ?GetRealFaxTimeAsSystemTime@@YAHQEAU_JOB_ENTRY@@W4FAX_ENUM_TIME_TYPES@@PEAU_SYSTEMTIME@@@Z; GetRealFaxTimeAsSystemTime(_JOB_ENTRY * const,FAX_ENUM_TIME_TYPES,_SYSTEMTIME *)
0x14002a021  mov     [rsp+2C0h+var_290], eax
0x14002a025  test    eax, eax
0x14002a027  jnz     short loc_14002A073
0x14002a029  mov     rax, cs:WPP_GLOBAL_Control
0x14002a030  lea     rcx, WPP_GLOBAL_Control
0x14002a037  cmp     rax, rcx
0x14002a03a  jz      short loc_14002A073
0x14002a03c  test    [rax+1Ch], r14b
0x14002a040  jz      short loc_14002A073
0x14002a042  cmp     [rax+19h], dil
0x14002a046  jb      short loc_14002A073
0x14002a048  call    cs:__imp_GetLastError
0x14002a04f  nop     dword ptr [rax+rax+00h]
0x14002a054  mov     edx, 2Bh ; '+'
0x14002a059  mov     r9d, eax
0x14002a05c  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002a063  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a06a  mov     rcx, [rcx+10h]
0x14002a06e  call    WPP_SF_d
0x14002a073  lea     rdx, asc_1400930FC; "\""
0x14002a07a  mov     rcx, rbx; Src
0x14002a07d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x14002a082  mov     ecx, [r13+8]
0x14002a086  or      r14, 0FFFFFFFFFFFFFFFFh
0x14002a08a  sub     ecx, 8
0x14002a08d  jz      short loc_14002A0F4
0x14002a08f  sub     ecx, 1
0x14002a092  jz      short loc_14002A0C8
0x14002a094  cmp     ecx, edi
0x14002a096  jnz     loc_14002A130
0x14002a09c  mov     ecx, 1F67h; unsigned int
0x14002a0a1  call    ?GetString@@YAPEAGK@Z; GetString(ulong)
0x14002a0a6  mov     rdx, rax; Src
0x14002a0a9  lea     rcx, [rsp+2C0h+Block]; void *
0x14002a0ae  call    FilteredLogString
0x14002a0b3  nop
0x14002a0b4  mov     r9, r14
0x14002a0b7  xor     r8d, r8d
0x14002a0ba  mov     rdx, rax
0x14002a0bd  mov     rcx, rbx
0x14002a0c0  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x14002a0c5  nop
0x14002a0c6  jmp     short loc_14002A11E
0x14002a0c8  mov     ecx, 20000008h; unsigned int
0x14002a0cd  call    ?GetString@@YAPEAGK@Z; GetString(ulong)
0x14002a0d2  mov     rdx, rax; Src
0x14002a0d5  lea     rcx, [rsp+2C0h+Block]; void *
0x14002a0da  call    FilteredLogString
0x14002a0df  nop
0x14002a0e0  mov     r9, r14
0x14002a0e3  xor     r8d, r8d
0x14002a0e6  mov     rdx, rax
0x14002a0e9  mov     rcx, rbx
0x14002a0ec  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x14002a0f1  nop
0x14002a0f2  jmp     short loc_14002A11E
0x14002a0f4  mov     ecx, 1F69h; unsigned int
0x14002a0f9  call    ?GetString@@YAPEAGK@Z; GetString(ulong)
0x14002a0fe  mov     rdx, rax; Src
0x14002a101  lea     rcx, [rsp+2C0h+Block]; void *
0x14002a106  call    FilteredLogString
0x14002a10b  nop
0x14002a10c  mov     r9, r14
0x14002a10f  xor     r8d, r8d
0x14002a112  mov     rdx, rax
0x14002a115  mov     rcx, rbx
0x14002a118  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x14002a11d  nop
0x14002a11e  cmp     [rsp+2C0h+var_270], 8
0x14002a124  jb      short loc_14002A130
0x14002a126  mov     rcx, [rsp+2C0h+Block]; Block
0x14002a12b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002a130  lea     rdx, asc_140093210; "\"\t\""
0x14002a137  mov     rcx, rbx; Src
0x14002a13a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x14002a13f  mov     [rbp+1C0h+var_230], 7
0x14002a147  mov     [rbp+1C0h+var_238], rsi
0x14002a14b  mov     word ptr [rsp+2C0h+Src], si
0x14002a150  mov     rdx, [r15+28h]
0x14002a154  lea     r14, asc_140093218; " "
0x14002a15b  add     rdx, 4C0h; Src
0x14002a162  jz      short loc_14002A17C
0x14002a164  cmp     [rdx], si
0x14002a167  jz      short loc_14002A17C
0x14002a169  lea     rcx, [rsp+2C0h+Src]; void *
0x14002a16e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x14002a173  lea     rdi, [r13+0Ch]
0x14002a177  jmp     loc_14002A253
0x14002a17c  lea     rdi, [r13+0Ch]
0x14002a180  cmp     [rdi], esi
0x14002a182  jnz     short loc_14002A18C
0x14002a184  mov     rdx, r14
0x14002a187  jmp     loc_14002A249
0x14002a18c  mov     ecx, [rdi]; unsigned int
0x14002a18e  call    ?MapFSPIJobExtendedStatusToString@@YAPEAGK@Z; MapFSPIJobExtendedStatusToString(ulong)
0x14002a193  test    rax, rax
0x14002a196  jnz     short loc_14002A201
0x14002a198  mov     rdx, r14; Src
0x14002a19b  lea     rcx, [rsp+2C0h+Src]; void *
0x14002a1a0  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x14002a1a5  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a1ac  lea     rax, WPP_GLOBAL_Control
0x14002a1b3  cmp     rcx, rax
0x14002a1b6  jz      loc_14002A253
0x14002a1bc  test    byte ptr [rcx+1Ch], 4
0x14002a1c0  jz      loc_14002A253
0x14002a1c6  cmp     byte ptr [rcx+19h], 2
0x14002a1ca  jb      loc_14002A253
0x14002a1d0  mov     rax, [r15+28h]
0x14002a1d4  mov     rdx, [rax+10h]
0x14002a1d8  mov     rax, [rdx+28h]
0x14002a1dc  add     rax, 248h
0x14002a1e2  mov     edx, 2Ch ; ','
0x14002a1e7  mov     [rsp+2C0h+var_2A0], rax
0x14002a1ec  mov     r9d, [rdi]
0x14002a1ef  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002a1f6  mov     rcx, [rcx+10h]
0x14002a1fa  call    WPP_SF_DS
0x14002a1ff  jmp     short loc_14002A253
0x14002a201  cmp     dword ptr [rdi], 10h
0x14002a204  jnz     short loc_14002A246
0x14002a206  lea     rsi, [r15+498h]
0x14002a20d  xor     ecx, ecx
0x14002a20f  test    rsi, rsi
0x14002a212  jz      short loc_14002A246
0x14002a214  cmp     [rsi], cx
0x14002a217  jz      short loc_14002A246
0x14002a219  mov     rdx, rax; Src
0x14002a21c  lea     rcx, [rsp+2C0h+Src]; void *
0x14002a221  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x14002a226  lea     rdx, asc_140093220; " - "
0x14002a22d  lea     rcx, [rsp+2C0h+Src]; Src
0x14002a232  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x14002a237  mov     rdx, rsi; void *
0x14002a23a  lea     rcx, [rsp+2C0h+Src]; Src
0x14002a23f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x14002a244  jmp     short loc_14002A253
0x14002a246  mov     rdx, rax; Src
0x14002a249  lea     rcx, [rsp+2C0h+Src]; void *
0x14002a24e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x14002a253  lea     rdx, [rsp+2C0h+Src]
0x14002a258  mov     esi, 8
0x14002a25d  cmp     [rbp+1C0h+var_230], rsi
0x14002a261  cmovnb  rdx, [rsp+2C0h+Src]; Src
0x14002a267  lea     rcx, [rsp+2C0h+Block]; void *
0x14002a26c  call    FilteredLogString
0x14002a271  nop
0x14002a272  or      r9, 0FFFFFFFFFFFFFFFFh
0x14002a276  xor     r8d, r8d
0x14002a279  mov     rdx, rax
0x14002a27c  mov     rcx, rbx
0x14002a27f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x14002a284  nop
0x14002a285  cmp     [rsp+2C0h+var_270], rsi
0x14002a28a  jb      short loc_14002A296
0x14002a28c  mov     rcx, [rsp+2C0h+Block]; Block
0x14002a291  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002a296  lea     rdx, asc_140093210; "\"\t\""
0x14002a29d  mov     rcx, rbx; Src
0x14002a2a0  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x14002a2a5  mov     r9d, [rdi]
0x14002a2a8  xor     edi, edi
0x14002a2aa  test    r9d, r9d
0x14002a2ad  jnz     short loc_14002A2B4
0x14002a2af  mov     rdx, r14
0x14002a2b2  jmp     short loc_14002A30A
0x14002a2b4  lea     r8, a0x08x_0; "0x%08x"
0x14002a2bb  mov     edx, 28h ; '('; unsigned __int64
0x14002a2c0  lea     rcx, [rbp+1C0h+var_200]; unsigned __int16 *
0x14002a2c4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002a2c9  test    eax, eax
0x14002a2cb  jns     short loc_14002A306
0x14002a2cd  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a2d4  lea     rdx, WPP_GLOBAL_Control
0x14002a2db  cmp     rcx, rdx
0x14002a2de  jz      short loc_14002A2AF
0x14002a2e0  test    byte ptr [rcx+1Ch], 4
0x14002a2e4  jz      short loc_14002A2AF
0x14002a2e6  cmp     byte ptr [rcx+19h], 2
0x14002a2ea  jb      short loc_14002A2AF
0x14002a2ec  mov     edx, 2Dh ; '-'
0x14002a2f1  mov     r9d, eax
0x14002a2f4  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002a2fb  mov     rcx, [rcx+10h]
0x14002a2ff  call    WPP_SF_d
0x14002a304  jmp     short loc_14002A2AF
0x14002a306  lea     rdx, [rbp+1C0h+var_200]; Src
0x14002a30a  lea     rcx, [rsp+2C0h+Src]; void *
0x14002a30f  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x14002a314  or      r9, 0FFFFFFFFFFFFFFFFh
0x14002a318  xor     r8d, r8d
0x14002a31b  lea     rdx, [rsp+2C0h+Src]
0x14002a320  mov     rcx, rbx
0x14002a323  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x14002a328  lea     rdx, asc_140093238; "\"\t"
0x14002a32f  mov     rcx, rbx; Src
0x14002a332  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x14002a337  test    r12d, r12d
0x14002a33a  mov     r12d, 7
0x14002a340  jz      loc_14002A408
0x14002a346  mov     [rsp+2C0h+var_270], r12
0x14002a34b  mov     [rsp+2C0h+var_278], rdi
0x14002a350  mov     word ptr [rsp+2C0h+Block], di
0x14002a355  lea     rdx, [rsp+2C0h+Block]; void *
0x14002a35a  lea     rcx, [rbp+1C0h+UniversalTime]; lpUniversalTime
0x14002a35e  call    GetFaxTimeAsString
0x14002a363  test    eax, eax
0x14002a365  jnz     short loc_14002A3B7
0x14002a367  mov     rax, cs:WPP_GLOBAL_Control
0x14002a36e  lea     rcx, WPP_GLOBAL_Control
0x14002a375  cmp     rax, rcx
0x14002a378  jz      short loc_14002A3B2
0x14002a37a  test    byte ptr [rax+1Ch], 4
0x14002a37e  jz      short loc_14002A3B2
0x14002a380  cmp     byte ptr [rax+19h], 2
0x14002a384  jb      short loc_14002A3B2
0x14002a386  call    cs:__imp_GetLastError
0x14002a38d  nop     dword ptr [rax+rax+00h]
0x14002a392  lea     edx, [r12+27h]
0x14002a397  mov     r9d, eax
0x14002a39a  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002a3a1  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a3a8  mov     rcx, [rcx+10h]
0x14002a3ac  call    WPP_SF_d
0x14002a3b1  nop
0x14002a3b2  jmp     loc_14002A491
0x14002a3b7  lea     rdx, [rsp+2C0h+Block]
0x14002a3bc  cmp     [rsp+2C0h+var_270], rsi
0x14002a3c1  cmovnb  rdx, [rsp+2C0h+Block]; Src
0x14002a3c7  lea     rcx, [rsp+2C0h+var_268]; void *
0x14002a3cc  call    FilteredLogString
0x14002a3d1  nop
0x14002a3d2  or      r9, 0FFFFFFFFFFFFFFFFh
0x14002a3d6  xor     r8d, r8d
0x14002a3d9  mov     rdx, rax
0x14002a3dc  mov     rcx, rbx
0x14002a3df  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x14002a3e4  nop
  ... truncated ...
```
