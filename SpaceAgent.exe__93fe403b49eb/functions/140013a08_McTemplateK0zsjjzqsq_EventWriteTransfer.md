# McTemplateK0zsjjzqsq_EventWriteTransfer

- ea: `0x140013a08`
- end: `0x140013b4d`
- name: `McTemplateK0zsjjzqsq_EventWriteTransfer`
- size: `325`
- prototype: `__int64 __fastcall(_DWORD, _DWORD, _DWORD, _DWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140012704`

## callees

- `0x14000356c`
- `0x140013a08`
- `0x14001edc0`

## string_xrefs

- `0x140013a51`: `SuCreateSpace`

## pseudocode

```c
ULONG __fastcall McTemplateK0zsjjzqsq_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        const wchar_t *a8,
        char a9,
        const char *a10,
        char a11)
{
  __int64 v11; // rcx
  __int64 v12; // rax
  const wchar_t *v13; // rdx
  __int64 v14; // rax
  int v15; // eax
  const char *v16; // rax
  int v17; // ecx
  struct _EVENT_DATA_DESCRIPTOR v19; // [rsp+30h] [rbp-81h] BYREF
  WCHAR *v20; // [rsp+40h] [rbp-71h]
  int v21; // [rsp+48h] [rbp-69h]
  int v22; // [rsp+4Ch] [rbp-65h]
  const char *v23; // [rsp+50h] [rbp-61h]
  __int64 v24; // [rsp+58h] [rbp-59h]
  __int64 v25; // [rsp+60h] [rbp-51h]
  __int64 v26; // [rsp+68h] [rbp-49h]
  __int64 v27; // [rsp+70h] [rbp-41h]
  __int64 v28; // [rsp+78h] [rbp-39h]
  const wchar_t *v29; // [rsp+80h] [rbp-31h]
  int v30; // [rsp+88h] [rbp-29h]
  int v31; // [rsp+8Ch] [rbp-25h]
  char *v32; // [rsp+90h] [rbp-21h]
  __int64 v33; // [rsp+98h] [rbp-19h]
  const char *v34; // [rsp+A0h] [rbp-11h]
  int v35; // [rsp+A8h] [rbp-9h]
  int v36; // [rsp+ACh] [rbp-5h]
  char *v37; // [rsp+B0h] [rbp-1h]
  __int64 v38; // [rsp+B8h] [rbp+7h]

  v11 = -1;
  v12 = -1;
  do
    ++v12;
  while ( *(&ModuleName + v12) );
  v20 = &ModuleName;
  v13 = a8;
  v21 = 2 * v12 + 2;
  v23 = "SuCreateSpace";
  v25 = a6;
  v27 = a7;
  v22 = 0;
  v24 = 14;
  v26 = 16;
  v28 = 16;
  if ( a8 )
  {
    v14 = -1;
    do
      ++v14;
    while ( a8[v14] );
    v15 = 2 * v14 + 2;
  }
  else
  {
    v15 = 10;
  }
  v30 = v15;
  v31 = 0;
  v32 = &a9;
  v16 = a10;
  if ( !a8 )
    v13 = L"NULL";
  v33 = 4;
  v29 = v13;
  if ( a10 )
  {
    do
      ++v11;
    while ( a10[v11] );
    v17 = v11 + 1;
  }
  else
  {
    v17 = 5;
  }
  v35 = v17;
  v36 = 0;
  if ( !a10 )
    v16 = "NULL";
  v38 = 4;
  v34 = v16;
  v37 = &a11;
  return McGenEventWrite_EventWriteTransfer(
           (REGHANDLE *)SpaceApiProvider_Context,
           (const EVENT_DESCRIPTOR *)CreateSpaceFailed,
           (__int64)L"NULL",
           9u,
           &v19);
}

```

## disassembly

