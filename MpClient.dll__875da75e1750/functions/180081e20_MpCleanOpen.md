# MpCleanOpen

- ea: `0x180081e20`
- end: `0x180082221`
- name: `MpCleanOpen`
- size: `1025`
- prototype: `__int64 __fastcall(int *, __int64, _QWORD *, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation`

## callees

- `0x18003b830`
- `0x180072da4`
- `0x180073384`
- `0x1800733a8`
- `0x180078724`
- `0x180078e00`
- `0x1800818e4`
- `0x180081e20`
- `0x180089890`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180082056`
- `KERNEL32!GetCurrentProcessId` at `0x180082056`
- `RPCRT4!NdrClientCall3` at `0x180081ff2`
- `RPCRT4!NdrClientCall3` at `0x180082091`
- `RPCRT4!NdrClientCall3` at `0x180082145`
- `RPCRT4!NdrClientCall3` at `0x180081ff2`
- `RPCRT4!NdrClientCall3` at `0x180082091`
- `RPCRT4!NdrClientCall3` at `0x180082145`

## pseudocode

```c
__int64 __fastcall MpCleanOpen(int *a1, __int64 a2, _QWORD *a3, __int64 a4)
{
  _BYTE *v7; // rcx
  signed int Pointer; // ebx
  __int64 v9; // r15
  __int64 v10; // r13
  __int64 v11; // rdx
  _OWORD *v13; // rax
  __int64 v14; // r9
  _DWORD *v15; // rsi
  int v16; // ecx
  int v17; // ecx
  int v18; // eax
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r9
  CLIENT_CALL_RETURN v22; // rdx
  signed int v23; // edi
  CLIENT_CALL_RETURN v24; // r8
  CLIENT_CALL_RETURN v25; // r9
  DWORD CurrentProcessId; // [rsp+30h] [rbp-40h]
  __int64 v27; // [rsp+50h] [rbp-20h] BYREF
  __int64 v28; // [rsp+58h] [rbp-18h] BYREF
  int v29; // [rsp+60h] [rbp-10h] BYREF

  v7 = off_18019DE80;
  if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 4) != 0 )
  {
    sub_180073384(*((_QWORD *)off_18019DE80 + 2), 10, qword_180145AC8, a4);
    v7 = off_18019DE80;
  }
  v28 = 0;
  Pointer = 0;
  v29 = 0;
  v9 = 0;
  v27 = 0;
  v10 = 0;
  if ( !a1 || !a3 )
  {
    if ( v7 == (_BYTE *)&off_18019DE80 || (v7[28] & 1) == 0 )
      return 2147942487LL;
    v11 = 11;
    goto LABEL_65;
  }
  if ( a2 && (!*(_DWORD *)a2 || !*(_QWORD *)(a2 + 8) || !*(_QWORD *)(a2 + 16)) )
  {
    if ( v7 == (_BYTE *)&off_18019DE80 || (v7[28] & 1) == 0 )
      return 2147942487LL;
    v11 = 12;
LABEL_65:
    sub_180073384(*((_QWORD *)v7 + 2), v11, qword_180145AC8, a4);
    return 2147942487LL;
  }
  if ( *a1 != 2 && *a1 != 1 )
  {
    if ( v7 != (_BYTE *)&off_18019DE80 && (v7[28] & 1) != 0 )
      sub_180073384(*((_QWORD *)v7 + 2), 13, qword_180145AC8, a4);
    return 2147942406LL;
  }
  v13 = (_OWORD *)MpAllocMemory(0x10u);
  v15 = v13;
  if ( !v13 )
  {
    Pointer = -2147024882;
    if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
      sub_180073384(*((_QWORD *)off_18019DE80 + 2), 14, qword_180145AC8, v14);
    goto LABEL_48;
  }
  v16 = *a1;
  *v13 = 0;
  v17 = v16 - 1;
  if ( v17 )
  {
    if ( v17 == 1 )
    {
      v10 = *((_QWORD *)a1 + 1);
      v18 = sub_180078724(0, *(_QWORD *)(v10 + 24), &v27);
      Pointer = v18;
      if ( v18 < 0 )
      {
        v19 = off_18019DE80;
        if ( off_18019DE80 == (_UNKNOWN *)&off_18019DE80 || (*((_BYTE *)off_18019DE80 + 28) & 1) == 0 )
          goto LABEL_48;
        v20 = 16;
        goto LABEL_34;
      }
      Pointer = (unsigned int)NdrClientCall3(
                                (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                                0x16u,
                                0,
                                *(_QWORD *)(*((_QWORD *)a1 + 1) + 32LL),
                                a2,
                                &v28,
                                &v29).Pointer;
    }
  }
  else
  {
    v9 = *((_QWORD *)a1 + 1);
    v18 = sub_180078724(0, v9, &v27);
    Pointer = v18;
    if ( v18 < 0 )
    {
      v19 = off_18019DE80;
      if ( off_18019DE80 == (_UNKNOWN *)&off_18019DE80 || (*((_BYTE *)off_18019DE80 + 28) & 1) == 0 )
        goto LABEL_48;
      v20 = 15;
      goto LABEL_34;
    }
    CurrentProcessId = GetCurrentProcessId();
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                              0x15u,
                              0,
                              v27,
                              *(_DWORD *)(v9 + 16),
                              a2,
                              CurrentProcessId,
                              &v28,
                              &v29).Pointer;
  }
  if ( v29 )
    Pointer = v29 | 0x80010000;
  if ( Pointer < 0 )
  {
    v19 = off_18019DE80;
    if ( off_18019DE80 == (_UNKNOWN *)&off_18019DE80 || (*((_BYTE *)off_18019DE80 + 28) & 1) == 0 )
      goto LABEL_48;
    v20 = 17;
    v21 = (unsigned int)Pointer;
    goto LABEL_35;
  }
  v18 = sub_1800818E4(v10, v9, &v28, v15 + 2);
  Pointer = v18;
  if ( v18 >= 0 )
  {
    *v15 = 3;
    goto LABEL_48;
  }
  v19 = off_18019DE80;
  if ( off_18019DE80 == (_UNKNOWN *)&off_18019DE80 || (*((_BYTE *)off_18019DE80 + 28) & 1) == 0 )
    goto LABEL_48;
  v20 = 18;
