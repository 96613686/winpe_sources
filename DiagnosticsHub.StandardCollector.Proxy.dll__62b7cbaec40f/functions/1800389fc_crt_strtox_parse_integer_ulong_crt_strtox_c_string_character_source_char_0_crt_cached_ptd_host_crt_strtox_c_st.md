# __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<char>,0>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<char>,int,bool)

- ea: `0x1800389fc`
- end: `0x180038cb0`
- name: `??$parse_integer@KV?$c_string_character_source@D@__crt_strtox@@$0A@@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@D@0@H_N@Z`
- size: `692`
- prototype: `__int64 __fastcall(__crt_cached_ptd_host *)`
- caller_count: `13`
- callee_count: `4`
- tags: ``

## callers

- `0x1800336e8`
- `0x18004336c`
- `0x1800433fc`
- `0x18004348c`
- `0x18004351c`
- `0x1800435ac`
- `0x18004363c`
- `0x1800523e0`
- `0x18005254c`
- `0x1800529e8`
- `0x180052b54`
- `0x180053274`
- `0x1800533b8`

## callees

- `0x180007b48`
- `0x180007c00`
- `0x180007ee8`
- `0x1800389fc`

## pseudocode

```c
__int64 __fastcall __crt_strtox::parse_integer<unsigned long,__crt_strtox::c_string_character_source<char>,0>(
        __crt_cached_ptd_host *a1,
        __int64 a2,
        int a3,
        unsigned __int8 a4)
{
  char *v4; // r12
  unsigned int v5; // ebp
  _QWORD *v8; // rcx
  char v9; // si
  char *v10; // rcx
  unsigned int v11; // r14d
  int v12; // edi
  int v13; // eax
  char v14; // dl
  int v15; // eax
  int v16; // eax
  char *v17; // r8
  unsigned int v18; // r9d
  unsigned int v19; // ecx
  unsigned int v20; // edx
  BOOL v21; // ecx
  bool v22; // cf
  bool v23; // zf
  char **v24; // rax
  int v26; // eax
  int v27; // ecx
  _QWORD *v28; // rdx
  _QWORD *v29; // rax

  v4 = *(char **)a2;
  v5 = a3;
  if ( !*(_QWORD *)a2 )
  {
    *errno() = 22;
    invalid_parameter_noinfo();
    goto LABEL_6;
  }
  if ( a3 && (unsigned int)(a3 - 2) > 0x22 )
  {
    *((_BYTE *)a1 + 48) = 1;
    *((_DWORD *)a1 + 11) = 22;
    invalid_parameter_internal(0, 0, 0, 0, 0, a1);
LABEL_6:
    v8 = *(_QWORD **)(a2 + 8);
    if ( v8 )
      *v8 = *(_QWORD *)a2;
    return 0;
  }
  v9 = *v4;
  v10 = v4 + 1;
  v11 = 0;
  *(_QWORD *)a2 = v4 + 1;
  v12 = a4 | 2;
  if ( v9 == 45 || (v12 = a4, v9 == 43) )
  {
    v9 = *v10;
    v10 = v4 + 2;
    *(_QWORD *)a2 = v4 + 2;
  }
  if ( (a3 & 0xFFFFFFEF) == 0 )
  {
    if ( (unsigned __int8)(v9 - 48) > 9u )
    {
      if ( (unsigned __int8)(v9 - 97) > 0x19u )
      {
        if ( (unsigned __int8)(v9 - 65) > 0x19u )
          goto LABEL_26;
        v13 = v9 - 55;
      }
      else
      {
        v13 = v9 - 87;
      }
    }
    else
    {
      v13 = v9 - 48;
    }
    if ( !v13 )
    {
      v14 = *v10;
      *(_QWORD *)a2 = v10 + 1;
      if ( ((v14 - 88) & 0xDF) != 0 )
      {
        *(_QWORD *)a2 = v10;
        v15 = 8;
        if ( a3 )
          v15 = a3;
        v5 = v15;
        if ( v14 && *v10 != v14 )
        {
          *errno() = 22;
          invalid_parameter_noinfo();
        }
        goto LABEL_30;
      }
      v9 = v10[1];
      *(_QWORD *)a2 = v10 + 2;
      v16 = 16;
      goto LABEL_27;
    }
LABEL_26:
    v16 = 10;
LABEL_27:
    if ( a3 )
      v16 = a3;
    v5 = v16;
  }
LABEL_30:
  v17 = *(char **)a2;
  v18 = 0xFFFFFFFF / v5;
  while ( 1 )
  {
    if ( (unsigned __int8)(v9 - 48) > 9u )
    {
      if ( (unsigned __int8)(v9 - 97) > 0x19u )
        v19 = (unsigned __int8)(v9 - 65) > 0x19u ? -1 : v9 - 55;
      else
        v19 = v9 - 87;
    }
    else
    {
      v19 = v9 - 48;
    }
    if ( v19 >= v5 )
      break;
    v9 = *v17;
    v20 = v5 * v11 + v19;
    v21 = v20 < v5 * v11;
    v22 = v11 < v18;
    v23 = v11 == v18;
    v11 = v20;
    v12 |= (4 * (!v22 && !v23 || v21)) | 8;
    *(_QWORD *)a2 = ++v17;
  }
  *(_QWORD *)a2 = v17 - 1;
  if ( v9 && *(v17 - 1) != v9 )
  {
    *errno() = 22;
    invalid_parameter_noinfo();
  }
  if ( (v12 & 8) == 0 )
  {
    v24 = *(char ***)(a2 + 8);
    *(_QWORD *)a2 = v4;
    if ( v24 )
      *v24 = v4;
    return 0;
  }
  if ( (v12 & 4) != 0 )
  {
    v26 = 1;
    v27 = v12;
    goto LABEL_55;
  }
  if ( (v12 & 1) == 0 )
  {
    if ( (v12 & 2) == 0 )
      goto LABEL_66;
    goto LABEL_65;
  }
  if ( (v12 & 2) == 0 )
  {
    if ( v11 <= 0x7FFFFFFF )
    {
LABEL_66:
      v29 = *(_QWORD **)(a2 + 8);
      if ( v29 )
        *v29 = *(_QWORD *)a2;
      return v11;
    }
    goto LABEL_54;
  }
  if ( v11 <= 0x80000000 )
  {
LABEL_65:
    v11 = -v11;
    goto LABEL_66;
  }
LABEL_54:
  v27 = 1;
  v26 = v12;
LABEL_55:
  *((_BYTE *)a1 + 48) = 1;
  *((_DWORD *)a1 + 11) = 34;
  if ( (v27 & v26) == 0 )
  {
    v11 = -1;
    goto LABEL_66;
  }
  v28 = *(_QWORD **)(a2 + 8);
  if ( (v12 & 2) != 0 )
  {
    if ( v28 )
      *v28 = *(_QWORD *)a2;
    return 0x80000000LL;
  }
  else
  {
    if ( v28 )
      *v28 = *(_QWORD *)a2;
    return 0x7FFFFFFF;
  }
}

```

