# winreCreatePartition(winrePartitionParameters *,IVdsDisk *,_VDS_DISK_EXTENT &)

- ea: `0x180044178`
- end: `0x180044668`
- name: `?winreCreatePartition@@YAHPEAVwinrePartitionParameters@@PEAUIVdsDisk@@AEAU_VDS_DISK_EXTENT@@@Z`
- size: `1264`
- prototype: `__int64 __fastcall(struct winrePartitionParameters *, struct IVdsDisk *, struct _VDS_DISK_EXTENT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180045174`

## callees

- `0x1800059fc`
- `0x180036b34`
- `0x18003d8a0`
- `0x18003d92c`
- `0x180044178`
- `0x18005cee2`
- `0x18005cf30`
- `0x18005f010`

## import_xrefs

- `ole32!CoCreateGuid` at `0x180044291`
- `ole32!CoCreateGuid` at `0x180044338`
- `ole32!CoCreateGuid` at `0x180044291`
- `ole32!CoCreateGuid` at `0x180044338`

## string_xrefs

- `0x180044598`: `winreCreatePartition Extent does not meet requirements error`
- `0x180044251`: `winreCreatePartition GetProperties error hr = 0x%X `
- `0x1800442a0`: `winreCreatePartition CoCreateGuid error hr = 0x%X `
- `0x180044344`: `winreCreatePartition CoCreateGuid error hr = 0x%X `
- `0x18004458a`: `winreCreatePartition Unknown/unsupported partitioning style`
- `0x18004431d`: `winreCreatePartition QueryInterface IID_IVdsDiskPartitionMF error hr = 0x%X `
- `0x180044373`: `winreCreatePartition QueryInterface IID_IVdsAdvancedDisk error hr = 0x%X `
- `0x1800444ec`: `winreCreatePartition QueryInterface IID_IVdsAdvancedDisk error hr = 0x%X `
- `0x18004438d`: `winreCreatePartition Will create partition at offset: %I64u with size: %I64u `
- `0x1800443d0`: `winreCreatePartition CreatePartition error hr = 0x%X `
- `0x18004457a`: `winreCreatePartition failed to create partition with wait error hr = 0x%X hrAsync = 0x%X `
- `0x180044424`: `winreCreatePartition create partition successfully, actual offset is: 0x%I64X`
- `0x18004447e`: `winreCreatePartition FormatPartitionEx error hr = 0x%X `
- `0x180044548`: `winreCreatePartition FormatPartitionEx Wait error hr = 0x%X hrAsync = 0x%X `
- `0x1800445fa`: `winreCreatePartition returning %ls`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall winreCreatePartition(
        struct winrePartitionParameters *a1,
        struct IVdsDisk *a2,
        struct _VDS_DISK_EXTENT *a3)
{
  unsigned int v6; // esi
  HRESULT v7; // eax
  int v8; // ebx
  const wchar_t *v9; // rdx
  HRESULT Guid; // eax
  ULONGLONG ullSize; // r9
  ULONGLONG v12; // r8
  int v13; // eax
  __int64 v14; // r15
  int v15; // eax
  int v16; // eax
  int v17; // eax
  const wchar_t *v18; // r8
  int v20; // [rsp+70h] [rbp-98h] BYREF
  int v21; // [rsp+74h] [rbp-94h] BYREF
  __int64 v22; // [rsp+78h] [rbp-90h] BYREF
  __int64 v23; // [rsp+80h] [rbp-88h] BYREF
  __int64 v24; // [rsp+88h] [rbp-80h] BYREF
  __int64 v25; // [rsp+90h] [rbp-78h] BYREF
  __int64 v26; // [rsp+98h] [rbp-70h] BYREF
  __int128 v27; // [rsp+A0h] [rbp-68h] BYREF
  int v28; // [rsp+B0h] [rbp-58h]
  _OWORD v29[2]; // [rsp+B8h] [rbp-50h] BYREF
  int v30; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v31[4]; // [rsp+DCh] [rbp-2Ch] BYREF
  __int16 v32; // [rsp+E0h] [rbp-28h]
  __int64 v33; // [rsp+E2h] [rbp-26h]
  int v34; // [rsp+EAh] [rbp-1Eh]
  __int16 v35; // [rsp+EEh] [rbp-1Ah]
  __int128 v36; // [rsp+F0h] [rbp-18h]
  unsigned __int64 v37; // [rsp+100h] [rbp-8h]
  __int16 v38; // [rsp+108h] [rbp+0h]
  _OWORD v39[2]; // [rsp+158h] [rbp+50h] BYREF
  _BYTE v40[68]; // [rsp+178h] [rbp+70h] BYREF
  int v41; // [rsp+1BCh] [rbp+B4h]

