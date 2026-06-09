# CspReadUserCertificate

- ea: `0x180020cdc`
- end: `0x180020e21`
- name: `CspReadUserCertificate`
- size: `325`
- prototype: `__int64 __fastcall(__int64, char *, unsigned int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180011ac0`
- `0x180020824`

## callees

- `0x18000de80`
- `0x180019430`
- `0x18001e398`
- `0x18001e66c`
- `0x180020cdc`
- `0x180027f78`
- `0x18002cfa0`

## pseudocode

```c
__int64 __fastcall CspReadUserCertificate(__int64 a1, char *a2, unsigned int *a3)
{
  unsigned int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rcx
  __int64 v8; // rcx
  void *v10; // rax
  unsigned int v11; // eax
  unsigned int v12; // [rsp+30h] [rbp-30h] BYREF
  __int64 v13; // [rsp+38h] [rbp-28h] BYREF
  __int64 v14; // [rsp+40h] [rbp-20h] BYREF
  int v15; // [rsp+48h] [rbp-18h]

  v13 = 0;
  v14 = 0;
  v15 = 0;
  v12 = 0;
  v5 = CspReadFile(a1, "mscp", a2, 0, &v13, &v12);
  v6 = v5;
  if ( v5 )
  {
    if ( v5 == -2146435036 )
      v6 = -2146435028;
    goto LABEL_4;
  }
  v6 = CspQueryCapabilities(a1, &v14);
  if ( v6 )
  {
LABEL_4:
    v7 = *((_QWORD *)a3 + 1);
    if ( v7 )
    {
      CspFreeH(v7);
      *((_QWORD *)a3 + 1) = 0;
    }
    goto LABEL_6;
  }
  if ( !HIDWORD(v14) )
  {
    v6 = UncompressData(v12, v13, a3, 0);
    if ( !v6 )
    {
      v10 = MIDL_user_allocate(*a3);
      *((_QWORD *)a3 + 1) = v10;
      if ( v10 )
      {
        v11 = UncompressData(v12, v13, a3, v10);
        v6 = v11;
        if ( !v11 )
        {
LABEL_6:
          v8 = v13;
          goto LABEL_7;
        }
        if ( v11 == 1359 )
          v6 = -2146893819;
      }
      else
      {
        v6 = -2146893810;
      }
    }
    goto LABEL_4;
  }
  v8 = 0;
  *a3 = v12;
  *((_QWORD *)a3 + 1) = v13;
  v13 = 0;
LABEL_7:
  if ( v8 )
    CspFreeH(v8);
  return v6;
}

```

## disassembly

```asm
0x180020cdc  mov     [rsp-18h+arg_18], rbx
0x180020ce1  push    rbp
0x180020ce2  push    rsi
0x180020ce3  push    rdi
0x180020ce4  mov     rbp, rsp
0x180020ce7  sub     rsp, 60h
0x180020ceb  mov     rax, cs:__security_cookie
0x180020cf2  xor     rax, rsp
0x180020cf5  mov     [rbp+var_10], rax
0x180020cf9  xor     eax, eax
0x180020cfb  mov     [rbp+var_28], 0
0x180020d03  mov     [rbp+var_20], rax
0x180020d07  mov     rdi, r8
0x180020d0a  mov     [rbp+var_18], eax
0x180020d0d  mov     r8, rdx
0x180020d10  lea     rax, [rbp+var_30]
0x180020d14  mov     [rbp+var_30], 0
0x180020d1b  mov     [rsp+60h+var_38], rax
0x180020d20  lea     rdx, aMscp; "mscp"
0x180020d27  lea     rax, [rbp+var_28]
0x180020d2b  xor     r9d, r9d
0x180020d2e  mov     [rsp+60h+var_40], rax
0x180020d33  mov     rsi, rcx
0x180020d36  call    CspReadFile
0x180020d3b  mov     ebx, eax
0x180020d3d  test    eax, eax
0x180020d3f  jz      short loc_180020D8F
0x180020d41  cmp     eax, 80100024h
0x180020d46  jnz     short loc_180020D4D
0x180020d48  mov     ebx, 8010002Ch
0x180020d4d  mov     rcx, [rdi+8]
0x180020d51  test    rcx, rcx
0x180020d54  jz      short loc_180020D63
0x180020d56  call    CspFreeH
0x180020d5b  mov     qword ptr [rdi+8], 0
0x180020d63  mov     rcx, [rbp+var_28]
0x180020d67  test    rcx, rcx
0x180020d6a  jz      short loc_180020D71
0x180020d6c  call    CspFreeH
0x180020d71  mov     eax, ebx
0x180020d73  mov     rcx, [rbp+var_10]
0x180020d77  xor     rcx, rsp; StackCookie
0x180020d7a  call    __security_check_cookie
0x180020d7f  mov     rbx, [rsp+60h+arg_18]
0x180020d87  add     rsp, 60h
0x180020d8b  pop     rdi
0x180020d8c  pop     rsi
0x180020d8d  pop     rbp
0x180020d8e  retn
0x180020d8f  lea     rdx, [rbp+var_20]
0x180020d93  mov     rcx, rsi
0x180020d96  call    CspQueryCapabilities
0x180020d9b  mov     ebx, eax
0x180020d9d  test    eax, eax
0x180020d9f  jnz     short loc_180020D4D
0x180020da1  cmp     dword ptr [rbp+var_20+4], eax
0x180020da4  jnz     short loc_180020E09
0x180020da6  mov     rdx, [rbp+var_28]
0x180020daa  xor     r9d, r9d
0x180020dad  mov     ecx, [rbp+var_30]
0x180020db0  mov     r8, rdi
0x180020db3  call    UncompressData
0x180020db8  mov     ebx, eax
0x180020dba  test    eax, eax
0x180020dbc  jnz     short loc_180020D4D
0x180020dbe  mov     ecx, [rdi]; size
0x180020dc0  call    MIDL_user_allocate
0x180020dc5  mov     [rdi+8], rax
0x180020dc9  test    rax, rax
0x180020dcc  jnz     short loc_180020DD8
0x180020dce  mov     ebx, 8009000Eh
0x180020dd3  jmp     loc_180020D4D
0x180020dd8  mov     rdx, [rbp+var_28]
0x180020ddc  mov     r9, rax
0x180020ddf  mov     ecx, [rbp+var_30]
0x180020de2  mov     r8, rdi
0x180020de5  call    UncompressData
0x180020dea  mov     ebx, eax
0x180020dec  test    eax, eax
0x180020dee  jz      loc_180020D63
0x180020df4  cmp     eax, 54Fh
0x180020df9  jnz     loc_180020D4D
0x180020dff  mov     ebx, 80090005h
0x180020e04  jmp     loc_180020D4D
0x180020e09  mov     eax, [rbp+var_30]
0x180020e0c  xor     ecx, ecx
0x180020e0e  mov     [rdi], eax
0x180020e10  mov     rax, [rbp+var_28]
0x180020e14  mov     [rdi+8], rax
0x180020e18  mov     [rbp+var_28], rcx
0x180020e1c  jmp     loc_180020D67
```
