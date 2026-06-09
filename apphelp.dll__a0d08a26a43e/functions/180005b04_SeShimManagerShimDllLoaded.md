# SeShimManagerShimDllLoaded

- ea: `0x180005b04`
- end: `0x180005d36`
- name: `SeShimManagerShimDllLoaded`
- size: `562`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001f3c4`

## callees

- `0x180005b04`
- `0x180005dfc`
- `0x180005e2c`
- `0x18000f114`
- `0x18001577c`
- `0x180018f20`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x180005c63`
- `ntdll!RtlCompareMemory` at `0x180005c63`
- `ntdll!RtlFreeHeap` at `0x180005b86`
- `ntdll!RtlFreeHeap` at `0x180005b86`
- `ntdll!_wcsicmp` at `0x180005bd6`
- `ntdll!_wcsicmp` at `0x180005bec`
- `ntdll!_wcsicmp` at `0x180005bd6`
- `ntdll!_wcsicmp` at `0x180005bec`

## string_xrefs

- `0x180005ceb`: `SeShimManagerShimDllLoaded`
- `0x180005d19`: `SeShimManagerShimDllLoaded`
- `0x180005cda`: `Failed to duplicate dll fullpath string [%x]`
- `0x180005d08`: `Failed to duplicate dll fullpath string [%x]`

## pseudocode

```c
__int64 __fastcall SeShimManagerShimDllLoaded(unsigned __int64 *a1, __int64 a2)
{
  int v4; // eax
  wchar_t *v5; // rsi
  unsigned int v6; // ebx
  void *FileNamePart; // r8
  unsigned __int64 i; // r15
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rcx
  _QWORD *v12; // r12
  wchar_t **v13; // r14
  wchar_t *v14; // rcx
  wchar_t *v15; // rax
  int v16; // eax
  unsigned __int64 j; // rbx
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rcx
  wchar_t **v21; // rdx
  unsigned __int64 v22; // rax
  wchar_t *String1; // [rsp+70h] [rbp+40h] BYREF
  PVOID P; // [rsp+80h] [rbp+50h] BYREF
  __int64 v25; // [rsp+88h] [rbp+58h]

  P = 0;
  String1 = 0;
  if ( a1 )
  {
    v4 = AslUnicodeStringDuplicateAsString(&P, (unsigned __int16 *)(a2 + 72));
    v5 = (wchar_t *)P;
    v6 = v4;
    if ( v4 >= 0 )
    {
      FileNamePart = (void *)AslPathGetFileNamePart((const wchar_t *)P);
      P = FileNamePart;
      for ( i = 0; ; ++i )
      {
        if ( i >= a1[2] )
        {
          v6 = 0;
          goto LABEL_6;
        }
        v25 = 0;
        v10 = a1[1] * i;
        if ( !is_mul_ok(a1[1], i) || (v11 = a1[5], v12 = (_QWORD *)(v11 + v10), v11 + v10 < v11) )
          v12 = 0;
        v13 = (wchar_t **)(v12 + 1);
        String1 = (wchar_t *)v12[1];
        if ( _wcsicmp(String1, (const wchar_t *)FileNamePart) )
        {
          v14 = String1;
        }
        else
        {
          v16 = AslStringDuplicate(v12 + 1, v5);
          v6 = v16;
          if ( v16 < 0 )
          {
            if ( v16 != -1073741801 )
              AslLogCallPrintf(
                1,
                "SeShimManagerShimDllLoaded",
                303,
                "Failed to duplicate dll fullpath string [%x]",
                v16);
            *v13 = String1;
            goto LABEL_6;
          }
          for ( j = 0; j < a1[8]; ++j )
          {
            v25 = 0;
            v18 = a1[7] * j;
            if ( is_mul_ok(a1[7], j) )
            {
              v19 = a1[11];
              if ( v19 + v18 >= v19 && RtlCompareMemory(&String1, (const void *)(v19 + v18), 8u) == 8 )
              {
                if ( (j & 0x8000000000000000uLL) == 0LL )
                {
                  v21 = 0;
                  if ( j < a1[8] )
                  {
                    v22 = a1[7] * j;
                    if ( !is_mul_ok(a1[7], j) || (v20 = a1[11], v21 = (wchar_t **)(v20 + v22), v20 + v22 < v20) )
                      v21 = 0;
                  }
                  *v21 = *v13;
                }
                break;
              }
            }
          }
          AslFree(NtCurrentPeb()->ProcessHeap, String1);
          v14 = 0;
          String1 = 0;
        }
        if ( !v14 || (_wcsicmp(v14, v5) ? (v15 = String1) : (v15 = 0, String1 = 0), !v15) )
          *v12 = *(_QWORD *)(a2 + 48);
        FileNamePart = P;
      }
    }
    if ( v4 != -1073741801 )
      AslLogCallPrintf(1, "SeShimManagerShimDllLoaded", 272, "Failed to duplicate dll fullpath string [%x]", v4);
LABEL_6:
    if ( v5 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return v6;
}

```

