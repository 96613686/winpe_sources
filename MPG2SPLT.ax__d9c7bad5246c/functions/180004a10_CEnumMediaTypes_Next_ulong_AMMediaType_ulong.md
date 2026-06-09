# CEnumMediaTypes::Next(ulong,_AMMediaType * *,ulong *)

- ea: `0x180004a10`
- end: `0x180004b8f`
- name: `?Next@CEnumMediaTypes@@UEAAJKPEAPEAU_AMMediaType@@PEAK@Z`
- size: `383`
- prototype: `__int64 __fastcall(CEnumMediaTypes *__hidden this, unsigned int, struct _AMMediaType **, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x180001460`
- `0x180001e98`
- `0x180004a10`
- `0x180006b18`
- `0x180034010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180004acc`
- `ole32!CoTaskMemAlloc` at `0x180004acc`

## pseudocode

```c
__int64 __fastcall CEnumMediaTypes::Next(
        CEnumMediaTypes *this,
        unsigned int a2,
        struct _AMMediaType **a3,
        unsigned int *a4)
{
  struct _AMMediaType **v5; // rsi
  unsigned int v9; // r14d
  __int64 v10; // rdx
  __int64 *v11; // rcx
  __int64 v12; // rax
  struct _AMMediaType *v13; // rax
  struct _AMMediaType v14; // [rsp+20h] [rbp-39h] BYREF

  v5 = a3;
  if ( !a3 )
    return 2147500035LL;
  if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 32LL))(*((_QWORD *)this + 2)) != *((_DWORD *)this + 6) )
    return 2147746307LL;
  if ( a4 )
  {
    *a4 = 0;
  }
  else if ( a2 > 1 )
  {
    return 2147942487LL;
  }
  v9 = 0;
  if ( a2 )
  {
    while ( 1 )
    {
      memset_0(&v14, 0, sizeof(v14));
      v10 = *((unsigned int *)this + 2);
      v11 = (__int64 *)*((_QWORD *)this + 2);
      v14.lSampleSize = 1;
      v14.bFixedSizeSamples = 1;
      v12 = *v11;
      *((_DWORD *)this + 2) = v10 + 1;
      if ( (*(unsigned int (__fastcall **)(__int64 *, __int64, struct _AMMediaType *))(v12 + 104))(v11, v10, &v14) )
        break;
      v13 = (struct _AMMediaType *)CoTaskMemAlloc(0x58u);
      *v5 = v13;
      if ( !v13 )
        break;
      ++v5;
      *v13 = v14;
      ++v9;
      v14.pbFormat = 0;
      v14.cbFormat = 0;
      v14.pUnk = 0;
      FreeMediaType(&v14);
      if ( !--a2 )
        goto LABEL_14;
    }
    FreeMediaType(&v14);
  }
LABEL_14:
  if ( a4 )
    *a4 = v9;
  return a2 != 0;
}

```

## disassembly

