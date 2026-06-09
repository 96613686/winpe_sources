# NgcHandler::RsaExportPublicKey(void *,_GUID const &,ushort const *,ushort const *,ushort const *,uchar * *,ulong *,uchar * *,ulong *)

- ea: `0x18000e230`
- end: `0x18000ea39`
- name: `?RsaExportPublicKey@NgcHandler@@QEAAJPEAXAEBU_GUID@@PEBG22PEAPEAEPEAK34@Z`
- size: `2057`
- prototype: `__int64 __fastcall(NgcHandler *__hidden this, void *, const struct _GUID *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000e11c`

## callees

- `0x18000a8e0`
- `0x18000b490`
- `0x18000c7e0`
- `0x18000e230`
- `0x18002c640`
- `0x18002d500`
- `0x180080010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e8cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e8cf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e8e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e8e3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000e375`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000e4e2`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000e780`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000e8c3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000e375`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000e4e2`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000e780`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000e8c3`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000e2aa`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000e2aa`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000e387`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000e510`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000e953`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000ea02`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000e387`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000e510`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000e953`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000ea02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e625`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e64b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e66b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e687`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e79c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e7b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e8ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e91b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e9ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e9ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e625`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e64b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e66b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e687`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e79c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e7b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e8ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e91b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e9ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e9ca`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall NgcHandler::RsaExportPublicKey(
        __int64 (__fastcall **this)(__int128 *, __int64 **),
        void *a2,
        const struct _GUID *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        const unsigned __int16 *a6,
        unsigned __int8 **a7,
        unsigned int *a8,
        unsigned __int8 **a9,
        unsigned int *a10)
{
  HRESULT v12; // eax
  int v13; // esi
  bool v14; // di
  __int64 *v16; // rcx
  __int64 *v17; // rcx
  __int64 *v18; // rcx
  __int64 *v19; // rcx
  __int64 v20; // rax
  __int128 *v21; // r8
  int v22; // r15d
  void *v23; // rcx
  void *v24; // rcx
  void *v25; // rcx
  void *v26; // rcx
  __int64 *v27; // rcx
  unsigned __int8 *v28; // rax
  unsigned __int8 *v29; // rsi
  void *v30; // rcx
  void *v31; // rcx
  __int64 *v32; // rcx
  unsigned __int8 *v33; // rax
  unsigned __int8 *v34; // r14
  HANDLE ProcessHeap; // rax
  void *v36; // rcx
  void *v37; // rcx
  __int64 *v38; // rcx
  void *v39; // rcx
  void *v40; // rcx
  __int64 *v41; // rcx
  __int64 *v42; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID Src; // [rsp+50h] [rbp-B0h] BYREF
  size_t size; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int8 **v46; // [rsp+60h] [rbp-A0h] BYREF
  const unsigned __int16 *v47; // [rsp+68h] [rbp-98h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+70h] [rbp-90h] BYREF
  bool v49; // [rsp+80h] [rbp-80h]
  int v50[3]; // [rsp+84h] [rbp-7Ch] BYREF
  __int128 v51; // [rsp+90h] [rbp-70h] BYREF
  LPVOID *p_Src; // [rsp+A0h] [rbp-60h]
  void *v53; // [rsp+A8h] [rbp-58h] BYREF
  char v54; // [rsp+B0h] [rbp-50h]
  unsigned int *v55; // [rsp+B8h] [rbp-48h]
  unsigned __int8 **v56; // [rsp+C0h] [rbp-40h]
  __int128 v57; // [rsp+C8h] [rbp-38h] BYREF
  __m128i si128; // [rsp+D8h] [rbp-28h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+E8h] [rbp-18h] BYREF
  int *v60; // [rsp+F8h] [rbp-8h]
  int v61; // [rsp+100h] [rbp+0h]
  int v62; // [rsp+104h] [rbp+4h]
  const unsigned __int16 **v63; // [rsp+108h] [rbp+8h]
  __int64 v64; // [rsp+110h] [rbp+10h]

  v47 = a6;
  v46 = a7;
  v55 = a8;
  v56 = a9;
  *(_QWORD *)&EventDescriptor.Id = a10;
  v12 = CoInitializeEx(0, 0);
  v13 = v12;
  v14 = v12 >= 0;
  v49 = v12 >= 0;
  if ( v12 < 0 )
  {
    if ( (unsigned int)dword_1800BE0B8 > 2 )
    {
      LODWORD(v46) = v12;
      v63 = (const unsigned __int16 **)&v46;
      v64 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_1800BE0C0;
      UserData.Size = *(unsigned __int16 *)off_1800BE0C0;
      UserData.Reserved = 2;
      v60 = (int *)byte_1800AAB33;
      v61 = 47;
      v62 = 1;
      LODWORD(v47) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
    }
LABEL_4:
    if ( v14 )
      CoUninitialize();
    return (unsigned int)v13;
  }
  v42 = 0;
  v51 = (__int128)*a3;
  v13 = (*this)(&v51, &v42);
  if ( v13 < 0 )
  {
    v16 = v42;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(__int64 *))(*v16 + 16))(v16);
    }
    goto LABEL_4;
  }
  v50[0] = 0;
  v51 = xmmword_18008F2D8;
  v13 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, int *))(*v42 + 88))(v42, &v51, v50);
  if ( v13 < 0 )
  {
    v17 = v42;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(__int64 *))(*v17 + 16))(v17);
    }
    goto LABEL_4;
  }
  if ( !v50[0] )
  {
    if ( (unsigned int)dword_1800BE0B8 > 2 )
    {
      LODWORD(v47) = -2147024809;
      v63 = &v47;
      v64 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_1800BE0C0;
      UserData.Size = *(unsigned __int16 *)off_1800BE0C0;
      UserData.Reserved = 2;
      v60 = &dword_1800AAB0C;
      v61 = 27;
      v62 = 1;
      LODWORD(v46) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
    }
    v18 = v42;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(__int64 *))(*v18 + 16))(v18);
    }
    if ( v14 )
      CoUninitialize();
    return 2147942487LL;
  }
  v57 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v57) = 0;
  v13 = NgcUtils::NgcContainerKeyName::BuildKeyNameString(a5);
  if ( v13 < 0 )
  {
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(&v57);
    v19 = v42;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(__int64 *))(*v19 + 16))(v19);
    }
    goto LABEL_4;
  }
  Src = 0;
  size = 0;
  pv = 0;
  v20 = *v42;
  UserData.Ptr = (ULONGLONG)&pv;
  *(_QWORD *)&UserData.Size = 0;
  LOBYTE(v60) = 1;
  p_Src = &Src;
  v53 = 0;
  v54 = 1;
  v21 = &v57;
  if ( si128.m128i_i64[1] > 7uLL )
    v21 = (__int128 *)v57;
  v51 = xmmword_18008F2D8;
  v22 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, __int128 *, void **, size_t *, ULONG *, char *))(v20 + 264))(
          v42,
          &v51,
          v21,
          &v53,
          &size,
          &UserData.Size,
          (char *)&size + 4);
  if ( v54 )
  {
    v23 = *p_Src;
    *p_Src = v53;
    if ( v23 )
      CoTaskMemFree(v23);
  }
  if ( (_BYTE)v60 )
  {
    v24 = *(void **)UserData.Ptr;
    *(_QWORD *)UserData.Ptr = *(_QWORD *)&UserData.Size;
    if ( v24 )
      CoTaskMemFree(v24);
  }
  if ( v22 < 0 )
  {
    v25 = pv;
    pv = 0;
    if ( v25 )
      CoTaskMemFree(v25);
    v26 = Src;
    Src = 0;
    if ( v26 )
      CoTaskMemFree(v26);
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(&v57);
    v27 = v42;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(__int64 *))(*v27 + 16))(v27);
    }
