# CMetadataRDFReaderWriter::HrCommitDirtyItemsToDOM(int)

- ea: `0x180017d40`
- end: `0x18001808d`
- name: `?HrCommitDirtyItemsToDOM@CMetadataRDFReaderWriter@@MEAAJH@Z`
- size: `845`
- prototype: `__int64 __fastcall(CMetadataRDFReaderWriter *__hidden this, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022ac0`

## callees

- `0x180015c60`
- `0x1800171c4`
- `0x180017d40`
- `0x180020c80`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::HrCommitDirtyItemsToDOM(CMetadataRDFReaderWriter *this, int a2)
{
  int v2; // ebx
  __int64 v3; // rsi
  __int64 *v5; // r13
  __int64 v6; // r14
  int v7; // eax
  __int64 v8; // rdi
  int v9; // eax
  int v10; // eax
  __int64 v11; // rcx
  void (__fastcall ***v12)(_QWORD, __int64); // rcx
  int v13; // ecx
  __int64 v15; // [rsp+20h] [rbp-18h] BYREF
  __int64 v16; // [rsp+28h] [rbp-10h] BYREF
  __int64 v17; // [rsp+80h] [rbp+48h] BYREF
  int v18; // [rsp+88h] [rbp+50h]
  __int64 v19; // [rsp+90h] [rbp+58h] BYREF
  __int64 v20; // [rsp+98h] [rbp+60h] BYREF

  v18 = a2;
  v2 = 0;
  v3 = 0;
  v17 = 0;
  v20 = 0;
  v16 = 0;
  v19 = 0;
  v15 = 0;
  if ( !*((_DWORD *)this + 58) )
    return (unsigned int)v2;
  v5 = (__int64 *)((char *)this + 208);
  while ( 1 )
  {
    v6 = *(_QWORD *)(*v5 + 8 * v3);
    v7 = *(_DWORD *)(v6 + 8);
    v8 = *(_QWORD *)(v6 + 16);
    if ( (v7 & 2) != 0 )
      break;
    if ( v8 && ((v7 & 4) == 0 || (v7 & 8) == 0) && (v7 & 1) == 0 )
      goto LABEL_51;
    v9 = CMetadataRDFReaderWriter::ApplyItemToDOM(this, *(struct RDFItem **)(*v5 + 8 * v3), a2);
    v2 = v9;
    if ( v9 < 0 )
    {
      if ( !g_doStackCaptures )
        goto LABEL_57;
      goto LABEL_55;
    }
LABEL_50:
    a2 = v18;
LABEL_51:
    v3 = (unsigned int)(v3 + 1);
    if ( (unsigned int)v3 >= *((_DWORD *)this + 58) )
      goto LABEL_57;
  }
  if ( !v8 )
  {
LABEL_37:
    v12 = *(void (__fastcall ****)(_QWORD, __int64))(*v5 + 8 * v3);
    if ( v12 )
      (**v12)(v12, 1);
    v9 = CMILObjectArray<RDFItem *>::RemoveAt(v5, v3);
    v2 = v9;
    if ( v9 < 0 )
    {
      if ( g_doStackCaptures == (_DWORD)v8 )
        goto LABEL_57;
      goto LABEL_55;
    }
    LODWORD(v3) = v3 - 1;
    goto LABEL_50;
  }
  if ( (v7 & 0x10) == 0 )
  {
    v2 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)v8 + 88LL))(*(_QWORD *)(v6 + 16), &v17);
    v10 = g_doStackCaptures;
    if ( v2 < 0 )
    {
      if ( !g_doStackCaptures )
        goto LABEL_57;
      goto LABEL_54;
    }
    if ( v2 )
      goto LABEL_53;
    v2 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v17 + 160LL))(v17, v8, &v20);
    LODWORD(v8) = 0;
    v10 = g_doStackCaptures;
    if ( v2 < 0 )
    {
      if ( !g_doStackCaptures )
        goto LABEL_57;
      goto LABEL_54;
    }
    if ( v2 )
    {
LABEL_53:
      v2 = -2147467259;
      if ( !v10 )
        goto LABEL_57;
      goto LABEL_54;
    }
    if ( v17 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      v17 = 0;
    }
    if ( v20 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      v20 = 0;
    }
    goto LABEL_34;
  }
  v9 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(v6 + 24))(
         *(_QWORD *)(v6 + 24),
         &IID_IXMLDOMElement,
         &v16);
  v2 = v9;
  if ( v9 < 0 )
  {
    if ( !g_doStackCaptures )
      goto LABEL_57;
    goto LABEL_55;
  }
  v9 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v8)(v8, &IID_IXMLDOMAttribute, &v19);
  LODWORD(v8) = 0;
  v2 = v9;
  if ( v9 >= 0 )
  {
    v2 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v16 + 392LL))(v16, v19, &v15);
    v10 = g_doStackCaptures;
    if ( v2 < 0 )
    {
      if ( !g_doStackCaptures )
        goto LABEL_57;
LABEL_54:
      v13 = v2;
      goto LABEL_56;
    }
    if ( v2 )
      goto LABEL_53;
    if ( v16 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      v16 = 0;
    }
    if ( v19 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      v19 = 0;
    }
    if ( v15 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      v15 = 0;
    }