```asm
0x140013a08  push    rbp
0x140013a0a  lea     rbp, [rsp-1Fh]
0x140013a0f  sub     rsp, 0D0h
0x140013a16  mov     rax, cs:__security_cookie
0x140013a1d  xor     rax, rsp
0x140013a20  mov     [rbp+1Fh+var_10], rax
0x140013a24  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140013a28  lea     rdx, ?ModuleName@@3PAGA; ushort near * ModuleName
0x140013a2f  mov     rax, rcx
0x140013a32  xor     r9d, r9d
0x140013a35  inc     rax
0x140013a38  cmp     [rdx+rax*2], r9w
0x140013a3d  jnz     short loc_140013A35
0x140013a3f  lea     eax, ds:2[rax*2]
0x140013a46  mov     [rbp+1Fh+var_90], rdx
0x140013a4a  mov     rdx, [rbp+1Fh+arg_38]
0x140013a4e  mov     [rbp+1Fh+var_88], eax
0x140013a51  lea     rax, aSucreatespace; "SuCreateSpace"
0x140013a58  mov     [rbp+1Fh+var_80], rax
0x140013a5c  mov     rax, [rbp+1Fh+arg_28]
0x140013a60  mov     [rbp+1Fh+var_70], rax
0x140013a64  mov     rax, [rbp+1Fh+arg_30]
0x140013a68  mov     [rbp+1Fh+var_60], rax
0x140013a6c  mov     [rbp+1Fh+var_84], r9d
0x140013a70  mov     [rbp+1Fh+var_78], 0Eh
0x140013a78  mov     [rbp+1Fh+var_68], 10h
0x140013a80  mov     [rbp+1Fh+var_58], 10h
0x140013a88  test    rdx, rdx
0x140013a8b  jz      short loc_140013AA3
0x140013a8d  mov     rax, rcx
0x140013a90  inc     rax
0x140013a93  cmp     [rdx+rax*2], r9w
0x140013a98  jnz     short loc_140013A90
0x140013a9a  lea     eax, ds:2[rax*2]
0x140013aa1  jmp     short loc_140013AA8
0x140013aa3  mov     eax, 0Ah
0x140013aa8  mov     [rbp+1Fh+var_48], eax
0x140013aab  lea     r8, aNull_0; "NULL"
0x140013ab2  lea     rax, [rbp+1Fh+arg_40]
0x140013ab6  mov     [rbp+1Fh+var_44], r9d
0x140013aba  test    rdx, rdx
0x140013abd  mov     [rbp+1Fh+var_40], rax
0x140013ac1  mov     rax, [rbp+1Fh+arg_48]
0x140013ac5  cmovz   rdx, r8
0x140013ac9  mov     [rbp+1Fh+var_38], 4
0x140013ad1  mov     [rbp+1Fh+var_50], rdx
0x140013ad5  test    rax, rax
0x140013ad8  jz      short loc_140013AE7
0x140013ada  inc     rcx
0x140013add  cmp     [rax+rcx], r9b
0x140013ae1  jnz     short loc_140013ADA
0x140013ae3  inc     ecx
0x140013ae5  jmp     short loc_140013AEC
0x140013ae7  mov     ecx, 5
0x140013aec  test    rax, rax
0x140013aef  mov     [rbp+1Fh+var_28], ecx
0x140013af2  lea     rdx, aNull; "NULL"
0x140013af9  mov     [rbp+1Fh+var_24], r9d
0x140013afd  cmovz   rax, rdx
0x140013b01  mov     [rbp+1Fh+var_18], 4
0x140013b09  mov     [rbp+1Fh+var_30], rax
0x140013b0d  lea     rdx, CreateSpaceFailed
0x140013b14  lea     rax, [rbp+1Fh+arg_50]
0x140013b18  mov     r9d, 9
0x140013b1e  mov     [rbp+1Fh+var_20], rax
0x140013b22  lea     rcx, SpaceApiProvider_Context
0x140013b29  lea     rax, [rsp+0D0h+var_A0]
0x140013b2e  mov     [rsp+0D0h+var_B0], rax
0x140013b33  call    McGenEventWrite_EventWriteTransfer
0x140013b38  mov     rcx, [rbp+1Fh+var_10]
0x140013b3c  xor     rcx, rsp; StackCookie
0x140013b3f  call    __security_check_cookie
0x140013b44  add     rsp, 0D0h
0x140013b4b  pop     rbp
0x140013b4c  retn
```
