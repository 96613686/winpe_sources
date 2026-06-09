# SdbInitDatabaseEx

- ea: `0x180002be0`
- end: `0x180002f4a`
- name: `SdbInitDatabaseEx`
- size: `874`
- prototype: ``
- caller_count: `17`
- callee_count: `14`
- tags: `loader_planting`

## callers

- `0x180001ea0`
- `0x180002b38`
- `0x180034170`
- `0x180039ef0`
- `0x18003a6a0`
- `0x18003ae40`
- `0x18003afa4`
- `0x180044140`
- `0x1800445e0`
- `0x180047130`
- `0x1800509c0`
- `0x180050bc0`
- `0x180051234`
- `0x1800517cc`
- `0x180051830`
- `0x180051a00`
- `0x180052f80`

## callees

- `0x180001410`
- `0x18000146c`
- `0x1800016b4`
- `0x180002118`
- `0x180002be0`
- `0x180002f60`
- `0x180003790`
- `0x18000f114`
- `0x1800160c0`
- `0x180018f20`
- `0x180039a5a`
- `0x18004ec04`
- `0x180059175`
- `0x1800591b0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180002c50`
- `ntdll!RtlAllocateHeap` at `0x180002c50`

## string_xrefs

- `0x180002d37`: `Unable to open main database %S`
- `0x180002cb6`: `SdbpResolveInitSdbPath failed to resolve the sdb path [%x]`
- `0x180002e46`: `Unable to open merge stub database %S`

## pseudocode

```c
_WORD *__fastcall SdbInitDatabaseEx(unsigned int a1, _WORD *a2, unsigned __int16 a3)
{
  const WCHAR *v6; // r14
  _WORD *Heap; // rax
  __int64 v8; // rdx
  _WORD *v9; // rbx
  int inited; // eax
  __int64 v12; // rdx
  const wchar_t ****v13; // rsi
  unsigned int v14; // r8d
  __int64 v15; // rax
  int MergeStubPath; // eax
  __int64 v17; // rdx
  const wchar_t ***v18; // rax
  const wchar_t **v19; // rcx
  unsigned int v21; // r8d
  __int64 v22; // rax
  __int64 v23; // rcx
  const WCHAR *v24; // [rsp+40h] [rbp-278h] BYREF
  _WORD *v25; // [rsp+48h] [rbp-270h]
  _WORD *v26; // [rsp+50h] [rbp-268h]
  _WORD *v27; // [rsp+58h] [rbp-260h]
  wchar_t String2; // [rsp+60h] [rbp-258h] BYREF
  char v29[526]; // [rsp+62h] [rbp-256h] BYREF

  LODWORD(v25) = a1;
  String2 = 0;
  memset_0(v29, 0, 0x206u);
  v6 = 0;
  v24 = 0;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x6F8u);
  v9 = Heap;
  v26 = Heap;
  if ( !Heap )
  {
    AslLogCallPrintf(1, "SdbInitDatabaseEx", 554, "Failed to allocate sdb context");
    return 0;
  }
  Heap[292] = a3;
  if ( (a1 & 4) == 0 )
  {
    inited = SdbpResolveInitSdbPath((__int64)&String2, v8, a1, a2, a3);
    if ( inited < 0 )
    {
      AslLogCallPrintf(
        1,
        "SdbInitDatabaseEx",
        569,
        "SdbpResolveInitSdbPath failed to resolve the sdb path [%x]",
        inited);
      v13 = (const wchar_t ****)(v9 + 4);
LABEL_24:
      if ( *v13 )
        SdbCloseDatabaseRead(*v13);
      v23 = *((_QWORD *)v9 + 2);
      if ( v23 )
        SdbCloseDatabaseRead(v23);
      AslFree(NtCurrentPeb()->ProcessHeap, v9);
      if ( v6 )
        AslFree(NtCurrentPeb()->ProcessHeap, v6);
      return 0;
    }
    v14 = 0;
    if ( (a1 & 8) != 0 )
      v14 = 32;
    *((_QWORD *)v9 + 1) = SdbOpenDatabaseEx(&String2, v12, v14);
    v13 = (const wchar_t ****)(v9 + 4);
    v25 = v9 + 4;
    v15 = *((_QWORD *)v9 + 1);
    if ( !v15 )
    {
      AslLogCallPrintf(1, "SdbInitDatabaseEx", 597, "Unable to open main database %S", &String2);
      goto LABEL_24;
    }
    *((_QWORD *)v9 + 7) = v15;
    *((_DWORD *)v9 + 16) = 3;
    *(_OWORD *)(v9 + 20) = *(_OWORD *)(v15 + 28);
    v27 = v9 + 18;
    *((_DWORD *)v9 + 9) |= 1u;
    MergeStubPath = SdbGetMergeStubPath(&v24, &String2);
    if ( MergeStubPath == -1073741772 )
      goto LABEL_31;
    if ( MergeStubPath < 0 )
    {
      AslLogCallPrintf(1, "SdbInitDatabaseEx", 630, "Unable to find merge stub database for %S", &String2);
      v6 = v24;
      goto LABEL_24;
    }
    v18 = *v13;
    if ( *v13 && (v19 = *v18) != 0 && *v19 && wcsicmp_0(*v19, &String2) != 0 )
    {
LABEL_31:
      *((_QWORD *)v9 + 2) = 0;
      v6 = v24;
    }
    else
    {
      v21 = 0;
      if ( (a1 & 0x10) != 0 )
        v21 = 32;
      v6 = v24;
      *((_QWORD *)v9 + 2) = SdbOpenDatabaseEx(v24, v17, v21);
      v22 = *((_QWORD *)v9 + 2);
      if ( !v22 )
      {
        AslLogCallPrintf(1, "SdbInitDatabaseEx", 666, "Unable to open merge stub database %S", &String2);
        goto LABEL_24;
      }
      *((_QWORD *)v9 + 15) = v22;
      *((_DWORD *)v9 + 32) = 3;
      *(_OWORD *)(v9 + 52) = *(_OWORD *)(v22 + 28);
      *((_DWORD *)v9 + 9) |= 4u;
    }
    if ( v6 )
      AslFree(NtCurrentPeb()->ProcessHeap, v6);
  }
  SdbpInitializeMatchers(v9);
  *((_DWORD *)v9 + 138) = SdbpGetBinaryRuntimePlatform(a3);
  SdbpGetCurrentOSKind(v9 + 284);
  return v9;
}

```

