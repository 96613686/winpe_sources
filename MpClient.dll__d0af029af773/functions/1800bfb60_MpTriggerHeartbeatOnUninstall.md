# MpTriggerHeartbeatOnUninstall

- ea: `0x1800bfb60`
- end: `0x1800bfe31`
- name: `MpTriggerHeartbeatOnUninstall`
- size: `721`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, installer_update`

## callees

- `0x18001c9bc`
- `0x18003b830`
- `0x18003bcc8`
- `0x1800733a8`
- `0x180078724`
- `0x1800bfb60`
- `0x1800ce5ac`
- `0x1800dcfc4`
- `0x180112ee0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x1800bfd95`
- `RPCRT4!NdrClientCall3` at `0x1800bfd95`

## string_xrefs

- `0x1800bfc72`: `MpService_NoCertCheck`
- `0x1800bfc97`: `MpService_AllowTestCert`

## pseudocode

```c
__int64 __fastcall MpTriggerHeartbeatOnUninstall(__int64 a1)
{
  signed int Pointer; // ebx
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  int v8; // eax
  int v9; // eax
  __int64 v10; // [rsp+30h] [rbp-20h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-18h] BYREF
  int v12; // [rsp+40h] [rbp-10h] BYREF

  LODWORD(v10) = 0;
  Pointer = sub_1800DCFC4(a1, 1, &v10);
  if ( Pointer < 0 )
  {
    v3 = off_18019DE80;
    if ( off_18019DE80 == (_UNKNOWN *)&off_18019DE80 || (*((_BYTE *)off_18019DE80 + 28) & 1) == 0 )
      return (unsigned int)Pointer;
    v4 = 16;
LABEL_5:
    sub_1800733A8(v3[2], v4, &stru_180147910, (unsigned int)Pointer);
    return (unsigned int)Pointer;
  }
  if ( !(_DWORD)v10 )
  {
    Pointer = -2147024891;
    v3 = off_18019DE80;
    if ( off_18019DE80 == (_UNKNOWN *)&off_18019DE80 || (*((_BYTE *)off_18019DE80 + 28) & 1) == 0 )
      return (unsigned int)Pointer;
    v4 = 17;
    goto LABEL_5;
  }
  lpMem = 0;
  Pointer = sub_18001C9BC(&lpMem, 0, 0);
  if ( Pointer < 0 )
  {
    v6 = off_18019DE80;
    if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
    {
      v7 = 18;
LABEL_15:
      sub_1800733A8(v6[2], v7, &stru_180147910, (unsigned int)Pointer);
      goto LABEL_16;
    }
    goto LABEL_16;
  }
  LODWORD(v10) = 0;
  if ( (int)sub_180112EE0(L"MpService_NoCertCheck", 0, &v10) >= 0 )
    v8 = v10;
  else
    v8 = 0;
  if ( !v8 )
  {
    LODWORD(v10) = 0;
    v9 = (int)sub_180112EE0(L"MpService_AllowTestCert", 0, &v10) >= 0 ? v10 : 0;
    Pointer = sub_1800CE5AC(lpMem, v9 != 0 ? 36 : 4, 0);
    if ( Pointer < 0 )
    {
      v6 = off_18019DE80;
      if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
      {
        v7 = 19;
        goto LABEL_15;
      }
LABEL_16:
      if ( lpMem )
        sub_18003BCC8(lpMem);
      return (unsigned int)Pointer;
    }
  }
  if ( *(_DWORD *)a1 != 1 )
  {
    Pointer = -2147024809;
    v6 = off_18019DE80;
    if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
    {
      v7 = 20;
      goto LABEL_15;
    }
    goto LABEL_16;
  }
  v10 = 0;
  Pointer = sub_180078724(0, *(_QWORD *)(a1 + 8), &v10);
  if ( Pointer < 0 )
  {
    v6 = off_18019DE80;
    if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
    {
      v7 = 21;
      goto LABEL_15;
    }
    goto LABEL_16;
  }
  v12 = 0;
  Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x6Fu, 0, v10, &v12).Pointer;
  if ( Pointer < 0 )
  {
    v6 = off_18019DE80;
    if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
    {
      v7 = 22;
      goto LABEL_15;
    }
    goto LABEL_16;
  }
  if ( v12 )
  {
    Pointer = v12 | 0x80010000;
    v6 = off_18019DE80;
    if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
    {
      v7 = 23;
      goto LABEL_15;
    }
    goto LABEL_16;
  }
  if ( lpMem )
    sub_18003BCC8(lpMem);
  return 0;
}

