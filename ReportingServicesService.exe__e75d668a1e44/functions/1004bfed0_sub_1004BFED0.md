# sub_1004BFED0

- ea: `0x1004bfed0`
- end: `0x1004c0371`
- name: `sub_1004BFED0`
- size: `1185`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x10040e470`
- `0x100411180`
- `0x1004496c0`
- `0x100450cc0`
- `0x1004ab010`
- `0x1004bfed0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1004bffe5`
- `KERNEL32!GetLastError` at `0x1004bffe5`
- `KERNEL32!TlsGetValue` at `0x1004bff01`
- `KERNEL32!TlsGetValue` at `0x1004bff20`
- `KERNEL32!TlsGetValue` at `0x1004bff37`
- `KERNEL32!TlsGetValue` at `0x1004bff56`
- `KERNEL32!TlsGetValue` at `0x1004c001b`
- `KERNEL32!TlsGetValue` at `0x1004c004a`
- `KERNEL32!TlsGetValue` at `0x1004c0110`
- `KERNEL32!TlsGetValue` at `0x1004c0142`
- `KERNEL32!TlsGetValue` at `0x1004c01a1`
- `KERNEL32!TlsGetValue` at `0x1004c01d3`
- `KERNEL32!TlsGetValue` at `0x1004c02b1`
- `KERNEL32!TlsGetValue` at `0x1004c02e3`
- `KERNEL32!TlsGetValue` at `0x1004c0327`
- `KERNEL32!TlsGetValue` at `0x1004c0347`
- `KERNEL32!TlsGetValue` at `0x1004bff01`
- `KERNEL32!TlsGetValue` at `0x1004bff20`
- `KERNEL32!TlsGetValue` at `0x1004bff37`
- `KERNEL32!TlsGetValue` at `0x1004bff56`
- `KERNEL32!TlsGetValue` at `0x1004c001b`
- `KERNEL32!TlsGetValue` at `0x1004c004a`
- `KERNEL32!TlsGetValue` at `0x1004c0110`
- `KERNEL32!TlsGetValue` at `0x1004c0142`
- `KERNEL32!TlsGetValue` at `0x1004c01a1`
- `KERNEL32!TlsGetValue` at `0x1004c01d3`
- `KERNEL32!TlsGetValue` at `0x1004c02b1`
- `KERNEL32!TlsGetValue` at `0x1004c02e3`
- `KERNEL32!TlsGetValue` at `0x1004c0327`
- `KERNEL32!TlsGetValue` at `0x1004c0347`
- `KERNEL32!GetQueuedCompletionStatus` at `0x1004bffdb`
- `KERNEL32!GetQueuedCompletionStatus` at `0x1004bffdb`

## string_xrefs

- `0x1004c0007`: `ERROR: IO completion 0x%p returned without overlapped structure\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall __noreturn sub_1004BFED0(__int64 a1)
{
  __int64 v1; // rsi
  _QWORD *Value; // rax
  int v3; // edx
  __int64 v4; // rcx
  _QWORD *v5; // rax
  int v6; // edx
  __int64 v7; // rcx
  int v8; // r8d
  int v9; // r9d
  DWORD LastError; // ebx
  _QWORD *v11; // rax
  int v12; // edx
  __int64 v13; // rcx
  __int64 v14; // rdx
  unsigned int j; // ecx
  __int64 v16; // rax
  __int64 v17; // rax
  _QWORD *v18; // rax
  int v19; // edx
  __int64 v20; // rcx
  _QWORD *v21; // rax
  int v22; // edx
  __int64 v23; // rcx
  __int64 v24; // r8
  unsigned int i; // edx
  __int64 v26; // rax
  __int64 v27; // rax
  _QWORD *v28; // rax
  int v29; // edx
  __int64 v30; // rcx
  _QWORD *v31; // rax
  int v32; // edx
  __int64 v33; // rcx
  __int64 *v34; // rbp
  DWORD v35; // ecx
  _QWORD *v36; // rax
  int v37; // edx
  __int64 v38; // rcx
  DWORD v39; // ecx
  __int64 v40; // rcx
  __int64 v41; // [rsp+0h] [rbp-1F8h] BYREF
  LPOVERLAPPED Overlapped; // [rsp+40h] [rbp-1B8h] BYREF
  unsigned int v43; // [rsp+48h] [rbp-1B0h]
  unsigned int v44; // [rsp+4Ch] [rbp-1ACh]
  unsigned __int64 CompletionKey; // [rsp+50h] [rbp-1A8h] BYREF
  _QWORD *v46; // [rsp+60h] [rbp-198h]
  unsigned __int64 v47; // [rsp+68h] [rbp-190h]
  __int64 v48; // [rsp+70h] [rbp-188h]
  __int64 v49; // [rsp+78h] [rbp-180h]
  _QWORD *v50; // [rsp+80h] [rbp-178h]
  _QWORD *v51; // [rsp+88h] [rbp-170h]
  unsigned __int64 v52; // [rsp+90h] [rbp-168h]
  __int64 v53; // [rsp+98h] [rbp-160h]
  __int64 v54; // [rsp+A0h] [rbp-158h]
  _QWORD *v55; // [rsp+A8h] [rbp-150h]
  __int64 v56; // [rsp+B8h] [rbp-140h]
  __int64 v57; // [rsp+C0h] [rbp-138h] BYREF
  HANDLE v58; // [rsp+D8h] [rbp-120h]
  __int64 v59; // [rsp+E0h] [rbp-118h]
  _QWORD *v60; // [rsp+E8h] [rbp-110h]
  __int64 v61; // [rsp+F0h] [rbp-108h]
  __int64 v62; // [rsp+F8h] [rbp-100h]
  __int64 v63; // [rsp+100h] [rbp-F8h]
  __int64 v64; // [rsp+108h] [rbp-F0h]
  _QWORD *v65; // [rsp+110h] [rbp-E8h]
  __int64 v66; // [rsp+118h] [rbp-E0h]
  __int64 v67; // [rsp+120h] [rbp-D8h]
  _QWORD *v68; // [rsp+128h] [rbp-D0h]
  __int64 v69; // [rsp+130h] [rbp-C8h]
  __int64 v70; // [rsp+138h] [rbp-C0h]
  __int64 v71; // [rsp+140h] [rbp-B8h]
  __int64 v72; // [rsp+148h] [rbp-B0h]
  _QWORD *v73; // [rsp+150h] [rbp-A8h]
  __int64 v74; // [rsp+158h] [rbp-A0h]
  __int64 v75; // [rsp+190h] [rbp-68h]
  char v76; // [rsp+198h] [rbp-60h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+200h] [rbp+8h] BYREF
  DWORD v78; // [rsp+208h] [rbp+10h]

  v75 = -2;
  v1 = a1;
  v56 = a1;
  Overlapped = 0;
  Value = TlsGetValue(dwTlsIndex);
  if ( !Value || !Value[32] )
  {
    sub_100450CC0(v4, v3);
    Value = TlsGetValue(dwTlsIndex);
  }
  *(_QWORD *)(v1 + 8) = Value[32];
  v5 = TlsGetValue(dwTlsIndex);
  if ( !v5 || !v5[32] )
  {
    sub_100450CC0(v7, v6);
    v5 = TlsGetValue(dwTlsIndex);
  }
  *(_DWORD *)(v5[32] + 712LL) |= 0x200000u;
  while ( 2 )
  {
    try
    {
      sub_10040E470((unsigned int)&v76, v6, v8, v9, (__int64)&loc_100410990, 0);
      *(_DWORD *)(v1 + 4) = 0;
      while ( 1 )
      {
        Overlapped = 0;
        NumberOfBytesTransferred = 0;
        LastError = 0;
        v78 = 0;
        v58 = *(HANDLE *)(v1 + 24);
        if ( !GetQueuedCompletionStatus(v58, &NumberOfBytesTransferred, &CompletionKey, &Overlapped, 0xFFFFFFFF) )
        {
          LastError = GetLastError();
          v78 = LastError;
        }
        if ( Overlapped )
        {
          HIDWORD(Overlapped[2].Internal) = LastError;
          LODWORD(Overlapped[2].Internal) = NumberOfBytesTransferred;
          _InterlockedIncrement((volatile signed __int32 *)v1);
          *(_DWORD *)(v1 + 4) = 1;
          ((void (__fastcall *)(LPOVERLAPPED))Overlapped[2].InternalHigh)(Overlapped);
          *(_DWORD *)(v1 + 4) = 0;
          v21 = TlsGetValue(dwTlsIndex);
          v51 = v21;
          if ( !v21 || (v23 = v21[32], (v67 = v23) == 0) )
          {
            sub_100450CC0(v23, v22);
            v21 = TlsGetValue(dwTlsIndex);
            v68 = v21;
            v51 = v21;
          }
          v69 = v21[32];
          v24 = *(_QWORD *)(v69 + 512);
          v70 = v24;
          v53 = v24;
          for ( i = 0; ; ++i )
          {
            v44 = i;
            if ( i >= 0x40 )
              break;
            v26 = *(_QWORD *)(v24 + 8LL * i + 432);
            v54 = v26;
            if ( v26 )
            {
              v52 = v26 / 0x2000;
              v71 = v26 / -8192;
              _InterlockedExchangeAdd64((volatile signed __int64 *)&xmmword_1006D5CC0[52 * i + 22] + 1, v26 / -8192);
              _InterlockedExchangeAdd64((volatile signed __int64 *)&xmmword_1006D5CC0[52 * i + 28] + 1, v52);
              v24 = v53;
              v27 = v54;
              *(_QWORD *)(v53 + 376) -= v54;
              *(_QWORD *)(v24 + 8LL * i + 432) -= v27;
              *(_QWORD *)(v24 + 424) -= v27;
              i = v44;
            }
          }
          v28 = TlsGetValue(dwTlsIndex);
          v55 = v28;
          if ( !v28 || (v30 = v28[32], (v72 = v30) == 0) )
          {
            sub_100450CC0(v30, v29);
            v28 = TlsGetValue(dwTlsIndex);
            v73 = v28;
            v55 = v28;
          }
          v74 = v28[32];
          sub_1004496C0();
        }
        else
        {
          off_10066A528(L"ERROR: IO completion 0x%p returned without overlapped structure\n", CompletionKey);
          v11 = TlsGetValue(dwTlsIndex);
          v46 = v11;
          if ( !v11 || (v13 = v11[32], (v59 = v13) == 0) )
          {
            sub_100450CC0(v13, v12);
            v11 = TlsGetValue(dwTlsIndex);
            v60 = v11;
            v46 = v11;
          }
          v61 = v11[32];
          v14 = *(_QWORD *)(v61 + 512);
          v62 = v14;
          v48 = v14;
          for ( j = 0; ; ++j )
          {
            v43 = j;
            if ( j >= 0x40 )
              break;
            v16 = *(_QWORD *)(v14 + 8LL * j + 432);
            v49 = v16;
            if ( v16 )
            {
              v47 = v16 / 0x2000;
              v63 = v16 / -8192;
              _InterlockedExchangeAdd64((volatile signed __int64 *)&xmmword_1006D5CC0[52 * j + 22] + 1, v16 / -8192);
              _InterlockedExchangeAdd64((volatile signed __int64 *)&xmmword_1006D5CC0[52 * j + 28] + 1, v47);
              v14 = v48;
              v17 = v49;
              *(_QWORD *)(v48 + 376) -= v49;
              *(_QWORD *)(v14 + 8LL * j + 432) -= v17;
              *(_QWORD *)(v14 + 424) -= v17;
              j = v43;
            }
          }
          v18 = TlsGetValue(dwTlsIndex);
          v50 = v18;
          if ( !v18 || (v20 = v18[32], (v64 = v20) == 0) )
          {
            sub_100450CC0(v20, v19);
            v18 = TlsGetValue(dwTlsIndex);
            v65 = v18;
            v50 = v18;
          }
          v66 = v18[32];
          sub_1004496C0();
        }
      }
    }
    catch ( SQLError v57 )
    {
      v34 = &v41;
      try
      {
        sub_100410A80(v34 + 48, v34 + 24);
        v35 = dwTlsIndex;
        *((_DWORD *)v34 + 132) = dwTlsIndex;
        v36 = TlsGetValue(v35);
        v34[22] = (__int64)v36;
        if ( !v36 || (v38 = v36[32], (v34[44] = v38) == 0) )
        {
          sub_100450CC0(v38, v37);
          v39 = dwTlsIndex;
          *((_DWORD *)v34 + 134) = dwTlsIndex;
          v36 = TlsGetValue(v39);
          v34[45] = (__int64)v36;
          v34[22] = (__int64)v36;
        }
        v40 = v36[32];
        v34[46] = v40;
        v34[47] = *(_QWORD *)(v40 + 192);
        *((_DWORD *)v34 + 22) = *((_DWORD *)v34 + 51);
        *((_DWORD *)v34 + 23) = *((_DWORD *)v34 + 49);
        off_10066A528(
          L"ERROR: IO completion routine raised unhandled exception.  Major: %d, Minor %d, Severity %d, State %d, IO CompR"
           "equest 0x%p, IO CompKey 0x%p, Address: 0x%p\n",
          (unsigned int)(*((_DWORD *)v34 + 48) / 100),
          (unsigned int)(*((_DWORD *)v34 + 48) % 100));
        sub_100410B30(v34 + 48);
      }
      catch ( ShortStackException )
      {
        v31 = TlsGetValue(dwTlsIndex);
        if ( !v31 || !v31[32] )
        {
          sub_100450CC0(v33, v32);
          v31 = TlsGetValue(dwTlsIndex);
        }
        if ( !*(_DWORD *)(v31[32] + 500LL) )
          return;
        sub_100411180();
        return;
      }
      v1 = v56;
      continue;
    }
    break;
  }
}

