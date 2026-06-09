# pExecuteDiff(ulong,ulong,ulong *,ulong,UnBCL::String *,UnBCL::String *,UnBCL::String *,UnBCL::String *,UnBCL::String *,long (*)(_DIFF_CALLBACK_DATA *,UnBCL::String *,UnBCL::String *,UnBCL::String *,CFileObject *,CFileObject *),_DIFF_CALLBACK_DATA *,UnBCL::Hashtable<UnBCL::String *,ulong> *)

- ea: `0x180032ae4`
- end: `0x18003317a`
- name: `?pExecuteDiff@@YAJKKPEAKKPEAVString@UnBCL@@1111P6AJPEAU_DIFF_CALLBACK_DATA@@111PEAVCFileObject@@3@Z2PEAV?$Hashtable@PEAVString@UnBCL@@K@2@@Z`
- size: `1686`
- prototype: `__int64 __fastcall(unsigned int, __int64, unsigned int *, int, struct UnBCL::String *, struct UnBCL::String *, __int64, UnBCL::String *, const struct UnBCL::String *, int, __int64, __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002a6fc`
- `0x180032ae4`

## callees

- `0x180009e04`
- `0x18000b070`
- `0x18002443c`
- `0x1800251e0`
- `0x180030ef0`
- `0x180032ae4`
- `0x180033180`
- `0x180050300`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180032bea`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180032d89`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180032bea`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180032d89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032cb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800330ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032cb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800330ac`
- `WDSCORE!CurrentIP` at `0x180032cc0`
- `WDSCORE!CurrentIP` at `0x1800330b4`
- `WDSCORE!CurrentIP` at `0x180032cc0`
- `WDSCORE!CurrentIP` at `0x1800330b4`
- `WDSCORE!WdsSetupLogMessageW` at `0x180032d32`
- `WDSCORE!WdsSetupLogMessageW` at `0x18003311a`
- `WDSCORE!WdsSetupLogMessageW` at `0x180032d32`
- `WDSCORE!WdsSetupLogMessageW` at `0x18003311a`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180032b5b`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180032b9f`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180032eed`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180032b5b`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180032b9f`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180032eed`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x180032f05`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x180032f05`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180032ccc`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180032ccc`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@0H@Z` at `0x180032e72`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@0H@Z` at `0x180032e72`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180032edd`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180032edd`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180032d9d`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180032f20`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180032d9d`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180032f20`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180032f3a`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18003308e`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180033125`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180032f3a`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18003308e`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180033125`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180032f2f`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180032f2f`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180032e43`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180032e59`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180032ec5`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180032f44`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180032fe5`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180032ff7`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180033009`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180032e43`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180032e59`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180032ec5`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180032f44`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180032fe5`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180032ff7`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180033009`

## string_xrefs

- `0x180032d0f`: `base\diagnosis\srt\pitr\dll\src\restore.cpp`
- `0x1800330f7`: `base\diagnosis\srt\pitr\dll\src\restore.cpp`
- `0x1800330c0`: `ExecuteDiff: Failure coming from callback. Error: 0x%08X`

## pseudocode

