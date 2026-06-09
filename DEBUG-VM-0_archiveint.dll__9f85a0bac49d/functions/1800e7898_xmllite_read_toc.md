# xmllite_read_toc

- ea: `0x1800e7898`
- end: `0x1800e7b2a`
- name: `xmllite_read_toc`
- size: `658`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x1800e4970`

## callees

- `0x180006c00`
- `0x1800e5a34`
- `0x1800e6158`
- `0x1800e6d78`
- `0x1800e7738`
- `0x1800e7800`
- `0x1800e7898`
- `0x1800e7b30`
- `0x18011a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800e78d4`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800e78d4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800e79be`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800e7a09`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800e7a84`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800e7a8e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800e7a97`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800e7acb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800e7b0a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800e79be`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800e7a09`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800e7a84`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800e7a8e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800e7a97`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800e7acb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800e7b0a`
- `XmlLite!CreateXmlReader` at `0x1800e7910`
- `XmlLite!CreateXmlReader` at `0x1800e7910`

## string_xrefs

- `0x1800e7935`: `Failed to prepare XML stream`
- `0x1800e7adb`: `Failed to read XML stream`

## pseudocode

```c
__int64 __fastcall xmllite_read_toc(__int64 a1)
{
  _QWORD *v2; // r14
  const char *v3; // r8
  unsigned int v4; // edi
  __int64 v5; // rax
  void *v6; // rbx
  int v7; // r13d
  void *v8; // r12
  void **v9; // r15
  void **v10; // rbx
  void *v12[2]; // [rsp+20h] [rbp-30h] BYREF
  void *Block[2]; // [rsp+30h] [rbp-20h] BYREF
  __int64 v14; // [rsp+40h] [rbp-10h]
  int v15; // [rsp+98h] [rbp+48h] BYREF
  void *ppvObject; // [rsp+A0h] [rbp+50h] BYREF

  v14 = 0;
  *(_OWORD *)Block = 0;
  v15 = 0;
  ppvObject = 0;
  *(_OWORD *)v12 = 0;
  v2 = calloc(1u, 0x10u);
  if ( !v2 )
  {
    v2 = 0;
    archive_set_error(a1, 12, "Out of memory");
LABEL_28:
    v4 = -30;
    goto LABEL_29;
  }
  v2[1] = a1;
  *v2 = off_18011DCF8;
  if ( CreateXmlReader(&riid, &ppvObject, 0) < 0 )
    goto LABEL_28;
  if ( (*(int (__fastcall **)(void *, _QWORD *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, v2) < 0 )
  {
    v3 = "Failed to prepare XML stream";
LABEL_27:
    archive_set_error(a1, 0xFFFFFFFFLL, v3);
    goto LABEL_28;
  }
  v4 = 0;
  while ( !(*(unsigned int (__fastcall **)(void *))(*(_QWORD *)ppvObject + 200LL))(ppvObject) )
  {
    if ( (*(int (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v15) < 0 )
    {
      v3 = "Failed to read XML stream";
      goto LABEL_27;
    }
    switch ( v15 )
    {
      case 1:
        v7 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 160LL))(ppvObject);
        v8 = (void *)xmllite_call_return_mbs(a1, ppvObject, *(_QWORD *)(*(_QWORD *)ppvObject + 112LL));
        if ( !v8 )
          goto LABEL_28;
        v4 = xmllite_xmlattr_setup(a1, v12, ppvObject);
        if ( !v4 )
          v4 = xml_start(a1, v8, v12);
        v9 = (void **)v12[0];
        if ( v12[0] )
        {
          do
          {
            v10 = (void **)*v9;
            free(v9[1]);
            free(v9[2]);
            free(v9);
            v9 = v10;
          }
          while ( v10 );
        }
        v12[0] = 0;
        v12[1] = v12;
        if ( !v4 && v7 )
          xml_end(a1, (__int64)v8);
        free(v8);
        if ( v4 )
          goto LABEL_29;
        break;
      case 3:
        v4 = xmllite_call_return_as(a1, Block, ppvObject, *(_QWORD *)(*(_QWORD *)ppvObject + 128LL));
        if ( v4 )
          goto LABEL_29;
        xml_data(a1, Block[0], SLODWORD(Block[1]));
        Block[1] = 0;
        v14 = 0;
        free(Block[0]);
        Block[0] = 0;
        break;
      case 15:
        v5 = xmllite_call_return_mbs(a1, ppvObject, *(_QWORD *)(*(_QWORD *)ppvObject + 112LL));
        v6 = (void *)v5;
        if ( !v5 )
          goto LABEL_28;
        xml_end(a1, v5);
        free(v6);
        break;
    }
  }
LABEL_29:
  if ( ppvObject )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
  free(v2);
  return v4;
}

```

## disassembly

