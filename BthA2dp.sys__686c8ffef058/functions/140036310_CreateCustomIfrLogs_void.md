# CreateCustomIfrLogs(void)

- ea: `0x140036310`
- end: `0x140036425`
- name: `?CreateCustomIfrLogs@@YAJXZ`
- size: `277`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14003bc28`

## callees

- `0x140036310`
- `0x14003642c`
- `0x14005c7d0`

## import_xrefs

- `WppRecorder!imp_WppRecorderLogCreate` at `0x1400363d7`
- `WppRecorder!imp_WppRecorderLogCreate` at `0x1400363d7`

## pseudocode

```c
__int64 CreateCustomIfrLogs(void)
{
  __int64 *v0; // rbx
  __int64 v1; // rax
  __int128 *v2; // rcx
  __int64 *v3; // r8
  __int64 v4; // rdx
  __int128 *v5; // rax
  int v6; // edi
  __int128 v8; // [rsp+20h] [rbp-40h] BYREF
  __int64 v9; // [rsp+30h] [rbp-30h]
  __int64 v10; // [rsp+38h] [rbp-28h]
  __int128 v11; // [rsp+40h] [rbp-20h] BYREF
  __int64 v12; // [rsp+50h] [rbp-10h]

  v0 = (__int64 *)aAvdtpCritical;
  while ( 1 )
  {
    v12 = 0;
    v10 = 0x1000000000LL;
    v9 = 0;
    v8 = 0;
    LODWORD(v8) = 56;
    v11 = 0;
    LOBYTE(v11) = 0;
    if ( v0 )
    {
      v1 = 2147483646;
      v2 = &v11;
      v3 = v0;
      v4 = 16;
      do
      {
        if ( !v1 )
          break;
        if ( !*(_BYTE *)v3 )
          break;
        *(_BYTE *)v2 = *(_BYTE *)v3;
        v3 = (__int64 *)((char *)v3 + 1);
        v2 = (__int128 *)((char *)v2 + 1);
        --v1;
        --v4;
      }
      while ( v4 );
      v5 = (__int128 *)((char *)v2 - 1);
      if ( v4 )
        v5 = v2;
      *(_BYTE *)v5 = 0;
    }
    *((_QWORD *)&v8 + 1) = v0[2];
    v12 = 0x200000002LL;
    DWORD1(v8) = 1346650433;
    v6 = imp_WppRecorderLogCreate(WPP_GLOBAL_Control, &v8, v0 + 3);
    if ( v6 < 0 )
      break;
    v0 += 4;
    if ( v0 == qword_14006F270 )
      return 0;
  }
  DeleteCustomIfrLogs();
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140036310  mov     [rsp-8+arg_0], rbx
0x140036315  mov     [rsp-8+arg_8], rdi
0x14003631a  push    rbp
0x14003631b  mov     rbp, rsp
0x14003631e  sub     rsp, 60h
0x140036322  mov     rax, cs:__security_cookie
0x140036329  xor     rax, rsp
0x14003632c  mov     [rbp+var_8], rax
0x140036330  lea     rbx, aAvdtpCritical; "AVDTP-Critical"
0x140036337  xor     eax, eax
0x140036339  xorps   xmm0, xmm0
0x14003633c  mov     [rbp+var_10], rax
0x140036340  movups  [rbp+var_30], xmm0
0x140036344  mov     dword ptr [rbp+var_30+0Ch], 10h
0x14003634b  mov     qword ptr [rbp+var_30], rax
0x14003634f  mov     byte ptr [rbp+var_30+8], al
0x140036352  movups  [rbp+var_40], xmm0
0x140036356  mov     dword ptr [rbp+var_40], 38h ; '8'
0x14003635d  movups  [rbp+var_20], xmm0
0x140036361  mov     byte ptr [rbp+var_20], al
0x140036364  test    rbx, rbx
0x140036367  jz      short loc_1400363A7
0x140036369  mov     eax, 7FFFFFFEh
0x14003636e  lea     rcx, [rbp+var_20]
0x140036372  mov     r8, rbx
0x140036375  mov     edx, 10h
0x14003637a  test    rax, rax
0x14003637d  jz      short loc_140036399
0x14003637f  mov     r9b, [r8]
0x140036382  test    r9b, r9b
0x140036385  jz      short loc_140036399
0x140036387  mov     [rcx], r9b
0x14003638a  inc     r8
0x14003638d  inc     rcx
0x140036390  dec     rax
0x140036393  sub     rdx, 1
0x140036397  jnz     short loc_14003637A
0x140036399  test    rdx, rdx
0x14003639c  lea     rax, [rcx-1]
0x1400363a0  cmovnz  rax, rcx
0x1400363a4  mov     byte ptr [rax], 0
0x1400363a7  mov     eax, [rbx+10h]
0x1400363aa  lea     r8, [rbx+18h]
0x1400363ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400363b5  lea     rdx, [rbp+var_40]
0x1400363b9  mov     dword ptr [rbp+var_40+8], eax
0x1400363bc  mov     eax, [rbx+14h]
0x1400363bf  mov     dword ptr [rbp+var_40+0Ch], eax
0x1400363c2  mov     dword ptr [rbp+var_10], 2
0x1400363c9  mov     dword ptr [rbp+var_10+4], 2
0x1400363d0  mov     dword ptr [rbp+var_40+4], 50444141h
0x1400363d7  call    cs:__imp_imp_WppRecorderLogCreate
0x1400363de  nop     dword ptr [rax+rax+00h]
0x1400363e3  mov     edi, eax
0x1400363e5  test    eax, eax
0x1400363e7  js      short loc_140036401
0x1400363e9  add     rbx, 20h ; ' '
0x1400363ed  lea     rax, qword_14006F270
0x1400363f4  cmp     rbx, rax
0x1400363f7  jnz     loc_140036337
0x1400363fd  xor     eax, eax
0x1400363ff  jmp     short loc_140036408
0x140036401  call    ?DeleteCustomIfrLogs@@YAXXZ; DeleteCustomIfrLogs(void)
0x140036406  mov     eax, edi
0x140036408  mov     rcx, [rbp+var_8]
0x14003640c  xor     rcx, rsp; StackCookie
0x14003640f  call    __security_check_cookie
0x140036414  mov     rbx, [rsp+60h+arg_0]
0x140036419  mov     rdi, [rsp+60h+arg_8]
0x14003641e  add     rsp, 60h
0x140036422  pop     rbp
0x140036423  retn
```
