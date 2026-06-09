# CPrintAbstractHelper::ProcessConstraintsInternal(CPrintCoreConfig *,int,int *)

- ea: `0x180031dc0`
- end: `0x180031ecd`
- name: `?ProcessConstraintsInternal@CPrintAbstractHelper@@MEAAJPEAVCPrintCoreConfig@@HPEAH@Z`
- size: `269`
- prototype: `int(CPrintAbstractHelper *__hidden this, struct CPrintCoreConfig *, int, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18002d0e0`

## callees

- `0x180031dc0`
- `0x180031ed4`
- `0x180032cb0`
- `0x180054a50`
- `0x18005d010`

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
  unsigned int v9; // r15d
  char *v10; // rbp
  __int64 v11; // rax
  unsigned int v12; // ebp
  char *v13; // rdi
  __int64 v14; // rax

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
      v11 = (*(__int64 (__fastcall **)(_QWORD))(*((_QWORD *)a2 + 1) + 32LL))(*(_QWORD *)a2);
      if ( (unsigned int)PPDResolveUIConflicts(v11, v10, 512, v9) && !*a4 )
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
      v14 = (*(__int64 (__fastcall **)(_QWORD))(*((_QWORD *)a2 + 1) + 32LL))(*(_QWORD *)a2);
      *a4 = PPDResolveUIConflicts(v14, v13, 512, v12) == 0;
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180031dc0  push    rbx
0x180031dc2  push    rbp
0x180031dc3  push    rsi
0x180031dc4  push    rdi
0x180031dc5  push    r14
0x180031dc7  push    r15
0x180031dc9  sub     rsp, 28h
0x180031dcd  mov     rsi, r9
0x180031dd0  mov     edi, r8d
0x180031dd3  mov     rbx, rdx
0x180031dd6  call    ?ResolveConstraintsFromTable@CPrintAbstractHelper@@IEAAJPEAVCPrintCoreConfig@@HPEAH@Z; CPrintAbstractHelper::ResolveConstraintsFromTable(CPrintCoreConfig *,int,int *)
0x180031ddb  mov     r14d, eax
0x180031dde  test    eax, eax
0x180031de0  js      loc_180031EBD
0x180031de6  test    edi, edi
0x180031de8  jz      short loc_180031E54
0x180031dea  mov     rcx, rbx; this
0x180031ded  call    ?GetHelperSettingsFlags@CPrintCoreConfig@@QEBAKXZ; CPrintCoreConfig::GetHelperSettingsFlags(void)
0x180031df2  not     eax
0x180031df4  mov     edi, 1
0x180031df9  and     eax, edi
0x180031dfb  cmp     qword ptr [rbx+10h], 0
0x180031e00  lea     r15d, [rax+1]
0x180031e04  jz      short loc_180031E0C
0x180031e06  lea     rbp, [rbx+1Ch]
0x180031e0a  jmp     short loc_180031E21
0x180031e0c  mov     rax, [rbx+8]
0x180031e10  xor     edx, edx
0x180031e12  mov     rcx, [rbx]
0x180031e15  mov     rax, [rax+8]
0x180031e19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031e1e  mov     rbp, rax
0x180031e21  mov     rcx, [rbx+8]
0x180031e25  mov     rax, [rcx+20h]
0x180031e29  mov     rcx, [rbx]
0x180031e2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031e31  mov     r9d, r15d
0x180031e34  mov     r8d, 200h
0x180031e3a  mov     rdx, rbp
0x180031e3d  mov     rcx, rax
0x180031e40  call    PPDResolveUIConflicts
0x180031e45  test    eax, eax
0x180031e47  jz      short loc_180031E50
0x180031e49  cmp     dword ptr [rsi], 0
0x180031e4c  jnz     short loc_180031E50
0x180031e4e  xor     edi, edi
0x180031e50  mov     [rsi], edi
0x180031e52  jmp     short loc_180031EBD
0x180031e54  cmp     dword ptr [rsi], 0
0x180031e57  jnz     short loc_180031EBD
0x180031e59  mov     rcx, rbx; this
0x180031e5c  call    ?GetHelperSettingsFlags@CPrintCoreConfig@@QEBAKXZ; CPrintCoreConfig::GetHelperSettingsFlags(void)
0x180031e61  mov     ebp, 1
0x180031e66  and     ebp, eax
0x180031e68  add     ebp, 80000001h
0x180031e6e  cmp     qword ptr [rbx+10h], 0
0x180031e73  jz      short loc_180031E7B
0x180031e75  lea     rdi, [rbx+1Ch]
0x180031e79  jmp     short loc_180031E90
0x180031e7b  mov     rax, [rbx+8]
0x180031e7f  xor     edx, edx
0x180031e81  mov     rcx, [rbx]
0x180031e84  mov     rax, [rax+8]
0x180031e88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031e8d  mov     rdi, rax
0x180031e90  mov     rcx, [rbx+8]
0x180031e94  mov     rax, [rcx+20h]
0x180031e98  mov     rcx, [rbx]
0x180031e9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031ea0  mov     r9d, ebp
0x180031ea3  mov     r8d, 200h
0x180031ea9  mov     rdx, rdi
0x180031eac  mov     rcx, rax
0x180031eaf  call    PPDResolveUIConflicts
0x180031eb4  xor     ecx, ecx
0x180031eb6  test    eax, eax
0x180031eb8  setz    cl
0x180031ebb  mov     [rsi], ecx
0x180031ebd  mov     eax, r14d
0x180031ec0  add     rsp, 28h
0x180031ec4  pop     r15
0x180031ec6  pop     r14
0x180031ec8  pop     rdi
0x180031ec9  pop     rsi
0x180031eca  pop     rbp
0x180031ecb  pop     rbx
0x180031ecc  retn
```
