# LogAppName(ushort *,ushort *,ulong)

- ea: `0x1800303fc`
- end: `0x18003062c`
- name: `?LogAppName@@YAXPEAG0K@Z`
- size: `560`
- prototype: `void __fastcall(wchar_t *Filename, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task`

## callers

- `0x180016250`
- `0x1800358a0`

## callees

- `0x1800303fc`
- `0x18003a580`
- `0x18003af10`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18003054b`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18003054b`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18003049e`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180030520`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180030565`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180030597`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800305f1`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18003049e`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180030520`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180030565`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180030597`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800305f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003056e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003056e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800305fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800305fc`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180030481`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180030481`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800304c1`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800304c1`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800304fe`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800304fe`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x1800305d4`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x1800305d4`

## pseudocode

```c
void __fastcall LogAppName(wchar_t *Filename, unsigned __int16 *a2)
{
  DWORD v4; // r14d
  HANDLE v5; // r15
  const wchar_t *v6; // r8
  __int64 v7; // rax
  DWORD dwSize; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL v9[3]; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD RpcCallAttributes[2]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v11[56]; // [rsp+78h] [rbp-88h] BYREF
  DWORD dwProcessId; // [rsp+B0h] [rbp-50h]
  WCHAR ExeName[2]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v14[524]; // [rsp+F4h] [rbp-Ch] BYREF

  memset(v9, 0, sizeof(v9));
  if ( !Filename || !a2 )
    return;
  memset_0(v11, 0, 0x70u);
  RpcCallAttributes[0] = 2;
  RpcCallAttributes[1] = 16;
  if ( RpcServerInqCallAttributesW(0, RpcCallAttributes) < 0 )
  {
    _o_wcsncpy_s(Filename, 256, L"Unknown", -1);
    return;
  }
  v4 = dwProcessId;
  if ( dwProcessId == 4 )
  {
    v6 = L"System";
  }
  else
  {
    v5 = OpenProcess(0x1000u, 0, dwProcessId);
    if ( v5 )
    {
      *(_DWORD *)ExeName = 0;
      memset_0(v14, 0, 0x206u);
      dwSize = 261;
      if ( !QueryFullProcessImageNameW(v5, 0, ExeName, &dwSize) )
        _o_wcsncpy_s(Filename, 256, L"Unknown", -1);
      if ( _wsplitpath_s(ExeName, 0, 0, 0, 0, Filename, 0x100u, 0, 0) )
        _o_wcsncpy_s(Filename, 256, L"Unknown", -1);
      CloseHandle(v5);
      goto LABEL_15;
    }
    v6 = L"Unknown";
  }
  _o_wcsncpy_s(Filename, 256, v6, -1);
LABEL_15:
  v7 = -1;
  do
    ++v7;
  while ( Filename[v7] );
  if ( v7 == 11 && v4 != 4 )
  {
    LODWORD(v9[0]) = v4;
    HIDWORD(v9[0]) = NtCurrentTeb()->SubProcessTag;
    if ( !(unsigned int)I_QueryTagInformation(0, 1, v9) )
    {
      if ( v9[2] )
      {
        _o_wcsncpy_s(a2, 256, v9[2], -1);
        LocalFree(v9[2]);
      }
    }
  }
}

```

## disassembly

