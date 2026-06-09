# sub_18005EBEC

- ea: `0x18005ebec`
- end: `0x18005edbf`
- name: `sub_18005EBEC`
- size: `467`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18005dfa4`

## callees

- `0x1800095a0`
- `0x180032da0`
- `0x18005ebec`
- `0x18005f600`
- `0x1800684a0`

## import_xrefs

- `MpClient!MpManagerVersionQuery` at `0x18005ec9f`
- `MpClient!MpManagerVersionQuery` at `0x18005ec9f`
- `MpClient!MpManagerOpen` at `0x18005ec26`
- `MpClient!MpManagerOpen` at `0x18005ec26`
- `MpClient!MpHandleClose` at `0x18005ec6d`
- `MpClient!MpHandleClose` at `0x18005ed9d`
- `MpClient!MpHandleClose` at `0x18005ec6d`
- `MpClient!MpHandleClose` at `0x18005ed9d`
- `MpClient!MpFreeMemory` at `0x18005ecf7`
- `MpClient!MpFreeMemory` at `0x18005ed29`
- `MpClient!MpFreeMemory` at `0x18005ed58`
- `MpClient!MpFreeMemory` at `0x18005ecf7`
- `MpClient!MpFreeMemory` at `0x18005ed29`
- `MpClient!MpFreeMemory` at `0x18005ed58`

## pseudocode

```c
__int64 __fastcall sub_18005EBEC(_QWORD *a1, _QWORD *a2, _QWORD *a3)
{
  int v6; // ebx
  _QWORD *v7; // rcx
  USHORT v8; // dx
  __int64 v10; // rcx
  __int64 v11; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v12; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v13; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v14; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v15; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v16[40]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v17; // [rsp+70h] [rbp-90h]
  __int64 v18; // [rsp+80h] [rbp-80h]
  __int64 v19; // [rsp+90h] [rbp-70h]

  v11 = 0;
  v6 = MpManagerOpen(0, &v11);
  if ( v6 < 0 )
  {
    v7 = off_180096D60;
    if ( off_180096D60 != (_UNKNOWN *)&off_180096D60 && (*((_BYTE *)off_180096D60 + 28) & 1) != 0 )
    {
      v8 = 64;
LABEL_5:
      sub_180032DA0(v7[2], v8, (const GUID *)qword_180086050, v6);
      goto LABEL_6;
    }
    goto LABEL_6;
  }
  v15 = 0;
  sub_1800684A0(v16, 0, 184);
  v6 = MpManagerVersionQuery(v11, &v15);
  if ( v6 < 0 )
  {
    v7 = off_180096D60;
    if ( off_180096D60 != (_UNKNOWN *)&off_180096D60 && (*((_BYTE *)off_180096D60 + 28) & 1) != 0 )
    {
      v8 = 65;
      goto LABEL_5;
    }
LABEL_6:
    if ( v11 )
      MpHandleClose();
    return (unsigned int)v6;
  }
  v12 = 0;
  v6 = sub_18005F600(&v12, v17);
  if ( v6 < 0 )
  {
LABEL_14:
    if ( v12 )
      MpFreeMemory(v12);
    goto LABEL_6;
  }
  v13 = 0;
  v6 = sub_18005F600(&v13, v19);
  if ( v6 < 0 )
  {
LABEL_17:
    if ( v13 )
      MpFreeMemory(v13);
    goto LABEL_14;
  }
  v14 = 0;
  v6 = sub_18005F600(&v14, v18);
  if ( v6 < 0 )
  {
    if ( v14 )
      MpFreeMemory(v14);
    goto LABEL_17;
  }
  v10 = v11;
  *a1 = v12;
  *a2 = v13;
  *a3 = v14;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  if ( v10 )
    MpHandleClose();
  return 0;
}

