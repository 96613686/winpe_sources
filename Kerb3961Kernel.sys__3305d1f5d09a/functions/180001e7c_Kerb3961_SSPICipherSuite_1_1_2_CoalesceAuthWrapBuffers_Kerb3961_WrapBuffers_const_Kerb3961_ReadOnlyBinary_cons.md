# Kerb3961::SSPICipherSuite<1,1,2>::CoalesceAuthWrapBuffers(Kerb3961::WrapBuffers const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x180001e7c`
- end: `0x180001feb`
- name: `?CoalesceAuthWrapBuffers@?$SSPICipherSuite@$00$00$01@Kerb3961@@IEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@AEBUReadOnlyBinary@2@@Z`
- size: `367`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1800064e0`
- `0x180006b30`

## callees

- `0x180001e7c`
- `0x180003a38`
- `0x180005b1c`
- `0x180011760`
- `0x180011b40`
- `0x180012300`

## pseudocode

```c
__int64 __fastcall Kerb3961::SSPICipherSuite<1,1,2>::CoalesceAuthWrapBuffers(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v5; // rcx
  __int64 v6; // rax
  const char *v7; // r9
  char v8; // r8
  __int64 v9; // r10
  const char *v10; // rdx
  const char *v11; // rdx
  int v12; // r15d
  __int64 v13; // rdi
  char *v14; // rbp
  char *v15; // rsi
  __int64 v16; // r14
  __int64 v17; // rcx
  void *v18; // rcx
  char *v19; // rcx
  __int64 v21; // [rsp+20h] [rbp-58h] BYREF
  void *v22; // [rsp+28h] [rbp-50h]
  __int64 v23; // [rsp+30h] [rbp-48h]

  if ( !*a3 )
  {
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = 0;
    return a2;
  }
  v5 = a3[1];
  v6 = 3LL * *a3;
  v7 = 0;
  v8 = 0;
  v9 = v5 + 8 * v6;
  if ( v5 == v9 )
  {
LABEL_23:
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = 0;
    return a2;
  }
  while ( 1 )
  {
    if ( !*(_BYTE *)(v5 + 16) )
      v8 = 1;
    v10 = &v7[*(_QWORD *)v5];
    if ( v10 < v7 )
    {
      v19 = "newTotalLength >= totalLength";
      goto LABEL_21;
    }
    if ( (unsigned __int64)v10 > 0xFFFFFFFFFFFF0000uLL )
    {
      v19 = "newTotalLength <= MessageLimit";
LABEL_21:
      Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v19, v10);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = -1073741675;
      return a2;
    }
    v5 += 24;
    if ( v5 == v9 )
      break;
    v7 = v10;
  }
  if ( !v8 || !v10 )
    goto LABEL_23;
  Kerb3961::MakeBuffer(&v21);
  v12 = v23;
  if ( (int)v23 < 0 )
  {
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"result", v11);
    v18 = v22;
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -1073741801;
    if ( v18 )
      Kerb3961Free(v18);
  }
  else
  {
    v13 = a3[1];
    v14 = (char *)v22;
    v15 = (char *)v22;
    v16 = v13 + 24LL * *a3;
    while ( v13 != v16 )
    {
      memmove(v15, *(const void **)(v13 + 8), *(_QWORD *)v13);
      v15 += *(_QWORD *)v13;
      v13 += 24;
    }
    v17 = v21;
    if ( v15 != &v14[v21] )
      Kerb3961::ConsistencyFail(
        (Kerb3961 *)L"Incorrect total length for coalescing auth buffers",
        (const unsigned __int16 *)v11);
    *(_DWORD *)(a2 + 16) = v12;
    *(_QWORD *)a2 = v17;
    *(_QWORD *)(a2 + 8) = v14;
  }
  return a2;
}

