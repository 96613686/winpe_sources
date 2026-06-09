# CommonUtil::UtilGetWindowsPath

- ea: `0x140003bc0`
- end: `0x140003c50`
- name: `CommonUtil::UtilGetWindowsPath`
- size: `144`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140003ba8`
- `0x140003c50`

## callees

- `0x140003054`
- `0x140003254`
- `0x140003814`
- `0x140003bc0`
- `0x140005c40`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilGetWindowsPath(__int64 a1, CommonUtil *a2, __int64 a3, unsigned int a4)
{
  int WindowsPath; // edi
  const wchar_t *v7; // r8
  wchar_t **v8; // rcx
  __int64 v9; // r9
  wchar_t **v10; // rbx
  int v11; // eax
  wchar_t **v13; // [rsp+20h] [rbp-18h] BYREF

  v13 = 0;
  WindowsPath = CommonUtil::HrGetWindowsPath(a1, &v13, a4);
  if ( WindowsPath >= 0 )
  {
    if ( a3 )
    {
      v9 = a3;
      v10 = v13;
      v11 = CommonUtil::NewSprintfW(a2, (wchar_t **)L"%ls\\%ls", (const wchar_t *)v13, v9);
    }
    else
    {
      v10 = v13;
      v11 = CommonUtil::HrDuplicateStringW(a2, v13, v7);
    }
    WindowsPath = v11;
    if ( v10 )
    {
      v8 = v10;
LABEL_9:
      operator delete(v8);
    }
  }
  else
  {
    v8 = v13;
    if ( v13 )
      goto LABEL_9;
  }
  return (unsigned int)WindowsPath;
}

```

## disassembly

```asm
0x140003bc0  mov     rax, rsp
0x140003bc3  mov     [rax+8], rbx
0x140003bc7  mov     [rax+10h], rsi
0x140003bcb  push    rdi
0x140003bcc  sub     rsp, 30h
0x140003bd0  mov     rbx, r8
0x140003bd3  mov     qword ptr [rax-18h], 0
0x140003bdb  mov     rsi, rdx
0x140003bde  mov     r8d, r9d
0x140003be1  lea     rdx, [rax-18h]
0x140003be5  call    CommonUtil__HrGetWindowsPath
0x140003bea  mov     ecx, eax
0x140003bec  mov     edi, eax
0x140003bee  shr     ecx, 1Fh
0x140003bf1  test    cl, cl
0x140003bf3  jz      short loc_140003C01
0x140003bf5  mov     rcx, [rsp+38h+var_18]
0x140003bfa  test    rcx, rcx
0x140003bfd  jz      short loc_140003C3E
0x140003bff  jmp     short loc_140003C39
0x140003c01  mov     rcx, rsi; this
0x140003c04  test    rbx, rbx
0x140003c07  jz      short loc_140003C22
0x140003c09  mov     r9, rbx
0x140003c0c  lea     rdx, aLsLs; "%ls\\%ls"
0x140003c13  mov     rbx, [rsp+38h+var_18]
0x140003c18  mov     r8, rbx; wchar_t *
0x140003c1b  call    ?NewSprintfW@CommonUtil@@YAJPEAPEA_WPEB_WZZ; CommonUtil::NewSprintfW(wchar_t * *,wchar_t const *,...)
0x140003c20  jmp     short loc_140003C2F
0x140003c22  mov     rbx, [rsp+38h+var_18]
0x140003c27  mov     rdx, rbx; wchar_t **
0x140003c2a  call    ?HrDuplicateStringW@CommonUtil@@YAJPEAPEA_WPEB_W@Z; CommonUtil::HrDuplicateStringW(wchar_t * *,wchar_t const *)
0x140003c2f  mov     edi, eax
0x140003c31  test    rbx, rbx
0x140003c34  jz      short loc_140003C3E
0x140003c36  mov     rcx, rbx; void *
0x140003c39  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140003c3e  mov     rbx, [rsp+38h+arg_0]
0x140003c43  mov     eax, edi
0x140003c45  mov     rsi, [rsp+38h+arg_8]
0x140003c4a  add     rsp, 30h
0x140003c4e  pop     rdi
0x140003c4f  retn
```
