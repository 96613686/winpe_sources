# CEnumMediaTypes::Next(ulong,_AMMediaType * *,ulong *)

- ea: `0x1800273c0`
- end: `0x180027548`
- name: `?Next@CEnumMediaTypes@@UEAAJKPEAPEAU_AMMediaType@@PEAK@Z`
- size: `392`
- prototype: `__int64 __fastcall(CEnumMediaTypes *__hidden this, unsigned int, struct _AMMediaType **, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800017b0`
- `0x1800021a8`
- `0x1800273c0`
- `0x180029f8c`
- `0x180088750`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002747e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002747e`

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
0x1800273c0  mov     [rsp-8+arg_8], rbx
0x1800273c5  push    rbp
0x1800273c6  push    rsi
0x1800273c7  push    rdi
0x1800273c8  push    r14
0x1800273ca  push    r15
0x1800273cc  lea     rbp, [rsp-37h]
0x1800273d1  sub     rsp, 90h
0x1800273d8  mov     rax, cs:__security_cookie
0x1800273df  xor     rax, rsp
0x1800273e2  mov     [rbp+57h+var_30], rax
0x1800273e6  mov     rdi, r9
0x1800273e9  mov     rsi, r8
0x1800273ec  mov     ebx, edx
0x1800273ee  mov     r15, rcx
0x1800273f1  test    r8, r8
0x1800273f4  jnz     short loc_180027400
0x1800273f6  mov     eax, 80004003h
0x1800273fb  jmp     loc_180027524
0x180027400  mov     rcx, [rcx+10h]
0x180027404  mov     rax, [rcx]
0x180027407  mov     rax, [rax+20h]
0x18002740b  call    cs:__guard_dispatch_icall_fptr
0x180027411  cmp     eax, [r15+18h]
0x180027415  jnz     loc_18002751F
0x18002741b  test    rdi, rdi
0x18002741e  jz      loc_1800274F5
0x180027424  mov     dword ptr [rdi], 0
0x18002742a  xor     r14d, r14d
0x18002742d  test    ebx, ebx
0x18002742f  jz      loc_18002750E
0x180027435  xor     edx, edx; Val
0x180027437  lea     rcx, [rbp+57h+var_90]; void *
0x18002743b  lea     r8d, [rdx+58h]; Size
0x18002743f  call    memset_0
0x180027444  mov     edx, [r15+8]
0x180027448  mov     rcx, [r15+10h]
0x18002744c  mov     [rbp+57h+var_90.lSampleSize], 1
0x180027453  mov     [rbp+57h+var_90.bFixedSizeSamples], 1
0x18002745a  lea     r8d, [rdx+1]
0x18002745e  mov     rax, [rcx]
0x180027461  mov     [r15+8], r8d
0x180027465  lea     r8, [rbp+57h+var_90]
0x180027469  mov     rax, [rax+68h]
0x18002746d  call    cs:__guard_dispatch_icall_fptr
0x180027473  test    eax, eax
0x180027475  jnz     loc_180027505
0x18002747b  lea     ecx, [rax+58h]; cb
0x18002747e  call    cs:__imp_CoTaskMemAlloc
0x180027485  nop     dword ptr [rax+rax+00h]
0x18002748a  mov     [rsi], rax
0x18002748d  lea     rcx, [rbp+57h+var_90]; struct _AMMediaType *
0x180027491  test    rax, rax
0x180027494  jz      short loc_180027509
0x180027496  movaps  xmm0, xmmword ptr [rbp+57h+var_90.majortype.Data1]
0x18002749a  add     rsi, 8
0x18002749e  movups  xmmword ptr [rax], xmm0
0x1800274a1  inc     r14d
0x1800274a4  movaps  xmm1, xmmword ptr [rbp+57h+var_90.subtype.Data1]
0x1800274a8  movups  xmmword ptr [rax+10h], xmm1
0x1800274ac  movaps  xmm0, xmmword ptr [rbp+57h+var_90.bFixedSizeSamples]
0x1800274b0  movups  xmmword ptr [rax+20h], xmm0
0x1800274b4  movaps  xmm1, xmmword ptr [rbp+57h+var_90.formattype.Data2]
0x1800274b8  movups  xmmword ptr [rax+30h], xmm1
0x1800274bc  movaps  xmm0, xmmword ptr [rbp+57h+var_90.pUnk]
0x1800274c0  movups  xmmword ptr [rax+40h], xmm0
0x1800274c4  movsd   xmm1, [rbp+57h+var_90.pbFormat]
0x1800274c9  movsd   qword ptr [rax+50h], xmm1
0x1800274ce  mov     [rbp+57h+var_90.pbFormat], 0
0x1800274d6  mov     [rbp+57h+var_90.cbFormat], 0
0x1800274dd  mov     [rbp+57h+var_90.pUnk], 0
0x1800274e5  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x1800274ea  add     ebx, 0FFFFFFFFh
0x1800274ed  jnz     loc_180027435
0x1800274f3  jmp     short loc_18002750E
0x1800274f5  cmp     ebx, 1
0x1800274f8  jbe     loc_18002742A
0x1800274fe  mov     eax, 80070057h
0x180027503  jmp     short loc_180027524
0x180027505  lea     rcx, [rbp+57h+var_90]; struct _AMMediaType *
0x180027509  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x18002750e  test    rdi, rdi
0x180027511  jz      short loc_180027516
0x180027513  mov     [rdi], r14d
0x180027516  xor     eax, eax
0x180027518  test    ebx, ebx
0x18002751a  setnz   al
0x18002751d  jmp     short loc_180027524
0x18002751f  mov     eax, 80040203h
0x180027524  mov     rcx, [rbp+57h+var_30]
0x180027528  xor     rcx, rsp; StackCookie
0x18002752b  call    __security_check_cookie
0x180027530  mov     rbx, [rsp+0B0h+arg_8]
0x180027538  add     rsp, 90h
0x18002753f  pop     r15
0x180027541  pop     r14
0x180027543  pop     rdi
0x180027544  pop     rsi
0x180027545  pop     rbp
0x180027546  retn
```
