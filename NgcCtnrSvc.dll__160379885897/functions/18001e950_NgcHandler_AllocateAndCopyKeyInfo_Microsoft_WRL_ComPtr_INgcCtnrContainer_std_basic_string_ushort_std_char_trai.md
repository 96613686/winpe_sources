# NgcHandler::AllocateAndCopyKeyInfo(Microsoft::WRL::ComPtr<INgcCtnrContainer> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,NgcRpcKeyInfo *)

- ea: `0x18001e950`
- end: `0x18001f5c1`
- name: `?AllocateAndCopyKeyInfo@NgcHandler@@CAJAEAV?$ComPtr@UINgcCtnrContainer@@@WRL@Microsoft@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUNgcRpcKeyInfo@@@Z`
- size: `3185`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000f040`

## callees

- `0x180004960`
- `0x18000a8e0`
- `0x18000c7e0`
- `0x18000ee90`
- `0x18001e950`
- `0x1800208b0`
- `0x18002c640`
- `0x18002cae0`
- `0x180080010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001eadd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001eb0f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ee3a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001effd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f4b8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f4ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f526`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001eadd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001eb0f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ee3a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001effd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f4b8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f4ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f526`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001eb23`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ee4e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f011`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f4cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f503`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f53a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001eb23`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ee4e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f011`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f4cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f503`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f53a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001eaf4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001eaf4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001ebe7`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001eda3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001ef8f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001f0d5`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001f370`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001f435`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001ebe7`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001eda3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001ef8f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001f0d5`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001f370`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001f435`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f2b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f451`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f561`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f2b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f451`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f561`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall NgcHandler::AllocateAndCopyKeyInfo(__int64 **a1, _QWORD *a2, __int64 a3)
{
  int v6; // ebx
  unsigned __int64 v7; // rdx
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rcx
  unsigned __int64 v10; // rdx
  unsigned __int16 *v11; // rcx
  unsigned __int64 v12; // rdx
  unsigned __int16 *v13; // rcx
  unsigned __int64 v15; // r14
  SIZE_T v16; // rbx
  HANDLE ProcessHeap; // rax
  void *v18; // rax
  unsigned __int64 v19; // rdx
  unsigned __int16 *v20; // rcx
  unsigned __int64 v21; // rdx
  unsigned __int16 *v22; // rcx
  unsigned __int64 v23; // rdx
  unsigned __int16 *v24; // rcx
  const unsigned __int16 *v25; // r8
  int v26; // eax
  unsigned __int64 v27; // r14
  LPVOID v28; // rax
  void *v29; // rbx
  HANDLE v30; // rax
  char *v31; // rax
  const unsigned __int16 *v32; // r8
  int v33; // eax
  unsigned int v34; // ebx
  char *v35; // rax
  unsigned __int64 v36; // r14
  void *v37; // rax
  const unsigned __int16 *v38; // r8
  int v39; // eax
  __int64 *v40; // rcx
  __int64 v41; // rax
  _QWORD *v42; // r8
  int v43; // eax
  __int64 *v44; // rcx
  __int64 v45; // rax
  _QWORD *v46; // r8
  int v47; // r14d
  void *v48; // rcx
  void *v49; // rcx
  LPVOID v50; // rax
  void *v51; // rbx
  HANDLE v52; // rax
  LPVOID v53; // rax
  void *v54; // rbx
  HANDLE v55; // rax
  LPVOID v56; // rax
  void *v57; // rbx
  HANDLE v58; // rax
  void *v59; // rcx
  bool v60; // zf
  unsigned int v61; // [rsp+40h] [rbp-C0h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID lpMem[2]; // [rsp+68h] [rbp-98h] BYREF
  LPVOID v65; // [rsp+78h] [rbp-88h]
  __int64 v66; // [rsp+80h] [rbp-80h] BYREF
  int v67; // [rsp+88h] [rbp-78h] BYREF
  _QWORD *v68; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v69[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v70; // [rsp+A8h] [rbp-58h]
  unsigned __int64 v71; // [rsp+B0h] [rbp-50h]
  unsigned __int16 *v72[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v73; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v74; // [rsp+D0h] [rbp-30h]
  unsigned __int16 *v75[2]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v76; // [rsp+E8h] [rbp-18h]
  unsigned __int64 v77; // [rsp+F0h] [rbp-10h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+F8h] [rbp-8h] BYREF
  char *v79; // [rsp+108h] [rbp+8h]
  int v80; // [rsp+110h] [rbp+10h]
  int v81; // [rsp+114h] [rbp+14h]
  unsigned int *v82; // [rsp+118h] [rbp+18h]
  __int64 v83; // [rsp+120h] [rbp+20h]

  v68 = a2;
  *(_OWORD *)v75 = 0;
  v76 = 0;
  v77 = 7;
  LOWORD(v75[0]) = 0;
  *(_OWORD *)v72 = 0;
  v73 = 0;
  v74 = 7;
  LOWORD(v72[0]) = 0;
  *(_OWORD *)v69 = 0;
  v70 = 0;
  v71 = 7;
  LOWORD(v69[0]) = 0;
  v6 = NgcUtils::NgcContainerKeyName::ParseKeyNameString(a2, v75, v72, v69);
  if ( v6 < 0 )
  {
    if ( v71 <= 7 )
    {
LABEL_9:
      if ( v74 <= 7 )
      {
LABEL_15:
        if ( v77 <= 7 )
        {
LABEL_21:
          std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(a2);
          return (unsigned int)v6;
        }
        v12 = 2 * v77 + 2;
        if ( v12 < 0x1000 )
        {
          v13 = v75[0];
          goto LABEL_20;
        }
        v13 = (unsigned __int16 *)*((_QWORD *)v75[0] - 1);
        if ( (unsigned __int64)((char *)v75[0] - (char *)v13 - 8) <= 0x1F )
        {
          v12 = 2 * v77 + 41;
LABEL_20:
          operator delete(v13, v12);
          goto LABEL_21;
        }
LABEL_55:
        __fastfail(5u);
      }
      v10 = 2 * v74 + 2;
      if ( v10 < 0x1000 )
      {
        v11 = v72[0];
        goto LABEL_14;
      }
      v11 = (unsigned __int16 *)*((_QWORD *)v72[0] - 1);
      if ( (unsigned __int64)((char *)v72[0] - (char *)v11 - 8) <= 0x1F )
      {
        v10 = 2 * v74 + 41;
LABEL_14:
        operator delete(v11, v10);
        goto LABEL_15;
      }
LABEL_54:
      __fastfail(5u);
    }
    v7 = 2 * v71 + 2;
    if ( v7 < 0x1000 )
    {
      v8 = v69[0];
      goto LABEL_7;
    }
    v8 = (unsigned __int16 *)*((_QWORD *)v69[0] - 1);
    if ( (unsigned __int64)((char *)v69[0] - (char *)v8 - 8) <= 0x1F )
    {
      v7 = 2 * v71 + 41;
LABEL_7:
      v9 = v8;
LABEL_8:
      operator delete(v9, v7);
      goto LABEL_9;
    }
LABEL_53:
    __fastfail(5u);
  }
  *(_OWORD *)lpMem = 0;
  v65 = 0;
  v66 = 0;
  v15 = v70 + 1;
  v16 = 2 * (v70 + 1);
  ProcessHeap = GetProcessHeap();
  v18 = HeapAlloc(ProcessHeap, 8u, v16);
  lpMem[0] = v18;
  if ( v18 )
  {
    v25 = (const unsigned __int16 *)v69;
    if ( v71 > 7 )
      v25 = v69[0];
    v26 = StringCchCopyW((unsigned __int16 *)v18, v15, v25);
    v6 = v26;
    if ( v26 < 0 )
    {
      if ( (unsigned int)dword_1800BE0B8 > 2 )
      {
        LODWORD(v68) = v26;
        v82 = (unsigned int *)&v68;
        v83 = 4;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        *(_DWORD *)&EventDescriptor.Level = 2;
        EventDescriptor.Keyword = 0;
        UserData.Ptr = (ULONGLONG)off_1800BE0C0;
        UserData.Size = *(unsigned __int16 *)off_1800BE0C0;
        UserData.Reserved = 2;
        v79 = (char *)&word_1800A9AE6;
        v80 = 37;
        v81 = 1;
        v61 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
      }
      NgcRpcKeyInfo::~NgcRpcKeyInfo((NgcRpcKeyInfo *)lpMem);
      if ( v71 <= 7 )
        goto LABEL_9;
      v8 = v69[0];
      v7 = 2 * v71 + 2;
      if ( v7 < 0x1000 )
        goto LABEL_7;
      v9 = (unsigned __int16 *)*((_QWORD *)v69[0] - 1);
      if ( (unsigned __int64)((char *)v69[0] - (char *)v9 - 8) <= 0x1F )
      {
        v7 = 2 * v71 + 41;
        goto LABEL_8;
      }
      goto LABEL_53;
    }
    if ( !v76 )
      goto LABEL_113;
    v27 = v76 + 1;
    v28 = MIDL_user_allocate(2 * (v76 + 1));
    v29 = lpMem[1];
    lpMem[1] = v28;
    if ( v29 )
    {
      v30 = GetProcessHeap();
      HeapFree(v30, 0, v29);
      v28 = lpMem[1];
    }
    if ( !v28 )
    {
      if ( (unsigned int)dword_1800BE0B8 > 2 )
      {
        LODWORD(v68) = -2147024882;
        v82 = (unsigned int *)&v68;
        v83 = 4;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        *(_DWORD *)&EventDescriptor.Level = 2;
        EventDescriptor.Keyword = 0;
        UserData.Ptr = (ULONGLONG)off_1800BE0C0;
        UserData.Size = *(unsigned __int16 *)off_1800BE0C0;
        v31 = byte_1800A9AB5;
        v80 = 37;
LABEL_73:
        v79 = v31;
        UserData.Reserved = 2;
        v81 = 1;
        v61 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
        goto LABEL_74;
      }
      goto LABEL_74;
    }
    v32 = (const unsigned __int16 *)v75;
    if ( v77 > 7 )
      v32 = v75[0];
    v33 = StringCchCopyW((unsigned __int16 *)v28, v27, v32);
    v34 = v33;
    if ( v33 < 0 )
    {
      if ( (unsigned int)dword_1800BE0B8 > 2 )
      {
        LODWORD(v68) = v33;
        v82 = (unsigned int *)&v68;
        v83 = 4;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        *(_DWORD *)&EventDescriptor.Level = 2;
        EventDescriptor.Keyword = 0;
        UserData.Ptr = (ULONGLONG)off_1800BE0C0;
        UserData.Size = *(unsigned __int16 *)off_1800BE0C0;
        v35 = (char *)&word_1800A9B4E;
        v80 = 34;
LABEL_67:
        UserData.Reserved = 2;
        v79 = v35;
        v81 = 1;
        v61 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
      }
    }
    else
    {
LABEL_113:
      if ( v73 )
      {
        v36 = v73 + 1;
        v37 = MIDL_user_allocate(2 * (v73 + 1));
        v65 = v37;
        if ( !v37 )
        {
          if ( (unsigned int)dword_1800BE0B8 > 2 )
          {
            LODWORD(v68) = -2147024882;
            v82 = (unsigned int *)&v68;
            v83 = 4;
            *(_DWORD *)&EventDescriptor.Id = 184549376;
            *(_DWORD *)&EventDescriptor.Level = 2;
            EventDescriptor.Keyword = 0;
            UserData.Ptr = (ULONGLONG)off_1800BE0C0;
            UserData.Size = *(unsigned __int16 *)off_1800BE0C0;
            v31 = &byte_1800A9B17;
            v80 = 43;
            goto LABEL_73;
          }
LABEL_74:
          NgcRpcKeyInfo::~NgcRpcKeyInfo((NgcRpcKeyInfo *)lpMem);
          std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v69);
          std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v72);
          std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v75);
          std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(a2);
          return 2147942414LL;
        }
        v38 = (const unsigned __int16 *)v72;
        if ( v74 > 7 )
          v38 = v72[0];
        v39 = StringCchCopyW((unsigned __int16 *)v37, v36, v38);
        v34 = v39;
        if ( v39 < 0 )
        {
          if ( (unsigned int)dword_1800BE0B8 <= 2 )
            goto LABEL_68;
          LODWORD(v68) = v39;
          v82 = (unsigned int *)&v68;
          v83 = 4;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          *(_DWORD *)&EventDescriptor.Level = 2;
          EventDescriptor.Keyword = 0;
          UserData.Ptr = (ULONGLONG)off_1800BE0C0;
          UserData.Size = *(unsigned __int16 *)off_1800BE0C0;
          v35 = byte_1800A9A11;
          v80 = 40;
          goto LABEL_67;
        }
      }
      v40 = *a1;
      v41 = **a1;
      if ( a2[3] <= 7u )
        v42 = a2;
      else
        v42 = (_QWORD *)*a2;
      EventDescriptor = (EVENT_DESCRIPTOR)xmmword_18008F2D8;
      v43 = (*(__int64 (__fastcall **)(__int64 *, EVENT_DESCRIPTOR *, _QWORD *, __int64 *))(v41 + 280))(
              v40,
              &EventDescriptor,
              v42,
              &v66);
      v34 = v43;
      if ( v43 >= 0 )
      {
        pv = 0;
        v67 = 0;
        v44 = *a1;
        v45 = **a1;
        UserData.Ptr = (ULONGLONG)&pv;
        *(_QWORD *)&UserData.Size = 0;
        LOBYTE(v79) = 1;
        if ( a2[3] <= 7u )
          v46 = a2;
        else
          v46 = (_QWORD *)*a2;
        EventDescriptor = (EVENT_DESCRIPTOR)xmmword_18008F2D8;
        v47 = (*(__int64 (__fastcall **)(__int64 *, EVENT_DESCRIPTOR *, _QWORD *, __int64, ULONG *, int *))(v45 + 136))(
                v44,
                &EventDescriptor,
                v46,
                8,
                &UserData.Size,
                &v67);
        if ( (_BYTE)v79 )
        {
          v48 = *(void **)UserData.Ptr;
          *(_QWORD *)UserData.Ptr = *(_QWORD *)&UserData.Size;
          if ( v48 )
            CoTaskMemFree(v48);
        }
        if ( v47 >= 0 )
        {
          if ( v67 != 4 )
          {
            if ( (unsigned int)dword_1800BE0B8 > 2 )
            {
              LODWORD(v68) = -2147418113;
              v82 = (unsigned int *)&v68;
              v83 = 4;
              *(_DWORD *)&EventDescriptor.Id = 184549376;
              *(_DWORD *)&EventDescriptor.Level = 2;
              EventDescriptor.Keyword = 0;
              UserData.Ptr = (ULONGLONG)off_1800BE0C0;
              UserData.Size = *(unsigned __int16 *)off_1800BE0C0;
              UserData.Reserved = 2;
              v79 = byte_1800A9A45;
              v80 = 43;
              v81 = 1;
              v61 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
              EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
            }
            v49 = pv;
            pv = 0;
            if ( v49 )
              CoTaskMemFree(v49);
            NgcRpcKeyInfo::~NgcRpcKeyInfo((NgcRpcKeyInfo *)lpMem);
            std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v69);
            std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v72);
            std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v75);
            std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(a2);
            return 2147549183LL;
          }
          HIDWORD(v66) = *(_DWORD *)pv;
          v50 = lpMem[0];
          lpMem[0] = 0;
          v51 = *(void **)a3;
          *(_QWORD *)a3 = v50;
          if ( v51 )
          {
            v52 = GetProcessHeap();
            HeapFree(v52, 0, v51);
          }
          v53 = lpMem[1];
          lpMem[1] = 0;
          v54 = *(void **)(a3 + 8);
          *(_QWORD *)(a3 + 8) = v53;
          if ( v54 )
          {
            v55 = GetProcessHeap();
            HeapFree(v55, 0, v54);
          }
          v56 = v65;
          v65 = 0;
          v57 = *(void **)(a3 + 16);
          *(_QWORD *)(a3 + 16) = v56;
          if ( v57 )
          {
            v58 = GetProcessHeap();
            HeapFree(v58, 0, v57);
          }
          *(_QWORD *)(a3 + 24) = v66;
        }
        else if ( (unsigned int)dword_1800BE0B8 > 2 )
        {
          LODWORD(v68) = v47;
          v82 = (unsigned int *)&v68;
          v83 = 4;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          *(_DWORD *)&EventDescriptor.Level = 2;
          EventDescriptor.Keyword = 0;
          UserData.Ptr = (ULONGLONG)off_1800BE0C0;
          UserData.Size = *(unsigned __int16 *)off_1800BE0C0;
          UserData.Reserved = 2;
          v79 = (char *)&dword_1800A9A7C;
          v80 = 45;
          v81 = 1;
          v61 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
        }
        v59 = pv;
        v60 = pv == 0;
        pv = 0;
        if ( !v60 )
          CoTaskMemFree(v59);
        NgcRpcKeyInfo::~NgcRpcKeyInfo((NgcRpcKeyInfo *)lpMem);
        std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v69);
        std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v72);
        std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v75);
        std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(a2);
        return (unsigned int)v47;
      }
      if ( (unsigned int)dword_1800BE0B8 > 2 )
      {
        LODWORD(v68) = v43;
        v82 = (unsigned int *)&v68;
        v83 = 4;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        *(_DWORD *)&EventDescriptor.Level = 2;
        EventDescriptor.Keyword = 0;
        UserData.Ptr = (ULONGLONG)off_1800BE0C0;
        UserData.Size = *(unsigned __int16 *)off_1800BE0C0;
        v35 = byte_1800A99DB;
        v80 = 42;
        goto LABEL_67;
      }
    }
