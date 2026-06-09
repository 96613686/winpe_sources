# CreateRequestHeader(ushort const * const,ushort * *)

- ea: `0x1800cd46c`
- end: `0x1800cdbd8`
- name: `?CreateRequestHeader@@YAJQEBGPEAPEAG@Z`
- size: `1900`
- prototype: `__int64 __fastcall(const unsigned __int16 *const, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800cdbe0`

## callees

- `0x180004ca8`
- `0x180005045`
- `0x18000b8c8`
- `0x18000efb8`
- `0x1800124a8`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x1800649d4`
- `0x1800cd46c`
- `0x1800dddf0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800cda90`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800cda90`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cda7e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cdb35`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cda7e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cdb35`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800cdb43`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800cdb43`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800cd585`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800cd585`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800cd5d6`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800cd5d6`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1800cd69e`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1800cd69e`

## string_xrefs

- `0x1800cd814`: `Content-Type: application/json; charset=utf-8\nAccept: application/json\nAuthorization: %s\nocp-adrs-client-name: "WIP (Windows)"\nocp-adrs-client-version: %s\nclient-request-id: %s\nreturn-client-request-id: true\nuser-agent:"WIP (Windows)"`
- `0x1800cdae2`: `Content-Type: application/json; charset=utf-8\nAccept: application/json\nAuthorization: %s\nocp-adrs-client-name: "WIP (Windows)"\nocp-adrs-client-version: %s\nclient-request-id: %s\nreturn-client-request-id: true\nuser-agent:"WIP (Windows)"`

## pseudocode

