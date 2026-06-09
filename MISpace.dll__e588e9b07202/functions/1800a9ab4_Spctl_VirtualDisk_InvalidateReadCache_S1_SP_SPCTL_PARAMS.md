# Spctl_VirtualDisk_InvalidateReadCache_S1(_SP_SPCTL_PARAMS *)

- ea: `0x1800a9ab4`
- end: `0x1800a9e57`
- name: `?Spctl_VirtualDisk_InvalidateReadCache_S1@@YAKPEAU_SP_SPCTL_PARAMS@@@Z`
- size: `931`
- prototype: `unsigned int __fastcall(struct _SP_SPCTL_PARAMS *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x18009304c`

## callees

- `0x1800011b0`
- `0x1800015b8`
- `0x18000cdc8`
- `0x18000f3bc`
- `0x180013a68`
- `0x1800194c4`
- `0x18001b134`
- `0x18002602c`
- `0x1800a9ab4`
- `0x1800ac344`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a9c4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a9c4e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a9c6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a9c6b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a9bb8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a9bb8`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800a9dbb`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800a9dbb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a9d58`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a9d58`

## string_xrefs

- `0x1800a9acc`: `Spctl_VirtualDisk_InvalidateReadCache_S1`
- `0x1800a9bdd`: `Spctl_VirtualDisk_InvalidateReadCache_S1`
- `0x1800a9c7c`: `Spctl_VirtualDisk_InvalidateReadCache_S1`
- `0x1800a9cfa`: `Spctl_VirtualDisk_InvalidateReadCache_S1`

## pseudocode

