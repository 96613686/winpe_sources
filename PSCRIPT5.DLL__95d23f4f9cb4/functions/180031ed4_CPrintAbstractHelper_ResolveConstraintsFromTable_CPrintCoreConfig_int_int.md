# CPrintAbstractHelper::ResolveConstraintsFromTable(CPrintCoreConfig *,int,int *)

- ea: `0x180031ed4`
- end: `0x180032093`
- name: `?ResolveConstraintsFromTable@CPrintAbstractHelper@@IEAAJPEAVCPrintCoreConfig@@HPEAH@Z`
- size: `447`
- prototype: `__int64 __fastcall(CPrintAbstractHelper *__hidden this, struct CPrintCoreConfig *, int, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180031dc0`

## callees

- `0x180031ed4`
- `0x18003209c`
- `0x18005d010`

## pseudocode

```c
__int64 __fastcall CPrintAbstractHelper::ResolveConstraintsFromTable(
        CPrintAbstractHelper *this,
        struct CPrintCoreConfig *a2,
        int a3,
        int *a4)
{
  int AvailableOption; // edi
  __int64 v9; // rax
  __int64 i; // rbx
  __int64 v11; // rax
  __int64 v12; // rdx
  const char *v14; // [rsp+60h] [rbp+8h] BYREF
  const char *v15; // [rsp+78h] [rbp+20h] BYREF

  AvailableOption = 0;
  v9 = (*(__int64 (__fastcall **)(CPrintAbstractHelper *))(*(_QWORD *)this + 120LL))(this);
  *a4 = 0;
  for ( i = v9; *(_DWORD *)i != 2; i += 40 )
  {
    v11 = *(_QWORD *)this;
    v12 = *(_QWORD *)(i + 8);
    v14 = 0;
    v15 = 0;
    AvailableOption = (*(__int64 (__fastcall **)(CPrintAbstractHelper *, __int64, struct CPrintCoreConfig *, const char **))(v11 + 88))(
                        this,
                        v12,
                        a2,
                        &v14);
    if ( AvailableOption >= 0 )
      AvailableOption = (*(__int64 (__fastcall **)(CPrintAbstractHelper *, _QWORD, struct CPrintCoreConfig *, const char **))(*(_QWORD *)this + 88LL))(
                          this,
                          *(_QWORD *)(i + 24),
                          a2,
                          &v15);
    if ( AvailableOption == -2147467259 )
    {
      AvailableOption = 0;
    }
    else if ( *(_DWORD *)i )
    {
      if ( *(_DWORD *)i == 1
        && AvailableOption >= 0
        && !strcmp(v14, *(const char **)(i + 16))
        && !strcmp(v15, *(const char **)(i + 32)) )
      {
        if ( a3 )
          AvailableOption = CPrintAbstractHelper::SelectFirstAvailableOption(this, a2, *(const char **)(i + 24));
        *a4 = 1;
LABEL_21:
        if ( !a3 )
          return (unsigned int)AvailableOption;
        continue;
      }
    }
    else if ( AvailableOption >= 0 && !strcmp(v14, *(const char **)(i + 16)) && strcmp(v15, *(const char **)(i + 32)) )
    {
      if ( a3 )
        AvailableOption = (*(__int64 (__fastcall **)(CPrintAbstractHelper *, _QWORD, _QWORD, struct CPrintCoreConfig *))(*(_QWORD *)this + 80LL))(
                            this,
                            *(_QWORD *)(i + 24),
                            *(_QWORD *)(i + 32),
                            a2);
      *a4 = 1;
    }
    if ( *a4 )
      goto LABEL_21;
  }
  return (unsigned int)AvailableOption;
}

```

## disassembly

