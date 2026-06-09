# SHGetPropertyStoreFromPropertyParsingName(ushort const *,_GUID const &,void * *)

- ea: `0x18003fc58`
- end: `0x18003ff02`
- name: `?SHGetPropertyStoreFromPropertyParsingName@@YAJPEBGAEBU_GUID@@PEAPEAX@Z`
- size: `682`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003faf8`

## callees

- `0x1800388e0`
- `0x18003f9f4`
- `0x18003fa20`
- `0x18003fc58`
- `0x1800401ac`
- `0x180053010`

## import_xrefs

- `msvcrt!wcstol` at `0x18003fd53`
- `msvcrt!wcstol` at `0x18003fd53`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003fe1f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003fe1f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003fe5d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003fe89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003feb3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003fe5d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003fe89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003feb3`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18003fc96`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18003fc96`

## pseudocode

```c
__int64 __fastcall SHGetPropertyStoreFromPropertyParsingName(unsigned __int16 *a1, const struct _GUID *a2, void **a3)
{
  int NextToken; // edi
  int v6; // ebx
  wchar_t *v7; // r14
  int v8; // r12d
  VARTYPE v9; // r15
  wchar_t *v10; // rbx
  unsigned __int16 v11; // ax
  int v12; // esi
  unsigned __int16 *v13; // rcx
  wchar_t *v14; // rax
  unsigned int v15; // ebx
  void *ppv; // [rsp+30h] [rbp-30h] BYREF
  wchar_t *EndPtr; // [rsp+38h] [rbp-28h] BYREF
  unsigned __int16 *v19; // [rsp+40h] [rbp-20h] BYREF
  struct tagPROPVARIANT pvar; // [rsp+48h] [rbp-18h] BYREF
  const struct _GUID *v21; // [rsp+A8h] [rbp+48h] BYREF
  wchar_t *String; // [rsp+B8h] [rbp+58h] BYREF

  v21 = a2;
  ppv = 0;
  Microsoft::WRL::ComPtr<IObjectWithRegistryKey>::InternalRelease(&ppv);
  NextToken = PSCreateMemoryPropertyStore(&GUID_71604b0f_97b0_4764_8577_2f13e98a1422, &ppv);
  if ( NextToken < 0 )
    goto LABEL_48;
  v6 = 0;
  v19 = a1;
  v7 = 0;
  LODWORD(v21) = 0;
  v8 = 0;
  v9 = 31;
  while ( 1 )
  {
    String = 0;
    NextToken = _GetNextToken(a1, v8, (enum PARSE_TOKEN_TYPE *)&v21, &String, (const unsigned __int16 **)&v19);
    if ( NextToken )
      break;
    switch ( v6 )
    {
      case 0:
        if ( !(_DWORD)v21 )
        {
          v7 = String;
          v6 = 1;
          String = 0;
          break;
        }
LABEL_39:
        NextToken = -2147024809;
        break;
      case 1:
        if ( (_DWORD)v21 == 1 )
        {
          v6 = 2;
          break;
        }
        if ( (_DWORD)v21 == 2 )
        {
          v6 = 4;
          v9 = 31;
          break;
        }
        goto LABEL_39;
      case 2:
        if ( (_DWORD)v21 )
          goto LABEL_39;
        EndPtr = 0;
        v10 = String;
        v11 = wcstol(String, &EndPtr, 16);
        v9 = v11;
        if ( EndPtr == v10 || !(unsigned int)IsVarTypeValid(v11) )
          NextToken = -2147024809;
        v6 = 3;
        break;
      case 3:
        if ( (_DWORD)v21 == 2 )
        {
          v6 = 4;
          break;
        }
        goto LABEL_39;
      case 4:
        v12 = (int)v21;
        if ( (_DWORD)v21 == 2 )
        {
          v8 = 1;
          break;
        }
        if ( (_DWORD)v21 && (_DWORD)v21 != 3 )
          goto LABEL_39;
        if ( v9 == 31 || v9 == 8 )
        {
          v14 = (wchar_t *)&String2;
          pvar.vt = 31;
          if ( String )
            v14 = String;
          pvar.hVal.QuadPart = (LONGLONG)v14;
          NextToken = (*(__int64 (__fastcall **)(void *, wchar_t *, struct tagPROPVARIANT *))(*(_QWORD *)ppv + 32LL))(
                        ppv,
                        v7,
                        &pvar);
        }
        else
        {
          v13 = (unsigned __int16 *)&String2;
          memset(&pvar, 0, sizeof(pvar));
          if ( String )
            v13 = String;
          NextToken = InitPropVariantFromStringEx(v13, v9, &pvar);
          if ( NextToken >= 0 )
          {
            NextToken = (*(__int64 (__fastcall **)(void *, wchar_t *, struct tagPROPVARIANT *))(*(_QWORD *)ppv + 32LL))(
                          ppv,
                          v7,
                          &pvar);
            PropVariantClear((PROPVARIANT *)&pvar);
          }
        }
        LocalFree(v7);
        v7 = 0;
        v6 = v12 == 0 ? 5 : 0;
        break;
      default:
        if ( v6 == 5 && (_DWORD)v21 == 3 )
        {
          v6 = 0;
          break;
        }
        goto LABEL_39;
    }
    LocalFree(String);
    if ( NextToken )
      goto LABEL_46;
    a1 = v19;
  }
  if ( NextToken == 1 && v6 && v6 != 5 )
    NextToken = -2147024809;
LABEL_46:
  LocalFree(v7);
  if ( NextToken >= 0 )
    NextToken = (**(__int64 (__fastcall ***)(void *, GUID *, void **))ppv)(
                  ppv,
                  &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
                  a3);
LABEL_48:
  v15 = 0;
  if ( NextToken < 0 )
    v15 = NextToken;
  Microsoft::WRL::ComPtr<IObjectWithRegistryKey>::InternalRelease(&ppv);
  return v15;
}

```