```asm
0x1800e7898  mov     [rsp-38h+arg_0], rbx
0x1800e789d  push    rbp
0x1800e789e  push    rsi
0x1800e789f  push    rdi
0x1800e78a0  push    r12
0x1800e78a2  push    r13
0x1800e78a4  push    r14
0x1800e78a6  push    r15
0x1800e78a8  mov     rbp, rsp
0x1800e78ab  sub     rsp, 50h
0x1800e78af  xor     eax, eax
0x1800e78b1  xorps   xmm0, xmm0
0x1800e78b4  mov     rsi, rcx
0x1800e78b7  mov     [rbp+var_10], rax
0x1800e78bb  xor     r15d, r15d
0x1800e78be  movups  xmmword ptr [rbp+Block], xmm0
0x1800e78c2  lea     edx, [rax+10h]; Size
0x1800e78c5  mov     [rbp+arg_8], r15d
0x1800e78c9  lea     ecx, [rax+1]; Count
0x1800e78cc  mov     [rbp+ppvObject], r15
0x1800e78d0  movups  xmmword ptr [rbp+var_30], xmm0
0x1800e78d4  call    cs:__imp_calloc
0x1800e78da  mov     r14, rax
0x1800e78dd  test    rax, rax
0x1800e78e0  jnz     short loc_1800E78F4
0x1800e78e2  mov     r14d, r15d
0x1800e78e5  lea     r8, aOutOfMemory_0; "Out of memory"
0x1800e78ec  lea     edx, [rax+0Ch]
0x1800e78ef  jmp     loc_1800E7AE5
0x1800e78f4  lea     rax, off_18011DCF8
0x1800e78fb  mov     [r14+8], rsi
0x1800e78ff  xor     r8d, r8d; pMalloc
0x1800e7902  mov     [r14], rax
0x1800e7905  lea     rdx, [rbp+ppvObject]; ppvObject
0x1800e7909  lea     rcx, riid; riid
0x1800e7910  call    cs:__imp_CreateXmlReader
0x1800e7916  test    eax, eax
0x1800e7918  js      loc_1800E7AED
0x1800e791e  mov     rcx, [rbp+ppvObject]
0x1800e7922  mov     rdx, r14
0x1800e7925  mov     rax, [rcx]
0x1800e7928  mov     rax, [rax+18h]
0x1800e792c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7931  test    eax, eax
0x1800e7933  jns     short loc_1800E7941
0x1800e7935  lea     r8, aFailedToPrepar; "Failed to prepare XML stream"
0x1800e793c  jmp     loc_1800E7AE2
0x1800e7941  mov     edi, r15d
0x1800e7944  mov     rcx, [rbp+ppvObject]
0x1800e7948  mov     rax, [rcx]
0x1800e794b  mov     rax, [rax+0C8h]
0x1800e7952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7957  test    eax, eax
0x1800e7959  jnz     loc_1800E7AF2
0x1800e795f  mov     rcx, [rbp+ppvObject]
0x1800e7963  lea     rdx, [rbp+arg_8]
0x1800e7967  mov     rax, [rcx]
0x1800e796a  mov     rax, [rax+30h]
0x1800e796e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7973  test    eax, eax
0x1800e7975  js      loc_1800E7ADB
0x1800e797b  mov     ecx, [rbp+arg_8]
0x1800e797e  sub     ecx, 1
0x1800e7981  jz      loc_1800E7A18
0x1800e7987  sub     ecx, 2
0x1800e798a  jz      short loc_1800E79C9
0x1800e798c  cmp     ecx, 0Ch
0x1800e798f  jnz     short loc_1800E7944
0x1800e7991  mov     rdx, [rbp+ppvObject]
0x1800e7995  mov     rcx, rsi
0x1800e7998  mov     r8, [rdx]
0x1800e799b  mov     r8, [r8+70h]
0x1800e799f  call    xmllite_call_return_mbs
0x1800e79a4  mov     rbx, rax
0x1800e79a7  test    rax, rax
0x1800e79aa  jz      loc_1800E7AED
0x1800e79b0  mov     rdx, rax
0x1800e79b3  mov     rcx, rsi
0x1800e79b6  call    xml_end
0x1800e79bb  mov     rcx, rbx; Block
0x1800e79be  call    cs:__imp_free
0x1800e79c4  jmp     loc_1800E7944
0x1800e79c9  mov     r8, [rbp+ppvObject]
0x1800e79cd  lea     rdx, [rbp+Block]
0x1800e79d1  mov     rcx, rsi
0x1800e79d4  mov     r9, [r8]
0x1800e79d7  mov     r9, [r9+80h]
0x1800e79de  call    xmllite_call_return_as
0x1800e79e3  mov     edi, eax
0x1800e79e5  test    eax, eax
0x1800e79e7  jnz     loc_1800E7AF2
0x1800e79ed  movsxd  r8, dword ptr [rbp+Block+8]
0x1800e79f1  mov     rcx, rsi
0x1800e79f4  mov     rdx, [rbp+Block]
0x1800e79f8  call    xml_data
0x1800e79fd  mov     rcx, [rbp+Block]; Block
0x1800e7a01  mov     [rbp+Block+8], r15
0x1800e7a05  mov     [rbp+var_10], r15
0x1800e7a09  call    cs:__imp_free
0x1800e7a0f  mov     [rbp+Block], r15
0x1800e7a13  jmp     loc_1800E7944
0x1800e7a18  mov     rcx, [rbp+ppvObject]
0x1800e7a1c  mov     rax, [rcx]
0x1800e7a1f  mov     rax, [rax+0A0h]
0x1800e7a26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7a2b  mov     rdx, [rbp+ppvObject]
0x1800e7a2f  mov     rcx, rsi
0x1800e7a32  mov     r13d, eax
0x1800e7a35  mov     r8, [rdx]
0x1800e7a38  mov     r8, [r8+70h]
0x1800e7a3c  call    xmllite_call_return_mbs
0x1800e7a41  mov     r12, rax
0x1800e7a44  test    rax, rax
0x1800e7a47  jz      loc_1800E7AED
0x1800e7a4d  mov     r8, [rbp+ppvObject]
0x1800e7a51  lea     rdx, [rbp+var_30]
0x1800e7a55  mov     rcx, rsi
0x1800e7a58  call    xmllite_xmlattr_setup
0x1800e7a5d  mov     edi, eax
0x1800e7a5f  test    eax, eax
0x1800e7a61  jnz     short loc_1800E7A74
0x1800e7a63  lea     r8, [rbp+var_30]
0x1800e7a67  mov     rdx, r12
0x1800e7a6a  mov     rcx, rsi
0x1800e7a6d  call    xml_start
0x1800e7a72  mov     edi, eax
0x1800e7a74  mov     r15, [rbp+var_30]
0x1800e7a78  test    r15, r15
0x1800e7a7b  jz      short loc_1800E7AA5
0x1800e7a7d  mov     rcx, [r15+8]; Block
0x1800e7a81  mov     rbx, [r15]
0x1800e7a84  call    cs:__imp_free
0x1800e7a8a  mov     rcx, [r15+10h]; Block
0x1800e7a8e  call    cs:__imp_free
0x1800e7a94  mov     rcx, r15; Block
0x1800e7a97  call    cs:__imp_free
0x1800e7a9d  mov     r15, rbx
0x1800e7aa0  test    rbx, rbx
0x1800e7aa3  jnz     short loc_1800E7A7D
0x1800e7aa5  xor     r15d, r15d
0x1800e7aa8  lea     rax, [rbp+var_30]
0x1800e7aac  mov     [rbp+var_30], r15
0x1800e7ab0  mov     [rbp+var_30+8], rax
0x1800e7ab4  test    edi, edi
0x1800e7ab6  jnz     short loc_1800E7AC8
0x1800e7ab8  test    r13d, r13d
0x1800e7abb  jz      short loc_1800E7AC8
0x1800e7abd  mov     rdx, r12
0x1800e7ac0  mov     rcx, rsi
0x1800e7ac3  call    xml_end
0x1800e7ac8  mov     rcx, r12; Block
0x1800e7acb  call    cs:__imp_free
0x1800e7ad1  test    edi, edi
0x1800e7ad3  jz      loc_1800E7944
0x1800e7ad9  jmp     short loc_1800E7AF2
0x1800e7adb  lea     r8, aFailedToReadXm_0; "Failed to read XML stream"
0x1800e7ae2  or      edx, 0FFFFFFFFh
0x1800e7ae5  mov     rcx, rsi
0x1800e7ae8  call    archive_set_error
0x1800e7aed  mov     edi, 0FFFFFFE2h
0x1800e7af2  mov     rcx, [rbp+ppvObject]
0x1800e7af6  test    rcx, rcx
0x1800e7af9  jz      short loc_1800E7B07
0x1800e7afb  mov     rax, [rcx]
0x1800e7afe  mov     rax, [rax+10h]
0x1800e7b02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7b07  mov     rcx, r14; Block
0x1800e7b0a  call    cs:__imp_free
0x1800e7b10  mov     rbx, [rsp+50h+arg_0]
0x1800e7b18  mov     eax, edi
0x1800e7b1a  add     rsp, 50h
0x1800e7b1e  pop     r15
0x1800e7b20  pop     r14
0x1800e7b22  pop     r13
0x1800e7b24  pop     r12
0x1800e7b26  pop     rdi
0x1800e7b27  pop     rsi
0x1800e7b28  pop     rbp
0x1800e7b29  retn
```
