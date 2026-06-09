# McTemplateK0zsjzqzsq_EventWriteTransfer

- ea: `0x14000ba08`
- end: `0x14000bb72`
- name: `McTemplateK0zsjzqzsq_EventWriteTransfer`
- size: `362`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000a8dc`

## callees

- `0x14000356c`
- `0x14000ba08`
- `0x14001edc0`

## string_xrefs

- `0x14000ba57`: `SuCreatePool`

## pseudocode

```c
ULONG __fastcall McTemplateK0zsjzqzsq_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        const wchar_t *a7,
        char a8,
        const wchar_t *a9,
        const char *a10,
        char a11)
{
  __int64 v11; // rcx
  __int64 v12; // rax
  const wchar_t *v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rax
  int v16; // eax
  const wchar_t *v17; // rax
  bool v18; // zf
  __int64 v19; // rdx
  const char *v20; // rax
  int v21; // ecx
  struct _EVENT_DATA_DESCRIPTOR v23; // [rsp+30h] [rbp-81h] BYREF
  WCHAR *v24; // [rsp+40h] [rbp-71h]
  int v25; // [rsp+48h] [rbp-69h]
  int v26; // [rsp+4Ch] [rbp-65h]
  const char *v27; // [rsp+50h] [rbp-61h]
  __int64 v28; // [rsp+58h] [rbp-59h]
  __int64 v29; // [rsp+60h] [rbp-51h]
  __int64 v30; // [rsp+68h] [rbp-49h]
  const wchar_t *v31; // [rsp+70h] [rbp-41h]
  int v32; // [rsp+78h] [rbp-39h]
  int v33; // [rsp+7Ch] [rbp-35h]
  char *v34; // [rsp+80h] [rbp-31h]
  __int64 v35; // [rsp+88h] [rbp-29h]
  const wchar_t *v36; // [rsp+90h] [rbp-21h]
  int v37; // [rsp+98h] [rbp-19h]
  int v38; // [rsp+9Ch] [rbp-15h]
  const char *v39; // [rsp+A0h] [rbp-11h]
  int v40; // [rsp+A8h] [rbp-9h]
  int v41; // [rsp+ACh] [rbp-5h]
  char *v42; // [rsp+B0h] [rbp-1h]
  __int64 v43; // [rsp+B8h] [rbp+7h]

  v11 = -1;
  v12 = -1;
  do
    ++v12;
  while ( *(&ModuleName + v12) );
  v24 = &ModuleName;
  v13 = a7;
  v14 = 10;
  v25 = 2 * v12 + 2;
  v27 = "SuCreatePool";
  v29 = a6;
  v26 = 0;
  v28 = 13;
  v30 = 16;
  if ( a7 )
  {
    v15 = -1;
    do
      ++v15;
    while ( a7[v15] );
    v16 = 2 * v15 + 2;
  }
  else
  {
    v16 = 10;
  }
  v32 = v16;
  v33 = 0;
  v34 = &a8;
  v17 = a9;
  if ( !a7 )
    v13 = L"NULL";
  v35 = 4;
  v31 = v13;
  v18 = a9 == 0;
  if ( a9 )
  {
    v19 = -1;
    do
      ++v19;
    while ( a9[v19] );
    v14 = (unsigned int)(2 * v19 + 2);
    v18 = a9 == 0;
  }
  if ( v18 )
    v17 = L"NULL";
  v37 = v14;
  v36 = v17;
  v20 = a10;
  v38 = 0;
  if ( a10 )
  {
    do
      ++v11;
    while ( a10[v11] );
    v21 = v11 + 1;
  }
  else
  {
    v21 = 5;
  }
  v40 = v21;
  v41 = 0;
  if ( !a10 )
    v20 = "NULL";
  v43 = 4;
  v39 = v20;
  v42 = &a11;
  return McGenEventWrite_EventWriteTransfer(
           (REGHANDLE *)SpaceApiProvider_Context,
           (const EVENT_DESCRIPTOR *)CreatePoolFailed,
           v14,
           9u,
           &v23);
}

