# StoragePerfGetAverageSpeed(_STORAGE_DEVICE_DATA const &,double *,double *)

- ea: `0x18000bd8c`
- end: `0x18000c058`
- name: `?StoragePerfGetAverageSpeed@@YAJAEBU_STORAGE_DEVICE_DATA@@PEAN1@Z`
- size: `716`
- prototype: `__int64 __fastcall(const struct _STORAGE_DEVICE_DATA *, double *, double *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180009cc0`

## callees

- `0x180001c80`
- `0x1800020e4`
- `0x180002158`
- `0x18000bd8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000bebc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000bebc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bfbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bfe0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bfbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bfe0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000be5b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000be5b`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18000be9c`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18000be9c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000be77`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000be77`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000be30`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000be30`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000be53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000be53`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000c00a`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000c00a`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000bf82`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000bf82`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18000bf3f`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18000bf67`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18000bf3f`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18000bf67`

## string_xrefs

- `0x18000bf26`: `Write speed is: %lf`
- `0x18000bf51`: `Read speed is: %lf`

## pseudocode

```c
__int64 __fastcall StoragePerfGetAverageSpeed(const struct _STORAGE_DEVICE_DATA *a1, double *a2, double *a3)
{
  unsigned __int64 i; // rdi
  __int64 v7; // rax
  HANDLE *v8; // r9
  HANDLE Thread; // rsi
  char *v10; // r14
  DWORD LastError; // ebx
  unsigned __int64 j; // rbx
  unsigned __int64 k; // rbx
  double v14; // xmm1_8
  double v15; // xmm2_8
  unsigned __int64 v16; // rax
  int v17; // r9d
  unsigned int v18; // ebx
  double v19; // xmm2_8
  unsigned int v20; // eax
  int v21; // r8d
  int v22; // ecx
  signed int v23; // eax
  HANDLE hObject[96]; // [rsp+30h] [rbp-D0h] BYREF

  `eh vector constructor iterator'(
    hObject,
    8u,
    0x10u,
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,
    (void (*)(void *))FileReader::~FileReader);
  for ( i = 0; i < 0x10; ++i )
  {
    v7 = 5 * i;
    v8 = &hObject[5 * i + 16];
    *v8 = a1;
    hObject[v7 + 17] = (HANDLE)i;
    hObject[v7 + 18] = 0;
    hObject[v7 + 19] = 0;
    Thread = CreateThread(0, 0, s_ThreadProc, v8, 4u, 0);
    v10 = (char *)hObject[i];
    if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      CloseHandle(v10);
      SetLastError(LastError);
    }
    hObject[i] = Thread;
    if ( !Thread )
    {
      v23 = GetLastError();
      if ( v23 )
      {
        if ( v23 > 0 )
          v23 = (unsigned __int16)v23 | 0x80070000;
      }
      else
      {
        v23 = -2143748092;
      }
      v21 = 350;
LABEL_34:
      v22 = v23;
LABEL_35:
      v20 = ZTraceReportOriginationNoThis(v22, "StoragePerfGetAverageSpeed", v21);
      goto LABEL_36;
    }
    if ( !SetThreadPriority(Thread, 15) )
    {
      v23 = GetLastError();
      if ( v23 )
      {
        if ( v23 > 0 )
          v23 = (unsigned __int16)v23 | 0x80070000;
      }
      else
      {
        v23 = -2143748092;
      }
      v21 = 352;
      goto LABEL_34;
    }
  }
  for ( j = 0; j < 0x10; ++j )
  {
    if ( ResumeThread(hObject[j]) == -1 )
    {
      v23 = GetLastError();
      if ( v23 )
      {
        if ( v23 > 0 )
          v23 = (unsigned __int16)v23 | 0x80070000;
      }
      else
      {
        v23 = -2143748092;
      }
      v21 = 357;
      goto LABEL_34;
    }
  }
  for ( k = 0; k < 0x10; ++k )
  {
    if ( WaitForSingleObject(hObject[k], 0xFFFFFFFF) )
    {
      v21 = 362;
      v22 = -2147418113;
      goto LABEL_35;
    }
  }
  v14 = 0.0;
  v15 = 0.0;
  v16 = 0;
  while ( 1 )
  {
    v17 = (int)hObject[5 * v16 + 20];
    if ( v17 < 0 )
      break;
    v14 = v14 + *(double *)&hObject[5 * v16 + 18];
    v15 = v15 + *(double *)&hObject[5 * v16++ + 19];
    if ( v16 >= 0x10 )
    {
      v18 = 0;
      *a2 = v14 * 0.0625;
      v19 = v15 * 0.0625;
      *a3 = v19;
      ZTraceHelperNoThis(3, "StoragePerfGetAverageSpeed", 377, "Write speed is: %lf", v19);
      ZTraceHelperNoThis(3, "StoragePerfGetAverageSpeed", 379, "Read speed is: %lf", *a2);
      goto LABEL_37;
    }
  }
  v20 = ZTraceReportPropagationNoThis(v17, "StoragePerfGetAverageSpeed", 368);
