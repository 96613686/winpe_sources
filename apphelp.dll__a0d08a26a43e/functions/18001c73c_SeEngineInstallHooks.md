# SeEngineInstallHooks

- ea: `0x18001c73c`
- end: `0x18001cb62`
- name: `SeEngineInstallHooks`
- size: `1062`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update`

## callers

- `0x18001c580`

## callees

- `0x1800078c0`
- `0x18000f114`
- `0x18001c73c`
- `0x18001cb68`
- `0x18001cc90`
- `0x18001d128`
- `0x18001df70`
- `0x18005a010`

## import_xrefs

- `ntdll!RtlUnicodeStringToAnsiString` at `0x18001c83e`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18001c83e`
- `ntdll!RtlAcquireSRWLockShared` at `0x18001c95e`
- `ntdll!RtlAcquireSRWLockShared` at `0x18001c95e`
- `ntdll!RtlReleaseSRWLockShared` at `0x18001c988`
- `ntdll!RtlReleaseSRWLockShared` at `0x18001c988`
- `ntdll!RtlFreeAnsiString` at `0x18001c7df`
- `ntdll!RtlFreeAnsiString` at `0x18001c7df`
- `ntdll!RtlInitUnicodeStringEx` at `0x18001c823`
- `ntdll!RtlInitUnicodeStringEx` at `0x18001c823`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001c99e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001c99e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001c941`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001c941`

## string_xrefs

- `0x18001c7ca`: `SeEngineInstallHooks`
- `0x18001ca8a`: `SeEngineInstallHooks`
- `0x18001cab0`: `SeEngineInstallHooks`
- `0x18001cb4c`: `SeEngineInstallHooks`
- `0x18001ca78`: `Shim DLL %S not loaded for shim %S.  Shim is disabled.`
- `0x18001cb0a`: `Failed to create EAT Hook Manager`

## pseudocode

