# SdbGetMergeStubPath

- ea: `0x140041d6c`
- end: `0x140041f42`
- name: `SdbGetMergeStubPath`
- size: `470`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x140029954`
- `0x14002a898`
- `0x140042724`
- `0x1400591c4`

## callees

- `0x14003e364`
- `0x140041638`
- `0x140041d6c`
- `0x140041f48`
- `0x14004506c`
- `0x140045d44`

## string_xrefs

- `0x140041e95`: `SdbpGetMergeRedirectPathInternal failed[%x]`
- `0x140041ea1`: `SdbGetMergeRedirectPath`
- `0x140041eb3`: `Failed to get manifested stub [%x]`
- `0x140041f04`: `Failed to get manifested stub [%x]`
- `0x140041ec4`: `SdbGetMergeStubPath`
- `0x140041f15`: `SdbGetMergeStubPath`

## pseudocode

```c
__int64 __fastcall SdbGetMergeStubPath(wchar_t **a1, const wchar_t *a2)
{
  int MergeRedirectPathInternal; // ebx
  const wchar_t *FileNamePart; // rax
  wchar_t *v7; // rsi
  int ManifestedMergeStubAlloc; // eax
  __int64 v9; // rcx
  wchar_t *v10; // rdi
  int v11; // eax
  void *v12; // rdx
  int v13; // [rsp+60h] [rbp+30h] BYREF
  void *v14; // [rsp+70h] [rbp+40h] BYREF
  wchar_t *v15; // [rsp+78h] [rbp+48h] BYREF

  v15 = 0;
  if ( a1 )
  {
    *a1 = 0;
    MergeRedirectPathInternal = -1073741772;
    FileNamePart = AslPathGetFileNamePart(a2);
    if ( FileNamePart == a2 )
      return (unsigned int)MergeRedirectPathInternal;
    v7 = 0;
    ManifestedMergeStubAlloc = SdbpGetManifestedMergeStubAlloc(&v15, FileNamePart);
    MergeRedirectPathInternal = ManifestedMergeStubAlloc;
    if ( ManifestedMergeStubAlloc != -1073741772 )
    {
      if ( ManifestedMergeStubAlloc >= 0 )
      {
        v10 = v15;
        v13 = 0;
        v14 = 0;
        MergeRedirectPathInternal = SdbpGetMergeRedirectPathInternal(&v14, &v13, 1, v15);
        if ( (int)(MergeRedirectPathInternal + 0x80000000) < 0 || MergeRedirectPathInternal == -1073741772 )
        {
          if ( v14 )
            AslFree(0x80000000LL, v14);
          v11 = SdbpGetMergeRedirectPathInternal(&v14, 0, 0, v10);
          MergeRedirectPathInternal = v11;
          if ( v11 >= 0 )
          {
            v7 = (wchar_t *)v14;
            v12 = 0;
            MergeRedirectPathInternal = 0;
LABEL_11:
            if ( v12 )
              AslFree(v9, v12);
            if ( MergeRedirectPathInternal == -1073741772 )
            {
              *a1 = v10;
              v10 = 0;
            }
            else
            {
              if ( MergeRedirectPathInternal < 0 )
              {
                AslLogCallPrintf(
                  1,
                  "SdbGetMergeStubPath",
                  1417,
                  "Failed to get manifested stub [%x]",
                  MergeRedirectPathInternal);
                goto LABEL_16;
              }
              *a1 = v7;
              v7 = 0;
            }
            MergeRedirectPathInternal = 0;
LABEL_16:
            if ( v10 )
              AslFree(v9, v10);
            if ( v7 )
              AslFree(v9, v7);
            return (unsigned int)MergeRedirectPathInternal;
          }
          if ( v11 != -1073741772 )
            AslLogCallPrintf(1, "SdbGetMergeRedirectPath", 2149, "SdbpGetMergeRedirectPathInternal failed[%x]", v11);
        }
        else
        {
          AslLogCallPrintf(
            1,
            "SdbGetMergeRedirectPath",
            2134,
            "SdbpGetMergeRedirectPathInternal failed[%x]",
            MergeRedirectPathInternal);
        }
        v12 = v14;
        goto LABEL_11;
      }
      AslLogCallPrintf(1, "SdbGetMergeStubPath", 1401, "Failed to get manifested stub [%x]", ManifestedMergeStubAlloc);
    }
    v10 = v15;
    goto LABEL_16;
  }
  return 3221225711LL;
}

