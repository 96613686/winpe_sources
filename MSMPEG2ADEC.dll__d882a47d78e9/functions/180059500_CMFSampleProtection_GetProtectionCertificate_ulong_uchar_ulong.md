# CMFSampleProtection::GetProtectionCertificate(ulong,uchar * *,ulong *)

- ea: `0x180059500`
- end: `0x1800595dd`
- name: `?GetProtectionCertificate@CMFSampleProtection@@UEAAJKPEAPEAEPEAK@Z`
- size: `221`
- prototype: `__int64 __fastcall(CMFSampleProtection *__hidden this, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180059500`
- `0x1800886fc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180059571`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180059571`

## pseudocode

```c
__int64 __fastcall CMFSampleProtection::GetProtectionCertificate(
        CMFSampleProtection *this,
        int a2,
        unsigned __int8 **a3,
        unsigned int *a4)
{
  const void *v6; // rsi
  unsigned int v7; // ebx
  unsigned __int8 *v8; // rax
  unsigned int v9; // edi

  if ( !a3 || !a4 )
    return 2147500035LL;
  if ( a2 == 3 )
  {
    v6 = (const void *)*((_QWORD *)this + 3);
    v7 = *((_DWORD *)this + 8);
  }
  else
  {
    if ( a2 != 4 )
      return 2147500033LL;
    v6 = (const void *)*((_QWORD *)this + 45);
    v7 = *((_DWORD *)this + 92);
  }
  *a3 = 0;
  *a4 = 0;
  if ( !v6 || !v7 )
    return 2147549183LL;
  v8 = (unsigned __int8 *)CoTaskMemAlloc(v7);
  *a3 = v8;
  if ( v8 )
  {
    v9 = 0;
    memcpy_0(v8, v6, v7);
    *a4 = v7;
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v9;
}

```

## disassembly

```asm
0x180059500  mov     [rsp+arg_18], rdi
0x180059505  push    r14
0x180059507  sub     rsp, 20h
0x18005950b  mov     r14, r9
0x18005950e  mov     rdi, r8
0x180059511  test    r8, r8
0x180059514  jz      loc_1800595CB
0x18005951a  test    r9, r9
0x18005951d  jz      loc_1800595CB
0x180059523  mov     [rsp+28h+arg_0], rbx
0x180059528  mov     [rsp+28h+arg_10], rsi
0x18005952d  cmp     edx, 3
0x180059530  jnz     short loc_18005953B
0x180059532  mov     rsi, [rcx+18h]
0x180059536  mov     ebx, [rcx+20h]
0x180059539  jmp     short loc_180059551
0x18005953b  cmp     edx, 4
0x18005953e  jnz     loc_1800595C4
0x180059544  mov     rsi, [rcx+168h]
0x18005954b  mov     ebx, [rcx+170h]
0x180059551  mov     qword ptr [r8], 0
0x180059558  mov     dword ptr [r9], 0
0x18005955f  test    rsi, rsi
0x180059562  jz      short loc_1800595BD
0x180059564  test    ebx, ebx
0x180059566  jz      short loc_1800595BD
0x180059568  mov     [rsp+28h+arg_8], rbp
0x18005956d  mov     ecx, ebx; cb
0x18005956f  mov     ebp, ebx
0x180059571  call    cs:__imp_CoTaskMemAlloc
0x180059578  nop     dword ptr [rax+rax+00h]
0x18005957d  mov     [rdi], rax
0x180059580  test    rax, rax
0x180059583  jnz     short loc_18005958C
0x180059585  mov     edi, 8007000Eh
0x18005958a  jmp     short loc_18005959F
0x18005958c  xor     edi, edi
0x18005958e  mov     r8, rbp; Size
0x180059591  mov     rdx, rsi; Src
0x180059594  mov     rcx, rax; void *
0x180059597  call    memcpy_0
0x18005959c  mov     [r14], ebx
0x18005959f  mov     rbp, [rsp+28h+arg_8]
0x1800595a4  mov     eax, edi
0x1800595a6  mov     rbx, [rsp+28h+arg_0]
0x1800595ab  mov     rsi, [rsp+28h+arg_10]
0x1800595b0  mov     rdi, [rsp+28h+arg_18]
0x1800595b5  add     rsp, 20h
0x1800595b9  pop     r14
0x1800595bb  retn
0x1800595bd  mov     eax, 8000FFFFh
0x1800595c2  jmp     short loc_1800595A6
0x1800595c4  mov     eax, 80004001h
0x1800595c9  jmp     short loc_1800595A6
0x1800595cb  mov     rdi, [rsp+28h+arg_18]
0x1800595d0  mov     eax, 80004003h
0x1800595d5  add     rsp, 20h
0x1800595d9  pop     r14
0x1800595db  retn
```