```c
__int64 __fastcall SeEngineInstallHooks(__int64 a1)
{
  _QWORD *v1; // rsi
  const WCHAR *v2; // r13
  unsigned __int64 v3; // r15
  unsigned __int64 *v4; // rcx
  unsigned __int64 v5; // rax
  unsigned __int64 v6; // rcx
  unsigned __int64 v7; // r8
  NTSTATUS inited; // ebx
  unsigned __int64 v10; // rax
  __int64 (__fastcall *v11)(PCHAR, const wchar_t *, unsigned int *); // rdi
  __int64 v12; // r13
  unsigned int v13; // edx
  int v14; // eax
  int v15; // eax
  unsigned __int64 *v16; // r14
  const WCHAR *v17; // rbx
  const wchar_t *v18; // r12
  __int64 v19; // rdi
  HMODULE v20; // rbx
  int v21; // ebx
  int ShimExports; // eax
  unsigned __int64 *v23; // rcx
  unsigned __int64 v24; // r9
  _QWORD *v25; // rax
  unsigned __int64 **v26; // rdi
  HMODULE phModule; // [rsp+40h] [rbp-49h] BYREF
  __int64 *v28; // [rsp+48h] [rbp-41h] BYREF
  __int64 v29; // [rsp+50h] [rbp-39h]
  __int64 (__fastcall *v30)(); // [rsp+58h] [rbp-31h] BYREF
  __int64 (__fastcall *v31)(PCHAR, const wchar_t *, unsigned int *); // [rsp+60h] [rbp-29h] BYREF
  ULONGLONG pullResult; // [rsp+68h] [rbp-21h]
  const WCHAR *v33; // [rsp+70h] [rbp-19h]
  char v34[8]; // [rsp+78h] [rbp-11h] BYREF
  struct _STRING AnsiString; // [rsp+80h] [rbp-9h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp+7h] BYREF
  unsigned int v37; // [rsp+F0h] [rbp+67h] BYREF
  int v38; // [rsp+F4h] [rbp+6Bh]
  __int64 v39; // [rsp+F8h] [rbp+6Fh]
  __int64 v40; // [rsp+100h] [rbp+77h]
  const WCHAR *v41; // [rsp+108h] [rbp+7Fh]

  v38 = HIDWORD(a1);
  v1 = (_QWORD *)g_Engine;
  v2 = 0;
  v29 = 0;
  v31 = 0;
  AnsiString = 0;
  v30 = 0;
  v3 = 0;
  DestinationString = 0;
  v37 = 0;
  while ( 1 )
  {
    v4 = (unsigned __int64 *)v1[2];
    if ( v3 >= v4[2] )
    {
      inited = 0;
      goto LABEL_6;
    }
    v39 = 0;
    v5 = v4[1] * v3;
    if ( !is_mul_ok(v4[1], v3) || (v6 = v4[5], v7 = v6 + v5, v6 + v5 < v6) || !v7 )
    {
      inited = -1073741275;
      AslLogCallPrintf(1, "SeEngineInstallHooks", 535, "Failed to lookup module %S by name", v2);
      goto LABEL_6;
    }
    v15 = *(_DWORD *)(v7 + 40);
    v2 = *(const WCHAR **)(v7 + 8);
    v41 = v2;
    LODWORD(v39) = v15;
    v16 = (unsigned __int64 *)(v15 == 1 ? v1[4] : v1[3]);
    if ( !v16 || !v16[2] )
      goto LABEL_25;
    v24 = 0;
    do
    {
      v40 = 0;
      if ( is_mul_ok(v16[1], v24) )
      {
        v25 = (_QWORD *)(v16[5] + v16[1] * v24);
        if ( (unsigned __int64)v25 >= v16[5] )
          goto LABEL_45;
      }
      v25 = 0;
LABEL_45:
      if ( v3 == *v25 )
        break;
      v25 = 0;
      ++v24;
    }
    while ( v24 < v16[2] );
    if ( !v25 )
    {
LABEL_25:
      v17 = *(const WCHAR **)(v7 + 32);
      v18 = *(const wchar_t **)(v7 + 16);
      LODWORD(v40) = *(_DWORD *)(v7 + 24);
      pullResult = *(_QWORD *)(v7 + 48);
      v33 = v17;
      v37 = 0;
      phModule = 0;
      if ( v2 )
      {
        v19 = v1[5];
        if ( GetModuleHandleExW(0, v2, &phModule) )
        {
          v20 = phModule;
          v28 = 0;
          RtlAcquireSRWLockShared(v19);
          SepModuleTrackerFindModule(&v28, v34, v19, v20);
          if ( v28 )
          {
            v21 = 0;
            v29 = *v28;
          }
          else
          {
            v21 = -1073741515;
          }
          RtlReleaseSRWLockShared(v19);
          if ( v21 >= 0 )
            v21 = 0;
        }
        else
        {
          v21 = -1073741515;
        }
        if ( phModule )
          FreeLibrary(phModule);
        if ( v21 == -1073741515 )
        {
          AslLogCallPrintf(
            2,
            "SeEngineInstallHooks",
            573,
            "Shim DLL %S not loaded for shim %S.  Shim is disabled.",
            v18,
            v2);
          goto LABEL_20;
        }
        v17 = v33;
      }
      ShimExports = SeUtilsGetShimExports(&v31, &v30, *(void **)(v29 + 48));
      if ( ShimExports < 0 )
      {
        AslLogCallPrintf(
          2,
          "SeEngineInstallHooks",
          587,
          "Failed to get exports for %S. Shim %S will be disabled [%x]",
          v2,
          v18,
          ShimExports);
        goto LABEL_20;
      }
      v23 = (unsigned __int64 *)v1[2];
      v10 = 0;
      if ( v3 < v23[2] )
      {
        if ( !is_mul_ok(v23[1], v3) || (v10 = v23[5] + v23[1] * v3, v10 < v23[5]) )
          v10 = 0;
      }
      v11 = v31;
      *(_QWORD *)(v10 + 56) = v30;
      if ( v11 )
        break;
    }
LABEL_20:
    ++v3;
  }
  inited = RtlInitUnicodeStringEx(&DestinationString, v17);
  if ( inited >= 0 )
  {
    inited = RtlUnicodeStringToAnsiString(&AnsiString, &DestinationString, 1u);
    if ( inited < 0 )
    {
      AslLogCallPrintf(1, "SeEngineInstallHooks", 615, "Failed to convert to ANSI");
      goto LABEL_6;
    }
    v12 = v11(AnsiString.Buffer, v18, &v37);
    if ( v12 )
    {
      v13 = v37;
      if ( v37 )
      {
        v14 = v39;
        if ( (_DWORD)v39 == 1 )
        {
          v26 = (unsigned __int64 **)(v1 + 4);
          if ( !v1[4] )
          {
            inited = SeHookManagerCreate(v1 + 4);
            if ( inited < 0 )
            {
              AslLogCallPrintf(1, "SeEngineInstallHooks", 628, "Failed to create EAT Hook Manager");
              goto LABEL_6;
            }
            *(_QWORD *)(v1[6] + 8LL) = *v26;
            v13 = v37;
            v14 = v39;
          }
          v16 = *v26;
          pullResult = 0;
        }
        inited = SeHookManagerAddHooks((int)v16, v3, v40, v12, v13, v14 != 1, pullResult);
        if ( inited < 0 )
        {
          AslLogCallPrintf(1, "SeEngineInstallHooks", 646, "Failed to add hooks for %S", v18);
          goto LABEL_6;
        }
        if ( !(_DWORD)v39 )
          SeModuleTrackerSetFlagAll(*(_QWORD *)(v1[6] + 16LL));
      }
    }
    v2 = v41;
    goto LABEL_20;
  }
  AslLogCallPrintf(1, "SeEngineInstallHooks", 609, "Failed to init unicode string");
LABEL_6:
  RtlFreeAnsiString(&AnsiString);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18001c73c  mov     [rsp-8+arg_0], rcx
0x18001c741  push    rbp
0x18001c742  push    rbx
0x18001c743  push    rsi
0x18001c744  push    rdi
0x18001c745  push    r12
0x18001c747  push    r13
0x18001c749  push    r14
0x18001c74b  push    r15
0x18001c74d  lea     rbp, [rsp-1Fh]
0x18001c752  sub     rsp, 0A8h
0x18001c759  mov     rsi, cs:g_Engine
0x18001c760  xor     r13d, r13d
0x18001c763  xorps   xmm0, xmm0
0x18001c766  mov     [rbp+57h+var_90], r13
0x18001c76a  xorps   xmm1, xmm1
0x18001c76d  mov     [rbp+57h+var_80], r13
0x18001c771  movups  xmmword ptr [rbp+57h+AnsiString.Length], xmm0
0x18001c775  mov     [rbp+57h+var_88], r13
0x18001c779  xor     r15d, r15d
0x18001c77c  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x18001c780  mov     dword ptr [rbp+57h+arg_0], r13d
0x18001c784  mov     rcx, [rsi+10h]
0x18001c788  cmp     r15, [rcx+10h]
0x18001c78c  jnb     short loc_18001C7FB
0x18001c78e  mov     rax, r15
0x18001c791  mov     [rbp+57h+arg_8], 0
0x18001c799  mul     qword ptr [rcx+8]
0x18001c79d  test    rdx, rdx
0x18001c7a0  jnz     short loc_18001C7B3
0x18001c7a2  mov     rcx, [rcx+28h]
0x18001c7a6  lea     r8, [rcx+rax]
0x18001c7aa  cmp     r8, rcx
0x18001c7ad  jnb     loc_18001C8D3
0x18001c7b3  mov     ebx, 0C0000225h
0x18001c7b8  mov     [rsp+0E0h+var_C0], r13
0x18001c7bd  lea     r9, aFailedToLookup_0; "Failed to lookup module %S by name"
0x18001c7c4  mov     r8d, 217h
0x18001c7ca  lea     rdx, aSeengineinstal; "SeEngineInstallHooks"
0x18001c7d1  mov     ecx, 1
0x18001c7d6  call    AslLogCallPrintf
0x18001c7db  lea     rcx, [rbp+57h+AnsiString]; AnsiString
0x18001c7df  call    cs:__imp_RtlFreeAnsiString
0x18001c7e5  mov     eax, ebx
0x18001c7e7  add     rsp, 0A8h
0x18001c7ee  pop     r15
0x18001c7f0  pop     r14
0x18001c7f2  pop     r13
0x18001c7f4  pop     r12
0x18001c7f6  pop     rdi
0x18001c7f7  pop     rsi
0x18001c7f8  pop     rbx
0x18001c7f9  pop     rbp
0x18001c7fa  retn
0x18001c7fb  xor     ebx, ebx
0x18001c7fd  jmp     short loc_18001C7DB
0x18001c7ff  add     rax, [rcx+28h]
0x18001c803  cmp     rax, [rcx+28h]
0x18001c807  jnb     short loc_18001C80B
0x18001c809  xor     eax, eax
0x18001c80b  mov     rdi, [rbp+57h+var_80]
0x18001c80f  mov     [rax+38h], r8
0x18001c813  test    rdi, rdi
0x18001c816  jz      loc_18001C8CB
0x18001c81c  mov     rdx, rbx; SourceString
0x18001c81f  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18001c823  call    cs:__imp_RtlInitUnicodeStringEx
0x18001c829  mov     ebx, eax
0x18001c82b  test    eax, eax
0x18001c82d  js      loc_18001CB3F
0x18001c833  mov     r8b, 1; AllocateDestinationString
0x18001c836  lea     rdx, [rbp+57h+DestinationString]; SourceString
0x18001c83a  lea     rcx, [rbp+57h+AnsiString]; DestinationString
0x18001c83e  call    cs:__imp_RtlUnicodeStringToAnsiString
0x18001c844  mov     ebx, eax
0x18001c846  test    eax, eax
0x18001c848  js      loc_18001CB30
0x18001c84e  mov     rcx, [rbp+57h+AnsiString.Buffer]
0x18001c852  lea     r8, [rbp+57h+arg_0]
0x18001c856  mov     rdx, r12
0x18001c859  mov     rax, rdi
0x18001c85c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c861  mov     r13, rax
0x18001c864  test    rax, rax
0x18001c867  jz      short loc_18001C8C7
0x18001c869  mov     edx, dword ptr [rbp+57h+arg_0]
0x18001c86c  test    edx, edx
0x18001c86e  jz      short loc_18001C8C7
0x18001c870  mov     eax, dword ptr [rbp+57h+arg_8]
0x18001c873  cmp     eax, 1
0x18001c876  jz      loc_18001CAD1
0x18001c87c  mov     r8d, dword ptr [rbp+57h+arg_10]; int
0x18001c880  xor     ecx, ecx
0x18001c882  cmp     eax, 1
0x18001c885  mov     r9, r13; int
0x18001c888  mov     eax, edx
0x18001c88a  mov     rdx, [rbp+57h+var_78]
0x18001c88e  setnz   cl
0x18001c891  mov     [rsp+0E0h+pullResult], rdx; pullResult
0x18001c896  mov     rdx, r15; int
0x18001c899  mov     [rsp+0E0h+var_B8], ecx; int
0x18001c89d  mov     rcx, r14; int
0x18001c8a0  mov     [rsp+0E0h+var_C0], rax; __int64
0x18001c8a5  call    SeHookManagerAddHooks
0x18001c8aa  mov     ebx, eax
0x18001c8ac  test    eax, eax
0x18001c8ae  js      loc_18001CB19
0x18001c8b4  cmp     dword ptr [rbp+57h+arg_8], 0
0x18001c8b8  jnz     short loc_18001C8C7
0x18001c8ba  mov     rcx, [rsi+30h]
0x18001c8be  mov     rcx, [rcx+10h]
0x18001c8c2  call    SeModuleTrackerSetFlagAll
0x18001c8c7  mov     r13, [rbp+57h+arg_18]
0x18001c8cb  inc     r15
0x18001c8ce  jmp     loc_18001C784
0x18001c8d3  test    r8, r8
0x18001c8d6  jz      loc_18001C7B3
0x18001c8dc  mov     eax, [r8+28h]
0x18001c8e0  mov     r13, [r8+8]
0x18001c8e4  mov     [rbp+57h+arg_18], r13
0x18001c8e8  mov     dword ptr [rbp+57h+arg_8], eax
0x18001c8eb  cmp     eax, 1
0x18001c8ee  jz      loc_18001CA5B
0x18001c8f4  mov     r14, [rsi+18h]
0x18001c8f8  test    r14, r14
0x18001c8fb  jnz     loc_18001CA05
0x18001c901  mov     eax, [r8+18h]
0x18001c905  mov     rbx, [r8+20h]
0x18001c909  mov     r12, [r8+10h]
0x18001c90d  mov     dword ptr [rbp+57h+arg_10], eax
0x18001c910  mov     rax, [r8+30h]
0x18001c914  mov     [rbp+57h+var_78], rax
0x18001c918  mov     [rbp+57h+var_70], rbx
0x18001c91c  mov     dword ptr [rbp+57h+arg_0], 0
0x18001c923  mov     [rbp+57h+phModule], 0
0x18001c92b  test    r13, r13
0x18001c92e  jz      loc_18001C9B4
0x18001c934  mov     rdi, [rsi+28h]
0x18001c938  lea     r8, [rbp+57h+phModule]; phModule
0x18001c93c  mov     rdx, r13; lpModuleName
0x18001c93f  xor     ecx, ecx; dwFlags
0x18001c941  call    cs:__imp_GetModuleHandleExW
0x18001c947  test    eax, eax
0x18001c949  jz      loc_18001CA69
0x18001c94f  mov     rbx, [rbp+57h+phModule]
0x18001c953  mov     rcx, rdi
0x18001c956  mov     [rbp+57h+var_98], 0
0x18001c95e  call    cs:__imp_RtlAcquireSRWLockShared
0x18001c964  mov     r9, rbx
0x18001c967  lea     rdx, [rbp+57h+var_68]
0x18001c96b  mov     r8, rdi
0x18001c96e  lea     rcx, [rbp+57h+var_98]
0x18001c972  call    SepModuleTrackerFindModule
0x18001c977  mov     rax, [rbp+57h+var_98]
0x18001c97b  test    rax, rax
0x18001c97e  jnz     short loc_18001C9FA
0x18001c980  mov     ebx, 0C0000135h
0x18001c985  mov     rcx, rdi
0x18001c988  call    cs:__imp_RtlReleaseSRWLockShared
0x18001c98e  xor     eax, eax
0x18001c990  test    ebx, ebx
0x18001c992  cmovns  ebx, eax
0x18001c995  mov     rcx, [rbp+57h+phModule]; hLibModule
0x18001c999  test    rcx, rcx
0x18001c99c  jz      short loc_18001C9A4
0x18001c99e  call    cs:__imp_FreeLibrary
0x18001c9a4  cmp     ebx, 0C0000135h
0x18001c9aa  jz      loc_18001CA73
0x18001c9b0  mov     rbx, [rbp+57h+var_70]
0x18001c9b4  mov     rax, [rbp+57h+var_90]
0x18001c9b8  lea     rdx, [rbp+57h+var_88]
0x18001c9bc  lea     rcx, [rbp+57h+var_80]
0x18001c9c0  mov     r8, [rax+30h]
0x18001c9c4  call    SeUtilsGetShimExports
0x18001c9c9  test    eax, eax
0x18001c9cb  js      loc_18001CAA0
0x18001c9d1  mov     rcx, [rsi+10h]
0x18001c9d5  xor     eax, eax
0x18001c9d7  mov     r8, [rbp+57h+var_88]
0x18001c9db  cmp     r15, [rcx+10h]
0x18001c9df  jnb     loc_18001C80B
0x18001c9e5  mov     rax, r15
0x18001c9e8  mul     qword ptr [rcx+8]
0x18001c9ec  test    rdx, rdx
0x18001c9ef  jnz     loc_18001C809
0x18001c9f5  jmp     loc_18001C7FF
0x18001c9fa  mov     rax, [rax]
0x18001c9fd  xor     ebx, ebx
0x18001c9ff  mov     [rbp+57h+var_90], rax
0x18001ca03  jmp     short loc_18001C985
0x18001ca05  cmp     qword ptr [r14+10h], 0
0x18001ca0a  jbe     loc_18001C901
0x18001ca10  xor     r9d, r9d
0x18001ca13  xor     r10d, r10d
0x18001ca16  mov     rax, r9
0x18001ca19  mov     [rbp+57h+arg_10], 0
0x18001ca21  mul     qword ptr [r14+8]
0x18001ca25  test    rdx, rdx
0x18001ca28  jnz     short loc_18001CA34
0x18001ca2a  add     rax, [r14+28h]
0x18001ca2e  cmp     rax, [r14+28h]
0x18001ca32  jnb     short loc_18001CA36
0x18001ca34  xor     eax, eax
0x18001ca36  cmp     r15, [rax]
0x18001ca39  jnz     short loc_18001CA4E
0x18001ca3b  test    r10, r10
0x18001ca3e  jnz     short loc_18001CA64
0x18001ca40  test    rax, rax
0x18001ca43  jz      loc_18001C901
0x18001ca49  jmp     loc_18001C8CB
0x18001ca4e  xor     eax, eax
0x18001ca50  inc     r9
0x18001ca53  cmp     r9, [r14+10h]
0x18001ca57  jb      short loc_18001CA16
0x18001ca59  jmp     short loc_18001CA40
0x18001ca5b  mov     r14, [rsi+20h]
0x18001ca5f  jmp     loc_18001C8F8
0x18001ca64  inc     r10
0x18001ca67  jmp     short loc_18001CA4E
0x18001ca69  mov     ebx, 0C0000135h
0x18001ca6e  jmp     loc_18001C995
0x18001ca73  mov     qword ptr [rsp+0E0h+var_B8], r13
0x18001ca78  lea     r9, aShimDllSNotLoa; "Shim DLL %S not loaded for shim %S.  Sh"...
0x18001ca7f  mov     r8d, 23Dh
0x18001ca85  mov     [rsp+0E0h+var_C0], r12
0x18001ca8a  lea     rdx, aSeengineinstal; "SeEngineInstallHooks"
0x18001ca91  mov     ecx, 2
0x18001ca96  call    AslLogCallPrintf
0x18001ca9b  jmp     loc_18001C8CB
0x18001caa0  mov     dword ptr [rsp+0E0h+pullResult], eax
0x18001caa4  lea     r9, aFailedToGetExp; "Failed to get exports for %S. Shim %S w"...
0x18001caab  mov     qword ptr [rsp+0E0h+var_B8], r12
0x18001cab0  lea     rdx, aSeengineinstal; "SeEngineInstallHooks"
0x18001cab7  mov     r8d, 24Bh
0x18001cabd  mov     [rsp+0E0h+var_C0], r13
0x18001cac2  mov     ecx, 2
0x18001cac7  call    AslLogCallPrintf
0x18001cacc  jmp     loc_18001C8CB
0x18001cad1  lea     rdi, [rsi+20h]
0x18001cad5  cmp     qword ptr [rdi], 0
0x18001cad9  jnz     short loc_18001CAFA
0x18001cadb  mov     rcx, rdi
0x18001cade  call    SeHookManagerCreate
0x18001cae3  mov     ebx, eax
0x18001cae5  test    eax, eax
0x18001cae7  js      short loc_18001CB0A
0x18001cae9  mov     rax, [rdi]
0x18001caec  mov     rcx, [rsi+30h]
0x18001caf0  mov     [rcx+8], rax
0x18001caf4  mov     edx, dword ptr [rbp+57h+arg_0]
0x18001caf7  mov     eax, dword ptr [rbp+57h+arg_8]
0x18001cafa  mov     r14, [rdi]
0x18001cafd  mov     [rbp+57h+var_78], 0
0x18001cb05  jmp     loc_18001C87C
0x18001cb0a  lea     r9, aFailedToCreate_11; "Failed to create EAT Hook Manager"
0x18001cb11  mov     r8d, 274h
0x18001cb17  jmp     short loc_18001CB4C
0x18001cb19  mov     [rsp+0E0h+var_C0], r12
0x18001cb1e  lea     r9, aFailedToAddHoo_0; "Failed to add hooks for %S"
0x18001cb25  mov     r8d, 286h
0x18001cb2b  jmp     loc_18001C7CA
0x18001cb30  lea     r9, aFailedToConver_26; "Failed to convert to ANSI"
0x18001cb37  mov     r8d, 267h
0x18001cb3d  jmp     short loc_18001CB4C
0x18001cb3f  lea     r9, aFailedToInitUn; "Failed to init unicode string"
0x18001cb46  mov     r8d, 261h
0x18001cb4c  lea     rdx, aSeengineinstal; "SeEngineInstallHooks"
0x18001cb53  mov     ecx, 1
0x18001cb58  call    AslLogCallPrintf
0x18001cb5d  jmp     loc_18001C7DB
```
