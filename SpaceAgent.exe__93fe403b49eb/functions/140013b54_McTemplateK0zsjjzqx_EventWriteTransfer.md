# McTemplateK0zsjjzqx_EventWriteTransfer

- ea: `0x140013b54`
- end: `0x140013c5d`
- name: `McTemplateK0zsjjzqx_EventWriteTransfer`
- size: `265`
- prototype: `__int64 __fastcall(_DWORD, _DWORD, _DWORD, _DWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140012704`

## callees

- `0x14000356c`
- `0x140013b54`
- `0x14001edc0`

## string_xrefs

- `0x140013b99`: `SuCreateSpace`

## pseudocode

```c
ULONG __fastcall McTemplateK0zsjjzqx_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        const wchar_t *a8,
        char a9,
        char a10)
{
  __int64 v10; // rcx
  __int64 v11; // rax
  const wchar_t *v12; // rax
  int v13; // ecx
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+30h] [rbp-69h] BYREF
  WCHAR *v16; // [rsp+40h] [rbp-59h]
  int v17; // [rsp+48h] [rbp-51h]
  int v18; // [rsp+4Ch] [rbp-4Dh]
  const char *v19; // [rsp+50h] [rbp-49h]
  __int64 v20; // [rsp+58h] [rbp-41h]
  __int64 v21; // [rsp+60h] [rbp-39h]
  __int64 v22; // [rsp+68h] [rbp-31h]
  __int64 v23; // [rsp+70h] [rbp-29h]
  __int64 v24; // [rsp+78h] [rbp-21h]
  const wchar_t *v25; // [rsp+80h] [rbp-19h]
  int v26; // [rsp+88h] [rbp-11h]
  int v27; // [rsp+8Ch] [rbp-Dh]
  char *v28; // [rsp+90h] [rbp-9h]
  __int64 v29; // [rsp+98h] [rbp-1h]
  char *v30; // [rsp+A0h] [rbp+7h]
  __int64 v31; // [rsp+A8h] [rbp+Fh]

  v10 = -1;
  v11 = -1;
  do
    ++v11;
  while ( *(&ModuleName + v11) );
  v16 = &ModuleName;
  v17 = 2 * v11 + 2;
  v19 = "SuCreateSpace";
  v21 = a6;
  v23 = a7;
  v12 = a8;
  v18 = 0;
  v20 = 14;
  v22 = 16;
  v24 = 16;
  if ( a8 )
  {
    do
      ++v10;
    while ( a8[v10] );
    v13 = 2 * v10 + 2;
  }
  else
  {
    v13 = 10;
  }
  v26 = v13;
  v27 = 0;
  if ( !a8 )
    v12 = L"NULL";
  v29 = 4;
  v25 = v12;
  v28 = &a9;
  v31 = 8;
  v30 = &a10;
  return McGenEventWrite_EventWriteTransfer(
           (REGHANDLE *)SpaceApiProvider_Context,
           (const EVENT_DESCRIPTOR *)CreateSpaceSucceeded,
           0,
           8u,
           &v15);
}

```

## disassembly

```asm
0x140013b54  push    rbp
0x140013b56  lea     rbp, [rsp-27h]
0x140013b5b  sub     rsp, 0C0h
0x140013b62  mov     rax, cs:__security_cookie
0x140013b69  xor     rax, rsp
0x140013b6c  mov     [rbp+27h+var_10], rax
0x140013b70  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140013b74  lea     rdx, ?ModuleName@@3PAGA; ushort near * ModuleName
0x140013b7b  mov     rax, rcx
0x140013b7e  xor     r8d, r8d
0x140013b81  inc     rax
0x140013b84  cmp     [rdx+rax*2], r8w
0x140013b89  jnz     short loc_140013B81
0x140013b8b  lea     eax, ds:2[rax*2]
0x140013b92  mov     [rbp+27h+var_80], rdx
0x140013b96  mov     [rbp+27h+var_78], eax
0x140013b99  lea     rax, aSucreatespace; "SuCreateSpace"
0x140013ba0  mov     [rbp+27h+var_70], rax
0x140013ba4  mov     rax, [rbp+27h+arg_28]
0x140013ba8  mov     [rbp+27h+var_60], rax
0x140013bac  mov     rax, [rbp+27h+arg_30]
0x140013bb0  mov     [rbp+27h+var_50], rax
0x140013bb4  mov     rax, [rbp+27h+arg_38]
0x140013bb8  mov     [rbp+27h+var_74], r8d
0x140013bbc  mov     [rbp+27h+var_68], 0Eh
0x140013bc4  mov     [rbp+27h+var_58], 10h
0x140013bcc  mov     [rbp+27h+var_48], 10h
0x140013bd4  test    rax, rax
0x140013bd7  jz      short loc_140013BEC
0x140013bd9  inc     rcx
0x140013bdc  cmp     [rax+rcx*2], r8w
0x140013be1  jnz     short loc_140013BD9
0x140013be3  lea     ecx, ds:2[rcx*2]
0x140013bea  jmp     short loc_140013BF1
0x140013bec  mov     ecx, 0Ah
0x140013bf1  test    rax, rax
0x140013bf4  mov     [rbp+27h+var_38], ecx
0x140013bf7  lea     rdx, aNull_0; "NULL"
0x140013bfe  mov     [rbp+27h+var_34], r8d
0x140013c02  cmovz   rax, rdx
0x140013c06  mov     [rbp+27h+var_28], 4
0x140013c0e  mov     [rbp+27h+var_40], rax
0x140013c12  lea     rdx, CreateSpaceSucceeded
0x140013c19  lea     rax, [rbp+27h+arg_40]
0x140013c1d  mov     r9d, 8
0x140013c23  mov     [rbp+27h+var_30], rax
0x140013c27  lea     rcx, SpaceApiProvider_Context
0x140013c2e  lea     rax, [rbp+27h+arg_48]
0x140013c32  mov     [rbp+27h+var_18], r9
0x140013c36  mov     [rbp+27h+var_20], rax
0x140013c3a  lea     rax, [rbp+27h+var_90]
0x140013c3e  mov     [rsp+0C0h+var_A0], rax
0x140013c43  call    McGenEventWrite_EventWriteTransfer
0x140013c48  mov     rcx, [rbp+27h+var_10]
0x140013c4c  xor     rcx, rsp; StackCookie
0x140013c4f  call    __security_check_cookie
0x140013c54  add     rsp, 0C0h
0x140013c5b  pop     rbp
0x140013c5c  retn
```