```c
__int64 __fastcall pExecuteDiff(
        unsigned int a1,
        __int64 a2,
        unsigned int *a3,
        int a4,
        struct UnBCL::String *a5,
        struct UnBCL::String *a6,
        __int64 a7,
        UnBCL::String *a8,
        const struct UnBCL::String *a9,
        int a10,
        __int64 a11,
        __int64 a12)
{
  struct _DIFF_CALLBACK_DATA *v12; // rdi
  UnBCL::String *v13; // rax
  int v14; // r15d
  UnBCL::String *v15; // rax
  _QWORD *v16; // r13
  void *v17; // rcx
  int FileObjects; // esi
  __int64 v20; // rbx
  DWORD LastError; // edi
  __int64 v22; // rbx
  const char *CString; // rax
  struct tagLOG_PARTIAL_MSG *v24; // rax
  int v25; // r15d
  int v26; // r12d
  void *v27; // rcx
  int (__fastcall ***v28)(_QWORD); // rcx
  __int64 v29; // rcx
  __int64 v30; // rbx
  int (__fastcall ***v31)(_QWORD); // rcx
  char *v32; // rcx
  __int64 v33; // rdi
  const struct UnBCL::String *P; // rsi
  const struct UnBCL::String *v35; // rax
  int v36; // eax
  __int64 v37; // rcx
  const struct UnBCL::String *v38; // r14
  struct UnBCL::String *v39; // rsi
  UnBCL::String *v40; // rax
  struct UnBCL::String *v41; // rax
  struct _DIFF_CALLBACK_DATA *v42; // r14
  int v43; // eax
  int v44; // eax
  unsigned int *v45; // rdx
  __int64 v46; // rcx
  __int64 v47; // rsi
  __int64 v48; // rax
  DWORD v49; // edi
  __int64 v50; // rbx
  struct tagLOG_PARTIAL_MSG *v51; // rax
  void **v52; // [rsp+60h] [rbp-89h] BYREF
  __int64 v53; // [rsp+68h] [rbp-81h]
  unsigned int v54; // [rsp+70h] [rbp-79h]
  int v55; // [rsp+74h] [rbp-75h]
  void **v56; // [rsp+78h] [rbp-71h] BYREF
  _QWORD *v57; // [rsp+80h] [rbp-69h]
  __int64 v58; // [rsp+88h] [rbp-61h]
  struct UnBCL::String *v59; // [rsp+90h] [rbp-59h]
  struct UnBCL::String *v60; // [rsp+98h] [rbp-51h]
  unsigned int *v61; // [rsp+A0h] [rbp-49h]
  struct _DIFF_CALLBACK_DATA *v62; // [rsp+A8h] [rbp-41h]
  UnBCL::String *v63; // [rsp+B0h] [rbp-39h]
  const struct UnBCL::String *v64; // [rsp+B8h] [rbp-31h]
  _BYTE v65[16]; // [rsp+C0h] [rbp-29h] BYREF
  _BYTE v66[16]; // [rsp+D0h] [rbp-19h] BYREF

  v55 = a4;
  v61 = a3;
  v54 = a1;
  v60 = a5;
  v59 = a6;
  v64 = a9;
  v12 = (struct _DIFF_CALLBACK_DATA *)a11;
  v62 = (struct _DIFF_CALLBACK_DATA *)a11;
  v58 = a12;
  v13 = (UnBCL::String *)UnBCL::Object::operator new(0x80u);
  v63 = v13;
  if ( v13 )
    v13 = (UnBCL::String *)UnBCL::ArrayList<CFileObject *>::ArrayList<CFileObject *>(v13);
  UnBCL::SmartPtr<UnBCL::ArrayList<CFileObject *>>::SmartPtr<UnBCL::ArrayList<CFileObject *>>(&v52, v13);
  v14 = v53;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v53 + 40LL))(v53, 1);
  v15 = (UnBCL::String *)UnBCL::Object::operator new(0x80u);
  v63 = v15;
  if ( v15 )
    v15 = (UnBCL::String *)UnBCL::ArrayList<CFileObject *>::ArrayList<CFileObject *>(v15);
  UnBCL::SmartPtr<UnBCL::ArrayList<CFileObject *>>::SmartPtr<UnBCL::ArrayList<CFileObject *>>(&v56, v15);
  v16 = v57;
  (*(void (__fastcall **)(_QWORD *, __int64))(*v57 + 40LL))(v57, 1);
  if ( a11 )
  {
    v17 = *(void **)(a11 + 104);
    if ( v17 )
    {
      if ( !WaitForSingleObject(v17, 0) )
      {
        v56 = &UnBCL::SmartPtr<UnBCL::ArrayList<CFileObject *>>::`vftable';
        UnBCL::SmartPtr<UnBCL::IEnumerator<unsigned long>>::DeAssign((__int64)&v56);
        v52 = &UnBCL::SmartPtr<UnBCL::ArrayList<CFileObject *>>::`vftable';
        UnBCL::SmartPtr<UnBCL::IEnumerator<unsigned long>>::DeAssign((__int64)&v52);
        return 2147943623LL;
      }
    }
  }
  FileObjects = 0;
  if ( a7 )
  {
    FileObjects = pGetFileObjects(a7, v14, (_DWORD)a9, v58, 0);
    if ( FileObjects < 0 )
      goto LABEL_87;
    v20 = v53;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 88LL))(v53);
  }
  else
  {
    v20 = v53;
  }
  if ( a8 )
  {
    FileObjects = pGetFileObjects((_DWORD)a8, (_DWORD)v16, (_DWORD)a9, v58, 0);
    if ( FileObjects < 0 )
    {
      LastError = GetLastError();
      v22 = CurrentIP();
      CString = (const char *)UnBCL::String::get_CString(a8);
      v24 = ConstructPartialMsgW(
              0x2000000,
              "ExecuteDiff: Error getting the real file objects for %s. Error: 0x%08X",
              CString,
              FileObjects);
      WdsSetupLogMessageW(
        v24,
        0,
        L"D",
        0,
        687,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\restore.cpp",
        L"pExecuteDiff",
        v22,
        LastError,
        0,
        0);
      v56 = &UnBCL::SmartPtr<UnBCL::ArrayList<CFileObject *>>::`vftable';
      UnBCL::SmartPtr<UnBCL::IEnumerator<unsigned long>>::DeAssign((__int64)&v56);
      v52 = &UnBCL::SmartPtr<UnBCL::ArrayList<CFileObject *>>::`vftable';
      UnBCL::SmartPtr<UnBCL::IEnumerator<unsigned long>>::DeAssign((__int64)&v52);
      return (unsigned int)FileObjects;
    }
    (*(void (__fastcall **)(_QWORD *))(*v16 + 88LL))(v16);
  }
  v25 = 0;
  v26 = 0;
  while ( 1 )
  {
    if ( v12 )
    {
      v27 = (void *)*((_QWORD *)v12 + 13);
      if ( v27 )
      {
        if ( !WaitForSingleObject(v27, 0) )
        {
          FileObjects = -2147023673;
          goto LABEL_87;
        }
      }
    }
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v66, 0);
    v28 = (int (__fastcall ***)(_QWORD))(v20 + *(int *)(*(_QWORD *)(v20 + 8) + 12LL) + 8LL);
    if ( v25 >= (**v28)(v28) )
    {
      v30 = 0;
    }
    else
    {
      v29 = v20 + 8 + *(int *)(*(_QWORD *)(v20 + 8) + 16LL);
      v30 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v29 + 24LL))(v29, (unsigned int)v25);
    }
    v31 = (int (__fastcall ***)(_QWORD))((char *)v16 + *(int *)(v16[1] + 12LL) + 8);
    if ( v26 >= (**v31)(v31) )
    {
      v33 = 0;
    }
    else
    {
      v32 = (char *)v16 + *(int *)(v16[1] + 16LL) + 8;
      v33 = *(_QWORD *)(*(__int64 (__fastcall **)(char *, _QWORD))(*(_QWORD *)v32 + 24LL))(v32, (unsigned int)v26);
    }
    if ( !v30 && !v33 )
      break;
    if ( v33 )
      P = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v33 + 24);
    else
      P = 0;
    if ( v30 )
      v35 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v30 + 24);
    else
      v35 = 0;
    v36 = UnBCL::String::Compare(v35, P, 1);
    if ( v36 < 0 )
    {
      if ( v30 )
      {
        v33 = 0;
        ++v25;
LABEL_49:
        v37 = v30 + 24;
        goto LABEL_53;
      }
      goto LABEL_51;
    }
    if ( v36 <= 0 )
    {
      if ( (*(_BYTE *)(v30 + 72) & 0x10) != 0 )
      {
        if ( (*(_BYTE *)(v33 + 72) & 0x10) == 0 )
        {
          v30 = 0;
LABEL_51:
          ++v26;
          goto LABEL_52;
        }
      }
      else if ( (*(_BYTE *)(v33 + 72) & 0x10) != 0 )
      {
        v33 = 0;
LABEL_44:
        ++v25;
        goto LABEL_48;
      }
      ++v25;
    }
    else
    {
      if ( !v33 )
        goto LABEL_44;
      v30 = 0;
    }
    ++v26;
LABEL_48:
    if ( v30 )
      goto LABEL_49;
LABEL_52:
    v37 = v33 + 24;
LABEL_53:
    v38 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v37);
    if ( v64 )
    {
      v39 = UnBCL::Path::Combine(v64, v38);
    }
    else
    {
      v40 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
      v39 = v40;
      v63 = v40;
      if ( v40 )
      {
        UnBCL::String::String(v40, v38);
        *(_QWORD *)v39 = &UnBCL::String::`local vftable';
      }
      else
      {
        v39 = 0;
      }
    }
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v65, v39);
    UnBCL::SmartPtr<UnBCL::String>::operator=(v66, v65);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v65);
    v41 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v66);
    v42 = v62;
    FileObjects = pDiffCallback(v62, v60, v59, v41, (struct CFileObject *)v30, (struct CFileObject *)v33);
    if ( FileObjects < 0 )
    {
      v49 = GetLastError();
      v50 = CurrentIP();
      v51 = ConstructPartialMsgW(0x2000000, "ExecuteDiff: Failure coming from callback. Error: 0x%08X", FileObjects);
      WdsSetupLogMessageW(
        v51,
        0,
        L"D",
        0,
        792,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\restore.cpp",
        L"pExecuteDiff",
        v50,
        v49,
        0,
        0);
      break;
    }
    if ( v30 )
    {
      if ( (*(_BYTE *)(v30 + 72) & 0x10) == 0 )
        goto LABEL_61;
      if ( (*(_DWORD *)(v30 + 72) & 0x400) == 0 )
        goto LABEL_67;
      v44 = *(_DWORD *)(v30 + 76);
    }
    else
    {
      if ( (*(_BYTE *)(v33 + 72) & 0x10) == 0 )
        goto LABEL_61;
      if ( (*(_DWORD *)(v33 + 72) & 0x400) == 0 )
        goto LABEL_67;
      v44 = *(_DWORD *)(v33 + 76);
    }
    if ( v44 < 0 && v44 != -1610612733 && v44 != -1610612724 )
    {
LABEL_67:
      v43 = 1;
      goto LABEL_68;
    }
