# SecureInput::Buffer::GetAttributePtr(_IUM_SECURE_BUFFER_ATTRIBUTE_ID,uchar * *,unsigned __int64 *)

- ea: `0x140002bc0`
- end: `0x140002d91`
- name: `?GetAttributePtr@Buffer@SecureInput@@AEBAJW4_IUM_SECURE_BUFFER_ATTRIBUTE_ID@@PEAPEAEPEA_K@Z`
- size: `465`
- prototype: `__int64 __fastcall(__int64, int, char **, _QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x140062ec0`
- `0x140063048`

## callees

- `0x140002bc0`
- `0x14000a420`

## string_xrefs

- `0x140002bda`: `onecore\ds\security\biometrics\service\trustlet\exe\secureinput.cpp`
- `0x140002cb2`: `onecore\ds\security\biometrics\service\trustlet\exe\secureinput.cpp`
- `0x140002cdf`: `onecore\ds\security\biometrics\service\trustlet\exe\secureinput.cpp`
- `0x140002cf8`: `onecore\ds\security\biometrics\service\trustlet\exe\secureinput.cpp`
- `0x140002d25`: `onecore\ds\security\biometrics\service\trustlet\exe\secureinput.cpp`
- `0x140002d52`: `onecore\ds\security\biometrics\service\trustlet\exe\secureinput.cpp`
- `0x140002d6e`: `onecore\ds\security\biometrics\service\trustlet\exe\secureinput.cpp`

## pseudocode

```c
__int64 __fastcall SecureInput::Buffer::GetAttributePtr(__int64 a1, int a2, char **a3, _QWORD *a4)
{
  unsigned int *v4; // rax
  char *v8; // rbx
  char *v9; // rcx
  __int64 v10; // r8
  unsigned int v11; // r9d
  wil::details::in1diag3 *v12; // rcx
  __int64 v13; // rdx
  int v14; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = *(unsigned int **)(a1 + 48);
  if ( v4 )
  {
    if ( a3 && a4 )
    {
      v8 = (char *)v4 + *(_QWORD *)(a1 + 56);
      while ( 1 )
      {
        if ( !v4 )
          goto LABEL_28;
        v9 = (char *)(v4 + 2);
        if ( v4 + 2 < v4 )
          break;
        v10 = *v4;
        if ( (unsigned int *)((char *)v4 + v10) < v4 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xB8,
            (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\secureinput.cpp",
            (const char *)0x80070216LL,
            v14);
          return 2147942934LL;
        }
        if ( v8 < v9 || v8 < (char *)v4 + v10 )
        {
          v12 = retaddr;
          v13 = 187;
          goto LABEL_23;
        }
        if ( (unsigned int)v10 < 8 )
        {
          v12 = retaddr;
          v13 = 189;
          goto LABEL_23;
        }
        v11 = v4[1];
        if ( v11 == a2 )
        {
          if ( a2 )
          {
            if ( a2 != 1 )
              return 2147500033LL;
            v9 = *(char **)v9;
          }
          if ( v9 )
          {
            *a3 = v9;
            *a4 = v10 - 8;
            return 0;
          }
LABEL_28:
          v12 = retaddr;
          v13 = 231;
LABEL_23:
          wil::details::in1diag3::Return_Hr(
            v12,
            (void *)v13,
            (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\secureinput.cpp",
            (const char *)0x80090005LL,
            v14);
          return 2148073477LL;
        }
        if ( v11 == 3 )
          return 2147943568LL;
        v4 = (unsigned int *)((char *)v4 + v10);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB3,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\secureinput.cpp",
        (const char *)0x80070216LL,
        v14);
      return 2147942934LL;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA1,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\secureinput.cpp",
        (const char *)0x80004003LL,
        v14);
      return 2147500035LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9C,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\secureinput.cpp",
      (const char *)0x8007139FLL,
      v14);
    return 2147947423LL;
  }
}

```

## disassembly

