# SuexUpdateFirmwareEnclosure(_SU_ENCLOSURE_OBJECT *,ushort *,ushort)

- ea: `0x180038a58`
- end: `0x180039026`
- name: `?SuexUpdateFirmwareEnclosure@@YA?AV_status_t@@PEAU_SU_ENCLOSURE_OBJECT@@PEAGG@Z`
- size: `1486`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, installer_update`

## callers

- `0x1800a360c`

## callees

- `0x1800011b0`
- `0x1800014ec`
- `0x1800015b8`
- `0x180001f0c`
- `0x180006290`
- `0x18000b964`
- `0x18000bb68`
- `0x18000cd18`
- `0x18000cd44`
- `0x18000cd6c`
- `0x18000ce3c`
- `0x18000f3bc`
- `0x18001adec`
- `0x180028f84`
- `0x18002b2bc`
- `0x18002cdc0`
- `0x180038a58`
- `0x18003902c`
- `0x18019e2c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038f6e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038f91`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038f6e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038f91`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038f56`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038f79`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038f56`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038f79`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038fa4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038fa4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180038c18`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180038c18`

## string_xrefs

- `0x180038a96`: `SuexUpdateFirmwareEnclosure`
- `0x180038b4d`: `SuexUpdateFirmwareEnclosure`
- `0x180038bc6`: `SuexUpdateFirmwareEnclosure`
- `0x180038c47`: `SuexUpdateFirmwareEnclosure`
- `0x180038cac`: `SuexUpdateFirmwareEnclosure`
- `0x180038d9a`: `SuexUpdateFirmwareEnclosure`
- `0x180038fc5`: `SuexUpdateFirmwareEnclosure`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int *__fastcall SuexUpdateFirmwareEnclosure(int *a1, __int64 a2, __int64 a3, __int16 a4)
{
  __int64 v8; // r14
  struct _STORAGE_HW_FIRMWARE_INFO *v9; // rdi
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  int LastError; // ecx
  int v14; // r8d
  int v15; // r9d
  struct _STORAGE_HW_FIRMWARE_INFO **v16; // rax
  char *v17; // rdx
  HANDLE FileW; // rax
  int Firmware; // eax
  int v20; // r8d
  int v21; // r9d
  int v22; // ecx
  __int64 v23; // rax
  __int64 v24; // r8
  __int64 v25; // rax
  unsigned __int8 *v26; // rsi
  int v27; // r8d
  int v28; // r9d
  unsigned __int8 *v29; // rcx
  BYTE *Revision; // rcx
  HANDLE ProcessHeap; // rax
  HANDLE v32; // rax
  int v33; // ecx
  int v34; // r8d
  __int16 v35; // r9
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  int v38; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v39; // [rsp+84h] [rbp-7Ch] BYREF
  struct _STORAGE_HW_FIRMWARE_INFO *v40; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int64 v41; // [rsp+90h] [rbp-70h] BYREF
  LPVOID lpMem; // [rsp+98h] [rbp-68h] BYREF
  struct _GUID v43; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v44; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int8 *v45; // [rsp+B8h] [rbp-48h] BYREF
  BYTE *v46; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v47; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v48; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v49; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v50; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v51[4]; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD v52[5]; // [rsp+108h] [rbp+8h] BYREF
  WCHAR FileName[256]; // [rsp+130h] [rbp+30h] BYREF

  if ( (unsigned int)dword_180397B68 > 5 )
  {
    v38 = 4728;
    lpMem = "SuexUpdateFirmwareEnclosure";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"SuexUpdateFirmwareEnclosure",
      (unsigned int)byte_1802F6B6D,
      a3,
      a4,
      (__int64)&lpMem,
      (__int64)&v38);
  }
  CSmTimer::CSmTimer((CSmTimer *)v52);
  CSmTimer::CSmTimer((CSmTimer *)v51);
  v44 = 0;
  v8 = -1;
  lpMem = 0;
  v9 = 0;
  v40 = 0;
  *(_QWORD *)a1 = 0;
  *((_BYTE *)a1 + 8) = 0;
  v43 = *(struct _GUID *)(a2 + 40);
  v10 = SmGuidToString(&v43, &v44);
  *a1 = v10;
  a1[1] = 0;
  *((_BYTE *)a1 + 8) = 0;
  *(_WORD *)((char *)a1 + 9) = *(_WORD *)&v43.Data4[1];
  *((_BYTE *)a1 + 11) = v43.Data4[3];
  if ( v10 < 0 )
  {
    if ( (unsigned int)dword_180397B68 > 2 )
    {
      v38 = v10;
      v39 = 4743;
      v40 = (struct _STORAGE_HW_FIRMWARE_INFO *)"SuexUpdateFirmwareEnclosure";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v10,
        (unsigned int)byte_1802FB5AB,
        v11,
        v12,
        (__int64)&v40,
        (__int64)&v39,
        (__int64)&v38);
    }
    goto LABEL_25;
  }
  LastError = StringCchPrintfW(FileName, 0x100u, L"\\\\.\\StorageEnclosure#%s", v44);
  *a1 = LastError;
  a1[1] = 0;
  *((_BYTE *)a1 + 8) = 0;
  *(_WORD *)((char *)a1 + 9) = *(_WORD *)&v43.Data4[1];
  *((_BYTE *)a1 + 11) = v43.Data4[3];
  if ( LastError < 0 )
  {
    if ( (unsigned int)dword_180397B68 <= 2 )
      goto LABEL_25;
    v38 = 4754;
    v40 = (struct _STORAGE_HW_FIRMWARE_INFO *)"SuexUpdateFirmwareEnclosure";
    v16 = &v40;
    v17 = (char *)&dword_1802F7E6C;
    goto LABEL_24;
  }
  FileW = CreateFileW(FileName, 0xC0000000, 7u, 0, 3u, 0x80u, 0);
  v8 = (__int64)FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = _status_t::GetLastError((_status_t *)a1);
    if ( (unsigned int)dword_180397B68 <= 2 )
      goto LABEL_25;
    v38 = 4768;
    v40 = (struct _STORAGE_HW_FIRMWARE_INFO *)"SuexUpdateFirmwareEnclosure";
    v16 = &v40;
    v17 = &byte_1802FCE77;
    goto LABEL_24;
  }
  Firmware = PuGetFirmware(FileW, (enum _STORAGE_BUS_TYPE)*(_DWORD *)(a2 + 2664), &v40);
  _status_t::SetBoolGle((_status_t *)a1, Firmware);
  v22 = *a1;
  if ( *a1 >= 0 )
  {
    v9 = v40;
    if ( a3
      && (CSmTimer::Start((CSmTimer *)v51),
          LOBYTE(dwCreationDisposition) = a4,
          v23 = SuexDownloadFirmware(&v43, v8, v9, a3, dwCreationDisposition),
          *(_QWORD *)a1 = *(_QWORD *)v23,
          a1[2] = *(_DWORD *)(v23 + 8),
          CSmTimer::Stop((CSmTimer *)v51),
          LastError = *a1,
          *a1 < 0) )
    {
      if ( (unsigned int)dword_180397B68 <= 2 )
        goto LABEL_25;
      v38 = 4795;
      v17 = (char *)word_1802FD792;
    }
    else
    {
      CSmTimer::Start((CSmTimer *)v52);
      LOBYTE(v24) = a4;
      v25 = SuexActivateFirmware(&v43, v8, v24);
      *(_QWORD *)a1 = *(_QWORD *)v25;
      a1[2] = *(_DWORD *)(v25 + 8);
      CSmTimer::Stop((CSmTimer *)v52);
      LastError = *a1;
      if ( *a1 >= 0 || (unsigned int)dword_180397B68 <= 2 )
        goto LABEL_25;
      v38 = 4809;
      v17 = &byte_1802FCACF;
    }
    v41 = (unsigned __int64)"SuexUpdateFirmwareEnclosure";
    v16 = (struct _STORAGE_HW_FIRMWARE_INFO **)&v41;
LABEL_24:
    v39 = LastError;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      LastError,
      (_DWORD)v17,
      v14,
      v15,
      (__int64)v16,
      (__int64)&v38,
      (__int64)&v39);
    goto LABEL_25;
  }
  if ( (unsigned int)dword_180397B68 > 2 )
  {
    v39 = *a1;
    v38 = 4778;
    v41 = (unsigned __int64)"SuexUpdateFirmwareEnclosure";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v22,
      (unsigned int)&byte_1802F6F5F,
      v20,
      v21,
      (__int64)&v41,
      (__int64)&v38,
      (__int64)&v39);
  }
  v9 = v40;