```

## disassembly

```asm
0x180001e7c  push    rbx
0x180001e7e  push    rbp
0x180001e7f  push    rsi
0x180001e80  push    rdi
0x180001e81  push    r14
0x180001e83  push    r15
0x180001e85  sub     rsp, 48h
0x180001e89  mov     rax, [r8]
0x180001e8c  xor     edi, edi
0x180001e8e  mov     r14, r8
0x180001e91  mov     rbx, rdx
0x180001e94  test    rax, rax
0x180001e97  jnz     short loc_180001EA8
0x180001e99  mov     [rdx], rdi
0x180001e9c  mov     [rdx+8], rdi
0x180001ea0  mov     [rdx+10h], edi
0x180001ea3  jmp     loc_180001FCD
0x180001ea8  mov     rcx, [r14+8]
0x180001eac  lea     rax, [rax+rax*2]
0x180001eb0  mov     r9, rdi
0x180001eb3  mov     r8b, dil
0x180001eb6  lea     r10, [rcx+rax*8]
0x180001eba  cmp     rcx, r10
0x180001ebd  jz      loc_180001FC3
0x180001ec3  cmp     [rcx+10h], dil
0x180001ec7  mov     eax, 1
0x180001ecc  mov     rdx, [rcx]
0x180001ecf  movzx   r8d, r8b
0x180001ed3  cmovz   r8d, eax
0x180001ed7  add     rdx, r9; char *
0x180001eda  cmp     rdx, r9
0x180001edd  jb      loc_180001FBA
0x180001ee3  cmp     rdx, 0FFFFFFFFFFFF0000h
0x180001eea  ja      loc_180001F9E
0x180001ef0  add     rcx, 18h
0x180001ef4  cmp     rcx, r10
0x180001ef7  jz      short loc_180001EFE
0x180001ef9  mov     r9, rdx
0x180001efc  jmp     short loc_180001EC3
0x180001efe  test    r8b, r8b
0x180001f01  jz      loc_180001FC3
0x180001f07  test    rdx, rdx
0x180001f0a  jz      loc_180001FC3
0x180001f10  lea     rcx, [rsp+78h+var_58]
0x180001f15  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x180001f1a  mov     r15, [rsp+78h+var_48]
0x180001f1f  test    r15d, r15d
0x180001f22  js      short loc_180001F73
0x180001f24  mov     rax, [r14]
0x180001f27  mov     rdi, [r14+8]
0x180001f2b  mov     rbp, [rsp+78h+var_50]
0x180001f30  mov     rsi, rbp
0x180001f33  lea     rcx, [rax+rax*2]
0x180001f37  lea     r14, [rdi+rcx*8]
0x180001f3b  jmp     short loc_180001F53
0x180001f3d  mov     r8, [rdi]; Size
0x180001f40  mov     rcx, rsi; void *
0x180001f43  mov     rdx, [rdi+8]; Src
0x180001f47  call    memmove
0x180001f4c  add     rsi, [rdi]
0x180001f4f  add     rdi, 18h
0x180001f53  cmp     rdi, r14
0x180001f56  jnz     short loc_180001F3D
0x180001f58  mov     rcx, [rsp+78h+var_58]
0x180001f5d  lea     rax, [rcx+rbp]
0x180001f61  cmp     rsi, rax
0x180001f64  jnz     short loc_180001FDE
0x180001f66  mov     [rbx+10h], r15d
0x180001f6a  mov     [rbx], rcx
0x180001f6d  mov     [rbx+8], rbp
0x180001f71  jmp     short loc_180001FCD
0x180001f73  lea     rcx, aResult; "result"
0x180001f7a  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180001f7f  mov     rcx, [rsp+78h+var_50]
0x180001f84  mov     [rbx], rdi
0x180001f87  mov     [rbx+8], rdi
0x180001f8b  mov     dword ptr [rbx+10h], 0C0000017h
0x180001f92  test    rcx, rcx
0x180001f95  jz      short loc_180001FCD
0x180001f97  call    Kerb3961Free
0x180001f9c  jmp     short loc_180001FCD
0x180001f9e  lea     rcx, aNewtotallength_0; "newTotalLength <= MessageLimit"
0x180001fa5  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180001faa  mov     [rbx], rdi
0x180001fad  mov     [rbx+8], rdi
0x180001fb1  mov     dword ptr [rbx+10h], 0C0000095h
0x180001fb8  jmp     short loc_180001FCD
0x180001fba  lea     rcx, aNewtotallength; "newTotalLength >= totalLength"
0x180001fc1  jmp     short loc_180001FA5
0x180001fc3  mov     [rbx], rdi
0x180001fc6  mov     [rbx+8], rdi
0x180001fca  mov     [rbx+10h], edi
0x180001fcd  mov     rax, rbx
0x180001fd0  add     rsp, 48h
0x180001fd4  pop     r15
0x180001fd6  pop     r14
0x180001fd8  pop     rdi
0x180001fd9  pop     rsi
0x180001fda  pop     rbp
0x180001fdb  pop     rbx
0x180001fdc  retn
0x180001fde  lea     rcx, aIncorrectTotal; "Incorrect total length for coalescing a"...
0x180001fe5  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
