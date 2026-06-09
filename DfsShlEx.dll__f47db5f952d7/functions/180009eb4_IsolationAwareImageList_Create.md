# IsolationAwareImageList_Create

- ea: `0x180009eb4`
- end: `0x180009f95`
- name: `IsolationAwareImageList_Create`
- size: `225`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180008eac`

## callees

- `0x180006dfc`
- `0x180009c18`
- `0x180009eb4`
- `0x18000c010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180009f87`
- `KERNEL32!SetLastError` at `0x18000b222`
- `KERNEL32!SetLastError` at `0x180009f87`
- `KERNEL32!SetLastError` at `0x18000b222`
- `KERNEL32!DeactivateActCtx` at `0x180009f7b`
- `KERNEL32!DeactivateActCtx` at `0x18000b216`
- `KERNEL32!DeactivateActCtx` at `0x180009f7b`
- `KERNEL32!DeactivateActCtx` at `0x18000b216`
- `KERNEL32!GetLastError` at `0x180009f66`
- `KERNEL32!GetLastError` at `0x18000b202`
- `KERNEL32!GetLastError` at `0x180009f66`
- `KERNEL32!GetLastError` at `0x18000b202`

## string_xrefs

- `0x180009f0d`: `ImageList_Create`

## pseudocode

```c
__int64 __fastcall IsolationAwareImageList_Create(unsigned int a1, unsigned int a2, __int64 a3, unsigned int a4)
{
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD); // rbx
  __int64 v10; // rax
  int v11; // esi
  DWORD LastError; // ebx
  ULONG_PTR ulCookie; // [rsp+30h] [rbp-38h] BYREF
  __int64 v14; // [rsp+38h] [rbp-30h]

  v7 = 0;
  v14 = 0;
  v8 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))`IsolationAwareImageList_Create'::`2'::s_pfn;
  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0;
  }
  if ( !v8 )
  {
    v10 = CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY("ImageList_Create");
    v8 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))v10;
    if ( !v10 )
      goto LABEL_9;
    `IsolationAwareImageList_Create'::`2'::s_pfn = v10;
  }
  v7 = v8(a1, a2, 0, a4, 0);
  v14 = v7;
LABEL_9:
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( v7 )
    {
      v11 = 0;
      LastError = 0;
    }
    else
    {
      v11 = 1;
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v11 )
      SetLastError(LastError);
  }
  return v7;
}

```

## disassembly

```asm
0x180009eb4  push    rbx
0x180009eb6  push    rsi
0x180009eb7  push    rdi
0x180009eb8  push    r14
0x180009eba  push    r15
0x180009ebc  sub     rsp, 40h
0x180009ec0  mov     esi, r9d
0x180009ec3  mov     r14d, edx
0x180009ec6  mov     r15d, ecx
0x180009ec9  xor     edi, edi
0x180009ecb  mov     [rsp+68h+var_30], rdi
0x180009ed0  mov     rbx, cs:?s_pfn@?1??IsolationAwareImageList_Create@@9@4P6APEAU_IMAGELIST@@HHIHH@ZEA; _IMAGELIST * (*`IsolationAwareImageList_Create'::`2'::s_pfn)(int,int,uint,int,int)
0x180009ed7  mov     [rsp+68h+ulCookie], rdi
0x180009edc  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, edi
0x180009ee2  jnz     short loc_180009F08
0x180009ee4  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, edi
0x180009eea  jnz     short loc_180009F08
0x180009eec  lea     rcx, [rsp+68h+ulCookie]; lpCookie
0x180009ef1  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x180009ef6  test    eax, eax
0x180009ef8  jnz     short loc_180009F08
0x180009efa  xor     eax, eax
0x180009efc  add     rsp, 40h
0x180009f00  pop     r15
0x180009f02  pop     r14
0x180009f04  pop     rdi
0x180009f05  pop     rsi
0x180009f06  pop     rbx
0x180009f07  retn
0x180009f08  test    rbx, rbx
0x180009f0b  jnz     short loc_180009F28
0x180009f0d  lea     rcx, aImagelistCreat; "ImageList_Create"
0x180009f14  call    CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x180009f19  mov     rbx, rax
0x180009f1c  test    rax, rax
0x180009f1f  jz      short loc_180009F4C
0x180009f21  mov     cs:?s_pfn@?1??IsolationAwareImageList_Create@@9@4P6APEAU_IMAGELIST@@HHIHH@ZEA, rax; _IMAGELIST * (*`IsolationAwareImageList_Create'::`2'::s_pfn)(int,int,uint,int,int)
0x180009f28  mov     [rsp+68h+var_48], 0
0x180009f30  mov     r9d, esi
0x180009f33  xor     r8d, r8d
0x180009f36  mov     edx, r14d
0x180009f39  mov     ecx, r15d
0x180009f3c  mov     rax, rbx
0x180009f3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f44  mov     rdi, rax
0x180009f47  mov     [rsp+68h+var_30], rax
0x180009f4c  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180009f53  jz      short loc_180009F5E
0x180009f55  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180009f5c  jnz     short loc_180009F8D
0x180009f5e  test    rdi, rdi
0x180009f61  jnz     short loc_180009F70
0x180009f63  lea     esi, [rdi+1]
0x180009f66  call    cs:__imp_GetLastError
0x180009f6c  mov     ebx, eax
0x180009f6e  jmp     short loc_180009F74
0x180009f70  xor     esi, esi
0x180009f72  xor     ebx, ebx
0x180009f74  mov     rdx, [rsp+68h+ulCookie]; ulCookie
0x180009f79  xor     ecx, ecx; dwFlags
0x180009f7b  call    cs:__imp_DeactivateActCtx
0x180009f81  test    esi, esi
0x180009f83  jz      short loc_180009F8D
0x180009f85  mov     ecx, ebx; dwErrCode
0x180009f87  call    cs:__imp_SetLastError
0x180009f8d  mov     rax, rdi
0x180009f90  jmp     loc_180009EFC
0x18000b1d9  push    rbx
0x18000b1db  push    rbp
0x18000b1dc  push    rdi
0x18000b1dd  sub     rsp, 30h
0x18000b1e1  mov     rbp, rdx
0x18000b1e4  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000b1eb  jz      short loc_18000B1F6
0x18000b1ed  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000b1f4  jnz     short loc_18000B229
0x18000b1f6  cmp     qword ptr [rbp+38h], 0
0x18000b1fb  jnz     short loc_18000B20C
0x18000b1fd  mov     edi, 1
0x18000b202  call    cs:__imp_GetLastError
0x18000b208  mov     ebx, eax
0x18000b20a  jmp     short loc_18000B210
0x18000b20c  xor     edi, edi
0x18000b20e  xor     ebx, ebx
0x18000b210  mov     rdx, [rbp+30h]; ulCookie
0x18000b214  xor     ecx, ecx; dwFlags
0x18000b216  call    cs:__imp_DeactivateActCtx
0x18000b21c  test    edi, edi
0x18000b21e  jz      short loc_18000B229
0x18000b220  mov     ecx, ebx; dwErrCode
0x18000b222  call    cs:__imp_SetLastError
0x18000b228  nop
0x18000b229  add     rsp, 30h
0x18000b22d  pop     rdi
0x18000b22e  pop     rbp
0x18000b22f  pop     rbx
0x18000b230  retn
```