LABEL_25:
  PuGetFirmware((HANDLE)v8, *(enum _STORAGE_BUS_TYPE *)(a2 + 2664), (struct _STORAGE_HW_FIRMWARE_INFO **)&lpMem);
  v26 = (unsigned __int8 *)lpMem;
  if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
  {
    v39 = _status_t::ToWin32((_status_t *)a1);
    v41 = (unsigned __int64)(1000LL * (v52[1] - v52[0])) / v52[2];
    lpMem = (LPVOID)((unsigned __int64)(1000LL * (v51[1] - v51[0])) / v51[2]);
    if ( v26 )
      v29 = &v26[32 * v26[10] + 40];
    else
      v29 = 0;
    v45 = v29;
    if ( v9 )
      Revision = v9->Slot[v9->ActiveSlot].Revision;
    else
      Revision = 0;
    v46 = Revision;
    LOWORD(v38) = a4;
    LODWORD(v40) = *(_DWORD *)(a2 + 2664);
    v47 = a2 + *(unsigned int *)(a2 + 2660) + 56LL;
    v48 = a2 + *(unsigned int *)(a2 + 2652) + 56LL;
    v49 = a2 + *(unsigned int *)(a2 + 2648) + 56LL;
    v50 = a2 + 64;
    *(_QWORD *)&v43.Data1 = L"StorageEnclosure";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v49,
      (unsigned int)byte_1802F6179,
      v27,
      v28,
      (__int64)&v43,
      (__int64)&v50,
      (__int64)&v49,
      (__int64)&v48,
      (__int64)&v47,
      (__int64)&v40,
      (__int64)&v38,
      (__int64)&v46,
      (__int64)&v45,
      (__int64)&lpMem,
      (__int64)&v41,
      (__int64)&v39);
  }
  if ( v26 )
  {
    ProcessHeap = GetProcessHeap();
    if ( ProcessHeap )
      HeapFree(ProcessHeap, 0, v26);
  }
  if ( v9 )
  {
    v32 = GetProcessHeap();
    if ( v32 )
      HeapFree(v32, 0, v9);
  }
  if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v8);
  SmFreeString(&v44);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    LODWORD(v40) = 4844;
    *(_QWORD *)&v43.Data1 = "SuexUpdateFirmwareEnclosure";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v33,
      (unsigned int)&byte_1802F5757,
      v34,
      v35,
      (__int64)&v43,
      (__int64)&v40);
  }
  CSmTimer::~CSmTimer((CSmTimer *)v51);
  CSmTimer::~CSmTimer((CSmTimer *)v52);
  return a1;
}