```

## disassembly

```asm
0x14000ba08  push    rbp
0x14000ba0a  lea     rbp, [rsp-1Fh]
0x14000ba0f  sub     rsp, 0D0h
0x14000ba16  mov     rax, cs:__security_cookie
0x14000ba1d  xor     rax, rsp
0x14000ba20  mov     [rbp+1Fh+var_10], rax
0x14000ba24  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000ba28  lea     rdx, ?ModuleName@@3PAGA; ushort near * ModuleName
0x14000ba2f  mov     rax, rcx
0x14000ba32  xor     r9d, r9d
0x14000ba35  inc     rax
0x14000ba38  cmp     [rdx+rax*2], r9w
0x14000ba3d  jnz     short loc_14000BA35
0x14000ba3f  lea     eax, ds:2[rax*2]
0x14000ba46  mov     [rbp+1Fh+var_90], rdx
0x14000ba4a  mov     rdx, [rbp+1Fh+arg_30]
0x14000ba4e  mov     r8d, 0Ah
0x14000ba54  mov     [rbp+1Fh+var_88], eax
0x14000ba57  lea     rax, aSucreatepool; "SuCreatePool"
0x14000ba5e  mov     [rbp+1Fh+var_80], rax
0x14000ba62  mov     rax, [rbp+1Fh+arg_28]
0x14000ba66  mov     [rbp+1Fh+var_70], rax
0x14000ba6a  mov     [rbp+1Fh+var_84], r9d
0x14000ba6e  mov     [rbp+1Fh+var_78], 0Dh
0x14000ba76  mov     [rbp+1Fh+var_68], 10h
0x14000ba7e  test    rdx, rdx
0x14000ba81  jz      short loc_14000BA99
0x14000ba83  mov     rax, rcx
0x14000ba86  inc     rax
0x14000ba89  cmp     [rdx+rax*2], r9w
0x14000ba8e  jnz     short loc_14000BA86
0x14000ba90  lea     eax, ds:2[rax*2]
0x14000ba97  jmp     short loc_14000BA9C
0x14000ba99  mov     eax, r8d
0x14000ba9c  mov     [rbp+1Fh+var_58], eax
0x14000ba9f  lea     r10, aNull_0; "NULL"
0x14000baa6  lea     rax, [rbp+1Fh+arg_38]
0x14000baaa  mov     [rbp+1Fh+var_54], r9d
0x14000baae  test    rdx, rdx
0x14000bab1  mov     [rbp+1Fh+var_50], rax
0x14000bab5  mov     rax, [rbp+1Fh+arg_40]
0x14000bab9  cmovz   rdx, r10
0x14000babd  mov     [rbp+1Fh+var_48], 4
0x14000bac5  mov     [rbp+1Fh+var_60], rdx
0x14000bac9  test    rax, rax
0x14000bacc  jz      short loc_14000BAE6
0x14000bace  mov     rdx, rcx
0x14000bad1  inc     rdx
0x14000bad4  cmp     [rax+rdx*2], r9w
0x14000bad9  jnz     short loc_14000BAD1
0x14000badb  lea     r8d, ds:2[rdx*2]
0x14000bae3  test    rax, rax
0x14000bae6  cmovz   rax, r10
0x14000baea  mov     [rbp+1Fh+var_38], r8d
0x14000baee  mov     [rbp+1Fh+var_40], rax
0x14000baf2  mov     rax, [rbp+1Fh+arg_48]
0x14000baf6  mov     [rbp+1Fh+var_34], r9d
0x14000bafa  test    rax, rax
0x14000bafd  jz      short loc_14000BB0C
0x14000baff  inc     rcx
0x14000bb02  cmp     [rax+rcx], r9b
0x14000bb06  jnz     short loc_14000BAFF
0x14000bb08  inc     ecx
0x14000bb0a  jmp     short loc_14000BB11
0x14000bb0c  mov     ecx, 5
0x14000bb11  test    rax, rax
0x14000bb14  mov     [rbp+1Fh+var_28], ecx
0x14000bb17  lea     rdx, aNull; "NULL"
0x14000bb1e  mov     [rbp+1Fh+var_24], r9d
0x14000bb22  cmovz   rax, rdx
0x14000bb26  mov     [rbp+1Fh+var_18], 4
0x14000bb2e  mov     [rbp+1Fh+var_30], rax
0x14000bb32  lea     rdx, CreatePoolFailed
0x14000bb39  lea     rax, [rbp+1Fh+arg_50]
0x14000bb3d  mov     r9d, 9
0x14000bb43  mov     [rbp+1Fh+var_20], rax
0x14000bb47  lea     rcx, SpaceApiProvider_Context
0x14000bb4e  lea     rax, [rsp+0D0h+var_A0]
0x14000bb53  mov     [rsp+0D0h+var_B0], rax
0x14000bb58  call    McGenEventWrite_EventWriteTransfer
0x14000bb5d  mov     rcx, [rbp+1Fh+var_10]
0x14000bb61  xor     rcx, rsp; StackCookie
0x14000bb64  call    __security_check_cookie
0x14000bb69  add     rsp, 0D0h
0x14000bb70  pop     rbp
0x14000bb71  retn
```