## disassembly

```asm
0x1800389fc  mov     [rsp+arg_0], rbx
0x180038a01  mov     [rsp+arg_8], rbp
0x180038a06  mov     [rsp+arg_10], rsi
0x180038a0b  push    rdi
0x180038a0c  push    r12
0x180038a0e  push    r13
0x180038a10  push    r14
0x180038a12  push    r15
0x180038a14  sub     rsp, 30h
0x180038a18  mov     r12, [rdx]
0x180038a1b  mov     ebp, r8d
0x180038a1e  mov     rbx, rdx
0x180038a21  mov     r13, rcx
0x180038a24  test    r12, r12
0x180038a27  jnz     short loc_180038A3B
0x180038a29  call    _errno
0x180038a2e  mov     dword ptr [rax], 16h
0x180038a34  call    _invalid_parameter_noinfo
0x180038a39  jmp     short loc_180038A6D
0x180038a3b  test    ebp, ebp
0x180038a3d  jz      short loc_180038A85
0x180038a3f  lea     eax, [r8-2]
0x180038a43  cmp     eax, 22h ; '"'
0x180038a46  jbe     short loc_180038A85
0x180038a48  mov     byte ptr [rcx+30h], 1
0x180038a4c  xor     r9d, r9d; LineNo
0x180038a4f  mov     dword ptr [rcx+2Ch], 16h
0x180038a56  xor     r8d, r8d; FileName
0x180038a59  mov     [rsp+58h+var_30], r13; __crt_cached_ptd_host *
0x180038a5e  xor     ecx, ecx; Expression
0x180038a60  and     [rsp+58h+var_38], 0
0x180038a66  xor     edx, edx; FunctionName
0x180038a68  call    _invalid_parameter_internal
0x180038a6d  mov     rcx, [rbx+8]
0x180038a71  test    rcx, rcx
0x180038a74  jz      loc_180038BF8
0x180038a7a  mov     rax, [rbx]
0x180038a7d  mov     [rcx], rax
0x180038a80  jmp     loc_180038BF8
0x180038a85  mov     sil, [r12]
0x180038a89  lea     rcx, [r12+1]
0x180038a8e  xor     r14d, r14d
0x180038a91  movzx   eax, r9b
0x180038a95  mov     edi, eax
0x180038a97  mov     [rdx], rcx
0x180038a9a  lea     r15d, [r14+2]
0x180038a9e  or      edi, r15d
0x180038aa1  cmp     sil, 2Dh ; '-'
0x180038aa5  cmovnz  edi, eax
0x180038aa8  jz      short loc_180038AB0
0x180038aaa  cmp     sil, 2Bh ; '+'
0x180038aae  jnz     short loc_180038AB9
0x180038ab0  mov     sil, [rcx]
0x180038ab3  inc     rcx
0x180038ab6  mov     [rdx], rcx
0x180038ab9  test    ebp, 0FFFFFFEFh
0x180038abf  jnz     loc_180038B4D
0x180038ac5  lea     eax, [rsi-30h]
0x180038ac8  cmp     al, 9
0x180038aca  ja      short loc_180038AD5
0x180038acc  movsx   eax, sil
0x180038ad0  add     eax, 0FFFFFFD0h
0x180038ad3  jmp     short loc_180038AF3
0x180038ad5  lea     eax, [rsi-61h]
0x180038ad8  cmp     al, 19h
0x180038ada  ja      short loc_180038AE5
0x180038adc  movsx   eax, sil
0x180038ae0  add     eax, 0FFFFFFA9h
0x180038ae3  jmp     short loc_180038AF3
0x180038ae5  lea     eax, [rsi-41h]
0x180038ae8  cmp     al, 19h
0x180038aea  ja      short loc_180038B41
0x180038aec  movsx   eax, sil
0x180038af0  add     eax, 0FFFFFFC9h
0x180038af3  test    eax, eax
0x180038af5  jnz     short loc_180038B41
0x180038af7  mov     dl, [rcx]
0x180038af9  lea     r8, [rcx+1]
0x180038afd  mov     [rbx], r8
0x180038b00  lea     eax, [rdx-58h]
0x180038b03  test    al, 0DFh
0x180038b05  jz      short loc_180038B30
0x180038b07  test    ebp, ebp
0x180038b09  mov     [rbx], rcx
0x180038b0c  mov     eax, 8
0x180038b11  cmovnz  eax, ebp
0x180038b14  mov     ebp, eax
0x180038b16  test    dl, dl
0x180038b18  jz      short loc_180038B4D
0x180038b1a  cmp     [rcx], dl
0x180038b1c  jz      short loc_180038B4D
0x180038b1e  call    _errno
0x180038b23  mov     dword ptr [rax], 16h
0x180038b29  call    _invalid_parameter_noinfo
0x180038b2e  jmp     short loc_180038B4D
0x180038b30  mov     sil, [r8]
0x180038b33  lea     rax, [r8+1]
0x180038b37  mov     [rbx], rax
0x180038b3a  mov     eax, 10h
0x180038b3f  jmp     short loc_180038B46
0x180038b41  mov     eax, 0Ah
0x180038b46  test    ebp, ebp
0x180038b48  cmovnz  eax, ebp
0x180038b4b  mov     ebp, eax
0x180038b4d  mov     r8, [rbx]
0x180038b50  xor     edx, edx
0x180038b52  or      eax, 0FFFFFFFFh
0x180038b55  div     ebp
0x180038b57  mov     r9d, eax
0x180038b5a  lea     ecx, [rsi-30h]
0x180038b5d  cmp     cl, 9
0x180038b60  ja      short loc_180038B6B
0x180038b62  movsx   ecx, sil
0x180038b66  add     ecx, 0FFFFFFD0h
0x180038b69  jmp     short loc_180038B8E
0x180038b6b  lea     eax, [rsi-61h]
0x180038b6e  cmp     al, 19h
0x180038b70  ja      short loc_180038B7B
0x180038b72  movsx   ecx, sil
0x180038b76  add     ecx, 0FFFFFFA9h
0x180038b79  jmp     short loc_180038B8E
0x180038b7b  lea     eax, [rsi-41h]
0x180038b7e  cmp     al, 19h
0x180038b80  ja      short loc_180038B8B
0x180038b82  movsx   ecx, sil
0x180038b86  add     ecx, 0FFFFFFC9h
0x180038b89  jmp     short loc_180038B8E
0x180038b8b  or      ecx, 0FFFFFFFFh
0x180038b8e  cmp     ecx, ebp
0x180038b90  jnb     short loc_180038BC2
0x180038b92  mov     sil, [r8]
0x180038b95  mov     eax, r14d
0x180038b98  imul    eax, ebp
0x180038b9b  lea     edx, [rax+rcx]
0x180038b9e  xor     ecx, ecx
0x180038ba0  cmp     edx, eax
0x180038ba2  setb    cl
0x180038ba5  xor     eax, eax
0x180038ba7  cmp     r14d, r9d
0x180038baa  mov     r14d, edx
0x180038bad  setnbe  al
0x180038bb0  or      ecx, eax
0x180038bb2  shl     ecx, 2
0x180038bb5  or      ecx, 8
0x180038bb8  or      edi, ecx
0x180038bba  inc     r8
0x180038bbd  mov     [rbx], r8
0x180038bc0  jmp     short loc_180038B5A
0x180038bc2  lea     rax, [r8-1]
0x180038bc6  mov     [rbx], rax
0x180038bc9  test    sil, sil
0x180038bcc  jz      short loc_180038BE3
0x180038bce  cmp     [rax], sil
0x180038bd1  jz      short loc_180038BE3
0x180038bd3  call    _errno
0x180038bd8  mov     dword ptr [rax], 16h
0x180038bde  call    _invalid_parameter_noinfo
0x180038be3  test    dil, 8
0x180038be7  jnz     short loc_180038BFF
0x180038be9  mov     rax, [rbx+8]
0x180038bed  mov     [rbx], r12
0x180038bf0  test    rax, rax
0x180038bf3  jz      short loc_180038BF8
0x180038bf5  mov     [rax], r12
0x180038bf8  xor     eax, eax
0x180038bfa  jmp     loc_180038C93
0x180038bff  mov     r8d, 80000000h
0x180038c05  lea     r9d, [r8-1]
0x180038c09  test    dil, 4
0x180038c0d  jz      short loc_180038C18
0x180038c0f  mov     eax, 1
0x180038c14  mov     ecx, edi
0x180038c16  jmp     short loc_180038C36
0x180038c18  test    dil, 1
0x180038c1c  jz      short loc_180038C79
0x180038c1e  test    r15b, dil
0x180038c21  jz      short loc_180038C2A
0x180038c23  cmp     r14d, r8d
0x180038c26  jbe     short loc_180038C7E
0x180038c28  jmp     short loc_180038C2F
0x180038c2a  cmp     r14d, r9d
0x180038c2d  jbe     short loc_180038C81
0x180038c2f  mov     ecx, 1
0x180038c34  mov     eax, edi
0x180038c36  and     r15d, edi
0x180038c39  mov     byte ptr [r13+30h], 1
0x180038c3e  mov     dword ptr [r13+2Ch], 22h ; '"'
0x180038c46  test    eax, ecx
0x180038c48  jnz     short loc_180038C50
0x180038c4a  or      r14d, 0FFFFFFFFh
0x180038c4e  jmp     short loc_180038C81
0x180038c50  mov     rdx, [rbx+8]
0x180038c54  test    r15d, r15d
0x180038c57  jz      short loc_180038C69
0x180038c59  test    rdx, rdx
0x180038c5c  jz      short loc_180038C64
0x180038c5e  mov     rcx, [rbx]
0x180038c61  mov     [rdx], rcx
0x180038c64  mov     eax, r8d
0x180038c67  jmp     short loc_180038C93
0x180038c69  test    rdx, rdx
0x180038c6c  jz      short loc_180038C74
0x180038c6e  mov     rcx, [rbx]
0x180038c71  mov     [rdx], rcx
0x180038c74  mov     eax, r9d
0x180038c77  jmp     short loc_180038C93
0x180038c79  test    r15b, dil
0x180038c7c  jz      short loc_180038C81
0x180038c7e  neg     r14d
0x180038c81  mov     rax, [rbx+8]
0x180038c85  test    rax, rax
0x180038c88  jz      short loc_180038C90
0x180038c8a  mov     rcx, [rbx]
0x180038c8d  mov     [rax], rcx
0x180038c90  mov     eax, r14d
0x180038c93  mov     rbx, [rsp+58h+arg_0]
0x180038c98  mov     rbp, [rsp+58h+arg_8]
0x180038c9d  mov     rsi, [rsp+58h+arg_10]
0x180038ca2  add     rsp, 30h
0x180038ca6  pop     r15
0x180038ca8  pop     r14
0x180038caa  pop     r13
0x180038cac  pop     r12
0x180038cae  pop     rdi
0x180038caf  retn
```