```asm
0x1800303fc  mov     [rsp-8+arg_10], rbx
0x180030401  push    rbp
0x180030402  push    rsi
0x180030403  push    rdi
0x180030404  push    r12
0x180030406  push    r13
0x180030408  push    r14
0x18003040a  push    r15
0x18003040c  lea     rbp, [rsp-210h]
0x180030414  sub     rsp, 310h
0x18003041b  mov     rax, cs:__security_cookie
0x180030422  xor     rax, rsp
0x180030425  mov     [rbp+240h+var_40], rax
0x18003042c  xor     r13d, r13d
0x18003042f  xor     eax, eax
0x180030431  mov     [rsp+340h+var_2E8], r13d
0x180030436  xorps   xmm0, xmm0
0x180030439  mov     [rsp+340h+var_2D4], eax
0x18003043d  mov     r12, rdx
0x180030440  mov     rsi, rcx
0x180030443  movups  xmmword ptr [rsp+340h+hMem], xmm0
0x180030448  test    rcx, rcx
0x18003044b  jz      loc_180030602
0x180030451  test    rdx, rdx
0x180030454  jz      loc_180030602
0x18003045a  xor     edx, edx; Val
0x18003045c  lea     r8d, [r13+70h]; Size
0x180030460  lea     rcx, [rsp+340h+var_2C8]; void *
0x180030465  call    memset_0
0x18003046a  lea     rdx, [rsp+340h+RpcCallAttributes]; RpcCallAttributes
0x18003046f  mov     [rsp+340h+RpcCallAttributes], 2
0x180030477  xor     ecx, ecx; ClientBinding
0x180030479  mov     [rsp+340h+var_2CC], 10h
0x180030481  call    cs:__imp_RpcServerInqCallAttributesW
0x180030487  test    eax, eax
0x180030489  jns     short loc_1800304A9
0x18003048b  or      r9, 0FFFFFFFFFFFFFFFFh
0x18003048f  lea     r8, aUnknown; "Unknown"
0x180030496  mov     edx, 100h
0x18003049b  mov     rcx, rsi
0x18003049e  call    cs:__imp__o_wcsncpy_s
0x1800304a4  jmp     loc_180030602
0x1800304a9  mov     r14d, [rbp+240h+dwProcessId]
0x1800304ad  cmp     r14d, 4
0x1800304b1  jz      loc_18003057F
0x1800304b7  mov     r8d, r14d; dwProcessId
0x1800304ba  xor     edx, edx; bInheritHandle
0x1800304bc  mov     ecx, 1000h; dwDesiredAccess
0x1800304c1  call    cs:__imp_OpenProcess
0x1800304c7  mov     r15, rax
0x1800304ca  test    rax, rax
0x1800304cd  jz      loc_180030576
0x1800304d3  xor     edx, edx; Val
0x1800304d5  mov     dword ptr [rbp+240h+ExeName], r13d
0x1800304d9  mov     r8d, 206h; Size
0x1800304df  lea     rcx, [rbp+240h+var_24C]; void *
0x1800304e3  call    memset_0
0x1800304e8  lea     r9, [rsp+340h+dwSize]; lpdwSize
0x1800304ed  mov     [rsp+340h+dwSize], 105h
0x1800304f5  lea     r8, [rbp+240h+ExeName]; lpExeName
0x1800304f9  xor     edx, edx; dwFlags
0x1800304fb  mov     rcx, r15; hProcess
0x1800304fe  call    cs:__imp_QueryFullProcessImageNameW
0x180030504  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180030508  mov     edi, 100h
0x18003050d  test    eax, eax
0x18003050f  jnz     short loc_180030526
0x180030511  mov     r9, rbx
0x180030514  lea     r8, aUnknown; "Unknown"
0x18003051b  mov     edx, edi
0x18003051d  mov     rcx, rsi
0x180030520  call    cs:__imp__o_wcsncpy_s
0x180030526  mov     [rsp+340h+ExtCount], r13; ExtCount
0x18003052b  lea     rcx, [rbp+240h+ExeName]; FullPath
0x18003052f  mov     [rsp+340h+Ext], r13; Ext
0x180030534  xor     r9d, r9d; Dir
0x180030537  mov     [rsp+340h+FilenameCount], rdi; FilenameCount
0x18003053c  xor     r8d, r8d; DriveCount
0x18003053f  mov     [rsp+340h+Filename], rsi; Filename
0x180030544  xor     edx, edx; Drive
0x180030546  mov     [rsp+340h+DirCount], r13; DirCount
0x18003054b  call    cs:__imp__wsplitpath_s
0x180030551  test    eax, eax
0x180030553  jz      short loc_18003056B
0x180030555  mov     r9, rbx
0x180030558  lea     r8, aUnknown; "Unknown"
0x18003055f  mov     rdx, rdi
0x180030562  mov     rcx, rsi
0x180030565  call    cs:__imp__o_wcsncpy_s
0x18003056b  mov     rcx, r15; hObject
0x18003056e  call    cs:__imp_CloseHandle
0x180030574  jmp     short loc_18003059D
0x180030576  lea     r8, aUnknown; "Unknown"
0x18003057d  jmp     short loc_180030586
0x18003057f  lea     r8, aSystem; "System"
0x180030586  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003058a  mov     edi, 100h
0x18003058f  mov     r9, rbx
0x180030592  mov     edx, edi
0x180030594  mov     rcx, rsi
0x180030597  call    cs:__imp__o_wcsncpy_s
0x18003059d  mov     rax, rbx
0x1800305a0  inc     rax
0x1800305a3  cmp     [rsi+rax*2], r13w
0x1800305a8  jnz     short loc_1800305A0
0x1800305aa  cmp     rax, 0Bh
0x1800305ae  jnz     short loc_180030602
0x1800305b0  cmp     r14d, 4
0x1800305b4  jz      short loc_180030602
0x1800305b6  mov     [rsp+340h+var_2E8], r14d
0x1800305bb  lea     r8, [rsp+340h+var_2E8]
0x1800305c0  mov     rax, gs:1720h
0x1800305c9  mov     edx, 1
0x1800305ce  xor     ecx, ecx
0x1800305d0  mov     dword ptr [rsp+340h+hMem], eax
0x1800305d4  call    cs:__imp_I_QueryTagInformation
0x1800305da  test    eax, eax
0x1800305dc  jnz     short loc_180030602
0x1800305de  mov     r8, [rsp+340h+hMem+0Ch]
0x1800305e3  test    r8, r8
0x1800305e6  jz      short loc_180030602
0x1800305e8  mov     r9, rbx
0x1800305eb  mov     rdx, rdi
0x1800305ee  mov     rcx, r12
0x1800305f1  call    cs:__imp__o_wcsncpy_s
0x1800305f7  mov     rcx, [rsp+340h+hMem+0Ch]; hMem
0x1800305fc  call    cs:__imp_LocalFree
0x180030602  mov     rcx, [rbp+240h+var_40]
0x180030609  xor     rcx, rsp; StackCookie
0x18003060c  call    __security_check_cookie
0x180030611  mov     rbx, [rsp+340h+arg_10]
0x180030619  add     rsp, 310h
0x180030620  pop     r15
0x180030622  pop     r14
0x180030624  pop     r13
0x180030626  pop     r12
0x180030628  pop     rdi
0x180030629  pop     rsi
0x18003062a  pop     rbp
0x18003062b  retn
```