  v22 = 0;
  v26 = 0;
  v25 = 0;
  v24 = 0;
  v23 = 0;
  v20 = 0;
  AsmCreatePartitionStart(a3->ullOffset, a3->ullSize, *((_QWORD *)a1 + 2));
  v6 = 1;
  if ( a3->type != VDS_DET_FREE
    || *(_QWORD *)&a3->volumeId.Data1 != *(_QWORD *)&GUID_NULL.Data1
    || *(_QWORD *)a3->volumeId.Data4 != *(_QWORD *)GUID_NULL.Data4
    || a3->ullSize < *((_QWORD *)a1 + 2) )
  {
    v8 = 0;
    UnattendLogW(2, L"winreCreatePartition Extent does not meet requirements error");
    goto LABEL_43;
  }
  memset_0(v40, 0, 0x80u);
  v7 = ((__int64 (__fastcall *)(struct IVdsDisk *, _BYTE *))a2->lpVtbl->GetProperties)(a2, v40);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = L"winreCreatePartition GetProperties error hr = 0x%X ";
LABEL_7:
    UnattendLogW(2, v9, (unsigned int)v7);
    goto LABEL_43;
  }
  memset_0(v31, 0, 0x74u);
  v30 = v41;
  if ( v41 == 2 )
  {
    Guid = CoCreateGuid((GUID *)((char *)a1 + 72));
    v8 = Guid;
    if ( Guid < 0 )
    {
      UnattendLogW(2, L"winreCreatePartition CoCreateGuid error hr = 0x%X ", (unsigned int)Guid);
      goto LABEL_43;
    }
    v36 = *(_OWORD *)((char *)a1 + 72);
    v32 = -17500;
    v33 = *(_QWORD *)((char *)&PARTITION_MSFT_RECOVERY_GUID.Data1 + 2);
    v34 = *(_DWORD *)&PARTITION_MSFT_RECOVERY_GUID.Data4[2];
    v35 = *(_WORD *)&PARTITION_MSFT_RECOVERY_GUID.Data4[6];
    v37 = 0x8000000000000001uLL;
    v38 = 0;
  }
  else
  {
    if ( v41 != 1 )
    {
      UnattendLogW(2, L"winreCreatePartition Unknown/unsupported partitioning style");
      goto LABEL_43;
    }
    v32 = 39;
    v7 = CoCreateGuid((GUID *)((char *)a1 + 72));
    v8 = v7;
    if ( v7 < 0 )
    {
      v9 = L"winreCreatePartition CoCreateGuid error hr = 0x%X ";
      goto LABEL_7;
    }
  }
  v7 = ((__int64 (__fastcall *)(struct IVdsDisk *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
         a2,
         &IID_IVdsDiskPartitionMF,
         &v25);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = L"winreCreatePartition QueryInterface IID_IVdsDiskPartitionMF error hr = 0x%X ";
    goto LABEL_7;
  }
  v7 = ((__int64 (__fastcall *)(struct IVdsDisk *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
         a2,
         &IID_IVdsAdvancedDisk,
         &v22);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = L"winreCreatePartition QueryInterface IID_IVdsAdvancedDisk error hr = 0x%X ";
    goto LABEL_7;
  }
  ullSize = *((_QWORD *)a1 + 2);
  if ( ullSize >= a3->ullSize )
    ullSize = a3->ullSize;
  UnattendLogW(
    0,
    L"winreCreatePartition Will create partition at offset: %I64u with size: %I64u ",
    a3->ullOffset,
    ullSize);
  v12 = *((_QWORD *)a1 + 2);
  if ( v12 >= a3->ullSize )
    v12 = a3->ullSize;
  v7 = (*(__int64 (__fastcall **)(__int64, ULONGLONG, ULONGLONG, int *, __int64 *))(*(_QWORD *)v22 + 40LL))(
         v22,
         a3->ullOffset,
         v12,
         &v30,
         &v24);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = L"winreCreatePartition CreatePartition error hr = 0x%X ";
    goto LABEL_7;
  }
  v21 = 0;
  memset(v29, 0, sizeof(v29));
  v13 = (*(__int64 (__fastcall **)(__int64, int *, _OWORD *))(*(_QWORD *)v24 + 32LL))(v24, &v21, v29);
  v8 = v13;
  if ( v13 < 0 || v21 < 0 )
  {
    UnattendLogW(
      2,
      L"winreCreatePartition failed to create partition with wait error hr = 0x%X hrAsync = 0x%X ",
      (unsigned int)v13,
      (unsigned int)v21);
    goto LABEL_43;
  }
  v14 = *((_QWORD *)&v29[0] + 1);
  UnattendLogW(
    0,
    L"winreCreatePartition create partition successfully, actual offset is: 0x%I64X",
    *((_QWORD *)&v29[0] + 1));
  v15 = (*(__int64 (__fastcall **)(__int64, __int64, const wchar_t *, _QWORD, _DWORD, const WCHAR *, _DWORD, int, _DWORD, __int64 *))(*(_QWORD *)v25 + 48LL))(
          v25,
          v14,
          L"NTFS",
          0,
          0,
          &cchOriginalDestLength,
          0,
          1,
          0,
          &v23);
  v8 = v15;
  if ( v15 < 0 )
    goto LABEL_28;
  memset(v39, 0, sizeof(v39));
  v8 = (*(__int64 (__fastcall **)(__int64, int *, _OWORD *))(*(_QWORD *)v23 + 32LL))(v23, &v20, v39);
  v16 = v20;
  if ( v8 >= 0 && v20 >= 0 )
  {
    if ( v30 == 1 )
    {
      v17 = ((__int64 (__fastcall *)(struct IVdsDisk *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
              a2,
              &IID_IVdsAdvancedDisk2,
              &v26);
      v8 = v17;
      if ( v17 < 0 )
      {
        UnattendLogW(2, L"winreCreatePartition QueryInterface IID_IVdsAdvancedDisk error hr = 0x%X ", (unsigned int)v17);
        goto LABEL_38;
      }
      v27 = 0;
      v28 = 0;
      LODWORD(v27) = 1;
      BYTE4(v27) = v32;
      v15 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int128 *))(*(_QWORD *)v26 + 24LL))(
              v26,
              v14,
              1,
              &v27);
      v8 = v15;
      if ( v15 < 0 )
      {
LABEL_28:
        UnattendLogW(2, L"winreCreatePartition FormatPartitionEx error hr = 0x%X ", (unsigned int)v15);
        goto LABEL_38;
      }
      v16 = v20;
    }
    *((_QWORD *)a1 + 11) = v14;
    *((_DWORD *)a1 + 38) = 1;
LABEL_48:
    v8 = v16;
    goto LABEL_49;
  }
  UnattendLogW(
    2,
    L"winreCreatePartition FormatPartitionEx Wait error hr = 0x%X hrAsync = 0x%X ",
    (unsigned int)v8,
    (unsigned int)v20);