## disassembly

```asm
0x180002be0  push    rbx
0x180002be2  push    rsi
0x180002be3  push    rdi
0x180002be4  push    r12
0x180002be6  push    r13
0x180002be8  push    r14
0x180002bea  push    r15
0x180002bec  sub     rsp, 280h
0x180002bf3  mov     rax, cs:__security_cookie
0x180002bfa  xor     rax, rsp
0x180002bfd  mov     [rsp+2B8h+var_48], rax
0x180002c05  movzx   r12d, r8w
0x180002c09  mov     rsi, rdx
0x180002c0c  mov     r13d, ecx
0x180002c0f  mov     dword ptr [rsp+2B8h+var_270], ecx
0x180002c13  mov     [rsp+2B8h+var_288], r8w
0x180002c19  xor     edi, edi
0x180002c1b  mov     [rsp+2B8h+String2], di
0x180002c20  xor     edx, edx; Val
0x180002c22  mov     r8d, 206h; Size
0x180002c28  lea     rcx, [rsp+2B8h+var_256]; void *
0x180002c2d  call    memset_0
0x180002c32  mov     r14d, edi
0x180002c35  mov     [rsp+2B8h+var_278], rdi
0x180002c3a  mov     rcx, gs:60h
0x180002c43  lea     edx, [rdi+8]; Flags
0x180002c46  mov     r8d, 6F8h; Size
0x180002c4c  mov     rcx, [rcx+30h]; HeapHandle
0x180002c50  call    cs:__imp_RtlAllocateHeap
0x180002c56  mov     rbx, rax
0x180002c59  mov     [rsp+2B8h+var_268], rax
0x180002c5e  test    rax, rax
0x180002c61  jnz     short loc_180002C86
0x180002c63  lea     r9, aFailedToAlloca_13; "Failed to allocate sdb context"
0x180002c6a  mov     r8d, 22Ah
0x180002c70  lea     rdx, aSdbinitdatabas_2; "SdbInitDatabaseEx"
0x180002c77  lea     ecx, [rdi+1]
0x180002c7a  call    AslLogCallPrintf
0x180002c7f  xor     eax, eax
0x180002c81  jmp     loc_180002F27
0x180002c86  mov     [rax+248h], r12w
0x180002c8e  test    r13b, 4
0x180002c92  jnz     loc_180002F01
0x180002c98  mov     word ptr [rsp+2B8h+var_298], r12w
0x180002c9e  mov     r9, rsi
0x180002ca1  mov     r8d, r13d
0x180002ca4  lea     rcx, [rsp+2B8h+String2]
0x180002ca9  call    SdbpResolveInitSdbPath
0x180002cae  test    eax, eax
0x180002cb0  jns     short loc_180002CDD
0x180002cb2  mov     dword ptr [rsp+2B8h+var_298], eax
0x180002cb6  lea     r9, aSdbpresolveini_0; "SdbpResolveInitSdbPath failed to resolv"...
0x180002cbd  mov     r8d, 239h
0x180002cc3  lea     rdx, aSdbinitdatabas_2; "SdbInitDatabaseEx"
0x180002cca  mov     ecx, 1
0x180002ccf  call    AslLogCallPrintf
0x180002cd4  lea     rsi, [rbx+8]
0x180002cd8  jmp     loc_180002E6E
0x180002cdd  mov     [rsp+2B8h+var_280], edi
0x180002ce1  test    r13b, 8
0x180002ce5  mov     r8d, edi
0x180002ce8  mov     r15d, 20h ; ' '
0x180002cee  cmovnz  r8d, r15d
0x180002cf2  mov     [rsp+2B8h+var_280], r8d
0x180002cf7  lea     rcx, [rsp+2B8h+String2]
0x180002cfc  call    SdbOpenDatabaseEx
0x180002d01  mov     [rbx+8], rax
0x180002d05  jmp     short loc_180002D26
0x180002d07  mov     rbx, [rsp+2B8h+var_268]
0x180002d0c  mov     qword ptr [rbx+8], 0
0x180002d14  xor     edi, edi
0x180002d16  mov     r14, [rsp+2B8h+var_278]
0x180002d1b  mov     r13d, dword ptr [rsp+2B8h+var_270]
0x180002d20  movzx   r12d, [rsp+2B8h+var_288]
0x180002d26  lea     rsi, [rbx+8]
0x180002d2a  mov     [rsp+2B8h+var_270], rsi
0x180002d2f  mov     rax, [rsi]
0x180002d32  test    rax, rax
0x180002d35  jnz     short loc_180002D49
0x180002d37  lea     r9, aUnableToOpenMa; "Unable to open main database %S"
0x180002d3e  mov     r8d, 255h
0x180002d44  jmp     loc_180002E53
0x180002d49  mov     [rbx+38h], rax
0x180002d4d  mov     dword ptr [rbx+40h], 3
0x180002d54  movups  xmm0, xmmword ptr [rax+1Ch]
0x180002d58  movdqu  xmmword ptr [rbx+28h], xmm0
0x180002d5d  lea     r15, [rbx+24h]
0x180002d61  mov     [rsp+2B8h+var_260], r15
0x180002d66  or      dword ptr [r15], 1
0x180002d6a  lea     rdx, [rsp+2B8h+String2]
0x180002d6f  lea     rcx, [rsp+2B8h+var_278]
0x180002d74  call    SdbGetMergeStubPath
0x180002d79  cmp     eax, 0C0000034h
0x180002d7e  jz      loc_180002EDE
0x180002d84  test    eax, eax
0x180002d86  jns     short loc_180002DBA
0x180002d88  lea     rax, [rsp+2B8h+String2]
0x180002d8d  mov     [rsp+2B8h+var_298], rax
0x180002d92  lea     r9, aUnableToFindMe; "Unable to find merge stub database for "...
0x180002d99  mov     r8d, 276h
0x180002d9f  lea     rdx, aSdbinitdatabas_2; "SdbInitDatabaseEx"
0x180002da6  mov     ecx, 1
0x180002dab  call    AslLogCallPrintf
0x180002db0  mov     r14, [rsp+2B8h+var_278]
0x180002db5  jmp     loc_180002E6E
0x180002dba  mov     rax, [rsi]
0x180002dbd  test    rax, rax
0x180002dc0  jz      short loc_180002DE5
0x180002dc2  mov     rcx, [rax]
0x180002dc5  test    rcx, rcx
0x180002dc8  jz      short loc_180002DE5
0x180002dca  cmp     [rcx], rdi
0x180002dcd  jz      short loc_180002DE5
0x180002dcf  lea     rdx, [rsp+2B8h+String2]; String2
0x180002dd4  mov     rcx, [rcx]; String1
0x180002dd7  call    _wcsicmp_0
0x180002ddc  mov     ecx, edi
0x180002dde  test    eax, eax
0x180002de0  setnz   cl
0x180002de3  jmp     short loc_180002DE7
0x180002de5  mov     ecx, edi
0x180002de7  test    ecx, ecx
0x180002de9  jnz     loc_180002EDE
0x180002def  mov     [rsp+2B8h+var_280], edi
0x180002df3  test    r13b, 10h
0x180002df7  mov     r8d, edi
0x180002dfa  lea     eax, [rcx+20h]
0x180002dfd  cmovnz  r8d, eax
0x180002e01  mov     [rsp+2B8h+var_280], r8d
0x180002e06  mov     r14, [rsp+2B8h+var_278]
0x180002e0b  mov     rcx, r14
0x180002e0e  call    SdbOpenDatabaseEx
0x180002e13  mov     [rbx+10h], rax
0x180002e17  jmp     short loc_180002E3D
0x180002e19  mov     rbx, [rsp+2B8h+var_268]
0x180002e1e  mov     qword ptr [rbx+10h], 0
0x180002e26  xor     edi, edi
0x180002e28  mov     r14, [rsp+2B8h+var_278]
0x180002e2d  movzx   r12d, [rsp+2B8h+var_288]
0x180002e33  mov     rsi, [rsp+2B8h+var_270]
0x180002e38  mov     r15, [rsp+2B8h+var_260]
0x180002e3d  mov     rax, [rbx+10h]
0x180002e41  test    rax, rax
0x180002e44  jnz     short loc_180002EC1
0x180002e46  lea     r9, aUnableToOpenMe; "Unable to open merge stub database %S"
0x180002e4d  mov     r8d, 29Ah
0x180002e53  lea     rax, [rsp+2B8h+String2]
0x180002e58  mov     [rsp+2B8h+var_298], rax
0x180002e5d  lea     rdx, aSdbinitdatabas_2; "SdbInitDatabaseEx"
0x180002e64  mov     ecx, 1
0x180002e69  call    AslLogCallPrintf
0x180002e6e  cmp     [rsi], rdi
0x180002e71  jz      short loc_180002E7B
0x180002e73  mov     rcx, [rsi]
0x180002e76  call    SdbCloseDatabaseRead
0x180002e7b  mov     rcx, [rbx+10h]
0x180002e7f  test    rcx, rcx
0x180002e82  jz      short loc_180002E89
0x180002e84  call    SdbCloseDatabaseRead
0x180002e89  mov     rcx, gs:60h
0x180002e92  mov     rdx, rbx
0x180002e95  mov     rcx, [rcx+30h]
0x180002e99  call    AslFree
0x180002e9e  test    r14, r14
0x180002ea1  jz      loc_180002C7F
0x180002ea7  mov     rcx, gs:60h
0x180002eb0  mov     rdx, r14
0x180002eb3  mov     rcx, [rcx+30h]
0x180002eb7  call    AslFree
0x180002ebc  jmp     loc_180002C7F
0x180002ec1  mov     [rbx+78h], rax
0x180002ec5  mov     dword ptr [rbx+80h], 3
0x180002ecf  movups  xmm0, xmmword ptr [rax+1Ch]
0x180002ed3  movdqu  xmmword ptr [rbx+68h], xmm0
0x180002ed8  or      dword ptr [r15], 4
0x180002edc  jmp     short loc_180002EE7
0x180002ede  mov     [rbx+10h], rdi
0x180002ee2  mov     r14, [rsp+2B8h+var_278]
0x180002ee7  test    r14, r14
0x180002eea  jz      short loc_180002F01
0x180002eec  mov     rcx, gs:60h
0x180002ef5  mov     rdx, r14
0x180002ef8  mov     rcx, [rcx+30h]
0x180002efc  call    AslFree
0x180002f01  mov     rcx, rbx
0x180002f04  call    SdbpInitializeMatchers
0x180002f09  movzx   ecx, r12w
0x180002f0d  call    SdbpGetBinaryRuntimePlatform
0x180002f12  mov     [rbx+228h], eax
0x180002f18  lea     rcx, [rbx+238h]
0x180002f1f  call    SdbpGetCurrentOSKind
0x180002f24  mov     rax, rbx
0x180002f27  mov     rcx, [rsp+2B8h+var_48]
0x180002f2f  xor     rcx, rsp; StackCookie
0x180002f32  call    __security_check_cookie
0x180002f37  add     rsp, 280h
0x180002f3e  pop     r15
0x180002f40  pop     r14
0x180002f42  pop     r13
0x180002f44  pop     r12
0x180002f46  pop     rdi
0x180002f47  pop     rsi
0x180002f48  pop     rbx
0x180002f49  retn
0x18005925c  push    rbp
0x18005925e  sub     rsp, 30h
0x180059262  mov     rbp, rdx
0x180059265  call    ShimExceptionHandler
0x18005926a  nop
0x18005926b  add     rsp, 30h
0x18005926f  pop     rbp
0x180059270  retn
0x180059272  push    rbp
0x180059274  sub     rsp, 30h
0x180059278  mov     rbp, rdx
0x18005927b  call    ShimExceptionHandler
0x180059280  nop
0x180059281  add     rsp, 30h
0x180059285  pop     rbp
0x180059286  retn
```
