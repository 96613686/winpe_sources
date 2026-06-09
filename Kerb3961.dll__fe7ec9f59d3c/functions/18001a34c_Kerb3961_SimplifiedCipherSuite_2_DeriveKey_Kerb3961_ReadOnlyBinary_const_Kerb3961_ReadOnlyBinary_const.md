# Kerb3961::SimplifiedCipherSuite<2>::DeriveKey(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x18001a34c`
- end: `0x18001a531`
- name: `?DeriveKey@?$SimplifiedCipherSuite@$01@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z`
- size: `485`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18001a760`
- `0x18001b910`

## callees

- `0x180001d64`
- `0x180002928`
- `0x180002fc0`
- `0x18000901c`
- `0x18000e320`
- `0x18001a34c`
- `0x18001d360`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall Kerb3961::SimplifiedCipherSuite<2>::DeriveKey(_QWORD *a1, __int64 a2, __int64 a3, size_t *a4)
{
  unsigned __int64 v8; // r14
  int v9; // r8d
  int v10; // esi
  int v11; // r8d
  int v12; // esi
  int v13; // r8d
  int v14; // esi
  unsigned __int64 v15; // rsi
  int v16; // r8d
  int v17; // r15d
  __int64 v19; // [rsp+30h] [rbp-50h] BYREF
  void *v20; // [rsp+38h] [rbp-48h]
  char *v21; // [rsp+40h] [rbp-40h]
  _BYTE v22[8]; // [rsp+48h] [rbp-38h] BYREF
  void *v23; // [rsp+50h] [rbp-30h]
  char *v24; // [rsp+58h] [rbp-28h]
  _BYTE v25[8]; // [rsp+60h] [rbp-20h] BYREF
  void *Src; // [rsp+68h] [rbp-18h]
  char *v27; // [rsp+70h] [rbp-10h]
  char v28; // [rsp+B0h] [rbp+30h] BYREF

  v8 = a1[12] + a1[9] - 1LL - (unsigned __int64)(a1[9] - 1LL) % a1[12];
  Kerb3961::MakeBuffer(&v19);
  v10 = (int)v21;
  if ( (int)v21 >= 0 )
  {
    Kerb3961::MakeBuffer(v22);
    v12 = (int)v24;
    if ( (int)v24 >= 0 )
    {
      Kerb3961::Nfold((__int64)v25, a1[12], a4);
      v14 = (int)v27;
      if ( (int)v27 >= 0 )
      {
        v15 = 0;
        if ( v8 )
        {
          while ( 1 )
          {
            memset_0(v23, 0, a1[12]);
            v17 = *(_DWORD *)(*(__int64 (__fastcall **)(_QWORD *, char *, __int64, _BYTE *, _BYTE *))(*a1 + 432LL))(
                               a1,
                               &v28,
                               a3,
                               v22,
                               v25);
            if ( v17 < 0 )
              break;
            memcpy_0((char *)v20 + v15, Src, a1[12]);
            v15 += a1[12];
            if ( v15 >= v8 )
              goto LABEL_10;
          }
          Kerb3961::Logging::Verify::StatusFailed(
            (Kerb3961::Logging::Verify *)"BlockEncrypt(baseKey, IV, nfoldConstant)",
            (const char *)(unsigned int)v17,
            v16);
          *(_QWORD *)a2 = 0;
          *(_QWORD *)(a2 + 8) = 0;
          *(_DWORD *)(a2 + 16) = v17;
        }
        else
        {
LABEL_10:
          v19 = a1[9];
          (*(void (__fastcall **)(_QWORD *, __int64, __int64 *))(*a1 + 128LL))(a1, a2, &v19);
        }
      }
      else
      {
        Kerb3961::Logging::Verify::StatusFailed(
          (Kerb3961::Logging::Verify *)"nfoldConstant",
          (const char *)(unsigned int)v27,
          v13);
        *(_QWORD *)a2 = 0;
        *(_QWORD *)(a2 + 8) = 0;
        *(_DWORD *)(a2 + 16) = v14;
      }
      if ( Src )
        operator delete(Src, 0);
    }
    else
    {
      Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"IV", (const char *)(unsigned int)v24, v11);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v12;
    }
    if ( v23 )
      operator delete(v23, 0);
  }
  else
  {
    Kerb3961::Logging::Verify::StatusFailed(
      (Kerb3961::Logging::Verify *)"workSpace",
      (const char *)(unsigned int)v21,
      v9);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v10;
  }
  if ( v20 )
    operator delete(v20, 0);
  return a2;
}

```

## disassembly