LABEL_38:
  if ( v14 )
    (*(void (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v22 + 48LL))(v22, v14, 1, 1);
LABEL_43:
  v6 = 0;
  if ( *((_QWORD *)a1 + 9) != *(_QWORD *)&GUID_NULL.Data1 || *((_QWORD *)a1 + 10) != *(_QWORD *)GUID_NULL.Data4 )
    *(GUID *)((char *)a1 + 72) = GUID_NULL;
  if ( v8 >= 0 )
  {
    v16 = v20;
    goto LABEL_48;
  }
LABEL_49:
  AsmCreatePartitionEnd(v6, (unsigned int)v8);
  v18 = L"TRUE";
  if ( !v6 )
    v18 = L"FALSE";
  UnattendLogW(0, L"winreCreatePartition returning %ls", v18);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v26);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
  return v6;
}

```

## disassembly

```asm
0x180044178  mov     rax, rsp
0x18004417b  push    rbp
0x18004417c  push    rsi
0x18004417d  push    rdi
0x18004417e  push    r12
0x180044180  push    r13
0x180044182  push    r14
0x180044184  push    r15
0x180044186  lea     rbp, [rax-138h]
0x18004418d  sub     rsp, 200h
0x180044194  mov     qword ptr [rsp+230h+var_1D0], 0FFFFFFFFFFFFFFFEh
0x18004419d  mov     [rax+20h], rbx
0x1800441a1  mov     rax, cs:__security_cookie
0x1800441a8  xor     rax, rsp
0x1800441ab  mov     [rbp+130h+var_40], rax
0x1800441b2  mov     r15, r8
0x1800441b5  mov     r12, rdx
0x1800441b8  mov     r14, rcx
0x1800441bb  xor     r13d, r13d
0x1800441be  mov     [rsp+230h+var_1C0], r13
0x1800441c3  mov     [rbp+130h+var_1A0], r13
0x1800441c7  mov     [rbp+130h+var_1A8], r13
0x1800441cb  mov     [rbp+130h+var_1B0], r13
0x1800441cf  mov     [rsp+230h+var_1B8], r13
0x1800441d4  mov     dword ptr [rsp+230h+var_1C8], r13d
0x1800441d9  mov     r8, [rcx+10h]; unsigned __int64
0x1800441dd  mov     rdx, [r15+20h]; unsigned __int64
0x1800441e1  mov     rcx, [r15+18h]; unsigned __int64
0x1800441e5  call    ?AsmCreatePartitionStart@@YAX_K00@Z; AsmCreatePartitionStart(unsigned __int64,unsigned __int64,unsigned __int64)
0x1800441ea  lea     esi, [r13+1]
0x1800441ee  cmp     [r15+10h], esi
0x1800441f2  jnz     loc_180044595
0x1800441f8  mov     rax, [r15+28h]
0x1800441fc  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x180044203  jnz     loc_180044595
0x180044209  mov     rax, [r15+30h]
0x18004420d  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x180044214  jnz     loc_180044595
0x18004421a  mov     rax, [r14+10h]
0x18004421e  cmp     [r15+20h], rax
0x180044222  jb      loc_180044595
0x180044228  xor     edx, edx; Val
0x18004422a  lea     r8d, [rsi+7Fh]; Size
0x18004422e  lea     rcx, [rbp+130h+var_C0]; void *
0x180044232  call    memset_0
0x180044237  mov     rax, [r12]
0x18004423b  lea     rdx, [rbp+130h+var_C0]
0x18004423f  mov     rcx, r12
0x180044242  mov     rax, [rax+18h]
0x180044246  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004424b  mov     ebx, eax
0x18004424d  test    eax, eax
0x18004424f  jns     short loc_180044268
0x180044251  lea     rdx, aWinrecreatepar_4; "winreCreatePartition GetProperties erro"...
0x180044258  lea     ecx, [rsi+1]
0x18004425b  mov     r8d, eax
0x18004425e  call    UnattendLogW
0x180044263  jmp     loc_1800445A9
0x180044268  xor     edx, edx; Val
0x18004426a  lea     r8d, [rdx+74h]; Size
0x18004426e  lea     rcx, [rbp+130h+var_15C]; void *
0x180044272  call    memset_0
0x180044277  mov     eax, [rbp+130h+var_7C]
0x18004427d  mov     [rbp+130h+var_160], eax
0x180044280  mov     edi, 2
0x180044285  cmp     eax, edi
0x180044287  jnz     loc_180044326
0x18004428d  lea     rcx, [r14+48h]; pguid
0x180044291  call    cs:__imp_CoCreateGuid
0x180044297  mov     ebx, eax
0x180044299  test    eax, eax
0x18004429b  jns     short loc_1800442B6
0x18004429d  mov     r8d, eax
0x1800442a0  lea     rdx, aWinrecreatepar_9; "winreCreatePartition CoCreateGuid error"...
0x1800442a7  mov     ecx, edi
0x1800442a9  call    UnattendLogW
0x1800442ae  xor     r13d, r13d
0x1800442b1  jmp     loc_1800445A9
0x1800442b6  movups  xmm0, xmmword ptr [r14+48h]
0x1800442bb  movdqu  [rbp+130h+var_148], xmm0
0x1800442c0  mov     [rbp+130h+var_158], 0BBA4h
0x1800442c6  movsd   xmm0, qword ptr cs:PARTITION_MSFT_RECOVERY_GUID.Data1+2
0x1800442ce  movsd   [rbp+130h+var_156], xmm0
0x1800442d3  mov     eax, dword ptr cs:PARTITION_MSFT_RECOVERY_GUID.Data4+2
0x1800442d9  mov     [rbp+130h+var_14E], eax
0x1800442dc  movzx   eax, word ptr cs:PARTITION_MSFT_RECOVERY_GUID.Data4+6
0x1800442e3  mov     [rbp+130h+var_14A], ax
0x1800442e7  mov     rax, 8000000000000001h
0x1800442f1  mov     [rbp+130h+var_138], rax
0x1800442f5  xor     r13d, r13d
0x1800442f8  mov     [rbp+130h+var_130], r13w
0x1800442fd  mov     rax, [r12]
0x180044301  lea     r8, [rbp+130h+var_1A8]
0x180044305  lea     rdx, IID_IVdsDiskPartitionMF
0x18004430c  mov     rcx, r12
0x18004430f  mov     rax, [rax]
0x180044312  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044317  mov     ebx, eax
0x180044319  test    eax, eax
0x18004431b  jns     short loc_180044352
0x18004431d  lea     rdx, aWinrecreatepar_3; "winreCreatePartition QueryInterface IID"...
0x180044324  jmp     short loc_18004434B
0x180044326  cmp     eax, esi
0x180044328  jnz     loc_18004458A
0x18004432e  mov     [rbp+130h+var_158], 27h ; '''
0x180044334  lea     rcx, [r14+48h]; pguid
0x180044338  call    cs:__imp_CoCreateGuid
0x18004433e  mov     ebx, eax
0x180044340  test    eax, eax
0x180044342  jns     short loc_1800442FD
0x180044344  lea     rdx, aWinrecreatepar_9; "winreCreatePartition CoCreateGuid error"...
0x18004434b  mov     ecx, edi
0x18004434d  jmp     loc_18004425B
0x180044352  mov     rax, [r12]
0x180044356  lea     r8, [rsp+230h+var_1C0]
0x18004435b  lea     rdx, IID_IVdsAdvancedDisk
0x180044362  mov     rcx, r12
0x180044365  mov     rax, [rax]
0x180044368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004436d  mov     ebx, eax
0x18004436f  test    eax, eax
0x180044371  jns     short loc_18004437C
0x180044373  lea     rdx, aWinrecreatepar; "winreCreatePartition QueryInterface IID"...
0x18004437a  jmp     short loc_18004434B
0x18004437c  mov     r9, [r14+10h]
0x180044380  cmp     r9, [r15+20h]
0x180044384  cmovnb  r9, [r15+20h]
0x180044389  mov     r8, [r15+18h]
0x18004438d  lea     rdx, aWinrecreatepar_11; "winreCreatePartition Will create partit"...
0x180044394  xor     ecx, ecx
0x180044396  call    UnattendLogW
0x18004439b  mov     rcx, [rsp+230h+var_1C0]
0x1800443a0  mov     r8, [r14+10h]
0x1800443a4  mov     rax, [rcx]
0x1800443a7  cmp     r8, [r15+20h]
0x1800443ab  cmovnb  r8, [r15+20h]
0x1800443b0  lea     rdx, [rbp+130h+var_1B0]
0x1800443b4  mov     [rsp+230h+var_210], rdx
0x1800443b9  lea     r9, [rbp+130h+var_160]
0x1800443bd  mov     rdx, [r15+18h]
0x1800443c1  mov     rax, [rax+28h]
0x1800443c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800443ca  mov     ebx, eax
0x1800443cc  test    eax, eax
0x1800443ce  jns     short loc_1800443DC
0x1800443d0  lea     rdx, aWinrecreatepar_8; "winreCreatePartition CreatePartition er"...
0x1800443d7  jmp     loc_18004434B
0x1800443dc  mov     dword ptr [rsp+230h+var_1C8+4], r13d
0x1800443e1  xorps   xmm0, xmm0
0x1800443e4  movups  [rbp+130h+var_180], xmm0
0x1800443e8  movups  [rbp+130h+var_170], xmm0
0x1800443ec  mov     rcx, [rbp+130h+var_1B0]
0x1800443f0  mov     rax, [rcx]
0x1800443f3  lea     r8, [rbp+130h+var_180]
0x1800443f7  lea     rdx, [rsp+230h+var_1C8+4]
0x1800443fc  mov     rax, [rax+20h]
0x180044400  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044405  mov     ebx, eax
0x180044407  mov     r9d, dword ptr [rsp+230h+var_1C8+4]
0x18004440c  test    eax, eax
0x18004440e  js      loc_180044577
0x180044414  test    r9d, r9d
0x180044417  js      loc_180044577
0x18004441d  mov     r15, qword ptr [rbp+130h+var_180+8]
0x180044421  mov     r8, r15
0x180044424  lea     rdx, aWinrecreatepar_1; "winreCreatePartition create partition s"...
0x18004442b  xor     ecx, ecx
0x18004442d  call    UnattendLogW
0x180044432  mov     rcx, [rbp+130h+var_1A8]
0x180044436  mov     rax, [rcx]
0x180044439  xor     r9d, r9d
0x18004443c  lea     rdx, [rsp+230h+var_1B8]
0x180044441  mov     [rsp+48h], rdx
0x180044446  mov     dword ptr [rsp+230h+var_1F0], r13d
0x18004444b  mov     [rsp+230h+var_1F8], esi
0x18004444f  mov     [rsp+230h+var_200], r13d
0x180044454  lea     rdx, cchOriginalDestLength
0x18004445b  mov     qword ptr [rsp+230h+var_208], rdx
0x180044460  mov     dword ptr [rsp+230h+var_210], r13d
0x180044465  lea     r8, aNtfs; "NTFS"
0x18004446c  mov     rdx, r15
0x18004446f  mov     rax, [rax+30h]
0x180044473  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044478  mov     ebx, eax
0x18004447a  test    eax, eax
0x18004447c  jns     short loc_180044494
0x18004447e  lea     rdx, aWinrecreatepar_6; "winreCreatePartition FormatPartitionEx "...
0x180044485  mov     r8d, eax
0x180044488  mov     ecx, edi
0x18004448a  call    UnattendLogW
0x18004448f  jmp     loc_180044556
0x180044494  xorps   xmm0, xmm0
0x180044497  movups  [rbp+130h+var_E0], xmm0
0x18004449b  movups  [rbp+130h+var_D0], xmm0
0x18004449f  mov     rcx, [rsp+230h+var_1B8]
0x1800444a4  mov     rax, [rcx]
0x1800444a7  lea     r8, [rbp+130h+var_E0]
0x1800444ab  lea     rdx, [rsp+230h+var_1C8]
0x1800444b0  mov     rax, [rax+20h]
0x1800444b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800444b9  mov     ebx, eax
0x1800444bb  mov     eax, dword ptr [rsp+230h+var_1C8]
0x1800444bf  test    ebx, ebx
0x1800444c1  js      short loc_180044542
0x1800444c3  test    eax, eax
0x1800444c5  js      short loc_180044542
0x1800444c7  cmp     [rbp+130h+var_160], esi
0x1800444ca  jnz     short loc_180044532
0x1800444cc  mov     rax, [r12]
0x1800444d0  lea     r8, [rbp+130h+var_1A0]
0x1800444d4  lea     rdx, IID_IVdsAdvancedDisk2
0x1800444db  mov     rcx, r12
0x1800444de  mov     rax, [rax]
0x1800444e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800444e6  mov     ebx, eax
0x1800444e8  test    eax, eax
0x1800444ea  jns     short loc_1800444F5
0x1800444ec  lea     rdx, aWinrecreatepar; "winreCreatePartition QueryInterface IID"...
0x1800444f3  jmp     short loc_180044485
0x1800444f5  xorps   xmm0, xmm0
0x1800444f8  xor     eax, eax
0x1800444fa  movups  [rbp+130h+var_198], xmm0
0x1800444fe  mov     [rbp+130h+var_188], eax
0x180044501  mov     dword ptr [rbp+130h+var_198], esi
0x180044504  mov     al, byte ptr [rbp+130h+var_158]
0x180044507  mov     byte ptr [rbp+130h+var_198+4], al
0x18004450a  mov     rcx, [rbp+130h+var_1A0]
0x18004450e  mov     rax, [rcx]
0x180044511  lea     r9, [rbp+130h+var_198]
0x180044515  mov     r8d, esi
0x180044518  mov     rdx, r15
0x18004451b  mov     rax, [rax+18h]
0x18004451f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044524  mov     ebx, eax
0x180044526  test    eax, eax
0x180044528  js      loc_18004447E
0x18004452e  mov     eax, dword ptr [rsp+230h+var_1C8]
0x180044532  mov     [r14+58h], r15
0x180044536  mov     [r14+98h], esi
0x18004453d  jmp     loc_1800445DB
0x180044542  mov     r9d, eax
0x180044545  mov     r8d, ebx
0x180044548  lea     rdx, aWinrecreatepar_2; "winreCreatePartition FormatPartitionEx "...
0x18004454f  mov     ecx, edi
0x180044551  call    UnattendLogW
0x180044556  test    r15, r15
0x180044559  jz      short loc_1800445A9
0x18004455b  mov     rcx, [rsp+230h+var_1C0]
0x180044560  mov     rax, [rcx]
0x180044563  mov     r9d, esi
0x180044566  mov     r8d, esi
0x180044569  mov     rdx, r15
0x18004456c  mov     rax, [rax+30h]
0x180044570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044575  jmp     short loc_1800445A9
0x180044577  mov     r8d, eax
0x18004457a  lea     rdx, aWinrecreatepar_0; "winreCreatePartition failed to create p"...
0x180044581  mov     ecx, edi
0x180044583  call    UnattendLogW
0x180044588  jmp     short loc_1800445A9
0x18004458a  lea     rdx, aWinrecreatepar_5; "winreCreatePartition Unknown/unsupporte"...
0x180044591  mov     ecx, edi
0x180044593  jmp     short loc_1800445A4
0x180044595  mov     ebx, r13d
0x180044598  lea     rdx, aWinrecreatepar_7; "winreCreatePartition Extent does not me"...
0x18004459f  mov     ecx, 2
0x1800445a4  call    UnattendLogW
0x1800445a9  mov     esi, r13d
0x1800445ac  mov     rax, [r14+48h]
0x1800445b0  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800445b7  jnz     short loc_1800445C6
0x1800445b9  mov     rax, [r14+50h]
0x1800445bd  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800445c4  jz      short loc_1800445D3
0x1800445c6  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800445cd  movdqu  xmmword ptr [r14+48h], xmm0
0x1800445d3  test    ebx, ebx
0x1800445d5  js      short loc_1800445DD
0x1800445d7  mov     eax, dword ptr [rsp+230h+var_1C8]
0x1800445db  mov     ebx, eax
0x1800445dd  mov     edx, ebx; unsigned int
0x1800445df  mov     ecx, esi; int
0x1800445e1  call    ?AsmCreatePartitionEnd@@YAXHK@Z; AsmCreatePartitionEnd(int,ulong)
0x1800445e6  lea     rax, aFalse_0; "FALSE"
0x1800445ed  lea     r8, aTrue_0; "TRUE"
0x1800445f4  test    esi, esi
0x1800445f6  cmovz   r8, rax
0x1800445fa  lea     rdx, aWinrecreatepar_10; "winreCreatePartition returning %ls"
0x180044601  xor     ecx, ecx
0x180044603  call    UnattendLogW
0x180044608  nop
0x180044609  lea     rcx, [rsp+230h+var_1B8]
0x18004460e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180044613  nop
0x180044614  lea     rcx, [rbp+130h+var_1B0]
0x180044618  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004461d  nop
0x18004461e  lea     rcx, [rbp+130h+var_1A8]
0x180044622  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180044627  nop
  ... truncated ...
```
