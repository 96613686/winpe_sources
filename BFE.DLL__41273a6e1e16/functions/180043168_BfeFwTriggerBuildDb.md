# BfeFwTriggerBuildDb

- ea: `0x180043168`
- end: `0x1800435cb`
- name: `BfeFwTriggerBuildDb`
- size: `1123`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180042eec`

## callees

- `0x180004798`
- `0x18000e7e0`
- `0x180012d8c`
- `0x1800135ac`
- `0x1800197d0`
- `0x180024e40`
- `0x180039b64`
- `0x180043168`
- `0x180045b18`
- `0x18004a3f8`
- `0x18005aa60`
- `0x1800671cc`
- `0x1800674d0`
- `0x18008ad6c`

## import_xrefs

- `ntdll!TpAllocTimer` at `0x180043392`
- `ntdll!TpAllocTimer` at `0x180043392`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800431c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004329b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800431c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004329b`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800431b5`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800431b5`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004356d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004356d`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x180043242`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x18004328b`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x180043242`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x18004328b`

## string_xrefs

- `0x180043215`: `OpenServiceW`
- `0x1800432aa`: `QueryServiceConfig2W`

## pseudocode

```c
__int64 __fastcall BfeFwTriggerBuildDb(SC_HANDLE a1, const WCHAR **a2)
{
  const WCHAR *v3; // rdx
  __int64 inited; // rbx
  SC_HANDLE v5; // r13
  int v6; // edx
  DWORD v7; // edi
  int v8; // r8d
  void *v9; // rcx
  DWORD v10; // edi
  LPBYTE v11; // rsi
  DWORD LastError; // eax
  __int64 v13; // rcx
  __int64 v14; // rax
  unsigned int v15; // r12d
  __int64 v16; // r15
  __int64 v17; // r14
  __int64 *v18; // rdi
  unsigned int v19; // eax
  __int64 v20; // r8
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rdi
  int v26; // ebx
  _QWORD *v27; // rcx
  size_t v28; // rdx
  BOOL v29; // eax
  const wchar_t *v30; // rax
  _OWORD *v31; // rcx
  void *v32; // rbx
  __int128 v33; // xmm0
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rcx
  __int64 *v37; // rax
  __int64 v38; // rcx
  unsigned int v40; // [rsp+30h] [rbp-39h]
  __int64 v41; // [rsp+38h] [rbp-31h] BYREF
  LPBYTE lpBuffer; // [rsp+40h] [rbp-29h]
  BOOL IsServiceDependOnBfe; // [rsp+48h] [rbp-21h]
  __int64 *v44; // [rsp+50h] [rbp-19h]
  size_t Size; // [rsp+58h] [rbp-11h]
  __int64 v46; // [rsp+60h] [rbp-9h]
  __int64 v47; // [rsp+68h] [rbp-1h]
  __int64 v48; // [rsp+70h] [rbp+7h]
  SC_HANDLE v49; // [rsp+78h] [rbp+Fh]
  DWORD cbBufSize; // [rsp+80h] [rbp+17h] BYREF

  v44 = (__int64 *)a2;
  v49 = a1;
  v3 = *a2;
  inited = 0;
  lpBuffer = 0;
  cbBufSize = 0;
  v5 = OpenServiceW(a1, v3, 1u);
  if ( v5 )
  {
    QueryServiceConfig2W(v5, 8u, 0, 0, &cbBufSize);
    v10 = cbBufSize;
    if ( cbBufSize )
    {
      v11 = lpBuffer;
      inited = WfpMemAlloc(cbBufSize, 0);
      if ( !inited )
      {
        if ( QueryServiceConfig2W(v5, 8u, lpBuffer, v10, &cbBufSize) )
        {
          v15 = 0;
          if ( *(_DWORD *)lpBuffer )
          {
            while ( 1 )
            {
              v16 = *((_QWORD *)v11 + 1);
              v17 = 32LL * v15;
              if ( *(_DWORD *)(v17 + v16) == 4 )
              {
                v18 = v44;
                IsServiceDependOnBfe = BfeFwTriggerIsServiceDependOnBfe(v49, *v44);
                v19 = 0;
                v40 = 0;
                if ( *(_DWORD *)(v17 + v16 + 16) )
                  break;
              }
LABEL_34:
              if ( ++v15 >= *(_DWORD *)v11 )
                goto LABEL_40;
            }
            while ( 1 )
            {
              v20 = *(_QWORD *)(v17 + v16 + 24);
              v21 = *v18;
              v22 = 16LL * v19;
              v46 = v22;
              v23 = -1;
              v47 = v20;
              do
                ++v23;
              while ( *(_WORD *)(v21 + 2 * v23) );
              v24 = *(unsigned int *)(v22 + v20 + 4) + 226LL;
              Size = 2 * v23 + 2;
              v41 = 0;
              inited = WfpMemAlloc(Size + v24, 0);
              if ( inited )
                break;
              v25 = v41;
              v48 = v41 + 72;
              inited = WfpCriticalSectionCreate(v41 + 72);
              if ( inited )
              {
                WfpMemFree(&v41);
                break;
              }
              v26 = TpAllocTimer(v25 + 56, BfeFwTriggerEntryTimer, v25, 0);
              if ( v26 < 0 )
              {
                WfpCriticalSectionDestroy(v48);
                WfpMemFree(&v41);
                v14 = WfpReportSysErrorAsNtStatus(v38, "TpAllocTimer", (unsigned int)v26);
                goto LABEL_12;
              }
              v27 = *(_QWORD **)(v17 + v16 + 8);
              if ( *v27 == *(_QWORD *)&FIREWALL_PORT_OPEN_GUID.Data1
                && v27[1] == *(_QWORD *)FIREWALL_PORT_OPEN_GUID.Data4 )
              {
                *(_DWORD *)(v25 + 28) = 0;
              }
              else
              {
                if ( *v27 != *(_QWORD *)&FIREWALL_PORT_CLOSE_GUID.Data1
                  || v27[1] != *(_QWORD *)FIREWALL_PORT_CLOSE_GUID.Data4 )
                {
                  __fastfail(5u);
                }
                *(_DWORD *)(v25 + 28) = 1;
              }
              memcpy_0((void *)(v25 + 152), (const void *)*v44, Size);
              v28 = Size;
              v29 = IsServiceDependOnBfe;
              *(_QWORD *)(v25 + 16) = v25 + 152;
              *(_DWORD *)(v25 + 24) = v29;
              v30 = L"b7569e07-8421-4ee0-ad10-86915afdad09";
              v31 = (_OWORD *)(v25 + v28 + 152);
              if ( *(_DWORD *)(v25 + 28) )
                v30 = L"a144ed38-8e12-4de4-9d96-e64740b1a524";
              v32 = (void *)(v25 + v28 + 226);
              *v31 = *(_OWORD *)v30;
              v31[1] = *((_OWORD *)v30 + 1);
              v31[2] = *((_OWORD *)v30 + 2);
              v31[3] = *((_OWORD *)v30 + 3);
              v33 = *(_OWORD *)(v30 + 29);
              v34 = v46;
              *(_OWORD *)((char *)v31 + 58) = v33;
              *(_QWORD *)(v25 + 32) = v31;
              memcpy_0(v32, *(const void **)(v34 + v47 + 8), *(unsigned int *)(v34 + v47 + 4));
              v35 = v46;
              v36 = v47;
              *(_QWORD *)(v25 + 40) = v32;
              *(_DWORD *)(v25 + 48) = *(_DWORD *)(v35 + v36 + 4);
              *(_DWORD *)(v25 + 52) = 0;
              *(_QWORD *)(v25 + 64) = 0;
              inited = BfeFwTriggerEntryInitParams(v25);
              if ( inited )
              {
                WfpCriticalSectionDestroy(v48);
                WfpMemFree(&v41);
              }
              else
              {
                *(_DWORD *)(v25 + 144) = 8;
                *(_DWORD *)(v25 + 148) = 8;
                v37 = (__int64 *)qword_1800F60C8;
                if ( *(__int64 **)qword_1800F60C8 != &gBfeFwTriggers )
                  __fastfail(3u);
                *(_QWORD *)v25 = &gBfeFwTriggers;
                *(_QWORD *)(v25 + 8) = v37;
                *v37 = v25;
                qword_1800F60C8 = v25;
              }
              v18 = v44;
              v19 = v40 + 1;
              v40 = v19;
              if ( v19 >= *(_DWORD *)(v17 + v16 + 16) )
                goto LABEL_34;
            }
          }
        }
        else
        {
          LastError = GetLastError();
          v14 = WfpReportSysErrorAsWinError(v13, "QueryServiceConfig2W", LastError);
LABEL_12:
          inited = v14;
        }
      }
    }
LABEL_40:
    CloseServiceHandle(v5);
    goto LABEL_41;
  }
  v7 = GetLastError();
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, v8, (unsigned int)*a2, v7);
  }
  if ( v7 == 14 )
  {
    inited = WfpReportSysErrorAsWinError(v9, "OpenServiceW", 14);
LABEL_41:
    if ( inited )
    {
      BfeFwTriggerFreeDb();
      WfpReportError(inited, "BfeFwTriggerBuildDb");
    }
  }
  return inited;
}

