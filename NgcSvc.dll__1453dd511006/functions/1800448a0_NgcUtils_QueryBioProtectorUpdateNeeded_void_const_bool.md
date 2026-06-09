# NgcUtils::QueryBioProtectorUpdateNeeded(void * const,bool *)

- ea: `0x1800448a0`
- end: `0x180044d5e`
- name: `?QueryBioProtectorUpdateNeeded@NgcUtils@@YAJQEAXPEA_N@Z`
- size: `1214`
- prototype: `__int64 __fastcall(NgcUtils *__hidden this, void *const, bool *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800512bc`

## callees

- `0x180007360`
- `0x18000bce0`
- `0x18000e960`
- `0x1800448a0`
- `0x180053618`
- `0x18005cee0`
- `0x18005d2b0`
- `0x18005dd2c`
- `0x18005dd38`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800448e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800448e9`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180044991`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180044c9c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180044991`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180044c9c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800449ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044bef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044d28`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800449ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044bef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044d28`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180044bc7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180044bc7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800448db`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800448db`

## string_xrefs

- `0x180044bb9`: `ProtectorUpdateNeeded`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NgcUtils::QueryBioProtectorUpdateNeeded(NgcUtils *this, bool *a2, bool *a3)
{
  signed int LastError; // ebx
  int RedirectedWinBioAccontInfoRegPath; // r13d
  unsigned __int64 v6; // rdx
  void *v7; // rax
  LPWSTR v8; // r14
  unsigned __int64 v9; // rsi
  __int64 v10; // r12
  unsigned __int64 v11; // r15
  __int64 v12; // rdi
  void **v13; // rbx
  char *v14; // rdi
  __int64 v15; // rbx
  __int64 v16; // r13
  unsigned __int64 v17; // rcx
  unsigned __int64 v18; // rdx
  size_t v19; // r8
  size_t v20; // rsi
  char *v21; // r12
  void *v22; // rbx
  unsigned __int64 v23; // rdx
  _BYTE *v24; // rcx
  void **v25; // rdx
  LSTATUS ValueW; // eax
  unsigned __int64 v27; // rdx
  void *v28; // rcx
  unsigned int v29; // [rsp+40h] [rbp-69h] BYREF
  LPWSTR StringSid; // [rsp+48h] [rbp-61h] BYREF
  int pvData; // [rsp+50h] [rbp-59h] BYREF
  bool *v32; // [rsp+58h] [rbp-51h] BYREF
  DWORD pcbData; // [rsp+60h] [rbp-49h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+68h] [rbp-41h] BYREF
  void *Src[2]; // [rsp+78h] [rbp-31h] BYREF
  __int64 v36; // [rsp+88h] [rbp-21h]
  unsigned __int64 v37; // [rsp+90h] [rbp-19h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+98h] [rbp-11h] BYREF
  char *v39; // [rsp+A8h] [rbp-1h]
  int v40; // [rsp+B0h] [rbp+7h]
  int v41; // [rsp+B4h] [rbp+Bh]
  unsigned int *v42; // [rsp+B8h] [rbp+Fh]
  __int64 v43; // [rsp+C0h] [rbp+17h]

  v32 = a2;
  *a2 = 0;
  StringSid = 0;
  if ( !ConvertSidToStringSidW(this, &StringSid) )
  {
    LastError = GetLastError();
    if ( (unsigned int)dword_180122070 > 2 )
    {
      v29 = LastError;
      v42 = &v29;
      v43 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_180122078;
      UserData.Size = *(unsigned __int16 *)off_180122078;
      UserData.Reserved = 2;
      v39 = byte_180106D53;
      v40 = 39;
      v41 = 1;
      LODWORD(v32) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_6:
    if ( StringSid )
      LocalFree(StringSid);
    return (unsigned int)LastError;
  }
  *(_OWORD *)Src = 0;
  v36 = 0;
  v37 = 7;
  LOWORD(Src[0]) = 0;
  RedirectedWinBioAccontInfoRegPath = anonymous_namespace_::GetRedirectedWinBioAccontInfoRegPath((char **)Src);
  v29 = RedirectedWinBioAccontInfoRegPath;
  if ( RedirectedWinBioAccontInfoRegPath < 0 )
  {
    if ( v37 <= 7 )
    {
LABEL_16:
      v36 = 0;
      LOWORD(Src[0]) = 0;
LABEL_56:
      v37 = 7;
      if ( StringSid )
        LocalFree(StringSid);
      return (unsigned int)RedirectedWinBioAccontInfoRegPath;
    }
    v6 = 2 * v37 + 2;
    if ( v6 < 0x1000 )
    {
      v7 = Src[0];
      goto LABEL_15;
    }
    v7 = (void *)*((_QWORD *)Src[0] - 1);
    if ( (unsigned __int64)((char *)Src[0] - (char *)v7 - 8) <= 0x1F )
    {
      v6 = 2 * v37 + 41;
LABEL_15:
      operator delete(v7, v6);
      goto LABEL_16;
    }
LABEL_52:
    __fastfail(5u);
  }
  v8 = StringSid;
  v9 = -1;
  do
    ++v9;
  while ( StringSid[v9] );
  v10 = v36;
  v11 = v37;
  if ( v9 > v37 - v36 )
  {
    v15 = 0x7FFFFFFFFFFFFFFELL;
    if ( 0x7FFFFFFFFFFFFFFELL - v36 < v9 )
      std::_Xlen_string();
    v16 = v9 + v36;
    v17 = (v9 + v36) | 7;
    if ( v17 <= 0x7FFFFFFFFFFFFFFELL )
    {
      v18 = v37 >> 1;
      if ( v37 <= 0x7FFFFFFFFFFFFFFELL - (v37 >> 1) )
      {
        v15 = v18 + v37;
        if ( v17 >= v18 + v37 )
          v15 = (v9 + v36) | 7;
      }
    }
    v14 = (char *)std::allocator<unsigned short>::allocate(v17, v15 + 1);
    v36 = v9 + v10;
    v37 = v15;
    v19 = 2 * v10;
    v20 = 2 * v9;
    v21 = &v14[2 * v10];
    if ( v11 <= 7 )
    {
      memcpy_0(v14, Src, v19);
      memcpy_0(v21, v8, v20);
      *(_WORD *)&v14[2 * v16] = 0;
    }
    else
    {
      v22 = Src[0];
      memcpy_0(v14, Src[0], v19);
      memcpy_0(v21, v8, v20);
      *(_WORD *)&v14[2 * v16] = 0;
      v23 = 2 * v11 + 2;
      if ( v23 < 0x1000 )
      {
        operator delete(v22, v23);
      }
      else
      {
        v24 = (_BYTE *)*((_QWORD *)v22 - 1);
        if ( (unsigned __int64)((_BYTE *)v22 - v24 - 8) > 0x1F )
          __fastfail(5u);
        operator delete(v24, 2 * v11 + 41);
      }
    }
    RedirectedWinBioAccontInfoRegPath = v29;
    Src[0] = v14;
  }
  else
  {
    v12 = v9 + v36;
    v36 += v9;
    v13 = Src;
    if ( v37 > 7 )
      v13 = (void **)Src[0];
    memmove_0((char *)v13 + 2 * v10, StringSid, 2 * v9);
    *((_WORD *)v13 + v12) = 0;
    v14 = (char *)Src[0];
  }
  pvData = 0;
  pcbData = 4;
  v25 = Src;
  if ( v37 > 7 )
    v25 = (void **)v14;
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, (LPCWSTR)v25, L"ProtectorUpdateNeeded", 0x10u, 0, &pvData, &pcbData);
  LastError = ValueW;
  if ( !ValueW )
  {
    *v32 = pvData != 0;
    if ( v37 > 7 )
    {
      v27 = 2 * v37 + 2;
      if ( v27 < 0x1000 )
      {
        v28 = Src[0];
      }
      else
      {
        v28 = (void *)*((_QWORD *)Src[0] - 1);
        if ( (unsigned __int64)((char *)Src[0] - (char *)v28 - 8) > 0x1F )
          goto LABEL_52;
        v27 = 2 * v37 + 41;
      }
      operator delete(v28, v27);
    }
    v36 = 0;
    LOWORD(Src[0]) = 0;
    goto LABEL_56;
  }
  if ( ValueW != 2 )
  {
    if ( (unsigned int)dword_180122070 > 2 )
    {
      LODWORD(v32) = ValueW;
      v42 = (unsigned int *)&v32;
      v43 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_180122078;
      UserData.Size = *(unsigned __int16 *)off_180122078;
      UserData.Reserved = 2;
      v39 = byte_180106D15;
      v40 = 50;
      v41 = 1;
      v29 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(Src);
    goto LABEL_6;
  }
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(Src);
  if ( StringSid )
    LocalFree(StringSid);
  return 0;
}

```