```

## disassembly

```asm
0x1004bfed0  push    rbx
0x1004bfed2  push    rsi
0x1004bfed3  push    rdi
0x1004bfed4  push    r14
0x1004bfed6  sub     rsp, 1D8h
0x1004bfedd  mov     [rsp+1F8h+var_68], 0FFFFFFFFFFFFFFFEh
0x1004bfee9  mov     rsi, rcx
0x1004bfeec  mov     [rsp+1F8h+var_140], rcx
0x1004bfef4  xor     edi, edi
0x1004bfef6  mov     [rsp+1F8h+Overlapped], rdi
0x1004bfefb  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x1004bff01  call    cs:TlsGetValue
0x1004bff07  test    rax, rax
0x1004bff0a  jz      short loc_1004BFF15
0x1004bff0c  cmp     [rax+100h], rdi
0x1004bff13  jnz     short loc_1004BFF26
0x1004bff15  call    sub_100450CC0
0x1004bff1a  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x1004bff20  call    cs:TlsGetValue
0x1004bff26  mov     rax, [rax+100h]
0x1004bff2d  mov     [rsi+8], rax
0x1004bff31  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x1004bff37  call    cs:TlsGetValue
0x1004bff3d  test    rax, rax
0x1004bff40  jz      short loc_1004BFF4B
0x1004bff42  cmp     [rax+100h], rdi
0x1004bff49  jnz     short loc_1004BFF5C
0x1004bff4b  call    sub_100450CC0
0x1004bff50  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x1004bff56  call    cs:TlsGetValue
0x1004bff5c  mov     rax, [rax+100h]
0x1004bff63  or      dword ptr [rax+2C8h], 200000h
0x1004bff6d  nop     dword ptr [rax]
0x1004bff70  mov     [rsp+1F8h+var_1D0], rdi
0x1004bff75  lea     rax, loc_100410990
0x1004bff7c  mov     qword ptr [rsp+1F8h+dwMilliseconds], rax
0x1004bff81  lea     rcx, [rsp+1F8h+var_60]
0x1004bff89  call    sub_10040E470
0x1004bff8e  nop
0x1004bff8f  mov     [rsi+4], edi
0x1004bff92  lea     r14, xmmword_1006D5CC0
0x1004bff99  nop     dword ptr [rax+00000000h]
0x1004bffa0  mov     [rsp+1F8h+Overlapped], rdi
0x1004bffa5  mov     [rsp+1F8h+NumberOfBytesTransferred], edi
0x1004bffac  mov     ebx, edi
0x1004bffae  mov     [rsp+1F8h+arg_8], ebx
0x1004bffb5  mov     rcx, [rsi+18h]; CompletionPort
0x1004bffb9  mov     [rsp+1F8h+var_120], rcx
0x1004bffc1  mov     [rsp+1F8h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x1004bffc9  lea     r9, [rsp+1F8h+Overlapped]; lpOverlapped
0x1004bffce  lea     r8, [rsp+1F8h+CompletionKey]; lpCompletionKey
0x1004bffd3  lea     rdx, [rsp+1F8h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x1004bffdb  call    cs:GetQueuedCompletionStatus
0x1004bffe1  test    eax, eax
0x1004bffe3  jnz     short loc_1004BFFF4
0x1004bffe5  call    cs:GetLastError
0x1004bffeb  mov     ebx, eax
0x1004bffed  mov     [rsp+1F8h+arg_8], eax
0x1004bfff4  mov     rax, [rsp+1F8h+Overlapped]
0x1004bfff9  test    rax, rax
0x1004bfffc  jnz     loc_1004C0171
0x1004c0002  mov     rdx, [rsp+1F8h+CompletionKey]
0x1004c0007  lea     rcx, aErrorIoComplet_0; "ERROR: IO completion 0x%p returned with"...
0x1004c000e  call    cs:off_10066A528
0x1004c0014  nop
0x1004c0015  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x1004c001b  call    cs:TlsGetValue
0x1004c0021  mov     [rsp+1F8h+var_198], rax
0x1004c0026  test    rax, rax
0x1004c0029  jz      short loc_1004C003F
0x1004c002b  mov     rcx, [rax+100h]
0x1004c0032  mov     [rsp+1F8h+var_118], rcx
0x1004c003a  test    rcx, rcx
0x1004c003d  jnz     short loc_1004C005D
0x1004c003f  call    sub_100450CC0
0x1004c0044  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x1004c004a  call    cs:TlsGetValue
0x1004c0050  mov     [rsp+1F8h+var_110], rax
0x1004c0058  mov     [rsp+1F8h+var_198], rax
0x1004c005d  mov     rax, [rax+100h]
0x1004c0064  mov     [rsp+1F8h+var_108], rax
0x1004c006c  mov     rdx, [rax+200h]
0x1004c0073  mov     [rsp+1F8h+var_100], rdx
0x1004c007b  mov     [rsp+1F8h+var_188], rdx
0x1004c0080  mov     ecx, edi
0x1004c0082  mov     [rsp+1F8h+var_1B0], ecx
0x1004c0086  cmp     ecx, 40h ; '@'
0x1004c0089  jnb     short loc_1004C010A
0x1004c008b  mov     r8d, ecx
0x1004c008e  mov     rax, [rdx+r8*8+1B0h]
0x1004c0096  mov     [rsp+1F8h+var_180], rax
0x1004c009b  test    rax, rax
0x1004c009e  jz      short loc_1004C0103
0x1004c00a0  cqo
0x1004c00a2  and     edx, 1FFFh
0x1004c00a8  add     rax, rdx
0x1004c00ab  sar     rax, 0Dh
0x1004c00af  mov     [rsp+1F8h+var_190], rax
0x1004c00b4  imul    rcx, r8, 340h
0x1004c00bb  neg     rax
0x1004c00be  mov     [rsp+1F8h+var_F8], rax
0x1004c00c6  lock xadd [rcx+r14+168h], rax
0x1004c00d0  mov     rax, [rsp+1F8h+var_190]
0x1004c00d5  lock xadd [rcx+r14+1C8h], rax
0x1004c00df  mov     rdx, [rsp+1F8h+var_188]
0x1004c00e4  mov     rax, [rsp+1F8h+var_180]
0x1004c00e9  sub     [rdx+178h], rax
0x1004c00f0  sub     [rdx+r8*8+1B0h], rax
0x1004c00f8  sub     [rdx+1A8h], rax
0x1004c00ff  mov     ecx, [rsp+1F8h+var_1B0]
0x1004c0103  inc     ecx
0x1004c0105  jmp     loc_1004C0082
0x1004c010a  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x1004c0110  call    cs:TlsGetValue
0x1004c0116  mov     [rsp+1F8h+var_178], rax
0x1004c011e  test    rax, rax
0x1004c0121  jz      short loc_1004C0137
0x1004c0123  mov     rcx, [rax+100h]
0x1004c012a  mov     [rsp+1F8h+var_F0], rcx
0x1004c0132  test    rcx, rcx
0x1004c0135  jnz     short loc_1004C0158
0x1004c0137  call    sub_100450CC0
0x1004c013c  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x1004c0142  call    cs:TlsGetValue
0x1004c0148  mov     [rsp+1F8h+var_E8], rax
0x1004c0150  mov     [rsp+1F8h+var_178], rax
0x1004c0158  mov     rcx, [rax+100h]
0x1004c015f  mov     [rsp+1F8h+var_E0], rcx
0x1004c0167  call    sub_1004496C0
0x1004c016c  jmp     loc_1004BFFA0
0x1004c0171  mov     [rax+44h], ebx
0x1004c0174  mov     rcx, [rsp+1F8h+Overlapped]
0x1004c0179  mov     eax, [rsp+1F8h+NumberOfBytesTransferred]
0x1004c0180  mov     [rcx+40h], eax
0x1004c0183  lock inc dword ptr [rsi]
0x1004c0186  mov     dword ptr [rsi+4], 1
0x1004c018d  mov     rax, [rsp+1F8h+Overlapped]
0x1004c0192  mov     rcx, rax
0x1004c0195  call    qword ptr [rax+48h]
0x1004c0198  mov     [rsi+4], edi
0x1004c019b  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x1004c01a1  call    cs:TlsGetValue
0x1004c01a7  mov     [rsp+1F8h+var_170], rax
0x1004c01af  test    rax, rax
0x1004c01b2  jz      short loc_1004C01C8
0x1004c01b4  mov     rcx, [rax+100h]
0x1004c01bb  mov     [rsp+1F8h+var_D8], rcx
0x1004c01c3  test    rcx, rcx
0x1004c01c6  jnz     short loc_1004C01E9
0x1004c01c8  call    sub_100450CC0
0x1004c01cd  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x1004c01d3  call    cs:TlsGetValue
0x1004c01d9  mov     [rsp+1F8h+var_D0], rax
0x1004c01e1  mov     [rsp+1F8h+var_170], rax
0x1004c01e9  mov     rax, [rax+100h]
0x1004c01f0  mov     [rsp+1F8h+var_C8], rax
0x1004c01f8  mov     r8, [rax+200h]
0x1004c01ff  mov     [rsp+1F8h+var_C0], r8
0x1004c0207  mov     [rsp+1F8h+var_160], r8
0x1004c020f  mov     edx, edi
0x1004c0211  mov     [rsp+1F8h+var_1AC], edx
0x1004c0215  cmp     edx, 40h ; '@'
0x1004c0218  jnb     loc_1004C02AB
0x1004c021e  mov     ecx, edx
0x1004c0220  mov     rax, [r8+rcx*8+1B0h]
0x1004c0228  mov     [rsp+1F8h+var_158], rax
0x1004c0230  test    rax, rax
0x1004c0233  jz      short loc_1004C02A4
0x1004c0235  cqo
0x1004c0237  and     edx, 1FFFh
0x1004c023d  add     rax, rdx
0x1004c0240  sar     rax, 0Dh
0x1004c0244  mov     [rsp+1F8h+var_168], rax
0x1004c024c  imul    rdx, rcx, 340h
0x1004c0253  neg     rax
0x1004c0256  mov     [rsp+1F8h+var_B8], rax
0x1004c025e  lock xadd [rdx+r14+168h], rax
0x1004c0268  mov     rax, [rsp+1F8h+var_168]
0x1004c0270  lock xadd [rdx+r14+1C8h], rax
0x1004c027a  mov     r8, [rsp+1F8h+var_160]
0x1004c0282  mov     rax, [rsp+1F8h+var_158]
0x1004c028a  sub     [r8+178h], rax
0x1004c0291  sub     [r8+rcx*8+1B0h], rax
0x1004c0299  sub     [r8+1A8h], rax
0x1004c02a0  mov     edx, [rsp+1F8h+var_1AC]
0x1004c02a4  inc     edx
0x1004c02a6  jmp     loc_1004C0211
0x1004c02ab  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x1004c02b1  call    cs:TlsGetValue
0x1004c02b7  mov     [rsp+1F8h+var_150], rax
0x1004c02bf  test    rax, rax
0x1004c02c2  jz      short loc_1004C02D8
0x1004c02c4  mov     rcx, [rax+100h]
0x1004c02cb  mov     [rsp+1F8h+var_B0], rcx
0x1004c02d3  test    rcx, rcx
0x1004c02d6  jnz     short loc_1004C02F9
0x1004c02d8  call    sub_100450CC0
0x1004c02dd  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x1004c02e3  call    cs:TlsGetValue
0x1004c02e9  mov     [rsp+1F8h+var_A8], rax
0x1004c02f1  mov     [rsp+1F8h+var_150], rax
0x1004c02f9  mov     rcx, [rax+100h]
0x1004c0300  mov     [rsp+1F8h+var_A0], rcx
0x1004c0308  call    sub_1004496C0
0x1004c030d  jmp     loc_1004BFFA0
0x1004c0312  xor     edi, edi
0x1004c0314  mov     rsi, [rsp+1F8h+var_140]
0x1004c031c  jmp     loc_1004BFF70
0x1004c0321  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x1004c0327  call    cs:TlsGetValue
0x1004c032d  test    rax, rax
0x1004c0330  jz      short loc_1004C033C
0x1004c0332  cmp     qword ptr [rax+100h], 0
0x1004c033a  jnz     short loc_1004C034D
0x1004c033c  call    sub_100450CC0
0x1004c0341  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x1004c0347  call    cs:TlsGetValue
0x1004c034d  mov     rcx, [rax+100h]
0x1004c0354  cmp     dword ptr [rcx+1F4h], 0
0x1004c035b  jz      short loc_1004C0362
0x1004c035d  call    sub_100411180
0x1004c0362  xor     eax, eax
0x1004c0364  add     rsp, 1D8h
0x1004c036b  pop     r14
0x1004c036d  pop     rdi
0x1004c036e  pop     rsi
0x1004c036f  pop     rbx
0x1004c0370  retn
```