LABEL_36:
  v18 = v20;
LABEL_37:
  `eh vector destructor iterator'(hObject, 8u, 0x10u, (void (*)(void *))FileReader::~FileReader);
  return v18;
}

```

## disassembly

```asm
0x18000bd8c  mov     [rsp-8+arg_0], rbx
0x18000bd91  push    rbp
0x18000bd92  push    rsi
0x18000bd93  push    rdi
0x18000bd94  push    r12
0x18000bd96  push    r13
0x18000bd98  push    r14
0x18000bd9a  push    r15
0x18000bd9c  lea     rbp, [rsp-240h]
0x18000bda4  sub     rsp, 340h
0x18000bdab  mov     rax, cs:__security_cookie
0x18000bdb2  xor     rax, rsp
0x18000bdb5  mov     [rbp+270h+var_40], rax
0x18000bdbc  mov     r13, r8
0x18000bdbf  mov     r12, rdx
0x18000bdc2  mov     r15, rcx
0x18000bdc5  lea     rax, ??1FileReader@@QEAA@XZ; FileReader::~FileReader(void)
0x18000bdcc  mov     qword ptr [rsp+370h+dwCreationFlags], rax; void (*)(void *)
0x18000bdd1  lea     r9, ??0?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x18000bdd8  mov     edx, 8; unsigned __int64
0x18000bddd  lea     r8d, [rdx+8]; unsigned __int64
0x18000bde1  lea     rcx, [rsp+370h+hObject]; void *
0x18000bde6  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18000bdeb  nop
0x18000bdec  xor     edi, edi
0x18000bdee  lea     rax, [rdi+rdi*4]
0x18000bdf2  lea     r9, [rbp+270h+var_2C0]
0x18000bdf6  lea     r9, [r9+rax*8]; lpParameter
0x18000bdfa  mov     [r9], r15
0x18000bdfd  mov     [rbp+rax*8+270h+var_2B8], rdi
0x18000be02  mov     [rbp+rax*8+270h+var_2B0], 0
0x18000be0b  mov     [rbp+rax*8+270h+var_2A8], 0
0x18000be14  mov     [rsp+370h+lpThreadId], 0; lpThreadId
0x18000be1d  mov     [rsp+370h+dwCreationFlags], 4; dwCreationFlags
0x18000be25  lea     r8, s_ThreadProc; lpStartAddress
0x18000be2c  xor     edx, edx; dwStackSize
0x18000be2e  xor     ecx, ecx; lpThreadAttributes
0x18000be30  call    cs:__imp_CreateThread
0x18000be36  mov     rsi, rax
0x18000be39  mov     r14, [rsp+rdi*8+370h+hObject]
0x18000be3e  lea     rdx, [r14-1]
0x18000be42  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000be46  ja      short loc_18000BE61
0x18000be48  call    cs:__imp_GetLastError
0x18000be4e  mov     ebx, eax
0x18000be50  mov     rcx, r14; hObject
0x18000be53  call    cs:__imp_CloseHandle
0x18000be59  mov     ecx, ebx; dwErrCode
0x18000be5b  call    cs:__imp_SetLastError
0x18000be61  mov     [rsp+rdi*8+370h+hObject], rsi
0x18000be66  test    rsi, rsi
0x18000be69  jz      loc_18000BFE0
0x18000be6f  mov     edx, 0Fh; nPriority
0x18000be74  mov     rcx, rsi; hThread
0x18000be77  call    cs:__imp_SetThreadPriority
0x18000be7d  test    eax, eax
0x18000be7f  jz      loc_18000BFBD
0x18000be85  inc     rdi
0x18000be88  cmp     rdi, 10h
0x18000be8c  jb      loc_18000BDEE
0x18000be92  xor     ebx, ebx
0x18000be94  or      edi, 0FFFFFFFFh
0x18000be97  mov     rcx, [rsp+rbx*8+370h+hObject]; hThread
0x18000be9c  call    cs:__imp_ResumeThread
0x18000bea2  cmp     eax, edi
0x18000bea4  jz      loc_18000BF9A
0x18000beaa  inc     rbx
0x18000bead  cmp     rbx, 10h
0x18000beb1  jb      short loc_18000BE97
0x18000beb3  xor     ebx, ebx
0x18000beb5  mov     edx, edi; dwMilliseconds
0x18000beb7  mov     rcx, [rsp+rbx*8+370h+hObject]; hHandle
0x18000bebc  call    cs:__imp_WaitForSingleObject
0x18000bec2  test    eax, eax
0x18000bec4  jnz     loc_18000BF8D
0x18000beca  inc     rbx
0x18000becd  cmp     rbx, 10h
0x18000bed1  jb      short loc_18000BEB5
0x18000bed3  xorps   xmm1, xmm1
0x18000bed6  xorps   xmm2, xmm2
0x18000bed9  xor     eax, eax
0x18000bedb  lea     rcx, [rax+rax*4]
0x18000bedf  mov     r9d, [rbp+rcx*8+270h+var_2A0]
0x18000bee4  test    r9d, r9d
0x18000bee7  js      loc_18000BF72
0x18000beed  addsd   xmm1, [rbp+rcx*8+270h+var_2B0]
0x18000bef3  addsd   xmm2, [rbp+rcx*8+270h+var_2A8]
0x18000bef9  inc     rax
0x18000befc  cmp     rax, 10h
0x18000bf00  jb      short loc_18000BEDB
0x18000bf02  xor     ebx, ebx
0x18000bf04  mulsd   xmm1, cs:__real@3fb0000000000000
0x18000bf0c  movsd   qword ptr [r12], xmm1
0x18000bf12  mulsd   xmm2, cs:__real@3fb0000000000000
0x18000bf1a  movsd   qword ptr [r13+0], xmm2
0x18000bf20  movsd   qword ptr [rsp+370h+dwCreationFlags], xmm2
0x18000bf26  lea     r9, aWriteSpeedIsLf; "Write speed is: %lf"
0x18000bf2d  mov     r8d, 179h
0x18000bf33  lea     rdx, aStorageperfget_1; "StoragePerfGetAverageSpeed"
0x18000bf3a  lea     edi, [rbx+3]
0x18000bf3d  mov     ecx, edi
0x18000bf3f  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x18000bf45  movsd   xmm0, qword ptr [r12]
0x18000bf4b  movsd   qword ptr [rsp+370h+dwCreationFlags], xmm0
0x18000bf51  lea     r9, aReadSpeedIsLf; "Read speed is: %lf"
0x18000bf58  mov     r8d, 17Bh
0x18000bf5e  lea     rdx, aStorageperfget_1; "StoragePerfGetAverageSpeed"
0x18000bf65  mov     ecx, edi
0x18000bf67  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x18000bf6d  jmp     loc_18000C012
0x18000bf72  mov     r8d, 170h
0x18000bf78  lea     rdx, aStorageperfget_1; "StoragePerfGetAverageSpeed"
0x18000bf7f  mov     ecx, r9d
0x18000bf82  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18000bf88  jmp     loc_18000C010
0x18000bf8d  mov     r8d, 16Ah
0x18000bf93  mov     ecx, 8000FFFFh
0x18000bf98  jmp     short loc_18000C003
0x18000bf9a  call    cs:__imp_GetLastError
0x18000bfa0  test    eax, eax
0x18000bfa2  jz      short loc_18000BFB0
0x18000bfa4  jle     short loc_18000BFB5
0x18000bfa6  movzx   eax, ax
0x18000bfa9  or      eax, 80070000h
0x18000bfae  jmp     short loc_18000BFB5
0x18000bfb0  mov     eax, 80390004h
0x18000bfb5  mov     r8d, 165h
0x18000bfbb  jmp     short loc_18000C001
0x18000bfbd  call    cs:__imp_GetLastError
0x18000bfc3  test    eax, eax
0x18000bfc5  jz      short loc_18000BFD3
0x18000bfc7  jle     short loc_18000BFD8
0x18000bfc9  movzx   eax, ax
0x18000bfcc  or      eax, 80070000h
0x18000bfd1  jmp     short loc_18000BFD8
0x18000bfd3  mov     eax, 80390004h
0x18000bfd8  mov     r8d, 160h
0x18000bfde  jmp     short loc_18000C001
0x18000bfe0  call    cs:__imp_GetLastError
0x18000bfe6  test    eax, eax
0x18000bfe8  jz      short loc_18000BFF6
0x18000bfea  jle     short loc_18000BFFB
0x18000bfec  movzx   eax, ax
0x18000bfef  or      eax, 80070000h
0x18000bff4  jmp     short loc_18000BFFB
0x18000bff6  mov     eax, 80390004h
0x18000bffb  mov     r8d, 15Eh
0x18000c001  mov     ecx, eax
0x18000c003  lea     rdx, aStorageperfget_1; "StoragePerfGetAverageSpeed"
0x18000c00a  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x18000c010  mov     ebx, eax
0x18000c012  lea     r9, ??1FileReader@@QEAA@XZ; void (*)(void *)
0x18000c019  mov     edx, 8; unsigned __int64
0x18000c01e  lea     r8d, [rdx+8]; unsigned __int64
0x18000c022  lea     rcx, [rsp+370h+hObject]; void *
0x18000c027  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18000c02c  mov     eax, ebx
0x18000c02e  mov     rcx, [rbp+270h+var_40]
0x18000c035  xor     rcx, rsp; StackCookie
0x18000c038  call    __security_check_cookie
0x18000c03d  mov     rbx, [rsp+370h+arg_0]
0x18000c045  add     rsp, 340h
0x18000c04c  pop     r15
0x18000c04e  pop     r14
0x18000c050  pop     r13
0x18000c052  pop     r12
0x18000c054  pop     rdi
0x18000c055  pop     rsi
0x18000c056  pop     rbp
0x18000c057  retn
```
