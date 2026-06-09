# DllCanUnloadNow

- ea: `0x180004820`
- end: `0x180004910`
- name: `DllCanUnloadNow`
- size: `240`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180004820`
- `0x180004930`
- `0x180004ac0`
- `0x180004ad0`
- `0x180004af0`
- `0x180004b00`
- `0x180011c50`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x1800048e6`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180004857`
- `KERNEL32!DecodePointer` at `0x18000489a`
- `KERNEL32!DecodePointer` at `0x18000485e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180004907`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180004865`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  __int64 v0; // rsi
  __int64 v1; // rdi
  unsigned __int64 v2; // rax
  unsigned __int64 v3; // rdi
  unsigned __int64 v4; // rbx
  __int64 v5; // rax
  PVOID v6; // rax
  RTL_SRWLOCK *v7; // r15
  void **v8; // rax
  void *v9; // r14

  v0 = sub_180004930();
  v1 = sub_180004AD0(v0);
  v2 = sub_180004AF0(v0);
  v3 = v1 + 8;
  if ( v3 < v2 )
  {
    v4 = v2;
    do
    {
      if ( *(_QWORD *)v3 )
      {
        if ( (unsigned int)sub_180004AC0(v0) )
        {
          LODWORD(v5) = 1;
          return v5;
        }
        if ( **(_QWORD **)(*(_QWORD *)v3 + 24LL) )
        {
          v7 = (RTL_SRWLOCK *)sub_180004B00(v0);
          AcquireSRWLockExclusive(v7);
          v8 = *(void ***)(*(_QWORD *)v3 + 24LL);
          v9 = *v8;
          if ( *v8 )
            *v8 = 0;
          if ( v7 )
            ReleaseSRWLockExclusive(v7);
          if ( v9 )
          {
            v6 = DecodePointer(v9);
            (*(void (__fastcall **)(PVOID))(*(_QWORD *)v6 + 16LL))(v6);
          }
        }
      }
      v3 += 8LL;
    }
    while ( v3 < v4 );
  }
  return sub_180004AC0(v0) != 0;
}

```

## disassembly

```asm
0x180004820  push    r15
0x180004822  push    r14
0x180004824  push    r13
0x180004826  push    r12
0x180004828  push    rsi
0x180004829  push    rdi
0x18000482a  push    rbp
0x18000482b  push    rbx
0x18000482c  sub     rsp, 28h
0x180004830  call    sub_180004930
0x180004835  mov     rsi, rax
0x180004838  mov     rcx, rax
0x18000483b  call    sub_180004AD0
0x180004840  mov     rdi, rax
0x180004843  mov     rcx, rsi
0x180004846  call    sub_180004AF0
0x18000484b  add     rdi, 8
0x18000484f  cmp     rdi, rax
0x180004852  jnb     short loc_18000486E
0x180004854  mov     rbx, rax
0x180004857  mov     r12, cs:AcquireSRWLockExclusive
0x18000485e  mov     r13, cs:DecodePointer
0x180004865  mov     rbp, cs:ReleaseSRWLockExclusive
0x18000486c  jmp     short loc_1800048B9
0x18000486e  mov     rcx, rsi
0x180004871  call    sub_180004AC0
0x180004876  mov     ecx, eax
0x180004878  xor     eax, eax
0x18000487a  test    ecx, ecx
0x18000487c  setnz   al
0x18000487f  add     rsp, 28h
0x180004883  pop     rbx
0x180004884  pop     rbp
0x180004885  pop     rdi
0x180004886  pop     rsi
0x180004887  pop     r12
0x180004889  pop     r13
0x18000488b  pop     r14
0x18000488d  pop     r15
0x18000488f  retn
0x180004890  mov     eax, 1
0x180004895  jmp     short loc_18000487F
0x180004897  mov     rcx, r14; Ptr
0x18000489a  call    r13 ; DecodePointer
0x18000489d  mov     rcx, [rax]
0x1800048a0  mov     rdx, [rcx+10h]
0x1800048a4  mov     rcx, rax
0x1800048a7  mov     rax, rdx
0x1800048aa  call    cs:__guard_dispatch_icall_fptr
0x1800048b0  add     rdi, 8
0x1800048b4  cmp     rdi, rbx
0x1800048b7  jnb     short loc_18000486E
0x1800048b9  cmp     qword ptr [rdi], 0
0x1800048bd  jz      short loc_1800048B0
0x1800048bf  mov     rcx, rsi
0x1800048c2  call    sub_180004AC0
0x1800048c7  test    eax, eax
0x1800048c9  jnz     short loc_180004890
0x1800048cb  mov     rax, [rdi]
0x1800048ce  mov     rax, [rax+18h]
0x1800048d2  cmp     qword ptr [rax], 0
0x1800048d6  jz      short loc_1800048B0
0x1800048d8  mov     rcx, rsi
0x1800048db  call    sub_180004B00
0x1800048e0  mov     r15, rax
0x1800048e3  mov     rcx, rax; SRWLock
0x1800048e6  call    r12 ; AcquireSRWLockExclusive
0x1800048e9  mov     rax, [rdi]
0x1800048ec  mov     rax, [rax+18h]
0x1800048f0  mov     r14, [rax]
0x1800048f3  test    r14, r14
0x1800048f6  jz      short loc_1800048FF
0x1800048f8  mov     qword ptr [rax], 0
0x1800048ff  test    r15, r15
0x180004902  jz      short loc_180004909
0x180004904  mov     rcx, r15; SRWLock
0x180004907  call    rbp ; ReleaseSRWLockExclusive
0x180004909  test    r14, r14
0x18000490c  jz      short loc_1800048B0
0x18000490e  jmp     short loc_180004897
```
