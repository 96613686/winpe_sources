# UtilGetProcessIntegrityRid(void *,ulong *)

- ea: `0x140011010`
- end: `0x140011146`
- name: `?UtilGetProcessIntegrityRid@@YAJPEAXPEAK@Z`
- size: `310`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001623c`

## callees

- `0x14000a9a4`
- `0x14000a9c4`
- `0x14000e404`
- `0x140011010`
- `0x1400114c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140011079`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140011079`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400110a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400110d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140011133`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400110a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400110d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140011133`

## string_xrefs

- `0x14001102f`: `onecore\windows\feedback\core\common\lib\utility.cpp`
- `0x1400110af`: `onecore\windows\feedback\core\common\lib\utility.cpp`
- `0x1400110fe`: `onecore\windows\feedback\core\common\lib\utility.cpp`

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
    v4 = 6018;
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
    v4 = 6019;
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
                  (void *)0x1786,
                  (unsigned int)"onecore\\windows\\feedback\\core\\common\\lib\\utility.cpp",
                  v9);
    goto LABEL_12;
  }
  if ( (unsigned __int64)hObject + 1 <= 1 )
  {
    LastError = -2147418113;
    v11 = 6023;
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
    v11 = 6025;
    goto LABEL_16;
  }
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  return 0;
}

```

## disassembly

```asm
0x140011010  mov     [rsp+arg_8], rbx
0x140011015  push    rdi
0x140011016  sub     rsp, 40h
0x14001101a  mov     rbx, rdx
0x14001101d  mov     rdi, rcx
0x140011020  test    rcx, rcx
0x140011023  jnz     short loc_14001104A
0x140011025  mov     edx, 1782h; void *
0x14001102a  mov     rcx, [rsp+48h]; this
0x14001102f  lea     r8, aOnecoreWindows_1; "onecore\\windows\\feedback\\core\\commo"...
0x140011036  mov     ebx, 80070057h
0x14001103b  mov     r9d, ebx; char *
0x14001103e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011043  mov     eax, ebx
0x140011045  jmp     loc_14001113B
0x14001104a  test    rbx, rbx
0x14001104d  jnz     short loc_140011056
0x14001104f  mov     edx, 1783h
0x140011054  jmp     short loc_14001102A
0x140011056  lea     rdx, [rsp+48h+hObject]
0x14001105b  mov     [rsp+48h+hObject], 0
0x140011064  lea     rcx, [rsp+48h+var_28]
0x140011069  call    ??$out_ptr@XV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@$$V@utl@@YA?A_PAEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z
0x14001106e  mov     r8, rax; TokenHandle
0x140011071  mov     edx, 8; DesiredAccess
0x140011076  mov     rcx, rdi; ProcessHandle
0x140011079  call    cs:__imp_OpenProcessToken
0x14001107f  mov     r8, [rsp+48h+var_28]
0x140011084  mov     edi, eax
0x140011086  test    r8, r8
0x140011089  jz      short loc_1400110A6
0x14001108b  mov     rdx, [rsp+48h+var_20]
0x140011090  mov     rcx, [rdx]; hObject
0x140011093  mov     [rdx], r8
0x140011096  lea     rdx, [rcx+1]
0x14001109a  cmp     rdx, 1
0x14001109e  jbe     short loc_1400110A6
0x1400110a0  call    cs:__imp_CloseHandle
0x1400110a6  test    edi, edi
0x1400110a8  jnz     short loc_1400110E0
0x1400110aa  mov     rcx, [rsp+48h]; this
0x1400110af  lea     r8, aOnecoreWindows_1; "onecore\\windows\\feedback\\core\\commo"...
0x1400110b6  mov     edx, 1786h; void *
0x1400110bb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400110c0  mov     ebx, eax
0x1400110c2  mov     rcx, [rsp+48h+hObject]; hObject
0x1400110c7  lea     rdx, [rcx+1]
0x1400110cb  cmp     rdx, 1
0x1400110cf  jbe     loc_140011043
0x1400110d5  call    cs:__imp_CloseHandle
0x1400110db  jmp     loc_140011043
0x1400110e0  mov     rcx, [rsp+48h+hObject]; TokenHandle
0x1400110e5  lea     rax, [rcx+1]
0x1400110e9  cmp     rax, 1
0x1400110ed  ja      short loc_14001110F
0x1400110ef  mov     ebx, 8000FFFFh
0x1400110f4  mov     edx, 1787h; void *
0x1400110f9  mov     rcx, [rsp+48h]; this
0x1400110fe  lea     r8, aOnecoreWindows_1; "onecore\\windows\\feedback\\core\\commo"...
0x140011105  mov     r9d, ebx; char *
0x140011108  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001110d  jmp     short loc_1400110C2
0x14001110f  mov     rdx, rbx; unsigned int *
0x140011112  call    ?UtilGetTokenIntegrityRid@@YAJPEAXPEAK@Z; UtilGetTokenIntegrityRid(void *,ulong *)
0x140011117  mov     ebx, eax
0x140011119  test    eax, eax
0x14001111b  jns     short loc_140011124
0x14001111d  mov     edx, 1789h
0x140011122  jmp     short loc_1400110F9
0x140011124  mov     rcx, [rsp+48h+hObject]; hObject
0x140011129  lea     rax, [rcx+1]
0x14001112d  cmp     rax, 1
0x140011131  jbe     short loc_140011139
0x140011133  call    cs:__imp_CloseHandle
0x140011139  xor     eax, eax
0x14001113b  mov     rbx, [rsp+48h+arg_8]
0x140011140  add     rsp, 40h
0x140011144  pop     rdi
0x140011145  retn
```