```c
__int64 __fastcall CreateRequestHeader(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  int v4; // ecx
  int v5; // ecx
  unsigned int v6; // ebx
  int v7; // r8d
  int v8; // ecx
  unsigned __int64 v9; // r14
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // r14
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  unsigned __int64 v17; // rsi
  unsigned __int64 v18; // rdi
  int v19; // ecx
  unsigned __int64 v20; // rax
  bool v21; // cf
  unsigned __int64 v22; // r14
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  HANDLE ProcessHeap; // rax
  int v27; // ecx
  unsigned __int16 *v28; // rdi
  HANDLE v29; // rax
  char v31; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v32; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v33; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v34; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v35; // [rsp+58h] [rbp-A8h] BYREF
  SIZE_T dwBytes; // [rsp+60h] [rbp-A0h] BYREF
  GUID pguid; // [rsp+68h] [rbp-98h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+80h] [rbp-80h] BYREF
  OLECHAR sz; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v40[526]; // [rsp+1A2h] [rbp+A2h] BYREF
  unsigned __int16 v41[264]; // [rsp+3B0h] [rbp+2B0h] BYREF

  memset_0(&sz, 0, 0x208u);
  v32 = 0;
  pguid = 0;
  memset_0(&VersionInformation, 0, sizeof(VersionInformation));
  memset_0(v41, 0, 0x208u);
  v35 = 0;
  v33 = 0;
  v34 = 0;
  dwBytes = 0;
  fnEfsLogTrace1Strings(v4, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 46, 20);
  if ( a2 )
    *a2 = 0;
  if ( !a1 )
  {
    v6 = -2147024809;
    v31 = 32;
    v7 = -2147024809;
LABEL_36:
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v7, 46, v31);
    goto LABEL_37;
  }
  if ( a2 )
  {
    fnEfsLogTrace1Strings(v5, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 46, 39);
    v6 = CoCreateGuid(&pguid);
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                v6,
                46,
                39) >= 0 )
    {
      if ( StringFromGUID2(&pguid, &sz, 260) )
      {
        fnEfsLogTrace1Strings(v8, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 46, 48);
        v6 = StringCchLengthW(&sz, 0x7FFFFFFFu, &v32);
        if ( (int)fnEfsLogTrace1String1Dword(
                    g_hPublisher,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                    (unsigned int)&sourceString,
                    v6,
                    46,
                    48) >= 0 )
        {
          v9 = v32;
          if ( v32 - 2 > 0x102 )
          {
            v6 = -2147467259;
            v31 = 56;
            v7 = -2147467259;
            goto LABEL_36;
          }
          v10 = 2 * v32 - 2;
          if ( v10 >= 0x208 )
            _report_rangecheckfailure();
          *(_WORD *)&v40[v10 - 2] = 0;
          v11 = v9 - 2;
          VersionInformation.dwOSVersionInfoSize = 276;
          GetVersionExW(&VersionInformation);
          fnEfsLogTrace1Strings(v12, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 46, 69);
          v6 = StringCchPrintfW(v41, 0x104u, L"%d", VersionInformation.dwBuildNumber);
          if ( (int)fnEfsLogTrace1String1Dword(
                      g_hPublisher,
                      (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                      (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                      (unsigned int)&sourceString,
                      v6,
                      46,
                      69) >= 0 )
          {
            fnEfsLogTrace1Strings(v13, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 46, 73);
            v6 = StringCchLengthW(v41, 0x7FFFFFFFu, &v35);
            if ( (int)fnEfsLogTrace1String1Dword(
                        g_hPublisher,
                        (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                        (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                        (unsigned int)&sourceString,
                        v6,
                        46,
                        73) >= 0 )
            {
              fnEfsLogTrace1Strings(v14, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 46, 77);
              v6 = StringCchLengthW(a1, 0x7FFFFFFFu, &v33);
              if ( (int)fnEfsLogTrace1String1Dword(
                          g_hPublisher,
                          (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                          (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                          (unsigned int)&sourceString,
                          v6,
                          46,
                          77) >= 0 )
              {
                fnEfsLogTrace1Strings(v15, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 46, 81);
                v6 = StringCchLengthW(
                       L"Content-Type: application/json; charset=utf-8\r\n"
                        "Accept: application/json\r\n"
                        "Authorization: %s\r\n"
                        "ocp-adrs-client-name: \"WIP (Windows)\"\r\n"
                        "ocp-adrs-client-version: %s\r\n"
                        "client-request-id: %s\r\n"
                        "return-client-request-id: true\r\n"
                        "user-agent:\"WIP (Windows)\"",
                       0x7FFFFFFFu,
                       &v34);
                if ( (int)fnEfsLogTrace1String1Dword(
                            g_hPublisher,
                            (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                            (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                            (unsigned int)&sourceString,
                            v6,
                            46,
                            81) >= 0 )
                {
                  fnEfsLogTrace1Strings(v16, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 46, 83);
                  v17 = -1;
                  v18 = v33 + v34;
                  if ( v33 + v34 < v33 )
                  {
                    v6 = -2147024362;
                    v18 = -1;
                  }
                  else
                  {
                    v6 = 0;
                  }
                  if ( (int)fnEfsLogTrace1String1Dword(
                              g_hPublisher,
                              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                              (unsigned int)&sourceString,
                              v6,
                              46,
                              83) >= 0 )
                  {
                    fnEfsLogTrace1Strings(v19, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 46, 84);
                    v20 = v18 + v11;
                    v21 = v18 + v11 < v18;
                    v22 = -1;
                    if ( !v21 )
                      v22 = v20;
                    v6 = v21 ? 0x80070216 : 0;
                    if ( (int)fnEfsLogTrace1String1Dword(
                                g_hPublisher,
                                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                                (unsigned int)&sourceString,
                                v6,
                                46,
                                84) >= 0 )
                    {
                      fnEfsLogTrace1Strings(
                        v23,
                        (unsigned int)EFS_TRACE_START_EVENT,
                        (unsigned int)&sourceString,
                        46,
                        85);
                      if ( v22 + v35 >= v22 )
                        v17 = v22 + v35;
                      v6 = v22 + v35 < v22 ? 0x80070216 : 0;
                      v32 = v17;
                      if ( (int)fnEfsLogTrace1String1Dword(
                                  g_hPublisher,
                                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                                  (unsigned int)&sourceString,
                                  v6,
                                  46,
                                  85) >= 0 )
                      {
                        fnEfsLogTrace1Strings(
                          v24,
                          (unsigned int)EFS_TRACE_START_EVENT,
                          (unsigned int)&sourceString,
                          46,
                          92);
                        v6 = ULongLongSub(v17, 5u, &v32);
                        if ( (int)fnEfsLogTrace1String1Dword(
                                    g_hPublisher,
                                    (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                                    (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                                    (unsigned int)&sourceString,
                                    v6,
                                    46,
                                    92) >= 0 )
                        {
                          fnEfsLogTrace1Strings(
                            v25,
                            (unsigned int)EFS_TRACE_START_EVENT,
                            (unsigned int)&sourceString,
                            46,
                            94);
                          v6 = ULongLongMult(v32, 2u, &dwBytes);
                          if ( (int)fnEfsLogTrace1String1Dword(
                                      g_hPublisher,
                                      (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                                      (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                                      (unsigned int)&sourceString,
                                      v6,
                                      46,
                                      94) >= 0 )
                          {
                            ProcessHeap = GetProcessHeap();
                            v28 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, dwBytes);
                            if ( v28 )
                            {
                              fnEfsLogTrace1Strings(
                                v27,
                                (unsigned int)EFS_TRACE_START_EVENT,
                                (unsigned int)&sourceString,
                                46,
                                104);
                              v6 = StringCchPrintfW(
                                     v28,
                                     v32,
                                     L"Content-Type: application/json; charset=utf-8\r\n"
                                      "Accept: application/json\r\n"
                                      "Authorization: %s\r\n"
                                      "ocp-adrs-client-name: \"WIP (Windows)\"\r\n"
                                      "ocp-adrs-client-version: %s\r\n"
                                      "client-request-id: %s\r\n"
                                      "return-client-request-id: true\r\n"
                                      "user-agent:\"WIP (Windows)\"",
                                     a1,
                                     v41,
                                     v40);
                              if ( (int)fnEfsLogTrace1String1Dword(
                                          g_hPublisher,
                                          (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                                          (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                                          (unsigned int)&sourceString,
                                          v6,
                                          46,
                                          104) < 0 )
                              {
                                v29 = GetProcessHeap();
                                HeapFree(v29, 0, v28);
                              }
                              else
                              {
                                *a2 = v28;
                              }
                            }
                            else
                            {
                              v6 = -2147024882;
                              fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024882, 46, 97);
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
      else
      {
        v6 = -2147024774;
        fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024774, 46, 43);
      }
    }
  }
  else
  {
    v6 = -2147467261;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147467261, 46, 33);
  }
LABEL_37:
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    v6,
    46,
    113);
  return v6;
}

```

