# NmrpFindConfigurationAndLoadProviderOnDemand

- ea: `0x14005d654`
- end: `0x14005d981`
- name: `NmrpFindConfigurationAndLoadProviderOnDemand`
- size: `813`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task`

## callers

- `0x14002c83c`

## callees

- `0x14003d4cc`
- `0x14003ebf0`
- `0x140042460`
- `0x14004266c`
- `0x140042d60`
- `0x1400438b8`
- `0x14005d410`
- `0x14005d654`
- `0x140077fa0`
- `0x140078400`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14005d955`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14005d955`
- `ntoskrnl!RtlStringFromGUID` at `0x14005d6c3`
- `ntoskrnl!RtlStringFromGUID` at `0x14005d6c3`
- `ntoskrnl!ZwLoadDriver` at `0x14005d856`
- `ntoskrnl!ZwLoadDriver` at `0x14005d856`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d914`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d92a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d914`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d92a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005d845`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005d845`

## string_xrefs

- `0x14005d6df`: `\Registry\Machine\System\CurrentControlSet\Control\NMR\providers`
- `0x14005d818`: `\Registry\Machine\SYSTEM\CurrentControlSet\Services\%ls`

## pseudocode

```c
void __fastcall NmrpFindConfigurationAndLoadProviderOnDemand(__int64 a1)
{
  void *v2; // rbx
  int *v3; // rdi
  __int64 v4; // rcx
  int v5; // esi
  NTSTATUS v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  NTSTATUS v10; // eax
  NTSTATUS v11; // eax
  int ValueKey; // eax
  int v13; // eax
  NTSTATUS v14; // eax
  int v15; // r9d
  int v16; // eax
  int v17; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD KeyHandle[3]; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v19; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v22[32]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v23; // [rsp+A0h] [rbp-60h]
  __int64 v24; // [rsp+A8h] [rbp-58h]
  _BYTE v25[16]; // [rsp+B0h] [rbp-50h] BYREF
  _DWORD *v26; // [rsp+C0h] [rbp-40h]
  __int64 v27; // [rsp+C8h] [rbp-38h]
  int *v28; // [rsp+D0h] [rbp-30h]
  __int64 v29; // [rsp+D8h] [rbp-28h]
  __int64 *v30; // [rsp+E0h] [rbp-20h]
  __int64 v31; // [rsp+E8h] [rbp-18h]
  wchar_t pszDest[256]; // [rsp+F0h] [rbp-10h] BYREF

  *(_QWORD *)&KeyHandle[1] = 0;
  v2 = 0;
  v3 = 0;
  v19 = 0;
  *(_QWORD *)&DestinationString.Length = 0;
  memset(pszDest, 0, sizeof(pszDest));
  v4 = *(_QWORD *)(a1 + 80);
  v5 = 0;
  GuidString = 0;
  v17 = 0;
  v6 = RtlStringFromGUID(*(const GUID *const *)(v4 + 40), &GuidString);
  v9 = (unsigned int)v6;
  if ( v6 >= 0 )
  {
    v10 = RtlStringCchPrintfW(
            pszDest,
            0x100u,
            L"%ls\\%ls",
            L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\NMR\\providers",
            GuidString.Buffer);
    v9 = (unsigned int)v10;
    if ( v10 >= 0 )
    {
      v11 = NetioOpenKey(pszDest, 0x20019u, (PHANDLE)&KeyHandle[1]);
      v9 = (unsigned int)v11;
      if ( v11 >= 0 )
      {
        ValueKey = NetioQueryValueKey(*(HANDLE *)&KeyHandle[1], 0x67524D4Eu, (__int64)&v19, (__int64)KeyHandle);
        v9 = (unsigned int)ValueKey;
        if ( ValueKey < 0 )
        {
          v13 = NetioQueryValueKey(
                  *(HANDLE *)&KeyHandle[1],
                  0x67524D4Eu,
                  (__int64)&DestinationString,
                  (__int64)KeyHandle);
          v3 = *(int **)&DestinationString.Length;
          if ( v13 >= 0 )
          {
            NetioQueryFeatureConfiguration(**(unsigned int **)&DestinationString.Length, &v17);
            v5 = v17;
          }
          v9 = (unsigned int)NetioQueryValueKey(
                               *(HANDLE *)&KeyHandle[1],
                               0x67524D4Eu,
                               (__int64)&v19,
                               (__int64)KeyHandle);
        }
        v2 = (void *)v19;
        if ( v19 )
        {
          memset(pszDest, 0, sizeof(pszDest));
          v14 = RtlStringCchPrintfW(
                  pszDest,
                  0x100u,
                  L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Services\\%ls",
                  v19);
          v9 = (unsigned int)v14;
          if ( v14 >= 0 )
          {
            DestinationString = 0;
            RtlInitUnicodeString(&DestinationString, pszDest);
            v9 = (unsigned int)ZwLoadDriver(&DestinationString);
          }
        }
      }
    }
  }
  if ( (unsigned int)dword_14009A008 > 5 )
  {
    v23 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 40LL);
    v24 = 16;
    tlgCreate1Sz_wchar_t(v25, pszDest, v8, v9);
    KeyHandle[0] = v15;
    v26 = KeyHandle;
    v27 = 4;
    if ( v3 )
      v16 = *v3;
    else
      v16 = 0;
    v17 = v16;
    v29 = 4;
    v28 = &v17;
    LODWORD(v19) = v5;
    v30 = &v19;
    v31 = 4;
    tlgWriteTransfer_EtwWriteTransfer(&dword_14009A008, &byte_1400907CF, 0, 0, 7, v22);
  }
  if ( v3 )
    ExFreePoolWithTag(v3, 0);
  if ( v2 )
    ExFreePoolWithTag(v2, 0);
  if ( *(_QWORD *)&KeyHandle[1] )
    NetioCloseKey(&KeyHandle[1], v7, v8, v9);
  if ( GuidString.Buffer )
    RtlFreeUnicodeString(&GuidString);
}

