# Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::ICpuFrameProcessor,Rdp::Avenc::ICpuFrameAsyncProcessor>::CreateSharedResources(std::span<Rdp::Avenc::AVENC_SHARED_RESOURCE,-1> &&,Rdp::Avenc::AVENC_RESOURCE_TYPE)

- ea: `0x180047f44`
- end: `0x18004872f`
- name: `?CreateSharedResources@?$CIc3FrameProcessor@UICpuFrameProcessor@Avenc@Rdp@@UICpuFrameAsyncProcessor@23@@Ic3@Avenc@Rdp@@IEAAJ$$QEAV?$span@UAVENC_SHARED_RESOURCE@Avenc@Rdp@@$0?0@std@@W4AVENC_RESOURCE_TYPE@34@@Z`
- size: `2027`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x180048fc4`
- `0x18004a030`

## callees

- `0x18000154c`
- `0x1800021e4`
- `0x180006580`
- `0x1800080cc`
- `0x18000e848`
- `0x18000ec04`
- `0x180019998`
- `0x1800199cc`
- `0x1800241ac`
- `0x180047f44`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800483ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004854a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800483ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004854a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800483ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048537`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800483ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048537`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800485d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800485d8`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800485fe`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800485fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800483f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048542`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048629`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048647`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800483f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048542`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048629`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048647`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180048044`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180048044`

## string_xrefs

- `0x1800486e2`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18004846b`: `Failed to create shared GPU texture handle`
- `0x180047fa1`: `CreateSharedResources`
- `0x180048659`: `Unable to create resources for stopped frame processor.`
- `0x180048719`: `Failed to open WUDFHost process`
- `0x18004836b`: `Failed to create shared texture`
- `0x1800482e6`: `Failed to create texture desc for shared resources`
- `0x18004859a`: `Failed to create shared GPU fence handle`
- `0x1800484f0`: `Failed to create shared fence.`
- `0x180047fad`: `Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::ICpuFrameProcessor,struct Rdp::Avenc::ICpuFrameAsyncProcessor>::CreateSharedResources`
- `0x18004801d`: `Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::ICpuFrameProcessor,struct Rdp::Avenc::ICpuFrameAsyncProcessor>::CreateSharedResources`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::ICpuFrameProcessor,Rdp::Avenc::ICpuFrameAsyncProcessor>::CreateSharedResources(
        __int64 a1,
        __int64 *a2,
        int a3,
        int a4)
{
  char *v6; // rbx
  __int64 v7; // rdx
  int v8; // ecx
  bool v9; // cl
  unsigned int v10; // eax
  int v11; // r8d
  int v12; // r9d
  __int64 v13; // rdi
  int v14; // edi
  __int64 v15; // rcx
  unsigned int v16; // eax
  int v17; // ecx
  __int64 v18; // rax
  int v19; // ecx
  __int64 v20; // r14
  __int64 v21; // rax
  __int64 *v22; // rcx
  __int64 v23; // rax
  unsigned int v24; // eax
  int v25; // eax
  HANDLE v26; // r13
  DWORD v27; // edi
  unsigned int v28; // edi
  __int64 *v29; // rcx
  __int64 v30; // rax
  unsigned int v31; // eax
  HANDLE v32; // r13
  DWORD LastError; // edi
  unsigned int v34; // eax
  HANDLE v35; // rdi
  HANDLE CurrentProcess; // rax
  HANDLE v37; // rax
  const char *v38; // r9
  __int64 result; // rax
  const char *v40; // r9
  int v41; // edx
  const char *dwDesiredAccess; // [rsp+20h] [rbp-128h]
  int dwDesiredAccessa; // [rsp+20h] [rbp-128h]
  const char *dwDesiredAccessb; // [rsp+20h] [rbp-128h]
  const char *bInheritHandle; // [rsp+28h] [rbp-120h]
  const char *bInheritHandlea; // [rsp+28h] [rbp-120h]
  const char *bInheritHandleb; // [rsp+28h] [rbp-120h]
  const char *bInheritHandlec; // [rsp+28h] [rbp-120h]
  HANDLE hObject; // [rsp+60h] [rbp-E8h] BYREF
  const char *v50; // [rsp+68h] [rbp-E0h] BYREF
  int v51; // [rsp+70h] [rbp-D8h]
  HANDLE TargetHandle; // [rsp+78h] [rbp-D0h] BYREF
  __int64 v53; // [rsp+80h] [rbp-C8h] BYREF
  int v54; // [rsp+88h] [rbp-C0h]
  const char *v55; // [rsp+90h] [rbp-B8h] BYREF
  const char *v56; // [rsp+98h] [rbp-B0h] BYREF
  _QWORD v57[2]; // [rsp+A0h] [rbp-A8h] BYREF
  _OWORD v58[3]; // [rsp+B0h] [rbp-98h] BYREF
  _DWORD v59[12]; // [rsp+E0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  try
  {
    v51 = a3;
    v54 = 0;
    if ( *(_QWORD *)(a1 + 176) )
    {
      if ( (unsigned int)dword_1800C1058 > 4 )
      {
        LODWORD(TargetHandle) = a3;
        hObject = "CreateSharedResources";
        v50 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::ICpuFrameProcessor,struct Rdp::Avenc::ICpuFrameAsyn"
              "cProcessor>::CreateSharedResources";
        LODWORD(v53) = 467;
        v55 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1800C1058,
          (unsigned int)word_1800B095A,
          a3,
          a4,
          (__int64)&v55,
          (__int64)&v53,
          (__int64)&v50,
          (__int64)&hObject,
          (__int64)&TargetHandle);
      }
      v6 = (char *)OpenProcess(0x1040u, 0, *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 176) + 104LL) + 280LL));
      v57[1] = v6;
      if ( (unsigned __int64)(v6 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
        wil::details::in1diag3::Throw_GetLastErrorMsg(
          retaddr,
          (void *)0x1DF,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
          "Failed to open WUDFHost process",
          dwDesiredAccess);
      v7 = *(_QWORD *)(a1 + 176);
      v8 = *(_DWORD *)(*(_QWORD *)(v7 + 104) + 284LL);
      LODWORD(hObject) = 8;
      HIWORD(hObject) = 0;
      v9 = v8 == 2;
      BYTE4(hObject) = v9;
      BYTE5(hObject) = v9;
      if ( *(_BYTE *)(*(_QWORD *)(v7 + 104) + 289LL) && v9 )
        *(_WORD *)((char *)&hObject + 5) = 256;
      v10 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64, HANDLE *))(**(_QWORD **)(a1 + 192) + 280LL))(
              *(_QWORD *)(a1 + 192),
              qword_18009A1C8,
              8,
              &hObject);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x1F1,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
        (const char *)v10,
        (int)"Failed to set FrameProcessorPrivateDataId private data on encoder device",
        bInheritHandle);
      v13 = *(_QWORD *)(a1 + 208);
      if ( v13 )
      {
        v14 = *(_DWORD *)(v13 + 272);
      }
      else
      {
        v15 = *(_QWORD *)(a1 + 216);
        if ( v15 )
        {
          memset(v59, 0, 28);
          v16 = (*(__int64 (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v15 + 128LL))(v15, v59);
          wil::details::in1diag3::Throw_IfFailedMsg(
            retaddr,
            (void *)0x1FF,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
            (const char *)v16,
            (int)"Failed to get video format from video source provider",
            bInheritHandlea);
          if ( v59[0] == 842094158 )
          {
            v14 = 103;
          }
          else
          {
            if ( v59[0] != 1095911234 )
            {
              v40 = (const char *)(unsigned int)wil::verify_hresult<long>(2147942450LL);
              LODWORD(bInheritHandlea) = v41;
              wil::details::in1diag3::Throw_HrMsg(
                retaddr,
                (void *)0x20B,
                (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
                v40,
                (int)"The given fcc format is not supported: %08X",
                bInheritHandlea);
            }
            v14 = 87;
          }
        }
        else
        {
          v14 = 0;
        }
      }
      if ( (unsigned int)dword_1800C1058 > 5 )
      {
        LODWORD(v53) = v51;
        LODWORD(TargetHandle) = v14;
        LODWORD(v50) = *((_DWORD *)a2 + 2);
        v55 = "Creating resources";
        v56 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::ICpuFrameProcessor,struct Rdp::Avenc::ICpuFrameAsyn"
              "cProcessor>::CreateSharedResources";
        LODWORD(hObject) = 532;
        v57[0] = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1800C1058,
          (unsigned int)&byte_1800B09A7,
          v11,
          v12,
          (__int64)v57,
          (__int64)&hObject,
          (__int64)&v56,
          (__int64)&v55,
          (__int64)&v50,
          (__int64)&TargetHandle,
          (__int64)&v53);
      }
      memset(v58, 0, 44);
      v17 = v51;
      if ( !v51 )
      {
        v18 = *(_QWORD *)(a1 + 176);
        v19 = *(_DWORD *)(v18 + 144);
        LODWORD(v58[0]) = (*(_DWORD *)(v18 + 140) + 1) & 0xFFFFFFFE;
        DWORD1(v58[0]) = (v19 + 1) & 0xFFFFFFFE;
        LODWORD(v58[1]) = v14;
        HIDWORD(v58[1]) = 0;
        *((_QWORD *)&v58[0] + 1) = 0x100000001LL;
        *(_QWORD *)&v58[2] = 136;
        *(_QWORD *)((char *)&v58[1] + 4) = 1;
        DWORD2(v58[2]) = 2050;
        wil::details::in1diag3::Throw_IfFailedMsg(
          retaddr,
          (void *)0x21E,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
          0,
          (int)"Failed to create texture desc for shared resources",
          bInheritHandlea);
        v17 = v51;
      }
      v20 = *a2;
      v21 = *a2 + 32 * a2[1];
      v55 = (const char *)v21;
      while ( v20 != v21 )
      {
        hObject = 0;
        if ( v17 )
        {
          if ( v17 == 1 )
          {
            v50 = 0;
            v29 = *(__int64 **)(a1 + 192);
            v30 = *v29;
            v50 = 0;
            v31 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, GUID *, const char **))(v30 + 544))(
                    v29,
                    0,
                    2,
                    &GUID_affde9d1_1df7_4bb7_8a34_0f46251dab80,
                    &v50);
            wil::details::in1diag3::Throw_IfFailedMsg(
              retaddr,
              (void *)0x250,
              (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
              (const char *)v31,
              (int)"Failed to create shared fence.",
              bInheritHandlea);
            v57[0] = v50;
            v56 = *(const char **)(*(_QWORD *)v50 + 56LL);
            v32 = hObject;
            if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            {
              LastError = GetLastError();
              CloseHandle(v32);
              SetLastError(LastError);
            }
            hObject = 0;
            v34 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD, HANDLE *))v56)(
                    v57[0],
                    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 176) + 104LL) + 296LL),
                    0x10000000,
                    0,
                    &hObject);
            wil::details::in1diag3::Throw_IfFailedMsg(
              retaddr,
              (void *)0x25B,
              (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
              (const char *)v34,
              (int)"Failed to create shared GPU fence handle",
              bInheritHandlec);
            *(_DWORD *)v20 = 32;
            *(_QWORD *)(v20 + 16) = v50;
            *(_DWORD *)(v20 + 24) = 1;
          }
        }
        else
        {
          v50 = 0;
          v22 = *(__int64 **)(a1 + 192);
          v23 = *v22;
          v50 = 0;
          v24 = (*(__int64 (__fastcall **)(__int64 *, _OWORD *, _QWORD, const char **))(v23 + 40))(v22, v58, 0, &v50);
          wil::details::in1diag3::Throw_IfFailedMsg(
            retaddr,
            (void *)0x230,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
            (const char *)v24,
            (int)"Failed to create shared texture",
            bInheritHandlea);
          v53 = 0;
          v25 = (**(__int64 (__fastcall ***)(const char *, GUID *, __int64 *))v50)(
                  v50,
                  &GUID_30961379_4609_4a41_998e_54fe567ee0c1,
                  &v53);
          if ( v25 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x1CBE,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
              (const char *)(unsigned int)v25,
              dwDesiredAccessa);
          v57[0] = v53;
          v56 = *(const char **)(*(_QWORD *)v53 + 104LL);
          v26 = hObject;
          if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          {
            v27 = GetLastError();
            CloseHandle(v26);
            SetLastError(v27);
          }
          hObject = 0;
          v28 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD, HANDLE *))v56)(
                  v57[0],
                  *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 176) + 104LL) + 296LL),
                  2147483649LL,
                  0,
                  &hObject);
          if ( v53 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
          wil::details::in1diag3::Throw_IfFailedMsg(
            retaddr,
            (void *)0x23B,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
            (const char *)v28,
            (int)"Failed to create shared GPU texture handle",
            bInheritHandleb);
          *(_DWORD *)v20 = 32;
          *(_QWORD *)(v20 + 16) = v50;
          *(_DWORD *)(v20 + 24) = 0;
          v54 |= 1u;
        }
        TargetHandle = 0;
        v35 = hObject;
        CurrentProcess = GetCurrentProcess();
        if ( !DuplicateHandle(CurrentProcess, v35, v6, &TargetHandle, 0, 0, 2u) )
          wil::details::in1diag3::Throw_GetLastErrorMsg(
            retaddr,
            (void *)0x275,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
            "Failed to duplicate shared resource handle while creating shared resources",
            dwDesiredAccessb);
        v37 = TargetHandle;
        TargetHandle = 0;
        *(_QWORD *)(v20 + 8) = v37;
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(hObject);
        v20 += 32;
        v21 = (__int64)v55;
        v17 = v51;
      }
      CloseHandle(v6);
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0x1CC,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
        (const char *)0x8000FFFFLL,
        (int)"Unable to create resources for stopped frame processor.",
        bInheritHandle);
      result = 0;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x280,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
                           v38);
  }
  return result;
}