LABEL_34:
    v11 = *(_QWORD *)(v6 + 16);
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    *(_QWORD *)(v6 + 16) = 0;
    goto LABEL_37;
  }
  if ( !g_doStackCaptures )
    goto LABEL_57;
LABEL_55:
  v13 = v9;
LABEL_56:
  DoStackCapture(v13);
LABEL_57:
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  if ( v20 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v20 = 0;
  }
  if ( v19 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    v19 = 0;
  }
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    v15 = 0;
  }
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180017d40  mov     [rsp-40h+arg_8], edx
0x180017d44  push    rbp
0x180017d45  push    rbx
0x180017d46  push    rsi
0x180017d47  push    rdi
0x180017d48  push    r12
0x180017d4a  push    r13
0x180017d4c  push    r14
0x180017d4e  push    r15
0x180017d50  mov     rbp, rsp
0x180017d53  sub     rsp, 38h
0x180017d57  xor     ebx, ebx
0x180017d59  xor     esi, esi
0x180017d5b  mov     r15, rcx
0x180017d5e  mov     [rbp+arg_0], rbx
0x180017d62  mov     [rbp+arg_18], rbx
0x180017d66  mov     [rbp+var_10], rbx
0x180017d6a  mov     [rbp+arg_10], rbx
0x180017d6e  mov     [rbp+var_18], rbx
0x180017d72  cmp     [rcx+0E8h], ebx
0x180017d78  jbe     loc_18001807A
0x180017d7e  lea     r13, [rcx+0D0h]
0x180017d85  mov     rax, [r13+0]
0x180017d89  mov     r14, [rax+rsi*8]
0x180017d8d  mov     eax, [r14+8]
0x180017d91  mov     rdi, [r14+10h]
0x180017d95  test    al, 2
0x180017d97  jz      loc_180017FA4
0x180017d9d  test    rdi, rdi
0x180017da0  jz      loc_180017F67
0x180017da6  test    al, 10h
0x180017da8  jz      loc_180017EA9
0x180017dae  mov     rcx, [r14+18h]
0x180017db2  lea     r8, [rbp+var_10]
0x180017db6  lea     rdx, IID_IXMLDOMElement
0x180017dbd  mov     rax, [rcx]
0x180017dc0  mov     rax, [rax]
0x180017dc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017dc8  mov     ebx, eax
0x180017dca  test    eax, eax
0x180017dcc  jns     short loc_180017DE3
0x180017dce  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180017dd5  jnz     loc_180017FF8
0x180017ddb  test    eax, eax
0x180017ddd  js      loc_180017FFF
0x180017de3  mov     rax, [rdi]
0x180017de6  lea     r8, [rbp+arg_10]
0x180017dea  lea     rdx, IID_IXMLDOMAttribute
0x180017df1  mov     rcx, rdi
0x180017df4  mov     rax, [rax]
0x180017df7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017dfc  xor     edi, edi
0x180017dfe  mov     ebx, eax
0x180017e00  test    eax, eax
0x180017e02  jns     short loc_180017E18
0x180017e04  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x180017e0a  jnz     loc_180017FF8
0x180017e10  test    eax, eax
0x180017e12  js      loc_180017FFF
0x180017e18  mov     rcx, [rbp+var_10]
0x180017e1c  lea     r8, [rbp+var_18]
0x180017e20  mov     rdx, [rbp+arg_10]
0x180017e24  mov     rax, [rcx]
0x180017e27  mov     rax, [rax+188h]
0x180017e2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e33  mov     ebx, eax
0x180017e35  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180017e3b  test    ebx, ebx
0x180017e3d  jns     short loc_180017E4F
0x180017e3f  test    eax, eax
0x180017e41  jnz     loc_180017FF4
0x180017e47  test    ebx, ebx
0x180017e49  js      loc_180017FFF
0x180017e4f  jnz     loc_180017FEB
0x180017e55  mov     rcx, [rbp+var_10]
0x180017e59  test    rcx, rcx
0x180017e5c  jz      short loc_180017E6E
0x180017e5e  mov     rax, [rcx]
0x180017e61  mov     rax, [rax+10h]
0x180017e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e6a  mov     [rbp+var_10], rdi
0x180017e6e  mov     rcx, [rbp+arg_10]
0x180017e72  test    rcx, rcx
0x180017e75  jz      short loc_180017E87
0x180017e77  mov     rax, [rcx]
0x180017e7a  mov     rax, [rax+10h]
0x180017e7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e83  mov     [rbp+arg_10], rdi
0x180017e87  mov     rcx, [rbp+var_18]
0x180017e8b  test    rcx, rcx
0x180017e8e  jz      loc_180017F4E
0x180017e94  mov     rax, [rcx]
0x180017e97  mov     rax, [rax+10h]
0x180017e9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ea0  mov     [rbp+var_18], rdi
0x180017ea4  jmp     loc_180017F4E
0x180017ea9  mov     rax, [rdi]
0x180017eac  lea     rdx, [rbp+arg_0]
0x180017eb0  mov     rcx, rdi
0x180017eb3  mov     rax, [rax+58h]
0x180017eb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ebc  mov     ebx, eax
0x180017ebe  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180017ec4  test    ebx, ebx
0x180017ec6  jns     short loc_180017ED8
0x180017ec8  test    eax, eax
0x180017eca  jnz     loc_180017FF4
0x180017ed0  test    ebx, ebx
0x180017ed2  js      loc_180017FFF
0x180017ed8  jnz     loc_180017FEB
0x180017ede  mov     rcx, [rbp+arg_0]
0x180017ee2  lea     r8, [rbp+arg_18]
0x180017ee6  mov     rdx, rdi
0x180017ee9  mov     rax, [rcx]
0x180017eec  mov     rax, [rax+0A0h]
0x180017ef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ef8  mov     ebx, eax
0x180017efa  xor     edi, edi
0x180017efc  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180017f02  test    ebx, ebx
0x180017f04  jns     short loc_180017F16
0x180017f06  test    eax, eax
0x180017f08  jnz     loc_180017FF4
0x180017f0e  test    ebx, ebx
0x180017f10  js      loc_180017FFF
0x180017f16  jnz     loc_180017FEB
0x180017f1c  mov     rcx, [rbp+arg_0]
0x180017f20  test    rcx, rcx
0x180017f23  jz      short loc_180017F35
0x180017f25  mov     rax, [rcx]
0x180017f28  mov     rax, [rax+10h]
0x180017f2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f31  mov     [rbp+arg_0], rdi
0x180017f35  mov     rcx, [rbp+arg_18]
0x180017f39  test    rcx, rcx
0x180017f3c  jz      short loc_180017F4E
0x180017f3e  mov     rax, [rcx]
0x180017f41  mov     rax, [rax+10h]
0x180017f45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f4a  mov     [rbp+arg_18], rdi
0x180017f4e  mov     rcx, [r14+10h]
0x180017f52  test    rcx, rcx
0x180017f55  jz      short loc_180017F63
0x180017f57  mov     rax, [rcx]
0x180017f5a  mov     rax, [rax+10h]
0x180017f5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f63  mov     [r14+10h], rdi
0x180017f67  mov     rax, [r13+0]
0x180017f6b  mov     rcx, [rax+rsi*8]
0x180017f6f  test    rcx, rcx
0x180017f72  jz      short loc_180017F84
0x180017f74  mov     rax, [rcx]
0x180017f77  mov     edx, 1
0x180017f7c  mov     rax, [rax]
0x180017f7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f84  mov     edx, esi
0x180017f86  mov     rcx, r13
0x180017f89  call    ?RemoveAt@?$CMILObjectArray@PEAVRDFItem@@@@QEAAJI@Z; CMILObjectArray<RDFItem *>::RemoveAt(uint)
0x180017f8e  mov     ebx, eax
0x180017f90  test    eax, eax
0x180017f92  jns     short loc_180017FA0
0x180017f94  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x180017f9a  jnz     short loc_180017FF8
0x180017f9c  test    eax, eax
0x180017f9e  js      short loc_180017FFF
0x180017fa0  dec     esi
0x180017fa2  jmp     short loc_180017FD7
0x180017fa4  test    rdi, rdi
0x180017fa7  jz      short loc_180017FB5
0x180017fa9  test    al, 4
0x180017fab  jz      short loc_180017FB1
0x180017fad  test    al, 8
0x180017faf  jnz     short loc_180017FB5
0x180017fb1  test    al, 1
0x180017fb3  jz      short loc_180017FDA
0x180017fb5  mov     r8d, edx; int
0x180017fb8  mov     rcx, r15; this
0x180017fbb  mov     rdx, r14; struct RDFItem *
0x180017fbe  call    ?ApplyItemToDOM@CMetadataRDFReaderWriter@@IEAAJPEAVRDFItem@@H@Z; CMetadataRDFReaderWriter::ApplyItemToDOM(RDFItem *,int)
0x180017fc3  xor     edi, edi
0x180017fc5  mov     ebx, eax
0x180017fc7  test    eax, eax
0x180017fc9  jns     short loc_180017FD7
0x180017fcb  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x180017fd1  jnz     short loc_180017FF8
0x180017fd3  test    eax, eax
0x180017fd5  js      short loc_180017FFF
0x180017fd7  mov     edx, [rbp+arg_8]
0x180017fda  inc     esi
0x180017fdc  cmp     esi, [r15+0E8h]
0x180017fe3  jb      loc_180017D85
0x180017fe9  jmp     short loc_180017FFF
0x180017feb  mov     ebx, 80004005h
0x180017ff0  test    eax, eax
0x180017ff2  jz      short loc_180017FFF
0x180017ff4  mov     ecx, ebx
0x180017ff6  jmp     short loc_180017FFA
0x180017ff8  mov     ecx, eax; int
0x180017ffa  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180017fff  mov     rcx, [rbp+arg_0]
0x180018003  xor     edi, edi
0x180018005  test    rcx, rcx
0x180018008  jz      short loc_18001801A
0x18001800a  mov     rax, [rcx]
0x18001800d  mov     rax, [rax+10h]
0x180018011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018016  mov     [rbp+arg_0], rdi
0x18001801a  mov     rcx, [rbp+arg_18]
0x18001801e  test    rcx, rcx
0x180018021  jz      short loc_180018033
0x180018023  mov     rax, [rcx]
0x180018026  mov     rax, [rax+10h]
0x18001802a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001802f  mov     [rbp+arg_18], rdi
0x180018033  mov     rcx, [rbp+arg_10]
0x180018037  test    rcx, rcx
0x18001803a  jz      short loc_18001804C
0x18001803c  mov     rax, [rcx]
0x18001803f  mov     rax, [rax+10h]
0x180018043  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018048  mov     [rbp+arg_10], rdi
0x18001804c  mov     rcx, [rbp+var_18]
0x180018050  test    rcx, rcx
0x180018053  jz      short loc_180018065
0x180018055  mov     rax, [rcx]
0x180018058  mov     rax, [rax+10h]
0x18001805c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018061  mov     [rbp+var_18], rdi
0x180018065  mov     rcx, [rbp+var_10]
0x180018069  test    rcx, rcx
0x18001806c  jz      short loc_18001807A
0x18001806e  mov     rdx, [rcx]
0x180018071  mov     rax, [rdx+10h]
0x180018075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001807a  mov     eax, ebx
0x18001807c  add     rsp, 38h
0x180018080  pop     r15
0x180018082  pop     r14
0x180018084  pop     r13
0x180018086  pop     r12
0x180018088  pop     rdi
0x180018089  pop     rsi
0x18001808a  pop     rbx
0x18001808b  pop     rbp
0x18001808c  retn
```
