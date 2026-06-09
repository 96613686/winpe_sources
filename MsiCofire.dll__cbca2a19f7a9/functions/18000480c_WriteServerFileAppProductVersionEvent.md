# WriteServerFileAppProductVersionEvent

- ea: `0x18000480c`
- end: `0x180004a68`
- name: `WriteServerFileAppProductVersionEvent`
- size: `604`
- prototype: `__int64 __usercall@<rax>(PCEVENT_DESCRIPTOR EventDescriptor@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800036f0`

## callees

- `0x180002590`
- `0x18000480c`
- `0x180007040`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x180004a0e`
- `ADVAPI32!EventWrite` at `0x180004a0e`
- `ADVAPI32!EventRegister` at `0x180004958`
- `ADVAPI32!EventRegister` at `0x180004958`

## string_xrefs

- `0x180004a3a`: `MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n`
- `0x180004a31`: `WriteServerFileAppProductVersionEvent`

## pseudocode

```c
__int64 __fastcall WriteServerFileAppProductVersionEvent(
        PCEVENT_DESCRIPTOR EventDescriptor,
        _WORD *a2,
        _WORD *a3,
        _WORD *a4,
        _WORD *a5)
{
  unsigned int v9; // ebx
  REGHANDLE v10; // rcx
  signed int v11; // eax
  int v12; // r9d
  __int64 v13; // r8
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  signed int v17; // eax
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+30h] [rbp-41h] BYREF
  _WORD *v20; // [rsp+40h] [rbp-31h]
  int v21; // [rsp+48h] [rbp-29h]
  int v22; // [rsp+4Ch] [rbp-25h]
  _WORD *v23; // [rsp+50h] [rbp-21h]
  int v24; // [rsp+58h] [rbp-19h]
  int v25; // [rsp+5Ch] [rbp-15h]
  _WORD *v26; // [rsp+60h] [rbp-11h]
  int v27; // [rsp+68h] [rbp-9h]
  int v28; // [rsp+6Ch] [rbp-5h]

  if ( !EventDescriptor )
  {
    v9 = -2147024809;
    DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "WriteServerFileAppProductVersionEvent", 126, -2147024809);
    return v9;
  }
  if ( !a2 )
  {
    v9 = -2147024809;
    DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "WriteServerFileAppProductVersionEvent", 127, -2147024809);
    return v9;
  }
  if ( !*a2 )
  {
    v9 = -2147024809;
    DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "WriteServerFileAppProductVersionEvent", 128, -2147024809);
    return v9;
  }
  if ( !a3 )
  {
    v9 = -2147024809;
    DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "WriteServerFileAppProductVersionEvent", 129, -2147024809);
    return v9;
  }
  if ( !*a3 )
  {
    v9 = -2147024809;
    DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "WriteServerFileAppProductVersionEvent", 130, -2147024809);
    return v9;
  }
  if ( !a4 )
  {
    v9 = -2147024809;
    DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "WriteServerFileAppProductVersionEvent", 131, -2147024809);
    return v9;
  }
  if ( !*a4 )
  {
    v9 = -2147024809;
    DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "WriteServerFileAppProductVersionEvent", 132, -2147024809);
    return v9;
  }
  if ( !a5 )
  {
    v9 = -2147024809;
    DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "WriteServerFileAppProductVersionEvent", 133, -2147024809);
    return v9;
  }
  if ( !*a5 )
  {
    v9 = -2147024809;
    DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "WriteServerFileAppProductVersionEvent", 134, -2147024809);
    return v9;
  }
  v10 = HServerEtwProvider;
  if ( !HServerEtwProvider )
  {
    v11 = EventRegister(&CFR_DM_ETW_PROVIDER, 0, 0, &HServerEtwProvider);
    v9 = v11;
    if ( v11 > 0 )
      v9 = (unsigned __int16)v11 | 0x80070000;
    if ( (v9 & 0x80000000) != 0 )
    {
      v12 = 144;
LABEL_37:
      DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "WriteServerFileAppProductVersionEvent", v12, v9);
      return v9;
    }
    v10 = HServerEtwProvider;
  }
  v13 = -1;
  UserData.Ptr = (ULONGLONG)a2;
  v14 = -1;
  do
    ++v14;
  while ( a2[v14] );
  UserData.Reserved = 0;
  UserData.Size = 2 * v14 + 2;
  v15 = -1;
  v20 = a3;
  do
    ++v15;
  while ( a3[v15] );
  v22 = 0;
  v21 = 2 * v15 + 2;
  v16 = -1;
  v23 = a4;
  do
    ++v16;
  while ( a4[v16] );
  v25 = 0;
  v24 = 2 * v16 + 2;
  v26 = a5;
  do
    ++v13;
  while ( a5[v13] );
  v28 = 0;
  v27 = 2 * v13 + 2;
  v17 = EventWrite(v10, EventDescriptor, 4u, &UserData);
  v9 = v17;
  if ( v17 > 0 )
    v9 = (unsigned __int16)v17 | 0x80070000;
  if ( (v9 & 0x80000000) != 0 )
  {
    v12 = 173;
    goto LABEL_37;
  }
  return v9;
}