```

## disassembly

```asm
0x1800bfb60  mov     [rsp-8+arg_8], rbx
0x1800bfb65  mov     [rsp-8+arg_10], rdi
0x1800bfb6a  push    rbp
0x1800bfb6b  mov     rbp, rsp
0x1800bfb6e  sub     rsp, 50h
0x1800bfb72  mov     rax, cs:__security_cookie
0x1800bfb79  xor     rax, rsp
0x1800bfb7c  mov     [rbp+var_8], rax
0x1800bfb80  mov     rdi, rcx
0x1800bfb83  mov     dword ptr [rbp+var_20], 0
0x1800bfb8a  lea     r8, [rbp+var_20]
0x1800bfb8e  mov     edx, 1
0x1800bfb93  call    sub_1800DCFC4
0x1800bfb98  mov     ebx, eax
0x1800bfb9a  test    eax, eax
0x1800bfb9c  jns     short loc_1800BFBD6
0x1800bfb9e  lea     rdx, off_18019DE80
0x1800bfba5  mov     rcx, cs:off_18019DE80
0x1800bfbac  cmp     rcx, rdx
0x1800bfbaf  jz      short loc_1800BFBCF
0x1800bfbb1  test    byte ptr [rcx+1Ch], 1
0x1800bfbb5  jz      short loc_1800BFBCF
0x1800bfbb7  mov     edx, 10h
0x1800bfbbc  mov     r9d, ebx
0x1800bfbbf  lea     r8, stru_180147910
0x1800bfbc6  mov     rcx, [rcx+10h]
0x1800bfbca  call    sub_1800733A8
0x1800bfbcf  mov     eax, ebx
0x1800bfbd1  jmp     loc_1800BFE15
0x1800bfbd6  cmp     dword ptr [rbp+var_20], 0
0x1800bfbda  jnz     short loc_1800BFC01
0x1800bfbdc  lea     rdx, off_18019DE80
0x1800bfbe3  mov     ebx, 80070005h
0x1800bfbe8  mov     rcx, cs:off_18019DE80
0x1800bfbef  cmp     rcx, rdx
0x1800bfbf2  jz      short loc_1800BFBCF
0x1800bfbf4  test    byte ptr [rcx+1Ch], 1
0x1800bfbf8  jz      short loc_1800BFBCF
0x1800bfbfa  mov     edx, 11h
0x1800bfbff  jmp     short loc_1800BFBBC
0x1800bfc01  mov     [rbp+lpMem], 0
0x1800bfc09  xor     r8d, r8d
0x1800bfc0c  xor     edx, edx
0x1800bfc0e  lea     rcx, [rbp+lpMem]
0x1800bfc12  call    sub_18001C9BC
0x1800bfc17  mov     ebx, eax
0x1800bfc19  test    eax, eax
0x1800bfc1b  jns     short loc_1800BFC65
0x1800bfc1d  lea     rdx, off_18019DE80
0x1800bfc24  mov     rcx, cs:off_18019DE80
0x1800bfc2b  cmp     rcx, rdx
0x1800bfc2e  jz      short loc_1800BFC4E
0x1800bfc30  test    byte ptr [rcx+1Ch], 1
0x1800bfc34  jz      short loc_1800BFC4E
0x1800bfc36  mov     edx, 12h
0x1800bfc3b  mov     r9d, ebx
0x1800bfc3e  lea     r8, stru_180147910
0x1800bfc45  mov     rcx, [rcx+10h]
0x1800bfc49  call    sub_1800733A8
0x1800bfc4e  mov     rcx, [rbp+lpMem]; lpMem
0x1800bfc52  test    rcx, rcx
0x1800bfc55  jz      loc_1800BFBCF
0x1800bfc5b  call    sub_18003BCC8
0x1800bfc60  jmp     loc_1800BFBCF
0x1800bfc65  mov     dword ptr [rbp+var_20], 0
0x1800bfc6c  lea     r8, [rbp+var_20]
0x1800bfc70  xor     edx, edx
0x1800bfc72  lea     rcx, aMpserviceNocer; "MpService_NoCertCheck"
0x1800bfc79  call    sub_180112EE0
0x1800bfc7e  nop
0x1800bfc7f  test    eax, eax
0x1800bfc81  jns     short loc_1800BFC87
0x1800bfc83  xor     eax, eax
0x1800bfc85  jmp     short loc_1800BFC8A
0x1800bfc87  mov     eax, dword ptr [rbp+var_20]
0x1800bfc8a  test    eax, eax
0x1800bfc8c  jnz     short loc_1800BFCF6
0x1800bfc8e  mov     dword ptr [rbp+var_20], eax
0x1800bfc91  lea     r8, [rbp+var_20]
0x1800bfc95  xor     edx, edx
0x1800bfc97  lea     rcx, aMpserviceAllow; "MpService_AllowTestCert"
0x1800bfc9e  call    sub_180112EE0
0x1800bfca3  nop
0x1800bfca4  test    eax, eax
0x1800bfca6  jns     short loc_1800BFCAC
0x1800bfca8  xor     eax, eax
0x1800bfcaa  jmp     short loc_1800BFCAF
0x1800bfcac  mov     eax, dword ptr [rbp+var_20]
0x1800bfcaf  neg     eax
0x1800bfcb1  sbb     edx, edx
0x1800bfcb3  and     edx, 20h
0x1800bfcb6  add     edx, 4
0x1800bfcb9  xor     r8d, r8d
0x1800bfcbc  mov     rcx, [rbp+lpMem]
0x1800bfcc0  call    sub_1800CE5AC
0x1800bfcc5  mov     ebx, eax
0x1800bfcc7  test    eax, eax
0x1800bfcc9  jns     short loc_1800BFCF6
0x1800bfccb  lea     rdx, off_18019DE80
0x1800bfcd2  mov     rcx, cs:off_18019DE80
0x1800bfcd9  cmp     rcx, rdx
0x1800bfcdc  jz      loc_1800BFC4E
0x1800bfce2  test    byte ptr [rcx+1Ch], 1
0x1800bfce6  jz      loc_1800BFC4E
0x1800bfcec  mov     edx, 13h
0x1800bfcf1  jmp     loc_1800BFC3B
0x1800bfcf6  cmp     dword ptr [rdi], 1
0x1800bfcf9  jz      short loc_1800BFD2B
0x1800bfcfb  lea     rdx, off_18019DE80
0x1800bfd02  mov     ebx, 80070057h
0x1800bfd07  mov     rcx, cs:off_18019DE80
0x1800bfd0e  cmp     rcx, rdx
0x1800bfd11  jz      loc_1800BFC4E
0x1800bfd17  test    byte ptr [rcx+1Ch], 1
0x1800bfd1b  jz      loc_1800BFC4E
0x1800bfd21  mov     edx, 14h
0x1800bfd26  jmp     loc_1800BFC3B
0x1800bfd2b  mov     [rbp+var_20], 0
0x1800bfd33  lea     r8, [rbp+var_20]
0x1800bfd37  mov     rdx, [rdi+8]
0x1800bfd3b  xor     ecx, ecx
0x1800bfd3d  call    sub_180078724
0x1800bfd42  mov     ebx, eax
0x1800bfd44  test    eax, eax
0x1800bfd46  jns     short loc_1800BFD73
0x1800bfd48  lea     rdx, off_18019DE80
0x1800bfd4f  mov     rcx, cs:off_18019DE80
0x1800bfd56  cmp     rcx, rdx
0x1800bfd59  jz      loc_1800BFC4E
0x1800bfd5f  test    byte ptr [rcx+1Ch], 1
0x1800bfd63  jz      loc_1800BFC4E
0x1800bfd69  mov     edx, 15h
0x1800bfd6e  jmp     loc_1800BFC3B
0x1800bfd73  mov     [rbp+var_10], 0
0x1800bfd7a  lea     rax, [rbp+var_10]
0x1800bfd7e  mov     [rsp+50h+var_30], rax
0x1800bfd83  mov     r9, [rbp+var_20]
0x1800bfd87  xor     r8d, r8d; pReturnValue
0x1800bfd8a  lea     edx, [r8+6Fh]; nProcNum
0x1800bfd8e  lea     rcx, pProxyInfo; pProxyInfo
0x1800bfd95  call    cs:NdrClientCall3
0x1800bfd9b  mov     rbx, rax
0x1800bfd9e  test    eax, eax
0x1800bfda0  jns     short loc_1800BFDCD
0x1800bfda2  lea     rdx, off_18019DE80
0x1800bfda9  mov     rcx, cs:off_18019DE80
0x1800bfdb0  cmp     rcx, rdx
0x1800bfdb3  jz      loc_1800BFC4E
0x1800bfdb9  test    byte ptr [rcx+1Ch], 1
0x1800bfdbd  jz      loc_1800BFC4E
0x1800bfdc3  mov     edx, 16h
0x1800bfdc8  jmp     loc_1800BFC3B
0x1800bfdcd  mov     ebx, [rbp+var_10]
0x1800bfdd0  test    ebx, ebx
0x1800bfdd2  jz      short loc_1800BFE05
0x1800bfdd4  or      ebx, 80010000h
0x1800bfdda  lea     rdx, off_18019DE80
0x1800bfde1  mov     rcx, cs:off_18019DE80
0x1800bfde8  cmp     rcx, rdx
0x1800bfdeb  jz      loc_1800BFC4E
0x1800bfdf1  test    byte ptr [rcx+1Ch], 1
0x1800bfdf5  jz      loc_1800BFC4E
0x1800bfdfb  mov     edx, 17h
0x1800bfe00  jmp     loc_1800BFC3B
0x1800bfe05  mov     rcx, [rbp+lpMem]; lpMem
0x1800bfe09  test    rcx, rcx
0x1800bfe0c  jz      short loc_1800BFE13
0x1800bfe0e  call    sub_18003BCC8
0x1800bfe13  xor     eax, eax
0x1800bfe15  mov     rcx, [rbp+var_8]
0x1800bfe19  xor     rcx, rsp; StackCookie
0x1800bfe1c  call    __security_check_cookie
0x1800bfe21  mov     rbx, [rsp+50h+arg_8]
0x1800bfe26  mov     rdi, [rsp+50h+arg_10]
0x1800bfe2b  add     rsp, 50h
0x1800bfe2f  pop     rbp
0x1800bfe30  retn
```