```asm
0x180031ed4  mov     [rsp+arg_8], rbx
0x180031ed9  push    rbp
0x180031eda  push    rsi
0x180031edb  push    rdi
0x180031edc  push    r14
0x180031ede  push    r15
0x180031ee0  sub     rsp, 30h
0x180031ee4  mov     rax, [rcx]
0x180031ee7  mov     r14, r9
0x180031eea  mov     ebp, r8d
0x180031eed  mov     r15, rdx
0x180031ef0  mov     rsi, rcx
0x180031ef3  xor     edi, edi
0x180031ef5  mov     rax, [rax+78h]
0x180031ef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031efe  mov     [r14], edi
0x180031f01  mov     rbx, rax
0x180031f04  cmp     dword ptr [rax], 2
0x180031f07  jz      loc_180032080
0x180031f0d  mov     rax, [rsi]
0x180031f10  lea     r9, [rsp+58h+arg_0]
0x180031f15  mov     rdx, [rbx+8]
0x180031f19  mov     r8, r15
0x180031f1c  mov     rcx, rsi
0x180031f1f  mov     [rsp+58h+arg_0], 0
0x180031f28  mov     [rsp+58h+arg_18], 0
0x180031f31  mov     rax, [rax+58h]
0x180031f35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f3a  mov     edi, eax
0x180031f3c  test    eax, eax
0x180031f3e  js      short loc_180031F5D
0x180031f40  mov     rax, [rsi]
0x180031f43  lea     r9, [rsp+58h+arg_18]
0x180031f48  mov     rdx, [rbx+18h]
0x180031f4c  mov     r8, r15
0x180031f4f  mov     rcx, rsi
0x180031f52  mov     rax, [rax+58h]
0x180031f56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f5b  mov     edi, eax
0x180031f5d  cmp     edi, 80004005h
0x180031f63  jnz     short loc_180031F6C
0x180031f65  xor     edi, edi
0x180031f67  jmp     loc_180032069
0x180031f6c  mov     ecx, [rbx]
0x180031f6e  test    ecx, ecx
0x180031f70  jz      loc_180031FF7
0x180031f76  cmp     ecx, 1
0x180031f79  jnz     loc_180032069
0x180031f7f  test    edi, edi
0x180031f81  js      loc_180032069
0x180031f87  mov     rax, [rsp+58h+arg_0]
0x180031f8c  mov     rdx, [rbx+10h]
0x180031f90  sub     rdx, rax
0x180031f93  movzx   ecx, byte ptr [rax]
0x180031f96  movzx   r8d, byte ptr [rax+rdx]
0x180031f9b  sub     ecx, r8d
0x180031f9e  jnz     short loc_180031FA8
0x180031fa0  inc     rax
0x180031fa3  test    r8d, r8d
0x180031fa6  jnz     short loc_180031F93
0x180031fa8  test    ecx, ecx
0x180031faa  jnz     loc_180032069
0x180031fb0  mov     rax, [rsp+58h+arg_18]
0x180031fb5  mov     rdx, [rbx+20h]
0x180031fb9  sub     rdx, rax
0x180031fbc  movzx   ecx, byte ptr [rax]
0x180031fbf  movzx   r8d, byte ptr [rax+rdx]
0x180031fc4  sub     ecx, r8d
0x180031fc7  jnz     short loc_180031FD1
0x180031fc9  inc     rax
0x180031fcc  test    r8d, r8d
0x180031fcf  jnz     short loc_180031FBC
0x180031fd1  test    ecx, ecx
0x180031fd3  jnz     loc_180032069
0x180031fd9  test    ebp, ebp
0x180031fdb  jz      short loc_180031FEE
0x180031fdd  mov     r8, [rbx+18h]; char *
0x180031fe1  mov     rdx, r15; struct CPrintCoreConfig *
0x180031fe4  mov     rcx, rsi; this
0x180031fe7  call    ?SelectFirstAvailableOption@CPrintAbstractHelper@@IEAAJPEAVCPrintCoreConfig@@PEBD@Z; CPrintAbstractHelper::SelectFirstAvailableOption(CPrintCoreConfig *,char const *)
0x180031fec  mov     edi, eax
0x180031fee  mov     dword ptr [r14], 1
0x180031ff5  jmp     short loc_18003206F
0x180031ff7  test    edi, edi
0x180031ff9  js      short loc_180032069
0x180031ffb  mov     rax, [rsp+58h+arg_0]
0x180032000  mov     rdx, [rbx+10h]
0x180032004  sub     rdx, rax
0x180032007  movzx   ecx, byte ptr [rax]
0x18003200a  movzx   r8d, byte ptr [rax+rdx]
0x18003200f  sub     ecx, r8d
0x180032012  jnz     short loc_18003201C
0x180032014  inc     rax
0x180032017  test    r8d, r8d
0x18003201a  jnz     short loc_180032007
0x18003201c  test    ecx, ecx
0x18003201e  jnz     short loc_180032069
0x180032020  mov     r8, [rbx+20h]
0x180032024  mov     rax, [rsp+58h+arg_18]
0x180032029  mov     r9, r8
0x18003202c  sub     r9, rax
0x18003202f  movzx   ecx, byte ptr [rax]
0x180032032  movzx   edx, byte ptr [rax+r9]
0x180032037  sub     ecx, edx
0x180032039  jnz     short loc_180032042
0x18003203b  inc     rax
0x18003203e  test    edx, edx
0x180032040  jnz     short loc_18003202F
0x180032042  test    ecx, ecx
0x180032044  jz      short loc_180032069
0x180032046  test    ebp, ebp
0x180032048  jz      short loc_180032062
0x18003204a  mov     rax, [rsi]
0x18003204d  mov     r9, r15
0x180032050  mov     rdx, [rbx+18h]
0x180032054  mov     rcx, rsi
0x180032057  mov     rax, [rax+50h]
0x18003205b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032060  mov     edi, eax
0x180032062  mov     dword ptr [r14], 1
0x180032069  cmp     dword ptr [r14], 0
0x18003206d  jz      short loc_180032073
0x18003206f  test    ebp, ebp
0x180032071  jz      short loc_180032080
0x180032073  add     rbx, 28h ; '('
0x180032077  cmp     dword ptr [rbx], 2
0x18003207a  jnz     loc_180031F0D
0x180032080  mov     rbx, [rsp+58h+arg_8]
0x180032085  mov     eax, edi
0x180032087  add     rsp, 30h
0x18003208b  pop     r15
0x18003208d  pop     r14
0x18003208f  pop     rdi
0x180032090  pop     rsi
0x180032091  pop     rbp
0x180032092  retn
```