## disassembly

```asm
0x180005b04  mov     [rsp-38h+arg_8], rbx
0x180005b09  push    rbp
0x180005b0a  push    rsi
0x180005b0b  push    rdi
0x180005b0c  push    r12
0x180005b0e  push    r13
0x180005b10  push    r14
0x180005b12  push    r15
0x180005b14  mov     rbp, rsp
0x180005b17  sub     rsp, 30h
0x180005b1b  mov     [rbp+P], 0
0x180005b23  mov     r13, rdx
0x180005b26  mov     [rbp+String1], 0
0x180005b2e  mov     rdi, rcx
0x180005b31  test    rcx, rcx
0x180005b34  jz      loc_180005CAA
0x180005b3a  add     rdx, 48h ; 'H'
0x180005b3e  lea     rcx, [rbp+P]
0x180005b42  call    AslUnicodeStringDuplicateAsString
0x180005b47  mov     rsi, [rbp+P]
0x180005b4b  mov     ebx, eax
0x180005b4d  test    eax, eax
0x180005b4f  js      loc_180005CCF
0x180005b55  mov     rcx, rsi
0x180005b58  call    AslPathGetFileNamePart
0x180005b5d  mov     r8, rax
0x180005b60  mov     [rbp+P], rax
0x180005b64  xor     r15d, r15d
0x180005b67  cmp     r15, [rdi+10h]
0x180005b6b  jb      short loc_180005BA3
0x180005b6d  xor     ebx, ebx
0x180005b6f  test    rsi, rsi
0x180005b72  jz      short loc_180005B8C
0x180005b74  mov     rcx, gs:60h
0x180005b7d  mov     r8, rsi; P
0x180005b80  xor     edx, edx; Flags
0x180005b82  mov     rcx, [rcx+30h]; HeapHandle
0x180005b86  call    cs:__imp_RtlFreeHeap
0x180005b8c  mov     eax, ebx
0x180005b8e  mov     rbx, [rsp+30h+arg_8]
0x180005b93  add     rsp, 30h
0x180005b97  pop     r15
0x180005b99  pop     r14
0x180005b9b  pop     r13
0x180005b9d  pop     r12
0x180005b9f  pop     rdi
0x180005ba0  pop     rsi
0x180005ba1  pop     rbp
0x180005ba2  retn
0x180005ba3  mov     rax, r15
0x180005ba6  mov     [rbp+arg_18], 0
0x180005bae  mul     qword ptr [rdi+8]
0x180005bb2  test    rdx, rdx
0x180005bb5  jnz     short loc_180005BC4
0x180005bb7  mov     rcx, [rdi+28h]
0x180005bbb  lea     r12, [rcx+rax]
0x180005bbf  cmp     r12, rcx
0x180005bc2  jnb     short loc_180005BC7
0x180005bc4  xor     r12d, r12d
0x180005bc7  lea     r14, [r12+8]
0x180005bcc  mov     rdx, r8; String2
0x180005bcf  mov     rcx, [r14]; String1
0x180005bd2  mov     [rbp+String1], rcx
0x180005bd6  call    cs:__imp__wcsicmp
0x180005bdc  test    eax, eax
0x180005bde  jz      short loc_180005C1B
0x180005be0  mov     rcx, [rbp+String1]; String1
0x180005be4  test    rcx, rcx
0x180005be7  jz      short loc_180005C01
0x180005be9  mov     rdx, rsi; String2
0x180005bec  call    cs:__imp__wcsicmp
0x180005bf2  test    eax, eax
0x180005bf4  jnz     short loc_180005C15
0x180005bf6  xor     eax, eax
0x180005bf8  mov     [rbp+String1], rax
0x180005bfc  test    rax, rax
0x180005bff  jnz     short loc_180005C09
0x180005c01  mov     rax, [r13+30h]
0x180005c05  mov     [r12], rax
0x180005c09  mov     r8, [rbp+P]
0x180005c0d  inc     r15
0x180005c10  jmp     loc_180005B67
0x180005c15  mov     rax, [rbp+String1]
0x180005c19  jmp     short loc_180005BFC
0x180005c1b  mov     rdx, rsi
0x180005c1e  mov     rcx, r14
0x180005c21  call    AslStringDuplicate
0x180005c26  mov     ebx, eax
0x180005c28  test    eax, eax
0x180005c2a  js      loc_180005D01
0x180005c30  xor     ebx, ebx
0x180005c32  cmp     rbx, [rdi+40h]
0x180005c36  jnb     short loc_180005C89
0x180005c38  mov     rax, rbx
0x180005c3b  mov     [rbp+arg_18], 0
0x180005c43  mul     qword ptr [rdi+38h]
0x180005c47  test    rdx, rdx
0x180005c4a  jnz     short loc_180005C6F
0x180005c4c  mov     rcx, [rdi+58h]
0x180005c50  lea     rdx, [rcx+rax]; Source2
0x180005c54  cmp     rdx, rcx
0x180005c57  jb      short loc_180005C6F
0x180005c59  mov     r8d, 8; Length
0x180005c5f  lea     rcx, [rbp+String1]; Source1
0x180005c63  call    cs:__imp_RtlCompareMemory
0x180005c69  cmp     rax, 8
0x180005c6d  jz      short loc_180005CB4
0x180005c6f  inc     rbx
0x180005c72  jmp     short loc_180005C32
0x180005c74  mov     rcx, [rdi+58h]
0x180005c78  lea     rdx, [rcx+rax]
0x180005c7c  cmp     rdx, rcx
0x180005c7f  jnb     short loc_180005C83
0x180005c81  xor     edx, edx
0x180005c83  mov     rax, [r14]
0x180005c86  mov     [rdx], rax
0x180005c89  mov     rcx, gs:60h
0x180005c92  mov     rdx, [rbp+String1]
0x180005c96  mov     rcx, [rcx+30h]
0x180005c9a  call    AslFree
0x180005c9f  xor     ecx, ecx
0x180005ca1  mov     [rbp+String1], rcx
0x180005ca5  jmp     loc_180005BE4
0x180005caa  mov     ebx, 0C000000Dh
0x180005caf  jmp     loc_180005B8C
0x180005cb4  test    rbx, rbx
0x180005cb7  js      short loc_180005C89
0x180005cb9  xor     edx, edx
0x180005cbb  cmp     rbx, [rdi+40h]
0x180005cbf  jnb     short loc_180005C83
0x180005cc1  mov     rax, rbx
0x180005cc4  mul     qword ptr [rdi+38h]
0x180005cc8  test    rdx, rdx
0x180005ccb  jnz     short loc_180005C81
0x180005ccd  jmp     short loc_180005C74
0x180005ccf  cmp     eax, 0C0000017h
0x180005cd4  jz      loc_180005B6F
0x180005cda  lea     r9, aFailedToDuplic_0; "Failed to duplicate dll fullpath string"...
0x180005ce1  mov     [rsp+30h+var_10], eax
0x180005ce5  mov     r8d, 110h
0x180005ceb  lea     rdx, aSeshimmanagers; "SeShimManagerShimDllLoaded"
0x180005cf2  mov     ecx, 1
0x180005cf7  call    AslLogCallPrintf
0x180005cfc  jmp     loc_180005B6F
0x180005d01  cmp     eax, 0C0000017h
0x180005d06  jz      short loc_180005D2A
0x180005d08  lea     r9, aFailedToDuplic_0; "Failed to duplicate dll fullpath string"...
0x180005d0f  mov     [rsp+30h+var_10], eax
0x180005d13  mov     r8d, 12Fh
0x180005d19  lea     rdx, aSeshimmanagers; "SeShimManagerShimDllLoaded"
0x180005d20  mov     ecx, 1
0x180005d25  call    AslLogCallPrintf
0x180005d2a  mov     rax, [rbp+String1]
0x180005d2e  mov     [r14], rax
0x180005d31  jmp     loc_180005B6F
```