```asm
0x180004a10  mov     [rsp-8+arg_8], rbx
0x180004a15  push    rbp
0x180004a16  push    rsi
0x180004a17  push    rdi
0x180004a18  push    r14
0x180004a1a  push    r15
0x180004a1c  lea     rbp, [rsp-37h]
0x180004a21  sub     rsp, 90h
0x180004a28  mov     rax, cs:__security_cookie
0x180004a2f  xor     rax, rsp
0x180004a32  mov     [rbp+57h+var_30], rax
0x180004a36  mov     rdi, r9
0x180004a39  mov     rsi, r8
0x180004a3c  mov     ebx, edx
0x180004a3e  mov     r15, rcx
0x180004a41  test    r8, r8
0x180004a44  jnz     short loc_180004A50
0x180004a46  mov     eax, 80004003h
0x180004a4b  jmp     loc_180004B6C
0x180004a50  mov     rcx, [rcx+10h]
0x180004a54  mov     rax, [rcx]
0x180004a57  mov     rax, [rax+20h]
0x180004a5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a60  cmp     eax, [r15+18h]
0x180004a64  jnz     loc_180004B67
0x180004a6a  test    rdi, rdi
0x180004a6d  jz      loc_180004B3D
0x180004a73  mov     dword ptr [rdi], 0
0x180004a79  xor     r14d, r14d
0x180004a7c  test    ebx, ebx
0x180004a7e  jz      loc_180004B56
0x180004a84  xor     edx, edx; Val
0x180004a86  lea     rcx, [rbp+57h+var_90]; void *
0x180004a8a  lea     r8d, [rdx+58h]; Size
0x180004a8e  call    memset_0
0x180004a93  mov     edx, [r15+8]
0x180004a97  mov     rcx, [r15+10h]
0x180004a9b  mov     [rbp+57h+var_90.lSampleSize], 1
0x180004aa2  mov     [rbp+57h+var_90.bFixedSizeSamples], 1
0x180004aa9  lea     r8d, [rdx+1]
0x180004aad  mov     rax, [rcx]
0x180004ab0  mov     [r15+8], r8d
0x180004ab4  lea     r8, [rbp+57h+var_90]
0x180004ab8  mov     rax, [rax+68h]
0x180004abc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ac1  test    eax, eax
0x180004ac3  jnz     loc_180004B4D
0x180004ac9  lea     ecx, [rax+58h]; cb
0x180004acc  call    cs:__imp_CoTaskMemAlloc
0x180004ad2  mov     [rsi], rax
0x180004ad5  lea     rcx, [rbp+57h+var_90]; struct _AMMediaType *
0x180004ad9  test    rax, rax
0x180004adc  jz      short loc_180004B51
0x180004ade  movaps  xmm0, xmmword ptr [rbp+57h+var_90.majortype.Data1]
0x180004ae2  add     rsi, 8
0x180004ae6  movups  xmmword ptr [rax], xmm0
0x180004ae9  inc     r14d
0x180004aec  movaps  xmm1, xmmword ptr [rbp+57h+var_90.subtype.Data1]
0x180004af0  movups  xmmword ptr [rax+10h], xmm1
0x180004af4  movaps  xmm0, xmmword ptr [rbp+57h+var_90.bFixedSizeSamples]
0x180004af8  movups  xmmword ptr [rax+20h], xmm0
0x180004afc  movaps  xmm1, xmmword ptr [rbp+57h+var_90.formattype.Data2]
0x180004b00  movups  xmmword ptr [rax+30h], xmm1
0x180004b04  movaps  xmm0, xmmword ptr [rbp+57h+var_90.pUnk]
0x180004b08  movups  xmmword ptr [rax+40h], xmm0
0x180004b0c  movsd   xmm1, [rbp+57h+var_90.pbFormat]
0x180004b11  movsd   qword ptr [rax+50h], xmm1
0x180004b16  mov     [rbp+57h+var_90.pbFormat], 0
0x180004b1e  mov     [rbp+57h+var_90.cbFormat], 0
0x180004b25  mov     [rbp+57h+var_90.pUnk], 0
0x180004b2d  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x180004b32  add     ebx, 0FFFFFFFFh
0x180004b35  jnz     loc_180004A84
0x180004b3b  jmp     short loc_180004B56
0x180004b3d  cmp     ebx, 1
0x180004b40  jbe     loc_180004A79
0x180004b46  mov     eax, 80070057h
0x180004b4b  jmp     short loc_180004B6C
0x180004b4d  lea     rcx, [rbp+57h+var_90]; struct _AMMediaType *
0x180004b51  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x180004b56  test    rdi, rdi
0x180004b59  jz      short loc_180004B5E
0x180004b5b  mov     [rdi], r14d
0x180004b5e  xor     eax, eax
0x180004b60  test    ebx, ebx
0x180004b62  setnz   al
0x180004b65  jmp     short loc_180004B6C
0x180004b67  mov     eax, 80040203h
0x180004b6c  mov     rcx, [rbp+57h+var_30]
0x180004b70  xor     rcx, rsp; StackCookie
0x180004b73  call    __security_check_cookie
0x180004b78  mov     rbx, [rsp+0B0h+arg_8]
0x180004b80  add     rsp, 90h
0x180004b87  pop     r15
0x180004b89  pop     r14
0x180004b8b  pop     rdi
0x180004b8c  pop     rsi
0x180004b8d  pop     rbp
0x180004b8e  retn
```