```

## disassembly

```asm
0x14005d654  push    rbp
0x14005d656  push    rbx
0x14005d657  push    rsi
0x14005d658  push    rdi
0x14005d659  push    r12
0x14005d65b  push    r14
0x14005d65d  lea     rbp, [rsp-208h]
0x14005d665  sub     rsp, 308h
0x14005d66c  mov     rax, cs:__security_cookie
0x14005d673  xor     rax, rsp
0x14005d676  mov     [rbp+230h+var_40], rax
0x14005d67d  mov     r14, rcx
0x14005d680  mov     qword ptr [rsp+330h+KeyHandle+4], 0
0x14005d689  xor     ebx, ebx
0x14005d68b  lea     rcx, [rbp+230h+pszDest]; void *
0x14005d68f  xor     edi, edi
0x14005d691  mov     [rsp+330h+var_2E0], rbx
0x14005d696  xor     edx, edx; Val
0x14005d698  mov     qword ptr [rsp+330h+DestinationString.Length], rdi
0x14005d69d  mov     r8d, 200h; Size
0x14005d6a3  call    memset
0x14005d6a8  mov     rcx, [r14+50h]
0x14005d6ac  lea     rdx, [rsp+330h+GuidString]; GuidString
0x14005d6b1  xorps   xmm0, xmm0
0x14005d6b4  xor     esi, esi
0x14005d6b6  movups  xmmword ptr [rsp+330h+GuidString.Length], xmm0
0x14005d6bb  mov     [rsp+330h+var_2F0], esi
0x14005d6bf  mov     rcx, [rcx+28h]; Guid
0x14005d6c3  call    cs:__imp_RtlStringFromGUID
0x14005d6ca  nop     dword ptr [rax+rax+00h]
0x14005d6cf  mov     r9d, eax
0x14005d6d2  test    eax, eax
0x14005d6d4  js      loc_14005D865
0x14005d6da  mov     rax, [rsp+330h+GuidString.Buffer]
0x14005d6df  lea     r9, aRegistryMachin_3; "\\Registry\\Machine\\System\\CurrentCon"...
0x14005d6e6  lea     r8, aLsLs; "%ls\\%ls"
0x14005d6ed  mov     qword ptr [rsp+330h+Tag], rax
0x14005d6f2  mov     edx, 100h; cchDest
0x14005d6f7  lea     rcx, [rbp+230h+pszDest]; pszDest
0x14005d6fb  call    RtlStringCchPrintfW
0x14005d700  mov     r9d, eax
0x14005d703  test    eax, eax
0x14005d705  js      loc_14005D865
0x14005d70b  lea     r8, [rsp+330h+KeyHandle+4]; KeyHandle
0x14005d710  mov     edx, 20019h; DesiredAccess
0x14005d715  lea     rcx, [rbp+230h+pszDest]; SourceString
0x14005d719  call    NetioOpenKey
0x14005d71e  mov     r9d, eax
0x14005d721  test    eax, eax
0x14005d723  js      loc_14005D865
0x14005d729  mov     rcx, qword ptr [rsp+330h+KeyHandle+4]; KeyHandle
0x14005d72e  lea     rax, [rsp+330h+KeyHandle]
0x14005d733  mov     [rsp+330h+var_300], rax; __int64
0x14005d738  lea     r12d, [rdi+40h]
0x14005d73c  lea     rax, [rsp+330h+var_2E0]
0x14005d741  mov     ebx, 67524D4Eh
0x14005d746  mov     [rsp+330h+var_308], rax; __int64
0x14005d74b  lea     r8d, [rdi+1]
0x14005d74f  mov     r9d, r12d
0x14005d752  mov     [rsp+330h+Tag], ebx; Tag
0x14005d756  lea     rdx, aOverride; "Override"
0x14005d75d  call    NetioQueryValueKey
0x14005d762  mov     r9d, eax
0x14005d765  test    eax, eax
0x14005d767  jns     loc_14005D7FA
0x14005d76d  mov     rcx, qword ptr [rsp+330h+KeyHandle+4]; KeyHandle
0x14005d772  lea     rax, [rsp+330h+KeyHandle]
0x14005d777  mov     [rsp+330h+var_300], rax; __int64
0x14005d77c  lea     r8d, [rdi+4]
0x14005d780  lea     rax, [rsp+330h+DestinationString]
0x14005d785  mov     r9d, r12d
0x14005d788  mov     [rsp+330h+var_308], rax; __int64
0x14005d78d  lea     rdx, aFeatureid; "FeatureId"
0x14005d794  mov     [rsp+330h+Tag], ebx; Tag
0x14005d798  call    NetioQueryValueKey
0x14005d79d  mov     rdi, qword ptr [rsp+330h+DestinationString.Length]
0x14005d7a2  test    eax, eax
0x14005d7a4  js      short loc_14005D7C5
0x14005d7a6  mov     ecx, [rdi]
0x14005d7a8  lea     rdx, [rsp+330h+var_2F0]
0x14005d7ad  call    NetioQueryFeatureConfiguration
0x14005d7b2  mov     esi, [rsp+330h+var_2F0]
0x14005d7b6  test    eax, eax
0x14005d7b8  js      short loc_14005D7C5
0x14005d7ba  lea     rdx, aPrevious; "Previous"
0x14005d7c1  test    esi, esi
0x14005d7c3  jz      short loc_14005D7CC
0x14005d7c5  lea     rdx, aLatest; "Latest"
0x14005d7cc  mov     rcx, qword ptr [rsp+330h+KeyHandle+4]; KeyHandle
0x14005d7d1  lea     rax, [rsp+330h+KeyHandle]
0x14005d7d6  mov     [rsp+330h+var_300], rax; __int64
0x14005d7db  mov     r9, r12
0x14005d7de  lea     rax, [rsp+330h+var_2E0]
0x14005d7e3  mov     r8d, 1
0x14005d7e9  mov     [rsp+330h+var_308], rax; __int64
0x14005d7ee  mov     [rsp+330h+Tag], ebx; Tag
0x14005d7f2  call    NetioQueryValueKey
0x14005d7f7  mov     r9d, eax
0x14005d7fa  mov     rbx, [rsp+330h+var_2E0]
0x14005d7ff  test    rbx, rbx
0x14005d802  jz      short loc_14005D865
0x14005d804  xor     edx, edx; Val
0x14005d806  lea     rcx, [rbp+230h+pszDest]; void *
0x14005d80a  mov     r8d, 200h; Size
0x14005d810  call    memset
0x14005d815  mov     r9, rbx
0x14005d818  lea     r8, aRegistryMachin_4; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x14005d81f  mov     edx, 100h; cchDest
0x14005d824  lea     rcx, [rbp+230h+pszDest]; pszDest
0x14005d828  call    RtlStringCchPrintfW
0x14005d82d  mov     r9d, eax
0x14005d830  test    eax, eax
0x14005d832  js      short loc_14005D865
0x14005d834  xorps   xmm0, xmm0
0x14005d837  lea     rdx, [rbp+230h+pszDest]; SourceString
0x14005d83b  lea     rcx, [rsp+330h+DestinationString]; DestinationString
0x14005d840  movups  xmmword ptr [rsp+330h+DestinationString.Length], xmm0
0x14005d845  call    cs:__imp_RtlInitUnicodeString
0x14005d84c  nop     dword ptr [rax+rax+00h]
0x14005d851  lea     rcx, [rsp+330h+DestinationString]; DriverServiceName
0x14005d856  call    cs:__imp_ZwLoadDriver
0x14005d85d  nop     dword ptr [rax+rax+00h]
0x14005d862  mov     r9d, eax
0x14005d865  mov     eax, cs:dword_14009A008
0x14005d86b  cmp     eax, 5
0x14005d86e  jbe     loc_14005D90A
0x14005d874  mov     rax, [r14+50h]
0x14005d878  lea     rdx, [rbp+230h+pszDest]
0x14005d87c  mov     rcx, [rax+28h]
0x14005d880  mov     [rbp+230h+var_290], rcx
0x14005d884  lea     rcx, [rbp+230h+var_280]
0x14005d888  mov     [rbp+230h+var_288], 10h
0x14005d890  call    _tlgCreate1Sz_wchar_t
0x14005d895  mov     dword ptr [rsp+330h+KeyHandle], r9d
0x14005d89a  lea     rax, [rsp+330h+KeyHandle]
0x14005d89f  mov     [rbp+230h+var_270], rax
0x14005d8a3  mov     [rbp+230h+var_268], 4
0x14005d8ab  test    rdi, rdi
0x14005d8ae  jz      short loc_14005D8B4
0x14005d8b0  mov     eax, [rdi]
0x14005d8b2  jmp     short loc_14005D8B6
0x14005d8b4  xor     eax, eax
0x14005d8b6  mov     [rsp+330h+var_2F0], eax
0x14005d8ba  lea     rdx, byte_1400907CF
0x14005d8c1  lea     rax, [rsp+330h+var_2F0]
0x14005d8c6  mov     [rbp+230h+var_258], 4
0x14005d8ce  mov     [rbp+230h+var_260], rax
0x14005d8d2  lea     rcx, dword_14009A008
0x14005d8d9  lea     rax, [rsp+330h+var_2E0]
0x14005d8de  mov     dword ptr [rsp+330h+var_2E0], esi
0x14005d8e2  mov     [rbp+230h+var_250], rax
0x14005d8e6  xor     r9d, r9d
0x14005d8e9  lea     rax, [rbp+230h+var_2B0]
0x14005d8ed  mov     [rbp+230h+var_248], 4
0x14005d8f5  mov     [rsp+330h+var_308], rax
0x14005d8fa  xor     r8d, r8d
0x14005d8fd  mov     [rsp+330h+Tag], 7
0x14005d905  call    _tlgWriteTransfer_EtwWriteTransfer
0x14005d90a  test    rdi, rdi
0x14005d90d  jz      short loc_14005D920
0x14005d90f  xor     edx, edx; Tag
0x14005d911  mov     rcx, rdi; P
0x14005d914  call    cs:__imp_ExFreePoolWithTag
0x14005d91b  nop     dword ptr [rax+rax+00h]
0x14005d920  test    rbx, rbx
0x14005d923  jz      short loc_14005D936
0x14005d925  xor     edx, edx; Tag
0x14005d927  mov     rcx, rbx; P
0x14005d92a  call    cs:__imp_ExFreePoolWithTag
0x14005d931  nop     dword ptr [rax+rax+00h]
0x14005d936  cmp     qword ptr [rsp+330h+KeyHandle+4], 0
0x14005d93c  jz      short loc_14005D948
0x14005d93e  lea     rcx, [rsp+330h+KeyHandle+4]
0x14005d943  call    NetioCloseKey
0x14005d948  cmp     [rsp+330h+GuidString.Buffer], 0
0x14005d94e  jz      short loc_14005D961
0x14005d950  lea     rcx, [rsp+330h+GuidString]; UnicodeString
0x14005d955  call    cs:__imp_RtlFreeUnicodeString
0x14005d95c  nop     dword ptr [rax+rax+00h]
0x14005d961  mov     rcx, [rbp+230h+var_40]
0x14005d968  xor     rcx, rsp; StackCookie
0x14005d96b  call    __security_check_cookie
0x14005d970  add     rsp, 308h
0x14005d977  pop     r14
0x14005d979  pop     r12
0x14005d97b  pop     rdi
0x14005d97c  pop     rsi
0x14005d97d  pop     rbx
0x14005d97e  pop     rbp
0x14005d97f  retn
```
