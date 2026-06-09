# CPrintAbstractHelper::ProcessConstraintsInternal(CPrintCoreConfig *,int,int *)

- ea: `0x180033420`
- end: `0x18003352e`
- name: `?ProcessConstraintsInternal@CPrintAbstractHelper@@MEAAJPEAVCPrintCoreConfig@@HPEAH@Z`
- size: `270`
- prototype: `__int64 __fastcall(CPrintAbstractHelper *this, struct CPrintCoreConfig *, int, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18002e500`

## callees

- `0x180033420`
- `0x180033534`
- `0x180034320`
- `0x18005642c`
- `0x18005f010`

## pseudocode

```c
__int64 __fastcall CPrintAbstractHelper::ProcessConstraintsInternal(
        CPrintAbstractHelper *this,
        struct CPrintCoreConfig *a2,
        int a3,
        int *a4)
{
  int v7; // r14d
  int v8; // edi
  int v9; // r15d
  char *v10; // rbp
  _DWORD *v11; // rax
  int v12; // ebp
  char *v13; // rdi
  _DWORD *v14; // rax

  v7 = CPrintAbstractHelper::ResolveConstraintsFromTable(this, a2, a3, a4);
  if ( v7 >= 0 )
  {
    if ( a3 )
    {
      v8 = 1;
      v9 = ((CPrintCoreConfig::GetHelperSettingsFlags(a2) & 1) == 0) + 1;
      if ( *((_QWORD *)a2 + 2) )
        v10 = (char *)a2 + 28;
      else
        v10 = (char *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(*((_QWORD *)a2 + 1) + 8LL))(*(_QWORD *)a2, 0);
      v11 = (_DWORD *)(*(__int64 (__fastcall **)(_QWORD))(*((_QWORD *)a2 + 1) + 32LL))(*(_QWORD *)a2);
      if ( (unsigned int)PPDResolveUIConflicts(v11, v10, 0x200u, v9) && !*a4 )
        v8 = 0;
      *a4 = v8;
    }
    else if ( !*a4 )
    {
      v12 = (CPrintCoreConfig::GetHelperSettingsFlags(a2) & 1) - 0x7FFFFFFF;
      if ( *((_QWORD *)a2 + 2) )
        v13 = (char *)a2 + 28;
      else
        v13 = (char *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(*((_QWORD *)a2 + 1) + 8LL))(*(_QWORD *)a2, 0);
      v14 = (_DWORD *)(*(__int64 (__fastcall **)(_QWORD))(*((_QWORD *)a2 + 1) + 32LL))(*(_QWORD *)a2);
      *a4 = PPDResolveUIConflicts(v14, v13, 0x200u, v12) == 0;
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180033420  push    rbx
0x180033422  push    rbp
0x180033423  push    rsi
0x180033424  push    rdi
0x180033425  push    r14
0x180033427  push    r15
0x180033429  sub     rsp, 28h
0x18003342d  mov     rsi, r9
0x180033430  mov     edi, r8d
0x180033433  mov     rbx, rdx
0x180033436  call    ?ResolveConstraintsFromTable@CPrintAbstractHelper@@IEAAJPEAVCPrintCoreConfig@@HPEAH@Z; CPrintAbstractHelper::ResolveConstraintsFromTable(CPrintCoreConfig *,int,int *)
0x18003343b  mov     r14d, eax
0x18003343e  test    eax, eax
0x180033440  js      loc_18003351D
0x180033446  test    edi, edi
0x180033448  jz      short loc_1800334B4
0x18003344a  mov     rcx, rbx; this
0x18003344d  call    ?GetHelperSettingsFlags@CPrintCoreConfig@@QEBAKXZ; CPrintCoreConfig::GetHelperSettingsFlags(void)
0x180033452  not     eax
0x180033454  mov     edi, 1
0x180033459  and     eax, edi
0x18003345b  cmp     qword ptr [rbx+10h], 0
0x180033460  lea     r15d, [rax+1]
0x180033464  jz      short loc_18003346C
0x180033466  lea     rbp, [rbx+1Ch]
0x18003346a  jmp     short loc_180033481
0x18003346c  mov     rax, [rbx+8]
0x180033470  xor     edx, edx
0x180033472  mov     rcx, [rbx]
0x180033475  mov     rax, [rax+8]
0x180033479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003347e  mov     rbp, rax
0x180033481  mov     rcx, [rbx+8]
0x180033485  mov     rax, [rcx+20h]
0x180033489  mov     rcx, [rbx]
0x18003348c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033491  mov     r9d, r15d
0x180033494  mov     r8d, 200h
0x18003349a  mov     rdx, rbp
0x18003349d  mov     rcx, rax
0x1800334a0  call    PPDResolveUIConflicts
0x1800334a5  test    eax, eax
0x1800334a7  jz      short loc_1800334B0
0x1800334a9  cmp     dword ptr [rsi], 0
0x1800334ac  jnz     short loc_1800334B0
0x1800334ae  xor     edi, edi
0x1800334b0  mov     [rsi], edi
0x1800334b2  jmp     short loc_18003351D
0x1800334b4  cmp     dword ptr [rsi], 0
0x1800334b7  jnz     short loc_18003351D
0x1800334b9  mov     rcx, rbx; this
0x1800334bc  call    ?GetHelperSettingsFlags@CPrintCoreConfig@@QEBAKXZ; CPrintCoreConfig::GetHelperSettingsFlags(void)
0x1800334c1  mov     ebp, 1
0x1800334c6  and     ebp, eax
0x1800334c8  add     ebp, 80000001h
0x1800334ce  cmp     qword ptr [rbx+10h], 0
0x1800334d3  jz      short loc_1800334DB
0x1800334d5  lea     rdi, [rbx+1Ch]
0x1800334d9  jmp     short loc_1800334F0
0x1800334db  mov     rax, [rbx+8]
0x1800334df  xor     edx, edx
0x1800334e1  mov     rcx, [rbx]
0x1800334e4  mov     rax, [rax+8]
0x1800334e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800334ed  mov     rdi, rax
0x1800334f0  mov     rcx, [rbx+8]
0x1800334f4  mov     rax, [rcx+20h]
0x1800334f8  mov     rcx, [rbx]
0x1800334fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033500  mov     r9d, ebp
0x180033503  mov     r8d, 200h
0x180033509  mov     rdx, rdi
0x18003350c  mov     rcx, rax
0x18003350f  call    PPDResolveUIConflicts
0x180033514  xor     ecx, ecx
0x180033516  test    eax, eax
0x180033518  setz    cl
0x18003351b  mov     [rsi], ecx
0x18003351d  mov     eax, r14d
0x180033520  add     rsp, 28h
0x180033524  pop     r15
0x180033526  pop     r14
0x180033528  pop     rdi
0x180033529  pop     rsi
0x18003352a  pop     rbp
0x18003352b  pop     rbx
0x18003352c  retn
```