```

## disassembly

```asm
0x180047f44  mov     r11, rsp
0x180047f47  mov     [r11+18h], rbx
0x180047f4b  push    rsi
0x180047f4c  push    rdi
0x180047f4d  push    r13
0x180047f4f  push    r14
0x180047f51  push    r15
0x180047f53  sub     rsp, 120h
0x180047f5a  mov     rax, cs:__security_cookie
0x180047f61  xor     rax, rsp
0x180047f64  mov     [rsp+148h+var_38], rax
0x180047f6c  mov     [rsp+148h+var_D8], r8d
0x180047f71  mov     r13, rdx
0x180047f74  mov     r15, rcx
0x180047f77  xor     edi, edi
0x180047f79  mov     [rsp+148h+var_C0], edi
0x180047f80  cmp     [rcx+0B0h], rdi
0x180047f87  jz      loc_180048651
0x180047f8d  mov     eax, cs:dword_1800C1058
0x180047f93  cmp     eax, 4
0x180047f96  jbe     loc_18004801D
0x180047f9c  mov     dword ptr [rsp+148h+TargetHandle], r8d
0x180047fa1  lea     rax, aCreatesharedre; "CreateSharedResources"
0x180047fa8  mov     [rsp+148h+hObject], rax
0x180047fad  lea     r14, aRdpAvencIc3Cic_14; "Rdp::Avenc::Ic3::CIc3FrameProcessor<str"...
0x180047fb4  mov     [rsp+148h+var_E0], r14
0x180047fb9  mov     dword ptr [rsp+148h+var_C8], 1D3h
0x180047fc4  lea     rsi, aOnecoreuapTerm_23; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180047fcb  mov     [r11-0B8h], rsi
0x180047fd2  lea     rax, [rsp+148h+TargetHandle]
0x180047fd7  mov     [rsp+148h+var_108], rax
0x180047fdc  lea     rax, [rsp+148h+hObject]
0x180047fe1  mov     [rsp+148h+var_110], rax
0x180047fe6  lea     rax, [rsp+148h+var_E0]
0x180047feb  mov     qword ptr [rsp+148h+dwOptions], rax
0x180047ff0  lea     rax, [r11-0C8h]
0x180047ff7  mov     qword ptr [rsp+148h+bInheritHandle], rax
0x180047ffc  lea     rax, [r11-0B8h]
0x180048003  mov     qword ptr [rsp+148h+dwDesiredAccess], rax
0x180048008  lea     rdx, word_1800B095A
0x18004800f  lea     rcx, dword_1800C1058
0x180048016  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18004801b  jmp     short loc_18004802B
0x18004801d  lea     r14, aRdpAvencIc3Cic_14; "Rdp::Avenc::Ic3::CIc3FrameProcessor<str"...
0x180048024  lea     rsi, aOnecoreuapTerm_23; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18004802b  mov     rax, [r15+0B0h]
0x180048032  mov     r8, [rax+68h]
0x180048036  mov     r8d, [r8+118h]; dwProcessId
0x18004803d  xor     edx, edx; bInheritHandle
0x18004803f  mov     ecx, 1040h; dwDesiredAccess
0x180048044  call    cs:__imp_OpenProcess
0x18004804a  mov     rbx, rax
0x18004804d  mov     [rsp+148h+var_A0], rax
0x180048055  dec     rax
0x180048058  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004805c  ja      loc_180048711
0x180048062  mov     rdx, [r15+0B0h]
0x180048069  mov     rax, [rdx+68h]
0x18004806d  mov     ecx, [rax+11Ch]
0x180048073  mov     r8d, 8
0x180048079  mov     dword ptr [rsp+148h+hObject], r8d
0x18004807e  mov     word ptr [rsp+148h+hObject+6], di
0x180048083  cmp     ecx, 2
0x180048086  setz    cl
0x180048089  mov     byte ptr [rsp+148h+hObject+4], cl
0x18004808d  mov     byte ptr [rsp+148h+hObject+5], cl
0x180048091  mov     rax, [rdx+68h]
0x180048095  cmp     [rax+121h], dil
0x18004809c  jz      short loc_1800480A9
0x18004809e  test    cl, cl
0x1800480a0  jz      short loc_1800480A9
0x1800480a2  mov     word ptr [rsp+148h+hObject+5], 100h
0x1800480a9  mov     rcx, [r15+0C0h]
0x1800480b0  mov     rax, [rcx]
0x1800480b3  lea     r9, [rsp+148h+hObject]
0x1800480b8  lea     rdx, qword_18009A1C8
0x1800480bf  mov     rax, [rax+118h]
0x1800480c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800480cb  mov     rcx, [rsp+148h]; this
0x1800480d3  lea     rdx, aFailedToSetFra; "Failed to set FrameProcessorPrivateData"...
0x1800480da  mov     qword ptr [rsp+148h+dwDesiredAccess], rdx; int
0x1800480df  mov     r9d, eax; char *
0x1800480e2  mov     r8, rsi; unsigned int
0x1800480e5  mov     edx, 1F1h; void *
0x1800480ea  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800480ef  mov     rdi, [r15+0D0h]
0x1800480f6  test    rdi, rdi
0x1800480f9  jz      short loc_180048106
0x1800480fb  mov     edi, [rdi+110h]
0x180048101  jmp     loc_18004818B
0x180048106  mov     rcx, [r15+0D8h]
0x18004810d  test    rcx, rcx
0x180048110  jz      short loc_180048189
0x180048112  xorps   xmm0, xmm0
0x180048115  movups  xmmword ptr [rsp+148h+var_68], xmm0
0x18004811d  movups  xmmword ptr [rsp+148h+var_68+0Ch], xmm0
0x180048125  mov     rax, [rcx]
0x180048128  lea     rdx, [rsp+148h+var_68]
0x180048130  mov     rax, [rax+80h]
0x180048137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004813c  mov     rcx, [rsp+148h]; this
0x180048144  lea     rdx, aFailedToGetVid; "Failed to get video format from video s"...
0x18004814b  mov     qword ptr [rsp+148h+dwDesiredAccess], rdx; int
0x180048150  mov     r9d, eax; char *
0x180048153  mov     r8, rsi; unsigned int
0x180048156  mov     edx, 1FFh; void *
0x18004815b  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180048160  mov     edx, [rsp+148h+var_68]
0x180048167  cmp     edx, 3231564Eh
0x18004816d  jz      short loc_180048182
0x18004816f  cmp     edx, 41524742h
0x180048175  jnz     loc_1800486AC
0x18004817b  mov     edi, 57h ; 'W'
0x180048180  jmp     short loc_18004818B
0x180048182  mov     edi, 67h ; 'g'
0x180048187  jmp     short loc_18004818B
0x180048189  xor     edi, edi
0x18004818b  mov     eax, cs:dword_1800C1058
0x180048191  cmp     eax, 5
0x180048194  jbe     loc_18004823D
0x18004819a  mov     eax, [rsp+148h+var_D8]
0x18004819e  mov     dword ptr [rsp+148h+var_C8], eax
0x1800481a5  mov     dword ptr [rsp+148h+TargetHandle], edi
0x1800481a9  mov     eax, [r13+8]
0x1800481ad  mov     dword ptr [rsp+148h+var_E0], eax
0x1800481b1  lea     rax, aCreatingResour; "Creating resources"
0x1800481b8  mov     [rsp+148h+var_B8], rax
0x1800481c0  mov     [rsp+148h+var_B0], r14
0x1800481c8  mov     dword ptr [rsp+148h+hObject], 214h
0x1800481d0  mov     [rsp+148h+var_A8], rsi
0x1800481d8  lea     rax, [rsp+148h+var_C8]
0x1800481e0  mov     [rsp+148h+var_F8], rax
0x1800481e5  lea     rax, [rsp+148h+TargetHandle]
0x1800481ea  mov     [rsp+148h+var_100], rax
0x1800481ef  lea     rax, [rsp+148h+var_E0]
0x1800481f4  mov     [rsp+148h+var_108], rax
0x1800481f9  lea     rax, [rsp+148h+var_B8]
0x180048201  mov     [rsp+148h+var_110], rax
0x180048206  lea     rax, [rsp+148h+var_B0]
0x18004820e  mov     qword ptr [rsp+148h+dwOptions], rax
0x180048213  lea     rax, [rsp+148h+hObject]
0x180048218  mov     qword ptr [rsp+148h+bInheritHandle], rax; char *
0x18004821d  lea     rax, [rsp+148h+var_A8]
0x180048225  mov     qword ptr [rsp+148h+dwDesiredAccess], rax
0x18004822a  lea     rdx, byte_1800B09A7
0x180048231  lea     rcx, dword_1800C1058
0x180048238  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18004823d  xorps   xmm0, xmm0
0x180048240  movups  [rsp+148h+var_98], xmm0
0x180048248  movups  [rsp+148h+var_88], xmm0
0x180048250  movups  [rsp+148h+var_88+0Ch], xmm0
0x180048258  mov     ecx, [rsp+148h+var_D8]
0x18004825c  xor     r8d, r8d
0x18004825f  test    ecx, ecx
0x180048261  jnz     loc_180048306
0x180048267  mov     rax, [r15+0B0h]
0x18004826e  mov     ecx, [rax+90h]
0x180048274  mov     eax, [rax+8Ch]
0x18004827a  inc     eax
0x18004827c  mov     edx, 0FFFFFFFEh
0x180048281  and     eax, edx
0x180048283  mov     dword ptr [rsp+148h+var_98], eax
0x18004828a  lea     eax, [rcx+1]
0x18004828d  and     eax, edx
0x18004828f  mov     dword ptr [rsp+148h+var_98+4], eax
0x180048296  mov     dword ptr [rsp+148h+var_88], edi
0x18004829d  mov     dword ptr [rsp+148h+var_88+0Ch], r8d
0x1800482a5  mov     dword ptr [rsp+148h+var_98+0Ch], 1
0x1800482b0  mov     dword ptr [rsp+148h+var_98+8], 1
0x1800482bb  mov     [rsp+148h+var_78], 88h
0x1800482c7  mov     qword ptr [rsp+148h+var_88+4], 1
0x1800482d3  mov     [rsp+148h+var_70], 802h
0x1800482de  mov     rcx, [rsp+148h]; this
0x1800482e6  lea     rax, aFailedToCreate_7; "Failed to create texture desc for share"...
0x1800482ed  mov     qword ptr [rsp+148h+dwDesiredAccess], rax; int
0x1800482f2  xor     r9d, r9d; char *
0x1800482f5  mov     r8, rsi; unsigned int
0x1800482f8  mov     edx, 21Eh; void *
0x1800482fd  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180048302  mov     ecx, [rsp+148h+var_D8]
0x180048306  mov     r14, [r13+0]
0x18004830a  mov     rax, [r13+8]
0x18004830e  shl     rax, 5
0x180048312  add     rax, r14
0x180048315  mov     [rsp+148h+var_B8], rax
0x18004831d  xor     r13d, r13d
0x180048320  cmp     r14, rax
0x180048323  jz      loc_180048644
0x180048329  mov     [rsp+148h+hObject], r13
0x18004832e  test    ecx, ecx
0x180048330  jnz     loc_1800484A8
0x180048336  mov     [rsp+148h+var_E0], r13
0x18004833b  mov     rcx, [r15+0C0h]
0x180048342  mov     rax, [rcx]
0x180048345  mov     [rsp+148h+var_E0], r13
0x18004834a  lea     r9, [rsp+148h+var_E0]
0x18004834f  xor     r8d, r8d
0x180048352  lea     rdx, [rsp+148h+var_98]
0x18004835a  mov     rax, [rax+28h]
0x18004835e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048363  mov     rcx, [rsp+148h]; this
0x18004836b  lea     rdx, aFailedToCreate_5; "Failed to create shared texture"
0x180048372  mov     qword ptr [rsp+148h+dwDesiredAccess], rdx; int
0x180048377  mov     r9d, eax; char *
0x18004837a  mov     r8, rsi; unsigned int
0x18004837d  mov     edx, 230h; void *
0x180048382  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180048387  mov     rcx, [rsp+148h+var_E0]
0x18004838c  mov     [rsp+148h+var_C8], r13
0x180048394  mov     rax, [rcx]
0x180048397  lea     r8, [rsp+148h+var_C8]
0x18004839f  lea     rdx, _GUID_30961379_4609_4a41_998e_54fe567ee0c1
0x1800483a6  mov     rax, [rax]
0x1800483a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800483ae  mov     rcx, [rsp+148h]; this
0x1800483b6  test    eax, eax
0x1800483b8  js      loc_1800486DF
0x1800483be  mov     rax, [rsp+148h+var_C8]
0x1800483c6  mov     [rsp+148h+var_A8], rax
0x1800483ce  mov     rax, [rax]
0x1800483d1  mov     rax, [rax+68h]
0x1800483d5  mov     [rsp+148h+var_B0], rax
0x1800483dd  mov     r13, [rsp+148h+hObject]
0x1800483e2  lea     rax, [r13-1]
0x1800483e6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800483ea  ja      short loc_180048405
0x1800483ec  call    cs:__imp_GetLastError
0x1800483f2  mov     edi, eax
0x1800483f4  mov     rcx, r13; hObject
0x1800483f7  call    cs:__imp_CloseHandle
0x1800483fd  mov     ecx, edi; dwErrCode
0x1800483ff  call    cs:__imp_SetLastError
0x180048405  xor     r13d, r13d
0x180048408  mov     [rsp+148h+hObject], r13
0x18004840d  mov     rdx, [r15+0B0h]
0x180048414  mov     rdx, [rdx+68h]
0x180048418  lea     rax, [rsp+148h+hObject]
0x18004841d  mov     qword ptr [rsp+148h+dwDesiredAccess], rax
0x180048422  xor     r9d, r9d
0x180048425  mov     r8d, 80000001h
0x18004842b  mov     rdx, [rdx+128h]
0x180048432  mov     rcx, [rsp+148h+var_A8]
0x18004843a  mov     rax, [rsp+148h+var_B0]
0x180048442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048447  mov     edi, eax
0x180048449  mov     rcx, [rsp+148h+var_C8]
0x180048451  test    rcx, rcx
0x180048454  jz      short loc_180048463
0x180048456  mov     rdx, [rcx]
0x180048459  mov     rax, [rdx+10h]
0x18004845d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048462  nop
0x180048463  mov     rcx, [rsp+148h]; this
0x18004846b  lea     rax, aFailedToCreate_6; "Failed to create shared GPU texture han"...
0x180048472  mov     qword ptr [rsp+148h+dwDesiredAccess], rax; int
0x180048477  mov     r9d, edi; char *
0x18004847a  mov     r8, rsi; unsigned int
0x18004847d  mov     edx, 23Bh; void *
0x180048482  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180048487  mov     dword ptr [r14], 20h ; ' '
0x18004848e  mov     rax, [rsp+148h+var_E0]
0x180048493  mov     [r14+10h], rax
0x180048497  mov     [r14+18h], r13d
0x18004849b  or      [rsp+148h+var_C0], 1
0x1800484a3  jmp     loc_1800485CE
0x1800484a8  cmp     ecx, 1
0x1800484ab  jnz     loc_1800485CE
0x1800484b1  mov     [rsp+148h+var_E0], r13
0x1800484b6  mov     rcx, [r15+0C0h]
0x1800484bd  mov     rax, [rcx]
0x1800484c0  mov     [rsp+148h+var_E0], r13
0x1800484c5  lea     rdx, [rsp+148h+var_E0]
0x1800484ca  mov     qword ptr [rsp+148h+dwDesiredAccess], rdx
0x1800484cf  lea     r9, _GUID_affde9d1_1df7_4bb7_8a34_0f46251dab80
0x1800484d6  xor     edx, edx
0x1800484d8  lea     r8d, [rdx+2]
0x1800484dc  mov     rax, [rax+220h]
0x1800484e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800484e8  mov     rcx, [rsp+148h]; this
0x1800484f0  lea     rdx, aFailedToCreate_11; "Failed to create shared fence."
0x1800484f7  mov     qword ptr [rsp+148h+dwDesiredAccess], rdx; int
0x1800484fc  mov     r9d, eax; char *
0x1800484ff  mov     r8, rsi; unsigned int
0x180048502  mov     edx, 250h; void *
0x180048507  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18004850c  mov     rax, [rsp+148h+var_E0]
0x180048511  mov     [rsp+148h+var_A8], rax
0x180048519  mov     rax, [rax]
0x18004851c  mov     rax, [rax+38h]
0x180048520  mov     [rsp+148h+var_B0], rax
0x180048528  mov     r13, [rsp+148h+hObject]
0x18004852d  lea     rax, [r13-1]
0x180048531  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180048535  ja      short loc_180048550
0x180048537  call    cs:__imp_GetLastError
0x18004853d  mov     edi, eax
0x18004853f  mov     rcx, r13; hObject
0x180048542  call    cs:__imp_CloseHandle
0x180048548  mov     ecx, edi; dwErrCode
0x18004854a  call    cs:__imp_SetLastError
  ... truncated ...
```