## disassembly

```asm
0x1800448a0  mov     [rsp-8+arg_10], rbx
0x1800448a5  push    rbp
0x1800448a6  push    rsi
0x1800448a7  push    rdi
0x1800448a8  push    r12
0x1800448aa  push    r13
0x1800448ac  push    r14
0x1800448ae  push    r15
0x1800448b0  lea     rbp, [rsp-27h]
0x1800448b5  sub     rsp, 0D0h
0x1800448bc  mov     rax, cs:__security_cookie
0x1800448c3  xor     rax, rsp
0x1800448c6  mov     [rbp+57h+var_38], rax
0x1800448ca  mov     [rbp+57h+var_A8], rdx
0x1800448ce  mov     byte ptr [rdx], 0
0x1800448d1  xor     edi, edi
0x1800448d3  mov     [rbp+57h+StringSid], rdi
0x1800448d7  lea     rdx, [rbp+57h+StringSid]; StringSid
0x1800448db  call    cs:__imp_ConvertSidToStringSidW
0x1800448e1  test    eax, eax
0x1800448e3  jnz     loc_1800449BA
0x1800448e9  call    cs:__imp_GetLastError
0x1800448ef  mov     ebx, eax
0x1800448f1  mov     eax, cs:dword_180122070
0x1800448f7  cmp     eax, 2
0x1800448fa  jbe     loc_180044997
0x180044900  mov     [rbp+57h+var_C0], ebx
0x180044903  lea     rax, [rbp+57h+var_C0]
0x180044907  mov     [rbp+57h+var_48], rax
0x18004490b  mov     [rbp+57h+var_40], 4
0x180044913  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x18004491a  movzx   eax, cs:word_180106D49
0x180044921  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x180044924  mov     [rbp+57h+EventDescriptor.Keyword], rdi
0x180044928  mov     rax, cs:off_180122078
0x18004492f  mov     [rbp+57h+var_68.Ptr], rax
0x180044933  movzx   eax, word ptr [rax]
0x180044936  mov     [rbp+57h+var_68.Size], eax
0x180044939  mov     dword ptr [rbp+57h+var_68.0Ch], 2
0x180044940  lea     rax, byte_180106D53
0x180044947  mov     [rbp+57h+var_58], rax
0x18004494b  mov     [rbp+57h+var_50], 27h ; '''
0x180044952  mov     [rbp+57h+var_4C], 1
0x180044959  lea     rax, _TraceLoggingMetadataEnd
0x180044960  lea     rcx, _TraceLoggingMetadata
0x180044967  sub     eax, ecx
0x180044969  mov     dword ptr [rbp+57h+var_A8], eax
0x18004496c  mov     eax, dword ptr [rbp+57h+var_A8]
0x18004496f  lea     rax, [rbp+57h+var_68]
0x180044973  mov     [rsp+100h+UserData], rax; UserData
0x180044978  mov     [rsp+100h+UserDataCount], 3; UserDataCount
0x180044980  xor     r9d, r9d; RelatedActivityId
0x180044983  xor     r8d, r8d; ActivityId
0x180044986  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18004498a  mov     rcx, cs:RegHandle; RegHandle
0x180044991  call    cs:__imp_EventWriteTransfer
0x180044997  test    ebx, ebx
0x180044999  jle     short loc_1800449A4
0x18004499b  movzx   ebx, bx
0x18004499e  or      ebx, 80070000h
0x1800449a4  mov     rcx, [rbp+57h+StringSid]; hMem
0x1800449a8  test    rcx, rcx
0x1800449ab  jz      short loc_1800449B3
0x1800449ad  call    cs:__imp_LocalFree
0x1800449b3  mov     eax, ebx
0x1800449b5  jmp     loc_180044D31
0x1800449ba  xorps   xmm0, xmm0
0x1800449bd  movups  xmmword ptr [rbp+57h+Src], xmm0
0x1800449c1  mov     [rbp+57h+var_78], rdi
0x1800449c5  mov     [rbp+57h+var_70], 7
0x1800449cd  mov     word ptr [rbp+57h+Src], di
0x1800449d1  lea     rcx, [rbp+57h+Src]
0x1800449d5  call    _anonymous_namespace___GetRedirectedWinBioAccontInfoRegPath
0x1800449da  mov     r13d, eax
0x1800449dd  mov     [rbp+57h+var_C0], eax
0x1800449e0  test    eax, eax
0x1800449e2  jns     short loc_180044A36
0x1800449e4  mov     rdx, [rbp+57h+var_70]
0x1800449e8  cmp     rdx, 7
0x1800449ec  jbe     short loc_180044A29
0x1800449ee  mov     rcx, [rbp+57h+Src]
0x1800449f2  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x1800449fa  cmp     rdx, 1000h
0x180044a01  jb      short loc_180044A1E
0x180044a03  mov     rax, [rcx-8]
0x180044a07  sub     rcx, rax
0x180044a0a  sub     rcx, 8
0x180044a0e  cmp     rcx, 1Fh
0x180044a12  ja      loc_180044D00
0x180044a18  add     rdx, 27h ; '''
0x180044a1c  jmp     short loc_180044A21
0x180044a1e  mov     rax, rcx
0x180044a21  mov     rcx, rax; void *
0x180044a24  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180044a29  mov     [rbp+57h+var_78], rdi
0x180044a2d  mov     word ptr [rbp+57h+Src], di
0x180044a31  jmp     loc_180044D17
0x180044a36  mov     r14, [rbp+57h+StringSid]
0x180044a3a  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180044a41  inc     rsi
0x180044a44  cmp     word ptr [r14+rsi*2], 0
0x180044a4a  jnz     short loc_180044A41
0x180044a4c  mov     r12, [rbp+57h+var_78]
0x180044a50  mov     r15, [rbp+57h+var_70]
0x180044a54  mov     rax, r15
0x180044a57  sub     rax, r12
0x180044a5a  cmp     rsi, rax
0x180044a5d  ja      short loc_180044A93
0x180044a5f  lea     rdi, [rsi+r12]
0x180044a63  mov     [rbp+57h+var_78], rdi
0x180044a67  lea     rbx, [rbp+57h+Src]
0x180044a6b  cmp     r15, 7
0x180044a6f  cmova   rbx, [rbp+57h+Src]
0x180044a74  lea     r8, [rsi+rsi]; Size
0x180044a78  lea     rcx, [rbx+r12*2]; void *
0x180044a7c  mov     rdx, r14; Src
0x180044a7f  call    memmove_0
0x180044a84  xor     esi, esi
0x180044a86  mov     [rbx+rdi*2], si
0x180044a8a  mov     rdi, [rbp+57h+Src]
0x180044a8e  jmp     loc_180044B85
0x180044a93  mov     rbx, 7FFFFFFFFFFFFFFEh
0x180044a9d  mov     rax, rbx
0x180044aa0  sub     rax, r12
0x180044aa3  cmp     rax, rsi
0x180044aa6  jb      loc_180044D58
0x180044aac  lea     r13, [rsi+r12]
0x180044ab0  mov     rcx, r13
0x180044ab3  or      rcx, 7
0x180044ab7  cmp     rcx, rbx
0x180044aba  ja      short loc_180044AD8
0x180044abc  mov     rdx, r15
0x180044abf  shr     rdx, 1
0x180044ac2  mov     rax, rbx
0x180044ac5  sub     rax, rdx
0x180044ac8  cmp     r15, rax
0x180044acb  ja      short loc_180044AD8
0x180044acd  lea     rbx, [rdx+r15]
0x180044ad1  cmp     rcx, rbx
0x180044ad4  cmovnb  rbx, rcx
0x180044ad8  lea     rdx, [rbx+1]
0x180044adc  call    ?allocate@?$allocator@G@std@@QEAAPEAG_K@Z; std::allocator<ushort>::allocate(unsigned __int64)
0x180044ae1  mov     rdi, rax
0x180044ae4  mov     [rbp+57h+var_78], r13
0x180044ae8  mov     [rbp+57h+var_70], rbx
0x180044aec  lea     r8, [r12+r12]; Size
0x180044af0  add     rsi, rsi
0x180044af3  lea     r12, [r8+rax]
0x180044af7  mov     rcx, rax; void *
0x180044afa  cmp     r15, 7
0x180044afe  jbe     short loc_180044B5F
0x180044b00  mov     rbx, [rbp+57h+Src]
0x180044b04  mov     rdx, rbx; Src
0x180044b07  call    memcpy_0
0x180044b0c  mov     r8, rsi; Size
0x180044b0f  mov     rdx, r14; Src
0x180044b12  mov     rcx, r12; void *
0x180044b15  call    memcpy_0
0x180044b1a  xor     esi, esi
0x180044b1c  mov     [rdi+r13*2], si
0x180044b21  lea     rdx, ds:2[r15*2]; unsigned __int64
0x180044b29  cmp     rdx, 1000h
0x180044b30  jb      short loc_180044B55
0x180044b32  mov     rcx, [rbx-8]; void *
0x180044b36  sub     rbx, rcx
0x180044b39  sub     rbx, 8
0x180044b3d  cmp     rbx, 1Fh
0x180044b41  ja      short loc_180044B4E
0x180044b43  add     rdx, 27h ; '''; unsigned __int64
0x180044b47  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180044b4c  jmp     short loc_180044B7D
0x180044b4e  mov     ecx, 5
0x180044b53  int     29h; Win8: RtlFailFast(ecx)
0x180044b55  mov     rcx, rbx; void *
0x180044b58  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180044b5d  jmp     short loc_180044B7D
0x180044b5f  lea     rdx, [rbp+57h+Src]; Src
0x180044b63  call    memcpy_0
0x180044b68  mov     r8, rsi; Size
0x180044b6b  mov     rdx, r14; Src
0x180044b6e  mov     rcx, r12; void *
0x180044b71  call    memcpy_0
0x180044b76  xor     esi, esi
0x180044b78  mov     [rdi+r13*2], si
0x180044b7d  mov     r13d, [rbp+57h+var_C0]
0x180044b81  mov     [rbp+57h+Src], rdi
0x180044b85  mov     [rbp+57h+pvData], esi
0x180044b88  mov     [rbp+57h+var_A0], 4
0x180044b8f  lea     rdx, [rbp+57h+Src]
0x180044b93  cmp     [rbp+57h+var_70], 7
0x180044b98  cmova   rdx, rdi; lpSubKey
0x180044b9c  lea     rax, [rbp+57h+var_A0]
0x180044ba0  mov     [rsp+100h+pcbData], rax; pcbData
0x180044ba5  lea     rax, [rbp+57h+pvData]
0x180044ba9  mov     [rsp+100h+UserData], rax; pvData
0x180044bae  mov     qword ptr [rsp+100h+UserDataCount], rsi; pdwType
0x180044bb3  mov     r9d, 10h; dwFlags
0x180044bb9  lea     r8, aProtectorupdat; "ProtectorUpdateNeeded"
0x180044bc0  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180044bc7  call    cs:__imp_RegGetValueW
0x180044bcd  mov     ebx, eax
0x180044bcf  test    eax, eax
0x180044bd1  jz      loc_180044CBD
0x180044bd7  cmp     eax, 2
0x180044bda  jnz     short loc_180044BFC
0x180044bdc  lea     rcx, [rbp+57h+Src]
0x180044be0  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x180044be5  nop
0x180044be6  mov     rcx, [rbp+57h+StringSid]; hMem
0x180044bea  test    rcx, rcx
0x180044bed  jz      short loc_180044BF5
0x180044bef  call    cs:__imp_LocalFree
0x180044bf5  xor     eax, eax
0x180044bf7  jmp     loc_180044D31
0x180044bfc  mov     eax, cs:dword_180122070
0x180044c02  cmp     eax, 2
0x180044c05  jbe     loc_180044CA2
0x180044c0b  mov     dword ptr [rbp+57h+var_A8], ebx
0x180044c0e  lea     rax, [rbp+57h+var_A8]
0x180044c12  mov     [rbp+57h+var_48], rax
0x180044c16  mov     [rbp+57h+var_40], 4
0x180044c1e  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x180044c25  movzx   eax, cs:word_180106D0B
0x180044c2c  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x180044c2f  mov     [rbp+57h+EventDescriptor.Keyword], rsi
0x180044c33  mov     rax, cs:off_180122078
0x180044c3a  mov     [rbp+57h+var_68.Ptr], rax
0x180044c3e  movzx   eax, word ptr [rax]
0x180044c41  mov     [rbp+57h+var_68.Size], eax
0x180044c44  mov     dword ptr [rbp+57h+var_68.0Ch], 2
0x180044c4b  lea     rax, byte_180106D15
0x180044c52  mov     [rbp+57h+var_58], rax
0x180044c56  mov     [rbp+57h+var_50], 32h ; '2'
0x180044c5d  mov     [rbp+57h+var_4C], 1
0x180044c64  lea     rax, _TraceLoggingMetadataEnd
0x180044c6b  lea     rcx, _TraceLoggingMetadata
0x180044c72  sub     eax, ecx
0x180044c74  mov     [rbp+57h+var_C0], eax
0x180044c77  mov     eax, [rbp+57h+var_C0]
0x180044c7a  lea     rax, [rbp+57h+var_68]
0x180044c7e  mov     [rsp+100h+UserData], rax; UserData
0x180044c83  mov     [rsp+100h+UserDataCount], 3; UserDataCount
0x180044c8b  xor     r9d, r9d; RelatedActivityId
0x180044c8e  xor     r8d, r8d; ActivityId
0x180044c91  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x180044c95  mov     rcx, cs:RegHandle; RegHandle
0x180044c9c  call    cs:__imp_EventWriteTransfer
0x180044ca2  test    ebx, ebx
0x180044ca4  jle     short loc_180044CAF
0x180044ca6  movzx   ebx, bx
0x180044ca9  or      ebx, 80070000h
0x180044caf  lea     rcx, [rbp+57h+Src]
0x180044cb3  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x180044cb8  jmp     loc_1800449A4
0x180044cbd  cmp     [rbp+57h+pvData], 0
0x180044cc1  setnz   al
0x180044cc4  mov     rcx, [rbp+57h+var_A8]
0x180044cc8  mov     [rcx], al
0x180044cca  mov     rdx, [rbp+57h+var_70]
0x180044cce  cmp     rdx, 7
0x180044cd2  jbe     short loc_180044D0F
0x180044cd4  mov     rax, [rbp+57h+Src]
0x180044cd8  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x180044ce0  cmp     rdx, 1000h
0x180044ce7  jb      short loc_180044D07
0x180044ce9  mov     rcx, [rax-8]
0x180044ced  sub     rax, rcx
0x180044cf0  sub     rax, 8
0x180044cf4  cmp     rax, 1Fh
0x180044cf8  ja      short loc_180044D00
0x180044cfa  add     rdx, 27h ; '''
0x180044cfe  jmp     short loc_180044D0A
0x180044d00  mov     ecx, 5
0x180044d05  int     29h; Win8: RtlFailFast(ecx)
0x180044d07  mov     rcx, rax; void *
0x180044d0a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180044d0f  mov     [rbp+57h+var_78], rsi
0x180044d13  mov     word ptr [rbp+57h+Src], si
0x180044d17  mov     [rbp+57h+var_70], 7
0x180044d1f  mov     rcx, [rbp+57h+StringSid]; hMem
0x180044d23  test    rcx, rcx
0x180044d26  jz      short loc_180044D2E
0x180044d28  call    cs:__imp_LocalFree
0x180044d2e  mov     eax, r13d
0x180044d31  mov     rcx, [rbp+57h+var_38]
0x180044d35  xor     rcx, rsp; StackCookie
0x180044d38  call    __security_check_cookie
0x180044d3d  mov     rbx, [rsp+100h+arg_10]
0x180044d45  add     rsp, 0D0h
0x180044d4c  pop     r15
0x180044d4e  pop     r14
0x180044d50  pop     r13
0x180044d52  pop     r12
0x180044d54  pop     rdi
0x180044d55  pop     rsi
0x180044d56  pop     rbp
0x180044d57  retn
0x180044d58  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