```

## disassembly

```asm
0x18005ebec  push    rbp
0x18005ebee  push    rbx
0x18005ebef  push    rsi
0x18005ebf0  push    rdi
0x18005ebf1  push    r14
0x18005ebf3  lea     rbp, [rsp-10h]
0x18005ebf8  sub     rsp, 110h
0x18005ebff  mov     rax, cs:__security_cookie
0x18005ec06  xor     rax, rsp
0x18005ec09  mov     [rbp+30h+var_30], rax
0x18005ec0d  mov     rsi, rdx
0x18005ec10  mov     [rsp+130h+var_110], 0
0x18005ec19  mov     rdi, rcx
0x18005ec1c  lea     rdx, [rsp+130h+var_110]
0x18005ec21  xor     ecx, ecx
0x18005ec23  mov     r14, r8
0x18005ec26  call    cs:MpManagerOpen
0x18005ec2c  mov     ebx, eax
0x18005ec2e  test    eax, eax
0x18005ec30  jns     short loc_18005EC7A
0x18005ec32  mov     rcx, cs:off_180096D60
0x18005ec39  lea     rdx, off_180096D60
0x18005ec40  cmp     rcx, rdx
0x18005ec43  jz      short loc_18005EC63
0x18005ec45  test    byte ptr [rcx+1Ch], 1
0x18005ec49  jz      short loc_18005EC63
0x18005ec4b  mov     edx, 40h ; '@'
0x18005ec50  mov     rcx, [rcx+10h]
0x18005ec54  lea     r8, qword_180086050
0x18005ec5b  mov     r9d, ebx
0x18005ec5e  call    sub_180032DA0
0x18005ec63  mov     rcx, [rsp+130h+var_110]
0x18005ec68  test    rcx, rcx
0x18005ec6b  jz      short loc_18005EC73
0x18005ec6d  call    cs:MpHandleClose
0x18005ec73  mov     eax, ebx
0x18005ec75  jmp     loc_18005EDA5
0x18005ec7a  xor     edx, edx
0x18005ec7c  mov     [rsp+130h+var_F0], 0
0x18005ec85  mov     r8d, 0B8h
0x18005ec8b  lea     rcx, [rsp+130h+var_E8]
0x18005ec90  call    sub_1800684A0
0x18005ec95  mov     rcx, [rsp+130h+var_110]
0x18005ec9a  lea     rdx, [rsp+130h+var_F0]
0x18005ec9f  call    cs:MpManagerVersionQuery
0x18005eca5  mov     ebx, eax
0x18005eca7  test    eax, eax
0x18005eca9  jns     short loc_18005ECCB
0x18005ecab  mov     rcx, cs:off_180096D60
0x18005ecb2  lea     rdx, off_180096D60
0x18005ecb9  cmp     rcx, rdx
0x18005ecbc  jz      short loc_18005EC63
0x18005ecbe  test    byte ptr [rcx+1Ch], 1
0x18005ecc2  jz      short loc_18005EC63
0x18005ecc4  mov     edx, 41h ; 'A'
0x18005ecc9  jmp     short loc_18005EC50
0x18005eccb  mov     rdx, [rsp+130h+var_C0]
0x18005ecd0  lea     rcx, [rsp+130h+var_108]
0x18005ecd5  mov     [rsp+130h+var_108], 0
0x18005ecde  call    sub_18005F600
0x18005ece3  mov     ebx, eax
0x18005ece5  test    eax, eax
0x18005ece7  jns     short loc_18005ED02
0x18005ece9  mov     rcx, [rsp+130h+var_108]
0x18005ecee  test    rcx, rcx
0x18005ecf1  jz      loc_18005EC63
0x18005ecf7  call    cs:MpFreeMemory
0x18005ecfd  jmp     loc_18005EC63
0x18005ed02  mov     rdx, [rbp+30h+var_A0]
0x18005ed06  lea     rcx, [rsp+130h+var_100]
0x18005ed0b  mov     [rsp+130h+var_100], 0
0x18005ed14  call    sub_18005F600
0x18005ed19  mov     ebx, eax
0x18005ed1b  test    eax, eax
0x18005ed1d  jns     short loc_18005ED31
0x18005ed1f  mov     rcx, [rsp+130h+var_100]
0x18005ed24  test    rcx, rcx
0x18005ed27  jz      short loc_18005ECE9
0x18005ed29  call    cs:MpFreeMemory
0x18005ed2f  jmp     short loc_18005ECE9
0x18005ed31  mov     rdx, [rbp+30h+var_B0]
0x18005ed35  lea     rcx, [rsp+130h+var_F8]
0x18005ed3a  mov     [rsp+130h+var_F8], 0
0x18005ed43  call    sub_18005F600
0x18005ed48  mov     ebx, eax
0x18005ed4a  test    eax, eax
0x18005ed4c  jns     short loc_18005ED60
0x18005ed4e  mov     rcx, [rsp+130h+var_F8]
0x18005ed53  test    rcx, rcx
0x18005ed56  jz      short loc_18005ED1F
0x18005ed58  call    cs:MpFreeMemory
0x18005ed5e  jmp     short loc_18005ED1F
0x18005ed60  mov     rax, [rsp+130h+var_108]
0x18005ed65  mov     rcx, [rsp+130h+var_110]
0x18005ed6a  mov     [rdi], rax
0x18005ed6d  mov     rax, [rsp+130h+var_100]
0x18005ed72  mov     [rsi], rax
0x18005ed75  mov     rax, [rsp+130h+var_F8]
0x18005ed7a  mov     [r14], rax
0x18005ed7d  mov     [rsp+130h+var_108], 0
0x18005ed86  mov     [rsp+130h+var_100], 0
0x18005ed8f  mov     [rsp+130h+var_F8], 0
0x18005ed98  test    rcx, rcx
0x18005ed9b  jz      short loc_18005EDA3
0x18005ed9d  call    cs:MpHandleClose
0x18005eda3  xor     eax, eax
0x18005eda5  mov     rcx, [rbp+30h+var_30]
0x18005eda9  xor     rcx, rsp; StackCookie
0x18005edac  call    __security_check_cookie
0x18005edb1  add     rsp, 110h
0x18005edb8  pop     r14
0x18005edba  pop     rdi
0x18005edbb  pop     rsi
0x18005edbc  pop     rbx
0x18005edbd  pop     rbp
0x18005edbe  retn
```