```

## disassembly

```asm
0x18000480c  push    rbp
0x18000480e  push    rbx
0x18000480f  push    rsi
0x180004810  push    rdi
0x180004811  push    r12
0x180004813  push    r13
0x180004815  push    r14
0x180004817  push    r15
0x180004819  lea     rbp, [rsp-17h]
0x18000481e  sub     rsp, 88h
0x180004825  mov     rax, cs:__security_cookie
0x18000482c  xor     rax, rsp
0x18000482f  mov     [rbp+4Fh+var_50], rax
0x180004833  xor     r13d, r13d
0x180004836  mov     r15, r9
0x180004839  mov     r14, r8
0x18000483c  mov     rdi, rdx
0x18000483f  mov     r12, rcx
0x180004842  test    rcx, rcx
0x180004845  jnz     short loc_18000485B
0x180004847  mov     eax, 80070057h
0x18000484c  lea     r9d, [rcx+7Eh]
0x180004850  mov     ebx, eax
0x180004852  mov     [rsp+0C0h+var_A0], eax
0x180004856  jmp     loc_180004A31
0x18000485b  test    rdi, rdi
0x18000485e  jnz     short loc_180004874
0x180004860  mov     eax, 80070057h
0x180004865  lea     r9d, [rdi+7Fh]
0x180004869  mov     ebx, eax
0x18000486b  mov     [rsp+0C0h+var_A0], eax
0x18000486f  jmp     loc_180004A31
0x180004874  cmp     [rdx], r13w
0x180004878  jnz     short loc_180004890
0x18000487a  mov     eax, 80070057h
0x18000487f  mov     r9d, 80h
0x180004885  mov     ebx, eax
0x180004887  mov     [rsp+0C0h+var_A0], eax
0x18000488b  jmp     loc_180004A31
0x180004890  test    r14, r14
0x180004893  jnz     short loc_1800048AB
0x180004895  mov     eax, 80070057h
0x18000489a  mov     r9d, 81h
0x1800048a0  mov     ebx, eax
0x1800048a2  mov     [rsp+0C0h+var_A0], eax
0x1800048a6  jmp     loc_180004A31
0x1800048ab  cmp     [r8], r13w
0x1800048af  jnz     short loc_1800048C7
0x1800048b1  mov     eax, 80070057h
0x1800048b6  mov     r9d, 82h
0x1800048bc  mov     ebx, eax
0x1800048be  mov     [rsp+0C0h+var_A0], eax
0x1800048c2  jmp     loc_180004A31
0x1800048c7  test    r15, r15
0x1800048ca  jnz     short loc_1800048E2
0x1800048cc  mov     eax, 80070057h
0x1800048d1  mov     r9d, 83h
0x1800048d7  mov     ebx, eax
0x1800048d9  mov     [rsp+0C0h+var_A0], eax
0x1800048dd  jmp     loc_180004A31
0x1800048e2  cmp     [r9], r13w
0x1800048e6  jnz     short loc_1800048FE
0x1800048e8  mov     eax, 80070057h
0x1800048ed  mov     r9d, 84h
0x1800048f3  mov     ebx, eax
0x1800048f5  mov     [rsp+0C0h+var_A0], eax
0x1800048f9  jmp     loc_180004A31
0x1800048fe  mov     rsi, [rbp+4Fh+arg_20]
0x180004902  test    rsi, rsi
0x180004905  jnz     short loc_18000491D
0x180004907  mov     eax, 80070057h
0x18000490c  mov     r9d, 85h
0x180004912  mov     ebx, eax
0x180004914  mov     [rsp+0C0h+var_A0], eax
0x180004918  jmp     loc_180004A31
0x18000491d  cmp     [rsi], r13w
0x180004921  jnz     short loc_180004939
0x180004923  mov     eax, 80070057h
0x180004928  mov     r9d, 86h
0x18000492e  mov     ebx, eax
0x180004930  mov     [rsp+0C0h+var_A0], eax
0x180004934  jmp     loc_180004A31
0x180004939  mov     rcx, cs:HServerEtwProvider
0x180004940  test    rcx, rcx
0x180004943  jnz     short loc_180004983
0x180004945  lea     r9, HServerEtwProvider; RegHandle
0x18000494c  xor     r8d, r8d; CallbackContext
0x18000494f  xor     edx, edx; EnableCallback
0x180004951  lea     rcx, CFR_DM_ETW_PROVIDER; ProviderId
0x180004958  call    cs:__imp_EventRegister
0x18000495e  mov     ebx, eax
0x180004960  test    eax, eax
0x180004962  jle     short loc_18000496D
0x180004964  movzx   ebx, ax
0x180004967  or      ebx, 80070000h
0x18000496d  test    ebx, ebx
0x18000496f  jns     short loc_18000497C
0x180004971  mov     r9d, 90h
0x180004977  jmp     loc_180004A2D
0x18000497c  mov     rcx, cs:HServerEtwProvider; RegHandle
0x180004983  or      r8, 0FFFFFFFFFFFFFFFFh
0x180004987  mov     [rbp+4Fh+UserData.Ptr], rdi
0x18000498b  mov     rax, r8
0x18000498e  inc     rax
0x180004991  cmp     [rdi+rax*2], r13w
0x180004996  jnz     short loc_18000498E
0x180004998  lea     eax, ds:2[rax*2]
0x18000499f  mov     dword ptr [rbp+4Fh+UserData.0Ch], r13d
0x1800049a3  mov     [rbp+4Fh+UserData.Size], eax
0x1800049a6  mov     rax, r8
0x1800049a9  mov     [rbp+4Fh+var_80], r14
0x1800049ad  inc     rax
0x1800049b0  cmp     [r14+rax*2], r13w
0x1800049b5  jnz     short loc_1800049AD
0x1800049b7  lea     eax, ds:2[rax*2]
0x1800049be  mov     [rbp+4Fh+var_74], r13d
0x1800049c2  mov     [rbp+4Fh+var_78], eax
0x1800049c5  mov     rax, r8
0x1800049c8  mov     [rbp+4Fh+var_70], r15
0x1800049cc  inc     rax
0x1800049cf  cmp     [r15+rax*2], r13w
0x1800049d4  jnz     short loc_1800049CC
0x1800049d6  lea     eax, ds:2[rax*2]
0x1800049dd  mov     [rbp+4Fh+var_64], r13d
0x1800049e1  mov     [rbp+4Fh+var_68], eax
0x1800049e4  mov     [rbp+4Fh+var_60], rsi
0x1800049e8  inc     r8
0x1800049eb  cmp     [rsi+r8*2], r13w
0x1800049f0  jnz     short loc_1800049E8
0x1800049f2  lea     eax, ds:2[r8*2]
0x1800049fa  mov     [rbp+4Fh+var_54], r13d
0x1800049fe  mov     r8d, 4; UserDataCount
0x180004a04  mov     [rbp+4Fh+var_58], eax
0x180004a07  lea     r9, [rbp+4Fh+UserData]; UserData
0x180004a0b  mov     rdx, r12; EventDescriptor
0x180004a0e  call    cs:__imp_EventWrite
0x180004a14  mov     ebx, eax
0x180004a16  test    eax, eax
0x180004a18  jle     short loc_180004A23
0x180004a1a  movzx   ebx, ax
0x180004a1d  or      ebx, 80070000h
0x180004a23  test    ebx, ebx
0x180004a25  jns     short loc_180004A46
0x180004a27  mov     r9d, 0ADh
0x180004a2d  mov     [rsp+0C0h+var_A0], ebx
0x180004a31  lea     r8, aWriteserverfil; "WriteServerFileAppProductVersionEvent"
0x180004a38  xor     ecx, ecx; Level
0x180004a3a  lea     rdx, aMsiCofireError; "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n"
0x180004a41  call    ?DebugPrint@@YAXKPEBDZZ; DebugPrint(ulong,char const *,...)
0x180004a46  mov     eax, ebx
0x180004a48  mov     rcx, [rbp+4Fh+var_50]
0x180004a4c  xor     rcx, rsp; StackCookie
0x180004a4f  call    __security_check_cookie
0x180004a54  add     rsp, 88h
0x180004a5b  pop     r15
0x180004a5d  pop     r14
0x180004a5f  pop     r13
0x180004a61  pop     r12
0x180004a63  pop     rdi
0x180004a64  pop     rsi
0x180004a65  pop     rbx
0x180004a66  pop     rbp
0x180004a67  retn
```
