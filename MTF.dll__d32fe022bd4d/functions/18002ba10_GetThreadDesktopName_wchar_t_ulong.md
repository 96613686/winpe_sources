# GetThreadDesktopName(wchar_t *,ulong)

- ea: `0x18002ba10`
- end: `0x18002bb13`
- name: `?GetThreadDesktopName@@YAHPEA_WK@Z`
- size: `259`
- prototype: `__int64 __fastcall(wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001fc54`

## callees

- `0x18002ba10`
- `0x18002bca0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ba38`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ba38`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x18002ba40`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x18002ba40`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x18002ba66`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x18002ba66`

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
  int *v9; // r8
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
    v9 = &dword_180033D2C;
    v6 = 260;
    do
    {
      if ( !v8 )
        break;
      if ( !*(_WORD *)v9 )
        break;
      *a1 = *(_WORD *)v9;
      v9 = (int *)((char *)v9 + 2);
      ++a1;
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
0x18002ba10  mov     [rsp+arg_8], rbx
0x18002ba15  push    rdi
0x18002ba16  sub     rsp, 260h
0x18002ba1d  mov     rax, cs:__security_cookie
0x18002ba24  xor     rax, rsp
0x18002ba27  mov     [rsp+268h+var_18], rax
0x18002ba2f  xor     edi, edi
0x18002ba31  mov     rbx, rcx
0x18002ba34  mov     [rsp+268h+nLengthNeeded], edi
0x18002ba38  call    cs:__imp_GetCurrentThreadId
0x18002ba3e  mov     ecx, eax; dwThreadId
0x18002ba40  call    cs:__imp_GetThreadDesktop
0x18002ba46  test    rax, rax
0x18002ba49  jz      short loc_18002BAA7
0x18002ba4b  lea     rcx, [rsp+268h+nLengthNeeded]
0x18002ba50  mov     r9d, 208h; nLength
0x18002ba56  mov     [rsp+268h+lpnLengthNeeded], rcx; lpnLengthNeeded
0x18002ba5b  lea     r8, [rsp+268h+pvInfo]; pvInfo
0x18002ba60  mov     rcx, rax; hObj
0x18002ba63  lea     edx, [rdi+2]; nIndex
0x18002ba66  call    cs:__imp_GetUserObjectInformationW
0x18002ba6c  test    eax, eax
0x18002ba6e  jz      short loc_18002BAA7
0x18002ba70  mov     ecx, 7FFFFFFEh
0x18002ba75  lea     r8, [rsp+268h+pvInfo]
0x18002ba7a  mov     eax, 104h
0x18002ba7f  lea     edx, [rdi+1]
0x18002ba82  test    rcx, rcx
0x18002ba85  jz      short loc_18002BAE2
0x18002ba87  movzx   r9d, word ptr [r8]
0x18002ba8b  test    r9w, r9w
0x18002ba8f  jz      short loc_18002BAE2
0x18002ba91  mov     [rbx], r9w
0x18002ba95  add     r8, 2
0x18002ba99  add     rbx, 2
0x18002ba9d  sub     rcx, rdx
0x18002baa0  sub     rax, rdx
0x18002baa3  jnz     short loc_18002BA82
0x18002baa5  jmp     short loc_18002BAE2
0x18002baa7  mov     ecx, 7FFFFFFEh
0x18002baac  lea     r8, dword_180033D2C
0x18002bab3  mov     eax, 104h
0x18002bab8  mov     edx, 1
0x18002babd  test    rcx, rcx
0x18002bac0  jz      short loc_18002BAE0
0x18002bac2  movzx   r9d, word ptr [r8]
0x18002bac6  test    r9w, r9w
0x18002baca  jz      short loc_18002BAE0
0x18002bacc  mov     [rbx], r9w
0x18002bad0  add     r8, 2
0x18002bad4  add     rbx, 2
0x18002bad8  sub     rcx, rdx
0x18002badb  sub     rax, rdx
0x18002bade  jnz     short loc_18002BABD
0x18002bae0  mov     edx, edi
0x18002bae2  test    rax, rax
0x18002bae5  lea     rcx, [rbx-2]
0x18002bae9  mov     eax, edx
0x18002baeb  cmovnz  rcx, rbx
0x18002baef  mov     [rcx], di
0x18002baf2  mov     rcx, [rsp+268h+var_18]
0x18002bafa  xor     rcx, rsp; StackCookie
0x18002bafd  call    __security_check_cookie
0x18002bb02  mov     rbx, [rsp+268h+arg_8]
0x18002bb0a  add     rsp, 260h
0x18002bb11  pop     rdi
0x18002bb12  retn
```