```asm
0x140002bc0  push    rdi; int
0x140002bc2  sub     rsp, 20h
0x140002bc6  mov     rax, [rcx+30h]
0x140002bca  mov     rdi, r9
0x140002bcd  mov     r10, r8
0x140002bd0  test    rax, rax
0x140002bd3  jnz     short loc_140002BFB
0x140002bd5  mov     rcx, [rsp+28h]; this
0x140002bda  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\biometrics\\serv"...
0x140002be1  mov     r9d, 8007139Fh; char *
0x140002be7  mov     edx, 9Ch; void *
0x140002bec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002bf1  mov     eax, 8007139Fh
0x140002bf6  jmp     loc_140002CD3
0x140002bfb  test    r10, r10
0x140002bfe  jz      loc_140002D69
0x140002c04  test    rdi, rdi
0x140002c07  jz      loc_140002D69
0x140002c0d  mov     [rsp+28h+arg_0], rbx
0x140002c12  mov     rbx, [rcx+38h]
0x140002c16  add     rbx, rax
0x140002c19  nop     dword ptr [rax+00000000h]
0x140002c20  test    rax, rax
0x140002c23  jz      loc_140002D4D
0x140002c29  lea     rcx, [rax+8]
0x140002c2d  cmp     rcx, rax
0x140002c30  jb      loc_140002D20
0x140002c36  mov     r8d, [rax]
0x140002c39  lea     r11, [r8+rax]
0x140002c3d  cmp     r11, rax
0x140002c40  jb      loc_140002CF3
0x140002c46  cmp     rbx, rcx
0x140002c49  jb      loc_140002CDA
0x140002c4f  cmp     rbx, r11
0x140002c52  jb      loc_140002CDA
0x140002c58  cmp     r8d, 8
0x140002c5c  jb      short loc_140002CAD
0x140002c5e  mov     r9d, [rax+4]
0x140002c62  cmp     r9d, edx
0x140002c65  jz      short loc_140002C79
0x140002c67  cmp     r9d, 3
0x140002c6b  jz      short loc_140002C72
0x140002c6d  mov     rax, r11
0x140002c70  jmp     short loc_140002C20
0x140002c72  mov     eax, 80070490h
0x140002c77  jmp     short loc_140002CCE
0x140002c79  test    edx, edx
0x140002c7b  jz      short loc_140002C96
0x140002c7d  cmp     edx, 1
0x140002c80  jz      short loc_140002C93
0x140002c82  mov     rbx, [rsp+28h+arg_0]
0x140002c87  mov     eax, 80004001h
0x140002c8c  add     rsp, 20h
0x140002c90  pop     rdi
0x140002c91  retn
0x140002c93  mov     rcx, [rcx]
0x140002c96  test    rcx, rcx
0x140002c99  jz      loc_140002D4D
0x140002c9f  lea     rax, [r8-8]
0x140002ca3  mov     [r10], rcx
0x140002ca6  mov     [rdi], rax
0x140002ca9  xor     eax, eax
0x140002cab  jmp     short loc_140002CCE
0x140002cad  mov     rcx, [rsp+28h]; this
0x140002cb2  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\biometrics\\serv"...
0x140002cb9  mov     r9d, 80090005h; char *
0x140002cbf  mov     edx, 0BDh; void *
0x140002cc4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002cc9  mov     eax, 80090005h
0x140002cce  mov     rbx, [rsp+28h+arg_0]
0x140002cd3  add     rsp, 20h
0x140002cd7  pop     rdi
0x140002cd8  retn
0x140002cda  mov     rcx, [rsp+28h]
0x140002cdf  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\biometrics\\serv"...
0x140002ce6  mov     r9d, 80090005h
0x140002cec  mov     edx, 0BBh
0x140002cf1  jmp     short loc_140002CC4
0x140002cf3  mov     rcx, [rsp+28h]; this
0x140002cf8  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\biometrics\\serv"...
0x140002cff  mov     r9d, 80070216h; char *
0x140002d05  mov     edx, 0B8h; void *
0x140002d0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002d0f  mov     rbx, [rsp+28h+arg_0]
0x140002d14  mov     eax, 80070216h
0x140002d19  add     rsp, 20h
0x140002d1d  pop     rdi
0x140002d1e  retn
0x140002d20  mov     rcx, [rsp+28h]; this
0x140002d25  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\biometrics\\serv"...
0x140002d2c  mov     r9d, 80070216h; char *
0x140002d32  mov     edx, 0B3h; void *
0x140002d37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002d3c  mov     rbx, [rsp+28h+arg_0]
0x140002d41  mov     eax, 80070216h
0x140002d46  add     rsp, 20h
0x140002d4a  pop     rdi
0x140002d4b  retn
0x140002d4d  mov     rcx, [rsp+28h]
0x140002d52  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\biometrics\\serv"...
0x140002d59  mov     r9d, 80090005h
0x140002d5f  mov     edx, 0E7h
0x140002d64  jmp     loc_140002CC4
0x140002d69  mov     rcx, [rsp+28h]; this
0x140002d6e  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\biometrics\\serv"...
0x140002d75  mov     r9d, 80004003h; char *
0x140002d7b  mov     edx, 0A1h; void *
0x140002d80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002d85  mov     eax, 80004003h
0x140002d8a  add     rsp, 20h
0x140002d8e  pop     rdi
0x140002d8f  retn
```