LABEL_34:
  v21 = (unsigned int)v18;
LABEL_35:
  sub_1800733A8(v19[2], v20, qword_180145AC8, v21);
LABEL_48:
  if ( v28 )
  {
    v23 = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x1Du, 0, v27, &v28, &v29).Pointer;
    if ( v29 )
    {
      v23 = v29 | 0x80010000;
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))sub_180072DA4)(
        v28,
        (CLIENT_CALL_RETURN)v22.Simple,
        (CLIENT_CALL_RETURN)v24.Simple,
        (CLIENT_CALL_RETURN)v25.Simple);
    }
    if ( v23 < 0 && off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
      sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 19, qword_180145AC8, (unsigned int)v23);
  }
  if ( Pointer < 0 && v15 )
  {
    MpHandleClose(v15);
    v15 = 0;
  }
  *a3 = v15;
  if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 4) != 0 )
    sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 20, qword_180145AC8, (unsigned int)Pointer);
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180081e20  mov     [rsp-38h+arg_18], rbx
0x180081e25  push    rbp
0x180081e26  push    rsi
0x180081e27  push    rdi
0x180081e28  push    r12
0x180081e2a  push    r13
0x180081e2c  push    r14
0x180081e2e  push    r15
0x180081e30  mov     rbp, rsp
0x180081e33  sub     rsp, 70h
0x180081e37  mov     rax, cs:__security_cookie
0x180081e3e  xor     rax, rsp
0x180081e41  mov     [rbp+var_8], rax
0x180081e45  mov     r12, r8
0x180081e48  mov     rdi, rdx
0x180081e4b  mov     r14, rcx
0x180081e4e  mov     rcx, cs:off_18019DE80
0x180081e55  lea     rdx, off_18019DE80
0x180081e5c  cmp     rcx, rdx
0x180081e5f  jz      short loc_180081E8A
0x180081e61  test    byte ptr [rcx+1Ch], 4
0x180081e65  jz      short loc_180081E8A
0x180081e67  mov     rcx, [rcx+10h]
0x180081e6b  lea     r8, qword_180145AC8
0x180081e72  mov     edx, 0Ah
0x180081e77  call    sub_180073384
0x180081e7c  mov     rcx, cs:off_18019DE80
0x180081e83  lea     rdx, off_18019DE80
0x180081e8a  xor     eax, eax
0x180081e8c  mov     [rbp+var_18], rax
0x180081e90  mov     ebx, eax
0x180081e92  mov     [rbp+var_10], eax
0x180081e95  mov     r15d, eax
0x180081e98  mov     [rbp+var_20], rax
0x180081e9c  mov     r13d, eax
0x180081e9f  test    r14, r14
0x180081ea2  jz      loc_1800821D8
0x180081ea8  test    r12, r12
0x180081eab  jz      loc_1800821D8
0x180081eb1  test    rdi, rdi
0x180081eb4  jz      short loc_180081EE3
0x180081eb6  cmp     [rdi], eax
0x180081eb8  jz      short loc_180081EC6
0x180081eba  cmp     [rdi+8], rax
0x180081ebe  jz      short loc_180081EC6
0x180081ec0  cmp     [rdi+10h], rax
0x180081ec4  jnz     short loc_180081EE3
0x180081ec6  cmp     rcx, rdx
0x180081ec9  jz      loc_1800821F8
0x180081ecf  test    byte ptr [rcx+1Ch], 1
0x180081ed3  jz      loc_1800821F8
0x180081ed9  mov     edx, 0Ch
0x180081ede  jmp     loc_1800821E8
0x180081ee3  cmp     dword ptr [r14], 2
0x180081ee7  jz      short loc_180081F19
0x180081ee9  cmp     dword ptr [r14], 1
0x180081eed  jz      short loc_180081F19
0x180081eef  cmp     rcx, rdx
0x180081ef2  jz      short loc_180081F0F
0x180081ef4  test    byte ptr [rcx+1Ch], 1
0x180081ef8  jz      short loc_180081F0F
0x180081efa  mov     rcx, [rcx+10h]
0x180081efe  lea     r8, qword_180145AC8
0x180081f05  mov     edx, 0Dh
0x180081f0a  call    sub_180073384
0x180081f0f  mov     eax, 80070006h
0x180081f14  jmp     loc_1800821FD
0x180081f19  mov     ecx, 10h; dwBytes
0x180081f1e  call    MpAllocMemory
0x180081f23  mov     rsi, rax
0x180081f26  test    rax, rax
0x180081f29  jnz     short loc_180081F69
0x180081f2b  mov     ebx, 8007000Eh
0x180081f30  mov     rcx, cs:off_18019DE80
0x180081f37  lea     r14, off_18019DE80
0x180081f3e  cmp     rcx, r14
0x180081f41  jz      loc_18008211A
0x180081f47  test    byte ptr [rcx+1Ch], 1
0x180081f4b  jz      loc_18008211A
0x180081f51  mov     rcx, [rcx+10h]
0x180081f55  lea     edx, [rax+0Eh]
0x180081f58  lea     r8, qword_180145AC8
0x180081f5f  call    sub_180073384
0x180081f64  jmp     loc_18008211A
0x180081f69  mov     ecx, [r14]
0x180081f6c  xorps   xmm0, xmm0
0x180081f6f  movups  xmmword ptr [rax], xmm0
0x180081f72  sub     ecx, 1
0x180081f75  jz      loc_180082000
0x180081f7b  cmp     ecx, 1
0x180081f7e  jnz     loc_180082099
0x180081f84  mov     r13, [r14+8]
0x180081f88  lea     r8, [rbp+var_20]
0x180081f8c  xor     ecx, ecx
0x180081f8e  mov     rdx, [r13+18h]
0x180081f92  call    sub_180078724
0x180081f97  mov     ebx, eax
0x180081f99  test    eax, eax
0x180081f9b  jns     short loc_180081FC5
0x180081f9d  mov     rcx, cs:off_18019DE80
0x180081fa4  lea     r14, off_18019DE80
0x180081fab  cmp     rcx, r14
0x180081fae  jz      loc_18008211A
0x180081fb4  test    byte ptr [rcx+1Ch], 1
0x180081fb8  jz      loc_18008211A
0x180081fbe  mov     edx, 10h
0x180081fc3  jmp     short loc_18008203E
0x180081fc5  mov     r9, [r14+8]
0x180081fc9  lea     rax, [rbp+var_10]
0x180081fcd  mov     [rsp+70h+var_40], rax
0x180081fd2  lea     rcx, pProxyInfo; pProxyInfo
0x180081fd9  xor     r8d, r8d; pReturnValue
0x180081fdc  lea     rax, [rbp+var_18]
0x180081fe0  mov     [rsp+70h+var_48], rax
0x180081fe5  mov     r9, [r9+20h]
0x180081fe9  mov     [rsp+70h+var_50], rdi
0x180081fee  lea     edx, [r8+16h]; nProcNum
0x180081ff2  call    cs:NdrClientCall3
0x180081ff8  mov     rbx, rax
0x180081ffb  jmp     loc_180082099
0x180082000  mov     r15, [r14+8]
0x180082004  lea     r8, [rbp+var_20]
0x180082008  mov     rdx, r15
0x18008200b  xor     ecx, ecx
0x18008200d  call    sub_180078724
0x180082012  mov     ebx, eax
0x180082014  test    eax, eax
0x180082016  jns     short loc_180082056
0x180082018  mov     rcx, cs:off_18019DE80
0x18008201f  lea     r14, off_18019DE80
0x180082026  cmp     rcx, r14
0x180082029  jz      loc_18008211A
0x18008202f  test    byte ptr [rcx+1Ch], 1
0x180082033  jz      loc_18008211A
0x180082039  mov     edx, 0Fh
0x18008203e  mov     r9d, eax
0x180082041  mov     rcx, [rcx+10h]
0x180082045  lea     r8, qword_180145AC8
0x18008204c  call    sub_1800733A8
0x180082051  jmp     loc_18008211A
0x180082056  call    cs:GetCurrentProcessId
0x18008205c  mov     r9, [rbp+var_20]
0x180082060  lea     rcx, [rbp+var_10]
0x180082064  mov     [rsp+70h+var_30], rcx
0x180082069  xor     r8d, r8d; pReturnValue
0x18008206c  lea     rcx, [rbp+var_18]
0x180082070  mov     [rsp+70h+var_38], rcx
0x180082075  lea     rcx, pProxyInfo; pProxyInfo
0x18008207c  mov     dword ptr [rsp+70h+var_40], eax
0x180082080  mov     eax, [r15+10h]
0x180082084  lea     edx, [r8+15h]; nProcNum
0x180082088  mov     [rsp+70h+var_48], rdi
0x18008208d  mov     dword ptr [rsp+70h+var_50], eax
0x180082091  call    cs:NdrClientCall3
0x180082097  mov     ebx, eax
0x180082099  mov     eax, [rbp+var_10]
0x18008209c  test    eax, eax
0x18008209e  jz      short loc_1800820A7
0x1800820a0  or      eax, 80010000h
0x1800820a5  mov     ebx, eax
0x1800820a7  test    ebx, ebx
0x1800820a9  jns     short loc_1800820D1
0x1800820ab  mov     rcx, cs:off_18019DE80
0x1800820b2  lea     r14, off_18019DE80
0x1800820b9  cmp     rcx, r14
0x1800820bc  jz      short loc_18008211A
0x1800820be  test    byte ptr [rcx+1Ch], 1
0x1800820c2  jz      short loc_18008211A
0x1800820c4  mov     edx, 11h
0x1800820c9  mov     r9d, ebx
0x1800820cc  jmp     loc_180082041
0x1800820d1  lea     r9, [rsi+8]
0x1800820d5  mov     rdx, r15
0x1800820d8  lea     r8, [rbp+var_18]
0x1800820dc  mov     rcx, r13
0x1800820df  call    sub_1800818E4
0x1800820e4  mov     ebx, eax
0x1800820e6  test    eax, eax
0x1800820e8  jns     short loc_18008210D
0x1800820ea  mov     rcx, cs:off_18019DE80
0x1800820f1  lea     r14, off_18019DE80
0x1800820f8  cmp     rcx, r14
0x1800820fb  jz      short loc_18008211A
0x1800820fd  test    byte ptr [rcx+1Ch], 1
0x180082101  jz      short loc_18008211A
0x180082103  mov     edx, 12h
0x180082108  jmp     loc_18008203E
0x18008210d  mov     dword ptr [rsi], 3
0x180082113  lea     r14, off_18019DE80
0x18008211a  cmp     [rbp+var_18], 0
0x18008211f  jz      short loc_180082193
0x180082121  mov     r9, [rbp+var_20]
0x180082125  lea     rax, [rbp+var_10]
0x180082129  mov     [rsp+70h+var_48], rax
0x18008212e  lea     rcx, pProxyInfo; pProxyInfo
0x180082135  xor     r8d, r8d; pReturnValue
0x180082138  lea     rax, [rbp+var_18]
0x18008213c  mov     [rsp+70h+var_50], rax
0x180082141  lea     edx, [r8+1Dh]; nProcNum
0x180082145  call    cs:NdrClientCall3
0x18008214b  mov     rdi, rax
0x18008214e  mov     eax, [rbp+var_10]
0x180082151  test    eax, eax
0x180082153  jz      short loc_180082165
0x180082155  mov     rcx, [rbp+var_18]
0x180082159  or      eax, 80010000h
0x18008215e  mov     edi, eax
0x180082160  call    sub_180072DA4
0x180082165  test    edi, edi
0x180082167  jns     short loc_180082193
0x180082169  mov     rcx, cs:off_18019DE80
0x180082170  cmp     rcx, r14
0x180082173  jz      short loc_180082193
0x180082175  test    byte ptr [rcx+1Ch], 1
0x180082179  jz      short loc_180082193
0x18008217b  mov     rcx, [rcx+10h]
0x18008217f  lea     r8, qword_180145AC8
0x180082186  mov     edx, 13h
0x18008218b  mov     r9d, edi
0x18008218e  call    sub_1800733A8
0x180082193  test    ebx, ebx
0x180082195  jns     short loc_1800821A6
0x180082197  test    rsi, rsi
0x18008219a  jz      short loc_1800821A6
0x18008219c  mov     rcx, rsi; lpMem
0x18008219f  call    MpHandleClose
0x1800821a4  xor     esi, esi
0x1800821a6  mov     [r12], rsi
0x1800821aa  mov     rcx, cs:off_18019DE80
0x1800821b1  cmp     rcx, r14
0x1800821b4  jz      short loc_1800821D4
0x1800821b6  test    byte ptr [rcx+1Ch], 4
0x1800821ba  jz      short loc_1800821D4
0x1800821bc  mov     rcx, [rcx+10h]
0x1800821c0  lea     r8, qword_180145AC8
0x1800821c7  mov     edx, 14h
0x1800821cc  mov     r9d, ebx
0x1800821cf  call    sub_1800733A8
0x1800821d4  mov     eax, ebx
0x1800821d6  jmp     short loc_1800821FD
0x1800821d8  cmp     rcx, rdx
0x1800821db  jz      short loc_1800821F8
0x1800821dd  test    byte ptr [rcx+1Ch], 1
0x1800821e1  jz      short loc_1800821F8
0x1800821e3  mov     edx, 0Bh
0x1800821e8  mov     rcx, [rcx+10h]
0x1800821ec  lea     r8, qword_180145AC8
0x1800821f3  call    sub_180073384
0x1800821f8  mov     eax, 80070057h
0x1800821fd  mov     rcx, [rbp+var_8]
0x180082201  xor     rcx, rsp; StackCookie
0x180082204  call    __security_check_cookie
0x180082209  mov     rbx, [rsp+70h+arg_18]
0x180082211  add     rsp, 70h
0x180082215  pop     r15
0x180082217  pop     r14
0x180082219  pop     r13
0x18008221b  pop     r12
0x18008221d  pop     rdi
0x18008221e  pop     rsi
0x18008221f  pop     rbp
0x180082220  retn
```