## disassembly

```asm
0x1800cd46c  mov     [rsp-8+arg_10], rbx
0x1800cd471  push    rbp
0x1800cd472  push    rsi
0x1800cd473  push    rdi
0x1800cd474  push    r12
0x1800cd476  push    r13
0x1800cd478  push    r14
0x1800cd47a  push    r15
0x1800cd47c  lea     rbp, [rsp-4D0h]
0x1800cd484  sub     rsp, 5D0h
0x1800cd48b  mov     rax, cs:__security_cookie
0x1800cd492  xor     rax, rsp
0x1800cd495  mov     [rbp+500h+var_40], rax
0x1800cd49c  mov     r15, rdx
0x1800cd49f  mov     r12, rcx
0x1800cd4a2  mov     ebx, 208h
0x1800cd4a7  lea     rcx, [rbp+500h+sz]; void *
0x1800cd4ae  mov     r8d, ebx; Size
0x1800cd4b1  xor     edx, edx; Val
0x1800cd4b3  call    memset_0
0x1800cd4b8  xorps   xmm0, xmm0
0x1800cd4bb  lea     rcx, [rbp+500h+VersionInformation]; void *
0x1800cd4bf  mov     edi, 114h
0x1800cd4c4  xor     esi, esi
0x1800cd4c6  mov     r8d, edi; Size
0x1800cd4c9  mov     [rsp+600h+var_5C0], rsi
0x1800cd4ce  xor     edx, edx; Val
0x1800cd4d0  movups  xmmword ptr [rsp+600h+pguid.Data1], xmm0
0x1800cd4d5  call    memset_0
0x1800cd4da  mov     r8d, ebx; Size
0x1800cd4dd  lea     rcx, [rbp+500h+var_250]; void *
0x1800cd4e4  xor     edx, edx; Val
0x1800cd4e6  call    memset_0
0x1800cd4eb  lea     r13d, [rsi+2Eh]
0x1800cd4ef  mov     [rsp+600h+var_5A8], rsi
0x1800cd4f4  mov     r9d, r13d
0x1800cd4f7  mov     [rsp+600h+var_5B8], rsi
0x1800cd4fc  lea     r8, sourceString
0x1800cd503  mov     [rsp+600h+var_5B0], rsi
0x1800cd508  lea     rdx, EFS_TRACE_ENTER_EVENT
0x1800cd50f  mov     [rsp+600h+dwBytes], rsi
0x1800cd514  mov     dword ptr [rsp+600h+var_5E0], edi
0x1800cd518  call    fnEfsLogTrace1Strings
0x1800cd51d  test    r15, r15
0x1800cd520  jz      short loc_1800CD527
0x1800cd522  xor     eax, eax
0x1800cd524  mov     [r15], rax
0x1800cd527  test    r12, r12
0x1800cd52a  jnz     short loc_1800CD544
0x1800cd52c  mov     ebx, 80070057h
0x1800cd531  mov     dword ptr [rsp+600h+var_5E0], 120h
0x1800cd539  mov     r8d, 80070057h
0x1800cd53f  jmp     loc_1800CDB64
0x1800cd544  mov     r9d, r13d
0x1800cd547  test    r15, r15
0x1800cd54a  jnz     short loc_1800CD564
0x1800cd54c  mov     ebx, 80004003h
0x1800cd551  mov     dword ptr [rsp+600h+var_5E0], 121h
0x1800cd559  mov     r8d, 80004003h
0x1800cd55f  jmp     loc_1800CDB67
0x1800cd564  mov     edi, 127h
0x1800cd569  lea     r8, sourceString
0x1800cd570  lea     rdx, EFS_TRACE_START_EVENT
0x1800cd577  mov     dword ptr [rsp+600h+var_5E0], edi
0x1800cd57b  call    fnEfsLogTrace1Strings
0x1800cd580  lea     rcx, [rsp+600h+pguid]; pguid
0x1800cd585  call    cs:__imp_CoCreateGuid
0x1800cd58b  mov     rcx, cs:g_hPublisher
0x1800cd592  lea     r14, sourceString
0x1800cd599  mov     [rsp+600h+var_5D0], edi
0x1800cd59d  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800cd5a4  mov     r9, r14
0x1800cd5a7  mov     dword ptr [rsp+600h+var_5D8], r13d
0x1800cd5ac  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800cd5b3  mov     dword ptr [rsp+600h+var_5E0], eax
0x1800cd5b7  mov     ebx, eax
0x1800cd5b9  call    fnEfsLogTrace1String1Dword
0x1800cd5be  test    eax, eax
0x1800cd5c0  js      loc_1800CDB7A
0x1800cd5c6  lea     r8d, [rdi-23h]; cchMax
0x1800cd5ca  lea     rdx, [rbp+500h+sz]; lpsz
0x1800cd5d1  lea     rcx, [rsp+600h+pguid]; rguid
0x1800cd5d6  call    cs:__imp_StringFromGUID2
0x1800cd5dc  mov     r9d, r13d
0x1800cd5df  test    eax, eax
0x1800cd5e1  jnz     short loc_1800CD5FB
0x1800cd5e3  mov     ebx, 8007007Ah
0x1800cd5e8  mov     dword ptr [rsp+600h+var_5E0], 12Bh
0x1800cd5f0  mov     r8d, 8007007Ah
0x1800cd5f6  jmp     loc_1800CDB67
0x1800cd5fb  mov     edi, 130h
0x1800cd600  lea     rdx, EFS_TRACE_START_EVENT
0x1800cd607  mov     r8, r14
0x1800cd60a  mov     dword ptr [rsp+600h+var_5E0], edi
0x1800cd60e  call    fnEfsLogTrace1Strings
0x1800cd613  lea     r8, [rsp+600h+var_5C0]; unsigned __int64 *
0x1800cd618  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800cd61d  lea     rcx, [rbp+500h+sz]; unsigned __int16 *
0x1800cd624  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800cd629  mov     rcx, cs:g_hPublisher
0x1800cd630  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800cd637  mov     [rsp+600h+var_5D0], edi
0x1800cd63b  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800cd642  mov     dword ptr [rsp+600h+var_5D8], r13d
0x1800cd647  mov     r9, r14
0x1800cd64a  mov     dword ptr [rsp+600h+var_5E0], eax
0x1800cd64e  mov     ebx, eax
0x1800cd650  call    fnEfsLogTrace1String1Dword
0x1800cd655  test    eax, eax
0x1800cd657  js      loc_1800CDB7A
0x1800cd65d  mov     r14, [rsp+600h+var_5C0]
0x1800cd662  lea     rax, [r14-2]
0x1800cd666  cmp     rax, 102h
0x1800cd66c  ja      loc_1800CDB51
0x1800cd672  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[r14*2]
0x1800cd67a  cmp     rcx, 208h
0x1800cd681  jnb     loc_1800CDB4B
0x1800cd687  mov     [rbp+rcx+500h+sz], si
0x1800cd68f  sub     r14, 2
0x1800cd693  lea     rcx, [rbp+500h+VersionInformation]; lpVersionInformation
0x1800cd697  mov     [rbp+500h+VersionInformation.dwOSVersionInfoSize], 114h
0x1800cd69e  call    cs:__imp_GetVersionExW
0x1800cd6a4  mov     edi, 145h
0x1800cd6a9  lea     r8, sourceString
0x1800cd6b0  mov     r9d, r13d
0x1800cd6b3  mov     dword ptr [rsp+600h+var_5E0], edi
0x1800cd6b7  lea     rdx, EFS_TRACE_START_EVENT
0x1800cd6be  call    fnEfsLogTrace1Strings
0x1800cd6c3  mov     r9d, [rbp+500h+VersionInformation.dwBuildNumber]
0x1800cd6c7  lea     r8, aD; "%d"
0x1800cd6ce  lea     edx, [rdi-41h]; unsigned __int64
0x1800cd6d1  lea     rcx, [rbp+500h+var_250]; unsigned __int16 *
0x1800cd6d8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800cd6dd  mov     rcx, cs:g_hPublisher
0x1800cd6e4  lea     r9, sourceString
0x1800cd6eb  mov     [rsp+600h+var_5D0], edi
0x1800cd6ef  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800cd6f6  mov     dword ptr [rsp+600h+var_5D8], r13d
0x1800cd6fb  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800cd702  mov     dword ptr [rsp+600h+var_5E0], eax
0x1800cd706  mov     ebx, eax
0x1800cd708  call    fnEfsLogTrace1String1Dword
0x1800cd70d  test    eax, eax
0x1800cd70f  js      loc_1800CDB7A
0x1800cd715  mov     edi, 149h
0x1800cd71a  lea     r8, sourceString
0x1800cd721  mov     r9d, r13d
0x1800cd724  mov     dword ptr [rsp+600h+var_5E0], edi
0x1800cd728  lea     rdx, EFS_TRACE_START_EVENT
0x1800cd72f  call    fnEfsLogTrace1Strings
0x1800cd734  lea     r8, [rsp+600h+var_5A8]; unsigned __int64 *
0x1800cd739  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800cd73e  lea     rcx, [rbp+500h+var_250]; unsigned __int16 *
0x1800cd745  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800cd74a  mov     rcx, cs:g_hPublisher
0x1800cd751  lea     r9, sourceString
0x1800cd758  mov     [rsp+600h+var_5D0], edi
0x1800cd75c  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800cd763  mov     dword ptr [rsp+600h+var_5D8], r13d
0x1800cd768  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800cd76f  mov     dword ptr [rsp+600h+var_5E0], eax
0x1800cd773  mov     ebx, eax
0x1800cd775  call    fnEfsLogTrace1String1Dword
0x1800cd77a  test    eax, eax
0x1800cd77c  js      loc_1800CDB7A
0x1800cd782  mov     edi, 14Dh
0x1800cd787  lea     r8, sourceString
0x1800cd78e  mov     r9d, r13d
0x1800cd791  mov     dword ptr [rsp+600h+var_5E0], edi
0x1800cd795  lea     rdx, EFS_TRACE_START_EVENT
0x1800cd79c  call    fnEfsLogTrace1Strings
0x1800cd7a1  lea     r8, [rsp+600h+var_5B8]; unsigned __int64 *
0x1800cd7a6  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800cd7ab  mov     rcx, r12; unsigned __int16 *
0x1800cd7ae  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800cd7b3  mov     rcx, cs:g_hPublisher
0x1800cd7ba  lea     r9, sourceString
0x1800cd7c1  mov     [rsp+600h+var_5D0], edi
0x1800cd7c5  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800cd7cc  mov     dword ptr [rsp+600h+var_5D8], r13d
0x1800cd7d1  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800cd7d8  mov     dword ptr [rsp+600h+var_5E0], eax
0x1800cd7dc  mov     ebx, eax
0x1800cd7de  call    fnEfsLogTrace1String1Dword
0x1800cd7e3  test    eax, eax
0x1800cd7e5  js      loc_1800CDB7A
0x1800cd7eb  mov     edi, 151h
0x1800cd7f0  lea     r8, sourceString
0x1800cd7f7  mov     r9d, r13d
0x1800cd7fa  mov     dword ptr [rsp+600h+var_5E0], edi
0x1800cd7fe  lea     rdx, EFS_TRACE_START_EVENT
0x1800cd805  call    fnEfsLogTrace1Strings
0x1800cd80a  lea     r8, [rsp+600h+var_5B0]; unsigned __int64 *
0x1800cd80f  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800cd814  lea     rcx, aContentTypeApp; "Content-Type: application/json; charset"...
0x1800cd81b  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800cd820  mov     rcx, cs:g_hPublisher
0x1800cd827  lea     r9, sourceString
0x1800cd82e  mov     [rsp+600h+var_5D0], edi
0x1800cd832  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800cd839  mov     dword ptr [rsp+600h+var_5D8], r13d
0x1800cd83e  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800cd845  mov     dword ptr [rsp+600h+var_5E0], eax
0x1800cd849  mov     ebx, eax
0x1800cd84b  call    fnEfsLogTrace1String1Dword
0x1800cd850  test    eax, eax
0x1800cd852  js      loc_1800CDB7A
0x1800cd858  mov     r9d, r13d
0x1800cd85b  mov     dword ptr [rsp+600h+var_5E0], 153h
0x1800cd863  lea     r8, sourceString
0x1800cd86a  lea     rdx, EFS_TRACE_START_EVENT
0x1800cd871  call    fnEfsLogTrace1Strings
0x1800cd876  mov     rdi, [rsp+600h+var_5B0]
0x1800cd87b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800cd87f  add     rdi, [rsp+600h+var_5B8]
0x1800cd884  cmp     rdi, [rsp+600h+var_5B8]
0x1800cd889  jb      short loc_1800CD88F
0x1800cd88b  xor     ebx, ebx
0x1800cd88d  jmp     short loc_1800CD897
0x1800cd88f  mov     ebx, 80070216h
0x1800cd894  mov     rdi, rsi
0x1800cd897  mov     rcx, cs:g_hPublisher
0x1800cd89e  lea     r9, sourceString
0x1800cd8a5  mov     [rsp+600h+var_5D0], 153h
0x1800cd8ad  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800cd8b4  mov     dword ptr [rsp+600h+var_5D8], r13d
0x1800cd8b9  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800cd8c0  mov     dword ptr [rsp+600h+var_5E0], ebx
0x1800cd8c4  call    fnEfsLogTrace1String1Dword
0x1800cd8c9  test    eax, eax
0x1800cd8cb  js      loc_1800CDB7A
0x1800cd8d1  mov     r13d, 154h
0x1800cd8d7  lea     r8, sourceString
0x1800cd8de  mov     r9d, 2Eh ; '.'
0x1800cd8e4  mov     dword ptr [rsp+600h+var_5E0], r13d
0x1800cd8e9  lea     rdx, EFS_TRACE_START_EVENT
0x1800cd8f0  call    fnEfsLogTrace1Strings
0x1800cd8f5  mov     rcx, cs:g_hPublisher
0x1800cd8fc  lea     rax, [rdi+r14]
0x1800cd900  cmp     rax, rdi
0x1800cd903  mov     [rsp+600h+var_5D0], r13d
0x1800cd908  mov     r14, rsi
0x1800cd90b  lea     r9, sourceString
0x1800cd912  cmovnb  r14, rax
0x1800cd916  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800cd91d  sbb     ebx, ebx
0x1800cd91f  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800cd926  mov     r13d, 2Eh ; '.'
0x1800cd92c  and     ebx, 80070216h
0x1800cd932  mov     dword ptr [rsp+600h+var_5D8], r13d
0x1800cd937  mov     dword ptr [rsp+600h+var_5E0], ebx
0x1800cd93b  call    fnEfsLogTrace1String1Dword
0x1800cd940  test    eax, eax
0x1800cd942  js      loc_1800CDB7A
0x1800cd948  mov     edi, 155h
0x1800cd94d  lea     r8, sourceString
0x1800cd954  mov     r9d, r13d
0x1800cd957  mov     dword ptr [rsp+600h+var_5E0], edi
0x1800cd95b  lea     rdx, EFS_TRACE_START_EVENT
0x1800cd962  call    fnEfsLogTrace1Strings
0x1800cd967  mov     rcx, [rsp+600h+var_5A8]
0x1800cd96c  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800cd973  add     rcx, r14
0x1800cd976  mov     [rsp+600h+var_5D0], edi
0x1800cd97a  cmp     rcx, r14
0x1800cd97d  mov     dword ptr [rsp+600h+var_5D8], r13d
0x1800cd982  lea     r14, sourceString
0x1800cd989  cmovnb  rsi, rcx
0x1800cd98d  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800cd994  mov     rcx, cs:g_hPublisher
0x1800cd99b  sbb     ebx, ebx
0x1800cd99d  and     ebx, 80070216h
0x1800cd9a3  mov     [rsp+600h+var_5C0], rsi
0x1800cd9a8  mov     r9, r14
0x1800cd9ab  mov     dword ptr [rsp+600h+var_5E0], ebx
0x1800cd9af  call    fnEfsLogTrace1String1Dword
0x1800cd9b4  test    eax, eax
0x1800cd9b6  js      loc_1800CDB7A
0x1800cd9bc  mov     edi, 15Ch
0x1800cd9c1  lea     rdx, EFS_TRACE_START_EVENT
0x1800cd9c8  mov     r9d, r13d
0x1800cd9cb  mov     dword ptr [rsp+600h+var_5E0], edi
0x1800cd9cf  mov     r8, r14
0x1800cd9d2  call    fnEfsLogTrace1Strings
0x1800cd9d7  lea     r8, [rsp+600h+var_5C0]; unsigned __int64 *
0x1800cd9dc  mov     rcx, rsi; unsigned __int64
0x1800cd9df  lea     edx, [r13-29h]; unsigned __int64
0x1800cd9e3  call    ?ULongLongSub@@YAJ_K0PEA_K@Z; ULongLongSub(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800cd9e8  mov     rcx, cs:g_hPublisher
0x1800cd9ef  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800cd9f6  mov     [rsp+600h+var_5D0], edi
0x1800cd9fa  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800cda01  mov     dword ptr [rsp+600h+var_5D8], r13d
0x1800cda06  mov     r9, r14
0x1800cda09  mov     dword ptr [rsp+600h+var_5E0], eax
0x1800cda0d  mov     ebx, eax
0x1800cda0f  call    fnEfsLogTrace1String1Dword
0x1800cda14  test    eax, eax
0x1800cda16  js      loc_1800CDB7A
0x1800cda1c  mov     edi, 15Eh
  ... truncated ...
```
