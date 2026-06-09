# GetThreadDesktopName(wchar_t *,ulong)

- ea: `0x180055b74`
- end: `0x180055c77`
- name: `?GetThreadDesktopName@@YAHPEA_WK@Z`
- size: `259`
- prototype: `__int64 __fastcall(wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002879c`

## callees

- `0x180002240`
- `0x180055b74`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180055b9c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180055b9c`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x180055ba4`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x180055ba4`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x180055bca`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x180055bca`

## pseudocode

```c
__int64 __fastcall GetThreadDesktopName(wchar_t *a1)
{
  DWORD CurrentThreadId; // eax
  HDESK ThreadDesktop; // rax
  __int64 v4; // rcx
  wchar_t *v5; // r8
  __int64 v6; // rax
  unsigned int v7; // edx
  __int64 v8; // rcx
  const WCHAR *v9; // r8
  bool v10; // zf
  wchar_t *v11; // rcx
  __int64 result; // rax
  DWORD nLengthNeeded[4]; // [rsp+30h] [rbp-238h] BYREF
  _BYTE pvInfo[528]; // [rsp+40h] [rbp-228h] BYREF

  nLengthNeeded[0] = 0;
  CurrentThreadId = GetCurrentThreadId();
  ThreadDesktop = GetThreadDesktop(CurrentThreadId);
  if ( ThreadDesktop && GetUserObjectInformationW(ThreadDesktop, 2, pvInfo, 0x208u, nLengthNeeded) )
  {
    v4 = 2147483646;
    v5 = (wchar_t *)pvInfo;
    v6 = 260;
    v7 = 1;
    do
    {
      if ( !v4 )
        break;
      if ( !*v5 )
        break;
      *a1++ = *v5++;
      --v4;
      --v6;
    }
    while ( v6 );
  }
  else
  {
    v8 = 2147483646;
    v9 = &sourceString;
    v6 = 260;
    do
    {
      if ( !v8 )
        break;
      if ( !*v9 )
        break;
      *a1++ = *v9++;
      --v8;
      --v6;
    }
    while ( v6 );
    v7 = 0;
  }
  v10 = v6 == 0;
  v11 = a1 - 1;
  result = v7;
  if ( !v10 )
    v11 = a1;
  *v11 = 0;
  return result;
}

```

## disassembly

```asm
0x180055b74  mov     [rsp+arg_8], rbx
0x180055b79  push    rdi
0x180055b7a  sub     rsp, 260h
0x180055b81  mov     rax, cs:__security_cookie
0x180055b88  xor     rax, rsp
0x180055b8b  mov     [rsp+268h+var_18], rax
0x180055b93  xor     edi, edi
0x180055b95  mov     rbx, rcx
0x180055b98  mov     [rsp+268h+nLengthNeeded], edi
0x180055b9c  call    cs:__imp_GetCurrentThreadId
0x180055ba2  mov     ecx, eax; dwThreadId
0x180055ba4  call    cs:__imp_GetThreadDesktop
0x180055baa  test    rax, rax
0x180055bad  jz      short loc_180055C0B
0x180055baf  lea     rcx, [rsp+268h+nLengthNeeded]
0x180055bb4  mov     r9d, 208h; nLength
0x180055bba  mov     [rsp+268h+lpnLengthNeeded], rcx; lpnLengthNeeded
0x180055bbf  lea     r8, [rsp+268h+pvInfo]; pvInfo
0x180055bc4  mov     rcx, rax; hObj
0x180055bc7  lea     edx, [rdi+2]; nIndex
0x180055bca  call    cs:__imp_GetUserObjectInformationW
0x180055bd0  test    eax, eax
0x180055bd2  jz      short loc_180055C0B
0x180055bd4  mov     ecx, 7FFFFFFEh
0x180055bd9  lea     r8, [rsp+268h+pvInfo]
0x180055bde  mov     eax, 104h
0x180055be3  lea     edx, [rdi+1]
0x180055be6  test    rcx, rcx
0x180055be9  jz      short loc_180055C46
0x180055beb  movzx   r9d, word ptr [r8]
0x180055bef  test    r9w, r9w
0x180055bf3  jz      short loc_180055C46
0x180055bf5  mov     [rbx], r9w
0x180055bf9  add     r8, 2
0x180055bfd  add     rbx, 2
0x180055c01  sub     rcx, rdx
0x180055c04  sub     rax, rdx
0x180055c07  jnz     short loc_180055BE6
0x180055c09  jmp     short loc_180055C46
0x180055c0b  mov     ecx, 7FFFFFFEh
0x180055c10  lea     r8, sourceString
0x180055c17  mov     eax, 104h
0x180055c1c  mov     edx, 1
0x180055c21  test    rcx, rcx
0x180055c24  jz      short loc_180055C44
0x180055c26  movzx   r9d, word ptr [r8]
0x180055c2a  test    r9w, r9w
0x180055c2e  jz      short loc_180055C44
0x180055c30  mov     [rbx], r9w
0x180055c34  add     r8, 2
0x180055c38  add     rbx, 2
0x180055c3c  sub     rcx, rdx
0x180055c3f  sub     rax, rdx
0x180055c42  jnz     short loc_180055C21
0x180055c44  mov     edx, edi
0x180055c46  test    rax, rax
0x180055c49  lea     rcx, [rbx-2]
0x180055c4d  mov     eax, edx
0x180055c4f  cmovnz  rcx, rbx
0x180055c53  mov     [rcx], di
0x180055c56  mov     rcx, [rsp+268h+var_18]
0x180055c5e  xor     rcx, rsp; StackCookie
0x180055c61  call    __security_check_cookie
0x180055c66  mov     rbx, [rsp+268h+arg_8]
0x180055c6e  add     rsp, 260h
0x180055c75  pop     rdi
0x180055c76  retn
```
