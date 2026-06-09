# CPrintAbstractHelper::ResolveConstraintsFromTable(CPrintCoreConfig *,int,int *)

- ea: `0x180033534`
- end: `0x1800336f4`
- name: `?ResolveConstraintsFromTable@CPrintAbstractHelper@@IEAAJPEAVCPrintCoreConfig@@HPEAH@Z`
- size: `448`
- prototype: `__int64 __fastcall(CPrintAbstractHelper *__hidden this, struct CPrintCoreConfig *, int, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180033420`

## callees

- `0x180033534`
- `0x1800336fc`
- `0x18005f010`

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
0x180033534  mov     [rsp+arg_8], rbx
0x180033539  push    rbp
0x18003353a  push    rsi
0x18003353b  push    rdi
0x18003353c  push    r14
0x18003353e  push    r15
0x180033540  sub     rsp, 30h
0x180033544  mov     rax, [rcx]
0x180033547  mov     r14, r9
0x18003354a  mov     ebp, r8d
0x18003354d  mov     r15, rdx
0x180033550  mov     rsi, rcx
0x180033553  xor     edi, edi
0x180033555  mov     rax, [rax+78h]
0x180033559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003355e  mov     [r14], edi
0x180033561  mov     rbx, rax
0x180033564  cmp     dword ptr [rax], 2
0x180033567  jz      loc_1800336E0
0x18003356d  mov     rax, [rsi]
0x180033570  lea     r9, [rsp+58h+arg_0]
0x180033575  mov     rdx, [rbx+8]
0x180033579  mov     r8, r15
0x18003357c  mov     rcx, rsi
0x18003357f  mov     [rsp+58h+arg_0], 0
0x180033588  mov     [rsp+58h+arg_18], 0
0x180033591  mov     rax, [rax+58h]
0x180033595  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003359a  mov     edi, eax
0x18003359c  test    eax, eax
0x18003359e  js      short loc_1800335BD
0x1800335a0  mov     rax, [rsi]
0x1800335a3  lea     r9, [rsp+58h+arg_18]
0x1800335a8  mov     rdx, [rbx+18h]
0x1800335ac  mov     r8, r15
0x1800335af  mov     rcx, rsi
0x1800335b2  mov     rax, [rax+58h]
0x1800335b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800335bb  mov     edi, eax
0x1800335bd  cmp     edi, 80004005h
0x1800335c3  jnz     short loc_1800335CC
0x1800335c5  xor     edi, edi
0x1800335c7  jmp     loc_1800336C9
0x1800335cc  mov     ecx, [rbx]
0x1800335ce  test    ecx, ecx
0x1800335d0  jz      loc_180033657
0x1800335d6  cmp     ecx, 1
0x1800335d9  jnz     loc_1800336C9
0x1800335df  test    edi, edi
0x1800335e1  js      loc_1800336C9
0x1800335e7  mov     rax, [rsp+58h+arg_0]
0x1800335ec  mov     rdx, [rbx+10h]
0x1800335f0  sub     rdx, rax
0x1800335f3  movzx   ecx, byte ptr [rax]
0x1800335f6  movzx   r8d, byte ptr [rax+rdx]
0x1800335fb  sub     ecx, r8d
0x1800335fe  jnz     short loc_180033608
0x180033600  inc     rax
0x180033603  test    r8d, r8d
0x180033606  jnz     short loc_1800335F3
0x180033608  test    ecx, ecx
0x18003360a  jnz     loc_1800336C9
0x180033610  mov     rax, [rsp+58h+arg_18]
0x180033615  mov     rdx, [rbx+20h]
0x180033619  sub     rdx, rax
0x18003361c  movzx   ecx, byte ptr [rax]
0x18003361f  movzx   r8d, byte ptr [rax+rdx]
0x180033624  sub     ecx, r8d
0x180033627  jnz     short loc_180033631
0x180033629  inc     rax
0x18003362c  test    r8d, r8d
0x18003362f  jnz     short loc_18003361C
0x180033631  test    ecx, ecx
0x180033633  jnz     loc_1800336C9
0x180033639  test    ebp, ebp
0x18003363b  jz      short loc_18003364E
0x18003363d  mov     r8, [rbx+18h]; char *
0x180033641  mov     rdx, r15; struct CPrintCoreConfig *
0x180033644  mov     rcx, rsi; this
0x180033647  call    ?SelectFirstAvailableOption@CPrintAbstractHelper@@IEAAJPEAVCPrintCoreConfig@@PEBD@Z; CPrintAbstractHelper::SelectFirstAvailableOption(CPrintCoreConfig *,char const *)
0x18003364c  mov     edi, eax
0x18003364e  mov     dword ptr [r14], 1
0x180033655  jmp     short loc_1800336CF
0x180033657  test    edi, edi
0x180033659  js      short loc_1800336C9
0x18003365b  mov     rax, [rsp+58h+arg_0]
0x180033660  mov     rdx, [rbx+10h]
0x180033664  sub     rdx, rax
0x180033667  movzx   ecx, byte ptr [rax]
0x18003366a  movzx   r8d, byte ptr [rax+rdx]
0x18003366f  sub     ecx, r8d
0x180033672  jnz     short loc_18003367C
0x180033674  inc     rax
0x180033677  test    r8d, r8d
0x18003367a  jnz     short loc_180033667
0x18003367c  test    ecx, ecx
0x18003367e  jnz     short loc_1800336C9
0x180033680  mov     r8, [rbx+20h]
0x180033684  mov     rax, [rsp+58h+arg_18]
0x180033689  mov     r9, r8
0x18003368c  sub     r9, rax
0x18003368f  movzx   ecx, byte ptr [rax]
0x180033692  movzx   edx, byte ptr [rax+r9]
0x180033697  sub     ecx, edx
0x180033699  jnz     short loc_1800336A2
0x18003369b  inc     rax
0x18003369e  test    edx, edx
0x1800336a0  jnz     short loc_18003368F
0x1800336a2  test    ecx, ecx
0x1800336a4  jz      short loc_1800336C9
0x1800336a6  test    ebp, ebp
0x1800336a8  jz      short loc_1800336C2
0x1800336aa  mov     rax, [rsi]
0x1800336ad  mov     r9, r15
0x1800336b0  mov     rdx, [rbx+18h]
0x1800336b4  mov     rcx, rsi
0x1800336b7  mov     rax, [rax+50h]
0x1800336bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800336c0  mov     edi, eax
0x1800336c2  mov     dword ptr [r14], 1
0x1800336c9  cmp     dword ptr [r14], 0
0x1800336cd  jz      short loc_1800336D3
0x1800336cf  test    ebp, ebp
0x1800336d1  jz      short loc_1800336E0
0x1800336d3  add     rbx, 28h ; '('
0x1800336d7  cmp     dword ptr [rbx], 2
0x1800336da  jnz     loc_18003356D
0x1800336e0  mov     rbx, [rsp+58h+arg_8]
0x1800336e5  mov     eax, edi
0x1800336e7  add     rsp, 30h
0x1800336eb  pop     r15
0x1800336ed  pop     r14
0x1800336ef  pop     rdi
0x1800336f0  pop     rsi
0x1800336f1  pop     rbp
0x1800336f2  retn
```