LABEL_68:
    NgcRpcKeyInfo::~NgcRpcKeyInfo((NgcRpcKeyInfo *)lpMem);
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v69);
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v72);
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v75);
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(a2);
    return v34;
  }
  if ( (unsigned int)dword_1800BE0B8 > 2 )
  {
    v61 = -2147024882;
    v82 = &v61;
    v83 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 2;
    EventDescriptor.Keyword = 0;
    UserData.Ptr = (ULONGLONG)off_1800BE0C0;
    UserData.Size = *(unsigned __int16 *)off_1800BE0C0;
    UserData.Reserved = 2;
    v79 = byte_1800A9BA1;
    v80 = 40;
    v81 = 1;
    LODWORD(v68) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  NgcRpcKeyInfo::~NgcRpcKeyInfo((NgcRpcKeyInfo *)lpMem);
  if ( v71 > 7 )
  {
    v19 = 2 * v71 + 2;
    if ( v19 < 0x1000 )
    {
      v20 = v69[0];
    }
    else
    {
      v20 = (unsigned __int16 *)*((_QWORD *)v69[0] - 1);
      if ( (unsigned __int64)((char *)v69[0] - (char *)v20 - 8) > 0x1F )
        goto LABEL_53;
      v19 = 2 * v71 + 41;
    }
    operator delete(v20, v19);
  }
  if ( v74 > 7 )
  {
    v21 = 2 * v74 + 2;
    if ( v21 < 0x1000 )
    {
      v22 = v72[0];
    }
    else
    {
      v22 = (unsigned __int16 *)*((_QWORD *)v72[0] - 1);
      if ( (unsigned __int64)((char *)v72[0] - (char *)v22 - 8) > 0x1F )
        goto LABEL_54;
      v21 = 2 * v74 + 41;
    }
    operator delete(v22, v21);
  }
  if ( v77 > 7 )
  {
    v23 = 2 * v77 + 2;
    if ( v23 < 0x1000 )
    {
      v24 = v75[0];
    }
    else
    {
      v24 = (unsigned __int16 *)*((_QWORD *)v75[0] - 1);
      if ( (unsigned __int64)((char *)v75[0] - (char *)v24 - 8) > 0x1F )
        goto LABEL_55;
      v23 = 2 * v77 + 41;
    }
    operator delete(v24, v23);
  }
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(a2);
  return 2147942414LL;
}