```asm
0x18001a34c  mov     [rsp-28h+arg_8], rbx
0x18001a351  mov     [rsp-28h+arg_10], rsi
0x18001a356  push    rbp
0x18001a357  push    rdi
0x18001a358  push    r12
0x18001a35a  push    r14
0x18001a35c  push    r15
0x18001a35e  mov     rbp, rsp
0x18001a361  sub     rsp, 80h
0x18001a368  mov     r14, [rcx+48h]
0x18001a36c  mov     rbx, rdx
0x18001a36f  dec     r14
0x18001a372  xor     edx, edx
0x18001a374  mov     rax, r14
0x18001a377  mov     rdi, rcx
0x18001a37a  div     qword ptr [rcx+60h]
0x18001a37e  mov     r15, r9
0x18001a381  mov     r12, r8
0x18001a384  sub     r14, rdx
0x18001a387  add     r14, [rcx+60h]
0x18001a38b  lea     rcx, [rbp+var_50]
0x18001a38f  mov     rdx, r14
0x18001a392  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x18001a397  mov     esi, dword ptr [rbp+var_40]
0x18001a39a  test    esi, esi
0x18001a39c  jns     short loc_18001A3C3
0x18001a39e  mov     edx, esi; char *
0x18001a3a0  lea     rcx, aWorkspace; "workSpace"
0x18001a3a7  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001a3ac  mov     qword ptr [rbx], 0
0x18001a3b3  mov     qword ptr [rbx+8], 0
0x18001a3bb  mov     [rbx+10h], esi
0x18001a3be  jmp     loc_18001A4DE
0x18001a3c3  mov     rdx, [rdi+60h]
0x18001a3c7  lea     rcx, [rbp+var_38]
0x18001a3cb  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x18001a3d0  mov     esi, dword ptr [rbp+var_28]
0x18001a3d3  test    esi, esi
0x18001a3d5  jns     short loc_18001A3FC
0x18001a3d7  mov     edx, esi; char *
0x18001a3d9  lea     rcx, aIv; "IV"
0x18001a3e0  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001a3e5  mov     qword ptr [rbx], 0
0x18001a3ec  mov     qword ptr [rbx+8], 0
0x18001a3f4  mov     [rbx+10h], esi
0x18001a3f7  jmp     loc_18001A4CE
0x18001a3fc  mov     rdx, [rdi+60h]
0x18001a400  lea     rcx, [rbp+var_20]
0x18001a404  mov     r8, r15
0x18001a407  call    ?Nfold@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_KAEBUReadOnlyBinary@1@@Z; Kerb3961::Nfold(unsigned __int64,Kerb3961::ReadOnlyBinary const &)
0x18001a40c  mov     esi, dword ptr [rbp+var_10]
0x18001a40f  test    esi, esi
0x18001a411  jns     short loc_18001A438
0x18001a413  mov     edx, esi; char *
0x18001a415  lea     rcx, aNfoldconstant; "nfoldConstant"
0x18001a41c  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001a421  mov     qword ptr [rbx], 0
0x18001a428  mov     qword ptr [rbx+8], 0
0x18001a430  mov     [rbx+10h], esi
0x18001a433  jmp     loc_18001A4BE
0x18001a438  xor     esi, esi
0x18001a43a  test    r14, r14
0x18001a43d  jz      short loc_18001A49D
0x18001a43f  mov     r8, [rdi+60h]; Size
0x18001a443  xor     edx, edx; Val
0x18001a445  mov     rcx, [rbp+var_30]; void *
0x18001a449  call    memset_0
0x18001a44e  mov     rax, [rdi]
0x18001a451  lea     rcx, [rbp+var_20]
0x18001a455  mov     [rsp+80h+var_60], rcx
0x18001a45a  lea     r9, [rbp+var_38]
0x18001a45e  mov     r8, r12
0x18001a461  lea     rdx, [rbp+arg_0]
0x18001a465  mov     rcx, rdi
0x18001a468  mov     rax, [rax+1B0h]
0x18001a46f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a474  mov     r15d, [rax]
0x18001a477  test    r15d, r15d
0x18001a47a  js      loc_18001A50D
0x18001a480  mov     rcx, [rbp+var_48]
0x18001a484  mov     r8, [rdi+60h]; Size
0x18001a488  add     rcx, rsi; void *
0x18001a48b  mov     rdx, [rbp+Src]; Src
0x18001a48f  call    memcpy_0
0x18001a494  add     rsi, [rdi+60h]
0x18001a498  cmp     rsi, r14
0x18001a49b  jb      short loc_18001A43F
0x18001a49d  mov     rax, [rdi+48h]
0x18001a4a1  lea     r8, [rbp+var_50]
0x18001a4a5  mov     [rbp+var_50], rax
0x18001a4a9  mov     rdx, rbx
0x18001a4ac  mov     rax, [rdi]
0x18001a4af  mov     rcx, rdi
0x18001a4b2  mov     rax, [rax+80h]
0x18001a4b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a4be  mov     rcx, [rbp+Src]; void *
0x18001a4c2  test    rcx, rcx
0x18001a4c5  jz      short loc_18001A4CE
0x18001a4c7  xor     edx, edx; struct std::nothrow_t *
0x18001a4c9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001a4ce  mov     rcx, [rbp+var_30]; void *
0x18001a4d2  test    rcx, rcx
0x18001a4d5  jz      short loc_18001A4DE
0x18001a4d7  xor     edx, edx; struct std::nothrow_t *
0x18001a4d9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001a4de  mov     rcx, [rbp+var_48]; void *
0x18001a4e2  test    rcx, rcx
0x18001a4e5  jz      short loc_18001A4EE
0x18001a4e7  xor     edx, edx; struct std::nothrow_t *
0x18001a4e9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001a4ee  lea     r11, [rsp+80h+var_s0]
0x18001a4f6  mov     rax, rbx
0x18001a4f9  mov     rbx, [r11+38h]
0x18001a4fd  mov     rsi, [r11+40h]
0x18001a501  mov     rsp, r11
0x18001a504  pop     r15
0x18001a506  pop     r14
0x18001a508  pop     r12
0x18001a50a  pop     rdi
0x18001a50b  pop     rbp
0x18001a50c  retn
0x18001a50d  mov     edx, r15d; char *
0x18001a510  lea     rcx, aBlockencryptBa_0; "BlockEncrypt(baseKey, IV, nfoldConstant"...
0x18001a517  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001a51c  mov     qword ptr [rbx], 0
0x18001a523  mov     qword ptr [rbx+8], 0
0x18001a52b  mov     [rbx+10h], r15d
0x18001a52f  jmp     short loc_18001A4BE
```