```

## disassembly

```asm
0x180038a58  push    rbp
0x180038a5a  push    rbx
0x180038a5b  push    rsi
0x180038a5c  push    rdi
0x180038a5d  push    r12
0x180038a5f  push    r14
0x180038a61  push    r15
0x180038a63  lea     rbp, [rsp-240h]
0x180038a6b  sub     rsp, 340h
0x180038a72  mov     rax, cs:__security_cookie
0x180038a79  xor     rax, rsp
0x180038a7c  mov     [rbp+270h+var_40], rax
0x180038a83  movzx   r12d, r9w
0x180038a87  mov     rsi, r8
0x180038a8a  mov     r15, rdx
0x180038a8d  mov     rbx, rcx
0x180038a90  mov     eax, cs:dword_180397B68
0x180038a96  lea     rcx, aSuexupdatefirm_0; "SuexUpdateFirmwareEnclosure"
0x180038a9d  cmp     eax, 5
0x180038aa0  jbe     short loc_180038ACB
0x180038aa2  mov     [rbp+270h+var_2F0], 1278h
0x180038aa9  mov     [rbp+270h+lpMem], rcx
0x180038aad  lea     rax, [rbp+270h+var_2F0]
0x180038ab1  mov     qword ptr [rsp+370h+dwFlagsAndAttributes], rax
0x180038ab6  lea     rax, [rbp+270h+lpMem]
0x180038aba  mov     qword ptr [rsp+370h+dwCreationDisposition], rax
0x180038abf  lea     rdx, byte_1802F6B6D
0x180038ac6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180038acb  lea     rcx, [rbp+270h+var_268]; this
0x180038acf  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x180038ad4  nop
0x180038ad5  lea     rcx, [rbp+270h+var_288]; this
0x180038ad9  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x180038ade  nop
0x180038adf  mov     [rbp+270h+var_2C0], 0
0x180038ae7  or      r14, 0FFFFFFFFFFFFFFFFh
0x180038aeb  mov     [rbp+270h+lpMem], 0
0x180038af3  xor     edi, edi
0x180038af5  mov     [rbp+270h+var_2E8], rdi
0x180038af9  mov     [rbx], rdi
0x180038afc  mov     [rbx+8], dil
0x180038b00  movups  xmm0, xmmword ptr [r15+28h]
0x180038b05  movdqu  xmmword ptr [rbp+270h+var_2D0.Data1], xmm0
0x180038b0a  lea     rdx, [rbp+270h+var_2C0]; unsigned __int16 **
0x180038b0e  lea     rcx, [rbp+270h+var_2D0]; struct _GUID
0x180038b12  call    ?SmGuidToString@@YAJU_GUID@@PEAPEAG@Z; SmGuidToString(_GUID,ushort * *)
0x180038b17  mov     ecx, eax
0x180038b19  mov     [rbx], eax
0x180038b1b  mov     [rbx+4], edi
0x180038b1e  mov     [rbx+8], dil
0x180038b22  movzx   eax, word ptr [rbp+270h+var_2D0.Data4+1]
0x180038b26  mov     [rbx+9], ax
0x180038b2a  mov     al, [rbp+270h+var_2D0.Data4+3]
0x180038b2d  mov     [rbx+0Bh], al
0x180038b30  test    ecx, ecx
0x180038b32  jns     short loc_180038B7A
0x180038b34  mov     eax, cs:dword_180397B68
0x180038b3a  cmp     eax, 2
0x180038b3d  jbe     loc_180038DC8
0x180038b43  mov     [rbp+270h+var_2F0], ecx
0x180038b46  mov     [rbp+270h+var_2EC], 1287h
0x180038b4d  lea     rax, aSuexupdatefirm_0; "SuexUpdateFirmwareEnclosure"
0x180038b54  mov     [rbp+270h+var_2E8], rax
0x180038b58  lea     rax, [rbp+270h+var_2F0]
0x180038b5c  mov     [rsp+370h+hTemplateFile], rax
0x180038b61  lea     rax, [rbp+270h+var_2EC]
0x180038b65  mov     qword ptr [rsp+370h+dwFlagsAndAttributes], rax
0x180038b6a  lea     rax, [rbp+270h+var_2E8]
0x180038b6e  lea     rdx, byte_1802FB5AB
0x180038b75  jmp     loc_180038DBE
0x180038b7a  mov     r9, [rbp+270h+var_2C0]
0x180038b7e  lea     r8, aStorageenclosu_1; "\\\\.\\StorageEnclosure#%s"
0x180038b85  mov     edx, 100h; unsigned __int64
0x180038b8a  lea     rcx, [rbp+270h+FileName]; unsigned __int16 *
0x180038b8e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180038b93  mov     ecx, eax
0x180038b95  mov     [rbx], eax
0x180038b97  mov     [rbx+4], edi
0x180038b9a  mov     [rbx+8], dil
0x180038b9e  movzx   eax, word ptr [rbp+270h+var_2D0.Data4+1]
0x180038ba2  mov     [rbx+9], ax
0x180038ba6  mov     al, [rbp+270h+var_2D0.Data4+3]
0x180038ba9  mov     [rbx+0Bh], al
0x180038bac  test    ecx, ecx
0x180038bae  jns     short loc_180038BF3
0x180038bb0  mov     eax, cs:dword_180397B68
0x180038bb6  cmp     eax, 2
0x180038bb9  jbe     loc_180038DC8
0x180038bbf  mov     [rbp+270h+var_2F0], 1292h
0x180038bc6  lea     rax, aSuexupdatefirm_0; "SuexUpdateFirmwareEnclosure"
0x180038bcd  mov     [rbp+270h+var_2E8], rax
0x180038bd1  lea     rax, [rbp+270h+var_2EC]
0x180038bd5  mov     [rsp+370h+hTemplateFile], rax
0x180038bda  lea     rax, [rbp+270h+var_2F0]
0x180038bde  mov     qword ptr [rsp+370h+dwFlagsAndAttributes], rax
0x180038be3  lea     rax, [rbp+270h+var_2E8]
0x180038be7  lea     rdx, dword_1802F7E6C
0x180038bee  jmp     loc_180038DBB
0x180038bf3  mov     [rsp+370h+hTemplateFile], rdi; hTemplateFile
0x180038bf8  mov     [rsp+370h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180038c00  mov     [rsp+370h+dwCreationDisposition], 3; dwCreationDisposition
0x180038c08  xor     r9d, r9d; lpSecurityAttributes
0x180038c0b  mov     edx, 0C0000000h; dwDesiredAccess
0x180038c10  lea     r8d, [r9+7]; dwShareMode
0x180038c14  lea     rcx, [rbp+270h+FileName]; lpFileName
0x180038c18  call    cs:__imp_CreateFileW
0x180038c1e  mov     r14, rax
0x180038c21  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180038c25  jnz     short loc_180038C74
0x180038c27  mov     rcx, rbx; this
0x180038c2a  call    ?GetLastError@_status_t@@QEAAJXZ; _status_t::GetLastError(void)
0x180038c2f  mov     ecx, eax
0x180038c31  mov     eax, cs:dword_180397B68
0x180038c37  cmp     eax, 2
0x180038c3a  jbe     loc_180038DC8
0x180038c40  mov     [rbp+270h+var_2F0], 12A0h
0x180038c47  lea     rax, aSuexupdatefirm_0; "SuexUpdateFirmwareEnclosure"
0x180038c4e  mov     [rbp+270h+var_2E8], rax
0x180038c52  lea     rax, [rbp+270h+var_2EC]
0x180038c56  mov     [rsp+370h+hTemplateFile], rax
0x180038c5b  lea     rax, [rbp+270h+var_2F0]
0x180038c5f  mov     qword ptr [rsp+370h+dwFlagsAndAttributes], rax
0x180038c64  lea     rax, [rbp+270h+var_2E8]
0x180038c68  lea     rdx, byte_1802FCE77
0x180038c6f  jmp     loc_180038DBB
0x180038c74  lea     r8, [rbp+270h+var_2E8]; struct _STORAGE_HW_FIRMWARE_INFO **
0x180038c78  mov     edx, [r15+0A68h]; enum _STORAGE_BUS_TYPE
0x180038c7f  mov     rcx, r14; hDevice
0x180038c82  call    ?PuGetFirmware@@YAHPEAXW4_STORAGE_BUS_TYPE@@PEAPEAU_STORAGE_HW_FIRMWARE_INFO@@@Z; PuGetFirmware(void *,_STORAGE_BUS_TYPE,_STORAGE_HW_FIRMWARE_INFO * *)
0x180038c87  mov     edx, eax; int
0x180038c89  mov     rcx, rbx; this
0x180038c8c  call    ?SetBoolGle@_status_t@@QEAAJH@Z; _status_t::SetBoolGle(int)
0x180038c91  mov     ecx, [rbx]
0x180038c93  test    ecx, ecx
0x180038c95  jns     short loc_180038CE7
0x180038c97  mov     eax, cs:dword_180397B68
0x180038c9d  cmp     eax, 2
0x180038ca0  jbe     short loc_180038CDE
0x180038ca2  mov     [rbp+270h+var_2EC], ecx
0x180038ca5  mov     [rbp+270h+var_2F0], 12AAh
0x180038cac  lea     rax, aSuexupdatefirm_0; "SuexUpdateFirmwareEnclosure"
0x180038cb3  mov     [rbp+270h+var_2E0], rax
0x180038cb7  lea     rax, [rbp+270h+var_2EC]
0x180038cbb  mov     [rsp+370h+hTemplateFile], rax
0x180038cc0  lea     rax, [rbp+270h+var_2F0]
0x180038cc4  mov     qword ptr [rsp+370h+dwFlagsAndAttributes], rax
0x180038cc9  lea     rax, [rbp+270h+var_2E0]
0x180038ccd  mov     qword ptr [rsp+370h+dwCreationDisposition], rax
0x180038cd2  lea     rdx, byte_1802F6F5F
0x180038cd9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180038cde  mov     rdi, [rbp+270h+var_2E8]
0x180038ce2  jmp     loc_180038DC8
0x180038ce7  mov     rdi, [rbp+270h+var_2E8]
0x180038ceb  test    rsi, rsi
0x180038cee  jz      short loc_180038D4C
0x180038cf0  lea     rcx, [rbp+270h+var_288]; this
0x180038cf4  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x180038cf9  mov     byte ptr [rsp+370h+dwCreationDisposition], r12b
0x180038cfe  mov     r9, rsi
0x180038d01  mov     r8, rdi
0x180038d04  mov     rdx, r14
0x180038d07  lea     rcx, [rbp+270h+var_2D0]
0x180038d0b  call    ?SuexDownloadFirmware@@YA?AV_status_t@@PEAXPEAU_STORAGE_HW_FIRMWARE_INFO@@PEAGE@Z; SuexDownloadFirmware(void *,_STORAGE_HW_FIRMWARE_INFO *,ushort *,uchar)
0x180038d10  movsd   xmm0, qword ptr [rax]
0x180038d14  movsd   qword ptr [rbx], xmm0
0x180038d18  mov     eax, [rax+8]
0x180038d1b  mov     [rbx+8], eax
0x180038d1e  lea     rcx, [rbp+270h+var_288]; this
0x180038d22  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x180038d27  mov     ecx, [rbx]
0x180038d29  test    ecx, ecx
0x180038d2b  jns     short loc_180038D4C
0x180038d2d  mov     eax, cs:dword_180397B68
0x180038d33  cmp     eax, 2
0x180038d36  jbe     loc_180038DC8
0x180038d3c  mov     [rbp+270h+var_2F0], 12BBh
0x180038d43  lea     rdx, word_1802FD792
0x180038d4a  jmp     short loc_180038D9A
0x180038d4c  lea     rcx, [rbp+270h+var_268]; this
0x180038d50  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x180038d55  mov     r8b, r12b
0x180038d58  mov     rdx, r14
0x180038d5b  lea     rcx, [rbp+270h+var_2D0]
0x180038d5f  call    ?SuexActivateFirmware@@YA?AV_status_t@@PEAXE@Z; SuexActivateFirmware(void *,uchar)
0x180038d64  movsd   xmm0, qword ptr [rax]
0x180038d68  movsd   qword ptr [rbx], xmm0
0x180038d6c  mov     eax, [rax+8]
0x180038d6f  mov     [rbx+8], eax
0x180038d72  lea     rcx, [rbp+270h+var_268]; this
0x180038d76  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x180038d7b  mov     ecx, [rbx]
0x180038d7d  test    ecx, ecx
0x180038d7f  jns     short loc_180038DC8
0x180038d81  mov     eax, cs:dword_180397B68
0x180038d87  cmp     eax, 2
0x180038d8a  jbe     short loc_180038DC8
0x180038d8c  mov     [rbp+270h+var_2F0], 12C9h
0x180038d93  lea     rdx, byte_1802FCACF
0x180038d9a  lea     rax, aSuexupdatefirm_0; "SuexUpdateFirmwareEnclosure"
0x180038da1  mov     [rbp+270h+var_2E0], rax
0x180038da5  lea     rax, [rbp+270h+var_2EC]
0x180038da9  mov     [rsp+370h+hTemplateFile], rax
0x180038dae  lea     rax, [rbp+270h+var_2F0]
0x180038db2  mov     qword ptr [rsp+370h+dwFlagsAndAttributes], rax
0x180038db7  lea     rax, [rbp+270h+var_2E0]
0x180038dbb  mov     [rbp+270h+var_2EC], ecx
0x180038dbe  mov     qword ptr [rsp+370h+dwCreationDisposition], rax
0x180038dc3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180038dc8  lea     r8, [rbp+270h+lpMem]; struct _STORAGE_HW_FIRMWARE_INFO **
0x180038dcc  mov     edx, [r15+0A68h]; enum _STORAGE_BUS_TYPE
0x180038dd3  mov     rcx, r14; hDevice
0x180038dd6  call    ?PuGetFirmware@@YAHPEAXW4_STORAGE_BUS_TYPE@@PEAPEAU_STORAGE_HW_FIRMWARE_INFO@@@Z; PuGetFirmware(void *,_STORAGE_BUS_TYPE,_STORAGE_HW_FIRMWARE_INFO * *)
0x180038ddb  mov     eax, cs:dword_180397B68
0x180038de1  mov     rsi, [rbp+270h+lpMem]
0x180038de5  cmp     eax, 5
0x180038de8  jbe     loc_180038F51
0x180038dee  mov     rdx, 400000000000h
0x180038df8  lea     rcx, dword_180397B68
0x180038dff  call    _tlgKeywordOn
0x180038e04  test    al, al
0x180038e06  jz      loc_180038F51
0x180038e0c  mov     rcx, rbx; this
0x180038e0f  call    ?ToWin32@_status_t@@QEAAKXZ; _status_t::ToWin32(void)
0x180038e14  mov     [rbp+270h+var_2EC], eax
0x180038e17  mov     rax, [rbp+270h+var_260]
0x180038e1b  sub     rax, [rbp+270h+var_268]
0x180038e1f  imul    rax, 3E8h
0x180038e26  xor     edx, edx
0x180038e28  div     [rbp+270h+var_258]
0x180038e2c  mov     [rbp+270h+var_2E0], rax
0x180038e30  mov     rax, [rbp+270h+var_280]
0x180038e34  sub     rax, [rbp+270h+var_288]
0x180038e38  imul    rax, 3E8h
0x180038e3f  xor     edx, edx
0x180038e41  div     [rbp+270h+var_278]
0x180038e45  mov     [rbp+270h+lpMem], rax
0x180038e49  test    rsi, rsi
0x180038e4c  jz      short loc_180038E5F
0x180038e4e  movzx   ecx, byte ptr [rsi+0Ah]
0x180038e52  shl     rcx, 5
0x180038e56  add     rcx, 28h ; '('
0x180038e5a  add     rcx, rsi
0x180038e5d  jmp     short loc_180038E61
0x180038e5f  xor     ecx, ecx
0x180038e61  mov     [rbp+270h+var_2B8], rcx
0x180038e65  test    rdi, rdi
0x180038e68  jz      short loc_180038E7B
0x180038e6a  movzx   ecx, byte ptr [rdi+0Ah]
0x180038e6e  shl     rcx, 5
0x180038e72  add     rcx, 28h ; '('
0x180038e76  add     rcx, rdi
0x180038e79  jmp     short loc_180038E7D
0x180038e7b  xor     ecx, ecx
0x180038e7d  mov     [rbp+270h+var_2B0], rcx
0x180038e81  mov     word ptr [rbp+270h+var_2F0], r12w
0x180038e86  mov     eax, [r15+0A68h]
0x180038e8d  mov     dword ptr [rbp+270h+var_2E8], eax
0x180038e90  mov     ecx, [r15+0A64h]
0x180038e97  add     rcx, 38h ; '8'
0x180038e9b  add     rcx, r15
0x180038e9e  mov     [rbp+270h+var_2A8], rcx
0x180038ea2  mov     ecx, [r15+0A5Ch]
0x180038ea9  add     rcx, 38h ; '8'
0x180038ead  add     rcx, r15
0x180038eb0  mov     [rbp+270h+var_2A0], rcx
0x180038eb4  mov     ecx, [r15+0A58h]
0x180038ebb  add     rcx, 38h ; '8'
0x180038ebf  add     rcx, r15
0x180038ec2  mov     [rbp+270h+var_298], rcx
0x180038ec6  lea     rax, [r15+40h]
0x180038eca  mov     [rbp+270h+var_290], rax
0x180038ece  lea     rax, aStorageenclosu_0; "StorageEnclosure"
0x180038ed5  mov     qword ptr [rbp+270h+var_2D0.Data1], rax
0x180038ed9  lea     rax, [rbp+270h+var_2EC]
0x180038edd  mov     [rsp+370h+var_2F8], rax
0x180038ee2  lea     rax, [rbp+270h+var_2E0]
0x180038ee6  mov     [rsp+370h+var_300], rax
0x180038eeb  lea     rax, [rbp+270h+lpMem]
0x180038eef  mov     [rsp+370h+var_308], rax
0x180038ef4  lea     rax, [rbp+270h+var_2B8]
0x180038ef8  mov     [rsp+370h+var_310], rax
0x180038efd  lea     rax, [rbp+270h+var_2B0]
0x180038f01  mov     [rsp+370h+var_318], rax
0x180038f06  lea     rax, [rbp+270h+var_2F0]
0x180038f0a  mov     [rsp+370h+var_320], rax
0x180038f0f  lea     rax, [rbp+270h+var_2E8]
0x180038f13  mov     [rsp+370h+var_328], rax
0x180038f18  lea     rax, [rbp+270h+var_2A8]
0x180038f1c  mov     [rsp+370h+var_330], rax
0x180038f21  lea     rax, [rbp+270h+var_2A0]
0x180038f25  mov     [rsp+370h+var_338], rax
0x180038f2a  lea     rax, [rbp+270h+var_298]
0x180038f2e  mov     [rsp+370h+hTemplateFile], rax
0x180038f33  lea     rax, [rbp+270h+var_290]
0x180038f37  mov     qword ptr [rsp+370h+dwFlagsAndAttributes], rax
0x180038f3c  lea     rax, [rbp+270h+var_2D0]
0x180038f40  mov     qword ptr [rsp+370h+dwCreationDisposition], rax
0x180038f45  lea     rdx, byte_1802F6179
0x180038f4c  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByRef@$0BA@@@U1@U1@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapSz@D@@U5@U?$_tlgWrapperByVal@$07@@U6@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByRef@$0BA@@@333AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapSz@D@@7AEBU?$_tlgWrapperByVal@$07@@85@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180038f51  test    rsi, rsi
  ... truncated ...
```