LABEL_61:
    v43 = 0;
LABEL_68:
    if ( v43 )
    {
      if ( v30 )
      {
        if ( v54 < 6 )
        {
          if ( v55 )
          {
            v45 = v61;
            ++*v61;
            v46 = *((_QWORD *)v42 + 14);
            if ( v46 )
              (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v46 + 8LL))(v46, *v45);
          }
        }
      }
      v47 = UnBCL::SmartPtr<UnBCL::String>::get_P(v66);
      if ( v33 )
        v33 = UnBCL::SmartPtr<UnBCL::String>::get_P(v33 + 8);
      v48 = v30 ? UnBCL::SmartPtr<UnBCL::String>::get_P(v30 + 8) : 0LL;
      FileObjects = pExecuteDiff(
                      v54 + 1,
                      6,
                      (_DWORD)v61,
                      v55,
                      (__int64)v60,
                      (__int64)v59,
                      v48,
                      v33,
                      v47,
                      (unsigned int)pDiffCallback,
                      (__int64)v42,
                      v58);
      if ( FileObjects < 0 )
        break;
    }
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v66);
    v12 = v62;
    v20 = v53;
  }
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v66);
LABEL_87:
  v56 = &UnBCL::SmartPtr<UnBCL::ArrayList<CFileObject *>>::`vftable';
  UnBCL::SmartPtr<UnBCL::IEnumerator<unsigned long>>::DeAssign((__int64)&v56);
  v52 = &UnBCL::SmartPtr<UnBCL::ArrayList<CFileObject *>>::`vftable';
  UnBCL::SmartPtr<UnBCL::IEnumerator<unsigned long>>::DeAssign((__int64)&v52);
  return (unsigned int)FileObjects;
}