```

## disassembly

```asm
0x140041d6c  mov     [rsp-28h+arg_8], rbx
0x140041d71  push    rbp
0x140041d72  push    rsi
0x140041d73  push    rdi
0x140041d74  push    r13
0x140041d76  push    r14
0x140041d78  mov     rbp, rsp
0x140041d7b  sub     rsp, 30h
0x140041d7f  mov     [rbp+arg_18], 0
0x140041d87  mov     rdi, rdx
0x140041d8a  mov     r14, rcx
0x140041d8d  test    rcx, rcx
0x140041d90  jz      loc_140041E7C
0x140041d96  mov     qword ptr [rcx], 0
0x140041d9d  mov     r13d, 0C0000034h
0x140041da3  mov     rcx, rdx
0x140041da6  mov     ebx, r13d
0x140041da9  call    AslPathGetFileNamePart
0x140041dae  cmp     rax, rdi
0x140041db1  jnz     short loc_140041DC7
0x140041db3  mov     eax, ebx
0x140041db5  mov     rbx, [rsp+30h+arg_8]
0x140041dba  add     rsp, 30h
0x140041dbe  pop     r14
0x140041dc0  pop     r13
0x140041dc2  pop     rdi
0x140041dc3  pop     rsi
0x140041dc4  pop     rbp
0x140041dc5  retn
0x140041dc7  mov     rdx, rax
0x140041dca  lea     rcx, [rbp+arg_18]
0x140041dce  xor     esi, esi
0x140041dd0  call    SdbpGetManifestedMergeStubAlloc
0x140041dd5  mov     ebx, eax
0x140041dd7  cmp     eax, r13d
0x140041dda  jz      loc_140041ED5
0x140041de0  test    eax, eax
0x140041de2  js      loc_140041EB3
0x140041de8  mov     rdi, [rbp+arg_18]
0x140041dec  lea     r8d, [rsi+1]
0x140041df0  mov     r9, rdi
0x140041df3  mov     [rbp+arg_0], esi
0x140041df6  lea     rdx, [rbp+arg_0]
0x140041dfa  mov     [rbp+arg_10], rsi
0x140041dfe  lea     rcx, [rbp+arg_10]
0x140041e02  call    SdbpGetMergeRedirectPathInternal
0x140041e07  mov     ecx, 80000000h
0x140041e0c  mov     ebx, eax
0x140041e0e  add     eax, ecx
0x140041e10  test    ecx, eax
0x140041e12  jz      short loc_140041E86
0x140041e14  mov     rdx, [rbp+arg_10]
0x140041e18  test    rdx, rdx
0x140041e1b  jnz     loc_140041EDB
0x140041e21  mov     r9, rdi
0x140041e24  lea     rcx, [rbp+arg_10]
0x140041e28  xor     r8d, r8d
0x140041e2b  xor     edx, edx
0x140041e2d  call    SdbpGetMergeRedirectPathInternal
0x140041e32  mov     ebx, eax
0x140041e34  test    eax, eax
0x140041e36  js      loc_140041EE5
0x140041e3c  mov     rsi, [rbp+arg_10]
0x140041e40  xor     edx, edx
0x140041e42  xor     ebx, ebx
0x140041e44  test    rdx, rdx
0x140041e47  jnz     loc_140041EF6
0x140041e4d  cmp     ebx, r13d
0x140041e50  jnz     loc_140041F00
0x140041e56  mov     [r14], rdi
0x140041e59  xor     edi, edi
0x140041e5b  xor     ebx, ebx
0x140041e5d  test    rdi, rdi
0x140041e60  jnz     loc_140041F35
0x140041e66  test    rsi, rsi
0x140041e69  jz      loc_140041DB3
0x140041e6f  mov     rdx, rsi
0x140041e72  call    AslFree
0x140041e77  jmp     loc_140041DB3
0x140041e7c  mov     eax, 0C00000EFh
0x140041e81  jmp     loc_140041DB5
0x140041e86  cmp     ebx, r13d
0x140041e89  jz      short loc_140041E14
0x140041e8b  mov     [rsp+30h+var_10], ebx
0x140041e8f  mov     r8d, 856h
0x140041e95  lea     r9, aSdbpgetmergere_0; "SdbpGetMergeRedirectPathInternal failed"...
0x140041e9c  mov     ecx, 1
0x140041ea1  lea     rdx, aSdbgetmergered_0; "SdbGetMergeRedirectPath"
0x140041ea8  call    AslLogCallPrintf
0x140041ead  mov     rdx, [rbp+arg_10]
0x140041eb1  jmp     short loc_140041E44
0x140041eb3  lea     r9, aFailedToGetMan; "Failed to get manifested stub [%x]"
0x140041eba  mov     [rsp+30h+var_10], eax
0x140041ebe  mov     r8d, 579h
0x140041ec4  lea     rdx, aSdbgetmergestu; "SdbGetMergeStubPath"
0x140041ecb  mov     ecx, 1
0x140041ed0  call    AslLogCallPrintf
0x140041ed5  mov     rdi, [rbp+arg_18]
0x140041ed9  jmp     short loc_140041E5D
0x140041edb  call    AslFree
0x140041ee0  jmp     loc_140041E21
0x140041ee5  cmp     eax, r13d
0x140041ee8  jz      short loc_140041EAD
0x140041eea  mov     [rsp+30h+var_10], eax
0x140041eee  mov     r8d, 865h
0x140041ef4  jmp     short loc_140041E95
0x140041ef6  call    AslFree
0x140041efb  jmp     loc_140041E4D
0x140041f00  test    ebx, ebx
0x140041f02  jns     short loc_140041F2B
0x140041f04  lea     r9, aFailedToGetMan; "Failed to get manifested stub [%x]"
0x140041f0b  mov     [rsp+30h+var_10], ebx
0x140041f0f  mov     r8d, 589h
0x140041f15  lea     rdx, aSdbgetmergestu; "SdbGetMergeStubPath"
0x140041f1c  mov     ecx, 1
0x140041f21  call    AslLogCallPrintf
0x140041f26  jmp     loc_140041E5D
0x140041f2b  mov     [r14], rsi
0x140041f2e  xor     esi, esi
0x140041f30  jmp     loc_140041E5B
0x140041f35  mov     rdx, rdi
0x140041f38  call    AslFree
0x140041f3d  jmp     loc_140041E66
```
