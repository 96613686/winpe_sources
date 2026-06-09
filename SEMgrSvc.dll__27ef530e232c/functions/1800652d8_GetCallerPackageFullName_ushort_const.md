# GetCallerPackageFullName(ushort * const)

- ea: `0x1800652d8`
- end: `0x180065415`
- name: `?GetCallerPackageFullName@@YAJQEAG@Z`
- size: `317`
- prototype: `__int64 __fastcall(PWSTR packageFullName)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180065014`
- `0x1800651ec`

## callees

- `0x18000c944`
- `0x18000c964`
- `0x180014898`
- `0x1800652d8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800652f3`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800652f3`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18006539e`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800653a9`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18006539e`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800653a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065343`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065343`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065356`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065356`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180065365`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180065365`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006537c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006537c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180065327`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006534e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800653fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180065327`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006534e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800653fd`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x1800653c4`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x1800653c4`

## string_xrefs

- `0x180065304`: `onecoreuap\ds\nfc\product\semanagement\common\seutils\src\accesscontrolhelper.cpp`
- `0x18006538b`: `onecoreuap\ds\nfc\product\semanagement\common\seutils\src\accesscontrolhelper.cpp`
- `0x1800653d3`: `onecoreuap\ds\nfc\product\semanagement\common\seutils\src\accesscontrolhelper.cpp`

## pseudocode

```c
__int64 __fastcall GetCallerPackageFullName(PWSTR packageFullName)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  HANDLE v5; // rdi
  DWORD LastError; // ebx
  HANDLE CurrentThread; // rax
  const char *v8; // r9
  unsigned int PackageFullNameFromToken; // eax
  unsigned int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  UINT32 packageFullNameLength; // [rsp+38h] [rbp+10h] BYREF
  HANDLE hObject; // [rsp+40h] [rbp+18h] BYREF

  hObject = 0;
  v2 = CoImpersonateClient();
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x84,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\seutils\\src\\accesscontrolhelper.cpp",
      (const char *)(unsigned int)v2,
      v10);
LABEL_3:
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    return v3;
  }
  v5 = hObject;
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    LastError = GetLastError();
    CloseHandle(v5);
    SetLastError(LastError);
  }
  hObject = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &hObject) )
  {
    v3 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x87,
           (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\seutils\\src\\accesscontrolhelper.cpp",
           v8);
    CoRevertToSelf();
    goto LABEL_3;
  }
  CoRevertToSelf();
  packageFullNameLength = 128;
  PackageFullNameFromToken = GetPackageFullNameFromToken(hObject, &packageFullNameLength, packageFullName);
  if ( PackageFullNameFromToken )
  {
    v3 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x8B,
           (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\seutils\\src\\accesscontrolhelper.cpp",
           (const char *)PackageFullNameFromToken,
           v10);
    goto LABEL_3;
  }
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  return 0;
}

```

## disassembly

```asm
0x1800652d8  mov     [rsp+arg_0], rbx
0x1800652dd  mov     [rsp+arg_18], rsi
0x1800652e2  push    rdi; unsigned int
0x1800652e3  sub     rsp, 20h
0x1800652e7  mov     rsi, rcx
0x1800652ea  mov     [rsp+28h+hObject], 0
0x1800652f3  call    cs:__imp_CoImpersonateClient
0x1800652f9  mov     ebx, eax
0x1800652fb  test    eax, eax
0x1800652fd  jns     short loc_180065334
0x1800652ff  mov     rcx, [rsp+28h]; this
0x180065304  lea     r8, aOnecoreuapDsNf_6; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x18006530b  mov     r9d, eax; char *
0x18006530e  mov     edx, 84h; void *
0x180065313  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065318  mov     rcx, [rsp+28h+hObject]; hObject
0x18006531d  lea     rdx, [rcx-1]
0x180065321  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180065325  ja      short loc_18006532D
0x180065327  call    cs:__imp_CloseHandle
0x18006532d  mov     eax, ebx
0x18006532f  jmp     loc_180065405
0x180065334  mov     rdi, [rsp+28h+hObject]
0x180065339  lea     rax, [rdi-1]
0x18006533d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180065341  ja      short loc_18006535C
0x180065343  call    cs:__imp_GetLastError
0x180065349  mov     rcx, rdi; hObject
0x18006534c  mov     ebx, eax
0x18006534e  call    cs:__imp_CloseHandle
0x180065354  mov     ecx, ebx; dwErrCode
0x180065356  call    cs:__imp_SetLastError
0x18006535c  mov     [rsp+28h+hObject], 0
0x180065365  call    cs:__imp_GetCurrentThread
0x18006536b  mov     edx, 8; DesiredAccess
0x180065370  lea     r9, [rsp+28h+hObject]; TokenHandle
0x180065375  mov     rcx, rax; ThreadHandle
0x180065378  lea     r8d, [rdx-7]; OpenAsSelf
0x18006537c  call    cs:__imp_OpenThreadToken
0x180065382  test    eax, eax
0x180065384  jnz     short loc_1800653A9
0x180065386  mov     rcx, [rsp+28h]; this
0x18006538b  lea     r8, aOnecoreuapDsNf_6; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x180065392  mov     edx, 87h; void *
0x180065397  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18006539c  mov     ebx, eax
0x18006539e  call    cs:__imp_CoRevertToSelf
0x1800653a4  jmp     loc_180065318
0x1800653a9  call    cs:__imp_CoRevertToSelf
0x1800653af  mov     rcx, [rsp+28h+hObject]; token
0x1800653b4  lea     rdx, [rsp+28h+packageFullNameLength]; packageFullNameLength
0x1800653b9  mov     r8, rsi; packageFullName
0x1800653bc  mov     [rsp+28h+packageFullNameLength], 80h
0x1800653c4  call    cs:__imp_GetPackageFullNameFromToken
0x1800653ca  test    eax, eax
0x1800653cc  jz      short loc_1800653EE
0x1800653ce  mov     rcx, [rsp+28h]; this
0x1800653d3  lea     r8, aOnecoreuapDsNf_6; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x1800653da  mov     r9d, eax; char *
0x1800653dd  mov     edx, 8Bh; void *
0x1800653e2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800653e7  mov     ebx, eax
0x1800653e9  jmp     loc_180065318
0x1800653ee  mov     rcx, [rsp+28h+hObject]; hObject
0x1800653f3  lea     rax, [rcx-1]
0x1800653f7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800653fb  ja      short loc_180065403
0x1800653fd  call    cs:__imp_CloseHandle
0x180065403  xor     eax, eax
0x180065405  mov     rbx, [rsp+28h+arg_0]
0x18006540a  mov     rsi, [rsp+28h+arg_18]
0x18006540f  add     rsp, 20h
0x180065413  pop     rdi
0x180065414  retn
```