```c
__int64 __fastcall Spctl_VirtualDisk_InvalidateReadCache_S1(struct _SP_SPCTL_PARAMS *a1, __int64 a2, int a3, int a4)
{
  __int64 v6; // r13
  __int128 v7; // xmm1
  __int64 FileW; // r15
  WCHAR *v9; // rdi
  enum _MI_Result VolumeOnVirtualDisk; // ecx
  int v11; // r8d
  int v12; // r9d
  int v13; // r8d
  int v14; // r9d
  const unsigned __int16 *v15; // r14
  __int64 v16; // rbx
  unsigned __int64 v17; // rbx
  unsigned __int16 *v18; // rax
  int v19; // ecx
  int *v20; // rdx
  __int64 v21; // rbx
  unsigned int v22; // eax
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  unsigned int v26; // ecx
  char *v27; // rdx
  int LastError; // eax
  int v29; // eax
  _OWORD v30[2]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v31; // [rsp+60h] [rbp-10h] BYREF
  char v32; // [rsp+68h] [rbp-8h]
  int v33; // [rsp+B0h] [rbp+40h] BYREF
  const char *v34; // [rsp+B8h] [rbp+48h] BYREF
  DWORD BytesReturned; // [rsp+C0h] [rbp+50h] BYREF
  MI_Instance *self; // [rsp+C8h] [rbp+58h] BYREF

  if ( (unsigned int)dword_180397B68 > 5 )
  {
    v33 = 5844;
    v34 = "Spctl_VirtualDisk_InvalidateReadCache_S1";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (_DWORD)a1,
      (unsigned int)&byte_180319237,
      a3,
      a4,
      (__int64)&v34,
      (__int64)&v33);
  }
  BytesReturned = 0;
  self = 0;
  v31 = 0;
  v32 = 0;
  if ( *((_DWORD *)a1 + 146) < 0x220u )
  {
    **((_DWORD **)a1 + 74) = 544;
    return 87;
  }
  v6 = *((_QWORD *)a1 + 72);
  v7 = *(_OWORD *)((char *)a1 + 20);
  FileW = -1;
  v30[0] = *(_OWORD *)((char *)a1 + 4);
  v9 = 0;
  v30[1] = v7;
  VolumeOnVirtualDisk = GetVolumeOnVirtualDisk((struct _SP_ID *)v30, &self);
  if ( VolumeOnVirtualDisk )
  {
    v26 = VolumeOnVirtualDisk | 0x85200000;
    LODWORD(v31) = v26;
    if ( (unsigned int)dword_180397B68 <= 2 )
      goto LABEL_14;
    v33 = v26;
    v27 = (char *)&word_18031D98E;
    LODWORD(v34) = 5865;
    *(_QWORD *)&v30[0] = "Spctl_VirtualDisk_InvalidateReadCache_S1";
    goto LABEL_27;
  }
  LODWORD(v31) = 85983232;
  v15 = *(const unsigned __int16 **)(SmMIGetInstance(v30, L"Path", self) + 8);
  if ( !v15 || !*v15 )
  {
    v19 = -2060451835;
    LODWORD(v31) = -2060451835;
    if ( (unsigned int)dword_180397B68 <= 2 )
      goto LABEL_14;
    LODWORD(v34) = 5874;
    v20 = &dword_18031E37C;
    *(_QWORD *)&v30[0] = "Spctl_VirtualDisk_InvalidateReadCache_S1";
    goto LABEL_13;
  }
  v16 = -1;
  do
    ++v16;
  while ( v15[v16] );
  v17 = v16 + 1;
  v18 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v17);
  v9 = v18;
  if ( v18 )
  {
    if ( (int)StringCchCopyW(v18, v17, v15) >= 0 )
    {
      if ( v9[v17 - 2] == 92 )
        v9[v17 - 2] = 0;
      FileW = (__int64)CreateFileW(v9, 0x80000000, 3u, 0, 3u, 0, 0);
      if ( FileW == -1 )
      {
        LastError = _status_t::GetLastError((_status_t *)&v31);
        v26 = dword_180397B68;
        if ( (unsigned int)dword_180397B68 <= 2 )
          goto LABEL_14;
        v33 = LastError;
        v27 = byte_18031B91B;
        LODWORD(v34) = 5914;
      }
      else
      {
        if ( DeviceIoControl((HANDLE)FileW, 0x9039Cu, 0, 0, 0, 0, &BytesReturned, 0) )
          goto LABEL_14;
        v29 = _status_t::GetLastError((_status_t *)&v31);
        v26 = dword_180397B68;
        if ( (unsigned int)dword_180397B68 <= 2 )
          goto LABEL_14;
        v33 = v29;
        v27 = byte_18031CD85;
        LODWORD(v34) = 5928;
      }
    }
    else
    {
      v26 = -2060451835;
      LODWORD(v31) = -2060451835;
      if ( (unsigned int)dword_180397B68 <= 2 )
        goto LABEL_14;
      v33 = -2060451835;
      v27 = byte_18032266B;
      LODWORD(v34) = 5891;
    }
    *(_QWORD *)&v30[0] = "Spctl_VirtualDisk_InvalidateReadCache_S1";
LABEL_27:
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v26,
      (_DWORD)v27,
      v11,
      v12,
      (__int64)v30,
      (__int64)&v34,
      (__int64)&v33);
    goto LABEL_14;
  }
  v19 = -2060411838;
  LODWORD(v31) = -2060411838;
  if ( (unsigned int)dword_180397B68 > 2 )
  {
    LODWORD(v34) = 5885;
    *(_QWORD *)&v30[0] = "Spctl_VirtualDisk_InvalidateReadCache_S1";
    v20 = (int *)byte_18031D6D9;
LABEL_13:
    v33 = v19;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v19,
      (_DWORD)v20,
      v13,
      v14,
      (__int64)v30,
      (__int64)&v34,
      (__int64)&v33);
  }
LABEL_14:
  v21 = *((_QWORD *)a1 + 74);
  v22 = _status_t::ToSMRC(&v31);
  _FillMethodResponse(v6, *((unsigned int *)a1 + 146), v22, 0, v21);
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  if ( self )
    MI_Instance_Delete(self);
  if ( v9 )
    LocalFree(v9);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    v33 = 5950;
    v34 = "Spctl_VirtualDisk_InvalidateReadCache_S1";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v23,
      (unsigned int)byte_18031D3F1,
      v24,
      v25,
      (__int64)&v34,
      (__int64)&v33);
  }
  return 0;
}

```

## disassembly

