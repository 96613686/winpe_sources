# BfeFwTriggerBuildDb

- ea: `0x180041ee0`
- end: `0x180042318`
- name: `BfeFwTriggerBuildDb`
- size: `1080`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180041ca0`

## callees

- `0x18000474c`
- `0x18000e000`
- `0x18001236c`
- `0x180012b54`
- `0x180018b74`
- `0x180022730`
- `0x18003b440`
- `0x180041ee0`
- `0x180043b5c`
- `0x180048448`
- `0x180058b30`
- `0x180064e00`
- `0x1800650a8`
- `0x180087dcc`

## import_xrefs

- `ntdll!TpAllocTimer` at `0x1800420ec`
- `ntdll!TpAllocTimer` at `0x1800420ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041f3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041ffb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041f3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041ffb`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180041f2d`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180041f2d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800422c1`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800422c1`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x180041fae`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x180041ff1`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x180041fae`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x180041ff1`

## string_xrefs

- `0x180041f81`: `OpenServiceW`
- `0x180042004`: `QueryServiceConfig2W`

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
                v37 = (__int64 *)qword_1800F30A8;
                if ( *(__int64 **)qword_1800F30A8 != &gBfeFwTriggers )
                  __fastfail(3u);
                *(_QWORD *)v25 = &gBfeFwTriggers;
                *(_QWORD *)(v25 + 8) = v37;
                *v37 = v25;
                qword_1800F30A8 = v25;
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
0x180041ee0  mov     [rsp-8+arg_10], rbx
0x180041ee5  push    rbp
0x180041ee6  push    rsi
0x180041ee7  push    rdi
0x180041ee8  push    r12
0x180041eea  push    r13
0x180041eec  push    r14
0x180041eee  push    r15
0x180041ef0  lea     rbp, [rsp-27h]
0x180041ef5  sub     rsp, 90h
0x180041efc  mov     rax, cs:__security_cookie
0x180041f03  xor     rax, rsp
0x180041f06  mov     [rbp+57h+var_38], rax
0x180041f0a  xor     r15d, r15d
0x180041f0d  mov     [rbp+57h+var_70], rdx
0x180041f11  mov     r14, rdx
0x180041f14  mov     [rbp+57h+var_48], rcx
0x180041f18  mov     rdx, [rdx]; lpServiceName
0x180041f1b  mov     ebx, r15d
0x180041f1e  mov     esi, r15d
0x180041f21  mov     [rbp+57h+lpBuffer], r15
0x180041f25  lea     r8d, [r15+1]; dwDesiredAccess
0x180041f29  mov     [rbp+57h+cbBufSize], r15d
0x180041f2d  call    cs:__imp_OpenServiceW
0x180041f33  mov     r13, rax
0x180041f36  test    rax, rax
0x180041f39  jnz     short loc_180041F95
0x180041f3b  call    cs:__imp_GetLastError
0x180041f41  mov     edi, eax
0x180041f43  mov     rcx, cs:WPP_GLOBAL_Control
0x180041f4a  lea     rax, WPP_GLOBAL_Control
0x180041f51  cmp     rcx, rax
0x180041f54  jz      short loc_180041F72
0x180041f56  cmp     byte ptr [rcx+19h], 4
0x180041f5a  jb      short loc_180041F72
0x180041f5c  test    byte ptr [rcx+1Ch], 2
0x180041f60  jz      short loc_180041F72
0x180041f62  mov     r9, [r14]
0x180041f65  mov     rcx, [rcx+10h]
0x180041f69  mov     dword ptr [rsp+0C0h+pcbBytesNeeded], edi
0x180041f6d  call    WPP_SF_Sd
0x180041f72  mov     r8d, 0Eh
0x180041f78  cmp     edi, r8d
0x180041f7b  jnz     loc_1800422EE
0x180041f81  lea     rdx, aOpenservicew_0; "OpenServiceW"
0x180041f88  call    WfpReportSysErrorAsWinError
0x180041f8d  mov     rbx, rax
0x180041f90  jmp     loc_1800422D5
0x180041f95  xor     r9d, r9d; cbBufSize
0x180041f98  lea     rax, [rbp+57h+cbBufSize]
0x180041f9c  xor     r8d, r8d; lpBuffer
0x180041f9f  mov     [rsp+0C0h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180041fa4  mov     rcx, r13; hService
0x180041fa7  lea     r14d, [r9+8]
0x180041fab  mov     edx, r14d; dwInfoLevel
0x180041fae  call    cs:__imp_QueryServiceConfig2W
0x180041fb4  mov     edi, [rbp+57h+cbBufSize]
0x180041fb7  test    edi, edi
0x180041fb9  jz      loc_1800422BE
0x180041fbf  mov     ecx, edi; dwBytes
0x180041fc1  lea     r8, [rbp+57h+lpBuffer]
0x180041fc5  xor     edx, edx; dwFlags
0x180041fc7  call    WfpMemAlloc
0x180041fcc  mov     rsi, [rbp+57h+lpBuffer]
0x180041fd0  mov     rbx, rax
0x180041fd3  test    rax, rax
0x180041fd6  jnz     loc_1800422BE
0x180041fdc  lea     rax, [rbp+57h+cbBufSize]
0x180041fe0  mov     r9d, edi; cbBufSize
0x180041fe3  mov     r8, rsi; lpBuffer
0x180041fe6  mov     [rsp+0C0h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180041feb  mov     edx, r14d; dwInfoLevel
0x180041fee  mov     rcx, r13; hService
0x180041ff1  call    cs:__imp_QueryServiceConfig2W
0x180041ff7  test    eax, eax
0x180041ff9  jnz     short loc_180042018
0x180041ffb  call    cs:__imp_GetLastError
0x180042001  mov     r8d, eax
0x180042004  lea     rdx, aQueryserviceco_1; "QueryServiceConfig2W"
0x18004200b  call    WfpReportSysErrorAsWinError
0x180042010  mov     rbx, rax
0x180042013  jmp     loc_1800422BE
0x180042018  mov     r12d, r15d
0x18004201b  cmp     [rsi], r15d
0x18004201e  jbe     loc_1800422BE
0x180042024  mov     r15, [rsi+8]
0x180042028  mov     r14d, r12d
0x18004202b  shl     r14, 5
0x18004202f  cmp     dword ptr [r14+r15], 4
0x180042034  jnz     loc_180042273
0x18004203a  mov     rdi, [rbp+57h+var_70]
0x18004203e  mov     rcx, [rbp+57h+var_48]
0x180042042  mov     rdx, [rdi]
0x180042045  call    BfeFwTriggerIsServiceDependOnBfe
0x18004204a  xor     r9d, r9d
0x18004204d  mov     [rbp+57h+var_78], eax
0x180042050  mov     eax, r9d
0x180042053  mov     [rbp+57h+var_90], eax
0x180042056  cmp     [r14+r15+10h], r9d
0x18004205b  jbe     loc_180042273
0x180042061  mov     r8, [r14+r15+18h]
0x180042066  mov     rdx, [rdi]
0x180042069  mov     ecx, eax
0x18004206b  shl     rcx, 4
0x18004206f  mov     [rbp+57h+var_60], rcx
0x180042073  or      rax, 0FFFFFFFFFFFFFFFFh
0x180042077  mov     [rbp+57h+var_58], r8
0x18004207b  inc     rax
0x18004207e  cmp     [rdx+rax*2], r9w
0x180042083  jnz     short loc_18004207B
0x180042085  mov     ecx, [rcx+r8+4]
0x18004208a  lea     rdx, ds:2[rax*2]
0x180042092  add     rcx, 0E2h
0x180042099  mov     [rbp+57h+Size], rdx
0x18004209d  add     rcx, rdx; dwBytes
0x1800420a0  mov     [rbp+57h+var_88], r9
0x1800420a4  xor     edx, edx; dwFlags
0x1800420a6  lea     r8, [rbp+57h+var_88]
0x1800420aa  call    WfpMemAlloc
0x1800420af  mov     rbx, rax
0x1800420b2  test    rax, rax
0x1800420b5  jnz     loc_1800422BE
0x1800420bb  mov     rdi, [rbp+57h+var_88]
0x1800420bf  lea     rax, [rdi+48h]
0x1800420c3  mov     rcx, rax
0x1800420c6  mov     [rbp+57h+var_50], rax
0x1800420ca  call    WfpCriticalSectionCreate
0x1800420cf  mov     rbx, rax
0x1800420d2  test    rax, rax
0x1800420d5  jnz     loc_1800422B5
0x1800420db  lea     rcx, [rdi+38h]
0x1800420df  xor     r9d, r9d
0x1800420e2  mov     r8, rdi
0x1800420e5  lea     rdx, BfeFwTriggerEntryTimer
0x1800420ec  call    cs:__imp_TpAllocTimer
0x1800420f2  mov     ebx, eax
0x1800420f4  test    eax, eax
0x1800420f6  js      loc_18004228F
0x1800420fc  mov     rcx, [r14+r15+8]
0x180042101  mov     rax, [rcx]
0x180042104  cmp     rax, qword ptr cs:FIREWALL_PORT_OPEN_GUID.Data1
0x18004210b  jnz     short loc_180042123
0x18004210d  mov     rax, [rcx+8]
0x180042111  cmp     rax, qword ptr cs:FIREWALL_PORT_OPEN_GUID.Data4
0x180042118  jnz     short loc_180042123
0x18004211a  mov     dword ptr [rdi+1Ch], 0
0x180042121  jmp     short loc_18004214B
0x180042123  mov     rax, [rcx]
0x180042126  cmp     rax, qword ptr cs:FIREWALL_PORT_CLOSE_GUID.Data1
0x18004212d  jnz     loc_180042288
0x180042133  mov     rax, [rcx+8]
0x180042137  cmp     rax, qword ptr cs:FIREWALL_PORT_CLOSE_GUID.Data4
0x18004213e  jnz     loc_180042288
0x180042144  mov     dword ptr [rdi+1Ch], 1
0x18004214b  mov     rdx, [rbp+57h+var_70]
0x18004214f  lea     rbx, [rdi+98h]
0x180042156  mov     r8, [rbp+57h+Size]; Size
0x18004215a  mov     rcx, rbx; void *
0x18004215d  mov     rdx, [rdx]; Src
0x180042160  call    memcpy_0
0x180042165  mov     rdx, [rbp+57h+Size]
0x180042169  lea     r8, aA144ed388e124d; "a144ed38-8e12-4de4-9d96-e64740b1a524"
0x180042170  mov     eax, [rbp+57h+var_78]
0x180042173  mov     [rdi+10h], rbx
0x180042177  mov     [rdi+18h], eax
0x18004217a  lea     rax, aB7569e0784214e; "b7569e07-8421-4ee0-ad10-86915afdad09"
0x180042181  lea     rcx, [rdx+98h]
0x180042188  add     rcx, rdi
0x18004218b  lea     rbx, [rdx+0E2h]
0x180042192  cmp     dword ptr [rdi+1Ch], 0
0x180042196  cmovnz  rax, r8
0x18004219a  add     rbx, rdi
0x18004219d  movups  xmm0, xmmword ptr [rax]
0x1800421a0  movups  xmmword ptr [rcx], xmm0
0x1800421a3  movups  xmm1, xmmword ptr [rax+10h]
0x1800421a7  movups  xmmword ptr [rcx+10h], xmm1
0x1800421ab  movups  xmm0, xmmword ptr [rax+20h]
0x1800421af  movups  xmmword ptr [rcx+20h], xmm0
0x1800421b3  movups  xmm1, xmmword ptr [rax+30h]
0x1800421b7  movups  xmmword ptr [rcx+30h], xmm1
0x1800421bb  movups  xmm0, xmmword ptr [rax+3Ah]
0x1800421bf  mov     rax, [rbp+57h+var_60]
0x1800421c3  movups  xmmword ptr [rcx+3Ah], xmm0
0x1800421c7  mov     [rdi+20h], rcx
0x1800421cb  mov     rcx, [rbp+57h+var_58]
0x1800421cf  mov     r8d, [rax+rcx+4]; Size
0x1800421d4  mov     rdx, [rax+rcx+8]; Src
0x1800421d9  mov     rcx, rbx; void *
0x1800421dc  call    memcpy_0
0x1800421e1  mov     rax, [rbp+57h+var_60]
0x1800421e5  mov     rcx, [rbp+57h+var_58]
0x1800421e9  mov     [rdi+28h], rbx
0x1800421ed  mov     eax, [rax+rcx+4]
0x1800421f1  mov     rcx, rdi
0x1800421f4  mov     [rdi+30h], eax
0x1800421f7  xor     eax, eax
0x1800421f9  mov     [rdi+34h], eax
0x1800421fc  mov     [rdi+40h], rax
0x180042200  call    BfeFwTriggerEntryInitParams
0x180042205  xor     r9d, r9d
0x180042208  mov     rbx, rax
0x18004220b  test    rax, rax
0x18004220e  jz      short loc_180042227
0x180042210  mov     rcx, [rbp+57h+var_50]
0x180042214  call    WfpCriticalSectionDestroy
0x180042219  lea     rcx, [rbp+57h+var_88]
0x18004221d  call    WfpMemFree
0x180042222  xor     r9d, r9d
0x180042225  jmp     short loc_18004225C
0x180042227  mov     eax, 8
0x18004222c  lea     rcx, gBfeFwTriggers
0x180042233  mov     [rdi+90h], eax
0x180042239  mov     [rdi+94h], eax
0x18004223f  mov     rax, cs:qword_1800F30A8
0x180042246  cmp     [rax], rcx
0x180042249  jnz     short loc_180042281
0x18004224b  mov     [rdi], rcx
0x18004224e  mov     [rdi+8], rax
0x180042252  mov     [rax], rdi
0x180042255  mov     cs:qword_1800F30A8, rdi
0x18004225c  mov     eax, [rbp+57h+var_90]
0x18004225f  mov     rdi, [rbp+57h+var_70]
0x180042263  inc     eax
0x180042265  mov     [rbp+57h+var_90], eax
0x180042268  cmp     eax, [r14+r15+10h]
0x18004226d  jb      loc_180042061
0x180042273  inc     r12d
0x180042276  cmp     r12d, [rsi]
0x180042279  jb      loc_180042024
0x18004227f  jmp     short loc_1800422BE
0x180042281  mov     ecx, 3
0x180042286  int     29h; Win8: RtlFailFast(ecx)
0x180042288  mov     ecx, 5
0x18004228d  int     29h; Win8: RtlFailFast(ecx)
0x18004228f  mov     rcx, [rbp+57h+var_50]
0x180042293  call    WfpCriticalSectionDestroy
0x180042298  lea     rcx, [rbp+57h+var_88]
0x18004229c  call    WfpMemFree
0x1800422a1  mov     r8d, ebx
0x1800422a4  lea     rdx, aTpalloctimer; "TpAllocTimer"
0x1800422ab  call    WfpReportSysErrorAsNtStatus
0x1800422b0  jmp     loc_180042010
0x1800422b5  lea     rcx, [rbp+57h+var_88]
0x1800422b9  call    WfpMemFree
0x1800422be  mov     rcx, r13; hSCObject
0x1800422c1  call    cs:__imp_CloseServiceHandle
0x1800422c7  test    rsi, rsi
0x1800422ca  jz      short loc_1800422D5
0x1800422cc  lea     rcx, [rbp+57h+lpBuffer]
0x1800422d0  call    WfpMemFree
0x1800422d5  test    rbx, rbx
0x1800422d8  jz      short loc_1800422EE
0x1800422da  call    BfeFwTriggerFreeDb
0x1800422df  lea     rdx, aBfefwtriggerbu; "BfeFwTriggerBuildDb"
0x1800422e6  mov     rcx, rbx
0x1800422e9  call    WfpReportError
0x1800422ee  mov     rax, rbx
0x1800422f1  mov     rcx, [rbp+57h+var_38]
0x1800422f5  xor     rcx, rsp; StackCookie
0x1800422f8  call    __security_check_cookie
0x1800422fd  mov     rbx, [rsp+0C0h+arg_10]
0x180042305  add     rsp, 90h
0x18004230c  pop     r15
0x18004230e  pop     r14
0x180042310  pop     r13
0x180042312  pop     r12
0x180042314  pop     rdi
0x180042315  pop     rsi
0x180042316  pop     rbp
0x180042317  retn
```