```

## disassembly

```asm
0x180032ae4  mov     [rsp-8+arg_8], rbx
0x180032ae9  push    rbp
0x180032aea  push    rsi
0x180032aeb  push    rdi
0x180032aec  push    r12
0x180032aee  push    r13
0x180032af0  push    r14
0x180032af2  push    r15
0x180032af4  lea     rbp, [rsp-7]
0x180032af9  sub     rsp, 0F0h
0x180032b00  mov     rax, cs:__security_cookie
0x180032b07  xor     rax, rsp
0x180032b0a  mov     [rbp+37h+var_40], rax
0x180032b0e  mov     [rbp+37h+var_AC], r9d
0x180032b12  mov     [rbp+37h+var_80], r8
0x180032b16  mov     [rbp+37h+var_B0], ecx
0x180032b19  mov     rax, [rbp+37h+arg_20]
0x180032b1d  mov     [rbp+37h+var_88], rax
0x180032b21  mov     rax, [rbp+37h+arg_28]
0x180032b25  mov     [rbp+37h+var_90], rax
0x180032b29  mov     rbx, [rbp+37h+arg_30]
0x180032b2d  mov     r14, [rbp+37h+arg_38]
0x180032b31  mov     r12, [rbp+37h+arg_40]
0x180032b38  mov     [rbp+37h+var_68], r12
0x180032b3c  mov     rdi, [rbp+37h+arg_50]
0x180032b43  mov     [rbp+37h+var_78], rdi
0x180032b47  mov     rax, [rbp+37h+arg_58]
0x180032b4e  mov     [rbp+37h+var_98], rax
0x180032b52  mov     r13d, 80h
0x180032b58  mov     ecx, r13d
0x180032b5b  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180032b61  mov     [rbp+37h+var_70], rax
0x180032b65  test    rax, rax
0x180032b68  jz      short loc_180032B73
0x180032b6a  mov     rcx, rax
0x180032b6d  call    ??0?$ArrayList@PEAVCFileObject@@@UnBCL@@QEAA@XZ; UnBCL::ArrayList<CFileObject *>::ArrayList<CFileObject *>(void)
0x180032b72  nop
0x180032b73  mov     rdx, rax
0x180032b76  lea     rcx, [rsp+120h+var_C0]
0x180032b7b  call    ??0?$SmartPtr@V?$ArrayList@PEAVCFileObject@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVCFileObject@@@1@@Z; UnBCL::SmartPtr<UnBCL::ArrayList<CFileObject *>>::SmartPtr<UnBCL::ArrayList<CFileObject *>>(UnBCL::ArrayList<CFileObject *> *)
0x180032b80  nop
0x180032b81  mov     r15, [rsp+120h+var_B8]
0x180032b86  mov     rax, [r15]
0x180032b89  mov     esi, 1
0x180032b8e  mov     edx, esi
0x180032b90  mov     rcx, r15
0x180032b93  mov     rax, [rax+28h]
0x180032b97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032b9c  mov     rcx, r13
0x180032b9f  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180032ba5  mov     [rbp+37h+var_70], rax
0x180032ba9  test    rax, rax
0x180032bac  jz      short loc_180032BB7
0x180032bae  mov     rcx, rax
0x180032bb1  call    ??0?$ArrayList@PEAVCFileObject@@@UnBCL@@QEAA@XZ; UnBCL::ArrayList<CFileObject *>::ArrayList<CFileObject *>(void)
0x180032bb6  nop
0x180032bb7  mov     rdx, rax
0x180032bba  lea     rcx, [rbp+37h+var_A8]
0x180032bbe  call    ??0?$SmartPtr@V?$ArrayList@PEAVCFileObject@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVCFileObject@@@1@@Z; UnBCL::SmartPtr<UnBCL::ArrayList<CFileObject *>>::SmartPtr<UnBCL::ArrayList<CFileObject *>>(UnBCL::ArrayList<CFileObject *> *)
0x180032bc3  nop
0x180032bc4  mov     r13, [rbp+37h+var_A0]
0x180032bc8  mov     rax, [r13+0]
0x180032bcc  mov     edx, esi
0x180032bce  mov     rcx, r13
0x180032bd1  mov     rax, [rax+28h]
0x180032bd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032bda  test    rdi, rdi
0x180032bdd  jz      short loc_180032C23
0x180032bdf  mov     rcx, [rdi+68h]; hHandle
0x180032be3  test    rcx, rcx
0x180032be6  jz      short loc_180032C23
0x180032be8  xor     edx, edx; dwMilliseconds
0x180032bea  call    cs:__imp_WaitForSingleObject
0x180032bf0  test    eax, eax
0x180032bf2  jnz     short loc_180032C23
0x180032bf4  lea     rbx, ??_7?$SmartPtr@V?$ArrayList@PEAVCFileObject@@@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::ArrayList<CFileObject *>>::`vftable'
0x180032bfb  mov     [rbp+37h+var_A8], rbx
0x180032bff  lea     rcx, [rbp+37h+var_A8]
0x180032c03  call    ?DeAssign@?$SmartPtr@U?$IEnumerator@K@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::IEnumerator<ulong>>::DeAssign(void)
0x180032c08  nop
0x180032c09  mov     [rsp+120h+var_C0], rbx
0x180032c0e  lea     rcx, [rsp+120h+var_C0]
0x180032c13  call    ?DeAssign@?$SmartPtr@U?$IEnumerator@K@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::IEnumerator<ulong>>::DeAssign(void)
0x180032c18  nop
0x180032c19  mov     eax, 800704C7h
0x180032c1e  jmp     loc_180033153
0x180032c23  xor     esi, esi
0x180032c25  test    rbx, rbx
0x180032c28  jz      short loc_180032C86
0x180032c2a  mov     dword ptr [rsp+120h+var_100], esi
0x180032c2e  mov     r9, [rbp+37h+var_98]
0x180032c32  mov     r8, r12
0x180032c35  mov     rdx, r15
0x180032c38  mov     rcx, rbx
0x180032c3b  call    ?pGetFileObjects@@YAJPEAVString@UnBCL@@PEAV?$ArrayList@PEAVCFileObject@@@2@0PEAV?$Hashtable@PEAVString@UnBCL@@K@2@H@Z; pGetFileObjects(UnBCL::String *,UnBCL::ArrayList<CFileObject *> *,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,ulong> *,int)
0x180032c40  mov     esi, eax
0x180032c42  test    eax, eax
0x180032c44  jns     short loc_180032C70
0x180032c46  lea     rbx, ??_7?$SmartPtr@V?$ArrayList@PEAVCFileObject@@@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::ArrayList<CFileObject *>>::`vftable'
0x180032c4d  mov     [rbp+37h+var_A8], rbx
0x180032c51  lea     rcx, [rbp+37h+var_A8]
0x180032c55  call    ?DeAssign@?$SmartPtr@U?$IEnumerator@K@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::IEnumerator<ulong>>::DeAssign(void)
0x180032c5a  nop
0x180032c5b  mov     [rsp+120h+var_C0], rbx
0x180032c60  lea     rcx, [rsp+120h+var_C0]
0x180032c65  call    ?DeAssign@?$SmartPtr@U?$IEnumerator@K@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::IEnumerator<ulong>>::DeAssign(void)
0x180032c6a  nop
0x180032c6b  jmp     loc_180033151
0x180032c70  mov     rbx, [rsp+120h+var_B8]
0x180032c75  mov     rax, [rbx]
0x180032c78  mov     rcx, rbx
0x180032c7b  mov     rax, [rax+58h]
0x180032c7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032c84  jmp     short loc_180032C8B
0x180032c86  mov     rbx, [rsp+120h+var_B8]
0x180032c8b  test    r14, r14
0x180032c8e  jz      loc_180032D73
0x180032c94  mov     dword ptr [rsp+120h+var_100], 0
0x180032c9c  mov     r9, [rbp+37h+var_98]
0x180032ca0  mov     r8, r12
0x180032ca3  mov     rdx, r13
0x180032ca6  mov     rcx, r14
0x180032ca9  call    ?pGetFileObjects@@YAJPEAVString@UnBCL@@PEAV?$ArrayList@PEAVCFileObject@@@2@0PEAV?$Hashtable@PEAVString@UnBCL@@K@2@H@Z; pGetFileObjects(UnBCL::String *,UnBCL::ArrayList<CFileObject *> *,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,ulong> *,int)
0x180032cae  mov     esi, eax
0x180032cb0  test    eax, eax
0x180032cb2  jns     loc_180032D63
0x180032cb8  call    cs:__imp_GetLastError
0x180032cbe  mov     edi, eax
0x180032cc0  call    cs:__imp_CurrentIP
0x180032cc6  mov     rbx, rax
0x180032cc9  mov     rcx, r14
0x180032ccc  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180032cd2  mov     r8, rax
0x180032cd5  mov     r9d, esi
0x180032cd8  lea     rdx, aExecutediffErr; "ExecuteDiff: Error getting the real fil"...
0x180032cdf  mov     ecx, 2000000h; unsigned int
0x180032ce4  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180032ce9  mov     dword ptr [rsp+120h+var_D0], 0
0x180032cf1  mov     [rsp+120h+var_D8], 0
0x180032cfa  mov     dword ptr [rsp+120h+var_E0], edi
0x180032cfe  mov     [rsp+120h+var_E8], rbx
0x180032d03  lea     rcx, aPexecutediff; "pExecuteDiff"
0x180032d0a  mov     [rsp+120h+var_F0], rcx
0x180032d0f  lea     rcx, aBaseDiagnosisS_3; "base\\diagnosis\\srt\\pitr\\dll\\src\\r"...
0x180032d16  mov     [rsp+120h+var_F8], rcx
0x180032d1b  mov     dword ptr [rsp+120h+var_100], 2AFh
0x180032d23  xor     r9d, r9d
0x180032d26  lea     r8, aD; "D"
0x180032d2d  xor     edx, edx
0x180032d2f  mov     rcx, rax
0x180032d32  call    cs:__imp_WdsSetupLogMessageW
0x180032d38  nop
0x180032d39  lea     rbx, ??_7?$SmartPtr@V?$ArrayList@PEAVCFileObject@@@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::ArrayList<CFileObject *>>::`vftable'
0x180032d40  mov     [rbp+37h+var_A8], rbx
0x180032d44  lea     rcx, [rbp+37h+var_A8]
0x180032d48  call    ?DeAssign@?$SmartPtr@U?$IEnumerator@K@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::IEnumerator<ulong>>::DeAssign(void)
0x180032d4d  nop
0x180032d4e  mov     [rsp+120h+var_C0], rbx
0x180032d53  lea     rcx, [rsp+120h+var_C0]
0x180032d58  call    ?DeAssign@?$SmartPtr@U?$IEnumerator@K@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::IEnumerator<ulong>>::DeAssign(void)
0x180032d5d  nop
0x180032d5e  jmp     loc_180033151
0x180032d63  mov     rax, [r13+0]
0x180032d67  mov     rcx, r13
0x180032d6a  mov     rax, [rax+58h]
0x180032d6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032d73  xor     r15d, r15d
0x180032d76  xor     r12d, r12d
0x180032d79  test    rdi, rdi
0x180032d7c  jz      short loc_180032D97
0x180032d7e  mov     rcx, [rdi+68h]; hHandle
0x180032d82  test    rcx, rcx
0x180032d85  jz      short loc_180032D97
0x180032d87  xor     edx, edx; dwMilliseconds
0x180032d89  call    cs:__imp_WaitForSingleObject
0x180032d8f  test    eax, eax
0x180032d91  jz      loc_1800330A2
0x180032d97  xor     edx, edx
0x180032d99  lea     rcx, [rbp+37h+var_50]
0x180032d9d  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180032da3  nop
0x180032da4  mov     rax, [rbx+8]
0x180032da8  movsxd  rcx, dword ptr [rax+0Ch]
0x180032dac  add     rcx, 8
0x180032db0  add     rcx, rbx
0x180032db3  mov     rax, [rcx]
0x180032db6  mov     rax, [rax]
0x180032db9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032dbe  cmp     r15d, eax
0x180032dc1  jge     short loc_180032DE6
0x180032dc3  mov     rax, [rbx+8]
0x180032dc7  movsxd  rcx, dword ptr [rax+10h]
0x180032dcb  add     rbx, 8
0x180032dcf  add     rcx, rbx
0x180032dd2  mov     rax, [rcx]
0x180032dd5  mov     edx, r15d
0x180032dd8  mov     rax, [rax+18h]
0x180032ddc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032de1  mov     rbx, [rax]
0x180032de4  jmp     short loc_180032DE8
0x180032de6  xor     ebx, ebx
0x180032de8  mov     rax, [r13+8]
0x180032dec  movsxd  rcx, dword ptr [rax+0Ch]
0x180032df0  add     rcx, 8
0x180032df4  add     rcx, r13
0x180032df7  mov     rax, [rcx]
0x180032dfa  mov     rax, [rax]
0x180032dfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032e02  cmp     r12d, eax
0x180032e05  jge     short loc_180032E2A
0x180032e07  mov     rax, [r13+8]
0x180032e0b  movsxd  rcx, dword ptr [rax+10h]
0x180032e0f  add     rcx, 8
0x180032e13  add     rcx, r13
0x180032e16  mov     rax, [rcx]
0x180032e19  mov     edx, r12d
0x180032e1c  mov     rax, [rax+18h]
0x180032e20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032e25  mov     rdi, [rax]
0x180032e28  jmp     short loc_180032E2C
0x180032e2a  xor     edi, edi
0x180032e2c  test    rbx, rbx
0x180032e2f  jnz     short loc_180032E3A
0x180032e31  test    rdi, rdi
0x180032e34  jz      loc_180033121
0x180032e3a  test    rdi, rdi
0x180032e3d  jz      short loc_180032E4E
0x180032e3f  lea     rcx, [rdi+18h]
0x180032e43  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180032e49  mov     rsi, rax
0x180032e4c  jmp     short loc_180032E50
0x180032e4e  xor     esi, esi
0x180032e50  test    rbx, rbx
0x180032e53  jz      short loc_180032E61
0x180032e55  lea     rcx, [rbx+18h]
0x180032e59  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180032e5f  jmp     short loc_180032E63
0x180032e61  xor     eax, eax
0x180032e63  mov     r14d, 1
0x180032e69  mov     r8d, r14d
0x180032e6c  mov     rdx, rsi
0x180032e6f  mov     rcx, rax
0x180032e72  call    cs:__imp_?Compare@String@UnBCL@@SAHPEBV12@0H@Z; UnBCL::String::Compare(UnBCL::String const *,UnBCL::String const *,int)
0x180032e78  test    eax, eax
0x180032e7a  jns     short loc_180032E88
0x180032e7c  test    rbx, rbx
0x180032e7f  jz      short loc_180032EBE
0x180032e81  xor     edi, edi
0x180032e83  add     r15d, r14d
0x180032e86  jmp     short loc_180032EB6
0x180032e88  jle     short loc_180032E93
0x180032e8a  test    rdi, rdi
0x180032e8d  jz      short loc_180032EA1
0x180032e8f  xor     ebx, ebx
0x180032e91  jmp     short loc_180032EAE
0x180032e93  mov     al, 10h
0x180032e95  test    [rbx+48h], al
0x180032e98  jnz     short loc_180032EA6
0x180032e9a  test    [rdi+48h], al
0x180032e9d  jz      short loc_180032EAB
0x180032e9f  xor     edi, edi
0x180032ea1  add     r15d, r14d
0x180032ea4  jmp     short loc_180032EB1
0x180032ea6  test    [rdi+48h], al
0x180032ea9  jz      short loc_180032EBC
0x180032eab  add     r15d, r14d
0x180032eae  add     r12d, r14d
0x180032eb1  test    rbx, rbx
0x180032eb4  jz      short loc_180032EC1
0x180032eb6  lea     rcx, [rbx+18h]
0x180032eba  jmp     short loc_180032EC5
0x180032ebc  xor     ebx, ebx
0x180032ebe  add     r12d, r14d
0x180032ec1  lea     rcx, [rdi+18h]
0x180032ec5  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180032ecb  mov     r14, rax
0x180032ece  mov     rax, [rbp+37h+var_68]
0x180032ed2  test    rax, rax
0x180032ed5  jz      short loc_180032EE8
0x180032ed7  mov     rdx, r14
0x180032eda  mov     rcx, rax
0x180032edd  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x180032ee3  mov     rsi, rax
0x180032ee6  jmp     short loc_180032F19
0x180032ee8  mov     ecx, 18h
0x180032eed  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180032ef3  mov     rsi, rax
0x180032ef6  mov     [rbp+37h+var_70], rax
0x180032efa  test    rax, rax
0x180032efd  jz      short loc_180032F17
0x180032eff  mov     rdx, r14
0x180032f02  mov     rcx, rax
0x180032f05  call    cs:__imp_??0String@UnBCL@@QEAA@PEBV01@@Z; UnBCL::String::String(UnBCL::String const *)
0x180032f0b  lea     rax, ??_SString@UnBCL@@6B@; const UnBCL::String::`local vftable'
0x180032f12  mov     [rsi], rax
0x180032f15  jmp     short loc_180032F19
0x180032f17  xor     esi, esi
0x180032f19  mov     rdx, rsi
0x180032f1c  lea     rcx, [rbp+37h+var_60]
0x180032f20  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
  ... truncated ...
```