## disassembly

```asm
0x18003fc58  mov     [rsp-38h+arg_0], rbx
0x18003fc5d  mov     [rsp-38h+arg_8], rdx
0x18003fc62  push    rbp
0x18003fc63  push    rsi
0x18003fc64  push    rdi
0x18003fc65  push    r12
0x18003fc67  push    r13
0x18003fc69  push    r14
0x18003fc6b  push    r15
0x18003fc6d  mov     rbp, rsp
0x18003fc70  sub     rsp, 60h
0x18003fc74  mov     rsi, rcx
0x18003fc77  mov     [rbp+ppv], 0
0x18003fc7f  lea     rcx, [rbp+ppv]
0x18003fc83  mov     r13, r8
0x18003fc86  call    ?InternalRelease@?$ComPtr@UIObjectWithRegistryKey@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IObjectWithRegistryKey>::InternalRelease(void)
0x18003fc8b  lea     rdx, [rbp+ppv]; ppv
0x18003fc8f  lea     rcx, _GUID_71604b0f_97b0_4764_8577_2f13e98a1422; riid
0x18003fc96  call    cs:__imp_PSCreateMemoryPropertyStore
0x18003fc9c  mov     edi, eax
0x18003fc9e  test    eax, eax
0x18003fca0  js      loc_18003FED8
0x18003fca6  xor     ebx, ebx
0x18003fca8  mov     [rbp+var_20], rsi
0x18003fcac  xor     r14d, r14d
0x18003fcaf  mov     dword ptr [rbp+arg_8], ebx
0x18003fcb2  xor     r12d, r12d
0x18003fcb5  lea     r15d, [rbx+1Fh]
0x18003fcb9  lea     rax, [rbp+var_20]
0x18003fcbd  mov     [rbp+String], 0
0x18003fcc5  lea     r9, [rbp+String]; unsigned __int16 **
0x18003fcc9  mov     [rsp+60h+var_40], rax; unsigned __int16 **
0x18003fcce  lea     r8, [rbp+arg_8]; enum PARSE_TOKEN_TYPE *
0x18003fcd2  mov     edx, r12d; int
0x18003fcd5  mov     rcx, rsi; unsigned __int16 *
0x18003fcd8  call    ?_GetNextToken@@YAJPEBGHPEAW4PARSE_TOKEN_TYPE@@PEAPEAGPEAPEBG@Z; _GetNextToken(ushort const *,int,PARSE_TOKEN_TYPE *,ushort * *,ushort const * *)
0x18003fcdd  xor     edx, edx
0x18003fcdf  mov     edi, eax
0x18003fce1  test    eax, eax
0x18003fce3  jnz     loc_18003FE9C
0x18003fce9  test    ebx, ebx
0x18003fceb  jnz     short loc_18003FD06
0x18003fced  cmp     dword ptr [rbp+arg_8], edx
0x18003fcf0  jnz     loc_18003FE80
0x18003fcf6  mov     r14, [rbp+String]
0x18003fcfa  lea     ebx, [rax+1]
0x18003fcfd  mov     [rbp+String], rdx
0x18003fd01  jmp     loc_18003FE85
0x18003fd06  cmp     ebx, 1
0x18003fd09  jnz     short loc_18003FD32
0x18003fd0b  cmp     dword ptr [rbp+arg_8], ebx
0x18003fd0e  jnz     short loc_18003FD1A
0x18003fd10  mov     ebx, 2
0x18003fd15  jmp     loc_18003FE85
0x18003fd1a  cmp     dword ptr [rbp+arg_8], 2
0x18003fd1e  jnz     loc_18003FE80
0x18003fd24  mov     ebx, 4
0x18003fd29  lea     r15d, [rbx+1Bh]
0x18003fd2d  jmp     loc_18003FE85
0x18003fd32  cmp     ebx, 2
0x18003fd35  jnz     short loc_18003FD7E
0x18003fd37  cmp     dword ptr [rbp+arg_8], edx
0x18003fd3a  jnz     loc_18003FE80
0x18003fd40  lea     r8d, [rbx+0Eh]; Radix
0x18003fd44  mov     [rbp+EndPtr], rdx
0x18003fd48  mov     rbx, [rbp+String]
0x18003fd4c  lea     rdx, [rbp+EndPtr]; EndPtr
0x18003fd50  mov     rcx, rbx; String
0x18003fd53  call    cs:__imp_wcstol
0x18003fd59  movzx   r15d, ax
0x18003fd5d  cmp     [rbp+EndPtr], rbx
0x18003fd61  jz      short loc_18003FD6F
0x18003fd63  movzx   ecx, ax; unsigned __int16
0x18003fd66  call    ?IsVarTypeValid@@YAHG@Z; IsVarTypeValid(ushort)
0x18003fd6b  test    eax, eax
0x18003fd6d  jnz     short loc_18003FD74
0x18003fd6f  mov     edi, 80070057h
0x18003fd74  mov     ebx, 3
0x18003fd79  jmp     loc_18003FE85
0x18003fd7e  cmp     ebx, 3
0x18003fd81  jnz     short loc_18003FD97
0x18003fd83  cmp     dword ptr [rbp+arg_8], 2
0x18003fd87  jnz     loc_18003FE80
0x18003fd8d  mov     ebx, 4
0x18003fd92  jmp     loc_18003FE85
0x18003fd97  cmp     ebx, 4
0x18003fd9a  jnz     loc_18003FE71
0x18003fda0  mov     esi, dword ptr [rbp+arg_8]
0x18003fda3  cmp     esi, 2
0x18003fda6  jnz     short loc_18003FDB1
0x18003fda8  lea     r12d, [rbx-3]
0x18003fdac  jmp     loc_18003FE85
0x18003fdb1  test    esi, esi
0x18003fdb3  jz      short loc_18003FDBE
0x18003fdb5  cmp     esi, 3
0x18003fdb8  jnz     loc_18003FE80
0x18003fdbe  mov     ecx, 1Fh
0x18003fdc3  cmp     r15w, cx
0x18003fdc7  jz      short loc_18003FE27
0x18003fdc9  cmp     r15w, 8
0x18003fdce  jz      short loc_18003FE27
0x18003fdd0  mov     rbx, [rbp+String]
0x18003fdd4  lea     rcx, String2
0x18003fddb  xor     eax, eax
0x18003fddd  lea     r8, [rbp+pvar]
0x18003fde1  xorps   xmm0, xmm0
0x18003fde4  mov     [rbp+var_8], rax
0x18003fde8  test    rbx, rbx
0x18003fdeb  movzx   edx, r15w
0x18003fdef  movups  xmmword ptr [rbp+pvar], xmm0
0x18003fdf3  cmovnz  rcx, rbx; unsigned __int16 *
0x18003fdf7  call    InitPropVariantFromStringEx
0x18003fdfc  mov     edi, eax
0x18003fdfe  test    eax, eax
0x18003fe00  js      short loc_18003FE5A
0x18003fe02  mov     rcx, [rbp+ppv]
0x18003fe06  lea     r8, [rbp+pvar]
0x18003fe0a  mov     rdx, r14
0x18003fe0d  mov     rax, [rcx]
0x18003fe10  mov     rax, [rax+20h]
0x18003fe14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fe19  lea     rcx, [rbp+pvar]; pvar
0x18003fe1d  mov     edi, eax
0x18003fe1f  call    cs:__imp_PropVariantClear
0x18003fe25  jmp     short loc_18003FE5A
0x18003fe27  mov     rbx, [rbp+String]
0x18003fe2b  lea     rax, String2
0x18003fe32  mov     word ptr [rbp+pvar], cx
0x18003fe36  lea     r8, [rbp+pvar]
0x18003fe3a  mov     rcx, [rbp+ppv]
0x18003fe3e  test    rbx, rbx
0x18003fe41  mov     rdx, r14
0x18003fe44  cmovnz  rax, rbx
0x18003fe48  mov     [rbp+pvar+8], rax
0x18003fe4c  mov     rax, [rcx]
0x18003fe4f  mov     rax, [rax+20h]
0x18003fe53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fe58  mov     edi, eax
0x18003fe5a  mov     rcx, r14; hMem
0x18003fe5d  call    cs:__imp_LocalFree
0x18003fe63  xor     r14d, r14d
0x18003fe66  neg     esi
0x18003fe68  sbb     ebx, ebx
0x18003fe6a  not     ebx
0x18003fe6c  and     ebx, 5
0x18003fe6f  jmp     short loc_18003FE85
0x18003fe71  cmp     ebx, 5
0x18003fe74  jnz     short loc_18003FE80
0x18003fe76  cmp     dword ptr [rbp+arg_8], 3
0x18003fe7a  jnz     short loc_18003FE80
0x18003fe7c  mov     ebx, edx
0x18003fe7e  jmp     short loc_18003FE85
0x18003fe80  mov     edi, 80070057h
0x18003fe85  mov     rcx, [rbp+String]; hMem
0x18003fe89  call    cs:__imp_LocalFree
0x18003fe8f  test    edi, edi
0x18003fe91  jnz     short loc_18003FEB0
0x18003fe93  mov     rsi, [rbp+var_20]
0x18003fe97  jmp     loc_18003FCB9
0x18003fe9c  cmp     edi, 1
0x18003fe9f  jnz     short loc_18003FEB0
0x18003fea1  test    ebx, ebx
0x18003fea3  jz      short loc_18003FEB0
0x18003fea5  cmp     ebx, 5
0x18003fea8  mov     eax, 80070057h
0x18003fead  cmovnz  edi, eax
0x18003feb0  mov     rcx, r14; hMem
0x18003feb3  call    cs:__imp_LocalFree
0x18003feb9  test    edi, edi
0x18003febb  js      short loc_18003FED8
0x18003febd  mov     rcx, [rbp+ppv]
0x18003fec1  lea     rdx, _GUID_55272a00_42cb_11ce_8135_00aa004bb851
0x18003fec8  mov     r8, r13
0x18003fecb  mov     rax, [rcx]
0x18003fece  mov     rax, [rax]
0x18003fed1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fed6  mov     edi, eax
0x18003fed8  xor     ebx, ebx
0x18003feda  lea     rcx, [rbp+ppv]
0x18003fede  test    edi, edi
0x18003fee0  cmovs   ebx, edi
0x18003fee3  call    ?InternalRelease@?$ComPtr@UIObjectWithRegistryKey@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IObjectWithRegistryKey>::InternalRelease(void)
0x18003fee8  mov     eax, ebx
0x18003feea  mov     rbx, [rsp+60h+arg_0]
0x18003fef2  add     rsp, 60h
0x18003fef6  pop     r15
0x18003fef8  pop     r14
0x18003fefa  pop     r13
0x18003fefc  pop     r12
0x18003fefe  pop     rdi
0x18003feff  pop     rsi
0x18003ff00  pop     rbp
0x18003ff01  retn
```