```

## disassembly

```asm
0x18001e950  push    rbp
0x18001e952  push    rbx
0x18001e953  push    rsi
0x18001e954  push    rdi
0x18001e955  push    r12
0x18001e957  push    r14
0x18001e959  push    r15
0x18001e95b  lea     rbp, [rsp-30h]
0x18001e960  sub     rsp, 130h
0x18001e967  mov     rax, cs:__security_cookie
0x18001e96e  xor     rax, rsp
0x18001e971  mov     [rbp+60h+var_38], rax
0x18001e975  mov     rsi, r8
0x18001e978  mov     rdi, rdx
0x18001e97b  mov     r15, rcx
0x18001e97e  mov     [rbp+60h+var_D0], rdx
0x18001e982  xorps   xmm0, xmm0
0x18001e985  movups  xmmword ptr [rbp+60h+var_88], xmm0
0x18001e989  xor     r12d, r12d
0x18001e98c  mov     [rbp+60h+var_78], r12
0x18001e990  mov     [rbp+60h+var_70], 7
0x18001e998  mov     word ptr [rbp+60h+var_88], r12w
0x18001e99d  movups  xmmword ptr [rbp+60h+var_A8], xmm0
0x18001e9a1  mov     [rbp+60h+var_98], r12
0x18001e9a5  mov     [rbp+60h+var_90], 7
0x18001e9ad  mov     word ptr [rbp+60h+var_A8], r12w
0x18001e9b2  movups  xmmword ptr [rbp+60h+var_C8], xmm0
0x18001e9b6  mov     [rbp+60h+var_B8], r12
0x18001e9ba  mov     [rbp+60h+var_B0], 7
0x18001e9c2  mov     word ptr [rbp+60h+var_C8], r12w
0x18001e9c7  lea     r9, [rbp+60h+var_C8]
0x18001e9cb  lea     r8, [rbp+60h+var_A8]
0x18001e9cf  lea     rdx, [rbp+60h+var_88]
0x18001e9d3  mov     rcx, rdi
0x18001e9d6  call    ?ParseKeyNameString@NgcContainerKeyName@NgcUtils@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV34@11@Z; NgcUtils::NgcContainerKeyName::ParseKeyNameString(std::wstring const &,std::wstring *,std::wstring *,std::wstring *)
0x18001e9db  mov     ebx, eax
0x18001e9dd  test    eax, eax
0x18001e9df  jns     loc_18001EAC0
0x18001e9e5  mov     rdx, [rbp+60h+var_B0]
0x18001e9e9  cmp     rdx, 7
0x18001e9ed  jbe     short loc_18001EA2B
0x18001e9ef  mov     rcx, [rbp+60h+var_C8]
0x18001e9f3  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x18001e9fb  cmp     rdx, 1000h
0x18001ea02  jb      short loc_18001EA1F
0x18001ea04  mov     rax, [rcx-8]
0x18001ea08  sub     rcx, rax
0x18001ea0b  sub     rcx, 8
0x18001ea0f  cmp     rcx, 1Fh
0x18001ea13  ja      loc_18001EDFC
0x18001ea19  add     rdx, 27h ; '''
0x18001ea1d  jmp     short loc_18001EA22
0x18001ea1f  mov     rax, rcx
0x18001ea22  mov     rcx, rax; void *
0x18001ea25  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001ea2a  nop
0x18001ea2b  mov     rdx, [rbp+60h+var_90]
0x18001ea2f  cmp     rdx, 7
0x18001ea33  jbe     short loc_18001EA6E
0x18001ea35  mov     rax, [rbp+60h+var_A8]
0x18001ea39  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x18001ea41  cmp     rdx, 1000h
0x18001ea48  jb      short loc_18001EA65
0x18001ea4a  mov     rcx, [rax-8]
0x18001ea4e  sub     rax, rcx
0x18001ea51  sub     rax, 8
0x18001ea55  cmp     rax, 1Fh
0x18001ea59  ja      loc_18001EE03
0x18001ea5f  add     rdx, 27h ; '''
0x18001ea63  jmp     short loc_18001EA68
0x18001ea65  mov     rcx, rax; void *
0x18001ea68  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001ea6d  nop
0x18001ea6e  mov     rdx, [rbp+60h+var_70]
0x18001ea72  cmp     rdx, 7
0x18001ea76  jbe     short loc_18001EAB1
0x18001ea78  mov     rax, [rbp+60h+var_88]
0x18001ea7c  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x18001ea84  cmp     rdx, 1000h
0x18001ea8b  jb      short loc_18001EAA8
0x18001ea8d  mov     rcx, [rax-8]
0x18001ea91  sub     rax, rcx
0x18001ea94  sub     rax, 8
0x18001ea98  cmp     rax, 1Fh
0x18001ea9c  ja      loc_18001EE0A
0x18001eaa2  add     rdx, 27h ; '''
0x18001eaa6  jmp     short loc_18001EAAB
0x18001eaa8  mov     rcx, rax; void *
0x18001eaab  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001eab0  nop
0x18001eab1  mov     rcx, rdi
0x18001eab4  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18001eab9  mov     eax, ebx
0x18001eabb  jmp     loc_18001F5A2
0x18001eac0  xorps   xmm0, xmm0
0x18001eac3  movdqu  xmmword ptr [rsp+160h+lpMem], xmm0
0x18001eac9  mov     [rsp+160h+var_E8], r12
0x18001eace  mov     [rbp+60h+var_E0], r12
0x18001ead2  mov     r14, [rbp+60h+var_B8]
0x18001ead6  inc     r14
0x18001ead9  lea     rbx, [r14+r14]
0x18001eadd  call    cs:__imp_GetProcessHeap
0x18001eae4  nop     dword ptr [rax+rax+00h]
0x18001eae9  mov     rcx, rax; hHeap
0x18001eaec  mov     r8, rbx; dwBytes
0x18001eaef  mov     edx, 8; dwFlags
0x18001eaf4  call    cs:__imp_HeapAlloc
0x18001eafb  nop     dword ptr [rax+rax+00h]
0x18001eb00  mov     rbx, [rsp+160h+lpMem]
0x18001eb05  mov     [rsp+160h+lpMem], rax
0x18001eb0a  test    rbx, rbx
0x18001eb0d  jz      short loc_18001EB34
0x18001eb0f  call    cs:__imp_GetProcessHeap
0x18001eb16  nop     dword ptr [rax+rax+00h]
0x18001eb1b  mov     rcx, rax; hHeap
0x18001eb1e  mov     r8, rbx; lpMem
0x18001eb21  xor     edx, edx; dwFlags
0x18001eb23  call    cs:__imp_HeapFree
0x18001eb2a  nop     dword ptr [rax+rax+00h]
0x18001eb2f  mov     rax, [rsp+160h+lpMem]
0x18001eb34  test    rax, rax
0x18001eb37  jnz     loc_18001ECDA
0x18001eb3d  mov     eax, cs:dword_1800BE0B8
0x18001eb43  cmp     eax, 2
0x18001eb46  jbe     loc_18001EBF4
0x18001eb4c  mov     [rsp+160h+var_120], 8007000Eh
0x18001eb54  lea     rax, [rsp+160h+var_120]
0x18001eb59  mov     [rbp+60h+var_48], rax
0x18001eb5d  mov     [rbp+60h+var_40], 4
0x18001eb65  mov     dword ptr [rsp+160h+EventDescriptor.Id], 0B000000h
0x18001eb6d  movzx   eax, cs:word_1800A9B97
0x18001eb74  mov     dword ptr [rsp+160h+EventDescriptor.Level], eax
0x18001eb78  mov     [rsp+160h+EventDescriptor.Keyword], r12
0x18001eb7d  mov     rax, cs:off_1800BE0C0
0x18001eb84  mov     [rbp+60h+var_68.Ptr], rax
0x18001eb88  movzx   eax, word ptr [rax]
0x18001eb8b  mov     [rbp+60h+var_68.Size], eax
0x18001eb8e  mov     dword ptr [rbp+60h+var_68.0Ch], 2
0x18001eb95  lea     rax, byte_1800A9BA1
0x18001eb9c  mov     [rbp+60h+var_58], rax
0x18001eba0  mov     [rbp+60h+var_50], 28h ; '('
0x18001eba7  mov     [rbp+60h+var_4C], 1
0x18001ebae  lea     rax, _TraceLoggingMetadataEnd
0x18001ebb5  lea     rcx, _TraceLoggingMetadata
0x18001ebbc  sub     eax, ecx
0x18001ebbe  mov     dword ptr [rbp+60h+var_D0], eax
0x18001ebc1  mov     eax, dword ptr [rbp+60h+var_D0]
0x18001ebc4  lea     rax, [rbp+60h+var_68]
0x18001ebc8  mov     [rsp+160h+UserData], rax; UserData
0x18001ebcd  mov     [rsp+160h+UserDataCount], 3; UserDataCount
0x18001ebd5  xor     r9d, r9d; RelatedActivityId
0x18001ebd8  xor     r8d, r8d; ActivityId
0x18001ebdb  lea     rdx, [rsp+160h+EventDescriptor]; EventDescriptor
0x18001ebe0  mov     rcx, cs:RegHandle; RegHandle
0x18001ebe7  call    cs:__imp_EventWriteTransfer
0x18001ebee  nop     dword ptr [rax+rax+00h]
0x18001ebf3  nop
0x18001ebf4  lea     rcx, [rsp+160h+lpMem]; this
0x18001ebf9  call    ??1NgcRpcKeyInfo@@QEAA@XZ; NgcRpcKeyInfo::~NgcRpcKeyInfo(void)
0x18001ebfe  nop
0x18001ebff  mov     rdx, [rbp+60h+var_B0]
0x18001ec03  cmp     rdx, 7
0x18001ec07  jbe     short loc_18001EC42
0x18001ec09  mov     rax, [rbp+60h+var_C8]
0x18001ec0d  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x18001ec15  cmp     rdx, 1000h
0x18001ec1c  jb      short loc_18001EC39
0x18001ec1e  mov     rcx, [rax-8]
0x18001ec22  sub     rax, rcx
0x18001ec25  sub     rax, 8
0x18001ec29  cmp     rax, 1Fh
0x18001ec2d  ja      loc_18001EDFC
0x18001ec33  add     rdx, 27h ; '''
0x18001ec37  jmp     short loc_18001EC3C
0x18001ec39  mov     rcx, rax; void *
0x18001ec3c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001ec41  nop
0x18001ec42  mov     rdx, [rbp+60h+var_90]
0x18001ec46  cmp     rdx, 7
0x18001ec4a  jbe     short loc_18001EC85
0x18001ec4c  mov     rax, [rbp+60h+var_A8]
0x18001ec50  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x18001ec58  cmp     rdx, 1000h
0x18001ec5f  jb      short loc_18001EC7C
0x18001ec61  mov     rcx, [rax-8]
0x18001ec65  sub     rax, rcx
0x18001ec68  sub     rax, 8
0x18001ec6c  cmp     rax, 1Fh
0x18001ec70  ja      loc_18001EE03
0x18001ec76  add     rdx, 27h ; '''
0x18001ec7a  jmp     short loc_18001EC7F
0x18001ec7c  mov     rcx, rax; void *
0x18001ec7f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001ec84  nop
0x18001ec85  mov     rdx, [rbp+60h+var_70]
0x18001ec89  cmp     rdx, 7
0x18001ec8d  jbe     short loc_18001ECC8
0x18001ec8f  mov     rax, [rbp+60h+var_88]
0x18001ec93  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x18001ec9b  cmp     rdx, 1000h
0x18001eca2  jb      short loc_18001ECBF
0x18001eca4  mov     rcx, [rax-8]
0x18001eca8  sub     rax, rcx
0x18001ecab  sub     rax, 8
0x18001ecaf  cmp     rax, 1Fh
0x18001ecb3  ja      loc_18001EE0A
0x18001ecb9  add     rdx, 27h ; '''
0x18001ecbd  jmp     short loc_18001ECC2
0x18001ecbf  mov     rcx, rax; void *
0x18001ecc2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001ecc7  nop
0x18001ecc8  mov     rcx, rdi
0x18001eccb  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18001ecd0  mov     eax, 8007000Eh
0x18001ecd5  jmp     loc_18001F5A2
0x18001ecda  lea     r8, [rbp+60h+var_C8]
0x18001ecde  cmp     [rbp+60h+var_B0], 7
0x18001ece3  cmova   r8, [rbp+60h+var_C8]; unsigned __int16 *
0x18001ece8  mov     rdx, r14; unsigned __int64
0x18001eceb  mov     rcx, rax; unsigned __int16 *
0x18001ecee  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001ecf3  mov     ebx, eax
0x18001ecf5  test    eax, eax
0x18001ecf7  jns     loc_18001EE11
0x18001ecfd  mov     ecx, cs:dword_1800BE0B8
0x18001ed03  cmp     ecx, 2
0x18001ed06  jbe     loc_18001EDB0
0x18001ed0c  mov     dword ptr [rbp+60h+var_D0], eax
0x18001ed0f  lea     rax, [rbp+60h+var_D0]
0x18001ed13  mov     [rbp+60h+var_48], rax
0x18001ed17  mov     [rbp+60h+var_40], 4
0x18001ed1f  mov     dword ptr [rsp+160h+EventDescriptor.Id], 0B000000h
0x18001ed27  movzx   eax, cs:word_1800A9ADC
0x18001ed2e  mov     dword ptr [rsp+160h+EventDescriptor.Level], eax
0x18001ed32  mov     [rsp+160h+EventDescriptor.Keyword], r12
0x18001ed37  mov     rax, cs:off_1800BE0C0
0x18001ed3e  mov     [rbp+60h+var_68.Ptr], rax
0x18001ed42  movzx   eax, word ptr [rax]
0x18001ed45  mov     [rbp+60h+var_68.Size], eax
0x18001ed48  mov     dword ptr [rbp+60h+var_68.0Ch], 2
0x18001ed4f  lea     rax, word_1800A9AE6
0x18001ed56  mov     [rbp+60h+var_58], rax
0x18001ed5a  mov     [rbp+60h+var_50], 25h ; '%'
0x18001ed61  mov     [rbp+60h+var_4C], 1
0x18001ed68  lea     rax, _TraceLoggingMetadataEnd
0x18001ed6f  lea     rcx, _TraceLoggingMetadata
0x18001ed76  sub     eax, ecx
0x18001ed78  mov     [rsp+160h+var_120], eax
0x18001ed7c  mov     eax, [rsp+160h+var_120]
0x18001ed80  lea     rax, [rbp+60h+var_68]
0x18001ed84  mov     [rsp+160h+UserData], rax; UserData
0x18001ed89  mov     [rsp+160h+UserDataCount], 3; UserDataCount
0x18001ed91  xor     r9d, r9d; RelatedActivityId
0x18001ed94  xor     r8d, r8d; ActivityId
0x18001ed97  lea     rdx, [rsp+160h+EventDescriptor]; EventDescriptor
0x18001ed9c  mov     rcx, cs:RegHandle; RegHandle
0x18001eda3  call    cs:__imp_EventWriteTransfer
0x18001edaa  nop     dword ptr [rax+rax+00h]
0x18001edaf  nop
0x18001edb0  lea     rcx, [rsp+160h+lpMem]; this
0x18001edb5  call    ??1NgcRpcKeyInfo@@QEAA@XZ; NgcRpcKeyInfo::~NgcRpcKeyInfo(void)
0x18001edba  nop
0x18001edbb  mov     rdx, [rbp+60h+var_B0]
0x18001edbf  cmp     rdx, 7
0x18001edc3  jbe     loc_18001EA2B
0x18001edc9  mov     rax, [rbp+60h+var_C8]
0x18001edcd  lea     rdx, ds:2[rdx*2]
0x18001edd5  cmp     rdx, 1000h
0x18001eddc  jb      loc_18001EA22
0x18001ede2  mov     rcx, [rax-8]
0x18001ede6  sub     rax, rcx
0x18001ede9  sub     rax, 8
0x18001eded  cmp     rax, 1Fh
0x18001edf1  ja      short loc_18001EDFC
0x18001edf3  add     rdx, 27h ; '''
0x18001edf7  jmp     loc_18001EA25
0x18001edfc  mov     ecx, 5
0x18001ee01  int     29h; Win8: RtlFailFast(ecx)
0x18001ee03  mov     ecx, 5
0x18001ee08  int     29h; Win8: RtlFailFast(ecx)
0x18001ee0a  mov     ecx, 5
0x18001ee0f  int     29h; Win8: RtlFailFast(ecx)
0x18001ee11  mov     rax, [rbp+60h+var_78]
0x18001ee15  test    rax, rax
0x18001ee18  jz      loc_18001EFD4
0x18001ee1e  lea     r14, [rax+1]
0x18001ee22  lea     rcx, [r14+r14]; size
0x18001ee26  call    MIDL_user_allocate
0x18001ee2b  mov     rbx, [rsp+160h+lpMem+8]
0x18001ee30  mov     [rsp+160h+lpMem+8], rax
0x18001ee35  test    rbx, rbx
0x18001ee38  jz      short loc_18001EE5F
0x18001ee3a  call    cs:__imp_GetProcessHeap
0x18001ee41  nop     dword ptr [rax+rax+00h]
0x18001ee46  mov     rcx, rax; hHeap
0x18001ee49  mov     r8, rbx; lpMem
0x18001ee4c  xor     edx, edx; dwFlags
0x18001ee4e  call    cs:__imp_HeapFree
0x18001ee55  nop     dword ptr [rax+rax+00h]
0x18001ee5a  mov     rax, [rsp+160h+lpMem+8]
  ... truncated ...
```
