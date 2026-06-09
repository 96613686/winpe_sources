# UtilGetProcessIntegrityRid(void *,ulong *)

- ea: `0x140011714`
- end: `0x140011863`
- name: `?UtilGetProcessIntegrityRid@@YAJPEAXPEAK@Z`
- size: `335`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140016e8c`

## callees

- `0x14000aab4`
- `0x14000aad4`
- `0x14000e6d8`
- `0x140011714`
- `0x140011c28`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14001177d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14001177d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400117aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400117e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140011849`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400117aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400117e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140011849`

## string_xrefs

- `0x140011733`: `onecore\windows\feedback\core\common\lib\utility.cpp`
- `0x1400117bf`: `onecore\windows\feedback\core\common\lib\utility.cpp`
- `0x140011814`: `onecore\windows\feedback\core\common\lib\utility.cpp`

## pseudocode

```c
__int64 __fastcall UtilGetProcessIntegrityRid(HANDLE ProcessHandle, unsigned int *a2)
{
  __int64 v4; // rdx
  unsigned int LastError; // ebx
  void **v7; // rax
  BOOL v8; // edi
  const char *v9; // r9
  void *v10; // rcx
  __int64 v11; // rdx
  void *v12; // [rsp+20h] [rbp-28h] BYREF
  void **v13; // [rsp+28h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HANDLE hObject; // [rsp+50h] [rbp+8h] BYREF

  if ( !ProcessHandle )
  {
    v4 = 6038;
LABEL_3:
    LastError = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\windows\\feedback\\core\\common\\lib\\utility.cpp",
      (const char *)0x80070057LL,
      (int)v12);
    return LastError;
  }
  if ( !a2 )
  {
    v4 = 6039;
    goto LABEL_3;
  }
  hObject = 0;
  v7 = (void **)utl::out_ptr<void,tlx::unique_any<tlx::file_handle_traits>,>(&v12, &hObject);
  v8 = OpenProcessToken(ProcessHandle, 8u, v7);
  if ( v12 )
  {
    v10 = *v13;
    *v13 = v12;
    if ( (unsigned __int64)v10 + 1 > 1 )
      CloseHandle(v10);
  }
  if ( !v8 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x179A,
                  (unsigned int)"onecore\\windows\\feedback\\core\\common\\lib\\utility.cpp",
                  v9);
    goto LABEL_12;
  }
  if ( (unsigned __int64)hObject + 1 <= 1 )
  {
    LastError = -2147418113;
    v11 = 6043;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\windows\\feedback\\core\\common\\lib\\utility.cpp",
      (const char *)LastError,
      (int)v12);
LABEL_12:
    if ( (unsigned __int64)hObject + 1 > 1 )
      CloseHandle(hObject);
    return LastError;
  }
  LastError = UtilGetTokenIntegrityRid(hObject, a2);
  if ( (LastError & 0x80000000) != 0 )
  {
    v11 = 6045;
    goto LABEL_16;
  }
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  return 0;
}

```

## disassembly

```asm
0x140011714  mov     [rsp+arg_8], rbx
0x140011719  push    rdi
0x14001171a  sub     rsp, 40h
0x14001171e  mov     rbx, rdx
0x140011721  mov     rdi, rcx
0x140011724  test    rcx, rcx
0x140011727  jnz     short loc_14001174E
0x140011729  mov     edx, 1796h; void *
0x14001172e  mov     rcx, [rsp+48h]; this
0x140011733  lea     r8, aOnecoreWindows_1; "onecore\\windows\\feedback\\core\\commo"...
0x14001173a  mov     ebx, 80070057h
0x14001173f  mov     r9d, ebx; char *
0x140011742  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011747  mov     eax, ebx
0x140011749  jmp     loc_140011857
0x14001174e  test    rbx, rbx
0x140011751  jnz     short loc_14001175A
0x140011753  mov     edx, 1797h
0x140011758  jmp     short loc_14001172E
0x14001175a  lea     rdx, [rsp+48h+hObject]
0x14001175f  mov     [rsp+48h+hObject], 0
0x140011768  lea     rcx, [rsp+48h+var_28]
0x14001176d  call    ??$out_ptr@XV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@$$V@utl@@YA?A_PAEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z
0x140011772  mov     r8, rax; TokenHandle
0x140011775  mov     edx, 8; DesiredAccess
0x14001177a  mov     rcx, rdi; ProcessHandle
0x14001177d  call    cs:__imp_OpenProcessToken
0x140011784  nop     dword ptr [rax+rax+00h]
0x140011789  mov     r8, [rsp+48h+var_28]
0x14001178e  mov     edi, eax
0x140011790  test    r8, r8
0x140011793  jz      short loc_1400117B6
0x140011795  mov     rdx, [rsp+48h+var_20]
0x14001179a  mov     rcx, [rdx]; hObject
0x14001179d  mov     [rdx], r8
0x1400117a0  lea     rdx, [rcx+1]
0x1400117a4  cmp     rdx, 1
0x1400117a8  jbe     short loc_1400117B6
0x1400117aa  call    cs:__imp_CloseHandle
0x1400117b1  nop     dword ptr [rax+rax+00h]
0x1400117b6  test    edi, edi
0x1400117b8  jnz     short loc_1400117F6
0x1400117ba  mov     rcx, [rsp+48h]; this
0x1400117bf  lea     r8, aOnecoreWindows_1; "onecore\\windows\\feedback\\core\\commo"...
0x1400117c6  mov     edx, 179Ah; void *
0x1400117cb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400117d0  mov     ebx, eax
0x1400117d2  mov     rcx, [rsp+48h+hObject]; hObject
0x1400117d7  lea     rdx, [rcx+1]
0x1400117db  cmp     rdx, 1
0x1400117df  jbe     loc_140011747
0x1400117e5  call    cs:__imp_CloseHandle
0x1400117ec  nop     dword ptr [rax+rax+00h]
0x1400117f1  jmp     loc_140011747
0x1400117f6  mov     rcx, [rsp+48h+hObject]; TokenHandle
0x1400117fb  lea     rax, [rcx+1]
0x1400117ff  cmp     rax, 1
0x140011803  ja      short loc_140011825
0x140011805  mov     ebx, 8000FFFFh
0x14001180a  mov     edx, 179Bh; void *
0x14001180f  mov     rcx, [rsp+48h]; this
0x140011814  lea     r8, aOnecoreWindows_1; "onecore\\windows\\feedback\\core\\commo"...
0x14001181b  mov     r9d, ebx; char *
0x14001181e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011823  jmp     short loc_1400117D2
0x140011825  mov     rdx, rbx; unsigned int *
0x140011828  call    ?UtilGetTokenIntegrityRid@@YAJPEAXPEAK@Z; UtilGetTokenIntegrityRid(void *,ulong *)
0x14001182d  mov     ebx, eax
0x14001182f  test    eax, eax
0x140011831  jns     short loc_14001183A
0x140011833  mov     edx, 179Dh
0x140011838  jmp     short loc_14001180F
0x14001183a  mov     rcx, [rsp+48h+hObject]; hObject
0x14001183f  lea     rax, [rcx+1]
0x140011843  cmp     rax, 1
0x140011847  jbe     short loc_140011855
0x140011849  call    cs:__imp_CloseHandle
0x140011850  nop     dword ptr [rax+rax+00h]
0x140011855  xor     eax, eax
0x140011857  mov     rbx, [rsp+48h+arg_8]
0x14001185c  add     rsp, 40h
0x140011860  pop     rdi
0x140011861  retn
```