```asm
0x1800a9ab4  push    rbp
0x1800a9ab6  push    rbx
0x1800a9ab7  push    rsi
0x1800a9ab8  push    rdi
0x1800a9ab9  push    r13
0x1800a9abb  push    r14
0x1800a9abd  push    r15
0x1800a9abf  mov     rbp, rsp
0x1800a9ac2  sub     rsp, 70h
0x1800a9ac6  mov     eax, cs:dword_180397B68
0x1800a9acc  lea     rbx, aSpctlVirtualdi_35; "Spctl_VirtualDisk_InvalidateReadCache_S"...
0x1800a9ad3  mov     rsi, rcx
0x1800a9ad6  cmp     eax, 5
0x1800a9ad9  jbe     short loc_1800A9B04
0x1800a9adb  lea     rax, [rbp+arg_0]
0x1800a9adf  mov     [rbp+arg_0], 16D4h
0x1800a9ae6  mov     qword ptr [rsp+70h+dwFlagsAndAttributes], rax
0x1800a9aeb  lea     rdx, byte_180319237
0x1800a9af2  lea     rax, [rbp+arg_8]
0x1800a9af6  mov     [rbp+arg_8], rbx
0x1800a9afa  mov     qword ptr [rsp+70h+dwCreationDisposition], rax
0x1800a9aff  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800a9b04  xor     r14d, r14d
0x1800a9b07  mov     ecx, 220h
0x1800a9b0c  mov     [rbp+BytesReturned], r14d
0x1800a9b10  mov     [rbp+self], r14
0x1800a9b14  mov     [rbp+var_10], r14
0x1800a9b18  mov     [rbp+var_8], r14b
0x1800a9b1c  cmp     [rsi+248h], ecx
0x1800a9b22  jnb     short loc_1800A9B36
0x1800a9b24  mov     rax, [rsi+250h]
0x1800a9b2b  mov     [rax], ecx
0x1800a9b2d  lea     eax, [r14+57h]
0x1800a9b31  jmp     loc_1800A9CAE
0x1800a9b36  movups  xmm0, xmmword ptr [rsi+4]
0x1800a9b3a  mov     r13, [rsi+240h]
0x1800a9b41  lea     rdx, [rbp+self]; struct _MI_Instance **
0x1800a9b45  movups  xmm1, xmmword ptr [rsi+14h]
0x1800a9b49  lea     rcx, [rbp+var_30]; struct _SP_ID *
0x1800a9b4d  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800a9b51  movups  [rbp+var_30], xmm0
0x1800a9b55  mov     rdi, r14
0x1800a9b58  movups  [rbp+var_20], xmm1
0x1800a9b5c  call    ?GetVolumeOnVirtualDisk@@YA?AW4_MI_Result@@PEAU_SP_ID@@PEAPEAU_MI_Instance@@@Z; GetVolumeOnVirtualDisk(_SP_ID *,_MI_Instance * *)
0x1800a9b61  mov     ecx, eax
0x1800a9b63  test    eax, eax
0x1800a9b65  jnz     loc_1800A9E25
0x1800a9b6b  mov     r8, [rbp+self]
0x1800a9b6f  lea     rdx, aPath; "Path"
0x1800a9b76  lea     rcx, [rbp+var_30]
0x1800a9b7a  mov     dword ptr [rbp+var_10], 5200000h
0x1800a9b81  call    ?SmMIGetInstance@@YA?AV?$Nullable@PEAU_MI_Instance@@@@PEBGPEBU_MI_Instance@@@Z; SmMIGetInstance(ushort const *,_MI_Instance const *)
0x1800a9b86  mov     r14, [rax+8]
0x1800a9b8a  xor     eax, eax
0x1800a9b8c  test    r14, r14
0x1800a9b8f  jz      loc_1800A9DF7
0x1800a9b95  cmp     [r14], ax
0x1800a9b99  jz      loc_1800A9DF7
0x1800a9b9f  or      rbx, r15
0x1800a9ba2  inc     rbx
0x1800a9ba5  cmp     [r14+rbx*2], ax
0x1800a9baa  jnz     short loc_1800A9BA2
0x1800a9bac  inc     rbx
0x1800a9baf  mov     ecx, 40h ; '@'; uFlags
0x1800a9bb4  lea     rdx, [rbx+rbx]; uBytes
0x1800a9bb8  call    cs:__imp_LocalAlloc
0x1800a9bbe  mov     rdi, rax
0x1800a9bc1  test    rax, rax
0x1800a9bc4  jnz     loc_1800A9CBD
0x1800a9bca  mov     eax, cs:dword_180397B68
0x1800a9bd0  mov     ecx, 85309C42h
0x1800a9bd5  mov     dword ptr [rbp+var_10], ecx
0x1800a9bd8  cmp     eax, 2
0x1800a9bdb  jbe     short loc_1800A9C19
0x1800a9bdd  lea     rax, aSpctlVirtualdi_35; "Spctl_VirtualDisk_InvalidateReadCache_S"...
0x1800a9be4  mov     dword ptr [rbp+arg_8], 16FDh
0x1800a9beb  mov     qword ptr [rbp+var_30], rax
0x1800a9bef  lea     rdx, byte_18031D6D9
0x1800a9bf6  lea     rax, [rbp+arg_0]
0x1800a9bfa  mov     [rsp+70h+hTemplateFile], rax
0x1800a9bff  lea     rax, [rbp+arg_8]
0x1800a9c03  mov     qword ptr [rsp+70h+dwFlagsAndAttributes], rax
0x1800a9c08  lea     rax, [rbp+var_30]
0x1800a9c0c  mov     qword ptr [rsp+70h+dwCreationDisposition], rax
0x1800a9c11  mov     [rbp+arg_0], ecx
0x1800a9c14  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800a9c19  xor     r14d, r14d
0x1800a9c1c  mov     rbx, [rsi+250h]
0x1800a9c23  lea     rcx, [rbp+var_10]
0x1800a9c27  call    ?ToSMRC@_status_t@@QEAA?AW4SM_RETURN_CODE@@XZ; _status_t::ToSMRC(void)
0x1800a9c2c  mov     edx, [rsi+248h]
0x1800a9c32  xor     r9d, r9d
0x1800a9c35  mov     r8d, eax
0x1800a9c38  mov     qword ptr [rsp+70h+dwCreationDisposition], rbx
0x1800a9c3d  mov     rcx, r13
0x1800a9c40  call    ?_FillMethodResponse@@YAXPEAEKW4SM_RETURN_CODE@@PEAU_SUEX_EXTENDEDSTATUS_OBJECT@@PEAK@Z; _FillMethodResponse(uchar *,ulong,SM_RETURN_CODE,_SUEX_EXTENDEDSTATUS_OBJECT *,ulong *)
0x1800a9c45  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x1800a9c49  jz      short loc_1800A9C54
0x1800a9c4b  mov     rcx, r15; hObject
0x1800a9c4e  call    cs:__imp_CloseHandle
0x1800a9c54  cmp     [rbp+self], r14
0x1800a9c58  jz      short loc_1800A9C63
0x1800a9c5a  mov     rcx, [rbp+self]; self
0x1800a9c5e  call    MI_Instance_Delete
0x1800a9c63  test    rdi, rdi
0x1800a9c66  jz      short loc_1800A9C71
0x1800a9c68  mov     rcx, rdi; hMem
0x1800a9c6b  call    cs:__imp_LocalFree
0x1800a9c71  mov     eax, cs:dword_180397B68
0x1800a9c77  cmp     eax, 5
0x1800a9c7a  jbe     short loc_1800A9CAC
0x1800a9c7c  lea     rax, aSpctlVirtualdi_35; "Spctl_VirtualDisk_InvalidateReadCache_S"...
0x1800a9c83  mov     [rbp+arg_0], 173Eh
0x1800a9c8a  mov     [rbp+arg_8], rax
0x1800a9c8e  lea     rdx, byte_18031D3F1
0x1800a9c95  lea     rax, [rbp+arg_0]
0x1800a9c99  mov     qword ptr [rsp+70h+dwFlagsAndAttributes], rax
0x1800a9c9e  lea     rax, [rbp+arg_8]
0x1800a9ca2  mov     qword ptr [rsp+70h+dwCreationDisposition], rax
0x1800a9ca7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800a9cac  xor     eax, eax
0x1800a9cae  add     rsp, 70h
0x1800a9cb2  pop     r15
0x1800a9cb4  pop     r14
0x1800a9cb6  pop     r13
0x1800a9cb8  pop     rdi
0x1800a9cb9  pop     rsi
0x1800a9cba  pop     rbx
0x1800a9cbb  pop     rbp
0x1800a9cbc  retn
0x1800a9cbd  mov     r8, r14; unsigned __int16 *
0x1800a9cc0  mov     rdx, rbx; unsigned __int64
0x1800a9cc3  mov     rcx, rdi; unsigned __int16 *
0x1800a9cc6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a9ccb  xor     r14d, r14d
0x1800a9cce  test    eax, eax
0x1800a9cd0  jns     short loc_1800A9D2A
0x1800a9cd2  mov     eax, cs:dword_180397B68
0x1800a9cd8  mov     ecx, 85300005h
0x1800a9cdd  mov     dword ptr [rbp+var_10], ecx
0x1800a9ce0  cmp     eax, 2
0x1800a9ce3  jbe     loc_1800A9C1C
0x1800a9ce9  mov     [rbp+arg_0], ecx
0x1800a9cec  lea     rdx, byte_18032266B
0x1800a9cf3  mov     dword ptr [rbp+arg_8], 1703h
0x1800a9cfa  lea     rax, aSpctlVirtualdi_35; "Spctl_VirtualDisk_InvalidateReadCache_S"...
0x1800a9d01  mov     qword ptr [rbp+var_30], rax
0x1800a9d05  lea     rax, [rbp+arg_0]
0x1800a9d09  mov     [rsp+70h+hTemplateFile], rax
0x1800a9d0e  lea     rax, [rbp+arg_8]
0x1800a9d12  mov     qword ptr [rsp+70h+dwFlagsAndAttributes], rax
0x1800a9d17  lea     rax, [rbp+var_30]
0x1800a9d1b  mov     qword ptr [rsp+70h+dwCreationDisposition], rax
0x1800a9d20  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800a9d25  jmp     loc_1800A9C1C
0x1800a9d2a  cmp     word ptr [rdi+rbx*2-4], 5Ch ; '\'
0x1800a9d30  jnz     short loc_1800A9D38
0x1800a9d32  mov     [rdi+rbx*2-4], r14w
0x1800a9d38  mov     [rsp+70h+hTemplateFile], r14; hTemplateFile
0x1800a9d3d  mov     r8d, 3; dwShareMode
0x1800a9d43  mov     [rsp+70h+dwFlagsAndAttributes], r14d; dwFlagsAndAttributes
0x1800a9d48  xor     r9d, r9d; lpSecurityAttributes
0x1800a9d4b  mov     edx, 80000000h; dwDesiredAccess
0x1800a9d50  mov     [rsp+70h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800a9d55  mov     rcx, rdi; lpFileName
0x1800a9d58  call    cs:__imp_CreateFileW
0x1800a9d5e  mov     r15, rax
0x1800a9d61  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a9d65  jnz     short loc_1800A9D95
0x1800a9d67  lea     rcx, [rbp+var_10]; this
0x1800a9d6b  call    ?GetLastError@_status_t@@QEAAJXZ; _status_t::GetLastError(void)
0x1800a9d70  mov     ecx, cs:dword_180397B68
0x1800a9d76  cmp     ecx, 2
0x1800a9d79  jbe     loc_1800A9C1C
0x1800a9d7f  mov     [rbp+arg_0], eax
0x1800a9d82  lea     rdx, byte_18031B91B
0x1800a9d89  mov     dword ptr [rbp+arg_8], 171Ah
0x1800a9d90  jmp     loc_1800A9CFA
0x1800a9d95  mov     [rsp+70h+lpOverlapped], r14; lpOverlapped
0x1800a9d9a  lea     rax, [rbp+BytesReturned]
0x1800a9d9e  mov     [rsp+70h+hTemplateFile], rax; lpBytesReturned
0x1800a9da3  xor     r9d, r9d; nInBufferSize
0x1800a9da6  mov     [rsp+70h+dwFlagsAndAttributes], r14d; nOutBufferSize
0x1800a9dab  xor     r8d, r8d; lpInBuffer
0x1800a9dae  mov     edx, 9039Ch; dwIoControlCode
0x1800a9db3  mov     qword ptr [rsp+70h+dwCreationDisposition], r14; lpOutBuffer
0x1800a9db8  mov     rcx, r15; hDevice
0x1800a9dbb  call    cs:__imp_DeviceIoControl
0x1800a9dc1  test    eax, eax
0x1800a9dc3  jnz     loc_1800A9C1C
0x1800a9dc9  lea     rcx, [rbp+var_10]; this
0x1800a9dcd  call    ?GetLastError@_status_t@@QEAAJXZ; _status_t::GetLastError(void)
0x1800a9dd2  mov     ecx, cs:dword_180397B68
0x1800a9dd8  cmp     ecx, 2
0x1800a9ddb  jbe     loc_1800A9C1C
0x1800a9de1  mov     [rbp+arg_0], eax
0x1800a9de4  lea     rdx, byte_18031CD85
0x1800a9deb  mov     dword ptr [rbp+arg_8], 1728h
0x1800a9df2  jmp     loc_1800A9CFA
0x1800a9df7  mov     eax, cs:dword_180397B68
0x1800a9dfd  mov     ecx, 85300005h
0x1800a9e02  mov     dword ptr [rbp+var_10], ecx
0x1800a9e05  cmp     eax, 2
0x1800a9e08  jbe     loc_1800A9C19
0x1800a9e0e  mov     dword ptr [rbp+arg_8], 16F2h
0x1800a9e15  lea     rdx, dword_18031E37C
0x1800a9e1c  mov     qword ptr [rbp+var_30], rbx
0x1800a9e20  jmp     loc_1800A9BF6
0x1800a9e25  mov     eax, cs:dword_180397B68
0x1800a9e2b  or      ecx, 85200000h
0x1800a9e31  mov     dword ptr [rbp+var_10], ecx
0x1800a9e34  cmp     eax, 2
0x1800a9e37  jbe     loc_1800A9C1C
0x1800a9e3d  mov     [rbp+arg_0], ecx
0x1800a9e40  lea     rdx, word_18031D98E
0x1800a9e47  mov     dword ptr [rbp+arg_8], 16E9h
0x1800a9e4e  mov     qword ptr [rbp+var_30], rbx
0x1800a9e52  jmp     loc_1800A9D05
```