```

## disassembly

```asm
0x180043168  mov     [rsp-8+arg_10], rbx
0x18004316d  push    rbp
0x18004316e  push    rsi
0x18004316f  push    rdi
0x180043170  push    r12
0x180043172  push    r13
0x180043174  push    r14
0x180043176  push    r15
0x180043178  lea     rbp, [rsp-27h]
0x18004317d  sub     rsp, 90h
0x180043184  mov     rax, cs:__security_cookie
0x18004318b  xor     rax, rsp
0x18004318e  mov     [rbp+57h+var_38], rax
0x180043192  xor     r15d, r15d
0x180043195  mov     [rbp+57h+var_70], rdx
0x180043199  mov     r14, rdx
0x18004319c  mov     [rbp+57h+var_48], rcx
0x1800431a0  mov     rdx, [rdx]; lpServiceName
0x1800431a3  mov     ebx, r15d
0x1800431a6  mov     esi, r15d
0x1800431a9  mov     [rbp+57h+lpBuffer], r15
0x1800431ad  lea     r8d, [r15+1]; dwDesiredAccess
0x1800431b1  mov     [rbp+57h+cbBufSize], r15d
0x1800431b5  call    cs:__imp_OpenServiceW
0x1800431bc  nop     dword ptr [rax+rax+00h]
0x1800431c1  mov     r13, rax
0x1800431c4  test    rax, rax
0x1800431c7  jnz     short loc_180043229
0x1800431c9  call    cs:__imp_GetLastError
0x1800431d0  nop     dword ptr [rax+rax+00h]
0x1800431d5  mov     edi, eax
0x1800431d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800431de  lea     rax, WPP_GLOBAL_Control
0x1800431e5  cmp     rcx, rax
0x1800431e8  jz      short loc_180043206
0x1800431ea  cmp     byte ptr [rcx+19h], 4
0x1800431ee  jb      short loc_180043206
0x1800431f0  test    byte ptr [rcx+1Ch], 2
0x1800431f4  jz      short loc_180043206
0x1800431f6  mov     r9, [r14]
0x1800431f9  mov     rcx, [rcx+10h]
0x1800431fd  mov     dword ptr [rsp+0C0h+pcbBytesNeeded], edi
0x180043201  call    WPP_SF_Sd
0x180043206  mov     r8d, 0Eh
0x18004320c  cmp     edi, r8d
0x18004320f  jnz     loc_1800435A0
0x180043215  lea     rdx, aOpenservicew_0; "OpenServiceW"
0x18004321c  call    WfpReportSysErrorAsWinError
0x180043221  mov     rbx, rax
0x180043224  jmp     loc_180043587
0x180043229  xor     r9d, r9d; cbBufSize
0x18004322c  lea     rax, [rbp+57h+cbBufSize]
0x180043230  xor     r8d, r8d; lpBuffer
0x180043233  mov     [rsp+0C0h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180043238  mov     rcx, r13; hService
0x18004323b  lea     r14d, [r9+8]
0x18004323f  mov     edx, r14d; dwInfoLevel
0x180043242  call    cs:__imp_QueryServiceConfig2W
0x180043249  nop     dword ptr [rax+rax+00h]
0x18004324e  mov     edi, [rbp+57h+cbBufSize]
0x180043251  test    edi, edi
0x180043253  jz      loc_18004356A
0x180043259  mov     ecx, edi; dwBytes
0x18004325b  lea     r8, [rbp+57h+lpBuffer]
0x18004325f  xor     edx, edx; dwFlags
0x180043261  call    WfpMemAlloc
0x180043266  mov     rsi, [rbp+57h+lpBuffer]
0x18004326a  mov     rbx, rax
0x18004326d  test    rax, rax
0x180043270  jnz     loc_18004356A
0x180043276  lea     rax, [rbp+57h+cbBufSize]
0x18004327a  mov     r9d, edi; cbBufSize
0x18004327d  mov     r8, rsi; lpBuffer
0x180043280  mov     [rsp+0C0h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180043285  mov     edx, r14d; dwInfoLevel
0x180043288  mov     rcx, r13; hService
0x18004328b  call    cs:__imp_QueryServiceConfig2W
0x180043292  nop     dword ptr [rax+rax+00h]
0x180043297  test    eax, eax
0x180043299  jnz     short loc_1800432BE
0x18004329b  call    cs:__imp_GetLastError
0x1800432a2  nop     dword ptr [rax+rax+00h]
0x1800432a7  mov     r8d, eax
0x1800432aa  lea     rdx, aQueryserviceco_1; "QueryServiceConfig2W"
0x1800432b1  call    WfpReportSysErrorAsWinError
0x1800432b6  mov     rbx, rax
0x1800432b9  jmp     loc_18004356A
0x1800432be  mov     r12d, r15d
0x1800432c1  cmp     [rsi], r15d
0x1800432c4  jbe     loc_18004356A
0x1800432ca  mov     r15, [rsi+8]
0x1800432ce  mov     r14d, r12d
0x1800432d1  shl     r14, 5
0x1800432d5  cmp     dword ptr [r14+r15], 4
0x1800432da  jnz     loc_18004351F
0x1800432e0  mov     rdi, [rbp+57h+var_70]
0x1800432e4  mov     rcx, [rbp+57h+var_48]
0x1800432e8  mov     rdx, [rdi]
0x1800432eb  call    BfeFwTriggerIsServiceDependOnBfe
0x1800432f0  xor     r9d, r9d
0x1800432f3  mov     [rbp+57h+var_78], eax
0x1800432f6  mov     eax, r9d
0x1800432f9  mov     [rbp+57h+var_90], eax
0x1800432fc  cmp     [r14+r15+10h], r9d
0x180043301  jbe     loc_18004351F
0x180043307  mov     r8, [r14+r15+18h]
0x18004330c  mov     rdx, [rdi]
0x18004330f  mov     ecx, eax
0x180043311  shl     rcx, 4
0x180043315  mov     [rbp+57h+var_60], rcx
0x180043319  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004331d  mov     [rbp+57h+var_58], r8
0x180043321  inc     rax
0x180043324  cmp     [rdx+rax*2], r9w
0x180043329  jnz     short loc_180043321
0x18004332b  mov     ecx, [rcx+r8+4]
0x180043330  lea     rdx, ds:2[rax*2]
0x180043338  add     rcx, 0E2h
0x18004333f  mov     [rbp+57h+Size], rdx
0x180043343  add     rcx, rdx; dwBytes
0x180043346  mov     [rbp+57h+var_88], r9
0x18004334a  xor     edx, edx; dwFlags
0x18004334c  lea     r8, [rbp+57h+var_88]
0x180043350  call    WfpMemAlloc
0x180043355  mov     rbx, rax
0x180043358  test    rax, rax
0x18004335b  jnz     loc_18004356A
0x180043361  mov     rdi, [rbp+57h+var_88]
0x180043365  lea     rax, [rdi+48h]
0x180043369  mov     rcx, rax
0x18004336c  mov     [rbp+57h+var_50], rax
0x180043370  call    WfpCriticalSectionCreate
0x180043375  mov     rbx, rax
0x180043378  test    rax, rax
0x18004337b  jnz     loc_180043561
0x180043381  lea     rcx, [rdi+38h]
0x180043385  xor     r9d, r9d
0x180043388  mov     r8, rdi
0x18004338b  lea     rdx, BfeFwTriggerEntryTimer
0x180043392  call    cs:__imp_TpAllocTimer
0x180043399  nop     dword ptr [rax+rax+00h]
0x18004339e  mov     ebx, eax
0x1800433a0  test    eax, eax
0x1800433a2  js      loc_18004353B
0x1800433a8  mov     rcx, [r14+r15+8]
0x1800433ad  mov     rax, [rcx]
0x1800433b0  cmp     rax, qword ptr cs:FIREWALL_PORT_OPEN_GUID.Data1
0x1800433b7  jnz     short loc_1800433CF
0x1800433b9  mov     rax, [rcx+8]
0x1800433bd  cmp     rax, qword ptr cs:FIREWALL_PORT_OPEN_GUID.Data4
0x1800433c4  jnz     short loc_1800433CF
0x1800433c6  mov     dword ptr [rdi+1Ch], 0
0x1800433cd  jmp     short loc_1800433F7
0x1800433cf  mov     rax, [rcx]
0x1800433d2  cmp     rax, qword ptr cs:FIREWALL_PORT_CLOSE_GUID.Data1
0x1800433d9  jnz     loc_180043534
0x1800433df  mov     rax, [rcx+8]
0x1800433e3  cmp     rax, qword ptr cs:FIREWALL_PORT_CLOSE_GUID.Data4
0x1800433ea  jnz     loc_180043534
0x1800433f0  mov     dword ptr [rdi+1Ch], 1
0x1800433f7  mov     rdx, [rbp+57h+var_70]
0x1800433fb  lea     rbx, [rdi+98h]
0x180043402  mov     r8, [rbp+57h+Size]; Size
0x180043406  mov     rcx, rbx; void *
0x180043409  mov     rdx, [rdx]; Src
0x18004340c  call    memcpy_0
0x180043411  mov     rdx, [rbp+57h+Size]
0x180043415  lea     r8, aA144ed388e124d; "a144ed38-8e12-4de4-9d96-e64740b1a524"
0x18004341c  mov     eax, [rbp+57h+var_78]
0x18004341f  mov     [rdi+10h], rbx
0x180043423  mov     [rdi+18h], eax
0x180043426  lea     rax, aB7569e0784214e; "b7569e07-8421-4ee0-ad10-86915afdad09"
0x18004342d  lea     rcx, [rdx+98h]
0x180043434  add     rcx, rdi
0x180043437  lea     rbx, [rdx+0E2h]
0x18004343e  cmp     dword ptr [rdi+1Ch], 0
0x180043442  cmovnz  rax, r8
0x180043446  add     rbx, rdi
0x180043449  movups  xmm0, xmmword ptr [rax]
0x18004344c  movups  xmmword ptr [rcx], xmm0
0x18004344f  movups  xmm1, xmmword ptr [rax+10h]
0x180043453  movups  xmmword ptr [rcx+10h], xmm1
0x180043457  movups  xmm0, xmmword ptr [rax+20h]
0x18004345b  movups  xmmword ptr [rcx+20h], xmm0
0x18004345f  movups  xmm1, xmmword ptr [rax+30h]
0x180043463  movups  xmmword ptr [rcx+30h], xmm1
0x180043467  movups  xmm0, xmmword ptr [rax+3Ah]
0x18004346b  mov     rax, [rbp+57h+var_60]
0x18004346f  movups  xmmword ptr [rcx+3Ah], xmm0
0x180043473  mov     [rdi+20h], rcx
0x180043477  mov     rcx, [rbp+57h+var_58]
0x18004347b  mov     r8d, [rax+rcx+4]; Size
0x180043480  mov     rdx, [rax+rcx+8]; Src
0x180043485  mov     rcx, rbx; void *
0x180043488  call    memcpy_0
0x18004348d  mov     rax, [rbp+57h+var_60]
0x180043491  mov     rcx, [rbp+57h+var_58]
0x180043495  mov     [rdi+28h], rbx
0x180043499  mov     eax, [rax+rcx+4]
0x18004349d  mov     rcx, rdi
0x1800434a0  mov     [rdi+30h], eax
0x1800434a3  xor     eax, eax
0x1800434a5  mov     [rdi+34h], eax
0x1800434a8  mov     [rdi+40h], rax
0x1800434ac  call    BfeFwTriggerEntryInitParams
0x1800434b1  xor     r9d, r9d
0x1800434b4  mov     rbx, rax
0x1800434b7  test    rax, rax
0x1800434ba  jz      short loc_1800434D3
0x1800434bc  mov     rcx, [rbp+57h+var_50]
0x1800434c0  call    WfpCriticalSectionDestroy
0x1800434c5  lea     rcx, [rbp+57h+var_88]
0x1800434c9  call    WfpMemFree
0x1800434ce  xor     r9d, r9d
0x1800434d1  jmp     short loc_180043508
0x1800434d3  mov     eax, 8
0x1800434d8  lea     rcx, gBfeFwTriggers
0x1800434df  mov     [rdi+90h], eax
0x1800434e5  mov     [rdi+94h], eax
0x1800434eb  mov     rax, cs:qword_1800F60C8
0x1800434f2  cmp     [rax], rcx
0x1800434f5  jnz     short loc_18004352D
0x1800434f7  mov     [rdi], rcx
0x1800434fa  mov     [rdi+8], rax
0x1800434fe  mov     [rax], rdi
0x180043501  mov     cs:qword_1800F60C8, rdi
0x180043508  mov     eax, [rbp+57h+var_90]
0x18004350b  mov     rdi, [rbp+57h+var_70]
0x18004350f  inc     eax
0x180043511  mov     [rbp+57h+var_90], eax
0x180043514  cmp     eax, [r14+r15+10h]
0x180043519  jb      loc_180043307
0x18004351f  inc     r12d
0x180043522  cmp     r12d, [rsi]
0x180043525  jb      loc_1800432CA
0x18004352b  jmp     short loc_18004356A
0x18004352d  mov     ecx, 3
0x180043532  int     29h; Win8: RtlFailFast(ecx)
0x180043534  mov     ecx, 5
0x180043539  int     29h; Win8: RtlFailFast(ecx)
0x18004353b  mov     rcx, [rbp+57h+var_50]
0x18004353f  call    WfpCriticalSectionDestroy
0x180043544  lea     rcx, [rbp+57h+var_88]
0x180043548  call    WfpMemFree
0x18004354d  mov     r8d, ebx
0x180043550  lea     rdx, aTpalloctimer; "TpAllocTimer"
0x180043557  call    WfpReportSysErrorAsNtStatus
0x18004355c  jmp     loc_1800432B6
0x180043561  lea     rcx, [rbp+57h+var_88]
0x180043565  call    WfpMemFree
0x18004356a  mov     rcx, r13; hSCObject
0x18004356d  call    cs:__imp_CloseServiceHandle
0x180043574  nop     dword ptr [rax+rax+00h]
0x180043579  test    rsi, rsi
0x18004357c  jz      short loc_180043587
0x18004357e  lea     rcx, [rbp+57h+lpBuffer]
0x180043582  call    WfpMemFree
0x180043587  test    rbx, rbx
0x18004358a  jz      short loc_1800435A0
0x18004358c  call    BfeFwTriggerFreeDb
0x180043591  lea     rdx, aBfefwtriggerbu; "BfeFwTriggerBuildDb"
0x180043598  mov     rcx, rbx
0x18004359b  call    WfpReportError
0x1800435a0  mov     rax, rbx
0x1800435a3  mov     rcx, [rbp+57h+var_38]
0x1800435a7  xor     rcx, rsp; StackCookie
0x1800435aa  call    __security_check_cookie
0x1800435af  mov     rbx, [rsp+0C0h+arg_10]
0x1800435b7  add     rsp, 90h
0x1800435be  pop     r15
0x1800435c0  pop     r14
0x1800435c2  pop     r13
0x1800435c4  pop     r12
0x1800435c6  pop     rdi
0x1800435c7  pop     rsi
0x1800435c8  pop     rbp
0x1800435c9  retn
```