LABEL_71:
    if ( v14 )
      CoUninitialize();
    return (unsigned int)v22;
  }
  v28 = (unsigned __int8 *)MIDL_user_allocate((unsigned int)size);
  v29 = v28;
  if ( v28 )
  {
    memcpy_0(v28, Src, (unsigned int)size);
    v33 = (unsigned __int8 *)MIDL_user_allocate(HIDWORD(size));
    v34 = v33;
    if ( v33 )
    {
      memcpy_0(v33, pv, HIDWORD(size));
      *v46 = v29;
      *v55 = size;
      *v56 = v34;
      **(_DWORD **)&EventDescriptor.Id = HIDWORD(size);
      v39 = pv;
      pv = 0;
      if ( v39 )
        CoTaskMemFree(v39);
      v40 = Src;
      Src = 0;
      if ( v40 )
        CoTaskMemFree(v40);
      std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(&v57);
      v41 = v42;
      if ( v42 )
      {
        v42 = 0;
        (*(void (__fastcall **)(__int64 *))(*v41 + 16))(v41);
      }
      goto LABEL_71;
    }
    if ( (unsigned int)dword_1800BE0B8 > 2 )
    {
      LODWORD(v47) = -2147024882;
      v63 = &v47;
      v64 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_1800BE0C0;
      UserData.Size = *(unsigned __int16 *)off_1800BE0C0;
      UserData.Reserved = 2;
      v60 = (int *)&unk_1800AAAB0;
      v61 = 41;
      v62 = 1;
      LODWORD(v46) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
    }
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v29);
    v36 = pv;
    pv = 0;
    if ( v36 )
      CoTaskMemFree(v36);
    v37 = Src;
    Src = 0;
    if ( v37 )
      CoTaskMemFree(v37);
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(&v57);
    v38 = v42;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(__int64 *))(*v38 + 16))(v38);
    }
  }
  else
  {
    if ( (unsigned int)dword_1800BE0B8 > 2 )
    {
      LODWORD(v47) = -2147024882;
      v63 = &v47;
      v64 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_1800BE0C0;
      UserData.Size = *(unsigned __int16 *)off_1800BE0C0;
      UserData.Reserved = 2;
      v60 = (int *)&unk_1800AAA40;
      v61 = 41;
      v62 = 1;
      LODWORD(v46) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
    }
    v30 = pv;
    pv = 0;
    if ( v30 )
      CoTaskMemFree(v30);
    v31 = Src;
    Src = 0;
    if ( v31 )
      CoTaskMemFree(v31);
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(&v57);
    v32 = v42;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(__int64 *))(*v32 + 16))(v32);
    }
  }
  if ( v14 )
    CoUninitialize();
  return 2147942414LL;
}

```

## disassembly

```asm
0x18000e230  mov     [rsp-8+arg_8], rbx
0x18000e235  push    rbp
0x18000e236  push    rsi
0x18000e237  push    rdi
0x18000e238  push    r12
0x18000e23a  push    r13
0x18000e23c  push    r14
0x18000e23e  push    r15
0x18000e240  lea     rbp, [rsp-20h]
0x18000e245  sub     rsp, 120h
0x18000e24c  mov     rax, cs:__security_cookie
0x18000e253  xor     rax, rsp
0x18000e256  mov     [rbp+50h+var_38], rax
0x18000e25a  mov     r12, r9
0x18000e25d  mov     r15, r8
0x18000e260  mov     r14, rcx
0x18000e263  mov     r13, [rbp+50h+arg_20]
0x18000e26a  mov     rax, [rbp+50h+arg_28]
0x18000e271  mov     [rsp+150h+var_E8], rax
0x18000e276  mov     rax, [rbp+50h+arg_30]
0x18000e27d  mov     [rsp+150h+var_F0], rax
0x18000e282  mov     rax, [rbp+50h+arg_38]
0x18000e289  mov     [rbp+50h+var_98], rax
0x18000e28d  mov     rax, [rbp+50h+arg_40]
0x18000e294  mov     [rbp+50h+var_90], rax
0x18000e298  mov     rax, [rbp+50h+arg_48]
0x18000e29f  mov     qword ptr [rsp+150h+EventDescriptor.Id], rax
0x18000e2a4  xor     bl, bl
0x18000e2a6  xor     edx, edx; dwCoInit
0x18000e2a8  xor     ecx, ecx; pvReserved
0x18000e2aa  call    cs:__imp_CoInitializeEx
0x18000e2b1  nop     dword ptr [rax+rax+00h]
0x18000e2b6  mov     esi, eax
0x18000e2b8  movzx   edi, bl
0x18000e2bb  mov     edx, 1
0x18000e2c0  test    eax, eax
0x18000e2c2  cmovns  edi, edx
0x18000e2c5  mov     [rbp+50h+var_D0], dil
0x18000e2c9  jns     loc_18000E39A
0x18000e2cf  mov     ecx, cs:dword_1800BE0B8
0x18000e2d5  cmp     ecx, 2
0x18000e2d8  jbe     loc_18000E382
0x18000e2de  mov     dword ptr [rsp+150h+var_F0], eax
0x18000e2e2  lea     rax, [rsp+150h+var_F0]
0x18000e2e7  mov     [rbp+50h+var_48], rax
0x18000e2eb  mov     [rbp+50h+var_40], 4
0x18000e2f3  xor     ebx, ebx
0x18000e2f5  mov     dword ptr [rsp+150h+EventDescriptor.Id], 0B000000h
0x18000e2fd  movzx   eax, cs:word_1800AAB29
0x18000e304  mov     dword ptr [rsp+150h+EventDescriptor.Level], eax
0x18000e308  mov     [rsp+150h+EventDescriptor.Keyword], rbx
0x18000e30d  mov     rax, cs:off_1800BE0C0
0x18000e314  mov     [rbp+50h+var_68.Ptr], rax
0x18000e318  movzx   eax, word ptr [rax]
0x18000e31b  mov     [rbp+50h+var_68.Size], eax
0x18000e31e  mov     dword ptr [rbp+50h+var_68.0Ch], 2
0x18000e325  lea     rax, byte_1800AAB33
0x18000e32c  mov     [rbp+50h+var_58], rax
0x18000e330  mov     [rbp+50h+var_50], 2Fh ; '/'
0x18000e337  mov     [rbp+50h+var_4C], edx
0x18000e33a  lea     rax, _TraceLoggingMetadataEnd
0x18000e341  lea     rcx, _TraceLoggingMetadata
0x18000e348  sub     eax, ecx
0x18000e34a  mov     dword ptr [rsp+150h+var_E8], eax
0x18000e34e  mov     eax, dword ptr [rsp+150h+var_E8]
0x18000e352  lea     rax, [rbp+50h+var_68]
0x18000e356  mov     [rsp+150h+UserData], rax; UserData
0x18000e35b  mov     [rsp+150h+UserDataCount], 3; UserDataCount
0x18000e363  xor     r9d, r9d; RelatedActivityId
0x18000e366  xor     r8d, r8d; ActivityId
0x18000e369  lea     rdx, [rsp+150h+EventDescriptor]; EventDescriptor
0x18000e36e  mov     rcx, cs:RegHandle; RegHandle
0x18000e375  call    cs:__imp_EventWriteTransfer
0x18000e37c  nop     dword ptr [rax+rax+00h]
0x18000e381  nop
0x18000e382  test    dil, dil
0x18000e385  jz      short loc_18000E393
0x18000e387  call    cs:__imp_CoUninitialize
0x18000e38e  nop     dword ptr [rax+rax+00h]
0x18000e393  mov     eax, esi
0x18000e395  jmp     loc_18000EA11
0x18000e39a  xor     ebx, ebx
0x18000e39c  mov     [rsp+150h+var_110], rbx
0x18000e3a1  movups  xmm0, xmmword ptr [r15]
0x18000e3a5  movaps  [rbp+50h+var_C0], xmm0
0x18000e3a9  lea     rdx, [rsp+150h+var_110]
0x18000e3ae  lea     rcx, [rbp+50h+var_C0]
0x18000e3b2  mov     rax, [r14]
0x18000e3b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3ba  mov     esi, eax
0x18000e3bc  test    eax, eax
0x18000e3be  jns     short loc_18000E3DE
0x18000e3c0  mov     rcx, [rsp+150h+var_110]
0x18000e3c5  test    rcx, rcx
0x18000e3c8  jz      short loc_18000E3DC
0x18000e3ca  mov     [rsp+150h+var_110], rbx
0x18000e3cf  mov     rdx, [rcx]
0x18000e3d2  mov     rax, [rdx+10h]
0x18000e3d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3db  nop
0x18000e3dc  jmp     short loc_18000E382
0x18000e3de  mov     [rbp+50h+var_CC], ebx
0x18000e3e1  mov     rcx, [rsp+150h+var_110]
0x18000e3e6  movups  xmm0, cs:xmmword_18008F2D8
0x18000e3ed  movaps  [rbp+50h+var_C0], xmm0
0x18000e3f1  mov     rax, [rcx]
0x18000e3f4  lea     r8, [rbp+50h+var_CC]
0x18000e3f8  lea     rdx, [rbp+50h+var_C0]
0x18000e3fc  mov     rax, [rax+58h]
0x18000e400  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e405  mov     esi, eax
0x18000e407  test    eax, eax
0x18000e409  jns     short loc_18000E42C
0x18000e40b  mov     rcx, [rsp+150h+var_110]
0x18000e410  test    rcx, rcx
0x18000e413  jz      short loc_18000E427
0x18000e415  mov     [rsp+150h+var_110], rbx
0x18000e41a  mov     rdx, [rcx]
0x18000e41d  mov     rax, [rdx+10h]
0x18000e421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e426  nop
0x18000e427  jmp     loc_18000E382
0x18000e42c  cmp     [rbp+50h+var_CC], 0
0x18000e430  jnz     loc_18000E526
0x18000e436  mov     eax, cs:dword_1800BE0B8
0x18000e43c  cmp     eax, 2
0x18000e43f  jbe     loc_18000E4EF
0x18000e445  mov     dword ptr [rsp+150h+var_E8], 80070057h
0x18000e44d  lea     rax, [rsp+150h+var_E8]
0x18000e452  mov     [rbp+50h+var_48], rax
0x18000e456  mov     [rbp+50h+var_40], 4
0x18000e45e  mov     dword ptr [rsp+150h+EventDescriptor.Id], 0B000000h
0x18000e466  movzx   eax, cs:word_1800AAB02
0x18000e46d  mov     dword ptr [rsp+150h+EventDescriptor.Level], eax
0x18000e471  mov     [rsp+150h+EventDescriptor.Keyword], rbx
0x18000e476  mov     rax, cs:off_1800BE0C0
0x18000e47d  mov     [rbp+50h+var_68.Ptr], rax
0x18000e481  movzx   eax, word ptr [rax]
0x18000e484  mov     [rbp+50h+var_68.Size], eax
0x18000e487  mov     dword ptr [rbp+50h+var_68.0Ch], 2
0x18000e48e  lea     rax, dword_1800AAB0C
0x18000e495  mov     [rbp+50h+var_58], rax
0x18000e499  mov     [rbp+50h+var_50], 1Bh
0x18000e4a0  mov     [rbp+50h+var_4C], 1
0x18000e4a7  lea     rax, _TraceLoggingMetadataEnd
0x18000e4ae  lea     rcx, _TraceLoggingMetadata
0x18000e4b5  sub     eax, ecx
0x18000e4b7  mov     dword ptr [rsp+150h+var_F0], eax
0x18000e4bb  mov     eax, dword ptr [rsp+150h+var_F0]
0x18000e4bf  lea     rax, [rbp+50h+var_68]
0x18000e4c3  mov     [rsp+150h+UserData], rax; UserData
0x18000e4c8  mov     [rsp+150h+UserDataCount], 3; UserDataCount
0x18000e4d0  xor     r9d, r9d; RelatedActivityId
0x18000e4d3  xor     r8d, r8d; ActivityId
0x18000e4d6  lea     rdx, [rsp+150h+EventDescriptor]; EventDescriptor
0x18000e4db  mov     rcx, cs:RegHandle; RegHandle
0x18000e4e2  call    cs:__imp_EventWriteTransfer
0x18000e4e9  nop     dword ptr [rax+rax+00h]
0x18000e4ee  nop
0x18000e4ef  mov     rcx, [rsp+150h+var_110]
0x18000e4f4  test    rcx, rcx
0x18000e4f7  jz      short loc_18000E50B
0x18000e4f9  mov     [rsp+150h+var_110], rbx
0x18000e4fe  mov     rax, [rcx]
0x18000e501  mov     rax, [rax+10h]
0x18000e505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e50a  nop
0x18000e50b  test    dil, dil
0x18000e50e  jz      short loc_18000E51C
0x18000e510  call    cs:__imp_CoUninitialize
0x18000e517  nop     dword ptr [rax+rax+00h]
0x18000e51c  mov     eax, 80070057h
0x18000e521  jmp     loc_18000EA11
0x18000e526  xorps   xmm0, xmm0
0x18000e529  movups  [rbp+50h+var_88], xmm0
0x18000e52d  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18000e535  movdqu  [rbp+50h+var_78], xmm1
0x18000e53a  mov     word ptr [rbp+50h+var_88], bx
0x18000e53e  lea     r9, [rbp+50h+var_88]
0x18000e542  mov     r8, r12
0x18000e545  mov     rdx, [rsp+150h+var_E8]
0x18000e54a  mov     rcx, r13; Src
0x18000e54d  call    ?BuildKeyNameString@NgcContainerKeyName@NgcUtils@@YAJPEBG00PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; NgcUtils::NgcContainerKeyName::BuildKeyNameString(ushort const *,ushort const *,ushort const *,std::wstring *)
0x18000e552  mov     esi, eax
0x18000e554  test    eax, eax
0x18000e556  jns     short loc_18000E583
0x18000e558  lea     rcx, [rbp+50h+var_88]
0x18000e55c  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18000e561  nop
0x18000e562  mov     rcx, [rsp+150h+var_110]
0x18000e567  test    rcx, rcx
0x18000e56a  jz      short loc_18000E57E
0x18000e56c  mov     [rsp+150h+var_110], rbx
0x18000e571  mov     rax, [rcx]
0x18000e574  mov     rax, [rax+10h]
0x18000e578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e57d  nop
0x18000e57e  jmp     loc_18000E382
0x18000e583  mov     [rsp+150h+Src], rbx
0x18000e588  mov     dword ptr [rsp+150h+size], ebx
0x18000e58c  mov     [rsp+150h+pv], rbx
0x18000e591  mov     dword ptr [rsp+150h+size+4], ebx
0x18000e595  mov     rcx, [rsp+150h+var_110]
0x18000e59a  mov     rax, [rcx]
0x18000e59d  lea     rdx, [rsp+150h+pv]
0x18000e5a2  mov     [rbp+50h+var_68.Ptr], rdx
0x18000e5a6  mov     qword ptr [rbp+50h+var_68.Size], rbx
0x18000e5aa  mov     byte ptr [rbp+50h+var_58], 1
0x18000e5ae  lea     rdx, [rsp+150h+Src]
0x18000e5b3  mov     [rbp+50h+var_B0], rdx
0x18000e5b7  mov     [rbp+50h+var_A8], rbx
0x18000e5bb  mov     [rbp+50h+var_A0], 1
0x18000e5bf  lea     r8, [rbp+50h+var_88]
0x18000e5c3  cmp     qword ptr [rbp+50h+var_78+8], 7
0x18000e5c8  cmova   r8, qword ptr [rbp+50h+var_88]
0x18000e5cd  movups  xmm0, cs:xmmword_18008F2D8
0x18000e5d4  movaps  [rbp+50h+var_C0], xmm0
0x18000e5d8  lea     rdx, [rsp+150h+size+4]
0x18000e5dd  mov     [rsp+150h+var_120], rdx
0x18000e5e2  lea     rdx, [rbp+50h+var_68.Size]
0x18000e5e6  mov     [rsp+150h+UserData], rdx
0x18000e5eb  lea     rdx, [rsp+150h+size]
0x18000e5f0  mov     qword ptr [rsp+150h+UserDataCount], rdx
0x18000e5f5  lea     r9, [rbp+50h+var_A8]
0x18000e5f9  lea     rdx, [rbp+50h+var_C0]
0x18000e5fd  mov     rax, [rax+108h]
0x18000e604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e609  mov     r15d, eax
0x18000e60c  cmp     [rbp+50h+var_A0], 0
0x18000e610  jz      short loc_18000E632
0x18000e612  mov     r8, [rbp+50h+var_B0]
0x18000e616  mov     rcx, [r8]; pv
0x18000e619  mov     rdx, [rbp+50h+var_A8]
0x18000e61d  mov     [r8], rdx
0x18000e620  test    rcx, rcx
0x18000e623  jz      short loc_18000E632
0x18000e625  call    cs:__imp_CoTaskMemFree
0x18000e62c  nop     dword ptr [rax+rax+00h]
0x18000e631  nop
0x18000e632  cmp     byte ptr [rbp+50h+var_58], 0
0x18000e636  jz      short loc_18000E657
0x18000e638  mov     rdx, [rbp+50h+var_68.Ptr]
0x18000e63c  mov     rcx, [rdx]; pv
0x18000e63f  mov     rax, qword ptr [rbp+50h+var_68.Size]
0x18000e643  mov     [rdx], rax
0x18000e646  test    rcx, rcx
0x18000e649  jz      short loc_18000E657
0x18000e64b  call    cs:__imp_CoTaskMemFree
0x18000e652  nop     dword ptr [rax+rax+00h]
0x18000e657  test    r15d, r15d
0x18000e65a  jns     short loc_18000E6BF
0x18000e65c  mov     rcx, [rsp+150h+pv]; pv
0x18000e661  mov     [rsp+150h+pv], rbx
0x18000e666  test    rcx, rcx
0x18000e669  jz      short loc_18000E678
0x18000e66b  call    cs:__imp_CoTaskMemFree
0x18000e672  nop     dword ptr [rax+rax+00h]
0x18000e677  nop
0x18000e678  mov     rcx, [rsp+150h+Src]; pv
0x18000e67d  mov     [rsp+150h+Src], rbx
0x18000e682  test    rcx, rcx
0x18000e685  jz      short loc_18000E694
0x18000e687  call    cs:__imp_CoTaskMemFree
0x18000e68e  nop     dword ptr [rax+rax+00h]
0x18000e693  nop
0x18000e694  lea     rcx, [rbp+50h+var_88]
0x18000e698  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18000e69d  nop
0x18000e69e  mov     rcx, [rsp+150h+var_110]
0x18000e6a3  test    rcx, rcx
0x18000e6a6  jz      short loc_18000E6BA
0x18000e6a8  mov     [rsp+150h+var_110], rbx
0x18000e6ad  mov     rax, [rcx]
0x18000e6b0  mov     rax, [rax+10h]
0x18000e6b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6b9  nop
0x18000e6ba  jmp     loc_18000E9FD
0x18000e6bf  mov     ecx, dword ptr [rsp+150h+size]; size
0x18000e6c3  call    MIDL_user_allocate
0x18000e6c8  mov     rsi, rax
0x18000e6cb  test    rax, rax
0x18000e6ce  jnz     loc_18000E7F0
0x18000e6d4  mov     eax, cs:dword_1800BE0B8
0x18000e6da  cmp     eax, 2
0x18000e6dd  jbe     loc_18000E78D
0x18000e6e3  mov     dword ptr [rsp+150h+var_E8], 8007000Eh
0x18000e6eb  lea     rax, [rsp+150h+var_E8]
0x18000e6f0  mov     [rbp+50h+var_48], rax
0x18000e6f4  mov     [rbp+50h+var_40], 4
0x18000e6fc  mov     dword ptr [rsp+150h+EventDescriptor.Id], 0B000000h
0x18000e704  movzx   eax, cs:word_1800AAA36
0x18000e70b  mov     dword ptr [rsp+150h+EventDescriptor.Level], eax
0x18000e70f  mov     [rsp+150h+EventDescriptor.Keyword], rbx
0x18000e714  mov     rax, cs:off_1800BE0C0
0x18000e71b  mov     [rbp+50h+var_68.Ptr], rax
0x18000e71f  movzx   eax, word ptr [rax]
0x18000e722  mov     [rbp+50h+var_68.Size], eax
0x18000e725  mov     dword ptr [rbp+50h+var_68.0Ch], 2
0x18000e72c  lea     rax, unk_1800AAA40
0x18000e733  mov     [rbp+50h+var_58], rax
  ... truncated ...
```
